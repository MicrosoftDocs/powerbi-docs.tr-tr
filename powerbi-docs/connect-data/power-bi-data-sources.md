---
title: Power BI veri kaynakları
description: Bu makalede, DirectQuery ve şirket içi veri ağ geçidi hakkındaki bilgiler de dahil olmak üzere Power BI’ın desteklediği veri kaynakları listelenir.
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: pbi-data-sources
ms.topic: conceptual
ms.date: 12/14/2020
ms.openlocfilehash: def849c9a3b867f181dbc91628260cf24491e855
ms.sourcegitcommit: fb529c4532fbbdfde7ce28e2b4b35f990e8f21d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2021
ms.locfileid: "99087948"
---
# <a name="power-bi-data-sources"></a>Power BI veri kaynakları

Aşağıdaki tabloda, DirectQuery ve şirket içi veri ağ geçidi hakkındaki bilgiler de dahil olmak üzere Power BI’ın veri kümeleri için desteklediği veri kaynakları gösterilir. Veri akışları hakkında bilgi için bkz. [Power BI veri akışları için veri kaynaklarına bağlanma](../transform-model/dataflows/dataflows-configure-consume.md).

| Veri kaynağı | Masaüstünden bağlanma | Hizmetten bağlanma ve yenileme | DirectQuery / Canlı bağlantı | Ağ Geçidi (desteklenen) | Ağ Geçidi (gerekli) | Power BI Veri Akışları |
|---|---|---|---|---|---|---|---|
| Access veritabanı | Evet | Yes | Hayır | Evet <sup>1</sup> | Evet | Evet |
| ActiveDirectory | Evet | Yes | Hayır | Yes | Evet | Evet |
| Adobe Analytics | Evet | Yes | Hayır | Hayır | Hayır | Hayır |
| Amazon Redshift | Evet | Yes | Evet | Evet | Hayır | Evet |
| appFigures | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| AtScale küpleri | Evet | Evet | Evet | Yes | Hayır | Hayır |
| Azure Analysis Services | Evet | Yes | Yes | Hayır | Hayır | Hayır |
| Azure Blob Depolama Alanı | Evet | Yes | Hayır | Yes | Hayır | Evet |
| Azure Cosmos DB | Evet | Yes | Hayır | Hayır | Hayır | Hayır |
| Azure Maliyet Yönetimi | Evet | Yes | Hayır | Hayır | Hayır | Hayır |
| Azure Veri Gezgini (kusto) | Evet | Evet | Evet | Yes | Hayır | Evet |
| Azure Data Lake Storage 1. Nesil | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| Azure Data Lake Storage Gen2 | Evet | Yes | Hayır | Evet | Hayır | Evet |
| Azure Databricks | Yes | Yes | Yes | Yes | Hayır | Hayır |
| Azure DevOps | Evet | Yes | Hayır | Hayır | Hayır | Hayır |
| Azure DevOps Server | Evet | Yes | Hayır | Evet | Evet | Hayır |
| Azure HDInsight (HDFS) | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| Azure HDInsight Spark | Evet | Evet | Evet | Hayır | Hayır | Yes |
| Azure SQL Veritabanı | Evet | Yes | Yes | Yes | Hayır | Evet |
| Azure SQL Veri Ambarı | Evet | Yes | Yes | Yes | Hayır | Evet |
| Azure Tablo Depolama | Evet | Yes | Hayır | Evet | Hayır | Evet |
| BI Bağlayıcısı | Evet | Yes | Evet | Evet | Evet | Hayır |
| BI360 - Budgeting & Financial Reporting | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| Microsoft Dataverse | Evet | Evet | Yes | Hayır | Hayır | Evet |
| Data.World - Veri Kümesi Al | Evet | Yes | Hayır | Hayır | Hayır | Hayır |
| Denodo | Evet | Yes | Yes | Yes | Evet | Hayır |
| Dremio | Evet | Yes | Yes | Evet | Evet | Hayır |
| Dynamics 365 (çevrimiçi) | Evet | Yes | Hayır | Hayır | Hayır | Hayır |
| Dynamics 365 Business Central | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| Dynamics 365 Business Central (şirket içi) | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| Dynamics 365 Customer Insights | Evet | Yes | Hayır | Hayır | Hayır | Hayır |
| Dynamics NAV | Evet | Yes | Hayır | Hayır | Hayır | Hayır |
| Emigo Data Source | Yes | Evet | Hayır | Hayır | Hayır | Hayır |
| Entersoft Business Suite | Evet | Yes | Hayır | Hayır | Hayır | Hayır |
| Essbase | Evet | Evet | Evet | Yes | Yes | Hayır |
| Exasol | Evet | Evet | Evet | Yes | Yes | Hayır |
| Excel | Evet <sup>3</sup> | Evet <sup>3</sup> | Hayır | Evet <sup>3</sup> | Hayır <sup>4</sup> | Evet |
| Facebook | Evet | Yes | Hayır | Hayır | Hayır | Hayır |
| Dosya | Evet | Yes | Hayır | Evet | Evet | Evet |
| Klasör | Evet | Yes | Hayır | Evet | Evet | Evet |
| GitHub | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| Google Analytics | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| Google BigQuery | Evet | Yes | Yes | Yes | Hayır | Evet |
| Hadoop Dosyası (HDFS) | Evet | Hayır | Hayır | Hayır | Hayır | Hayır |
| Hive LLAP | Evet | Evet | Yes | Evet | Hayır | Hayır |
| HDInsight Etkileşimli Sorgu | Evet | Yes | Evet | Hayır | Hayır | Hayır |
| IBM DB2 | Evet | Evet | Evet | Yes | Hayır | Evet |
| IBM Informix Veritabanı | Evet | Evet | Hayır | Evet | Hayır | Hayır |
| IBM Netezza | Evet | Yes | Yes | Yes | Yes | Hayır |
| Impala | Evet | Yes | Yes | Yes | Evet | Evet |
| Indexima | Evet | Evet | Yes | Evet | Evet | Hayır |
| Industrial App Store | Evet | Yes | Hayır | Hayır | Hayır | Hayır |
| Information Grid | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| Intersystems IRIS | Evet | Evet | Yes | Yes | Yes | Hayır |
| Intune Veri Ambarı | Evet | Yes | Hayır | Hayır | Hayır | Hayır |
| Jethro ODBC | Evet | Yes | Evet | Yes | Evet | Hayır |
| JSON | Yes | Yes | Hayır | Evet** | Hayır <sup>4</sup> | Evet |
| Kyligence Enterprise | Evet | Yes | Evet | Evet | Yes | Hayır |
| MailChimp | Yes | Evet | Hayır | Hayır | Hayır | Hayır |
| Marketo | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| MarkLogic ODBC | Evet | Yes | Evet | Yes | Yes | Hayır |
| Microsoft Azure Consumption Insights | Evet | Yes | Hayır | Hayır | Hayır | Hayır |
| Microsoft Exchange | Evet | Yes | Hayır | Evet | Hayır | Hayır |
| Microsoft Exchange Online | Evet | Yes | Hayır | Hayır | Hayır | Evet |
| Microsoft Graph Güvenliği | Evet | Evet | Hayır | Yes | Hayır | Hayır |
| Mixpanel | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| MySQL | Evet | Yes | Hayır | Yes | Yes | Evet |
| OData | Evet | Evet <sup>7</sup> | Hayır | Yes | Hayır | Evet |
| ODBC | Evet | Evet | Hayır | Evet | Evet | Evet |
| OleDb | Evet | Yes | Hayır | Evet | Yes | Hayır |
| Oracle | Evet | Evet | Yes | Yes | Yes | Evet |
| Paxata <sup>8</sup> | Evet | Evet | Hayır | Yes | Hayır | Hayır |
| PDF | Evet | Yes | Hayır | Evet | Hayır <sup>4</sup> | Evet |
| Planview Enterprise One - CTM | Evet | Yes | Hayır | Hayır | Hayır | Hayır |
| Planview Enterprise One - PRM | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| Planview Projectplace | Evet | Yes | Hayır | Hayır | Hayır | Hayır |
| PostgreSQL | Evet | Evet | Evet | Yes | Hayır | Evet |
| Power BI veri akışları | Evet | Evet | Hayır | Hayır | Hayır | Evet |
| Power BI veri kümeleri | Evet | Yes | Yes | Hayır | Hayır | Hayır |
| Power Platform veri akışları | Evet | Yes | Hayır | Hayır | Hayır | Evet |
| Python betiği | Evet | Evet <sup>5</sup> | Hayır | Evet <sup>5</sup> | Evet | Hayır |
| QubolePresto | Evet | Yes | Evet | Evet | Yes | Hayır |
| Quick Base | Evet | Evet | Hayır | Evet | Evet | Hayır |
| QuickBooks Online | Evet | Evet | Hayır | Hayır | Hayır | Hayır |
| R betiği | Evet | Evet <sup>5</sup> | Hayır | Evet <sup>5</sup> | Hayır | Hayır |
| Roamler | Evet | Yes | Hayır | Yes | Hayır | Hayır |
| Salesforce Nesneleri | Evet | Yes | Hayır | Hayır | Hayır | Evet |
| Salesforce Raporları | Evet | Yes | Hayır | Hayır | Hayır | Yes |
| SAP Business Warehouse İleti Sunucusu | Evet | Evet | Evet | Yes | Yes | Yes |
| SAP Business Warehouse Sunucusu | Evet | Evet | Evet | Evet | Evet | Yes |
| SAP HANA | Evet | Yes | Evet | Yes | Yes | Evet |
| SharePoint Klasörü | Evet | Yes | Hayır | Evet | Hayır <sup>4</sup> | Evet |
| SharePoint Listesi | Evet | Yes | Hayır | Evet | Hayır <sup>4</sup> | Evet |
| SharePoint Online Listesi | Evet | Yes | Hayır | Evet | Hayır | Evet |
| Smartsheet | Evet | Evet | Hayır | Hayır | Hayır | Evet |
| Snowflake | Evet | Evet | Yes | Yes | Hayır | Evet |
| Spark | Evet | Yes | Evet | Yes | Hayır | Evet |
| SparkPost | Evet | Yes | Hayır | Hayır | Hayır | Hayır |
| SQL Server | Evet | Yes | Yes | Yes | Yes | Yes |
| SQL Server Analysis Services | Evet | Yes | Yes | Yes | Yes | Hayır |
| Stripe | Evet | Yes | Hayır | Hayır | Hayır | Hayır |
| SurveyMonkey | Evet | Yes | Hayır | Yes | Hayır | Hayır |
| SweetIQ | Evet | Yes | Hayır | Hayır | Hayır | Hayır |
| Sybase | Evet | Yes | Hayır | Yes | Yes | Evet |
| TeamDesk | Evet | Yes | Hayır | Yes | Hayır | Hayır |
| Tenforce | Evet | Yes | Hayır | Hayır | Hayır | Hayır |
| Teradata | Evet | Yes | Yes | Yes | Yes | Evet |
| Metin/CSV | Evet | Yes | Hayır | Evet | Hayır <sup>4</sup> | Evet |
| Twilio | Evet | Yes | Hayır | Hayır | Hayır | Hayır |
| tyGraph | Evet | Yes | Hayır | Hayır | Hayır | Hayır |
| Vertica | Evet | Yes | Yes | Yes | Yes | Evet |
| Web | Evet | Yes | Hayır | Evet | Evet <sup>6</sup> | Evet |
| Webtrends | Evet | Yes | Hayır | Hayır | Hayır | Hayır |
| Workforce Dimensions | Evet | Yes | Hayır | Yes | Hayır | Hayır |
| XML | Evet | Yes | Hayır | Evet | Hayır <sup>4</sup> | Evet |
| Zendesk | Evet | Yes | Hayır | Hayır | Hayır | Hayır |
| | | | | | | | |

<sup>1</sup>[ACE OLEDB sağlayıcısı](https://www.microsoft.com/download/details.aspx?id=54920) ile desteklenir, ağ geçidiyle aynı makineye yüklenir.

<sup>3</sup> Excel 1997-2003 dosyaları (.xls) [ACE OLEDB sağlayıcısını](https://www.microsoft.com/download/details.aspx?id=54920) gerektirir.

<sup>4</sup> Teknolojinin şirket içi sürümü için gereklidir.

<sup>5</sup> Yalnızca [kişisel ağ geçidiyle](service-gateway-personal-mode.md) desteklenir.

<sup>6</sup> .html, .xls ve Access Veritabanları için gereklidir

<sup>7</sup> Power BI hizmeti genel OAuth2’yi desteklemez.

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
