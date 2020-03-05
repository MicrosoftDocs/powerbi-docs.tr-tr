---
title: Bir veri kümesine veri gönderme
description: Power BI veri kümelerine veri gönderme
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 05/22/2019
ms.openlocfilehash: ceebf32f62395db8741eaf43cfc494652fbbbf98
ms.sourcegitcommit: 0cc594ebb78a6d0e88784673ed09f8aefd10c7a7
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76818813"
---
# <a name="push-data-into-a-power-bi-dataset"></a>Power BI veri kümelerine veri gönderme

Power BI API verileri Power BI veri kümesine göndermenize olanak tanır. Bu makalede bir Product tablosu içeren Sales Marketing veri kümesinin mevcut bir veri kümesine nasıl gönderileceğini göstereceğiz.

Başlamadan önce Azure Active Directory (Azure AD) ve [Power BI hesabınızın](create-an-azure-active-directory-tenant.md) olması gerekir.

## <a name="steps-to-push-data-into-a-dataset"></a>Bir veri kümesine veri göndermeye ilişkin adımlar

* 1\. Adım: [Bir uygulamayı Azure AD'ye kaydetme](walkthrough-push-data-register-app-with-azure-ad.md)
* 2\. Adım: [Kimlik doğrulaması erişim belirteci alma](walkthrough-push-data-get-token.md)
* 3\. Adım: [Power BI'da bir veri kümesi oluşturma](walkthrough-push-data-create-dataset.md)
* 4\. Adım: [Bir Power BI tablosuna satır eklemek için veri kümesi alma](walkthrough-push-data-get-datasets.md)
* 5\. Adım: [Bir Power BI tablosuna satır ekleme](walkthrough-push-data-add-rows.md)

Sonraki bölümde, veri gönderilmesini sağlayan Power BI API işlemleri genel olarak ele alınmıştır.

## <a name="power-bi-api-operations-to-push-data"></a>Veri göndermeye yönelik için Power BI API işlemleri

Power BI REST API'siyle Power BI'a veri kaynakları gönderebilirsiniz. Bir uygulama veri kümesine satır eklediğinde, pano kutucukları yeni verilerle otomatik olarak güncelleştirilir. Verileri göndermek için [PostDataset](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postdataset) ve [PostRows](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postrows) işlemlerini kullanın. Bir veri kümesini bulmak için [Veri Kümelerini Al](https://docs.microsoft.com/rest/api/power-bi/datasets/getdatasets) işlemini kullanın. Bu işlemlerden herhangi birinde bir grupla çalışmak için grup kimliği geçirebilirsiniz. Grup kimliği listesini almak için [Get Groups](https://docs.microsoft.com/rest/api/power-bi/groups/getgroups) işlemini kullanın.

Bir veri kümesine veri göndermeye yönelik işlemler şunlardır:

* [PostDataset](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postdataset)
* [Get Datasets (Veri Kümelerini Al)](https://docs.microsoft.com/rest/api/power-bi/datasets/getdatasets)
* [Post Rows](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postrows)
* [Grupları Al](https://docs.microsoft.com/rest/api/power-bi/groups/getgroups)

Bir JavaScript Nesne Gösterimi (JSON) dizesini Power BI hizmetine geçirerek veri kümesi oluşturabilirsiniz. JSON hakkında daha fazla bilgi edinmek için bkz. [Introducing JSON (JSON'a giriş)](https://json.org/).

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

Sales Marketing veri kümesi örneğimizde, aşağıda gösterildiği gibi bir JSON dizesi geçirebilirsiniz. Bu örnekte veri kümesinin adı **SalesMarketing** ve tablonun adı **Product**'tır. Tabloyu tanımladıktan sonra tablo şemasını tanımlarsınız. **SalesMarketing** veri kümesi için, tablo şemasının şu sütunları vardır: ProductID, Manufacturer, Category, Segment, Product ve IsCompete.

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
| Çift |Double.MaxValue ve Double.MinValue değerlerine izin verilmez. NaN desteklenmez. +Infinity ve -Infinity bazı işlevlerde (örneğin Min, Max) desteklenmez. |
| Boole |Yok |
| Tarih Saat |Veri yüklemesi sırasında, gün kesitleri içeren değerleri 1/300 saniyenin (3,33 ms) tam katları olarak nicelendiririz. |
| Dize |Şu anda en fazla 128.000 karaktere izin verilir. |

## <a name="learn-more-about-pushing-data-into-power-bi"></a>Power BI'a veri gönderme hakkında daha fazla bilgi edinin

Verileri bir veri kümesine göndermeye başlamak için, sol gezinti bölmesinde [1. Adım: Bir uygulamayı Azure AD'ye kaydetme](walkthrough-push-data-register-app-with-azure-ad.md) bölümüne bakın.

[Sonraki Adım >](walkthrough-push-data-register-app-with-azure-ad.md)

## <a name="next-steps"></a>Sonraki adımlar

[Power BI'a kaydolma](create-an-azure-active-directory-tenant.md)  
[Introducing JSON (JSON'a giriş)](https://json.org/)  
[Overview of Power BI REST API (Power BI REST API'sine Genel Bakış)](overview-of-power-bi-rest-api.md)  
Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)