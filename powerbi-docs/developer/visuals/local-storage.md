---
title: Power BI Görsellerinde Yerel Depolama API'si
description: Makalede, tarayıcı yerel depolama alanına erişim elde etmek için Power BI Görselleri API'sinin nasıl kullanılacağı açıklanmaktadır
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 01/21/2019
ms.openlocfilehash: e2cb11ea9be85916e6b5557e7933f6a6b5a7159a
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "79380606"
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
**Görselinizin[AppSource](https://appsource.microsoft.com/en-us/marketplace/apps?product=power-bi-visuals)'ta kullanılabilir ve [sertifikalı](https://powerbi.microsoft.com/en-us/documentation/powerbi-custom-visuals-certified/) olması gerektiğini lütfen unutmayın.**
