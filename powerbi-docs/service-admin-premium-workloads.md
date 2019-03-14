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
ms.date: 03/11/2019
LocalizationGroup: Premium
ms.openlocfilehash: 0baab138ee98d2ec96bc9f47e6e727525a57ed3e
ms.sourcegitcommit: f176ba9d52d50d93f264eca21bb3fd987dbf934b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2019
ms.locfileid: "57757258"
---
# <a name="configure-workloads-in-a-premium-capacity"></a>Premium kapasitedeki iş yüklerini yapılandırma

Bu makalede, Power BI Premium kapasiteleri için iş yüklerini etkinleştirme ve yapılandırma açıklanmaktadır. Varsayılan olarak, kapasiteler yalnızca çalışan Power BI sorgularıyla ilişkili iş yüklerini destekler. Sorgu iş yükleri, Premium kapasite SKU’nuza göre belirlenen kaynaklar için iyileştirilmiştir ve bunlarla sınırlıdır. Premium kapasiteler ayrıca kapasite kaynaklarını kullanabilen ek iş yüklerini de destekler.

## <a name="configure-workloads"></a>İş yüklerini yapılandırma

AI, [Veri akışları](service-dataflows-overview.md#dataflow-capabilities-on-power-bi-premium) ve [Sayfalandırılmış raporlar](paginated-reports-save-to-power-bi-service.md) için ek iş yükleri etkinleştirebilir ve yapılandırabilirsiniz. Bu iş yükleri için varsayılan bellek değerleri, SKU’nuz için kullanılabilir kapasite düğümlerini temel alır. En yüksek bellek ayarları kümülatif değildir. Belirtilen en yüksek değere kadar bellek, AI ve veri akışları için dinamik olarak ayrılır ancak sayfalandırılmış raporlar için statik olarak ayrılır. 

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


## <a name="next-steps"></a>Sonraki adımlar

[Power BI Premium kapasite kaynak yönetimi ve en iyi duruma getirme](service-premium-understand-how-it-works.md)   
[Veri akışları ile Power BI’da self servis veri hazırlığı](service-dataflows-overview.md)   
[Power BI Premium’da sayfalandırılmış raporlar nelerdir?](paginated-reports-report-builder-power-bi.md)   

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)