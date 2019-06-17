---
title: DirectQuery ile Azure SQL Veritabanı
description: DirectQuery ile Azure SQL Veritabanı
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.custom: ''
ms.date: 06/20/2018
LocalizationGroup: Data from databases
ms.openlocfilehash: 5365c076b75d0989df8db15c1dc16f4e11bc3f09
ms.sourcegitcommit: c539726c9c180e899a8a34443e3fda2b9848beb2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66448403"
---
# <a name="azure-sql-database-with-directquery"></a>DirectQuery ile Azure SQL Veritabanı

Azure SQL Veritabanı'na doğrudan nasıl bağlanacağınızı ve canlı verilerin kullanıldığı raporları nasıl oluşturacağınızı öğrenin. Verilerinizi Power BI yerine kaynakta tutabilirsiniz.

DirectQuery ile, siz verileri rapor görünümünde araştırırken sorgular Azure SQL Varitabanınıza geri gönderilir. Bu deneyim, bağlandıkları veritabanlarına ve varlıklara aşina kullanıcılar için önerilir.

**Notlar:**

* Bağlanırken tam sunucu adını belirtin (daha fazla ayrıntı için aşağıya bakın)
* Veritabanı güvenlik duvarı kurallarının "[Azure hizmetlerine erişime izin ver](https://msdn.microsoft.com/library/azure/ee621782.aspx)" olarak yapılandırıldığından emin olun
* Sütun seçme veya filtre ekleme gibi her işlem veritabanına sorgu gönderir
* Kutucuklar saatte bir yenilenir (yenileme işleminin zamanlanması gerekmez). Bu, bağlantı kurulduktan sonra Gelişmiş ayarlar'da ayarlanabilir.
* Soru-Cevap, DirectQuery veri kümeleri için kullanılamaz
* Şema değişiklikleri otomatik olarak alınmaz

Bu kısıtlamalar ve notlar, biz deneyimleri iyileştirmeye devam ettikçe değişebilir. Bağlanma adımları aşağıda ayrıntılı şekilde verilmiştir.

> [!Important]
> Azure SQL Database ile bağlantımızı geliştirdik.  Azure SQL Database veri kaynağınıza en iyi bağlanma deneyimi için Power BI Desktop kullanın.  Modelinizi ve raporunuzu oluşturduktan sonra, bunu Power BI hizmetine yayımlayabilirsiniz.  Power BI hizmetindeki Azure SQL Database doğrudan bağlayıcısı artık kullanım dışı bırakılmıştır.

## <a name="power-bi-desktop-and-directquery"></a>Power BI Desktop ve DirectQuery

DirectQuery'yi kullanarak Azure SQL Veritabanı'na bağlanmak için Power BI Desktop'ı kullanmanız gerekir. Bu yaklaşım, daha fazla esneklik ve özellik sunar. Power BI Desktop kullanılarak oluşturulan raporlar daha sonra Power BI hizmetinde yayımlanabilir. Power BI Desktop'ta [DirectQuery'yi kullanarak Azure SQL Veritabanı](desktop-use-directquery.md)'na nasıl bağlanacağınızla ilgili daha fazla bilgi edinebilirsiniz.

## <a name="finding-parameter-values"></a>Parametre Değerlerini Bulma

Tam sunucu adınız ve veritabanınızın adı Azure portalda bulunabilir.

![Yeni Azure bağlantı noktası güncelleştirme](media/service-azure-sql-database-with-direct-connect/azureportnew_update.png)

![Azure portal güncelleştirmesi](media/service-azure-sql-database-with-direct-connect/azureportal_update.png)

[!INCLUDE [direct-query-sso](includes/direct-query-sso.md)]

## <a name="next-steps"></a>Sonraki adımlar

* [Power BI Desktop'ta DirectQuery'yi kullanma](desktop-use-directquery.md)  
* [Power BI nedir?](power-bi-overview.md)  
* [Power BI için veri alma](service-get-data.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)
