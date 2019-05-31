---
title: Microsoft Power BI Premium nedir?
description: Power BI Premium, daha güvenilir performans ve daha yüksek veri hacimleri, kullanıcı başına lisans satın almanıza gerek kalmadan vererek kuruluşunuz için ayrılmış kapasite sağlar.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/22/2019
ms.custom: seodec18
LocalizationGroup: Premium
ms.openlocfilehash: e5ffa624bf69cf470aade076c80ac37028a55456
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65565274"
---
# <a name="what-is-power-bi-premium"></a>Power BI Premium nedir?

Power BI Premium, kuruluşunuz için Power BI hizmeti çalıştırmak için adanmış ve iyileştirilmiş kaynaklar sağlar. Örnek:

- Büyük ölçek ve performans
- Kapasite lisansla esnekliği
- Self Servis ve kurumsal BI birleştirin
- Power BI rapor sunucusu ile şirket içi BI'ı genişletin
- Veri yerleşikliği desteği (çoklu coğrafi) bölgeye göre
- Verileri kullanıcı başına lisans satın almadan herkesle paylaşma

Bu makalede, Power BI Premium - her bir özellik hakkında kapsamlı bilgi aslında sağlamak için tasarlanmamıştır, bu yalnızca yüzeysel dokunduğu. Gerektiğinde ek makalelerle daha ayrıntılı bilgi için bağlantılar sağlanır.

## <a name="subscriptions-and-licensing"></a>Abonelikler ve lisanslar

Power BI Premium, Kiracı düzeyinde Office 365 aboneliği iki SKU (stok tutma birimi) ailelerinde kullanılabilir olan:

- **EM** ekleme için SKU'ları (EM1-EM3) bir yıllık taahhüt gerektiren aylık faturalandırılır.
- **P** aylık veya yıllık taahhüt gerektiren SKU'lar (P1-P3) ekleme ve kurumsal özellikler için aylık olarak faturalandırılır ve Power BI rapor sunucusu şirket içi yüklemek için bir lisans içerir.

Satın almak için alternatif bir yaklaşım olan bir **Azure Power BI Embedded** sahip tek bir abonelik **A** ekleme ve test etme kapasitesi (A1-A6) SKU ailesi yalnızca amacıyla. Kapasite oluşturmak için sanal çekirdekler tüm SKU'ların teslim ancak EM SKU'ları için daha küçük bir ölçek ekleme kısıtlanır. EM1 ve EM2, A1 ve A2 SKU'larına Dörtten az çekirdek adanmış altyapı üzerinde çalıştırmayın.

Bu makalenin odak P SKU'larında olsa da, açıklanana çoğunu da A SKU'ları için geçerlidir. Premium aboneliği aksine SKU'ları, Azure SKU'ları hiçbir zaman taahhüdü gerektirir ve saatlik olarak faturalandırılır. Bunlar yukarı ölçek etkinleştirme tam esneklik sunar, ölçeği, duraklatma, sürdürme ve silin. 

Azure Power BI Embedded büyük ölçüde bu makalenin kapsamı dışındadır olmakla birlikte, açıklanan [test yaklaşımları](service-premium-capacity-optimize.md#testing-approaches) test ve iş yüklerini ölçmek için pratik ve ekonomik bir seçenek olarak en iyi duruma getirme Premium kapasiteleri makalenin bölümü. Azure SKU'ları hakkında daha fazla bilgi için bkz: [Azure Power BI Embedded belgeleri](https://azure.microsoft.com/services/power-bi-embedded/).

### <a name="purchasing"></a>Satın alma

Power BI Premium abonelikleri Microsoft 365 Yönetim merkezinde yöneticiler tarafından satın alınır. Özellikle, yalnızca Office 365 genel yönetici veya faturalama yöneticileri SKU satın alabilirsiniz. Satın aldığınızda, Kiracı olarak bilinen kapasiteler, atamak için sanal çekirdekler karşılık gelen sayıda alan *sanal çekirdek havuzu*. Örneğin, bir P3 SKU satın almak kiracıya 32 sanal çekirdek sağlar. Daha fazla bilgi için bkz. [Power BI Premium'u satın alma](service-admin-premium-purchase.md).

## <a name="dedicated-capacities"></a>Adanmış kapasite

Power BI Premium ile aldığınız *adanmış kapasitelerini*. İş yükleri diğer müşteriler ile paylaşılan hesaplama kaynaklarında çalıştırıldığı paylaşılan kapasite aksine ayrılmış bir kapasite için özel bir kuruluş tarafından kullanılır. Barındırılan içerik için güvenilir ve tutarlı bir performans sağlayan ayrılmış hesaplama kaynaklarını ile yalıtılmış. 

Çalışma alanlarının kapasiteler içinde yer alır. Her Power BI kullanıcısı olarak bilinen bir kişisel çalışma alanı olan **çalışma Alanım**. İşbirliği ve dağıtımı etkinleştirmek için ek bir çalışma alanı oluşturulabilir ve bunlar olarak bilinen **uygulama çalışma alanları**. Varsayılan olarak, paylaşılan kapasiteye kişisel çalışma alanlarını dahil çalışma oluşturulur. Premium kapasiteler varsa, hem My çalışma alanları hem de uygulama çalışma alanları için Premium kapasiteleri atanabilir.

### <a name="capacity-nodes"></a>Kapasite düğümleri

Bölümünde anlatıldığı gibi [abonelikler ve lisans](#subscriptions-and-licensing) bölümünde, iki Power BI Premium SKU ailesi vardır: **EM** ve **P**. Tüm Power BI Premium SKU'ları kullanılabilir kapasitesi olarak *düğümleri*, her bir işlemci, bellek ve depolama oluşan kaynakları miktarını temsil eden. Kaynakların yanı sıra her SKU, DirectQuery ve canlı bağlantı bağlantıları saniye başına sayısı işlem limitleri vardır ve paralel model sayısı yenilenir.

İşleme, ön uç ve arka uç arasında eşit olarak bölünür çekirdek, ayarlana sayıda elde edilir.

**Arka uç çekirdek** için temel Power BI işlevleri sorgu işleme, önbellek yönetimi, R services, model yenileme, doğal dil işleme (soru- cevap) ve raporlar ile resimlerin sunucu tarafında işlenmesi çalıştırma dahil olmak üzere, sorumludur. Arka uç çekirdek konak modelleri, etkin olarak da bilinen veri kümeleri için sabit bir temel olarak kullanılan bellek miktarını atanır.

**Ön uç sanal çekirdek** web hizmetinden, Pano ve rapor belge yönetiminden, erişim hakları yönetiminden, zamanlama, API'ler, yükler ve indirir ve genellikle kullanıcı ile ilgili her şeyi deneyimleri sorumludur.

Depolama ayarlanmış **100 TB kapasite düğüm başına**.

Kaynaklar ve her bir Premium SKU sınırları (ve bir SKU'eşdeğer boyutta) aşağıdaki tabloda açıklanmıştır:

| Kapasite düğümleri | Toplam sanal çekirdek sayısı | Arka uç sanal çekirdek sayısı | RAM (GB) | Ön uç sanal çekirdek sayısı | DirectQuery/canlı bağlantı (/ sn) | Model yenileme paralellik |
| --- | --- | --- | --- | --- | --- | --- |
| EM1/A1 | 1 | 0,5 | 2.5 | 0,5 | 3.75 | 1 |
| EM2/A2 | 2 | 1 | 5 | 1 | 7.5 | 2 |
| EM3/A3 | 4 | 2 | 10 | 2 | 15 | 3 |
| P1/A4 | 8 | 4 | 25 | 4 | 30 | 6 |
| P2/A5 | 16 | 8 | 50 | 8 | 60 | 12 |
| P3/A6 | 32 | 16 | 100 | 16 | 120 | 24 |
| | | | | | | |

### <a name="capacity-workloads"></a>Kapasite iş yükleri

Kapasite iş yükleri, kullanıcıların kullanımına sunulmasını hizmetleridir. Varsayılan olarak, Premium ve Azure kapasitelerinin yalnızca Power BI sorgularını çalıştırmayla ilgili bir veri kümesi yükünü destekler. Veri kümesi iş yükü devre dışı bırakılamaz. Ek iş yükleri için etkinleştirilebilir [AI (Bilişsel hizmetler)](https://powerbi.microsoft.com/blog/easy-access-to-ai-in-power-bi-preview/), [veri akışlarını](service-dataflows-overview.md#dataflow-capabilities-on-power-bi-premium), ve [sayfalandırılmış raporlar](paginated-reports-save-to-power-bi-service.md). Bu iş yükleri, yalnızca Premium aboneliklerinde desteklenir. 

Her ek iş yükü, iş yükü tarafından kullanılabilecek maksimum bellek (olarak, toplam kullanılabilir belleğin yüzdesi cinsinden) yapılandırma sağlar. Maksimum bellek için varsayılan değerleri SKU tarafından belirlenir. Bunların kullanılması durumunda ek bu iş yüklerinin etkinleştirerek kapasitenizi 's kullanılabilir kaynakları en üst düzeye çıkarabilirsiniz. Ve yalnızca varsayılan ayarlarını belirlediğinizde ayarları kapasite gereksinimleri karşılamıyor bellek değiştirebilirsiniz. İş yükleri etkinleştirilmeli ve kapasite tarafından kapasite yöneticileri için kullanılarak yapılandırılan **kapasite ayarlarını** içinde [Yönetici portalı](service-admin-portal.md) kullanarak veya [kapasiteler REST API'leri](https://docs.microsoft.com/rest/api/power-bi/capacities).  

![İş yüklerini etkinleştirme](media/service-admin-premium-workloads/admin-portal-workloads.png)

Daha fazla bilgi için bkz. [Premium kapasitede iş yüklerini yapılandırma](service-admin-premium-workloads.md). 

### <a name="how-capacities-function"></a>Nasıl kapasiteler işlevi

AT her zaman Power BI hizmetinde sınır uygulanmaz ve kapasite üzerinde geçmeyen çalışırken kapasite kaynakların en iyi kullanımı sağlar.

Kapasite operations olarak sınıflandırılan *etkileşimli* veya *arka plan*. Etkileşimli işlem istekleri oluşturma ve Kullanıcı etkileşimlerine (filtreleme, soru- cevap sorgulama, vb.) yanıt içerir. Genel olarak, DirectQuery ve canlı bağlantı modelleri sorgulama CPU yoğunluklu olsa bellek kaynak kullanımı yoğun bir modeli içeri aktarma sorgulama olur. Arka plan işlemleri, veri akışı içerir ve model yenileme işlemleri ve Pano sorgu önbelleğe alın.

Etkileşimli işlem arka plan işlemleri olabilecek en iyi kullanıcı deneyimi sağlamak için her zaman önceliklendirilir anlamak önemlidir. Yetersiz kaynak varsa, arka plan işlemleri kaynakları boşaltmaya, işleme için kuyruğa eklenir. Veri kümesini yenilemeleri gibi arka plan işlemleri, Power BI hizmeti tarafından durdurulan ortasında bir işlem olabilir ve bir kuyruğa eklenir.

Alma modelleri, sorgulanan güncelleştirilebilecek veya yenilenebilecek belleğe tam yüklü olmalıdır. Power BI hizmetini kullanarak kullanım algoritmaları en fazla kullanılabilir bellek kullanımını emin olmak için karmaşık ve kapasite aşırı işleme neden bellek yönetir: Birçok alma depolamak bir kapasite için mümkündür (en fazla 100 TB Premium kapasite başına) modelleri sırada, kendi birleştirilmiş disk depolama alanı desteklenen belleği aşıyor (ve ek bellek sorgulama ve yenileme için gerekli olduğunda), ardından bunların tüm sırasında belleğe yüklenemiyor aynı anda.

İçeri aktarma modelleri bu nedenle yüklenen ve bellek kullanım göre kaldırılır. Bir içeri aktarma modeli sorgulanan (etkileşimli işlem) olduğunda ve henüz bellekte veya yenilenmesi gerektiğinde yüklenir (arka plan işlemi).

Bir modelin bellekten temizleme olarak da bilinen *çıkarma*. Bu, Power BI hızlı bir şekilde modelleri boyutuna bağlı olarak gerçekleştirebileceğiniz bir işlemdir. Kapasite herhangi bir bellek baskısı yaşamadığından, modelleri sadece belleğe yüklenir ve orada kalır. Ancak, yetersiz bellek modeli yüklemek kullanılabilir duruma geldiğinde Power BI hizmetinde ilk boşaltın bellek gerekir. Son üç dakika içinde kullanılmamış Modellerinizi arayan tarafından etkin olmayan duruma gelmiş modelleri algılayarak bellek bıraktığı \[ [1](#endnote-1)\]ve ardından bunları çıkarma. Hiçbir etkin olmayan modelleri çıkarmak için varsa, arka plan işlemleri için yüklenen modelleri çıkarmak Power BI hizmetinde arar. Başarısız oturum açma girişimlerinin 30 saniye sonra son çare \[ [1](#endnote-1)\], etkileşimli işlem başarısız sağlamaktır. Bu durumda, rapor kullanıcısı, kısa süre sonra yeniden denemek için bir öneriyle hata bildirilir. Bazı durumlarda, modelleri hizmet işlemleri nedeniyle bellekten kaldırılmış olabilir.

Veri kümesi çıkarma normal ve beklenen bir davranış olduğunu vurgulamak önemlidir. Yükleme ve modelleri, birleşik boyutları kullanılabilir bellek aşabilir kaldırma bellek kullanımını en üst düzeye çıkarmaya çalışır. Tasarıma göre ve rapor kullanıcılara tamamen şeffaf budur. Yüksek çıkarma oranları, kapasite yeterince kaynak var mutlaka gelmez. Sorgu veya yenileme yanıt hızı yüksek çıkarma oranları nedeniyle yaşıyorsa, ancak bir sorun haline olabilir.

Yenilemeler alma modelleri, her zaman modelleri belleğe yüklenmesi gibi yoğun bellek olur. Ek bellek, işleme için gereklidir. Tam yenilemenin yaklaşık iki model tarafından gerekli bellek miktarını kullanabilirsiniz. Bu sorguları yenilemesi tamamlandı ve yeni model verileri kullanılabilir kadar mevcut modeline gönderildiğinden modeli bile işlenmekte olan, sorgulanabilir sağlar. Artımlı yenileme daha az bellek gerektirir ve daha hızlı işlemi tamamlanamadı ve böylece kapasite kaynakları Basıncı önemli ölçüde azaltabilir. Yenilemeler da CPU kullanımı yoğun olabilir modelleri için özellikle karmaşık Power Query dönüşümleri veya hesaplanan tabloları/sütunları ile karmaşık olan veya büyük tabloları temel alır.

Sorgu gibi bir yenileme, model belleğe yüklenmiş gerektirir. Yetersiz bellek varsa, Power BI hizmetinde etkin olmayan modelleri çıkarmak dener ve bu (tüm modelleri etkin olan) mümkün değilse, yenileme işi kuyruğa alındı. Yenileme genellikle CPU-yoğun, hatta daha şekilde sorguları daha. Bu nedenle, x sayısı arka uç yuvarlanan çekirdek, 1.5 koymak eşzamanlı yenileme sayısı kapasitesi sınırı yoktur. Çok fazla eş zamanlı yenilemeleri varsa, zamanlanmış yenileme kuyruğa alınır. Bu durum gerçekleştiğinde, yenileme tamamlanması uzun sürer. Bir kullanıcı isteği tarafından tetiklenip olanlar gibi isteğe bağlı yeniler veya API çağrısı üç kez yeniden deneyecek \[ [1](#endnote-1)\]. Yeterli kaynaklara hala mevcut değilse yenileme ardından başarısız olur.

Bölüm Notlar:   
<a name="endnote-1"></a>\[1\] değiştirilebilir.

### <a name="regional-support"></a>Bölgesel destek

Yeni bir kapasite, Office 365 genel yöneticileri ve Power BI hizmet yöneticileri oluşturma belirtebilirsiniz, burada kapasiteye çalışma alanlarını atanmış bir bölgede yer alacaktır. Bu olarak bilinir **çoklu coğrafi**. Office 365 aboneliği bulunduğu bölgesinden farklı olsa bile çoklu coğrafi ile kuruluşların belirli bir bölgedeki veri merkezleri için içerik dağıtma veri yerleşikliğinin karşılayabilirsiniz. Daha fazla bilgi için bkz. [çoklu coğrafi Power BI Premium desteği](service-admin-premium-multi-geo.md).

### <a name="capacity-management"></a>Kapasite yönetimi

Premium kapasite yönetimi oluşturma veya kapasiteler silme, yöneticiler atama, çalışma alanları atama, izleme ve kapasite performansını iyileştirmek için ayarlamaları yaparak iş yükleri, yapılandırma gerektirir. 

Office 365 genel yöneticileri ve Power BI hizmeti yöneticileri Premium kapasiteleri kullanılabilir çekirdek oluşturabilir, veya var olan Premium kapasiteleri değiştirin. Bir kapasiteye oluşturulduğunda, kapasite boyutunu ve coğrafi bölgede belirtilen ve en az bir kapasite Yöneticisi atanır. 

Kapasiteleri oluşturulduğunda, çoğu yönetim görevi de tamamlanır [Yönetici portalı](service-admin-portal.md).

![Yönetim portalı](media/service-premium-what-is/premium-admin-portal.png)

Kapasite yöneticileri kapasiteye çalışma alanları atama, kullanıcı izinlerini yönetme ve diğer yöneticilerin atayın. Kapasite yöneticileri ayrıca iş yükleri, bellek ayırma, ayarlama yapılandırabilir ve gerekirse, işlem kapasitesi aşırı yük durumunda sıfırlama kapasitesi, yeniden başlatın.

![Yönetim portalı](media/service-premium-what-is/premium-admin-portal-mgmt.png)

Kapasite yöneticileri ayrıca kapasitesi çalıştığından emin olabilirsiniz. Bunlar, Premium kapasite ölçümleri uygulamasını kullanarak ya da Yönetici portalındaki kapasite durumu sağ izleyebilirsiniz.

Daha fazla hakkında kapasiteler oluşturma, yöneticileri atama ve çalışma alanları atama bilgi edinmek için [yönetme Premium kapasiteleri](service-premium-capacity-manage.md). Rolleri hakkında daha fazla bilgi edinmek için [yönetici rolleri için Power BI ilgili](service-admin-administering-power-bi-in-your-organization.md#administrator-roles-related-to-power-bi).

### <a name="monitoring"></a>İzleme

Premium kapasiteler izleme kapasiteleri nasıl performans gösterdiğini anlamak yöneticilerine sağlar. Yönetici portalını kullanarak kapasiteler izlenebilir ve [Power BI Premium kapasite ölçümleri uygulama](https://app.powerbi.com/groups/me/getapps/services/capacitymetrics).

Portalda izleme yerleştirilen yükler ve, son yedi gün içindeki ortalama kapasitenizi tarafından kullanılan kaynakları gösteren üst düzey ölçümler ile hızlı bir görünüm sağlar. 

![Yönetim portalı](media/service-premium-what-is/premium-admin-portal-health.png)

**Power BI Premium kapasite ölçümleri** uygulaması, kapasiteler performansı hakkında en ayrıntılı bilgileri sağlar. Uygulamanın yüksek düzey bir Pano sağlar ve daha ayrıntılı raporlar.

![Ölçüm uygulama panosu](media/service-admin-premium-monitor-capacity/app-dashboard.png)

Uygulamanın panodan ayrıntılı bir rapor açmak için bir ölçüm hücre tıklayabilirsiniz. Ayrıntılı Ölçümler ve en önemli bilgileri, detaya filtreleme yeteneği, kapasiteler sorunsuz çalışır durumda tutmanız gerekir raporları sağlar.

![Dönemsel en yüksek sayılar sorgu bekleme süresi olası CPU doygunluğu sayılarını gösterir](media/service-premium-capacity-scenarios/peak-query-wait-times.png)

Kapasiteleri izleme hakkında daha fazla bilgi edinmek için [Power BI Yönetici portalı'nda izlemeyi](service-admin-premium-monitor-portal.md) ve [Power BI Premium kapasite ölçümleri uygulamayla izleme](service-admin-premium-monitor-capacity.md).

### <a name="optimizing-capacities"></a>Kapasite iyileştirme

Kullanıcılarınızın performansını gerçekleştirmek için kritik, kapasite kullanımını en iyi hale getirme ve Premium yatırımınızı en çok değer alma. Ana ölçümler izleyerek, Yöneticiler, performans sorunlarını gidermek ve gerekli eylem en iyi şekilde nasıl belirleyebilirsiniz. Daha fazla bilgi için bkz. [en iyi duruma getirme Premium kapasiteleri](service-premium-capacity-optimize.md) ve [Premium kapasite senaryolarında](service-premium-capacity-scenarios.md).

### <a name="capacities-rest-apis"></a>Kapasiteleri REST API'leri

Power BI REST API'lerini içeren bir koleksiyonu [kapasiteler API'leri](https://docs.microsoft.com/rest/api/power-bi/capacities). API'leri ile yöneticileri etkinleştirme ve devre dışı iş yükleri kapasite ve daha fazlası için çalışma alanları atama dahil olmak üzere, Premium kapasiteleri birçok yönden programlı olarak yönetebilirsiniz.

## <a name="large-datasets"></a>Büyük veri kümeleri

SKU'ya bağlı olarak, en çok karşıya yükleme Power BI Desktop (.pbix) model dosyaları Power BI Premium destekler **10 GB** boyutu. Yüklendiğinde, model Premium kapasiteye atanmış bir çalışma alanı ardından yayımlanabilir. Veri kümesi için yukarı ardından yenilenebilir **12 GB** boyutu.

### <a name="size-considerations"></a>Boyutu konuları

Büyük modeller yoğun kaynak olabilir. 1 GB'tan büyük tüm modeller için en az P1 SKU olması gerekir. Çalışma alanları için büyük modellerin yayımlama A3 kadar bir SKU'ları tarafından desteklenen rağmen iş, yenileme yapmamayı.

Aşağıdaki tabloda çeşitli .pbix boyutları için önerilen SKU'lar açıklanmıştır:

   |SKU  |.pbix dosyasının boyutu   |
   |---------|---------|
   |P1    | 3 GB’tan küçük        |
   |P2    | 6 GB’tan küçük        |
   |P3, P4, P5    | 10 GB'a kadar   |

Power BI Embedded A4 SKU’su P1 SKU, A5 = P2 ve A6 = P3’e eşittir. A ve EM SKU'larında büyük modellerin yayımlanması durumunda, paylaşılan kapasitedeki model boyutu sınırlamasına özgü olmayan hatalar döndürülebilir. A ve EM SKU'larında büyük modellerin yenilenmesi muhtemelen zaman aşımı hatalarına neden olacaktır. 

.Pbix dosyalarınız, verileri temsil eden bir *durumu'yüksek oranda sıkıştırılmış*. Muhtemelen veriler belleğe yüklenirken birkaç kez genişletilir ve veri yenileme sırasında birkaç kez daha genişletilebilir.

Büyük veri kümelerini zamanlanmış yenileme çok uzun zaman alabilir ve yoğun kaynak. Çok fazla örtüşen yenileme zamanlayamazsınız önemlidir. Önerilir [artımlı yenileme](service-premium-incremental-refresh.md) yapılandırılır, daha hızlı, daha güvenilir olduğundan, ve daha az kaynak kullanır.

Veri kümesini kullanıldığı son bir saat sonra biraz çağrıldıysa, büyük veri kümelerinin ilk raporunun yüklenmesi uzun sürebilir. Yüklenmesi nispeten uzun süren raporların ilerleme durumunu göstermek için bir yükleme çubuğu görüntülenir.

Sorgu başına bellek ve zaman kısıtlamalarına Premium kapasitede çok daha yüksek olsa da, yalnızca gerekli olanla görüntüleneceği şekilde kısıtlamanız için filtreler ve dilimleyiciler kullanmanız önerilir.

## <a name="incremental-refresh"></a>Artımlı yenileme

Artımlı yenileme ayrılmaz bir parçası olan ve büyük veri kümelerini Power BI Premium'da bakımını sağlar. Artımlı yenileme pek çok faydası vardır, örneğin, yalnızca veri yenilenmesi değişen ihtiyaçlarına sahip olduğundan yenileme daha hızlı. Uzun süre çalışan geçici veri kaynaklarına bağlantı korumak gereksiz olduğundan yenileme daha güvenilirdir. Yenilemek için daha az veri genel bellek ve diğer kaynakların tüketimini azaltır çünkü kaynak tüketimi azalır. Artımlı yenileme ilkeleri tanımlanmış **Power BI Desktop**ve bir çalışma alanı Premium kapasite yayımladığınızda uygulanır. 

![Yenileme ayrıntıları](media/service-premium-incremental-refresh/refresh-details.png)

Daha fazla bilgi için bkz. [artımlı yenileme Power BI Premium'da](service-premium-incremental-refresh.md).

## <a name="paginated-reports"></a>Sayfalandırılmış raporlar

Sayfalandırılmış raporlar, P1-P3 ve A4_A6 SKU'ları, desteklenen SQL Server Raporlama Hizmetleri'nde rapor tanım Dili'nin (RDL) teknolojisini temel alır. RDL teknolojisini temel alan, ancak bunu ayrıca Power BI Premium'a dahildir şirket içinde yüklediğiniz indirilebilir bir raporlama platformu olan Power BI rapor sunucusu ile aynı değil. Sayfalandırılmış raporlar, yazdırılan veya paylaşılan iyi bir sayfaya sığmayacak biçimlendirilir. Tablonun birden çok sayfaya yayıldığında bile, veriler bir tabloda görüntülenir. Ücretsiz kullanarak [ **Power BI Rapor Oluşturucusu'nu** ](https://go.microsoft.com/fwlink/?linkid=2086513) Windows masaüstü uygulaması, kullanıcıların Yazar sayfalandırılmış raporlar ve hizmetine yayımlarsınız.

Power BI Premium'da Paginated kapasitesi için Yönetici portalını kullanarak etkinleştirilmelidir. bir iş yükü raporlardır. Kapasite yöneticileri etkinleştirebilir ve ardından kapasiteyi'nın genel bellek kaynaklarının yüzdesi olarak bellek miktarını belirtin. Diğer iş yükleri türlerinin aksine, Premium kapasite içinde kapsanan bir boşluk sayfalandırılmış raporları çalıştırır. İş yükü etkin olup olmadığını bu alanı için belirtilen en fazla bellek kullanılır. Varsayılan değer % 20 ' dir. 

Daha fazla bilgi için bkz. [sayfalandırılmış raporlar Power BI Premium'da](paginated-reports-report-builder-power-bi.md). Paginated raporları iş yükünü etkinleştirme hakkında daha fazla bilgi edinmek için [iş yüklerini yapılandırma](service-admin-premium-workloads.md).

## <a name="power-bi-report-server"></a>Power BI Rapor Sunucusu
 
Power BI Premium ile bulunan, Power BI rapor sunucusu olan bir *şirket içi* rapor sunucusu web portalıyla. Ortamında şirket içi, BI oluşturabilir ve raporları, kuruluşunuzun güvenlik duvarının arkasında dağıtın. Rapor sunucusu zengin, etkileşimli ve SQL Server Reporting Services Kurumsal raporlama yetenekleri için kullanıcılara erişim sağlar. Kullanıcılar, görsel verileri keşfedin ve desenleri daha iyi, daha hızlı kararlar almak için daha hızlı keşfedeceksiniz. Rapor sunucusu, kendi koşullarınıza göre idare sağlar. Zaman gelir durumunda Power BI rapor sunucusu, burada kuruluşunuzun tüm Power BI Premium işlevlerin yararlanabilirsiniz buluta taşımayı kolaylaştırır.

Daha fazla bilgi için bkz. [Power BI rapor sunucusu](report-server/get-started.md).

## <a name="unlimited-content-sharing"></a>Sınırsız içerik paylaşma

Premium ile herkes, içinde veya dışında kuruluşunuzun ister görüntüleyebilir bağımsız lisansları satın almadan sayfalandırılmış ve etkileşimli raporlar da dahil olmak üzere Power BI içeriğiniz. 

![İçerik paylaşımı](media/service-premium-what-is/premium-sharing.png)

Premium içeriğini görüntülemek için alıcıları Pro lisanslarına gerek kalmadan yaygın dağıtım Pro kullanıcıları tarafından içerik sağlar. İçerik oluşturucuları için Pro lisansı gereklidir. Oluşturucuları model verileri, veri kaynağına bağlanın ve raporları ve çalışma uygulamaları olarak paketlenir panolar oluşturun. 

Daha fazla bilgi için bkz. [Power BI lisansı](service-admin-licensing-organization.md).

## <a name="tool-connectivity-preview"></a>Aracı bağlantısı (Önizleme)

Altyapı, Microsoft kanıtlanmış Kurumsal altında **Analysis Services Vertipaq altyapısı** Power BI veri kümelerini güçlendirir. Analysis Services programlama sağlar ve istemci kitaplıkları ve açık standart XMLA protokolünü destekleyen API'ler istemci uygulaması ve araç desteği. Şu anda Power BI Premium veri kümeleri destekleyen *salt okunur* Microsoft ve üçüncü taraf istemci uygulamaları ve araçları aracılığıyla operations **XMLA bitiş noktası**. 

SQL Server Management Studio ve SQL Server Profiler ve DAX Studio ve veri görselleştirme uygulamaları gibi üçüncü taraf uygulamaları gibi Microsoft araçlarıyla, bağlanın ve XMLA, DAX, MDX, Dmv'leri ve izleme olaylarını kullanarak Premium veri kümelerini sorgulayın. 

![SSMS](media/service-premium-what-is/connect-tools-ssms-dax.png)

Daha fazla bilgi için bkz. [istemci uygulamaları ve araçları ile veri kümelerine bağlanma](service-premium-connect-tools.md).

## <a name="acknowledgements"></a>Onayları

Peter Myers, veri platformu MVP ve bağımsız BI Uzmanı ile [Bitsel çözümleri](https://www.bitwisesolutions.com.au/), ve Microsoft Power BI Müşteri danışma ekibi (CAT) büyük katkıda bulunanların bu makaleye.

## <a name="next-steps"></a>Sonraki adımlar

> [!div class="nextstepaction"]
> [Premium kapasite yönetimi](service-premium-capacity-manage.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)

||||||
