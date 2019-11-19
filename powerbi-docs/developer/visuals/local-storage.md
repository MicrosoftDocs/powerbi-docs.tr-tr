---
title: Power BI Görsellerinde Yerel Depolama API'si
description: Makalede, tarayıcı yerel depolama alanına erişim elde etmek için Power BI Görselleri API'sinin nasıl kullanılacağı açıklanmaktadır
author: uve
ms.author: v-grniki
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 10/31/2019
ms.openlocfilehash: f69a3c8928b8079f79b8a6dd5f5b132235a7089c
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73879898"
---
# <a name="local-storage-api"></a>Yerel Depolama API’si

Yerel depolama API'si, özel bir görselin, konağın cihazın depolama alanından veri kaydetmesini veya yüklemesini istemek için kullanabileceği bir API'dir. Farklı görsel türler arasında depolama erişimi birbirinden ayrıldığı için yalıtılmıştır.

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

Yerel Depolama API'si, Özel Görseller için varsayılan olarak etkin değildir. Özel Görseliniz için etkinleştirmek isterseniz lütfen Power BI Özel Görselleri Desteği’ne istek gönderin `pbicvsupport@microsoft.com`
