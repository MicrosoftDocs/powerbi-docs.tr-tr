---
title: Power BI'da DirectQuery tarafından desteklenen veri kaynakları
description: Hangi veri kaynaklarında DirectQuery'nin kullanabildiğini gösteren listeyi edinin.
author: davidiseminger
ms.author: davidi
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 04/10/2019
LocalizationGroup: Connect to data
ms.openlocfilehash: 3bb7de9685a1e0fc9fa423328ad9e1e5faa53603
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "61305467"
---
# <a name="data-sources-supported-by-directquery-in-power-bi"></a>Power BI'da DirectQuery tarafından desteklenen veri kaynakları

**Power BI Desktop** ve **Power BI hizmeti**, bağlanıp verilere erişebileceğiniz pek çok veri kaynağına sahiptir. Bu makalede hangi Power BI kaynaklarının **DirectQuery** olarak bilinen bağlantı yöntemini desteklediği açıklanmaktadır. DirectQuery hakkında daha fazla bilgi için [**Power BI'da DirectQuery**](desktop-directquery-about.md) başlıklı makaleye bakın.

Aşağıdaki veri kaynakları, Power BI'da DirectQuery'yi desteklemektedir:

* Amazon Redshift
* AtScale (Beta)
* Azure HDInsight Spark
* Azure SQL Veritabanı
* Azure SQL Veri Ambarı
* Google BigQuery
* HDInsight Etkileşimli Sorgu
* IBM DB2 veritabanı
* IBM Netezza
* Impala (2.x sürümü)
* Oracle Database (12 ve sonraki sürümler)
* Oracle Essbase
* SAP Business Warehouse Uygulama Sunucusu
* SAP Business Warehouse İleti Sunucusu
* SAP HANA
* Snowflake
* Spark (sürüm 0.9 ve üzeri)
* SQL Server
* Teradata Veritabanı
* Vertica

Adının yanında **(Beta)** veya **(Önizleme)** bulunan veri kaynakları, değişikliğe tabidir ve üretim ortamında kullanımları desteklenmez. Ayrıca bunlar, **Power BI hizmetinde** yayımlanan raporlarda da desteklenmeyebilir. Bu, yayımlanmış bir raporu açma veya veri kümesini araştırma işlemlerinin hatayla sonuçlanabileceği anlamına gelir.

**(Beta)** ile **(Önizleme)** veri kaynakları arasındaki tek fark, **(Önizleme)** kaynaklarının yalnızca Önizleme özelliği olarak etkinleştirildikten sonra kullanılabilmesidir. Bir **(Önizleme)** veri bağlayıcısını etkinleştirmek için **Power BI Desktop**'ta **Dosya > Seçenekler ve Ayarlar > Seçenekler** adımlarını izleyin ve ardından **Önizleme özellikleri** seçeneğini belirleyin.

> [!NOTE]
> SQL Server’a yönelik DirectQuery sorguları, erişimi oluşturmak için geçerli Windows kimlik doğrulaması kimlik bilgileri veya veritabanı kimlik bilgileri kullanılarak kimlik doğrulaması yapmayı gerektirir. Alternatif kimlik bilgileri desteklenmez.
>

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
| Spark (Beta), 0.9 ve sonraki sürümler |Evet |
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

