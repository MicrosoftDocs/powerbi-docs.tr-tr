---
title: "Bir veri kümesine veri gönderme"
description: "Power BI veri kümelerine veri gönderme"
services: powerbi
documentationcenter: 
author: guyinacube
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 08/10/2017
ms.author: asaxton
ms.openlocfilehash: e62b08614a38502fb79f48f369013d32fd538659
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="push-data-into-a-power-bi-dataset"></a>Power BI veri kümelerine veri gönderme
Power BI API ile bir Power BI veri kümesine veri gönderebilirsiniz. Veri kümenize anahtar verileri göndermek için mevcut bir iş akışını genişletmek istediğinizi varsayalım. Bu örnekte, bir veri kümesine, Ürün tablosu içeren bir Satış Pazarlama veri kümesi göndermeniz gerekiyor.

Bir veri kümesine veri göndermeye başlamadan önce Azure Active Directory (Azure AD) ve [Power BI hesabınızın](create-an-azure-active-directory-tenant.md) olması gerekir.

## <a name="steps-to-push-data-into-a-dataset"></a>Bir veri kümesine veri göndermeye ilişkin adımlar
* 1. Adım: [Bir uygulamayı Azure AD'ye kaydetme](walkthrough-push-data-register-app-with-azure-ad.md)
* 2. Adım: [Kimlik doğrulaması erişim belirteci alma](walkthrough-push-data-get-token.md)
* 3. Adım: [Power BI'da bir veri kümesi oluşturma](walkthrough-push-data-create-dataset.md)
* 4. Adım: [Bir Power BI tablosuna satır eklemek için veri kümesi alma](walkthrough-push-data-get-datasets.md)
* 5. Adım: [Bir Power BI tablosuna satır ekleme](walkthrough-push-data-add-rows.md)

Sonraki bölümde, veri gönderilmesini sağlayan Power BI API işlemleri genel olarak ele alınmıştır.

## <a name="power-bi-api-operations-to-push-data"></a>Veri göndermeye yönelik için Power BI API işlemleri
Power BI REST API'siyle Power BI'a veri kaynakları gönderebilirsiniz. Bir uygulama, veri kümesine satırlar eklediğinde panodaki kutucuklar, güncelleştirilen verilerle otomatik olarak güncelleştirilir. Veri göndermek için [Satır Ekle](https://msdn.microsoft.com/library/mt203561.aspx) işlemiyle birlikte [Veri Kümesi Oluştur](https://msdn.microsoft.com/library/mt203562.aspx) işlemi kullanılır. Bir veri kümesini bulmak için [Veri Kümelerini Al](https://msdn.microsoft.com/library/mt203567.aspx) işlemini kullanmanız gerekir. Bu işlemlerden herhangi biri için bir grupla çalışmak üzere grup kimliği geçirebilirsiniz. Bir grup kimliği listesi almak için [Grupları Al](https://msdn.microsoft.com/library/mt243842.aspx) işlemini kullanın. Power BI REST API'sini kullanmaya ilişkin örnekler için bkz. [APIARY'deki Power BI REST API'si](http://docs.powerbi.apiary.io/).

Bir veri kümesine veri göndermeye yönelik işlemler şunlardır:

* [Veri Kümesi Oluştur](https://msdn.microsoft.com/library/mt203562.aspx)
* [Veri Kümelerini Al](https://msdn.microsoft.com/library/mt203567.aspx)
* [Satır Ekle](https://msdn.microsoft.com/library/mt203561.aspx)
* [Grupları Al](https://msdn.microsoft.com/library/mt243842.aspx)

Bir JavaScript Nesne Gösterimi (JSON) dizesini Power BI hizmetine geçirerek veri kümesi oluşturabilirsiniz. JSON hakkında daha fazla bilgi edinmek için bkz. [Introducing JSON (JSON'a giriş)](http://json.org/).

Bir veri kümesi için JSON dizesi aşağıdaki biçimdedir:

**Power BI Veri Kümesi JSON nesnesi**

    {"name": "dataset_name", "tables":
        [{"name": "", "columns":
            [{ "name": "column_name1", "dataType": "data_type"},
             { "name": "column_name2", "dataType": "data_type"},
             { ... }
            ]
          }
        ]
    }

Satış Pazarlama veri kümesi örneğimize geri dönecek olursak, aşağıdaki örnekte verilene benzer bir JSON dizesi geçirmeniz gerekir. Bu örnekteki veri kümesinin adı **Sales Marketing**, tablonun adı ise **Product**'tır. Önce tabloyu, ardından da şemayı tanımlayın. **Sales Marketing** veri kümesi için tablo şeması şu sütunları içerir: ProductID, Manufacturer, Category, Segment, Product ve IsCompete.

**Örnek veri kümesi nesnesi JSON**

    {
        "name": "SalesMarketing",
        "tables": [
            {
                "name": "Product",
                "columns": [
                {
                    "name": "ProductID",
                    "dataType": "int"
                },
                {
                    "name": "Manufacturer",
                    "dataType": "string"
                },
                {
                    "name": "Category",
                    "dataType": "string"
                },
                {
                    "name": "Segment",
                    "dataType": "string"
                },
                {
                    "name": "Product",
                    "dataType": "string"
                },
                {
                    "name": "IsCompete",
                    "dataType": "bool"
                }
                ]
            }
        ]
    }

Bir Power BI tablo şeması için aşağıdaki veri türlerini kullanabilirsiniz.

## <a name="power-bi-table-data-types"></a>Power BI tablosu veri türleri
| **Veri türü** | **Kısıtlamalar** |
| --- | --- |
| Int64 |Int64.MaxValue ve Int64.MinValue değerlerine izin verilmez. |
| Çift |Double.MaxValue ve Double.MinValue değerlerine izin verilmez. NaN desteklenmez. +Infinity ve -Infinity bazı işlevlerde (ör. Min, Maks) desteklenmez. |
| Boole |Yok |
| Tarih Saat |Veri yüklemesi sırasında, gün kesitleri içeren değerleri 1/300 saniyenin (3,33 ms) tam katları olarak nicelendiririz. |
| Dize |Şu anda en fazla 128.000 karaktere izin verilir. |

## <a name="learn-more-about-pushing-data-into-power-bi"></a>Power BI'a veri gönderme hakkında daha fazla bilgi edinin
Bir veri kümesine veri göndermeye başlamak için sol gezinti bölmesindeki [1. Adım: Bir uygulamayı Azure AD'ye kaydetme](walkthrough-push-data-register-app-with-azure-ad.md) bağlantısına bakın.

[Sonraki Adım >](walkthrough-push-data-register-app-with-azure-ad.md)

## <a name="next-steps"></a>Sonraki adımlar
[Power BI'a kaydolma](create-an-azure-active-directory-tenant.md)  
[Veri Kümesi Oluştur](https://msdn.microsoft.com/library/mt203562.aspx)  
[Veri Kümelerini Al](https://msdn.microsoft.com/library/mt203567.aspx)  
[Satır Ekle](https://msdn.microsoft.com/library/mt203561.aspx)  
[Grupları Al](https://msdn.microsoft.com/library/mt243842.aspx)  
[Introducing JSON (JSON'a giriş)](http://json.org/)  
[Overview of Power BI REST API (Power BI REST API'sine Genel Bakış)](overview-of-power-bi-rest-api.md)  
[APIARY'deki Power BI REST API'si](http://docs.powerbi.apiary.io/)  
Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)
