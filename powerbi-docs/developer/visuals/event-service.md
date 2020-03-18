---
title: Power BI görsellerinde olayları işleme
description: Power BI görselleri, PowerPoint’e veya PDF’ye dışarı aktarmak için hazır olduklarını Power BI’a bildirebilir.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 06/18/2019
ms.openlocfilehash: c54aaa92f3463ce1102866c8d3b69532c8b25cf7
ms.sourcegitcommit: 6bbc3d0073ca605c50911c162dc9f58926db7b66
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79380261"
---
# <a name="render-events-in-power-bi-visuals"></a>Power BI görsellerinde olayları işleme

Yeni API, işleme sırasında çağrılması gereken üç yöntemden (`started`, `finished` veya `failed`) oluşur.

İşleme başladığında Power BI görsel kodu işlemenin başlatıldığını belirtmek için `renderingStarted` yöntemini çağırır.

İşleme başarıyla tamamlanırsa, Power BI görsel kodu hemen `renderingFinished` yöntemini çağırarak dinleyicilere (öncelikli olarak *PDF’ye aktar* ve *PowerPoint’e aktar*) görselin görüntüsünün hazır olduğunu bildirir.

Bu işlem sırasında sorun oluşursa Power BI görselinin başarıyla işlenmesi engellenir. İşlemenin tamamlanmadığını dinleyicilere bildirmek için Power BI görsel kodunun `renderingFailed` yöntemini çağırması gerekir. Bu yöntem hatanın nedenini belirtmek üzere isteğe bağlı bir dize de sağlar.

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
     * Should be called just before the actual rendering starts, 
     * usually at the start of the update method
     *
     * @param options - the visual update options received as an update parameter
     */
    renderingStarted(options: VisualUpdateOptions): void;

    /**
     * Should be called immediately after rendering finishes successfully
     * 
     * @param options - the visual update options received as an update parameter
     */
    renderingFinished(options: VisualUpdateOptions): void;

    /**
     * Called when rendering fails, with an optional reason string
     * 
     * @param options - the visual update options received as an update parameter
     * @param reason - the optional failure reason string
     */
    renderingFailed(options: VisualUpdateOptions, reason?: string): void;
}
```

### <a name="sample-the-visual-displays-no-animations"></a>Örnek: Görsel hiç animasyon görüntülemiyor

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

### <a name="sample-the-visual-displays-animations"></a>Örnek: Görsel animasyonları görüntülüyor

Görselin işlenecek animasyonları veya zaman uyumsuz işlevleri varsa, animasyondan sonra veya zaman uyumsuz işlevin içinde `renderingFinished` yöntemi çağrılmalıdır.

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
            // Learn more at https://github.com/d3/d3-transition/blob/master/README.md#transition_end
            d3.select(this.element).transition().duration(100).style("opacity","0").end().then(() => {
                // renderingFinished called after transition end
                this.events.renderingFinished(options);
            });
        }
```

## <a name="rendering-events-for-visual-certification"></a>Görsel sertifika için olayları işleme

Görsel sertifikanın gereksinimlerinden biri, görsel tarafından olayları işleme desteğidir. Daha fazla bilgi için bkz. [sertifika gereksinimleri](power-bi-custom-visuals-certified.md#certification-requirements).