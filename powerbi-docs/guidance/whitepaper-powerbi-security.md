---
title: Power BI güvenlik teknik incelemesi
description: Power BI yönelik güvenlik mimarisini ve uygulamasını açıklayan ve açıklayan bir Teknik İnceleme
author: paulinbar
ms.author: painbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi
ms.topic: conceptual
ms.date: 02/11/2021
LocalizationGroup: Conceptual
ms.openlocfilehash: 0c6fb504cd985103d811b820cc85212aaa72bc76
ms.sourcegitcommit: 9a00abaca80d0cdb2bd0cd9270f99db62df8a2ce
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/17/2021
ms.locfileid: "100569546"
---
# <a name="power-bi-security-white-paper"></a>Power BI güvenlik teknik incelemesi

**Özet:** Power BI, Microsoft 'un sunduğu ve kolayca self servis Iş zekası panoları, raporları, veri kümeleri ve görselleştirmeler oluşturmanıza olanak sağlayan bir çevrimiçi yazılım hizmetidir (*SaaS* veya hizmet olarak yazılım). Power BI ile birçok farklı veri kaynağına bağlanabilir, bu bağlantılardan gelen verileri birleştirip şekillendirebilir ve ardından başkalarıyla paylaşılabilen rapor ve panolar oluşturabilirsiniz.

**Yazarlar:** Yitzhak Kesselman, doldurma y Ostoa, Matt Netada, ıseencic, Srinivasan Turuvekere, cristia Petcupascu, adı Regev, Naveen Sivaraj, ben Glastein, Evgeny Tshiorny, Arthi Ramasubramanian Iyer, SID Jayadevan, Ronald Chang, Ori Ho ar, Anton Fritz, ıdan Sheınberg, Ron Gilad, Sagiv Hadaya, Paul Inbar, Igveya Uzhviev, Michael Roth, Ahtarquino, Gennady Pats, Orion Lee, Yury Berezansky, Maya Shenhav, Romit Chattopadhyay, Yarıv Maimon, Bogdan Crivat

**Teknik gözden geçirenler:** Cristia Petcutascu, Amir Netz, Sergei Gundorov

**Uygulama hedefi:** Power BI SaaS, Power BI Desktop, Power BI Premium, Power BI Embedded analiz, Power BI Mobil

> [!NOTE]
> Tarayıcınızdan **Yazdır** ' ı seçip **PDF olarak kaydet**' i seçerek bu teknik incelemeyi kaydedebilir veya yazdırabilirsiniz.

## <a name="introduction"></a>Giriş

Power BI, Microsoft’un çevrimiçi yazılım hizmeti (*SaaS* veya Hizmet olarak Yazılım) teklifidir. Bu hizmet, kolayca ve hızla self servis İş Zekası panoları, raporları, veri kümeleri ve görselleştirmeleri oluşturmanıza olanak tanır. Power BI ile birçok farklı veri kaynağına bağlanabilir, bu bağlantılardan gelen verileri birleştirip şekillendirebilir ve ardından başkalarıyla paylaşılabilen rapor ve panolar oluşturabilirsiniz.

Dünya hızla değişiyor; kuruluşlar hızlandırılmış dijital dönüşümden geçerek, uzaktan çalışırken büyük bir artış, çevrimiçi hizmetler için artan müşteri talebi ve işlemler ve iş kararı verme konusunda gelişmiş teknolojilerin kullanımını arttıracağız. Tüm bu bulut tarafından desteklenir.

Buluta geçiş, bir Trickle 'nın bir taşla ve bununla birlikte gelen yeni, ortaya çıkan yüzey alanıyla aynı olduğundan daha fazla şirket, bulutta ne kadar güvenli bir şekilde *veri olduğunu* soruyor? ve *hassas verilerin sızmasını engellemek için ne kadar uçtan uca koruma var?* Ve genellikle kuruluştaki en çok stratejik bilgilerin bazılarını ele alan bı platformları için, bu sorular çok önemlidir.

Bı güvenlik modeli-nesne düzeyi ve satır düzeyi güvenliği 'nin Decades-eski temelleri, hala önemli, bulut dönemi içinde gerekli güvenlik türünü sağlamak için de artık önemli değildir. Bunun yerine, kuruluşların iş zekası verileri için bulut Yerel, çok katmanlı, derinlemesine savunma güvenlik çözümü araması gerekir.

Power BI, veriler için sektör lideri tam ve hermetic korumasını sağlamak üzere oluşturulmuştur. Ürün, sektörde bulunan en yüksek güvenlik sınıflandırmalarını kazanmıştır ve günümüzde çok sayıda Ulusal Güvenlik Kurumu, finans kurumları ve sağlık hizmetleri sağlayıcılarının en hassas bilgileriyle bu bilgilere güvenir.

Hepsi, temel ile başlar. Erken bir andan itibaren, Microsoft, güvenlik açıklarını gidermeye yönelik büyük yatırımlar yaptı ve aşağıdaki yıllardır çalıştırdığından, makine yongasında BIOS çekirdeği kadar derin olan ve son kullanıcı deneyimine kadar olan çok güçlü bir güvenlik yığını sunuyor. Bu derin yatırımlar devam eder ve bugün 3.500 ' den fazla Microsoft mühendisleri, Microsoft 'un güvenlik yığınını oluşturup geliştirmeye ve sürekli olarak değiştirme tehlikesi yataya daha etkin bir şekilde nasıl bir şekilde ele almaya Milyarlarca bilgisayar, trilyon oturum açma bilgileri ve Microsoft 'un korumasına güvenmiş olan bilgi zettabytes, şirket artık teknik sektörde en gelişmiş güvenlik yığınına sahiptir ve kötü amaçlı aktörlere karşı genel lider olarak büyük ölçüde görüntülenir.

Bu çok güçlü bir temel üzerinde yapılar Power BI. Bu, dünyanın en hassas verilerini sunma ve koruma hakkını karşılayan aynı güvenlik yığınını kullanır ve Microsoft 365 en gelişmiş Information Protection ve uyumluluk araçlarıyla tümleştirilir. Bunların en üstünde, bulut dönemi 'nin benzersiz güçlükleriyle başa çıkmak için tasarlanan uçtan uca koruma ile sonuçlanan, çok katmanlı güvenlik önlemleri aracılığıyla güvenlik sağlar.

Hassas varlıkları korumaya yönelik uçtan uca bir çözüm sağlamak için, ürün ekibinin birden çok eş zamanlı müşteri sorunlarını ele vermesi gerekir:
* *Kimlerin bağlanabileceği, nereden bağlandıkları ve nasıl bağlanabileceği nasıl denetliyoruz?* *Bağlantıları nasıl denetliyoruz?*
* *Veriler nasıl depolanır?* *Nasıl şifrelenir?* *Verilerim üzerinde hangi denetimleri var?*
* *Hassas verileri denetlemek ve korumak Nasıl yaparım??* *Bu verilerin kuruluş dışından sızmasını Nasıl yaparım? emin misiniz?*
* *Hangi işlemleri yürüttüğü Nasıl yaparım? denetim mi?* *Hizmette şüpheli etkinlik varsa Nasıl yaparım? hızlı bir şekilde tepki veriyor musunuz?*

Bu makalede tüm bu sorulara kapsamlı bir yanıt sunulmaktadır. Hizmet mimarisine genel bir bakış ile başlar ve sistemdeki ana akışların nasıl çalıştığını açıklar. Daha sonra kullanıcıların Power BI kimlik doğrulaması yapma, veri bağlantılarının nasıl oluşturulduğu ve Power BI hizmet aracılığıyla verileri nasıl depolayıp taşıdığına ilişkin açıklamayı anlatmaktadır. Son bölümde, hizmet yöneticisi olarak en değerli varlıklarınızı korumak için size izin veren güvenlik özellikleri açıklanmaktadır.

Power BI hizmeti [Microsoft Online Services Koşulları](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=31) ve [Microsoft Kurumsal Gizlilik Bildirimi](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx) koşullarına tabidir. Veri işleme konumu için, [Microsoft Online Services koşullarında](http://www.microsoftvolumelicensing.com/Downloader.aspx?DocumentId=9555) veri Işleme koşullarının konumunu ve [veri koruma eki](https://www.microsoft.com/download/details.aspx?id=101581)' ne bakın. Uyumluluk bilgileri için [Microsoft Güven Merkezi](https://www.microsoft.com/trustcenter) Power BI’ın birincil kaynağıdır. Power BI takımı müşterilerine en son yenilikleri ve üretkenlik çözümlerini getirmek için çalışıyor. [Microsoft Uyumluluk teklifleriyle](/compliance/regulatory/offering-home)uyumluluk hakkında daha fazla bilgi edinin.

Power BI hizmeti, güvenlik güvencesi ve uyumluluk gereksinimlerini destekleyen güvenlik geliştirme yaşam döngüsü (SDL) ve sıkı güvenlik uygulamalarına uyar. SDL, geliştiricilerin yazılım içindeki güvenlik açıklarının sayısını ve önem derecesini azaltarak daha güvenli yazılım oluşturmalarına yardımcı olur, ancak geliştirme maliyetini azaltır. [Microsoft güvenlik geliştirme yaşam döngüsü uygulamalarından](https://www.microsoft.com/securityengineering/sdl/practices)daha fazla bilgi edinin.

## <a name="power-bi-architecture"></a>Power BI mimarisi

Power BI hizmeti, Microsoft 'un [bulut bilgi işlem platformu](https://azure.microsoft.com/overview/what-is-azure/)olan Azure 'da oluşturulmuştur. Power BI şu anda dünyanın her yerinde birçok veri merkezine dağıtılmıştır. Bu veri merkezlerinin hizmet verdiği bölgelerdeki müşterilerin kullanıma sunulan çok sayıda etkin dağıtım bulunur ve her etkin dağıtım için yedekleme işlevi gören, edilgen dağıtımlar vardır.

![WFE ve Arka Uç](media/whitepaper-powerbi-security/powerbi-security-whitepaper_01.png)

### <a name="web-front-end-cluster-wfe"></a>Web ön uç kümesi (WFE)

WFE kümesi, Kullanıcı tarayıcısına site yüklemede ilk HTML sayfası içeriğini sağlar ve istemcilerin kimliğini doğrulamak ve Power BI arka uç hizmetine sonraki istemci bağlantıları için belirteçler sağlamak üzere Azure Active Directory (Azure AD) kullanarak Power BI için ilk bağlantı ve kimlik doğrulama sürecini yönetir.

![WEF Kümesi](media/whitepaper-powerbi-security/powerbi-security-whitepaper_02.png)

WFE kümesi, [Azure App Service ortamı](/azure/app-service/environment/intro)çalıştıran bir ASP.NET Web sitesinden oluşur. Kullanıcılar Power BI hizmeti bağlanmayı denediklerinde, istemcinin DNS hizmeti, Power BI dağıtımıyla en uygun (genellikle en yakın) veri merkezini bulmak için Azure Traffic Manager ile iletişim kurabilir. Bu işlem hakkında daha fazla bilgi için bkz. [Azure Için performans trafiği-yönlendirme yöntemi Traffic Manager](/azure/traffic-manager/traffic-manager-routing-methods#performance-traffic-routing-method).

Kullanıcıya atanan WFE kümesi, oturum açma ve kimlik doğrulama sırasını (Bu makalede daha sonra açıklanmıştır) yönetir ve kimlik doğrulaması başarılı olduktan sonra bir Azure AD erişim belirteci alır. WFE kümesi içindeki ASP.NET bileşeni, kullanıcının hangi kuruluşa ait olduğunu belirleyen belirteci ayrıştırır ve sonra Power BI küresel hizmetine bakar. WFE, kuruluşun kiracısının hangi arka uç kümesinin barındırıldığı tarayıcıya belirtir. Bir kullanıcının kimliği doğrulandıktan sonra, müşteri verileri için sonraki istemci etkileşimleri, bu istekler için WFE intermediator olmadan doğrudan arka uç veya Premium kümeyle gerçekleştirilir.

**. Js*, **. css* ve resim dosyaları gibi statik kaynaklar çoğunlukla Azure Content Delivery Network (CDN) üzerinde depolanır ve doğrudan tarayıcı tarafından alınır. Evereksel kamu kümesi dağıtımlarının bu kural için bir özel durum olduğunu ve uyumluluk nedenlerinin, statik içeriği barındırmak için uyumlu bir bölgeden WFE kümesi kullanmasını unutmayın.

### <a name="power-bi-back-end-cluster-be"></a>Arka uç kümesi Power BI ()

Arka uç kümesi, Power BI bulunan tüm işlevlerin omurgası olur. Web ön ucu ve API istemcilerinin yanı sıra arka plan çalışma Hizmetleri, veritabanları, önbellekler ve diğer diğer bileşenler tarafından tüketilen çeşitli hizmet uç noktalarından oluşur.

Arka uç Azure bölgelerinde kullanılabilir ve kullanılabilir hale geldiğinde yeni bölgelerde dağıtılır. Tek bir Azure bölgesi, tek bir kümenin dikey ve yatay ölçeklendirme sınırları bittiğinde Power BI hizmeti sınırsız yatay ölçeklendirmeye izin veren bir veya daha fazla arka uç kümesi barındırır.

Her bir arka uç kümesinin durum bilgisi vardır ve bu kümeye atanan tüm kiracıların tüm verilerini barındırır. Belirli bir kiracının verilerini içeren bir küme, kiracının ana kümesi olarak adlandırılır. Kimliği doğrulanmış bir kullanıcının giriş kümesi bilgileri küresel hizmet tarafından sağlanır ve Web ön ucu tarafından, istekleri kiracının ana kümesine yönlendirmek için kullanılır.

Her arka uç kümesi, belirli görevleri gerçekleştirmek için ayarlanmış birden çok yeniden boyutlandırılabilir ölçek kümesi, SQL veritabanları, depolama hesapları, hizmet yolları, önbellekler ve diğer gerekli bulut bileşenleri gibi durum bilgisi olan birden fazla sanal makineden oluşur.

Kiracı meta verileri ve verileri, aynı Azure Coğrafya 'daki eşleştirilmiş bir Azure bölgesindeki ikincil arka uç kümesine veri çoğaltması haricinde küme sınırları içinde depolanır. İkincil arka uç kümesi, bölgesel kesinti olması durumunda bir yük devretme kümesi işlevi görür ve başka herhangi bir zamanda pasif bir durumdur.

Arka uç işlevselliği, genel İnternet 'ten erişilebilen iki bileşen dışında, kümenin sanal ağı içindeki farklı makinelerde çalışan mikro hizmetler tarafından sunulur:
* Ağ geçidi hizmeti
* Azure API Management

![Arka uç kümesi](media/whitepaper-powerbi-security/powerbi-security-whitepaper_03.png)

### <a name="power-bi-premium-infrastructure"></a>Power BI Premium altyapısı

Power BI Premium, veri akışları, sayfalandırılmış raporlar, AI vb. gibi Premium Power BI özellikleri gerektiren aboneler için bir hizmet sunar. Bir müşteri Power BI Premium aboneliğine kaydolduğunda, Premium kapasite Azure Resource Manager üzerinden oluşturulur.

Power BI Premium kapasiteleri, düzenli Power BI arka uçtan bağımsız olan arka uç kümelerinde barındırılır – yukarıya bakın). Bu, Premium teklifin daha iyi yalıtımı, kaynak ayırma, desteklenebilirlik, güvenlik yalıtımı ve ölçeklenebilirlik sağlar.

Aşağıdaki diyagramda Power BI Premium altyapısının mimarisi gösterilmektedir:

![Power BI Premium](media/whitepaper-powerbi-security/powerbi-security-whitepaper_05.png)

Power BI Premium altyapısına bağlantı, Kullanıcı senaryosuna bağlı olarak çeşitli yollarla yapılabilir. Power BI Premium istemcileri bir kullanıcının tarayıcısı, düzenli bir Power BI arka ucu, XMLA istemcileri, ARM API 'Leri aracılığıyla doğrudan bağlantılar olabilir.

Bir Azure bölgesindeki Power BI Premium altyapısı, birden çok Power BI Premium kümesinden (en az bir adet) oluşur. Premium kaynakların çoğunluğu bir küme içinde (örneğin, işlem) kapsüllenir ve bazı yaygın bölgesel kaynaklar (örneğin, meta veri depolaması) vardır. Premium altyapı, bir bölgede yatay ölçeklenebilirlik elde etmenin iki yolunu sağlar: kümeler içindeki kaynakları artırma ve/veya isteğe bağlı olarak, gerektiğinde daha fazla küme ekleme (küme kaynakları sınırlara yaklaşıyorsa).

Her kümenin omurgası, [Sanal Makine Ölçek Kümeleri (VMSS)](/azure/virtual-machine-scale-sets/overview) ve [Azure Service Fabric](/azure/service-fabric/service-fabric-overview)tarafından yönetilen işlem kaynaklarıdır. VMSS ve Service Fabric işlem düğümlerinin kullanımı arttıkça ve Power BI Premium Hizmetleri ve uygulamaları dağıtım, yönetim ve izleme işlemlerini genişleyerek, işlem düğümlerinin hızlı ve sorunsuz artışına izin verir.

Güvenli ve güvenilir bir altyapının bulunduğu çok sayıda kaynak vardır: yük dengeleyiciler, sanal ağlar, ağ güvenlik grupları, hizmet veri yolu, depolama vb. Power BI Premium için gereken gizli dizi, anahtar ve sertifikalar, [Azure Key Vault](/azure/key-vault/general/basic-concepts) tarafından özel olarak yönetilir. Herhangi bir kimlik doğrulaması, yalnızca Azure AD ile tümleştirme aracılığıyla yapılır.

Power BI Premium altyapısına gelen tüm istekler öncelikle ön uç düğümlerine gider. Bunlar, dış bağlantılar için kullanılabilen tek düğümlerdir. Kaynakların geri kalanı sanal ağların arkasına gizlenir. Ön uç düğümleri isteğin kimliğini doğrular, işler veya uygun kaynaklara (örneğin, arka uç düğümleri) iletir.

Arka uç düğümleri Power BI Premium özelliklerinin ve özelliklerinin çoğunu sağlar.

### <a name="power-bi-mobile"></a>Power BI Mobil

Power BI Mobil, üç birincil mobil platform için tasarlanan uygulamalar koleksiyonudur: Android, iOS ve Windows (UWP). Power BI Mobil uygulamalar için güvenlik konuları iki kategoriye ayrılır:
* Cihaz iletişimi
* Cihazdaki uygulama ve veriler

Cihaz iletişiminde, tüm Power BI Mobil uygulamalar Power BI hizmeti iletişim kurar ve tarayıcılar tarafından kullanılan bağlantı ve kimlik doğrulama dizilerini kullanır ve bu teknik incelemeye daha önce ayrıntılı olarak açıklanmıştır. İOS ve Android için Power BI mobil uygulamalar, uygulamanın kendisi içinde bir tarayıcı oturumu getirir. Windows mobil uygulaması, iletişim kanalını Power BI (oturum açma işlemi için) kurmak için bir aracı getirir.

Aşağıdaki tabloda, mobil cihaz platformuna göre Power BI Mobil için sertifika tabanlı kimlik doğrulaması (CBA) desteği gösterilmektedir:


|CBA desteği  |iOS  |Android  |Windows  |
|---------|---------|---------|---------|
|Power BI (hizmette oturum açın)    |Desteklenir         |Desteklenir         |Desteklenmez         |
|SSRS ADFS on-Pred (SSRS sunucusuna bağlan)     |Desteklenmez         |Desteklenir         |Desteklenmez         |
|SSRS uygulama proxy 'Si     |Desteklenir         |Desteklenir         |Desteklenmez         |

Power BI Mobil uygulamaları Power BI hizmetiyle etkin bir iletişim kurar. Telemetri, kullanımı ve etkinlikleri izlemek için kullanılan hizmetlere aktarılan mobil uygulama kullanımı istatistiklerini ve benzer verileri toplamak için kullanılır; Telemetri ile hiçbir müşteri verisi gönderilmez.

Power BI uygulaması, uygulamanın kullanımını kolaylaştıran verileri cihazda depolar:
* Azure AD ve yenileme belirteçleri, sektör standardı güvenlik önlemleri kullanılarak cihazda güvenli bir mekanizmaya depolanır.
* Veriler ve ayarlar (Kullanıcı Yapılandırması için anahtar-değer çiftleri) cihazdaki depolamada önbelleğe alınır ve işletim sistemi tarafından şifrelenebilir. İOS 'ta, Kullanıcı bir geçiş kodu ayarladığında bu otomatik olarak yapılır. Android 'de bu, ayarlarda yapılandırılabilir. Windows 'da, BitLocker kullanılarak gerçekleştirilir.
* Android ve iOS uygulamaları için, veriler ve ayarlar (Kullanıcı Yapılandırması için anahtar-değer çiftleri), bir korumalı alanda ve yalnızca uygulama tarafından erişilebilen dahili depolamada bulunan depolamada önbelleğe alınır. Windows uygulaması için verilere yalnızca Kullanıcı (ve Sistem Yöneticisi) erişebilir.
* Coğrafi konum, Kullanıcı tarafından açıkça etkin veya devre dışı bırakıldı. Etkinleştirilirse, coğrafi konum verileri cihaza kaydedilmez ve Microsoft ile paylaşılmaz.
* Bildirimler Kullanıcı tarafından açıkça etkinleştirilir veya devre dışı bırakılır. Etkinleştirilirse, Android ve iOS bildirimler için coğrafi veri fazlalığını desteklemez.

Veri şifreleme, mobil cihaz ve uygulama yönetimi sağlayan bir yazılım hizmeti olan Microsoft Intune aracılığıyla dosya düzeyinde şifreleme uygulanarak geliştirilebilir. Power BI Mobil kullanılabildiği tüm üç platform Intune desteğine sahiptir. Intune etkinleştirilip yapılandırıldığında, mobil cihazlardaki veriler şifrelenir ve Power BI uygulamasının kendisi bir SD karta yüklenemez. [Microsoft Intune hakkında daha fazla bilgi edinin](https://www.microsoft.com/cloud-platform/microsoft-intune).

Windows uygulaması [windows Information Protection (WIP)](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)de destekler.

SSO uygulamak için, belirteç tabanlı kimlik doğrulamasıyla ilgili bazı güvenli depolama değerleri diğer Microsoft 1. taraf uygulamaları (örneğin, Microsoft Authenticator) için kullanılabilir ve Azure Active Directory kimlik doğrulama kitaplığı (ADAL) SDK 'Sı tarafından yönetilir.  

Power BI Mobil önbelleğe alınmış veriler, uygulama kaldırıldığında, Kullanıcı Power BI Mobil oturumunu kapattığında veya Kullanıcı oturum açamazsa (bir belirteç süre sonu olayından sonra veya parola değişikliğinden sonra) silinir. Veri önbelleği daha önce Power BI Mobil uygulamasından erişilen panoları ve raporları içerir.

Power BI Mobil, cihazdaki diğer uygulama klasörlerine veya dosyalarına erişemez.

İOS ve Android için Power BI uygulamaları, yüz KIMLIĞI, Touch ID veya iOS için bir geçiş kodu sağlamak ve Android için biyometrik veriler (Parmak Izi KIMLIĞI) gibi ek kimlik yapılandırarak verilerinizi korumanıza olanak sağlar. [Ek kimlik hakkında daha fazla bilgi edinin](../consumer/mobile/mobile-native-secure-access.md).

## <a name="authentication-to-the-power-bi-service"></a>Power BI hizmeti kimlik doğrulaması

Power BI hizmetinde kullanıcı kimlik doğrulaması bir dizi istek, yanıt ve kullanıcının tarayıcısı ile Power BI hizmeti veya Power BI tarafından kullanılan Azure hizmeti arasında gerçekleşen yeniden yönlendirmeden oluşur. Bu dizi, Power BI ' de Kullanıcı kimlik doğrulaması işlemini açıklar ve bu da [Azure Active Directory kimlik doğrulama kodu verme akışını](/azure/active-directory/develop/v2-oauth2-auth-code-flow)izler. Kuruluşun kullanıcı kimlik doğrulama modelleriyle ilgili seçenekler (oturum açma modelleri) hakkında daha fazla bilgi için bkz. [Microsoft 365 için oturum açma modeli seçme](https://blogs.office.com/2014/05/13/choosing-a-sign-in-model-for-office-365/).

### <a name="authentication-sequence"></a>Kimlik doğrulama dizisi

Power BI hizmeti için Kullanıcı kimlik doğrulama sırası, izleyen görüntüde gösterilen aşağıdaki adımlarda açıklandığı gibi oluşur.

1. Kullanıcı, adres çubuğuna Power BI adresini yazarak veya Power BI giriş sayfasından *oturum aç* ' ı seçerek bir tarayıcıdan Power BI hizmeti bağlantı başlatır ( https://powerbi.microsoft.com) . Bağlantı, TLS 1.2 ve HTTPS kullanarak kurulur ve daha sonra tarayıcı ile Power BI hizmeti arasındaki tüm bağlantılarda HTTPS kullanılır.

1. Azure Traffic Manager, Power BI dağıtıldığı en uygun (genellikle en yakın) veri merkezini belirlemek için kullanıcının DNS kaydını denetler ve kullanıcının gönderilmesi gereken WFE kümesinin IP adresiyle DNS 'ye yanıt verir.

1. WFE daha sonra kullanıcıyı Microsoft Online Services oturum açma sayfasına yönlendirir.

1. Kullanıcının kimliği doğrulandıktan sonra, oturum açma sayfası kullanıcıyı önceden belirlenen en yakın Power BI hizmeti WFE kümesine bir kimlik doğrulama kodu ile yönlendirir.

1. WFE kümesi, kimlik doğrulama kodunu kullanarak bir Azure AD güvenlik belirteci almak için Azure AD hizmeti ile kontrol eder. Azure AD, kullanıcının başarılı kimlik doğrulamasını geri döndürdüğünde ve bir Azure AD güvenlik belirteci döndürdüğünde, WFE kümesi, kiracılar ve Power BI arka uç kümesi konumlarının listesini tutan ve hangi Power BI arka uç hizmet kümesinin kullanıcının kiracısını içerdiğini belirleyen Power BI küresel hizmetini danışmanlar. WFE kümesi daha sonra, işlem için gereken oturum, erişim ve yönlendirme bilgileriyle kullanıcının tarayıcısına bir uygulama sayfası döndürür.

1. Artık, istemci tarayıcısı müşteri verileri gerektirdiğinde, istek, yetkilendirme üstbilgisindeki Azure AD erişim belirteci ile arka uç küme adresine gönderilir. Power BI arka uç kümesi, Azure AD erişim belirtecini okur ve isteğin kimliğinin geçerli olduğundan emin olmak için imzayı doğrular. [Azure AD erişim belirtecinin varsayılan yaşam süresi 1 saattir](/azure/active-directory/develop/active-directory-configurable-token-lifetimes#configurable-token-lifetime-properties-after-the-retirement)ve geçerli oturumu sürdürmek için kullanıcının tarayıcısı, erişim belirtecini süresi dolmadan önce yenilemek için düzenli istekleri yapar.

![Kimlik doğrulama dizisi](media/whitepaper-powerbi-security/powerbi-security-whitepaper_08.png)

## <a name="data-residency"></a>Veri yerleşimi

Belgelerde aksi belirtilmedikçe, Power BI müşteri verilerini bir [Azure AD kiracısı](/office365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings) Power BI Hizmetleri ilk kez kaydolduğunda atanan bir Azure Coğrafya 'da depolar. Bir Azure AD kiracısı, Kullanıcı ve uygulama kimliklerini, grupları ve bir kuruluşa ve güvenliğine ait diğer ilgili bilgileri barındırır. 

Kiracı veri depolaması için bir Azure Coğrafya ataması, Azure AD kiracı kurulumunun bir parçası olarak seçilen ülke veya bölgeyi, bir Power BI dağıtımının bulunduğu en uygun Azure coğrafya ile eşleyerek yapılır. Bu belirleme yapıldıktan sonra, kuruluşların çoklu coğrafi dağıtımlardan yararlandıkları durumlar dışında, tüm Power BI müşteri verileri bu seçili Azure Coğrafya ( *Ev coğrafi bölge* olarak da bilinir) alanında depolanır.

### <a name="multiple-geographies-multi-geo"></a>Birden çok coğrafi grafik (çok coğrafi)

Bazı kuruluşların küresel bir varlığı vardır ve birden çok Azure coğrafi konumunda Power BI Hizmetleri gerekebilir. Örneğin, bir işletme, merkezi olarak Birleşik Devletler, ancak Avustralya gibi diğer coğrafi alanlarda da iş oluşturabilir. Bu tür durumlarda, iş, yerel yönetmeliklere uymak için, belirli Power BI verilerinin uzak bölgedeki geri kalan konumda depolanmasını gerektirebilir. Power BI hizmeti bu özelliği *Çoklu coğrafi bölge* olarak adlandırılır.

Sorgu yürütme katmanı, sorgu önbellekleri ve çoklu coğrafi çalışma alanına atanan yapıt verileri barındırılır ve uzak kapasite Azure Coğrafya 'da kalır. Ancak, rapor yapısı gibi bazı yapıt meta verileri, kiracının ev coğrafi bölge öğesinde depolanabilecek şekilde kalabilir. Ayrıca, bazı veri aktarma ve işleme, çok coğrafi bir Premium kapasitede barındırılan çalışma alanları için bile kiracının ev coğrafi konumunda gerçekleşmeyebilir.

Birden çok Azure coğrafi bölge 'yi kapsayan Power BI dağıtımlarını oluşturma ve yönetme hakkında daha fazla bilgi için lütfen bkz. [Power BI Premium Için çoklu coğrafi desteği yapılandırma](../admin/service-admin-premium-multi-geo.md) .

### <a name="regions-and-datacenters"></a>Bölgeler ve veri merkezleri

Power BI Hizmetleri, [Microsoft Güven Merkezi](https://www.microsoft.com/TrustCenter/CloudServices/business-application-platform/data-location)' nde açıklandığı gibi belirli Azure coğrafi bölgelerde kullanılabilir. Verilerinizin depolandığı ve nasıl kullanıldığı hakkında daha fazla bilgi için lütfen [Microsoft Güven Merkezi](https://www.microsoft.com/TrustCenter/Transparency/default.aspx#_You_know_where)' ne bakın. Bekleyen müşteri verilerinin konumuyla ilgili taahhütler, [Microsoft Online Services koşullarının](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=31)veri işleme koşullarında belirtilmiştir.

Microsoft, sogeign varlıkları için de veri merkezleri sağlar. Ulusal bulutlar için Power BI hizmetinin kullanılabilirliği hakkında daha fazla bilgi için bkz. [Power BI ulusal bulutları](https://powerbi.microsoft.com/clouds/). 

## <a name="data-handling"></a>Veri İşleme

Bu bölümde, müşteri verilerini depolama, işleme ve aktarmaya yönelik veri işleme uygulamaları Power BI özetlenmektedir.

### <a name="data-at-rest"></a>Bekleme durumundaki veriler

Power BI iki birincil veri depolama kaynağı türünü kullanır:
* Azure Storage
* Azure SQL Veritabanları

Çoğu senaryoda, Azure depolama, yapıt meta verilerini kalıcı hale getirmek için Azure SQL veritabanları kullanıldığında Power BI yapıtların verilerini kalıcı hale getirmek için kullanılır. 

Power BI tarafından kalıcı yapılan tüm veriler, varsayılan olarak Microsoft tarafından yönetilen anahtarlar kullanılarak şifrelenir. Azure SQL veritabanlarında depolanan müşteri verileri [Azure sql saydam veri şifrelemesi (tde)](/azure/sql-database/transparent-data-encryption-azure-sql) teknolojisi kullanılarak tamamen şifrelenir. Azure Blob depolamada depolanan müşteri verileri, [Azure depolama şifrelemesi](/azure/storage/common/storage-service-encryption)kullanılarak şifrelenir.

İsteğe bağlı olarak kuruluşlar, bir veri kümesine aktarılan verileri şifrelemek için kendi anahtarlarını kullanmak üzere Power BI Premium kullanabilir. Bu yaklaşım genellikle kendi anahtarını getir (KAG) olarak tanımlanır. BYOK kullanımı, bir hizmet operatörü hatası olsa da, müşteri verilerinin sunulmamasından ve saydam hizmet tarafı şifrelemesi kullanılarak kolayca ulaşılamaz bir şeydir. Daha fazla bilgi için lütfen bkz. [Power BI için kendi şifreleme anahtarlarınızı getirme](../admin/service-encryption-byok.md) .

Power BI veri kümeleri, veri kaynağı verilerinin hizmette kalıcı olup olmadığını belirleyen çeşitli veri kaynağı bağlantı modlarına izin verir.

|Veri kümesi modu (tür)   |Power BI 'de kalıcı veriler |
|----------------------|---------------------------|
|İçeri Aktar                |Yes |
|Direct Query          |Hayır |
|Canlı Bağlantı          |Hayır |
|Bileşik             |Bir Içeri aktarma veri kaynağı içeriyorsa |
|Akış             |Kalıcı olacak şekilde yapılandırıldıysa |

Kullanılan veri kümesi modu ne olursa olsun, sorgu ve rapor yükleme performansını iyileştirmek için alınan verileri geçici olarak önbelleğe alabilir Power BI.

### <a name="data-in-processing"></a>İşlenen veriler

Veriler, etkileşimli bir senaryonun parçası olarak bir veya daha fazla kullanıcı tarafından etkin bir şekilde kullanıldığında veya yenileme gibi bir arka plan işlemi bu verilere dokunduğunda işleme içinde olur. Power BI, etkin olarak işlenen verileri bir veya daha fazla hizmet iş yükünün bellek alanına yükler. İş yükünün gerektirdiği işlevselliği kolaylaştırmak için bellekteki işlenen veriler şifrelenmez.

### <a name="data-in-transit"></a>Aktarım durumundaki veriler
Power BI tüm gelen HTTP trafiğinin TLS 1,2 veya üzeri kullanılarak şifrelenmesini gerektirir. Bu hizmeti TLS 1,1 veya daha düşük bir düzeyde kullanmaya çalışan istekler reddedilir.

## <a name="authentication-to-data-sources"></a>Veri kaynaklarında kimlik doğrulaması

Bir veri kaynağına bağlanırken, bir Kullanıcı, verilerin bir kopyasını Power BI içeri aktarmayı veya doğrudan veri kaynağına bağlanmasını tercih edebilir. 

İçeri aktarma durumunda, Kullanıcı kullanıcının oturum açmasını temel alan bir bağlantı kurar ve kimlik bilgileriyle verilere erişir. Veri kümesi Power BI hizmeti yayımlandıktan sonra, Power BI verileri içeri aktarmak için her zaman bu kullanıcının kimlik bilgilerini kullanır. Veriler içeri aktarıldıktan sonra raporlarda ve panolarda verilerin görüntülenmesi, temel alınan veri kaynağına erişemez. Power BI seçili veri kaynakları için çoklu oturum açma kimlik doğrulamasını destekler. Bağlantı, çoklu oturum açma kullanacak şekilde yapılandırıldıysa veri kaynağına bağlanmak için veri kümesi sahibinin kimlik bilgileri kullanılır.

Bir veri kaynağı önceden yapılandırılmış kimlik bilgileri kullanılarak doğrudan bağlandıysa, herhangi bir kullanıcı verileri görüntülediğinde veri kaynağına bağlanmak için önceden yapılandırılmış kimlik bilgileri kullanılır. Bir veri kaynağı doğrudan çoklu oturum açma kullanılarak bağlandıysa, Kullanıcı verileri görüntülediğinde veri kaynağına bağlanmak için geçerli kullanıcının kimlik bilgileri kullanılır. Çoklu oturum açma ile kullanıldığında, veri kaynağında satır düzeyi güvenlik (RLS) uygulanabilir. Bu, kullanıcıların yalnızca erişim ayrıcalıklarına sahip oldukları verileri görüntülemesine olanak tanır. Bağlantı, buluttaki veri kaynaklarına geldiğinde, çoklu oturum açma için Azure AD kimlik doğrulaması kullanılır; Şirket içi veri kaynakları, Kerberos, Security Assertion Markup Language (SAML) ve Azure AD için desteklenir.

Veri kaynağı Azure Analysis Services veya şirket içi Analysis Services ve RLS yapılandırılmışsa, Power BI hizmeti bu satır düzeyi güvenliği uygular ve temel alınan verilere erişmek için yeterli kimlik bilgilerine sahip olmayan kullanıcılar (bir panoda, raporda veya başka bir veri yapısında kullanılan bir sorgu olabilir) için yeterli ayrıcalıklara sahip olmadıkları verileri görmez.

## <a name="premium-features"></a>Premium özellikler

### <a name="dataflows-architecture"></a>Veri akışları mimarisi

Veri akışları, kullanıcılara polimorphous veri kaynaklarından veri ayıklayabileceği arka uç veri işleme işlemlerini yapılandırma, verilere karşı dönüştürme mantığını yürütme ve sonra çeşitli raporlama sunum teknolojileri genelinde kullanılmak üzere bir hedef modelde bu işlemi kullanma olanağı sunar. Bir çalışma alanında üye, katkıda bulunan veya yönetici rolü olan herhangi bir Kullanıcı, bir veri akışı oluşturabilir. Görüntüleyici rolündeki kullanıcılar veri akışı tarafından işlenen verileri görüntüleyebilir, ancak kendi kompozisyonunun üzerinde değişiklik yapamaz. Bir veri akışı alındıktan sonra, çalışma alanının herhangi bir üyesi, katılımcısı veya Yöneticisi yenilemeler zamanlayabilir, bunun yanı sıra veri akışını da onun sahipliğini alarak görüntüleyebilir ve düzenleyebilirsiniz.

Yapılandırılan her veri kaynağı, bu veri kaynağına erişmek için bir istemci teknolojisine bağlanır. Bunlara erişmek için gereken kimlik bilgilerinin yapısı, veri kaynağının gerekli uygulama ayrıntılarını eşleştirmek üzere biçimlendirilir. Dönüştürme mantığı Power Query Hizmetleri tarafından, veriler uçuş sırasında uygulanır. Premium veri akışları için Power Query Hizmetleri arka uç düğümlerinde yürütülür. Veriler doğrudan bulut kaynaklarından ya da şirket içinde yüklü bir ağ geçidiyle çekkalabilir. Aktarım, bir bulut kaynağından hizmete veya ağ geçidine doğrudan çekildiğinde, varsa, istemci teknolojisine özgü koruma yöntemini kullanır. Veriler ağ geçidinden bulut hizmetine aktarıldığında şifrelenir. Yukarıdaki [verileri işleme bölümündeki verilere](#data-in-processing) bakın.

Müşteri tarafından belirtilen veri kaynakları erişim için kimlik bilgileri gerektirdiğinde, veri akışının sahibi/Oluşturucusu, yazma sırasında bu verileri sağlar. Bunlar standart ürün genelinde kimlik bilgisi depolaması kullanılarak depolanır. Yukarıdaki [veri kaynaklarına kimlik doğrulama](#authentication-to-data-sources) bölümüne bakın. Kullanıcıların veri kalıcılığını ve erişimini iyileştirmek için yapılandırabileceği çeşitli yaklaşımlar vardır. Varsayılan olarak, veriler Power BI sahip ve korumalı depolama hesabına yerleştirilir. Depolama şifrelemesi, verileri bekleyen durumdayken korumak için BLOB depolama kapsayıcılarında etkindir. Aşağıdaki [rest bölümündeki veriler](#data-at-rest) bölümüne bakın. Ancak kullanıcılar kendi Azure abonelikleri ile ilişkili kendi depolama hesabını yapılandırabilir. Bunu yaparken, bir Power BI hizmeti sorumlusu, bu depolama hesabına erişim verildiğinde, verileri yenileme sırasında buraya yazabilir. Bu durumda, yapılandırılmış ADLS depolama hesabında şifrelemeyi yapılandırmadan depolama kaynağı sahibi sorumludur. Veriler her zaman şifreleme kullanılarak blob depolamaya iletilir.

Depolama hesaplarına erişirken performans bazı veriler için uygun olmayabilir. Ayrıca, kullanıcıların performansı artırmak için Power BI barındırılan bir işlem altyapısı kullanma seçeneği de vardır. Bu durumda, veriler, arka uç Power BI sistemine erişim yoluyla DirectQuery için kullanılabilen bir SQL veritabanında Redundantly. Veriler her zaman dosya sisteminde şifrelenir. Kullanıcı, SQL veritabanında depolanan verileri şifrelemek için bir anahtar sağlıyorsa, bu anahtar, bunu bir şekilde şifrelemek için kullanılacaktır.

DirectQuery kullanarak sorgulama yaparken, API 'ye erişmek için şifreli aktarım protokolü HTTPS kullanılır. DirectQuery 'nin tüm ikincil veya dolaylı kullanımı, daha önce açıklanan erişim denetimleri tarafından denetlenir. Veri akışları her zaman bir çalışma alanına bağlandığından, verilere erişim her zaman o çalışma alanındaki Kullanıcı rolü tarafından alınır. Bir kullanıcının, verileri herhangi bir şekilde sorgulayabilmesi için en azından okuma erişimi olmalıdır.

Veri akışındaki verilere erişmek için Power BI Desktop kullanıldığında, kullanıcının verileri görüntülemek için yeterli haklara sahip olup olmadığını öğrenmek için önce Azure AD 'yi kullanarak kullanıcının kimliğini doğrulaması gerekir. Bu durumda, bir SaS anahtarı alınır ve şifreli aktarım protokolü HTTPS kullanılarak doğrudan depolamaya erişim için kullanılır.

Ardışık düzen genelinde verilerin işlenmesi Office 365 denetim olaylarını yayar. Bu olaylardan bazıları, güvenlik ve gizlilikle ilgili işlemleri yakalar.

### <a name="paginated-reports"></a>Sayfalandırılmış raporlar

Sayfalandırılmış raporlar, yazdırılmak veya paylaşılmak üzere tasarlanmıştır. Sayfalandırılmış olarak adlandırılmalarının nedeni, bir sayfaya düzgün yerleştirilecek şekilde biçimlendirilmiş olmalarıdır. Tablo birden fazla sayfaya yayılsa bile tüm verileri bir tabloda gösterirler. Rapor sayfası düzenini tam olarak denetleyebilme olanağı sayesinde her bir ayrıntıyı kusursuz hale getirebilirsiniz.

Sayfalandırılmış raporlar, Microsoft Visual Basic .NET içinde yazılmış zengin ve güçlü ifadeleri destekler. İfadeler Power BI Report Builder sayfalandırılmış raporlarında verileri almak, hesaplamak, görüntülemek, gruplandırmak, sıralamak, filtrelemek parametreleştirmek ve biçimlendirmek için yaygın olanak kullanılır.

İfadeler, .NET Framework 'ün geniş kapsamlı özelliklerine erişimi olan raporun yazarı tarafından oluşturulur. Sayfalandırılmış raporların işlenmesi ve yürütülmesi bir korumalı alan içinde gerçekleştirilir.

Sayfalandırılmış rapor tanımları (. rdl) Power BI depolanır ve yukarıdaki [Power BI hizmeti](#authentication-to-the-power-bi-service) bölümünde açıklanan şekilde kimlik doğrulaması yapmak ve yetkilendirmek için bir Kullanıcı ihtiyacı olan bir sayfalandırılmış rapor yayımlamak ve/veya işlemek için kullanılır.

Kimlik doğrulaması sırasında elde edilen Azure AD belirteci, doğrudan tarayıcıdan Power BI Premium kümesine iletişim kurmak için kullanılır.

Premium Gen1 için, kiracının kapasitelerinin her biri için tek bir korumalı alan vardır ve kapasiteye atanan çalışma alanları tarafından paylaşılır.

![Sayfalandırılmış raporlar Gen 1](media/whitepaper-powerbi-security/powerbi-security-whitepaper-paginated-reports-gen1.png)

Premium Gen2 (önizlemede) için, bir rapor oluşturmların her biri için bireysel ve özel bir kısa ömürlü Sandbox oluşturulur ve kullanıcılar arasında daha yüksek bir yalıtım düzeyi sağlar.

![Sayfalandırılmış raporlar Gen 2](media/whitepaper-powerbi-security/powerbi-security-whitepaper-paginated-reports-gen2.png)

Sayfalandırılmış bir rapor, rapor işlemenin bir parçası olarak geniş bir veri kaynağı kümesine erişebilir. Korumalı alan herhangi bir veri kaynağı ile doğrudan iletişim kurmaz, bunun yerine veri istemek için güvenilir işlemle iletişim kurar ve ardından Güvenilen işlem, gerekli kimlik bilgilerini bağlantıya ekler. Bu şekilde, korumalı alan herhangi bir kimlik bilgisi veya gizli dizi için hiçbir şekilde erişemez. 

Bing Haritalar veya Azure Işlevlerine yapılan çağrılar gibi özellikleri desteklemek için, korumalı alanının internet erişimi vardır.

### <a name="power-bi-embedded-analytics"></a>Katıştırılmış analiz Power BI

Bağımsız yazılım satıcıları (ISV 'Ler) ve çözüm sağlayıcılarının, Web uygulamalarına ve portallarına Power BI yapıt ekleme ve müşterilerinize ekleme ve müşterileriniz [için](../developer/embedded/embed-sample-for-your-organization.md) [ekleme](../developer/embedded/embed-sample-for-customers.md)gibi iki ana modu vardır. Yapıt, uygulama veya portalda bir iframe içine gömülüdür. Dış Web uygulamasından veya portalından veri okuma veya yazma izni verilmez ve iframe ile iletişim, ileti gönderme kullanarak Power BI Istemci SDK 'Sı kullanılarak yapılır.

[Kuruluşunuz için bir ekleme](../developer/embedded/embed-sample-for-your-organization.md) SENARYOSUNDA Azure AD kullanıcıları, kuruluşları tarafından özelleştirilmiş portallardan kendi Power BI içeriğine erişir. Bu kağıda (satır düzeyi güvenlik (RLS) gibi) açıklanan tüm Power BI ilkeleri ve özellikleri, [Power BI portalı](https://app.powerbi.com/) veya özelleştirilmiş portallar aracılığıyla Power BI erişip erişemeyeceğini bağımsız olarak tüm kullanıcılara otomatik olarak uygulanır.

[Müşteriler için bir ekleme](../developer/embedded/embed-sample-for-customers.md) senaryosunda, ISV 'ler genellikle Power BI kiracılar ve Power BI yapıtlarına (panolar, raporlar, veri kümeleri vb.) sahiptir. Bu, son kullanıcıların kimliğini doğrulamak ve hangi yapıtların ve hangi erişim düzeyinin o son kullanıcıya uygun olduğuna karar vermek için bir ISV arka uç hizmetinin sorumluluğundadır. ISV ilke kararları, Power BI tarafından oluşturulan ve ISV 'nin iş mantığına göre son kullanıcılara daha fazla dağıtım için ISV arka ucuna geçirilen bir [ekleme belirtecinde](/rest/api/power-bi/embedtoken) şifrelenir. Tarayıcı veya diğer istemci uygulamaları kullanan son kullanıcılar ekleme belirteçlerinin şifresini çözemez veya değiştiremezler. [Power BI Istemci API 'leri](/javascript/api/overview/powerbi/) gibi Istemci tarafı SDK 'ları, şifreli ekleme belirtecini bir *Yetkilendirme: embedtoken* üstbilgisi olarak Power BI isteklere otomatik olarak ekler. Power BI, bu üst bilgiyi temel alarak tüm ilkeleri (Access veya RLS), oluşturma sırasında ISV tarafından tam olarak belirtildiği gibi zorlar.

Ekleme ve Otomasyonu etkinleştirmek ve yukarıda açıklanan ekleme belirteçlerini oluşturmak için, Power BI zengin bir [REST API](/rest/api/power-bi/embedtoken)kümesi sunar. Bu Power BI REST API 'Leri hem Kullanıcı [temsilcisi](/azure/active-directory/develop/v2-permissions-and-consent) hem de [HIZMET sorumlusu](../admin/service-premium-service-principal.md) Azure AD yöntemlerini kimlik doğrulama ve yetkilendirme için destekler.

Power BI ekli analiz ve REST API 'Leri, bu makalede açıklanan tüm Power BI ağ yalıtımı yeteneklerini destekler: Örneğin, [hizmet etiketleri](#service-tags) ve [özel bağlantılar](#private-link-integration).

### <a name="ai-features"></a>AI özellikleri

Power BI Şu anda üründe bulunan çok sayıda AI özelliği vardır: AI görselleri ve AI zenginleri. Görsel düzeyi AI özellikleri, anahtar etkili şifreleme, ayrıştırma ağacı, akıllı anlatım, şifreleme, anomali algılama, R-görsel, Python-görsel, kümeleme, tahmin, Q&A, Quick-Insights vb. gibi özellikleri içerir. AI zenginleştirme özellikleri, oto ml, AzureML, Biliveservices, R/Python dönüştürmeleri vb. gibi özellikleri içerir. 

Yukarıda bahsedilen özelliklerin çoğu, paylaşılan ve Premium çalışma alanlarında bugün desteklenir. Ancak,, IP kısıtlamaları nedeniyle, oto ml ve Biliveservices yalnızca Premium çalışma alanlarında desteklenir. Bugün, Power BI ' de, oto ml tümleştirmesiyle, bir kullanıcı özel bir ML modeli oluşturup eğitebilir (tahmin, sınıflandırma, regresyon vb.) ve verileri Premium bir çalışma alanında tanımlanan bir veri akışına yüklerken tahmine dayalı olarak uygulayabilir. Ayrıca, Power BI kullanıcılar bir Premium çalışma alanında tanımlanan bir veri akışına/veri kümesine yüklemeden önce verileri dönüştürmek için TextAnalytics ve ımageetiketleme gibi çeşitli Bilivev API 'Leri uygulayabilir. 

Premium AI zenginleştirme özellikleri, bir Power BI veri kümesi veya veri akışı tarafından kullanılan veri tümleştirme işlem hatlarında Power BI kullanıcıları tarafından kullanılabilecek, durum bilgisi olmayan bir AI işlevleri/dönüştürmeleri koleksiyonu olarak en iyi şekilde görüntülenebilir. Bu işlevlere ayrıca Power BI hizmetindeki geçerli veri akışı/veri kümesi yazma ortamlarından de erişilebilir ve Power BI Desktop. Bu AI işlevleri/dönüştürmeleri her zaman bir Premium çalışma alanında/kapasitede çalıştırılır. Bu işlevler, Power BI AI işlevini kullanan Power BI Kullanıcı için Azure AD belirteci gerektiren bir veri kaynağı olarak ortaya çıkmış. Bu AI veri kaynakları, kendi verilerinin hiçbirini sunmadığından ve yalnızca bu işlevleri/dönüşümleri sağladığından özeldir. Yürütme sırasında, bu özellikler müşterinin verilerini aktarmak için diğer hizmetlere giden hiçbir çağrı yapamaz. İletişim düzenlerini ve bunlarla ilgili güvenlikle ilgili ilgili ayrıntıları anlamak için Premium senaryolara tek tek bakmamıza izin verin. 

Eğitim ve bir oto ml modeli uygulama Power BI, Azure oto ml SDK 'sını kullanır ve müşterinin Power BI kapasitesinde tüm eğitimleri çalıştırır. Eğitim yinelemeleri sırasında, Power BI geçerli yineleme için uygun bir model ve Hyper-parametreleri seçmek üzere bir deneme AzureML hizmeti çağırır. Bu giden çağrıda, önceki yinelemeden yalnızca ilgili deneme meta verileri (örn. doğruluk, ml algoritması, algoritma parametreleri vb.) gönderilir. Otomatik ml eğitimi, daha sonra veri akışına kaydedilen bir ONNX modeli ve eğitim raporu verileri oluşturur. Daha sonra, Power BI kullanıcılar daha sonra eğitilen ML modelini, ML modelini zamanlanan bir şekilde işlemek için bir dönüşüm olarak uygulayabilir. TextAnalytics ve ımageetiketleme API 'Leri için, Power BI Biliveservices hizmet API 'Lerini doğrudan çağırmaz, bunun yerine API 'Leri Power BI Premium kapasitede çalıştırmak için bir iç SDK kullanır. Bugün bu API 'Ler Power BI veri akışları ve veri kümelerinde desteklenir. Power BI Desktop bir veri kümesi yazarken, kullanıcılar bu işlevselliğe yalnızca bir Premium Power BI çalışma alanına erişim varsa erişebilirler. Bu nedenle, müşterilerin Azure AD kimlik bilgilerini sağlaması istenir. 

## <a name="network-isolation"></a>Ağ yalıtımı

Bu bölümde Power BI gelişmiş güvenlik özellikleri özetlenmektedir. Bazı özelliklerden belirli lisans gereksinimleri vardır. Ayrıntılar için aşağıdaki bölümlere bakın.

### <a name="service-tags"></a>Hizmet etiketleri

Hizmet etiketi, belirli bir Azure hizmetinden bir IP adresi önekleri grubunu temsil eder. Ağ güvenlik kuralları için sık sık güncelleştirmelerin karmaşıklığını en aza indirmenize yardımcı olur. Müşteriler, [ağ güvenlik gruplarında](/azure/virtual-network/security-overview#security-rules) veya [Azure Güvenlik duvarında](/azure/firewall/service-tags)ağ erişim denetimleri tanımlamak için hizmet etiketlerini kullanabilir. Müşteriler, güvenlik kuralları oluştururken belirli IP adreslerinin yerine hizmet etiketlerini kullanabilir. Bir kuralın uygun kaynak veya hedef (API 'Ler için) alanında hizmet etiketi adı (ör., PowerBI) belirterek, müşteriler ilgili hizmet için trafiğe izin verebilir veya bu trafiği reddedebilir. Microsoft, hizmet etiketi ile çevrelenmiş adres öneklerini yönetir ve adres değişikliği olarak hizmet etiketini otomatik olarak güncelleştirir.

### <a name="private-link-integration"></a>Özel bağlantı tümleştirmesi

Azure ağı, Power BI Azure ağ özel uç noktaları aracılığıyla güvenli erişim sağlamasına olanak sağlayan Azure özel bağlantı özelliğini sağlar. Azure özel bağlantısı ve özel uç noktalar sayesinde veri trafiği, Microsoft 'un omurga ağ altyapısını kullanarak özel olarak gönderilir ve bu nedenle veriler Internet 'e çapraz geçiş yapmaz.

Özel bağlantı, Power BI kullanıcıların Power BI hizmeti kaynaklara gittiğinden Microsoft özel ağ omurgasını kullanmasını sağlar.

Power BI ile özel bağlantı kullanmak aşağıdaki avantajları sağlar:
* Özel bağlantı, trafiğin Azure 'un bulut tabanlı kaynaklar için özel bir uç noktaya akışını sağlar.
* Şirket içi erişim gibi Azure tabanlı olmayan altyapıdan ağ trafiği yalıtımına, müşterilerin ExpressRoute veya bir sanal özel ağ (VPN) yapılandırması gerekir.

Daha fazla bilgi için bkz. [Power BI erişmek Için özel bağlantılar](../admin/service-security-private-links.md) .

### <a name="vnet-connectivity-preview---coming-soon"></a>VNet bağlantısı (yakında önizleme geliyor)

Özel bağlantı tümleştirme özelliği Power BI için güvenli gelen bağlantılar sağlarken, VNet bağlantısı özelliği bir sanal ağ içindeki veri kaynaklarına Power BI giden bağlantının güvenliğini sağlar. 

VNet ağ geçitleri (Microsoft tarafından yönetilen), VNet ile ilişkili veri kaynaklarına bağlanmak için şirket içi veri ağ geçitlerini yükleme ve izleme yükünü ortadan kaldıracak. Ancak, şirket içi veri ağ geçidinde olduğu gibi, güvenlik ve veri kaynaklarını yönetme sürecini yine de takip eder.

Aşağıda, VNet ağ geçitleri kullanılarak VNet içindeki bir veri kaynağına bağlı bir Power BI raporuyla etkileşim kurarken ne olacağı hakkında genel bir bakış verilmiştir:

1. Power BI bulut hizmeti (veya desteklenen diğer bulut hizmetlerinden biri) bir sorgu üzerinden çıkarılan ve sorguyu, veri kaynağı ayrıntılarını ve kimlik bilgilerini güç platformu VNet hizmeti 'ne (PP VNet) gönderir.

1. Sonra PP VNet hizmeti, VNet ağ geçidini çalıştıran bir kapsayıcıyı alt ağa güvenli bir şekilde çıkarır. Bu kapsayıcı, artık bu alt ağ içinden erişilebilen veri hizmetlerine bağlanabilir.

1. Sonra PP VNet hizmeti sorguyu, veri kaynağı ayrıntılarını ve kimlik bilgilerini VNet Gateway 'e gönderir. 

1. VNet Gateway, sorguyu alır ve bu kimlik bilgileriyle veri kaynaklarına bağlanır.

1. Sorgu daha sonra yürütülmek üzere veri kaynağına gönderilir.

1. Yürütmeden sonra sonuçlar VNet ağ geçidine gönderilir ve PP VNet hizmeti, verileri kapsayıcıdan Power BI bulut hizmetine güvenli bir şekilde gönderir.

Bu özellik kısa bir süre önce genel önizlemede kullanıma sunulacaktır.

### <a name="service-principals"></a>Hizmet sorumluları

Power BI, hizmet sorumlularının kullanımını destekler. Bir Key Vault Power BI şifrelemek veya bunlara erişmek için kullanılan hizmet sorumlusu kimlik bilgilerini depolayın, kasaya uygun erişim ilkeleri atayın ve erişim izinlerini düzenli olarak gözden geçirin.

Daha fazla bilgi için bkz. [Premium çalışma alanını ve veri kümesi görevlerini hizmet sorumluları Ile otomatikleştirme](../admin/service-premium-service-principal.md) .

## <a name="data-loss-prevention-dlp"></a>Veri kaybı önleme (DLP)

### <a name="microsoft-365-sensitivity-labels"></a>Duyarlılık etiketleri Microsoft 365

Power BI, kuruluşların Office Suite genelinde DLP ilke yönetimi, denetim ve uyumluluk için tek ve tümleşik bir çözüme sahip olmasını sağlayan Microsoft Information Protection (MıP) duyarlılık etiketleriyle derin bir tümleştirme içerir.

Duyarlılık etiketleri Power BI ' de etkinleştirildiğinde:
* Hem Power BI hizmeti (GA) hem de Power BI Desktop (Önizleme) olan hassas veriler, Office 'te ve Azure purview 'da kullanılan tanıdık Microsoft Information Protection duyarlılık etiketleri kullanılarak sınıflandırılabilir ve etiketlenebilir. 
* Power BI içerik Excel, PowerPoint, PDF veya *. pbix* dosyalarına aktarıldığında bile, verilerin Power BI bırakılsa bile korunmasını sağlamaya yardımcı olmak için idare ilkeleri zorlanabilir.
* *. pbix* dosyaları, masaüstündeki *. pbix* dosyasına bir MIP etiketi uygulandığında, bu dosyayı yalnızca yetkili KULLANıCıLARıN düzenleyebilmesini sağlayarak MIP etiket ilkelerine göre şifrelenebilir.
* *. Pbix* dosyalarını Excel, Word ve PowerPoint dosyaları ile yapıldığı gibi sınıflandırmak ve korumak kolaydır. Yalnızca iki tıklama ile, bir dosya duyarlık düzeyine göre etiketlenebilir ve daha da fazla iş bakımından gizli veriler içeriyorsa şifrelenir.
* Excel çalışma kitapları, Power BI (Önizleme) ' ye bağlandıklarında duyarlık etiketlerini otomatik olarak devralır, bu, uçtan uca sınıflandırmanın bakımını yapma ve Power BI veri kümesi Excel 'de analiz edildiğinde koruma uygulama olanağı sağlar.
* Power BI raporlarında ve panolarda uygulanan duyarlılık etiketleri, Power BI iOS ve Android mobil uygulamalarında görünür olacaktır.
* Power BI bir rapor takımlara, SharePoint 'e veya güvenli bir Web sitesine (Önizleme) katıştırıldığında duyarlılık etiketleri kalır. Bu, kuruluşların Power BI içerik eklerken dışarı aktarma sırasında sınıflandırma ve koruma korumasına yardımcı olur.
* Power BI hizmeti yeni içerik oluşturma üzerine etiket devralma, Power BI hizmeti bir veri kümesine uygulanan etiketin, veri kümesinin üstünde oluşturulan yeni içeriğe uygulanmasını sağlar. 
* [Power BI yönetici tarama API 'leri](/rest/api/power-bi/admin/workspaceinfo_getscanresult) , Power BI hizmeti etiketlemeyi izlemek ve yönetim raporları oluşturmak için Power BI ve INFOSEC yöneticilerinin bir Power BI yapıt duyarlılık etiketini ayıklayabilir. 
* Power BI, yalnızca yetkili kullanıcıların, Power BI hizmeti koruma ayarlarına sahip etiketleri değiştireveya kaldırabilecek şekilde emin olur. 
* Çok yakında
    * Merkezi ekiplerin Power BI hizmeti içeriği programlı olarak etiketlemesini sağlamak için MıP etiketlerini uygulamaya yönelik yönetici API 'Leri Power BI.  
    * Yöneticiler, Power BI hizmeti (Önizleme) içinde bir zorunlu etiket ilkesiyle yeni veya düzenlenmiş içerikte etiket uygulanmasını zorlayabilir.
    * Power BI hizmeti içinde otomatik aşağı akış yapıt etiketleme. Veri kümesindeki bir etiket uygulandığında veya değiştirildiğinde, etiket otomatik olarak bu yapıya bağlı tüm aşağı akış içeriğine uygulanır.

Daha fazla bilgi için [Power BI Microsoft Information Protection duyarlılık etiketi belgelerine](../admin/service-security-sensitivity-label-overview.md) bakın.

### <a name="microsoft-cloud-app-security-mcas-for-power-bi"></a>Power BI için Microsoft Cloud App Security (MCAS)

Microsoft Cloud App Security, dünyanın önde gelen bulut erişimi güvenlik aracılarından biridir. Bu, bulut erişimi güvenlik Aracısı (CASB) pazarında Gartner 'in sihirli çeyreğine lider olarak adlandırılır. Cloud App Security, bulut uygulamalarının kullanımını güvence altına almak için kullanılır. Kuruluşların, yönetilmeyen cihazlardan Kullanıcı erişimi gibi gerçek zamanlı, riskli Power BI oturumlarını izlemelerine ve denetlemesine olanak sağlar. Güvenlik yöneticileri, raporları hassas bilgilerle indirme gibi kullanıcı eylemlerini denetlemek için ilkeler tanımlayabilir.

Cloud App Security, kuruluşlar aşağıdaki DLP yeteneklerini elde edebilir: 
* Power BI riskli kullanıcı oturumlarını zorlamak için gerçek zamanlı denetimleri ayarlayın. Örneğin, bir Kullanıcı, ülkelerin dışından Power BI bağlanırsa, oturum Cloud App Security gerçek zamanlı denetimler tarafından izlenebilir ve "çok gizli" duyarlılık etiketiyle etiketlenmiş verilerin indirilmesi gibi riskli eylemler hemen engellenebilir.
* Cloud App Security etkinlik günlüğü ile Kullanıcı etkinliklerini Power BI araştırın. Cloud App Security etkinlik günlüğü, Office 365 denetim günlüğünde yakalanan Power BI etkinliği içerir. Bu, tüm Kullanıcı ve yönetici etkinlikleriyle ilgili bilgiler içerir, Ayrıca, uygulama, değiştirme ve etiketi kaldırma gibi ilgili etkinliklere yönelik duyarlılık etiketi bilgileri içerir. Yöneticiler Cloud App Security gelişmiş filtrelerinden ve etkili sorun araştırmasına yönelik hızlı eylemlerle faydalanabilir. 
* Power BI şüpheli Kullanıcı etkinliğine uyarı vermek için özel ilkeler oluşturun. Cloud App Security etkinlik ilkesi özelliği, norm göre farklılık gösteren kullanıcı davranışlarını tespit etmenize ve hatta çok tehlikeli görünüyorsa otomatik olarak üzerinde işlem yapması için kendi özel kurallarınızı tanımlamak üzere yararlanılabilir olabilir.
* Cloud App Security yerleşik anomali algılama ile çalışın. Cloud App Security anomali algılama ilkeleri, eski kullanıcı davranış analizi ve makine öğrenimi sağlar, böylece, bulut ortamınızda Gelişmiş tehdit algılamayı çalıştırmak üzere bilinemeyebilir 'ten hazır olursunuz. Anomali algılama ilkesi şüpheli bir davranışı belirlediğinde, bir güvenlik uyarısını tetikler. 
* Cloud App Security portalında yönetici rolü Power BI. Cloud App Security, Power BI yöneticilere yalnızca portalda Power BI ilgili verilere (uyarılar, risk altındaki kullanıcılar, etkinlik günlükleri ve diğer Power BI ilgili bilgiler) erişmesi için gereken izinleri vermek için kullanılabilecek bir uygulamaya özgü yönetici rolü sağlar.

Daha fazla bilgi için bkz. [Power BI Microsoft Cloud App Security denetimlerini kullanma](../admin/service-security-using-microsoft-cloud-app-security-controls.md) .

## <a name="preview-security-features"></a>Önizleme güvenlik özellikleri

Bu konuda Mart 2021 ' den itibaren yayınlanacak özellikler listelenmiştir. Bu konuda henüz yayımlanmayan Özellikler listelenmediğinden, **teslim zaman çizelgeleri değişebilir ve tasarlanan Işlevsellik mart 2021 ' den daha sonra yayımlanmayabilir veya hiç yayımlanmayabilir**. Önizlemeler hakkında daha fazla bilgi için lütfen [çevrimiçi hizmet koşulları](https://www.microsoft.com/licensing/product-licensing/products)' nı gözden geçirin.

### <a name="bring-your-own-log-analytics-byola"></a>Kendi Log Analytics getirme (BYOLA)

Kendi Log Analytics getirin Power BI ve Azure Log Analytics arasında tümleştirmeyi mümkün hale getirir. Bu tümleştirme Azure Log Analytics ' gelişmiş analitik altyapısı, etkileşimli sorgu dili ve yerleşik makine öğrenimi yapılarını içerir.

## <a name="power-bi-security-questions-and-answers"></a>Power BI güvenlik soruları ve yanıtları

Aşağıda, Power BI için yaygın olarak kullanılan sorular ve yanıtlar verilmiştir. Bunlar, bu kağıt güncelleştirildiği sırada yeni soruları ve yanıtları hızlı bir şekilde bulma yeteneğinizi kolaylaştırmak için bu teknik incelemeye eklendikleri zaman temel alınarak düzenlenmiştir. En yeni sorular bu listenin sonuna eklenmiştir.

**Kullanıcılar Power BI'ı kullanırken nasıl bağlantı kurabilir ve veri kaynaklarına erişebilir?**

* Power BI, her kullanıcı için veri kaynaklarına yönelik kimlik bilgilerini bulut kimlik bilgileri veya kişisel bir ağ geçidi üzerinden bağlantı için yönetir. Şirket içi veri ağ geçidi tarafından yönetilen veri kaynakları kuruluş genelinde paylaşılabilir ve bu veri kaynaklarının izinleri ağ geçidi Yöneticisi tarafından yönetilebilir. Bir veri kümesini yapılandırırken, kullanıcının kişisel mağazalarından kimlik bilgileri seçmesini veya paylaşılan bir kimlik bilgisi kullanmak için şirket içi veri ağ geçidini kullanmasına izin verilir.

    İçeri aktarma durumunda, Kullanıcı kullanıcının oturum açmasını temel alan bir bağlantı kurar ve kimlik bilgileriyle verilere erişir. Veri kümesi Power BI hizmeti yayımlandığında, Power BI verileri içeri aktarmak için her zaman bu kullanıcının kimlik bilgilerini kullanır. Veriler içeri aktarıldıktan sonra raporlarda ve panoda verilerin görüntülenmesi, temel alınan veri kaynağına erişemez. Power BI seçili veri kaynakları için çoklu oturum açma kimlik doğrulamasını destekler. Bağlantı çoklu oturum açma kullanacak şekilde yapılandırıldıysa, veri kaynağıyla bağlantı kurmak için veri kümesi sahibinin kimlik bilgileri kullanılır.

    DirectQuery ile bağlantılı raporlar için, veri kaynağı önceden yapılandırılmış bir kimlik bilgisi kullanılarak doğrudan bağlanır, herhangi bir kullanıcı verileri görüntülediğinde veri kaynağına bağlanmak için önceden yapılandırılmış kimlik bilgileri kullanılır. Bir veri kaynağı doğrudan çoklu oturum açma kullanılarak bağlandıysa, Kullanıcı verileri görüntülediğinde veri kaynağına bağlanmak için geçerli kullanıcının kimlik bilgileri kullanılır. Çoklu oturum açma ile kullanılırken, veri kaynağında satır düzeyi güvenlik (RLS) uygulanabilir ve bu, kullanıcıların erişim ayrıcalıklarına sahip oldukları verileri görüntülemesine olanak tanır. Bağlantı, buluttaki veri kaynaklarına geldiğinde, çoklu oturum açma için Azure AD kimlik doğrulaması kullanılır; Şirket içi veri kaynakları için Kerberos, SAML ve Azure AD desteklenir.  

    Kerberos ile bağlanırken, kullanıcının UPN 'si ağ geçidine geçirilir ve Kerberos kısıtlanmış temsili kullanılarak kullanıcı kimliğine bürünerek ilgili veri kaynaklarına bağlanır. SAML, SAP HANA veri kaynağı için ağ geçidinde de desteklenir. Daha fazla bilgi için, [ağ geçitleri için çoklu oturum açma konusuna genel bakış](../connect-data/service-gateway-sso-overview.md)sunulmaktadır.

    Veri kaynağı Azure Analysis Services veya şirket içi Analysis Services ve satır düzeyi güvenlik (RLS) yapılandırılmışsa Power BI hizmeti, bu satır düzeyi güvenliği uygular ve temel alınan verilere erişmek için yeterli kimlik bilgilerine sahip olmayan kullanıcılar (bir panoda, raporda veya başka bir veri yapısında kullanılan bir sorgu olabilir), kullanıcının yeterli ayrıcalıklara sahip olmadığı verileri görmez.

    [Power BI Ile satır düzeyi güvenlik](../admin/service-admin-rls.md) , belirli kullanıcılar için veri erişimini kısıtlamak üzere kullanılabilir. Filtreler, satır düzeyinde veri erişimini kısıtlar ve rol içinde filtreler tanımlayabilirsiniz.  

**Veriler Power BI'a nasıl aktarılır?**

* Power BI tarafından istenen ve iletilen tüm veriler, HTTPS kullanılarak (müşterinin seçtiği veri kaynağı HTTPS 'yi desteklemediğinde), veri kaynağından Power BI hizmeti bağlanacak şekilde şifrelenir. Veri sağlayıcısıyla güvenli bir bağlantı kurulur ve ancak bu bağlantı kurulduktan sonra veriler ağdan geçer.

**Power BI rapor, pano veya model verilerini nasıl önbelleğe alır ve bu güvenli bir yöntem midir?**

* Bir veri kaynağına erişildiğinde Power BI hizmeti, bu belgede daha önce yer aldığı [veri kaynaklarında kimlik doğrulaması](#authentication-to-data-sources) bölümünde özetlenen süreci izler.

**İstemciler web sayfası verilerini yerel olarak önbelleğe alır mı?**

* Tarayıcı istemcileri Power BI'a eriştiğinde, Power BI web sunucuları *Cache-Control* yönergesini *no-store* olarak ayarlar. Bu *no-store* yönergesi tarayıcılara kullanıcı tarafından görüntülenmekte olan web sayfasını önbelleğe almamasını ve istemcinin önbellek klasöründe depolamamasını bildirir.

**Rol tabanlı güvenlik, rapor veya pano paylaşma ve veri bağlantıları hakkında ne olacak? Veri erişimi, pano görüntüleme, rapor erişimi veya yenileme bakımından nasıl çalışır?**

* **Rol Düzeyi Güvenliğin (RLS) etkinleştirilmediği** veri kaynaklarında bir pano, rapor veya veri modeli Power BI üzerinden başka kullanıcılarla paylaşılırsa, veriler görüntülenmek ve etkileşimli çalışılmak üzere paylaşıldığı kullanıcıların kullanımına sunulur. Power BI verilerin özgün kaynağında kullanıcıların kimliğini yeniden *doğrulamaz*; veriler Power BI'a yüklendikten sonra başka hangi kullanıcıların ve grupların verileri görüntüleyebileceğini yönetme sorumluluğu kaynak verilerde kimliği doğrulanan kullanıcıya aittir.

  Analysis Services veri kaynağı gibi bir **RLS** özellikli veri kaynağına veri bağlantıları yapıldığında, yalnızca pano verileri Power BI önbelleğe alınır. RLS özellikli veri kaynağından gelen verilerin kullanıldığı bir rapor veya veri kümesi Power BI'da her görüntülendiğinde veya bu veri kümesine her erişildiğinde, Power BI hizmeti veri kümesine erişerek kullanıcının kimlik bilgilerine göre verileri alır ve yeterli izinler varsa veriler söz konusu kullanıcı için rapora veya veri modeline yüklenir. Kimlik doğrulaması başarısız olursa kullanıcı bir hata görür.

  Daha fazla bilgi için bu belgede daha önce bulunan [veri kaynaklarına yönelik kimlik doğrulaması](#authentication-to-data-sources) bölümüne bakın.

**Kullanıcılarımız, bazıları etki alanı kimlik bilgilerinden farklı kimlik bilgileri gerektiren her seferinde aynı veri kaynaklarına bağlanır. Her veri bağlantısı kurduklarında bu kimlik bilgilerini girmek zorunda kalmaktan kaçınabilirsiniz.**

* Power BI kullanıcıların birden çok farklı veri kaynağı için kimlik bilgileri oluşturmasına, sonra da bu veri kaynaklarından birine arka arkaya erişilirken söz konusu kimlik bilgilerini otomatik olarak kullanmasına olanak tanıyan [Power BI Personal Gateway](../connect-data/service-gateway-personal-mode.md) özelliğini sunar. Daha fazla bilgi için bkz. [Power BI Personal Gateway](../connect-data/service-gateway-personal-mode.md).

**Şirket içi veri ağ geçidi ve kişisel ağ geçidi tarafından hangi bağlantı noktaları kullanılır? Bağlantı amaçları için izin verilmesi gereken etki alanı adları var mı?**

* Bu soruya ayrıntılı yanıtı şu bağlantıda bulabilirsiniz: [ağ geçidi bağlantı noktaları](/data-integration/gateway/service-gateway-communication#ports)

**Şirket içi veri ağ geçidiyle çalışırken, kurtarma anahtarları nasıl kullanılır ve nerede depolanır? Güvenli kimlik bilgisi yönetimi ne?**

* Ağ geçidi yüklemesi ve yapılandırması sırasında yönetici bir ağ geçidi **Kurtarma Anahtarı** yazar. Bu **Kurtarma anahtarı** , güçlü bir AES Simetrik anahtar oluşturmak için kullanılır. Aynı anda RSA asimetrik anahtarı da oluşturulur.

    Oluşturulan bu anahtarlar (RSA ve AES), yerel makinede bulunan bir dosyada depolanır. Bu dosya da şifrelenmiştir. Dosya içeriğinin şifresi yalnızca söz konusu Windows makinesi tarafından ve yalnızca bu özel ağ geçidi hizmet hesabıyla çözülebilir.

    Bir kullanıcı Power BI hizmeti kullanıcı arabirimine veri kaynağının kimlik bilgilerini girdiğinde, kimlik bilgileri tarayıcıdaki ortak anahtarla şifrelenir. Ağ Geçidi, RSA özel anahtarını kullanarak kimlik bilgilerinin şifresini çözer ve veriler Power BI hizmeti depolanmadan önce AES Simetrik anahtarıyla yeniden şifreler. Bu işlemle, Power BI hizmeti hiçbir zaman şifrelenmemiş verilere erişmez.

**Şirket içi veri ağ geçidi hangi iletişim protokollerini kullanır ve bunların güvenliği nasıl sağlanır?**

* Ağ geçidi şu iki iletişim protokolünü destekler:

  - AMQP 1,0 – TCP + TLS: Bu protokol, giden iletişim için 443, 5671-5672 ve 9350-9354 bağlantı noktalarını gerektirir. İletişim yükü daha düşük olduğundan bu protokol tercih edilir.

  - HTTPS – WebSockets üzerinden https + TLS: Bu protokol yalnızca 443 numaralı bağlantı noktasını kullanır. WebSocket tek bir HTTP CONNECT iletisiyle başlatılır. Kanal oluşturulduktan sonra iletişim temelde TCP+TLS iletişimidir. Ağ geçidini, [Şirket içi ağ geçidi makalesinde](/data-integration/gateway/service-gateway-communication#force-https-communication-with-azure-service-bus)açıklanan bir ayarı değiştirerek bu protokolü kullanmaya zorlayabilirsiniz.

**Power BI'da Azure CDN'nin rolü nedir?**

* Daha önce açıklandığı gibi, Power BI statik içeriği ve dosyaları coğrafi yerel ayara göre kullanıcılara verimli bir şekilde dağıtmak için Azure Content Delivery Network (CDN) hizmetini kullanır. Daha ayrıntılı açıklamak gerekirse, Power BI hizmeti genel İnternet üzerinden kullanıcılara gerekli statik içeriği ve dosyaları verimli bir şekilde dağıtmak için birden çok CDN kullanır. Bu statik dosyalar ürün indirmelerini (Power BI Desktop, şirket içi veri ağ geçidi veya çeşitli bağımsız hizmet sağlayıcılarından Power BI uygulamaları gibi), Power BI hizmetiyle sonraki bağlantıları başlatmak ve kurmak için kullanılan tarayıcı yapılandırma dosyalarını, ayrıca başlangıçtaki güvenli Power BI oturum açma sayfasını içerir.

  Power BI hizmetiyle ilk kurulan bağlantı sırasında sağlanan bilgiler temelinde, kullanıcının tarayıcısı tarayıcının Power BI hizmetiyle iletişimini etkinleştirmek için gereken belirli ortak dosyaların koleksiyonunu indirmek amacıyla belirtilen Azure CDN ile (veya bazı dosyalar için WFE ile) iletişime geçer. Tarayıcı sayfası daha sonra Azure AD belirtecini, oturum bilgilerini, ilişkili arka uç kümesinin konumunu ve Power BI hizmeti tarayıcı oturumunun süresi boyunca Azure CDN ve WFE kümesinden indirilen dosya koleksiyonunu içerir.

**Power BI görselleri için, Microsoft, öğeleri galeriye yayımlamadan önce özel görsel kodu güvenlik veya gizlilik değerlendirmesi gerçekleştirsin mi?**

* Hayır. Özel görsel kodunu gözden geçirmek ve bu koda güvenilip güvenilmeyeceğini saptamak müşterinin sorumluluğundadır. Tüm özel görsel kodu korumalı alan ortamında çalıştırılır ve bu sayede özel görseldeki herhangi bir hatalı kodun Power BI hizmetinin kalanını olumsuz etkilemesi önlenir.

**Müşteri ağının dışına bilgi gönderen başka Power BI görselleri var mı?**

* Evet. Bing Haritalar ve ESRI görselleri, bu hizmetleri kullanan görseller için Power BI hizmetinin dışına veri iletir.

**Şablon uygulamaları için, Microsoft, öğeleri galeriye yayımlamadan önce şablon uygulamasının herhangi bir güvenlik veya gizlilik değerlendirmesi gerçekleştirmesini ister misiniz?**
* Hayır. Uygulama yayımcısı, müşterinin gözden geçirilmesi ve şablon uygulama yayımcısına güvenip güvenmeyeceğini tespit ederken içeriğin sorumluluğundadır. 

**Müşteri ağı dışına bilgi gönderebilen şablon uygulamaları var mı?**
* Evet. Yayımcının gizlilik ilkesini gözden geçirmek ve şablon uygulamanın kiracıya yüklenip yüklenmeyeceğini öğrenmek müşterinin sorumluluğundadır. Yayımcı, müşterinin uygulama davranışı ve özellikleri hakkında bilgi sağlamaktan sorumludur.

**Veri ne olacak? Verilerin ülke kenarlıklarını terk etmemesini sağlamak için, belirli coğrafi bölgelerde bulunan veri merkezlerinde kiracılar sağlayabiliriz.**

* Belirli coğrafi bölgelerdeki müşterilerin bir bölümü ulusal bulutta kiracı oluşturma seçeneğine sahiptir. Bu bulutta veri depolama ile işleme diğer tüm veri merkezlerinden ayrı tutulur. Ulusal bulut Power BI hizmetini Microsoft adına ayrı bir veri şirketi çalıştırdığından, ulusal bulutların güvenlik türü biraz farklıdır.

  Alternatif olarak, müşteriler belirli bir bölgede de kiracı ayarlayabilir. Ancak, bu kiracıların Microsoft 'tan ayrı bir veri güvenliği yoktur. Ulusal bulutların fiyatlandırması genel kullanıma sunulan ticari Power BI hizmetinden farklıdır. Ulusal bulutlar için Power BI hizmetinin kullanılabilirliği hakkında daha fazla bilgi için bkz. [Power BI ulusal bulutları](https://powerbi.microsoft.com/clouds/).

**Microsoft, Power BI Premium abonelikleri olan müşteriler için bağlantıları nasıl işler? Bu bağlantılar Premium olmayan Power BI hizmeti göre belirlenenlerden farklı midir?**

* Power BI Premium abonelikleri olan müşteriler için kurulan bağlantılar, erişim denetimi ve yetkilendirmesini etkinleştirmek için Azure AD 'yi kullanarak bir [Azure Işletmeden işletmeye (B2B)](/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b) yetkilendirme işlemi uygular. Power BI, Power BI Premium abonelerinden Power BI Premium kaynaklarına yönelik bağlantıları da diğer Azure AD kullanıcıları için yaptığı gibi işler.

## <a name="feedback-and-suggestions"></a>Geri bildirim ve öneriler

Geri bildirimleriniz bizim için önemlidir. Bu teknik incelemeye yönelik iyileştirme, eklemeler veya açıklamalar veya Power BI ilgili diğer içerikler için sahip olduğunuz tüm önerileri duymakla ilgileniyoruz. Önerilerinizi uygulamasına gönderin [pbiss@microsoft.com](mailto:pbiss@microsoft.com) .

## <a name="additional-resources"></a>Ek kaynaklar

Power BI'la ilgili daha fazla bilgi için aşağıdaki kaynaklara bakabilirsiniz.

* [Power BI Desktop ile çalışmaya başlama](../fundamentals/desktop-getting-started.md)
* [Power BI REST API - Genel Bakış](/rest/api/power-bi/)
* [Power BI API başvurusu](/rest/api/power-bi/)
* [On-premises data gateway (Şirket içi veri ağ geçidi)](../connect-data/service-gateway-onprem.md)
* [Power BI Ulusal Bulutlar](https://powerbi.microsoft.com/clouds/)
* [Power BI Premium](https://aka.ms/pbipremiumwhitepaper)
* [Power BI'daki ağ geçitleri için çoklu oturum açmaya (SSO) genel bakış](../connect-data/service-gateway-sso-overview.md)