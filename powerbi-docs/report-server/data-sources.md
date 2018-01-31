---
title: "Power BI Rapor Sunucusu'nda Power BI raporu veri kaynakları"
description: "Power BI raporları farklı veri kaynaklarına bağlanabilir. Verilerin nasıl kullanıldığına bağlı olarak farklı veri kaynakları kullanılabilir."
services: powerbi
documentationcenter: 
author: markingmyname
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
ms.date: 11/01/2017
ms.author: maghan
ms.openlocfilehash: caa45aab2c31974abb041a82eb2216ebee2eb148
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2018
---
# <a name="power-bi-report-data-sources-in-power-bi-report-server"></a>Power BI Rapor Sunucusu'nda Power BI raporu veri kaynakları
Power BI raporları farklı veri kaynaklarına bağlanabilir. Verilerin nasıl kullanıldığına bağlı olarak farklı veri kaynakları kullanılabilir. Veriler, doğrudan DirectQuery veya SQL Server Analysis Services'e yönelik canlı bağlantı kullanılarak içeri aktarılabilir veya sorgulanabilir.

Bu veri kaynakları, Power BI Rapor Sunucusu'nda kullanılan Power BI raporlarına özeldir. Sayfalandırılmış raporlar tarafından desteklenen veri kaynakları hakkında daha fazla bilgi için bkz. [Reporting Services Tarafından Desteklenen Veri Kaynakları](https://docs.microsoft.com/sql/reporting-services/report-data/data-sources-supported-by-reporting-services-ssrs).

> [!IMPORTANT]
> Zamanlanmış yenilemenin yapılandırılabilmesi için bir Power BI Desktop raporundaki tüm veri kaynaklarının desteklenmesi gerekir.
> 
> 

## <a name="list-of-supported-data-sources"></a>Desteklenen veri kaynaklarının listesi
Bunlar dışındaki veri kaynakları, desteklenenler listesinde bulunmasa bile çalışıyor olabilir.

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
| Azure HDInsight (HDFS) |Evet |Evet |Hayır |
| Azure HDInsight (Spark) |Evet |Evet |Hayır |
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
| Teradata Veritabanı |Evet |Evet |Evet |
| Metin/CSV |Evet |Evet |Hayır |
| Web |Evet |Evet |Hayır |
| XML |Evet |Evet |Hayır |
| appFigures (Beta) |Evet |Hayır |Hayır |
| Azure Analysis Services veritabanı (Beta) |Evet |Hayır |Hayır |
| Azure Cosmos DB (Beta) |Evet |Hayır |Hayır |
| Azure HDInsight Spark (Beta) |Evet |Hayır |Hayır |
| Common Data Service (Beta) |Evet |Hayır |Hayır |
| comScore Digital Analytix (Beta) |Evet |Hayır |Hayır |
| Customer Insights için Dynamics 365 (Beta) |Evet |Hayır |Hayır |
| Dynamics 365 for Financials (Beta) |Evet |Hayır |Hayır |
| GitHub (Beta) |Evet |Hayır |Hayır |
| Google BigQuery (Beta) |Evet |Hayır |Hayır |
| IBM Informix veritabanı (Beta) |Evet |Hayır |Hayır |
| IBM Netezza (Beta) |Evet |Hayır |Hayır |
| Kusto (Beta) |Evet |Hayır |Hayır |
| MailChimp (Beta) |Evet |Hayır |Hayır |
| Microsoft Azure Tüketim Öngörüleri (Beta) |Evet |Hayır |Hayır |
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

## <a name="next-steps"></a>Sonraki adımlar
Veri kaynağınızı seçildiğine göre, artık bu veri kaynağındaki verileri kullanarak [rapor oluşturabilirsiniz](quickstart-create-powerbi-report.md).

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)

