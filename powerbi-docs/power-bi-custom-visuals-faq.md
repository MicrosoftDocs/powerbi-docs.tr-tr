---
title: Power BI özel görselleri hakkında sık sorulan sorular
description: Power BI özel görselleri hakkında sık sorulan sorular ve cevaplar listesini inceleyin
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.custom: ''
ms.date: 12/17/2018
ms.openlocfilehash: c17f9b9841335420db67abb62c92603bf804f275
ms.sourcegitcommit: 13fdc8d62960f20c6d9ca1ab292f98992b47083b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/18/2018
ms.locfileid: "53553916"
---
# <a name="frequently-asked-questions-about-power-bi-custom-visuals"></a>Power BI özel görselleri hakkında sık sorulan sorular

## <a name="organizational-custom-visuals"></a>Özel kuruluş görselleri

### <a name="how-can-the-admin-manage-the-organizational-custom-visuals"></a>Yöneticiler, özel kuruluş görsellerini nasıl yönetebilir?

Yöneticiler, Yönetim portalının "Özel kuruluş görselleri" sekmesinden [kuruluştaki tüm özel kuruluş görsellerini görebilir ve şu yönetim işlemlerini gerçekleştirebilir](https://docs.microsoft.com/power-bi/service-admin-portal#organization-visuals): ekleme, devre dışı bırakma, etkinleştirme ve silme.
Artık bu görselleri e-posta veya paylaşılan klasörle paylaşmaya gerek yoktur! Görseller kuruluş deposuna dağıtıldıktan sonra kuruluştaki kullanıcılar bunları kolayca bulabilir ve özel kuruluş görsellerini doğrudan Power BI Desktop’tan veya Power BI hizmetinden raporlarına aktarabilir. Özel kuruluş görsellerine *KURULUŞUM* sekmesindeki yerleşik mağazadan (Desktop ve hizmet) erişebilirsiniz. Yönetici özel bir görselin yeni sürümünü yüklediğinde kuruluştaki tüm kullanıcılar aynı güncel sürüme sahip olur. Rapor yazarlarının raporlardaki görselleri silerek yeni sürümünü eklemesine gerek yoktur. Bu görselin kullanıldığı tüm raporlar otomatik olarak güncelleştirilir! Market görsellerinin güncelleştirme mekanizması da benzerdir.

### <a name="if-an-admin-uploads-a-custom-visual-from-the-public-marketplace-to-the-organization-store-is-it-automatically-updated-once-a-vendor-updates-the-visual-in-the-public-marketplace"></a>Yöneticinin genel marketten kuruluş deposuna yüklediği özel görsellerde satıcı tarafından yapılan güncelleştirmeler otomatik olarak uygulanır mı?

Hayır, genel marketten otomatik güncelleştirme yapılmaz.
Özel kuruluş görsellerinin güncel sürümünü yüklemek Yöneticinin sorumluluğundadır.

### <a name="is-there-a-way-to-disable-the-organizational-store"></a>Kuruluş deposunu devre dışı bırakmak mümkün mü?

Hayır, kullanıcılar Power BI Desktop uygulamasında ve hizmetinde her zaman "KURULUŞUM" sekmesini görür. Yönetici, yönetim portalından tüm özel kuruluş görsellerini devre dışı bırakabilir veya silebilir. Bu durumda kuruluş deposu boş olacaktır.
  
### <a name="if-the-administrator-disables-custom-visuals-from-the-admin-portal-tenant-settings-do-users-still-have-access-to-the-organizational-custom-visuals"></a>Yönetici, özel görselleri Yönetim portalından (Kiracı ayarları) devre dışı bıraktığında kullanıcılar özel kuruluş görsellerine erişmeye devam edebilir mi?

Evet, yöneticinin özel görselleri yönetim portalından devre dışı bırakması kuruluş deposunu etkilemez. Bazı kuruluşlar özel görselleri devre dışı bırakıp yalnızca Power BI yöneticisi tarafından kuruluş deposuna aktarılan ve yüklenen seçili görsellerin kullanılmasını etkinleştirmektedir. Özel görsellerin Yönetim portalından devre dışı bırakılması Power BI Desktop uygulamasını etkilemez. Power BI Desktop kullanıcıları genel marketteki özel görselleri ekleyip raporlarında kullanabilir. Ancak rapor Power BI hizmetinde yayımlandığında bu ortak görseller işlenmez ve bu durumu bildiren bir hata iletisi görüntülenir. Power BI hizmetini kullanırken genel marketteki özel görselleri içeri aktaramazsınız. Yönetim portalındaki özel görsel ayarı Power BI hizmetine uygulandığından yalnızca kuruluş deposundaki görselleri içeri aktarabilirsiniz.

### <a name="why-does-the-organizational-store-and-organizational-custom-visuals-make-a-great-enterprise-solution"></a>Kuruluş deposunun ve özel kuruluş görsellerinin kurumsal bir çözüm oluşturma açısından sağladığı avantajlar nelerdir?

* Herkes Power BI yöneticisi tarafından denetlenen aynı görsel sürümüne sahip olur. Yönetici, görsel sürümünü yönetim portalından güncelleştirdiğinde kuruluştaki tüm kullanıcılar otomatik olarak güncel sürümü alır.

* Görsel dosyalarını e-posta veya paylaşılan klasörlerle paylaşmanıza gerek kalmaz! Özel görseller, oturum açmış olan tüm kullanıcıların görüntüleyebileceği tek bir yerde depolanır.

* Özel kuruluş görsellerinin yeni sürümleri market görselleri gibi tüm raporlarda otomatik olarak güncelleştirilerek güvenlik ve desteklenebilirlik sağlar.

* Kuruluş içindeki özel kuruluş görseli kullanan çalışanların ilgili özel kuruluş görsellerini görmek ve kullanmak için oturum açmış olması gerekir. Bu da kuruluş için ek bir güvenlik katmanı sağlar.

* Yöneticiler, kuruluşta kullanılabilecek olan özel görselleri denetleyebilir.

* Yöneticiler, yönetim portalını kullanarak görselleri test amaçlı olarak etkinleştirebilir/devre dışı bırakabilir. Bu görsellere erişme izni yalnızca kuruluş üyelerine verileceğinden daha güvenli bir erişim sağlanmış olur.

## <a name="certified-custom-visuals"></a>Sertifikalı özel görseller

### <a name="what-are-certified-custom-visuals"></a>Sertifikalı özel görseller nedir?

Sertifikalı özel görseller, [markette](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals) bulunan ve Power BI ekibi tarafından oluşturulan [belirli](power-bi-custom-visuals-certified.md) kod gereksinimlerini karşılayan ve belirli testlerden geçmiş olan görsellerdir.  Gerçekleştirilen testler görselin dış hizmetlere veya kaynaklara erişmediğini denetleyecek şekilde tasarlanmıştır. Öte yandan, üçüncü taraf özel görsellerinin yazarı Microsoft değildir. Müşterilerin bu tür bir görselin işlevselliğini doğrulamak için doğrudan yazarına başvurmasını öneririz.

## <a name="visuals-with-additional-purchases"></a>Ek satın almaları olan görseller

### <a name="what-is-a-visual-with-additional-purchases"></a>Ek satın almaları olan görsel nedir?

Ek satın almaları olan görsel, marketteki uygulama içi satın alma (IAP) eklentisine benzer. Bu eklentilerin  **Ek satın alma işlemleri gerekebilir** şeklinde bir fiyat etiketi vardır.

IAP özel görselleri ücretsiz, indirilebilir özel görsellerdir. Kullanıcılar bu özel görselleri marketten indirirken hiçbir ödeme yapmaz. IAP görselleri gelişmiş özellikler için isteğe bağlı uygulama içi satın almalar sunar.  

### <a name="whats-the-benefit-to-developers"></a>Geliştiriciler açısından avantajı nedir?

AppSource'ta IAP özel görselleri birçok günlük ziyaretçi tarafından bulunabilecek, trafikte değerli bir artış sağlayacak, IAP özel görsellerinizin ve bir geliştirici olarak sizin bilinirliğinizi artıracaktır.

Söz konusu görselleri kısa süre öncesine kadar web siteniz üzerinden yönettiyseniz, şimdi bunları AppSource'a gönderebilirsiniz. Bunu yapmanız Power BI topluluğu içinde IAP görsellerinin bulunabilirlik ve görünürlük düzeyini artıracaktır.

AppSource'taki görseller, mağazadaki inceleme ve değerlendirme sistemi aracılığıyla IAP özel görselini kullanan müşterilerinizin Doğrudan geri bildirim kanalından yararlanır.  

IAP görseli AppSource doğrulama takımı tarafından onaylandıktan sonra, söz konusu görseli sertifikalanması için de gönderebilirsiniz. Bu isteğe bağlı bir işlemdir.  

Sertifikalanan IAP özel görselleri PowerPoint'e aktarılabilir ve kullanıcı rapor sayfalarına abone olduğunda alınan e-postalarda görüntülenebilir. Dolayısıyla artık IAP görsellerini markete göndererek IAP özel görsellerinin sertifikalanması ve ek özellik kümesini desteklemesi sağlanabilir.  

### <a name="do-iap-visuals-need-to-be-certified"></a>IAP görsellerinin sertifikalanması gerekli mi?

Sertifikasyon işlemi isteğe bağlıdır. Ücretsiz görsellerde olduğu gibi, IAP özel görsellerini sertifikalama konusundaki karar da geliştiriciye aittir.

### <a name="what-is-changing-in-the-submission-process"></a>Gönderim işleminde neler değişti?

IAP özel görsellerini markete gönderim işlemi, ücretsiz görselleri gönderim işlemiyle aynıdır. Satıcı panosu aracılığıyla yapılır.  Gönderim işlemindeki tek değişiklik, geliştiricilerin satıcı panosundaki geliştirici notlarında şunu belirtmesinin gerekli olmasıdır: “Uygulama içi satın alması olan görsel”. Ücretli/gelişmiş özellikleri doğrulamak için gerekliyse bir lisans anahtarı/belirteci sağlamanız da istenecektir.  

Satıcı panosunda yeni seçenek olmayacaktır. *Uygulama içi satın almalar içeren ücretsiz uygulama* olduğunda IAP görsellerinizi *ücretsiz* olarak göndermeniz gerekecektir.

Bunun yanı sıra, mağazanızda hangi özelliklerin ücretsiz olduğu ve hangilerinin çalışması için ek satın almalar gerektirdiği konusunda ayrıntılı bir açıklama sağlayarak kullanıcılara neler bekleyebileceklerini bildirin.  

### <a name="what-should-i-do-beforesubmittingmy-iap-custom-visual"></a>IAP özel görselimi göndermeden önce ne yapmalıyım?

Bir özel IAP görseli üzerinde çalışıyorsanız veya zaten böyle bir görseliniz varsa bunun yönergelere uygun olduğundan emin olun.  

Özel görsel üzerinde bir logo varsa bunun logo yönergelerine (renk, konum, boyut ve eylem tetikleme) uygun olduğundan emin olun.

Ayrıca yönergelerde en iyi yöntemler hakkında notlar da bulabilirsiniz.  

### <a name="can-i-get-my-iap-custom-visual-certified"></a>IAP özel görselimin sertifikalı olmasını sağlayabilir miyim?

Evet, ücretsiz görsellerle aynı şekilde.  IAP özel görseliniz AppSource takımı tarafından onaylandıktan sonra, görselinizi sertifikasyon işlemi için gönderebilirsiniz.

Görselinizin sertifikalı olması için sertifikasyon gereksinimlerini karşılaması gerekir. Örneğin, görsel lisans doğrulaması için dış hizmetlere erişememelidir.

Sertifikasyonun isteğe bağlı bir işlem olduğunu unutmayın. IAP görselinizin sertifikalı olmasını isteyip istemediğinize siz karar verirsiniz.

## <a name="additional-questions"></a>Diğer sorular

### <a name="how-to-get-support"></a>Nasıl destek alınır?

Tüm sorularınız, yorumlarınız veya sorunlarınız için özel görseller destek takımına başvurmaktan çekinmeyin: *pbicvsupport@microsoft.com* .  

## <a name="next-steps"></a>Sonraki adımlar

Daha fazla bilgi için [Power BI özel görsellerinizin sorunlarını giderme](power-bi-custom-visuals-troubleshoot.md) bağlantısını ziyaret edin.
