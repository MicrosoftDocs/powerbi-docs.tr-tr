---
title: Power BI’da özel kuruluş görselleri
description: Power BI'da özel kuruluş görsellerini kullanma, yönetme ve oluşturma
author: sranins
ms.author: rasala
manager: kfile
ms.reviewer: maghan
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 12/11/2018
LocalizationGroup: Visualizations
ms.openlocfilehash: 157b20107a5be106ac97e0cb927b1e496e1ba115
ms.sourcegitcommit: d0abedcf07f964418c9e5ea8d8ee3338b0b97a50
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57695093"
---
# <a name="organizational-custom-visuals-in-power-bi"></a>Power BI’da özel kuruluş görselleri

Power BI'da özel görselleri kullanarak size göre uyarlanmış benzersiz türde bir görsel oluşturabilirsiniz. Özel görseller geliştiriciler tarafından, Power BI’a eklenmiş olan zengin görsellerin gereksinimlerini tam olarak karşılamadığı durumlarda oluşturulur.

Bazı kuruluşlarda özel görseller daha da önemlidir ve bunlar kuruluşa özgü verilerin ya da bilgilerin aktarılması için gerekli olabilir, özel veri gereksinimlerine sahip olabilir ya da özel iş yöntemlerini vurgulayabilir. Bu durumdaki kuruluşların özel görseller geliştirmesi, kuruluş genelinde paylaşması ve bakımlarının düzgün yapıldığından emin olması gerekir. Power BI özel görselleri, kuruluşların tam olarak bunu yapmasına olanak sağlar.

Aşağıdaki resimde, Power BI’daki özel kuruluş görsellerinin yöneticiden başlayıp geliştirme ve bakım aşamalarından geçerek veri analistinde sonlanan akış süreci gösterilmektedir.

![Özel görsel resmi](media/power-bi-custom-visuals-organizational/custom-visual-org-01.jpg)

Kuruluş görselleri, Power BI yöneticisi tarafından Yönetim portalından dağıtılır ve yönetilir. Görsel kuruluş deposuna dağıtıldıktan sonra kuruluştaki kullanıcılar bunları doğrudan Power BI Desktop’tan kolayca keşfedebilir ve özel kuruluş görsellerini raporlarında içeri aktarabilir.

Oluşturduğunuz raporlarda özel kuruluş görsellerini kullanma hakkında daha fazla bilgi için şu makaleye bakın: [Kuruluş görsellerini raporlarınızda içeri aktarma hakkında daha fazla bilgi](power-bi-custom-visuals.md).

## <a name="administer-organizational-custom-visuals"></a>Özel kuruluş görsellerini yönetme

Kuruluşunuzda özel kuruluş görsellerini yönetme, dağıtma ve yönetme hakkında daha fazla bilgi edinmek için şu makaleye bakın: [Özel kuruluş görsellerinin dağıtımı ve yönetimi hakkında daha fazla bilgi](https://go.microsoft.com/fwlink/?linkid=866790).

> [!WARNING]
> Özel bir görsel, güvenlik veya gizlilik riski taşıyan kod içerebilir. Bir özel görseli kuruluş deposuna dağıtmadan önce görselin yazarına ve kaynağına güvendiğinizden emin olun.

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

Bilmeniz gereken birçok önemli nokta ve sınırlama vardır.

Yönetici:

* Eski özel görseller (yeni sürümü oluşturulan API'leri temel almayan özel görseller gibi) desteklenmez

* Özel bir görsel depodan silinirse, silinen görseli kullanan tüm mevcut raporlar işlenmeyi durdurur. Depodan silme işlemi geri alınamaz. Özel bir görseli geçici olarak devre dışı bırakmak için "Devre dışı bırak" özelliğini kullanın.

Son kullanıcı:

* Özel kuruluş görselleri, kuruluş deposundan içeri aktarılan özel görsellerdir. Tüm özel görsellerde olduğu gibi [PowerPoint’e aktarılamaz](https://docs.microsoft.com/power-bi/consumer/end-user-powerpoint) veya kullanıcı [rapor sayfalarına abone olduğunda](https://docs.microsoft.com/power-bi/consumer/end-user-subscribe) gönderilen e-postalarda görüntülenmez. Bu özellikler yalnızca doğrudan marketten içeri aktarılmış olan [sertifikalı özel görseller](https://docs.microsoft.com/power-bi/power-bi-custom-visuals-certified) için kullanılabilir.

* AppSource marketten alınan Visio görseli, PowerApps görseli, Mapbox görseli ve GlobeMap görseli kuruluş deposu aracılığıyla dağıtılırsa gösterilmez.

## <a name="troubleshoot"></a>Sorun giderme

Sorun giderme hakkında bilgi için [Power BI özel görsellerinizin sorunlarını giderme](power-bi-custom-visuals-troubleshoot.md) bağlantısını ziyaret edin.

## <a name="faq"></a>SSS

Daha fazla bilgi edinmek ve sorularınıza yanıt bulmak için [Power BI özel görselleri hakkında sık sorulan sorular](power-bi-custom-visuals-faq.md#organizational-custom-visuals) bağlantısını ziyaret edin.

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/).
