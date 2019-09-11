---
title: Power BI görsellerinin nesneleri ve özellikleri
description: Bu makalede Power BI görsellerinin özelleştirilebilir özellikleri açıklanır.
author: MrMeison
ms.author: rasala
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: e15d80af35ff7c56879dab4380d4ae0c9fdd0e8a
ms.sourcegitcommit: b602cdffa80653bc24123726d1d7f1afbd93d77c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70236623"
---
# <a name="objects-and-properties-of-power-bi-visuals"></a>Power BI görsellerinin nesneleri ve özellikleri

Nesneler görselle ilişkilendirilmiş özelleştirilebilir özellikleri açıklar. Nesnenin birden çok özelliği olabilir ve her özelliğin ne olacağını açıklayan ilişkili bir türü vardır. Bu makalede nesne ve özellik türleri hakkında bilgi sağlanır.

`myCustomObject`, `dataView` ile `enumerateObjectInstances` içinde nesneye başvurmak için kullanılan dahili addır.

```json
"objects": {
    "myCustomObject": {
        "displayName": "My Object Name",
        "properties": { ... }
    }
}
```

## <a name="display-name"></a>Görünen ad

`displayName`, özellik bölmesinde gösterilecek addır.

## <a name="properties"></a>Özellikler

`properties` geliştirici tarafından tanımlanan bir özellik eşlemesidir.

```json
"properties": {
    "myFirstProperty": {
        "displayName": "firstPropertyName",
        "type": ValueTypeDescriptor | StructuralTypeDescriptor
    }
}
```

> [!NOTE]
> `show`, nesneye geçiş yapmak için bir anahtar sağlayan özel bir özelliktir.

Örnek:

```json
"properties": {
    "show": {
        "displayName": "My Property Switch",
        "type": {"bool": true}
    }
}
```

### <a name="property-types"></a>Özellik türleri

İki özellik türü vardır: `ValueTypeDescriptor` ve `StructuralTypeDescriptor`.

#### <a name="value-type-descriptor"></a>Değer türü tanımlayıcısı

`ValueTypeDescriptor` türleri çoğunlukla basit türlerdir ve normalde statik nesne olarak kullanılır.

Yaygın `ValueTypeDescriptor` özelliklerinden bazıları şunlardır:

```typescript
export interface ValueTypeDescriptor {
    text?: boolean;
    numeric?: boolean;
    integer?: boolean;
    bool?: boolean;
}
```

#### <a name="structural-type-descriptor"></a>Yapısal tür tanımlayıcısı

`StructuralTypeDescriptor` türleri çoğunlukla veri bağlantılı nesneler için kullanılır.
En yaygın `StructuralTypeDescriptor` türü *fill*’dir.

```typescript
export interface StructuralTypeDescriptor {
    fill?: FillTypeDescriptor;
}
```

## <a name="gradient-property"></a>Gradyan özelliği

Gradyan özelliği, standart özellik olarak ayarlanamayan bir özelliktir. Bunun yerine, renk seçici özelliğinin (*fill* türü) değişimi için bir kural ayarlamanız gerekir.

Aşağıdaki kodda bir örnek gösterilmiştir:

```json
"properties": {
    "showAllDataPoints": {
        "displayName": "Show all",
        "displayNameKey": "Visual_DataPoint_Show_All",
        "type": {
            "bool": true
        }
    },
    "fill": {
        "displayName": "Fill",
        "displayNameKey": "Visual_Fill",
        "type": {
            "fill": {
                "solid": {
                    "color": true
                }
            }
        }
    },
    "fillRule": {
        "displayName": "Color saturation",
        "displayNameKey": "Visual_ColorSaturation",
        "type": {
            "fillRule": {}
        },
        "rule": {
            "inputRole": "Gradient",
            "output": {
                "property": "fill",
                    "selector": [
                        "Category"
                    ]
            }
        }
    }
}
```

*fill* ve *fillRule* özelliklerine dikkat edin. Birincisi renk seçicisi, ikincisi ise kural koşulları karşılandığında *fill özelliği* `visually` yerine geçecek gradyan için değiştirme kuralıdır.

*fill* özelliği ile değiştirme kuralı arasındaki bu bağlantı, *fillRule* özelliğinin `"rule"`>`"output"` bölümünde ayarlanır.

`"Rule"`>`"InputRole"` özelliği kuralı (koşulu) tetikleyen veri rolünü ayarlar. Bu örnekte, `"Gradient"` veri rolü verileri içeriyorsa, `"fill"` özelliği için kural uygulanır.

Aşağıdaki kodda fill kuralını (`the last item`) tetikleyen veri rolü örneği gösterilir:

```json
{
    "dataRoles": [
            {
                "name": "Category",
                "kind": "Grouping",
                "displayName": "Details",
                "displayNameKey": "Role_DisplayName_Details"
            },
            {
                "name": "Series",
                "kind": "Grouping",
                "displayName": "Legend",
                "displayNameKey": "Role_DisplayName_Legend"
            },
            {
                "name": "Gradient",
                "kind": "Measure",
                "displayName": "Color saturation",
                "displayNameKey": "Role_DisplayName_Gradient"
            }
    ]
}
```

## <a name="the-enumerateobjectinstances-method"></a>enumerateObjectInstances yöntemi

Nesneleri etkin bir şekilde kullanmak için özel görselinizde `enumerateObjectInstances` adlı bir işleve ihtiyacınız vardır. Bu işlev, özellik bölmesini nesnelerle doldurur ve ayrıca nesnelerinizin dataView içinde nereye bağlanacağını da belirler.  

Tipik bir kurulum şöyle görünür:

```typescript
public enumerateObjectInstances(options: EnumerateVisualObjectInstancesOptions): VisualObjectInstanceEnumeration {
    let objectName: string = options.objectName;
    let objectEnumeration: VisualObjectInstance[] = [];

    switch( objectName ) {
        case 'myCustomObject':
            objectEnumeration.push({
                objectName: objectName,
                properties: { ... },
                selector: { ... }
            });
            break;
    };

    return objectEnumeration;
}
```

### <a name="properties"></a>Özellikler

`enumerateObjectInstances` içindeki özellikler, yetenekleriniz çerçevesinde tanımladığınız özellikleri yansıtır. Örnek görmek için bu makalenin sonuna gidin.

### <a name="objects-selector"></a>Nesne seçicisi

`enumerateObjectInstances` içindeki seçici, her nesnenin dataView içinde nereye bağlandığını belirler. Dört farklı seçenek vardır.

#### <a name="static"></a>statik

Bu nesne burada gösterildiği gibi `dataviews[index].metadata.objects` meta verilerine bağlıdır.

```typescript
selector: null
```

#### <a name="columns"></a>sütunlar

Bu nesne, `QueryName` değeri eşleşen sütunlara bağlıdır.

```typescript
selector: {
    metadata: 'QueryName'
}
```

#### <a name="selector"></a>seçici

Bu nesne, kendisi için bir `selectionID` oluşturmuş olduğumuz öğeye bağlıdır. Bu örnekte bazı veri noktaları için `selectionID` değerleri oluşturduğumuzu ve bunlar arasında döngü oluşturduğumuzu varsayalım.

```typescript
for (let dataPoint in dataPoints) {
    ...
    selector: dataPoint.selectionID.getSelector()
}
```

#### <a name="scope-identity"></a>Kapsam kimliği

Bu nesne grupların kesişimindeki belirli değerlere bağlıdır. Örneğin `["Jan", "Feb", "March", ...]` kategorileriniz ve `["Small", "Medium", "Large"]` serileriniz varsa, `Feb` ve `Large` ile eşleşen değerlerin kesişiminde bir nesneniz olmasını isteyebilirsiniz. Bunu gerçekleştirmek için her iki sütundan `DataViewScopeIdentity` öğesini alabilir, bunları `identities` değişkenine gönderebilir ve seçicide bu söz dizimini kullanabiliriz.

```typescript
selector: {
    data: <DataViewScopeIdentity[]>identities
}
```

##### <a name="example"></a>Örnek

Aşağıdaki örnekte bir objectEnumeration öğesinin tek bir *fill* özelliği olan bir customColor nesnesi için nasıl göründüğü gösterilir. Bu nesnenin aşağıdaki gösterildiği gibi statik olarak `dataViews[index].metadata.objects` öğesine bağlı olmasını istiyoruz:

```typescript
objectEnumeration.push({
    objectName: "customColor",
    displayName: "Custom Color",
    properties: {
        fill: {
            solid: {
                color: dataPoint.color
            }
        }
    },
    selector: null
});
```
