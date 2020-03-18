---
title: Power BI görselinde biçimlendirme yardımcı programlarını kullanmaya giriş
description: Bu makalede Power BI görselinde değerleri biçimlendirmek ve değerlere yerelleştirme uygulamak için biçimlendirme yardımcı programlarını kullanma işlemi açıklanır
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
manager: rkarlin
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 06/18/2019
ms.openlocfilehash: dc2d036ab1e3e3dab551269163ced2f066a71626
ms.sourcegitcommit: 6bbc3d0073ca605c50911c162dc9f58926db7b66
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79378036"
---
# <a name="formatting-utils"></a>Biçimlendirme yardımcı programları

Biçimlendirme yardımcı programları, değerleri biçimlendirmeye yönelik sınıfları, arabirimleri ve yöntemleri içerir. Ayrıca SVG/HTML belgesinde dizeleri işlemek ve metin boyutunu ölçmek için genişletici yöntemlerini içerir.

## <a name="text-measurement-service"></a>Metin ölçümü hizmeti

Modül aşağıdaki işlevleri ve arabirimleri sağlar:

### <a name="textproperties-interface"></a>TextProperties arabirimi

Bu arabirim metnin ortak özelliklerini açıklar.

```typescript
interface TextProperties {
    text?: string;
    fontFamily: string;
    fontSize: string;
    fontWeight?: string;
    fontStyle?: string;
    fontVariant?: string;
    whiteSpace?: string;
}
```

### <a name="measuresvgtextwidth"></a>measureSvgTextWidth

Bu işlev verili SVG metin özellikleriyle metnin genişliğini ölçer.

```typescript
function measureSvgTextWidth(textProperties: TextProperties, text?: string): number;
```

`measureSvgTextWidth` kullanım örneği:

```typescript
import { textMeasurementService } from "powerbi-visuals-utils-formattingutils";
import TextProperties = textMeasurementService.TextProperties;
// ...

let textProperties: TextProperties = {
    text: "Microsoft PowerBI",
    fontFamily: "sans-serif",
    fontSize: "24px"
};

textMeasurementService.measureSvgTextWidth(textProperties);

// returns: 194.71875
```

### <a name="measuresvgtextrect"></a>measureSvgTextRect

Bu işlev verili SVG metin özellikleriyle bir dikdörtgen döndürür.

```typescript
function measureSvgTextRect(textProperties: TextProperties, text?: string): SVGRect;
```

`measureSvgTextRect` kullanım örneği:

```typescript
import { textMeasurementService } from "powerbi-visuals-utils-formattingutils";
import TextProperties = textMeasurementService.TextProperties;
// ...

let textProperties: TextProperties = {
    text: "Microsoft PowerBI",
    fontFamily: "sans-serif",
    fontSize: "24px"
};

textMeasurementService.measureSvgTextRect(textProperties);

// returns: { x: 0, y: -22, width: 194.71875, height: 27 }
```

### <a name="measuresvgtextheight"></a>measureSvgTextHeight

Bu işlev verili SVG metin özellikleriyle metnin yüksekliğini ölçer.

```typescript
function measureSvgTextHeight(textProperties: TextProperties, text?: string): number;
```

`measureSvgTextHeight` kullanım örneği:

```typescript
import { textMeasurementService } from "powerbi-visuals-utils-formattingutils";
import TextProperties = textMeasurementService.TextProperties;
// ...


let textProperties: TextProperties = {
    text: "Microsoft PowerBI",
    fontFamily: "sans-serif",
    fontSize: "24px"
};

textMeasurementService.measureSvgTextHeight(textProperties);

// returns: 27
```

### <a name="estimatesvgtextbaselinedelta"></a>estimateSvgTextBaselineDelta

Bu işlev verili SVG metin özelliklerinin temelini döndürür.

```typescript
function estimateSvgTextBaselineDelta(textProperties: TextProperties): number;
```

Örnek:

```typescript
import { textMeasurementService } from "powerbi-visuals-utils-formattingutils";
import TextProperties = textMeasurementService.TextProperties;
// ...

let textProperties: TextProperties = {
    text: "Microsoft PowerBI",
    fontFamily: "sans-serif",
    fontSize: "24px"
};

textMeasurementService.estimateSvgTextBaselineDelta(textProperties);

// returns: 5
```

### <a name="estimatesvgtextheight"></a>estimateSvgTextHeight

Bu işlev verili SVG metin özellikleriyle metnin yüksekliğini tahmin eder.

```typescript
function estimateSvgTextHeight(textProperties: TextProperties, tightFightForNumeric?: boolean): number;
```

`estimateSvgTextHeight` kullanım örneği:

```typescript
import { textMeasurementService } from "powerbi-visuals-utils-formattingutils";
import TextProperties = textMeasurementService.TextProperties;
// ...

let textProperties: TextProperties = {
    text: "Microsoft PowerBI",
    fontFamily: "sans-serif",
    fontSize: "24px"
};

textMeasurementService.estimateSvgTextHeight(textProperties);

// returns: 27
```

[Burada](https://github.com/Microsoft/powerbi-visuals-sankey/blob/4d544ea145b4e15006083a3610dfead3da5f61a4/src/visual.ts#L372) örnek özel görsel kodunu gözden geçirebilirsiniz.

### <a name="measuresvgtextelementwidth"></a>measureSvgTextElementWidth

Bu işlev svgElement'in genişliğini ölçer.

```typescript
function measureSvgTextElementWidth(svgElement: SVGTextElement): number;
```

measureSvgTextElementWidth kullanım örneği:

```typescript
import { textMeasurementService } from "powerbi-visuals-utils-formattingutils";
// ...

let svg: D3.Selection = d3.select("body").append("svg");

svg.append("text")
    .text("Microsoft PowerBI")
    .attr({
        "x": 25,
        "y": 25
    })
    .style({
        "font-family": "sans-serif",
        "font-size": "24px"
    });

let textElement: D3.Selection = svg.select("text");

textMeasurementService.measureSvgTextElementWidth(textElement.node());

// returns: 194.71875
```

### <a name="getmeasurementproperties"></a>getMeasurementProperties

Bu işlev verili DOM öğesinin metin ölçümü özelliklerini getirir.

```typescript
function getMeasurementProperties(element: Element): TextProperties;
```

`getMeasurementProperties` kullanım örneği:

```typescript
import { textMeasurementService } from "powerbi-visuals-utils-formattingutils";
// ...

let element: JQuery = $(document.createElement("div"));

element.text("Microsoft PowerBI");

element.css({
    "width": 500,
    "height": 500,
    "font-family": "sans-serif",
    "font-size": "32em",
    "font-weight": "bold",
    "font-style": "italic",
    "white-space": "nowrap"
});

textMeasurementService.getMeasurementProperties(element.get(0));

/* returns: {
    fontFamily:"sans-serif",
    fontSize: "32em",
    fontStyle: "italic",
    fontVariant: "",
    fontWeight: "bold",
    text: "Microsoft PowerBI",
    whiteSpace: "nowrap"
}*/
```

### <a name="getsvgmeasurementproperties"></a>getSvgMeasurementProperties

Bu işlev verili SVG metin öğesinin metin ölçümü özelliklerini getirir.

```typescript
function getSvgMeasurementProperties(svgElement: SVGTextElement): TextProperties;
```

`getSvgMeasurementProperties` kullanım örneği:

```typescript
import { textMeasurementService } from "powerbi-visuals-utils-formattingutils";
// ...

let svg: D3.Selection = d3.select("body").append("svg");

let textElement: D3.Selection = svg.append("text")
    .text("Microsoft PowerBI")
    .attr({
        "x": 25,
        "y": 25
    })
    .style({
        "font-family": "sans-serif",
        "font-size": "24px"
    });

textMeasurementService.getSvgMeasurementProperties(textElement.node());

/* returns: {
    "text": "Microsoft PowerBI",
    "fontFamily": "sans-serif",
    "fontSize": "24px",
    "fontWeight": "normal",
    "fontStyle": "normal",
    "fontVariant": "normal",
    "whiteSpace": "nowrap"
}*/
```

## <a name="getdivelementwidth"></a>getDivElementWidth

Bu işlev div öğesinin genişliğini döndürür.

```typescript
function getDivElementWidth(element: JQuery): string;
```

`getDivElementWidth` kullanım örneği:

```typescript
import { textMeasurementService } from "powerbi-visuals-utils-formattingutils";
// ...

let svg: Element = d3.select("body")
    .append("div")
    .style({
        "width": "150px",
        "height": "150px"
    })
    .node();

textMeasurementService.getDivElementWidth(svg)

// returns: 150px
```

### <a name="gettailoredtextordefault"></a>getTailoredTextOrDefault

Etiketlerin metin boyutunu kullanılabilir boyutla karşılaştırır ve kullanılabilir boyut daha küçükse üç noktalar oluşturur.

```typescript
function getTailoredTextOrDefault(textProperties: TextProperties, maxWidth: number): string;
```

`getTailoredTextOrDefault` kullanım örneği:

```typescript
import { textMeasurementService } from "powerbi-visuals-utils-formattingutils";
import TextProperties = textMeasurementService.TextProperties;
// ...

let textProperties: TextProperties = {
    text: "Microsoft PowerBI!",
    fontFamily: "sans-serif",
    fontSize: "24px"
};

textMeasurementService.getTailoredTextOrDefault(textProperties, 100);

// returns: Micros...
```

## <a name="string-extensions"></a>Dize uzantıları

Modül aşağıdaki işlevleri sağlar:

## <a name="endswith"></a>endsWith

Bu işlev dizenin bir alt dize ile bitip bitmediğini denetler.

```typescript
function endsWith(str: string, suffix: string): boolean;
```

`endsWith` kullanım örneği:

```typescript
import { stringExtensions } from "powerbi-visuals-utils-formattingutils";
// ...

stringExtensions.endsWith("Power BI", "BI");

// returns: true
```

### <a name="equalignorecase"></a>equalIgnoreCase

Bu işlev, büyük/küçük harf kullanımını yoksayarak dizeleri karşılaştırır.

```typescript
function equalIgnoreCase(a: string, b: string): boolean;
```

`equalIgnoreCase` kullanım örneği:

```typescript
import { stringExtensions } from "powerbi-visuals-utils-formattingutils";
// ...

stringExtensions.equalIgnoreCase("Power BI", "power bi");

// returns: true
```

### <a name="startswith"></a>startsWith

Bu işlev dizenin bir alt dize ile başlayıp başlamadığını denetler.

```typescript
function startsWith(a: string, b: string): boolean;
```

`startsWith` kullanım örneği:

```typescript
import { stringExtensions } from "powerbi-visuals-utils-formattingutils";
// ...

stringExtensions.startsWith("Power BI", "Power");

// returns: true
```

### <a name="contains"></a>içerir

Bu işlev dizenin belirtilen alt dizeyi içerip içermediğini denetler.

```typescript
function contains(source: string, substring: string): boolean;
```

`contains` yöntemi kullanım örneği:

```typescript
import { stringExtensions } from "powerbi-visuals-utils-formattingutils";
// ...

stringExtensions.contains("Microsoft Power BI Visuals", "Power BI");

// returns: true
```

### <a name="isnullorempty"></a>isNullOrEmpty

Dizenin null, tanımsız veya boş olup olmadığını denetler.

```typescript
function isNullOrEmpty(value: string): boolean;
```

`isNullOrEmpty` yöntemi örneği:

```typescript
import { stringExtensions } from "powerbi-visuals-utils-formattingutils";
// ...

stringExtensions.isNullOrEmpty(null);

// returns: true
```

## <a name="value-formatter"></a>Değer biçimlendiricisi

Modül aşağıdaki işlevleri, arabirimleri ve sınıfları sağlar:

## <a name="ivalueformatter"></a>IValueFormatter

Bu arabirim biçimlendiricinin genel yöntemlerini ve özelliklerini açıklar.

```typescript
interface IValueFormatter {
    format(value: any): string;
    displayUnit?: DisplayUnit;
    options?: ValueFormatterOptions;
}
```

### <a name="ivalueformatterformat"></a>IValueFormatter.format

Bu yöntem verilen değeri biçimlendirir.

```typescript
function format(value: any, format?: string, allowFormatBeautification?: boolean): string;
```

`IValueFormatter.format` örnekleri:

#### <a name="the-thousand-formats"></a>Binlik biçimleri

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

let iValueFormatter = valueFormatter.create({ value: 1001 });

iValueFormatter.format(5678);

// returns: "5.68K"
```

#### <a name="the-million-formats"></a>Milyon biçimleri

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

let iValueFormatter = valueFormatter.create({ value: 1e6 });

iValueFormatter.format(1234567890);

// returns: "1234.57M"
```

#### <a name="the-billion-formats"></a>Milyar biçimleri

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

let iValueFormatter = valueFormatter.create({ value: 1e9 });

iValueFormatter.format(1234567891236);

// returns: 1234.57bn
```

#### <a name="the-trillion-format"></a>Trilyon biçimleri

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

let iValueFormatter = valueFormatter.create({ value: 1e12 });

iValueFormatter.format(1234567891236);

// returns: 1.23T
```

#### <a name="the-exponent-format"></a>Üs biçimi

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

let iValueFormatter = valueFormatter.create({ format: "E" });

iValueFormatter.format(1234567891236);

// returns: 1.234568E+012
```

### <a name="the-culture-selector"></a>Kültür seçicisi

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

let valueFormatterUK = valueFormatter.create({ cultureSelector: "en-GB" });

valueFormatterUK.format(new Date(2007, 2, 3, 17, 42, 42));

// returns: 03/03/2007 17:42:42

let valueFormatterUSA = valueFormatter.create({ cultureSelector: "en-US" });

valueFormatterUSA.format(new Date(2007, 2, 3, 17, 42, 42));

// returns: 3/3/2007 5:42:42 PM
```

#### <a name="the-percentage-format"></a>Yüzde biçimi

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

let iValueFormatter = valueFormatter.create({ format: "0.00 %;-0.00 %;0.00 %" });

iValueFormatter.format(0.54);

// returns: 54.00 %
```

#### <a name="the-dates-format"></a>Tarih biçimi

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

let date = new Date(2016, 10, 28, 15, 36, 0),
    iValueFormatter = valueFormatter.create({});

iValueFormatter.format(date);

// returns: 11/28/2016 3:36:00 PM
```

#### <a name="the-boolean-format"></a>Boole biçimi

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

let iValueFormatter = valueFormatter.create({});

iValueFormatter.format(true);

// returns: True
```

#### <a name="the-customized-precision"></a>Özelleştirilmiş duyarlık

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

let iValueFormatter = valueFormatter.create({ value: 0, precision: 3 });

iValueFormatter.format(3.141592653589793);

// returns: 3.142
```

[Burada](https://github.com/Microsoft/powerbi-visuals-sankey/blob/4d544ea145b4e15006083a3610dfead3da5f61a4/src/visual.ts#L359) örnek özel görsel kodunu gözden geçirebilirsiniz.

## <a name="valueformatteroptions"></a>ValueFormatterOptions

Bu arabirim IValueFormatter'ın `options` öğesini ve 'create' işlevinin seçeneklerini açıklar.

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";
import ValueFormatterOptions = valueFormatter.ValueFormatterOptions;

interface ValueFormatterOptions {
    /** The format string to use. */
    format?: string;
    /** The data value. */
    value?: any;
    /** The data value. */
    value2?: any;
    /** The number of ticks. */
    tickCount?: any;
    /** The display unit system to use */
    displayUnitSystemType?: DisplayUnitSystemType;
    /** True if we are formatting single values in isolation (e.g. card), as opposed to multiple values with a common base (e.g. chart axes) */
    formatSingleValues?: boolean;
    /** True if we want to trim off unnecessary zeroes after the decimal and remove a space before the % symbol */
    allowFormatBeautification?: boolean;
    /** Specifies the maximum number of decimal places to show*/
    precision?: number;
    /** Detect axis precision based on value */
    detectAxisPrecision?: boolean;
    /** Specifies the column type of the data value */
    columnType?: ValueTypeDescriptor;
    /** Specifies the culture */
    cultureSelector?: string;
}
```

## <a name="create"></a>oluştur

Bu yöntem bir IValueFormatter örneği oluşturur.

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";
import create = valueFormatter.create;

function create(options: ValueFormatterOptions): IValueFormatter;
```

### <a name="example-of-using-create"></a>create yöntemi kullanım örneği

```typescript
import { valueFormatter } from "powerbi-visuals-utils-formattingutils";

valueFormatter.create({});

// returns: an instance of IValueFormatter.
```

## <a name="next-steps"></a>Sonraki adımlar

[Power BI özel görseline yerelleştirmeler ekleme](localization.md)  
