---
title: "Power BI Desktop'taki veri kaynakları"
description: "Power BI Desktop'taki veri kaynakları"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: complete
qualitydate: 04/29/2016
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/05/2017
ms.author: davidi
ms.openlocfilehash: 6014b38e0e9cabe0dc909268f87cdb284de47106
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="data-sources-in-power-bi-desktop"></a>Power BI Desktop'taki veri kaynakları
Power BI Desktop ile birçok farklı kaynaktaki verilere bağlanabilirsiniz. Bu sayfanın en altında, kullanabileceğiniz veri kaynaklarının tam listesi yer almaktadır.

Verilere bağlanmak için **Giriş** şeridindeki **Veri Al** seçeneğini belirleyin. Düğmedeki aşağı oku veya **Veri Al** metnini seçtiğinizde, **En Yaygın** veri türlerinin yer aldığı menü görüntülenir. (Aşağıda gösterilmektedir.)

![](media/desktop-data-sources/data-sources_1.png)

**En Yaygın** menüsündeki **Diğer...** seçeneğini belirlediğinizde **Veri Al** penceresi görüntülenir. Ayrıca **Veri Al** **simgesinin bulunduğu düğmeyi** seçtiğinizde **En Yaygın** menüsünü atlayarak **Veri Al** penceresini doğrudan görüntüleyebilirsiniz.

![](media/desktop-data-sources/data-sources_2.png)

> [!NOTE]
> Power BI ekibi, **Power BI Desktop** ve **Power BI hizmetinde** kullanıma sunulan veri kaynaklarının sayısını sürekli olarak artırmaktadır. Bu nedenle, sık sık *Beta* veya *Önizleme* olarak işaretlenmiş veri kaynaklarıyla karşılaşırsınız. Bunlar, üzerinde çalışılmakta olan veri kaynaklarının ilk sürümleridir. *Beta* veya *Önizleme* olarak işaretlenen veri kaynakları için destek ve işlevsellik sınırlıdır. Bunlar, üretim ortamlarında kullanılmamalıdır.
> 
> 

## <a name="data-sources"></a>Veri Kaynakları
Veri türleri, aşağıdaki kategoriler halinde düzenlenmiştir:

* Tümü
* Dosya
* Veritabanı
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
* SharePoint Klasörü

Aşağıda, **Dosya** kategorisine ilişkin **Veri Al** penceresi gösterilmektedir.

![](media/desktop-data-sources/data-sources_3.png)

> [!NOTE]
> Power BI Desktop'ın önceki sürümlerinde **CSV** ve **Metin** ayrı veri bağlantı türleri olarak ele alınıyordu. Bu veri bağlayıcıları artık **CSV/Metin** olarak bir araya getirildi.
> 
> 

**Veritabanı** kategorisinde aşağıdaki veri bağlantıları sağlanır:

* SQL Server Veritabanı
* Access Veritabanı
* SQL Server Analysis Services Veritabanı
* Oracle Veritabanı
* IBM DB2 Veritabanı
* IBM Informix veritabanı (Beta)
* IBM Netezza (Beta)
* MySQL Veritabanı
* PostgreSQL Veritabanı
* Sybase Veritabanı
* Teradata Veritabanı
* SAP HANA Veritabanı
* SAP Business Warehouse sunucusu
* Amazon Redshift
* Impala
* Google BigQuery (Beta)
* Snowflake

> [!NOTE]
> Bazı veri bağlayıcıları için **Dosya > Seçenekler ve ayarlar > Seçenekler** bölümüne gidip **Önizleme Özellikleri**'ni seçerek ilgili bağlayıcıyı etkinleştirmeniz gerekir. Yukarıda belirtilen bağlayıcılardan bazılarını görmüyorsanız söz konusu bağlayıcıları kullanmak için **Önizleme Özellikleri** ayarlarınızı kontrol edin. Ayrıca, *Beta* veya *Önizleme* olarak işaretlenen veri kaynakları için destek ve işlevselliğin sınırlı olduğunu ve bunların, üretim ortamlarında kullanılmaması gerektiğini unutmayın.
> 
> 

Aşağıda, **Veritabanı** kategorisine ilişkin **Veri Al** penceresi gösterilmektedir.

![](media/desktop-data-sources/data-sources_4.png)

**Azure** kategorisinde, aşağıdaki veri bağlantıları sağlanır:

* Azure SQL Veritabanı
* Azure SQL Veri Ambarı
* Azure Analysis Services veritabanı (Beta)
* Azure Blob Depolama
* Azure Tablo Depolama
* Azure Cosmos DB (Beta)
* Azure Data Lake Store
* Azure HDInsight (HDFS)
* Azure HDInsight Spark (Beta)

Aşağıda, **Azure** kategorisine ilişkin **Veri Al** penceresi gösterilmektedir.

![](media/desktop-data-sources/data-sources_5.png)

**Çevrimiçi Hizmetler** kategorisinde, aşağıdaki veri bağlantıları sağlanır:

* Power BI hizmeti
* SharePoint Online Listesi
* Microsoft Exchange Online
* Dynamics 365 (çevrimiçi)
* Dynamics 365 for Financials (Beta)
* Common Data Service (Beta)
* Microsoft Azure Tüketim Öngörüleri (Beta)
* Visual Studio Team Services (Beta)
* Salesforce Nesneleri
* Salesforce Raporları
* Google Analytics
* appFigures (Beta)
* comScore Digital Analytix (Beta)
* Customer Insights için Dynamics 365 (Beta)
* Facebook
* GitHub (Beta)
* Kusto (Beta)
* MailChimp (Beta)
* Mixpanel (Beta)
* Planview Enterprise (Beta)
* Projectplace (Beta)
* QuickBooks Online (Beta)
* Smartsheet
* SparkPost (Beta)
* SQL Sentry (Beta)
* Stripe (Beta)
* SweetIQ (Beta)
* Troux (Beta)
* Twilio (Beta)
* tyGraph (Beta)
* Webtrends (Beta)
* Zendesk (Beta)

Aşağıda, **Çevrimiçi Hizmetler** kategorisine ilişkin **Veri Al** penceresi gösterilmektedir.

![](media/desktop-data-sources/data-sources_6b.png)

**Diğer** kategorisinde, aşağıdaki veri bağlantıları sağlanır:

* Vertica (Beta)
* Web
* SharePoint Listesi
* OData Akışı
* Active Directory
* Microsoft Exchange
* Hadoop Dosyası (HDFS)
* Spark (Beta)
* R Betiği
* ODBC
* OLE DB
* Boş Sorgu

Aşağıda, **Diğer** kategorisine ilişkin **Veri Al** penceresi gösterilmektedir.

![](media/desktop-data-sources/data-sources_7a.png)

> [!NOTE]
> Şu anda, güvenliği Azure Active Directory ile sağlanan özel veri kaynaklarına bağlanılamamaktadır.
> 
> 

## <a name="connecting-to-a-data-source"></a>Veri Kaynaklarına Bağlanma
Bir veri kaynağına bağlanmak için **Veri Al** penceresinde söz konusu veri kaynağını seçin ve ardından **Bağlan** seçeneğini belirleyin. Aşağıdaki görüntüde, **Diğer** veri bağlantısı kategorisinde yer alan **Web** seçeneği belirlenmiştir.

![](media/desktop-data-sources/data-sources_7b.png)

Veri bağlantısının türüne özel bir bağlantı penceresi görüntülenir. Gerekli olması halinde kimlik bilgilerinizi girmeniz istenir. Aşağıdaki görüntüde, bir Web veri kaynağına bağlanmak için girilen bir URL gösterilmektedir.

![](media/desktop-data-sources/datasources_fromwebbox.png)

URL veya kaynak bağlantı bilgilerini girdikten sonra **Tamam**'ı seçin. Power BI Desktop veri kaynağı bağlantısını gerçekleştirir ve kullanabileceğiniz veri kaynaklarını **Gezgin** penceresinde görüntüler.

![](media/desktop-data-sources/datasources_fromnavigatordialog.png)

**Gezgin** bölmesinin alt kısmındaki **Yükle** düğmesini seçerek verileri yükleyebilir veya verileri yüklemeden önce sorguyu düzenlemek isterseniz **Düzenle** düğmesini seçebilirsiniz.

Power BI Desktop'ta veri kaynaklarına bağlanmak için tüm yapmanız gereken bu! Sayısı sürekli artan veri kaynaklarımızdaki verilere bağlanın ve veri kaynaklarımızın bulunduğu listeyi sık sık kontrol edin. Yeni veri kaynakları eklemeye devam edeceğiz.

## <a name="next-steps"></a>Sonraki adımlar
Power BI Desktop ile yapabileceğiniz pek çok şey vardır. Sunulan özellikler hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

* [Power BI Desktop ile Çalışmaya Başlama](desktop-getting-started.md)
* [Power BI Desktop ile Sorgulara Genel Bakış](desktop-query-overview.md)
* [Power BI Desktop'taki Veri Türleri](desktop-data-types.md)
* [Power BI Desktop'ta Verileri Şekillendirme ve Birleştirme](desktop-shape-and-combine-data.md)
* [Power BI Desktop'taki Genel Sorgu Görevleri](desktop-common-query-tasks.md)    

