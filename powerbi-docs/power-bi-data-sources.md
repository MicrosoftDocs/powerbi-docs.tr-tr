---
title: Power BI veri kaynakları
description: Bu makalede, DirectQuery ve şirket içi veri ağ geçidi hakkındaki bilgiler de dahil olmak üzere Power BI’ın desteklediği veri kaynakları listelenir.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 03/10/2020
ms.author: kfollis
ms.openlocfilehash: 1853e710958b5bed0dad011594d9e04ccc99842d
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "79041689"
---
# <a name="power-bi-data-sources"></a>Power BI veri kaynakları

Aşağıdaki tabloda, DirectQuery ve şirket içi veri ağ geçidi hakkındaki bilgiler de dahil olmak üzere Power BI’ın veri kümeleri için desteklediği veri kaynakları gösterilir. Veri akışları hakkında bilgi için bkz. [Power BI veri akışları için veri kaynaklarına bağlanma](service-dataflows-data-sources.md).

> [!NOTE]
> Birçok Power BI Desktop veri bağlayıcısı, kimlik doğrulaması için Internet Explorer 10 (veya daha yeni bir sürümü) uygulamasına ihtiyaç duyar. 


| Veri kaynağı | Masaüstünden bağlanma | Hizmetten bağlanma ve yenileme | DirectQuery / Canlı bağlantı | Ağ Geçidi (desteklenen) | Ağ Geçidi (gerekli) |
|---|---|---|---|---|---|---|---|
| Access veritabanı | Evet | Evet | Hayır | Evet <sup>1</sup> | Evet |
| ActiveDirectory | Evet | Evet | Hayır | Evet | Evet |
| Adobe Analytics | Evet | Evet | Hayır | Hayır | Hayır |
| Amazon Redshift | Evet | Evet | Evet | Evet | Hayır |
| appFigures | Evet | Evet | Hayır | Hayır | Hayır |
| AtScale küpleri | Evet | Evet | Evet | Evet | Hayır |
| Azure Analysis Services | Evet | Evet | Evet | Evet <sup>2</sup> | Hayır |
| Azure Blob Depolama Alanı | Evet | Evet | Hayır | Evet | Hayır |
| Azure Cosmos DB | Evet | Evet | Hayır | Hayır | Hayır |
| Azure Maliyet Yönetimi | Evet | Evet | Hayır | Hayır | Hayır |
| Azure Veri Gezgini (kusto) | Evet | Evet | Evet | Hayır | Hayır |
| Azure Data Lake Storage Gen1 | Evet | Evet | Hayır | Hayır | Hayır |
| Azure Data Lake Storage Gen2 | Evet | Evet | Hayır | Evet | Hayır |
| Azure DevOps | Evet | Evet | Hayır | Hayır | Hayır |
| Azure DevOps Server | Evet | Evet | Hayır | Evet | Evet |
| Azure HDInsight (HDFS) | Evet | Evet | Hayır | Hayır | Hayır |
| Azure HDInsight Spark | Evet | Evet | Evet | Hayır | Hayır |
| Azure SQL Veritabanı | Evet | Evet | Evet | Evet <sup>2</sup> | Hayır |
| Azure SQL Veri Ambarı | Evet | Evet | Evet | Evet <sup>2</sup> | Hayır |
| Azure Tablo Depolama | Evet | Evet | Hayır | Evet | Hayır |
| BI Bağlayıcısı | Evet | Evet | Evet | Evet | Evet |
| BI360 - Budgeting & Financial Reporting | Evet | Evet | Hayır | Hayır | Hayır |
| Common Data Service | Evet | Evet | Hayır | Hayır | Hayır |
| Data.World - Veri Kümesi Al | Evet | Evet | Hayır | Hayır | Hayır |
| Denodo | Evet | Evet | Evet | Evet | Evet |
| Dremio | Evet | Evet | Evet | Evet | Evet |
| Dynamics 365 (Çevrimiçi) | Evet | Evet | Hayır | Hayır | Hayır |
| Dynamics 365 Business Central | Evet | Evet | Hayır | Hayır | Hayır |
| Dynamics 365 Business Central (şirket içi) | Evet | Evet | Hayır | Hayır | Hayır |
| Dynamics 365 Customer Insights | Evet | Evet | Hayır | Hayır | Hayır |
| Dynamics NAV | Evet | Evet | Hayır | Hayır | Hayır |
| Emigo Data Source | Evet | Evet | Hayır | Hayır | Hayır |
| Entersoft Business Suite | Evet | Evet | Hayır | Hayır | Hayır |
| Essbase | Evet | Evet | Evet | Evet | Evet |
| Exasol | Evet | Evet | Evet | Evet | Evet |
| Excel | Evet <sup>3</sup> | Evet <sup>3</sup> | Hayır | Evet <sup>3</sup> | Hayır <sup>4</sup> |
| Facebook | Evet | Evet | Hayır | Hayır | Hayır |
| Dosya | Evet | Evet | Hayır | Evet | Evet |
| Klasör | Evet | Evet | Hayır | Evet | Evet |
| GitHub | Evet | Evet | Hayır | Hayır | Hayır |
| Google Analytics | Evet | Evet | Hayır | Hayır | Hayır |
| Google BigQuery | Evet | Evet | Hayır | Hayır | Hayır |
| Hadoop Dosyası (HDFS) | Evet | Hayır | Hayır | Hayır | Hayır |
| HDInsight Etkileşimli Sorgu | Evet | Evet | Evet | Hayır | Hayır |
| IBM DB2 | Evet | Evet | Evet | Evet | Hayır |
| IBM Informix Veritabanı | Evet | Evet | Hayır | Evet | Hayır |
| IBM Netezza | Evet | Evet | Evet | Evet | Evet |
| Impala | Evet | Evet | Evet | Evet | Evet |
| Indexima | Evet | Evet | Evet | Evet | Evet |
| Industrial App Store | Evet | Evet | Hayır | Hayır | Hayır |
| Information Grid | Evet | Evet | Hayır | Hayır | Hayır |
| Intersystems IRIS | Evet | Evet | Evet | Evet | Evet |
| Intune Veri Ambarı | Evet | Evet | Hayır | Hayır | Hayır |
| Jethro ODBC | Evet | Evet | Evet | Evet | Evet |
| JSON | Evet | Evet | Hayır | Evet** | Hayır <sup>4</sup> |
| Kyligence Enterprise | Evet | Evet | Evet | Evet | Evet |
| MailChimp | Evet | Evet | Hayır | Hayır | Hayır |
| Marketo | Evet | Evet | Hayır | Hayır | Hayır |
| MarkLogic ODBC | Evet | Evet | Evet | Evet | Evet |
| Microsoft Azure Tüketim Öngörüleri | Evet | Evet | Hayır | Hayır | Hayır |
| Microsoft Exchange | Evet | Evet | Hayır | Evet | Hayır |
| Microsoft Exchange Online | Evet | Evet | Hayır | Hayır | Hayır |
| Microsoft Graph Güvenliği | Evet | Evet | Hayır | Evet | Hayır |
| Mixpanel | Evet | Evet | Hayır | Hayır | Hayır |
| MySQL | Evet | Evet | Hayır | Evet | Evet |
| OData | Evet | Evet | Hayır | Evet | Hayır |
| ODBC | Evet | Evet | Hayır | Evet | Evet |
| OleDb | Evet | Evet | Hayır | Evet | Evet |
| Oracle | Evet | Evet | Evet | Evet | Evet |
| Paxata | Evet | Evet | Hayır | Evet | Hayır |
| PDF | Evet | Evet | Hayır | Evet | Hayır <sup>4</sup> |
| Planview Enterprise One - CTM | Evet | Evet | Hayır | Hayır | Hayır |
| Planview Enterprise One - PRM | Evet | Evet | Hayır | Hayır | Hayır |
| Planview Projectplace | Evet | Evet | Hayır | Hayır | Hayır |
| PostgreSQL | Evet | Evet | Evet | Evet | Hayır |
| Power BI veri akışları | Evet | Evet | Hayır | Hayır | Hayır |
| Power BI veri kümeleri | Evet | Evet | Evet | Hayır | Hayır |
| Power Platform veri akışları | Evet | Evet | Hayır | Hayır | Hayır |
| Python betiği | Evet | Evet <sup>5</sup> | Hayır | Evet <sup>5</sup> | Evet |
| QubolePresto | Evet | Evet | Evet | Evet | Evet |
| Quick Base | Evet | Evet | Hayır | Evet | Evet |
| QuickBooks Online | Evet | Evet | Hayır | Hayır | Hayır |
| R betiği | Evet | Evet <sup>5</sup> | Hayır | Evet <sup>5</sup> | Hayır |
| Roamler | Evet | Evet | Hayır | Evet | Hayır |
| Salesforce Nesneleri | Evet | Evet | Hayır | Hayır | Hayır |
| Salesforce Raporları | Evet | Evet | Hayır | Hayır | Hayır |
| SAP Business Warehouse İleti Sunucusu | Evet | Evet | Evet | Evet | Evet |
| SAP Business Warehouse Sunucusu | Evet | Evet | Evet | Evet | Evet |
| SAP HANA | Evet | Evet | Evet | Evet | Evet |
| SharePoint Klasörü | Evet | Evet | Hayır | Evet | Hayır <sup>4</sup> |
| SharePoint Listesi | Evet | Evet | Hayır | Evet | Hayır <sup>4</sup> |
| SharePoint Online Listesi | Evet | Evet | Hayır | Evet <sup>2</sup> | Hayır |
| Smartsheet | Evet | Evet | Hayır | Hayır | Hayır |
| Snowflake | Evet | Evet | Evet | Evet | Hayır |
| Spark | Evet | Evet | Evet | Evet | Hayır |
| SparkPost | Evet | Evet | Hayır | Hayır | Hayır |
| SQL Server | Evet | Evet | Evet | Evet | Evet |
| SQL Server Analysis Services | Evet | Evet | Evet | Evet | Evet |
| Stripe | Evet | Evet | Hayır | Hayır | Hayır |
| SurveyMonkey | Evet | Evet | Hayır | Evet | Hayır |
| SweetIQ | Evet | Evet | Hayır | Hayır | Hayır |
| Sybase | Evet | Evet | Hayır | Evet | Evet |
| TeamDesk | Evet | Evet | Hayır | Evet | Hayır |
| Tenforce | Evet | Evet | Hayır | Hayır | Hayır |
| Teradata | Evet | Evet | Evet | Evet | Evet |
| Metin/CSV | Evet | Evet | Hayır | Evet | Hayır <sup>4</sup> |
| Twilio | Evet | Evet | Hayır | Hayır | Hayır |
| tyGraph | Evet | Evet | Hayır | Hayır | Hayır |
| Vertica | Evet | Evet | Evet | Evet | Evet |
| Web | Evet | Evet | Hayır | Evet | Evet <sup>6</sup> |
| Webtrends | Evet | Evet | Hayır | Hayır | Hayır |
| Workforce Dimensions | Evet | Evet | Hayır | Evet | Hayır |
| XML | Evet | Evet | Hayır | Evet | Hayır <sup>4</sup> |
| Zendesk | Evet | Evet | Hayır | Hayır | Hayır |
| | | | | | | | |

<sup>1</sup>[ACE OLEDB sağlayıcısı](https://www.microsoft.com/download/details.aspx?id=54920) ile desteklenir, ağ geçidiyle aynı makineye yüklenir.

<sup>2</sup> Şirket içi sürümüyle aynı M işleviyle desteklenir ve Kimlik Doğrulama seçeneklerinin kısıtlanmasına neden olur (ağ geçidinin OAuth desteği yoktur).

<sup>3</sup> Excel 1997-2003 dosyaları (.xls) [ACE OLEDB sağlayıcısını](https://www.microsoft.com/download/details.aspx?id=54920) gerektirir.

<sup>4</sup> Teknolojinin şirket içi sürümü için gereklidir.

<sup>5</sup> Yalnızca [kişisel ağ geçidiyle](service-gateway-personal-mode.md) desteklenir.

<sup>6</sup> .html, .xls ve Access Veritabanları için gereklidir

## <a name="single-sign-on-sso-for-directquery-sources"></a>DirectQuery kaynakları için çoklu oturum açma (SSO)

SSO seçeneği etkinleştirildiğinde ve kullanıcılarınız veri kaynağının üstünde derlenen raporlara eriştiğinde, Power BI, kimliği doğrulanmış sorgulardaki Azure AD kimlik bilgilerini temel alınan veri kaynağı gönderir. Bu sayede Power BI, veri kaynağı seviyesinde yapılandırılmış olan güvenlik ayarlarını uygular.
SSO seçeneği bu veri kaynağını kullanan tüm veri kümelerinde geçerli olur. İçeri aktarma senaryoları için kullanılan kimlik doğrulama yöntemini etkilemez. Aşağıdaki veri kaynakları, DirectQuery aracılığıyla bağlantılar için SSO destekler:

- Azure SQL Veritabanı
- Azure SQL Veri Ambarı
- Impala
- SAP HANA
- SAP BW
- SAP BW İleti Sunucusu
- Snowflake
- Spark
- SQL Server
- Teradata

> [!Note]
> Azure Multi-Factor Authentication (MFA) desteklenmiyor. DirectQuery ile SSO kullanmak isteyen kullanıcılar MFA'den muaf tutulmalıdır.

## <a name="next-steps"></a>Sonraki adımlar

[Power BI Desktop'ta verilere bağlanma](desktop-quickstart-connect-to-data.md)  
[Power BI'da DirectQuery kullanma](desktop-directquery-about.md)  
[Power BI'da SQL Server Analysis Services canlı verileri](sql-server-analysis-services-tabular-data.md)  
[Şirket içi veri ağ geçidi nedir?](service-gateway-onprem.md)  
