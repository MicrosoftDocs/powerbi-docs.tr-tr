---
title: Power BI Rapor Sunucusu nedir?
description: SQL Server Reporting Services (SSRS) ve Power BI hizmetinin geri kalanı ile uyumunu anlamak için Power BI Rapor Sunucusu’na genel bir bakış elde edin.
author: maggiesMSFT
ms.author: maggies
keywords: ''
ms.date: 05/28/2020
ms.topic: overview
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.custom: mvc
ms.openlocfilehash: eba3038e654192ca0ae0ec381323762f80cf711a
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96397821"
---
# <a name="what-is-power-bi-report-server"></a>Power BI Rapor Sunucusu nedir?

Power BI Rapor Sunucusu, içinde rapor ve KPI’ları görüntüleyip yönettiğiniz bir web portalı olan, şirket içi bir rapor sunucusudur. Bu sunucuyla birlikte Power BI raporları, sayfalandırılmış raporlar, mobil raporlar ve KPI’lar oluşturan araçlar gelir. Kullanıcılarınız bu raporlara farklı yöntemlerle erişebilir: bir web tarayıcısı ya da mobil cihazdan veya gelen kutularında e-posta olarak görüntüleyerek.

![Power BI Rapor Sunucusu web portalını gösteren ekran görüntüsü.](media/get-started/power-bi-report-server-overview.png)

## <a name="comparing-power-bi-report-server"></a>Power BI Rapor Sunucusunu karşılaştırma 
Power BI Rapor Sunucusu hem SQL Server Reporting Services hem de Power BI çevrimiçi hizmetiyle benzerdir, ancak bu benzerlik farklı şekillerde görülür. Power BI hizmeti gibi Power BI Rapor Sunucusu da Power BI raporlarını (.pbix), Excel dosyalarını ve sayfalandırılmış raporları (.rdl) barındırır. Power BI Rapor Sunucusu, Reporting Services gibi şirket içidir. Power BI Rapor Sunucusu'nun özellikleri Reporting Services’in bir üst kümesidir: Reporting Services'de yapabileceğiniz her şeyi ve Power BI raporları desteğiyle birlikte daha fazlasını Power BI Rapor Sunucusu ile de yapabilirsiniz. Ayrıntılar için bkz. [Power BI Rapor Sunucusu ile Power BI hizmetini karşılaştırma](compare-report-server-service.md).

## <a name="licensing-power-bi-report-server"></a>Power BI Rapor Sunucusunu lisanslama
Power BI Rapor Sunucusu iki farklı lisansla sağlanır: [Power BI Premium](../admin/service-premium-what-is.md) ve Yazılım Güvencesi ile SQL Server Enterprise Edition. Ayrıntılar için bkz. [Microsoft Toplu Lisanslama](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=1&ShowArchived=True). Bir Power BI Premium lisansı ile bir karma dağıtım bulut ve şirket içi karışımı oluşturabilirsiniz.

Power BI raporlarını Power BI Rapor Sunucusu’nda yayımlarsanız bir Power BI Pro lisansa da ihtiyaç duyarsınız. Power BI Rapor Sunucusu’nda Power BI raporlarını görüntüleyip bunlarla etkileşim kurmak için Power BI Pro lisansına sahip olmanız gerekmez.

> [!NOTE]
> Power BI Premium için Power BI Rapor Sunucusu yalnızca P SKU’ları ile birlikte sunulur. EM SKU’larına dahil değildir.

## <a name="web-portal"></a>Web portalı
Power BI Rapor Sunucusu'nun giriş noktası, tüm güncel tarayıcılarda görüntüleyebileceğiniz güvenli bir web portalıdır. Buradan tüm raporlarınıza ve KPI'larınıza erişirsiniz. Web portalındaki içerik, geleneksel bir klasör hiyerarşisi halinde düzenlenir. Klasörlerinizde, içerik türe göre gruplandırılır: Power BI raporları, mobil raporlar, sayfalandırılmış raporlar, KPI’lar ve Excel çalışma kitapları. Paylaşılan veri kümeleri ve paylaşılan veri kaynakları raporlarınızın yapı taşı olarak kullanılmak üzere kendi klasörlerinde yer alır. Sık kullanılanları tek bir klasörde görüntülemek üzere etiketlersiniz. Ayrıca doğrudan web portalında KPI'lar oluşturursunuz. 

![Power BI Rapor Sunucusu web portalını gösteren bir dizüstü bilgisayarın yer aldığı fotoğraf.](media/get-started/web-portal.png)

İzinlerinize bağlı olarak, web portalındaki içeriği yönetebilirsiniz. Rapor işleme zamanlaması oluşturabilir, isteğe bağlı olarak raporlara erişebilir ve yayımlanan raporlara abone olabilirsiniz. Ayrıca, web portalınıza kendi özel [markalamanızı](/sql/reporting-services/branding-the-web-portal) uygulayabilirsiniz. 

[Power BI Rapor Sunucusu web portalı](/sql/reporting-services/web-portal-ssrs-native-mode) hakkında daha fazla bilgi.

## <a name="power-bi-reports"></a>Power BI raporları
Rapor sunucusu için en iyi duruma getirilmiş Power BI Desktop sürümü ile Power BI raporları (.pbix) oluşturabilirsiniz. Sonra bu raporları kendi ortamınızdaki web portalında yayımlayabilir ve görüntüleyebilirsiniz.

![Power BI Rapor Sunucusundaki Power BI raporları](media/get-started/powerbi-reports.png)

Power BI raporları, bir veri modelinden edinilen farklı bulguları ve öngörüleri temsil eden görselleştirmeler yardımıyla bu veri modeline ilişkin çok yönlü bir yaklaşım sunar.  Bir raporda tek bir görselleştirme olabilir veya rapor, görselleştirmelerle dolu sayfalardan oluşabilir. Rolünüze bağlı olarak, raporları okuyup keşfedebilir veya başkaları için raporlar oluşturabilirsiniz.

[Microsoft Power BI Desktop'ı yükleme](install-powerbi-desktop.md) hakkındaki yazıyı okuyun.

## <a name="paginated-reports"></a>Sayfalandırılmış raporlar
Sayfalandırılmış raporlar (.rdl), görseller içeren ve içindeki tabloların tüm verileri göstermek üzere yatay ve dikey yönde genişlediği, gerektiğinde sayfalara yayıldığı belge stili raporlardır. Bu raporlar, PDF ve Word dosyaları gibi yazdırma işlemi için en iyi duruma getirilmiş sabit düzenli, kusursuz kalitede belgeler oluşturmak için idealdir. 

![Power BI Rapor Sunucusundaki sayfalandırılmış raporlar](media/get-started/paginated-reports.png)

[SQL Server Veri Araçları'nda (SSDT)](/sql/reporting-services/tools/reporting-services-in-sql-server-data-tools-ssdt)[Rapor Oluşturucusu](/sql/reporting-services/report-builder/report-builder-in-sql-server-2016)'nu veya Rapor Tasarımcısı'nı kullanarak sayfalandırılmış raporlar oluşturabilirsiniz.

## <a name="reporting-services-mobile-reports"></a>Reporting Services mobil raporları
Mobil raporlar şirket içi verilere bağlanır ve farklı cihazlara ve cihazları nasıl tuttuğunuza göre uyum sağlayan farklı yöntemlere uyum sağlayan esnek bir düzene sahiptir. Bu raporları SQL Server Mobil Rapor Yayımcısı ile oluşturabilirsiniz.

[Reporting Services mobil raporları](/sql/reporting-services/mobile-reports/create-mobile-reports-with-sql-server-mobile-report-publisher) hakkında daha fazla bilgi. 

## <a name="report-server-programming-features"></a>Rapor Sunucusu programlama özellikleri
Özel uygulamalardaki veri ve rapor işleme süreçlerini tümleştirmeye veya genişletmeye yönelik API'lerle raporlarınızı genişletmek ve özelleştirmek için Power BI Rapor Sunucusu programlama özelliklerinden yararlanın.

Diğer [Rapor Sunucusu geliştirici belgeleri](/sql/reporting-services/reporting-services-developer-documentation).

## <a name="next-steps"></a>Sonraki adımlar
[Power BI Rapor Sunucusu'nu yükleme](install-report-server.md)  
[Rapor Oluşturucusu’nu indirme](https://www.microsoft.com/download/details.aspx?id=53613)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)