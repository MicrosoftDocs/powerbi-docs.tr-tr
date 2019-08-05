---
title: Özellikler
description: Power BI Görselleri yetenekleri ve özellikleri
author: asander
ms.author: asander
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: f6bb4293a44f98f2f8098fb197c7b406b618d211
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425471"
---
# <a name="power-bi-visual-capabilities"></a>Power BI Görsel yetenekleri

Yetenekler, ana bilgisayara görseliniz hakkında bilgiler sağlar. Yetenekler modelindeki tüm özellikler `optional`

Görselin yeteneklerinin kök nesneleri `dataRoles`, `dataViewMappings` ve benzer öğelerdir.

```json
{
    "dataRoles": [ ... ],
    "dataViewMappings": [ ... ],
    "objects":  { ... },
    "supportsHighlight": true|false,
    "advancedEditModeSupport": 0|1|2,
    "sorting": { ... }
}

```

## <a name="define-the-data-fields-your-visual-expects---dataroles"></a>Görselinizin beklediği veri alanlarını tanımlayın - `dataRoles`

Verilere bağlanabilen alanları tanımlamak için, gereken tüm özellikleri tanımlayan bir `DataViewRole` nesne dizisi alan `dataRoles` kullanıyoruz.

### <a name="properties"></a>Özellikler

* **ad** - bu veri alanının iç adı (benzersiz olmalıdır)
* **tür** - alanın türü:
    * `Grouping` - Ölçü alanlarının gruplandırılması için kullanılan ayrık değerler
    * `Measure` - Sayısal veri değerleri
    * `GroupingOrMeasure` - Bir gruplandırma veya ölçü olarak kullanılabilir
* **displayName** - özellikler bölmesinde kullanıcıya görüntülenecek ad
* **açıklama** - alanın kısa bir açıklaması (isteğe bağlı)
* **requiredTypes** - bu veri rolü için gerekli veri türü. Eşleşmeyen tüm değerler null olarak ayarlanacak (isteğe bağlı)
* **preferredTypes** - bu veri rolü için tercih edilen veri türü (isteğe bağlı)

### <a name="valid-data-types-in-requiredtypes-and-preferredtypes"></a>"requiredTypes" ve "preferredTypes" içindeki geçerli veri türleri

* **bool** - boolean değeri
* **tamsayı** - tamsayı değeri
* **sayısal** - sayısal bir değer
* **metin** - bir metin değeri
* **coğrafya** - coğrafi veriler

### <a name="example"></a>Örnek

```json
"dataRoles": [
    {
        "displayName": "My Category Data",
        "name": "myCategory",
        "kind": "Grouping",
        "requiredTypes": [
            {
                "text": true
            },
            {
                "numeric": true
            },
            {
                "integer": true
            }
        ],
        "preferredTypes": [
            {
                "text": true
            }
        ]
    },
    {
        "displayName": "My Measure Data",
        "name": "myMeasure",
        "kind": "Measure",
        "requiredTypes": [
            {
                "integer": true
            },
            {
                "numeric": true
            }
        ],
        "preferredTypes": [
            {
                "integer": true
            }
        ]
    },
    {
        "displayNameKey": "Visual_Location",
        "name": "Locations",
        "kind": "Measure",
        "displayName": "Locations",
        "requiredTypes": [
            {
                "geography": {
                    "address": true
                }
            },
            {
                "geography": {
                    "city": true
                }
            },
            {
                "geography": {
                    "continent": true
                }
            },
            {
                "geography": {
                    "country": true
                }
            },
            {
                "geography": {
                    "county": true
                }
            },
            {
                "geography": {
                    "place": true
                }
            },
            {
                "geography": {
                    "postalCode": true
                }
            },
            {
                "geography": {
                    "region": true
                }
            },
            {
                "geography": {
                    "stateOrProvince": true
                }
            }
        ]
    }
]
```

Yukarıdaki veri rolleri aşağıdaki alanları oluşturur

![Veri rolü görüntüleme](./media/data-role-display.png)

## <a name="define-how-you-want-the-data-mapped---dataviewmappings"></a>Verilerin nasıl eşlenmesini istediğinizi tanımlayın - `dataViewMappings`

Bir DataViewMapping, veri rollerinin birbirleriyle nasıl ilişkili olduğunu açıklar ve bunlar için koşullu gereksinimleri belirtmenize olanak tanır.

Çoğu görselde tek bir eşleme sağlanır, ancak birden çok dataViewMappings sağlayabilirsiniz. Her geçerli eşleme bir DataView oluşturacaktır. 

```json
"dataViewMappings": [
    {
        "conditions": [ ... ],
        "categorical": { ... },
        "table": { ... },
        "single": { ... },
        "matrix": { ... }
    }
]
```

[DataViewMappings hakkında daha fazla bilgi edinin](dataview-mappings.md)

## <a name="define-property-pane-options---objects"></a>Özellik bölmesi seçeneklerini tanımlayın - `objects`

Nesneler görselle ilişkili özelleştirilebilir özellikleri tanımlar.
Her nesne birden fazla özelliğe sahip olabilir ve her bir özelliğin kendisiyle ilişkilendirilmiş bir türü vardır.
Türler, özelliğin ne olacağını ifade eder. Türler hakkında daha fazla bilgi için lütfen aşağıya bakın.

```json
"objects": {
    "myCustomObject": {
        "displayName": "My Object Name",
        "properties": { ... }
    }
}
```

[Nesneler hakkında daha fazla bilgi edinin](objects-properties.md)

## <a name="handle-partial-highlighting---supportshighlight"></a>Kısmi vurgulamayı işle - `supportsHighlight`

Varsayılan olarak, bu değer false olarak ayarlanır; bu, sayfada bir öğe seçildiğinde "Değerler" alanının otomatik olarak filtreleneceği ve bu sayede görselinizin yalnızca seçili değeri görüntüleyecek şekilde güncelleneceği anlamına gelir. Tüm verileri göstermek ancak yalnızca seçili öğeleri vurgulamak istiyorsanız, capabilities.json’nizde `supportsHighlight` öğesini true olarak ayarlamanız gerekir.

[Vurgulama hakkında daha fazla bilgi edinin](highlight.md)

## <a name="handle-advanced-edit-mode---advancededitmodesupport"></a>Gelişmiş Düzenleme Modunu İşle - `advancedEditModeSupport`

Görsel, Gelişmiş Düzenleme Modu desteğini bildirebilir.
Varsayılan olarak, bir görsel, capabilities.json içinde aksi belirtilmedikçe Gelişmiş Düzenleme Modu’nu desteklemez.

[advancedEditModeSupport hakkında daha fazla bilgi edinin](advanced-edit-mode.md)

## <a name="data-sorting-options-for-visual---sorting"></a>Görsel için veri sıralama seçenekleri - `sorting`

Görsel, kendi özelliklerini kullanarak sıralama davranışını tanımlayabilir.
Varsayılan olarak, bir görsel, capabilities.json içinde aksi belirtilmedikçe sıralama sırasının değiştirilmesini desteklemez.

[Sıralama hakkında daha fazla bilgi edinin](sort-options.md)
