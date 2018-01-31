---
title: Power BI Rapor Sunucusu'ndaki yenilikler
description: "Power BI Rapor Sunucusu'ndaki yenilikler hakkında bilgi edinin. Önemli özelliklere yer verilen bu belge, yeni sürümlerle birlikte güncelleştirilmektedir."
services: powerbi
documentationcenter: 
author: markingmyname
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
ms.date: 10/31/2017
ms.author: maghan
ms.openlocfilehash: 2ac4efa4e1eff5099fa3732b0fa753b04941979e
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2018
---
# <a name="whats-new-in-power-bi-report-server"></a>Power BI Rapor Sunucusu'ndaki yenilikler
Power BI Rapor Sunucusu'ndaki yenilikler hakkında bilgi edinin. Önemli özelliklere yer verilen bu belge, yeni sürümlerle birlikte güncelleştirilmektedir.

Power BI Rapor Sunucusu'nu ve Power BI Rapor Sunucusu için en iyi duruma getirilmiş Power BI Desktop'ı indirmek için [On-premises reporting with Power BI Report Server (Power BI Rapor Sunucusu ile şirket içi raporlama)](https://powerbi.microsoft.com/report-server/) sayfasına gidin.

![ipucu](media/whats-new/fyi-tip.png "ipucu") Geçerli sürüm notları için bkz. [Power BI Rapor Sunucusu - Sürüm notları](release-notes.md).

İlgili "Yenilikler" bilgileri için aşağıdaki sayfalara bakın:

* [Power BI hizmetindeki yenilikler](../service-whats-new.md)
* [Power BI Desktop'taki yenilikler](../desktop-latest-update.md)
* [Power BI mobil uygulamalarındaki yenilikler](../mobile-whats-new-in-the-mobile-apps.md)
* [Power BI ekibi blogu](https://powerbi.microsoft.com/blog/)

## <a name="october-2017-release"></a>Ekim 2017 sürümü
### <a name="power-bi-report-data-sources"></a>Power BI raporu veri kaynakları
Power BI Rapor Sunucusu'ndaki Power BI raporları çeşitli veri kaynaklarına bağlanabilir. Verileri içeri aktarabilir, veri yenileme zamanlayabilir veya DirectQuery ya da SQL Server Analysis Services canlı bağlantısı kullanarak doğrudan sorgulayabilirsiniz. Zamanlanmış yenileme ve DirectQuery desteği sunan veri kaynaklarının listesi için bkz. "Power BI Rapor Sunucusu'ndaki Power BI raporu veri kaynakları".

### <a name="scheduled-data-refresh-for-imported-data"></a>İçeri aktarılan veriler için zamanlanmış veri yenileme
Power BI Rapor Sunucusu'nda canlı bağlantı veya DirectQuery yerine ekli bir model kullanarak Power BI raporlarındaki verileri güncel tutmak için zamanlanmış veri yenileme özelliğini kullanabilirsiniz. Ekli bir model ile verileri içeri aktarırsınız ve verilerin, özgün veri kaynağıyla bağlantısı kesilir. Verilerin güncel tutulması için güncelleştirilmesi gerekir ve bunu zamanlamış yenileme ile gerçekleştirebilirsiniz. "Power BI Rapor Sunucusu'ndaki Power BI raporları için zamanlanmış yenileme" hakkında daha fazla bilgi edinin.

### <a name="editing-power-bi-reports-from-the-server"></a>Power BI raporlarını sunucuda düzenleme
Power BI raporu (.pbix) dosyalarını sunucuda açıp düzenleyebilirsiniz ancak bu durumda, karşıya yüklediğiniz özgün dosyaya dönersiniz.  Başka bir deyişle **veriler sunucu tarafından yenilenmişse dosyayı ilk açtığınızda veriler yenilenmez**. Değişiklikleri görmek için dosyayı el ile yenilemeniz gerekir.

### <a name="large-file-uploaddownload"></a>Büyük dosyaları karşıya yükleme/indirme
SQL Server Management Studio'daki (SSMS) Rapor Sunucusu ayarlarında sınır 1 GB olarak belirtilmiş olsa da en fazla 2 GB boyutundaki dosyaları karşıya yükleyebilirsiniz.  Bu dosyalar veritabanında SharePoint'te olduğu gibi depolanır ve SQL Server kataloğu için özel bir yapılandırma gerekmez.  

### <a name="accessing-shared-datasets-as-odata-feeds"></a>Paylaşılan veri kümelerine OData akışı olarak erişme
Paylaşılan veri kümelerine Power BI Desktop'tan OData akışı ile erişebilirsiniz. Daha fazla bilgi için bkz. [Power BI Rapor Sunucusu'nda, paylaşılan veri kümelerine OData akışları olarak erişme](access-dataset-odata.md).

### <a name="scale-out"></a>Ölçeği genişletme
Bu sürüm, ölçeği genişletme desteği sunmaktadır. En iyi deneyim için yük dengeleyici kullanın ve sunucu benzeşimi oluşturun. Senaryonun henüz ölçeği genişletme için en iyi duruma getirilmediğini unutmayın. Bu nedenle, modellerin birden fazla düğümde çoğaltıldığını görebilirsiniz. Bu senaryo Ağ Yükü Dengeleyici ve kalıcı oturum desteği olmadan çalışacaktır. Ancak, bu durumda model N kez yüklendiği için düğümler arasında fazla bellek kullanımının yanı sıra model, istekler arasında yeni bir düğümle karşılaştığında akış yapılacağından bağlantılar arası performans düşüklüğü yaşanacaktır.  

### <a name="administrator-settings"></a>Yönetici ayarları
Yöneticiler sunucu grubunun SSMS Gelişmiş Özellikleri bölümünde aşağıdaki ayarları yapabilir:

* EnableCustomVisuals: True/False
* EnablePowerBIReportEmbeddedModels: True/False
* EnablePowerBIReportExportData: True/False
* MaxFileSizeMb: Varsayılan değer 1000'dir
* ModelCleanupCycleMinutes: Bellekteki modelleri çıkarmak için denetim sıklığı
* ModelExpirationMinutes: Son kullanılma zamanına bağlı olarak modelin süresinin dolması ve çıkarılması için beklenecek süre
* ScheduleRefreshTimeoutMinutes: Model başına izin verilen veri yenileme işlemi süresi. Bu süre varsayılan olarak iki saattir.  Kesin bir üst sınır yoktur.

**rsreportserver.config yapılandırma dosyası**

```
<Configuration>
  <Service>
    <PollingInterval>10</PollingInterval>
    <IsDataModelRefreshService>false</IsDataModelRefreshService>
    <MaxQueueThreads>0</MaxQueueThreads>
  </Service>
</Configuration>
```

### <a name="developer-api"></a>Geliştirici API'si
SSRS 2017 için yayımlanmış olan geliştirici API'si (REST API), Power BI Rapor Sunucusu için genişletilerek hem Excel dosyaları hem de .pbix dosyalarıyla çalışacak şekilde geliştirilmiştir. Olası kullanım senaryolarından biri sunucudaki dosyaları programlama yoluyla indirmek, yenilemek ve yeniden yayımlamaktır. Örneğin, bu, PowerPivot modellerine sahip Excel çalışma kitaplarını yenilemenin tek yoludur.

Daha büyük dosyalar için yeni bir API olduğunu ve bunun, Swagger'ın Power BI Rapor Sunucusu sürümünde güncelleştirileceğini unutmayın. 

### <a name="sql-server-analysis-services-ssas-and-the-power-bi-report-server-memory-footprint"></a>SQL Server Analysis Services (SSAS) ve Power BI Rapor Sunucusu bellek ayak izi
SQL Server Analysis Services (SSAS) artık Power BI Rapor Sunucusu içinde barındırılmaktadır. Bu durum zamanlanmış yenilemeye özgü değildir. SSAS hizmetinin barındırılması sayesinde rapor sunucusu bellek ayak izi önemli ölçüde genişletilebilir. AS.ini yapılandırma dosyası sunucu düğümleri üzerinde mevcuttur. Bu nedenle SSAS konusunda bilgi sahibiyseniz maksimum bellek sınırı ve diski önbelleğe alma gibi özellikler de dahil olmak üzere bu ayarları güncelleştirebilirsiniz. Ayrıntılar için bkz. [Analysis Services'deki sunucu özellikleri](https://docs.microsoft.com/sql/analysis-services/server-properties/server-properties-in-analysis-services).

### <a name="viewing-and-interacting-with-excel-workbooks"></a>Excel çalışma kitaplarını görüntüleme ve bunlarla etkileşim kurma
Excel ve Power BI, sektörde benzeri olmayan bir araç portföyü sunabilir. Bu iki uygulama bir arada kullanıldığında iş analistlerine verileri toplama, şekillendirme, çözümleme ve görsel olarak inceleme konusunda kolaylık sunar. İş kullanıcıları, Power BI raporlarını web portalında görüntülemenin yanı sıra Power BI Rapor Sunucusu'nda Excel çalışma kitaplarını görüntüleyerek tek noktadan kendilerine ait Microsoft BI içeriğini yayımlayabilir ve görüntüleyebilir.

[Power BI Rapor Sunucusu önizleme ortamınıza Office Online Server (OOS) eklemeye ilişkin adım adım yönergelerin sağlandığı bir kılavuz](excel-oos.md) yayımladık. Toplu Lisanslama hesabına sahip müşteriler OOS uygulamasını Toplu Lisanslama Hizmeti Merkezi'nden ücretsiz indirerek yalnızca görüntüleme işlevini kullanabilir. Kullanıcılar, yapılandırmanın ardından aşağıdaki koşulları karşılayan Excel çalışma kitaplarını görüntüleyebilir ve bunlarla etkileşim kurabilir:

* Dış veri kaynağı bağımlılıklarına sahip olmayan
* Dış SQL Server Analysis Services veri kaynağına yönelik bir canlı bağlantıya sahip olan
* PowerPivot veri modeline sahip olan

### <a name="support-for-new-table-and-matrix-visuals"></a>Yeni tablo ve matris görselleri için destek
Power BI Rapor Sunucusu artık yeni Power BI tablo ve matris görsellerini desteklemektedir. Bu görsellerle rapor oluşturmak için Power BI Desktop uygulamasının Ekim 2017 sürümünü kullanmanız gerekir. Bu sürümü Power BI Desktop (Haziran 2017) yan yana yükleyebilirsiniz. Power BI Desktop uygulamasının en güncel sürümü için [Power BI Rapor Sunucusu indirme sayfasında](https://powerbi.microsoft.com/report-server/) **Gelişmiş indirme seçenekleri**'ne tıklayın.

## <a name="june-2017"></a>Haziran 2017
* Power BI Rapor Sunucusu genel kullanıma (GA) sunuldu.

## <a name="may-2017"></a>Mayıs 2017
* Power BI Rapor Sunucusu Önizleme kullanıma sunuldu
* Power BI raporlarını şirket içi ortamda yayımlama olanağı
  * Özel görseller için destek
  * Daha fazla veri kaynağı için Analysis Services canlı bağlantı desteği yakında kullanıma sunulacaktır.
  * Power BI Mobil uygulaması Power BI Rapor Sunucusu'nda barındırılan Power BI raporlarını görüntüleyecek şekilde güncelleştirildi
* Yorumlar eklenerek raporlardaki işbirliği özellikleri geliştirildi

## <a name="next-steps"></a>Sonraki adımlar
[Power BI Rapor Sunucusu sürüm notları](release-notes.md)  
[Kullanıcı el kitabı](user-handbook-overview.md)  
[Yönetici el kitabı](admin-handbook-overview.md)  
[Hızlı Başlangıç: Power BI Rapor Sunucusu'nu yükleme](quickstart-install-report-server.md)  
[Install Report Builder (Rapor Oluşturucusu'nu yükleme)](https://docs.microsoft.com/sql/reporting-services/install-windows/install-report-builder)  
[Download SQL Server Data Tools (SSDT) (SQL Server Veri Araçlarını (SSDT) indirme)](http://go.microsoft.com/fwlink/?LinkID=616714)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)

