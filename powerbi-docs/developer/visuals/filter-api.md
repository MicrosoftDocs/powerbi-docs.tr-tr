---
title: Daha iyi tümleşik BI içgörüleri için, Power BI tümleşik analizleri Power BI görsellerindeki Görsel Filtreler API'si
description: Bu makalede Power BI görsellerinin diğer görselleri nasıl filtreleyebildiği açıklanır. Power BI tümleşik analiz kullanarak daha iyi tümleşik BI içgörüleri elde edin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: how-to
ms.date: 06/18/2019
ms.openlocfilehash: c03c64c2835ff8bf0b0f1ad3bd555da94aaf3126
ms.sourcegitcommit: eeaf607e7c1d89ef7312421731e1729ddce5a5cc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2021
ms.locfileid: "97888754"
---
# <a name="the-visual-filters-api-in-power-bi-visuals"></a>Power BI görsellerinde Görsel Filtreler API’si

Görsel Filtreler API’si Power BI görsellerindeki verileri filtrelemenize olanak tanır. Diğer seçimlerden en önemli farkı, diğer görsel tarafından desteklenmesine rağmen diğer görsellerin herhangi bir şekilde filtrelenmesidir.

Görselde filtrelemeyi etkinleştirmek için, görsel *capabilities.json* kodunun `general` bölümünde `filter` nesnesini içermelidir.

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

Görsel Filtreler API’si arabirimleri [powerbi-models](https://www.npmjs.com/package/powerbi-models) paketinde sağlanır. Paket, filtre örnekleri oluşturmak için sınıflar da içerir.

```cmd
npm install powerbi-models --save
```

Araçların daha eski (3.x.x’ten önceki) bir sürümünü kullanıyorsanız görsel paketine `powerbi-models` öğesini eklemelisiniz. Daha fazla bilgi için kısa [Özel görsele Gelişmiş Filtre API’si ekleme](https://github.com/Microsoft/powerbi-visuals-sampleslicer/blob/master/doc/AddingAdvancedFilterAPI.md) kılavuzunu okuyun.

Aşağıdaki kodda gösterildiği gibi tüm filtreler `IFilter` arabirimini genişletir:

```typescript
export interface IFilter {
    $schema: string;
    target: IFilterTarget;
}
```
Burada:
* `target` veri kaynağındaki tablo sütunudur.

## <a name="the-basic-filter-api"></a>Temel Filtre API’si

Temel filtre arabirimi aşağıdaki kodda gösterilmiştir:

```typescript
export interface IBasicFilter extends IFilter {
    operator: BasicFilterOperators;
    values: (string | number | boolean)[];
}
```

Burada:
* `operator`; *In*, *NotIn* ve *All* değerlerini içeren bir sabit listedir.
* `values` koşul değerleridir.

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

Filtre "`col1` öğesinin 1, 2 veya 3’e eşit olduğu tüm satırları ver" anlamına gelir.

SQL eşdeğeri şöyledir:

```sql
SELECT * FROM table WHERE col1 IN ( 1 , 2 , 3 )
```

Filtre oluşturmak için, `powerbi-models` içinde BasicFilter sınıfını kullanabilirsiniz.

Aracın daha eski bir sürümünü kullanıyorsanız, aşağıdaki kodda gösterildiği gibi `window['powerbi-models']` kullanarak pencere nesnesinde modellerin bir örneğini almanız gerekir:

```javascript
let categories: DataViewCategoricalColumn = this.dataView.categorical.categories[0];

let target: IFilterColumnTarget = {
    table: categories.source.queryName.substr(0, categories.source.queryName.indexOf('.')),
    column: categories.source.displayName
};

let values = [ 1, 2, 3 ];

let filter: IBasicFilter = new window['powerbi-models'].BasicFilter(target, "In", values);
```

Görsel, oluşturucu içindeki görsele sağlanan konak arabirimi IVisualHost üzerindeki applyJsonFilter() yöntemini kullanarak filtreyi çağırır.

```typescript
visualHost.applyJsonFilter(filter, "general", "filter", FilterAction.merge);
```

## <a name="the-advanced-filter-api"></a>Gelişmiş Filtre API’si

[Gelişmiş Filtre API’si](https://github.com/Microsoft/powerbi-models), *LessThan*, *Contains*, *Is* ve *IsBlank* gibi birden çok ölçüte göre karmaşık çapraz görsel veri noktası seçme ve filtreleme sorgularını etkinleştirir.

Filtre API’si, Görseller API 1.7.0’da tanıtılmıştır.

Gelişmiş Filtre API’si ayrıca `table` ve `column` adıyla `target` gerektirir. Ama Gelişmiş Filtre API’sinin işleçleri *And* ve *Or*’dur. 

Bunun yanı sıra filtrede arabirimle birlikte değerler yerine koşullar kullanılır:

```typescript
interface IAdvancedFilterCondition {
    value: (string | number | boolean);
    operator: AdvancedFilterConditionOperators;
}
```

`operator` parametresinin koşul işleçleri *None*, *LessThan*, *LessThanOrEqual*, *GreaterThan*, *GreaterThanOrEqual*, *Contains*, *DoesNotContain*, *StartsWith*, *DoesNotStartWith*, *Is*, *IsNot*, *IsBlank* ve "IsNotBlank" işleçleridir

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

SQL eşdeğeri şöyledir:

```sql
SELECT * FROM table WHERE col1 < 0;
```

Gelişmiş Filtre API’sini kullanmaya yönelik eksiksiz bir örnek kod için [Sampleslicer görsel deposuna](https://github.com/Microsoft/powerbi-visuals-sampleslicer) gidin.

## <a name="the-tuple-filter-api-multi-column-filter"></a>Tanımlama Grubu Filtresi API’si (çok sütunlu filtre)

Tanımlama Grubu Filtresi API’si, Görseller API’si 2.3.0’da kullanıma sunulmuştur. Temel Filtre API’sine benzer, ancak birkaç sütun ve tablo için koşulları tanımlamanıza olanak tanır.

Filtre arabirimi aşağıdaki kodda gösterilmiştir: 

```typescript
interface ITupleFilter extends IFilter {
    $schema: string;
    filterType: FilterType;
    operator: TupleFilterOperators;
    target: ITupleFilterTarget;
    values: TupleValueType[];
}
```

Burada:
* `target` tablo adları içeren bir sütun dizisidir:

    ```typescript
    declare type ITupleFilterTarget = IFilterTarget[];
    ```

  Filtre, çeşitli tablolardaki sütunlara yönelik olabilir.

* `$schema`, https://powerbi.com/product/schema#tuple değeridir.

* `filterType`, *FilterType.Tuple* değeridir.

* `operator` yalnızca *In* işlecine kullanıma izin verir.

* `values` bir dizi değer tanımlama grubudur ve her tanımlama grubu hedef sütun değerlerinin izin verilen bir birleşimini temsil eder. 

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
        // the first column combination value (or the column tuple/vector value) that the filter will pass through
        {
            value: "Team1" // the value for the `Team` column of the `DataTable` table
        },
        {
            value: 5 // the value for the `Value` column of the `DataTable` table
        }
    ],
    [
        // the second column combination value (or the column tuple/vector value) that the filter will pass through
        {
            value: "Team2" // the value for `Team` column of `DataTable` table
        },
        {
            value: 6 // the value for `Value` column of `DataTable` table
        }
    ]
];

let filter: ITupleFilter = {
    $schema: "https://powerbi.com/product/schema#tuple",
    filterType: FilterType.Tuple,
    operator: "In",
    target: target,
    values: values
}

// invoke the filter
visualHost.applyJsonFilter(filter, "general", "filter", FilterAction.merge);
```

> [!IMPORTANT]
> Sütun adlarının ve koşul değerlerinin sırası önemlidir.

SQL eşdeğeri şöyledir:

```sql
SELECT * FROM DataTable WHERE ( Team = "Team1" AND Value = 5 ) OR ( Team = "Team2" AND Value = 6 );
```  

## <a name="restore-the-json-filter-from-the-data-view"></a>JSON filtresini veri görünümünden geri yükleme

API’nin 2.2.0 sürümünden başlayarak, aşağıdaki kodda gösterildiği gibi JSON filtresini *VisualUpdateOptions* öğesinden geri yükleyebilirsiniz:

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

Yer işaretlerini değiştirdiğinizde Power BI görselin `update` yöntemini çağırır ve görsel buna karşılık gelen `filter` nesnesini alır. Daha fazla bilgi için bkz. [Power BI görselleri için yer işareti desteği ekleme](bookmarks-support.md).

### <a name="sample-json-filter"></a>Örnek JSON filtresi

Aşağıdaki resimde örnek bir JSON filtresi kodu gösterilir:

![JSON filtresi kodu](media/filter-api/json-filter.png)

### <a name="clear-the-json-filter"></a>JSON filtresini temizleme

Filtre API’si, filtrenin `null` değerini *sıfırlama* veya *temizleme* olarak kabul eder.

```typescript
// invoke the filter
visualHost.applyJsonFilter(null, "general", "filter", FilterAction.merge);
```
