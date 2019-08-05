---
title: Daha fazla veri getirme
description: Power BI Görselleri için büyük veri kümelerini kesimli bir şekilde getirmeyi etkinleştirme
author: AviSander
ms.author: asander
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: bc8ff673927fd66bf44164e4e9950c279b98c6c1
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425080"
---
# <a name="fetch-more-data-from-power-bi"></a>Power BI’dan daha fazla veri getirme

30 binlik veri noktası sabit sınırını aşmak için daha fazla veri API’si yükleyin. Verileri öbekler halinde getirir. Öbek boyutu, performansı kullanım durumuna göre geliştirmek için yapılandırılabilir.  

## <a name="enable-segmented-fetch-of-large-datasets"></a>Büyük veri kümelerini kesimli bir şekilde getirmeyi etkinleştirme

`dataview` segment modu için, gereken dataViewMapping için görselin `capabilities.json` öğesindeki “pencere” dataReductionAlgorithm değerini tanımlayın.
`count`, her güncelleştirmede `dataview` öğesine eklenen yeni veri satırı sayısını sınırlandıran pencere boyutunu belirler.

capabilities.json dosyasına eklenecek

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

## <a name="usage-in-the-custom-visual"></a>Özel görselde kullanım

Verilerin bulunup bulunmadığının göstergeleri, `dataView.metadata.segment` öğesinin varlığı denetlenerek belirlenebilir:

```typescript
    public update(options: VisualUpdateOptions) {
        const dataView = options.dataViews[0];
        console.log(dataView.metadata.segment);
        // output: __proto__: Object
    }
```

`options.operationKind` öğesini denetleyerek, bunun birinci mi yoksa sonraki güncelleştirme mi olduğunu denetlemek de mümkündür.

`VisualDataChangeOperationKind.Create` birinci segment, `VisualDataChangeOperationKind.Append` de sonraki segmentler anlamına gelir.

Örnek uygulama için aşağıdaki kod parçacığına bakın:

```typescript
// CV update implementation
public update(options: VisualUpdateOptions) {
    // indicates this is the first segment of new data.
    if (options.operationKind == VisualDataChangeOperationKind.Create) {

    }

    // on second or subesquent segments:
    if (options.operationKind == VisualDataChangeOperationKind.Append) {

    }

    // complete update implementation
}
```

`fetchMoreData` yöntemi, bir kullanıcı arabirimi olay işleyicisinden de çağrılabilir

```typescript
btn_click(){
{
    // check if more data is expected for the current dataview
    if (dataView.metadata.segment) {
        //request for more data if available, as resopnce Power BI will call update method
        let request_accepted: bool = this.host.fetchMoreData();
        // handle rejection
        if (!request_accepted) {
            // for example when the 100 MB limit has been reached
        }
    }
}
```

Power BI, `this.host.fetchMoreData` öğesine çağrı yöntemine yanıt olarak yeni veri segmenti ile görselin `update` yöntemine çağrı yapar.

> [!NOTE]
> Power BI, istemci belleği kısıtlamalarını önlemek için getirilen verilerin toplamını **100 MB** ile sınırlar. fetchMoreData() ‘false’ olarak döndürdüğünde bu sınıra ulaşıldığını tespit edebilirsiniz.*
