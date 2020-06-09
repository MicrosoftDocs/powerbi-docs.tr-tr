---
title: DirectQuery ile Azure SQL Veri Ambarı
description: DirectQuery ile Azure SQL Veri Ambarı
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.custom: ''
ms.date: 06/03/2020
LocalizationGroup: Data from databases
ms.openlocfilehash: cde97805519a800fc98668cb523db92f0276b06d
ms.sourcegitcommit: f05f7b0112a8ec2dce60839ea5f922eda3cc776c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/03/2020
ms.locfileid: "84336992"
---
# <a name="azure-sql-data-warehouse-with-directquery"></a>DirectQuery ile Azure SQL Veri Ambarı

DirectQuery ile Azure SQL Veri Ambarı, Azure SQL Veri Ambarı'ndaki hazır verilerinizi ve ölçümlerinizi temel alan dinamik raporlar oluşturmanızı sağlar. DirectQuery ile, siz verileri keşfederken sorgular Azure SQL Veri Ambarı'nıza gerçek zamanlı olarak geri gönderilir. Gerçek zamanlı sorgular, SQL Veri Ambarı’nın ölçeğiyle birleştirildiğinde kullanıcıların terabaytlarca veriden birkaç dakika içinde dinamik rapor oluşturmasını sağlar. Ayrıca **Panolar ve raporlar oluşturun** bağlantısı, kullanıcıların SQL Veri Ambarları’nı kullanarak Power BI raporları oluşturmalarına olanak verir.

SQL Veri Ambarı bağlayıcısını kullanırken:

* Bağlanırken tam sunucu adını belirtin (ayrıntılar için aşağıya bakın)
* Sunucu güvenlik duvarı kurallarının "Azure hizmetlerine erişime izin ver" şeklinde yapılandırıldığından emin olun
* Sütun seçme veya filtre ekleme gibi her işlem, veri ambarına doğrudan sorgu gönderir
* Kutucuklar yaklaşık olarak 15 dakikada bir yenilenecek şekilde ayarlanmıştır ve yenileme işleminin zamanlanması gerekmez.  Yenileme özelliği, bağlantı kurulduktan sonra Gelişmiş ayarlar’da ayarlanabilir.
* DirectQuery veri kümeleri için Soru-Cevap özelliği kullanılamaz
* Şema değişiklikleri otomatik olarak alınmaz

Bu kısıtlamalar ve notlar, biz deneyimi iyileştirmeye devam ettikçe değişebilir. Bağlanma adımları aşağıda ayrıntılı şekilde verilmiştir.

## <a name="build-dashboards-and-reports-in-power-bi"></a>Power BI’da panolar ve raporlar oluşturma

> [!Important]
> Azure SQL Veri Ambarı ile bağlantımızı geliştirdik. Azure SQL Veri Ambarı veri kaynağınıza en iyi bağlanma deneyimi için Power BI Desktop kullanın. Modelinizi ve raporunuzu oluşturduktan sonra, bunu Power BI hizmetine yayımlayabilirsiniz. Power BI hizmetindeki Azure SQL Veri Ambarı’na yönelik önceki doğrudan bağlayıcı artık kullanılamıyor.

SQL Veri Ambarınız ve Power BI arasında veri alışverişi yapmanın en kolay yolu, Power BI Desktop’ta raporlar oluşturmaktır. Azure portalındaki **Panolar ve raporlar oluşturun** düğmesini kullanabilirsiniz.

1. Kullanmaya başlamak için Power BI Desktop’ı indirip yükleyin. İndirme ve yükleme hakkında bilgi almak için [Power BI Desktop’ı edinin](../fundamentals/desktop-get-the-desktop.md) makalesine bakın veya doğrudan sonraki adıma geçin.

2. Power BI Desktop’ı indirmek için **Panolar ve raporlar oluşturun** bağlantısına da tıklayabilirsiniz.

    ![Power BI’da aç](media/service-azure-sql-data-warehouse-with-direct-connect/create-reports-01.png)


## <a name="connecting-through-power-bi-desktop"></a>Power BI Desktop aracılığıyla bağlanma

Power BI Desktop’taki **Veri Al** düğmesini kullanarak bir SQL Veri Ambarı’na bağlanabilirsiniz. 

1. **Giriş** menüsünden **Veri Al**’ı seçin.  

    ![Veri al düğmesi](media/service-azure-sql-data-warehouse-with-direct-connect/create-reports-02.png)

2. Tüm kullanılabilir veri kaynaklarını görmek için **Daha fazla...** seçeneğini belirleyin. Görüntülenen pencerede soldaki bölmeden **Azure**’ı, sağdaki bölmede yer alan kullanılabilir bağlayıcılar listesinden **Azure SQL Veri Ambarı**’nı seçin.

    ![Azure veri kaynakları](media/service-azure-sql-data-warehouse-with-direct-connect/create-reports-03.png)

3. Görüntülenen pencerede sunucunuzu ve isteğe bağlı olarak bağlanmak istediğiniz veritabanını girin. Veri bağlantısı modunuzu da seçebilirsiniz: İçeri aktarma veya DirectQuery. Azure SQL Veri Ambarınızdaki bilgilere gerçek zamanlı bir şekilde erişmek için DirectQuery’yi kullanın.

    ![Doğrudan bağlantı ile Azure SQL DW](media/service-azure-sql-data-warehouse-with-direct-connect/create-reports-04.png)

4. Azure SQL Veri Ambarı bağlantısına yönelik gelişmiş seçenekler için, bağlantınıza ilişkin ek seçenekleri görüntülemek üzere **Gelişmiş seçeneklerin** yanındaki aşağı oku seçin.

    ![Sunucu adı](media/service-azure-sql-data-warehouse-with-direct-connect/create-reports-05.png)

Sonraki bölümde, bağlantınıza yönelik parametre değerlerini nasıl bulacağınız açıklanmaktadır. 

## <a name="finding-parameter-values"></a>Parametre Değerlerini Bulma

Tam sunucu adınız ve veritabanınızın adı Azure portalda bulunabilir. SQL Veri Ambarı’nın şu anda yalnızca Azure portalında bulunduğunu unutmayın.

![Azure portalı](media/service-azure-sql-data-warehouse-with-direct-connect/azureportal.png)

> [!NOTE]
> Power BI kiracınız Azure SQL Veri Ambarı ile aynı bölgedeyse çıkış ücreti uygulanmaz. [Bu yönergeleri](https://docs.microsoft.com/power-bi/service-admin-where-is-my-tenant-located) kullanarak Power BI kiracınızın bulunduğu yeri belirleyebilirsiniz.

[!INCLUDE [direct-query-sso](../includes/direct-query-sso.md)]

## <a name="next-steps"></a>Sonraki adımlar

* [Power BI'da DirectQuery kullanma hakkında](desktop-directquery-about.md)
* [Power BI nedir?](../fundamentals/power-bi-overview.md)  
* [Power BI için veri alma](service-get-data.md)  
* [Azure SQL Veri Ambarı](/azure/sql-data-warehouse/sql-data-warehouse-overview-what-is/)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)
