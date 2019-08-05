---
title: Görsel Filtreler API’si
description: Power BI Görsellerinin diğer görselleri filtreleme biçimi
author: sranins
ms.author: rasala
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 50e9601faf497675ebc3f24609a856a600e3bcb1
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425057"
---
# <a name="power-bi-visual-filters-api"></a>Power BI Görselleri Filtreler API’si

Filtre görsel, verilere filtre uygulanmasına olanak sağlar. Seçimlerdeki temel fark, diğer görsel tarafından desteklenmesine rağmen, diğer görsellerin herhangi bir şekilde filtrelenmesidir.

Görsel için filtrelemeyi etkinleştirmek üzere, görsel capabilities.json içeriğinin `general` bölümünde `filter` nesnesini içermelidir.

```json
"objects": {
        "general": {
            "displayName": "General",
            "displayNameKey": "formattingGeneral",
            "properties": {
                "filter": {
                    "type": {
                        "filter": true
                    }
                }
            }
        }
    }
```

Filtre API arabirimlerini [`powerbi-models`](https://www.npmjs.com/package/powerbi-models) paketinde bulabilirsiniz. Paket, filtre örnekleri oluşturmak için sınıflar da içerir.

```cmd
npm install powerbi-models --save
```

Eski sürüm araçlarını (3.x.x sürümünden önceki bir sürüm) kullanıyorsanız, `powerbi-models` öğesini görseller paketine eklemeniz gerekir. [Paketin nasıl ekleneceğini gösteren kısa kılavuz](https://github.com/Microsoft/powerbi-visuals-sampleslicer/blob/master/doc/AddingAdvancedFilterAPI.md)

Tüm filtreler `IFilter` arabirimini genişletir.

```typescript
export interface IFilter {
    $schema: string;
    target: IFilterTarget;
}
```

`target` - veri kaynağı üzerinde tablo sütunudur.

## <a name="basic-filter-api"></a>Temel filtreleme API’si

Temel filtre arabirimi

```typescript
export interface IBasicFilter extends IFilter {
    operator: BasicFilterOperators;
    values: (string | number | boolean)[];
}
```

`operator` - "In", "NotIn", "All" değerlerine sahip sabit listesidir

`values` - koşula ait değerlerdir

Temel filtre örneği:

```typescript
let basicFilter = {
    target: {
        column: "Col1"
    },
    operator: "In",
    values: [1,2,3]
}
```

Filtre "`col1` öğesinin 1, 2 veya 3 değerlerinden birine eşit olduğu tüm satırları ver" anlamına gelir.

SQL eşdeğeri

```sql
SELECT * FROM table WHERE col1 IN ( 1 , 2 , 3 )
```

Filtre oluşturmak için, `powerbi-models` içinde BasicFilter sınıfını kullanabilirsiniz.

Araçların eski sürümünü kullanıyorsanız, bir model örneğini `window['powerbi-models']`tarafından bir pencere nesnesinde almalısınız:

```javascript
let categories: DataViewCategoricalColumn = this.dataView.categorical.categories[0];

let target: IFilterColumnTarget = {
    table: categories.source.queryName.substr(0, categories.source.queryName.indexOf('.')),
    column: categories.source.displayName
};

let values = [ 1, 2, 3 ];

let filter: IBasicFilter = new window['powerbi-models'].BasicFilter(target, "In", values);
```

Görsel, oluşturucu içindeki görsele sağlanan ana bilgisayar arabirimi IVisualHost üzerindeki applyJsonFilter() yöntemini kullanarak filtreyi çağırır.

```typescript
visualHost.applyJsonFilter(filter, "general", "filter", FilterAction.merge);
```

## <a name="advanced-filter-api"></a>Gelişmiş filtre API’si

[Gelişmiş Filtre API’si](https://github.com/Microsoft/powerbi-models), birden çok ölçüte ("LessThan", "Contains", "Is", "IsBlank" vb.) göre karmaşık çapraz görsel veri noktası seçme/filtreleme sorguları sunar.

Filtre API’si, Görseller API 1.7.0’da tanıtılmıştır.

Gelişmiş Filtre API’si ayrıca `table` ile `target` ve `column` adını gerektirir. Ancak Gelişmiş Filtre API işleçleri şunlardır: `"And" | "Or"`. 

Ayrıca, filtre, arayüzle değerler yerine koşulları kullanır:

```typescript
interface IAdvancedFilterCondition {
    value: (string | number | boolean);
    operator: AdvancedFilterConditionOperators;
}
```

`operator` parametresi için koşul işleçleri şunlardır: `"None" | "LessThan" | "LessThanOrEqual" | "GreaterThan" | "GreaterThanOrEqual" | "Contains" | "DoesNotContain" | "StartsWith" | "DoesNotStartWith" | "Is" | "IsNot" | "IsBlank" | "IsNotBlank"`

```javascript
let categories: DataViewCategoricalColumn = this.dataView.categorical.categories[0];

let target: IFilterColumnTarget = {
    table: categories.source.queryName.substr(0, categories.source.queryName.indexOf('.')), // table
    column: categories.source.displayName // col1
};

let conditions: IAdvancedFilterCondition[] = [];

conditions.push({
    operator: "LessThan",
    value: 0
});

let filter: IAdvancedFilter = new window['powerbi-models'].AdvancedFilter(target, "And", conditions);

// invoke the filter
visualHost.applyJsonFilter(filter, "general", "filter", FilterAction.merge);
```

SQL eşdeğeri

```sql
SELECT * FROM table WHERE col1 < 0;
```

Gelişmiş Filtre API’sini kullanma hakkında tüm örnek kod [`Sampleslicer visual` deposunda](https://github.com/Microsoft/powerbi-visuals-sampleslicer) bulunabilir.

## <a name="tuple-filter-api-multi-column-filter"></a>Tanımlama grubu API’si (Çoklu sütun filtresi)

Tanımlama Grubu Filtresi API’si, Görseller API 2.3.0’da tanıtılmıştır.

Demet filtresi API’si Temel filtreye benzer, ancak birkaç sütun ve tablo için koşulların tanımlanmasına olanak tanır.

Filtrenin arabirimi vardır: 

```typescript
interface ITupleFilter extends IFilter {
    $schema: string;
    filterType: FilterType;
    operator: TupleFilterOperators;
    target: ITupleFilterTarget;
    values: TupleValueType[];
}
```

`target` tablo adları içeren bir sütun dizisidir:

```typescript
declare type ITupleFilterTarget = IFilterTarget[];
```

  Filtre, farklı tablolardaki sütunlara yönelik olabilir.

`$schema` "http://powerbi.com/product/schema#tuple"

`filterType` `FilterType.Tuple`

`operator` yalnızca `"In"` işlecinin kullanılmasına izin verir

`values`, her tanımlama grubunun, hedef sütun değerlerinin izin verilen bir birleşimini temsil ettiği bir değer tanımlama grupları dizisidir 

```typescript
declare type TupleValueType = ITupleElementValue[];

interface ITupleElementValue {
    value: PrimitiveValueType
}
```

Tamamlanan örnek:

```typescript
let target: ITupleFilterTarget = [
    {
        table: "DataTable",
        column: "Team"
    },
    {
        table: "DataTable",
        column: "Value"
    }
];

let values = [
    [
        // the 1st column combination value (aka column tuple/vector value) that the filter will pass through
        {
            value: "Team1" // the value for `Team` column of `DataTable` table
        },
        {
            value: 5 // the value for `Value` column of `DataTable` table
        }
    ],
    [
        // the 2nd column combination value (aka column tuple/vector value) that the filter will pass through
        {
            value: "Team2" // the value for `Team` column of `DataTable` table
        },
        {
            value: 6 // the value for `Value` column of `DataTable` table
        }
    ]
];

let filter: ITupleFilter = {
    $schema: "http://powerbi.com/product/schema#tuple",
    filterType: FilterType.Tuple,
    operator: "In",
    target: target,
    values: values
}

// invoke the filter
visualHost.applyJsonFilter(filter, "general", "filter", FilterAction.merge);
```

**Sütun adları ve koşulun değerlerinin sırası duyarlıdır.**

SQL eşdeğeri

```sql
SELECT * FROM DataTable WHERE ( Team = "Team1" AND Value = 5 ) OR ( Team = "Team2" AND Value = 6 );
```  

## <a name="restoring-json-filter-from-dataview"></a>JSON Filtresini DataView’dan geri yükleme

API 2.2’den başlayarak **JSON Filtreleri** **VisualUpdateOptions**’tan geri yüklenebilir

```typescript
export interface VisualUpdateOptions extends extensibility.VisualUpdateOptions {
    viewport: IViewport;
    dataViews: DataView[];
    type: VisualUpdateType;
    viewMode?: ViewMode;
    editMode?: EditMode;
    operationKind?: VisualDataChangeOperationKind;
    jsonFilters?: IFilter[];
}
```

Power BI, anahtar yer işaretleri kullanılırken görselin `update` yöntemini çağırır ve görsel karşılık gelen `filter` nesnesini alır.
[Yer işaretleri desteği hakkında daha fazla bilgi edinin](bookmarks-support.md)

### <a name="sample-json-filter"></a>Örnek JSON Filtresi

![Ekran Görüntüsü JSON Filtresi](./media/json-filter.png)

### <a name="clear-json-filter"></a>JSON Filtresini Temizle

Filtre API’si, filtrenin `null` değerini sıfırlama veya temizleme olarak kabul eder.

```typescript
// invoke the filter
visualHost.applyJsonFilter(null, "general", "filter", FilterAction.merge);
```
