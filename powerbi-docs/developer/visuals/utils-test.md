---
title: Daha iyi tümleşik BI içgörüleri için Power BI tümleşik analizlerindeki Power BI görselinde test yardımcı programlarının kullanımına giriş
description: Bu makalede, Power BI görselleri için sahte uygulamaların ve ünite testinde belirli yöntemlerin kullanımını basitleştirmek için test yardımcı programlarının nasıl kullanılacağı açıklanmaktadır. Power BI tümleşik analiz kullanarak daha iyi tümleşik BI içgörüleri elde edin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 02/14/2020
ms.openlocfilehash: 4b2a846f4905c4cb28fe92043cf3c71750b40f11
ms.sourcegitcommit: eeaf607e7c1d89ef7312421731e1729ddce5a5cc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2021
ms.locfileid: "97888064"
---
# <a name="power-bi-visuals-test-utils"></a>Power BI görselleri test yardımcı programları

Bu makale, Power BI görselleri test yardımcı programlarını yüklemenize, içeri aktarmanıza ve kullanmanıza yardımcı olur. Birim testi için kullanılabilen bu test yardımcı programları veri görünümleri, seçimler ve renk şemaları gibi öğelere yönelik sahte uygulamalar ile yöntemleri içerebilir.

## <a name="requirements"></a>Gereksinimler

Bu paketi kullanmak için aşağıdakileri yüklemeniz gerekir:

* [node.js](https://nodejs.org), LTS sürümünün kullanılması önerilir
* [npm](https://www.npmjs.com/), sürüm 3.0.0 veya üzeri
* [PowerBI-visuals-tools](https://github.com/Microsoft/PowerBI-visuals-tools) paketi

## <a name="installation"></a>Yükleme

Test yardımcı programlarını ve bağımlılığını *package.json* dosyanıza yüklemek için Power BI görselleri dizinindeki şu komutu çalıştırın:

```bash
npm install powerbi-visuals-utils-testutils --save
```

Aşağıdakiler, test yardımcı programları genel API’leri hakkında açıklamalar ve örnekler sağlar.

## <a name="visualbuilderbase"></a>VisualBuilderBase

Birim testlerinde en sık kullanılan `build`, `update` ve `updateRenderTimeout` yöntemleriyle birlikte **VisualBuilder** tarafından kullanılır. 

`build` yöntemi, görselin oluşturulmuş bir örneğini döndürür.

`enumerateObjectInstances` ve `updateEnumerateObjectInstancesRenderTimeout` yöntemleri için demetteki değişikliklerin ve biçimlendirme seçeneklerinin denetlenmesi gerekir.

```typescript
abstract class VisualBuilderBase<T extends IVisual> {
    element: JQuery;
    viewport: IViewport;
    visualHost: IVisualHost;
    protected visual: T;
    constructor(width?: number, height?: number, guid?: string, element?: JQuery);
    protected abstract build(options: VisualConstructorOptions): T;
     nit(): void;
    destroy(): void;
    update(dataView: DataView[] | DataView): void;
    updateRenderTimeout(dataViews: DataView[] | DataView, fn: Function, timeout?: number): number;
    updateEnumerateObjectInstancesRenderTimeout(dataViews: DataView[] | DataView, options: EnumerateVisualObjectInstancesOptions, fn: (enumeration: VisualObjectInstance[]) => void, timeout?: number): number;
    updateFlushAllD3Transitions(dataViews: DataView[] | DataView): void;
    updateflushAllD3TransitionsRenderTimeout(dataViews: DataView[] | DataView, fn: Function, timeout?: number): number;
    enumerateObjectInstances(options: EnumerateVisualObjectInstancesOptions): VisualObjectInstance[];
}
```

> [!NOTE]
> Daha fazla örnek için bkz. [VisualBuilderBase birim testleri yazma](./unit-tests-introduction.md#create-a-visual-instance-builder) ve [VisualBuilderBase gerçek kullanım senaryoları](https://github.com/microsoft/powerbi-visuals-gantt/blob/master/test/visualBuilder.ts).

## <a name="dataviewbuilder"></a>DataViewBuilder

**TestDataViewBuilder** tarafından kullanılan bu modülde, `createCategoricalDataViewBuilder` yönteminde kullanılan **CategoricalDataViewBuilder** sınıfı sağlanır. Ayrıca, birim testlerinde sahte **DataView** ile çalışmak için gereken arabirimler ve yöntemler belirtilir.

* `withValues` statik seri sütunları, `withGroupedValues` ise dinamik seri sütunları ekler

  Görsel bir **DataViewCategorical**’a hem dinamik hem de statik seri uygulamayın. Bunları yalnızca **DataViewTransform**’un ayrı görsel **DataViewCategorical** nesnelerine bölünmesi beklenen **DataViewCategorical** sorgusunda birlikte kullanabilirsiniz.

* `build`, meta veriler içeren DataView ve DataViewCategorical’ı döndürür

  Görsel **DataView** oluşturulurken hem dinamik hem statik serilerin dahil edildiğindeki gibi parametre birleşimi geçersizse `build`, **Tanımsız** döndürür.

```typescript
class CategoricalDataViewBuilder implements IDataViewBuilderCategorical {
    withCategory(options: DataViewBuilderCategoryColumnOptions): IDataViewBuilderCategorical;
    withCategories(categories: DataViewCategoryColumn[]): IDataViewBuilderCategorical;
    withValues(options: DataViewBuilderValuesOptions): IDataViewBuilderCategorical;
    withGroupedValues(options: DataViewBuilderGroupedValuesOptions): IDataViewBuilderCategorical;
    build(): DataView;
}

function createCategoricalDataViewBuilder(): IDataViewBuilderCategorical;
```

## <a name="testdataviewbuilder"></a>TestDataViewBuilder

Birim testlerinde **VisualData** oluşturmak için kullanılır. Veriler veri alanı demetlerine yerleştirildiğinde, Power BI verilere göre kategorik bir **DataView** nesnesi oluşturur. **TestDataViewBuilder**, kategorik **DataView** oluşturmanın simüle edilmesine yardımcı olur.

```typescript
abstract class TestDataViewBuilder {
    static DataViewName: string;
    private aggregateFunction;
    static setDefaultQueryName(source: DataViewMetadataColumn): DataViewMetadataColumn;
    static getDataViewBuilderColumnIdentitySources(options: TestDataViewBuilderColumnOptions[] | TestDataViewBuilderColumnOptions): DataViewBuilderColumnIdentitySource[];
    static getValuesTable(categories?: DataViewCategoryColumn[], values?: DataViewValueColumn[]): any[][];
    static createDataViewBuilderColumnOptions(categoriesColumns: (TestDataViewBuilderCategoryColumnOptions | TestDataViewBuilderCategoryColumnOptions[])[], valuesColumns: (DataViewBuilderValuesColumnOptions | DataViewBuilderValuesColumnOptions[])[], filter?: (options: TestDataViewBuilderColumnOptions) => boolean, customizeColumns?: CustomizeColumnFn): DataViewBuilderAllColumnOptions;
    static setUpDataViewBuilderColumnOptions(options: DataViewBuilderAllColumnOptions, aggregateFunction: (array: number[]) => number): DataViewBuilderAllColumnOptions;
    static setUpDataView(dataView: DataView, options: DataViewBuilderAllColumnOptions): DataView;
    protected createCategoricalDataViewBuilder(categoriesColumns: (TestDataViewBuilderCategoryColumnOptions | TestDataViewBuilderCategoryColumnOptions[])[], valuesColumns: (DataViewBuilderValuesColumnOptions | DataViewBuilderValuesColumnOptions[])[], columnNames: string[], customizeColumns?: CustomizeColumnFn): IDataViewBuilderCategorical;
    abstract getDataView(columnNames?: string[]): DataView;
}
```

  Aşağıda, `testDataView` oluşturulurken en sık kullanılan arabirimler listelenmektedir:

  ```typescript
  interface TestDataViewBuilderColumnOptions extends DataViewBuilderColumnOptions {
      values: any[];
  }

  interface TestDataViewBuilderCategoryColumnOptions extends TestDataViewBuilderColumnOptions {
      objects?: DataViewObjects[];
      isGroup?: boolean;
  }

  interface DataViewBuilderColumnOptions {
      source: DataViewMetadataColumn;
  }

  interface DataViewBuilderSeriesData {
      values: PrimitiveValue[];
      highlights?: PrimitiveValue[];
      /** Client-computed maximum value for a column. */
      maxLocal?: any;
      /** Client-computed maximum value for a column. */
      minLocal?: any;
  }

  interface DataViewBuilderColumnIdentitySource {
      fields: any[];
      identities?: CustomVisualOpaqueIdentity[];
  }
  ```
   
> [!NOTE]
> Daha fazla örnek için bkz. [TestDataViewBuilder birim testleri yazma](./unit-tests-introduction.md#how-to-add-static-data-for-unit-tests) ve [TestDataViewBuilder gerçek kullanım senaryoları](https://github.com/microsoft/powerbi-visuals-gantt/blob/master/test/visualData.ts).

## <a name="mocks"></a>Sahte uygulamalar

### <a name="mockivisualhost"></a>MockIVisualHost

Power BI çerçevesi gibi dış bağımlılıklar olmadan Power BI görsellerini test etmek için **IVisualHost** uygular.

Yararlı yöntemler arasında `createSelectionIdBuilder`, `createSelectionManager` ve `createLocalizationManager` ile alıcı özellikleri yer alır.

```typescript
import powerbi from "powerbi-visuals-api";

import VisualObjectInstancesToPersist = powerbi.VisualObjectInstancesToPersist;
import ISelectionIdBuilder = powerbi.visuals.ISelectionIdBuilder;
import ISelectionManager = powerbi.extensibility.ISelectionManager;
import IColorPalette = powerbi.extensibility.IColorPalette;
import IVisualEventService = powerbi.extensibility.IVisualEventService;
import ITooltipService = powerbi.extensibility.ITooltipService;
import IVisualHost = powerbi.extensibility.visual.IVisualHost;

class MockIVisualHost implements IVisualHost {
      constructor(
          colorPalette?: IColorPalette,
          selectionManager?: ISelectionManager,
          tooltipServiceInstance?: ITooltipService,
          localeInstance?: MockILocale,
          allowInteractionsInstance?: MockIAllowInteractions,
          localizationManager?: powerbi.extensibility.ILocalizationManager,
          telemetryService?: powerbi.extensibility.ITelemetryService,
          authService?: powerbi.extensibility.IAuthenticationService,
          storageService?: ILocalVisualStorageService,
          eventService?: IVisualEventService);
      createSelectionIdBuilder(): ISelectionIdBuilder;
      createSelectionManager(): ISelectionManager;
      createLocalizationManager(): ILocalizationManager;
      colorPalette: IColorPalette;
      locale: string;
      telemetry: ITelemetryService;
      tooltipService: ITooltipService;
      allowInteractios: boolean;
      storageService: ILocalVisualStorageService;
      eventService: IVisualEventService;
      persistProperties(changes: VisualObjectInstancesToPersist): void;
}
```
   
- `createVisualHost`, aslında **MockIVisualHost** olan **IVisualHost** örneğini oluşturup döndürür
  ```typescript
  function createVisualHost(locale?: Object, allowInteractions?: boolean, colors?: IColorInfo[], isEnabled?: boolean, displayNames?: any, token?: string): IVisualHost;
  ```

    Örnek
    ```typescript
    import { createVisualHost } from "powerbi-visuals-utils-testutils"

    let host: IVisualHost = createVisualHost();
    ```

> [!IMPORTANT]
> **MockIVisualHost**, sahte bir **IVisualHost** uygulamasıdır ve yalnızca birim testleriyle kullanılmalıdır.

### <a name="mockicolorpalette"></a>MockIColorPalette

Power BI çerçevesi gibi dış bağımlılıklar olmadan Power BI görsellerini test etmek için **IColorPalette** uygular.

**MockIColorPalette**, birim testlerinde renk şemasını veya yüksek karşıtlık modunu denetlemeye yönelik yararlı özellikler sağlar.

  ```typescript
  import powerbi from "powerbi-visuals-api";
  import IColorPalette = powerbi.extensibility.ISandboxExtendedColorPalette;
  import IColorInfo = powerbi.IColorInfo;

  class MockIColorPalette implements IColorPalette {
      constructor(colors?: IColorInfo[]);
      getColor(key: string): IColorInfo;
      reset(): IColorPalette;
      isHighContrastMode: boolean;
      foreground: {value: string};
      foregroundLight: {value: string};
      ...
      background: {value: string};
      backgroundLight: {value: string};
      ...
      shapeStroke: {value: string};
  }
  ```
  - `createColorPalette`, aslında **MockIColorPalette** olan **IColorPalette** örneğini oluşturup döndürür
    ```typescript
    function createColorPalette(colors?: IColorInfo[]): IColorPalette;
    ```

    Örnek
    ```typescript
    import { createColorPalette } from "powerbi-visuals-utils-testutils"

    let colorPalette: IColorPalette = createColorPalette();
    ```
    
> [!IMPORTANT]
> **MockIColorPalette**, sahte bir **IColorPalette** uygulamasıdır ve yalnızca birim testleriyle kullanılmalıdır.

### <a name="mockiselectionid"></a>MockISelectionId

Power BI çerçevesi gibi dış bağımlılıklar olmadan Power BI görsellerini test etmek için **SelectionId** uygular.

  ```typescript
  import powerbi from "powerbi-visuals-api";
  import Selector = powerbi.data.Selector;
  import ISelectionId = powerbi.visuals.ISelectionId;

  class MockISelectionId implements ISelectionId {
      constructor(key: string);
      equals(other: ISelectionId): boolean;
      includes(other: ISelectionId, ignoreHighlight?: boolean): boolean;
      getKey(): string;
      getSelector(): Selector;
      getSelectorsByColumn(): Selector;
      hasIdentity(): boolean;
  }
  ```

  - `createSelectionId`, aslında **MockISelectionId** olan **SelectionId** örneğini oluşturup döndürür
    ```typescript
    function createSelectionId(key?: string): ISelectionId;
    ```

    Örnek
    ```typescript
    import { createColorPalette } from "powerbi-visuals-utils-testutils"

    let selectionId: ISelectionId = createSelectionId();
    ```
    
> [!NOTE]
> **MockISelectionId**, sahte bir **ISelectionId** uygulamasıdır ve yalnızca birim testleriyle kullanılmalıdır.

### <a name="mockiselectionidbuilder"></a>MockISelectionIdBuilder

Power BI çerçevesi gibi dış bağımlılıklar olmadan Power BI görsellerini test etmek için **ISelectionIdBuilder** uygular. 

  ```typescript
  import DataViewCategoryColumn = powerbi.DataViewCategoryColumn;
  import DataViewValueColumn = powerbi.DataViewValueColumn;
  import DataViewValueColumnGroup = powerbi.DataViewValueColumnGroup;
  import DataViewValueColumns = powerbi.DataViewValueColumns;
  import ISelectionIdBuilder = powerbi.visuals.ISelectionIdBuilder;
  import ISelectionId = powerbi.visuals.ISelectionId;

  class MockISelectionIdBuilder implements ISelectionIdBuilder {
      withCategory(categoryColumn: DataViewCategoryColumn, index: number): this;
      withSeries(seriesColumn: DataViewValueColumns, valueColumn: DataViewValueColumn | DataViewValueColumnGroup): this;
      withMeasure(measureId: string): this;
      createSelectionId(): ISelectionId;
      withMatrixNode(matrixNode: DataViewMatrixNode, levels: DataViewHierarchyLevel[]): this;
      withTable(table: DataViewTable, rowIndex: number): this;
  }
  ```

  - `createSelectionIdBuilder`, aslında **MockISelectionIdBuilder** olan **ISelectionIdBuilder** örneğini oluşturup döndürür
    ```typescript
    function createSelectionIdBuilder(): ISelectionIdBuilder;
    ```

    Örnek
    ```typescript
    import { selectionIdBuilder } from "powerbi-visuals-utils-testutils";

    let selectionIdBuilder = createSelectionIdBuilder();
    ```

> [!NOTE]
> **MockISelectionIdBuilder**, sahte bir **ISelectionIdBuilder** uygulamasıdır ve yalnızca birim testleriyle kullanılmalıdır.

### <a name="mockiselectionmanager"></a>MockISelectionManager

Power BI çerçevesi gibi dış bağımlılıklar olmadan Power BI görsellerini test etmek için **ISelectionManager** uygular. 

  ```typescript
  import powerbi from "powerbi-visuals-api";
  import IPromise = powerbi.IPromise;
  import ISelectionId = powerbi.visuals.ISelectionId;
  import ISelectionManager = powerbi.extensibility.ISelectionManager;

  class MockISelectionManager implements ISelectionManager {
      select(selectionId: ISelectionId | ISelectionId[], multiSelect?: boolean): IPromise<ISelectionId[]>;
      hasSelection(): boolean;
      clear(): IPromise<{}>;
      getSelectionIds(): ISelectionId[];
      containsSelection(id: ISelectionId): boolean;
      showContextMenu(selectionId: ISelectionId, position: IPoint): IPromise<{}>;
      registerOnSelectCallback(callback: (ids: ISelectionId[]) => void): void;
      simutateSelection(selections: ISelectionId[]): void;
  }
  ```

  - `createSelectionManager`, aslında **MockISelectionManager** olan **ISelectionManager** örneğini oluşturup döndürür
    ```typescript
    function createSelectionManager(): ISelectionManager
    ```

    Örnek
    ```typescript
    import { createSelectionManager } from "powerbi-visuals-utils-testutils";

    let selectionManager: ISelectionManager = createSelectionManager();
    ```

> [!NOTE]
> **MockISelectionManager**, sahte bir **ISelectionManager** uygulamasıdır ve yalnızca birim testleriyle kullanılmalıdır.

### <a name="mockilocale"></a>MockILocale

  Yerel ayarları belirler ve birim testi sürecindeki ihtiyaçlarınıza göre değiştirir.
  ```typescript
  class MockILocale {
      constructor(locales?: Object): void; // Default locales are en-US and ru-RU 
      locale(key: string): void;// setter property
      locale(): string; // getter property
  }
  ```
  - `createLocale`, **MockILocale** örneğini oluşturup döndürür
    ```typescript
    funciton createLocale(locales?: Object): MockILocale;
    ```

### <a name="mockitooltipservice"></a><a id="mockitooltipservice"></a> MockITooltipService
`TooltipService` simülasyonu yapar ve bunu birim testi sürecindeki ihtiyaçlarınıza göre çağırır.
  ```typescript
  class MockITooltipService implements ITooltipService {
      constructor(isEnabled: boolean = true);
      enabled(): boolean;
      show(options: TooltipShowOptions): void;
      move(options: TooltipMoveOptions): void;
      hide(options: TooltipHideOptions): void;
  }
  ```
  - `createTooltipService`, **MockITooltipService** örneğini oluşturup döndürür
    ```typescript
    function createTooltipService(isEnabled?: boolean): ITooltipService;
    ```

### <a name="mockiallowinteractions"></a>MockIAllowInteractions

```typescript
export class MockIAllowInteractions {
    constructor(public isEnabled?: boolean); // false by default
}
```
  - `createAllowInteractions`, **MockIAllowInteractions** örneğini oluşturup döndürür
    ```typescript
    function createAllowInteractions(isEnabled?: boolean): MockIAllowInteractions;
    ```

### <a name="mockilocalizationmanager"></a><a id="mockilocalizationmanager"></a> MockILocalizationManager
Birim testi için gereken temel **LocalizationManager** özelliklerini sağlar.
```typescript
class MockILocalizationManager implements ILocalizationManager {
    constructor(displayNames: {[key: string]: string});
    getDisplayName(key: string): string; // returns default or setted displayNames for localized elements
}
```
  - `createLocalizationManager`, aslında **MockILocalizationManager** olan **ILocalizationManager** örneğini oluşturup döndürür
    ```typescript
    function createLocalizationManager(displayNames?: any): ILocalizationManager;
    ```

    Örnek
    ```typescript
    import { createLocalizationManager } from "powerbi-visuals-utils-testutils";
    let localizationManagerMock: ILocalizationManager = createLocalizationManager();
    ```

### <a name="mockitelemetryservice"></a>MockITelemetryService
**TelemetryService** kullanımını simüle eder.
```typescript
class MockITelemetryService implements ITelemetryService {
    instanceId: string;
    trace(veType: powerbi.VisualEventType, payload?: string) {
    }
}
```
  `MockITelemetryService` oluşturma
    ```typescript
    function createTelemetryService(): ITelemetryService;
    ```
### <a name="mockiauthenticationservice"></a>MockIAuthenticationService
Sahte bir AAD belirteci sağlayarak **AuthenticationService** işini simüle eder.
```typescript
class MockIAuthenticationService implements IAuthenticationService  {
    constructor(token: string);
    getAADToken(visualId?: string): powerbi.IPromise<string>
}
```
  - `createAuthenticationService`, aslında **MockIAuthenticationService** olan **IAuthenticationService** örneğini oluşturup döndürür
    ```typescript
    function createAuthenticationService(token?: string): IAuthenticationService;
    ```

### <a name="mockistorageservice"></a>MockIStorageService
**ILocalVisualStorageService**’i, **LocalStorage** ile aynı davranışa sahip olacak şekilde kullanmanıza olanak verir.
```typescript
class MockIStorageService implements ILocalVisualStorageService {
  get(key: string): IPromise<string>;
  set(key: string, data: string): IPromise<number>;
  remove(key: string): void;
}
```
  - `createStorageService`, aslında **MockIStorageService** olan **ILocalVisualStorageService** örneğini oluşturup döndürür
    ```typescript
    function createStorageService(): ILocalVisualStorageService;
    ```

### <a name="mockieventservice"></a>MockIEventService
```typescript
import powerbi from "powerbi-visuals-api";
import IVisualEventService = powerbi.extensibility.IVisualEventService;
import VisualUpdateOptions = powerbi.extensibility.VisualUpdateOptions;

class MockIEventService implements IVisualEventService {
      renderingStarted(options: VisualUpdateOptions): void;
      renderingFinished(options: VisualUpdateOptions): void;
      renderingFailed(options: VisualUpdateOptions, reason?: string): void;
}
```
  - `createEventService`, aslında **MockIEventService** olan **IVisualEventService** örneğini oluşturup döndürür
    ```typescript
    function createEventService(): IVisualEventService;
    ```

## <a name="utils"></a>Yardımcı programlar

Yardımcı programlar, Power BI görsellerinin birim testi için renk, sayı ve olaylarla ilgili yardımcılar dahil olmak üzere yardımcı yöntemleri içerir.

- `renderTimeout`, zaman aşımını döndürür
  ```typescript
  function renderTimeout(fn: Function, timeout: number = DefaultWaitForRender): number
  ```

- `testDom`, birim testlerinde düzen ayarlamaya yardımcı olur
  ```typescript
  function testDom(height: number | string, width: number | string): JQuery
  ```
  Örnek
  ```typescript
  import { testDom }  from "powerbi-visuals-utils-testutils";
  describe("testDom", () => {
      it("should return an element", () => {
          let element: JQuery = testDom(500, 500);
          expect(element.get(0)).toBeDefined();
      });
  });
  ```

### <a name="color-related-helper-methods"></a>Renklerle ilgili yardımcı yöntemler

- `getSolidColorStructuralObject`
  ```typescript
  function getSolidColorStructuralObject(color: string): any
  ```
  Şu yapıyı döndürür:

  ```json
  { solid: { color: color } }
  ```

- `assertColorsMatch`, giriş dizelerinden ayrıştırılan **RgbColor** nesnelerini karşılaştırır
  ```typescript
  function assertColorsMatch(actual: string, expected: string, invert: boolean = false): boolean
  ```

- `parseColorString`, rengi giriş dizesinden ayrıştırır ve belirli **RgbColor** arabiriminde döndürür
  ```typescript
  function parseColorString(color: string): RgbColor
  ```

### <a name="number-related-helper-methods"></a>Sayıyla ilgili yardımcı yöntemler

- `getRandomNumbers`, en küçük ve en büyük değerleri kullanarak rastgele bir sayı oluşturur. `exceptionList` belirtebilir ve sonuç değişikliği için bir işlev sağlayabilirsiniz.
  ```typescript
  function getRandomNumber(
      min: number,
      max: number,
      exceptionList?: number[],
      changeResult: (value: any) => number = x => x): number
  ```

- `getRandomNumbers`, belirtilen en küçük ve en büyük değerler ile `getRandomNumber` yöntemi tarafından oluşturulan bir rastgele sayı dizisi sağlar
  ```typescript
  function getRandomNumbers(count: number, min: number = 0, max: number = 1): number[]
  ```

### <a name="event-related-helper-methods"></a>Olaylarla ilgili yardımcı yöntemler
Aşağıdaki yöntemler, birim testlerinde web sayfası olayı simülasyonu için yazılmıştır.

- `clickElement`, belirtilen öğe üzerinde tıklamayı simüle eder
  ```typescript
  function clickElement(element: JQuery, ctrlKey: boolean = false): void
  ```

- `createTouch`, dokunma olayını simüle etmeye yardımcı olan bir **Touch** nesnesi döndürür
  ```typescript
  function createTouch(x: number, y: number, element: JQuery, id: number = 0): Touch
  ```

- `createTouchesList`, simüle edilen **Touch** olaylarının bir listesini döndürür
  ```typescript
  function createTouchesList(touches: Touch[]): TouchList
  ```

- `createContextMenuEvent`, **MouseEvent** döndürür
  ```typescript
  function createContextMenuEvent(x: number, y: number): MouseEvent
  ```

- `createMouseEvent`, **MouseEvent** oluşturup döndürür
  ```typescript
  function createMouseEvent(
      mouseEventType: MouseEventType,
      eventType: ClickEventType,
      x: number,
      y: number,
      button: number = 0): MouseEvent
  ```

- `createTouchEndEvent`
  ```typescript
  function createTouchEndEvent(touchList?: TouchList): UIEvent
  ```

- `createTouchMoveEvent`
  ```typescript
  function createTouchMoveEvent(touchList?: TouchList): UIEvent
  ```

- `createTouchStartEvent`
  ```typescript
  function createTouchStartEvent(touchList?: TouchList): UIEvent
  ```

### <a name="d3-event-related-helper-methods"></a>D3 olaylarıyla ilgili yardımcı yöntemler

Aşağıdaki yöntemler, birim testlerinde D3 olaylarını simüle etmek için kullanılır.

- `flushAllD3Transitions`, tüm D3 geçişlerini tamamlamaya zorlar

  ```typescript
  function flushAllD3Transitions()
  ```
  
  > [!NOTE]
  > Sıfır gecikmeli geçişler normalde anlık bir gecikmeden (10 ms’den az) sonra yürütülür ancak bu, tarayıcı sayfayı iki kez işliyorsa kısa bir titreşime neden olabilir. İlk olarak olay döngüsünün sonuna ulaşıldığında, ardından hemen ilk zamanlayıcı geri aramasında.
  >
  > Bu titreşimler çok sayıda web görünümüyle IE’de daha belirgindir ve iOS için önerilmez.
  > 
  > İlk olay döngüsünün sonunda zamanlayıcı kuyruğunu boşaltarak tüm sıfır gecikmeli geçişleri hemen çalıştırıp titreşimden kaçınabilirsiniz.

Aşağıdaki yöntemler de dahildir:
```typescript
function d3Click(element: JQuery, x: number, y: number, eventType?: ClickEventType, button?: number): void
function d3MouseUp(element: JQuery, x: number, y: number, eventType?: ClickEventType, button?: number): void
function d3MouseDown(element: JQuery, x: number, y: number, eventType?: ClickEventType, button?: number): void
function d3MouseOver(element: JQuery, x: number, y: number, eventType?: ClickEventType, button?: number): void
function d3MouseMove(element: JQuery, x: number, y: number, eventType?: ClickEventType, button?: number): void
function d3MouseOut(element: JQuery, x: number, y: number, eventType?: ClickEventType, button?: number): void
function d3KeyEvent(element: JQuery, typeArg: string, keyArg: string, keyCode: number): void
function d3TouchStart(element: JQuery, touchList?: TouchList): void
function d3TouchMove(element: JQuery, touchList?: TouchList): void
function d3TouchEnd(element: JQuery, touchList?: TouchList): void
function d3ContextMenu(element: JQuery, x: number, y: number): void
```

### <a name="helper-interfaces"></a>Yardımcı arabirimleri
Aşağıdaki arabirim ve sabit listeleri yardımcı işlevinde kullanılır.

```typescript
interface RgbColor {
    R: number;
    G: number;
    B: number;
    A?: number; 
}

enum ClickEventType {
    Default = 0,
    CtrlKey = 1,
    AltKey = 2,
    ShiftKey = 4,
    MetaKey = 8,
}

enum MouseEventType {
    click,
    mousedown,
    mouseup,
    mouseover,
    mousemove,
    mouseout,
}
```

## <a name="next-steps"></a>Sonraki adımlar

Web paketi tabanlı Power BI görsellerine birim testleri ve `karma` ile `jasmine` içeren birim testi yazmak için bkz. [Öğretici: Power BI görsel projeleri için birim testleri ekleme](./unit-tests-introduction.md).
