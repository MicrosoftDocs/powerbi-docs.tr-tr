---
title: Power BI bir dış Konuk kullanıcı (Azure AD B2B) içeriği görüntüleyin
description: Dış kuruluştan sizinle paylaşılan içeriği görüntülemek için Power BI mobil uygulamaları kullanın.
author: mshenhav
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 03/27/2019
ms.author: mshenhav
ms.openlocfilehash: a15da4349ce97e34c8321909abc862e424b2839c
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "61338772"
---
# <a name="view-power-bi-content-shared-with-you-from-an-external-organization"></a>Bir dış kuruluştan paylaşılan Power BI içeriğini görüntüleme

Power BI, Azure Active Directory--işletmeler arası (B2B Power BI içeriklerinin kuruluş dışındaki kullanıcılara güvenli dağıtım izin vermek için Azure AD) ile tümleşir. Ve dış konuk kullanıcılara kendileriyle paylaşılan Power BI içeriği erişmek için Power BI mobil uygulamasını kullanabilirsiniz. 


Aşağıdakiler cihazlar için geçerlidir:

| ![iPhone](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/iphone-logo-50-px.png) | ![iPad](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/ipad-logo-50-px.png) | ![Android telefon](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/android-phone-logo-50-px.png) | ![Android tablet](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/android-tablet-logo-50-px.png) |
|:--- |:--- |:--- |:--- |
| iPhone'lar |iPad'ler |Android telefonlar |Android tabletler |

## <a name="accessing-shared-content"></a>Paylaşılan içeriği erişme

**İlk olarak, birisi sizinle bir öğe paylaştırmak için bir dış kuruluştan gerekir.** Birisi olduğunda [öğeyi paylaştığında](../../service-share-dashboards.md), aynı kuruluş veya bir dış kuruluştan, paylaşılan öğeyi bağlantısını içeren bir e-posta alırsınız. Mobil Cihazınızı, bağlantıyı izleyerek Power BI mobil uygulamasında açılır. Uygulama öğesi bir dış kuruluştan paylaşıldı tanıyorsa uygulama, kuruluş kimliğinizle yeniden bağlanır. Uygulama, daha sonra bu kuruluştan Sizinle paylaşılmış olan tüm öğeleri yükler.

![Power BI, e-postadan paylaşılan öğe açın ](./media/mobile-apps-b2b/mobile-b2b-open-item-email.png)

> [!NOTE]
> Bu bir dış konuk kullanıcıyla paylaşılan ilk öğesi ise, bir tarayıcıda davet talep gerekir. Talep Power BI uygulamasında davet edilemiyor.

Harici bir kuruluş için bağlı olduğu sürece, uygulamada siyah üstbilgi görünür. Bu üst bilgisi, ev kuruluşunuza bağlı değil gösterir. Giriş kuruluşunuza bağlamak için konuk modundan çıkın.

![Power BI Konuk kullanıcı üstbilgisi](./media/mobile-apps-b2b/mobile-b2b-exit-home.png)

Harici bir kuruluş için uygulamanızı geçer sonra bağlanmak için Power BI yapı bağlantısına ihtiyacınız olsa da, (yalnızca e-postadan açılır öğe) sizinle paylaşılan tüm öğelere erişebilirsiniz. Dış kuruluştaki erişebileceğiniz tüm öğeleri görüntülemek için uygulama menüsüne gidin ve seçin **benimle paylaşılan**. Altında **uygulamaları** de kullanabilen uygulamalar bulun.

![Dış Konuk kullanıcı olarak Power BI uygulama menüsü](./media/mobile-apps-b2b/mobile-b2b-menu.png)

## <a name="limitations"></a>Sınırlamalar

- Koşullu erişim ve diğer Intune ilkeleri, Azure AD B2B ve Power BI mobil uygulamalarında desteklenmez. Varsa bu uygulama yalnızca giriş kuruluşun ilkelerini zorlayan anlamına gelir.
- Anında iletme bildirimleri yalnızca giriş kuruluş siteden alınan (hatta kullanıcı harici bir kuruluş için bir konuk olarak bağlandığında). Bildirim açarak uygulamayı kullanıcının ev kuruluş siteye yeniden bağlanır.
- Kullanıcı, uygulamayı kapanıyorsa olduğunda yeniden açılmış uygulamayı kullanıcının ev kuruluşa otomatik olarak bağlanır.
- Harici bir kuruluş için bağlandığınızda, bazı eylemler devre dışı: sık kullanılan öğe veri uyarıları, yorum oluşturma ve paylaşma.
- Harici bir kuruluş için bağlı değilken çevrimdışı veri kullanılamıyor.
- Şirket portalı uygulamasının Cihazınızda yüklü varsa, cihazın kayıtlı olmalıdır.
