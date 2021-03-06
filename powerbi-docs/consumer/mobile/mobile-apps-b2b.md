---
title: Power BI içeriğini dış konuk kullanıcı olarak görüntüleme (Azure AD B2B)
description: Dış kuruluştan sizinle paylaşılan içeriği görüntülemek için Power BI mobile uygulamalarını kullanın.
author: paulinbar
ms.author: painbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: how-to
ms.date: 12/09/2019
ms.openlocfilehash: effa9622896f44cff0cf37d7612c35f27e726ef7
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96413254"
---
# <a name="view-power-bi-content-shared-with-you-from-an-external-organization"></a>Dış kuruluştan sizinle paylaşılan Power BI içeriğini görüntüleme

Power BI, işletmeler arası Azure Active Directory (Azure AD B2B ) ile tümleşerek Power BI içeriklerinin kuruluşunuz dışındaki kullanıcılara güvenli bir şekilde dağıtılmasına olanak sağlar. Dış konuk kullanıcılar ise kendileriyle paylaşılan Power BI içeriğine erişmek için Power BI mobil uygulamasını kullanabilirler. 


Aşağıdakiler için geçerlidir:

| ![iPhone](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/iphone-logo-50-px.png) | ![iPad](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/ipad-logo-50-px.png) | ![Android telefon](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/android-phone-logo-50-px.png) | ![Android tablet](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/android-tablet-logo-50-px.png) |
|:--- |:--- |:--- |:--- |
| iPhone'lar |iPad'ler |Android telefonlar |Android tabletler |

## <a name="accessing-shared-content"></a>Paylaşılan içeriğe erişme

**İlk olarak, sizinle içerik paylaşması için dış kuruluştan bir kişi gereklidir.** Sizinle aynı kuruluştan ya da bir dış kuruluştan birisi [sizinle bir içerik paylaştığında](../../collaborate-share/service-share-dashboards.md), paylaşılan içeriğin bağlantısını içeren bir e-posta alırsınız. Mobil cihazınızda bu bağlantıyı takip etmek Power BI mobil uygulamasını açar. Uygulama içeriğin bir dış kuruluştan paylaşıldığını belirlerse, uygulama sizin kimliğinizi kullanarak bu kuruluşa yeniden bağlanır. Uygulama daha sonra o kuruluştan sizinle paylaşılan tüm içerikleri yükler.

![Power BI’da paylaşılan öğeyi e-postadan açma ](./media/mobile-apps-b2b/mobile-b2b-open-item-email-new.png)

> [!NOTE]
> Dış konuk kullanıcı olarak sizinle paylaşılan ilk içerik buysa, daveti bir tarayıcıdan kabul etmeniz gerekir. Daveti Power BI uygulamasından kabul edemezsiniz.

Bir dış kuruluşa bağlı olduğunuz sürece uygulamada siyah bir üst bilgi görünür. Bu üst bilgi, ana kuruluşunuza bağlı olmadığınızı gösterir. Ana kuruluşunuza tekrar bağlanmak için konuk modundan çıkış yapın.

![Power BI konuk kullanıcı üst bilgisi](./media/mobile-apps-b2b/mobile-b2b-exit-home-new.png)

Bir dış kuruluşa bağlanmak için Power BI yapıt bağlantısına sahip olmanız gerekse de, uygulamanız geçiş yaptıktan sonra sizinle paylaşılan tüm içeriklere erişebilirsiniz (yalnızca e-postadan açtığınız içeriğe değil). Dış kuruluşta erişebileceğiniz tüm içerikleri görüntülemek için uygulama menüsüne gidin ve **Benimle paylaşılan**’ı seçin. **Uygulamalar**'ın altında, kullanabileceğiniz uygulamaları da bulabilirsiniz.

![Konuk dış kullanıcı olarak Power BI uygulama menüsü](./media/mobile-apps-b2b/mobile-b2b-menu-new.png)

## <a name="limitations"></a>Sınırlamalar

- Kullanıcıların etkin bir Power BI hesabına ve Ana kiracıya sahip olması gerekir.
- Kullanıcıların, bir dış kiracıdan kendileriyle paylaşılan içeriğe erişebilmesi için Power BI ana kiracılarında oturum açmış olmaları gerekir.
- Koşullu erişim ve diğer Intune ilkeleri, Azure AD B2B ve Power BI mobilde desteklenmez. Bunun anlamı, uygulamanın varsa yalnızca ana kuruluşun ilkelerini zorlamasıdır.
- Anında iletme bildirimleri yalnızca ana kuruluş sitesinden alınır (kullanıcı bir dış kuruluşa konuk olarak bağlandığında bile). Bildirimin açılması, uygulamayı kullanıcının ana kuruluş sitesine yeniden bağlar.
- Kullanıcı uygulamayı kapatırsa, uygulama yeniden açıldığında kullanıcının ana kuruluşuna otomatik olarak bağlanır.
- Bir dış kuruluşa bağlanıldığında bazı eylemler devre dışı bırakılır: sık kullanılan öğeler, veri uyarıları, yorum yapma ve paylaşma.
- Bir dış kuruluşa bağlıyken çevrimdışı veriler kullanılamaz.
- Cihazınızda Şirket Portalı uygulaması yüklüyse cihazınızın kayıtlı olması gerekir.
