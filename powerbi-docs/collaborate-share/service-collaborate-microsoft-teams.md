---
title: Power BI ile Microsoft Teams’de işbirliği yapma
description: Dağıtılmış iş gücü norm haline geldikçe daha fazla kuruluş, uzaktan çalışmaya olanak vermek ve çalışanların senkronizasyonunu sağlamak için Microsoft Teams kullanıyor.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: pbi-collaborate-share
ms.topic: conceptual
LocalizationGroup: Share your work
ms.date: 12/14/2020
ms.openlocfilehash: 7c8fa59521be1cfc8bb25fb04c3904f257fb62be
ms.sourcegitcommit: 932f6856849c39e34229dc9a49fb9379c56a888a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/06/2021
ms.locfileid: "97926701"
---
# <a name="collaborate-in-microsoft-teams-with-power-bi"></a>Power BI ile Microsoft Teams’de işbirliği yapma

Dağıtılmış iş gücü norm haline geldikçe daha fazla kuruluş, uzaktan çalışmaya olanak vermek ve çalışanların senkronizasyonunu sağlamak için Microsoft Teams kullanıyor. Microsoft Teams kanallarında ve sohbetlerinde etkileşimli Power BI içeriğini paylaşmaya ve bu içerik üzerinde işbirliği yapmaya yönelik seçenekler bu makalede özetlenmiştir. 

- Microsoft Teams için **Power BI sekmesi** sayesinde [etkileşimli raporları Microsoft Teams kanallarına ve sohbetlerine ekleyebilirsiniz](service-embed-report-microsoft-teams.md). Power BI sekmesi iş arkadaşlarınızın ekibinizin verilerini bulmasına ve verileri ekip kanalınızda tartışmalarına yardımcı olur. 
- Microsoft Teams ileti kutusuna raporlarınızın, panolarınızın ve uygulamalarınızın bağlantılarını yapıştırdığınızda bir [bağlantı önizlemesi](service-teams-link-preview.md) oluşturun. Bağlantı önizlemesi bağlantı ile ilgili bilgileri gösterir. 
- Microsoft Teams’de konuşmaları hemen başlatmak için Power BI hizmetinde raporları ve panoları görüntülerken [Microsoft Teams’de Sohbet](service-share-report-teams.md)’i kullanın.
- Temel Power BI hizmeti deneyiminizin tamamını Microsoft Teams’e aktarmak için [Microsoft Teams’deki Power BI uygulamasını](service-microsoft-teams-app.md) kullanın.
 
:::image type="content" source="media/service-collaborate-microsoft-teams/power-bi-embed-teams-report.png" alt-text="Microsoft Teams kanalına eklenmiş Power BI raporunun ekran görüntüsü.":::

## <a name="requirements"></a>Gereksinimler

Genel olarak Power BI’ın Microsoft Team’de çalışması için şunlardan emin olmalısınız:

- Kullanıcılarınızın bir Power BI Pro lisansına sahip olması veya raporun Power BI lisansına sahip bir [Power BI Premium kapasite (EM veya P SKU)](../admin/service-premium-what-is.md) içinde yer alması.
- Kullanıcıların, Power BI lisansını etkinleştirmek için Power BI hizmetinde oturum açmış olması.
- Kullanıcıların, Microsoft Teams’de **Power BI** sekmesini kullanma gereksinimlerini karşılaması.

## <a name="grant-access-to-reports"></a>Raporlara erişim verme

Bir raporu Microsoft Teams’e eklediğinizde veya bir öğeye bağlantı gönderdiğinizde, kullanıcılara raporu görüntüleme izni otomatik olarak verilmez. [Kullanıcıların raporu Power BI’da görüntülemesine izin vermeniz](service-share-dashboards.md) gerekir. Bu işlemi kolaylaştırmak isterseniz ekibiniz için bir Microsoft 365 Grubu kullanabilirsiniz.

> [!IMPORTANT]
> Power BI hizmetinde, raporu görebilecek olan kullanıcıları belirleyip listede olmayanlara erişim izni vermeyi unutmayın.

Ekipteki herkesin raporlara erişmesini sağlamak için raporları tek bir çalışma alanına yerleştirip ekibinizin Microsoft 365 Grubuna erişim izni verebilirsiniz.

## <a name="share-with-external-users"></a>Dış kullanıcılarla paylaşma

Power BI raporlarını Teams ile tümleştirebilir ve dış kullanıcılarla paylaşabilirsiniz. İzlenmesi gereken adımlar şunlardır.

1.  Dış kullanıcıyı kuruluşa davet edersiniz ve bu kişi davetinizi kabul eder. Ayrıntılar için bkz. [Azure Active Directory B2B'yi kullanarak Power BI içeriğini dış konuk kullanıcılara dağıtma](../guidance/whitepaper-azure-b2b-power-bi.md).
2.  Rapora dış kullanıcı izni verin. Bireysel izinler atama en iyi sonucu verir.
3.  Dış kullanıcının kendisine atanmış bir Power BI lisansı olduğundan emin olun. İçerik bir Premium kapasitede ise, kullanıcının yalnızca Ücretsiz bir lisansa ihtiyacı vardır. Değilse, kullanıcı bir [Power BI Pro ücretsiz deneme sürümüne kaydolabilir](../fundamentals/service-self-service-signup-for-power-bi.md#sign-up-for-an-individual-trial-of-power-bi-pro).

## <a name="known-issues-and-limitations"></a>Bilinen sorunlar ve sınırlamalar

- Power BI, Microsoft Teams ile aynı yerelleştirilmiş dilleri desteklemez. Bu nedenle, eklenen rapordaki yerelleştirme doğru olmayabilir.
- Power BI panoları, Microsoft Teams için **Power BI** sekmesine eklenemez.
- Power BI lisansına veya rapora erişim izni olmayan kullanıcılar “İçerik kullanılamıyor” iletisiyle karşılaşır.
- Internet Explorer 10 kullanıyorsanız sorunlarla karşılaşabilirsiniz. <!--You can look at the [browsers support for Power BI](../fundamentals/power-bi-browsers.md) and for [Microsoft 365](https://products.office.com/office-system-requirements#Browsers-section). -->
- Microsoft Teams için **Power BI** sekmesinde [URL filtreleri](service-url-filters.md) desteklenmez.
- Yeni **Power BI** sekmesi ulusal bulutlarda kullanılamaz. Power BI uygulamalarındaki yeni çalışma alanı deneyimini veya raporları desteklemeyen eski bir sürüm kullanılabilir.
- Sekmeyi kaydettikten sonra, sekme ayarlarından sekme adı değiştirilemez. Değiştirmek için **Yeniden adlandır** seçeneğini kullanın.
- Bağlantı önizleme hizmetinde çoklu oturum açma desteklenmez.
- Bağlantı önizlemeleri, toplantı sohbetinde veya özel kanallarda çalışmaz.

## <a name="microsoft-power-platform-in-microsoft-teams"></a>Microsoft Teams’deki Microsoft Power Platform

Diğer Microsoft Power Platform uygulamaları da Microsoft Teams ile tümleşir.

- [Power Platform yönetici deneyimi](/power-platform/admin/about-teams-environment)
- [Power Automate](/power-automate/teams/overview)
- [Power Apps](/powerapps/teams/overview)
- [Power Virtual Agents](/power-virtual-agents/)

## <a name="next-steps"></a>Sonraki adımlar

- [Microsoft Teams’e Power BI içeriği ekleme](service-embed-report-microsoft-teams.md)
- [Microsoft Teams’de Power BI bağlantı önizlemesi alma](service-teams-link-preview.md)
- [Doğrudan Power BI hizmetinden Microsoft Teams'de sohbet](service-share-report-teams.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/).
