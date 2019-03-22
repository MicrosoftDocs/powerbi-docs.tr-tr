---
title: Power BI görsellerinin yönergeleri
description: Özel görselinizi diğer kullanıcıların keşfetmesi ve satın alma yoluyla kullanması amacıyla AppSource'ta nasıl yayımlayabileceğinizi öğrenin.
author: sranins
ms.author: rasala
manager: kfile
ms.reviewer: maghan
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 03/10/2019
ms.openlocfilehash: 02ce5146a154583d784de8030a0b0ec84740fcb3
ms.sourcegitcommit: 8fda7843a9f0e8193ced4a7a0e5c2dc5386059a6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/18/2019
ms.locfileid: "58175491"
---
# <a name="guidelines-for-power-bi-visuals"></a>Power BI görselleri için yönergeler

## <a name="guidelines-for-power-bi-visuals-with-additional-purchases"></a>Ek satın almalarla Power BI görsellerine ilişkin yönergeler

Yakın zamana kadar, Market (AppSource) yalnızca ücretsiz olan Power BI görsellerini kabul ediyordu. Bu ilke değiştirildi (18 Aralık) ve AppSource'a "ek satın alma işlemleri gerekebilir" fiyat etiketine sahip görseller de gönderebilmeniz mümkün hale getirildi. 

"Ek satın alma işlemleri gerekebilir" etiketine sahip görseller, Office Mağazası'ndaki uygulama için satın alma (IAP) eklentilerine benzer. Geliştiriciler bu görselleri, AppSource ekibi onayladıktan ve sertifika gereksinimlerine uyduğundan emin olduktan sonra da sertifikasyon için gönderebilir. Gereksinimler hakkında daha fazla bilgi için bkz. [Sertifikalı özel görseller](../power-bi-custom-visuals-certified.md).

> [!NOTE]
> Görselin sertifikalanması için, dış hizmetlere veya kaynaklara erişmemesi gerekir.

>[!IMPORTANT]  
> Görselinizi ücretsizden "Ek satın alma işlemleri gerekebilir" düzeyine güncelleştirmek için kullanıcıların güncelleştirme öncesiyle aynı ücretsiz işlevsellik düzeyini elde etmesi gerekir. Var olan ücretsiz özelliklerin üzerine isteğe bağlı olarak gelişmiş ücretli özellikler ekleyebilirsiniz. Var olan ücretsiz görselleri güncelleştirmek yerine, gelişmiş özellikler içeren IAP görsellerini yeni görseller olarak göndermenizi öneririz.


## <a name="what-changed-in-the-submission-process"></a>Gönderim işleminde neler değişti?

Geliştiriciler, ücretsiz görseller için yaptıkları gibi Satıcı Panosu üzerinden IAP görsellerini AppSource'a yüklerler. Gönderilen görselin IAP özelliklerine sahip olduğunu belirtmek için, geliştiricilerin Satıcı Panosu'na "Uygulama içi satın alma özellikli görsel" yazması gerekir. Ayrıca, doğrulama ekibinin IAP özelliklerini doğrulayabilmesi için geliştiriciler bir lisans anahtarı veya belirteç sağlamalıdır. Görsel doğrulandıktan ve onaylandıktan sonra, IAP görseli için AppSource listesinde, fiyat seçeneklerinin altında "Ek satın alma işlemleri gerekebilir" belirtimi yer alır.

## <a name="what-is-a-power-bi-visual-with-iap-features"></a>IAP özelliklerine sahip Power BI görseli nedir?

IAP görseli, **ücretsiz özelliklere** sahip **ücretsiz** bir görseldir. Çalıştırmak için ek ücret gerektiren gelişmiş özelliklere de sahip olabilir. Geliştiricilerin, görselin açıklamasında çalıştırmak için ek satın almalar gereken özellikleri kullanıcılara bildirmesi gerekir. Şu anda Microsoft, uygulama içinde ve eklentilerde satın almayı desteklemek için yerel API'ler sağlamamaktadır.

Geliştiriciler söz konusu satın almalarda üçüncü taraf bir ödeme sistemi kullanabilir. Daha fazla bilgi için [mağaza ilkemize](https://docs.microsoft.com/office/dev/store/validation-policies#2-apps-or-add-ins-can-display-certain-ads) bakın.

> [!NOTE]
> Ücretsiz özelliklerde veya ücretsiz görsellerde filigranlara izin verilmez. Filigranlar yalnızca geçerli bir lisans olmadan kullanılan ücretli özelliklerde kullanılabilir. Gelişmiş ücretli özellikler geçerli bir lisans olmadan kullanılıyorsa, lisansla ilgili tüm bilgileri içeren bir açılır pencere görüntülenmesini öneririz.  

## <a name="logo-guidelines"></a>Logo yönergeleri

Bu bölümde, görsellere logolar ve logo türleri ekleme belirtimleri açıklanır.

> [!IMPORTANT]
> Logolara **yalnızca düzenleme modunda** izin verilir. Logolar görüntüleme modunda **gösterilemez**.

![Tanımlar](media/office-store-in-app-purchase-visual-guidelines/definitions.png)

![Akılda tutulması gereken noktalar](media/office-store-in-app-purchase-visual-guidelines/things-to-keep-in-mind.png)

![Yapılmaması gerekenler](media/office-store-in-app-purchase-visual-guidelines/things-to-avoid.png)

![Boyut ve biçim](media/office-store-in-app-purchase-visual-guidelines/size-and-format.png)

![Kenar boşlukları ve boyutlandırma](media/office-store-in-app-purchase-visual-guidelines/margins-and-sizes.png)

![Düzenleme modu](media/office-store-in-app-purchase-visual-guidelines/logos-in-edit-mode.png)

## <a name="best-practices"></a>En iyi yöntemler

### <a name="visual-landing-page"></a>Görsel giriş sayfası

Görselinizi nasıl kullanabilecekleri ve lisansı nereden satın alabilecekleri konusunda kullanıcıları bilgilendirmek için giriş sayfasını kullanın. Otomatik olarak tetiklenen videolar eklemeyin. Lisans satın alma ayrıntılarıyla ilgili bilgiler veya bağlantılar ve IAP özelliklerinin kullanımı gibi, yalnızca kullanıcı deneyimini geliştirmeye yardımcı olacak malzemeleri ekleyin.

### <a name="license-key-and-token"></a>Lisans anahtarı ve belirteci

Kullanıcıya kolaylık sağlamak için, biçim bölmesinin üst kısmına lisans anahtarı veya belirteciyle ilgili alanları ekleyin.

## <a name="faq"></a>SSS

Görseller hakkında daha fazla bilgi için bkz. [Ek satın almalar gerektiren görseller hakkında sık sorulan sorular](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-faq#visuals-with-additional-purchases).

## <a name="next-steps"></a>Sonraki adımlar

Özel görselinizi diğer kullanıcıların keşfetmesi ve kullanması amacıyla [AppSource](office-store.md)'ta nasıl yayımlayabileceğinizi öğrenin.