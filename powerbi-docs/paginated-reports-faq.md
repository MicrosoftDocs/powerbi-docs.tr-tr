---
title: 'Power BI’daki sayfalandırılmış raporlar: SSS (Önizleme)'
description: Bu makalede sayfalandırılmış raporlar hakkında sık sorulan sorular yanıtlanır. Bu raporlar, üst düzeyde biçimlendirilmiş, yazdırma veya PDF oluşturma için iyileştirilmiş mükemmel çıkışlardır.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: report-builder
ms.topic: overview
ms.date: 11/05/2018
ms.author: maggies
ms.openlocfilehash: d3fdf9b568aa13ba5a8437c684835e0fce803d19
ms.sourcegitcommit: bb4cf3469b44e451153c469725a9069dcd548809
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2018
ms.locfileid: "53649457"
---
# <a name="paginated-reports-in-power-bi-faq-preview"></a>Power BI’daki sayfalandırılmış raporlar: SSS (Önizleme)

Bu makalede sayfalandırılmış raporlar hakkında sık sorulan sorular yanıtlanır. Bu raporlar, üst düzeyde biçimlendirilmiş, yazdırma veya PDF oluşturma için iyileştirilmiş mükemmel çıkışlardır. "Sayfalandırılmış" olarak adlandırılmalarının nedeni, birden çok sayfaya düzgün yerleştirilecek şekilde biçimlendirilmiş olmalarıdır. Sayfalandırılmış raporlar, SQL Server Reporting Services’in RDL rapor teknolojisini temel alır. 

Bu makalede Power BI Premium'daki sayfalandırılmış raporlar hakkında ve sayfalandırılmış raporları yazmak için kullanılan tek başına Rapor Oluşturucusu aracı hakkında kullanıcıların sorduğu en yaygın sorular yanıtlanır. Hizmette bir rapor yayımlamak için Power BI Pro lisansı gereklidir. Sayfalandırılmış raporları Çalışma Alanım bölümünüzde veya Power BI Premium kapasitesi içindeki uygulama çalışma alanlarında yayımlayıp paylaşabilirsiniz. 

## <a name="administration"></a>Yönetim

### <a name="what-size-premium-capacity-do-i-need-for-paginated-reports"></a>Sayfalandırılmış raporlar için hangi boyutta Premium kapasite gerekiyor?

Sayfalandırılmış raporlar iş yükü, genel önizleme için P1 – P3 SKU'larında sağlanır.  Ayrıca A4 – A6 SKU'larıyla test/geliştirme senaryoları için kullanabilirsiniz.

### <a name="what-is-the-maximum-memory-threshold-i-can-put-for-paginated-reports-in-my-capacity"></a>Kapasiteme sayfalandırılmış raporlar için ekleyebileceğim bellek eşiği üst sınırı nedir?

Şu anda, bu iş yükü için belleğin yalnızca %50'sini ayırabilirsiniz. 

### <a name="how-does-user-access-work-for-paginated-reports"></a>Sayfalandırılmış raporlarda kullanıcı erişimi nasıl çalışır?

Sayfalandırılmış raporlar için kullanıcı erişimi Power BI hizmetindeki tüm diğer içeriğin kullanıcı erişimiyle aynıdır 

### <a name="how-do-i-turn-onoff-my-paginated-reports-workload"></a>Sayfalandırılmış raporlar iş yükümü nasıl açabilirim/kapatabilirim?

Kapasite yöneticisi, sayfalandırılmış raporlar iş yükünü kapasite yönetim portalı sayfasında etkinleştirebilir veya devre dışı bırakabilir.  

### <a name="how-can-i-monitor-usage-of-paginated-reports-in-my-tenant"></a>Kiracımda sayfalandırılmış raporların kullanımını nasıl izleyebilirim?

Office 365 denetim günlüklerinde bu rapor türünün kullanımı aşağıdaki olaylar altında ayrıntılarıyla verilir: 

- Power BI Raporunu görüntüleme
- Power BI raporunu silme
- Power BI raporunu oluşturma
- Power BI raporu indirme

Power BI raporları yerine sayfalandırılmış rapor olduğunu tanımlamak için ReportType alanında “PaginatedReport” değeri yer alır.

Ayrıca, denetim günlüklerinde sayfalandırılmış raporlar için aşağıdaki olaylar sağlanır:

- Ağ geçidine bağlanmış Power BI veri kümesi
- Power BI Veri Kaynağını keşfetme
- TakeOverDatasource

### <a name="can-i-monitor-this-workload-through-the-premium-capacity-monitoring-app"></a>Bu iş yükünü Premium Kapasite İzleme Uygulaması üzerinden izleyebilir miyim?

Evet, Power BI veri kümelerinizle aynı uygun ayrıntılarla yeni bir sekme olarak izleme sağlanıyor.

### <a name="do-i-need-a-pro-license-to-create-and-publish-paginated-reports"></a>Sayfalandırılmış raporları oluşturmak ve yayımlamak için Pro lisansına ihtiyacım var mı?

Evet. Pro lisansı olmadan raporları çalışma alanına yükleyemezsiniz. Pro lisansı olmadan Rapor Oluşturucusu'nu indirip deneyebilirsiniz ama oluşturduğunuz sayfalandırılmış raporları yayımlayamazsınız. 

### <a name="what-if-i-have-a-paginated-report-in-a-workspace-and-the-paginated-report-workload-is-turned-off"></a>Bir çalışma alanında sayfalandırılmış raporum varsa ve sayfalandırılmış rapor iş yükü kapatıldıysa ne olur?

Hata iletisi alırsınız ve iş yükü yeniden açılana kadar raporunuzu görüntüleyemezsiniz. Yine de çalışma alanından raporu silebilirsiniz.

### <a name="what-is-the-default-memory-for-each-of-the-premium-skus-supported-for-paginated-reports"></a>Sayfalandırılmış raporlar için desteklenen Premium SKU'lardan her birinin varsayılan belleği nedir?

Sayfalandırılmış raporlar için her Premium SKU'daki varsayılan bellek:

- **P1/A4**: %20 varsayılan; %10 en küçük
- **P2/A5**: %20 varsayılan; %5 en küçük
- **P3/A6**: %20 varsayılan; %2,5 en küçük

## <a name="general"></a>Genel

### <a name="when-should-i-use-a-paginated-report-vs-a-power-bi-report"></a>Ne zaman Power BI raporu yerine sayfalandırılmış rapor kullanmalıyım?

Sayfalandırılmış raporlar, üst düzeyde biçimlendirilmiş, yazdırma veya PDF oluşturma için iyileştirilmiş mükemmel çıkışlar gerektiren senaryolara çok uygundur.  Kar ve zarar beyanı, büyük olasılıkla sayfalandırılmış rapor olarak oluşturmak isteyebileceğiniz rapor türüne iyi bir örnektir.  

Power BI raporları, araştırma ve etkileşim için iyileştirilmiştir.  Farklı satış elemanlarının aynı rapordaki verileri kendi bölgelerine/sektörlerine/müşterilerine göre ayırmak ve sayılardaki değişimi görmek istedikleri bir satış raporu için Power BI raporu çok uygun olabilir.

### <a name="the-documentation-says-report-builder-is-the-preferred-authoring-tool-can-i-create-paginated-reports-in-sql-server-data-tools-for-power-bi"></a>Belgelerde, tercih edilen yazma aracının Rapor Oluşturucusu olduğu belirtilir. Power BI için SQL Server Veri Araçları'nda sayfalandırılmış raporlar oluşturabilir miyim?

Evet, ama Power BI hizmeti bir kerede tek bir öğeyi karşıya yüklemenize izin veriyor; dolayısıyla yazarların SQL Server Veri Araçları (SSDT) ile kullandığı senaryolardan çoğu henüz desteklenmiyor. Bu SSS bölümünün devamında sağlanan [desteklenmeyen özellikler listesini](#what-paginated-report-features-in-ssrs-arent-yet-supported-in-power-bi) gözden geçirin.  

### <a name="what-versions-of-report-builder-do-you-support"></a>Rapor Oluşturucusu'nun hangi sürümlerini destekliyorsunuz?

Raporlarınızı yazmak ve Power BI hizmetinde yayımlamak için SQL Server 2016 Rapor Oluşturucusu'nun en son sürümünü kullanın. [Microsoft İndirme Merkezi'nden Rapor Oluşturucusu'nu](https://www.microsoft.com/download/details.aspx?id=53613) yükleyin.

### <a name="how-do-i-move-existing-reports-i-have-saved-in-sql-server-reporting-services-to-power-bi"></a>SQL Server Reporting Services'e kaydettiğim mevcut raporları Power BI'a nasıl taşırım?

Sunucudan raporu indirmeniz ve ardından portal aracılığıyla Power BI'a yüklemeniz gerekir.  Şu anda bir geçiş aracı yoktur ama genel önizlemeyi tamamladıktan ve ürünler arasında doğru özellik eşliği düzeyini yakaladıktan sonra bir geçiş aracı oluşturmayı düşünüyoruz.

### <a name="can-i-open-reports-and-publish-directly-to-the-service"></a>Raporları açıp doğrudan hizmette yayımlayabilir miyim?

Bu noktada bunu yapamazsınız. Aynı Power BI Desktop ile yapabildiğiniz gibi, Rapor Oluşturucusu'ndan raporları açıp doğrudan hizmete yayımlama desteğini bir noktada ekleyeceğiz.

### <a name="what-paginated-report-features-in-ssrs-arent-yet-supported-in-power-bi"></a>SSRS'deki sayfalandırılmış rapor özelliklerinden hangileri henüz Power BI'da desteklenmiyor?

Şu anda, sayfalandırılmış raporlar şu öğeleri desteklemiyor:

- Paylaşılan veri kaynakları
- Paylaşılan veri kümeleri
- Alt raporlar
- Tıklama ve detaylandırma eylemleri
- Bağlantılı raporlar
- Yer imleri
- Bing harita katmanları
- Özel yazı tipleri

Geçiş/sıralama dışında Power BI hizmetinde desteklenmeyen bir özelliğe sahip bir dosyayı karşıya yüklemeyi denerseniz, hata iletisi alırsınız.

### <a name="what-data-sources-do-you-support-currently-for-paginated-reports"></a>Şu anda sayfalandırılmış raporlarda hangi veri kaynaklarını destekliyorsunuz?

Azure SQL Veritabanı'nı, SQL Server'ı ve şirket içi Ağ Geçidini kullanan hem SQL Server Analysis Services (SSAS) tabular (DAX) hem de çok boyutlu (MDX) modellerini destekliyoruz.

Ağ Geçidi üzerinden SSAS'ye erişirken, kimlik bilgileri depolanan kullanıcının Ağ Geçidi'nden çalışmak için SSAS'de yükseltilmiş izinlere ihtiyacı vardır.

### <a name="what-authentication-methods-do-you-support"></a>Hangi kimlik doğrulama yöntemlerini destekliyorsunuz?

Şu anda portalda veya ağ geçidinde veri kaynağıyla birlikte kullanıcı adı ve parola depolamanız gerekiyor.  Satır düzeyi güvenliği gibi öğeleri desteklemeye yönelik ek kimlik doğrulama yöntemleri önizlemenin sonraki aşamalarında sağlanacak.

### <a name="can-i-use-a-power-bi-dataset-as-a-data-source-for-my-paginated-report"></a>Sayfalandırılmış raporum için veri kaynağı olarak Power BI veri kümesini kullanabilir miyim?

Henüz kullanamazsınız, ama bu desteğin yakında sağlanması planlanıyor.

### <a name="can-i-use-stored-procedures-through-the-gateway"></a>Ağ Geçidi üzerinden saklı yordamları kullanabilir miyim?

Ağ Geçidi aracılığıyla bir saklı yordam kullanabilirsiniz ama saklı yordamın parametreleri varsa bazı senaryolarda sorunlarla karşılaşabilirsiniz.

### <a name="what-export-formats-are-available-for-my-report-in-the-power-bi-service"></a>Power BI hizmetinde raporum için hangi dışarı aktarma biçimleri kullanılabilir?

Microsoft Excel, Microsoft Word, Microsoft PowerPoint, PDF, .CSV, XML ve MHTML'ye aktarabilirsiniz.

### <a name="can-i-print-paginated-reports"></a>Sayfalandırılmış raporları yazdırabilir miyim?

Evet, Sayfalandırılmış Raporlar için yeni ve geliştirilmiş baskı önizleme deneyimiyle yazdırma olanağı sağlanır. 

### <a name="are-e-mail-subscriptions-available-yet-for-paginated-reports"></a>Sayfalandırılmış raporlar için e-posta abonelikleri sağlanıyor mu?

Hayır, bununla birlikte e-posta abonelikleri yakında sunulacaktır.

### <a name="what-features-from-ssrs-will-you-be-supporting-in-the-power-bi-service"></a>SSRS'den hangi özellikleri Power BI hizmetinde destekleyeceksiniz?

Senaryoların çoğu için özellik eşliği sağlamayı planlıyoruz ama SSRS ile Power BI'daki bazı şeylerin mevcut SSRS desenlerine uydurmak için değiştirilmeye çalışılması anlamlı olmayabilir.  Örneğin, Power BI'daki farklı izin modelleri geriye doğru SSRS ile eşlenemeyebilir.  Bu tür kararları vermek için müşterilerden ve iş ortaklarından gelecek geri bildirimleri bekleyeceğiz.

### <a name="can-i-run-custom-code-in-my-report"></a>Raporumda özel kod çalıştırabilir miyim?

Evet, SSRS'de yapabildiğiniz gibi raporlarınızda kod çalıştırabilme özelliğini destekliyoruz.

### <a name="does-this-mean-ssrs-is-going-away"></a>Bu SSRS'nin kullanımdan kaldırılacağı anlamına mı geliyor?

Kesinlikle hayır.  Bu yeni teklif müşterilere sayfalandırılmış raporları için bulut tabanlı bir seçenek sunuyor.  

### <a name="can-i-use-power-bi-embedded-to-embed-my-paginated-reports-into-an-app-im-hosting"></a>Sayfalandırılmış raporlarımı barındırdığım bir uygulamaya eklemek için Power BI Embedded'i kullanabilir miyim?

Mevcut Power BI API'leriyle bu senaryoyu desteklemeyi planlıyoruz ama bu senaryonun ne zaman sağlanacağı konusunda henüz bir zaman çerçevesi oluşturmadık.

### <a name="can-i-drill-through-from-a-power-bi-report-to-a-paginated-report"></a>Bir Power BI raporundan sayfalandırılmış rapora detaylandırma yapabilir miyim?

Henüz yapamazsınız, ama kesinlikle bu senaryoyu desteklemeyi planlıyoruz.

### <a name="can-i-share-my-paginated-report-content-through-a-power-bi-app"></a>Sayfalandırılmış rapor içeriğimi Power BI uygulaması üzerinden paylaşabilir miyim?

Şu anda sayfalandırılmış raporları tek tek portaldaki paylaşım eylemi aracılığıyla veya araç çubuğu üzerinden diğer kullanıcılarla paylaşabilirsiniz. Henüz bir uygulama içinde paylaşımı desteklemiyoruz ama yakında bu desteği sağlamanızı bekleyebilirsiniz. 

### <a name="will-other-report-specific-features-in-power-bi-like-pinning-to-report-tiles-to-dashboards-work-with-paginated-reports"></a>Rapor kutucuklarını panolara sabitleme gibi Power BI'daki rapora özgü diğer özellikler, sayfalandırılmış raporlarla da çalışacak mı?

Raporların hizmetteki önemli senaryoların aynılarını olabildiğince desteklemesini sağlamayı planlıyoruz.  İdeal koşullarda, bu raporları yazma aracı farklı olsa da, tüketicinin bakış açısından bunlar portaldaki listede yer alan raporlardan biri olacaktır. Nasıl oluşturuldukları önemli değil, gerçekleştirmeleri gereken işlevi gerçekleştirebilirler.  Bu özellik eşliğine iyi bir örnek olarak, planlanan açıklama desteği verilebilir. Bu özellik her rapor türünde biraz farklı çalışabilir ama her iki türde de açıklamaları kullanabileceksiniz.

### <a name="are-you-planning-to-create-a-new-authoring-tool-for-paginated-reports-in-the-power-bi-service--we-cant-do-everything-we-need-to-with-report-builder-today"></a>Power BI hizmetinde sayfalandırılmış raporlar için yeni bir yazma aracı oluşturmayı planlıyor musunuz?  Bugün Rapor Oluşturucusu ile ihtiyacımız olan her şeyi yapamıyoruz.

Power BI'daki sayfalandırılmış raporlarda en iyi araçları sağlamak için farklı seçenekleri gözden geçirmeye devam ediyoruz. 

### <a name="is-a-migration-tool-planned-so-ssrs-customers-can-move-their-existing-reports-and-assets-to-power-bi"></a>SSRS müşterilerinin mevcut raporlarıyla varlıklarını Power BI'a taşıyabilmelerini sağlayacak bir geçiş aracı planlanıyor mu?

İçeriğin Power BI'a otomatik bir yolla taşınmasına olanak tanıyacak seçenekleri değerlendiriyoruz ama bu özellik GA'ya kadar kullanıma sunulmayacak.

### <a name="will-i-ever-be-able-to-create-both-paginated-reports-and-power-bi-reports-in-a-single-authoring-tool"></a>Bir süre sonra tek bir yazma aracıyla hem sayfalandırılmış raporlar hem de Power BI raporları oluşturabilmemiz mümkün olacak mı?

Potansiyel olarak.  Şu anda bu senaryoya imkan tanımanın veya tek tek indirmeler/markalar yerine yazma araçlarını tek bir BI paketi olarak dağıtabilmenin yollarını arıyoruz.

### <a name="is-there-a-report-viewer-control-for-paginated-reports-in-the-power-bi-service"></a>Power BI hizmetinde sayfalandırılmış raporlar için bir rapor görüntüleyicisi denetimi var mı?

Hayır, şu anda bir rapor görüntüleyicisi denetimi yok.

### <a name="can-you-search-for-paginated-reports-from-the-new-home-experience-in-the-power-bi-service"></a>Power BI hizmetindeki yeni Giriş deneyiminden sayfalandırılmış raporlar için arama yapılabiliyor mu?

Hayır, şu anda Giriş'ten sayfalandırılmış raporlar için arama yapamazsınız.  Öte yandan, yeni Giriş deneyiminin diğer bölümlerinde bu raporları görebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

- [Rapor Oluşturucusu'nu Microsoft İndirme Merkezi'nden yükleme](https://www.microsoft.com/download/details.aspx?id=53613)
- [Öğretici: Sayfalandırılmış rapor oluşturma](paginated-reports-quickstart-aw.md)
