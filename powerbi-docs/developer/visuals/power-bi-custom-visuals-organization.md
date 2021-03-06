---
title: Daha iyi tümleşik BI içgörüleri için, Power BI tümleşik analizlerinde Power BI kuruluş görselleri
description: Power BI'da kuruluş görsellerini kullanma, yönetme ve oluşturma. Power BI tümleşik analiz kullanarak daha iyi tümleşik BI içgörüleri elde edin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 12/11/2018
LocalizationGroup: Visualizations
ms.openlocfilehash: 908225c772aee7e5697ba828c55b96f74c204c1d
ms.sourcegitcommit: eeaf607e7c1d89ef7312421731e1729ddce5a5cc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2021
ms.locfileid: "97888156"
---
# <a name="organizational-visuals-in-power-bi"></a>Power BI’da kuruluşlara yönelik görseller

Power BI’da Power BI görsellerini kullanarak size göre uyarlanmış benzersiz türde bir görsel oluşturabilirsiniz. Power BI görselleri geliştiriciler tarafından, Power BI’a eklenmiş olan zengin görsellerin gereksinimlerini tam olarak karşılamadığı durumlarda oluşturulur.

Bazı kuruluşlarda Power BI görselleri daha da önemlidir ve bunlar kuruluşa özgü verilerin ya da bilgilerin aktarılması için gerekli olabilir, özel veri gereksinimlerine sahip olabilir ya da özel iş yöntemlerini vurgulayabilir. Bu durumdaki kuruluşların Power BI görselleri geliştirmesi, kuruluş genelinde paylaşması ve bakımlarının düzgün yapıldığından emin olması gerekir. Power BI görselleri, kuruluşların tam olarak bunu yapmasına olanak sağlar.

Aşağıdaki resimde, Power BI’daki Power BI kuruluş görsellerinin yöneticiden başlayıp geliştirme ve bakım aşamalarından geçerek veri analistinde sonlanan akış süreci gösterilmektedir.

![Özel görsel resmi](media/power-bi-custom-visuals-organizational/custom-visual-org-01.jpg)

Kuruluş görselleri, Power BI yöneticisi tarafından Yönetim portalından dağıtılır ve yönetilir. Görsel kuruluş deposuna dağıtıldıktan sonra kuruluştaki kullanıcılar bunları doğrudan Power BI Desktop’tan kolayca keşfedebilir ve Power BI kuruluş görsellerini raporlarında içeri aktarabilir.

Oluşturduğunuz raporlarda Power BI kuruluş görsellerini kullanma hakkında daha fazla bilgi için şu makaleye bakın: [Kuruluş görsellerini raporlarınızda içeri aktarma hakkında daha fazla bilgi](power-bi-custom-visuals.md).

## <a name="administer-organizational-power-bi-visuals"></a>Power BI kuruluş görsellerini yönetme

Kuruluşunuzda Power BI kuruluş görsellerini yönetme, dağıtma ve yönetme hakkında daha fazla bilgi edinmek için şu makaleye bakın: [Power BI kuruluş görsellerinin dağıtımı ve yönetimi hakkında daha fazla bilgi](../../admin/organizational-visuals.md).

> [!WARNING]
> Bir dosyadan yüklenen Power BI görseli, güvenlik veya gizlilik riski taşıyan kod içerebilir. Power BI görseli dosyasını kuruluş deposuna dağıtmadan önce görselin yazarına ve kaynağına güvendiğinizden emin olun.

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

Bilmeniz gereken birçok önemli nokta ve sınırlama vardır.

Yönetici:

* AppSource’tan veya bir dosyadan yüklenen Power BI görseli depodan silinirse silinen görseli kullanan tüm mevcut raporlar işlenmeyi durdurur. Depodan silme işlemi geri alınamaz. AppSource’tan veya bir dosyadan Power BI görseli yüklemeyi geçici olarak devre dışı bırakmak için “Devre Dışı Bırak” özelliğini kullanın.

* Power BI kuruluş görselleri, Power BI Rapor Sunucusu’nda desteklenmez.

Son kullanıcı:

* Power BI kuruluş görselleri, kuruluş deposundan içeri aktarılan özel görsellerdir. Tüm özel görsellerde olduğu gibi [PowerPoint’e aktarılamaz](../../consumer/end-user-powerpoint.md) veya kullanıcı [rapor sayfalarına abone olduğunda](../../consumer/end-user-subscribe.md) gönderilen e-postalarda görüntülenmez. Bu özellikler yalnızca doğrudan marketten içeri aktarılmış olan [sertifikalı Power BI görselleri](power-bi-custom-visuals-certified.md) için kullanılabilir.

* AppSource marketten alınan Visio görseli, PowerApps görseli, Mapbox görseli ve GlobeMap görseli kuruluş deposu aracılığıyla dağıtılırsa gösterilmez.

## <a name="troubleshoot"></a>Sorun giderme

Sorun giderme hakkında bilgi için [Power BI görsellerinizin sorunlarını giderme](power-bi-custom-visuals-troubleshoot.md) bağlantısını ziyaret edin.

## <a name="faq"></a>SSS

Daha fazla bilgi edinmek ve sorularınıza yanıt bulmak için [Power BI görselleri hakkında sık sorulan sorular](power-bi-custom-visuals-faq.md#organizational-power-bi-visuals) bağlantısını ziyaret edin.

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/).