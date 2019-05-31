---
title: Bir veri kümesine veri gönderme
description: Power BI veri kümelerine veri gönderme
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: madia
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 05/22/2019
ms.openlocfilehash: 9eb81610044f795b6f9dc5c58aeefad13de06542
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66222153"
---
# <a name="push-data-into-a-power-bi-dataset"></a>Power BI veri kümelerine veri gönderme

Power BI API'si sayesinde bir Power BI veri kümesine veri gönderme. Bu makalede, var olan bir veri kümesine ürün tablosu içeren bir satış pazarlama veri kümesi göndermek nasıl gösteriyoruz.

Başlamadan önce bir Azure Active Directory (Azure AD) gerekir ve bir [Power BI hesabı](create-an-azure-active-directory-tenant.md).

## <a name="steps-to-push-data-into-a-dataset"></a>Bir veri kümesine veri göndermeye ilişkin adımlar

* 1. Adım: [Bir uygulamayı Azure AD'ye kaydetme](walkthrough-push-data-register-app-with-azure-ad.md)
* 2. Adım: [Kimlik doğrulaması erişim belirteci alma](walkthrough-push-data-get-token.md)
* 3. Adım: [Power BI'da bir veri kümesi oluşturma](walkthrough-push-data-create-dataset.md)
* 4. Adım: [Bir Power BI tablosuna satır eklemek için veri kümesi alma](walkthrough-push-data-get-datasets.md)
* 5 Adım: [Bir Power BI tablosuna satır ekleme](walkthrough-push-data-add-rows.md)

Sonraki bölümde, veri gönderilmesini sağlayan Power BI API işlemleri genel olarak ele alınmıştır.

## <a name="power-bi-api-operations-to-push-data"></a>Veri göndermeye yönelik için Power BI API işlemleri

Power BI REST API'siyle Power BI'a veri kaynakları gönderebilirsiniz. Bir uygulama bir veri kümesine satırlar eklediğinde, güncelleştirme otomatik olarak yeni verilerle birlikte Pano kutucuklarının. Veri göndermeye ilişkin kullanın [PostDataset](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postdataset) ve [PostRows](https://docs.microsoft.com/rest/api/power-bi/pushdatasets/datasets_postrows) işlemleri. Bir veri kümesini bulmak için kullanmak [veri kümelerini Al](https://docs.microsoft.com/rest/api/power-bi/datasets/getdatasets) işlemi. Bu işlemlerden herhangi biri için bir grup ile çalışmak için bir grup kimliği geçirebilirsiniz. Bir grup kimliği listesi almak için kullanın [grupları alma](https://docs.microsoft.com/rest/api/power-bi/groups/getgroups) işlemi.

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

Satış Pazarlama veri kümesi Örneğin, aşağıda gösterildiği gibi bir JSON dizesi geçirmeniz gerekir. Bu örnekte, **Sales Marketing** veri kümesinin adıdır ve **ürün** tablo adı. Tablo tanımlandıktan sonra tablo şeması tanımlayın. **SalesMarketing** veri kümesi için, tablo şemasının şu sütunları vardır: ProductID, Manufacturer, Category, Segment, Product ve IsCompete.

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
| Çift |Double.MaxValue ve Double.MinValue değerlerine izin verilmez. NaN desteklenmez. + Infinity ve - Infinity bazı işlevlerde (örneğin, Min, Maks) desteklenmez. |
| Boole |Yok |
| Tarih Saat |Veri yükleme sırasında biz, 1/300 saniyenin (3,33 ms) tam katlarına gün Kesitleri içeren değerleri nicelendiririz. |
| Dize |Şu anda en fazla 128 K karakterler sağlar. |

## <a name="learn-more-about-pushing-data-into-power-bi"></a>Power BI'a veri gönderme hakkında daha fazla bilgi edinin

Verileri bir veri kümesine göndermeye başlamak için, sol gezinti bölmesinde [1. Adım: Bir uygulamayı Azure AD'ye kaydetme](walkthrough-push-data-register-app-with-azure-ad.md) bölümüne bakın.

[Sonraki Adım >](walkthrough-push-data-register-app-with-azure-ad.md)

## <a name="next-steps"></a>Sonraki adımlar

[Power BI'a kaydolma](create-an-azure-active-directory-tenant.md)  
[Introducing JSON (JSON'a giriş)](http://json.org/)  
[Overview of Power BI REST API (Power BI REST API'sine Genel Bakış)](overview-of-power-bi-rest-api.md)  
Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)