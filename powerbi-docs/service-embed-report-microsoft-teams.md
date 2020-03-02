---
title: Microsoft Teams için Power BI sekmesinden rapor ekleme
description: Microsoft Teams için Power BI sekmesi sayesinde etkileşimli raporları kanallara ve sohbetlere kolayca ekleyebilirsiniz.
author: LukaszPawlowski-MS
ms.author: lukaszp
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
LocalizationGroup: Share your work
ms.date: 01/31/2020
ms.openlocfilehash: fb4846a777dda4787e1ed0be7de869367a616ea5
ms.sourcegitcommit: b22a9a43f61ed7fc0ced1924eec71b2534ac63f3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/21/2020
ms.locfileid: "77530499"
---
# <a name="embed-report-with-the-power-bi-tab-for-microsoft-teams"></a>Microsoft Teams için Power BI sekmesinden rapor ekleme

Güncelleştirilmiş Microsoft Teams için Power BI sekmesi sayesinde etkileşimli raporları Microsoft Teams kanallarına ve sohbetlerine kolayca ekleyebilirsiniz.

Microsoft Teams için Power BI sekmesini kullanarak iş arkadaşlarınızın, ekibinizin kullandığı verileri kullanmasına ve verilerin ekip kanallarınızda tartışılmasına yardımcı olun.

## <a name="requirements"></a>Gereksinimler

**Microsoft Teams için Power BI sekmesinin** çalışması aşağıdaki gereksinimlere bağlıdır:

- Bir Power BI Pro lisansı veya raporun Power BI lisansına sahip bir [Power BI Premium kapasite (EM veya P SKU)](service-premium-what-is.md) içinde yer alması.
- Microsoft Teams için Power BI sekmesi.
- Raporu kullanmak için kullanıcıların Power BI hizmetinde oturum açarak Power BI lisanslarını etkinleştirmeleri gerekir.
- Kullanıcı, raporu görüntüleme iznine sahip olmalıdır.

## <a name="embed-your-report"></a>Raporunuzu ekleme
Raporunuzu bir Microsoft Teams kanalına veya sohbetine eklemek için aşağıdaki adımları izleyin.

1. Microsoft Teams'de istediğiniz kanalı veya sohbeti açıp **+** simgesini seçin.

    ![Kanala veya sohbete sekme ekleme](media/service-embed-report-microsoft-teams/service-embed-report-microsoft-teams-add.png)

2. Power BI sekmesini seçin.

    ![Power BI'ı gösteren Microsoft Teams sekme listesi](media/service-embed-report-microsoft-teams/service-embed-report-microsoft-teams-tab.png)

3. Sunulan seçenekleri kullanarak Çalışma alanı, Benimle paylaşılanlar veya Power BI uygulaması kaynaklarından bir rapor seçin

    ![Microsoft Teams için Power BI sekmesi ayarları](media/service-embed-report-microsoft-teams/service-embed-report-microsoft-teams-tab-settings.png)

4. Sekme adı, rapor adıyla eşleşecek şekilde otomatik olarak güncelleştirilir ancak dilerseniz değiştirebilirsiniz. 

5. **Kaydet**’e basın.

## <a name="supported-reports"></a>Desteklenen raporlar

Sekmeden şu raporları ekleyebilirsiniz:

- Etkileşimli ve sayfalandırılmış raporlar
- Çalışma alanım, yeni çalışma alanı deneyimi ve klasik çalışma alanları içindeki raporlar
- Power BI uygulamalarındaki raporlar


## <a name="grant-access-to-reports"></a>Raporlara erişim verme

Bir raporu Microsoft Teams'e eklediğinizde kullanıcılara raporu görüntüleme izni otomatik olarak verilmez. [Kullanıcıların raporu Power BI'da görüntülemesine izin vermeniz](service-share-dashboards.md) gerekir. Bu işlemi kolaylaştırmak isterseniz ekibiniz için bir Office 365 Grubu kullanabilirsiniz. 

> [!IMPORTANT]
> Power BI hizmetinde, raporu görebilecek olan kullanıcıları belirleyip listede olmayanlara erişim izni vermeyi unutmayın.

Ekibinizdeki herkesin eklediğiniz raporlara erişmesini sağlamak için raporları Power BI'da tek bir çalışma alanına ekleyip ekibinizin Office 365 Grubuna bu çalışma alanına erişim izni verebilirsiniz.

## <a name="known-issues-and-limitations"></a>Bilinen sorunlar ve sınırlamalar

- Power BI, Microsoft Teams ile aynı yerelleştirilmiş dilleri desteklemez. Bu nedenle, eklenen rapordaki yerelleştirme doğru olmayabilir.
- Power BI panoları, Microsoft Teams için Power BI sekmesine eklenemez.
- Power BI lisansı veya rapor için izni olmayan kullanıcılar "İçerik kullanılamıyor" iletisiyle karşılaşır.
- Internet Explorer 10 kullanıyorsanız sorunlarla karşılaşabilirsiniz. <!--You can look at the [browsers support for Power BI](consumer/end-user-browsers.md) and for [Office 365](https://products.office.com/office-system-requirements#Browsers-section). -->
- Microsoft Teams için Power BI sekmesinde [URL filtreleri](service-url-filters.md) desteklenmez.
- Ulusal bulutlarda yeni Power BI sekmesi mevcut değildir. Yeni çalışma alanı deneyimini veya Power BI uygulamalarındaki raporları desteklemeyen eski bir sürüm mevcut olabilir. 
- Sekme kaydedildikten sonra sekme ayarlarından adı değiştirilemez. Değiştirmek için yeniden adlandırma seçeneğini kullanın.

## <a name="next-steps"></a>Sonraki adımlar
- [Panoları iş arkadaşlarınızla ve diğer kişilerle paylaşma](service-share-dashboards.md)  
- [Power BI'da uygulama oluşturma ve dağıtma](service-create-distribute-apps.md)  
- [Power BI Premium nedir?](service-premium-what-is.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
