---
title: Power BI görsellerinin yönergeleri
description: Özel görselinizi diğer kullanıcıların keşfetmesi ve satın alma yoluyla kullanması amacıyla AppSource'ta nasıl yayımlayabileceğinizi öğrenin.
author: KesemSharabi
ms.author: kesharab
manager: rkarlin
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 07/16/2019
ms.openlocfilehash: 4e17406b0b4e616a9857cf40298a7931e2b65427
ms.sourcegitcommit: b7a9862b6da940ddebe61bc945a353f91cd0e4bd
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2019
ms.locfileid: "71944851"
---
# <a name="guidelines-for-power-bi-visuals"></a>Power BI görselleri için yönergeler
Görselinizi başkalarının bulması ve kullanması amacıyla AppSource’ta [yayımlamadan](https://docs.microsoft.com/power-bi/developer/office-store) önce kullanıcılarınıza yönelik harika bir deneyim oluşturmak için aşağıdaki yönergeleri izlediğinizden emin olun. 

## <a name="context-menu"></a>Bağlam menüsü
Bağlam menüsü, kullanıcı imlecini bir görselin üzerine getirdiğinde görüntülenen sağ tıklama menüsüdür.
Birleşik bir deneyim sunmak için tüm Power BI görsellerinde bağlam menüsü etkinleştirmelidir. Bağlam menüsü eklemeyi öğrenmek için lütfen [bu makaleye](https://github.com/Microsoft/PowerBI-visuals/blob/gh-pages/tutorials/building-bar-chart/adding-context-menu-to-the-bar.md) bakın.


## <a name="logo-guidelines"></a>Logo yönergeleri
> [!NOTE]
> Bu makalede logo sözcüğü aşağıdaki resimlerde açıklandığı gibi herhangi bir ticari şirket logosu için kullanılır. 

Bu bölümde, Power BI görsellerine logo ekleme belirtimleri açıklanır. Amblemler zorunlu değildir. Eklendiyse, bu kurallara uymalıdır. 

> [!IMPORTANT]
> Logolara *yalnızca düzenleme modunda* izin verilir. Logolar görüntüleme modunda *gösterilemez*.


![Tanımlar](media/guidelines-powerbi-visuals/definitions.png)

![Akılda tutulması gereken noktalar](media/guidelines-powerbi-visuals/things-to-keep-in-mind.png)

![Yapılmaması gerekenler](media/guidelines-powerbi-visuals/things-to-avoid.png)

![Boyut ve biçim](media/guidelines-powerbi-visuals/size-and-format.png)

![Kenar boşlukları ve boyutlandırma](media/guidelines-powerbi-visuals/margins-and-sizes.png)

![Düzenleme modu](media/guidelines-powerbi-visuals/logos-in-edit-mode.png)


Bilgi verici simgeler varsa, bunlar okuma modunda renk, boyut ve konum açısından yukarıdaki logolarla uyumlu olmalıdır.

## <a name="guidelines-for-power-bi-visuals-with-additional-purchases"></a>Ek satın almalarla Power BI görsellerine ilişkin yönergeler

Yakın zamana kadar, Market (AppSource) yalnızca ücretsiz olan Power BI görsellerini kabul ediyordu. Bu ilke değiştirildi (18 Aralık) ve AppSource'a "ek satın alma işlemleri gerekebilir" fiyat etiketine sahip görseller de gönderebilmeniz mümkün hale getirildi. 

"Ek satın alma işlemleri gerekebilir" etiketine sahip görseller, Office Mağazası'ndaki uygulama için satın alma (IAP) eklentilerine benzer. Geliştiriciler bu görselleri, AppSource ekibi onayladıktan ve sertifika gereksinimlerine uyduğundan emin olduktan sonra da sertifikasyon için gönderebilir. Gereksinimler hakkında daha fazla bilgi için bkz. [Sertifikalı Power BI görselleri](../power-bi-custom-visuals-certified.md).

> [!NOTE]
> Görselin sertifikalanması için, dış hizmetlere veya kaynaklara erişmemesi gerekir.

>[!IMPORTANT]  
> Görselinizi ücretsizden "Ek satın alma işlemleri gerekebilir" düzeyine güncelleştirmek için kullanıcıların güncelleştirme öncesiyle aynı ücretsiz işlevsellik düzeyini elde etmesi gerekir. Var olan ücretsiz özelliklerin üzerine isteğe bağlı olarak gelişmiş ücretli özellikler ekleyebilirsiniz. Var olan ücretsiz görselleri güncelleştirmek yerine, gelişmiş özellikler içeren IAP görsellerini yeni görseller olarak göndermenizi öneririz.

## <a name="what-changed-in-the-submission-process"></a>Gönderim işleminde neler değişti?

Geliştiriciler, ücretsiz görseller için yaptıkları gibi Satıcı Panosu üzerinden IAP görsellerini AppSource'a yüklerler. Gönderilen görselin IAP özelliklerine sahip olduğunu belirtmek için, geliştiricilerin Satıcı Panosu'na "Uygulama içi satın alma özellikli görsel" yazması gerekir. Ayrıca, doğrulama ekibinin IAP özelliklerini doğrulayabilmesi için geliştiriciler bir lisans anahtarı veya belirteç sağlamalıdır. Görsel doğrulandıktan ve onaylandıktan sonra, IAP görseli için AppSource listesinde, fiyat seçeneklerinin altında "Ek satın alma işlemleri gerekebilir" belirtimi yer alır.

## <a name="what-is-a-power-bi-visual-with-iap-features"></a>IAP özelliklerine sahip Power BI görseli nedir?

IAP görseli, *ücretsiz özelliklere* sahip *ücretsiz* bir görseldir. Çalıştırmak için ek ücret gerektiren gelişmiş özelliklere de sahip olabilir. Geliştiricilerin, görselin açıklamasında çalıştırmak için ek satın almalar gereken özellikleri kullanıcılara bildirmesi gerekir. Şu anda Microsoft, uygulama içinde ve eklentilerde satın almayı desteklemek için yerel API'ler sağlamamaktadır.

Geliştiriciler söz konusu satın almalarda üçüncü taraf bir ödeme sistemi kullanabilir. Daha fazla bilgi için [mağaza ilkemize](https://docs.microsoft.com/office/dev/store/validation-policies#2-apps-or-add-ins-can-display-certain-ads) bakın.

> [!NOTE]
> Ücretsiz özelliklerde veya ücretsiz görsellerde filigranlara izin verilmez. Filigranlar yalnızca geçerli bir lisans olmadan kullanılan ücretli özelliklerde kullanılabilir. Gelişmiş ücretli özellikler geçerli bir lisans olmadan kullanılıyorsa, lisansla ilgili tüm bilgileri içeren bir açılır pencere görüntülenmesini öneririz.  


## <a name="best-practices"></a>En iyi yöntemler

### <a name="visual-landing-page"></a>Görsel giriş sayfası

Görselinizi nasıl kullanabilecekleri ve lisansı nereden satın alabilecekleri konusunda kullanıcıları bilgilendirmek için giriş sayfasını kullanın. Otomatik olarak tetiklenen videolar eklemeyin. Lisans satın alma ayrıntılarıyla ilgili bilgiler veya bağlantılar ve IAP özelliklerinin kullanımı gibi, yalnızca kullanıcı deneyimini geliştirmeye yardımcı olacak malzemeleri ekleyin.

### <a name="license-key-and-token"></a>Lisans anahtarı ve belirteci

Kullanıcıya kolaylık sağlamak için, biçim bölmesinin üst kısmına lisans anahtarı veya belirteciyle ilgili alanları ekleyin.

## <a name="faq"></a>SSS

Görseller hakkında daha fazla bilgi için bkz. [Ek satın almalar gerektiren görseller hakkında sık sorulan sorular](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-faq#visuals-with-additional-purchases).

## <a name="next-steps"></a>Sonraki adımlar

Özel görselinizi diğer kullanıcıların keşfetmesi ve kullanması amacıyla [AppSource](office-store.md)'ta nasıl yayımlayabileceğinizi öğrenin.
