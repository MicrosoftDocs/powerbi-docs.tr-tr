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
ms.openlocfilehash: c84bebef5589ec391e3640ff3be674b1fb5a0ebd
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65564874"
---
# <a name="configure-workloads-in-a-premium-capacity"></a>Premium kapasitedeki iş yüklerini yapılandırma

Bu makalede, Power BI Premium kapasiteleri için iş yüklerini etkinleştirme ve yapılandırma açıklanmaktadır. Varsayılan olarak, kapasiteler yalnızca çalışan Power BI sorgularıyla ilişkili iş yüklerini destekler. **[AI (Bilişsel Hizmetler)](service-cognitive-services.md)** , **[Veri akışları](service-dataflows-overview.md#dataflow-capabilities-on-power-bi-premium)** ve **[Sayfalandırılmış raporlar](paginated-reports-save-to-power-bi-service.md)** için de ek iş yüklerini etkinleştirebilir ve yapılandırabilirsiniz.

## <a name="default-memory-settings"></a>Varsayılan bellek ayarları

Sorgu iş yükleri, Premium kapasite SKU’nuza göre belirlenen kaynaklar için iyileştirilmiştir ve bunlarla sınırlıdır. Premium kapasiteler ayrıca kapasitenizin kaynaklarını kullanabilen ek iş yüklerini de destekler. Bu iş yükleri için varsayılan bellek değerleri, SKU’nuz için kullanılabilir kapasite düğümlerini temel alır. En yüksek bellek ayarları kümülatif değildir. Belirtilen en yüksek değere kadar bellek, AI ve veri akışları için dinamik olarak ayrılır ancak sayfalandırılmış raporlar için statik olarak ayrılır. 

### <a name="microsoft-office-skus-for-software-as-a-service-saas-scenarios"></a>Hizmet olarak yazılım (SaaS) senaryoları için Microsoft Office SKU'ları

|                     | EM2                      | EM3                       | P1                      | P2                       | P3                       |
|---------------------|--------------------------|--------------------------|-------------------------|--------------------------|--------------------------|
| YAPAY ZEKA | YOK | YOK | % 20 varsayılan; en az %20 | %20 varsayılan; %10 en küçük | %20 varsayılan; %5 en küçük |
| Veri akışları | YOK |%20 varsayılan; %12 en küçük  | %20 varsayılan; %5 en küçük  | %20 varsayılan; %3 en küçük | %20 varsayılan; %2 en küçük  |
| Sayfalandırılmış raporlar | YOK |YOK | %20 varsayılan; %10 en küçük | %20 varsayılan; %5 en küçük | %20 varsayılan; %2,5 en küçük |
| | | | | | |

### <a name="microsoft-azure-skus-for-platform-as-a-service-paas-scenarios"></a>Hizmet olarak platform (PaaS) senaryoları için Microsoft Azure SKU'ları

|                  | A1                       | A2                       | A3                      | A4                       | A5                      | A6                        |
|-------------------|--------------------------|--------------------------|-------------------------|--------------------------|-------------------------|---------------------------|
| YAPAY ZEKA | YOK                      | % 20 varsayılan; en az %100                     | % 20 varsayılan; en az %50                     | % 20 varsayılan; en az %20 | %20 varsayılan; %10 en küçük | %20 varsayılan; %5 en küçük |
| Veri akışları         | %40 varsayılan; %40 en küçük | %24 varsayılan; %24 en küçük | %20 varsayılan; %12 en küçük | %20 varsayılan; %5 en küçük  | %20 varsayılan; %3 en küçük | %20 varsayılan; %2 en küçük   |
| Sayfalandırılmış raporlar | YOK                      | YOK                      | YOK                     | %20 varsayılan; %10 en küçük | %20 varsayılan; %5 en küçük | %20 varsayılan; %2,5 en küçük |
| | | | | | |

## <a name="workload-settings"></a>İş yükü ayarları

### <a name="ai-preview"></a>AI (Önizleme)

Ek olarak **en fazla bellek** ayarlama, yapay ZEKA iş yükü olan bir ek ayarı **kullanım Power BI Desktop'tan izin**. Varsayılan değer **kapalı**. Bu ayar, gelecekte kullanılmak üzere ayrılmıştır ve tüm kiracılar görünmeyebilir.

### <a name="datasets-preview"></a>Veri kümeleri (Önizleme)

Veri kümelerini iş yükü, varsayılan olarak etkinleştirilir ve devre dışı bırakılamaz. Bu iş yükünü içeren bir ek ayarı **XMLA bitiş noktası**. Varsayılan değer **1**, etkin anlamına gelir. Bu ayar, istemci uygulamalardan gelen bağlantıları ayarlayın çalışma ve uygulama düzeylerinde güvenlik grubu üyeliğine dikkate belirtir. Daha fazla bilgi için bkz. [istemci uygulamaları ve araçları ile veri kümelerine bağlanma](service-premium-connect-tools.md).

### <a name="dataflows"></a>Veri akışları

Ek olarak **en fazla bellek** ayarlama, veri akışlarını iş yükü bir ek ayarı sahip **kapsayıcı boyutu**. Bu ayar, daha karmaşık, bilgi işlem yoğun veri akışı işleme için veri akışı iş yükü performansı iyileştirmenize imkan sağlar.

Bir veri akışı yenilerken, veri akışı iş yükü veri akışı her varlık için bir kapsayıcı olarak çoğaltılır. Her kapsayıcı birimin adede kadar bellek kapsayıcı boyutu ayarında belirtilen alabilir. Tüm SKU'ları için varsayılan değer **700 MB**. Varsa bu ayarı değiştirmek isteyebilirsiniz:

- Veri akışlarını yenilemek için çok uzun sürdüğünü veya bir zaman aşımı veri akışı yenileme başarısız olur.
- Hesaplama adımlar, örneğin, bir birleştirme veri akışı varlıkları içerir.  

Bu kullanıcının kullanmanız önerilir [Power BI Premium kapasite ölçümleri](service-admin-premium-monitor-capacity.md) veri akışı iş yükü performansını analiz etmek için uygulama. 

Bazı durumlarda, kapsayıcı boyutu artırmayı performansını değil. Örneğin, veri akışı veri kaynağından yalnızca önemli hesaplamaları yapmadan hale geliyor, kapsayıcı boyutu büyük olasılıkla değiştirme yardımcı olmayacaktır. Veri akışı iş yükü, yenileme işlemlerini varlık için daha fazla bellek ayırmaya olanak tanır, kapsayıcı boyutu artırmayı yardımcı olabilir. Daha fazla bellek tahsis sağlayarak, yoğun olarak hesaplanan varlıkları yenilemek için gereken süreyi azaltabilir. 

Kapsayıcı boyutu değeri, veri akışlarını iş yükü için en fazla belleği aşamaz. Örneğin, 25 GB bellek bir P1 kapasiteye sahiptir. Veri akışı iş yükü en fazla bellek (%) ayarlanmış %20 5000 kapsayıcı boyutu (MB) aşamaz. Daha yüksek bir değere ayarlanmış olsa bile her durumda, kapsayıcı boyutu en fazla bellek aşamaz. 

### <a name="paginated-reports-preview"></a>Sayfalandırılmış raporlar (Önizleme)

Sayfalandırılmış raporlar, rapor oluşturma sırasında çalıştırmak özel kod izin verin. Örneğin, dinamik olarak içeriğine göre metin rengini değiştirmek, hangi ek bellek alabilir. Power BI Premium sayfalandırılmış raporları kapasite içinde kapsanan bir alanda çalıştırır. En fazla bellek belirtilen kullanılan *olup olmadığını* etkin iş yüküdür. Varsayılan, en fazla bellek ayarı değiştirmeden yaparsanız düşük ayarladığınızdan emin yeterince BT'nin diğer iş yüklerini olumsuz etkilemez.

Bazı durumlarda, sayfalandırılmış raporları iş yükü kullanılamaz hale gelebilir. Bu durumda, iş yükünün Yönetim Portalı'nda bir hata durumu gösterilir ve kullanıcılar için rapor işleme zaman aşımı bakın. Bu sorunu gidermek için iş yükü devre dışı bırakıp yeniden etkinleştirin.

## <a name="configure-workloads"></a>İş yüklerini yapılandırma

İş yüklerini yalnızca kullanılacakları zaman etkinleştirerek kapasitenizin kullanılabilir kaynaklarını en üst düzeye çıkarın. Bellek ayarlarını yalnızca belirlenmiş varsayılan ayarlarınızın kapasite kaynak gereksinimlerinizi karşılamadığı durumlarda değiştirin.  

### <a name="to-configure-workloads-in-the-power-bi-admin-portal"></a>Power BI yönetici portalında iş yüklerini yapılandırmak için

1. **Kapasite ayarları** > **PREMIUM KAPASİTELER** içinde, bir kapasite seçin.

1. **DİĞER SEÇENEKLER** altında **İş Yükleri**’ni genişletin.

1. Bir veya daha fazla iş yükünü etkinleştirin ve **En Büyük Bellek** için bir değer belirleyin.   

    
    ![İş yüklerini etkinleştirme](media/service-admin-premium-workloads/admin-portal-workloads.png)

1. **Uygula**'ya tıklayın.

### <a name="rest-api"></a>REST API

İş yükleri, [Kapasiteler](https://docs.microsoft.com/rest/api/power-bi/capacities) REST API’leri kullanılarak etkinleştirilebilir ve bir iş yüküne atanabilir.

## <a name="monitoring-workloads"></a>İş yüklerini izleme

[Power BI Premium Kapasite Ölçümleri uygulaması](service-admin-premium-monitor-capacity.md), kapasitelerinizde etkinleştirilmiş iş yüklerini izlemek için veri kümesi, veri akışları ve sayfalandırılmış rapor ölçümleri sağlar. 

## <a name="next-steps"></a>Sonraki adımlar

[Power BI Premium kapasiteleri en iyi duruma getirme](service-premium-capacity-optimize.md)     
[Veri akışları ile Power BI’da self servis veri hazırlığı](service-dataflows-overview.md)   
[Power BI Premium’da sayfalandırılmış raporlar nelerdir?](paginated-reports-report-builder-power-bi.md)   

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)