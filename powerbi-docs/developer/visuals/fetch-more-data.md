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
ms.openlocfilehash: 6d51a27bc5c0f18b7f784395dedd58813bfffbc0
ms.sourcegitcommit: 6bbc3d0073ca605c50911c162dc9f58926db7b66
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79380698"
---
# <a name="fetch-more-data-from-power-bi"></a>Power BI’dan daha fazla veri getirme

Bu makalede nasıl 30 KB olan veri noktası sınırını atlayıp daha fazla veri yüklenebileceği açıklanır. Bu yaklaşım öbekler halinde veri sağlar. Performansı artırmak için öbek boyutunu kullanım örneğinize uyacak şekilde yapılandırabilirsiniz.  

## <a name="enable-a-segmented-fetch-of-large-datasets"></a>Büyük veri kümelerinde parçalı olarak getirmeyi etkinleştirme

`dataview` parçalı modunda, görselin *capabilities.json* dosyasında gerekli dataViewMapping’e yönelik olarak dataReductionAlgorithm için bir pencere boyutu tanımlarsınız. `count`, her güncelleştirmede `dataview` öğesine eklenebilecek yeni veri satırı sayısını sınırlandıran pencere boyutunu belirler.

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

`dataView.metadata.segment` öğesinin var olup olmadığını denetleyerek verilerin var olup olmadığını belirleyebilirsiniz:

```typescript
    public update(options: VisualUpdateOptions) {
        const dataView = options.dataViews[0];
        console.log(dataView.metadata.segment);
        // output: __proto__: Object
    }
```

Ayrıca `options.operationKind` öğesini denetleyerek bunu ilk güncelleştirme mi yoksa sonraki bir güncelleştirme mi olduğunu da görebilirsiniz. Aşağıdaki kodda `VisualDataChangeOperationKind.Create` ilk parçaya ve `VisualDataChangeOperationKind.Append` sonraki parçalara işaret eder.

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
        let request_accepted: bool = this.host.fetchMoreData();
        // handle rejection
        if (!request_accepted) {
            // for example, when the 100 MB limit has been reached
        }
    }
}
```

`this.host.fetchMoreData` yöntemi çağrısına yanıt olarak, Power BI yeni veri parçasıyla görselin `update` yöntemini çağırır.

> [!NOTE]
> İstemci bellek kısıtlamalarından kaçınmak için Power BI şu anda getirilen verileri toplam 100 MB ile sınırlandırır. fetchMoreData() `false` döndürdüğünde sınıra ulaşıldığını anlayabilirsiniz.
