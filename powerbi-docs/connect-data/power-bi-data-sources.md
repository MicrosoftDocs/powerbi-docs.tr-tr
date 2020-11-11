---
title: Power BI veri kaynakları
description: Bu makalede, DirectQuery ve şirket içi veri ağ geçidi hakkındaki bilgiler de dahil olmak üzere Power BI’ın desteklediği veri kaynakları listelenir.
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 10/07/2020
ms.author: davidi
ms.openlocfilehash: 3cce51ad577c700a0f9595a2b92694e5e1b61cc5
ms.sourcegitcommit: 37bd34053557089c4fbf0e05f78e959609966561
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94397404"
---
# <a name="power-bi-data-sources"></a>Power BI veri kaynakları

Aşağıdaki tabloda, DirectQuery ve şirket içi veri ağ geçidi hakkındaki bilgiler de dahil olmak üzere Power BI’ın veri kümeleri için desteklediği veri kaynakları gösterilir. Veri akışları hakkında bilgi için bkz. [Power BI veri akışları için veri kaynaklarına bağlanma](../transform-model/dataflows/dataflows-configure-consume.md).

| Veri kaynağı | Masaüstünden bağlanma | Hizmetten bağlanma ve yenileme | DirectQuery / Canlı bağlantı | Ağ Geçidi (desteklenen) | Ağ Geçidi (gerekli) | Power BI Veri Akışları |
|---|---|---|---|---|---|---|---|
| Access veritabanı | Evet | Evet | Hayır | Evet <sup>1</sup> | Evet | Evet |
| ActiveDirectory | Evet | Yes | Hayır | Evet | Evet | Evet |
| Adobe Analytics | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| Amazon Redshift | Evet | Evet | Evet | Evet | Hayır | Evet |
| appFigures | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| AtScale küpleri | Evet | Evet | Evet | Evet | Hayır | Hayır |
| Azure Analysis Services | Evet | Evet | Yes | Hayır | Hayır | Hayır |
| Azure Blob Depolama Alanı | Evet | Evet | Hayır | Evet | Hayır | Evet |
| Azure Cosmos DB | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| Azure Maliyet Yönetimi | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| Azure Veri Gezgini (kusto) | Evet | Evet | Evet | Evet | Hayır | Evet |
| Azure Data Lake Storage 1. Nesil | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| Azure Data Lake Storage Gen2 | Evet | Evet | Hayır | Evet | Hayır | Evet |
| Azure DevOps | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| Azure DevOps Server | Evet | Evet | Hayır | Evet | Evet | Hayır |
| Azure HDInsight (HDFS) | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| Azure HDInsight Spark | Evet | Evet | Evet | Hayır | Hayır | Evet |
| Azure SQL Veritabanı | Evet | Evet | Evet | Evet | Hayır | Evet |
| Azure SQL Veri Ambarı | Evet | Evet | Evet | Evet | Hayır | Evet |
| Azure Tablo Depolama | Evet | Evet | Hayır | Evet | Hayır | Evet |
| BI Bağlayıcısı | Evet | Evet | Evet | Evet | Evet | Hayır |
| BI360 - Budgeting & Financial Reporting | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| Common Data Service | Evet | Evet | Hayır | Hayır | Hayır | Evet |
| Data.World - Veri Kümesi Al | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| Denodo | Evet | Evet | Evet | Evet | Evet | Hayır |
| Dremio | Evet | Evet | Evet | Evet | Evet | Hayır |
| Dynamics 365 (çevrimiçi) | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| Dynamics 365 Business Central | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| Dynamics 365 Business Central (şirket içi) | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| Dynamics 365 Customer Insights | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| Dynamics NAV | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| Emigo Data Source | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| Entersoft Business Suite | Yes | Evet | Hayır | Hayır | Hayır | Hayır |
| Essbase | Evet | Evet | Evet | Evet | Evet | Hayır |
| Exasol | Evet | Evet | Evet | Evet | Evet | Hayır |
| Excel | Evet <sup>3</sup> | Evet <sup>3</sup> | Hayır | Evet <sup>3</sup> | Hayır <sup>4</sup> | Evet |
| Facebook | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| Dosya | Evet | Evet | Hayır | Evet | Evet | Evet |
| Klasör | Evet | Evet | Hayır | Evet | Evet | Evet |
| GitHub | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| Google Analytics | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| Google BigQuery | Evet | Evet | Evet | Hayır | Hayır | Evet |
| Hadoop Dosyası (HDFS) | Evet | Hayır | Hayır | Hayır | Hayır | Hayır |
| Hive LLAP | Evet | Evet | Evet | Evet | Hayır | Hayır |
| HDInsight Etkileşimli Sorgu | Evet | Evet | Evet | Hayır | Hayır | Hayır |
| IBM DB2 | Evet | Evet | Evet | Evet | Hayır | Evet |
| IBM Informix Veritabanı | Evet | Evet | Hayır | Evet | Hayır | Hayır |
| IBM Netezza | Evet | Evet | Evet | Evet | Evet | Hayır |
| Impala | Evet | Evet | Evet | Evet | Evet | Evet |
| Indexima | Evet | Evet | Evet | Evet | Evet | Hayır |
| Industrial App Store | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| Information Grid | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| Intersystems IRIS | Evet | Evet | Evet | Evet | Evet | Hayır |
| Intune Veri Ambarı | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| Jethro ODBC | Evet | Evet | Evet | Evet | Evet | Hayır |
| JSON | Evet | Yes | Hayır | Evet** | Hayır <sup>4</sup> | Evet |
| Kyligence Enterprise | Yes | Evet | Evet | Evet | Evet | Hayır |
| MailChimp | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| Marketo | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| MarkLogic ODBC | Evet | Evet | Evet | Evet | Evet | Hayır |
| Microsoft Azure Consumption Insights | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| Microsoft Exchange | Evet | Evet | Hayır | Evet | Hayır | Hayır |
| Microsoft Exchange Online | Evet | Evet | Hayır | Hayır | Hayır | Evet |
| Microsoft Graph Güvenliği | Evet | Evet | Hayır | Evet | Hayır | Hayır |
| Mixpanel | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| MySQL | Evet | Evet | Hayır | Evet | Evet | Evet |
| OData | Evet | Evet <sup>7</sup> | Hayır | Evet | Hayır | Evet |
| ODBC | Evet | Evet | Hayır | Evet | Evet | Evet |
| OleDb | Evet | Evet | Hayır | Evet | Evet | Hayır |
| Oracle | Evet | Evet | Evet | Evet | Evet | Evet |
| Paxata <sup>8</sup> | Evet | Evet | Hayır | Evet | Hayır | Hayır |
| PDF | Evet | Evet | Hayır | Evet | Hayır <sup>4</sup> | Evet |
| Planview Enterprise One - CTM | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| Planview Enterprise One - PRM | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| Planview Projectplace | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| PostgreSQL | Evet | Evet | Evet | Evet | Hayır | Evet |
| Power BI veri akışları | Evet | Evet | Hayır | Hayır | Hayır | Evet |
| Power BI veri kümeleri | Evet | Evet | Evet | Hayır | Hayır | Hayır |
| Power Platform veri akışları | Evet | Evet | Hayır | Hayır | Hayır | Evet |
| Python betiği | Evet | Evet <sup>5</sup> | Hayır | Evet <sup>5</sup> | Evet | Hayır |
| QubolePresto | Evet | Evet | Evet | Evet | Evet | Hayır |
| Quick Base | Evet | Evet | Hayır | Evet | Evet | Hayır |
| QuickBooks Online | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| R betiği | Evet | Evet <sup>5</sup> | Hayır | Evet <sup>5</sup> | Hayır | Hayır |
| Roamler | Evet | Evet | Hayır | Evet | Hayır | Hayır |
| Salesforce Nesneleri | Evet | Yes | Hayır | Hayır | Hayır | Evet |
| Salesforce Raporları | Evet | Evet | Hayır | Hayır | Hayır | Evet |
| SAP Business Warehouse İleti Sunucusu | Evet | Evet | Evet | Evet | Evet | Yes |
| SAP Business Warehouse Sunucusu | Evet | Evet | Evet | Evet | Evet | Evet |
| SAP HANA | Evet | Evet | Evet | Evet | Evet | Evet |
| SharePoint Klasörü | Evet | Evet | Hayır | Evet | Hayır <sup>4</sup> | Evet |
| SharePoint Listesi | Evet | Evet | Hayır | Evet | Hayır <sup>4</sup> | Evet |
| SharePoint Online Listesi | Evet | Evet | Hayır | Evet | Hayır | Evet |
| Smartsheet | Evet | Evet | Hayır | Hayır | Hayır | Evet |
| Snowflake | Evet | Evet | Evet | Evet | Hayır | Evet |
| Spark | Evet | Evet | Evet | Evet | Hayır | Evet |
| SparkPost | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| SQL Server | Evet | Evet | Evet | Evet | Evet | Evet |
| SQL Server Analysis Services | Evet | Evet | Evet | Evet | Evet | Hayır |
| Stripe | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| SurveyMonkey | Evet | Evet | Hayır | Evet | Hayır | Hayır |
| SweetIQ | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| Sybase | Evet | Evet | Hayır | Evet | Evet | Evet |
| TeamDesk | Evet | Evet | Hayır | Evet | Hayır | Hayır |
| Tenforce | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| Teradata | Evet | Evet | Evet | Evet | Evet | Evet |
| Metin/CSV | Evet | Evet | Hayır | Evet | Hayır <sup>4</sup> | Evet |
| Twilio | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| tyGraph | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| Vertica | Evet | Evet | Evet | Evet | Evet | Evet |
| Web | Evet | Evet | Hayır | Evet | Evet <sup>6</sup> | Evet |
| Webtrends | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| Workforce Dimensions | Evet | Evet | Hayır | Evet | Hayır | Hayır |
| XML | Evet | Evet | Hayır | Evet | Hayır <sup>4</sup> | Evet |
| Zendesk | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| | | | | | | | |

<sup>1</sup>[ACE OLEDB sağlayıcısı](https://www.microsoft.com/download/details.aspx?id=54920) ile desteklenir, ağ geçidiyle aynı makineye yüklenir.

<sup>3</sup> Excel 1997-2003 dosyaları (.xls) [ACE OLEDB sağlayıcısını](https://www.microsoft.com/download/details.aspx?id=54920) gerektirir.

<sup>4</sup> Teknolojinin şirket içi sürümü için gereklidir.

<sup>5</sup> Yalnızca [kişisel ağ geçidiyle](service-gateway-personal-mode.md) desteklenir.

<sup>6</sup> .html, .xls ve Access Veritabanları için gereklidir

<sup>7</sup> Power BI hizmeti, kimlik doğrulaması gerektiren OData akışlarını desteklemez.

<sup>8</sup> Paxata, Power BI Rapor Sunucusu için iyileştirilmiş Power BI Desktop sürümünde desteklenir. Power BI Rapor Sunucusu’na yayımlanan Power BI raporlarında desteklenmez. Desteklenen veri kaynakları listesi için bkz. [Power BI Rapor Sunucusu’nda Power BI raporu veri kaynakları](../report-server/data-sources.md).

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

- Birçok Power BI Desktop veri bağlayıcısı, kimlik doğrulaması için Internet Explorer 10 (veya daha yeni bir sürümü) gerektirir. 
- Power BI Desktop’ta, Power BI Rapor Sunucusu için iyileştirilmiş olan ancak Power BI Rapor Sunucusu’nda yayımlandığında desteklenmeyen bazı veri kaynakları bulunur. Desteklenen veri kaynakları listesi için bkz. [Power BI Rapor Sunucusu’nda Power BI raporu veri kaynakları](../report-server/data-sources.md).

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

## <a name="next-steps"></a>Sonraki adımlar

[Power BI Desktop'ta verilere bağlanma](desktop-quickstart-connect-to-data.md)  
[Power BI'da DirectQuery kullanma](desktop-directquery-about.md)  
[Power BI'da SQL Server Analysis Services canlı verileri](sql-server-analysis-services-tabular-data.md)  
[Şirket içi veri ağ geçidi nedir?](service-gateway-onprem.md)  
[Power BI Rapor Sunucusu'nda Power BI raporu veri kaynakları](../report-server/data-sources.md)