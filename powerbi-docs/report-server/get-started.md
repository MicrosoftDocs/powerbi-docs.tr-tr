---
title: Power BI Rapor Sunucusu nedir?
description: SQL Server Reporting Services (SSRS) ve Power BI hizmetinin geri kalanı ile uyumunu anlamak için Power BI Rapor Sunucusu’na genel bir bakış elde edin.
services: powerbi
keywords: ''
author: maggiesMSFT
ms.author: maggies
ms.component: powerbi-report-server
ms.date: 05/07/2018
ms.topic: overview
ms.service: powerbi
manager: kfile
ms.custom: mvc
ms.openlocfilehash: 83220c399b527df421a14f9e45148feabc902ebb
ms.sourcegitcommit: c29525cbac2e747edb4dd3a1841084bb0ce42582
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33840109"
---
# <a name="what-is-power-bi-report-server"></a>Power BI Rapor Sunucusu nedir?

Power BI Rapor Sunucusu; Power BI raporları, sayfalandırılmış raporlar, mobil raporlar ve KPI’lar oluşturmaya yönelik araçlarla birlikte rapor ve KPI’ları görüntüleyip yönetebileceğiniz bir web portalı içeren, bir şirket içi rapor sunucusudur. Kullanıcılarınız bu raporlara farklı yöntemlerle erişebilir: bir web tarayıcısı ya da mobil cihazdan veya gelen kutularında e-posta olarak görüntüleyerek.

![Power BI Rapor Sunucusu web portalı](media/get-started/power-bi-report-server-overview.png)

## <a name="comparing-power-bi-report-server"></a>Power BI Rapor Sunucusunu karşılaştırma 
Power BI Rapor Sunucusu hem SQL Server Reporting Services hem de Power BI çevrimiçi hizmetiyle benzerdir, ancak bu benzerlik farklı şekillerde görülür. Power BI Rapor Sunucusu, Power BI hizmeti gibi Power BI raporlarını (.PBIX) ve Excel dosyalarını barındırır. Power BI Rapor Sunucusu, Reporting Services gibi şirket içidir ve sayfalandırılmış raporları (.RDL) barındırır. Power BI Rapor Sunucusu, Reporting Services’in bir üst kümesidir: Reporting Services ile yapabileceğiniz her şeyi ve Power BI raporları desteği eklendiğinde daha fazlasını Power BI Rapor Sunucusu ile de yapabilirsiniz. Ayrıntılar için bkz. [Power BI Rapor Sunucusu ile Power BI hizmetini karşılaştırma](compare-report-server-service.md).

## <a name="licensing-power-bi-report-server"></a>Power BI Rapor Sunucusunu lisanslama
Power BI Rapor Sunucusu iki farklı lisansla kullanılabilir: [Power BI Premium](../service-premium.md) ve Yazılım Güvencesi ile [SQL Server Enterprise Edition](https://www.microsoft.com/sql-server/sql-server-2017-editions). Bir Power BI Premium lisansı ile bir karma dağıtım bulut ve şirket içi karışımı oluşturabilirsiniz.  

## <a name="web-portal"></a>Web portalı
Power BI Rapor Sunucusu'nun giriş noktası, tüm güncel tarayıcılarda görüntüleyebileceğiniz güvenli bir web portalıdır. Buradan tüm raporlarınıza ve KPI'larınıza erişebilirsiniz. Web portalındaki içerik, geleneksel bir klasör hiyerarşisi halinde düzenlenir. Klasörlerinizdeki içerik, türe göre gruplandırılır: Power BI raporları, mobil raporlar, sayfalandırılmış raporlar, KPI'lar ve Excel çalışma kitapları, paylaşılan veri kümeleri ve raporlarınız için yapı taşı olarak kullanılabilecek paylaşılan veri kaynakları. Sık kullanılanları tek bir klasörde görüntülemek üzere etiketleyebilirsiniz. Ayrıca doğrudan web portalında KPI'ler oluşturabilirsiniz. 

![Power BI Rapor Sunucusu web portalı](media/get-started/web-portal.png)

İzinlerinize bağlı olarak, web portalındaki içeriği yönetebilirsiniz. Rapor işleme zamanlaması oluşturabilir, isteğe bağlı olarak raporlara erişebilir ve yayımlanan raporlara abone olabilirsiniz. Ayrıca, web portalınıza kendi özel [markalamanızı](https://docs.microsoft.com/sql/reporting-services/branding-the-web-portal) uygulayabilirsiniz. 

[Power BI Rapor Sunucusu web portalı](https://docs.microsoft.com/sql/reporting-services/web-portal-ssrs-native-mode) hakkında daha fazla bilgi.

## <a name="power-bi-reports"></a>Power BI raporları
Rapor sunucusu için en iyi duruma getirilmiş Power BI Desktop sürümü ile Power BI raporları (.PBIX) oluşturabilirsiniz. Sonra bu raporları kendi ortamınızdaki web portalında yayımlayıp görüntüleyebilirsiniz.

![Power BI Rapor Sunucusundaki Power BI raporları](media/get-started/powerbi-reports.png)

Power BI raporları, bir veri modelinden edinilen farklı bulguları ve öngörüleri temsil eden görselleştirmeler yardımıyla bu veri modeline ilişkin çok yönlü bir yaklaşım sunar.  Bir raporda tek bir görselleştirme olabilir veya rapor, görselleştirmelerle dolu sayfalardan oluşabilir. Rolünüze bağlı olarak, raporları okuyup keşfedebilir veya başkaları için raporlar oluşturabilirsiniz.

[Power BI Rapor Sunucusu için en iyi duruma getirilmiş Power BI Desktop uygulamasını](quickstart-create-powerbi-report.md) yükleyin.

## <a name="paginated-reports"></a>Sayfalandırılmış raporlar
Sayfalandırılmış raporlar (.RDL), görseller içeren ve içindeki tabloların tüm verileri göstermek üzere yatay ve dikey yönde genişlediği, gerektiğinde sayfalara yayıldığı belge stili raporlardır. Bu raporlar, PDF ve Word dosyaları gibi yazdırma işlemi için en iyi duruma getirilmiş sabit düzenli, kusursuz kalitede belgeler oluşturmak için idealdir.

![Power BI Rapor Sunucusundaki sayfalandırılmış raporlar](media/get-started/paginated-reports.png)

[SQL Server Veri Araçları'nda (SSDT)](https://docs.microsoft.com/sql/reporting-services/tools/reporting-services-in-sql-server-data-tools-ssdt) [Rapor Oluşturucusu](https://docs.microsoft.com/sql/reporting-services/report-builder/report-builder-in-sql-server-2016)'nu veya Rapor Tasarımcısı'nı kullanarak modern görünümlü raporlar oluşturabilirsiniz.

## <a name="reporting-services-mobile-reports"></a>Reporting Services mobil raporları
Mobil raporlar şirket içi verilere bağlanır ve farklı cihazlara ve cihazları nasıl tuttuğunuza göre uyum sağlayan farklı yöntemlere uyum sağlayan esnek bir düzene sahiptir. Bu raporları SQL Server Mobil Rapor Yayımcısı ile oluşturabilirsiniz.

[Reporting Services mobil raporları](https://docs.microsoft.com/sql/reporting-services/mobile-reports/create-mobile-reports-with-sql-server-mobile-report-publisher) hakkında daha fazla bilgi. 

## <a name="report-server-programming-features"></a>Rapor Sunucusu programlama özellikleri
Özel uygulamalardaki veri ve rapor işleme süreçlerini tümleştirmeye veya genişletmeye yönelik API'lerle raporlama işlevlerinizi genişletmek ve özelleştirmek için Power BI Rapor Sunucusu programlama özelliklerinden yararlanın.

Diğer [Rapor Sunucusu geliştirici belgeleri](https://docs.microsoft.com/sql/reporting-services/reporting-services-developer-documentation).

## <a name="next-steps"></a>Sonraki adımlar
[Power BI Rapor Sunucusu'nu yükleme](install-report-server.md)  
[Install Report Builder (Rapor Oluşturucusu'nu yükleme)](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)


