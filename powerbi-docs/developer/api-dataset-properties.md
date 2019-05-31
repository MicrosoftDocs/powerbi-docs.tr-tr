---
title: Power BI veri kümesi özellikleri
description: Power BI veri kümesi API'lerinin özellikleri hakkında bilgi edinin
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/08/2018
ms.openlocfilehash: 508f304e2f5033c301db683e3b7557856fb3731b
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "61386316"
---
# <a name="dataset-properties"></a>Veri kümesi özellikleri

Veri kümesi API'sinin geçerli v1 sürümü, veri kümesinin yalnızca bir ad ve tablo koleksiyonuyla oluşturulmasına izin verir. Her tablonun bir adı ve sütun koleksiyonu olabilir. Her sütunun bir adı ve veri türü vardır. Bu özellikleri en belirgin şekilde tablolar arasındaki ölçüler ve ilişkiler için sağlanan destekle genişletiyoruz. Bu sürümde desteklenen özelliklerin tam listesi:

> [!IMPORTANT]
> Buna, [Veri Kümesi İşlem Grupları](https://docs.microsoft.com/rest/api/power-bi/datasets) sayfasında erişebilirsiniz.

## <a name="dataset"></a>Veri kümesi

Ad  |Tür  |Açıklama  |Salt Okunur  |Gerekli
---------|---------|---------|---------|---------
kimlik     |  Guid       | Veri kümesi için sistem genelinde benzersiz tanımlayıcı.        | Doğru        | Yanlış        
ad     | Dize        | Veri kümesinin kullanıcı tanımlı adı.        | Yanlış        | Doğru        
tablolar     | Table[]        | Tablo koleksiyonu.        |  Yanlış       | Yanlış        
ilişkiler     | Relationship[]        | Tablolar arasında ilişki koleksiyonu.        | Yanlış        |  Yanlış  
defaultMode     | Dize        | Veri kümesi, akışlı gönderildiğinde olup olmadığını belirler veya her ikisi de "Push" ve "Akış" değerine sahip         | Yanlış        |  Yanlış

## <a name="table"></a>Tablo

Ad  |Tür  |Açıklama  |Salt Okunur  |Gerekli
---------|---------|---------|---------|---------
ad     | Dize        |  Tablonun kullanıcı tanımlı adı. Ayrıca tablonun tanımlayıcısı olarak da kullanılır.       | Yanlış        |  Doğru       
sütunlar     |  column[]       |  Sütun koleksiyonu.       | Yanlış        |  Doğru       
ölçüler     | measure[]        |  Ölçü koleksiyonu.       | Yanlış        |  Yanlış       
isHidden     | Boole        | Doğru olduğunda, tablo istemci araçlarından gizlenir.        | Yanlış        | Yanlış        

## <a name="column"></a>Sütun

Ad  |Tür  |Açıklama  |Salt Okunur  |Gerekli
---------|---------|---------|---------|---------
ad     |  Dize        | Sütunun kullanıcı tanımlı adı.        |  Yanlış       | Doğru       
dataType     |  Dize       |  Desteklenen [EDM veri türleri](https://msdn.microsoft.com/library/ee382832.aspx) ve kısıtlamalar. Bkz. [Veri türü kısıtlamaları](#DataTypeRestrictions).      |  Yanlış       | Doğru        
formatString     | Dize        | Değerin görüntülenirken nasıl biçimlendirilmesi gerektiğini açıklayan bir dize. Dize biçimlendirmesi hakkında daha fazla bilgi edinmek için bkz. [FORMAT_STRING İçeriği](https://msdn.microsoft.com/library/ms146084.aspx).      | Yanlış        | Yanlış        
sortByColumn    | Dize        |   Geçerli sütunu sıralamak için kullanılacak, aynı tablodaki bir sütunun dize adı.     | Yanlış        | Yanlış       
dataCategory     | Dize        |  Bu sütun içindeki verileri açıklayan, veri kategorisi için kullanılacak dize değeri. Bazı yaygın değerler şunlardır: Address, City, Continent, Country, Image, ImageUrl, Latitude, Longitude, Organization, Place, PostalCode, StateOrProvince, WebUrl       |  Yanlış       | Yanlış        
isHidden    |  Boole       |  Sütunun görünümden gizlenip gizlenmeyeceğini belirten özellik. Varsayılan değer Yanlış'tır.       | Yanlış        | Yanlış        
summarizeBy     | Dize        |  Sütun için varsayılan toplama yöntemi. Değerler şunlardır: default, none, sum, min, max, count, average, distinctCount     |  Yanlış       | Yanlış

## <a name="measure"></a>Ölçü

Ad  |Tür  |Açıklama  |Salt Okunur  |Gerekli
---------|---------|---------|---------|---------
ad     | Dize        |  Ölçünün kullanıcı tanımlı adı.       |  Yanlış       | Doğru        
ifade     | Dize        | Geçerli bir DAX ifadesi.        | Yanlış        |  Doğru       
formatString     | Dize        |  Değerin görüntülenirken nasıl biçimlendirilmesi gerektiğini açıklayan bir dize. Dize biçimlendirmesi hakkında daha fazla bilgi edinmek için bkz. [FORMAT_STRING İçeriği](https://msdn.microsoft.com/library/ms146084.aspx).       | Yanlış        | Yanlış        
isHidden     | Dize        |  Doğru olduğunda, tablo istemci araçlarından gizlenir.       |  Yanlış       | Yanlış       

## <a name="relationship"></a>İlişki

Ad  |Tür  |Açıklama  |Salt Okunur  |Gerekli 
---------|---------|---------|---------|---------
ad     | Dize        | İlişkinin kullanıcı tanımlı adı. Ayrıca ilişkinin tanımlayıcısı olarak da kullanılır.        | Yanlış       | Doğru        
crossFilteringBehavior     | Dize        |    İlişkinin filtre yönü: OneDirection (varsayılan), BothDirections, Automatic       | Yanlış        | Yanlış        
fromTable     | Dize        | Yabancı anahtar tablosunun adı.        | Yanlış        | Doğru         
fromColumn    | Dize        | Yabancı anahtar sütununun adı.        | Yanlış        | Doğru         
toTable    | Dize        | Birincil anahtar tablosunun adı.        | Yanlış        | Doğru         
toColumn     | Dize        | Birincil anahtar sütununun adı.        | Yanlış        | Doğru        

<a name="DataTypeRestrictions"/>

## <a name="data-type-restrictions-applies-to-datatype-property"></a>Veri türü kısıtlamaları (dataType özelliği için geçerlidir)

Veri türü  |Kısıtlamalar  
---------|---------
Int64     |   Int64.MaxValue ve Int64.MinValue değerlerine izin verilmez.      
Çift     |  Double.MaxValue ve Double.MinValue değerlerine izin verilmez. NaN desteklenmez. +Infinity ve -Infinity bazı işlevlerde (ör. Min, Maks) desteklenmez.       
Boole     |   Doğru veya Yanlış.
Tarih Saat    |   Veri yüklemesi sırasında, gün kesitleri içeren değerleri 1/300 saniyenin (3,33 ms) tam katları olarak nicelendiririz.      
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