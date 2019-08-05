---
title: Nesne ve özellikler
description: Power BI Görselinin özelleştirilebilir özellikleri
author: MrMeison
ms.author: rasala
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: c22a1cfb281c9902d490e2320b85c2f6bbb63468
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2019
ms.locfileid: "68424620"
---
# <a name="object-and-properties"></a>Nesne ve özellikler

Nesneler görselle ilişkili özelleştirilebilir özellikleri tanımlar.
Her nesne birden fazla özelliğe sahip olabilir ve her bir özelliğin kendisiyle ilişkilendirilmiş bir türü vardır.
Türler, özelliğin ne olacağını ifade eder. Türler hakkında daha fazla bilgi için lütfen aşağıya bakın.

`myCustomObject`, `dataView` ve `enumerateObjectInstances` içinde nesneye başvurmak için kullanılan dahili addır

```json
"objects": {
    "myCustomObject": {
        "displayName": "My Object Name",
        "properties": { ... }
    }
}
```

## <a name="display-name"></a>Görünen Ad

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

#### <a name="value-type-descriptor"></a>Değer Türü Tanımlayıcısı

`ValueTypeDescriptor` çoğunlukla basit türlerdir ve genellikle statik nesne olarak kullanılır.
Önemli `ValueTypeDescriptor` özelliklerinden bazıları şunlardır

```typescript
export interface ValueTypeDescriptor {
    text?: boolean;
    numeric?: boolean;
    integer?: boolean;
    bool?: boolean;
}
```

#### <a name="structural-type-descriptor"></a>Yapısal Tür Tanımlayıcısı

`StructuralTypeDescriptor` genellikle veri bağlantılı nesneler için kullanılır.
Dolgu, en yaygın `StructuralTypeDescriptor` türüdür

```typescript
export interface StructuralTypeDescriptor {
    fill?: FillTypeDescriptor;
}
```

## <a name="gradient-property"></a>Gradyan özelliği

Gradyan özelliği, standart özellik olarak ayarlanamaz bir özelliktir. Bunun yerine, renk seçici özelliğinin (dolgu türü) değişimi için bir kural ayarlamanız gerekir.
Aşağıdaki örneğe bakın:

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

`"fill"` ve `"fillRule"` özelliklerine dikkat edin. Birincisi renk seçicisi, ikincisi ise kural koşulları karşılandığında "dolgu" özelliği `visually` yerine geçecek gradyan için değiştirme kuralıdır.

Dolgu özelliği ve değiştirme kuralı arasındaki bu bağlantı, `"fillRule"` özelliğinin `"rule"`->`"output"` bölümünde ayarlanır.

`"Rule"`->`"InputRole"`, kuralı (koşulu) tetikleyen veri rolünü ayarlar. Bu örnekte, `"Gradient"` veri rolü verileri içeriyorsa, kural `"fill"` özelliği için de uygulanır.

Aşağıda, dolgu kuralını (`the last item`) tetikleyen veri rolü örneğini görebilirsiniz.

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

## <a name="enumerateobjectinstances-method"></a>`enumerateObjectInstances` yöntemi

Nesneleri etkin bir şekilde kullanmak için özel görselinizde `enumerateObjectInstances` adlı bir işleve ihtiyacınız vardır. Bu işlev, özellik bölmesini nesnelerle doldurur ve ayrıca nesnelerinizin dataView içinde nereye bağlanması gerektiğini de belirler.  

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

`enumerateObjectInstances` içindeki özellikler, yetenekleriniz içinde tanımladığınız özellikleri yansıtır. Sayfanın altındaki örneğe bakın.

### <a name="objects-selector"></a>Nesne seçicisi

`enumerateObjectInstances` içindeki seçici, her nesnenin dataView içinde nereye bağlanacağını belirler. Dört farklı seçenek vardır.

#### <a name="static"></a>statik

Bu nesne `dataviews[index].metadata.objects` meta verilerine bağlanacak

```typescript
selector: null
```

#### <a name="columns"></a>sütunlar

Bu nesne, eşleşen `QueryName` ile sütunlara bağlanacak.

```typescript
selector: {
    metadata: 'QueryName'
}
```

#### <a name="selector"></a>seçici

Bu nesne, kendisi için bir `selectionID` oluşturmuş olduğumuz öğeye bağlanacak. Bu örnekte, bazı veri noktaları için `selectionID` oluşturduğumuzu ve bunlar arasında döngü oluşturduğumuzu varsayacağız.

```typescript
for (let dataPoint in dataPoints) {
    ...
    selector: dataPoint.selectionID.getSelector()
}
```

#### <a name="scope-identity"></a>Kapsam kimliği

Bu nesne, grupların kesişimindeki belirli değerlere bağlanacak. Örneğin, `["Jan", "Feb", "March", ...]` kategorim ve `["Small", "Medium", "Large"]` serimiz varsa, `Feb` ve `Large` ile eşleşen değerlerin kesişiminde bir nesne olmasını isteyebiliriz. Bunu gerçekleştirmek için her iki sütundan `DataViewScopeIdentity` öğesini alabilir, bunları `identities` değişkenine gönderebilir ve bu söz dizimini seçiciyle birlikte kullanabiliriz.

```typescript
selector: {
    data: <DataViewScopeIdentity[]>identities
}
```

##### <a name="example"></a>Örnek

Bu örnekte, bir objectEnumeration öğesinin tek bir `fill` özelliği olan bir customColor nesnesi için nasıl göründüğünü gösteririz. Bu nesnenin statik olarak `dataViews[index].metadata.objects` öğesine bağlanmasını istiyoruz

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
