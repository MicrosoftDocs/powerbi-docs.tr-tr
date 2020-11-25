---
title: Power BI hizmetinden doğrudan Microsoft Teams’de paylaşma
description: Power BI panolarını ve raporlarını Power BI hizmetinden doğrudan Microsoft Teams'le paylaşabilirsiniz.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
LocalizationGroup: Share your work
ms.date: 07/31/2020
ms.openlocfilehash: db9084e7f7e78ecf17abe38ade732ab7ad2df754
ms.sourcegitcommit: 5bbe7725918a72919ba069c5f8a59e95453ec14c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2020
ms.locfileid: "94946783"
---
# <a name="share-directly-to-microsoft-teams-from-the-power-bi-service"></a>Power BI hizmetinden doğrudan Microsoft Teams’de paylaşma

Power BI panolarını, raporlarını ve görsellerini Power BI hizmetinden doğrudan Microsoft Teams'le paylaşabilirsiniz. Power BI hizmetinde raporları ve panoları görüntülerken hızla konuşma başlatmak için **Teams’de Paylaş** özelliğini kullanın.

## <a name="requirements"></a>Gereksinimler

Power BI’da **Teams'de Paylaş** işlevini kullanmak için bu ayarın aşağıdaki gibi olduğundan emin olun:

- Power BI yöneticileri Power BI yönetici portalındaki **Teams’de Paylaş** kiracı ayarını devre dışı bırakmamış. Bu ayar kuruluşların **Teams’de Paylaş** düğmelerini gizlemesini sağlar. Ayrıntılar için [Power BI yönetici portalı](../admin/service-admin-portal.md#share-to-teams) makalesine bakın.

Power BI ile Microsoft Teams’in birlikte nasıl çalıştığı hakkındaki arka plan bilgileri ve diğer gereksinimler için bkz. [Power BI ile Microsoft Teams’de işbirliği yapma](service-collaborate-microsoft-teams.md).

## <a name="share-power-bi-content-to-microsoft-teams"></a>Power BI içeriğini Microsoft Teams’de paylaşma

Power BI hizmetindeki raporlar, panolar ve görsellerin bağlantılarını Microsoft Teams kanalları ve sohbetlerinde paylaşmak için şu adımları izleyin.

1. Şu seçeneklerden birini belirtin:

   * Pano veya raporun eylem çubuğunda **Teams'de Paylaş**:

       ![Eylem çubuğundaki Teams’de Paylaş düğmesinin ekran görüntüsü.](media/service-share-report-teams/service-teams-share-to-teams-action-bar-button.png)
    
   * Tek bir görselin bağlam menüsündeki **Teams'de Paylaş**:
    
      ![Görselin bağlam menüsündeki Teams’de Paylaş düğmesinin ekran görüntüsü.](media/service-share-report-teams/service-teams-share-to-teams-visual-context-menu.png)

1. **Microsoft Teams’de Paylaş** iletişim kutusunda, bağlantıyı göndermek istediğiniz takımı veya kanalı seçin. Dilerseniz ileti ekleyebilirsiniz. Önce Microsoft Teams’de oturum açmanız istenebilir.

    ![Bilgi ve ileti içeren Microsoft Teams’de Paylaş iletişim kutusunun ekran görüntüsü.](media/service-share-report-teams/service-teams-share-to-teams-dialog.png)

1. Bağlantıyı göndermek için **Paylaş**’ı seçin.
    
1. Bağlantı mevcut konuşmalara eklenir veya yeni bir sohbet başlatır.

    ![Power BI öğesinin bağlantısını içeren Microsoft Teams konuşmasının ekran görüntüsü.](media/service-share-report-teams/service-teams-share-to-teams-deep-link.png)

1. Öğeyi Power BI hizmetinde açmak için bağlantıyı seçin.

1. Belirli bir görselde bağlam menüsü kullandıysanız rapor açıldığında görsel vurgulanır.

    ![Vurgulanan belirli bir görselin yer aldığı açık Power BI raporunun ekran görüntüsü.](media/service-share-report-teams/service-teams-share-to-teams-spotlight-visual.png)


## <a name="known-issues-and-limitations"></a>Bilinen sorunlar ve sınırlamalar

- Power BI lisansına veya rapora erişim izni olmayan kullanıcılar “İçerik kullanılamıyor” iletisiyle karşılaşır.
- Tarayıcınızda katı gizlilik ayarları kullanılıyorsa **Teams’de Paylaş** düğmeleri çalışmayabilir. İletişim kutusu doğru biçimde açılmazsa **Sorun mu yaşıyorsunuz? Yeni bir pencerede açmayı deneyin** seçeneğini kullanın.
- **Teams’de Paylaş** düğmesinde bağlantı önizlemesi bulunmaz.
- Bağlantı önizlemeleri ve **Teams’de Paylaş**, kullanıcılara öğeyi görüntüleme izni vermez. İzinlerin ayrı yönetilmesi gerekir.
- Bir rapor yazarı görsel için **Daha fazla** seçeneğini **Kapalı** olarak ayarladığında görselin bağlam menülerinde **Teams’de Paylaş** düğmesi kullanılamaz.
- Diğer sorunlar için "Microsoft Teams'de İşbirliği Yapma" makalesinin [Bilinen sorunlar ve sınırlamalar](service-collaborate-microsoft-teams.md#known-issues-and-limitations) bölümüne bakın.

## <a name="next-steps"></a>Sonraki adımlar

- [Power BI ile Microsoft Teams’de işbirliği yapma](service-collaborate-microsoft-teams.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/).
