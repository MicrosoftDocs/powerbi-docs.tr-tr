---
title: Power BI görselinde Veri görünümü yardımcı programlarını kullanmaya giriş
description: Bu makalede Power BI görselleri için DataView nesnesini ayrıştırma işlemini basitleştirmek amacıyla SVG yardımcı programlarının nasıl kullanılacağı açıklanır
author: KesemSharabi
ms.author: kesharab
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 06/18/2019
ms.openlocfilehash: 80c53b183f37dc09ee83ff20bd97f944bdcbc9b4
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "79379341"
---
# <a name="dataviewutils"></a>DataViewUtils

`DataViewUtils`, Power BI görselleri için DataView nesnesini ayrıştırma işlemini basitleştirmeye yönelik bir dizi işlev ve sınıftır

## <a name="installation"></a>Yükleme

Paketi yüklemek için geçerli özel görselinizin dizininde aşağıdaki komutu çalıştırmalısınız:

npm install powerbi-visuals-utils-dataviewutils --save Bu komut paketi yükler ve package.json dosyanıza bağımlılık olarak bir paket ekler

## <a name="datarolehelper"></a>DataRoleHelper

`DataRoleHelper` dataView nesnesinin rollerini denetlemek için işlevler sağlar.

Modül aşağıdaki işlevleri sağlar:

### <a name="getmeasureindexofrole"></a>getMeasureIndexOfRole

Bu işlev rol adına göre ölçüyü bulur ve dizinini döndürür.

```typescript
function getMeasureIndexOfRole(grouped: DataViewValueColumnGroup[], roleName: string): number;
```

Örnek:

```typescript
import powerbi from "powerbi-visuals-api";
import DataViewValueColumnGroup = powerbi.DataViewValueColumnGroup;
import { dataRoleHelper } from "powerbi-visuals-utils-dataviewutils";
// ...

// This object is actually a part of the dataView object.
let columnGroup: DataViewValueColumnGroup[] = [{
    values: [
        {
            source: {
                displayName: "Microsoft",
                roles: {
                    "company": true
                }
            },
            values: []
        },
        {
            source: {
                displayName: "Power BI",
                roles: {
                    "product": true
                }
            },
            values: []
        }
    ]
}];

dataRoleHelper.getMeasureIndexOfRole(columnGroup, "product");

// returns: 1
```

### <a name="getcategoryindexofrole"></a>getCategoryIndexOfRole

Bu işlev rol adına göre kategoriyi bulur ve dizinini döndürür.

```typescript
function getCategoryIndexOfRole(categories: DataViewCategoryColumn[], roleName: string): number;
```

Örnek:

```typescript
import powerbi from "powerbi-visuals-api";
import DataViewCategoryColumn = powerbi.DataViewCategoryColumn;
import { dataRoleHelper } from "powerbi-visuals-utils-dataviewutils";
// ...

// This object is actually a part of the dataView object.
let categoryGroup: DataViewCategoryColumn[] = [
    {
        source: {
            displayName: "Microsoft",
            roles: {
                "company": true
            }
        },
        values: []
    },
    {
        source: {
            displayName: "Power BI",
            roles: {
                "product": true
            }
        },
        values: []
    }
];

dataRoleHelper.getCategoryIndexOfRole(categoryGroup, "product");

// returns: 1
```

### <a name="hasrole"></a>hasRole

Bu işlev sağlanan rolün meta verilerde tanımlanıp tanımlanmadığını denetler.

```typescript
function hasRole(column: DataViewMetadataColumn, name: string): boolean;
```

Örnek:

```typescript
import powerbi from "powerbi-visuals-api";
import DataViewMetadataColumn = powerbi.DataViewMetadataColumn;
import { dataRoleHelper } from "powerbi-visuals-utils-dataviewutils";

// This object is actually a part of the dataView object.
let metadata: DataViewMetadataColumn = {
    displayName: "Microsoft",
    roles: {
        "company": true
    }
};

DataRoleHelper.hasRole(metadata, "company");

// returns: true
```

### <a name="hasroleindataview"></a>hasRoleInDataView

Bu işlev sağlanan rolün dataView içinde tanımlanıp tanımlanmadığını denetler.

```typescript
function hasRoleInDataView(dataView: DataView, name: string): boolean;
```

Örnek:

```typescript
import powerbi from "powerbi-visuals-api";
import DataView = powerbi.DataView;
import { dataRoleHelper } from "powerbi-visuals-utils-dataviewutils";

// This object is actually a part of the dataView object.
let dataView: DataView = {
    metadata: {
        columns: [
            {
                displayName: "Microsoft",
                roles: {
                    "company": true
                }
            },
            {
                displayName: "Power BI",
                roles: {
                    "product": true
                }
            }
        ]
    }
};

DataRoleHelper.hasRoleInDataView(dataView, "product");

// returns: true
```

### <a name="hasroleinvaluecolumn"></a>hasRoleInValueColumn

Bu işlev sağlanan rolün değer sütununda tanımlanıp tanımlanmadığını denetler.

```typescript
function hasRoleInValueColumn(valueColumn: DataViewValueColumn, name: string): boolean;
```

Örnek:

```typescript
import powerbi from "powerbi-visuals-api";
import DataViewValueColumn = powerbi.DataViewValueColumn;
import { dataRoleHelper } from "powerbi-visuals-utils-dataviewutils";

// This object is actually a part of the dataView object.
let valueColumn: DataViewValueColumn = {
    source: {
        displayName: "Microsoft",
        roles: {
            "company": true
        }
    },
    values: []
};

dataRoleHelper.hasRoleInValueColumn(valueColumn, "company");

// returns: true
```

## <a name="dataviewobjects"></a>DataViewObjects

`DataViewObjects` nesnelerin değerlerini ayıklamak için işlevler sağlar.

Modül aşağıdaki işlevleri sağlar:

### <a name="getvalue"></a>getValue

Bu işlev verili nesnenin değerini döndürür.

```typescript
function getValue<T>(objects: DataViewObjects, propertyId: DataViewObjectPropertyIdentifier, defaultValue?: T): T;
```

Örnek:

```typescript
import powerbi from "powerbi-visuals-api";
import DataViewObjectPropertyIdentifier = powerbi.DataViewObjectPropertyIdentifier;
import { dataViewObjects } from "powerbi-visuals-utils-dataviewutils";

let property: DataViewObjectPropertyIdentifier = {
    objectName: "microsoft",
    propertyName: "bi"
};

// This object is actually a part of the dataView object.
let objects: powerbi.DataViewObjects = {
    "microsoft": {
        "windows": 5,
        "bi": "Power"
    }
};

dataViewObjects.getValue(objects, property);

// returns: Power
```

### <a name="getobject"></a>getObject

Bu işlev verili nesne için bir nesne döndürür.

```typescript
function getObject(objects: DataViewObjects, objectName: string, defaultValue?: IDataViewObject): IDataViewObject;
```

Örnek:

```typescript
import { dataViewObjects } from "powerbi-visuals-utils-dataviewutils";

// This object is actually a part of the dataView object.
let objects: powerbi.DataViewObjects = {
    "microsoft": {
        "windows": 5,
        "bi": "Power"
    }
};

dataViewObjects.getObject(objects, "microsoft");

/* returns: {
    "bi": "Power",
    "windows": 5

}*/
```

### <a name="getfillcolor"></a>getFillColor

Bu işlev nesnelerin düz rengini döndürür.

```typescript
function getFillColor(objects: DataViewObjects, propertyId: DataViewObjectPropertyIdentifier, defaultColor?: string): string;
```

Örnek:

```typescript
import powerbi from "powerbi-visuals-api";
import DataViewObjectPropertyIdentifier = powerbi.DataViewObjectPropertyIdentifier;
import { dataViewObjects } from "powerbi-visuals-utils-dataviewutils";

let property: DataViewObjectPropertyIdentifier = {
    objectName: "power",
    propertyName: "fillColor"
};

// This object is actually part of the dataView object.
let objects: powerbi.DataViewObjects = {
    "power": {
        "fillColor": {
            "solid": {
                "color": "yellow"
            }
        },
        "bi": "Power"
    }
};

dataViewObjects.getFillColor(objects, property);

// returns: yellow
```

### <a name="getcommonvalue"></a>getCommonValue

Bu işlev verili nesnenin rengini veya değerini almaya yönelik evrensel bir işlevdir.

```typescript
function getCommonValue(objects: DataViewObjects, propertyId: DataViewObjectPropertyIdentifier, defaultValue?: any): any;
```

Örnek:

```typescript
import powerbi from "powerbi-visuals-api";
import DataViewObjectPropertyIdentifier = powerbi.DataViewObjectPropertyIdentifier;
import { dataViewObjects } from "powerbi-visuals-utils-dataviewutils";

let colorProperty: DataViewObjectPropertyIdentifier = {
    objectName: "power",
    propertyName: "fillColor"
};

let biProperty: DataViewObjectPropertyIdentifier = {
    objectName: "power",
    propertyName: "bi"
};

// This object is actually part of the dataView object.
let objects: powerbi.DataViewObjects = {
    "power": {
        "fillColor": {
            "solid": {
                "color": "yellow"
            }
        },
        "bi": "Power"
    }
};

dataViewObjects.getCommonValue(objects, colorProperty); // returns: yellow
dataViewObjects.getCommonValue(objects, biProperty); // returns: Power
```

## <a name="dataviewobject"></a>DataViewObject

`DataViewObject` nesnenin değerini ayıklamak için işlevler sağlar.

Modül aşağıdaki işlevleri sağlar:

### <a name="getvalue"></a>getValue

Bu işlev özellik adına göre nesnenin değerinin döndürür.

```typescript
function getValue<T>(object: IDataViewObject, propertyName: string, defaultValue?: T): T;
```

Örnek:

```typescript
import { dataViewObject } from "powerbi-visuals-utils-dataviewutils";

// This object is actually a part of the dataView object.
let object: powerbi.DataViewObject = {
    "windows": 5,
    "microsoft": "Power BI"
};

dataViewObject.getValue(object, "microsoft");

// returns: Power BI
```

### <a name="getfillcolorbypropertyname"></a>getFillColorByPropertyName

Bu işlev özellik adına göre nesnenin düz rengini döndürür.

```typescript
function getFillColorByPropertyName(object: IDataViewObject, propertyName: string, defaultColor?: string): string;
```

Örnek:

```typescript
import { dataViewObject } from "powerbi-visuals-utils-dataviewutils";

// This object is actually a part of the dataView object.
let object: powerbi.DataViewObject = {
    "windows": 5,
    "fillColor": {
        "solid": {
            "color": "green"
        }
    }
};

dataViewObject.getFillColorByPropertyName(object, "fillColor");

// returns: green
```

### <a name="converterhelper"></a>converterHelper

`converterHelper` dataView özelliklerini denetlemek için işlevler sağlar.

Modül aşağıdaki işlevleri sağlar:

### <a name="categoryisalsoseriesrole"></a>categoryIsAlsoSeriesRole

Bu işlev kategorinin de seri olup olmadığını denetler.

```typescript
function categoryIsAlsoSeriesRole(dataView: DataViewCategorical, seriesRoleName: string, categoryRoleName: string): boolean;
```

Örnek:

```typescript
import powerbi from "powerbi-visuals-api";
import DataViewCategorical = powerbi.DataViewCategorical;
import { converterHelper } from "powerbi-visuals-utils-dataviewutils";
// ...


// This object is actually part of the dataView object.
let categorical: DataViewCategorical = {
    categories: [{
        source: {
            displayName: "Microsoft",
            roles: {
                "power": true,
                "bi": true
            }
        },
        values: []
    }]
};

converterHelper.categoryIsAlsoSeriesRole(categorical, "power", "bi");

// returns: true
```

### <a name="getseriesname"></a>getSeriesName

Bu işlev serinin adını döndürür.

```typescript
function getSeriesName(source: DataViewMetadataColumn): PrimitiveValue;
```

Örnek:

```typescript
import powerbi from "powerbi-visuals-api";
import DataViewMetadataColumn = powerbi.DataViewMetadataColumn;
import { converterHelper } from "powerbi-visuals-utils-dataviewutils";

// This object is actually a part of the dataView object.
let metadata: DataViewMetadataColumn = {
    displayName: "Microsoft",
    roles: {
        "power": true,
        "bi": true
    },
    groupName: "Power BI"
};

converterHelper.getSeriesName(metadata);

// returns: Power BI
```

### <a name="isimageurlcolumn"></a>isImageUrlColumn

Bu işlev sütunun resim url'si içerip içermediğini denetler.

```typescript
function isImageUrlColumn(column: DataViewMetadataColumn): boolean;
```

Örnek:

```typescript
import powerbi from "powerbi-visuals-api";
import DataViewMetadataColumn = powerbi.DataViewMetadataColumn;
import { converterHelper } from "powerbi-visuals-utils-dataviewutils";

// This object is actually a part of the dataView object.
let metadata: DataViewMetadataColumn = {
    displayName: "Microsoft",
    type: {
        misc: {
            imageUrl: true
        }
    }
};

converterHelper.isImageUrlColumn(metadata);

// returns: true
```

### <a name="isweburlcolumn"></a>isWebUrlColumn

Bu işlev sütunun web url'si içerip içermediğini denetler.

```typescript
function isWebUrlColumn(column: DataViewMetadataColumn): boolean;
```

Örnek:

```typescript
import powerbi from "powerbi-visuals-api";
import DataViewMetadataColumn = powerbi.DataViewMetadataColumn;
import { converterHelper } from "powerbi-visuals-utils-dataviewutils";

// This object is actually a part of the dataView object.
let metadata: DataViewMetadataColumn = {
    displayName: "Microsoft",
    type: {
        misc: {
            webUrl: true
        }
    }
};

converterHelper.isWebUrlColumn(metadata);

// returns: true
```

### <a name="hasimageurlcolumn"></a>hasImageUrlColumn

Bu işlev dataView'da resim url'si içeren bir sütun bulunup bulunmadığını denetler.

```typescript
function hasImageUrlColumn(dataView: DataView): boolean;
```

Örnek:

```typescript
import DataView = powerbi.DataView;
import converterHelper = powerbi.extensibility.utils.dataview.converterHelper;

// This object is actually part of the dataView object.
let dataView: DataView = {
    metadata: {
        columns: [
            {
                displayName: "Microsoft"
            },
            {
                displayName: "Power BI",
                type: {
                    misc: {
                        imageUrl: true
                    }
                }
            }
        ]
    }
};

converterHelper.hasImageUrlColumn(dataView);

// returns: true
```

## <a name="dataviewobjectsparser"></a>DataViewObjectsParser

`DataViewObjectsParser`, biçimlendirme panelinin özelliklerini ayrıştırmaya yönelik en basit yolu sağlar.

Sınıf aşağıdaki yöntemleri sağlar:

### <a name="getdefault"></a>getDefault

Bu statik yöntem bir DataViewObjectsParser örneği döndürür.

```typescript
static getDefault(): DataViewObjectsParser;
```

Örnek:

```typescript
import { dataViewObjectsParser } from "powerbi-visuals-utils-dataviewutils";
// ...

dataViewObjectsParser.getDefault();

// returns: an instance of the DataViewObjectsParser
```

### <a name="parse"></a>parse

Bu yöntem biçimlendirme panelinin özelliklerini ayrıştırır ve bir `DataViewObjectsParser` örneği döndürür.

```typescript
static parse<T extends DataViewObjectsParser>(dataView: DataView): T;
```

Örnek:

```typescript
import powerbi from "powerbi-visuals-api";
import IVisual = powerbi.extensibility.IVisual;
import VisualUpdateOptions = powerbi.extensibility.visual.VisualUpdateOptions;
import { dataViewObjectsParser } from "powerbi-visuals-utils-dataviewutils";

/**
 * This class describes formatting panel properties.
 * Name of the property should match its name described in the capabilities.
 */
class DataPointProperties {
    public fillColor: string = "red"; // This value is a default value of the property.
}

class PropertiesParser extends dataViewObjectsParser.DataViewObjectsParser {
    /**
     * This property describes a group of properties.
     */
    public dataPoint: DataPointProperties = new DataPointProperties();
}

export class YourVisual extends IVisual {
    // implementation of the IVisual.

    private propertiesParser: PropertiesParser;

    public update(options: VisualUpdateOptions): void {
        // Parses properties.
        this.propertiesParser = PropertiesParser.parse<PropertiesParser>(options.dataViews[0]);

        // You can use the properties after parsing
        console.log(this.propertiesParser.dataPoint.fillColor); // returns "red" as default value, it will be updated automatically after any change of the formatting panel.
    }
}
```

## <a name="enumerateobjectinstances"></a>enumerateObjectInstances

Bu statik yöntem özellikleri numaralandırır ve bir `VisualObjectInstanceEnumeration` örneği döndürür.

Bunu görselin `enumerateObjectInstances` yönteminde yürütün.

```typescript
static enumerateObjectInstances(dataViewObjectParser: dataViewObjectsParser.DataViewObjectsParser, options: EnumerateVisualObjectInstancesOptions): VisualObjectInstanceEnumeration;
```

Örnek:

```typescript
import powerbi from "powerbi-visuals-api";
import IVisual = powerbi.extensibility.IVisual;
import EnumerateVisualObjectInstancesOptions = powerbi.EnumerateVisualObjectInstancesOptions;
import VisualObjectInstanceEnumeration = powerbi.VisualObjectInstanceEnumeration;
import VisualUpdateOptions = powerbi.extensibility.visual.VisualUpdateOptions;
import { dataViewObjectsParser } from "powerbi-visuals-utils-dataviewutils";

/**
 * This class describes formatting panel properties.
 * Name of the property should match its name described in the capabilities.
 */
class DataPointProperties {
    public fillColor: string = "red";
}

class PropertiesParser extends dataViewObjectsParser.DataViewObjectsParser {
    /**
     * This property describes a group of properties.
     */
    public dataPoint: DataPointProperties = new DataPointProperties();
}

export class YourVisual extends IVisual {
    // implementation of the IVisual.

    private propertiesParser: PropertiesParser;

    public update(options: VisualUpdateOptions): void {
        // Parses properties.
        this.propertiesParser = PropertiesParser.parse<PropertiesParser>(options.dataViews[0]);
    }

    /**
     * This method will be executed only if the formatting panel is open.
     */
    public enumerateObjectInstances(options: EnumerateVisualObjectInstancesOptions): VisualObjectInstanceEnumeration {
        return PropertiesParser.enumerateObjectInstances(this.propertiesParser, options);
    }
}
```
