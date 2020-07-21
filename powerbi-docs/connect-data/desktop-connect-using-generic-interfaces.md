---
title: Power BI Desktop'ta genel arabirimleri kullanarak verilere bağlanma
description: Power BI Desktop'ta genel arabirimlerle farklı veri kaynaklarına bağlanmayı öğrenin
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 106b2e4f9b829190cff8269342c3239429b41f24
ms.sourcegitcommit: c83146ad008ce13bf3289de9b76c507be2c330aa
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2020
ms.locfileid: "86214742"
---
# <a name="connect-to-data-by-using-power-bi-desktop-generic-interfaces"></a>Power BI Desktop genel arabirimlerini kullanarak verilere bağlanma 

**Veri Al** penceresinde gösterildiği gibi, **Access veritabanlarından** **Zendesk** kaynaklarına kadar çeşitlilik gösteren yerleşik veri bağlayıcılarını kullanarak **Power BI Desktop**'ta çok sayıda veri kaynağına bağlanabilirsiniz. Ayrıca, **Power BI Desktop**’ta yerleşik olarak bulunan genel arabirimleri (**ODBC** veya **REST API’leri** gibi) kullanarak çok çeşitli *başka* veri kaynaklarına da bağlanabilir, bu sayede bağlantı seçeneklerinizi daha da genişletebilirsiniz.

![ODBC seçimini gösteren Veri Al iletişim kutusunun ekran görüntüsü.](media/desktop-connect-using-generic-interfaces/generic-data-interfaces_1.png)

## <a name="power-bi-desktop-data-interfaces"></a>Power BI Desktop veri arabirimleri
**Power BI Desktop**, belirli bir veri kaynağına bağlanmak için oluşturulmuş, sürekli büyüyen bir veri bağlayıcısı koleksiyonuna sahiptir. Örneğin, **SharePoint Listesi** veri bağlayıcısı, bağlantı sırasında, **SharePoint Listeleri** için tasarlanmış belirli alanlar ve destekleyici bilgiler sağlar ve bu durum, **Veri Al > Diğer...** (önceki görüntüde verilen) seçeneğini belirlediğinizde açılan penceredeki diğer veri kaynakları için de geçerlidir.

Ayrıca **Power BI Desktop**, aşağıdaki genel veri arabirimlerinden birini kullanarak **Veri Al** listelerinde tanımlanmayan veri kaynaklarına bağlanmanıza da olanak sağlar:

* **ODBC**
* **OLE DB**
* **OData**
* **REST API'leri**
* **R Betikleri**

Bu genel arabirimler tarafından sunulan bağlantı pencerelerinde uygun parametreleri sağlayarak **Power BI Desktop**'ta erişebileceğiniz ve kullanabileceğiniz veri kaynakları dünyası, önemli ölçüde büyümektedir.

Söz konusu genel arabirimler tarafından erişilebilen veri kaynaklarına ait listeleri aşağıdaki bölümlerde bulabilirsiniz.

**Power BI Desktop** ile kullanmak istediğiniz veri kaynağını bulamıyor musunuz? Power BI ekibinin [fikir ve istek listesine](https://ideas.powerbi.com/) fikrinizi gönderin.

## <a name="data-sources-accessible-through-odbc"></a>ODBC aracılığıyla erişilebilir veri kaynakları
**Power BI Desktop**'taki **ODBC** bağlayıcısı, yalnızca bir **Veri Kaynağı Adı (DSN)** veya *bağlantı dizesi* belirterek herhangi bir üçüncü taraf ODBC sürücüsünden veri içeri aktarmanıza olanak sağlar. Bir seçenek olarak, ODBC sürücüsüne yönelik olarak yürütmek için bir SQL deyimi de belirtebilirsiniz.

![DSN ve Gelişmiş seçeneklerini gösteren ODBC bağlayıcısı iletişim kutusunun ekran görüntüsü.](media/desktop-connect-using-generic-interfaces/generic-data-interfaces_2.png)

Aşağıdaki listede, **Power BI Desktop**'ın, genel **ODBC** arabirimini kullanarak bağlanabileceği veri kaynaklarına yönelik birkaç örnek verilmiştir.

| Power BI Desktop genel bağlayıcısı | Dış veri kaynağı | Daha fazla bilgi için bağlantı |
| --- | --- | --- |
| ODBC |Cassandra |[Cassandra ODBC sürücüsü](https://www.simba.com/drivers/cassandra-odbc-jdbc/) |
| ODBC |Couchbase DB |[Couchbase ve Power BI](https://powerbi.microsoft.com/blog/visualizing-data-from-couchbase-server-v4-using-power-bi/) |
| ODBC |DynamoDB |[DynamoDB ODBC sürücüsü](https://www.simba.com/drivers/dynamodb-odbc-jdbc/) |
| ODBC |Google BigQuery |[BigQuery ODBC sürücüsü](https://www.simba.com/drivers/bigquery-odbc-jdbc/) |
| ODBC |HBase |[HBase ODBC sürücüsü](https://www.simba.com/drivers/hbase-odbc-jdbc/) |
| ODBC |Hive |[Hive ODBC sürücüsü](https://www.simba.com/drivers/hive-odbc-jdbc/) |
| ODBC |IBM Netezza |[IBM Netezza bilgileri](https://www.ibm.com/support/knowledgecenter/SSULQD_7.2.1/com.ibm.nz.datacon.doc/c_datacon_plg_overview.html) |
| ODBC |Presto |[Presto ODBC sürücüsü](https://www.simba.com/drivers/presto-odbc-jdbc/) |
| ODBC |Project Online |[Project Online makalesi](desktop-project-online-connect-to-data.md) |
| ODBC |Progress OpenEdge |[Progress OpenEdge ODBC sürücüsü blog gönderisi](https://www.progress.com/blogs/connect-microsoft-power-bi-to-openedge-via-odbc-driver) |

## <a name="data-sources-accessible-through-ole-db"></a>OLE DB aracılığıyla erişilebilir veri kaynakları
**Power BI Desktop**'taki **OLE DB** bağlayıcısı, bir *bağlantı dizesi* belirterek herhangi bir üçüncü taraf OLE DB sürücüsündeki verileri içeri aktarmanıza olanak sağlar. Bir seçenek olarak, OLE DB sürücüsüne yönelik olarak yürütmek için bir SQL deyimi de belirtebilirsiniz.

![Bağlantı dizesi ve Gelişmiş seçeneklerini gösteren OLEDB bağlayıcı iletişim kutusunun ekran görüntüsü.](media/desktop-connect-using-generic-interfaces/generic-data-interfaces_3.png)

Aşağıdaki listede, **Power BI Desktop**'ın, genel **OLE DB** arabirimini kullanarak bağlanabileceği veri kaynaklarına yönelik birkaç örnek verilmiştir.

| Power BI Desktop genel bağlayıcısı | Dış veri kaynağı | Daha fazla bilgi için bağlantı |
| --- | --- | --- |
| OLE DB |SAS OLE DB |[OLE DB için SAS sağlayıcısı](https://support.sas.com/downloads/package.htm?pid=648) |
| OLE DB |Sybase OLE DB |[OLE DB için Sybase sağlayıcısı](http://infocenter.sybase.com/help/index.jsp?topic=/com.sybase.infocenter.dc35888.1550/doc/html/jon1256941734395.html) |

## <a name="data-sources-accessible-through-odata"></a>OData aracılığıyla erişilebilir veri kaynakları
**Power BI Desktop**'taki **OData** bağlayıcısı, **OData** URL'sini yazarak veya kopyalayarak herhangi bir **OData** URL'sindeki verileri içeri aktarmanıza olanak sağlar. Bu bağlantıları **OData Akışı** penceresindeki metin kutularına yazarak veya kopyalayarak birden çok URL parçası ekleyebilirsiniz.

![URL parçaları ve önizleme alanlarını gösteren OData Akışı iletişim kutusunun ekran görüntüsü.](media/desktop-connect-using-generic-interfaces/generic-data-interfaces_4.png)

Aşağıdaki listede, **Power BI Desktop**'ın, genel **OData** arabirimini kullanarak bağlanabileceği veri kaynaklarına yönelik birkaç örnek verilmiştir.

| Power BI Desktop genel bağlayıcısı | Dış veri kaynağı | Daha fazla bilgi için bağlantı |
| --- | --- | --- |
| OData |Çok yakında |OData veri kaynakları için sayfayı yakında tekrar ziyaret edin |

## <a name="data-sources-accessible-through-rest-apis"></a>REST API'leri aracılığıyla erişilebilir veri kaynakları
**REST API**'lerini kullanarak veri kaynaklarına bağlanabilir ve böylece **REST**'i destekleyen çeşitli veri kaynaklarındaki verileri kullanabilirsiniz.

![Veri kaynaklarını gösteren Sorgu iletişim kutusunun ekran görüntüsü.](media/desktop-connect-using-generic-interfaces/generic-data-interfaces_5.png)

Aşağıdaki listede, **Power BI Desktop**'ın, genel **REST API'leri** arabirimini kullanarak bağlanabileceği veri kaynaklarına yönelik birkaç örnek verilmiştir.

| Power BI Desktop genel bağlayıcısı | Dış veri kaynağı | Daha fazla bilgi için bağlantı |
| --- | --- | --- |
| REST API'leri |Couchbase DB |[Couchbase REST API'si bilgileri](https://powerbi.microsoft.com/blog/visualizing-data-from-couchbase-server-v4-using-power-bi/) |

## <a name="data-sources-accessible-through-r-script"></a>R Betiği aracılığıyla erişilebilir veri kaynakları
**R betiklerini** kullanarak veri kaynaklarına erişebilir ve bu verileri **Power BI Desktop**'ta kullanabilirsiniz.

![Yürütme betiğini gösteren R Betiği iletişim kutusunun ekran görüntüsü.](media/desktop-connect-using-generic-interfaces/r-scripts-2.png)

Aşağıdaki listede, **Power BI Desktop**'ın, genel **R betikleri** arabirimini kullanarak bağlanabileceği veri kaynaklarına yönelik birkaç örnek verilmiştir.

| Power BI Desktop genel bağlayıcısı | Dış veri kaynağı | Daha fazla bilgi için bağlantı |
| --- | --- | --- |
| R Betiği |SAS Dosyaları |[CRAN tarafından sunulan R betiği kılavuzu](https://cran.r-project.org/doc/manuals/R-data.html) |
| R Betiği |SPSS Dosyaları |[CRAN tarafından sunulan R betiği kılavuzu](https://cran.r-project.org/doc/manuals/R-data.html) |
| R Betiği |R İstatistik Dosyaları |[CRAN tarafından sunulan R betiği kılavuzu](https://cran.r-project.org/doc/manuals/R-data.html) |

## <a name="next-steps"></a>Sonraki adımlar
**Power BI Desktop**’ı kullanarak çok çeşitli türlerdeki veri kaynaklarına bağlanabilirsiniz. Veri kaynakları hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

* [Power BI Desktop nedir?](../fundamentals/desktop-what-is-desktop.md)
* [Power BI Desktop'ta Veri Kaynakları](desktop-data-sources.md)
* [Power BI Desktop'ta Verileri Şekillendirme ve Birleştirme](desktop-shape-and-combine-data.md)
* [Power BI Desktop'ta Excel çalışma kitaplarına bağlanma](desktop-connect-excel.md)   
* [Verileri doğrudan Power BI Desktop'a girme](desktop-enter-data-directly-into-desktop.md)   
