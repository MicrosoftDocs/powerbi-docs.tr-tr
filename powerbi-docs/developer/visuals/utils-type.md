---
title: Power BI görselinde tür yardımcı programlarını kullanmaya giriş
description: Bu makalede Power BI görsellerinin temel türlerini genişletmek için SVG yardımcı programlarının nasıl kullanılacağı açıklanır
author: KesemSharabi
ms.author: kesharab
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 06/18/2019
ms.openlocfilehash: 5a3cfb7ea9c9f398193b45652aa43c6b83c8f70b
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "79378007"
---
# <a name="type-utils"></a>Yazma yardımcı programları

TypeUtils, Power BI görsellerinin temel türlerini genişletmeye yönelik bir işlev ve sınıf kümesidir.

## <a name="installation"></a>Yükleme

Paketi yüklemek için geçerli özel görselinizin dizininde aşağıdaki komutu çalıştırmalısınız:

npm install powerbi-visuals-utils-typeutils --save Bu komut paketi yükler ve package.json dosyanıza bağımlılık olarak bir paket ekler

## <a name="double"></a>Çift

`Double`, sayıların duyarlığını işleme özellikleri sağlar.

Modül aşağıdaki işlevleri sağlar:

### <a name="pow10"></a>pow10

Bu işlev 10 üssünü döndürür.

```typescript
function pow10(exp: number): number;
```

Örnek:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.pow10(25);

// returns: 1e+25
```

### <a name="log10"></a>log10

Bu işlev sayının 10 tabanında logaritmasını döndürür.

```typescript
function log10(val: number): number;
```

Örnek:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.log10(25);

// returns: 1
```

## <a name="getprecision"></a>getPrecision

Bu işlev sayının duyarlığını temsil eden 10 üssünü döndürür.

```typescript
function getPrecision(x: number, decimalDigits?: number): number;
```

Örnek:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.getPrecision(562344, 6);

// returns: 0.1
```

### <a name="equalwithprecision"></a>equalWithPrecision

Bu işlev iki sayı arasındaki deltanın sağlanan duyarlıktan küçük olup olmadığını denetler.

```typescript
function equalWithPrecision(x: number, y: number, precision?: number): boolean;
```

Örnek:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.equalWithPrecision(1, 1.005, 0.01);

// returns: true
```

### <a name="lesswithprecision"></a>lessWithPrecision

Bu işlev ilk değerin ikinci değerden küçük olup olmadığını denetler.

```typescript
function lessWithPrecision(x: number, y: number, precision?: number): boolean;
```

Örnek:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.lessWithPrecision(0.995, 1, 0.001);

// returns: true
```

### <a name="lessorequalwithprecision"></a>lessOrEqualWithPrecision

Bu işlev ilk değerin ikinci değerden küçük veya ona eşit olup olmadığını denetler.

```typescript
function lessOrEqualWithPrecision(x: number, y: number, precision?: number): boolean;
```

Örnek:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.lessOrEqualWithPrecision(1.005, 1, 0.01);

// returns: true
```

### <a name="greaterwithprecision"></a>greaterWithPrecision

Bu işlev ilk değerin ikinci değerden büyük olup olmadığını denetler.

```typescript
function greaterWithPrecision(x: number, y: number, precision?: number): boolean;
```

Örnek:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.greaterWithPrecision(1, 0.995, 0.01);

// returns: false
```

### <a name="greaterorequalwithprecision"></a>greaterOrEqualWithPrecision

Bu işlev ilk değerin ikinci değerden büyük veya ona eşit olup olmadığını denetler.

```typescript
function greaterOrEqualWithPrecision(x: number, y: number, precision?: number): boolean;
```

Örnek:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.greaterOrEqualWithPrecision(1, 1.005, 0.01);

// returns: true
```

### <a name="floorwithprecision"></a>floorWithPrecision

Bu işlev sağlanan duyarlıkla sayıdan büyük olmayan en büyük tamsayıyı verir.

```typescript
function floorWithPrecision(x: number, precision?: number): number;
```

Örnek:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.floorWithPrecision(5.96, 0.001);

// returns: 5
```

### <a name="ceilwithprecision"></a>ceilWithPrecision

Bu işlev sağlanan duyarlıkla sayıdan küçük olmayan en küçük tamsayıyı verir (`ceils`).

```typescript
function ceilWithPrecision(x: number, precision?: number): number;
```

Örnek:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.ceilWithPrecision(5.06, 0.001);

// returns: 6
```

### <a name="floortoprecision"></a>floorToPrecision

Bu işlev sağlanan duyarlığa göre sayıdan büyük olmayan en büyük tamsayıyı verir.

```typescript
function floorToPrecision(x: number, precision?: number): number;
```

Örnek:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.floorToPrecision(5.96, 0.1);

// returns: 5.9
```

### <a name="ceiltoprecision"></a>ceilToPrecision

Bu işlev sağlanan duyarlığa göre sayıdan küçük olmayan en küçük büyük tamsayıyı verir (`ceils`).

```typescript
function ceilToPrecision(x: number, precision?: number): number;
```

Örnek:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.ceilToPrecision(-506, 10);

// returns: -500
```

### <a name="roundtoprecision"></a>roundToPrecision

Bu işlev sağlanan duyarlığa göre sayıyı yuvarlar.

```typescript
function roundToPrecision(x: number, precision?: number): number;
```

Örnek:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.roundToPrecision(596, 10);

// returns: 600
```

### <a name="ensureinrange"></a>ensureInRange

Bu işlev en küçük ve en büyük arasındaki bir sayıyı döndürür.

```typescript
function ensureInRange(x: number, min: number, max: number): number;
```

Örnek:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.ensureInRange(-27.2, -10, -5);

// returns: -10
```

### <a name="round"></a>round

Bu işlev sayıyı yuvarlar.

```typescript
function round(x: number): number;
```

Örnek:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.round(27.45);

// returns: 27
```

### <a name="removedecimalnoise"></a>removeDecimalNoise

Bu işlev ondalık kalabalığı kaldırır.

```typescript
function removeDecimalNoise(value: number): number;
```

Örnek:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.removeDecimalNoise(21.493000000000002);

// returns: 21.493
```

### <a name="isinteger"></a>isInteger

Bu işlev sayının tamsayı olup olmadığını denetler.

```typescript
function isInteger(value: number): boolean;
```

Örnek:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.isInteger(21.493000000000002);

// returns: false
```

### <a name="toincrement"></a>toIncrement

Bu işlev sayıyı sağlanan sayıda artırır ve yuvarlanan sayıyı döndürür.

```typescript
function toIncrement(value: number, increment: number): number;
```

Örnek:

```typescript
import { double } from "powerbi-visuals-utils-typeutils";
// ...

double.toIncrement(0.6383723, 0.05);

// returns: 0.65
```

## <a name="prototype"></a>Prototype

`Prototype` nesneleri devralma özellikleri sağlar.

Modül aşağıdaki işlevleri sağlar:

## <a name="inherit"></a>inherit

Bu işlev sağlanan nesneyi prototip olarak kullanarak yeni bir nesne döndürür.

```typescript
function inherit<T>(obj: T, extension?: (inherited: T) => void): T;
```

Örnek:

```typescript
import { prototype } from "powerbi-visuals-utils-typeutils";
// ...

let base = { Microsoft: "Power BI" };

prototype.inherit(base);

/* returns: {
    __proto__: {
        Microsoft: "Power BI"
    }
}*/
```

## <a name="inheritsingle"></a>inheritSingle

Bu işlev, prototipin ayarlanmamış olması koşuluyla, sağlanan nesneyi prototip olarak kullanarak yeni bir nesne döndürür.

```typescript
function inheritSingle<T>(obj: T): T;
```

Örnek:

```typescript
import { prototype } from "powerbi-visuals-utils-typeutils";
// ...

let base = { Microsoft: "Power BI" };

prototype.inheritSingle(base);

/* returns: {
    __proto__: {
        Microsoft: "Power BI"
    }
}*/
```

## <a name="pixelconverter"></a>PixelConverter

`PixelConverter` pikselleri noktalara ve noktaları piksellere dönüştürme özelliği sağlar.

Modül aşağıdaki işlevleri sağlar:

## <a name="tostring"></a>toString

Bu işlev piksel değerini dizeye dönüştürür.

```typescript
function toString(px: number): string;
```

Örnek:

```typescript
import { pixelConverter } from "powerbi-visuals-utils-typeutils";
// ...

pixelConverter.toString(25);

// returns: 25px
```

## <a name="frompoint"></a>fromPoint

Bu işlev sağlanan nokta değerini piksel değerine dönüştürür ve dize yorumunu döndürür.

```typescript
function fromPoint(pt: number): string;
```

Örnek:

```typescript
import { pixelConverter } from "powerbi-visuals-utils-typeutils";
// ...

pixelConverter.fromPoint(8);

// returns: 33.33333333333333px
```

## <a name="frompointtopixel"></a>fromPointToPixel

Bu işlev sağlanan nokta değerini piksel değerine dönüştürür.

```typescript
function fromPointToPixel(pt: number): number;
```

Örnek:

```typescript
import { pixelConverter } from "powerbi-visuals-utils-typeutils";
// ...

pixelConverter.fromPointToPixel(8);

// returns: 10.666666666666666
```

## <a name="topoint"></a>toPoint

Bu işlev piksel değerini nokta değerine dönüştürür.

```typescript
function toPoint(px: number): number;
```

Örnek:

```typescript
import { pixelConverter } from "powerbi-visuals-utils-typeutils";
// ...

pixelConverter.toPoint(8);

// returns: 6
```
