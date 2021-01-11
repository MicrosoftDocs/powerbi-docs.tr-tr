---
title: Daha iyi tümleşik BI içgörüleri için, Power BI tümleşik analizlerinde Power BI Görselleri Yerel Depolama Alanı API'si
description: Makalede yerel depolama alanına göz atmak üzere erişim almak için Power BI Görselleri API'sinin kullanılması anlatılmaktadır. Power BI tümleşik analiz kullanarak daha iyi tümleşik BI içgörüleri elde edin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 01/21/2019
ms.openlocfilehash: abec68c5622d3dcd96746148ed7a6da4f06c8ec0
ms.sourcegitcommit: eeaf607e7c1d89ef7312421731e1729ddce5a5cc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2021
ms.locfileid: "97888202"
---
# <a name="local-storage-api"></a>Yerel Depolama API’si

Yerel depolama API’si, özel bir görselin, konağın cihazın depolama alanından veri kaydetmesini veya yüklemesini istemek için kullanabileceği bir API’dir. Farklı görsel türler arasında depolama erişimi birbirinden ayrıldığı için yalıtılmıştır.

## <a name="sample"></a>Örnek

Güncelleştirme yöntemi her çağrıldığında özel görselin bir sayacı artırması gerekiyorsa ancak her görsel başlangıcında sayaç değerinin korunması ve sıfırlanmaması gerekiyorsa:

```typescript
export class Visual implements IVisual {
        // ...
        private updateCountName: string = 'updateCount';
        private updateCount: number;
        private storage: ILocalVisualStorageService;
        // ...

        constructor(options: VisualConstructorOptions) {
            // ...
            this.storage = options.host.storageService;
            // ...

            this.storage.get(this.updateCountName).then(count =>
            {
                this.updateCount = +count;
            })
            .catch(() =>
            {
                this.updateCount = 0;
                this.storage.set(this.updateCountName, this.updateCount.toString());
            });
            // ...
        }

        public update(options: VisualUpdateOptions) {
            // ...
            this.updateCount++;
            this.storage.set(this.updateCountName, this.updateCount.toString());
            // ...
        }
}
```

## <a name="known-limitations-and-issues"></a>Bilinen sınırlamalar ve sorunlar

Yerel Depolama API’si, Power BI görselleri için varsayılan olarak etkin değildir. Power BI görseliniz için etkinleştirmek isterseniz Power BI görselleri Desteği’ne istek gönderin `pbicvsupport@microsoft.com`.  
**Görselinizin [AppSource](https://appsource.microsoft.com/en-us/marketplace/apps?product=power-bi-visuals)'ta kullanılabilir ve [sertifikalı](https://powerbi.microsoft.com/en-us/documentation/powerbi-custom-visuals-certified/) olması gerektiğini lütfen unutmayın.**
