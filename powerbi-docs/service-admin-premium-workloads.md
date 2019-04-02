---
title: Power BI Premium’da iş yüklerini yapılandırma
description: Power BI Premium kapasitesinde iş yüklerini yapılandırmayı öğrenin.
author: minewiskan
ms.author: owend
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/01/2019
LocalizationGroup: Premium
ms.openlocfilehash: fbff4b744cf4a35f2fe1d0ae46f4676cd5f1db77
ms.sourcegitcommit: 8525b6365f3e224176730f4b8e5dae83f540a4ff
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58795257"
---
# <a name="configure-workloads-in-a-premium-capacity"></a>Premium kapasitedeki iş yüklerini yapılandırma

Bu makalede, Power BI Premium kapasiteleri için iş yüklerini etkinleştirme ve yapılandırma açıklanmaktadır. Varsayılan olarak, kapasiteler yalnızca çalışan Power BI sorgularıyla ilişkili iş yüklerini destekler. **[AI (Bilişsel Hizmetler)](service-cognitive-services.md)**, **[Veri akışları](service-dataflows-overview.md#dataflow-capabilities-on-power-bi-premium)** ve **[Sayfalandırılmış raporlar](paginated-reports-save-to-power-bi-service.md)** için de ek iş yüklerini etkinleştirebilir ve yapılandırabilirsiniz.

## <a name="default-memory-settings"></a>Varsayılan bellek ayarları

Sorgu iş yükleri, Premium kapasite SKU’nuza göre belirlenen kaynaklar için iyileştirilmiştir ve bunlarla sınırlıdır. Premium kapasiteler ayrıca kapasitenizin kaynaklarını kullanabilen ek iş yüklerini de destekler. Bu iş yükleri için varsayılan bellek değerleri, SKU’nuz için kullanılabilir kapasite düğümlerini temel alır. En yüksek bellek ayarları kümülatif değildir. Belirtilen en yüksek değere kadar bellek, AI ve veri akışları için dinamik olarak ayrılır ancak sayfalandırılmış raporlar için statik olarak ayrılır. 

### <a name="microsoft-office-skus-for-software-as-a-service-saas-scenarios"></a>Hizmet olarak yazılım (SaaS) senaryoları için Microsoft Office SKU'ları

|                     | EM2                      | EM3                       | P1                      | P2                       | P3                       |
|---------------------|--------------------------|--------------------------|-------------------------|--------------------------|--------------------------|
| AI (Bilişsel Hizmetler) | %20 varsayılan; en küçük TBD| %20 varsayılan; en küçük TBD | %20 varsayılan; en küçük TBD | %20 varsayılan; en küçük TBD | %20 varsayılan; en küçük TBD |
| Veri akışları | YOK |%20 varsayılan; %12 en küçük  | %20 varsayılan; %5 en küçük  | %20 varsayılan; %3 en küçük | %20 varsayılan; %2 en küçük  |
| Sayfalandırılmış raporlar | YOK |YOK | %20 varsayılan; %10 en küçük | %20 varsayılan; %5 en küçük | %20 varsayılan; %2,5 en küçük |
| | | | | | |

### <a name="microsoft-azure-skus-for-platform-as-a-service-paas-scenarios"></a>Hizmet olarak platform (PaaS) senaryoları için Microsoft Azure SKU'ları

|                  | A1                       | A2                       | A3                      | A4                       | A5                      | A6                        |
|-------------------|--------------------------|--------------------------|-------------------------|--------------------------|-------------------------|---------------------------|
| AI (Bilişsel Hizmetler) | YOK                      | %20 varsayılan; en küçük TBD                      | %20 varsayılan; en küçük TBD                     | %20 varsayılan; en küçük TBD | %20 varsayılan; en küçük TBD | %20 varsayılan; en küçük TBD |
| Veri akışları         | %40 varsayılan; %40 en küçük | %24 varsayılan; %24 en küçük | %20 varsayılan; %12 en küçük | %20 varsayılan; %5 en küçük  | %20 varsayılan; %3 en küçük | %20 varsayılan; %2 en küçük   |
| Sayfalandırılmış raporlar | YOK                      | YOK                      | YOK                     | %20 varsayılan; %10 en küçük | %20 varsayılan; %5 en küçük | %20 varsayılan; %2,5 en küçük |
| | | | | | |

## <a name="configure-workloads"></a>İş yüklerini yapılandırma

İş yüklerini yalnızca kullanılacakları zaman etkinleştirerek kapasitenizin kullanılabilir kaynaklarını en üst düzeye çıkarın. Bellek ayarlarını yalnızca belirlenmiş varsayılan ayarlarınızın kapasite kaynak gereksinimlerinizi karşılamadığı durumlarda değiştirin.  

### <a name="to-configure-workloads-in-the-power-bi-admin-portal"></a>Power BI yönetici portalında iş yüklerini yapılandırmak için

1. **Kapasite ayarları** > **PREMIUM KAPASİTELER** içinde, bir kapasite seçin.

1. **DİĞER SEÇENEKLER** altında **İş Yükleri**’ni genişletin.

1. Bir veya daha fazla iş yükünü etkinleştirin ve **En Büyük Bellek** için bir değer belirleyin.   

    
    ![İş yüklerini etkinleştirme](media/service-admin-premium-workloads/admin-portal-workloads.png)

1. **Uygula**'ya tıklayın.

> [!NOTE]
> Sayfalandırılmış raporlar iş yükünü etkinleştiriyorsanız, sayfalandırılmış raporlar bir raporu işlerken (örneğin, içeriğe göre metin rengini dinamik olarak değiştirme) kendi kodunuzu çalıştırmanıza olanak tanır. Power BI Premium sayfalandırılmış raporları kapasite içinde kapsanan bir alanda çalıştırır. İş yükünün etkin olup olmadığına bakılmaksızın, bu alana belirttiğiniz en büyük bellek kullanılır. Power BI raporlarını veya veri akışlarını aynı kapasitede kullanıyorsanız, sayfalandırılmış raporlar için diğer iş yüklerini olumsuz yönde etkilemeyecek kadar düşük bellek ayarladığınızdan emin olun. Nadir durumlarda sayfalandırılmış raporlar iş yükü kullanılamaz hale gelebilir. Böyle bir durumda iş yükü, yönetici portalında bir hata durumu gösterir ve kullanıcılar rapor işleme için zaman aşımı değerlerini görürler. Bu sorunu gidermek için iş yükünü devre dışı bırakın, sonra yeniden etkinleştirin.

### <a name="rest-api"></a>REST API

İş yükleri, [Kapasiteler](https://docs.microsoft.com/rest/api/power-bi/capacities) REST API’leri kullanılarak etkinleştirilebilir ve bir iş yüküne atanabilir.

## <a name="monitoring-workloads"></a>İş yüklerini izleme

[Power BI Premium Kapasite Ölçümleri uygulaması](service-admin-premium-monitor-capacity.md), kapasitelerinizde etkinleştirilmiş iş yüklerini izlemek için veri kümesi, veri akışları ve sayfalandırılmış rapor ölçümleri sağlar. 

## <a name="next-steps"></a>Sonraki adımlar

[Power BI Premium kapasite kaynak yönetimi ve en iyi duruma getirme](service-premium-understand-how-it-works.md)   
[Veri akışları ile Power BI’da self servis veri hazırlığı](service-dataflows-overview.md)   
[Power BI Premium’da sayfalandırılmış raporlar nelerdir?](paginated-reports-report-builder-power-bi.md)   

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)