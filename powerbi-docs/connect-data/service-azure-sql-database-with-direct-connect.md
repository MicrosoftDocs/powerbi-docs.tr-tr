---
title: DirectQuery ile Azure SQL Veritabanı
description: DirectQuery ile Azure SQL Veritabanı
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.custom: ''
ms.date: 04/28/2020
LocalizationGroup: Data from databases
ms.openlocfilehash: 038d18639639fa13250e44da141314e9a94fe412
ms.sourcegitcommit: 9350f994b7f18b0a52a2e9f8f8f8e472c342ea42
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90861924"
---
# <a name="azure-sql-database-with-directquery"></a>DirectQuery ile Azure SQL Veritabanı

Azure SQL Veritabanı'na doğrudan nasıl bağlanacağınızı ve canlı verilerin kullanıldığı raporları nasıl oluşturacağınızı öğrenin. Verilerinizi Power BI yerine kaynakta tutabilirsiniz.

DirectQuery ile, siz verileri rapor görünümünde araştırırken sorgular Azure SQL Varitabanınıza geri gönderilir. Bu deneyim, bağlandıkları veritabanlarına ve varlıklara aşina kullanıcılar için önerilir.

> [!Important]
> Bu açıklamada, Azure SQL veritabanının bir sanal ağın arkasında olmadığı veya etkin bir özel bağlantı uç noktasına sahip olduğu varsayılmıştır.

**Notlar:**

* Bağlanırken tam sunucu adını belirtin (daha fazla ayrıntı için aşağıya bakın).
* Veritabanı güvenlik duvarı kurallarının "[Azure hizmetlerine erişime izin ver](/azure/sql-database/sql-database-networkaccess-overview#allow-azure-services)" olarak yapılandırıldığından emin olun.
* Sütun seçme veya filtre ekleme gibi her işlem veritabanına sorgu gönderir.
* Kutucuklar saatte bir yenilenir (yenileme işleminin zamanlanması gerekmez). Bağlandığınızda Gelişmiş ayarlarda yenileme sıklığını ayarlayabilirsiniz.
* DirectQuery veri kümeleri için Soru-Cevap özelliği kullanılamaz.
* Şema değişiklikleri otomatik olarak alınmaz.

Bu kısıtlamalar ve notlar, biz deneyimleri iyileştirmeye devam ettikçe değişebilir. Bağlanma adımları aşağıda ayrıntılı şekilde verilmiştir.

> [!Important]
> Azure SQL Database ile bağlantımızı geliştirdik.  Azure SQL Database veri kaynağınıza en iyi bağlanma deneyimi için Power BI Desktop kullanın.  Modelinizi ve raporunuzu oluşturduktan sonra, bunu Power BI hizmetine yayımlayabilirsiniz.  Power BI hizmetindeki Azure SQL Database doğrudan bağlayıcısı artık kullanım dışı bırakılmıştır.

## <a name="power-bi-desktop-and-directquery"></a>Power BI Desktop ve DirectQuery

DirectQuery'yi kullanarak Azure SQL Veritabanı'na bağlanmak için Power BI Desktop kullanmanız gerekir. Bu yaklaşım, daha fazla esneklik ve özellik sunar. Power BI Desktop kullanılarak oluşturulan raporlar daha sonra Power BI hizmetinde yayımlanabilir. Power BI Desktop'ta [DirectQuery'yi kullanarak Azure SQL Veritabanı](desktop-use-directquery.md)'na nasıl bağlanacağınızla ilgili daha fazla bilgi edinebilirsiniz.

## <a name="find-parameter-values"></a>Parametre değerlerini bulma

Tam sunucu adınızı ve veritabanınızın adını Azure portalda bulabilirsiniz.

![Yeni Azure portalı güncelleştirmesi](media/service-azure-sql-database-with-direct-connect/azureportnew_update.png)

![Azure portal güncelleştirmesi](media/service-azure-sql-database-with-direct-connect/azureportal_update.png)

[!INCLUDE [direct-query-sso](../includes/direct-query-sso.md)]

## <a name="next-steps"></a>Sonraki adımlar

* [Power BI Desktop'ta DirectQuery'yi kullanma](desktop-use-directquery.md)  
* [Power BI nedir?](../fundamentals/power-bi-overview.md)  
* [Power BI için veri alma](service-get-data.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu'nu deneyin](https://community.powerbi.com/)