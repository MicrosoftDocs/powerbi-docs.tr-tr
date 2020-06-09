---
title: Microsoft Teams’e rapor ekleme
description: Microsoft Teams için Power BI sekmesi sayesinde etkileşimli raporları kanallara ve sohbetlere kolayca ekleyebilirsiniz.
author: LukaszPawlowski-MS
ms.author: lukaszp
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
LocalizationGroup: Share your work
ms.date: 04/27/2020
ms.openlocfilehash: 5d0c9fcfbd35b8b42e8196f6f014c96803f6ffc5
ms.sourcegitcommit: 3f864ec22f99ca9e25cda3a5abda8a5f69ccfa8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2020
ms.locfileid: "84159548"
---
# <a name="embed-reports-in-microsoft-teams-with-the-power-bi-tab"></a>Power BI sekmesinden Microsoft Teams’e rapor ekleme

Güncelleştirilmiş Microsoft Teams için Power BI sekmesi sayesinde etkileşimli raporları Microsoft Teams kanallarına ve sohbetlerine kolayca ekleyebilirsiniz. Microsoft Teams için Power BI sekmesini kullanarak iş arkadaşlarınızın, ekibinizin kullandığı verileri kullanmasına ve verilerin ekip kanallarınızda tartışılmasına yardımcı olun.  Rapor, pano ve uygulamalarınızın bağlantısını Microsoft Teams ileti kutusuna yapıştırdığınızda, bağlantı önizlemesi bunlar hakkında bilgiler gösterir. Kullanıcılarınız, bağlantının onları hangi öğeye götüreceğini daha kolay bir şekilde anlayabilir.

## <a name="requirements"></a>Gereksinimler

**Microsoft Teams için Power BI sekmesinin** çalışması şunlara bağlıdır:

- Kullanıcılarınızın bir Power BI Pro lisansına sahip olması veya raporun Power BI lisansına sahip bir [Power BI Premium kapasite (EM veya P SKU)](../admin/service-premium-what-is.md) içinde yer alması.
- Microsoft Teams’te Power BI sekmesinin bulunması.
- Kullanıcıların, raporu kullanmak üzere Power BI lisansını etkinleştirmek için Power BI hizmetinde oturum açmış olması.
- Power BI sekmesi olan Microsoft Teams’e rapor eklemek için, raporu barındıran çalışma alanında en azından Görüntüleyici rolünüz olmalıdır. Farklı roller hakkında bilgi edinmek için [Yeni çalışma alanlarındaki roller](service-new-workspaces.md#roles-in-the-new-workspaces) bölümüne bakın.
- Raporu Microsoft Teams’in Power BI sekmesinde görmek için kullanıcıların rapor görüntüleme izni olmalıdır.

Ayrıca, **bağlantı önizlemelerinin** çalışması şunlara bağlıdır:
- Kullanıcıların, Microsoft Teams için Power BI sekmesini kullanma gereksinimlerini karşılaması.
- Kullanıcıların Power BI hizmetinde oturum açmış olması. 


## <a name="embed-your-report"></a>Raporunuzu ekleme

Raporunuzu bir Microsoft Teams kanalına veya sohbetine eklemek için bu adımları izleyin.

1. Microsoft Teams’de bir kanalı veya sohbeti açıp **+** simgesini seçin.

    ![Kanala veya sohbete sekme ekleme](media/service-embed-report-microsoft-teams/service-embed-report-microsoft-teams-add.png)

2. Power BI sekmesini seçin.

    ![Power BI'ı gösteren Microsoft Teams sekme listesi](media/service-embed-report-microsoft-teams/service-embed-report-microsoft-teams-tab.png)

3. Sunulan seçenekleri kullanarak çalışma alanı veya Power BI uygulaması kaynaklarından bir rapor seçin.

    ![Microsoft Teams için Power BI sekmesi ayarları](media/service-embed-report-microsoft-teams/service-embed-report-microsoft-teams-tab-settings.png)

4. Sekme adı, rapor adıyla eşleşecek şekilde otomatik olarak güncelleştirilir ancak dilerseniz değiştirebilirsiniz. 

5. **Kaydet**’e basın.

## <a name="supported-reports-for-embedding-the-power-bi-tab"></a>Power BI sekmesine eklenmesi desteklenen raporlar
Power BI sekmesine şu türdeki raporları ekleyebilirsiniz:

- Etkileşimli ve sayfalandırılmış raporlar.
- Çalışma alanım, yeni çalışma alanı deneyimleri ve klasik çalışma alanları içindeki raporlar.
- Power BI uygulamalarındaki raporlar.

## <a name="get-a-link-preview"></a>Bağlantı önizlemesini alma

Power BI hizmetindeki içeriğin bağlantı önizlemesini almak için bu adımları izleyin.

1. Bağlantıyı, Power BI hizmetindeki bir rapor, pano veya uygulamaya kopyalayın. Örneğin, tarayıcınızın adres çubuğundaki bağlantıyı kopyalayın.

2. Bağlantıyı Microsoft Teams ileti kutusuna yapıştırın. İstenirse bağlantı önizleme hizmetinde oturum açın. Bağlantı önizlemesinin yüklenmesi için birkaç saniye beklemeniz gerekebilir.

    ![Power BI Bot hizmetinde oturum açma](media/service-embed-report-microsoft-teams/service-teams-link-preview-sign-in-needed.png)

3. Temel bağlantı önizlemesi, başarıyla oturum açıldıktan sonra gösterilir.

    ![Temel bağlantı önizlemesi](media/service-embed-report-microsoft-teams/service-teams-link-preview-basic.png)

4. Zengin önizleme kartını göstermek için genişlet simgesini seçin.

    ![Genişlet simgesi](media/service-embed-report-microsoft-teams/service-teams-link-preview-expand-icon.png)

5. Zengin bağlantı önizlemesi kartı, bağlantıyı ve ilgili eylem düğmelerini gösterir

    ![Zengin bağlantı önizlemesi kartı](media/service-embed-report-microsoft-teams/service-teams-link-preview-nice-card.png)

6. İletiyi gönderin.



## <a name="grant-access-to-reports"></a>Raporlara erişim verme

Bir raporu Microsoft Teams’e eklediğinizde veya bir öğeye bağlantı gönderdiğinizde, kullanıcılara raporu görüntüleme izni otomatik olarak verilmez. [Kullanıcıların raporu Power BI’da görüntülemesine izin vermeniz](service-share-dashboards.md) gerekir. Bu işlemi kolaylaştırmak isterseniz ekibiniz için bir Microsoft 365 Grubu kullanabilirsiniz.

> [!IMPORTANT]
> Power BI hizmetinde, raporu görebilecek olan kullanıcıları belirleyip listede olmayanlara erişim izni vermeyi unutmayın.

Ekibinizdeki herkesin raporlara erişmesini sağlamak için raporları Power BI’da tek bir çalışma alanına yerleştirip ekibinizin Microsoft 365 Grubuna bu çalışma alanına erişim izni verebilirsiniz.

## <a name="link-previews"></a>Bağlantı önizlemeleri 

Bağlantı önizlemeleri, Power BI’daki şu öğeler için sağlanır:
- Raporlar
- Panolar
- Uygulamalar

Bağlantı önizleme hizmeti için kullanıcılarınızın oturum açması gerekir. Oturumu kapatman için ileti kutusunun altındaki Power BI simgesini seçin ve sonra oturumu kapat seçeneğini belirleyin.

## <a name="start-a-conversation"></a>Bir konuşma başlat

Teams’e bir Power BI raporu sekmesi eklediğinizde Teams, rapor için otomatik olarak bir sekme görüşmesi oluşturur. 

- Sağ üst köşedeki **Sekme görüşmesini göster** seçeneğini belirleyin.

    ![Sekme görüşmesini göster simgesi](media/service-embed-report-microsoft-teams/power-bi-teams-conversation-icon.png)

    İlk açıklama, raporun bir bağlantısıdır. Teams kanalındaki herkes görüşmede raporu görebilir ve rapor hakkında tartışabilir.

    ![Sekme görüşmesi](media/service-embed-report-microsoft-teams/power-bi-teams-conversation-tab.png)

## <a name="known-issues-and-limitations"></a>Bilinen sorunlar ve sınırlamalar

- Power BI, Microsoft Teams ile aynı yerelleştirilmiş dilleri desteklemez. Bu nedenle, eklenen rapordaki yerelleştirme doğru olmayabilir.
- Power BI panoları, Microsoft Teams için Power BI sekmesine eklenemez.
- Power BI lisansı veya raporu görme izni olmayan kullanıcılar “İçerik kullanılamıyor” iletisiyle karşılaşır.
- Internet Explorer 10 kullanıyorsanız sorunlarla karşılaşabilirsiniz. <!--You can look at the [browsers support for Power BI](../consumer/end-user-browsers.md) and for [Microsoft 365](https://products.office.com/office-system-requirements#Browsers-section). -->
- Microsoft Teams için Power BI sekmesinde [URL filtreleri](service-url-filters.md) desteklenmez.
- Yeni Power BI sekmesi ulusal bulutlarda kullanılamaz. Power BI uygulamalarındaki yeni çalışma alanı deneyimini veya raporları desteklemeyen eski bir sürüm kullanılabilir. 
- Sekmeyi kaydettikten sonra, sekme ayarlarından sekme adı değiştirilemez. Değiştirmek için yeniden adlandırma seçeneğini kullanın.
- Bağlantı önizleme hizmetinde Çoklu Oturum Açma desteklenmez.
- Bağlantı önizlemeleri, toplantı sohbetinde veya özel kanallarda çalışmaz.

## <a name="next-steps"></a>Sonraki adımlar
- [Panoları iş arkadaşlarınızla ve diğer kişilerle paylaşma](service-share-dashboards.md)  
- [Power BI'da uygulama oluşturma ve dağıtma](service-create-distribute-apps.md)  
- [Power BI Premium nedir?](../admin/service-premium-what-is.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
