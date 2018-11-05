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
ms.date: 10/29/2018
LocalizationGroup: Visualizations
ms.openlocfilehash: a2e43d205b9e4f3085652ac3603ee68f67b2b33c
ms.sourcegitcommit: f9dd6098ca57d4d6cad34284126d4e58eab1c92c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2018
ms.locfileid: "50222178"
---
# <a name="frequently-asked-questions-about-power-bi-custom-visuals"></a>Power BI özel görselleri hakkında sık sorulan sorular

## <a name="organizational-custom-visuals"></a>Özel kuruluş görselleri

**Yöneticiler, özel kuruluş görsellerini nasıl yönetebilir?**

Yöneticiler, Yönetim portalının "Özel kuruluş görselleri" sekmesinden [kuruluştaki tüm özel kuruluş görsellerini görebilir ve şu yönetim işlemlerini gerçekleştirebilir](https://docs.microsoft.com/power-bi/service-admin-portal#organization-visuals): ekleme, devre dışı bırakma, etkinleştirme ve silme.
Bu görselleri e-posta veya paylaşılan klasörle paylaşmaya gerek yoktur! Görsel kuruluş deposuna dağıtıldıktan sonra kuruluştaki kullanıcılar bunları doğrudan Power BI Desktop’tan veya Power BI hizmetinden kolayca keşfedebilir ve özel kuruluş görsellerini raporlarında içeri aktarabilir. Özel kuruluş görsellerine "KURULUŞUM" sekmesindeki yerleşik depodan (Desktop ve hizmet) erişebilirsiniz. Yönetici özel bir görselin yeni sürümünü yüklediğinde kuruluştaki tüm kullanıcılar aynı güncel sürüme sahip olur. Rapor yazarlarının raporlardaki görselleri silerek yeni sürümünü eklemesine gerek yoktur. Bu görseli kullanan tüm raporlar otomatik olarak güncelleştirilir! Market görsellerinin güncelleştirme mekanizması da benzerdir.

**Bir yöneticinin ortak marketten kuruluş deposuna yüklediği özel görsellerde satıcı tarafından yapılan güncelleştirmeler otomatik olarak uygulanır mı?**

Hayır, ortak marketten otomatik güncelleştirme yapılmaz.
Özel kuruluş görsellerinin güncel sürümünü yüklemek isteğe bağlıdır ve Yöneticinin sorumluluğundadır.

**Kuruluş deposunu devre dışı bırakmak mümkün mü?**

Hayır, kullanıcılar Power BI Desktop uygulamasında ve hizmetinde her zaman "KURULUŞUM" sekmesini görür. Yönetici, yönetim portalından tüm özel kuruluş görsellerini devre dışı bırakabilir veya silebilir. Bu durumda kuruluş deposu boş olacaktır.
  
**Yönetici, özel görselleri Yönetim portalından (Kiracı ayarlar) devre dışı bıraktığında kullanıcılar özel kuruluş görsellere erişmeye devam edebilir mi?**

Evet, yöneticinin özel görselleri yönetim portalından devre dışı bırakması kuruluş deposunu etkilemez. Bazı kuruluşlar özel görselleri devre dışı bırakıp yalnızca Power BI yöneticisi tarafından kuruluş deposuna aktarılan ve yüklenen seçili görsellerin kullanılmasını etkinleştirmektedir. Özel görsellerin Yönetim portalından devre dışı bırakılması Power BI Desktop uygulamasını etkilemez. Power BI Desktop kullanıcıları ortak marketteki özel görselleri ekleyip raporlarında kullanabilir. Ancak rapor Power BI hizmetinde yayımlandığında bu ortak görseller işlenmez ve bu durumu bildiren bir hata iletisi görüntülenir. Power BI hizmetini kullanırken ortak marketteki özel görselleri içeri aktaramazsınız. Yönetim portalındaki özel görsel ayarı Power BI hizmetine uygulandığından yalnızca kuruluş deposundaki görselleri içeri aktarabilirsiniz.

**Kuruluş deposunun ve özel kuruluş görsellerinin kurumsal bir çözüm oluşturma açısından sağladığı avantajlar nelerdir?**

* Herkes Power BI yöneticisi tarafından denetlenen aynı görsel sürümüne sahip olur. Yönetici, görsel sürümünü yönetim portalından güncelleştirdiğinde kuruluştaki tüm kullanıcılar otomatik olarak güncel sürümü alır.

* Görsel dosyalarını e-posta veya paylaşılan klasörlerle paylaşmanıza gerek kalmaz! Özel görseller, oturum açmış olan tüm kullanıcıların görüntüleyebileceği tek bir yerde depolanır.

* Özel kuruluş görsellerinin yeni sürümleri market görselleri gibi tüm raporlarda otomatik olarak güncelleştirilerek güvenlik ve desteklenebilirlik sağlar.

* Kuruluş içindeki özel kuruluş görseli kullanan çalışanların ilgili özel kuruluş görsellerini görmek ve kullanmak için oturum açmış olması gerekir. Bu da kuruluş için ek bir güvenlik katmanı sağlar.

* Yöneticiler, kuruluşta kullanılabilecek olan özel görselleri denetleyebilir.

* Yöneticiler, yönetim portalını kullanarak görselleri test amaçlı olarak etkinleştirebilir/devre dışı bırakabilir. Bu görsellere erişme izni yalnızca kuruluş üyelerine verileceğinden daha güvenli bir erişim sağlanmış olur.

## <a name="certified-custom-visuals"></a>Sertifikalı özel görseller

**Sertifikalı özel görseller nedir?**

Sertifikalı özel görseller, [markette](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals) bulunan ve Power BI ekibi tarafından oluşturulan [belirli](power-bi-custom-visuals-certified.md) kod gereksinimlerini karşılayan ve belirli testlerden geçmiş olan görsellerdir.  Gerçekleştirilen testler, görselin dış hizmetlere veya kaynaklara erişmediğinden emin olmak için gerçekleştirilir. Ancak üçüncü taraf özel görseller Microsoft tarafından oluşturulmadığından müşterilerin ilgili görsellerin işlevini doğrulama amacıyla doğrudan yazarla iletişime geçmesini öneririz.
