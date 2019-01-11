---
title: Ek satın alma işlemleri gerekebilir - Power BI Görselleri Yönergeleri
description: Özel görselinizi diğer kullanıcıların keşfetmesi ve satın alma yoluyla kullanması amacıyla AppSource'ta nasıl yayımlayabileceğinizi öğrenin.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.subservice: powerbi-custom-visuals
ms.date: 11/26/2018
ms.openlocfilehash: 2b7a71baafd8ec2ef839aaca95529221c642357f
ms.sourcegitcommit: c09241803664643e1b2ba0c150e525e1262ca466
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/08/2019
ms.locfileid: "54072187"
---
# <a name="guidelines-for-power-bi-visuals-with-additional-purchases"></a>Ek satın almalarla Power BI görsellerine ilişkin yönergeler

Yakın zamana kadar, **Market (AppSource)** yalnızca ücretsiz olan Power BI görsellerini kabul ediyordu. Bu ilke değişiyor ve artık "ek satın alma gerekebilir" fiyat etiketini taşıyan görseller de **AppSource**'a gönderilebilir. Ek satın alma işlemleri gerektirebilen görseller, Office mağazasındaki uygulama için satın alma (IAP) eklentilerine benzer. Geliştiriciler bu görselleri, **AppSource** ekibi onayladıktan ve [Sertifikalı özel görseller makalesinde](../power-bi-custom-visuals-certified.md) açıklanan sertifika gereksinimlerine uyduğundan emin olduktan sonra da sertifikasyon için gönderebilir.

> [!Note]
> Görselin sertifikalanması için, dış hizmetlere veya kaynaklara erişmemesi gerekir.

## <a name="whats-changing-in-the-submission-process"></a>Gönderim işleminde neler değişti?

Geliştiriciler, ücretsiz görseller için yaptıkları gibi Satıcı Panosu üzerinden IAP görsellerini AppSource'a yüklerler. Gönderilen görselin IAP özelliklerine sahip olduğunu belirtmek için, geliştiricilerin satıcı panosuna not yazması gerekir: "Uygulama içi satın alma özellikli görsel." Ayrıca, doğrulama ekibinin IAP özelliklerini doğrulayabilmesi için geliştiriciler bir lisans anahtarı veya belirteç sağlamalıdır. Görsel doğrulandıktan ve onaylandıktan sonra, IAP görseli için AppSource listesinde, fiyat seçeneklerinin altında 'Ek satın alma gerekebilir' belirtimi yer alır.

## <a name="what-is-a-power-bi-visual-with-iap-features"></a>IAP özelliklerine sahip Power BI görseli nedir?

IAP görseli ücretsiz bir görseldir ve ücretsiz özellikler sunar, ama çalıştırmak için fazladan ücret ödemeyi gerektirebilecek ek özellikleri de vardır. Geliştiricilerin, görselin açıklamasında hangi özellikleri çalıştırmak için ek satın almalar gerektiğini kullanıcılara bildirmesi gerekir. Şu anda Microsoft, uygulama içinde ve eklentilerde satın almayı desteklemek için yerel uygulama programı arabirimi (API) sağlamamaktadır. Geliştiriciler söz konusu satın almalarda üçüncü taraf bir ödeme sistemi kullanabilir. Mağaza [ilkemizi](https://docs.microsoft.com/office/dev/store/validation-policies#2-apps-or-add-ins-can-display-certain-ads) gözden geçirin.

## <a name="logo-guidelines"></a>Logo yönergeleri

Bu bölümde, görsellere logolar ve logo türleri ekleme belirtimleri açıklanır.

> [!NOTE]
> Logolara yalnızca düzenleme modunda izin verilir. Logolar görüntüleme modunda gösterilemez.

![tanımlar](media/office-store-in-app-purchase-visual-guidelines/definitions.png)

![saklanacak öğeler](media/office-store-in-app-purchase-visual-guidelines/things-to-keep-in-mind.png)

![öğeler](media/office-store-in-app-purchase-visual-guidelines/things-to-avoid.png)

![boyut ve biçim ](media/office-store-in-app-purchase-visual-guidelines/size-and-format.png)

![kenar boşlukları ve](media/office-store-in-app-purchase-visual-guidelines/margins-and-sizes.png)

![düzenleme modu](media/office-store-in-app-purchase-visual-guidelines/logos-in-edit-mode.png)

## <a name="best-practices"></a>En iyi yöntemler

### <a name="visual-landing-page"></a>Görsel giriş sayfası

Görselinizi nasıl kullanabilecekleri ve lisansı nereden satın alabilecekleri konusunda kullanıcıları bilgilendirmek için giriş sayfasını kullanın. Otomatik olarak tetiklenen videolar eklemeyin. Lisans satın alma ayrıntılarıyla ilgili bilgiler veya bağlantılar ve IAP özelliklerinin kullanımı gibi, yalnızca kullanıcı deneyimini geliştirmeye yardımcı olacak malzemeleri ekleyin.

### <a name="license-key-and-token"></a>Lisans anahtarı ve belirteci

Kullanıcıya kolaylık sağlamak için, biçim bölmesinin üst kısmına lisans anahtarı veya belirteciyle ilgili alanları ekleyin. Böylelikle kullanıcılar bunlara daha kolay ulaşabilir.

## <a name="faq"></a>SSS

Daha fazla bilgi edinmek ve sorularınıza yanıt bulmak için [Ek satın almalar gerektiren görseller hakkında sık sorulan sorular](https://docs.microsoft.com/en-us/power-bi/power-bi-custom-visuals-faq#visuals-with-additional-purchases) bağlantısını ziyaret edin.

## <a name="next-steps"></a>Sonraki adımlar

Özel görselinizi diğer kullanıcıların keşfetmesi ve kullanması amacıyla [AppSource](office-store.md)'ta nasıl yayımlayabileceğinizi öğrenin.
