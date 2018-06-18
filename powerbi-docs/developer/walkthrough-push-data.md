---
title: Bir veri kümesine veri gönderme
description: Power BI veri kümelerine veri gönderme
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 01/05/2017
ms.author: maghan
ms.openlocfilehash: 96b29c9dc6c384b663ef375d4968dedb011bd05d
ms.sourcegitcommit: 8ee0ebd4d47a41108387d13a3bc3e7e2770cbeb8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/06/2018
ms.locfileid: "34813124"
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
Power BI REST API'siyle Power BI'a veri kaynakları gönderebilirsiniz. Bir uygulama, veri kümesine satırlar eklediğinde panodaki kutucuklar, güncelleştirilen verilerle otomatik olarak güncelleştirilir. Veri göndermek için [PostRows](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postrows) işlemiyle birlikte [PostDataset](https://docs.microsoft.com/rest/api/power-bi/pushdatasets) işlemi kullanılır. Bir veri kümesini bulmak için [Veri Kümelerini Al](https://docs.microsoft.com/rest/api/power-bi/datasets/getdatasets) işlemini kullanmanız gerekir. Bu işlemlerden herhangi biri için bir grupla çalışmak üzere grup kimliği geçirebilirsiniz. Bir grup kimliği listesi almak için [Grupları Al](https://docs.microsoft.com/rest/api/power-bi/groups/getgroups) işlemini kullanın.

Bir veri kümesine veri göndermeye yönelik işlemler şunlardır:

* [PostDataset](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postdataset)
* [Get Datasets (Veri Kümelerini Al)](https://docs.microsoft.com/rest/api/power-bi/datasets/getdatasets)
* [Post Rows](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postrows)
* [Grupları Al](https://docs.microsoft.com/rest/api/power-bi/groups/getgroups)

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
[Introducing JSON (JSON'a giriş)](http://json.org/)  
[Overview of Power BI REST API (Power BI REST API'sine Genel Bakış)](overview-of-power-bi-rest-api.md)  
Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

