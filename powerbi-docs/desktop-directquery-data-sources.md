---
title: Power BI'da DirectQuery tarafından desteklenen veri kaynakları
description: Hangi veri kaynaklarında DirectQuery'nin kullanabildiğini gösteren listeyi edinin.
author: davidiseminger
ms.author: davidi
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 09/04/2019
LocalizationGroup: Connect to data
ms.openlocfilehash: 75b7a606e588ca7f6d1393c5b6e0dd9041f6d63e
ms.sourcegitcommit: b7a9862b6da940ddebe61bc945a353f91cd0e4bd
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71945193"
---
# <a name="data-sources-supported-by-directquery-in-power-bi"></a>Power BI'da DirectQuery tarafından desteklenen veri kaynakları

**Power BI Desktop** ve **Power BI hizmeti**, bağlanıp verilere erişebileceğiniz pek çok veri kaynağına sahiptir. Bu makalede hangi Power BI kaynaklarının **DirectQuery** olarak bilinen bağlantı yöntemini desteklediği açıklanmaktadır. DirectQuery hakkında daha fazla bilgi için [**Power BI'da DirectQuery**](desktop-directquery-about.md) başlıklı makaleye bakın.

Aşağıdaki veri kaynakları, Power BI'da DirectQuery'yi desteklemektedir:

* Amazon Redshift
* AtScale (Beta)
* Azure Veri Gezgini
* Azure HDInsight Spark
* [Azure SQL Veritabanı](service-azure-sql-database-with-direct-connect.md)
* [Azure SQL Veri Ambarı](service-azure-sql-data-warehouse-with-direct-connect.md)
* Denodo
* Google BigQuery
* HDInsight Etkileşimli Sorgu
* IBM DB2 (Microsoft Sağlayıcısı))
* IBM Netezza
* Impala (2.x sürümü)
* MarkLogic
* Oracle Database (12 ve sonraki sürümler)
* Oracle Essbase
* PostgreSQL
* SAP Business Warehouse Uygulama Sunucusu
* SAP Business Warehouse İleti Sunucusu
* SAP HANA
* Snowflake
* Spark (sürüm 0.9 ve üzeri)
* SQL Server
* Teradata
* Vertica

Adının yanında **(Beta)** veya **(Önizleme)** bulunan veri kaynakları, değişikliğe tabidir ve üretim ortamında kullanımları desteklenmez. Ayrıca bunlar, **Power BI hizmetinde** yayımlanan raporlarda da desteklenmeyebilir. Bu, yayımlanmış bir raporu açma veya veri kümesini araştırma işlemlerinin hatayla sonuçlanabileceği anlamına gelir.

**(Beta)** ile **(Önizleme)** veri kaynakları arasındaki tek fark, **(Önizleme)** kaynaklarının yalnızca Önizleme özelliği olarak etkinleştirildikten sonra kullanılabilmesidir. Bir **(Önizleme)** veri bağlayıcısını etkinleştirmek için **Power BI Desktop**'ta **Dosya > Seçenekler ve Ayarlar > Seçenekler** adımlarını izleyin ve ardından **Önizleme özellikleri** seçeneğini belirleyin.

> [!NOTE]
> SQL Server’a yönelik DirectQuery sorguları, erişimi oluşturmak için geçerli Windows kimlik doğrulaması kimlik bilgileri veya veritabanı kimlik bilgileri kullanılarak kimlik doğrulaması yapmayı gerektirir. Alternatif kimlik bilgileri desteklenmez.
>

## <a name="on-premises-gateway-requirements"></a>Şirket içi ağ geçidi gereksinimleri
Aşağıdaki tabloda, **Power BI hizmetinde** bir rapor yayımladıktan sonra, belirtilen veri kaynağına bağlanmak için bir **şirket içi veri ağ geçidi** gerekip gerekmediği açıklanmaktadır.

| Kaynak | Ağ geçidi gerekli mi? |
| --- | --- |
| Amazon Redshift |Hayır |
| Azure HDInsight Spark (Beta) |Hayır |
| Azure SQL Veritabanı |Hayır |
| Azure SQL Veri Ambarı |Hayır |
| Google BigQuery |Hayır |
| IBM Netezza |Evet |
| IBM DB2 (IBM Sağlayıcısı) |Evet |
| IBM DB2 (Microsoft Sağlayıcısı) |Hayır |
| IBM Informix Veritabanı |Hayır |
| Impala (2.x sürümü) |Evet |
| MySQL |Evet |
| ODBC |Evet |
| Oracle Database |Evet |
| PostgreSQL |Evet |
| SAP Business Warehouse Uygulama Sunucusu |Evet |
| SAP Business Warehouse İleti Sunucusu |**Power BI hizmetinde** henüz desteklenmiyor |
| SAP HANA |Evet |
| Snowflake |Evet |
| Spark (Beta), 0.9 ve sonraki sürümler |Evet |
| SQL Server |Evet |
| Sybase |Evet |
| Teradata |Evet |
| Vertica |Evet |


## <a name="single-sign-on-sso-for-directquery-sources"></a>DirectQuery kaynakları için çoklu oturum açma (SSO)

SSO seçeneği etkinleştirildiğinde ve kullanıcılarınız veri kaynağının üstünde derlenen raporlara eriştiğinde, Power BI, kimliği doğrulanmış sorgulardaki Azure AD kimlik bilgilerini temel alınan veri kaynağı gönderir. Bu sayede Power BI, veri kaynağı seviyesinde yapılandırılmış olan güvenlik ayarlarını uygular.

SSO seçeneği bu veri kaynağını kullanan tüm veri kümelerinde geçerli olur. İçeri aktarma senaryoları için kullanılan kimlik doğrulama yöntemini etkilemez. Aşağıdaki veri kaynakları, DirectQuery aracılığıyla bağlantılar için SSO destekler:

- Azure SQL Veritabanı
- Azure SQL Veri Ambarı
- Impala
- SAP HANA
- SAP BW
- Spark
- SQL Server
- Teradata

> [!Note]
> Azure Multi-Factor Authentication (MFA) desteklenmiyor. DirectQuery ile SSO kullanmak isteyen kullanıcılar MFA'den muaf tutulmalıdır.

## <a name="next-steps"></a>Sonraki adımlar
DirectQuery hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

* [Power BI'da DirectQuery](desktop-directquery-about.md)
* [DirectQuery ve SAP HANA](desktop-directquery-sap-hana.md)
* [DirectQuery ve SAP BW](desktop-directquery-sap-bw.md)
* [Şirket içi veri ağ geçidi](service-gateway-onprem.md)

