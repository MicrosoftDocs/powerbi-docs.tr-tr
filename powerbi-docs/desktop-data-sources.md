---
title: Power BI Desktop'taki veri kaynakları
description: Power BI Desktop'taki veri kaynakları
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 08/16/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 5004b55fa48cdf98aedd019749b738352d68c4cd
ms.sourcegitcommit: f6ac9e25760561f49d4257a6335ca0f54ad2d22e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69560878"
---
# <a name="data-sources-in-power-bi-desktop"></a>Power BI Desktop'taki veri kaynakları
Power BI Desktop ile birçok farklı kaynaktaki verilere bağlanabilirsiniz. Bu sayfanın en altında, kullanabileceğiniz veri kaynaklarının tam listesi yer almaktadır.

Verilere bağlanmak için **Giriş** şeridindeki **Veri Al** seçeneğini belirleyin. Düğmedeki aşağı oku veya **Veri Al** metnini seçtiğinizde, **En Yaygın** veri türlerinin yer aldığı menü görüntülenir. (Aşağıda gösterilmektedir.)

![Power BI Desktop'ta Veri Al](media/desktop-data-sources/data-sources-01.png)

**En Yaygın** menüsündeki **Diğer...** seçeneğini belirlediğinizde **Veri Al** penceresi görüntülenir. Ayrıca **Veri Al** **simgesinin bulunduğu düğmeyi** seçtiğinizde **En Yaygın** menüsünü atlayarak **Veri Al** penceresini doğrudan görüntüleyebilirsiniz.

![Veri Al düğmesi](media/desktop-data-sources/data-sources-02.png)

> [!NOTE]
> Power BI ekibi, **Power BI Desktop** ve **Power BI hizmetinde** kullanıma sunulan veri kaynaklarının sayısını sürekli olarak artırmaktadır. Bu nedenle, sık sık *Beta* veya *Önizleme* olarak işaretlenmiş veri kaynaklarıyla karşılaşırsınız. Bunlar, üzerinde çalışılmakta olan veri kaynaklarının ilk sürümleridir. *Beta* veya *Önizleme* olarak işaretlenen veri kaynakları için destek ve işlevsellik sınırlıdır. Bunlar, üretim ortamlarında kullanılmamalıdır. 

> Ayrıca, **Power BI Desktop** için *Beta* veya *Önizleme* olarak işaretlenen herhangi bir veri kaynağı, genel olarak kullanılabilir (GA) hale gelene kadar **Power BI hizmetinde** veya diğer Microsoft hizmetlerinde kullanılamayabilir.

## <a name="data-sources"></a>Veri Kaynakları
Veri türleri, aşağıdaki kategoriler halinde düzenlenmiştir:

* Tümü
* Dosya
* Veritabanı
* Power BI
* Azure
* Çevrimiçi Hizmetler
* Diğer

**Tümü** kategorisi, tüm kategorilerdeki bütün veri bağlantı türlerini içerir.

**Dosya** kategorisinde, aşağıdaki veri bağlantıları sağlanır:

* Excel
* Metin/CSV
* XML
* JSON
* Klasör
* PDF
* SharePoint Klasörü

Aşağıda, **Dosya** kategorisine ilişkin **Veri Al** penceresi gösterilmektedir.

![Veri Al > Dosya](media/desktop-data-sources/data-sources-03.png)

**Veritabanı** kategorisinde aşağıdaki veri bağlantıları sağlanır:

* SQL Server Veritabanı
* Access Veritabanı
* SQL Server Analysis Services Veritabanı
* Oracle Veritabanı
* IBM DB2 Veritabanı
* IBM Informix veritabanı (Beta)
* IBM Netezza
* MySQL Veritabanı
* PostgreSQL Veritabanı
* Sybase Veritabanı
* Teradata Veritabanı
* SAP HANA Veritabanı
* SAP Business Warehouse Uygulama Sunucusu
* SAP Business Warehouse İleti Sunucusu
* Amazon Redshift
* Impala
* Google BigQuery
* Vertica
* Snowflake
* Essbase
* AtScale küpleri (Beta)
* BI Bağlayıcısı
* Dremio
* Exasol
* Indexima (Beta)
* InterSystems IRIS (Beta)
* Jethro (Beta)
* Kyligence Enterprise (Beta)
* MarkLogic (Beta)

> [!NOTE]
> Bazı veri bağlayıcıları için **Dosya > Seçenekler ve ayarlar > Seçenekler** bölümüne gidip **Önizleme Özellikleri**'ni seçerek ilgili bağlayıcıyı etkinleştirmeniz gerekir. Yukarıda belirtilen bağlayıcılardan bazılarını görmüyorsanız söz konusu bağlayıcıları kullanmak için **Önizleme Özellikleri** ayarlarınızı kontrol edin. Ayrıca, *Beta* veya *Önizleme* olarak işaretlenen veri kaynakları için destek ve işlevselliğin sınırlı olduğunu ve bunların, üretim ortamlarında kullanılmaması gerektiğini unutmayın.

Aşağıda, **Veritabanı** kategorisine ilişkin **Veri Al** penceresi gösterilmektedir.

![Veri Al > Veritabanları](media/desktop-data-sources/data-sources-04.png)

**Power Platform** kategorisinde aşağıdaki veri bağlantıları sağlanır:

* Power BI veri kümeleri
* Power BI veri akışları
* Common Data Service
* Power Platform veri akışları (Beta)

Aşağıdaki görüntüde **Power Platform** kategorisine ilişkin **Veri Al** penceresi gösterilmektedir.

![Veri Al > Power BI](media/desktop-data-sources/data-sources-05.png)

**Azure** kategorisinde, aşağıdaki veri bağlantıları sağlanır:

* Azure SQL Veritabanı
* Azure SQL Veri Ambarı
* Azure Analysis Services veritabanı
* Azure Blob Depolama
* Azure Tablo Depolama
* Azure Cosmos DB
* Azure Data Lake Storage 2. Nesil (Beta)
* Azure Data Lake Storage 1. Nesil
* Azure HDInsight (HDFS)
* Azure HDInsight Spark
* HDInsight Etkileşimli Sorgu
* Azure Veri Gezgini (Kusto)
* Azure Maliyet Yönetimi (Beta)

Aşağıda, **Azure** kategorisine ilişkin **Veri Al** penceresi gösterilmektedir.

![Veri Al > Azure](media/desktop-data-sources/data-sources-06.png)

**Çevrimiçi Hizmetler** kategorisinde, aşağıdaki veri bağlantıları sağlanır:

* SharePoint Online Listesi
* Microsoft Exchange Online
* Dynamics 365 (çevrimiçi)
* Dynamics NAV
* Dynamics 365 Business Central
* Dynamics 365 Business Central (şirket içi)
* Microsoft Azure Consumption Insights (Beta)
* Azure DevOps (Beta)
* Azure DevOps Server (Beta)
* Salesforce Nesneleri
* Salesforce Raporları
* Google Analytics
* Adobe Analytics
* appFigures (Beta)
* Data.World - Veri Kümesi Al (Beta)
* Facebook
* GitHub (Beta)
* MailChimp (Beta)
* Marketo (Beta)
* Mixpanel (Beta)
* Planview Enterprise One - PRM (Beta)
* Planview Projectplace (Beta)
* QuickBooks Online (Beta)
* Smartsheet
* SparkPost (Beta)
* Stripe (Beta)
* SweetIQ (Beta)
* Planview Enterprise One - CMT (Beta)
* Twilio (Beta)
* tyGraph (Beta)
* Webtrends (Beta)
* Zendesk (Beta)
* Dynamics 365 Customer Insights (Beta)
* Emigo Data Source (Beta)
* Entersoft Business Suite (Beta)
* Industrial App Store
* Intune Veri Ambarı (Beta)
* Microsoft Graph Güvenliği (Beta)
* Quick Base
* TeamDesk (Beta)


Aşağıda, **Çevrimiçi Hizmetler** kategorisine ilişkin **Veri Al** penceresi gösterilmektedir.

![Veri Al > Çevrimiçi Hizmetler](media/desktop-data-sources/data-sources-07.png)

**Diğer** kategorisinde, aşağıdaki veri bağlantıları sağlanır:

* Web
* SharePoint Listesi
* OData Akışı
* Active Directory
* Microsoft Exchange
* Hadoop Dosyası (HDFS)
* Spark
* R Betiği
* Python betiği
* ODBC
* OLE DB
* BI360 - Budgeting & Financial Reporting (Beta)
* Denado
* Information Grid (Beta)
* Paxata 
* QubolePresto (Beta)
* Roamler (Beta)
* SurveyMonkey (Beta)
* Tenforce (Smart)List (Beta)
* Workforce Dimensions (Beta)
* Boş Sorgu

Aşağıda, **Diğer** kategorisine ilişkin **Veri Al** penceresi gösterilmektedir.

![Veri Al > Diğer](media/desktop-data-sources/data-sources-08.png)

> [!NOTE]
> Şu anda, güvenliği Azure Active Directory ile sağlanan özel veri kaynaklarına bağlanılamamaktadır.

## <a name="connecting-to-a-data-source"></a>Veri Kaynaklarına Bağlanma
Bir veri kaynağına bağlanmak için **Veri Al** penceresinde söz konusu veri kaynağını seçin ve ardından **Bağlan** seçeneğini belirleyin. Aşağıdaki görüntüde, **Diğer** veri bağlantısı kategorisinde yer alan **Web** seçeneği belirlenmiştir.

![Web’e bağlanma](media/desktop-data-sources/data-sources-08.png)

Veri bağlantısının türüne özel bir bağlantı penceresi görüntülenir. Gerekli olması halinde kimlik bilgilerinizi girmeniz istenir. Aşağıdaki görüntüde, bir Web veri kaynağına bağlanmak için girilen bir URL gösterilmektedir.

![Web URL'si girme](media/desktop-data-sources/datasources-fromwebbox.png)

URL veya kaynak bağlantı bilgilerini girdikten sonra **Tamam**'ı seçin. Power BI Desktop veri kaynağı bağlantısını gerçekleştirir ve kullanabileceğiniz veri kaynaklarını **Gezgin** penceresinde görüntüler.

![Gezgin ekranı](media/desktop-data-sources/datasources-fromnavigatordialog.png)

**Gezgin** bölmesinin alt kısmındaki **Yükle** düğmesini seçerek verileri yükleyebilir veya verileri yüklemeden önce sorguyu düzenlemek isterseniz **Düzenle** düğmesini seçebilirsiniz.

Power BI Desktop'ta veri kaynaklarına bağlanmak için tüm yapmanız gereken bu! Sayısı sürekli artan veri kaynaklarımızdaki verilere bağlanın ve veri kaynaklarımızın bulunduğu listeyi sık sık kontrol edin. Yeni veri kaynakları eklemeye devam edeceğiz.

## <a name="next-steps"></a>Sonraki adımlar
Power BI Desktop ile yapabileceğiniz çok şey var. Özellikler hakkında daha fazla bilgi edinmek için aşağıdaki kaynaklara bakın:

* [Power BI Desktop nedir?](desktop-what-is-desktop.md)
* [Power BI Desktop ile Sorgulara Genel Bakış](desktop-query-overview.md)
* [Power BI Desktop'taki Veri Türleri](desktop-data-types.md)
* [Power BI Desktop'ta Verileri Şekillendirme ve Birleştirme](desktop-shape-and-combine-data.md)
* [Power BI Desktop'taki Genel Sorgu Görevleri](desktop-common-query-tasks.md)    
