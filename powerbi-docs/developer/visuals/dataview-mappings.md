---
title: Veri görünümü eşlemeleri
description: Power BI verileri görsellere geçirmeden önce nasıl dönüştürür?
author: asander
ms.author: asander
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: ff70b2f12921694617a736164484df1326471eea
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425195"
---
# <a name="data-view-mappings-in-power-bi-visuals"></a>Power BI Görselleri’nde veri görünümü eşlemeleri

Bir `dataViewMappings`, veri rollerinin birbirleriyle nasıl ilişkili olduğunu açıklar ve bunlar için koşullu gereksinimleri belirtmenize olanak tanır.
Her bir `dataMappings` için bir bölüm vardır.

Her geçerli eşleme bir `DataView`oluşturur, ancak şu anda görsel başına yalnızca bir sorgu gerçekleştirmeyi destekliyoruz; yani çoğu durumda yalnızca bir tane `DataView` elde edersiniz. Ancak, farklı koşullarla birden çok veri eşlemesi sağlamaya izin verilir

```json
"dataViewMappings": [
    {
        "conditions": [ ... ],
        "categorical": { ... },
        "single": { ... },
        "table": { ... },
        "matrix": { ... }
    }
]
```

> [!NOTE]
> Power BI’ın yalnızca `dataViewMappings` içinde geçerli eşleme doldurulduysa bir DataView öğesine eşleme oluşturduğunu unutmayın.

Diğer bir deyişle, aşağıdaki örnekte olduğu gibi `dataViewMappings` içinde `categorical` tanımlandıysa ancak `table` ve `single` gibi diğer eşlemeler tanımlanmadıysa:
```json
"dataViewMappings": [
    {
        "categorical": { ... }
    }
]
```

Power BI, tek bir `categorical` eşlemesi ile bir `DataView` üretir (`table` ve diğer eşlemeler `undefined`olacaktır):
```javascript
{
    "categorical": {
        "categories": [ ... ],
        "values": [ ... ]
    },
    "metadata": { ... }
}
```

## <a name="conditions"></a>Koşullar

Belirli bir veri eşlemesinin koşullarını açıklar. Birden çok koşul kümesi sağlayabilirsiniz ve veriler, belirtilen koşul kümelerinden biriyle eşleşiyorsa görsel, verileri geçerli olarak kabul eder.

Şu anda her alan için bir en küçük ve en büyük değer belirtebilirsiniz. Bu veri rolüne bağlanabilen alan sayısını temsil eder. 

> [!NOTE]
> Koşulda bir veri rolü atlanırsa, herhangi bir sayıda alan olabilir.

### <a name="example-1"></a>Örnek 1

Birden çok alanı her bir veri rolüne sürükleyebilirsiniz. Bu örnekte, kategoriyi bir veri alanıyla ve ölçüyü iki veri alanıyla sınırlandırıyoruz.

```json
"conditions": [
    { "category": { "max": 1 }, "y": { "max": 2 } },
]
```

### <a name="example-2"></a>Örnek 2

Bu örnekte, iki koşuldan biri gereklidir. Tam olarak bir kategori veri alanı ve tam olarak iki ölçü ya da tam olarak iki kategori ve tam olarak bir ölçü.

```json
"conditions": [
    { "category": { "min": 1, "max": 1 }, "measure": { "min": 2, "max": 2 } },
    { "category": { "min": 2, "max": 2 }, "measure": { "min": 1, "max": 1 } }
]
```

## <a name="single-data-mapping"></a>Tek Veri Eşlemesi

Tek veri eşlemesi, veri eşlemesinin en basit biçimidir. Tek bir ölçü alanını kabul eder ve size toplamı verir. Alan sayısal ise, size toplam değeri verecektir. Aksi takdirde, size benzersiz değerlerin sayısını verecektir.

Tek veri eşlemesini kullanmak için, eşlemek istediğiniz veri rolünün adını tanımlamanız gerekir. Bu eşleme yalnızca tek bir ölçü alanıyla çalışır. İkinci bir alan atanmışsa veri görünümü oluşturulmaz. Bu nedenle, verileri tek bir alanla sınırlayan bir koşul da eklemek iyi bir uygulamadır.

> [!NOTE]
> Bu veri eşlemesi diğer veri eşlemeleriyle birlikte kullanılamaz. Verileri tek bir sayısal değere düşürmek için tasarlanmıştır.

### <a name="example-3"></a>Örnek 3

```json
"dataViewMappings": {
    "conditions": [
        { "Y": { "max": 1 } }
    ],
    "single": {
        "role": "Y"
    }
}  
```

Elde edilen veri görünümü, diğer türleri (tablo, kategorik vb.) yine de içerecektir, ancak her eşleme yalnızca tek bir değer içerir. En iyi uygulama, yalnızca tek değere erişmektir.

```JSON
{
    "dataView": [
        {
            "metadata": null,
            "categorical": null,
            "matrix": null,
            "table": null,
            "tree": null,
            "single": {
                "value": 94163140.3560001
            }
        }
    ]
}
```

## <a name="categorical-data-mapping"></a>Kategorik Veri Eşlemesi

Kategorik veri eşlemesi, bir veya iki bağımsız veri grubunu almak için kullanılır.

### <a name="example-4"></a>Örnek 4

Burada, DataRoles’deki önceki örneğimizin tanımı verilmiştir.

```json
"dataRole":[
    {
        "displayName": "Category",
        "name": "category",
        "kind": "Grouping"
    },
    {
        "displayName": "Y Axis",
        "name": "measure",
        "kind": "Measure"
    }
]
```

Eşlemeyi tanımlamamız gerekirse:

```json
"dataViewMappings": {
    "categorical": {
        "categories": {
            "for": { "in": "category" }
        },
        "values": {
            "select": [
                { "bind": { "to": "measure" } }
            ]
        }
    }
}
```

"`category` DataRole’ümü, `category` içine sürüklediğim her alanın verilerini `categorical.categories` ile eşleyecek şekilde eşleştir. Ayrıca `measure` DataRole’ümü `categorical.values` öğesine eşle." anlamına gelen basit bir örnektir.

* **for...in** - Bu veri rolündeki tüm öğeler için, bunları veri sorgusuna ekler.
* **bind...to** - For...in ile aynı sonucu üretir, ancak DataRole’de öğeyi tek bir alan ile kısıtlayan bir koşul olmasını bekler.

### <a name="example-5"></a>Örnek 5

Bu örnekte, önceki örnekteki ilk iki DataRole kullanılır ve ayrıca `grouping` ve `measure2` tanımlanır.

```json
"dataRole":[
    {
        "displayName": "Category",
        "name": "category",
        "kind": "Grouping"
    },
    {
        "displayName": "Y Axis",
        "name": "measure",
        "kind": "Measure"
    },
    {
        "displayName": "Grouping with",
        "name": "grouping",
        "kind": "Grouping"
    },
    {
        "displayName": "X Axis",
        "name": "measure2",
        "kind": "Grouping"
    }
]
```

Eşlemeyi tanımlamamız gerekirse:

```json
"dataViewMappings":{
    "categorical": {
        "categories": {
            "for": { "in": "category" }
        },
        "values": {
            "group": {
                "by": "grouping",
                "select":[
                    { "bind": { "to": "measure" } },
                    { "bind": { "to": "measure2" } }
                ]
            }
        }
    }
}
```

Kategorik değerlerini eşlemeye yönelik fark aşağıdaki gibidir. "`measure` ve `measure2` Veri rollerimi `grouping` Veri rolü tarafından gruplanacak şekilde eşle." anlamına gelir.

### <a name="example-6"></a>Örnek 6

dataRoles aşağıdaki gibidir.

```json
"dataRoles": [
    {
        "displayName": "Categories",
        "name": "category",
        "kind": "Grouping"
    },
    {
        "displayName": "Measures",
        "name": "measure",
        "kind": "Measure"
    },
    {
        "displayName": "Series",
        "name": "series",
        "kind": "Measure"
    }
]
```

dataViewMapping aşağıdaki gibidir.

```json
"dataViewMappings": [
    {
        "categorical": {
            "categories": {
                "for": {
                    "in": "category"
                }
            },
            "values": {
                "group": {
                    "by": "series",
                    "select": [{
                            "for": {
                                "in": "measure"
                            }
                        }
                    ]
                }
            }
        }
    }
]
```

Kategorik `dataview` bu şekilde görselleştirilebilir.

| Kategorik |  |  | | | |
|-----|-----|------|------|------|------|
| | Yıl | 2013 | 2014 | 2015 | 2016 |
| Ülke | | |
| Amerika Birleşik Devletleri | | x | x | 125 | 100 |
| Kanada | | x | 50 | 200 | x |
| Meksika | | 300 | x | x | x |
| Birleşik Krallık | | x | x | 75 | x |

Power BI size kategorik DataView olarak üretecektir. Kategori kümesidir.

```JSON
{
    "categorical": {
        "categories": [
            {
                "source": {...},
                "values": [
                    "Canada",
                    "Mexico",
                    "UK",
                    "USA"
                ],
                "identity": [...],
                "identityFields": [...],
            }
        ]
    }
}
```

Her kategori bir değerler kümesiyle de eşlenir. Bu değerlerin her biri, yıl olan bir seriye göre gruplandırılır.

Örneğin, 2013’te Kanada satışları null, 2014’de Kanada satışları 50’dir.

```JSON
{
    "values": [
        {
            "source": {...},
            "values": [
                null,
                300,
                null,
                null
            ],
            "identity": [...],
        },
        {
            "source": {...},
            "values": [
                50,
                null,
                150,
                null
            ],
            "identity": [...],
        },
        {
            "source": {...},
            "values": [
                200,
                null,
                null,
                125
            ],
            "identity": [...],
        },
        {
            "source": {...},
            "values": [
                null,
                null,
                null,
                100
            ],
            "identity": [...],
        }
    ]
}
```

## <a name="table-data-mapping"></a>Tablo Veri Eşlemesi

Tablo veri görünümü basit bir veri eşlemedir. Temelde, bu, sayısal veri noktalarının toplanabileceği veri noktalarının bir listesidir.

### <a name="example-7"></a>Örnek 7

Verilen yetenekler ile:

```json
"dataRoles": [
    {
        "displayName": "Values",
        "name": "values",
        "kind": "Measure"
    }
]
```

```json
"dataViewMappings": [
    {
        "table": {
            "rows": {
                "for": {
                    "in": "values"
                }
            }
        }
    }
]
```

`dataview` tablosu bu şekilde görselleştirilebilir.  

| Ülke| Yıl | Satışlar |
|-----|-----|------|
| Amerika Birleşik Devletleri | 2016 | 100 |
| Amerika Birleşik Devletleri | 2015 | 50 |
| Kanada | 2015 | 200 |
| Kanada | 2015 | 50 |
| Meksika | 2013 | 300 |
| Birleşik Krallık | 2014 | 150 |
| Amerika Birleşik Devletleri | 2015 | 75 |

Power BI size tablo dataview olarak üretecektir. Bir sıralama olduğunu varsaymayın.

```JSON
{
    "table" : {
        "columns": [...],
        "rows": [
            [
                "Canada",
                2014,
                50
            ],
            [
                "Canada",
                2015,
                200
            ],
            [
                "Mexico",
                2013,
                300
            ],
            [
                "UK",
                2014,
                150
            ],
            [
                "USA",
                2015,
                100
            ],
            [
                "USA",
                2015,
                75
            ],
            [
                "USA",
                2016,
                100
            ]
        ]
    }
}
```

Veriler, istenen alanı seçip Özet’e tıklanarak toplanabilir.  

![Verileri toplama](./media/data-aggregation.png)

## <a name="matrix-data-mapping"></a>Matris Veri Eşlemesi

Matris Veri Eşlemesi, tablo veri eşlemesine benzer ancak satırlar hiyerarşik olarak sunulur. `dataRole` değerlerden biri sütun üst bilgisi değeri olarak kullanılabilir.

```json
{
    "dataRoles": [
        {
            "name": "Category",
            "displayName": "Category",
            "displayNameKey": "Visual_Category",
            "kind": "Grouping"
        },
        {
            "name": "Column",
            "displayName": "Column",
            "displayNameKey": "Visual_Column",
            "kind": "Grouping"
        },
        {
            "name": "Measure",
            "displayName": "Measure",
            "displayNameKey": "Visual_Values",
            "kind": "Measure"
        }
    ],
    "dataViewMappings": [
        {
            "matrix": {
                "rows": {
                    "for": {
                        "in": "Category"
                    }
                },
                "columns": {
                    "for": {
                        "in": "Column"
                    }
                },
                "values": {
                    "select": [
                        {
                            "for": {
                                "in": "Measure"
                            }
                        }
                    ]
                }
            }
        }
    ]
}
```

Power BI hiyerarşik veri yapısı oluşturur. Ağacın kökü, `Category` veri rolünün ilk sütunundan verilerle veri rolünün ikinci sütunundan alt öğeleri içerir.

Veri kümesi:

| Üst öğeler | Alt öğeler | Alt öğenin alt öğeleri | Sütunlar | Değerler |
|-----|-----|------|-------|-------|
| Üst öğe1 | Alt öğe1 | Alt öğenin alt öğesi1 | Süt1 | 5 |
| Üst öğe1 | Alt öğe1 | Alt öğenin alt öğesi1 | Süt2 | 6 |
| Üst öğe1 | Alt öğe1 | Alt öğenin alt öğesi2 | Süt1 | 7 |
| Üst öğe1 | Alt öğe1 | Alt öğenin alt öğesi2 | Süt2 | 8 |
| Üst öğe1 | Alt öğe2 | Alt öğenin alt öğesi3 | Süt1 | 5 |
| Üst öğe1 | Alt öğe2 | Alt öğenin alt öğesi3 | Süt2 | 3 |
| Üst öğe1 | Alt öğe2 | Alt öğenin alt öğesi4 | Süt1 | 4 |
| Üst öğe1 | Alt öğe2 | Alt öğenin alt öğesi4 | Süt2 | 9 |
| Üst öğe1 | Alt öğe2 | Alt öğenin alt öğesi5 | Süt1 | 3 |
| Üst öğe1 | Alt öğe2 | Alt öğenin alt öğesi5 | Süt2 | 5 |
| Üst öğe2 | Alt öğe3 | Alt öğenin alt öğesi6 | Süt1 | 1 |
| Üst öğe2 | Alt öğe3 | Alt öğenin alt öğesi6 | Süt2 | 2 |
| Üst öğe2 | Alt öğe3 | Alt öğenin alt öğesi7 | Süt1 | 7 |
| Üst öğe2 | Alt öğe3 | Alt öğenin alt öğesi7 | Süt2 | 1 |
| Üst öğe2 | Alt öğe3 | Alt öğenin alt öğesi8 | Süt1 | 10 |
| Üst öğe2 | Alt öğe3 | Alt öğenin alt öğesi8 | Süt2 | 13 |

Power BI Temel Matris görseli bir tablo gibi işler.

![Matris görseli](./media/matrix-visual-smaple.png)

Görsel, aşağıda açıklandığı gibi veri yapısını alır (yalnızca ilk iki satır gösterilir):

```json
{
    "metadata": {...},
    "matrix": {
        "rows": {
            "levels": [...],
            "root": {
                "childIdentityFields": [...],
                "children": [
                    {
                        "level": 0,
                        "levelValues": [...],
                        "value": "Parent1",
                        "identity": {...},
                        "childIdentityFields": [...],
                        "children": [
                            {
                                "level": 1,
                                "levelValues": [...],
                                "value": "Child1",
                                "identity": {...},
                                "childIdentityFields": [...],
                                "children": [
                                    {
                                        "level": 2,
                                        "levelValues": [...],
                                        "value": "Grand child1",
                                        "identity": {...},
                                        "values": {
                                            "0": {
                                                "value": 5 // value for Col1
                                            },
                                            "1": {
                                                "value": 6 // value for Col2
                                            }
                                        }
                                    },
                                    ...
                                ]
                            },
                            ...
                        ]
                    },
                    ...
                ]
            }
        },
        "columns": {
            "levels": [...],
            "root": {
                "childIdentityFields": [...],
                "children": [
                    {
                        "level": 0,
                        "levelValues": [...],
                        "value": "Col1",
                        "identity": {...}
                    },
                    {
                        "level": 0,
                        "levelValues": [...],
                        "value": "Col2",
                        "identity": {...}
                    },
                    ...
                ]
            }
        },
        "valueSources": [...]
    }
}
```

## <a name="data-reduction-algorithm"></a>Veri Azaltma Algoritması

DataView içinde alınan veri miktarını denetlemek istiyorsanız, `DataReductionAlgorithm` uygulanabilir.

Varsayılan olarak tüm Özel Görsellere, "count" değeri 1000 dataPoints olan DataReductionAlgorithm uygulanmıştır. Capabilities.json dosyasında aşağıdaki özellikleri ayarlamaya eşdeğerdir:

```json
"dataReductionAlgorithm": {
    "top": {
        "count": 1000
    }
}
```

'Count' değerini, 30.000’e kadar olan herhangi bir tamsayı değeri ile değiştirebilirsiniz. R tabanlı özel görseller, en fazla 150.000 satırı destekleyebilir.

## <a name="data-reduction-algorithm-types"></a>Veri Azaltma Algoritması türleri

Dört tür `DataReductionAlgorithm` ayarı vardır:

* `top` - verileri veri kümesinin en üstünden alınan değerlerle sınırlamak istiyorsanız. İlk "sayı" değerleri veri kümesinden alınacaktır.
* `bottom` - verileri veri kümesinin en altından alınan değerlerle sınırlamak istiyorsanız. Son "sayı" değerleri veri kümesinden alınacaktır.
* `sample` - veri kümesini, "count" öğe sayısıyla sınırlı bir basit örnekleme algoritması ile azaltabilirsiniz. Bu, ilk ve son öğelerin dahil olduğu ve aralarında eşit aralıklar olan bir "count" öğe sayısı olduğu anlamına gelir.
Örneğin veri kümeniz [0, 1, 2, ... 100] ve bir `count: 9` ise, şu değerleri alırsınız: [0, 10, 20 ... 100]
* `window` - "count" öğelerini içeren bir zamanda veri noktalarının bir 'window' öğesini yükler. Şu `top` anda `window` ve eşdeğerdir. Bir pencereleme ayarını tam olarak desteklemek için çalışmaya devam ediyoruz.

## <a name="data-reduction-algorithm-usage"></a>Veri Azaltma Algoritması kullanımı

`DataReductionAlgorithm` kategorik, tablo veya matris `dataview` eşlemesinde kullanılabilir.

Kategorik veri eşlemesi için `categories` ve/veya `values` grup bölümüne ayarlanabilir.

### <a name="example-8"></a>Örnek 8

```json
"dataViewMappings": {
    "categorical": {
        "categories": {
            "for": { "in": "category" },
            "dataReductionAlgorithm": {
                "window": {
                    "count": 300
                }
            }  
        },
        "values": {
            "group": {
                "by": "series",
                "select": [{
                        "for": {
                            "in": "measure"
                        }
                    }
                ],
                "dataReductionAlgorithm": {
                    "top": {
                        "count": 100
                    }
                }  
            }
        }
    }
}
```

Veri azaltma algoritması, tablo `dataview` eşlemesinin `rows` bölümüne uygulanabilir.

### <a name="example-9"></a>Örnek 9

```json
"dataViewMappings": [
    {
        "table": {
            "rows": {
                "for": {
                    "in": "values"
                },
                "dataReductionAlgorithm": {
                    "top": {
                        "count": 2000
                    }
                } 
            }
        }
    }
]
```

Veri azaltma algoritması, `matrix` `dataview` eşlemesinin `rows` ve/veya `columns` bölümüne uygulanabilir.
