---
title: 'Power BI’daki sayfalandırılmış raporlar: SSS'
description: Bu makalede sayfalandırılmış raporlar hakkında sık sorulan sorular yanıtlanır. Bu raporlar, üst düzeyde biçimlendirilmiş, yazdırma veya PDF oluşturma için iyileştirilmiş mükemmel çıkışlardır.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.date: 02/09/2021
ms.openlocfilehash: 788f6cbd840b2c260b00033e27d39f56ed7ce964
ms.sourcegitcommit: 24887643bd3e1b3749ce325dc0ae407432d7fee4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100489843"
---
# <a name="paginated-reports-in-power-bi-faq"></a>Power BI’daki sayfalandırılmış raporlar: SSS 

[!INCLUDE [applies-to](../includes/applies-to.md)] [!INCLUDE [yes-service](../includes/yes-service.md)] [!INCLUDE [yes-paginated](../includes/yes-paginated.md)] [!INCLUDE [yes-premium](../includes/yes-premium.md)] [!INCLUDE [no-desktop](../includes/no-desktop.md)] 

Bu makalede sayfalandırılmış raporlar hakkında sık sorulan sorular yanıtlanır. Bu raporlar, üst düzeyde biçimlendirilmiş, yazdırma veya PDF oluşturma için iyileştirilmiş mükemmel çıkışlardır. "Sayfalandırılmış" olarak adlandırılmalarının nedeni, birden çok sayfaya düzgün yerleştirilecek şekilde biçimlendirilmiş olmalarıdır. Sayfalandırılmış raporlar, SQL Server Reporting Services’in RDL rapor teknolojisini temel alır. 

Bu makalede Power BI Premium'daki sayfalandırılmış raporlar hakkında ve sayfalandırılmış raporları yazmak için kullanılan tek başına Rapor Oluşturucusu aracı hakkında kullanıcıların sorduğu en yaygın sorular yanıtlanır. Hizmette bir rapor yayımlamak için Power BI Pro lisansı gereklidir. Sayfalandırılmış raporları Çalışma Alanım bölümünüzde veya Power BI Premium kapasitesi içindeki çalışma alanlarında yayımlayıp paylaşabilirsiniz. 

## <a name="administration"></a>Yönetim

### <a name="what-size-premium-capacity-do-i-need-for-paginated-reports"></a>Sayfalandırılmış raporlar için hangi boyutta Premium kapasite gerekiyor?

Sayfalandırılmış raporlar iş yükü P1 – P3 SKU'larında sağlanır.  Ayrıca A4 – A6 SKU'larıyla ekleme ve test/geliştirme senaryoları için kullanabilirsiniz.

> [!NOTE]
> Power BI son zamanlarda, şu anda önizleme aşamasında olan **Premium Gen2** adlı Premium 'un yeni bir sürümünü kullanıma sundu. **Premium Gen2**'de, sayfalandırılmış raporlar Iş yükü EM1-EM3 SKU 'Ları, P1-P3 SKU 'Ları ve a1-a6 SKU 'larında kullanılabilir.  Ayrıca, Premium Gen2 ve ayrıca genel önizlemede oluşturulan kullanıcı başına Premium ile Kullanıcı başına kullanılabilir. 
>
>Premium Gen2, Premium kapasitelerinin yönetimini basitleştirir ve yönetim yükünü azaltır. Daha fazla bilgi için bkz. [Power BI Premium 2. Nesil (önizleme)](../admin/service-premium-what-is.md#power-bi-premium-generation-2-preview).
>
>Power BI Embedded Gen2 geliştirmelerini gözden geçirmek için [Power BI Embedded 2. nesil](../developer/embedded/power-bi-embedded-generation-2.md)bölümüne bakın.

### <a name="what-is-the-maximum-memory-threshold-i-can-put-for-paginated-reports-in-my-capacity"></a>Kapasiteme sayfalandırılmış raporlar için ekleyebileceğim bellek eşiği üst sınırı nedir?

Bu iş yükü için %100 bellek kullanabilirsiniz.

### <a name="how-does-user-access-work-for-paginated-reports"></a>Sayfalandırılmış raporlarda kullanıcı erişimi nasıl çalışır?

Sayfalandırılmış raporlar için kullanıcı erişimi Power BI hizmetindeki tüm diğer içeriğin kullanıcı erişimiyle aynıdır 

### <a name="how-do-i-turn-onoff-my-paginated-reports-workload"></a>Sayfalandırılmış raporlar iş yükümü nasıl açabilirim/kapatabilirim?

Kapasite yöneticisi, sayfalandırılmış raporlar iş yükünü kapasite yönetim portalı sayfasında etkinleştirebilir veya devre dışı bırakabilir.  Varsayılan olarak, oluşturduğunuz tüm yeni kapasitelerde iş yükü açıktır ama siz ilk sayfalandırılmış raporunuzu karşıya yükleyene kadar bellek tüketmez.  

### <a name="how-can-i-monitor-usage-of-paginated-reports-in-my-tenant"></a>Kiracımda sayfalandırılmış raporların kullanımını nasıl izleyebilirim?

Denetim günlüklerinde bu rapor türünün kullanımı aşağıdaki olaylar altında ayrıntılarıyla verilir:

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

Sayfalandırılmış raporları, Premium Kapasitede olmaları koşuluyla Pro lisansı olmadan Çalışma Alanım’a yükleyebilirsiniz.  Diğer çalışma alanlarında içerik yazıp yayımlayabilmeniz için Pro lisansınız olması gerekir. Pro lisansınız olmasa da Power BI Rapor Oluşturucusu’nu kullanmanızı öneririz ancak Pro lisansınız olmadan oluşturduğunuz sayfalandırılmış raporları yayımlayamazsınız. 

### <a name="what-if-i-have-a-paginated-report-in-a-workspace-and-the-paginated-report-workload-is-turned-off"></a>Bir çalışma alanında sayfalandırılmış raporum varsa ve sayfalandırılmış rapor iş yükü kapatıldıysa ne olur?

Hata iletisi alırsınız ve iş yükü yeniden açılana kadar raporunuzu görüntüleyemezsiniz. Yine de çalışma alanından raporu silebilirsiniz.

### <a name="what-is-the-default-memory-for-each-of-the-premium-skus-that-support-paginated-reports"></a>Sayfalandırılmış raporları destekleyen Premium SKU’lardan her birine yönelik varsayılan bellek ne kadardır?

Sayfalandırılmış raporlar için her Premium SKU'daki varsayılan bellek:

- **P1/A4**: %20 varsayılan; %10 en küçük
- **P2/A5**: %20 varsayılan; %5 en küçük
- **P3/A6**: %20 varsayılan; %2,5 en küçük

Power BI yöneticileri en fazla bellek yüzdesini Yönetici portalından değiştirebilir. **Kapasite ayarları** sekmesindeki **Power BI Premium** seçeneğinde yer alan **Sayfalandırılmış Raporlar** iş yükü bölümüne bakın.

:::image type="content" source="media/paginated-reports-faq/paginated-reports-capacity-settings.png" alt-text="Sayfalandırılmış raporlar bölümündeki kapasite ayarları sekmesi":::

> [!NOTE]
> Şu anda önizleme aşamasında olan **Premium Gen2** bellek ayarlarını değiştirmenizi gerektirmez. Temeldeki sistem, Premium Gen2 'daki belleği otomatik olarak yönetir. Sayfalandırılmış raporlar iş yükü, **Premium Gen2**'teki P1-P3 SKU 'Ları ve a1-a6 SKU 'larında mevcuttur.

## <a name="general"></a>Genel

### <a name="when-should-i-use-a-paginated-report-vs-a-power-bi-report"></a>Ne zaman Power BI raporu yerine sayfalandırılmış rapor kullanmalıyım?

Sayfalandırılmış raporlar, üst düzeyde biçimlendirilmiş, yazdırma veya PDF oluşturma için iyileştirilmiş mükemmel çıkışlar gerektiren senaryolara çok uygundur.  Kar ve zarar beyanı, büyük olasılıkla sayfalandırılmış rapor olarak oluşturmak isteyebileceğiniz rapor türüne iyi bir örnektir.  

Power BI raporları, araştırma ve etkileşim için iyileştirilmiştir.  Farklı satış elemanlarının aynı rapordaki verileri kendi bölgelerine/sektörlerine/müşterilerine göre ayırmak ve sayılardaki değişimi görmek istedikleri bir satış raporu için Power BI raporu çok uygun olabilir.

Daha fazla bilgi için bkz. [Power BI’daki sayfalandırılmış raporları kullanma zamanı](../guidance/report-paginated-or-power-bi.md).

### <a name="the-documentation-says-power-bi-report-builder-is-the-preferred-authoring-tool-can-i-create-paginated-reports-in-sql-server-data-tools-for-power-bi"></a>Belgelerde tercih edilen yazma aracının Power BI Rapor Oluşturucusu olduğu belirtilir. Power BI için SQL Server Veri Araçları'nda sayfalandırılmış raporlar oluşturabilir miyim?

Evet oluşturabilirsiniz ancak Power BI hizmeti bir kerede tek bir öğeyi karşıya yüklemenize izin verir. Bu nedenle, yazarların SQL Server Veri Araçları (SSDT) ile kullandığı senaryoların çoğu henüz desteklenmiyor. Bu SSS bölümünün devamında sağlanan [desteklenmeyen özellikler listesini](#what-paginated-report-features-in-ssrs-arent-yet-supported-in-power-bi) gözden geçirin.  

### <a name="what-versions-of-report-builder-do-you-support"></a>Rapor Oluşturucusu'nun hangi sürümlerini destekliyorsunuz?

Power BI Rapor Oluşturucusu’nu, Power BI Hizmetinde sayfalandırılmış raporlar için birincil yazma aracı olarak yayımladık. [Power BI Rapor Oluşturucusu'nu Microsoft İndirme Merkezi'nden](https://aka.ms/pbireportbuilder) yükleyin.

### <a name="how-do-i-move-existing-reports-i-have-saved-in-sql-server-reporting-services-to-power-bi"></a>SQL Server Reporting Services'e kaydettiğim mevcut raporları Power BI'a nasıl taşırım?

GitHub'daki bir proje artık içeriğin SQL Server Reporting Services’ten Power BI’ya geçirilmesini desteklemektedir.  Buradan ayrıntıları görüntüleyin ve aracı indirin: [https://github.com/microsoft/RdlMigration](https://github.com/microsoft/RdlMigration)

### <a name="can-i-open-reports-and-publish-directly-to-the-service"></a>Raporları açıp doğrudan hizmette yayımlayabilir miyim?

Evet. Raporları açma ve Power BI Rapor Oluşturucusu’ndan doğrudan hizmette yayımlama desteği ekledik.

### <a name="what-paginated-report-features-in-ssrs-arent-yet-supported-in-power-bi"></a>SSRS’deki sayfalandırılmış rapor özelliklerinden hangileri henüz Power BI’da desteklenmiyor?

Şu anda, sayfalandırılmış raporlar şu öğeleri desteklemiyor:

- Paylaşılan veri kaynakları
- Paylaşılan veri kümeleri
- Detaylandırma ve tıklayarak diğer raporlara ulaşma
- Bağlantılı raporlar
- Özel yazı tipleri

Geçiş/sıralama dışında Power BI hizmetinde desteklenmeyen bir özelliğe sahip bir dosyayı karşıya yüklemeyi denerseniz, hata iletisi alırsınız.

### <a name="what-data-sources-do-you-support-currently-for-paginated-reports"></a>Şu anda sayfalandırılmış raporlarda hangi veri kaynaklarını destekliyorsunuz?

Veri kaynaklarının listesi için [Power BI sayfalandırılmış raporlarında desteklenen veri kaynakları](paginated-reports-data-sources.md) makalesine bakın. 

### <a name="what-authentication-methods-do-you-support"></a>Hangi kimlik doğrulama yöntemlerini destekliyorsunuz?

Azure Analysis Services, Azure SQL Veritabanı ve Power BI veri kaynakları için SSO’yu destekliyoruz.  Azure SQL Veritabanı ve Azure Analysis Services için OAuth’u da destekliyoruz.  Diğer veri kaynakları için şu anda portalda veya ağ geçidinde veri kaynağıyla birlikte kullanıcı adı ve parola depolamanız gerekiyor.  

### <a name="can-i-use-a-power-bi-dataset-as-a-data-source-for-my-paginated-report"></a>Sayfalandırılmış raporum için veri kaynağı olarak Power BI veri kümesini kullanabilir miyim?

Evet, sayfalandırılmış raporlarınız için veri kaynağı olarak Power BI veri kümelerini destekliyoruz.

### <a name="can-i-use-stored-procedures-through-the-gateway"></a>Ağ Geçidi üzerinden saklı yordamları kullanabilir miyim?

Evet, Ağ Geçidi üzerinden saklı yordamlar, parametre kullananlar da dahil olmak üzere SQL Server veri kaynaklarında desteklenir.

### <a name="what-export-formats-are-available-for-my-report-in-the-power-bi-service"></a>Power BI hizmetinde raporum için hangi dışarı aktarma biçimleri kullanılabilir?

Microsoft Excel, Microsoft Word, Microsoft PowerPoint, PDF, .CSV, XML ve MHTML'ye aktarabilirsiniz.

### <a name="can-i-print-paginated-reports"></a>Sayfalandırılmış raporları yazdırabilir miyim?

Evet, sayfalandırılmış raporlar için yeni ve geliştirilmiş baskı önizleme deneyimiyle yazdırma olanağı sağlanıyor. 

### <a name="are-e-mail-subscriptions-available-for-paginated-reports"></a>Sayfalandırılmış raporlar için e-posta abonelikleri sağlanıyor mu?

Evet, sayfalandırılmış raporlar e-posta aboneliklerini tamamen destekliyor ve altı farklı dosya biçimi ve parametre değerleri için destek içeriyor.

### <a name="can-i-run-custom-code-in-my-report"></a>Raporumda özel kod çalıştırabilir miyim?

Evet, SSRS'de yapabildiğiniz gibi raporlarınızda kod çalıştırabilme özelliğini destekliyoruz.

### <a name="can-i-use-power-bi-embedded-to-embed-my-paginated-reports-into-an-app-im-hosting"></a>Sayfalandırılmış raporlarımı barındırdığım bir uygulamaya eklemek için Power BI Embedded’i kullanabilir miyim?

Güvenli Ekleme desteği dahil olmak üzere SaaS ekleme zaten kullanılabilir. PaaS ekleme için [Uygulamaya müşterileriniz için sayfalandırılmış Power BI raporları ekleme](../developer/embedded/embed-paginated-reports-customers.md) öğreticisine bakın.

### <a name="can-i-drill-through-from-a-power-bi-report-to-a-paginated-report"></a>Bir Power BI raporundan sayfalandırılmış rapora detaylandırma yapabilir miyim?

Evet, sayfalandırılmış raporlarınızla URL parametrelerini birlikte kullanarak bu işlemi gerçekleştirebilirsiniz.

### <a name="can-i-share-my-paginated-report-content-through-a-power-bi-app"></a>Sayfalandırılmış rapor içeriğimi Power BI uygulaması üzerinden paylaşabilir miyim?

Evet, sayfalandırılmış raporların hem v1 hem de v2 çalışma alanlarından gelen uygulamalarla dağıtılması destekleniyor. 

### <a name="will-other-report-specific-features-in-power-bi-like-pinning-report-tiles-to-dashboards-work-with-paginated-reports"></a>Rapor kutucuklarını panolara sabitleme gibi Power BI’daki rapora özgü diğer özellikler, sayfalandırılmış raporlarla da çalışacak mı?

Raporların hizmetteki önemli senaryoların aynılarını olabildiğince desteklemesini sağlamayı planlıyoruz.  İdeal koşullarda, bu raporları yazmak için kullanılan araçlar farklı olsa da, tüketicinin bakış açısından bunlar portalda yer alan listedeki raporlardan biridir. Tüketici bunların nasıl oluşturulduğunu önemsemez ve yalnızca yapmaları gereken işleri gerçekleştirmeyi amaçlar.  Bu özellik eşliğine iyi bir örnek olarak, planlanan açıklama desteği verilebilir. Bu özellik her rapor türünde biraz farklı çalışsa da her ikisi için de açıklamaları kullanabilirsiniz.

### <a name="is-there-a-report-viewer-control-for-paginated-reports-in-the-power-bi-service"></a>Power BI hizmetinde sayfalandırılmış raporlar için bir rapor görüntüleyicisi denetimi var mı?

Hayır, şu anda bir rapor görüntüleyicisi denetimi sunulmuyor.

### <a name="can-you-search-for-paginated-reports-from-the-new-home-experience-in-the-power-bi-service"></a>Power BI hizmetindeki yeni Giriş deneyiminden sayfalandırılmış raporlar için arama yapılabiliyor mu?

Evet, artık Giriş'ten sayfalandırılmış raporlar için arama yapabilirsiniz.  Bu raporları yeni Giriş deneyiminin diğer bölümlerinde de görebilirsiniz.

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme
Sayfalandırılmış raporlarda DateTime alanlarıyla çalışırken aklınızda bulunması gereken bir şeyi burada bulabilirsiniz.

- Şu anda DateTime parametreleriyle ilgili bazı genelleştirme sınırlamaları vardır. Power BI hizmetindeki tüm DateTime parametreleri, Power BI Report Builder’da DateTime’ı nasıl tasarladığınız fark etmeksizin ABD biçiminde (AA/GG/YYYY) getirilir.

Kullanıcılar, Power BI hizmetinde sayfalandırılmış raporları görüntülerken oturum zaman aşımına uğrayabilir ve aşağıdaki bildirim görüntülenebilir:

:::image type="content" source="media/paginated-reports-faq/expired-session-notification.png" alt-text="Sayfalandırılmış rapor oturumunun süresinin dolduğunu gösteren bildirim":::

- Oturum, 60 dakika boyunca herhangi bir işlem yapılmadığında veya cihazın kilitlenmesi ya da boşta kalması durumunda daha erken bir noktada veya raporun tarayıcının etkin sekmesinde görüntülenmemesi halinde zaman aşımına uğrar.

## <a name="next-steps"></a>Sonraki adımlar

- [Power BI Rapor Oluşturucusu'nu Microsoft İndirme Merkezi'nden yükleme](https://aka.ms/pbireportbuilder)
- [Öğretici: Sayfalandırılmış rapor oluşturma](paginated-reports-quickstart-aw.md)
