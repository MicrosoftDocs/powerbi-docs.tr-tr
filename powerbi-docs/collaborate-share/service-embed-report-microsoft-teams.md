---
title: Microsoft Teams'e Power BI raporlarını ekleme
description: Etkileşimli Power BI raporlarını Microsoft Teams kanallarına ve sohbetlerine kolayca ekleyebilirsiniz. .
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: pbi-collaborate-share
ms.topic: conceptual
LocalizationGroup: Share your work
ms.date: 09/21/2020
ms.openlocfilehash: 36973d52f94b806db860b739a84f0c94b2a8945d
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96411874"
---
# <a name="embed-power-bi-content-in-microsoft-teams"></a>Power BI içeriğini Microsoft Teams'e ekleme

Etkileşimli Power BI raporlarını Microsoft Teams kanallarına ve sohbetlerine kolayca ekleyebilirsiniz. 

## <a name="requirements"></a>Gereksinimler

Microsoft Teams'de **Power BI** sekmesini kullanmak için şunlardan emin olmalısınız:

- Microsoft Teams’de **Power BI** sekmesinin bulunması.
- **Power BI** sekmesi olan Microsoft Teams’e rapor eklemek için, raporu barındıran çalışma alanında en azından Görüntüleyici rolünüz olması. Farklı roller hakkında bilgi edinmek için [Yeni çalışma alanlarındaki roller](service-new-workspaces.md#roles-in-the-new-workspaces) bölümüne bakın.
- Raporu Microsoft Teams’in **Power BI** sekmesinde görmek için kullanıcıların rapor görüntüleme izni olmalıdır.
- Kullanıcıların, kanallara ve sohbetlere erişimi olan Microsoft Teams kullanıcıları olması gerekir.

Power BI ile Microsoft Teams’in birlikte nasıl çalıştığı hakkındaki arka plan bilgileri ve diğer gereksinimler için bkz. [Power BI ile Microsoft Teams’de işbirliği yapma](service-embed-report-microsoft-teams.md).

## <a name="embed-a-report-in-microsoft-teams"></a>Microsoft Teams’e rapor ekleme

Raporunuzu bir Microsoft Teams kanalına veya sohbetine eklemek için bu adımları izleyin.

1. Microsoft Teams’de bir kanalı veya sohbeti açıp **+** simgesini seçin.

    ![Kanala veya sohbete sekme ekleme işleminin ekran görüntüsü.](media/service-embed-report-microsoft-teams/service-embed-report-microsoft-teams-add.png)

1. **Power BI** sekmesini seçin.

    ![Power B I'ı gösteren Microsoft Teams sekme listesinin ekran görüntüsü.](media/service-embed-report-microsoft-teams/service-embed-report-microsoft-teams-tab.png)

1. Sunulan seçenekleri kullanarak çalışma alanı veya Power BI uygulaması kaynaklarından bir rapor seçin.

    ![Microsoft Teams için Power B I sekmesi ayarlarının ekran görüntüsü.](media/service-embed-report-microsoft-teams/service-embed-report-microsoft-teams-tab-settings.png)

1. Sekme adı, rapor adıyla eşleşecek şekilde otomatik olarak güncelleştirilir ancak dilerseniz değiştirebilirsiniz.

1. **Kaydet**'i seçin.

### <a name="reports-you-can-embed-on-the-power-bi-tab"></a>Power BI sekmesinde ekleyebileceğiniz raporlar

**Power BI** sekmesine şu türdeki raporları ekleyebilirsiniz:

- Etkileşimli ve sayfalandırılmış raporlar.
- **Çalışma alanım**, yeni çalışma alanı deneyimleri ve klasik çalışma alanları içindeki raporlar.
- Power BI uygulamalarındaki raporlar.

## <a name="start-a-conversation"></a>Bir konuşma başlat

Microsoft Teams’e bir Power BI raporu sekmesi eklediğinizde Microsoft Teams, rapor için otomatik olarak bir sekme görüşmesi oluşturur.

- Sağ üst köşedeki **Sekme konuşmasını göster** simgesini seçin.

    ![Göster sekmesi konuşma simgesinin ekran görüntüsü.](media/service-embed-report-microsoft-teams/power-bi-teams-conversation-icon.png)

    İlk açıklama, raporun bir bağlantısıdır. Microsoft Teams kanalındaki herkes konuşmada raporu görebilir ve rapor hakkında tartışabilir.

    ![Sekme konuşmasının ekran görüntüsü.](media/service-embed-report-microsoft-teams/power-bi-teams-conversation-tab.png)

## <a name="known-issues-and-limitations"></a>Bilinen sorunlar ve sınırlamalar

- Microsoft Teams’de, bir Power BI raporundaki görselde yer alan verileri dışarı aktardığınızda bu veriler otomatik olarak İndirmeler klasörünüze kaydedilir. Bu, “data (*n*).xlsx” adlı bir Excel dosyasıdır. Burada *n*, aynı klasöre verileri kaç kez dışarı aktardığınızı belirten bir sayıdır.
- Power BI panolarını, Microsoft Teams için **Power BI** sekmesine ekleyemezsiniz.
- Microsoft Teams için **Power BI** sekmesinde [URL filtreleri](service-url-filters.md) desteklenmez.
- Yeni **Power BI** sekmesi ulusal bulutlarda kullanılamaz. Power BI uygulamalarındaki yeni çalışma alanı deneyimini veya raporları desteklemeyen eski bir sürüm kullanılabilir.
- Sekmeyi kaydettikten sonra, sekme ayarlarından sekme adı değiştirilmez. Değiştirmek için **Yeniden adlandır** seçeneğini kullanın.
- Diğer sorunlar için "Microsoft Teams'de İşbirliği Yapma" makalesinin [Bilinen sorunlar ve sınırlamalar](service-collaborate-microsoft-teams.md#known-issues-and-limitations) bölümüne bakın.

## <a name="next-steps"></a>Sonraki adımlar

- [Power BI ile Microsoft Teams’de işbirliği yapma](service-collaborate-microsoft-teams.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/).
