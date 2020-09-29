---
title: Power BI ile Microsoft Teams’de işbirliği yapma
description: Dağıtılmış iş gücü norm haline geldikçe daha fazla kuruluş, uzaktan çalışmaya olanak vermek ve çalışanların senkronizasyonunu sağlamak için Microsoft Teams kullanıyor.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
LocalizationGroup: Share your work
ms.date: 09/15/2020
ms.openlocfilehash: d0510a3c8caf2e07034b9410d4338431670833e5
ms.sourcegitcommit: b3d32b8a4ce26fba7fdb5f1c5954d2b2e426503c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/22/2020
ms.locfileid: "91005503"
---
# <a name="collaborate-in-microsoft-teams-with-power-bi"></a>Power BI ile Microsoft Teams’de işbirliği yapma

Dağıtılmış iş gücü norm haline geldikçe daha fazla kuruluş, uzaktan çalışmaya olanak vermek ve çalışanların senkronizasyonunu sağlamak için Microsoft Teams kullanıyor. Microsoft Teams kanallarında ve sohbetlerinde etkileşimli Power BI içeriğini paylaşmaya ve bu içerik üzerinde işbirliği yapmaya yönelik seçenekler bu makalede özetlenmiştir. 

- Microsoft Teams için **Power BI sekmesi** sayesinde [etkileşimli raporları Microsoft Teams kanallarına ve sohbetlerine ekleyebilirsiniz](service-embed-report-microsoft-teams.md). Power BI sekmesi iş arkadaşlarınızın ekibinizin verilerini bulmasına ve verileri ekip kanalınızda tartışmalarına yardımcı olur. 
- Microsoft Teams ileti kutusuna raporlarınızın, panolarınızın ve uygulamalarınızın bağlantılarını yapıştırdığınızda bir [bağlantı önizlemesi](service-teams-link-preview.md) oluşturun. Bağlantı önizlemesi bağlantı ile ilgili bilgileri gösterir. 
- Microsoft Teams’de konuşmaları hemen başlatmak için Power BI hizmetinde raporları ve panoları görüntülerken [Microsoft Teams’de Paylaş](service-share-report-teams.md)’ı kullanın.
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

## <a name="known-issues-and-limitations"></a>Bilinen sorunlar ve sınırlamalar

- Power BI, Microsoft Teams ile aynı yerelleştirilmiş dilleri desteklemez. Bu nedenle, eklenen rapordaki yerelleştirme doğru olmayabilir.
- Power BI panoları, Microsoft Teams için **Power BI** sekmesine eklenemez.
- Power BI lisansına veya rapora erişim izni olmayan kullanıcılar “İçerik kullanılamıyor” iletisiyle karşılaşır.
- Internet Explorer 10 kullanıyorsanız sorunlarla karşılaşabilirsiniz. <!--You can look at the [browsers support for Power BI](../consumer/end-user-browsers.md) and for [Microsoft 365](https://products.office.com/office-system-requirements#Browsers-section). -->
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
- [Power BI hizmetinden doğrudan Microsoft Teams’de paylaşma](service-share-report-teams.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/).
