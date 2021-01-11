---
title: Daha iyi tümleşik BI içgörüleri için Power BI tümleşik analizlerindeki Power BI görsellerinde SVG yardımcı programları kullanmaya giriş
description: Bu makalede, Power BI görselleri için SVG işlemlerini kolaylaştırmak amacıyla SVG yardımcı programlarının nasıl kullanılacağı anlatılmaktadır. Power BI tümleşik analiz kullanarak daha iyi tümleşik BI içgörüleri elde edin.
author: KesemSharabi
ms.author: kesharab
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 06/18/2019
ms.openlocfilehash: cf798ae13d874e354f6941d50982bfe26d73424d
ms.sourcegitcommit: eeaf607e7c1d89ef7312421731e1729ddce5a5cc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2021
ms.locfileid: "97887765"
---
# <a name="svg-utils"></a>SVG yardımcı programları

SVGUtils, Power BI görselleri için SVG işlemelerini kolaylaştırmaya yönelik bir dizi işlev ve sınıftır

## <a name="installation"></a>Yükleme

Paketi yüklemek için geçerli görselinizin dizininde aşağıdaki komutu çalıştırmalısınız:

```bash
npm install powerbi-visuals-utils-svgutils --save
```

## <a name="cssconstants"></a>CssConstants

`CssConstants` modülü, sınıf seçicileriyle çalışacak özel işlevi ve arabirimi sağlar.

`powerbi.extensibility.utils.svg.CssConstants` modülü şu işlevi ve arabirimi sağlar:

## <a name="classandselector"></a>ClassAndSelector

Bu arabirim sınıf seçicinin ortak özelliklerini açıklar.

```typescript
interface ClassAndSelector {
  class: string;
  selector: string;
}
```

### <a name="createclassandselector"></a>createClassAndSelector

Bu işlev, sınıfın verili adıyla bir ClassAndSelector örneği oluşturur.

```typescript
function createClassAndSelector(className: string): ClassAndSelector;
```

Örnek:

```typescript
import { CssConstants } from "powerbi-visuals-utils-svgutils";
import createClassAndSelector = CssConstants.createClassAndSelector;
import ClassAndSelector = CssConstants.ClassAndSelector;

let divSelector: ClassAndSelector = createClassAndSelector("sample-block");

divSelector.selector === ".sample-block"; // returns: true
divSelector.class === "sample-block"; // returns: true
```

## <a name="manipulation"></a>manipulation

`manipulation`, SVG dönüştürme özelliğiyle kullanılacak dizeleri oluşturmak için bazı özel işlevler sağlar.

Modül aşağıdaki işlevleri sağlar:

### <a name="translate"></a>translate

Bu işlev SVG transform özelliğiyle kullanılacak bir translate dizesi oluşturur.

```typescript
function translate(x: number, y: number): string;
```

Örnek:

```typescript
import { manipulation } from "powerbi-visuals-utils-svgutils";
// ...

manipulation.translate(100, 100);

// returns: translate(100,100)
```

### <a name="translatexwithpixels"></a>translateXWithPixels

Bu işlev SVG transform özelliğiyle kullanılacak bir translateX dizesi oluşturur.

```typescript
function translateXWithPixels(x: number): string;
```

Örnek:

```typescript
import { manipulation } from "powerbi-visuals-utils-svgutils";
// ...

manipulation.translateXWithPixels(100);

// returns: translateX(100px)
```

### <a name="translatewithpixels"></a>translateWithPixels

Bu işlev SVG transform özelliğiyle kullanılacak bir translate dizesi oluşturur.

```typescript
function translateWithPixels(x: number, y: number): string;
```

Örnek:

```typescript
import { manipulation } from "powerbi-visuals-utils-svgutils";
// ...

manipulation.translateWithPixels(100, 100);

// returns: translate(100px,100px)
```

### <a name="translateandrotate"></a>translateAndRotate

Bu işlev SVG transform özelliğiyle kullanılacak bir translate-rotate dizesi oluşturur.

```typescript
function translateAndRotate(
  x: number,
  y: number,
  px: number,
  py: number,
  angle: number
): string;
```

Örnek:

```typescript
import { manipulation } from "powerbi-visuals-utils-svgutils";
// ...

manipulation.translateAndRotate(100, 100, 50, 50, 35);

// returns: translate(100,100) rotate(35,50,50)
```

### <a name="scale"></a>scale

Bu işlev CSS transform özelliği için kullanılacak bir scale dizesi oluşturur.

```typescript
function scale(scale: number): string;
```

Örnek:

```typescript
import { manipulation } from "powerbi-visuals-utils-svgutils";
// ...

manipulation.scale(50);

// returns: scale(50)
```

### <a name="transformorigin"></a>transformOrigin

Bu işlev CSS transform-origin özelliği için kullanılacak bir transform-origin dizesi oluşturur.

```typescript
function transformOrigin(xOffset: string, yOffset: string): string;
```

Örnek:

```typescript
import { manipulation } from "powerbi-visuals-utils-svgutils";
// ...

manipulation.transformOrigin(5, 5);

// returns: 5 5
```

### <a name="flushalld3transitions"></a>flushAllD3Transitions

Bu işlev her D3 geçişinin tamamlanmasını zorunlu tutar.

```typescript
function flushAllD3Transitions(): void;
```

Örnek:

```typescript
import { manipulation } from "powerbi-visuals-utils-svgutils";
// ...

manipulation.flushAllD3Transitions();

// forces every transition of D3 to complete
```

### <a name="parsetranslatetransform"></a>parseTranslateTransform

Bu işlev transform dizesini "translate(x,y)" değeriyle ayrıştırır.

```typescript
function parseTranslateTransform(input: string): { x: string; y: string };
```

Örnek:

```typescript
import { manipulation } from "powerbi-visuals-utils-svgutils";
// ...

manipulation.parseTranslateTransform("translate(100px,100px)");

// returns: { "x":"100px", "y":"100px" }
```

### <a name="createarrow"></a>createArrow

Bu işlev bir ok oluşturur.

```typescript
function createArrow(
  width: number,
  height: number,
  rotate: number
): { path: string; transform: string };
```

Örnek:

```typescript
import { manipulation } from "powerbi-visuals-utils-svgutils";
// ...

manipulation.createArrow(10, 20, 5);

/* returns: {
    "path": "M0 0L0 20L10 10 Z",
    "transform": "rotate(5 5 10)"
}*/
```

## <a name="rect"></a>Rect

`Rect` modülü dikdörtgenleri işlemeye yönelik bazı özel işlevler sağlar.

Modül aşağıdaki işlevleri sağlar:

### <a name="getoffset"></a>getOffset

Bu işlev dikdörtgenin farkını döndürür.

```typescript
function getOffset(rect: IRect): IPoint;
```

Örnek:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.getOffset({ left: 25, top: 25, width: 100, height: 100 });

/* returns: {
    x: 25,
    y: 25
}*/
```

### <a name="getsize"></a>getSize

Bu işlev dikdörtgenin boyutunu döndürür.

```typescript
function getSize(rect: IRect): ISize;
```

Örnek:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.getSize({ left: 25, top: 25, width: 100, height: 100 });

/* returns: {
    width: 100,
    height: 100
}*/
```

### <a name="setsize"></a>setSize

Bu işlev dikdörtgenin boyutunu değiştirir.

```typescript
function setSize(rect: IRect, value: ISize): void;
```

Örnek:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

let rectangle = { left: 25, top: 25, width: 100, height: 100 };

Rect.setSize(rectangle, { width: 250, height: 250 });

// rectangle === { left: 25, top: 25, width: 250, height: 250 }
```

### <a name="right"></a>sağ

Bu işlev dikdörtgenin sağ konumunu döndürür.

```typescript
function right(rect: IRect): number;
```

Örnek:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.right({ left: 25, top: 25, width: 100, height: 100 });

// returns: 125
```

### <a name="bottom"></a>bottom

Bu işlev dikdörtgenin alt konumunu döndürür.

```typescript
function bottom(rect: IRect): number;
```

Örnek:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.bottom({ left: 25, top: 25, width: 100, height: 100 });

// returns: 125
```

### <a name="topleft"></a>topLeft

Bu işlev dikdörtgenin sol üst konumunu döndürür.

```typescript
function topLeft(rect: IRect): IPoint;
```

Örnek:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.topLeft({ left: 25, top: 25, width: 100, height: 100 });

// returns: { x: 25, y: 25 }
```

### <a name="topright"></a>topRight

Bu işlev dikdörtgenin sağ üst konumunu döndürür.

```typescript
function topRight(rect: IRect): IPoint;
```

Örnek:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.topRight({ left: 25, top: 25, width: 100, height: 100 });

// returns: { x: 125, y: 25 }
```

### <a name="bottomleft"></a>bottomLeft

Bu işlev dikdörtgenin sol alt konumunu döndürür.

```typescript
function bottomLeft(rect: IRect): IPoint;
```

Örnek:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.bottomLeft({ left: 25, top: 25, width: 100, height: 100 });

// returns: { x: 25, y: 125 }
```

### <a name="bottomright"></a>bottomRight

Bu işlev dikdörtgenin sağ alt konumunu döndürür.

```typescript
function bottomRight(rect: IRect): IPoint;
```

### <a name="example"></a>Örnek

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.bottomRight({ left: 25, top: 25, width: 100, height: 100 });

// returns: { x: 125, y: 125 }
```

### <a name="clone"></a>clone

Bu işlev dikdörtgenin kopyasını oluşturur.

```typescript
function clone(rect: IRect): IRect;
```

Örnek:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.clone({ left: 25, top: 25, width: 100, height: 100 });

/* returns: {
    left: 25, top: 25, width: 100, height: 100}
*/
```

### <a name="tostring"></a>toString

Bu işlev dikdörtgeni dizeye dönüştürür.

```typescript
function toString(rect: IRect): string;
```

Örnek:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.toString({ left: 25, top: 25, width: 100, height: 100 });

// returns: {left:25, top:25, width:100, height:100}
```

### <a name="offset"></a>uzaklık

Bu işlev verili farkı dikdörtgene uygular.

```typescript
function offset(rect: IRect, offsetX: number, offsetY: number): IRect;
```

Örnek:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.offset({ left: 25, top: 25, width: 100, height: 100 }, 50, 50);

/* returns: {
    left: 75,
    top: 75,
    width: 100,
    height: 100
}*/
```

### <a name="add"></a>add

Bu işlev ilk dikdörtgeni ikinci dikdörtgene ekler.

```typescript
function add(rect: IRect, rect2: IRect): IRect;
```

Örnek:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.add(
  { left: 25, top: 25, width: 100, height: 100 },
  { left: 50, top: 50, width: 75, height: 75 }
);

/* returns: {
    left: 75,
    top: 75,
    height: 175,
    width: 175
}*/
```

### <a name="getclosestpoint"></a>getClosestPoint

Bu işlev verilen noktaya dikdörtgen üzerindeki en yakın noktayı döndürür.

```typescript
function getClosestPoint(rect: IRect, x: number, y: number): IPoint;
```

Örnek:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.getClosestPoint({ left: 0, top: 0, width: 100, height: 100 }, 50, 50);

/* returns: {
    x: 50,
    y: 50
}*/
```

### <a name="equal"></a>equal

Bu işlev dikdörtgenleri karşılaştırır ve bunlar aynıysa True değerini döndürür.

```typescript
function equal(rect1: IRect, rect2: IRect): boolean;
```

Örnek:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.equal(
  { left: 0, top: 0, width: 100, height: 100 },
  { left: 50, top: 50, width: 100, height: 100 }
);

// returns: false
```

### <a name="equalwithprecision"></a>equalWithPrecision

Bu işlev değerlerin duyarlığını dikkate alarak dikdörtgenleri karşılaştırır.

```typescript
function equalWithPrecision(rect1: IRect, rect2: IRect): boolean;
```

Örnek:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.equalWithPrecision(
  { left: 0, top: 0, width: 100, height: 100 },
  { left: 50, top: 50, width: 100, height: 100 }
);

// returns: false
```

### <a name="isempty"></a>isEmpty

Bu işlev dikdörtgenin boş olup olmadığını denetler.

```typescript
function isEmpty(rect: IRect): boolean;
```

Örnek:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.isEmpty({ left: 0, top: 0, width: 0, height: 0 });

// returns: true
```

### <a name="containspoint"></a>containsPoint

Bu işlev dikdörtgenin nokta içerip içermediğini denetler.

```typescript
function containsPoint(rect: IRect, point: IPoint): boolean;
```

Örnek:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.containsPoint(
  { left: 0, top: 0, width: 100, height: 100 },
  { x: 50, y: 50 }
);

// returns: true
```

### <a name="isintersecting"></a>isIntersecting

Bu işlev dikdörtgenlerin kesişip kesişmediğini denetler.

```typescript
function isIntersecting(rect1: IRect, rect2: IRect): boolean;
```

Örnek:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.isIntersecting(
  { left: 0, top: 0, width: 100, height: 100 },
  { left: 0, top: 0, width: 50, height: 50 }
);

// returns: true
```

### <a name="intersect"></a>intersect

Bu işlev dikdörtgenlerin kesişimini döndürür.

```typescript
function intersect(rect1: IRect, rect2: IRect): IRect;
```

Örnek:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.intersect(
  { left: 0, top: 0, width: 100, height: 100 },
  { left: 0, top: 0, width: 50, height: 50 }
);

/* returns: {
    left: 0,
    top: 0,
    width: 50,
    height: 50
}*/
```

### <a name="combine"></a>combine

Bu işlev dikdörtgenleri birleştirir.

```typescript
function combine(rect1: IRect, rect2: IRect): IRect;
```

Örnek:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.combine(
  { left: 0, top: 0, width: 100, height: 100 },
  { left: 0, top: 0, width: 50, height: 120 }
);

/* returns: {
    left: 0,
    top: 0,
    width: 100,
    height: 120
}*/
```

### <a name="getcentroid"></a>getCentroid

Bu işlev dikdörtgenin orta noktasını döndürür.

```typescript
function getCentroid(rect: IRect): IPoint;
```

Örnek:

```typescript
import { shapes } from "powerbi-visuals-utils-svgutils";
import Rect = shapes.Rect;
// ...

Rect.getCentroid({ left: 0, top: 0, width: 100, height: 100 });

/* returns: {
    x: 50,
    y: 50
}*/
```

## <a name="pointer"></a>pointer

`pointer` modülü, işaretçinin konumunu almak için özel bir işlev sağlar.

Modül şu işlevi sağlar:

### <a name="getcoordinates"></a>getCoordinates

Bu işlev işaretçinin konumunu döndürür.

```typescript
function getCoordinates(rootNode: Element, isPointerEvent: boolean): number[];
```

Örnek:

```typescript
import { pointer } from "powerbi-visuals-utils-svgutils";

let bodySelection = d3.select("body");

bodySelection
  .append("div")
  .style({
    width: "100px",
    height: "100px",
    "background-color": "green"
  })
  .on("click", () => {
    pointer.getCoordinates(bodySelection.node(), true);
  });

// click element, after that you will get position of the pointer
```
