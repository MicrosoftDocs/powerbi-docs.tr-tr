---
title: Power BI görselleri etkileşim yardımcı programları
description: Makalede etkileşim yardımcı programlarını kullanarak Power BI görsellerine seçim ekleme açıklanır
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
manager: rkarlin
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: how-to
ms.date: 02/24/2020
ms.openlocfilehash: 3614505cec185779bce3f63c6e7a565a5ef39443
ms.sourcegitcommit: ced8c9d6c365cab6f63fbe8367fb33e6d827cb97
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/07/2020
ms.locfileid: "78920894"
---
# <a name="power-bi-visuals-interactivity-utils"></a>Power BI görselleri etkileşim yardımcı programları

Etkileşim yardımcı programları (`InteractivityUtils`), çapraz seçimin ve çapraz filtrelemenin uygulanmasını basitleştirmek için kullanılabilen bir dizi işlev ve sınıftır.

> [!NOTE]
> Etkileşim yardımcı programlarının yeni güncelleştirmeleri yalnızca araçların en son sürümünü (3.x.x ve üzeri) destekler.

## <a name="installation"></a>Yükleme

1. Paketi yüklemek için geçerli Power BI görsel projenizin dizininde aşağıdaki komutu çalıştırın.

    ```bash
    npm install powerbi-visuals-utils-interactivityutils --save
    ```

2. Aracın 3.0 veya sonraki bir sürümünü kullanıyorsanız, bağımlılıkları çözmek için `powerbi-models` yükleyin.

    ```bash
    npm install powerbi-models --save
    ```

3. Etkileşim yardımcı programlarını kullanmak için Power BI görselinin kaynak kodunda gerekli bileşeni içeri aktarın.

    ```typescript
    import { interactivitySelectionService } from "powerbi-visuals-utils-interactivityutils";
    ```

### <a name="including-the-css-files"></a>CSS dosyaları da dahil

Paketi Power BI görselinizle kullanabilmeniz için şu CSS dosyasını `.less` dosyanıza aktarın.

`node_modules/powerbi-visuals-utils-interactivityutils/lib/index.css`

CSS dosyasını bir `.less` dosyası olarak içeri aktarın çünkü Power BI görselleri aracı dış CSS kurallarını sarmalar.

```less
@import (less) "node_modules/powerbi-visuals-utils-interactivityutils/lib/index.css";
```

## <a name="selectabledatapoint-properties"></a>SelectableDataPoint özellikleri

Genellikle veri noktaları seçimler ve değerler içerir. Arabirim, `SelectableDataPoint` arabirimini genişletir.

Aşağıda açıklandığı gibi `SelectableDataPoint` zaten özellikleri içerir.

```typescript
  /** Flag for identifying that a data point was selected */
  selected: boolean;

  /** Identity for identifying the selectable data point for selection purposes */
  identity: powerbi.extensibility.ISelectionId;

  /*
   * A specific identity for when data points exist at a finer granularity than
   * selection is performed.  For example, if your data points select based
   * only on series, even if they exist as category/series intersections.
   */

  specificIdentity?: powerbi.extensibility.ISelectionId;
```

## <a name="defining-an-interface-for-data-points"></a>Veri noktaları için arabirimi tanımlama

1. Etkileşim yardımcı programlarının bir örneğini oluşturun ve nesneyi görselin özelliği olarak kaydedin

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

2. Temel davranış sınıfını genişletin.

    > [!NOTE]
    > `BaseBehavior`, [etkileşim yardımcı programlarının 5.6.x sürümünde](https://www.npmjs.com/package/powerbi-visuals-utils-interactivityutils/v/5.6.0) kullanıma sunulmuştur. Daha eski bir sürüm kullanıyorsanız, davranış sınıfını aşağıdaki örnekten oluşturun.

3. Davranış sınıfı seçenekleri için arabirimi tanımlayın.

    ```typescript
    import { SelectableDataPoint } from "./interactivitySelectionService";

    import {
        IBehaviorOptions,
        BaseDataPoint
    } from "./interactivityBaseService";

    export interface BaseBehaviorOptions<SelectableDataPointType extends BaseDataPoint> extends IBehaviorOptions<SelectableDataPointType> {

    /** d3 selection object of the main elements on the chart */
    elementsSelection: Selection<any, SelectableDataPoint, any, any>;

    /** d3 selection object of some elements on backgroup, to hadle click of reset selection */
    clearCatcherSelection: d3.Selection<any, any, any, any>;
    }
    ```

4. `visual behavior` için sınıfı tanımlayın. İsterseniz `BaseBehavior` sınıfını genişletin.

    **`visual behavior` için sınıf tanımlama**

    Sınıf `click`, `contextmenu` fare olaylarının işlenmesinden sorumludur.

    Kullanıcı veri öğelerine tıkladığında, görsel veri noktalarını seçmek için seçim işleyicisini çağırır. Kullanıcı görselin arka plan öğesine tıklarsa, seçimi temizleme işleyicisini çağırır.

    Sınıfın bunlara karşılık gelen şu yöntemleri vardır:
    * `bindClick`
    * `bindClearCatcher`
    * `bindContextMenu`.

    ```typescript
    export class Behavior<SelectableDataPointType extends BaseDataPoint> implements IInteractiveBehavior {

        /** d3 selection object of main elements in the chart */
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

    **`BaseBehavior` sınıfını genişletme**

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

5. Öğelere tıklamayı işlemek için *d3* seçim nesnesi `on` yöntemini çağırın. Bu `elementsSelection` ve `clearCatcherSelection` için de geçerlidir.

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

6. `contextmenu` olayı için benzer bir işleyici ekleyerek seçim yöneticisinin `showContextMenu` yöntemini çağırın.

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

7. İşleyicilere işlev atamak için etkileşim yardımcı programları `bindEvents` yöntemini çağırır. Aşağıdaki çağrıları `bindEvents` yöntemine ekleyin:
    * `bindClick`
    * `bindClearCatcher`
    * `bindContextMenu`

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

8. Grafikte öğelerin görsel durumunu güncelleştirmek `renderSelection` yönteminin sorumluluğundadır. Burada `renderSelection` yöntemini uygulama örneği verilmiştir.

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

9. Son adım `visual behavior` örneği oluşturmak and etkileşim yardımcı programları örneğinin `bind` yöntemini çağırmaktır.

    ```typescript
    this.interactivity.bind(<BaseBehaviorOptions<VisualDataPoint>>{
        behavior: this.behavior,
        dataPoints: this.categories,
        clearCatcherSelection: select(this.target),
        elementsSelection: selectionMerge
    });
    ```

    * `selectionMerge`, tüm görsellerdeki seçilebilir öğeleri temsil eden *d3* seçim nesnesidir.
    * `select(this.target)`, görselin ana DOM öğelerini temsil eden *d3* seçim nesnesidir.
    * `this.categories` öğelerin olduğu veri noktalarıdır; burada arabirim `VisualDataPoint` veya `categories: VisualDataPoint[];` olur.
    * `this.behavior`, aşağıda gösterildiği gibi görselin oluşturucusunda oluşturulan yeni bir `visual behavior` örneğidir.

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
## <a name="next-steps"></a>Sonraki adımlar

* [Yer işaretleri değiştirmede seçimlerin nasıl işlendiğini öğrenin](bookmarks-support.md#visuals-with-selection)

* [Görsellerin veri noktaları için bağlam menüsü eklemeyi öğrenin](context-menu.md)

* [Power BI Görsellerine seçimler eklemek için seçim yöneticisinin nasıl kullanıldığını öğrenin](selection-api.md)
