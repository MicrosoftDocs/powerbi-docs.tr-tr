---
title: Power BI görselleri etkileşim yardımcı programları
description: Makalede etkileşim yardımcı programlarını kullanarak Power BI görsellerine seçim ekleme açıklanır
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
manager: rkarlin
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: be7a708dfcc6ebc40c62a1a9075e2cbf134363b1
ms.sourcegitcommit: 8e3d53cf971853c32eff4531d2d3cdb725a199af
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/04/2020
ms.locfileid: "76818698"
---
# <a name="microsoft-power-bi-visuals-interactivity-utils"></a>Microsoft Power BI görselleri etkileşim yardımcı programları

InteractivityUtils Power BI özel görsellerinde çapraz seçim ve çapraz filtrelemenin basitleştirilmesine yönelik bir işlev ve sınıf kümesidir.

## <a name="installation"></a>Yükleme

> [!NOTE]
> powerbi-visuals-tools'un eski sürümlerini (3.x.x'ten düşük bir sürüm numarası) kullanmaya devam ediyorsanız, araçların yeni sürümünü (3.x.x) yükleyin.

> [!IMPORTANT]
> Etkileşim yardımcı programlarının yeni güncelleştirmeleri yalnızca araçların en son sürümünü destekler. [En son araçlarla kullanmak üzere görsel kodunuzu nasıl güncelleştireceğiniz hakkında daha fazla bilgi edinin](migrate-to-new-tools.md)

Paketi yüklemek için geçerli özel görselinizin dizininde aşağıdaki komutu çalıştırmalısınız:

```bash
npm install powerbi-visuals-utils-interactivityutils --save
```

Sürüm 3.0 veya üzerinde, bağımlılıkları çözmek için ```powerbi-models``` yüklemeniz de gerekir.

```bash
npm install powerbi-models --save
```

Etkileşim yardımcı programlarını kullanmak için görselin kaynak kodunda gerekli bileşeni içeri aktarmalısınız.

```typescript
import { interactivitySelectionService } from "powerbi-visuals-utils-interactivityutils";
```

### <a name="including-css-artifacts-to-the-custom-visual"></a>Özel görsele CSS yapıtlarını ekleme

Paketi özel görsellerinizle kullanabilmeniz için şu CSS dosyasını `your.less` dosyasına aktarmanız gerekir:

`node_modules/powerbi-visuals-utils-interactivityutils/lib/index.css`

Sonuç olarak şu dosya yapısına sahip olursunuz:

```less
@import (less) "node_modules/powerbi-visuals-utils-interactivityutils/lib/index.css";
```

> [!NOTE]
> Power BI Görsel Araçları dış CSS kurallarını sarmaladığından, .css dosyasını .less dosyası olarak eklemeniz gerekir.

## <a name="usage"></a>Kullanım

### <a name="define-interface-for-data-points"></a>Veri noktaları için arabirimi tanımlama

Genellikle veri noktaları seçimler ve değerler içerir. Arabirim, `SelectableDataPoint` arabirimini genişletir. `SelectableDataPoint` zaten özellikleri içerir:

```typescript
  /** Flag for identifying that data point was selected */
  selected: boolean;
  /** Identity for identifying the selectable data point for selection purposes */
  identity: powerbi.extensibility.ISelectionId;
  /**
   * A specific identity for when data points exist at a finer granularity than
   * selection is performed.  For example, if your data points should select based
   * only on series even if they exist as category/series intersections.
   */
  specificIdentity?: powerbi.extensibility.ISelectionId;
```

Etkileşim yardımcı programlarını kullanmanın ilk adımı, etkileşim yardımcı programlarının örneğini oluşturmak ve nesneyi görselin özelliği olarak kaydetmektir

```typescript
export class Visual implements IVisual {
  // ...
  private interactivity: interactivityBaseService.IInteractivityService<VisualDataPoint>;
  // ...
  constructor(options: VisualConstructorOptions) {
      // ...
      this.interactivity = interactivitySelectionService.createInteractivitySelectionService(this.host);
      // ...
  }
}
```

```typescript
import { interactivitySelectionService } from "powerbi-visuals-utils-interactivityutils";

export interface VisualDataPoint extends interactivitySelectionService.SelectableDataPoint {
    value: powerbi.PrimitiveValue;
}
```

İkinci adım temel davranış sınıfını genişletmektir:

> [!NOTE]
> BaseBehavior, [etkileşim yardımcı programlarının 5.6.x sürümünde](https://www.npmjs.com/package/powerbi-visuals-utils-interactivityutils/v/5.6.0) kullanıma sunulmuştur. Eski sürümü kullanıyorsanız, davranış sınıfını aşağıdaki örnekten oluşturun (`BaseBehavior` sınıfı aynıdır):

Davranış sınıfının seçenekleri için arabirimi tanımlayın:

```typescript
import { SelectableDataPoint } from "./interactivitySelectionService";

import {
    IBehaviorOptions,
    BaseDataPoint
} from "./interactivityBaseService";

export interface BaseBehaviorOptions<SelectableDataPointType extends BaseDataPoint> extends IBehaviorOptions<SelectableDataPointType> {
    /** D3 selection object of main elements on the chart */
    elementsSelection: Selection<any, SelectableDataPoint, any, any>;
    /** D3 selection object of some element on backgroup to hadle click of reset selection */
    clearCatcherSelection: d3.Selection<any, any, any, any>;
}
```

`visual behavior` için sınıfı tanımlayın. Sınıf `click`, `contextmenu` fare olaylarının işlenmesinden sorumludur.
Kullanıcı veri öğelerine tıkladığında, görsel veri noktalarını seçmek için seçim işleyicisini çağırır. Kullanıcı görselin arka plan öğesine tıklarsa, seçimi temizleme işleyicisini çağırır. Sınıfın bunlara karşılık gelen şu yöntemleri vardır: `bindClick`, `bindClearCatcher`, `bindContextMenu`.

```typescript
export class Behavior<SelectableDataPointType extends BaseDataPoint> implements IInteractiveBehavior {
    /** D3 selection object of main elements on the chart */
    protected options: BaseBehaviorOptions<SelectableDataPointType>;
    protected selectionHandler: ISelectionHandler;

    protected bindClick() {
      // ...
    }

    protected bindClearCatcher() {
      // ...
    }

    protected bindContextMenu() {
      // ...
    }

    public bindEvents(
        options: BaseBehaviorOptions<SelectableDataPointType>,
        selectionHandler: ISelectionHandler): void {
      // ...
    }

    public renderSelection(hasSelection: boolean): void {
      // ...
    }
}
```

Öte yandan `BaseBehavior` sınıfını genişletebilirsiniz:

```typescript
import powerbi from "powerbi-visuals-api";
import { interactivitySelectionService, baseBehavior } from "powerbi-visuals-utils-interactivityutils";

export interface VisualDataPoint extends interactivitySelectionService.SelectableDataPoint {
    value: powerbi.PrimitiveValue;
}

export class Behavior extends baseBehavior.BaseBehavior<VisualDataPoint> {
  // ...
}
```

Öğelere tıklamayı işlemek için D3 seçin nesnesinin `on` yöntemini çağırın (elementsSelection ve clearCatcherSelection için de):

```typescript
protected bindClick() {
  const {
      elementsSelection
  } = this.options;

  elementsSelection.on("click", (datum) => {
      const mouseEvent: MouseEvent = getEvent() as MouseEvent || window.event as MouseEvent;
      mouseEvent && this.selectionHandler.handleSelection(
          datum,
          mouseEvent.ctrlKey);
  });
}
```

Seçim yöneticisinin `showContextMenu` yöntemini çağırmak üzere, `contextmenu` için benzer bir işleyici ekleyin:

```typescript
protected bindContextMenu() {
    const {
        elementsSelection
    } = this.options;

    elementsSelection.on("contextmenu", (datum) => {
        const event: MouseEvent = (getEvent() as MouseEvent) || window.event as MouseEvent;
        if (event) {
            this.selectionHandler.handleContextMenu(
                datum,
                {
                    x: event.clientX,
                    y: event.clientY
                });
            event.preventDefault();
        }
    });
}
```

Etkileşim yardımcı programları işleyicilere işlev atamak için `bindEvents` yöntemlerini çağırır; `bindEvents` yöntemine `bindClick`, `bindClearCatcher` ve`bindContextMenu` çağrıları ekler:

```typescript
  public bindEvents(
      options: BaseBehaviorOptions<SelectableDataPointType>,
      selectionHandler: ISelectionHandler): void {

      this.options = options;
      this.selectionHandler = selectionHandler;

      this.bindClick();
      this.bindClearCatcher();
      this.bindContextMenu();
  }
```

Grafikte öğelerin görsel durumunu güncelleştirmek `renderSelection` yönteminin sorumluluğundadır.

`renderSelection` yöntemini uygulama örneği:

```typescript
public renderSelection(hasSelection: boolean): void {
    this.options.elementsSelection.style("opacity", (category: any) => {
        if (category.selected) {
            return 0.5;
        } else {
            return 1;
        }
    });
}
```

Son adım `visual behavior` örneği oluşturmak and etkileşim yardımcı programları örneğinin `bind` yöntemini çağırmaktır:

```typescript
this.interactivity.bind(<BaseBehaviorOptions<VisualDataPoint>>{
    behavior: this.behavior,
    dataPoints: this.categories,
    clearCatcherSelection: select(this.target),
    elementsSelection: selectionMerge
});
```

* `selectionMerge`, görseldeki tüm seçilebilir öğeleri temsil eden D3 seçim nesnesidir.

* `select(this.target)`, görseldeki ana DOM öğelerini temsil eden D3 seçim nesnesidir.

* `this.categories` öğelerin olduğu veri noktalarıdır, burada arabirim `VisualDataPoint` (veya `categories: VisualDataPoint[];`)

* `this.behavior`, yeni `visual behavior` örneğidir;

  görselin oluşturucusunda oluşturulmuştur:

  ```typescript
  export class Visual implements IVisual {
    // ...
    constructor(options: VisualConstructorOptions) {
        // ...
        this.behavior = new Behavior();
    }
    // ...
  }
  ```

Artık görseliniz seçimi işlemeye hazırdır.

## <a name="next-steps"></a>Sonraki adımlar

* [Yer işaretleri değiştirmede seçimlerin nasıl işlendiğini öğrenin](bookmarks-support.md#visuals-with-selection)

* [Görsellerin veri noktaları için bağlam menüsü eklemeyi öğrenin](context-menu.md)

* [Power BI Görsellerine seçimler eklemek için seçim yöneticisinin nasıl kullanıldığını öğrenin](selection-api.md)
