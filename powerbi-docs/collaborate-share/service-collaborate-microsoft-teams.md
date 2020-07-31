---
title: Power BI ile Microsoft Teams’de işbirliği yapma
description: Microsoft Teams kanallarında ve sohbetlerinde Power BI içeriğini kolayca paylaşabilir ve içerik üzerinde işbirliği yapabilirsiniz.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
LocalizationGroup: Share your work
ms.date: 07/22/2020
ms.openlocfilehash: 17a0879dac416a98d214ed11861947cb2c311487
ms.sourcegitcommit: 65025ab7ae57e338bdbd94be795886e5affd45b4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87254298"
---
# <a name="collaborate-in-microsoft-teams-with-power-bi"></a>Power BI ile Microsoft Teams’de işbirliği yapma

Microsoft Teams kanallarında ve sohbetlerinde etkileşimli Power BI içeriğini paylaşmak ve bu içerik üzerinde işbirliği yapmak için çeşitli seçenekleriniz vardır. 

- Microsoft Teams için **Power BI** sekmesi sayesinde [etkileşimli raporları Microsoft Teams kanallarına ve sohbetlerine ekleyebilirsiniz](service-embed-report-microsoft-teams.md). **Power BI** sekmesi iş arkadaşlarınızın ekibinizin verilerini bulmasına ve verileri ekip kanalınızda tartışmalarına yardımcı olur. 
- Microsoft Teams ileti kutusuna raporlarınızın, panolarınızın ve uygulamalarınızın bağlantılarını yapıştırdığınızda bir [bağlantı önizlemesi](service-teams-link-preview.md) oluşturun. Bağlantı önizlemesi bağlantı ile ilgili bilgileri gösterir. 
- Teams’de konuşmaları hemen başlatmak için Power BI hizmetinde raporları ve panoları görüntülerken [Teams’de Paylaş](service-share-report-teams.md)’ı kullanın.
 
:::image type="content" source="media/service-collaborate-microsoft-teams/power-bi-embed-teams-report.png" alt-text="Teams kanalına eklenmiş Power BI raporunun ekran görüntüsü.":::

## <a name="requirements"></a>Gereksinimler

Genel olarak Power BI’ın Microsoft Team’de çalışması için şunlardan emin olmalısınız:

- Kullanıcılarınızın bir Power BI Pro lisansına sahip olması veya raporun Power BI lisansına sahip bir [Power BI Premium kapasite (EM veya P SKU)](../admin/service-premium-what-is.md) içinde yer alması.
- Kullanıcıların, Power BI lisansını etkinleştirmek için Power BI hizmetinde oturum açmış olması.
- Kullanıcıların, Microsoft Teams’de **Power BI** sekmesini kullanma gereksinimlerini karşılaması.

Microsoft Teams'de **Power BI** sekmesini kullanmak için şunlardan emin olmalısınız:

- Microsoft Teams’de **Power BI** sekmesinin bulunması.
- **Power BI** sekmesi olan Microsoft Teams’e rapor eklemek için, raporu barındıran çalışma alanında en azından Görüntüleyici rolünüz olması. Farklı roller hakkında bilgi edinmek için [Yeni çalışma alanlarındaki roller](service-new-workspaces.md#roles-in-the-new-workspaces) bölümüne bakın.
- Raporu Microsoft Teams’in **Power BI** sekmesinde görmek için kullanıcıların rapor görüntüleme izni olmalıdır.
- Kullanıcıların, kanallara ve sohbetlere erişimi olan Microsoft Teams kullanıcıları olması gerekir.

Power BI’da **Teams'de Paylaş** işlevini kullanmak için bu ayarın aşağıdaki gibi olduğundan emin olun:

- Power BI yöneticileri Power BI yönetici portalındaki**Teams’de Paylaş** kiracı ayarını devre dışı bırakmamış. Bu ayar kuruluşların **Teams’de Paylaş** düğmelerini gizlemesini sağlar. Ayrıntılar için [Power BI yönetici portalı](../admin/service-admin-portal.md#share-to-teams-tenant-setting) makalesine bakın.

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

## <a name="next-steps"></a>Sonraki adımlar

- [Microsoft Teams’e Power BI içeriği ekleme](service-embed-report-microsoft-teams.md)
- [Microsoft Teams’de Power BI bağlantı önizlemesi alma](service-teams-link-preview.md)
- [Power BI hizmetinden doğrudan Teams’de paylaşma](service-share-report-teams.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/).
