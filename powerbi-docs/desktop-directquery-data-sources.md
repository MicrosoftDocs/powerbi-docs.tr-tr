---
title: "Power BI'da DirectQuery tarafından desteklenen veri kaynakları"
description: "Hangi veri kaynaklarında DirectQuery'nin kullanabildiğini gösteren listeyi edinin."
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.date: 03/09/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 2f395a5030cb2e025b8b69fa9b5375f471dea452
ms.sourcegitcommit: 4217430c3419046c3a90819c34f133ec7905b6e7
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="data-sources-supported-by-directquery-in-power-bi"></a>Power BI'da DirectQuery tarafından desteklenen veri kaynakları
**Power BI Desktop** ve **Power BI hizmeti**, bağlanıp verilere erişebileceğiniz pek çok veri kaynağına sahiptir. Bu makalede hangi Power BI kaynaklarının **DirectQuery** olarak bilinen bağlantı yöntemini desteklediği açıklanmaktadır. DirectQuery hakkında daha fazla bilgi için [**Power BI'da DirectQuery**](desktop-directquery-about.md) başlıklı makaleye bakın.

Aşağıdaki veri kaynakları, Power BI'da DirectQuery'yi desteklemektedir:

* Amazon Redshift
* Azure HDInsight Spark (Beta)
* Azure SQL Veritabanı
* Azure SQL Veri Ambarı
* Google BigQuery (Beta)
* IBM Netezza (Beta)
* Impala (2.x sürümü)
* Oracle Database (12 ve sonraki sürümler)
* SAP Business Warehouse Uygulama Sunucusu
* SAP Business Warehouse İleti Sunucusu (Beta)
* SAP HANA
* Snowflake
* Spark (Beta) (0.9 ve sonraki sürümler)
* SQL Server
* Teradata Veritabanı
* Vertica (Beta)

Adının yanında **(Beta)** veya **(Önizleme)** bulunan veri kaynakları, değişikliğe tabidir ve üretim ortamında kullanımları desteklenmez. Ayrıca bunlar, **Power BI hizmetinde** yayımlanan raporlarda da desteklenmeyebilir. Bu, yayımlanmış bir raporu açma veya veri kümesini araştırma işlemlerinin hatayla sonuçlanabileceği anlamına gelir.

**(Beta)** ile **(Önizleme)** veri kaynakları arasındaki tek fark, **(Önizleme)** kaynaklarının yalnızca Önizleme özelliği olarak etkinleştirildikten sonra kullanılabilmesidir. Bir **(Önizleme)** veri bağlayıcısını etkinleştirmek için **Power BI Desktop**'ta **Dosya > Seçenekler ve Ayarlar** seçeneğine gidin ve ardından **Ayarlar > Seçenekler > Önizleme özellikleri** seçeneğini belirleyin.

## <a name="on-premises-gateway-requirements"></a>Şirket içi ağ geçidi gereksinimleri
Aşağıdaki tabloda, **Power BI hizmetinde** bir rapor yayımladıktan sonra, belirtilen veri kaynağına bağlanmak için bir **şirket içi veri ağ geçidi** gerekip gerekmediği açıklanmaktadır.

| Kaynak | Ağ geçidi gerekli mi? |
| --- | --- |
| SQL Server |Evet |
| Azure SQL Veritabanı |Hayır |
| Azure SQL Veri Ambarı |Hayır |
| SAP HANA |Evet |
| Oracle Database |Evet |
| Teradata Veritabanı |Evet |
| Amazon Redshift |Hayır |
| Impala (2.x sürümü) |Evet |
| Snowflake |Evet |
| Spark (Beta), 0.9 ve sonraki sürümler |**Power BI hizmetinde** henüz desteklenmiyor |
| Azure HDInsight Spark (Beta) |Hayır |
| IBM Netezza |Evet |
| SAP Business Warehouse Uygulama Sunucusu |Evet |
| SAP Business Warehouse İleti Sunucusu |**Power BI hizmetinde** henüz desteklenmiyor |
| Google BigQuery |Hayır |


## <a name="next-steps"></a>Sonraki adımlar
DirectQuery hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

* [Power BI'da DirectQuery](desktop-directquery-about.md)
* [DirectQuery ve SAP HANA](desktop-directquery-sap-hana.md)
* [DirectQuery ve SAP BW](desktop-directquery-sap-bw.md)
* [Şirket içi veri ağ geçidi](service-gateway-onprem.md)

