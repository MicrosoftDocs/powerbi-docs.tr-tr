---
title: Panoları ve raporları paylaşma sorunlarını giderme
description: Power BI panolarını ve raporları kuruluşunuzdaki iş arkadaşlarınızla ve kuruluş dışındaki diğer kullanıcılarla paylaşma sorunlarını giderme.
author: maggiesMSFT
ms.reviewer: lukaszp
featuredvideoid: 0tUwn8DHo3s
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: troubleshooting
ms.date: 06/23/2020
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: ef78847829ef292a16856a1597a53c95e7d20708
ms.sourcegitcommit: a453ba52aafa012896f665660df7df7bc117ade5
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2020
ms.locfileid: "85486816"
---
# <a name="troubleshoot-sharing-dashboards-and-reports"></a>Panoları ve raporları paylaşma sorunlarını giderme

Bir panoyu veya raporu paylaşırken ya da bunlar sizinle paylaşılırken ortaya çıkabilecek yaygın sorunlardan bazıları aşağıda verilmiştir. 

## <a name="dashboard-recipients-see-a-lock-icon-in-a-tile"></a>Pano alıcıları bir kutucukta kilit simgesi görüyor

Pano paylaşımında bulunduğunuz kişiler burada kilitli bir kutucuk veya bir raporu görüntülemeye çalıştıklarında "İzin gerekiyor" iletisi görebilir.

![Power BI kilitli kutucuğu](media/service-share-dashboards/power-bi-locked_tile_small.png)

Bu durumda bu kişilere, temel alınan veri kümesine yönelik erişim izni vermeniz gerekir.

1. İçerik listenizdeki **Veri kümeleri** sekmesine gidin.

1. Veri kümesinin yanındaki üç nokta ( **...** ) simgesini seçin ve ardından **İzinleri yönet** seçeneğini belirleyin.

    ![İzinleri yönet](media/service-share-dashboards/power-bi-sharing-manage-permissions.png)

1. **Kullanıcı ekle**'yi seçin.

    ![Kullanıcı ekle seçeneğini belirleme](media/service-share-dashboards/power-bi-share-dataset-add-user.png)

1. Kişilerin, dağıtım gruplarının veya güvenlik gruplarının tam e-posta adreslerini girin. Dinamik dağıtım listeleri ile paylaşım yapamazsınız.

    ![E-posta adresi ekleme](media/service-share-dashboards/power-bi-add-user-dataset.png)

1. **Ekle**'yi seçin.

## <a name="i-cant-share-a-dashboard-or-report"></a>Bir pano veya raporu paylaşamıyorum

Bir panoyu veya raporu paylaşmak için, temel alınan içeriği (ilgili tüm raporlar ve veri kümeleri) yeniden paylaşma iznine sahip olmanız gerekir. Paylaşım yapamayacağınızı belirten bir iletiyle karşılaşırsanız raporun yazarından size söz konusu raporlar ve veri kümeleri için yeniden paylaşma izni vermesini isteyin.

!["Paylaşılamadı" iletisi](media/service-share-dashboards/power-bi-sharing-unable-to-share.png)

## <a name="i-dont-have-access-to-a-dashboard-or-report"></a>Panoya veya rapora erişimim yok

Bir rapor veya pano bağlantısını seçtiğinizde “Erişim iste” iletisini görüyorsanız bu bağlantıyı görme izniniz yoktur. [Bu bağlantıya erişim istemeniz](service-request-access.md) gerekir.

## <a name="next-steps"></a>Sonraki adımlar

- [Power BI panolarını ve raporlarını iş arkadaşlarıyla ve başkalarıyla paylaşma](service-share-dashboards.md)
- [Panolar ve raporlar üzerinde nasıl işbirliği yapabilir ve bunları nasıl paylaşabilirim?](service-how-to-collaborate-distribute-dashboards-reports.md)
-  [Filtre uygulanmış bir Power BI raporunu paylaşma](service-share-reports.md)
- Sorularınız mı var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)
