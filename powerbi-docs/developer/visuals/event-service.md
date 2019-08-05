---
title: Olayları işleme
description: Power BI Görselleri, Power Point/PDF olarak dışarı aktarma için hazır olunduğunu Power BI’a bildirebilir
author: Yarovinsky
ms.author: alexyar
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 46166b3503a770e033b98474fcf9240235296cc2
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425103"
---
# <a name="event-service"></a>Olay hizmeti

Yeni API, işleme esnasında çağrılması gereken üç yöntemden oluşur (başlatıldı, tamamlandı veya başarısız).

İşleme başladığında, özel görsel kodu işlemenin başladığını belirtmek için renderingStarted yöntemini çağırır.

İşleme başarıyla tamamlanırsa, özel görsel kod hemen `renderingFinished` yöntemine çağrı yaparak dinleyicilere görselin görüntüsünün hazır olduğunu bildirir (**başlıca ‘PDF’e aktar’ ve ‘PowerPoint’e aktar’** ).

İşleme esnasında özel görselin başarıyla tamamlanmasını engelleyen bir sorun oluşursa. Özel görsel kodun `renderingFailed` yöntemini arayıp dinleyiciye işleme sürecinin tamamlanmadığını bildirmesi gerekir. Bu yöntem, hatanın sebebine yönelik isteğe bağlı bir dize de sağlar.

## <a name="usage"></a>Kullanım

```typescript
export interface IVisualHost extends extensibility.IVisualHost {
    eventService: IVisualEventService ;
}

/**
 * An interface for reporting rendering events
 */
export interface IVisualEventService {
    /**
     * Should be called just before the actual rendering was started. 
     * Usually at the very start of the update method.
     *
     * @param options - the visual update options received as update parameter
     */
    renderingStarted(options: VisualUpdateOptions): void;

    /**
     * Shoudl be called immediately after finishing successfull rendering.
     * 
     * @param options - the visual update options received as update parameter
     */
    renderingFinished(options: VisualUpdateOptions): void;

    /**
     * Called when rendering failed with optional reason string
     * 
     * @param options - the visual update options received as update parameter
     * @param reason - the option failure reason string
     */
    renderingFailed(options: VisualUpdateOptions, reason?: string): void;
}
```

### <a name="simple-sample-the-visual-hasnt-any-animations-on-rendering"></a>Basit Örnek. Görselin işlemeye yönelik animasyonu bulunmuyor

```typescript
    export class Visual implements IVisual {
        ...
        private events: IVisualEventService;
        ...

        constructor(options: VisualConstructorOptions) {
            ...
            this.events = options.host.eventService;
            ...
        }

        public update(options: VisualUpdateOptions) {
            this.events.renderingStarted(options);
            ...
            this.events.renderingFinished(options);
        }
```

### <a name="sample-the-visual-with-animation"></a>Örnek. Animasyonlu görsel

Görselin işlemeye yönelik animasyonu veya asenkron işlevleri varsa, animasyondan sonra veya asenkron işlevin içinde `renderingFinished` işlevi çağrılmalıdır.

```typescript
    export class Visual implements IVisual {
        ...
        private events: IVisualEventService;
        private element: HTMLElement;
        ...

        constructor(options: VisualConstructorOptions) {
            ...
            this.events = options.host.eventService;
            this.element = options.element;
            ...
        }

        public update(options: VisualUpdateOptions) {
            this.events.renderingStarted(options);
            ...
            // read more https://github.com/d3/d3-transition/blob/master/README.md#transition_end
            d3.select(this.element).transition().duration(100).style("opacity","0").end().then(() => {
                // renderingFinished called after transition end
                this.events.renderingFinished(options);
            });
        }
```

## <a name="rendering-events-for-visual-certification"></a>Görsel sertifika için olayları işleme

Görsel ile olayları işleme desteği, görsellere yönelik sertifikasyonun gereksinimlerinden biridir. [Sertifikasyon gereksinimleri](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified?#certification-requirements) hakkında daha fazla bilgi edinin
