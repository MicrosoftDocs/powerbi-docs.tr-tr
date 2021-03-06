---
title: Daha iyi tümleşik BI içgörüleri için, Power BI tümleşik analizlerinde Power BI görselinde araç ipucu yardımcı programları kullanmaya giriş
description: Bu makalede Power BI görselleri araç ipuçlarının özelleştirilmesini basitleştirmek için araç ipucu yardımcı programlarının kullanılması anlatılmaktadır. Power BI tümleşik analiz kullanarak daha iyi tümleşik BI içgörüleri elde edin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 02/14/2020
ms.openlocfilehash: b2ddc85d9ba2530dc394b4106d72b4af702bd9b4
ms.sourcegitcommit: eeaf607e7c1d89ef7312421731e1729ddce5a5cc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2021
ms.locfileid: "97888662"
---
# <a name="tooltip-utils"></a>Araç ipucu yardımcı programları
Bu makale araç ipucu yardımcı programlarını yükleme, içeri aktarma ve kullanma işlemlerinde size yardımcı olur. Bu yardımcı program Power BI görsellerinde yapılan tüm araç ipucu özelleştirmelerinde yararlı olur.

## <a name="requirements"></a>Gereksinimler
Paketi kullanmak için aşağıdaki öğelere sahip olmalısınız:
* [node.js](https://nodejs.org) (en son LTS sürümünü öneririz)
* [npm](https://www.npmjs.com/) (desteklenen en düşük sürüm 3.0.0’dır)
* [PowerBI-visuals-tools](https://www.npmjs.com/package/powerbi-visuals-tools) tarafından oluşturulan özel bir görsel

## <a name="installation"></a>Yükleme

Paketi yüklemek için geçerli görselinizin dizininde aşağıdaki komutu çalıştırmalısınız:

```bash
npm install powerbi-visuals-utils-tooltiputils --save
```
Bu komut paketi yükler ve ```package.json``` dosyanıza bağımlılık olarak bir paket ekler

## <a name="usage"></a>Kullanım

> Kullanım Kılavuzunda paketin genel API’si açıklanır. Paketin her genel arabirimi için bir açıklama ve birkaç örnek bulabilirsiniz.

Bu paket size `TooltipServiceWrapper` oluşturma yolu ve araç ipucu eylemlerini işlemeye yardımcı olan yöntemler sağlar. Araç ipucu arabirimlerini kullanır - `ITooltipServiceWrapper`, `TooltipEventArgs`, `TooltipEnabledDataPoint`. 

Ayrıca mobil dağıtımla ilgili belirli yöntemleri (dokunma olayı işleyicileri) vardır: `touchEndEventName`, `touchStartEventName`, `usePointerEvents`.

`TooltipServiceWrapper`, araç ipuçlarını işlemenin en basit yolunu sağlar.

Bu modül aşağıdaki arabirimi ve işlevi sağlar:
* [ITooltipServiceWrapper](#itooltipservicewrapper)
  * [addTooltip](#itooltipservicewrapperaddtooltip)
  * [hide](#itooltipservicewrapperhide)

* [Arabirimler](#interfaces)
  * [TooltipEventArgs](#tooltipeventargs)
  * [TooltipEnabledDataPoint](#tooltipenableddatapoint)
  * [TooltipServiceWrapperOptions](#tooltipservicewrapperoptions)
* [Dokunma olayları](#touch-events)

### `createTooltipServiceWrapper`
Bu işlev bir ITooltipServiceWrapper örneği oluşturur.

```typescript
function createTooltipServiceWrapper(tooltipService: ITooltipService, rootElement: Element, handleTouchDelay?: number,  getEventMethod?: () => MouseEvent): ITooltipServiceWrapper;
```

```ITooltipService```, [IVisualHost](https://github.com/microsoft/PowerBI-visuals-tools/blob/master/templates/visuals/.api/v2.6.0/PowerBI-visuals.d.ts#L1335) içinde sağlanır.

**Örnek**

```typescript
import { createTooltipServiceWrapper } from "powerbi-visuals-utils-tooltiputils";

export class YourVisual implements IVisual {
    // implementation of IVisual.

    constructor(options: VisualConstructorOptions) {
        createTooltipServiceWrapper(
            options.host.tooltipService,
            options.element);

        // returns: an instance of ITooltipServiceWrapper.
    }
}
```

[Burada](https://github.com/microsoft/powerbi-visuals-gantt/blob/master/src/gantt.ts#L391) örnek özel görsel kodunu gözden geçirebilirsiniz.

### `ITooltipServiceWrapper`
Bu arabirim TooltipService’in genel yöntemlerini açıklar.

```typescript
interface ITooltipServiceWrapper {
    addTooltip<T>(selection: d3.Selection<any, any, any, any>, getTooltipInfoDelegate: (args: TooltipEventArgs<T>) => powerbi.extensibility.VisualTooltipDataItem[], getDataPointIdentity?: (args: TooltipEventArgs<T>) => powerbi.visuals.ISelectionId, reloadTooltipDataOnMouseMove?: boolean): void;
    hide(): void;
}
```

#### `ITooltipServiceWrapper.addTooltip`

Bu yöntem geçerli seçime araç ipuçları ekler.

```typescript
addTooltip<T>(selection: d3.Selection<any>, getTooltipInfoDelegate: (args: TooltipEventArgs<T>) => VisualTooltipDataItem[], getDataPointIdentity?: (args: TooltipEventArgs<T>) => ISelectionId, reloadTooltipDataOnMouseMove?: boolean): void;
```

**Örnek**

```typescript
import { createTooltipServiceWrapper, TooltipEventArgs, ITooltipServiceWrapper, TooltipEnabledDataPoint } from "powerbi-visuals-utils-tooltiputils";

let bodyElement = d3.select("body");

let element = bodyElement
    .append("div")
    .style({
        "background-color": "green",
        "width": "150px",
        "height": "150px"
    })
    .classed("visual", true)
    .data([{
        tooltipInfo: [{
            displayName: "Power BI",
            value: 2016
        }]
    }]);

let tooltipServiceWrapper: ITooltipServiceWrapper = createTooltipServiceWrapper(tooltipService, bodyElement.get(0)); // tooltipService is from the IVisualHost.

tooltipServiceWrapper.addTooltip<TooltipEnabledDataPoint>(element, (eventArgs: TooltipEventArgs<TooltipEnabledDataPoint>) => {
    return eventArgs.data.tooltipInfo;
});

// You will see a tooltip if you mouseover the element.
```

[Burada](https://github.com/microsoft/powerbi-visuals-gantt/blob/master/src/gantt.ts#L2931) örnek özel görsel kodunu gözden geçirebilirsiniz.

Ayrıca [burada](https://github.com/microsoft/powerbi-visuals-gantt/blob/master/src/gantt.ts#L573-L648), Gantt özel görselinde araç ipucu özelleştirme örneğine dikkat edin

### `ITooltipServiceWrapper.hide`

Bu yöntem araç ipucunu gizler.

```typescript
hide(): void;
```

**Örnek**

```typescript
import {createTooltipServiceWrapper} from "powerbi-visuals-utils-tooltiputils";

let tooltipServiceWrapper = createTooltipServiceWrapper(options.host.tooltipService, options.element); // options are from the VisualConstructorOptions.

tooltipServiceWrapper.hide();
```
### `Interfaces`
TooltipServiceWrapper oluşturma ve kullanma sırasında bu arabirimler kullanılır. Ayrıca [burada](#itooltipservicewrapperaddtooltip), önceki konunun örneklerinde de bunlardan bahsedilmiştir.

#### `TooltipEventArgs`
```typescript
interface TooltipEventArgs<TData> {
    data: TData;
    coordinates: number[];
    elementCoordinates: number[];
    context: HTMLElement;
    isTouchEvent: boolean;
}
```

#### `TooltipEnabledDataPoint`
```typescript
interface TooltipEnabledDataPoint {
    tooltipInfo?: powerbi.extensibility.VisualTooltipDataItem[];
}
```

#### `TooltipServiceWrapperOptions`
```typescript
interface TooltipServiceWrapperOptions {
    tooltipService: ITooltipService;
    rootElement: Element;
    handleTouchDelay: number;
    getEventMethod?: () => MouseEvent;
```

### `Touch events`

Artık araç ipucu yardımcı programlarının mobil geliştirmede yararlı olan çeşitli dokunma olayı işleme özellikleri vardır.

#### `touchStartEventName`
```typescript
function touchStartEventName(): string
```
Bu yöntem dokunma başlatma olayının adını döndürür.

#### `touchEndEventName`
```typescript
function touchEndEventName(): string
```
Bu yöntem dokunma başlatma olayının adını döndürür.

#### `usePointerEvents`
```typescript
function usePointerEvents(): boolean
```
Bu yöntem geçerli touchStart olayının işaretçiyle ilgili olup olmadığını döndürür.
