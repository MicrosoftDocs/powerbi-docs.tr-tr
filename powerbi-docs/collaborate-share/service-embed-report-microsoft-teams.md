---
title: Power BI ile Microsoft Teams’de işbirliği yapma
description: Microsoft Teams için Power BI sekmesi sayesinde etkileşimli raporları kanallara ve sohbetlere kolayca ekleyebilirsiniz.
author: LukaszPawlowski-MS
ms.author: lukaszp
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
LocalizationGroup: Share your work
ms.date: 06/05/2020
ms.openlocfilehash: aedc65b1d13c25068d4bc19026e1475081336e77
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85226381"
---
# <a name="collaborate-in-microsoft-teams-with-power-bi"></a>Power BI ile Microsoft Teams’de işbirliği yapma

Microsoft Teams için **Power BI** sekmesi sayesinde etkileşimli raporları Microsoft Teams kanallarına ve sohbetlerine kolayca ekleyebilirsiniz. Microsoft Teams için **Power BI** sekmesini kullanarak iş arkadaşlarınızın, ekibinizin kullandığı verileri kullanmasına ve verilerin ekip kanallarınızda tartışılmasına yardımcı olun. Rapor, pano ve uygulamalarınızın bağlantısını Microsoft Teams ileti kutusuna yapıştırdığınızda, bağlantı önizlemesi bu bağlantı hakkında bilgiler gösterir. Power BI’da raporları ve panoları görüntülerken hızla konuşma başlatmak için **Teams’de Paylaş** düğmelerini kullanın.

## <a name="requirements"></a>Gereksinimler

Microsoft Teams için **Power BI** sekmesinin çalışması şunlara bağlıdır:

- Kullanıcılarınızın bir Power BI Pro lisansına sahip olması veya raporun Power BI lisansına sahip bir [Power BI Premium kapasite (EM veya P SKU)](../admin/service-premium-what-is.md) içinde yer alması.
- Microsoft Teams’de **Power BI** sekmesinin bulunması.
- Kullanıcıların, raporu kullanmak üzere Power BI lisansını etkinleştirmek için Power BI hizmetinde oturum açmış olması.
- **Power BI** sekmesi olan Microsoft Teams’e rapor eklemek için, raporu barındıran çalışma alanında en azından Görüntüleyici rolünüz olmalıdır. Farklı roller hakkında bilgi edinmek için [Yeni çalışma alanlarındaki roller](service-new-workspaces.md#roles-in-the-new-workspaces) bölümüne bakın.
- Raporu Microsoft Teams’in **Power BI** sekmesinde görmek için kullanıcıların rapor görüntüleme izni olmalıdır.
- Kullanıcıların, kanallara ve sohbetlere erişimi olan Microsoft Teams kullanıcıları olması gerekir.

Bağlantı önizlemelerinin çalışması şunlara bağlıdır:

- Kullanıcıların, Microsoft Teams için **Power BI** sekmesini kullanma gereksinimlerini karşılaması.
- Kullanıcıların Power BI’da oturum açmış olması.

**Teams’de Paylaş** düğmelerinin çalışması şunlara bağlıdır:

- Kullanıcıların, Microsoft Teams için **Power BI** sekmesini kullanma gereksinimlerini karşılaması.
- Kullanıcıların Power BI’da oturum açmış olması.
- Power BI yöneticilerinin **Teams’de Paylaş** kiracı ayarını devre dışı bırakmamış olması.


## <a name="embed-your-report"></a>Raporunuzu ekleme

Raporunuzu bir Microsoft Teams kanalına veya sohbetine eklemek için bu adımları izleyin.

1. Microsoft Teams’de bir kanalı veya sohbeti açıp **+** simgesini seçin.

    ![Kanala veya sohbete sekme ekleme](media/service-embed-report-microsoft-teams/service-embed-report-microsoft-teams-add.png)

1. **Power BI** sekmesini seçin.

    ![Power BI'ı gösteren Microsoft Teams sekme listesi](media/service-embed-report-microsoft-teams/service-embed-report-microsoft-teams-tab.png)

1. Sunulan seçenekleri kullanarak çalışma alanı veya Power BI uygulaması kaynaklarından bir rapor seçin.

    ![Microsoft Teams için Power BI sekmesi ayarları](media/service-embed-report-microsoft-teams/service-embed-report-microsoft-teams-tab-settings.png)

1. Sekme adı, rapor adıyla eşleşecek şekilde otomatik olarak güncelleştirilir ancak dilerseniz değiştirebilirsiniz.

1. **Kaydet**'i seçin.

## <a name="supported-reports-for-embedding-the-power-bi-tab"></a>Power BI sekmesine eklenmesi desteklenen raporlar

**Power BI** sekmesine şu türdeki raporları ekleyebilirsiniz:

- Etkileşimli ve sayfalandırılmış raporlar.
- **Çalışma alanım**, yeni çalışma alanı deneyimleri ve klasik çalışma alanları içindeki raporlar.
- Power BI uygulamalarındaki raporlar.

## <a name="get-a-link-preview"></a>Bağlantı önizlemesini alma

Power BI hizmetindeki içeriğin bağlantı önizlemesini almak için bu adımları izleyin.

1. Bağlantıyı, Power BI hizmetindeki bir rapor, pano veya uygulamaya kopyalayın. Örneğin, tarayıcınızın adres çubuğundaki bağlantıyı kopyalayın.

1. Bağlantıyı Microsoft Teams ileti kutusuna yapıştırın. İstenirse bağlantı önizleme hizmetinde oturum açın. Bağlantı önizlemesinin yüklenmesi için birkaç saniye beklemeniz gerekebilir.

    ![Power BI bot hizmetinde oturum açma](media/service-embed-report-microsoft-teams/service-teams-link-preview-sign-in-needed.png)

1. Temel bağlantı önizlemesi, başarıyla oturum açıldıktan sonra gösterilir.

    ![Temel bağlantı önizlemesi](media/service-embed-report-microsoft-teams/service-teams-link-preview-basic.png)

1. Zengin önizleme kartını göstermek için **Genişlet** simgesini seçin.

    ![Genişlet simgesi](media/service-embed-report-microsoft-teams/service-teams-link-preview-expand-icon.png)

1. Zengin bağlantı önizlemesi kartı, bağlantıyı ve ilgili eylem düğmelerini gösterir.

    ![Zengin bağlantı önizlemesi kartı](media/service-embed-report-microsoft-teams/service-teams-link-preview-nice-card.png)

1. İletiyi gönderin.

## <a name="share-to-teams-buttons-in-the-power-bi-service"></a>Power BI hizmetindeki Teams’de Paylaş düğmeleri

Power BI hizmetinde raporları veya panoları görüntülerken bağlantıları Microsoft Teams kanallarında ve sohbetlerinde paylaşmak için şu adımları izleyin.

1. Eylem çubuğunda veya belirli bir görseldeki bağlam menüsünde yer alan **Teams’de Paylaş** düğmelerini kullanın.

   * Eylem çubuğundaki **Teams’de Paylaş** düğmesi:

       ![Eylem çubuğundaki Teams’de Paylaş düğmesi](media/service-embed-report-microsoft-teams/service-teams-share-to-teams-action-bar-button.png)
    
   * Görsel bağlam menüsündeki **Teams’de Paylaş** düğmesi:
    
      ![Görsel bağlam menüsündeki Teams’de Paylaş düğmesi](media/service-embed-report-microsoft-teams/service-teams-share-to-teams-visual-context-menu.png)

1. **Microsoft Teams’de Paylaş** iletişim kutusunda, bağlantıyı göndermek istediğiniz kanalı veya kişileri seçin. Dilerseniz ileti ekleyebilirsiniz. Önce Microsoft Teams’de oturum açmanız istenebilir.

    ![Bilgi ve ileti içeren Microsoft Teams’de Paylaş iletişim kutusu](media/service-embed-report-microsoft-teams/service-teams-share-to-teams-dialog.png)

1. Bağlantıyı göndermek için **Paylaş**’ı seçin.
    
1. Bağlantı mevcut konuşmalara eklenir veya yeni bir sohbet başlatır.

    ![Power BI öğesi bağlantısı içeren Microsoft Teams konuşması](media/service-embed-report-microsoft-teams/service-teams-share-to-teams-deep-link.png)

1. Öğeyi Power BI hizmetinde açmak için bağlantıyı seçin.

1. Belirli bir görselde bağlam menüsü kullandıysanız rapor açıldığında görsel vurgulanır.

    ![Vurgulanan belirli bir görselin yer aldığı açık Power BI raporu](media/service-embed-report-microsoft-teams/service-teams-share-to-teams-spotlight-visual.png)
    

## <a name="grant-access-to-reports"></a>Raporlara erişim verme

Bir raporu Microsoft Teams’e eklediğinizde veya bir öğeye bağlantı gönderdiğinizde, kullanıcılara raporu görüntüleme izni otomatik olarak verilmez. [Kullanıcıların raporu Power BI’da görüntülemesine izin vermeniz](service-share-dashboards.md) gerekir. Bu işlemi kolaylaştırmak isterseniz ekibiniz için bir Microsoft 365 Grubu kullanabilirsiniz.

> [!IMPORTANT]
> Power BI hizmetinde, raporu görebilecek olan kullanıcıları belirleyip listede olmayanlara erişim izni vermeyi unutmayın.

Ekipteki herkesin raporlara erişmesini sağlamak için raporları tek bir çalışma alanına yerleştirip ekibinizin Microsoft 365 Grubuna erişim izni verebilirsiniz.

## <a name="link-previews"></a>Bağlantı önizlemeleri

Bağlantı önizlemeleri, Power BI’daki şu öğeler için sağlanır:
- Raporlar
- Panolar
- Uygulamalar

Bağlantı önizleme hizmeti için kullanıcılarınızın oturum açması gerekir. Oturumu kapatmak için ileti kutusunun altındaki **Power BI** simgesini seçin. Sonra **Oturumu kapat** seçeneğini belirleyin.

## <a name="start-a-conversation"></a>Bir konuşma başlat

Microsoft Teams’e bir Power BI raporu sekmesi eklediğinizde Teams, rapor için otomatik olarak bir sekme görüşmesi oluşturur.

- Sağ üst köşedeki **Sekme konuşmasını göster** simgesini seçin.

    ![Sekme görüşmesini göster simgesi](media/service-embed-report-microsoft-teams/power-bi-teams-conversation-icon.png)

    İlk açıklama, raporun bir bağlantısıdır. Microsoft Teams kanalındaki herkes konuşmada raporu görebilir ve rapor hakkında tartışabilir.

    ![Sekme görüşmesi](media/service-embed-report-microsoft-teams/power-bi-teams-conversation-tab.png)
    
## <a name="share-to-teams-tenant-setting"></a>Teams’de Paylaş kiracı ayarı

Power BI yönetici portalındaki **Teams’de Paylaş** kiracı ayarı, kuruluşların **Teams’de Paylaş** düğmelerini gizlemesine olanak verir. Devre dışı olarak ayarlandığında, Power BI hizmetinde raporları ve panoları görüntüleyen kullanıcılar eylem çubuğunda veya bağlam menülerinde **Teams’de Paylaş** düğmelerini görmez.

![Power BI yönetim portalındaki Teams’de Paylaş kiracı ayarı](media/service-embed-report-microsoft-teams/service-teams-share-to-teams-tenant-setting.png)

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
- Tarayıcınızda katı gizlilik ayarları kullanılıyorsa **Teams’de Paylaş** düğmeleri çalışmayabilir. İletişim kutusu doğru biçimde açılmazsa **Sorun mu yaşıyorsunuz? Yeni bir pencerede açmayı deneyin** seçeneğini kullanın.
- **Teams’de Paylaş** düğmesinde bağlantı önizlemesi bulunmaz.
- Bağlantı önizlemeleri ve **Teams’de Paylaş**, kullanıcılara öğeyi görüntüleme izni vermez. İzinlerin ayrı yönetilmesi gerekir.
- Bir rapor yazarı görsel için **Daha fazla** seçeneğini *Kapalı* olarak ayarladığında görsel bağlam menülerinde **Teams’de Paylaş** düğmesi kullanılamaz.

## <a name="next-steps"></a>Sonraki adımlar

- [Panoları iş arkadaşlarınızla ve diğer kişilerle paylaşma](service-share-dashboards.md)
- [Power BI'da uygulama oluşturma ve dağıtma](service-create-distribute-apps.md)
- [Power BI Premium nedir?](../admin/service-premium-what-is.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/).
