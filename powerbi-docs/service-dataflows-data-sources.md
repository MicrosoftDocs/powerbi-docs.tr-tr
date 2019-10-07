---
title: Power BI'da veri akışlarına bağlanmayı öğrenin
description: Power BI’da veri akışlarının nasıl çalıştığını öğrenin
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 09/20/2019
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: ae260e36d0ca7363a3b21242087813d951cf4983
ms.sourcegitcommit: b7a9862b6da940ddebe61bc945a353f91cd0e4bd
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71945801"
---
# <a name="connect-to-data-sources-for-power-bi-dataflows"></a>Power BI veri akışları için veri kaynaklarına bağlanma

Power BI veri akışlarıyla birçok farklı veri kaynağına bağlanarak yeni veri akışları oluşturabilir veya mevcut veri akışına yeni varlıklar ekleyebilirsiniz.

Bu makalede oluşturulabilecek veya veri akışlarına eklenebilecek birçok veri kaynağı listelenir ve bu veri kaynaklarını kullanarak söz konusu veri akışlarının nasıl oluşturulacağı açıklanır.

Veri akışlarını oluşturma ve kullanma işlemlerine genel bir bakış için, bkz. [Power BI'da veri akışlarını oluşturma ve kullanma](service-dataflows-create-use.md).

## <a name="create-a-dataflow-from-a-data-source"></a>Veri kaynağından veri akışı oluşturma

Verilere bağlanmak için, **Power BI hizmeti**'nde **+ Oluştur** menü öğesini seçin ve sonra da görüntülenen menüde **veri akışı** öğesini seçin. Bu seçildiğinde, Power BI hizmetinin tuvalinde aşağıdaki görüntü gösterilir. 

![Yeni veri akışı veya varlık ekleme](media/service-dataflows-data-sources/dataflows-data-sources_01.png)

Zaten veri akışınız varsa, aşağıda gösterildiği gibi **Varlık ekle**'yi seçerek veya veri akışı yazma aracında **Veri al**'ı seçerek veri akışınıza yeni varlıklar ekleyebilirsiniz.

![Mevcut veri akışına varlık ekleme](media/service-dataflows-data-sources/dataflows-data-sources_02.png)

Aşağıdaki görüntüde, veri akışı yazma aracının **Veri al** düğmesi gösterilir. 

![Ver Al düğmesini kullanarak varlık ekleme](media/service-dataflows-data-sources/dataflows-data-sources_03.png)


## <a name="data-sources-for-dataflows"></a>Veri akışları için veri kaynakları

Veri akışı yazma aracında **Veri Al**'ı seçerek kullanılabilir veri kaynaklarını görüntüleyebilirsiniz. Bu, aşağıdaki görüntüde gösterildiği gibi kategorileri ve veri kaynaklarını seçmeniz için bir iletişim kutusu görüntüler.


![Veri akışları için veri kategorilerini alma](media/service-dataflows-data-sources/dataflows-data-sources_04.png)

Veri akışlarının veri kaynakları, **Veri al** iletişim kutusunun üst kısmında gösterilen aşağıdaki kategoriler altında düzenlenmiştir:

* Tüm kategoriler
* Dosya
* Veritabanı
* Power BI
* Azure
* Çevrimiçi Hizmetler
* Diğer

**Tüm kategoriler** kategorisi, tüm kategorilerin tüm veri kaynaklarını içerir. 

**Dosya** kategorisi, veri akışları için aşağıdaki kullanılabilir veri bağlantılarını içerir:

* Erişim
* Excel
* JSON
* Metin/CSV
* XML

**Veritabanı** kategorisi, veri akışları için aşağıdaki kullanılabilir veri bağlantılarını içerir:

* IBM DB2 Veritabanı
* MySQL Veritabanı
* Oracle Database
* PostgreSQL Veritabanı
* SQL Server Veritabanı
* Sybase Veritabanı
* Teradata
* Vertica

**Power BI** kategorisi, veri akışları için aşağıdaki kullanılabilir veri bağlantılarını içerir:

* Power BI veri akışları

**Azure** kategorisi, veri akışları için aşağıdaki kullanılabilir veri bağlantılarını içerir:

* Azure Blobları
* Azure Veri Gezgini
* Azure SQL Veri Ambarı
* Azure SQL Veritabanı
* Azure Tabloları

**Çevrimiçi Hizmetler** kategorisi, veri akışları için aşağıdaki kullanılabilir veri bağlantılarını içerir:

* Amazon Redshift
* Uygulamalar için Common Data Service
* Microsoft Exchange Online
* Salesforce Nesneleri
* Salesforce Raporları
* SharePoint Online Listesi
* Smartsheet

**Diğer** kategorisi, veri akışları için aşağıdaki kullanılabilir veri bağlantılarını içerir:

* Active Directory
* OData
* SharePoint Listesi
* Web API'si
* Web sayfası
* Boş tablo
* Boş Sorgu


## <a name="connecting-to-a-data-source"></a>Veri kaynağına bağlanma

Bir veri kaynağına bağlanmak için, veri kaynağını seçin. İşlemin nasıl çalıştığını tek bir örnekle göstereceğiz ama veri akışları için tüm veri bağlantılarının işlemleri birbirine benzer. Farklı bağlayıcılar belirli kimlik bilgileri veya başka bilgiler gerektirebilir, ama akış benzer olur. Bizim örneğimizde, aşağıdaki görüntüde gösterildiği gibi **Çevrimiçi hizmetler** veri bağlantısı kategorisinden **Uygulamalar için Common Data Service** seçilir.

![Uygulamalar için Common Data Service'i seçin](media/service-dataflows-data-sources/dataflows-data-sources_05.png)

Seçilen veri bağlantısı için bir bağlantı penceresi görüntülenir. Gerekli olması halinde kimlik bilgilerinizi sağlamanız istenir. Aşağıdaki görüntüde, Uygulamalar için Common Data Service sunucusuna bağlanmak için bir Sunucu URL'sinin girildiği gösterilir.

![Veri bağlantıları için kimlik bilgileri veya URL'ler](media/service-dataflows-data-sources/dataflows-data-sources_06.png)

Sunucu URL'si veya kaynak bağlantısı bilgileri sağlandıktan sonra, **Oturum aç**'ı seçerek veri erişiminde kullanılacak kimlik bilgilerini girin ve **İleri**'yi seçin.

**Power Query Online** başlatılır, veri kaynağıyla bağlantı kurar ve ardından aşağıdaki görüntüde gösterildiği gibi **Gezgin** penceresinde bu veri kaynağındaki kullanılabilir tabloları gösterir.

![Gezgin penceresi veri kaynağındaki tabloları gösteriyor](media/service-dataflows-data-sources/dataflows-data-sources_07.png)

Sol bölmede her öğenin yanındaki onay kutusunu işaretleyerek yüklenecek tabloları ve verileri seçebilirsiniz. Verileri yüklemek için, **Gezgin** bölmesinin alt kısmındaki **Tamam** düğmesini seçin. Sorguları düzenleyebileceğiniz ve seçilen veriler üzerinde istediğiniz diğer dönüştürmeleri gerçekleştirebileceğiniz bir Power Query Online iletişim kutusu görüntülenir.

![Power Query Düzenleyicisi'nde sorguları düzenleme ve dönüştürme](media/service-dataflows-data-sources/dataflows-data-sources_08.png)

İşte bu kadar kolay. Diğer veri kaynakları da benzer akışlara sahiptir ve veri akışınıza getirdiğiniz verileri düzenlemek ve dönüştürmek için Power Query Online'ı kullanır.

## <a name="connecting-to-additional-data-sources"></a>Ek veri kaynaklarına bağlanma

Power BI veri akışları kullanıcı arabiriminde gösterilmeyen ama birkaç ek adımla desteklenen başka veri bağlayıcıları da vardır. 

Aşağıdaki adımları izleyerek, kullanıcı arabiriminde gösterilmeyen bir bağlayıcıya yönelik bağlantı oluşturabilirsiniz:

1. **Power BI Desktop**'ı açın ve **Veri Al**'ı seçin.
2. Aşağıdaki görüntüde gösterildiği gibi Power BI Desktop'ta **Power Query Düzenleyicisi**'ni açın, ilgili sorguya sağ tıklayın ve **Gelişmiş Düzenleyici**'yi açın. Burada, Gelişmiş Düzenleyici'de gösterilen M betiğini kopyalayabilirsiniz.

    ![Power BI Desktop'taki Gelişmiş Düzenleyici'den M betiğini kopyalayın](media/service-dataflows-data-sources/dataflows-data-sources_09.png) 

3. Power BI veri akışını açın ve aşağıdaki görüntüde gösterildiği gibi boş sorgu için **Veri al**'ı seçin.

    ![Veri akışı için boş bir sorgu oluşturma](media/service-dataflows-data-sources/dataflows-data-sources_10.png) 

4. Kopyalanan sorguyu veri akışı için boş sorguya yapıştırın.

    ![M betiğini düzenleyici penceresine kopyalayın](media/service-dataflows-data-sources/dataflows-data-sources_11.png) 

Bundan sonra, betiğiniz belirttiğiniz veri kaynağına bağlanır. 

Aşağıdaki listede, şu anda M sorgusunu kopyalayıp boş sorguya yapıştırarak kullanabileceğiniz bağlayıcılar gösterilir:

* Azure Analysis Services
* Adobe Analytics
* ODBC
* OLE DB
* Klasör
* SharePoint Online klasörü
* SharePoint klasörü
* Hadoop HDFS
* Azure HDInsight (HDFS)
* Hadoop dosyası HDFS
* Informix (beta)

Power BI veri akışlarında veri kaynaklarına bağlanmak için tüm yapmanız gereken bu.


## <a name="next-steps"></a>Sonraki Adımlar

Bu makalede veri akışları için hangi veri kaynaklarına bağlanabileceğiniz gösterildi. Aşağıdaki makalelerde, veri akışlarının yaygın kullanım senaryoları daha ayrıntılı olarak ele alınır. 

* [Power BI’da self servis veri hazırlığı](service-dataflows-overview.md)
* [Power BI’da veri akışları oluşturma ve kullanma](service-dataflows-create-use.md)
* [Power BI Premium'da hesaplanan varlıkları kullanma](service-dataflows-computed-entities-premium.md)
* [Şirket içi veri kaynakları ile veri akışlarını kullanma](service-dataflows-on-premises-gateways.md)
* [Power BI veri akışları için geliştirici kaynakları](service-dataflows-developer-resources.md)
* [Veri akışları ve Azure Data Lake tümleştirmesi (Önizleme)](service-dataflows-azure-data-lake-integration.md)

Power Query ve zamanlanmış yenileme hakkında daha fazla bilgi için şu makaleleri okuyabilirsiniz:
* [Power BI Desktop'ta sorgulara genel bakış](desktop-query-overview.md)
* [Zamanlanmış yenileme yapılandırma](refresh-scheduled-refresh.md)

Ortak Veri Modeli hakkında daha fazla bilgi için genel bakış makalesini okuyabilirsiniz:
* [Ortak Veri Modeli - genel bakış ](https://docs.microsoft.com/powerapps/common-data-model/overview)

