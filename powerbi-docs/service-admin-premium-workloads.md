---
title: Power BI Premium’da iş yüklerini yapılandırma
description: Power BI Premium kapasitesinde iş yüklerini yapılandırmayı öğrenin.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/15/2019
LocalizationGroup: Premium
ms.openlocfilehash: 49a1f02e5aa327c2704b6c2d789934a43b760ad0
ms.sourcegitcommit: 0e50ebfa8762e19286566432870ef16d242ac78f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/13/2019
ms.locfileid: "68962024"
---
# <a name="configure-workloads-in-a-premium-capacity"></a>Premium kapasitedeki iş yüklerini yapılandırma

Bu makalede, Power BI Premium kapasiteleri için iş yüklerini etkinleştirme ve yapılandırma açıklanmaktadır. Varsayılan olarak, kapasiteler yalnızca çalışan Power BI sorgularıyla ilişkili iş yüklerini destekler. **[AI (Bilişsel Hizmetler)](service-cognitive-services.md)**, **[Veri akışları](service-dataflows-overview.md#dataflow-capabilities-on-power-bi-premium)** ve **[Sayfalandırılmış raporlar](paginated-reports-save-to-power-bi-service.md)** için de ek iş yüklerini etkinleştirebilir ve yapılandırabilirsiniz.

## <a name="default-memory-settings"></a>Varsayılan bellek ayarları

Sorgu iş yükleri, Premium kapasite SKU’nuza göre belirlenen kaynaklar için iyileştirilmiştir ve bunlarla sınırlıdır. Premium kapasiteler ayrıca kapasitenizin kaynaklarını kullanabilen ek iş yüklerini de destekler. Bu iş yükleri için varsayılan bellek değerleri, SKU’nuz için kullanılabilir kapasite düğümlerini temel alır. En yüksek bellek ayarları kümülatif değildir. Belirtilen en yüksek değere kadar bellek, AI ve veri akışları için dinamik olarak ayrılır ancak sayfalandırılmış raporlar için statik olarak ayrılır.

### <a name="microsoft-office-skus-for-software-as-a-service-saas-scenarios"></a>Hizmet olarak yazılım (SaaS) senaryoları için Microsoft Office SKU'ları

|                     | EM2                      | EM3                       | P1                      | P2                       | P3                       |
|---------------------|--------------------------|--------------------------|-------------------------|--------------------------|--------------------------|
| AI | YOK | YOK | %20 varsayılan; %20 en küçük | %20 varsayılan; %10 en küçük | %20 varsayılan; %5 en küçük |
| Veri akışları | YOK |%20 varsayılan; %12 en küçük  | %20 varsayılan; %5 en küçük  | %20 varsayılan; %3 en küçük | %20 varsayılan; %2 en küçük  |
| Sayfalandırılmış raporlar | YOK |YOK | %20 varsayılan; %10 en küçük | %20 varsayılan; %5 en küçük | %20 varsayılan; %2,5 en küçük |
| | | | | | |

### <a name="microsoft-azure-skus-for-platform-as-a-service-paas-scenarios"></a>Hizmet olarak platform (PaaS) senaryoları için Microsoft Azure SKU'ları

|                  | A1                       | A2                       | A3                      | A4                       | A5                      | A6                        |
|-------------------|--------------------------|--------------------------|-------------------------|--------------------------|-------------------------|---------------------------|
| AI | YOK                      | %20 varsayılan; %100 en küçük                     | %20 varsayılan; %50 en küçük                     | %20 varsayılan; %20 en küçük | %20 varsayılan; %10 en küçük | %20 varsayılan; %5 en küçük |
| Veri akışları         | %40 varsayılan; %40 en küçük | %24 varsayılan; %24 en küçük | %20 varsayılan; %12 en küçük | %20 varsayılan; %5 en küçük  | %20 varsayılan; %3 en küçük | %20 varsayılan; %2 en küçük   |
| Sayfalandırılmış raporlar | YOK                      | YOK                      | YOK                     | %20 varsayılan; %10 en küçük | %20 varsayılan; %5 en küçük | %20 varsayılan; %2,5 en küçük |
| | | | | | |

## <a name="workload-settings"></a>İş yükü ayarları

### <a name="ai-preview"></a>AI (Önizleme)

**En Yüksek Bellek** ayarına ek olarak AI iş yükünün bir ayarı daha vardır: **Power BI Desktop'tan kullanıma izin ver**. Varsayılan değeri **Kapalı**'dır. Bu ayar gelecekte kullanım için ayrılmıştır ve tüm kiracılarda görünmeyebilir.

### <a name="datasets-preview"></a>Veri kümeleri (Önizleme)

Varsayılan olarak Veri Kümeleri iş yükü etkindir ve devre dışı bırakılamaz. Bu iş yükü _XMLA uç noktası_ için ek bir ayar ve performansla ilgili bir dizi ayar içerir. Bu **XMLA Uç Noktası** ayarı istemci uygulamalarından gelen bağlantıların çalışma alanı ve uygulama düzeylerinde ayarlanan güvenlik grubu üyeliğini kabul edeceğini belirtir. Daha fazla bilgi için bkz. [İstemci uygulaması ve araçlarıyla veri kümelerine bağlanma](service-premium-connect-tools.md).

Performansla ilgili ayarlar aşağıdaki tabloda açıklanır.

| Ayar Adı | Açıklama | Kullanım |
|---------------------------------|----------------------------------------|----------------------------------------|
| **En Fazla Ara Satır Sayısı** | DirectQuery tarafından döndürülen ara satır sayısı üst sınırı. Varsayılan değer 1000000 olarak ayarlanır ve izin verilen değerler 100000 ile 2147483647 arasındadır | Yoğun kaynak kullanılan veya kötü tasarlanmış raporların etkisini denetim altına alır. |
| **En Büyük Çevrimdışı Veri Kümesi Boyutu (GB)** | Bellekteki çevrimdışı veri kümesinin boyut üst sınırı. Bu, diskteki sıkıştırılmış boyuttur. Varsayılan değer SKU tarafından ayarlanır ve izin verilen değerler 0,1 – 10 GB aralığıdır | Rapor oluşturucularının kapasiteyi olumsuz etkileyebilecek büyük veri kümeleri yayımlamasını önler. |
| **En Büyük Sonuç Satır Kümesi Sayısı** | DAX sorgusunda döndürülen satır sayısı üst sınırını tanımlar. Varsayılan değer -1 (sınır yok) olarak ayarlanır ve izin verilen değerler 100000 ile 2147483647 arasındadır | Yoğun kaynak kullanılan veya kötü tasarlanmış raporların etkisini denetim altına alır. |
| **Sorgu Belleği Sınırı (%)** | Yalnızca DAX ölçülerine ve sorgularına uygulanır. % olarak belirtilir ve sorgu sırasında geçici sonuçlar tarafından kullanılabilecek bellek miktarını sınırlar. | Yoğun kaynak kullanılan veya kötü tasarlanmış raporların etkisini denetim altına alır. |
| **Sorgu Zaman Aşımı (saniye)** | Sorgular için saniye cinsinden zaman aşımını tanımlayan tamsayı. Varsayılan değer 3600 saniyedir (veya 60 dakika). Sıfır (0) değeri hiçbir sorgunun zaman aşımına uğramayacağını belirtir. | Uzun süre çalışan sorgularda daha iyi bir denetim sağlar. |
|  |  |  |

### <a name="dataflows"></a>Veri akışları

**En Yüksek Bellek** ayarına ek olarak, Veri Akışları iş yükünün bir ayarı daha (**Kapsayıcı boyutu**) vardır. Bu ayar daha karmaşık, yoğun işlem içeren veri akışlarını işlemek için veri akışı iş yükü performansını iyileştirmenize olanak tanır.

Veri akışı yenilenirken, veri akışı iş yükü veri akışındaki her varlık için bir kapsayıcı üretir. Her kapsayıcı, Kapsayıcı boyutu ayarında belirtilen miktara kadar bellek alabilir. Tüm SKU'larda varsayılan değer **700 MB**'tır. Aşağıdaki durumlarda bu ayarı değiştirmek isteyebilirsiniz:

- Veri akışlarının yenilenmesi fazla uzun sürüyor veya veri akışı yenilemesi zaman aşımından dolayı başarısız oluyor.
- Veri akışı varlıkları hesaplama adımları, örneğin birleştirme içeriyor.  

Veri akışı iş yükü performansını analiz etmek için [Power BI Premium Kapasite Ölçümleri](service-admin-premium-monitor-capacity.md) uygulamasını kullanmanız önerilir. 

Bazı durumlarda kapsayıcı boyutunu artırmak performansı geliştirmeyebilir. Örneğin, veri akışı önemli hesaplamalar yapmadan verileri yalnızca kaynaktan alıyorsa, kapsayıcı boyutu değiştirmek büyük olasılıkla işe yaramayacaktır. Kapsayıcı boyutunun artırılması, Veri Akışı iş yükünün varlık yenileme işlemlerine daha fazla bellek ayırmasına olanak tanıyorsa yararlı olur. Daha fazla bellek ayrılması, yoğun işlem içeren varlıkların yenilenmesi için gereken süreyi kısaltabilir.

Kapsayıcı Boyutu değeri, Veri Akışları iş yükü için en yüksek bellek miktarını aşamaz. Örneğin P1 kapasitenin 25 GB belleği vardır. Veri Akışı iş yükünün En Yüksek Bellek (%) değeri %20 olarak ayarlandıysa Kapsayıcı Boyutu (MB) 5000'i aşamaz. Her durumda, daha yüksek bir değer ayarlamış olsanız bile Kapsayıcı Boyutu En Yüksek Bellek miktarını aşamaz.

### <a name="paginated-reports-preview"></a>Sayfalandırılmış raporlar (Önizleme)

Sayfalandırılmış raporlar, bir raporu işlerken özel kodun çalıştırılmasına olanak tanır. Örneğin metin rengini içeriğe göre dinamik olarak değiştirme olabilir ve bu işlem ek bellek kullanabilir. Power BI Premium sayfalandırılmış raporları kapasite içinde kapsanan bir alanda çalıştırır. İş yükünün etkin *olup olmadığına* bakılmaksızın, belirtilen En Yüksek Bellek kullanılır. En Yüksek Bellek ayarının varsayılan değeri değiştiriliyorsa, bu değeri diğer iş yüklerini olumsuz etkilemeyecek kadar düşük ayarlamaya dikkat edin.

Bazı durumlarda Sayfalandırılmış Raporlar iş yükü kullanılamaz hale gelebilir. Böyle bir durumda iş yükü Yönetici portalında bir hata durumu gösterir ve kullanıcılar rapor işleme için zaman aşımı değerlerini görürler. Bu sorunu gidermek için iş yükünü devre dışı bırakın ve sonra yeniden etkinleştirin.

## <a name="configure-workloads"></a>İş yüklerini yapılandırma

İş yüklerini yalnızca kullanılacakları zaman etkinleştirerek kapasitenizin kullanılabilir kaynaklarını en üst düzeye çıkarın. Bellek ayarını ve diğer ayarları, ancak belirlenmiş varsayılan ayarlarınızın kapasite kaynak gereksinimlerinizi karşılamadığı durumlarda değiştirin.

### <a name="to-configure-workloads-in-the-power-bi-admin-portal"></a>Power BI yönetici portalında iş yüklerini yapılandırmak için

1. **Kapasite ayarları** > **PREMIUM KAPASİTELER** içinde, bir kapasite seçin.

1. **DİĞER SEÇENEKLER** altında **İş Yükleri**’ni genişletin.

1. Bir veya daha fazla iş yükünü etkinleştirin ve **En Büyük Bellek** için ve diğer ayarlar için değer belirleyin.

1. **Apply** (Uygula) seçeneğini belirleyin.

### <a name="rest-api"></a>REST API

İş yükleri, [Kapasiteler](https://docs.microsoft.com/rest/api/power-bi/capacities) REST API’leri kullanılarak etkinleştirilebilir ve bir iş yüküne atanabilir.

## <a name="monitoring-workloads"></a>İş yüklerini izleme

[Power BI Premium Kapasite Ölçümleri uygulaması](service-admin-premium-monitor-capacity.md), kapasitelerinizde etkinleştirilmiş iş yüklerini izlemek için veri kümesi, veri akışları ve sayfalandırılmış rapor ölçümleri sağlar. 

## <a name="next-steps"></a>Sonraki adımlar

[Power BI Premium kapasitelerini en iyi duruma getirme](service-premium-capacity-optimize.md)     
[Veri akışları ile Power BI’da self servis veri hazırlığı](service-dataflows-overview.md)   
[Power BI Premium’da sayfalandırılmış raporlar nelerdir?](paginated-reports-report-builder-power-bi.md)   

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)