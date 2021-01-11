---
title: Daha iyi tümleşik BI içgörüleri için, Power BI tümleşik analizlerinde Power BI veri kümesi özellikleri
description: Power BI veri kümesi API'lerinin özellikleri hakkında bilgi edinin. Power BI tümleşik analiz kullanarak daha iyi tümleşik BI içgörüleri elde edin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/08/2018
ms.openlocfilehash: b4bd173c2f3730a0a6082214afbfdf5760048102
ms.sourcegitcommit: eeaf607e7c1d89ef7312421731e1729ddce5a5cc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2021
ms.locfileid: "97887696"
---
# <a name="dataset-properties"></a>Veri kümesi özellikleri

Veri kümesi API'sinin geçerli v1 sürümü, veri kümesinin yalnızca bir ad ve tablo koleksiyonuyla oluşturulmasına izin verir. Her tablonun bir adı ve sütun koleksiyonu olabilir. Her sütunun bir adı ve veri türü vardır. Bu özellikleri en belirgin şekilde tablolar arasındaki ölçüler ve ilişkiler için sağlanan destekle genişletiyoruz. Bu sürümde desteklenen özelliklerin tam listesi:

> [!IMPORTANT]
> Buna, [Veri Kümesi İşlem Grupları](/rest/api/power-bi/datasets) sayfasında erişebilirsiniz.

## <a name="dataset"></a>Veri kümesi

Ad  |Tür  |Description  |Salt Okunur  |Gerekli
---------|---------|---------|---------|---------
kimlik     |  Guid       | Veri kümesi için sistem genelinde benzersiz tanımlayıcı.        | Doğru        | Yanlış        
name     | Dize        | Veri kümesinin kullanıcı tanımlı adı.        | Yanlış        | Doğru        
tablolarda     | Table[]        | Tablo koleksiyonu.        |  False       | Yanlış        
ilişkiler     | Relationship[]        | Tablolar arasında ilişki koleksiyonu.        | False        |  Yanlış  
defaultMode     | Dize        | "Push" ve "Streaming" değerleriyle veri kümesinin gönderildiğini, akıtıldığını veya her ikisinin de yapıldığını belirler.         | False        |  Yanlış

## <a name="table"></a>Tablo

Ad  |Tür  |Description  |Salt Okunur  |Gerekli
---------|---------|---------|---------|---------
name     | Dize        |  Tablonun kullanıcı tanımlı adı. Ayrıca tablonun tanımlayıcısı olarak da kullanılır.       | Yanlış        |  Doğru       
sütunlar     |  column[]       |  Sütun koleksiyonu.       | Yanlış        |  Doğru       
ölçüler     | measure[]        |  Ölçü koleksiyonu.       | False        |  Yanlış       
isHidden     | Boole        | Doğru olduğunda, tablo istemci araçlarından gizlenir.        | False        | Yanlış        

## <a name="column"></a>Sütun

Ad  |Tür  |Description  |Salt Okunur  |Gerekli
---------|---------|---------|---------|---------
name     |  Dize        | Sütunun kullanıcı tanımlı adı.        |  Yanlış       | Doğru       
dataType     |  Dize       |  Desteklenen [EDM veri türleri](/dotnet/framework/data/adonet/entity-data-model-primitive-data-types) ve kısıtlamalar. Bkz. [Veri türü kısıtlamaları](#data-type-restrictions).      |  Yanlış       | Doğru        
formatString     | Dize        | Değerin görüntülenirken nasıl biçimlendirilmesi gerektiğini açıklayan bir dize. Dize biçimlendirmesi hakkında daha fazla bilgi edinmek için bkz. [FORMAT_STRING İçeriği](/analysis-services/multidimensional-models/mdx/mdx-cell-properties-format-string-contents).      | False        | Yanlış        
sortByColumn    | Dize        |   Geçerli sütunu sıralamak için kullanılacak, aynı tablodaki bir sütunun dize adı.     | False        | Yanlış       
dataCategory     | Dize        |  Bu sütun içindeki verileri açıklayan, veri kategorisi için kullanılacak dize değeri. Bazı yaygın değerler şunlardır: Address, City, Continent, Country, Image, ImageUrl, Latitude, Longitude, Organization, Place, PostalCode, StateOrProvince, WebUrl       |  False       | Yanlış        
isHidden    |  Boole       |  Sütunun görünümden gizlenip gizlenmeyeceğini belirten özellik. Varsayılan değer false’tur.       | False        | Yanlış        
summarizeBy     | Dize        |  Sütun için varsayılan toplama yöntemi. Değerler şunlardır: default, none, sum, min, max, count, average, distinctCount     |  False       | Yanlış

## <a name="measure"></a>Ölçü

Ad  |Tür  |Description  |Salt Okunur  |Gerekli
---------|---------|---------|---------|---------
name     | Dize        |  Ölçünün kullanıcı tanımlı adı.       |  Yanlış       | Doğru        
ifade     | Dize        | Geçerli bir DAX ifadesi.        | Yanlış        |  Doğru       
formatString     | Dize        |  Değerin görüntülenirken nasıl biçimlendirilmesi gerektiğini açıklayan bir dize. Dize biçimlendirmesi hakkında daha fazla bilgi edinmek için bkz. [FORMAT_STRING İçeriği](/analysis-services/multidimensional-models/mdx/mdx-cell-properties-format-string-contents).       | False        | Yanlış        
isHidden     | Dize        |  Doğru olduğunda, tablo istemci araçlarından gizlenir.       |  False       | Yanlış       

## <a name="relationship"></a>İlişki

Ad  |Tür  |Description  |Salt Okunur  |Gerekli 
---------|---------|---------|---------|---------
name     | Dize        | İlişkinin kullanıcı tanımlı adı. Ayrıca ilişkinin tanımlayıcısı olarak da kullanılır.        | Yanlış       | Doğru        
crossFilteringBehavior     | Dize        |    İlişkinin filtre yönü: OneDirection (varsayılan), BothDirections, Automatic       | False        | Yanlış        
fromTable     | Dize        | Yabancı anahtar tablosunun adı.        | Yanlış        | Doğru         
fromColumn    | Dize        | Yabancı anahtar sütununun adı.        | Yanlış        | Doğru         
toTable    | Dize        | Birincil anahtar tablosunun adı.        | Yanlış        | Doğru         
toColumn     | Dize        | Birincil anahtar sütununun adı.        | Yanlış        | Doğru        

## <a name="data-type-restrictions"></a>Veri türü kısıtlamaları

Bu kısıtlamalar dataType özelliği için geçerlidir.

Veri türü  |Kısıtlamalar  
---------|---------
Int64     |   Int64.MaxValue ve Int64.MinValue değerlerine izin verilmez.      
Çift     |  Double.MaxValue ve Double.MinValue değerlerine izin verilmez. NaN desteklenmez. +Infinity ve -Infinity bazı işlevlerde (ör. Min, Maks) desteklenmez.       
Boole     |   Doğru veya Yanlış.
Tarih saat    |   Veri yüklemesi sırasında, gün kesitleri içeren değerleri 1/300 saniyenin (3,33 ms) tam katları olarak nicelendiririz.      
Dize     |  Şu anda dize değeri başına en çok 4000 karaktere izin verilir.
Ondalık|precision=28, scale=4

## <a name="example"></a>Örnek
Aşağıdaki kod örneği bu özelliklerden bazılarını içerir:

```json
{

  "name": "PushAdvanced",

  "tables": [

    {

      "name": "Date",

      "columns": [

        {

          "name": "Date",

          "dataType": "dateTime",

          "formatString": "dddd\\, mmmm d\\, yyyy",

          "summarizeBy": "none"

        }

      ]

    },

    {

      "name": "sales",

      "columns": [

        {

          "name": "Date",

          "dataType": "dateTime",

          "formatString": "dddd\\, mmmm d\\, yyyy",

          "summarizeBy": "none"

        },

        {

          "name": "Sales",

          "dataType": "int64",

          "formatString": "0",

          "summarizeBy": "sum"

        }

      ],

      "measures": [

        {

          "name": "percent to forecast",

          "expression": "SUM(sales[Sales])/SUM(forecast[forecast])",

          "formatString": "0.00 %;-0.00 %;0.00 %"

        }

      ]

    },

    {

      "name": "forecast",

      "columns": [

        {

          "name": "date",

          "dataType": "dateTime",

          "formatString": "m/d/yyyy",

          "summarizeBy": "none"

        },

        {

          "name": "forecast",

          "dataType": "int64",

          "formatString": "0",

          "summarizeBy": "sum"

        }

      ]

    }

  ],

  "relationships": [

    {

      "name": "2ea345ce-b147-436e-8ac2-9d3c4d82af8d",

      "fromTable": "sales",

      "fromColumn": "Date",

      "toTable": "Date",

      "toColumn": "Date",

      "crossFilteringBehavior": "bothDirections"

    },

    {

      "name": "5d95f419-e589-4345-9581-6e70670b1bba",

      "fromTable": "forecast",

      "fromColumn": "date",

      "toTable": "Date",

      "toColumn": "Date",

      "crossFilteringBehavior": "bothDirections"

    }

  ]

}
```