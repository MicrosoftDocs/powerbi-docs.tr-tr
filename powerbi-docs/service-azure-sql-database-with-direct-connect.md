---
title: "DirectQuery ile Azure SQL Veritabanı"
description: "DirectQuery ile Azure SQL Veritabanı"
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
ms.openlocfilehash: 83613f0ed915a03b65b90d4bf61e37568b922182
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="azure-sql-database-with-directquery"></a>DirectQuery ile Azure SQL Veritabanı
Azure SQL Veritabanı'na doğrudan nasıl bağlanacağınızı ve canlı verilerin kullanıldığı raporları nasıl oluşturacağınızı öğrenin. Verilerinizi Power BI yerine kaynakta tutabilirsiniz.

DirectQuery ile, siz verileri rapor görünümünde araştırırken sorgular Azure SQL Varitabanınıza geri gönderilir. Bu deneyim, bağlandıkları veritabanlarına ve varlıklara aşina kullanıcılar için önerilir.

**Notlar:**

* Bağlanırken tam sunucu adını belirtin (daha fazla ayrıntı için aşağıya bakın)
* Veritabanı güvenlik duvarı kurallarının "[Azure hizmetlerine erişime izin ver](https://msdn.microsoft.com/library/azure/ee621782.aspx)" olarak yapılandırıldığından emin olun.
* Sütun seçme veya filtre ekleme gibi her işlem veritabanına sorgu gönderir
* Kutucuklar yaklaşık her 15 dakikada bir yenilenir. (Yenileme işleminin zamanlanması gerekmez.) Bu, bağlantı kurulduktan sonra Gelişmiş ayarlar'da ayarlanabilir.
* Soru-Cevap, DirectQuery veri kümeleri için kullanılamaz
* Şema değişiklikleri otomatik olarak alınmaz

Bu kısıtlamalar ve notlar, biz deneyimleri iyileştirmeye devam ettikçe değişebilir. Bağlanma adımları aşağıda ayrıntılı şekilde verilmiştir. 

## <a name="power-bi-desktop-and-directquery"></a>Power BI Desktop ve DirectQuery
DirectQuery'yi kullanarak Azure SQL Veritabanı'na bağlanmak için Power BI Desktop'ı kullanmanız gerekir. Bu yaklaşım, daha fazla esneklik ve özellik sunar. Power BI Desktop kullanılarak oluşturulan raporlar daha sonra Power BI hizmetinde yayımlanabilir. Power BI Desktop'ta [DirectQuery'yi kullanarak Azure SQL Veritabanı](desktop-use-directquery.md)'na nasıl bağlanacağınızla ilgili daha fazla bilgi edinebilirsiniz. 

## <a name="connecting-through-power-bi"></a>Power BI aracılığıyla bağlanma
Artık Azure SQL Veritabanı'na doğrudan Power BI hizmetinden bağlanamazsınız. [Azure SQL Veritabanı bağlayıcısını](https://app.powerbi.com/getdata/bigdata/azure-sql-database-with-live-connect) seçtiğinizde, bağlantıyı Power BI Desktop'tan kurmanız istenir. Ardından Power BI Desktop raporlarınızı Power BI hizmetinizde yayımlayabilirsiniz. 

![](media/service-azure-sql-database-with-direct-connect/azure-sql-database-in-power-bi.png)

### <a name="finding-parameter-values"></a>Parametre Değerlerini Bulma
Tam sunucu adınız ve veritabanınızın adı Azure Portal'da bulunabilir.

![](media/service-azure-sql-database-with-direct-connect/azureportnew_update.png)

![](media/service-azure-sql-database-with-direct-connect/azureportal_update.png)

## <a name="next-steps"></a>Sonraki adımlar
[Power BI Desktop'ta DirectQuery'yi kullanma](desktop-use-directquery.md)  
[Power BI ile çalışmaya başlama](service-get-started.md)  
[Power BI için veri alma](service-get-data.md)  
Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

