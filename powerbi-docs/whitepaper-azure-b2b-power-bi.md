---
title: Power BI içeriğini dış konuk kullanıcılara Azure Active Directory B2B kullanarak dağıtma
description: Power BI dış konuk kullanıcılara dağıtmak için Azure Active Directory B2B kullanmayı açıklar teknik incelemesi
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 03/07/2019
ms.author: davidi
LocalizationGroup: Conceptual
ms.openlocfilehash: 79b8ae80413cc54b065d12bf36ccb1651a670812
ms.sourcegitcommit: ec5b6a9f87bc098a85c0f4607ca7f6e2287df1f5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66051588"
---
# <a name="distribute-power-bi-content-to-external-guest-users-using-azure-active-directory-b2b"></a>Power BI içeriğini dış konuk kullanıcılara Azure Active Directory B2B kullanarak dağıtma

**Özet:** Azure Active Directory--işletmeler arası (Azure AD B2B) Tümleştirmesi kullanılarak kuruluş dışındaki kullanıcılara içerik dağıtmak nasıl açıklayan bir teknik incelemedir budur.

**Yazarlar:** Lukasz Pawlowski, Kasper de Jonge

**Teknik Açıdan Gözden Geçirenler:** ADAM Wilson, Sheng Liu, Qian Liang, Sergei Gundorov, Jacob Grimm, Adem Saxton, Maya Shenhav, Nimrod Shalit, Elisabeth Olson

> [!NOTE]
> Tarayıcınızdan **Yazdır**’ı ve ardından **PDF olarak kaydet**’i seçerek bu teknik incelemeyi yazdırabilir veya kaydedebilirsiniz.

## <a name="introduction"></a>Giriş

Power BI, kuruluşlara işletmelerini 360 derecelik bir görünümünü sunar ve herkesin bu kuruluşlardaki verileri kullanarak akıllı kararlar güçlendirir. Bu kuruluşların birçoğu, dış iş ortakları, istemciler ve Yükleniciler sağlam ve güvenilir ilişkisine sahip. Bu kuruluşların güvenli erişim Power BI panoları ve raporları bu dış iş ortakları kullanıcılara sağlamanız gerekir.

Power BI ile tümleştirilir [Azure Active Directory--işletmeler arası (Azure AD B2B)](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b) hala denetimi elde tutma ve yöneten erişim sırasında Power BI'ın güvenli dağıtım içerik – kuruluş dışındaki kullanıcılara izin vermek için iç veri.

Bu teknik incelemede, Azure Active Directory B2B ile Power BI'ın tümleştirme anlamak için gereken tüm ayrıntıları ele alınmaktadır. Bunun en yaygın kullanım örneği, Kurulum, lisanslama ve satır düzeyi güvenlik ele.

> [!NOTE]
> Bu teknik yazı boyunca Azure AD olarak Azure Active Directory ve Azure Active Directory Azure AD B2B işletmeler arası diyoruz.

## <a name="scenarios"></a>Senaryoları

Contoso bir otomotiv üreticisi olan ve tüm bileşenleri, malzemeler ve üretim işlemlerini çalıştırmak gerekli hizmetleri sağlayan birçok farklı sağlayıcıdan ile çalışır. Contoso, tedarik zincirinin temel performans ölçümlerini izlemek üzere Power BI'ı kullanmak için planlar ve tedarik zinciri Lojistik kolaylaştırmak ister. Contoso dış tedarik zinciri iş ortakları analytics ile güvenli ve yönetilebilir bir şekilde paylaşmak istiyor.

Contoso, Power BI ve Azure AD B2B kullanarak dış kullanıcılar için aşağıdaki deneyimleri etkinleştirebilirsiniz.

### <a name="ad-hoc-per-item-sharing"></a>Geçici öğe paylaşım başına

Contoso, Contoso'nun otomobiller için radyatörlerine derlemeleri bir sağlayıcı ile birlikte çalışır. Genellikle, Contoso'nun otomobiller tüm verileri kullanarak radyatörlerine güvenilirliği iyileştirmek gerekir. Contoso'da Analistin bir tedarikçi mühendisi Soğutucu güvenilirlik raporu paylaşmak için Power BI kullanır. Mühendislik raporu görüntülemek için bir bağlantı içeren bir e-posta alır.

Yukarıda açıklandığı gibi bu paylaşım geçici olarak gerekli olarak iş kullanıcıları tarafından gerçekleştirilir. Dış kullanıcı için Power BI tarafından gönderilen bir Azure AD B2B davet bağlantısını bağlantıdır. Dış kullanıcı bağlantısı açıldığında bunlar Contoso Azure AD kuruluş Konuk kullanıcı olarak katılması istenir. Daveti kabul edildikten sonra belirli bir rapor veya Pano bağlantı açar. Azure Active Directory Yöneticisi, dış kullanıcılar kuruluşa davet izni atar ve bu belgenin idare bölümünde açıklandığı gibi daveti kabul ederlerse kullanıcılarla yapabileceklerinizi seçer. Azure AD Yöneticisi, bu eylem ve Power BI yalnızca izin için Contoso analist Konuk kullanıcı davet edebilir Power BI'ın Kiracı ayarlarında içeriği görüntülemek için Konukları davet etmek için yönetici kullanıcılara izin.

![Power BI'ın AAD kullanılarak Konukları davet edin](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_01.png)

1. Bir panoyu veya raporu ile dış kullanıcı paylaşımı Contoso iç kullanıcı işlemi başlar. Dış kullanıcı zaten bir konuk Contoso'nun azure'da değilse, AD, davet edilen. Contoso'nun azure'a davet içeren e-posta adresi bir e-posta gönderilmesini AD
2. Alıcı davet contoso Azure AD dizinindeki ve Contoso'nun Azure Konuk kullanıcı olarak eklenmiş kabul AD.
3. Alıcı, ardından Power BI Pano, rapor veya kullanıcı için salt okunur olan uygulamasına yönlendirilir.

İş kullanıcıları Contoso kendi iş amaçlarıyla gerektiğinde davet eylemi gerçekleştirmeye olduğundan işlem geçici olarak kabul edilir. Dış kullanıcının erişebileceği bir bağlantı olduğu her öğe paylaşılan içeriği görüntülemek için.

Contoso kaynaklara erişmek için dış kullanıcıyı davet sonra bir gölge hesabı için Contoso Azure AD içinde oluşturulabilir ve yeniden davet gerekmez.  Bir Power BI Panosu gibi bir Contoso kaynağa erişmeye çalıştıklarında ilk kez davet redeems bir onay sürecinden gitmeleri.  Onay tamamlamaz, bunların herhangi birini Contoso'nun içerik erişemez.  Bir Azure AD Yöneticisi, davetini aracılığıyla sağlanan özgün bağlantıyı kuponumu kullanmakta zorluk oluşturulduysa bunları kullanmak özel davet bağlantısını yeniden.

### <a name="planned-per-item-sharing"></a>Öğe paylaşım başına planlı

Contoso radyatörlerine güvenilirlik analizi gerçekleştirmek için bir alt yüklenici ile çalışır. Alt yüklenici, Contoso'nun Power BI ortamına verilerine erişmesi gereken 10 kişilerin bir ekibe sahiptir. Contoso Azure AD Yöneticisi, tüm kullanıcıları davet etmek ve personel en alt yüklenici değişiklik olarak eklemeleri/değişiklikleri işlemek için karmaşıktır. Azure AD Yöneticisi, en alt yüklenici tüm çalışanlar için bir güvenlik grubu oluşturur. Güvenlik grubu kullanarak, Contoso'nun çalışanlar raporlara erişimi yönetebilir ve tüm gerekli alt yüklenici personelinin tüm gerekli raporlar, panolar ve Power BI uygulamaları erişime sahip olun. Azure AD Yöneticisi, aynı zamanda davet işlemine tamamen zamanında personel emin olmak için güvenilen bir çalışana Contoso veya alt yüklenici davet hakların temsilcilere atanmasını seçerek dahil kaçınabilirsiniz yönetimi.

Bazı kuruluşların dış kullanıcılar eklenen zaman üzerinde daha fazla denetim gerektiren, dış bir kuruluşta çok sayıda kullanıcı ya da dış pek çok kuruluş davet ediyorsunuz. Bu durumlarda, planlanan paylaşımı paylaşımı, kuruluş ilkelerini zorlamak için ve hatta davet edin ve dış kullanıcıları yönetmek için güvenilir kişiler için yetki verme ölçek yönetmek için kullanılabilir. Azure AD B2B destekleyen doğrudan gönderilecek planlanmış davetler [bir BT yöneticisi tarafından Azure portalından](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator), aracılığıyla veya [davet manager API kullanarak PowerShell](https://docs.microsoft.com/azure/active-directory/b2b/customize-invitation-api) burada kullanıcı davet edilemez birinde Eylem. Yaklaşım davet planlanan kullanarak, kuruluş kullanan kullanıcıları davet ve onaylama işlemlerini uygulamak kontrol edebilirsiniz. Azure AD dinamik grupları güvenlik grup üyeliğini otomatik olarak korumak kolay yapabilirsiniz gibi gelişmiş.


![Denetim içeriği hangi Konukları görebilirsiniz](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_02.png)



1. El ile veya API üzerinden Azure Active Directory tarafından sağlanan Konuk kullanıcı davet BT yöneticisi ile işlem yıldız
2. Kullanıcı kuruluşa davet kabul eder.
3. Kullanıcının daveti kabul edildikten sonra bir kullanıcının Power bı'da bir rapora veya panoya dış kullanıcı ya da bir güvenlik grubu içinde bulundukları paylaşabilirsiniz. Normal Power BI'da paylaşım ile olduğu gibi dış kullanıcı öğenin bağlantısını içeren bir e-posta olarak alır.
4. Ne zaman bağlantı, kimlik doğrulamasını directory'lerinde Contoso için geçirilen dış kullanıcı erişimlerinin Azure ad'sine ve Power BI içeriğine erişim kazanmak için kullanılır.

### <a name="ad-hoc-or-planned-sharing-of-power-bi-apps"></a>Geçici veya planlanan Power BI uygulamaları paylaşım

Contoso, raporlar ve Panolar ile bir veya daha fazla tedarikçileri paylaşmak için ihtiyaç duydukları kümesi vardır. Gerekli tüm dış kullanıcıların bu içeriğe erişiminiz olduğundan emin olmak için bir Power BI uygulaması olarak paketlenir. Dış kullanıcılar, uygulama erişim listesine doğrudan veya güvenlik grupları üzerinden ya da eklenir. Contoso, ardından uygulama URL'sini tüm dış kullanıcılar, örneğin bir e-posta gönderir. Dış kullanıcıları bağlantıyı açtığınızda, tüm içerikleri tek bir kolayca deneyimine gitmek için görürler.

Power BI uygulamasında, bir BI portalı tedarikçileri için oluşturmak Contoso kolaylaştırır. Bir tek bir erişim listesi, durum zaman denetleme ve öğe düzeyi izinleri ayarlama azaltma tüm gerekli içeriği erişimi denetler. Azure AD B2B, böylece kullanıcılar ek oturum açma kimlik bilgileri gerekmez, tedarikçi yerel kimlik kullanarak güvenlik erişimi korur. Güvenlik grupları ile davet planlı kullanarak, uygulamaya erişim yönetimi personel içine veya dışına proje döndürürken basitleştirilmiştir. Üyelik, güvenlik gruplarını el ile veya kullanılarak [dinamik gruplar](https://docs.microsoft.com/azure/active-directory/b2b/use-dynamic-groups), böylece bir sağlayıcıdan tüm dış kullanıcıların otomatik olarak uygun güvenlik grubuna eklenir.


![AAD ile içerik denetimi](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_03.png)

1. Azure portal veya PowerShell aracılığıyla Contoso Azure AD kuruluş davet kullanıcı tarafından işlemi başlatır.
2. Kullanıcının Azure AD'de bir kullanıcı grubuna eklenebilir. Bir statik veya dinamik kullanıcı grubu kullanılabilir, ancak dinamik gruplar el ile gerçekleştirilen iş miktarını azaltmaya yardımcı olur.
3. Dış kullanıcılar, kullanıcı grubu ile Power BI uygulaması için erişim verilir. Uygulama URL'si doğrudan dış kullanıcı tarafından gönderilebilecek veya bir sitede yer erişimleri. Power BI harici kullanıcılara uygulama bağlantısını içeren bir e-posta göndermek için bir en iyi hale getirir ancak kullanıcı grupları üyeliğini değiştirebilirsiniz kullanırken, Power BI kullanıcı grupları yönetilen tüm dış kullanıcılara göndermek mümkün değildir.
4. Dış kullanıcı Power BI uygulama URL'sini eriştiğinde, Contoso'nun Azure tarafından doğrulanır AD, uygulama kullanıcı için yüklenir ve kullanıcının tüm kapsanan raporlar ve panolar uygulama içinde görebilirsiniz.

Uygulamalar, uygulama yazarların kullanıcı oturum açtığında kullanılabilir olacak şekilde otomatik olarak kullanıcı, uygulamayı yüklemek benzersiz bir özellik de sahiptir. Bu özellik yalnızca otomatik olarak zaten Contoso'nun kuruluş zaman uygulama yayımlanmış veya güncelleştirilmiş bir parçası olan dış kullanıcılar için yükler. Bu nedenle, iyi planlanmış davetler yaklaşımıyla kullanılır ve yayımlanan veya kullanıcıların Contoso'nun Azure'a eklendikten sonra güncelleştirilmiş olması uygulama bağlıdır AD. Dış kullanıcılar, her zaman uygulama bağlantısı kullanarak uygulamayı yükleyebilir.

### <a name="commenting-and-subscribing-to-content-across-organizations"></a>Yorum ve kuruluşlar arasında içeriğe abone

Contoso bunun alt yüklenicilerin veya tedarikçileri ile çalışmaya devam ettikçe dış mühendislerin yakın Contoso'nun analistleri ile çalışması gerekir. Power BI, kullanıcıların kullanabilecekleri içerikle ilgili iletişim kurmasına yardımcı çeşitli işbirliği özelliklerini sağlar. Panonun yorum (ve yakında raporu yorumlama) kullanıcıların görebilir ve soru sormak için rapor yazarları ile iletişim kurmak veri noktaları ele olanak tanır.

Şu anda dış konuk kullanıcılara yorum bırakın ve yanıtları okuyarak açıklamalarda katılabilir. Ancak, iç kullanıcılar farklı olarak, Konuk kullanıcılar olamaz @mentioned ve bir açıklamayı alıp almadığınızı bildirimleri almazsınız. Konuk kullanıcılar Power BI içinde abonelikleri özelliği makalenin yazıldığı sırada kullanamaz. Konuk kullanıcı bir yorum, e-posta alır ve gelecek bir sürümde bu kısıtlamaların kaldırılması @mentions bunları veya ne zaman bir abonelik girmediklerinden Power bı'da içerik için bir bağlantı içeren e-posta.

### <a name="access-content-in-the-power-bi-mobile-apps"></a>Power BI mobil uygulamalarında erişim içeriği

Contoso'nun kullanıcıların dış Konuk karşılıklarını raporlar veya Pano paylaştığınızda gelecek bir sürümde Power BI Konuk bildiren bir e-posta gönderin. Rapor veya Pano mobil cihazlarında bağlantısını Konuk kullanıcı oturum açtığında, bunlar yüklü değilse içerik, cihazındaki yerel Power BI mobil uygulamalarında açılır. Konuk kullanıcı ardından dış Kiracı ve kendi içeriğinden giriş, kiracılarının dön kendileriyle paylaşılan içerik arasında gezinmek mümkün olacaktır.

> [!NOTE]
> Konuk kullanıcıya Power BI mobil uygulamasını açın ve hemen dış kiracıya gidin, dış kiracısındaki bir öğeye bir bağlantı ile başlamalıdır. Genel geçici çözümler açıklanmıştır [üst kuruluşun Power bı'da içerik bağlantıları dağıtma](#distributing-links-to-content-in-the-parent-organizations-power-bi) bu belgenin sonraki bölümlerinde bölümü.

### <a name="cross-organization-editing-and-management-of-power-bi-content"></a>Kuruluşlar arası düzenleme ve Power BI içerik yönetimi

Contoso ve sağlayıcıları ve alt yüklenicilerin verilerinize giderek daha yakından birlikte çalışır. Genellikle alt yüklenici analist Contoso paylaştığı bir rapora eklenecek ek ölçümleri veya veri görselleştirme gerekir. Veri Contoso'nun Power BI kiracısında bulunmalıdır ancak harici kullanıcılar düzenlemek, yeni içerik oluştur ve hatta bunu uygun kişilere dağıtma olmalıdır.

Power BI sağlayan bir seçenek sağlar **dış konuk kullanıcılara düzenleyebilir ve içeriği yönetme** kuruluştaki. Varsayılan olarak, dış kullanıcılar bir salt okunur tüketim tabanlı deneyime sahiptir. Ancak, bu yeni ayar hangi dış kullanıcıların düzenlemek ve yönetmek seçmek Power BI yönetici kendi kurumlarından içerik sağlar. İzin sonra dış kullanıcı raporları, panolar düzenlemek, yayımlamak veya uygulamaları güncelleştirme, çalışma alanlarında çalışabilir ve kullanma iznine sahip oldukları verilere.

Bu senaryo, düzenlemek ve daha sonra bu belgedeki içeriği Power bı'da yönetmek için bölüm etkinleştirme dış kullanıcılar ayrıntılı açıklanmıştır.

## <a name="organizational-relationships-using-power-bi-and-azure-ad-b2b"></a>Power BI ve Azure AD B2B kullanarak kurumsal ilişkiler

Power BI'ın tüm kullanıcılar kuruluşa iç olduğunda, Azure AD B2B kullanmaya gerek yoktur. İki veya daha fazla kuruluşların verileri ve öngörüleri üzerinde işbirliği yapmak istediğiniz bir kez ancak Power BI'ın desteği Azure AD B2B, kolay ve bunu yapmak için uygun maliyetli hale getirir.

Power bı'da Azure AD B2B stili kuruluşlar arası işbirliği için uygun olan sık rastlanan kuruluş yapıları aşağıda verilmiştir. Azure AD B2B da çoğu durumda çalışır, ancak bazı durumlarda ortak yaklaşımlar bu belgenin sonunda kapsamında dikkate değer olan.

### <a name="case-1-direct-collaboration-between-organizations"></a>1. durum: Kuruluşlar arasında doğrudan işbirliği

Contoso'nun ilişki, Soğutucu tedarikçiden ile kuruluşlar arasında doğrudan işbirliği örneğidir. Contoso'da nispeten az sayıda kullanıcı varsa ve dış paylaşım Azure AD B2B kullanarak Soğutucu güvenilirlik bilgilere erişmesi gereken, sağlayıcı tabanlı olduğundan idealdir. Bu kullanımı kolay ve yönetmek basit olur. Danışmanlık hizmetleri de genel bir desen ayrıca burada bir danışman içeriği bir kuruluş için oluşturmak gerekebilir yöntemdir.

![Kuruluşlar arasında paylaşma](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_04.png)


Genellikle, bu paylaşım başlangıçta geçici öğe paylaşım başına kullanarak gerçekleşir. Ancak, takımlar büyütün veya ilişkileri güçlendirmenizi, planlanan öğesi paylaşım başına yaklaşım yönetim yükünü azaltmak için tercih edilen yöntem olur. Ayrıca, geçici veya planlanan Power BI uygulamaları paylaşım, yorum oluşturma ve kuruluşlar arasında içeriğe abone, mobil uygulamalar içeriği erişim imkanı de play ve kuruluşlar arası düzenleme ve Power BI içerik yönetimini gelebilir. Önemlisi, her iki kuruluşta kullanıcılar kendi kuruluşlarının Power BI Pro lisansları varsa, bunlar birbirlerinin Power BI ortamlarda Pro lisansları kullanabilirsiniz. Bu, davet eden kuruluştan bir Power BI Pro lisansı dış kullanıcılar için ödeme yapmak gerekebileceği değil avantajlı lisanslama sağlar. Bu lisans bölümünde bu belgenin ilerleyen bölümlerinde daha ayrıntılı olarak ele alınmıştır.

### <a name="case-2-parent-and-its-subsidiaries-or-affiliates"></a>2. durum: Üst ve yan kuruluşlarının veya yan kuruluşlarının

Bazı kuruluş yapıları kısmen veya tamamen ait bağlı kuruluşlarının, bağlı şirketlerine veya yönetilen hizmet sağlayıcısı ilişkileri gibi daha karmaşık. Bir üst kuruluşunuz bir holding gibi bu kuruluşların var, ancak temel alınan kuruluşların noktalı otonom olarak, bazen farklı bölgesel gereksinimleri altında çalışır. Bu, kendi Azure AD ortamını ve farklı Power BI kiracıları sahip her kuruluş için yol açar.

![Yan kuruluşlar ile çalışma](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_05.png)


Bu yapıda, standartlaştırılmış ınsights'a onun bağlı kuruluşlarının dağıtmak üst kuruluşun genellikle gerekir. Genellikle, bu paylaşım geçici veya planlanan geniş hedef kitlelerine standartlaştırılmış yetkili içeriği dağıtımının olanak tanıdığından, aşağıdaki görüntüde gösterildiği gibi Power BI uygulamaları yaklaşımın paylaşımı kullanarak gerçekleşir. Uygulamada, bu belgede daha önce bahsedilen tüm senaryoları birlikte kullanılır.

![Birleştirme senaryoları](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_06.png)


Bu, aşağıdaki işlemi aşağıdaki gibidir:

1. Her yan kuruluşu olan kullanıcılardan Contoso'nun Azure'a davet AD
2. Power BI uygulaması için gerekli verileri bu kullanıcıların erişimlerini ardından yayımlanır
3. Son olarak, kullanıcıların raporları görmek için verilmişse bir bağlantı aracılığıyla uygulamayı açın

Birkaç önemli zorlukları, bu yapı kuruluşların karşı karşıya kalmaktadır:

- Üst kuruluşunuzun Power bı'daki içeriklere bağlantıların nasıl dağıtılacağını
- Üst kuruluş tarafından barındırılan bir veri kaynağına erişmek bayi kullanıcılar izin verme

#### <a name="distributing-links-to-content-in-the-parent-organizations-power-bi"></a>Üst kuruluşun Power bı'da içerik bağlantıları dağıtma

Üç yaklaşımları içeriklere dağıtmak için yaygın olarak kullanılır. İlk ve en temel bağlantı gerekli kullanıcıları uygulamaya göndermek için veya bir SharePoint Online sitesine içinden açılıp yerleştirmek için. Ardından kullanıcılar tarayıcılarını ihtiyaç duydukları verilere daha hızlı erişim için bağlantıya yer işareti ekleyebilirsiniz.

İkinci yaklaşım, kuruluşlar arası düzenleme ve management Power BI içerik yeteneğinin kullanır. Üst kuruluş ortak, Power BI erişmesine olanak tanır ve izni erişim denetler. Bu BI giriş burada kullanıcı temsilcisine üst kuruluşun kiracısında kendileriyle paylaşılan içerik kapsamlı bir listesini görür Power erişmenizi sağlar. Ardından üst kuruluşlar Power BI ortam URL'si altındaki yan kuruluşları kullanıcılar verilir.

Son bir yaklaşım, her bir yan kuruluşu için Power BI kiracınızın içinde oluşturulan bir Power BI uygulamasını kullanır. Power BI uygulaması ile bir Pano içerir [dış bağlantı seçeneği ile yapılandırılan kutucukları](https://docs.microsoft.com/power-bi/service-dashboard-edit-tile#hyperlink). Kullanıcı kutucuğu bastığında uygun raporu, Pano veya üst kuruluşun Power bı'da uygulama alınır. Bu yaklaşım, uygulamanın yan kuruluşu olan tüm kullanıcılar için otomatik olarak yüklenebilir ve kendi Power BI ortamına oturum her kullanabilecekleri ek faydası vardır. Bu yaklaşım, ek bir avantaj bağlantı yerel olarak açabileceğiniz de Power BI mobil uygulamaları ile çalışmamasıdır. Ayrıca bunu daha kolay bir şekilde Power BI ortamlar arasında geçiş yapma etkinleştirmek için ikinci yaklaşım kullanılarak birleştirebilirsiniz.

#### <a name="allowing-subsidiary-users-to-access-data-sources-hosted-by-the-parent-organization"></a>Üst kuruluş tarafından barındırılan veri kaynaklarına erişmek bayi vererek

Genellikle bir yan kuruluşu, analistlerin, üst kuruluşunuz tarafından sağlanan verileri kullanarak, kendi analiz oluşturmanız gerekebilir. Bu durumda, yaygın olarak bulut veri kaynağı sorunu çözmek için kullanılır.

İlk yaklaşım yararlanır [Azure Analysis Services](https://docs.microsoft.com/azure/analysis-services/analysis-services-overview) analistlerin ihtiyaçlarını üst ve onun bağlı kuruluşlarının aşağıdaki resimde gösterildiği gibi hizmet veren bir kurumsal sınıf veri ambarı oluşturmak için. Contoso, verileri barındırmak ve kullanıcılar her bir yan kuruluşu emin olmak için satır düzeyi güvenlik yalnızca verilerine erişebilir gibi özellikleri kullanın. Her kuruluş, analistleri, veri ambarına Power BI Desktop erişim ve sonuçta elde edilen analiz ilgili Power BI kiracıları için yayımlayın.

![Power BI kiracıyla paylaşımı nasıl gerçekleşir](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_07.png)


İkinci yaklaşım yararlanır [Azure SQL veritabanı](https://azure.microsoft.com/services/sql-database/) verilerine erişim sağlaması için ilişkisel veri ambarı oluşturmak için. Bu benzer şekilde Azure Analysis Services yaklaşımı, ancak satır düzeyi güvenlik dağıtıp yan kuruluşlar arasında korumak zor olabilir gibi bazı özellikler çalışır.

Daha karmaşık bir yaklaşım da yukarıdaki arayla en sık karşılaşılan, ancak mümkündür.

### <a name="case-3-shared-environment-across-partners"></a>3. durum: İş ortakları arasında paylaşılan bir ortamda

Contoso, tüm dünyada bir araba üzerinde paylaşılan bir montaj hattı oluşturmak için ancak aracın farklı markaları altında veya farklı bölgelerde dağıtmak için rakip ile iş ortaklığı içine girebilirsiniz. Bu, kuruluşlar arasında kapsamlı işbirliği ve veri, zeka ve analiz co-ownership gerektirir. Bu yapı Ayrıca, danışmanlar ekibi için bir istemci projesi tabanlı analiz nerede yapabilirsiniz danışmanlık hizmetleri sektörün yaygındır.

![İş ortakları arasında paylaşılan bir ortamda](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_08.png)



Uygulama, bu yapılar aşağıdaki görüntüde gösterildiği gibi karmaşık ve korumak için personeli gerektirir. Etkili olması için ilgili Power BI kiracıları için satın alınan Power BI Pro lisanslarını yeniden kuruluşların olanak tanıdığından bu yapı kuruluşlar arası düzenleme ve management Power BI içerik yeteneğinin kullanır.

![Lisanslar ve paylaşılan kuruluş içerik](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_09.png)



Paylaşılan bir Power BI kiracısı oluşturmak için Azure Active Directory oluşturulması gerekir ve en az bir Power BI Pro kullanıcı hesabı, active Directory'de bir kullanıcı için satın almanız gerekir. Bu kullanıcı, gerekli kullanıcıları paylaşılan kuruluşa davet eder. Bunlar paylaşılan kuruluşunuzun Power BI hizmetinde çalışır olduğunda da önemlisi, bu senaryoda, Contoso'nun kullanıcıların dış kullanıcı olarak kabul edilir.

İşlemi aşağıdaki gibidir:

1. Yeni bir kuruluş içinde en az bir kullanıcı hesabı oluşturulur ve paylaşılan kuruluş yeni bir Azure Active Directory kurulur. Kullanıcının kendisine atanmış bir Power BI Pro Lisansı olmalıdır.
2. Bu kullanıcıya bir Power BI Kiracı oluşturur ve gerekli kullanıcıları Contoso ve iş ortağı kuruluşun davet eder. Kullanıcı, Azure Analysis Services gibi herhangi bir paylaşılan veri varlıklarını da oluşturur. Contoso ve iş ortağı kullanıcılar paylaşılan kuruluşunuzun Power BI Konuk kullanıcılar erişebilir. Düzenleme ve Power BI içeriği yönetme izni olmadığını dış kullanıcılar Power BI giriş kullanın, çalışma alanları, karşıya yükleme veya düzenleme içerik kullanın ve raporları paylaşabilirsiniz. Genellikle, paylaşılan tüm varlıklara depolanır ve paylaşılan kuruluştan erişilebilir.
3. Nasıl taraflar işbirliği kabul bağlı olarak, her kuruluşun kendi özel veri ve paylaşılan veri ambarı varlıkları kullanarak analytics geliştirmek mümkündür. Bunlar, bu iç Power BI kiracıları kullanarak kendi ilgili iç kullanıcılara dağıtabilirsiniz.

### <a name="case-4-distribution-to-hundreds-or-thousands-of-external-partners"></a>4. durum: Yüzlerce veya binlerce dış iş ortakları için dağıtım

Artık contoso Soğutucu güvenilirlik rapor için bir sağlayıcı oluşturulmuş olsa da Contoso tedarikçileri yüzlerce için standartlaştırılmış raporlar oluşturmak istediği. Bu geliştirmeler yapmak veya üretim hatalarını düzeltmek için ihtiyaç duydukları analytics tüm Üreticiler olduğundan emin olmak Contoso sağlar.

![Birçok iş ortakları için dağıtım](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_10.png)


Bir kuruluş, standartlaştırılmış verileri ve öngörüleri birçok dış kullanıcıların/kuruluşlara dağıtmak gerektiğinde, geçici veya planlanan paylaşımı Power BI uygulamaları senaryo BI Portal, hızlı ve kapsamlı geliştirme maliyetleri olmadan oluşturmak için kullanabilirler. Power BI uygulamasını kullanarak portal oluşturma işlemi, örnek durum incelemesini içinde ele alınmıştır: Power BI'ı kullanarak BI Portal + Azure AD B2B – adım adım yönergeler bu belgenin sonraki bölümlerinde oluşturma.

Bu durumda, ortak bir değişken, bir kuruluş için Power BI ile Azure B2C kullanmaya yönelik özellikle baktığımda tüketicilerinizle öngörüleri paylaşmak çalışıyor andır. Power BI, Azure B2C yerel olarak desteklemez. Bu durumda seçeneklerini değerlendiriyorsanız alternatif seçenek 2 ortak yaklaşımlar içinde bu belgenin sonraki bölümlerinde bölümü kullanarak göz önünde bulundurun.

## <a name="case-study-building-a-bi-portal-using-power-bi--azure-ad-b2b--step-by-step-instructions"></a>Örnek olay incelemesi: Oluşturma bir Power BI'ı kullanarak BI Portal + Azure AD B2B – adım adım yönergeler

Azure AD B2B ile Power BI'ın tümleştirme Contoso Konuk kullanıcılar, BI portalı güvenli erişim sağlamak için sorunsuz, sorunsuz bir yol sağlar. Contoso bu üç adımı ile ayarlayabilirsiniz:

![Portal oluşturma](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_11.png)


1. Power BI’da BI portal oluşturma

    Contoso için ilk görev, Power BI'da, BI portalı oluşturmaktır. Contoso'nun BI portalı amaca yönelik panolar ve raporların çoğu iç ve Konuk kullanıcılar için kullanılabilir hale getirilir koleksiyonu oluşur. Power BI'da Bunu yapmak için önerilen yol, bir Power BI uygulaması oluşturmaktır. Daha fazla bilgi edinin [Power bı'da uygulamalar](https://powerbi.microsoft.com/blog/distribute-to-large-audiences-with-power-bi-apps/).

- Contoso'nun BI ekibi, Power BI'da uygulama çalışma alanı oluşturur

    ![Uygulama çalışma alanı](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_12.png)
    

- Diğer yazarların çalışma alanına eklenir.

    ![Yazarlar Ekle](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_13.png)


- İçerik içinde çalışma alanı oluşturulur.

    ![Çalışma alanı içindeki içerik oluşturma](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_14.png)


    İçeriği bir uygulama çalışma alanında oluşturulur, bu içeriği kullanmak için iş ortağı kuruluşta Konuk kullanıcıları davet etmek üzere Contoso hazırdır.

2. Konuk Kullanıcı Davet Et

    Power BI, BI portalında Konuk kullanıcılar davet etmek üzere Contoso için iki yolu vardır:

    * Planlanmış davetler
    * Geçici davetler

    **Planlanmış davetler**

    Bu yaklaşım, Contoso, Azure AD'ye önceden Konuk kullanıcıları davet ve ardından bunları Power BI içeriği dağıtır. Contoso Azure portaldan veya PowerShell kullanarak Konuk kullanıcılar davet edebilirsiniz. Azure portalından Konuk kullanıcıları davet etmek için adımlar şunlardır:

    - Contoso Azure AD Yöneticisi gider **Azure portalı > Azure Active Directory > Kullanıcılar ve Gruplar > tüm kullanıcılar > Yeni Konuk kullanıcı**

    ![Konuk kullanıcı](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_15.png)


    - Konuk kullanıcılar davet iletisine ekleyin ve davet tıklayın

    ![Davet Ekle](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_16.png)


    > [!NOTE]
    > Azure portalından Konuk kullanıcıları davet etmek için Azure Active Directory kiracınızın Yöneticisi için gerekir.

    Contoso, çok sayıda Konuk kullanıcıları davet etmek isterse, PowerShell kullanarak yapabilirsiniz. Contoso Azure AD Yöneticisi, bir CSV dosyasında tüm Konuk kullanıcılar e-posta adreslerini depolar. İşte [Azure Active Directory B2B işbirliği kodu ve PowerShell örnekleri](https://docs.microsoft.com/azure/active-directory/b2b/code-samples) ve yönergeler.

    Davet sonra konuk kullanıcılar davet bağlantısını içeren bir e-posta alır.

    ![Davet bağlantı](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_17.png)


    Konuk kullanıcılar bağlantısına tıkladığınızda, bunlar Contoso Azure AD kiracısında içeriğe erişebilir.

    > [!NOTE]
    > Açıklandığı gibi Azure AD marka özelliğini kullanarak e-posta davetiyesi düzenini değiştirmek mümkündür [burada](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-invitation-email).


    **Geçici davetler**

    Peki Contoso önceden davet etmek istediği tüm Konuk kullanıcılar bilmez? Veya BI portalı oluşturuldu analist contoso'da ne kendisini Konuk kullanıcılar içeriği dağıtmak istiyor? Bu senaryonun Power BI'da ile geçici davetler destekliyoruz.

    Bunlar, yayımlama sırasında analist yalnızca uygulama erişim listesine dış kullanıcıları ekleyebilirsiniz. Konuk kullanıcıları davet alır ve bunlar kabul ettikten sonra Power BI içeriği otomatik olarak yönlendirilir.

    ![Dış kullanıcı ekleme](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_18.png)


    > [!NOTE]
    > Davetler, yalnızca bir dış kullanıcının kuruluşunuza davet ilk kez gereklidir.


3. İçeriği Dağıt

    Contoso'nun BI ekibi BI portalında oluşturulan ve Konuk kullanıcılar davet göre bunlar kendi son kullanıcıları portalında Konuk kullanıcılar uygulamaya erişim verme ve yayımlama dağıtabilirsiniz. Power BI otomatik olarak Contoso kiracıya daha önce eklediğiniz konuk kullanıcıların adları tamamlar. Geçici davetler diğer Konuk kullanıcılar da bu noktada eklenebilir.

    > [!NOTE]
    > Dış kullanıcılar için uygulama erişimi yönetmek için güvenlik gruplarını kullanıyorsanız, planlanmış davetler yaklaşımı kullanın ve uygulama bağlantısı erişmesi gereken doğrudan her dış kullanıcıyla paylaşın. Aksi takdirde, dış kullanıcıyı yüklemek veya uygulamadaki içeriği görüntülemek mümkün olmayabilir. _

    Konuk kullanıcılar, uygulama bağlantısını içeren bir e-posta alın.

    ![E-posta davetiyesi bağlantısı](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_19.png)


    Bu bağlantıya tıklandığında üzerinde Konuk kullanıcılar kendi kuruluş kimliği ile kimlik doğrulaması istenir.

    ![Oturum açma sayfası](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_20.png)


    Başarıyla doğrulandıktan sonra bunlar Contoso'nun BI uygulamaya yönlendirilir.

    ![Paylaşılan içeriğe bakın](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_21.png)

    Konuk kullanıcılar daha sonra e-postadaki bağlantıya tıklayarak veya bağlantıya yer işareti ekleme Contoso uygulamasına alabilirsiniz. Contoso Ayrıca, Konuk kullanıcılar için konuk kullanıcıların halen kullandıkları tüm mevcut extranet portalı için bu bağlantıyı ekleyerek kolaylaştırabilir.

4. Sonraki adımlar

    Bir Power BI uygulaması ile Azure AD B2B, Contoso BI portalı tedarikçileri için bir kod içermeyen şekilde hızlı bir şekilde oluşturabilir. Bu, büyük ölçüde standartlaştırılmış analiz için gerekli tüm Üreticiler dağıtma Basitleştirilmiş.

    Power BI, tek bir sık kullanılan rapor Üreticiler arasında nasıl dağıtılmış bir örnek gösterilmiştir, ancak çok daha gidebilirsiniz. Her iş ortağı yalnızca kendileriyle ilgili verileri görür emin olmak için satır düzeyi güvenlik kolayca rapor ve veri modeline eklenebilir. Bu belgenin sonraki bölümlerinde dış iş ortakları bölümü için veri güvenliği, ayrıntıları bu işlemini açıklar.

    Genellikle ayrı raporlar ve panolar, varolan bir Portalı'na eklenmesi gerekir. Bu, örnekte gösterilen teknikleri çoğunu yeniden da gerçekleştirilebilir. Ancak, bu tür durumlarda raporlarına veya panolara bir çalışma alanından doğrudan katıştırmak daha kolay olabilir. Davet etme ve güvenlik izin atama işlemi kullanıcılar aynı kalmasını gerektirir.

## <a name="under-the-hood-how-is-lucy-from-supplier1-able-to-access-power-bi-content-from-contosos-tenant"></a>Başlık altında: Nasıl Lucy gelen Supplier1 Power BI içeriğini Contoso'nun kiracıdan erişebilir mi?

Contoso Konuk iş ortağı kuruluşlardaki kullanıcılara Power BI içeriğini sorunsuz bir şekilde dağıtmak için nasıl olduğunu gördük, bu başlık altında nasıl çalıştığını konumunda göz atalım.

Contoso zaman davet [ lucy@supplier1.com ](mailto:lucy@supplier1.com) kendi dizini için Azure AD arasında bir bağlantı oluşturur. [ Lucy@supplier1.com ](mailto:Lucy@supplier1.com) ve Contoso Azure AD Kiracı. Bu bağlantıyı Azure AD'ye biliyor sağlar Lucy@supplier1.com Contoso kiracısındaki içeriğe erişebilir.

Lucy Contoso'nun Power BI uygulaması erişmeye çalıştığında Azure AD'ye Lucy Contoso kiracısındaki erişebilirsiniz ve ardından Power BI Lucy Contoso kiracıda içerik erişimi doğrulandığını gösteren bir belirteç sağlar doğrular. Power BI Bu belirteci yetkilendirme ve Lucy Contoso'nun Power BI uygulamasına erişimi olduğundan emin olmak için kullanır.

![Doğrulama ve yetkilendirme](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_22.png)

Azure AD B2B ile Power BI'ın entegrasyonu, tüm iş e-posta adresi ile çalışır. Kullanıcının bir Azure AD kimlik yoksa, oluşturmanız istenebilir. Aşağıdaki görüntüde ayrıntılı akışı gösterilmektedir:

![Tümleştirme akış çizelgesi](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_23.png)


Önemli olan Azure AD, bu kullanıcının Azure AD hesabını kullanılan veya kaldırılacak harici taraf içinde oluşturulmuş olduğunu bilmek Kiracı Lucy, kendi kullanıcı adı ve parola kullanabilir ve kendi kimlik bilgilerini, otomatik olarak diğer çalışmayı durdurur mümkün olduğunda yapma Filiz Her Kuruluş Azure AD'ye kullandığında şirketten ayrılması.

## <a name="licensing"></a>Lisanslama

Contoso üç yaklaşımlardan biri, tedarikçileri ve iş ortağı kuruluşlar Power BI içerik erişimi için konuk kullanıcılara lisans seçebilirsiniz.

> [!NOTE]
> _Azure AD B2B'ın ücretsiz katmanı, Azure AD B2B ile Power BI'ı kullanmak için yeterli olacaktır. Dinamik gruplar gibi bazı gelişmiş Azure AD B2B özellikleri, Ek lisanslar gerektirir. Lütfen ek bilgi için Azure AD B2B belgelerine bakın:_ [_https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance_](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance)

### <a name="approach-1-contoso-uses-power-bi-premium"></a>Yaklaşım 1: Power BI Premium contoso kullanır

Bu yaklaşımla, Contoso Power BI Premium kapasitesi satın alma ve BI portal içeriğini bu kapasiteye atar. Bu iş ortağı kuruluşlardan Konuk kullanıcılar herhangi bir Power BI lisansı olmadan Contoso'nun Power BI uygulamasına erişmesine izin verir.

Dış kullanıcılar ayrıca, Power BI Premium içinde içerik kullanırken Power bı'da "Ücretsiz" kullanıcılara yalnızca deneyimleri sunulan tüketim tabidir.

Contoso da artırılmış yenileme sıklığı, ayrılmış kapasite ve büyük model boyutları gibi uygulamalar için diğer Power BI premium özelliklerden yararlanabilirsiniz.

![Ek Özellikler](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_24.png)


### <a name="approach-2-contoso-assigns-power-bi-pro-licenses-to-guest-users"></a>Yaklaşım 2: Contoso Konuk kullanıcılar için Power BI Pro lisansları atar.

Bu yaklaşımla, Contoso pro lisansları Konuk iş ortağı kuruluşlar atar: Contoso'nun Microsoft 365 Yönetim Merkezi'nden bu yapılabilir. Bu iş ortağı kuruluşlardan konuk kullanıcıların Lisans kendilerini satın almadan Contoso'nun Power BI uygulamasına erişmesine izin verir. Bu, kuruluşunuzun Power BI henüz başlamıştır olmayan dış kullanıcılarla paylaşmak için uygun olabilir.

> [!NOTE]
> _Yalnızca bunlar Contoso kiracısındaki içeriğe eriştiğinde Contoso'nun pro lisansı Konuk kullanıcılar için geçerlidir. Pro lisansları Power BI Premium kapasitede olmayan içerik erişimi etkinleştirin. Bununla birlikte, dış kullanıcılarla Pro sürüm lisansı tüketim yalnızca deneyimi için varsayılan olarak kısıtlanmıştır. Açıklanan bir yaklaşım kullanarak bu değişikliği olabilir_ _düzenleyin ve Power bı'da içerik yönetmek dış kullanıcıların_ _bu belgenin sonraki bölümünde._

![Lisans bilgileri](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_25.png)


### <a name="approach-3-guest-users-bring-their-own-power-bi-pro-license"></a>Yaklaşım 3: Konuk kullanıcılar kendi Power BI Pro lisansı Getir

Bu yaklaşımda, tedarikçi 1 Lucy için Power BI Pro lisansı atar. Filiz, daha sonra Contoso'nun Power BI uygulaması ile bu lisans erişebilirsiniz. Lucy Pro lisansı kendi kuruluştan bir dış Power BI ortam erişirken kullanabilir olduğundan, bu yaklaşım bazen olarak adlandırılır _kendi lisansını Getir_ (KLG). Her iki kuruluşta Power BI kullanıyorsanız, bu yararlı yönelik genel bir analiz çözümü lisans sunar ve dış kullanıcılara lisanslar atama yükünü en aza indirir.

> [!NOTE]
> _Pro lisansı için Lucy tedarikçi 1 tarafından verilen Lucy Konuk kullanıcı olduğu tüm Power BI kiracısı için geçerlidir. Pro lisansları Power BI Premium kapasitede olmayan içerik erişimi etkinleştirin. Bununla birlikte, dış kullanıcılarla Pro sürüm lisansı tüketim yalnızca deneyimi için varsayılan olarak kısıtlanmıştır. Açıklanan bir yaklaşım kullanarak bu değişikliği olabilir_ _düzenleyin ve Power bı'da içerik yönetmek dış kullanıcıların_ _bu belgenin sonraki bölümünde._

![Pro lisansı gereksinimleri](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_26.png)

## <a name="data-security-for-external-partners"></a>Dış iş ortakları tarafından sunulan veri güvenliği

Yaygın olarak birden çok dış sağlayıcıları ile çalışırken, Contoso her tedarikçi yalnızca kendi ürünlerle ilgili verileri görür sağlaması gerekir. Kullanıcı tabanlı güvenlik ve dinamik satır düzeyi güvenlik bu Power BI ile gerçekleştirmek kolay hale getirir.

### <a name="user-based-security"></a>Kullanıcı tabanlı güvenlik

Power BI'ın en güçlü özelliklerden biri, satır düzeyi güvenlik olduğundan. Bu özellik, her kullanıcı için farklı güvenlik kuralları hala geçerlidir ancak tek bir rapor ve veri kümesi oluşturmak Contoso sağlar. Ayrıntılı bir açıklama için bkz. [satır düzeyi güvenlik (RLS)](https://powerbi.microsoft.com/documentation/powerbi-admin-rls/).

Contoso kiracısına davet edilen olarak satır düzeyi güvenlik kurallarını konuk kullanıcılara atamak Contoso Azure AD B2B ile Power BI'ın tümleştirme sağlar. Contoso Konuk kullanıcılar ya da aracılığıyla ekleyebilmeniz için önce anlatıldığı gibi planlanan veya geçici davetler. Contoso satır düzeyinde güvenlik zorlama isterse, planlanmış davetler zaman ve içeriği paylaşmadan önce güvenlik rollerine atama önüne Konuk kullanıcıları eklemek için kullanılacak önemle tavsiye edilir. Bunun yerine contoso kullanıyorsa, geçici davetler, burada Konuk kullanıcılar tüm verileri görmek mümkün olmayacaktır kısa bir süre olabilir.

> [!NOTE]
> Kullanarak geçici davetler olduğunda RLS tarafından korunan verilere bu gecikme, boş ya da bozuk bir paylaşımı açma bağladığınızda aldıkları e-postada, raporların ve panoların isteyen kullanıcıların göreceği çünkü BT ekibiniz isteklerini desteklemek için neden olabilir. Bu nedenle planlanmış davetler bu scenario.* * içinde kullanmak için önerilir

Bu örnek ile atalım.

Daha önce belirtildiği gibi dünyanın çeşitli yerlerinde tedarikçileri Contoso vardır ve kendi tedarikçi kuruluşlardan kullanıcılar bölgeden yalnızca kendi verilerinden öngörü edinme emin olmak istedikleri.  Ancak, Contoso kullanıcıların tüm verilere erişebilir. Birkaç farklı raporlar oluşturmak yerine Contoso tek bir rapor oluşturur ve filtreler verileri görüntüleyen kullanıcı göre.

![Paylaşılan içeriği](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_27.png)

Contoso kimin bağlanmaya ilişkin verileri filtreleyebilirsiniz emin olmak için Power BI Desktop'ta iki rolü oluşturulur. Bir "Avrupa" Salesterritoryregion alınan tüm veriler, diğeri "Kuzey Amerika" için filtre uygulamak için.

![Rollerini yönetme](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_28.png)

Rolleri raporda tanımlanan her bir kullanıcı için herhangi bir veri erişim elde etmek bunları belirli bir role atanması gerekir. Power BI hizmetinin içinde rol atamasını olur ( **veri kümeleri > Güvenlik** )

![Güvenliği ayarlanıyor](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_29.png)

Contoso'nun BI ekibi iki görmesi burada bir sayfa açılır oluşturdukları rolleri.  Şimdi Contoso'nun BI ekibi rollere kullanıcılar atayabilirsiniz.

![Satır düzeyi güvenlik](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_30.png)

Örnekte Contoso e-posta adresiyle bir iş ortağı kuruluşta bir kullanıcı ekleme "[adam@themeasuredproduct.com](mailto:adam@themeasuredproduct.com)" Avrupa rolü:

![Satır düzeyi güvenlik ayarları](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_31.png)

Bu Azure AD tarafından çözümlenen, Contoso hazır penceresinde görünmesini adı görebilirsiniz:

![Rolleri Göster](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_32.png)

Bu kullanıcı ile paylaşılan uygulamayı açtığında, artık yalnızca Avrupa veri içeren bir rapor görür:

![İçeriği görüntüleme](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_33.png)

### <a name="dynamic-row-level-security"></a>Dinamik satır düzeyi güvenlik

Başka bir ilginç konuyu nasıl dinamik satır düzeyi güvenlik (RLS) iş ile Azure AD B2B görmektir.

Kısacası, dinamik satır düzeyi güvenlik Power bı'a kişinin kullanıcı adı dayalı modeli verileri filtreleyerek çalışır. Kullanıcı grupları için birden çok rol eklemek yerine, kullanıcıların modelde tanımlayın. Biz burada ayrıntılı deseni açıklar olmaz. Sağlayan: Kasper de Jong sunar ayrıntılı bir yazma satır düzeyi güvenlik, tüm özellikleri üzerinde [Power BI Desktop dinamik güvenlik kağıdı](https://www.kasperonbi.com/power-bi-desktop-dynamic-security-cheat-sheet/)hem de [Bu teknik incelemede](https://msdn.microsoft.com/library/jj127437.aspx) .

Küçük bir örneğe göz atalım: Contoso satış gruplarına göre basit bir rapor vardır:

![Örnek içerik](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_34.png)

Bu rapor, bir iç kullanıcıyı iki Konuk kullanıcı ile paylaşılan gerekiyor - iç kullanıcı, her şeyi görebilirsiniz, ancak Konuk kullanıcılar yalnızca grupları görebilir artık erişim sahiptirler. Başka bir deyişle, veriler yalnızca konuk kullanıcılar için filtreleyeceğiz gerekir. Veriler uygun şekilde filtrelemek için teknik incelemeyi ve blog gönderisinde açıklandığı Contoso Dynamic RLS deseni kullanır. Diğer bir deyişle, Contoso kullanıcı adlarını veri için ekler:

![Veri için RLS kullanıcıları görüntüle](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_35.png)

Ardından, Contoso doğru ilişkileri ile uygun şekilde verilere filtre doğru veri modeli oluşturur:

![Uygun veri gösterilir](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_36.png)

Otomatik olarak açan temel alınarak verilere filtre uygulamak için Contoso bağlanan kullanıcı başarılı bir rol oluşturmanız gerekir. Bu durumda, iki rol – Contoso oluşturur "geçerli kullanıcının kullanıcı adıyla oturum açmış Power BI'ın (Bu çalışır bile Azure AD B2B Konuk kullanıcılar için) kullanıcıları tabloyla filtreler securityrole" ilk sunucudur.

![Rolleri yönet](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_37.png)

Contoso "AllRole" başka her şeyi görebilirsiniz iç kullanıcılar için de oluşturur.-Bu rolün tüm güvenlik koşuluna sahip değil.

Hizmette Power BI Masaüstü dosyayı karşıya yükledikten sonra Contoso Konuk kullanıcıları "SecurityRole" ve "AllRole" İç kullanıcılara atayabilirsiniz

Şimdi, Konuk kullanıcılar raporu açtığınızda, bunlar yalnızca görür satış grubu A:

![Yalnızca Grup A](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_38.png)

Sağa Matristeki her ikisini de Konuk kullanıcılar e-posta adresi dönüş USERNAME() ve USERPRINCIPALNAME() işlevin sonucu görebilirsiniz.

Artık tüm verileri görmek iç kullanıcı alır:

![Gösterilen tüm veriler](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_39.png)

Gördüğünüz gibi Dynamic RLS hem iç hem de Konuk kullanıcılar ile çalışır.

> [!NOTE]
> Bu senaryo, bir modeli Azure Analysis Services kullanılırken de çalışır. Genellikle, Azure Analysis Service olarak Power BI aynı Azure AD bağlı - ayrıca Azure AD B2B aracılığıyla davet edilen konuk kullanıcıların bu durumda, Azure Analysis Services bilir.

## <a name="connecting-to-on-premises-data-sources"></a>Şirket içi veri kaynaklarına bağlanma

Power BI gibi şirket içi veri kaynakları üzerinde yararlanmak Contoso olanağını sunar [SQL Server Analysis Services](https://powerbi.microsoft.com/documentation/powerbi-gateway-enterprise-manage-ssas/) veya [SQL Server](https://powerbi.microsoft.com/documentation/powerbi-gateway-kerberos-for-sso-pbi-to-on-premises-data/) doğrudan performanstan için [şirket içi veri ağ geçidi](https://powerbi.microsoft.com/documentation/powerbi-gateway-onprem/). Bu veri kaynaklarına kullanılan Power BI ile aynı kimlik bilgileriyle oturum bile mümkündür.

> [!NOTE]
> Power BI kiracınıza bağlamak için bir ağ geçidi yükleme sırasında bir kullanıcı tarafından oluşturulmuş kiracınızda kullanmanız gerekir. Dış kullanıcılar bir ağ geçidi yükleyin ve kiracınız ile bağlayın. _

Dış kullanıcılar için bu dış kullanıcıları genellikle şirket içi bilinmemesi daha karmaşık olabilir AD. Power BI sunar geçici bir çözüm bu bölümünde anlatıldığı gibi dış kullanıcı adları için iç kullanıcı adlarını eşlemek Contoso yöneticilerin vererek [yönetme - Analysis Services veri kaynağı](https://powerbi.microsoft.com/documentation/powerbi-gateway-enterprise-manage-ssas/). Örneğin, [ lucy@supplier1.com ](mailto:lucy@supplier1.com) eşlenebilir [lucy\_supplier1\_com #EXT@contoso.com](mailto:lucy_supplier1_com).

![Kullanıcı adlarını eşleme](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_40.png)

Bu yöntem, yalnızca birkaç kullanıcı ya da Contoso, tüm dış kullanıcıların tek bir iç hesabına eşlemek, Contoso varsa uygundur. Daha karmaşık senaryolarda, her bir kullanıcı kendi kimlik bilgilerini gereken yere kullanan daha gelişmiş bir yaklaşım yoktur [özel AD öznitelikleri](https://technet.microsoft.com/library/cc961737.aspx) açıklandığı eşleme yapmak için [veri kaynağınızı - Analysis Servicesyönetme](https://powerbi.microsoft.com/documentation/powerbi-gateway-enterprise-manage-ssas/). Bu, Azure AD'de (Ayrıca Dış B2B kullanıcıları) her kullanıcı için bir eşleme tanımlamak Contoso yönetici çalıştırmasına olanak tanır.  Bu öznitelikleri, Contoso davet veya zamanlanmış temposu eşleme tamamen otomatik hale getirebilirsiniz betikleri veya kodları kullanarak AD nesne modeli aracılığıyla ayarlanabilir.

## <a name="enabling-external-users-to-edit-and-manage-content-within-power-bi"></a>Düzen ve içeriği Power bı'da yönetmek dış kullanıcıları etkinleştirme

Contoso, daha önce kuruluşlar arası düzenleme ve Power BI içerik bölümünün Yönetim bölümünde açıklandığı gibi kuruluş içindeki içeriği katkıda bulunmak dış kullanıcılar izin verebilirsiniz.

> [!NOTE]
> Düzenleme ve yönetme, kuruluşunuzun Power bı'daki içerikleri için kullanıcı Power BI Pro lisansı çalışma Alanım dışındaki bir çalışma alanında olmalıdır. Kullanıcılar the_ içinde anlatıldığı gibi Pro lisansları elde edebilirsiniz _Licensing__section bu belgenin._

Power BI Yönetici portalı sağlar **düzenlemek ve yönetmek dış konuk kullanıcılara kuruluştaki içerik izin** Kiracı ayarlarında ayarlama. Varsayılan olarak devre dışı, dış kullanıcılar varsayılan olarak kısıtlanmış bir salt okunur deneyimi elde anlamı ayarı ayarlanır. Ayar, Konuk için Azure AD'de ayarladığı UserType ile kullanıcılar için geçerlidir. Aşağıdaki tabloda, kullanıcılar kendi UserType ve ayarların nasıl yapılandırıldığına bağlı olarak deneyimi davranışları açıklanmaktadır.

| **Azure AD'de kullanıcı türü** | **Düzenle ve içerik ayarlarını yönetmek dış konuk kullanıcılara izin ver** | **Davranışı** |
| --- | --- | --- |
| Konuk | Devre dışı bırakıldı kullanıcının (varsayılan) | Öğe tüketim yalnızca görüntüleyin. Raporlar, panolar ve Konuk kullanıcı için gönderilen URL'yi görüntülendiğinde uygulamaları salt okunur erişim sağlar. Power BI mobil uygulamaları, Konuk kullanıcıya salt okunur bir görünüm sağlar. |
| Konuk | Kullanıcı için etkin | Bazı özellikler kullanılamaz ancak dış kullanıcı Power BI deneyimi tam erişim onlara alır. Dış kullanıcı Power bı'a Power BI hizmeti URL'si dahil Kiracı bilgileri kullanarak oturum açmalısınız. Giriş deneyimi, bir çalışma Alanım ve izinlere göre göz atabilir, kullanıcı alır, görüntüleyin ve içerik oluşturun. </br></br> Power BI mobil uygulamaları, Konuk kullanıcıya salt okunur bir görünüm sağlar. |

> [!NOTE]
> Dış kullanıcılar Azure AD'de de UserType üyesine ayarlayabilirsiniz. Bu Power BI'da şu anda desteklenmiyor.

Power BI Yönetici portalı'nda, ayar aşağıdaki resimde gösterilmektedir.

![Yönetici ayarları](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_41.png)

Konuk kullanıcıları salt okunur bir varsayılan deneyim ve, Düzen ve içeriği yönetme alın. Varsayılan, tüm Konuk kullanıcılar salt okunur deneyime sahiptir yani devre dışıdır. Power BI yönetici ya da Azure AD'de tanımlanan belirli güvenlik grupları veya kuruluştaki tüm Konuk kullanıcılar için ayarını etkinleştirebilirsiniz. Aşağıdaki görüntüde, Contoso Power BI yönetici hangi dış kullanıcılar düzenleyip Contoso kiracısındaki içeriği yönetme yönetmek için Azure AD'de bir güvenlik grubu oluşturulur.

Power BI'da oturum açmak için bu kullanıcılara yardımcı olmak için bunları ile Kiracı URL'si sağlayın. Kiracı URL'sini bulmak için şu adımları izleyin.

1. Power BI hizmetinde üst menü Yardım'ı seçin ( **?** ) sonra **Power BI hakkında**.
2. Değeri bakmak **Kiracı URL'si**. Bu, Konuk Kullanıcılarınızla paylaşabilirsiniz Kiracı URL'dir.

    ![Kiracı URL'si](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_42.png)

İzin dış konuk kullanıcılara düzenlemek ve kuruluştaki içeriğini yönetmek için kullanırken, belirtilen Konuk kullanıcılar, kuruluşunuzun Power BI erişin ve iznine sahip oldukları herhangi bir içerik bakın. Bunlar giriş erişmek, göz atın ve çalışma alanı içeriğine katkıda bulunmak, nerede bunlar erişim listesini ve yüklü uygulamaları yüklemek bir çalışma Alanım. Yeni çalışma alanı deneyiminin kullanıldığı çalışma alanları oluşturabilir ve bu çalışma alanlarının Yöneticisi olabilir.

> [!NOTE]
> Bu seçeneği kullanarak yaptığınızda varsayılan Azure AD ayarları, azaltılmış experience.* * için yol açabilecek kişiler seçiciler gibi belirli özellikleri kullanmak için konuk kullanıcıları engellemek olduğundan bu belgenin idare bölümünü gözden geçirdiğinizden emin

Düzenle ve kuruluş Kiracı ayarı içeriği yönetmek için izin dış konuk kullanıcılara aracılığıyla etkinleştirilen Konuk kullanıcılar için bazı deneyimleri için kullanılabilir değildir. Güncelleştirmek veya raporları yayımlamak için Power BI hizmeti web kullanıcı Arabirimi, Power BI Desktop dosyaları karşıya yüklemek için Veri Al dahil olmak üzere kullanmak konuk kullanıcılara gerekir. Aşağıdaki deneyimler desteklenmez:

- Power BI Desktop'tan Power BI hizmetine doğrudan yayımlama
- Konuk kullanıcılar Power BI hizmetindeki hizmet veri kümelerine bağlanmak için Power BI Desktop kullanamaz
- Office 365 Gruplarına bağlanan klasik çalışma alanları: Konuk kullanıcılar bu çalışma alanlarını oluşturamaz ve bunların Yöneticisi olamaz. Bunlara üye olabilirler.
- Çalışma alanı erişim listeleri için geçici davet gönderme desteklenmez
- Konuk kullanıcılarda Excel için Power BI Publisher desteklenmez
- Konuk kullanıcılar Power BI Gateway yükleyemez ve bunu kuruluşunuza bağlayamaz
- Konuk kullanıcılar kuruluşun tamamına yayımlayan uygulamalar yükleyemez
- Konuk kullanıcılar kurumsal içerik paketlerini kullanamaz, oluşturamaz, güncelleştiremez veya yükleyemez
- Konuk kullanıcılar Excel'de Çözümle özelliğini kullanamaz
- Konuk kullanıcılar olamaz @mentioned yorum içinde (Bu işlev, gelecek bir sürümde de eklenir)
- Konuk kullanıcılar (Bu işlev, gelecek sürümlerden birinde eklenecektir) abonelikleri kullanamaz
- Bu özelliği kullanan konuk kullanıcıların iş veya okul hesabı olmalıdır. Kişisel hesapları kullanan Konuk kullanıcılar oturum açma kısıtlamaları nedeniyle diğer kısıtlamalar karşılaşırsınız.



## <a name="governance"></a>İdare

### <a name="additional-azure-ad-settings-that-affect-experiences-in-power-bi-related-to-azure-ad-b2b"></a>Azure AD B2B için Power BI deneyimlerin etkileyen diğer Azure AD ayarları ilgili

Azure AD B2B paylaşımı kullanırken, Azure Active Directory Yöneticisi yönlerini dış kullanıcı deneyimini denetler. Bu, dış işbirliği Ayarları sayfasında Kiracınız için Azure Active Directory ayarları içinde denetlenir.

Ayrıntı ayarları şuradan ulaşılabilir:

[https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)

> [!NOTE]
> Varsayılan olarak, konuk kullanıcıların izinleri sınırlıdır seçeneği Evet olarak ayarlandığında, konuk kullanıcıların Power bı'da deneyimleri özellikle sınırlı şekilde burada Kişi Seçici kullanıcı arabirimleri çalışmaz söz konusu kullanıcılar için paylaşımı çevreleyen. Hayır olarak ayarlamak için Azure AD yöneticinizin ile iyi experience.* * emin olmak için aşağıda gösterildiği gibi çalışma yürütmeniz önemlidir

![Dış işbirliği ayarları](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_43.png)


### <a name="control-guest-invites"></a>Denetim Konuk davetler

Power BI yöneticileri, dış yalnızca Power BI için Power BI Yönetici portalı ziyaret ederek paylaşım kontrol edebilirsiniz. Ancak, Kiracı yöneticileri, dış paylaşım çeşitli Azure AD'ye ilkeleriyle de denetleyebilirsiniz.  Bu ilkeler, Kiracı yöneticilerine izin ver

- Son kullanıcılar tarafından davetler devre dışı bırakma
- Yalnızca Yöneticiler ve Konuk davet eden rolündeki kullanıcılar davet edebilir
- Yöneticiler, Konuk davet eden rolü ve üyeler davet edebilir
- Konuklar, dahil olmak üzere tüm kullanıcıları davet edebilir

Daha fazla bilgi bu ilkeleri hakkında [temsilci davetleri Azure Active Directory B2B işbirliği](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-delegate-invitations).

Tüm Power BI harici kullanıcılar tarafından ayrıca eylemlerdir [denetim portalımıza denetlenen](https://powerbi.microsoft.com/documentation/powerbi-admin-auditing/).

### <a name="conditional-access-policies-for-guest-users"></a>Konuk kullanıcılar için koşullu erişim ilkeleri

Contoso Konuk kullanıcılar Contoso kiracıdan içeriğe erişmek için koşullu erişim ilkeleri zorunlu kılabilir. Ayrıntılı yönergeleri bulabilirsiniz [B2B işbirliği kullanıcıları için koşullu erişim](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-mfa-instructions).

## <a name="common-alternative-approaches"></a>Ortak yaklaşımlar

Azure AD B2B kuruluşlar arasında verileri ve raporları paylaşma kolaylaştırır, ancak belirli durumlarda üstün olabilir ve yaygın olarak kullanılan diğer birçok yaklaşım vardır.

### <a name="alternative-option-1-create-duplicate-identities-for-partner-users"></a>Alternatif seçenek 1: Kullanıcılar iş ortağı için yinelenen kimlikler oluşturun

Bu seçenek belirtilmişse, Contoso her bir iş ortağı kullanıcı için yinelenen kimliklerin Contoso Kiracıda el ile oluşturmak aşağıdaki görüntüde gösterildiği gibi vardı. Ardından Power BI'da Contoso atanan kimlikleri uygun raporları, panoları veya uygulamaları paylaşabilir.

![Uygun eşlemeleri ve adları ayarlama](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_44.png)

Bu alternatif nedenleri:

- Kullanıcının kimlik, kuruluşunuz tarafından denetlenir olduğundan, hizmet e-posta, SharePoint gibi ilgili, vb. kuruluşunuzun içindeki denetim de bulunur. BT yöneticilerinize parolalarını sıfırlamasına, hesaplara erişimi devre dışı bırakın veya hizmetlerin etkinliklerini denetleme.
- İşletmelerini genellikle kısıtlanır için belirli hizmetlere erişimi kişisel hesapları kullanan kullanıcılar, bu nedenle bir kuruluş hesabı gerekebilir.
- Bazı hizmetler, yalnızca kuruluşunuzdaki kullanıcılar üzerinde çalışır. Örneğin, Azure B2B kullanarak dış kullanıcıların kişisel/mobil cihazlarda içerik yönetmek için Intune kullanmak mümkün olmayabilir.

Bu alternatif seçin değil nedenleri:

- İş ortağı kuruluşlardan iki Contoso içeriğe erişmek için kendi kuruluşları ve diğer içeriğe erişmek için kimlik bilgilerini – birini hatırlamanız gerekir. Bu Konuk kullanıcılar için bir kolayca budur ve çok sayıda Konuk kullanıcı tarafından bu deneyim karıştırılabilecek.
- Contoso, satın alın ve bu kullanıcılar için kullanıcı başına lisans atayın. Bir kullanıcının e-posta veya office uygulamalarını kullanmaktadır erişmesi gerekiyorsa, bunlar düzenleme ve Power bı'da içerik paylaşmak için Power BI Pro dahil olmak üzere uygun Lisansınızın olması gerekir.
- Contoso daha katı bir yetkilendirme ve iç kullanıcılara kıyasla dış kullanıcılar için idare ilkelerini zorunlu kılmak isteyebilirsiniz. Bunu başarmak için Contoso dış kullanıcılar için şirket içi bir adlandırma oluşturmak için gerek duyduğu ve tüm Contoso kullanıcıları bu terminolojisi hakkında eğitilmesi gerekir.
- Kullanıcı kuruluşu ayrıldığında, kullanıcının Contoso yönetici hesabını elle silene kadar Contoso'nun kaynaklara erişimi devam
- Contoso yöneticileri oluşturma, parola sıfırlama, vb. dahil olmak üzere konuk için Kimlik Yönetimi gerekir.

### <a name="alternative-option-2-create-a-custom-power-bi-embedded-application-using-custom-authentication"></a>Alternatif seçenek 2: Özel kimlik doğrulama kullanarak özel bir Power BI Embedded uygulaması oluşturun

Özel kimlik doğrulama ile kendi özel ekli Power BI uygulaması oluşturmak için Contoso için başka bir seçenek olduğunu (['Uygulama, verilerin sahibi'](https://docs.microsoft.com/power-bi/developer/embed-sample-for-customers)). Çoğu kuruluş saat veya dış iş ortakları için içerik Power BI'ı dağıtmak için özel bir uygulama oluşturmak için kaynak değil olsa da, bazı kuruluşlar için bu en iyi yaklaşımdır ve ciddi değerlendirilmesi.

Genellikle, kuruluşların, tüm kurumsal kaynaklara erişimi iş ortakları için tek bir merkezden yönetin., iç kurumsal kaynaklardan yalıtımı sağlar ve iş ortaklarının çoğu desteklemek üzere iş ortakları için kolaylaştırılmış deneyimleri sağlayan var olan iş ortağı portalı vardır ve bireysel kullanıcıları.

![Birçok iş ortağı portalı](media/whitepaper-azure-b2b-power-bi/whitepaper-azure-b2b-power-bi_45.png)

Her tedarikçi oturum açma kullanıcılardan Contoso'nun iş ortağı portalı için yukarıdaki örnekte, AAD kimlik sağlayıcısı olarak kullanır. AAD B2B, Azure B2C, yerel kimlikler kullanın veya diğer kimlik sağlayıcılardan herhangi bir sayıda ile federasyona. Kullanıcı oturum açın ve Azure Web uygulaması veya benzer bir altyapı kullanarak bir iş ortağı portalı derleme erişim.

Web App'ta, Power BI raporlarını Power BI Embedded dağıtımdan katıştırılır. Web uygulaması, raporları ve ilgili hizmetlerin Contoso ile etkileşim kurmak için Web kolaylaştırmak için amaçlayan cohesive bir deneyime erişim kolaylaştırın. Portal bu ortam Contoso iç AAD'den diğerlerinden ayrılır ve tedarikçileri emin olmak için Contoso'nun iç Power BI ortamına kaynaklarla erişilemedi. Genellikle veri de veri yalıtımı sağlamak üzere bir ayrı iş ortağı veri ambarında depolanır. Kuruluşunuzun verilerini doğrudan erişim sınırlama hangi verilerin büyük olasılıkla dış kullanıcı tarafından kullanılabilir olabilir ve yanlışlıkla paylaşılmasını dış kullanıcılarla sınırlama dış kullanıcılarla sayısını sınırlayan olduğundan bu yalıtım avantajları vardır.

Power BI Embedded kullanarak portal avantajlı lisanslama yararlanabilir, son kullanıcılara lisans atama hakkında endişeleriniz basitleştirir ve ölçeği artırabilirsiniz Azure modelinde satın/aşağı tabanlı uygulama belirteci veya ana kullanıcı artı premium kapasite kullanılarak açık bekleniyor Kullanım. Tüm bir iş ortağının gereksinimleriniz düşünülerek tasarlanan tek bir portal iş ortaklarına erişin beri portal bir genel daha yüksek kalitede ve tutarlı bir deneyim sunabilir. Power BI Embedded tabanlı çözümler genellikle çok kiracılı olacak şekilde tasarlanmıştır olduğundan, son olarak, bu iş ortağı kuruluşlar arasında yalıtım sağlamak kolaylaştırır.

Bu alternatif nedenleri:

- İş ortağı kuruluşların sayısı arttıkça daha kolay büyür. İş ortakları, Contoso'nun iç AAD dizinden yalıtılmış ayrı bir dizine eklenir, yönetim görevlerini basitleştirir ve dış kullanıcılar iç verilerinin yanlışlıkla paylaşılmasını önlemeye yardımcı olur.
- Tipik iş ortağı portalı yüksek düzeyde iş ortakları arasında tutarlı deneyimler deneyimlerle markalı ve tipik iş ortaklarının ihtiyaçlarını karşılamak için kolaylaştırılmıştır. Contoso bu nedenle daha yeni olan bütün bir deneyim iş ortakları için gerekli tüm hizmetleri tek bir portal tümleştirerek sunabilir.
- Lisans maliyetlerini düzenleme içeriği Power BI Embedded, Azure tarafından kapsanan gibi Gelişmiş senaryolar için Power BI Premium'u satın aldıysam ve bu kullanıcılar için Power BI Pro lisansları atama gerektirmez.
- Çok kiracılı bir çözüm desteklemesi için iş ortakları arasında daha iyi yalıtım sağlar.
- İş ortağı portalı genellikle Power BI raporları, panolar ve uygulamalar dışında iş ortağı için diğer araçlar içerir.

Bu alternatif seçin değil nedenleri:

- Önemli miktarda çaba oluşturmak, çalıştırmak ve kaynaklar ve zaman içinde önemli bir yatırım yaparak portalı korumak için gereklidir.
- Çözüm için dikkatli planlama beri B2B paylaşım kullanmaktan çok daha uzun zamandır ve birden çok iş akışları arasında yürütme gereklidir.
- İş ortaklarının daha küçük bir sayı olduğunda bu alternatif için gereken çabayı büyük olasılıkla çok yaslamak için yüksek.
- Geçici paylaşım, işbirliği, kuruluşunuz tarafından karşılaşılan birincil senaryodur.
- Raporlar ve panolar için her bir iş ortağı farklıdır. Bu seçenek yalnızca doğrudan iş ortaklarıyla paylaşımı ötesinde ek yükü yönetim sunar.



## <a name="faq"></a>SSS

**Böylece kullanıcı "hemen kullanıma hazır" Contoso otomatik olarak kullanıldıktan, davetiye gönderebilir miyim? Veya kullanıcı her zaman tıklatarak alma URL'sine sahip?**

Kullanıcıların içeriğe erişebilmesi için önce son kullanıcı onayı deneyimi her zaman tıklamanız gerekir.

Çok sayıda Konuk kullanıcı davet, bu, çekirdek Azure AD yöneticileri tarafından gelen devretmenizi öneririz [kaynak kuruluşta Konuk davet edici rolüne kullanıcı ekleme](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-add-guest-to-role). Oturum açma kullanıcı arabirimini, PowerShell betiklerini kullanarak iş ortağı kuruluştaki diğer kullanıcılar bu kullanıcı davet edebilir veya API'leri. Bu, Azure AD yöneticilerinizin davet veya iş ortağı kuruluşta kullanıcılara davetler yeniden üzerinde yönetim yükünü azaltır.

**İş ortakları, çok faktörlü kimlik doğrulaması yoksa, Contoso Konuk kullanıcılar için çok faktörlü kimlik doğrulamasını zorlayabilir miyim?**

Evet. Daha fazla bilgi için [B2B işbirliği kullanıcıları için koşullu erişim](https://docs.microsoft.com/azure/active-directory/active-directory-b2b-mfa-instructions).

**Davet edilen iş ortağı kendi şirket içi kimlik doğrulaması eklemek için Federasyon kullanırken, B2B işbirliği nasıl çalışır?**

İş ortağı için şirket içi kimlik altyapınızı federe bir Azure AD kiracınız varsa, şirket içi çoklu oturum açma (SSO) otomatik olarak sağlanır. İş ortağı, Azure AD kiracısı yoksa, yeni kullanıcılar için bir Azure AD hesabı oluşturulabilir.

**Tüketici e-posta hesaplarına sahip Konuk kullanıcılar davet et?**

Tüketici e-posta hesaplarına sahip Konuk kullanıcıları davet Power BI'da desteklenir. Bu, hotmail.com, outlook.com ve gmail.com gibi etki alanlarını içerir. Ancak bu kullanıcıların hangi kullanıcılarla iş ötesinde sınırlamaları karşılaşabilirsiniz ya da Okul hesapları karşılaştığınız.
