---
title: Power BI görselleri hakkında sık sorulan sorular
description: Power BI görselleri hakkında sık sorulan sorular ve cevaplar listesini inceleyin
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.topic: conceptual
ms.subservice: powerbi-custom-visuals
ms.custom: ''
ms.date: 12/17/2018
ms.openlocfilehash: 0b5677e7f3acab464f8d9e4c293ed1df9d0bdd0f
ms.sourcegitcommit: 08b73af260ded51daaa6749338cb85db2eab587f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2019
ms.locfileid: "74102169"
---
# <a name="frequently-asked-questions-about-power-bi-visuals"></a>Power BI görselleri hakkında sık sorulan sorular

## <a name="organizational-visuals"></a>Kuruluş görselleri

Yönetici portalı, kuruluşunuz için bir Power BI görsellerini yönetmenize olanak sağlar.

### <a name="how-can-the-admin-manage-the-organizational-power-bi-visuals"></a>Yöneticiler, Power BI kuruluş görsellerini nasıl yönetebilir?

Yöneticiler, Yönetim portalının "Kuruluş görselleri" sekmesinden [kuruluştaki tüm Power BI kuruluş görsellerini görebilir ve şu yönetim işlemlerini gerçekleştirebilir](../service-admin-portal.md#organizational-visuals): ekleme, devre dışı bırakma, etkinleştirme ve silme.
Artık bu görselleri e-posta veya paylaşılan klasörle paylaşmaya gerek yoktur! Görseller kuruluş deposuna dağıtıldıktan sonra kuruluştaki kullanıcılar bunları kolayca bulabilir ve kuruluş görsellerini doğrudan Power BI Desktop’tan veya Power BI hizmetinden raporlarına aktarabilir. Kuruluş görsellerine *KURULUŞUM* sekmesindeki yerleşik depodan (Desktop ve hizmet) erişebilirsiniz. Yönetici özel bir görselin yeni sürümünü yüklediğinde kuruluştaki tüm kullanıcılar aynı güncel sürüme sahip olur. Rapor yazarlarının raporlardaki görselleri silerek yeni sürümünü eklemesine gerek yoktur. Bu görselin kullanıldığı tüm raporlar otomatik olarak güncelleştirilir! Market görsellerinin güncelleştirme mekanizması da benzerdir.

### <a name="if-an-admin-uploads-a-custom-visual-from-the-public-marketplace-to-the-organization-store-is-it-automatically-updated-once-a-vendor-updates-the-visual-in-the-public-marketplace"></a>Yöneticinin genel marketten kuruluş deposuna yüklediği özel görsellerde satıcı tarafından yapılan güncelleştirmeler otomatik olarak uygulanır mı?

Hayır, genel marketten otomatik güncelleştirme yapılmaz.
Kuruluş görsellerinin sürümünü güncelleştirmek Yöneticinin sorumluluğundadır.

### <a name="is-there-a-way-to-disable-the-organizational-store"></a>Kuruluş deposunu devre dışı bırakmak mümkün mü?

Hayır, kullanıcılar Power BI Desktop uygulamasında ve hizmetinde her zaman "KURULUŞUM" sekmesini görür. Yönetici, yönetim portalından tüm kuruluş görsellerini devre dışı bırakabilir veya silebilir. Bu durumda kuruluş deposu boş olacaktır.
  
### <a name="if-the-administrator-disables-power-bi-visuals-from-the-admin-portal-tenant-settings-do-users-still-have-access-to-the-organizational-visuals"></a>Yönetici, Power BI görsellerini Yönetim portalından (Kiracı ayarları) devre dışı bıraktığında kullanıcılar kuruluş görsellerine erişmeye devam edebilir mi?

Evet, yöneticinin Power BI görsellerini yönetim portalından devre dışı bırakması kuruluş deposunu etkilemez. Bazı kuruluşlar Power BI görsellerini devre dışı bırakıp yalnızca Power BI yöneticisi tarafından kuruluş deposuna aktarılan ve yüklenen seçili görsellerin kullanılmasını etkinleştirmektedir. Power BI görsellerinin Yönetim portalından devre dışı bırakılması Power BI Desktop uygulamasını etkilemez. Power BI Desktop kullanıcıları genel marketteki Power BI görsellerini ekleyip raporlarında kullanabilir. Ancak rapor Power BI hizmetinde yayımlandıktan sonra bu ortak Power BI görselleri işlenmez ve bu durumu bildiren bir hata iletisi görüntülenir. Power BI hizmetini kullanırken genel marketteki Power BI görsellerini içeri aktaramazsınız. Yönetim portalındaki Power BI görselleri ayarı Power BI hizmetine uygulandığından yalnızca kuruluş deposundaki görselleri içeri aktarabilirsiniz.

### <a name="why-does-the-organizational-store-and-organizational-visuals-make-a-great-enterprise-solution"></a>Kuruluş deposunun ve kuruluş görsellerinin kurumsal bir çözüm oluşturma açısından sağladığı avantajlar nelerdir?

* Herkes Power BI yöneticisi tarafından denetlenen aynı görsel sürümüne sahip olur. Yönetici, görsel sürümünü yönetim portalından güncelleştirdiğinde kuruluştaki tüm kullanıcılar otomatik olarak güncel sürümü alır.

* Görsel dosyalarını e-posta veya paylaşılan klasörlerle paylaşmanıza gerek kalmaz! Özel görseller, oturum açmış olan tüm kullanıcıların görüntüleyebileceği tek bir yerde depolanır.

* Kuruluş görsellerinin yeni sürümleri market görselleri gibi tüm raporlarda otomatik olarak güncelleştirilerek güvenlik ve desteklenebilirlik sağlar.

* Kuruluş içindeki, kuruluş görseli kullanan çalışanların ilgili kuruluş görsellerini görmek ve kullanmak için oturum açmış olması gerekir. Bu da kuruluş için ek bir güvenlik katmanı sağlar.

* Yöneticiler, kuruluşta kullanılabilecek olan Power BI görsellerini denetleyebilir.

* Yöneticiler, yönetim portalını kullanarak görselleri test amaçlı olarak etkinleştirebilir/devre dışı bırakabilir. Bu görsellere erişme izni yalnızca kuruluş üyelerine verileceğinden daha güvenli bir erişim sağlanmış olur.

## <a name="certified-power-bi-visuals"></a>Sertifikalı Power BI görselleri

### <a name="what-are-certified-power-bi-visuals"></a>Sertifikalı Power BI görselleri nelerdir?

Sertifikalı Power BI görselleri, [markette](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals) bulunan ve Power BI ekibi tarafından oluşturulmuş [belirli](power-bi-custom-visuals-certified.md) kod gereksinimlerini karşılayan ve belirli testlerden geçmiş olan görsellerdir.  Gerçekleştirilen testler, görselin dış hizmetlere veya kaynaklara erişmediğini denetleyecek şekilde tasarlanmıştır. Ancak, Microsoft üçüncü taraf Power BI görsellerinin yazarı değildir ve müşterilere bu tür bir görselin işlevselliğini doğrulamak için doğrudan yazarına başvurmasını öneririz.

### <a name="what-tests-are-done-during-the-certification-process"></a>Sertifikasyon işlemi sırasında hangi testler yapılır?

Sertifikasyon işlemi testlerinden bazıları şunlardır: Kod incelemeleri, statik kod analizi, veri sızıntısı, rastlantısal veri testi, sızma testi, XSS erişimi testi, kötü amaçlı veri ekleme, giriş doğrulama ve işlevsel test.
 
### <a name="do-you-certify-visuals-every-submission"></a>Gönderilen her görseli sertifikalandırıyor musunuz?

Evet. Sertifikalı görselin yeni bir sürümü Market’e her gönderildiğinde, görselin sürüm güncelleştirmesi de aynı sertifika denetimlerinden geçer.

Geliştiriciler için not: Sertifikalı görsele yönelik bir sürüm güncelleştirilmesi gönderiyorsanız [ilk sertifikasyon isteği](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified#process-for-submitting-a-custom-visual-for-certification) olarak ayrı bir e-posta göndermeniz gerekmez. Sürüm güncelleştirmesinin sertifikasyonu otomatik olarak gerçekleşir ve reddedilmesine neden olan ihlaller için nelerin düzeltilmesi gerektiğini açıklayan bir e-posta gönderilir. 

### <a name="is-it-possible-that-a-certified-visual-stops-being-certified-with-a-new-update"></a>Sertifikalı bir görselin yeni bir güncelleştirme ile sertifikalı olmayı bırakması mümkün müdür?

Hayır, bu mümkün değildir. Sertifikalı bir görsel yeni bir güncelleştirme ile sertifikasız hale gelmez. Güncelleştirme reddedilir.
 
### <a name="do-i-need-to-share-my-code-in-public-repository-if-i-am-submitting-to-the-certification-process"></a>Sertifikasyon işlemine gönderiyorsam, kodumu ortak depoda paylaşmam gerekiyor mu?

Hayır, kodunuzu herkese açık şekilde paylaşmanıza gerek yoktur. Ancak, görselin kodunu denetlememiz için bize okuma izinleri vermeniz gerekir. Örn. GitHub’daki özel depo.
 
### <a name="do-we-have-to-publishhttpsdocsmicrosoftcompower-bideveloperoffice-store-the-visual-in-the-marketplacehttpsappsourcemicrosoftcommarketplaceappspage1productpower-bi-visuals-to-certify-it"></a>Sertifikalanması için görseli [Market](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals)’te [yayımlamamız](https://docs.microsoft.com/power-bi/developer/office-store) gerekiyor mu?

Evet. Görselin ilk olarak Market’te yayımlanması, sertifikasyon işlemi için zorunlu bir gereksinimdir.
Özel bir görselin sertifikalanması için sunucularımızda bulunması gerekir. Özel görselleri sertifikalandıramayız.
 
### <a name="how-long-does-it-take-to-certify-my-visual"></a>Görselimin sertifikalanması ne kadar sürer?

Güncelleştirilmiş sürüm için 3 haftaya kadar sürebilir. Yeni bir gönderim için (ilk sertifikasyon) 4 haftaya kadar sürebilir. 

### <a name="does-the-certification-process-ensure-that-no-data-leakage-occurs"></a>Sertifikasyon işlemi, veri sızıntısı yaşanmasını önler mi?

Gerçekleştirilen testler, görselin dış hizmetlere veya kaynaklara erişmediğini denetleyecek şekilde tasarlanmıştır. Ancak, Microsoft üçüncü taraf Power BI görsellerinin yazarı değildir ve müşterilere bu tür bir görselin işlevselliğini doğrulamak için doğrudan yazarına başvurmasını öneririz.
 
### <a name="are-uncertified-power-bi-visuals-safe-to-use"></a>Sertifikalı olmayan Power BI görsellerini kullanmak güvenli midir?

Sertifikalı olmayan Power BI görsellerinin, güvenli olmayan görseller olması şart değildir.
Bazı görseller sertifikalanmamıştır çünkü [sertifikasyon gereksinimlerinin](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified?#certification-requirements) biriyle veya birden çoğuyla uyumlu değildir. Örneğin, harita görselleri gibi dış hizmetlere bağlanan veya ticari kitaplıkları kullanan görseller böyledir.
 
## <a name="visuals-with-additional-purchases"></a>Ek satın almaları olan görseller

### <a name="what-is-a-visual-with-additional-purchases"></a>Ek satın almaları olan görsel nedir?

Ek satın almaları olan görsel, marketteki uygulama içi satın alma (IAP) eklentisine benzer. Bu eklentilerin **Ek satın alma işlemleri gerekebilir** şeklinde bir fiyat etiketi vardır.

IAP Power BI görselleri ücretsiz, indirilebilir Power BI görselleridir. Kullanıcılar bu Power BI görsellerini marketten indirirken hiçbir ödeme yapmaz. IAP görselleri gelişmiş özellikler için isteğe bağlı uygulama içi satın almalar sunar.  

### <a name="whats-the-benefit-to-developers"></a>Geliştiriciler açısından avantajı nedir?

AppSource’ta IAP Power BI görselleri birçok günlük ziyaretçi tarafından bulunabilecek, trafikte değerli bir artış sağlayacak, IAP Power BI görsellerinizin ve bir geliştirici olarak sizin bilinirliğinizi artıracaktır.

Söz konusu görselleri kısa süre öncesine kadar web siteniz üzerinden yönettiyseniz, şimdi bunları AppSource'a gönderebilirsiniz. Bunu yapmanız Power BI topluluğu içinde IAP görsellerinin bulunabilirlik ve görünürlük düzeyini artıracaktır.

AppSource'taki görseller, mağazadaki inceleme ve değerlendirme sistemi aracılığıyla IAP özel görselini kullanan müşterilerinizin Doğrudan geri bildirim kanalından yararlanır.  

IAP görseli AppSource doğrulama takımı tarafından onaylandıktan sonra, söz konusu görseli sertifikalanması için de gönderebilirsiniz. Bu isteğe bağlı bir işlemdir.  

Sertifikalanan IAP Power BI görselleri PowerPoint’e aktarılabilir ve kullanıcı rapor sayfalarına abone olduğunda alınan e-postalarda görüntülenebilir. Dolayısıyla artık IAP görsellerini markete göndererek IAP Power BI görsellerinin sertifikalanması ve ek özellik kümesini desteklemesi sağlanabilir.  

### <a name="do-iap-visuals-need-to-be-certified"></a>IAP görsellerinin sertifikalanması gerekli mi?

Sertifikasyon işlemi isteğe bağlıdır. Ücretsiz görsellerde olduğu gibi, IAP Power BI görsellerini sertifikalama konusundaki karar da geliştiriciye aittir.

### <a name="what-is-changing-in-the-submission-process"></a>Gönderim işleminde neler değişti?

IAP Power BI görsellerini markete gönderim işlemi, ücretsiz görselleri gönderim işlemiyle aynıdır. Satıcı panosu aracılığıyla yapılır.  Gönderim işlemindeki tek değişiklik, geliştiricilerin satıcı panosundaki geliştirici notlarında şunu belirtmesinin gerekli olmasıdır: “Uygulama içi satın alması olan görsel”. Ücretli/gelişmiş özellikleri doğrulamak için gerekliyse bir lisans anahtarı/belirteci sağlamanız da istenecektir.  

Satıcı panosunda yeni seçenek olmayacaktır. *Uygulama içi satın almalar içeren ücretsiz uygulama* olduğunda IAP görsellerinizi *ücretsiz* olarak göndermeniz gerekecektir.

Bunun yanı sıra, mağazanızda hangi özelliklerin ücretsiz olduğu ve hangilerinin çalışması için ek satın almalar gerektirdiği konusunda ayrıntılı bir açıklama sağlayarak kullanıcılara neler bekleyebileceklerini bildirin.  

### <a name="what-should-i-do-beforesubmittingmy-iap-custom-visual"></a>IAP özel görselimi göndermeden önce ne yapmalıyım?

Bir özel IAP görseli üzerinde çalışıyorsanız veya zaten böyle bir görseliniz varsa bunun yönergelere uygun olduğundan emin olun.  

Özel görsel üzerinde bir logo varsa bunun logo yönergelerine (renk, konum, boyut ve eylem tetikleme) uygun olduğundan emin olun.

Ayrıca yönergelerde en iyi yöntemler hakkında notlar da bulabilirsiniz.  
> [!Note]
> Tüm ücretsiz görseller daha önce sunulan ücretsiz özellikleri korumalıdır. Eski ücretsiz özelliklerin üzerine isteğe bağlı olarak gelişmiş ücretli özellikler ekleyebilirsiniz. Eski ücretsiz görselleri güncelleştirmek yerine, gelişmiş özellikler içeren IAP görsellerini yeni görseller olarak göndermenizi öneririz.

### <a name="can-i-get-my-iap-custom-visual-certified"></a>IAP özel görselimin sertifikalı olmasını sağlayabilir miyim?

Evet, ücretsiz görsellerle aynı şekilde.  IAP özel görseliniz AppSource takımı tarafından onaylandıktan sonra, görselinizi sertifikasyon işlemi için gönderebilirsiniz.

Görselinizin sertifikalı olması için sertifikasyon gereksinimlerini karşılaması gerekir. Örneğin, görsel lisans doğrulaması için dış hizmetlere erişememelidir.

Sertifikasyonun isteğe bağlı bir işlem olduğunu unutmayın. IAP görselinizin sertifikalı olmasını isteyip istemediğinize siz karar verirsiniz.

## <a name="additional-questions"></a>Diğer sorular

### <a name="how-to-get-support"></a>Nasıl destek alınır?

Tüm sorularınız, yorumlarınız veya sorunlarınız için Power BI görselleri destek takımına başvurmaktan çekinmeyin: *pbicvsupport@microsoft.com*  .  

## <a name="next-steps"></a>Sonraki adımlar

Daha fazla bilgi için [Power BI görsellerinizin sorunlarını giderme](power-bi-custom-visuals-troubleshoot.md) bağlantısını ziyaret edin.
