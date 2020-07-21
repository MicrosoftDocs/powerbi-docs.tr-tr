---
title: Kiracı yöneticisi ayarları rehberi
description: Power BI kiracı ayarlarına yönelik rehber.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 01/29/2020
ms.author: v-pemyer
ms.openlocfilehash: 7dd6c812116d9ba196b157bd12d6362c19ac64ec
ms.sourcegitcommit: c83146ad008ce13bf3289de9b76c507be2c330aa
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2020
ms.locfileid: "86216724"
---
# <a name="tenant-admin-settings-guidance"></a>Kiracı yöneticisi ayarları rehberi

Bu makalenin hedef kitlesi, kuruluşlarındaki Power BI ortamını ayarlamadan ve yapılandırmadan sorumlu Power BI yöneticileridir.

Makalede, Power BI deneyimini geliştirmeye yardımcı olan veya kuruluşunuzu risk altında bırakabilecek belirli kiracı ayarlarına yönelik rehberlik sunulur. Kiracınızı kuruluşunuzun ilke ve süreçleriyle uyumlu olacak şekilde yapılandırmanızı öneririz.

[Kiracı ayarları](../admin/service-admin-portal.md#tenant-settings) [Yönetici portalından](https://app.powerbi.com/admin-portal/tenantSettings) yönetilir ve bir [Power BI hizmet yöneticisi](../admin/service-admin-administering-power-bi-in-your-organization.md#administrator-roles-related-to-power-bi) tarafından yapılandırılabilir. Çoğu kiracı ayarı, özellikleri sınırlı sayıda kullanıcıyla kısıtlayabilir. Bu nedenle, ihtiyaç duyacağınız güvenlik gruplarını planlamak için ilk olarak ayarları öğrenmeniz önerilir. Aynı güvenlik grubunu birden fazla ayara uygulayabileceğinizi fark edebilirsiniz.

## <a name="improve-power-bi-experience"></a>Power BI deneyimini geliştirme

### <a name="publish-get-help-information"></a>“Yardım alın” bilgilerini yayımlama

[Microsoft Teams](/microsoftteams) veya farklı bir işbirliği platformunu kullanarak Power BI ile ilgili iç siteler oluşturmanızı öneririz. Bu siteler, eğitim belgelerini depolamak, tartışma düzenlemek, lisans isteğinde bulunmak veya yardım isteklerine yanıt vermek için kullanılabilir.

Bunu yapacaksanız, _tüm kuruluş için_ **“Yardım Alın” bilgilerini yayımla** ayarını etkinleştirmenizi öneririz. Bu ayar, **Yardım ve destek ayarları** grubunda bulunur. Şunlar için URL ayarlayabilirsiniz:

- Eğitim belgeleriniz
- Tartışma forumunuz
- Lisans istekleriniz
- Yardım masanız

Bu URL’ler, Power BI yardım menüsünde bağlantı olarak kullanıma sunulur.

> [!NOTE]
> **Lisanslama istekleri** URL’sinin sağlanması, bireysel kullanıcıların 60 günlük ücretsiz Power BI Pro deneme sürümüne kaydolmasını engeller. Bunun yerine, kullanıcılar Power BI Ücretsiz veya Pro için lisans alma bilgilerini içeren iç sitenize yönlendirilir.

![Yardım ve Destek ayarlarını gösteren Power BI Desktop’ın ekran görüntüsü.](media/admin-tenant-settings/publish-get-help-information.png)

## <a name="manage-risk"></a>Riski yönetin
Riskleri yönetme ayarları, Power BI kiracınızda idare ilkeleri oluşturmanıza yardımcı olabilir. Ancak, idare ayarlarının bir güvenlik ölçümü olmadığını unutmayın. Örneğin, **Verileri dışarı aktar** ayarını devre dışı bırakmak, özelliği Power BI kullanıcı arabiriminden kaldırır ve bu şekilde Power BI kullanıcılarının kuruluşunuzun idare ilkeleriyle uyumlu bir şekilde çalışmasına yardımcı olur, ancak belirli kullanıcıların diğer seçenekleri kullanarak dışarı veri aktarmalarını önlemez. Güvenlik açısından, bir veri kümesine ilişkin okuma iznine sahip bir Power BI kullanıcısı bu veri kümesini sorgulama iznine sahiptir ve Power BI kullanıcı arabiriminde kullanılabilir özelliklerden bağımsız olarak sonuçları kalıcı hale getirebilir.
### <a name="receive-email-notification-service-outages-or-incidents"></a>Hizmet kesintileri veya olaylar için e-posta bildirimleri gönder

Kiracınız hizmet kesintisinden veya olaydan etkileniyorsa e-posta yoluyla bildirim alabilirsiniz. Böylece, olaylara proaktif olarak yanıt verebilirsiniz.

**Hizmet kesintileri veya olaylar için e-posta bildirimleri gönder** ayarını etkinleştirmenizi öneririz. Bu ayar **Yardım ve destek ayarları** grubunda bulunur. Bir veya daha fazla _Posta etkin_ güvenlik grubu atayın.

![“Hizmet kesintileri veya olaylar için e-posta bildirimleri gönder” ayarını gösteren Power BI Desktop’ın ekran görüntüsü.](media/admin-tenant-settings/receive-email-notifications-for-service-outages-or-incidents.png)

### <a name="information-protection"></a>Bilgi koruması

Bilgi koruması, veriler Power BI hizmetinden dışarı aktarılırken şifreleme veya eşik değerler gibi koruma ayarlarının uygulanmasına olanak tanır.

Bilgi korumasına ilişkin iki kiracı ayarı bulunur. Varsayılan olarak, ikisi de tüm kuruluş için devre dışıdır.

Hassas verilerle çalışmanız veya bunları korumanız gerekiyorsa bu ayarları etkinleştirmenizi öneririz. Daha fazla bilgi için bkz. [Power BI’da veri koruması](../admin/service-security-data-protection-overview.md).

### <a name="create-workspaces"></a>Çalışma alanı oluşturma

Kullanıcıların çalışma alanı oluşturmasını kısıtlayabilirsiniz. Böylece, kuruluşunuzda nelerin oluşturulabileceğini belirleyebilirsiniz.

> [!NOTE]
> Şu anda, eski çalışma alanı deneyiminden yenisine geçiş süreci devam ediyor. Bu kiracı ayarı yalnızca yeni deneyim için geçerlidir.

**Çalışma alanları oluştur** ayarı tüm kuruluş için varsayılan olarak etkindir. Bu ayar, **Çalışma alanı ayarları** grubunda bulunur.

Bir veya daha fazla güvenlik grubu atamanızı öneririz. Bu gruplara çalışma alanı oluşturma izni verilebilir _veya izin reddedilebilir_.

Çalışma alanı oluşturma hakları olmayan kullanıcılara yeni bir çalışma alanı istemeyi öğreten yönergeleri belgelerinize eklemeyi unutmayın.

![“Çalışma alanı oluştur” ayarını gösteren Power BI Desktop’ın ekran görüntüsü.](media/admin-tenant-settings/create-workspaces.png)

### <a name="share-content-with-external-users"></a>Dış kullanıcılarla içerik paylaşma

Kullanıcılar, raporları ve panoları kuruluşunuzun dışındaki kişilerle paylaşabilir.

**Dış kullanıcılarla içerik paylaş** ayarı tüm kuruluş için varsayılan olarak etkindir. Bu ayar, **Dışarı aktarma ve paylaşım ayarları** grubunda bulunur.

Bir veya daha fazla güvenlik grubu atamanızı öneririz. Bu gruplara dış kullanıcılarla içerik paylaşma izni atanabilir veya _izin reddedilebilir_.

![“Dış kullanıcılarla içerik paylaşma” ayarını gösteren Power BI Desktop’ın ekran görüntüsü.](media/admin-tenant-settings/share-content-with-external-users.png)

### <a name="publish-to-web"></a>Web'de yayımla

[Web’de yayımla](../collaborate-share/service-publish-to-web.md) özelliği, genel raporların Web’de yayımlanmasına olanak tanır. Uygun şekilde kullanılmazsa, gizli bilgilerin Web’de canlı olarak kullanılabilir hale gelme riski vardır.

**Web’de yayımla** ayarı, tüm kuruluş için varsayılan olarak etkindir. Ancak, yönetici olmayan kullanıcıların ekleme kodu oluşturma özellikleri kısıtlanır. **Dışarı aktarma ve paylaşım ayarları** grubunda bulunur.

Bu özellik etkinse, bir veya daha fazla güvenlik grubu atamanızı öneririz. Bu gruplara rapor yayımlama izni verilebilir _veya izin reddedilebilir_.

Ayrıca, ekleme kodlarınızın nasıl çalışacağını belirleme seçeneği de bulunur. Varsayılan olarak, **Yalnızca mevcut kodlara izin ver** olarak ayarlanır. Bu ayar, kullanıcılardan ekleme kodu oluşturmak için Power BI yöneticisine ulaşmalarının isteneceğini belirtir.

![“Web’de yayımlama” ayarını gösteren Power BI Desktop’ın ekran görüntüsü.](media/admin-tenant-settings/publish-to-web.png)

[Web’de yayımla ekleme kodlarını](https://app.powerbi.com/admin-portal/embedCodes) düzenli olarak gözden geçirmenizi de öneririz. Özel veya gizli bilgilerin yayımlanması durumunda, buna sebep olan kodları kaldırın.

### <a name="export-data"></a>Verileri dışarı aktar

Kullanıcıların pano kutucuklarından veya rapor görsellerinden verileri dışarı aktarmalarını kısıtlayabilirsiniz.

**Verileri dışarı aktar** ayarı tüm kuruluş için varsayılan olarak etkindir. **Dışarı aktarma ve paylaşım ayarları** grubunda bulunur.

Bir veya daha fazla güvenlik grubu atamanızı öneririz. Bu gruplara rapor yayımlama izni verilebilir _veya izin reddedilebilir_.

> [!IMPORTANT]
> Bu ayarın devre dışı bırakılması, [Excel’de Çözümle](../collaborate-share/service-analyze-in-excel.md) ve Power BI hizmeti [canlı bağlantı](../connect-data/desktop-report-lifecycle-datasets.md#using-a-power-bi-service-live-connection-for-report-lifecycle-management) özelliklerinin kullanımını da kısıtlar.

![“Verileri dışarı aktarma” ayarını gösteren Power BI Desktop’ın ekran görüntüsü.](media/admin-tenant-settings/export-data.png)

> [!NOTE]
> Kullanıcılar, diğer kullanıcıların verileri dışarı aktarmasına izin verirse, [veri koruması](../admin/service-security-data-protection-overview.md) uygulayarak koruma katmanı ekleyebilirsiniz. Bu yapılandırıldığında, duyarlılık etiketleri ile yetkisiz kullanıcıların içeriği dışarı aktarması engellenir.

### <a name="allow-external-guest-users-to-edit-and-manage-content-in-the-organization"></a>Harici konuk kullanıcıların kuruluş içeriklerini düzenlemelerine ve yönetmelerine izin ver

Dış kullanıcılar Power BI içeriğini düzenleyebilir ve yönetebilir. Daha fazla bilgi için bkz. [Azure AD B2B ile Power BI içeriğini dış konuk kullanıcılara dağıtma](../admin/service-admin-azure-ad-b2b.md).

**Dış konuk kullanıcıların kuruluş içeriklerini düzenlemelerine ve yönetmelerine izin ver** ayarı tüm kuruluş için varsayılan olarak devre dışıdır. **Dışarı aktarma ve paylaşım ayarları** grubunda bulunur.

Dış kullanıcılara içerik düzenleme ve yönetme yetkisi vermeniz gerekiyorsa, bir veya daha fazla güvenlik grubu atamanızı öneririz. Bu gruplara rapor yayımlama izni verilebilir _veya izin reddedilebilir_.

![“Dış konuk kullanıcıların kuruluştaki içeriği düzenleyip yönetmesine izin verme” ayarını gösteren Power BI Desktop’ın ekran görüntüsü.](media/admin-tenant-settings/allow-external-guest-users.png)

### <a name="developer-settings"></a>Geliştirici ayarları

[Power BI içeriğini eklemeye](../developer/embedded/embedding.md) ilişkin iki kiracı ayarı bulunur. Bunlar:

- Uygulamalara içerik ekle (varsayılan olarak etkindir)
- Hizmet sorumlularının Power BI API’lerini kullanmasına izin ver (varsayılan olarak devre dışıdır)

İçerik eklemek için geliştirici API’lerini kullanma amacınız yoksa, bunları devre dışı bırakmanızı öneririz. Ya da bu işlemi gerçekleştirecek belirli güvenlik grupları yapılandırabilirsiniz.

![Geliştirici ayarlarını gösteren Power BI Desktop’ın ekran görüntüsü.](media/admin-tenant-settings/developer-settings.png)

## <a name="next-steps"></a>Sonraki adımlar

Bu makaleyle ilgili daha fazla bilgi için aşağıdaki kaynaklara bakın:

- [Power BI yönetimi nedir?](../admin/service-admin-administering-power-bi-in-your-organization.md)
- [Yönetim portalında Power BI’ı yönetme](../admin/service-admin-portal.md)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
- Önerileriniz mi var? [Power BI'ı geliştirmek için fikirlerinizi paylaşın](https://ideas.powerbi.com)