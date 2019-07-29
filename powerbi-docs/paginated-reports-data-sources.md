---
title: Power BI sayfalandırılmış raporları için desteklenen veri kaynakları
description: Bu makalede Power BI hizmetindeki sayfalandırılmış raporlar için desteklenen veri kaynaklarını ve Azure SQL Veritabanı veri kaynaklarına nasıl bağlanacağınızı öğreneceksiniz.
author: onegoodsausage
ms.author: andremi
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 07/19/2019
ms.openlocfilehash: f055cd27f25af399b63336e66aaad526ed740de2
ms.sourcegitcommit: 8aa90f662afb7492ffcfc11ef142cdb0ccecc9aa
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68462323"
---
# <a name="supported-data-sources-for-power-bi-paginated-reports"></a>Power BI sayfalandırılmış raporları için desteklenen veri kaynakları

Bu makalede Power BI hizmetindeki sayfalandırılmış raporlar için desteklenen veri kaynakları ve Azure SQL Veritabanı veri kaynaklarına nasıl bağlanılacağı açıklanır. Bazı veri kaynakları yerel olarak desteklenir. Diğerlerine veri ağ geçitleri yoluyla bağlanabilirsiniz.

## <a name="natively-supported-data-sources"></a>Yerel olarak desteklenen veri kaynakları

Sayfalandırılmış raporlar aşağıdaki veri kaynakları listesini yerel olarak destekler:

| Veri Kaynağı | Kimlik Doğrulama | Notlar |
| --- | --- | --- |
| Azure SQL Veritabanı <br>Azure SQL Veri Ambarı | Temel, çoklu oturum açma (SSO), OAuth2 |   |
| Azure Analysis Services | SSO, OAuth2 |   |
| Power BI veri kümesi | SSO | Premium ve Premium olmayan Power BI veri kümeleri |
| Premium Power BI veri kümesi (XMLA) | SSO |   |
| Veri Gir | YOK | Veriler rapora katıştırılmıştır. |

Siz raporu Power BI hizmetine yükledikten sonra Azure SQL Veritabanı dışındaki tüm veri kaynakları kullanıma hazırdır. Veri kaynakları uygulanabilir olduğunda varsayılan olarak çoklu oturum açmayı (SSO) kullanır. Azure Analysis Services için kimlik doğrulaması türünü OAuth2 olarak değiştirebilirsiniz.

Azure SQL Veritabanı veri kaynakları için, [Azure SQL Veritabanı Kimlik Doğrulaması](#azure-sql-database-authentication) bölümünde açıklandığı gibi daha fazla bilgi sağlamanız gerekir.

## <a name="other-data-sources"></a>Diğer veri kaynakları

Yukarıdaki yerel olarak desteklenen veri kaynaklarına ek olarak, aşağıdaki veri kaynaklarına da [Power BI veri ağ geçidi](service-gateway-onprem.md) yoluyla erişilebilir:

- SQL Server
- SQL Server Analysis Services
- Oracle
- Teradata

Sayfalandırılmış raporlar için şu anda Azure SQL Veritabanı'na ve Azure Analysis Services'e Power BI veri ağ geçidi üzerinden erişilemez.

## <a name="azure-sql-database-authentication"></a>Azure SQL Veritabanı kimlik doğrulaması

Azure SQL Veritabanı veri kaynakları için, raporu çalıştırmadan önce kimlik doğrulaması türünü ayarlamalısınız. Bu yalnızca çalışma alanında bir veri kaynağını ilk kez kullanırken geçerlidir. Bu ilk kullanımınızda aşağıdaki iletiyi görürsünüz:

![Power BI'da yayımlanıyor](media/paginated-reports-data-sources/power-bi-paginated-publishing.png)

Kimlik bilgilerini sağlamazsanız raporu çalıştırdığınızda hata oluşur. Yeni karşıya yüklediğiniz raporun **Veri kaynağı kimlik bilgileri** sayfasına gitmek için **Devam**'ı seçin:

![Azure SQL Veritabanı için ayarlar](media/paginated-reports-data-sources/power-bi-paginated-settings-azure-sql.png)

**Yapılandır** iletişim kutusunu görüntülemek için belirli bir veri kaynağının **Kimlik bilgilerini düzenle** bağlantısını seçin:

![Azure SQL Veritabanını Yapılandırma](media/paginated-reports-data-sources/power-bi-paginated-configure-azure-sql.png)

Azure SQL Veritabanı veri kaynakları için desteklenen kimlik doğrulaması türleri şunlardır:

- Temel (kullanıcı adı ve parola)
- SSO (çoklu oturum açma)
- OAuth2 (depolanmış AAD belirteci)

SSO ve OAuth2'nin doğru çalışması için veri kaynağının bağlantılı olduğu Azure SQL Veritabanı sunucusunda [AAD kimlik doğrulaması desteğinin etkinleştirilmiş](https://docs.microsoft.com/azure/sql-database/sql-database-aad-authentication-configure) olması gerekir. OAuth2 kimlik doğrulama yöntemi için AAD bir belirteç oluşturur ve bunu gelecekteki veri kaynağı erişimleri için depolar. Bunun yerine [SSO kimlik doğrulama yöntemini](https://docs.microsoft.com/power-bi/service-azure-sql-database-with-direct-connect#single-sign-on) kullanmak için, hemen altındaki SSO seçeneğini belirtin: **DirectQuery ile bu veri kaynağına erişirken, son kullanıcılar kendi OAuth2 kimlik bilgilerini kullanır**.
  
## <a name="next-steps"></a>Sonraki adımlar

[Power BI hizmetinde sayfalandırılmış rapor görüntüleme](paginated-reports-view-power-bi-service.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)
