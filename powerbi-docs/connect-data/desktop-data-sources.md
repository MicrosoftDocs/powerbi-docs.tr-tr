---
title: Power BI Desktop'taki veri kaynakları
description: Power BI Desktop'taki veri kaynakları
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 08/12/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 1e64ca5c94b180cf98cf8d8992681861281ca2ae
ms.sourcegitcommit: b60063c49ac39f8b28c448908ecbb44b54326335
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/12/2020
ms.locfileid: "88160407"
---
# <a name="data-sources-in-power-bi-desktop"></a>Power BI Desktop'taki veri kaynakları

Power BI Desktop ile birçok farklı kaynaktaki verilere bağlanabilirsiniz. Kullanılabilir veri kaynaklarının tam listesi için bkz. [Power BI veri kaynakları](power-bi-data-sources.md).

**Giriş** şeridini kullanarak verilere bağlanırsınız. **En Yaygın** veri türleri menüsünü göstermek için **Veri Al** düğme etiketini veya aşağı oku seçin.

![Power BI Desktop’ta En Yaygın veri türleri menüsü, Veri Al](media/desktop-data-sources/data-sources-01.png)

**Veri Al** iletişim kutusuna gitmek için **En Yaygın** veri türleri menüsünü görüntüleyin ve **Diğer**’i seçin. Ayrıca **Veri Al** simgesini seçtiğinizde **En Yaygın** menüsünü atlayarak doğrudan **Veri Al** iletişim kutusunu görüntüleyebilirsiniz.

![Veri Al düğmesi, Power BI Desktop](media/desktop-data-sources/data-sources-02.png)

> [!NOTE]
> Power BI ekibi, Power BI Desktop ve Power BI hizmetinde kullanıma sunulan veri kaynaklarının sayısını sürekli olarak artırmaktadır. Bu nedenle, sık sık **Beta** veya **Önizleme** olarak işaretlenmiş veri kaynaklarıyla karşılaşırsınız. Bunlar, üzerinde çalışılmakta olan veri kaynaklarının ilk sürümleridir. **Beta** veya **Önizleme** olarak işaretlenen veri kaynakları için destek ve işlevsellik sınırlıdır. Bunlar, üretim ortamlarında kullanılmamalıdır. Ayrıca, Power BI Desktop için **Beta** veya **Önizleme** olarak işaretlenen herhangi bir veri kaynağı, genel olarak kullanılabilir (GA) hale gelene kadar Power BI hizmetinde veya diğer Microsoft hizmetlerinde kullanılamayabilir.

> [!NOTE]
> Birçok Power BI Desktop veri bağlayıcısı, kimlik doğrulaması için Internet Explorer 10 (veya daha yeni bir sürümü) uygulamasına ihtiyaç duyar. 


## <a name="data-sources"></a>Veri kaynakları

**Veri Al** iletişim kutusu veri türlerini şu kategorilerde düzenler:

* Tümü
* Dosya
* Veritabanı
* Power Platformu
* Azure
* Çevrimiçi Hizmetler
* Diğer

**Tümü** kategorisi, tüm kategorilerdeki bütün veri bağlantı türlerini içerir.

### <a name="file-data-sources"></a>Dosya veri kaynakları

**Dosya** kategorisinde, aşağıdaki veri bağlantıları sağlanır:

* Excel
* Metin/CSV
* XML
* JSON
* Klasör
* PDF
* SharePoint klasörü

Aşağıda, **Dosya** kategorisine ilişkin **Veri Al** penceresi gösterilmektedir.

![Dosya veri kaynakları, Veri Al iletişim kutusu, Power BI Desktop](media/desktop-data-sources/data-sources-03.png)

### <a name="database-data-sources"></a>Veritabanı veri kaynakları

**Veritabanı** kategorisinde aşağıdaki veri bağlantıları sağlanır:

* SQL Server veritabanı
* Access veritabanı
* SQL Server Analysis Services veritabanı
* Oracle veritabanı
* IBM Db2 veritabanı
* IBM Informix veritabanı (Beta)
* IBM Netezza
* MySQL veritabanı
* PostgreSQL veritabanı
* Sybase veritabanı
* Teradata veritabanı
* SAP HANA veritabanı
* SAP Business Warehouse Uygulama Sunucusu
* SAP Business Warehouse İleti Sunucusu
* Amazon Redshift
* Impala
* Google BigQuery
* Vertica
* Snowflake
* Essbase
* AtScale küpleri
* BI Bağlayıcısı 
* Data Virtuality LDW (Beta)
* Denodo
* Dremio
* Exasol
* Indexima (Beta)
* InterSystems IRIS (Beta)
* Jethro (Beta)
* Kyligence
* Linkar PICK Style / MultiValue Databases (Beta)
* MarkLogic

> [!NOTE]
> Bazı veri bağlayıcıları için **Dosya > Seçenekler ve ayarlar > Seçenekler** bölümüne gidip **Önizleme Özellikleri**'ni seçerek ilgili bağlayıcıyı etkinleştirmeniz gerekir. Yukarıda belirtilen bağlayıcılardan bazılarını görmüyorsanız söz konusu bağlayıcıları kullanmak için **Önizleme Özellikleri** ayarlarınızı kontrol edin. Ayrıca, *Beta* veya *Önizleme* olarak işaretlenen veri kaynakları için destek ve işlevselliğin sınırlı olduğunu ve bunların, üretim ortamlarında kullanılmaması gerektiğini unutmayın.

Aşağıda, **Veritabanı** kategorisine ilişkin **Veri Al** penceresi gösterilmektedir.

![Veritabanı veri kaynakları, Veri Al iletişim kutusu, Power BI Desktop](media/desktop-data-sources/data-sources-04.png)

### <a name="power-platform-data-sources"></a>Power Platform veri kaynakları

**Power Platform** kategorisinde aşağıdaki veri bağlantıları sağlanır:

* Power BI veri kümeleri
* Power BI veri akışları
* Common Data Service
* Power Platform veri akışları (Beta)

Aşağıdaki görüntüde **Power Platform** kategorisine ilişkin **Veri Al** penceresi gösterilmektedir.

![Power Platform veri kaynakları, Veri Al iletişim kutusu, Power BI Desktop](media/desktop-data-sources/data-sources-05.png)

### <a name="azure-data-sources"></a>Azure veri kaynakları

**Azure** kategorisinde, aşağıdaki veri bağlantıları sağlanır:

* Azure SQL Veritabanı
* Azure SQL Veri Ambarı
* Azure Analysis Services veritabanı
* PostgreSQL için Azure Veritabanı
* Azure Blob Depolama
* Azure Tablo Depolama
* Azure Cosmos DB
* Azure Veri Gezgini (Kusto)
* Azure Data Lake Storage Gen2
* Azure Data Lake Storage 1. Nesil
* Azure HDInsight (HDFS)
* Azure HDInsight Spark
* HDInsight Etkileşimli Sorgu
* Azure Veri Gezgini (Kusto)
* Azure Maliyet Yönetimi
* Azure Time Series Insights (Beta)


Aşağıda, **Azure** kategorisine ilişkin **Veri Al** penceresi gösterilmektedir.

![Azure veri kaynakları, Veri Al iletişim kutusu, Power BI Desktop](media/desktop-data-sources/data-sources-06.png)

### <a name="online-services-data-sources"></a>Çevrimiçi Hizmetler veri kaynakları

**Çevrimiçi Hizmetler** kategorisinde, aşağıdaki veri bağlantıları sağlanır:

* SharePoint Online Listesi
* Microsoft Exchange Online
* Dynamics 365 (çevrimiçi)
* Dynamics NAV
* Dynamics 365 Business Central
* Dynamics 365 Business Central (şirket içi)
* Microsoft Azure Consumption Insights (Beta)
* Azure DevOps (yalnızca Panolar)
* Azure DevOps Server (yalnızca Panolar)
* Salesforce Nesneleri
* Salesforce Raporları
* Google Analytics
* Adobe Analytics
* appFigures (Beta)
* Data.World - Veri Kümesi Al (Beta)
* GitHub (Beta)
* LinkedIn Satış Gezgini (Beta)
* Marketo (Beta)
* Mixpanel (Beta)
* Planview Enterprise One - PRM (Beta)
* QuickBooks Online (Beta)
* Smartsheet
* SparkPost (Beta)
* SweetIQ (Beta)
* Planview Enterprise One - CTM (Beta)
* Twilio (Beta)
* Zendesk (Beta)
* Asana (Beta)
* Dynamics 365 Customer Insights (Beta)
* Emigo Data Source
* Entersoft Business Suite (Beta)
* FactSet Analytics
* Palantir Foundry
* Industrial App Store
* Intune Veri Ambarı (Beta)
* Microsoft Graph Güvenliği (Beta)
* Power BI için Projectplace (Beta)
* Product Insights (beta)
* Quick Base
* TeamDesk (Beta)
* Webtrends Analytics (Beta)
* Witivio (Beta)
* Workplace Analytics (Beta)
* Zoho Creator (Beta)

Aşağıda, **Çevrimiçi Hizmetler** kategorisine ilişkin **Veri Al** penceresi gösterilmektedir.

![Çevrimiçi Hizmetler veri kaynakları, Veri Al iletişim kutusu, Power BI Desktop](media/desktop-data-sources/data-sources-07.png)

### <a name="other-data-sources"></a>Diğer veri kaynakları

**Diğer** kategorisinde, aşağıdaki veri bağlantıları sağlanır:

* Web
* SharePoint listesi
* OData Akışı
* Active Directory
* Microsoft Exchange
* Hadoop Dosyası (HDFS)
* Spark
* Hive LLAP (Beta)
* R betiği
* Python betiği
* ODBC
* OLE DB
* Solver
* FHIR
* Information Grid (Beta)
* Jamf Pro (Beta)
* Paxata
* QubolePresto (Beta)
* Roamler (Beta)
* Shortcuts Business Insights (Beta)
* Siteimprove
* Tenforce (Smart)List
* TIBCO(R) Veri Sanallaştırması (Beta)
* Vessel Insight (Beta)
* Workforce Dimensions (Beta)
* Zucchetti HR Infinity (Beta)
* Cognite Data Fusion (Beta)
* Power BI için MicroStrategy
* SurveyMonkey (Beta)
* Vena (Beta)
* Acterys: Model Automation & Planning (Beta)
* Automation Anywhere (Beta)
* Cherwell (Beta)
* Boş Sorgu




Aşağıda, **Diğer** kategorisine ilişkin **Veri Al** penceresi gösterilmektedir.

![Diğer veri kaynakları, Veri Al iletişim kutusu, Power BI Desktop](media/desktop-data-sources/data-sources-08.png)

> [!NOTE]
> Şu anda, güvenliği Azure Active Directory ile sağlanan özel veri kaynaklarına bağlanılamamaktadır.

## <a name="connecting-to-a-data-source"></a>Veri kaynağına bağlanma

Bir veri kaynağına bağlanmak için **Veri Al** penceresinde söz konusu veri kaynağını seçin ve ardından **Bağlan** seçeneğini belirleyin. Aşağıdaki görüntüde, **Diğer** veri bağlantısı kategorisinde yer alan **Web** seçeneği belirlenmiştir.

![Web’e bağlanma, Veri Al iletişim kutusu, Power BI Desktop](media/desktop-data-sources/data-sources-08.png)

Veri bağlantısının türüne özel bir bağlantı penceresi görüntülenir. Gerekli olması halinde kimlik bilgilerinizi girmeniz istenir. Aşağıdaki görüntüde, bir Web veri kaynağına bağlanmak için girilen bir URL gösterilmektedir.

![Giriş URL’si, Web’den iletişim kutusu, Power BI Desktop](media/desktop-data-sources/datasources-fromwebbox.png)

URL’yi veya kaynak bağlantısı bilgilerini girin ve **Tamam**’ı seçin. Power BI Desktop veri kaynağı bağlantısını gerçekleştirir ve kullanabileceğiniz veri kaynaklarını **Gezgin** penceresinde görüntüler.

![Gezgin iletişim kutusu, Power BI Desktop](media/desktop-data-sources/datasources-fromnavigatordialog.png)

Verileri yüklemek için, **Gezgin** bölmesinin alt kısmındaki **Yükle** düğmesini seçin. Verileri yüklemeden önce Power Query Düzenleyicisi’nde sorguyu dönüştürmek veya düzenlemek için **Veri Dönüştürme** düğmesini seçin.

Power BI Desktop'ta veri kaynaklarına bağlanmak için tüm yapmanız gereken bu! Sayısı sürekli artan veri kaynaklarımızdaki verilere bağlanın ve veri kaynaklarımızın bulunduğu listeyi sık sık kontrol edin. Yeni veri kaynakları eklemeye devam edeceğiz.

## <a name="using-pbids-files-to-get-data"></a>Verileri almak için PBIDS dosyalarını kullanma

PBIDS dosyaları, belirli bir yapısı olan ve Power BI veri kaynağı dosyası olarak tanımlanması için .PBIDS uzantısına sahip olan Power BI Desktop dosyalarıdır.

Kuruluşunuzda rapor oluşturanlara yönelik **Veri Al** deneyimini kolaylaştırmak için bir PBIDS dosyası oluşturabilirsiniz. Yeni bir rapor yazarının PBIDS dosyalarını kullanmasını kolaylaştırmak için, bir yöneticinin ortak kullanılan bağlantılarda bu dosyaları oluşturmasını öneririz.

Yazar PBIDS dosyasını açtığında Power BI Desktop açılır ve kullanıcıdan kimlik doğrulaması yapıp dosyada belirtilen veri kaynağına bağlanması için kimlik bilgileri istenir. **Gezinti** iletişim kutusu görüntülenir ve kullanıcının veri kaynağından modele yüklenecek tabloları seçmesi gerekir. PBIDS dosyasında belirtilmemişse, kullanıcıların veritabanlarını seçmesi de gerekebilir.

Bu noktadan itibaren kullanıcı görselleştirmeler oluşturmaya başlayabilir veya modele yeni bir tablo kümesi yüklemek için **Son Kaynaklar**’ı seçebilir.

Şu anda PBIDS dosyaları tek dosyada yalnızca bir veri kaynağını destekler. Birden fazla veri kaynağı belirtilmesi bir hatayla sonuçlanır.

Yönetici PBIDS dosyasını oluştururken, tek bağlantı için gerekli girişleri belirtmelidir. Ayrıca bağlantı modu olarak DirectQuery veya İçeri Aktarma’yı belirtebilir. Dosyada **mode** ayarı yoksa veya null ise, Power BI Desktop’ta dosyayı açan kullanıcıdan **DirectQuery** veya **İçeri Aktarma**’yı seçmesi istenir.

### <a name="pbids-file-examples"></a>PBIDS dosyası örnekleri

Bu bölümde, yaygın olarak kullanılan veri kaynaklarından bazı örnekler sağlanmaktadır. PBIDS dosya türü yalnızca Power BI Desktop’ta da desteklenen veri bağlantılarını destekler. Bunun yalnızca iki istisnası vardır: Live Connect ve Boş Sorgu.

PBIDS dosyası, kimlik doğrulaması bilgilerini ve tablo ve şema bilgilerini *içermez*.  

Aşağıda kod parçacıkları PBIDS dosyalarının birkaç yaygın örneğini gösterir ama bunlar eksiksiz veya kapsamlı değildir. Diğer veri kaynakları için, [Protokol ve adres bilgileri için Veri Kaynağı Başvurusu (DSR) biçimi](https://docs.microsoft.com/azure/data-catalog/data-catalog-dsr#data-source-reference-specification) bölümüne bakabilirsiniz.

Bu örnekler yalnızca kolaylık sağlamak için verilmiştir; tüm örnekleri kapsamaz ve DSR biçiminde desteklenen tüm bağlayıcıları içermez. Yöneticiler veya kuruluşlar kılavuz olarak bu örnekleri kullanarak kendi veri kaynaklarını oluşturabilir. Bu örnekler sayesinde kendi veri kaynağı dosyalarını oluşturup destekleyebilirler.

#### <a name="azure-as"></a>Azure AS

```json
{ 
    "version": "0.1", 
    "connections": [ 
    { 
        "details": { 
        "protocol": "analysis-services", 
        "address": { 
            "server": "server-here" 
        }, 
        } 
    } 
    ] 
}
```

#### <a name="folder"></a>Klasör

```json
{ 
  "version": "0.1", 
  "connections": [ 
    { 
      "details": { 
        "protocol": "folder", 
        "address": { 
            "path": "folder-path-here" 
        } 
      } 
    } 
  ] 
} 
```

#### <a name="odata"></a>OData

```json
{ 
  "version": "0.1", 
  "connections": [ 
    { 
      "details": { 
        "protocol": "odata", 
        "address": { 
            "url": "URL-here" 
        } 
      } 
    } 
  ] 
} 
```

#### <a name="sap-bw"></a>SAP BW

```json
{ 
  "version": "0.1", 
  "connections": [ 
    { 
      "details": { 
        "protocol": "sap-bw-olap", 
        "address": { 
          "server": "server-name-here", 
          "systemNumber": "system-number-here", 
          "clientId": "client-id-here" 
        }, 
      } 
    } 
  ] 
} 
```

#### <a name="sap-hana"></a>SAP Hana

```json
{ 
  "version": "0.1", 
  "connections": [ 
    { 
      "details": { 
        "protocol": "sap-hana-sql", 
        "address": { 
          "server": "server-name-here:port-here" 
        }, 
      } 
    } 
  ] 
} 
```

#### <a name="sharepoint-list"></a>SharePoint listesi

URL SharePoint sitesi içindeki bir listeyi değil, SharePoint sitesinin kendisini işaret etmelidir. Kullanıcılar, bu siteden bir veya daha fazla liste seçmesine olanak sağlayan bir gezgin alır. Bu listelerin her biri modelde bir tablo olur.

```json
{ 
  "version": "0.1", 
  "connections": [ 
    { 
      "details": { 
        "protocol": "sharepoint-list", 
        "address": { 
          "url": "URL-here" 
        }, 
       } 
    } 
  ] 
} 
```

#### <a name="sql-server"></a>SQL Server

```json
{ 
  "version": "0.1", 
  "connections": [ 
    { 
      "details": { 
        "protocol": "tds", 
        "address": { 
          "server": "server-name-here", 
          "database": "db-name-here (optional) "
        } 
      }, 
      "options": {}, 
      "mode": "DirectQuery" 
    } 
  ] 
} 
```

#### <a name="text-file"></a>Metin dosyası

```json
{ 
  "version": "0.1", 
  "connections": [ 
    { 
      "details": { 
        "protocol": "file", 
        "address": { 
            "path": "path-here" 
        } 
      } 
    } 
  ] 
} 
```

#### <a name="web"></a>Web

```json
{ 
  "version": "0.1", 
  "connections": [ 
    { 
      "details": { 
        "protocol": "http", 
        "address": { 
            "url": "URL-here" 
        } 
      } 
    } 
  ] 
} 
```

#### <a name="dataflow"></a>Veri akışı

```json
{
  "version": "0.1",
  "connections": [
    {
      "details": {
        "protocol": "powerbi-dataflows",
        "address": {
          "workspace":"workspace id (Guid)",
          "dataflow":"optional dataflow id (Guid)",
          "entity":"optional entity name"
        }
       }
    }
  ]
}
```

## <a name="next-steps"></a>Sonraki adımlar

Power BI Desktop ile her şeyi yapabilirsiniz. Özellikler hakkında daha fazla bilgi edinmek için aşağıdaki kaynaklara bakın:

* [Power BI Desktop nedir?](../fundamentals/desktop-what-is-desktop.md)
* [Power BI Desktop ile sorgulara genel bakış](../transform-model/desktop-query-overview.md)
* [Power BI Desktop'taki veri türleri](desktop-data-types.md)
* [Power BI Desktop'ta verileri şekillendirme ve birleştirme](desktop-shape-and-combine-data.md)
* [Power BI Desktop'taki genel sorgu görevleri](../transform-model/desktop-common-query-tasks.md)
