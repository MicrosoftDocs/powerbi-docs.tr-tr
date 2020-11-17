---
title: Power BI’dan daha fazla veri getirme
description: Bu makalede Power BI görselleri için büyük veri kümelerini parçalı olarak getirmeyi etkinleştirme işlemi açıklanır.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: how-to
ms.date: 06/18/2019
ms.openlocfilehash: b8be5b68603f818e26e7f731e4f163bc626b5053
ms.sourcegitcommit: 132b3f6ba6d2b1948ddc15969d64cf629f7fb280
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/11/2020
ms.locfileid: "94483708"
---
# <a name="fetch-more-data-from-power-bi"></a>Power BI’dan daha fazla veri getirme

Bu makalede `fetchMoreData` yöntemi kullanılarak nasıl 30 KB olan veri noktası sınırını atlayıp daha fazla veri yüklenebileceği açıklanır. Bu yaklaşım öbekler halinde veri sağlar. Performansı artırmak için öbek boyutunu kullanım örneğinize uyacak şekilde yapılandırabilirsiniz.

## <a name="limitations-of-fetchmoredata"></a>fetchMoreData için geçerli sınırlamalar

* Pencere boyutu 2 ile 30.000 arasında olabilir.
* Veri görünümü toplam satır sayısı 1.048.576 satırla sınırlanmıştır.
* Segment toplama modunda veri görünümü bellek boyutu 100 MB ile sınırlıdır.

## <a name="enable-a-segmented-fetch-of-large-datasets"></a>Büyük veri kümelerinde parçalı olarak getirmeyi etkinleştirme

`dataview` segment modunda, görselin *capabilities.json* dosyasında gerekli `dataViewMapping` öğesine yönelik olarak `dataReductionAlgorithm` için bir pencere boyutu tanımlarsınız. `count`, her güncelleştirmede `dataview` öğesine eklenebilecek yeni veri satırı sayısını sınırlandıran pencere boyutunu belirler.

Aşağıdaki kodu *capabilities.json* dosyasına ekleyin:

```typescript
"dataViewMappings": [
    {
        "table": {
            "rows": {
                "for": {
                    "in": "values"
                },
                "dataReductionAlgorithm": {
                    "window": {
                        "count": 100
                    }
                }
            }
    }
]
```

Yeni segmentler mevcut `dataview` öğesine eklendi ve bir `update` çağrısı olarak görsele sağlandı.

## <a name="usage-in-the-power-bi-visual"></a>Power BI görselinde kullanım

Power BI'da `fetchMoreData` öğesini varsayılan segment toplama modunda veya artımlı güncelleştirmeler modunda kullanabilirsiniz. 

### <a name="using-segments-aggregation-mode-default"></a>Segment toplama modunu kullanma (varsayılan)

Bu modda görsel için sağlanan veri görünümünde önceki tüm `fetchMoreData requests` öğelerine ait verilerin toplamı bulunur. Bu nedenle her güncelleştirmeden sonra veri görünümü boyutunun artması beklenir. Örneğin toplam 100.000 satır bekleniyorsa ve pencere boyutu 10.000 olarak ayarlanmışsa ilk güncelleştirme veri görünümünde 10.000 satır, ikinci güncelleştirme veri görünümünde 20.000 satır olacak ve bu şekilde devam edecektir.

Bu modu seçmek için `fetchMoreData` çağrısının `aggregateSegments = true` ile yapılması gerekir.

`dataView.metadata.segment` öğesinin var olup olmadığını denetleyerek verilerin var olup olmadığını belirleyebilirsiniz:

```typescript
    public update(options: VisualUpdateOptions) {
        const dataView = options.dataViews[0];
        console.log(dataView.metadata.segment);
        // output: __proto__: Object
    }
```

Ayrıca `options.operationKind` öğesini denetleyerek bunu ilk güncelleştirme mi yoksa sonraki bir güncelleştirme mi olduğunu da görebilirsiniz. Aşağıdaki kodda `VisualDataChangeOperationKind.Create` ilk segmente, `VisualDataChangeOperationKind.Append` ise sonraki segmentlere işaret eder.

Örnek bir uygulama olarak aşağıdaki kod parçacığına bakın:

```typescript
// CV update implementation
public update(options: VisualUpdateOptions) {
    // indicates this is the first segment of new data.
    if (options.operationKind == VisualDataChangeOperationKind.Create) {

    }

    // on second or subsequent segments:
    if (options.operationKind == VisualDataChangeOperationKind.Append) {

    }

    // complete update implementation
}
```

Ayrıca burada gösterildiği gibi UI olay işleyicisi olarak `fetchMoreData` yöntemini de çağırabilirsiniz:

```typescript
btn_click(){
{
    // check if more data is expected for the current data view
    if (dataView.metadata.segment) {
        //request for more data if available; as a response, Power BI will call update method
        let request_accepted: bool = this.host.fetchMoreData(true);
        // handle rejection
        if (!request_accepted) {
            // for example, when the 100 MB limit has been reached
        }
    }
}
```

`this.host.fetchMoreData` yöntemi çağrısına yanıt olarak, Power BI yeni veri parçasıyla görselin `update` yöntemini çağırır.

> [!NOTE]
> İstemci bellek kısıtlamalarından kaçınmak için Power BI şu anda getirilen verileri toplam 100 MB ile sınırlandırır. `fetchMoreData()`, `false` döndürdüğünde sınıra ulaşıldığını anlayabilirsiniz.

### <a name="using-incremental-updates-mode"></a>Artımlı güncelleştirme modunu kullanma

Bu modda görsele sağlanan veri görünümünde yalnızca artımlı veriler bulunur. Bu nedenle veri görünümü boyutu, tanımlanmış pencere boyutunu aşmaz. Örneğin 101.000 satır bekleniyorsa ve pencere boyutu 10.000 olarak ayarlanmışsa görsel, veri görünümü boyutu 10.000 olan 10 güncelleştirme ile veri görünümü boyutu 1.000 olan tek bir güncelleştirme alır.

Bu modu seçmek için `fetchMoreData` çağrısının `aggregateSegments = false` ile yapılması gerekir.

`dataView.metadata.segment` öğesinin var olup olmadığını denetleyerek verilerin var olup olmadığını belirleyebilirsiniz:

```typescript
    public update(options: VisualUpdateOptions) {
        const dataView = options.dataViews[0];
        console.log(dataView.metadata.segment);
        // output: __proto__: Object
    }
```

Ayrıca `options.operationKind` öğesini denetleyerek bunu ilk güncelleştirme mi yoksa sonraki bir güncelleştirme mi olduğunu da görebilirsiniz. Aşağıdaki kodda `VisualDataChangeOperationKind.Create` ilk parçaya ve `VisualDataChangeOperationKind.Segment` sonraki parçalara işaret eder.

Örnek bir uygulama olarak aşağıdaki kod parçacığına bakın:

```typescript
// CV update implementation
public update(options: VisualUpdateOptions) {
    // indicates this is the first segment of new data.
    if (options.operationKind == VisualDataChangeOperationKind.Create) {

    }

    // on second or subsequent segments:
    if (options.operationKind == VisualDataChangeOperationKind.Segment) {
        
    }

    // skip overlapping rows 
    const rowOffset = (dataView.table['lastMergeIndex'] === undefined) ? 0 : dataView.table['lastMergeIndex'] + 1;

    // Process incoming data
    for (var i = rowOffset; i < dataView.table.rows.length; i++) {
        var val = <number>(dataView.table.rows[i][0]); // Pick first column               
            
     }
     
    // complete update implementation
}
```

Ayrıca burada gösterildiği gibi UI olay işleyicisi olarak `fetchMoreData` yöntemini de çağırabilirsiniz:

```typescript
btn_click(){
{
    // check if more data is expected for the current data view
    if (dataView.metadata.segment) {
        //request for more data if available; as a response, Power BI will call update method
        let request_accepted: bool = this.host.fetchMoreData(false);
        // handle rejection
        if (!request_accepted) {
            // for example, when the 100 MB limit has been reached
        }
    }
}
```

`this.host.fetchMoreData` yöntemi çağrısına yanıt olarak, Power BI yeni veri parçasıyla görselin `update` yöntemini çağırır.

> [!NOTE]
> Farklı güncelleştirmeler arasındaki veri görünümleri verileri çoğunlukla dışlayıcı olsa da birbirini takip eden veri görünümleri arasında çakışmalar olacaktır.
> Tablo ve kategorik veri eşleme için ilk N veri görünümü satırında önceki veri görünümünden kopyalanan verilerin bulunması beklenir.
> N değeri şu şekilde belirlenebilir: `(dataView.table['lastMergeIndex'] === undefined) ? 0 : dataView.table['lastMergeIndex'] + 1`