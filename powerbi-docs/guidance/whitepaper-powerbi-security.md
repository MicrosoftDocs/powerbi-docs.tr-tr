---
title: Power BI güvenliği teknik incelemesi
description: Power BI'ın güvenlik mimarisi ve uygulamasının açıklandığı ve tartışıldığı teknik inceleme
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi
ms.topic: conceptual
ms.date: 05/14/2020
LocalizationGroup: Conceptual
ms.openlocfilehash: 806869b10b52ff7c161484f3e8d38fbc61b85f60
ms.sourcegitcommit: c700e78dfedc34f5a74b23bbefdaef77e2a87f8a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97961282"
---
# <a name="power-bi-security-whitepaper"></a>Power BI güvenliği teknik incelemesi

**Özet:** Power BI, Microsoft 'un sunduğu ve kolayca self servis Iş zekası panoları, raporları, veri kümeleri ve görselleştirmeler oluşturmanıza olanak sağlayan bir çevrimiçi yazılım hizmetidir (*SaaS* veya hizmet olarak yazılım). Power BI ile birçok farklı veri kaynağına bağlanabilir, bu bağlantılardan gelen verileri birleştirip şekillendirebilir ve ardından başkalarıyla paylaşılabilen rapor ve panolar oluşturabilirsiniz.

**Yazıcı:** David Iyayma aygıtı

**Teknik gözden geçirenler:** Pedram Rezaei, cristia Petcukascu, sıva Harınres, Tod Manle, Haydn Richardson, adam Solson, ben Childs, Robert Bruckner, Sergei Gundorov, Kasper de Jonge

**Uygulama hedefi:** Power BI SaaS, Power BI Desktop, Power BI Embedded, Power BI Premium

> [!NOTE]
> Tarayıcınızdan **Yazdır** ' ı seçerek ve ardından **PDF olarak kaydet**' i seçerek bu teknik incelemeyi kaydedebilir veya yazdırabilirsiniz.

## <a name="introduction"></a>Giriş

**Power BI** , Microsoft 'un sunduğu ve kolayca self servis iş zekası panoları, raporları, veri kümeleri ve görselleştirmeler oluşturmanıza olanak sağlayan bir çevrimiçi yazılım hizmetidir (_SaaS_ veya hizmet olarak yazılım). Power BI ile birçok farklı veri kaynağına bağlanabilir, bu bağlantılardan gelen verileri birleştirip şekillendirebilir ve ardından başkalarıyla paylaşılabilen rapor ve panolar oluşturabilirsiniz.

Power BI hizmeti [Microsoft Online Services Koşulları](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=31) ve [Microsoft Kurumsal Gizlilik Bildirimi](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx) koşullarına tabidir. Bilgi işlem konumu için Microsoft Online Services Koşullarında Bilgi İşlem Konumu koşullarına bakın. Uyumluluk bilgileri için [Microsoft Güven Merkezi](https://www.microsoft.com/trust-center/product-overview) Power BI’ın birincil kaynağıdır. Power BI takımı müşterilerine en son yenilikleri ve üretkenlik çözümlerini getirmek için çalışıyor. Power BI Şu anda Microsoft 365 uyumluluk çerçevesinin katman D ' sidir. [Microsoft Güven Merkezi](https://docs.microsoft.com/compliance/regulatory/offering-home)'nde uyumluluk hakkında daha fazla bilgi edinin.

Bu makalede, Power BI mimarisini açıklanıp kullanıcıların nasıl Power BI’da kimlik doğrulayarak veri bağlantıları oluşturdukları anlatıldıktan sonra Power BI’ın hizmet üzerinden nasıl veri taşıdığı ve depoladığı açıklanarak Power BI güvenliği tanımlanır. Son bölüm güvenlikle ilgili sorulara ve bu soruların yanıtlarına ayrılmıştır.

## <a name="power-bi-architecture"></a>Power BI Mimarisi

**Power BI** hizmetinin temelini, Microsoft'un [bulut bilgi işlem platformu](https://azure.microsoft.com/overview/what-is-azure/) olan **Azure** oluşturur. Power BI şu anda dünyanın her yerinde birçok veri merkezine dağıtılmıştır. Bu veri merkezlerinin hizmet verdiği bölgelerdeki müşterilerin kullanıma sunulan çok sayıda etkin dağıtım bulunur ve her etkin dağıtım için yedekleme işlevi gören, edilgen dağıtımlar vardır.

Her Power BI dağıtımı iki kümeden oluşur: Bir Web Ön Uç (**WFE**) kümesi ve bir **Arka Uç** kümesi. Bu iki küme aşağıdaki resimde gösterilmiştir ve makalenin geri kalanının arka planını oluşturur. 

![WFE ve Arka Uç](media/whitepaper-powerbi-security/powerbi-security-whitepaper_01.png)

Power BI hesap kimliği doğrulaması ve yönetimi için Azure Active Directory (**AAD**) kullanır. Power BI Ayrıca, kimlik doğrulama işlemi ve statik içerik ve dosyaları indirmek için, bağlantı kurmaya çalışan istemcinin DNS kaydı tarafından belirlenen en yakın veri merkezine Kullanıcı trafiğini yönlendirmek için **Azure Traffic Manager (ATM)** kullanır. Power BI, **Azure Content Delivery Network (CDN)** kullanılarak sunulan Power BI görsellerinin dışında, gerekli statik içerik ve dosyaları kullanıcılara verimli bir şekilde dağıtmak için coğrafi olarak en yakın WFE 'yi kullanır.

### <a name="the-wfe-cluster"></a>WFE Kümesi

**WFE** kümesi Power BI için ilk bağlantı ve kimlik doğrulaması işlemlerini yönetir. Bu küme, AAD hizmetini kullanarak istemcilerin kimliklerini doğrular ve Power BI hizmetiyle kurulacak sonraki istemci bağlantıları için belirteçler sağlar.

![WEF Kümesi](media/whitepaper-powerbi-security/powerbi-security-whitepaper_02.png)

Kullanıcılar Power BI hizmetine bağlanmaya çalıştığında istemcinin DNS hizmeti Power BI dağıtımı olan en yakın veri merkezini bulmak için **Azure Traffic Manager** ile iletişim kurabilir. Bu işlem hakkında daha fazla bilgi için bkz. [Azure Traffic Manager için yüksek performanslı trafik yönlendirme yöntemi](/azure/traffic-manager/traffic-manager-routing-methods#performance-traffic-routing-method).

Kullanıcıya en yakın WFE kümesi oturum açma ve kimlik doğrulama dizisini yönetir (bu makalenin devamında açıklanmıştır) ve kimlik doğrulaması başarılı olduğunda kullanıcıya bir AAD belirtici sağlar. WFE kümesindeki ASP.NET bileşeni kullanıcının hangi kuruluşa ait olduğunu belirlemek için isteği ayrıştırır ve ardından Power BI **Genel Hizmeti**’ne başvurur. Genel Hizmet, dünya çapında tüm WFE ve Arka Uç kümeleri arasında paylaşılan ve kullanıcılarla müşteri kuruluşlarını Power BI kiracılarının barındırıldığı veri merkeziyle eşleyen tek bir Azure Tablosudur. WFE tarayıcıya hangi Arka Uç kümesinin kuruluşun kiracısını barındırdığını belirtir. Kullanıcının kimliği doğrulandıktan sonra yapılan istemci etkileşimleri, WFE’nin aracılık etmesine gerek kalmadan doğrudan Arka Uç kümesiyle gerçekleştirilir.

### <a name="the-power-bi-back-end-cluster"></a>Power BI Arka Uç Kümesi

**Arka Uç** kümesi, kimlik doğrulamasından geçen istemcilerin, Power BI hizmetiyle nasıl etkileşim kuracağını belirler. **Arka Uç** kümesi; görselleştirmeleri, kullanıcı panolarını, veri kümelerini, raporları, veri depolama alanlarını, veri bağlantılarını, veri yenileme özelliklerini ve Power BI hizmetiyle etkileşim kurarken kullanılan diğer öğeleri yönetir.

![Arka Uç Kümesi](media/whitepaper-powerbi-security/powerbi-security-whitepaper_03.png)

**Ağ Geçidi Rolü** kullanıcı istekleriyle Power BI hizmeti arasında bir ağ geçidi işlevi görür. Kullanıcılar Ağ Geçidi Rolü haricindeki bir rolle doğrudan etkileşim kurmaz.

**Önemli:** _Yalnızca_ Azure API Management (**APIM**) ve Gateway (**GW**) rollerinin genel Internet üzerinden erişilebilir olduğunu unutmayın. Bu hizmetler kimlik doğrulaması, yetkilendirme, DDoS koruması, Azaltma, Yük Dengeleme, Yönlendirme gibi özellikler sunar.

Yukarıdaki **Arka Uç** kümesi resminde yer alan kesik çizgi, kullanıcılar tarafından erişilebilen iki rol (kesik çizginin sol tarafı) ile yalnızca sistem tarafından erişilebilen roller arasındaki ayrımı gösterir. Kimliği doğrulanmış bir kullanıcı Power BI hizmetine bağlandığında bağlantı ve istemci istekleri **Ağ Geçidi Rolü** ve **Azure API Management** tarafından kabul edilip yönetilir ve bu rol Power BI hizmetinin geri kalan kısmında kullanıcının adına etkileşimde bulunur. Örneğin, bir istemci bir panoyu görüntülemek istediğinde **Ağ Geçidi Rolü** bu isteği kabul eder ve tarayıcının panoyu oluşturması için gerekli olan verileri almak için **Sunum Rolü**'ne ayrı bir istek gönderir.

![Ağ Geçidi rolü](media/whitepaper-powerbi-security/powerbi-security-whitepaper_04.png)

### <a name="power-bi-premium"></a>Power BI Premium

**Power BI Premium**, Power BI etkinlikleri için ayrılmış kaynaklara ihtiyacı olan abonelere ayrılmış, sağlanmış ve bölümlenmiş bir hizmet çalışma alanı sunar. Müşteri Power BI Premium aboneliğine kaydolduğunda Premium kapasite **Azure Resource Manager** üzerinden oluşturulur. Bu aboneliğin dağıtımı; Power BI kiracısının barındırıldığı veri merkezinde (bu makalenin devamında açıklandığı gibi Multi-Geo ortamları dışında), **Azure Service Fabric** dağıtımı olarak başlatılan ve abonelik düzeyiyle orantılı olan bir sanal makine kümesi atar.

![Power BI Premium](media/whitepaper-powerbi-security/powerbi-security-whitepaper_05.png)

Oluşturulduktan sonra, Premium kümesindeki tüm iletişimler Power BI Arka Uç kümesine yönlendirilir ve buradan istemcinin ayrılmış **Power BI Premium** aboneliği sanal makinesiyle iletişim kurulur.

### <a name="data-storage-architecture"></a>Veri Depolama Mimarisi

Power BI hizmetinin veri depolamak ve yönetmek için kullandığı iki ana depo vardır. Kullanıcılar tarafından karşıya yüklenen veriler genelde **Azure Blob** depolama alanına gönderilirken sisteme ait meta veriler ve tüm yapıtlar **Azure SQL Veritabanı**'nda güvenlik duvarının arkasında depolanır.

![Veri depolama](media/whitepaper-powerbi-security/powerbi-security-whitepaper_06.png)

Örneğin bir kullanıcı Power BI hizmetine Excel çalışma kitabı aktardığında, bellek içi bir Analysis Services tablolu veritabanı oluşturulur ve en fazla bir saat boyunca (veya sistemde bellek baskısı oluşana kadar) veriler bellek içinde depolanır. Veriler **Azure Blob** depolama alanına da gönderilir.

Kullanıcının Power BI aboneliği hakkındaki meta veriler (panolar, raporlar, son veri kaynakları, çalışma alanları, kurumsal bilgiler, kiracı bilgileri ve sistem hakkında diğer meta verileri gibi), **Azure SQL Veritabanı**’nda depolanır ve güncelleştirilir. Azure SQL Veritabanı’nda depolanan tüm bilgiler [Azure SQL’in Saydam Veri Şifreleme](/azure/sql-database/transparent-data-encryption-azure-sql) (TDE) teknolojisi kullanılarak şifrelenir. Azure Blob depolama alanında depolanan tüm veriler de şifrelenir. **Veri Depolama ve Taşıma** bölümünde veri yükleme, depolama ve taşıma işlemi hakkında daha fazla bilgi verilmiştir.

## <a name="tenant-creation"></a>Kiracı Oluşturma

Kiracı, bir kuruluşun Azure, Microsoft Intune, Power BI veya Microsoft 365 gibi bir Microsoft bulut hizmetine kaydolduğunda aldığı ve sahip olduğu adanmış bir Azure AD hizmeti örneğidir. Her Azure AD kiracısı benzersizdir ve diğer Azure AD kiracılarından ayrıdır.

Kiracı, bir şirket içindeki kullanıcıları ve bunlarla ilgili bilgileri (parolalarını, kullanıcı profili verilerini, izinlerini vb.) barındırır. Ayrıca bir kuruluşa ve kuruluşun güvenliğine ilişkin grupları, uygulamaları ve diğer bilgileri de içerir. Daha fazla bilgi için bkz. [Azure AD kiracısı nedir?](/office365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings).

Veri merkezinde, Microsoft 365 veya Power BI hizmeti başlangıçta sağlandığı zaman sağlanan Azure Active Directory kiracı için sağlanan ülke (veya bölgeye) ve durum bilgilerine en yakın bir Power BI kiracı oluşturulur. Power BI kiracısı bugün söz konusu veri merkezi konumundan taşınmaz.

### <a name="multiple-geographies-multi-geo"></a>Birden Çok Coğrafi Bölge (Multi-Geo)

Bazı kuruluşlar iş gereksinimlerine bağlı olarak birden çok coğrafyada veya bölgede Power BI varlığına ihtiyaç duyar. Örneğin, bir işletme Birleşik Devletler Power BI kiracıya sahip olabilir, ancak Avustralya gibi diğer coğrafi alanlara de iş oluşturabilir ve yerel yönetmeliklerle uyumlu olması için belirli Power BI verilerinin o uzak bölgedeki geri kalanında kalması gerekir. 2018 ikinci yarısında başlayarak, tek bir Coğrafya 'daki ev kiracılarına sahip kuruluşlar, başka bir Coğrafya içinde bulunan Power BI kaynaklarını da sağlayabilir ve bunlara erişebilir. Bu özellik, bu belgenin devamında kolaylık ve başvuru sağlamak için **multi-geo** olarak adlandırılır.

Birden çok coğrafi bölge için en güncel ve birincil makale, [Power BI Premium Için çok coğrafi olarak kullanılan desteği yapılandırma](../admin/service-admin-premium-multi-geo.md) makaledir. 

Farklı coğrafi bölgelerde çalışırken yerel yasalar ve yönetmelikler bağlamında değerlendirilmesi gereken birden çok teknik ayrıntı vardır. Bu ayrıntılar şunları içerir:

- Uzak bir sorgu yürütme katmanı, veri modelinin, önbelleklerinin ve en çok veri işlemenin uzak kapasite bölgesinde kalmasını sağlamak için uzak kapasite bölgesinde barındırılır. [Çok coğrafi Power BI Premium](../admin/service-admin-premium-multi-geo.md) makalesinde açıklandığı gibi bazı özel durumlar vardır.
- Önbelleğe alınmış bir sorgu metni ve bir uzak bölgede depolanan karşılık gelen sonuç, bekleyen bu bölgede kalır, ancak yoldaki diğer veriler birden fazla coğrafi grafik arasında geri dönebilir.
- Power BI hizmeti çoklu coğrafi kapasiteye yayınlanan (karşıya yüklenen) PBIX veya XLSX dosyaları, bir kopyanın Power BI kiracı bölgesindeki Azure Blob depolamada geçici olarak depolanmasına neden olabilir. Bu gibi durumlarda, veriler Azure Depolama Hizmeti Şifrelemesi (SSE) kullanılarak şifrelenir ve dosya içeriği işleme ve uzak bölgeye aktarımı tamamlanır başlamaz kopya çöp toplama için zamanlanır. 
- Verileri çok coğrafi bir ortamda bölgeler arasında taşırken, kaynak bölgedeki verilerin örneği 7-30 gün içinde silinir. 

### <a name="datacenters-and-locales"></a>Veri Merkezleri ve Yerel Ayarlar

Power BI, Power BI kümelerinin bölgesel veri merkezlerinde dağıtıldığı yerlere bağlı olarak belirli bölgelerde sunulur. Microsoft, Power BI altyapısını daha fazla veri merkezine genişletmeyi planlamaktadır.

Aşağıdaki bağlantılar Azure veri merkezleri hakkında ek bilgi sağlar.

- [Azure Bölgeleri](https://azure.microsoft.com/regions/): Azure’ın küresel varlığı ve konumları hakkında bilgiler
- [Bölgeye göre Azure Hizmetleri](https://azure.microsoft.com/regions/#services): Her bölgede Microsoft tarafından sunulan Azure hizmetlerinin (hem altyapı hizmetleri hem de platform hizmetleri) tam listesi.

Şu anda Power BI hizmeti, [Microsoft Güven Merkezi](https://www.microsoft.com/trust-center/product-overview)'nde açıklandığı şekilde veri merkezleri tarafından hizmet verilen belirli bölgelerde kullanılabilir. Şu bağlantı Power BI veri merkezlerinin haritasını gösterir; bir bölgedeki veri merkezlerini görmek için bölgenin üzerine gelin:

* [Power BI Veri Merkezleri](https://www.microsoft.com/TrustCenter/CloudServices/business-application-platform/data-location)

Microsoft özerk bölgeler için de veri merkezleri sağlar. Ulusal bulutlar için Power BI hizmetinin kullanılabilirliği hakkında daha fazla bilgi için bkz. [Power BI ulusal bulutları](https://powerbi.microsoft.com/clouds/).

Verilerinizin nerede depolandığı ve nasıl kullanıldığı hakkında daha fazla bilgi için [Microsoft Güven Merkezi](https://www.microsoft.com/trust-center/product-overview)’ne bakın. Bekleyen müşteri verilerinin konumuyla ilgili taahhütler [Microsoft Online Services Koşulları](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=31)'nın **Bilgi İşlem Koşulları** bölümünde belirtilir.

## <a name="user-authentication"></a>Kullanıcı Kimlik Doğrulaması

Power BI hizmetinde kullanıcı kimlik doğrulaması bir dizi istek, yanıt ve kullanıcının tarayıcısı ile Power BI hizmeti veya Power BI tarafından kullanılan Azure hizmeti arasında gerçekleşen yeniden yönlendirmeden oluşur. Bu dizi Power BI’da kullanıcı kimlik doğrulaması işlemini açıklar. Kuruluşun kullanıcı kimlik doğrulama modelleriyle ilgili seçenekler (oturum açma modelleri) hakkında daha fazla bilgi için bkz. [Microsoft 365 için oturum açma modeli seçme](https://blogs.office.com/2014/05/13/choosing-a-sign-in-model-for-office-365/).

### <a name="authentication-sequence"></a>Kimlik Doğrulaması Dizisi

Power BI hizmeti için kullanıcı kimlik doğrulaması işlemi aşağıdaki adımlarda açıklanan ve aşağıdaki resimlerde gösterilen şekilde gerçekleşir.

1. Kullanıcı, adres çubuğuna (gibi) Power BI adresini yazarak `https://app.powerbi.com` veya Power BI giriş sayfasından _oturum aç_ ' ı seçerek bir tarayıcıdan Power BI hizmeti bağlantı başlatır ( https://powerbi.microsoft.com) . Bağlantı, TLS 1.2 ve HTTPS kullanarak kurulur ve daha sonra tarayıcı ile Power BI hizmeti arasındaki tüm bağlantılarda HTTPS kullanılır. İstek **Azure Traffic Manager**’a gönderilir.

2. **Azure Traffic Manager**, Power BI’ın dağıtıldığı en yakın veri merkezini belirlemek için kullanıcının DNS kaydını denetler ve DNS’ye kullanıcının gönderileceği WFE kümesinin IP adresiyle yanıt verir.

3. Ardından WFE kullanıcıyı Microsoft Online Services'in oturum açma sayfasına yönlendirir.

    ![Kimlik doğrulama dizisi](media/whitepaper-powerbi-security/powerbi-security-whitepaper_08.png)

1. Kullanıcının kimliği doğrulandıktan sonra oturum açma sayfası kullanıcıyı önceden belirlenen en yakın Power BI hizmeti **WFE kümesine** yönlendirir.

2. Tarayıcı, Microsoft Online Services'te başarıyla oturum açıldığında alınan çerezi gönderir ve bu çerez **WFE kümesinin** içindeki **ASP.NET hizmeti** tarafından incelenir.

3. WFE kümesi, kullanıcının Power BI hizmeti aboneliğinin kimliğini doğrulamak ve bir AAD güvenlik belirteci almak için **Azure Active Directory** (**AAD**) hizmetine danışır. AAD kullanıcının kimlik doğrulamasının başarılı olduğunu bildirir ve AAD güvenlik belirtecini döndürürse, WFE kümesi kiracıların ve Power BI Arka Uç kümesi konumlarının listesini yöneten ve kullanıcının kiracısını hangi Power BI hizmeti kümesinin içerdiğini belirleyen **Power BI**** Genel Hizmeti**’ne başvurur. Ardından WFE kümesi kullanıcıyı, kiracısının bulunduğu Power BI kümesine yönlendirir ve kullanıcının tarayıcısına öğelerin bir koleksiyonunu döndürür:

      - **AAD güvenlik belirteci**
      - **Oturum bilgileri**
      - Kullanıcının bağlantı kurup etkileşimde bulunabileceği **Arka Uç** kümesinin web adresi

1. Kullanıcının tarayıcısı, tarayıcının Power BI hizmetiyle iletişimini etkinleştirmek için gereken belirli ortak dosyaların koleksiyonunu indirmek amacıyla belirtilen Azure CDN ile (veya bazı dosyalar için WFE ile) iletişime geçer. Tarayıcı sayfası, Power BI hizmeti tarayıcı oturumu süresince AAD belirtecini, oturum bilgilerini, ilişkili Arka Uç kümesinin konumunu ve Azure CDN ile WFE kümesinden indirilen dosya koleksiyonunu içerir.

![Azure CDN etkileşimi](media/whitepaper-powerbi-security/powerbi-security-whitepaper_09.png)

Bu öğeler tamamlandıktan sonra tarayıcı belirtilen Arka Uç kümesiyle bağlantı kurar ve kullanıcının Power BI hizmetiyle ilişkisi başlatılır. Bu noktadan sonra Power BI hizmetine yapılan tüm çağrılar belirtilen Arka Uç kümesiyle sağlanır ve kullanıcının AAD belirtecini içerir. AAD belirtecinin bir saatlik zaman aşımı vardır; kullanıcının oturumu açık kaldığı sürece erişimi korumak için WFE belirteci düzenli aralıklarla yeniler.

## <a name="data-storage-and-movement"></a>Veri Depolama ve Taşıma

Power BI hizmetinde, veriler _beklemede_ (Power BI kullanıcısının kullanımına sunulan ve şu anda üzerinde işlem yapılmayan veriler) ya da _işlemdedir_ (örneğin: sorguların çalıştırılması, veri bağlantıları ve modelleri üzerinde işlem yapılması, verilerin ve/veya modellerin Power BI hizmetine yüklenmesi ve kullanıcıların ya da Power BI hizmetinin verilere etkin olarak erişilen veya yüklenen diğer eylemler gerçekleştirmesi). İşlenmekte olan verilere _işlemdeki veriler_ denir. Power BI’da bekleyen veriler şifrelenir. Taşınan veriler, Power BI hizmeti tarafından gönderilen veya alınan verilerdir ve onlar da şifrelenir.

Power BI hizmeti, verileri **DirectQuery** ile veya içeri aktarmayla erişilmelerine bağlı olarak da farklı yönetir. Yani Power BI için kullanıcı verileri iki kategoriye ayrılır: DirectQuery ile erişilen veriler ve DirectQuery ile erişilmeyen veriler.

**DirectQuery**; Power BI kullanıcısının sorgusunun, Microsoft’un Veri Çözümleme İfadeleri (DAX) dilinden (Power BI ve diğer Microsoft ürünleri tarafından sorgu oluşturmak için kullanılan dil) veri kaynağının ana veri diline (T-SQL veya diğer ana veritabanı dilleri gibi) çevrildiği bir sorgudur. DirectQuery ile ilişkilendirilmiş veriler yalnızca başvuru yoluyla depolanır. Başka bir deyişle DirectQuery etkin değilken kaynak veriler Power BI’da depolanmaz (aşağıdaki _İşlemdeki veriler (veri taşıma)_ bölümünde açıklanan, panoları ve raporları görüntülemek için kullanılan görselleştirme verileri dışında). Bunun yerine DirectQuery verilerine yapılan başvurular depolanır ve bu sayede DirectQuery çalıştırıldığında verilere erişim sağlanır. Sorguyu yürütmek için gerekli tüm bilgiler DirectQuery’de bulunur. Bunlara, DirectQuery’nin otomatik yenilemeye dahil edilen veri kaynaklarına bağlanmasını sağlayan, veri kaynaklarına erişim için kullanılan bağlantı dizesi ve kimlik bilgileri dahildir. DirectQuery ile, temel alınan veri modeli bilgileri DirectQuery’ye eklenir.

İçeri aktarma veri kümesine yönelik bir sorgu, temel alınan hiçbir veri kaynağının ana diline doğrudan _çevrilmeyen_ bir DAX sorguları koleksiyonundan oluşur. İçeri aktarma sorgusu olmayan sorgular temel alınan veriler için kimlik bilgileri içermez ve temel alınan veriler bir [Power BI Gateway](../connect-data/service-gateway-onprem.md) üzerinden erişilen şirket içi veriler olmadığı sürece (bu durumda sorgu yalnızca şirket içi verilerin başvurularını depolar) Power BI hizmetinin içine yüklenir.

Aşağıdaki tabloda kullanılan sorgu türü temelinde Power BI verileri açıklanır. **X** işareti ilişkili veri türü kullanıldığında Power BI verilerinin varlığına işaret eder.

|                         | İçeri Aktarma   | DirectQuery | Canlı Bağlantı  |
|-------------------------|----------|-------------|---------------|
|**Şema**               | X        | X           |               |
|**Ham veriler**             | X        |             |               |
|**Görsellerin veri önbelleği** | X        | X           | X             |

DirectQuery ile diğer sorgular arasındaki fark, Power BI hizmetinin bekleyen verileri nasıl işlediğini ve sorgunun şifrelenip şifrelenmediğini belirler. Aşağıdaki bölümlerde bekleyen ve taşınan veriler, ayrıca şifreleme, konum ve verilerin işlenme işlemi açıklanır.

### <a name="data-at-rest"></a>Bekleme durumundaki veriler

Veriler beklemedeyse Power BI hizmeti veri kümelerini, raporları ve pano kutucuklarını aşağıdaki alt bölümlerde açıklandığı şekilde depolar. Daha önce bahsedildiği gibi Power BI’da bekleyen veriler şifrelenir. Aşağıdaki bölümlerde ETL (Extract, Transform ve Load'un baş harfleri) Ayıklama, Dönüştürme ve Yükleme anlamında kullanılmıştır.

#### <a name="encryption-keys"></a>Şifreleme Anahtarları

- Azure Blob anahtarlarının şifreleme anahtarları Azure Key Vault’ta depolanır ve şifrelenir.
- Azure SQL Veritabanı TDE teknolojisinin şifreleme anahtarları Azure SQL'in kendisi tarafından yönetilir.
- Veri Taşıma hizmeti ve şirket içi veri ağ geçidinin şifreleme anahtarı şuralarda depolanır:
  - Şirket içi veri kaynakları için müşterinin altyapısındaki şirket içi veri ağ geçidinde
  - Bulut tabanlı veri kaynakları için Veri Taşıma Rolünde

Microsoft Azure Blob depolamayı şifrelemek için kullanılan Içerik şifreleme anahtarı (CEK) rastgele oluşturulmuş 256 bit anahtarıdır. CEK’nin içeriği şifrelemek için kullandığı algoritma AES\_CBC\_256’dır.

CEK’yi şifrelemek için kullanılan Anahtar Şifreleme Anahtarı (KEK) önceden tanımlanmış 256 bit bir anahtardır. KEK’nin CEK’yi şifrelemek için kullandığı algoritma A256KW’dur.

Kurtarma anahtarını temel alan ağ geçidi şifreleme anahtarları hiçbir zaman şirket içi altyapının dışına çıkmaz. Power BI şifrelenmiş şirket içi kimlik bilgilerinin değerlerine erişemez ve bu kimlik bilgilerine müdahale edemez; web istemcileri kimlik bilgilerini iletişim kurdukları belirli ağ geçidiyle ilişkili bir ortak anahtar kullanarak şifreler.

Bulut tabanlı veri kaynakları için Veri Taşıma Rolü şifreleme anahtarlarını [Always Encrypted](/sql/relational-databases/security/encryption/always-encrypted-database-engine) yöntemlerini kullanarak şifreler. [Always Encrypted veritabanı özelliği](/sql/relational-databases/security/encryption/always-encrypted-database-engine) hakkında daha fazla bilgi edinebilirsiniz.

#### <a name="datasets"></a>Veri kümeleri

1. Meta veriler (tablolar, sütunlar, ölçüler, hesaplamalar, bağlantı dizeleri vb.)

    a. Analysis Services şirket içi için, Azure SQL'de şifrelenmiş olarak depolanan bu veritabanının başvurusu dışında hiçbir şey depolanmaz.

    b. ETL, DirectQuery ve Veri Gönderimi'ne yönelik diğer tüm meta veriler Azure Blob depolama alanında şifrelenir ve depolanır.

1. Özgün veri kaynaklarının kimlik bilgileri
  
      a. Şirket içi Analysis Services: Hiçbir kimlik bilgisi gerekmediği için hiçbir kimlik bilgisi depolanmaz.

      b. DirectQuery: Bu, modelin doğrudan hizmette oluşturulup oluşturulmadığına göre değişir. Hizmette oluşturuluyorsa kimlik bilgileri bağlantı dizesinde depolanır ve Azure Blob’da şifrelenir. Model Power BI Desktop’tan içeri aktarılıyorsa kimlik bilgileri Veri Taşıma’nın Azure SQL Veritabanında şifrelenmiş olarak depolanır. Şifreleme anahtarı müşterinin altyapısında Ağ Geçidini çalıştıran makinede depolanır.

      c. Gönderilen veriler: Geçerli değil

      d. ETL

      - **Salesforce** veya **OneDrive** için: Yenileme belirteçleri Power BI hizmetinin Azure SQL Veritabanında şifrelenmiş olarak depolanır.
      - Aksi durumda:.
        - Veri kümesi yenileme için ayarlanırsa kimlik bilgileri Veri Taşıma’nın Azure SQL Veritabanında şifrelenmiş olarak depolanır. Şifreleme anahtarı müşterinin altyapısında Ağ Geçidini çalıştıran makinede depolanır.
        - Veri kümesi yenileme için ayarlanmazsa veri kaynakları için depolanan kimlik bilgileri yoktur

1. Veriler

    a. Analysis Services şirket içi ve DirectQuery: Power BI Hizmetinde hiçbir şey depolanmaz.

    b. ETL: Azure Blob depolama alanında şifrelenir ancak şu anda Power BI hizmetinin Azure Blob depolama alanında yer alan tüm veriler sunucu tarafı şifrelemesi olarak da bilinen [Azure Depolama Hizmeti Şifrelemesi (SSE)](/azure/storage/common/storage-service-encryption) kullanır. Multi-geo da SSE kullanır.

    c. Veri gönderimi v1: Azure Blob depolama alanında şifrelenmiş olarak depolanır ama şu anda Power BI hizmetinin Azure Blob depolama alanında yer alan tüm veriler sunucu tarafı şifrelemesi olarak da bilinen [Azure Depolama Hizmeti Şifrelemesi (SSE)](/azure/storage/common/storage-service-encryption) kullanır. Multi-geo da SSE kullanır. Gönderim verileri v1 2016 tarihinden itibaren kullanımdan kaldırılmıştır. 

    d. Veri gönderimi v2: Azure SQL’de şifrelenmiş olarak depolanır.

Power BI istemci tarafı şifrelemesi yaklaşımını kullanılır. Bu yaklaşımda Azure Blob depolama alanını şifrelemek için gelişmiş şifreleme standardıyla (AES) zincirleme blok şifreleme (CBC) modu kullanılır. [İstemci tarafı şifrelemesi hakkında daha fazla bilgi edinebilirsiniz.](/azure/storage/common/storage-client-side-encryption)

Power BI aşağıdaki yollarla veri bütünlüğünün izlenmesini sağlar:

* Azure SQL’de bekleyen veriler için Power BI SQL’in yerel tekliflerinin bir parçası olarak dbcc'yi, TDE'yi ve sürekli sayfa sağlama toplamını kullanır.

* Azure Blob depolama alanında bekleyen veriler için Power BI istemci tarafı şifrelemesi ve HTTPS kullanarak, verileri veri alımı sırasında veri bütünlüğünü denetleyen depolama alanlarına aktarır. [Azure Blob depolama güvenliği hakkında daha fazla bilgi edinebilirsiniz](/azure/storage/blobs/security-recommendations).

#### <a name="reports"></a>Raporlar

1. Meta veriler (rapor tanımı)

   a. Raporlar, Microsoft 365 raporları veya Power BI raporları için Excel olabilir. Aşağıdakiler, raporun türüne göre meta veriler için geçerlidir:
        
    &ensp;&ensp;a. Excel rapor meta verileri SQL Azure şifreli olarak depolanır. Meta veriler de Microsoft 365 depolanır.

    &ensp;&ensp;b. Power BI raporlar, Azure SQL veritabanı 'nda şifreli olarak depolanır.

2. Statik veriler

   Statik veriler, arka plan görüntüleri ve Power BI görselleri gibi yapıtları içerir.

    &ensp;&ensp;a. Microsoft 365 için Excel ile oluşturulan raporlarda hiçbir şey depolanmaz.

    &ensp;&ensp;b. Power BI raporları söz konusu olduğunda statik veriler Azure Blob depolama alanında depolanır ve şifrelenir.

3. Önbellekler

    &ensp;&ensp;a. Microsoft 365 için Excel ile oluşturulan raporlarda hiçbir şey önbelleğe alınmaz.

    &ensp;&ensp;b. Power BI raporlarında, gösterilen raporların görsellerinin verileri aşağıdaki bölümde açıklanan görsel veri önbelleğinde önbelleğe alınır ve depolanır.
 

4. Özgün Power BI Desktop (.pbix) veya Excel (.xlsx) dosyaları Power BI’da yayımlanır

    Bazen .xlsx veya .pbix dosyalarının bir kopyası veya gölge kopyası Power BI’ın Azure Blob depolama alanında depolanabilir ve bu durumda veriler şifrelenir. Power BI hizmetindeki Azure Blob depolama alanında depolanan bu tür raporların tümü sunucu tarafı şifrelemesi olarak da bilinen [Azure Depolama Hizmeti Şifrelemesi (SSE)](/azure/storage/common/storage-service-encryption) kullanır. Multi-geo da SSE kullanır.

#### <a name="dashboards-and-dashboard-tiles"></a>Panolar ve Pano Kutucukları

1. Önbellekler: panodaki görsellerin gerek duyduğu veriler genellikle önbelleğe alınır ve aşağıdaki bölümde açıklanan görsel veri önbelleğinde depolanır. Excel veya SQL Server Reporting Services’in (SSRS) sabitlenmiş görselleri gibi diğer kutucuklar Azure Blob’da resim olarak depolanır ve onlar da şifrelenir.

2. Statik veriler: arka plan görüntüleri ve Azure Blob depolama alanında depolanan, şifrelenen Power BI görseller gibi yapıtlar içerir.

Microsoft, kullanılan şifreleme yönteminden bağımsız olarak, müşterilerin adına anahtar şifrelemesini yönetir.

#### <a name="visual-data-cache"></a>Görsel veri önbelleği

Görsel veriler, veri kümesinin Power BI Premium kapasitede barındırılmasına bağlı olarak farklı konumlarda önbelleğe alınır. Bir kapasitede barındırılmayan veri kümelerinde görsel veriler önbelleğe alınır ve bir Azure SQL veritabanında şifrelenir. Bir kapasitede barındırılan veri kümelerinde, görsel veriler aşağıdaki konumlardan herhangi birinde önbelleğe alınabilir:

* Azure Blob Depolama
* Azure Premium dosyaları
* Power BI Premium kapasitesi düğümü


### <a name="data-transiently-stored-on-non-volatile-devices"></a>Geçici Olmayan Cihazlarda Geçici Olarak Depolanan Veriler

Geçici olmayan cihazlar, sabit güç olmadan devam eden belleğe sahip cihazlardır. Aşağıda geçici olmayan cihazlarda geçici bir süre depolanan veriler açıklanır. 

#### <a name="datasets"></a>Veri kümeleri

1. Meta veriler (tablolar, sütunlar, ölçüler, hesaplamalar, bağlantı dizeleri vb.)

2. Şemayla ilgili bazı yapıtlar sınırlı bir süre için işlem düğümlerinin diskinde depolanabilir. Ayrıca bazı yapıtlar sınırlı bir süre için şifrelenmemiş olarak Azure REDIS Cache'de de depolanabilir.

3. Özgün veri kaynaklarının kimlik bilgileri

    a. Analysis Services şirket içi: Hiçbir şey depolanmaz

    b. DirectQuery: Bu, modelin doğrudan hizmette oluşturulup oluşturulmadığına göre değişir. Hizmette oluşturuluyorsa şifrelenmiş biçimde bağlantı dizesinde depolanır ve yine burada düz metin olarak şifreleme anahtarı da bulunur. Model, Power BI Desktop’tan içeri aktarılıyorsa geçici olmayan cihazlarda kimlik bilgileri depolanmaz.

    > [!NOTE]
    > Hizmet tarafı modeli oluşturma özelliği 2017 ' den itibaren kullanımdan kaldırılmıştır.

    c. Gönderilen veriler: Yok (geçerli değil)

    d. ETL: Yok (işlem düğümünde hiçbir şey depolanmaz ve yukarıda **Bekleyen Veriler** bölümünde açıklanan durumdan farkı yoktur)
4. Veriler

    Bazı veri yapıtları sınırlı bir süre için işlem düğümlerinin diskinde depolanabilir.

### <a name="data-in-process"></a>İşlemdeki veriler

Veriler, etkin olarak kullanılırken veya bir kullanıcı tarafından erişildiğinde işlemde olur. Örneğin, kullanıcı bir veri kümesine erişirse, pano veya raporu düzeltir ya da değiştirirse, yenileme gerçekleştirildiğinde veya diğer olası veri erişimi etkinliklerinde veri işlemdedir. Bu olaylardan herhangi biri gerçekleştiğinde ve veri işleme alındığında Power BI hizmetindeki **Veri Rolü** bellek içi bir Analysis Services (AS) veritabanı oluşturur ve veri kümesi bu bellek içi Analysis Services veritabanına yüklenir. Veri kümesinin bir DirectQuery’yi temel alıp almadığına bağlı olarak AS veritabanında yüklenen verilerin şifresi **Veri Rolü**’nün erişimini sağlamak amacıyla çözülür ve Power BI hizmetinin veri kümesine ihtiyacı kalmayana kadar sonraki erişimler için bellekte tutulur. Power BI Premium aboneliği olan müşteriler için, Power BI müşterinin ayrı olarak sağlanan Power BI sanal makineler koleksiyonunda bellek içi bir Analysis Services (AS) veritabanı oluşturur.

Veriler üzerinde işlem yapıldığında (bu işlem verileri başlangıçta Power BI'a yüklemeyi içerir), veri kümesinin DirectQuery'yi temel alıp almamasına bakılmaksızın Power BI hizmeti görselleştirme verilerini şifrelenmiş **Azure SQL Veritabanı** içinde önbelleğe alabilir.

Power BI işlemdeki verilerin veri bütünlüğünü izlemek için HTTPS, TCP/IP ve TLS kullanarak taşıma sırasında verilerin şifrelendiğinden emin olur ve bütünlüğünü korur.

## <a name="user-authentication-to-data-sources"></a>Veri Kaynaklarına Yönelik Kullanıcı Kimlik Doğrulaması

Her veri kaynağıyla, Kullanıcı oturum açma bilgilerini temel alan bir bağlantı kurar ve bu kimlik bilgileriyle verilere erişir. Kullanıcılar temel alınan verilere dayalı sorgular, panolar ve raporlar oluşturabilir.

Kullanıcı sorguları, panoları, raporları veya herhangi bir görselleştirmeyi paylaştığında bu verilere ve görselleştirmelere erişim, temel alınan veri kaynaklarının Rol Düzeyi Güvenlik (RLS) desteği olup olmamasına bağlıdır.

Temel alınan veri kaynağı **Power BI’ın**** Rol Düzeyi Güvenlik (RLS)** özelliğine sahipse, Power BI hizmeti bu rol düzeyi güvenliği uygular ve kimlik bilgileri temel alınan verilere (bir panoda, raporda veya diğer veri yapıtlarında kullanılan sorgular olabilir) erişmeye yeterli olmayan kullanıcılar gerekli ayrıcalıklara sahip olmadıkları verileri göremez. Kullanıcının temel alınan verilere erişimi panoyu veya raporu oluşturan kullanıcıdan farklıysa, görselleştirmeler ve diğer yapıtlar yalnızca kullanıcının verilere erişim düzeyine göre görüntülenir.

Veri kaynağı RLS **uygulamıyorsa**, Power BI oturum açma kimlik bilgileri temel alınan veri kaynağına uygulanır. Bağlantı sırasında başka kimlik bilgileri sağlanırsa, sağlanan bu kimlik bilgileri uygulanır. Kullanıcı, RLS olmayan veri kaynaklarından Power BI hizmetine veri yüklediğinde, veriler bu belgenin **Veri Depolama ve Taşıma** bölümünde açıklandığı gibi Power BI’da depolanır. RLS olmayan veri kaynakları için veriler diğer kullanıcılarla paylaşıldığında (pano veya rapor aracılığıyla olabilir) veya veri yenilemesi yapıldığında verilere erişmek ya da verileri görüntülemek için özgün kimlik bilgileri kullanılır.

![Rol düzeyi güvenlik (RLS)](media/whitepaper-powerbi-security/powerbi-security-whitepaper_10.png)

RLS ve RLS olmayan veri kaynaklarını karşılaştırmak için örnek olarak Sam’in bir rapor ve pano oluşturup Abby ve Ralph ile paylaştığını düşünün. Rapor ve panoda kullanılan veri kaynakları RLS desteği **olmayan** veri kaynaklarından geliyorsa, hem Abby hem de Ralph Sam’in panosunda bulunan verileri (Power BI hizmetine yüklenen veriler) görebilir ve ikisi de bu verilerle etkileşim kurabilir. Buna karşılık, Sam RLS desteği olan veri kaynaklarından rapor veya pano oluşturup Abby ve Ralph ile paylaşırsa Abby panoyu görüntülemeye çalıştığında şunlar olur:

1. Pano RLS veri kaynağından oluşturulduğu için pano görselleştirmesi, Power BI hizmeti panonun temel aldığı sorgu ile ilişkili bağlantı dizesinde belirtilen mevcut veri kümesini almak için veri kaynağını sorgularken kısaca bir &quot;yükleniyor&quot; iletisi gösterir.

2. Abby’nin kimlik bilgileri ve rolüne göre verilere erişim sağlanır ve veriler alınır. Yalnızca Abby’nin yeterli yetkiye sahip olduğu veriler pano ve rapora yüklenir.

3. Pano ve rapordaki görselleştirmeler Abby’nin rol düzeyine göre görüntülenir.

Paylaşılan pano veya rapora Ralph erişirse, onun rol düzeyine bağlı olarak aynı olaylar zinciri gerçekleşir.

## <a name="power-bi-mobile"></a>Power BI Mobil

Power BI Mobil, üç birincil mobil platform için tasarlanan uygulamalar koleksiyonudur: Android, iOS ve Windows Mobile. Power BI Mobil uygulamalarının güvenlik yaklaşımları iki kategoriye ayrılır:

* Cihaz iletişimi
* Cihazdaki uygulama ve veriler

**Cihaz iletişimi** için, tüm Power BI Mobil uygulamaları Power BI hizmetiyle iletişim kurar ve tarayıcının kullandığı bağlantı ve kimlik doğrulaması dizilerinin aynılarını kullanır (bu teknik incelemenin önceki bölümlerinde ayrıntılı olarak açıklanmıştır). iOS ve Android Power BI mobil uygulamaları, uygulamanın içinde bir tarayıcı oturumu açar ve Windows mobil uygulaması Power BI ile iletişim kanalı başlatmak için bir aracı getirir.

Aşağıdaki tabloda mobil cihazın platformuna göre Power BI Mobil için sertifika tabanlı kimlik doğrulaması (CBA) desteği listelenir:

| **CBA Desteği** | **iOS** | **Android** | **Windows** |
| --- | --- | --- | --- |
| **Power BI** (hizmette oturum açın) | destekleniyor | destekleniyor | Desteklenmez |
| **SSRS ADFS** (SSRS sunucusuna bağlanın) | Desteklenmez | Desteklenir | Desteklenmez |

Power BI Mobil uygulamaları Power BI hizmetiyle etkin bir iletişim kurar. Mobil uygulamanın kullanım istatistiklerini ve benzer verileri toplamak için telemetri kullanılır. Bu telemetri kullanım ve etkinliği izlemek için kullanılan hizmetlere iletilir; telemetri verileriyle birlikte hiçbir kişisel veri gönderilmez.

**Cihazdaki Power BI uygulaması**, cihazda uygulamanın kullanımını kolaylaştıran verileri depolar:

* Azure Active Directory ve yenileme belirteçleri cihazda endüstri standardı güvenlik önlemleri kullanılarak güvenli bir mekanizmada depolanır.

* Veriler cihazın depolama alanında önbelleğe alınır ve uygulamanın kendisi tarafından doğrudan şifrelenmez

* Ayarlar da cihazda şifrelenmemiş olarak depolanır hiçbir gerçek kullanıcı verisi depolanmaz.

Power BI Mobil'den gelen veri önbelleği iki hafta süreyle veya şunlardan biri gerçekleşene kadar cihazda kalır: uygulamanın kaldırılması, kullanıcının Power BI Mobil oturumunu kapatması veya kullanıcının oturum açamaması (örneğin belirteç süre sonu olayı veya parola değişikliği gibi). Veri önbelleği daha önce Power BI Mobil uygulamasından erişilen panoları ve raporları içerir.

Power BI Mobil uygulamaları cihazdaki klasörlere bakmaz. 

Power BI Mobil'in sağlandığı platformların üçü de, mobil cihaz ve uygulama yönetimi sağlayan yazılım hizmeti Microsoft Intune'u destekler. Intune etkinleştirilip yapılandırıldığında, mobil cihazlardaki veriler şifrelenir ve Power BI uygulamasının kendisi bir SD karta yüklenemez. [Microsoft Intune hakkında daha fazla bilgi edinebilirsiniz](https://www.microsoft.com/cloud-platform/microsoft-intune).

## <a name="power-bi-security-questions-and-answers"></a>Power BI Güvenlik Soruları ve Yanıtları

Aşağıda, Power BI için yaygın olarak kullanılan sorular ve yanıtlar verilmiştir. Bunlar, bu teknik inceleme güncelleştirildiğinde yeni soruları ve yanıtları hızla bulabilmeniz için buraya eklendikleri sırayla düzenlenmiştir. En yeni sorular bu listenin sonuna eklenmiştir.

**Kullanıcılar Power BI'ı kullanırken nasıl bağlantı kurabilir ve veri kaynaklarına erişebilir?**

* **Power BI kimlik bilgileri ve etki alanı kimlik bilgileri:** Kullanıcılar bir e-posta adresi kullanarak Power BI oturum açtığında; bir Kullanıcı bir veri kaynağına bağlanmaya çalıştığında, Power BI Power BI oturum açma e-posta adresini kimlik bilgileri olarak geçirir. Etki alanına bağlı kaynaklar için (şirket içi veya bulut tabanlı), erişime izin vermeye yetecek kimlik bilgilerinin mevcut olup olmadığını saptamak için oturum açma e-postası dizin hizmeti tarafından bir _Kullanıcı Asıl Adı_ ([UPN](/windows/win32/secauthn/user-name-formats)) ile eşleştirilir. Power BI oturum açmak için iş tabanlı e-posta adreslerini kullanan kuruluşlarda (gibi iş kaynaklarında oturum açmak için kullandıkları e-posta _david@contoso.com_ ), eşleme sorunsuz bir şekilde gerçekleşebilir; iş tabanlı e-posta adresleri kullanmayan kuruluşlar (gibi _david@contoso.onmicrosoft.com_ ), oturum açma kimlik bilgileriyle Power BI şirket içi kaynaklara erişime izin vermek için Dizin eşlemesi oluşturulmalıdır.

* **SQL Server Analysis Services ve Power BI:** Şirket içi SQL Server Analysis Services kullanan kuruluşlar için Power BI, Power BI şirket içi veri ağ geçidini (önceki bölümlerde başvurulduğu gibi bir **ağ geçidi**) sunmaktadır.  Power BI şirket içi veri ağ geçidi, veri kaynaklarında rol düzeyi güvenliği (RLS) zorunlu tutabilir. RLS hakkında daha fazla bilgi için, bu belgenin başlarındaki **Veri Kaynaklarına Yönelik Kullanıcı Kimlik Doğrulaması** bölümüne bakın. Ağ geçitleri hakkında daha fazla bilgi için bkz. Şirket [içi veri ağ geçidi](../connect-data/service-gateway-onprem.md).

  Bunlara ek olarak, kuruluşlar **çoklu oturum açma** (SSO) için Kerberos kullanabilir ve Power BI'dan SQL Server, SAP HANA ve Teradata gibi şirket içi veri kaynaklarına sorun yaşamadan bağlanabilir. Daha fazla bilgi edinmek ve belirli yapılandırma gereksinimlerini öğrenmek için bkz. [**Power BI'dan şirket içi veri kaynaklarına SSO için Kerberos kullanma**](../connect-data/service-gateway-sso-overview.md).

* **Etki alanı olmayan bağlantılar**: etki alanına katılmamış ve rol düzeyi GÜVENLIK (RLS) özelliğine sahip olmayan veri bağlantıları için, Kullanıcı bağlantı sırası sırasında kimlik bilgilerini sağlamalıdır ve Power BI bu da bağlantıyı kurmak için veri kaynağına geçirilir. İzinler yeterliyse, veriler veri kaynağından Power BI hizmetine yüklenir.

**Veriler Power BI'a nasıl aktarılır?**

* Veri kaynağından Power BI hizmetine bağlanmak için Power BI tarafından istenen ve iletilen tüm veriler aktarım sırasında HTTPS kullanılarak şifrelenir. Veri sağlayıcısıyla güvenli bir bağlantı kurulur ve ancak bu bağlantı kurulduktan sonra veriler ağdan geçer.

**Power BI rapor, pano veya model verilerini nasıl önbelleğe alır ve bu güvenli bir yöntem midir?**

* Veri kaynağına erişildiğinde Power BI hizmeti bu belgenin başlarındaki **Veri Depolama ve Taşıma** bölümünde açıklanan süreci izler.

**İstemciler web sayfası verilerini yerel olarak önbelleğe alır mı?**

* Tarayıcı istemcileri Power BI'a eriştiğinde, Power BI web sunucuları _Cache-Control_ yönergesini _no-store_ olarak ayarlar. Bu _no-store_ yönergesi tarayıcılara kullanıcı tarafından görüntülenmekte olan web sayfasını önbelleğe almamasını ve istemcinin önbellek klasöründe depolamamasını bildirir.

**Rol tabanlı güvenlik, rapor veya pano paylaşma ve veri bağlantıları hakkında ne olacak? Veri erişimi, pano görüntüleme, rapor erişimi veya yenileme bakımından nasıl çalışır?**

* **Rol Düzeyi Güvenliğin (RLS) etkinleştirilmediği** veri kaynaklarında bir pano, rapor veya veri modeli Power BI üzerinden başka kullanıcılarla paylaşılırsa, veriler görüntülenmek ve etkileşimli çalışılmak üzere paylaşıldığı kullanıcıların kullanımına sunulur. Power BI verilerin özgün kaynağında kullanıcıların kimliğini yeniden *doğrulamaz*; veriler Power BI'a yüklendikten sonra başka hangi kullanıcıların ve grupların verileri görüntüleyebileceğini yönetme sorumluluğu kaynak verilerde kimliği doğrulanan kullanıcıya aittir.

  Analysis Services veri kaynağı gibi **RLS** özellikli bir veri kaynağına veri bağlantıları kurulduğunda Power BI'da yalnızca pano verileri önbelleğe alınır. RLS özellikli veri kaynağından gelen verilerin kullanıldığı bir rapor veya veri kümesi Power BI'da her görüntülendiğinde veya bu veri kümesine her erişildiğinde, Power BI hizmeti veri kümesine erişerek kullanıcının kimlik bilgilerine göre verileri alır ve yeterli izinler varsa veriler söz konusu kullanıcı için rapora veya veri modeline yüklenir. Kimlik doğrulaması başarısız olursa kullanıcı bir hata görür.

  Daha fazla bilgi için bu belgenin başlarındaki **Veri Kaynaklarına Yönelik Kullanıcı Kimlik Doğrulaması** bölümüne bakın.

**Kullanıcılarımız, bazıları etki alanı kimlik bilgilerinden farklı kimlik bilgileri gerektiren her seferinde aynı veri kaynaklarına bağlanır. Her veri bağlantısı kurduklarında bu kimlik bilgilerini girmek zorunda kalmaktan kaçınabilirsiniz.**

* Power BI kullanıcıların birden çok farklı veri kaynağı için kimlik bilgileri oluşturmasına, sonra da bu veri kaynaklarından birine arka arkaya erişilirken söz konusu kimlik bilgilerini otomatik olarak kullanmasına olanak tanıyan [Power BI Personal Gateway](https://support.powerbi.com/knowledgebase/articles/649846) özelliğini sunar. Daha fazla bilgi için bkz. [Power BI Personal Gateway](https://support.powerbi.com/knowledgebase/articles/649846).

**Power BI Grupları nasıl çalışır?**

* Power BI Grupları kullanıcıların panoları, raporları ve veri modellerini oluştururken hazır takımlarla hızla ve kolayca işbirliği yapmasına olanak tanır. Örneğin, yakın çalıştığınız takımdaki herkesin üye olduğu bir Power BI Grubunuz varsa, Power BI'ın içinden Grubu seçerek takımınızdaki herkesle kolayca işbirliği yapabilirsiniz. Power BI Grupları Office 365 Evrensel Gruplarının eşdeğeridir (bu grupları [öğrenebilir](https://support.office.com/Article/Find-help-about-Groups-in-Office-365-7a9b321f-b76a-4d53-b98b-a2b0b7946de1), [oluşturabilir](https://support.office.com/Article/View-create-and-delete-Groups-in-the-Office-365-admin-center-a6360120-2fc4-46af-b105-6a04dc5461c7) ve [yönetebilirsiniz](https://support.office.com/Article/Manage-Group-membership-in-the-Office-365-admin-center-e186d224-a324-4afa-8300-0e4fc0c3000a)) ve verilerin güvenliğini sağlamak için Azure Active Directory'de kullanılan kimlik doğrulama mekanizmalarını kullanır. [Power BI'da grup oluşturabileceğiniz](https://support.powerbi.com/knowledgebase/articles/654250) gibi, Microsoft 365 yönetim merkezinde de Evrensel Grup oluşturabilirsiniz; Power BI'da grup oluşturma açısından her ikisi de aynı sonucu verir.

  Power BI Grupları ile paylaşılan verilerin güvenliğinde dikkate alınan noktaların Power BI'da paylaşılan tüm verilerle aynı olduğunu aklınızda bulundurun. **RLS özellikli olmayan** veri kaynaklarında Power BI verilerin özgün kaynağında kullanıcıların kimliğini yeniden **doğrulamaz**; veriler Power BI'a yüklendikten sonra başka hangi kullanıcıların ve grupların verileri görüntüleyebileceğini yönetme sorumluluğu kaynak verilerde kimliği doğrulanan kullanıcıya aittir. Daha fazla bilgi için bu belgenin başlarındaki **Veri Kaynaklarına Yönelik Kullanıcı Kimlik Doğrulaması** bölümüne bakın.

  [Power BI'daki Gruplar](https://support.powerbi.com/knowledgebase/articles/654247) hakkında daha fazla bilgi edinebilirsiniz.

**Şirket içi veri ağ geçidi ve kişisel ağ geçidi tarafından hangi bağlantı noktaları kullanılır? Bağlantı amaçları için izin verilmesi gereken etki alanı adları var mı?**

* Bu soruya ayrıntılı yanıtı şu bağlantıda bulabilirsiniz: [ağ geçidi bağlantı noktaları](/data-integration/gateway/service-gateway-communication#ports)

**Şirket içi veri ağ geçidiyle çalışırken, kurtarma anahtarları nasıl kullanılır ve nerede depolanır? Güvenli kimlik bilgisi yönetimi ne?**

* Ağ geçidi yüklemesi ve yapılandırması sırasında yönetici bir ağ geçidi **Kurtarma Anahtarı** yazar. Bu **Kurtarma anahtarı** , güçlü bir **AES** simetrik anahtar oluşturmak için kullanılır. Aynı anda **RSA** asimetrik anahtarı da oluşturulur.

    Oluşturulan bu anahtarlar (**RSA** ve **AES**) yerel makinedeki bir dosyada depolanır. Bu dosya da şifrelenmiştir. Dosya içeriğinin şifresi yalnızca söz konusu Windows makinesi tarafından ve yalnızca bu özel ağ geçidi hizmet hesabıyla çözülebilir.

    Bir kullanıcı Power BI hizmeti kullanıcı arabirimine veri kaynağının kimlik bilgilerini girdiğinde, kimlik bilgileri tarayıcıdaki ortak anahtarla şifrelenir. Ağ Geçidi, RSA özel anahtarını kullanarak kimlik bilgilerinin şifresini çözer ve veriler Power BI hizmeti depolanmadan önce AES Simetrik anahtarıyla yeniden şifreler. Bu işlemle, Power BI hizmeti hiçbir zaman şifrelenmemiş verilere erişmez.

**Şirket içi veri ağ geçidi hangi iletişim protokollerini kullanır ve bunların güvenliği nasıl sağlanır?**

* Ağ geçidi şu iki iletişim protokolünü destekler:

  - **AMQP 1,0 – TCP + TLS**: Bu protokol, giden iletişim için 443, 5671-5672 ve 9350-9354 bağlantı noktalarını gerektirir. İletişim yükü daha düşük olduğundan bu protokol tercih edilir.

  - **Https – WebSockets üzerinden https + TLS**: Bu protokol yalnızca 443 numaralı bağlantı noktasını kullanır. WebSocket tek bir HTTP CONNECT iletisiyle başlatılır. Kanal oluşturulduktan sonra iletişim temelde TCP+TLS iletişimidir. Ağ geçidini, [Şirket içi ağ geçidi makalesinde](/data-integration/gateway/service-gateway-communication#force-https-communication-with-azure-service-bus)açıklanan bir ayarı değiştirerek bu protokolü kullanmaya zorlayabilirsiniz.

**Power BI'da Azure CDN'nin rolü nedir?**

* Daha önce açıklandığı gibi, Power BI statik içeriği ve dosyaları coğrafi yerel ayara göre kullanıcılara verimli bir şekilde dağıtmak için **Azure Content Delivery Network** (CDN) hizmetini kullanır. Daha ayrıntılı açıklamak gerekirse, Power BI hizmeti genel İnternet üzerinden kullanıcılara gerekli statik içeriği ve dosyaları verimli bir şekilde dağıtmak için birden çok **CDN** kullanır. Bu statik dosyalar ürün indirmelerini (**Power BI Desktop**, **şirket içi veri ağ geçidi** veya çeşitli bağımsız hizmet sağlayıcılarından Power BI uygulamaları gibi), Power BI hizmetiyle sonraki bağlantıları başlatmak ve kurmak için kullanılan tarayıcı yapılandırma dosyalarını, ayrıca başlangıçtaki güvenli Power BI oturum açma sayfasını içerir.

  Power BI hizmetiyle ilk kurulan bağlantı sırasında sağlanan bilgiler temelinde, kullanıcının tarayıcısı tarayıcının Power BI hizmetiyle iletişimini etkinleştirmek için gereken belirli ortak dosyaların koleksiyonunu indirmek amacıyla belirtilen Azure **CDN** ile (veya bazı dosyalar için **WFE** ile) iletişime geçer. Tarayıcı sayfası, Power BI hizmeti tarayıcı oturumu süresince AAD belirtecini, oturum bilgilerini, ilişkili **Arka Uç** kümesinin konumunu ve Azure **CDN** ile **WFE** kümesinden indirilen dosya koleksiyonunu içerir.

**Power BI görselleri için, Microsoft, öğeleri galeriye yayımlamadan önce özel görsel kodu güvenlik veya gizlilik değerlendirmesi gerçekleştirsin mi?**

* Hayır. Özel görsel kodunu gözden geçirmek ve bu koda güvenilip güvenilmeyeceğini saptamak müşterinin sorumluluğundadır. Tüm özel görsel kodu korumalı alan ortamında çalıştırılır ve bu sayede özel görseldeki herhangi bir hatalı kodun Power BI hizmetinin kalanını olumsuz etkilemesi önlenir.

**Müşteri ağının dışına bilgi gönderen başka Power BI görselleri var mı?**

* Evet. Bing Haritalar ve ESRI görselleri, bu hizmetleri kullanan görseller için Power BI hizmetinin dışına veri iletir.

**Şablon uygulamaları için, Microsoft, öğeleri galeriye yayımlamadan önce şablon uygulamasının herhangi bir güvenlik veya gizlilik değerlendirmesi gerçekleştirmesini ister misiniz?**
* Hayır. Uygulama yayımcısı, müşterinin gözden geçirilmesi ve şablon uygulama yayımcısına güvenip güvenmeyeceğini tespit ederken içerikten sorumludur. 

**Müşteri ağı dışına bilgi gönderebilen şablon uygulamaları var mı?**
* Evet. Yayımcının gizlilik ilkesini gözden geçirmek ve şablon uygulamanın kiracıya yüklenip yüklenmeyeceğini öğrenmek müşterinin sorumluluğundadır. Ayrıca Yayımcı, uygulamanın davranış ve yeteneklerini bildirmekten sorumludur.

**Veri ne olacak? Verilerin ülke kenarlıklarını terk etmemesini sağlamak için, belirli coğrafi bölgelerde bulunan veri merkezlerinde kiracılar sağlayabiliriz.**

* Belirli coğrafi bölgelerdeki müşterilerin bir bölümü ulusal bulutta kiracı oluşturma seçeneğine sahiptir. Bu bulutta veri depolama ile işleme diğer tüm veri merkezlerinden ayrı tutulur. Ulusal bulut Power BI hizmetini Microsoft adına ayrı bir veri şirketi çalıştırdığından, ulusal bulutların güvenlik türü biraz farklıdır.

  Alternatif olarak müşteriler belirli bir bölgede kiracı ayarlayabilir ama bu tür kiracıların Microsoft'tan ayrı bir veri şirketi yoktur. Ulusal bulutların fiyatlandırması genel kullanıma sunulan ticari Power BI hizmetinden farklıdır. Ulusal bulutlar için Power BI hizmetinin kullanılabilirliği hakkında daha fazla bilgi için bkz. [Power BI ulusal bulutları](https://powerbi.microsoft.com/clouds/).

**Microsoft, Power BI Premium abonelikleri olan müşteriler için bağlantıları nasıl işler? Bu bağlantılar Premium olmayan Power BI hizmeti göre belirlenenlerden farklı midir?**

* Power BI Premium abonelikleri olan müşteriler için kurulan bağlantılar, erişim denetimi ve yetkilendirmesini etkinleştirmek için Azure Active Directory (AD) kullanarak [İşletmeler Arası (B2B)](/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b) yetkilendirme işlemi gerçekleştirir. Power BI, Power BI Premium abonelerinden Power BI Premium kaynaklarına yönelik bağlantıları da diğer Azure AD kullanıcıları için yaptığı gibi işler.

## <a name="conclusion"></a>Sonuç

Power BI hizmetinin mimarisi iki kümeye dayanır: Web Ön Ucu (WFE) kümesi ve Arka Uç kümesi. WFE kümesi, Power BI hizmetine yönelik ilk bağlantıdan ve kimlik doğrulamasından sorumludur. Kimlik doğrulaması yapıldıktan sonraki tüm kullanıcı etkileşimlerini Arka Uç üstlenir. Power BI, kullanıcı kimliklerini depolamak ve yönetmek için Azure Active Directory (AAD) hizmetini, verileri ve meta verileri depolamak ve yönetmek içinse Azure Blob ve Azure SQL Veritabanı hizmetlerini kullanır.

Power BI'da veri depolama ve veri işleme işlemleri, verilere DirectQuery kullanılarak erişilip erişilmediğine bağlı olarak değişir ve aynı zamanda veri kaynaklarının bulutta mı yoksa şirket içinde mi yer aldığına da bağlıdır. Power BI ayrıca Rol Düzeyi Güvenliği (RLS) zorunlu tutabilir ve şirket içi verilere erişim sağlayan Ağ Geçitleriyle etkileşim kurar.

## <a name="feedback-and-suggestions"></a>Geri Bildirim ve Öneriler

Geri bildirimleriniz bizim için önemlidir. Bu teknik incelemeyi ve Power BI'la ilgili diğer içeriği geliştirmeye, netleştirmeye veya bu içeriğe eklemeler yapmaya yönelik önerilerinizi duymak isteriz. Önerilerinizi uygulamasına gönderin [pbidocfeedback@microsoft.com](mailto:pbidocfeedback@microsoft.com) .

## <a name="additional-resources"></a>Ek Kaynaklar

Power BI'la ilgili daha fazla bilgi için aşağıdaki kaynaklara bakabilirsiniz.

- [Power BI’da Gruplar](https://support.powerbi.com/knowledgebase/articles/654247)
- [Power BI Desktop ile çalışmaya başlama](https://support.powerbi.com/knowledgebase/articles/471664)
- [Power BI REST API - Genel Bakış](/rest/api/power-bi/)
- [Power BI API başvurusu](/rest/api/power-bi/)
- [On-premises data gateway (Şirket içi veri ağ geçidi)](../connect-data/service-gateway-onprem.md)
- [Power BI Ulusal Bulutlar](https://powerbi.microsoft.com/clouds/)
- [Power BI Premium](https://aka.ms/pbipremiumwhitepaper)
- [Power BI’dan şirket içi veri kaynaklarına SSO için Kerberos kullanma](../connect-data/service-gateway-sso-overview.md)