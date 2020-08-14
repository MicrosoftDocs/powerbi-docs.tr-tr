---
title: Power BI Rapor Sunucusu'nda Power BI raporu veri kaynakları
description: Power BI raporları birkaç veri kaynağına bağlanabilir. Verilerin nasıl kullanıldığına bağlı olarak farklı veri kaynakları kullanılabilir.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 08/04/2020
ms.author: maggies
ms.openlocfilehash: 00c00ca7bbd7ad3f901c98f44a2900f332e3616a
ms.sourcegitcommit: 65822b51810a5239fea9d3d0af1fc286436c6cad
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87837624"
---
# <a name="power-bi-report-data-sources-in-power-bi-report-server"></a>Power BI Rapor Sunucusu'nda Power BI raporu veri kaynakları
Power BI raporları birkaç veri kaynağına bağlanabilir. Verilerin nasıl kullanıldığına bağlı olarak farklı veri kaynakları kullanılabilir. Veriler, doğrudan DirectQuery veya SQL Server Analysis Services'e yönelik canlı bağlantı kullanılarak içeri aktarılabilir veya sorgulanabilir. Power BI Desktop’ta, Power BI Rapor Sunucusu için iyileştirilmiş olan ancak Power BI Rapor Sunucusu’na yayımlanan Power BI raporları için iyileştirilmiş olmayan bazı veri kaynakları desteklenir. Her iki yerde de desteklenen veri kaynakları için aşağıdaki listeye bakın.

Bu veri kaynakları, Power BI Rapor Sunucusu'nda kullanılan Power BI raporlarına özeldir. Sayfalandırılmış raporlar (.rdl) tarafından desteklenen veri kaynakları hakkında daha fazla bilgi için bkz. [Reporting Services Tarafından Desteklenen Veri Kaynakları](https://docs.microsoft.com/sql/reporting-services/report-data/data-sources-supported-by-reporting-services-ssrs).

> [!IMPORTANT]
> Bir Power BI Desktop raporundaki tüm veri kaynaklarının zamanlanmış yenilemeyi yapılandırma özelliğini desteklemesi gerekir.
>  

## <a name="list-of-supported-data-sources"></a>Desteklenen veri kaynaklarının listesi

| **Veri kaynağı** | **Önbelleğe veri alma** | **Zamanlanmış yenileme** | **Canlı/DirectQuery** |
| --- | --- | --- | --- |
| SQL Server Veritabanı |Evet |Evet |Evet |
| SQL Server Analysis Services |Evet |Evet |Evet |
| Azure SQL Veritabanı |Evet |Evet |Evet |
| Azure SQL Veri Ambarı |Evet |Evet |Evet |
| Excel |Evet |Evet |Hayır |
| Access Veritabanı |Evet |Evet |Hayır |
| Active Directory |Evet |Evet |Hayır |
| Amazon Redshift |Evet |Hayır |Hayır |
| Azure Blob Depolama Alanı |Evet |Evet |Hayır |
| Azure Data Lake Store |Evet |Hayır |Hayır |
| Azure HDInsight (HDFS) |Evet |Hayır |Hayır |
| Azure HDInsight (Spark) |Evet |Hayır |Hayır |
| Azure Tablo Depolama |Evet |Evet |Hayır |
| Dynamics 365 (çevrimiçi) |Evet |Hayır |Hayır |
| Facebook |Evet |Hayır |Hayır |
| Klasör |Evet |Evet |Hayır |
| Google Analytics |Evet |Hayır |Hayır |
| Hadoop Dosyası (HDFS) |Evet |Hayır |Hayır |
| IBM DB2 Veritabanı |Evet |Evet |Hayır |
| Impala |Evet |Hayır |Hayır |
| JSON |Evet |Evet |Hayır |
| Microsoft Exchange |Evet |Hayır |Hayır |
| Microsoft Exchange Online |Evet |Hayır |Hayır |
| MySQL Veritabanı |Evet |Evet |Hayır |
| OData Akışı |Evet |Evet |Hayır |
| ODBC |Evet |Evet |Hayır |
| OLE DB |Evet |Evet |Hayır |
| Oracle Veritabanı |Evet |Evet |Evet |
| PostgreSQL Veritabanı |Evet |Evet |Hayır |
| Power BI hizmeti |Hayır |Hayır |Hayır |
| R Betiği |Evet |Hayır |Hayır |
| Salesforce Nesneleri |Evet |Hayır |Hayır |
| Salesforce Raporları |Evet |Hayır |Hayır |
| SAP Business Warehouse sunucusu |Evet |Evet |Evet |
| SAP HANA Veritabanı |Evet |Evet |Evet |
| SharePoint Klasörü (şirket içi) |Evet |Evet |Hayır |
| SharePoint Listesi (şirket içi) |Evet |Evet |Hayır |
| SharePoint Online Listesi |Evet |Hayır |Hayır |
| Snowflake |Evet |Hayır |Hayır |
| Sybase Veritabanı |Evet |Evet |Hayır |
| Teradata |Evet |Evet |Evet |
| Metin/CSV |Evet |Evet |Hayır |
| Web |Evet |Evet |Hayır |
| XML |Evet |Evet |Hayır |
| appFigures (Beta) |Evet |Hayır |Hayır |
| Azure Analysis Services veritabanı |Evet |Hayır |Evet |
| Azure Cosmos DB (Beta) |Evet |Hayır |Hayır |
| Azure HDInsight Spark (Beta) |Evet |Hayır |Hayır |
| Common Data Service (Beta) |Evet |Hayır |Hayır |
| comScore Digital Analytix (Beta) |Evet |Hayır |Hayır |
| Dynamics 365 for Customer Insights (Beta) |Evet |Hayır |Hayır |
| Dynamics 365 for Financials (Beta) |Evet |Hayır |Hayır |
| GitHub (Beta) |Evet |Hayır |Hayır |
| Google BigQuery (Beta) |Evet |Hayır |Hayır |
| IBM Informix veritabanı (Beta) |Evet |Hayır |Hayır |
| IBM Netezza (Beta) |Evet |Hayır |Hayır |
| Kusto (Beta) |Evet |Hayır |Hayır |
| MailChimp (Beta) |Evet |Hayır |Hayır |
| Microsoft Azure Consumption Insights (Beta) |Evet |Hayır |Hayır |
| Mixpanel (Beta) |Evet |Hayır |Hayır |
| Planview Enterprise (Beta) |Evet |Hayır |Hayır |
| Projectplace (Beta) |Evet |Hayır |Hayır |
| QuickBooks Online (Beta) |Evet |Hayır |Hayır |
| Smartsheet |Evet |Hayır |Hayır |
| Spark (Beta) |Evet |Hayır |Hayır |
| SparkPost (Beta) |Evet |Hayır |Hayır |
| SQL Sentry (Beta) |Evet |Hayır |Hayır |
| Stripe (Beta) |Evet |Hayır |Hayır |
| SweetIQ (Beta) |Evet |Hayır |Hayır |
| Troux (Beta) |Evet |Hayır |Hayır |
| Twilio (Beta) |Evet |Hayır |Hayır |
| tyGraph (Beta) |Evet |Hayır |Hayır |
| Vertica (Beta) |Evet |Hayır |Hayır |
| Visual Studio Team Services (Beta) |Evet |Hayır |Hayır |
| Webtrends (Beta) |Evet |Hayır |Hayır |
| Zendesk (Beta) |Evet |Hayır |Hayır |

> [!IMPORTANT]
> Kerberos'un ortamınızda uygun şekilde yapılandırıldığı varsayıldığında, veri kaynağında yapılandırılmış satır düzeyi güvenlik, belirli DirectQuery (SQL Server, Azure SQL Veritabanı, Oracle ve Teradata) bağlantıları ve canlı bağlantılar için çalışacaktır.
> 
> 

## <a name="list-of-supported-authentication-methods-for-model-refresh"></a>Model yenileme için desteklenen kimlik doğrulama yöntemleri listesi

Power BI Rapor Sunucusu, OAuth tabanlı kimlik doğrulaması için model yenilemeyi desteklemez. Excel veya Access veritabanları gibi bazı veri kaynakları, verilere bağlanmak için Dosya veya Web gibi ayrı bir adımdan yararlanır.

| **Veri kaynağı** | **Anonim Kimlik Doğrulaması** | **Anahtar Kimlik Doğrulaması** | **Kullanıcı Adı ve Parola** | **Windows Kimlik Doğrulaması** |
| --- | --- | --- | --- | --- |
| SQL Server Veritabanı |Hayır |Hayır |Evet |Evet |
| SQL Server Analysis Services |Hayır |Hayır |Evet |Evet |
| Web |Evet |Hayır |Evet |Evet |
| Azure SQL Veritabanı |Hayır |Hayır |Evet |Hayır |
| Azure SQL Veri Ambarı |Hayır |Hayır |Evet |Hayır |
| Active Directory |Hayır |Hayır |Evet |Evet |
| Amazon Redshift |Hayır |Hayır |Hayır |Hayır |
| Azure Blob Depolama Alanı |Evet |Evet |Hayır |Hayır |
| Azure Data Lake Store |Hayır |Hayır |Hayır |Hayır |
| Azure HDInsight (HDFS) |Hayır |Hayır |Hayır |Hayır |
| Azure HDInsight (Spark) |Hayır |Hayır |Hayır |Hayır |
| Azure Tablo Depolama |Hayır |Evet |Hayır |Hayır |
| Dynamics 365 (çevrimiçi) |Hayır |Hayır |Hayır |Hayır |
| Facebook |Hayır |Hayır |Hayır |Hayır |
| Klasör |Hayır |Hayır |Hayır |Evet |
| Google Analytics |Hayır |Hayır |Hayır |Hayır |
| Hadoop Dosyası (HDFS) |Hayır |Hayır |Hayır |Hayır |
| IBM DB2 Veritabanı |Hayır |Hayır |Evet |Evet |
| Impala |Hayır |Hayır |Hayır |Hayır |
| Microsoft Exchange |Hayır |Hayır |Hayır |Hayır |
| Microsoft Exchange Online |Hayır |Hayır |Hayır |Hayır |
| MySQL Veritabanı |Hayır |Hayır |Evet |Evet |
| OData Akışı |Evet |Evet |Evet |Evet |
| ODBC |Evet |Hayır |Evet |Evet |
| OLE DB |Evet |Hayır |Evet |Evet |
| Oracle Veritabanı |Hayır |Hayır |Evet |Evet |
| PostgreSQL Veritabanı |Hayır |Hayır |Evet |Hayır |
| Power BI hizmeti |Hayır |Hayır |Hayır |Hayır |
| R Betiği |Hayır |Hayır |Hayır |Hayır |
| Salesforce Nesneleri |Hayır |Hayır |Hayır |Hayır |
| Salesforce Raporları |Hayır |Hayır |Hayır |Hayır |
| SAP Business Warehouse sunucusu |Hayır |Hayır |Evet |Hayır |
| SAP HANA Veritabanı |Hayır |Hayır |Evet |Evet |
| SharePoint Klasörü (şirket içi) |Evet |Hayır |Hayır |Evet |
| SharePoint Listesi (şirket içi) |Evet |Hayır |Hayır |Evet |
| SharePoint Online Listesi |Hayır |Hayır |Hayır |Hayır |
| Snowflake |Hayır |Hayır |Hayır |Hayır |
| Sybase Veritabanı |Hayır |Hayır |Evet |Evet |
| Teradata |Hayır |Hayır |Evet |Evet** |
| appFigures (Beta) |Hayır |Hayır |Hayır |Hayır |
| Azure Analysis Services veritabanı (Beta) |Hayır |Hayır |Hayır |Hayır |
| Azure Cosmos DB (Beta) |Hayır |Hayır |Hayır |Hayır |
| Azure HDInsight Spark (Beta) |Hayır |Hayır |Hayır |Hayır |
| Common Data Service (Beta) |Hayır |Hayır |Hayır |Hayır |
| comScore Digital Analytix (Beta) |Hayır |Hayır |Hayır |Hayır |
| Dynamics 365 for Customer Insights (Beta) |Hayır |Hayır |Hayır |Hayır |
| Dynamics 365 for Financials (Beta) |Hayır |Hayır |Hayır |Hayır |
| GitHub (Beta) |Hayır |Hayır |Hayır |Hayır |
| Google BigQuery (Beta) |Hayır |Hayır |Hayır |Hayır |
| IBM Informix veritabanı (Beta) |Hayır |Hayır |Hayır |Hayır |
| IBM Netezza (Beta) |Hayır |Hayır |Hayır |Hayır |
| Kusto (Beta) |Hayır |Hayır |Hayır |Hayır |
| MailChimp (Beta) |Hayır |Hayır |Hayır |Hayır |
| Microsoft Azure Consumption Insights (Beta) |Hayır |Hayır |Hayır |Hayır |
| Mixpanel (Beta) |Hayır |Hayır |Hayır |Hayır |
| Planview Enterprise (Beta) |Hayır |Hayır |Hayır |Hayır |
| Projectplace (Beta) |Hayır |Hayır |Hayır |Hayır |
| QuickBooks Online (Beta) |Hayır |Hayır |Hayır |Hayır |
| Smartsheet |Hayır |Hayır |Hayır |Hayır |
| Spark (Beta) |Hayır |Hayır |Hayır |Hayır |
| SparkPost (Beta) |Hayır |Hayır |Hayır |Hayır |
| SQL Sentry (Beta) |Hayır |Hayır |Hayır |Hayır |
| Stripe (Beta) |Hayır |Hayır |Hayır |Hayır |
| SweetIQ (Beta) |Hayır |Hayır |Hayır |Hayır |
| Troux (Beta) |Hayır |Hayır |Hayır |Hayır |
| Twilio (Beta) |Hayır |Hayır |Hayır |Hayır |
| tyGraph (Beta) |Hayır |Hayır |Hayır |Hayır |
| Vertica (Beta) |Hayır |Hayır |Hayır |Hayır |
| Visual Studio Team Services (Beta) |Hayır |Hayır |Hayır |Hayır |
| Webtrends (Beta) |Hayır |Hayır |Hayır |Hayır |
| Zendesk (Beta) |Hayır |Hayır |Hayır |Hayır |

**Teradata ile LDAP kimlik doğrulamasını kullanma (Power BI Desktop’ta Komut İstemi komutu 'setx PBI_EnableTeradataLdap true' kullanılarak etkinleştirilir) model yenileme için desteklenmez.

## <a name="list-of-supported-authentication-methods-for-directquery"></a>DirectQuery için desteklenen kimlik doğrulama yöntemleri listesi

Power BI Rapor Sunucusu, OAuth tabanlı kimlik doğrulaması için DirectQuery’yi desteklemez.

| **Veri kaynağı** | **Anonim Kimlik Doğrulaması** | **Anahtar Kimlik Doğrulaması** | **Kullanıcı Adı ve Parola** | **Windows Kimlik Doğrulaması** | **Tümleşik Windows Kimlik Doğrulaması** |
| --- | --- | --- | --- | --- | --- |
| SQL Server Veritabanı |Hayır |Hayır |Evet |Evet |Evet |
| SQL Server Analysis Services |Hayır |Hayır |Evet |Evet |Evet |
| Azure SQL Veritabanı |Hayır |Hayır |Evet |Hayır |Hayır |
| Azure SQL Veri Ambarı |Hayır |Hayır |Evet |Hayır |Hayır |
| Oracle Veritabanı |Hayır |Hayır |Evet |Evet |Evet |
| SAP Business Warehouse sunucusu |Hayır |Hayır |Evet |Hayır |Hayır |
| SAP HANA Veritabanı |Hayır |Hayır |Evet |Evet |Evet** |
| Teradata |Hayır |Hayır |Evet |Evet |Evet |

**SAP HANA Tümleşik Windows Kimlik Doğrulaması ile DirectQuery'yi yalnızca bunu yayımlanmış Power BI Desktop dosyasında (.pbix) ilişkisel veritabanı olarak kullandığında destekler.

## <a name="next-steps"></a>Sonraki adımlar

Power BI hizmetinde [Power BI raporları için veri kaynakları[(../connect-data/power-bi-data-sources.md) Veri kaynağınıza bağlandığınıza göre şimdi bu veri kaynağındaki verileri kullanarak [bir Power BI raporu oluşturun](quickstart-create-powerbi-report.md).

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
