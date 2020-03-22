---
title: Power BI görselinde renk yardımcı programlarını kullanmaya giriş
description: Bu makalede Power BI görsellerinde görselin veri noktalarına temaları ve paletleri basit bir şekilde uygulamak için renk yardımcı programlarının nasıl kullanabileceği açıklanır
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 02/14/2020
ms.openlocfilehash: 8de530871739a18c1afc72cee3e0da5fc70ebb16
ms.sourcegitcommit: 6bbc3d0073ca605c50911c162dc9f58926db7b66
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79379364"
---
# <a name="color-utils"></a>Renk yardımcı programları
Bu makale renk yardımcı programlarını yükleme, içeri aktarma ve kullanma işlemlerinde size yardımcı olur. Bu makalede Power BI görsellerinde görselin veri noktalarına temaları ve paletleri basit bir şekilde uygulamak için renk yardımcı programlarının nasıl kullanabileceği açıklanır.

## <a name="requirements"></a>Gereksinimler
Paketi kullanmak için aşağıdaki öğelere sahip olmalısınız:
* [node.js](https://nodejs.org) (en son LTS sürümünü öneririz)
* [npm](https://www.npmjs.com/) (desteklenen en düşük sürüm 3.0.0’dır)
* [PowerBI-visuals-tools](https://www.npmjs.com/package/powerbi-visuals-tools) tarafından oluşturulan özel bir görsel

## <a name="installation"></a>Yükleme

Paketi yüklemek için geçerli görselinizin dizininde aşağıdaki komutu çalıştırmalısınız:

```bash
npm install powerbi-visuals-utils-colorutils --save
```
Bu komut paketi yükler ve ```package.json``` dosyanıza bağımlılık olarak bir paket ekler

## <a name="usage"></a>Kullanım

Etkileşim yardımcı programlarını kullanmak için görselin kaynak kodunda gerekli bileşeni içeri aktarmalısınız.
```typescript
import { ColorHelper } from "powerbi-visuals-utils-colorutils";
```

Power BI görsellerinizde ColorUtils’i yüklemeyi ve kullanmayı öğrenin:

* [Kullanım Kılavuzu] Kullanım Kılavuzunda paketin genel API’si açıklanır. Paketin her genel arabirimi için bir açıklama ve birkaç örnek bulabilirsiniz.

Bu paket aşağıdaki sınıfları ve modülleri içerir:
* [ColorHelper](#colorhelper) - grafik değerleriniz için farklı renkler oluşturmanıza yardımcı olur
* [colorUtils](#colorutils) - renk biçimlerini dönüştürmeye yardımcı olur

## `ColorHelper`
`ColorHelper` sınıfı aşağıdaki işlevleri ve yöntemleri sağlar:

### `getColorForSeriesValue` 
Bu yöntem belirli bir seri değerinin rengini alır. Açıkça bir renk ayarlanmadıysa veya varsayılan renk ayarlandıysa, bu serinin renk ölçeğindeki renk ayrılır.
```typescript
getColorForSeriesValue(objects: IDataViewObjects, value: PrimitiveValue, themeColorName?: ThemeColorName): string;
```
#### <a name="example"></a>Örnek
```typescript
import powerbi from "powerbi-visuals-api";
import { ColorHelper } from "powerbi-visuals-utils-colorutils";

import DataViewObjects = powerbi.DataViewObjects;

import DataViewValueColumns = powerbi.DataViewValueColumns;
import DataViewValueColumnGroup = powerbi.DataViewValueColumnGroup;
import DataViewObjectPropertyIdentifier = powerbi.DataViewObjectPropertyIdentifier;

import IVisual = powerbi.extensibility.visual.IVisual;
import IColorPalette = powerbi.extensibility.IColorPalette;
import VisualUpdateOptions = powerbi.extensibility.visual.VisualUpdateOptions;
import VisualConstructorOptions = powerbi.extensibility.visual.VisualConstructorOptions;

export class YourVisual implements IVisual {
    // Implementation of IVisual

    private colorPalette: IColorPalette;

    constructor(options: VisualConstructorOptions) {
        this.colorPalette = options.host.colorPalette;
    }

    public update(visualUpdateOptions: VisualUpdateOptions): void {
        const valueColumns: DataViewValueColumns = visualUpdateOptions.dataViews[0].categorical.values,
            grouped: DataViewValueColumnGroup[] = valueColumns.grouped(),
            defaultDataPointColor: string = "green",
            fillProp: DataViewObjectPropertyIdentifier = {
                objectName: "objectName",
                propertyName: "propertyName"
            };

        let colorHelper: ColorHelper = new ColorHelper(
            this.colorPalette,
            fillProp,
            defaultDataPointColor);

        for (let i = 0; i < grouped.length; i++) {
            let grouping: DataViewValueColumnGroup = grouped[i];

            let color = colorHelper.getColorForSeriesValue(grouping.objects, grouping.name); // returns a color of the series
        }
    }
}
```

### `getColorForMeasure`
Bu yöntem belirli bir ölçünün rengini alır.
```typescript
 getColorForMeasure(objects: IDataViewObjects, measureKey: any, themeColorName?: ThemeColorName): string;
```
#### <a name="example"></a>Örnek
```typescript
import powerbi from "powerbi-visuals-api";
import { ColorHelper } from "powerbi-visuals-utils-colorutils";

import DataViewObjects = powerbi.DataViewObjects;
import IVisual = powerbi.extensibility.visual.IVisual;
import IColorPalette = powerbi.extensibility.IColorPalette;
import VisualUpdateOptions = powerbi.extensibility.visual.VisualUpdateOptions;
import DataViewObjectPropertyIdentifier = powerbi.DataViewObjectPropertyIdentifier;
import VisualConstructorOptions = powerbi.extensibility.visual.VisualConstructorOptions;

export class YourVisual implements IVisual {
    // Implementation of IVisual

    private colorPalette: IColorPalette;

    constructor(options: VisualConstructorOptions) {
        this.colorPalette = options.host.colorPalette;
    }

    public update(visualUpdateOptions: VisualUpdateOptions): void {
        const objects: DataViewObjects = visualUpdateOptions.dataViews[0].categorical.categories[0].objects[0],
            defaultDataPointColor: string = "green",
            fillProp: DataViewObjectPropertyIdentifier = {
                objectName: "objectName",
                propertyName: "propertyName"
            };

        let colorHelper: ColorHelper = new ColorHelper(
            this.colorPalette,
            fillProp,
            defaultDataPointColor);

        let color = colorHelper.getColorForMeasure(objects, ""); // returns a color
    }
}
```

### <a name="static-normalizeselector"></a>statik `normalizeSelector`
Bu yöntem normalleştirilmiş seçiciyi döndürür
```typescript
static normalizeSelector(selector: Selector, isSingleSeries?: boolean): Selector;
```
#### <a name="example"></a>Örnek
```typescript
import ISelectionId = powerbi.visuals.ISelectionId;
import { ColorHelper } from "powerbi-visuals-utils-colorutils";

let selectionId: ISelectionId = ...;
let selector = ColorHelper.normalizeSelector(selectionId.getSelector(), false);
```

`getThemeColor` ve `getHighContrastColor` yöntemlerinin ikisi de renk teması renkleriyle ilgilidir.
Ayrıca `ColorHelper` sınıfının denetimde yararlı olacak `isHighContrast` özelliği vardır.

### `getThemeColor`
Bu yöntem tema rengini döndürür
```typescript
 getThemeColor(themeColorName?: ThemeColorName): string;
```
### `getHighContrastColor`
 Bu yöntem yüksek karşıtlık modu için renk döndürür
```typescript
getHighContrastColor(themeColorName?: ThemeColorName, defaultColor?: string): string;
```
#### <a name="example-related-to-high-contrast-mode-usage"></a>Yüksek karşıtlık modu kullanımıyla ilgili örnek:
```typescript

import { ColorHelper } from "powerbi-visuals-utils-colorutils";

export class MyVisual implements IVisual {
        private colorHelper: ColorHelper;

        private init(options: VisualConstructorOptions): void {
            this.colors = options.host.colorPalette;
            this.colorHelper = new ColorHelper(this.colors);
        } 

            private createViewport(element: HTMLElement): void {
                const fontColor: string = "#131aea";
                const axisBackgroundColor: string = this.colorHelper.getThemeColor();
                
                // some d3 code before
                d3ElementName.attr("fill", colorHelper.getHighContrastColor("foreground", fontColor);
            }
                
            public static parseSettings(dataView: DataView, colorHelper: ColorHelper): VisualSettings {
                // some code that should be applied on formatting settings
                if (colorHelper.isHighContrast) {
                        this.settings.fontColor = colorHelper.getHighContrastColor("foreground", this.settings.fontColor);
                    }
            }
}
```


## `ColorUtils`
 Modül aşağıdaki işlevleri sağlar:

* [hexToRGBString](#hextorgbstring)
* [rotate](#rotate)
* [parseColorString](#parsecolorstring)
* [calculateHighlightColor](#calculatehighlightcolor)
* [createLinearColorScale](#createlinearcolorscale)
* [shadeColor](#shadecolor)
* [rgbBlend](#rgbblend)
* [channelBlend](#channelblend)
* [hexBlend](#hexblend)

### <a name="hextorgbstring"></a>hexToRGBString
Onaltılık rengi RGB dizesine dönüştürür.

```typescript
function hexToRGBString(hex: string, transparency?: number): string
```

#### <a name="example"></a>Örnek

```typescript
import  { hexToRGBString } from "powerbi-visuals-utils-colorutils";

hexToRGBString('#112233');

// returns: "rgb(17,34,51)"
```

### <a name="rotate"></a>rotate
RGB rengini döndürür.

```typescript
function rotate(rgbString: string, rotateFactor: number): string
```

#### <a name="example"></a>Örnek

```typescript
import { rotate } from "powerbi-visuals-utils-colorutils";

rotate("#CC0000", 0.25); // returns: #66CC00
```

### <a name="parsecolorstring"></a>parseColorString
Herhangi bir renk dizesini RGB biçimine ayrıştırır.

```typescript
function parseColorString(color: string): RgbColor
```

#### <a name="example"></a>Örnek

```typescript
import { parseColorString } from "powerbi-visuals-utils-colorutils";

parseColorString('#09f');
// returns: {R: 0, G: 153, B: 255 }

parseColorString('rgba(1, 2, 3, 1.0)');
// returns: {R: 1, G: 2, B: 3, A: 1.0 }
```

### <a name="calculatehighlightcolor"></a>calculateHighlightColor
lumianceThreshold ve delta temelinde rgbColor’dan vurgu rengini hesaplar.

```typescript
function calculateHighlightColor(rgbColor: RgbColor, lumianceThreshold: number, delta: number): string
```

#### <a name="example"></a>Örnek

```typescript
import { calculateHighlightColor } from "powerbi-visuals-utils-colorutils";

let yellow = "#FFFF00",
    yellowRGB = parseColorString(yellow);

calculateHighlightColor(yellowRGB, 0.8, 0.2);

// returns: '#CCCC00'
```

### <a name="createlinearcolorscale"></a>createLinearColorScale
Belirli bir sayı etki alanı için doğrusal renk ölçeğini döndürür.

```typescript
function createLinearColorScale(domain: number[], range: string[], clamp: boolean): LinearColorScale
```

#### <a name="example"></a>Örnek

```typescript
import { createLinearColorScale } from "powerbi-visuals-utils-colorutils";

let scale = ColorUtility.createLinearColorScale(
    [0, 1, 2, 3, 4],
    ["red", "green", "blue", "black", "yellow"],
    true);

scale(1); // returns: green
scale(10); // returns: yellow
```

### <a name="shadecolor"></a>shadeColor
Dize onaltılık ifadesini sayıya dönüştürür, yüzdeyi ve R, G, B kanallarını hesaplar.
Her kanala yüzdeyi uygular ve onaltılık değeri sterlin simgesiyle dize olarak geri döndürür.

```typescript
function shadeColor(color: string, percent: number): string
```

#### <a name="example"></a>Örnek

```typescript
import { shadeColor } from "powerbi-visuals-utils-colorutils";

shadeColor('#000000', 0.1); // returns '#1a1a1a'
shadeColor('#FFFFFF', -0.5); // returns '#808080'
shadeColor('#00B8AA', -0.25); // returns '#008a80'
shadeColor('#00B8AA', 0); // returns '#00b8aa'
```

### <a name="rgbblend"></a>rgbBlend
Arka plan renginin üzerine opaklıkla bir renk katmanı uygular. Tüm alfa kanalları yoksayılır.

```typescript
function rgbBlend(foreColor: RgbColor, opacity: number, backColor: RgbColor): RgbColor
```

#### <a name="example"></a>Örnek

```typescript
import { rgbBlend} from "powerbi-visuals-utils-colorutils";

rgbBlend({R: 100, G: 100, B: 100}, 0.5, {R: 200, G: 200, B: 200});

// returns: {R: 150, G: 150, B: 150}
```

### <a name="channelblend"></a>channelBlend
İki renk için tek kanalı karıştırır.

```typescript
function channelBlend(foreChannel: number, opacity: number, backChannel: number): number
```

#### <a name="example"></a>Örnek

```typescript
import { channelBlend} from "powerbi-visuals-utils-colorutils";

channelBlend(0, 1, 255); // returns: 0
channelBlend(128, 1, 255); // returns: 128
channelBlend(255, 0, 0); // returns: 0
channelBlend(88, 0, 88); // returns: 88
```

### <a name="hexblend"></a>hexBlend
Arka plan renginin üzerine opaklıkla bir renk katmanı uygular.

```typescript
function hexBlend(foreColor: string, opacity: number, backColor: string): string
```

#### <a name="example"></a>Örnek

```typescript
import { hexBlend} from "powerbi-visuals-utils-colorutils";

let yellow = "#FFFF00",
    black = "#000000",
    white = "#FFFFFF";

hexBlend(yellow, 0.5, white); // returns: "#FFFF80"
hexBlend(white, 0.5, yellow); // returns: "#FFFF80"

hexBlend(yellow, 0.5, black); // returns: "#808000"
hexBlend(black, 0.5, yellow); // returns: "#808000"
```