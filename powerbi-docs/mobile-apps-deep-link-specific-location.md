---
title: Power BI mobil uygulamalarında belirli bir konumun bağlantısını oluşturma
description: Tekdüzen kaynak tanımlayıcısı (URI) kullanarak Power BI mobil uygulamasındaki belirli bir panonun, kutucuğun veya raporun ayrıntılı bağlantısını oluşturmayı öğrenin.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-mobile
ms.topic: conceptual
ms.date: 06/28/2018
ms.author: maggies
ms.openlocfilehash: 3ea99d26418a583a6ca588879aeafcd114aeaa6e
ms.sourcegitcommit: 16098be04df05bc8e3d44a99b4d143b622759c59
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39616017"
---
# <a name="create-a-link-to-a-specific-location-in-the-power-bi-mobile-apps"></a>Power BI mobil uygulamalarında belirli bir konumun bağlantısını oluşturma
Tüm mobil platformlardaki (iOS, Android cihazlar ve Windows 10) Power BI mobil uygulamalarında belirli bir konumun bağlantısına (*ayrıntılı bağlantı*) yönelik bir tekdüzen kaynak tanımlayıcısı (URI) oluşturup kullanabilirsiniz.

URI bağlantıları doğrudan panolara, kutucuklara ve raporlara işaret edebilir.

Ayrıntılı bağlantının hedefi, URI'nin biçimini belirler. Farklı konumların ayrıntılı bağlantılarını oluşturmak için aşağıdaki adımları uygulayın. 

## <a name="open-the-power-bi-mobile-app"></a>Power BI mobil uygulamasını açma
Herhangi bir cihazda Power BI mobil uygulamasını açmak için bu URI'yi kullanın:

    mspbi://app/


## <a name="open-to-a-specific-dashboard"></a>Belirli bir pano ile açma
Bu URI, Power BI mobil uygulamasını belirli bir pano ile açar:

    mspbi://app/OpenDashboard?DashboardObjectId=<36-character-dashboard-id>

36 karakterden oluşan pano nesnesi kimliğini bulmak için Power BI hizmetinde (https://powerbi.com)) söz konusu panoya gidin. Örneğin, şu URL'nin vurgulanan bölümüne bakın:

`https://powerbi.com/groups/me/dashboards/**61b7e871-cb98-48ed-bddc-6572c921e270**`

Pano, Çalışma Alanım dışındaki bir gruptaysa pano kimliğinin önüne veya sonuna `&GroupObjectId=<36-character-group-id>` ekleyin. Örneğin, 

mspbi://app/OpenDashboard?DashboardObjectId=e684af3a-9e7f-44ee-b679-b9a1c59b5d60 **&GroupObjectId=8cc900cc-7339-467f-8900-fec82d748248**

İkisi arasındaki ve işaretine (&) dikkat edin.

## <a name="open-to-a-specific-tile-in-focus"></a>Odak modunda belirli bir kutucukla açma
Bu URI, Power BI mobil uygulamasını odak modunda belirli bir pano ile açar:

    mspbi://app/OpenTile?DashboardObjectId=<36-character-dashboard-id>&TileObjectId=<36-character-tile-id>

36 karakterden oluşan pano ve kutucuk nesnesi kimliklerini bulmak için Power BI hizmetinde (https://powerbi.com)) söz konusu panoya gidin ve kutucuğu odak modunda açın. Örneğin, şu URL'nin vurgulanan bölümlerine bakın:

`https://powerbi.com/groups/me/dashboards/**3784f99f-b460-4d5e-b86c-b6d8f7ec54b7**/tiles/**565f9740-5131-4648-87f2-f79c4cf9c5f5**/infocus`

Bu kutucuk için URI şu şekilde olur:

    mspbi://app/OpenTile?DashboardObjectId=3784f99f-b460-4d5e-b86c-b6d8f7ec54b7&TileObjectId=565f9740-5131-4648-87f2-f79c4cf9c5f5

İkisi arasındaki ve işaretine (&) dikkat edin.

Pano, Çalışma Alanım dışında bir gruptaysa `&GroupObjectId=<36-character-group-id>` ekleyin

## <a name="open-to-a-specific-report"></a>Belirli bir rapor ile açma
Bu URI, Power BI mobil uygulamasında belirli bir raporu açar:

    mspbi://app/OpenReport?ReportObjectId=<36-character-report-id>

36 karakterden oluşan rapor nesnesi kimliğini bulmak için Power BI hizmetindeki (https://powerbi.com)) söz konusu rapora gidin. Örneğin, şu URL'nin vurgulanan bölümüne bakın:

https://powerbi.com/groups/me/reports/**df9f0e94-31df-450b-b97f-4461a7e4d300**

## <a name="open-to-a-specific-report-page"></a>Belirli bir rapor sayfası ile açma
Bu URI, Power BI mobil uygulamasında belirli bir rapor sayfasını açar:

    mspbi://app/OpenReport?ReportObjectId=<36-character-report-id>&reportPage=ReportSection<number>

Rapor sayfası, ardından gelecek bir sayıyla birlikte "ReportSection" olarak adlandırılır. Power BI hizmetinde (https://powerbi.com)) raporu tekrar açın ve söz konusu rapor sayfasına gidin. 

Örneğin, şu URL'nin vurgulanan bölümüne bakın:

https://powerbi.com/groups/me/reports/df9f0e94-31df-450b-b97f-4461a7e4d300/**ReportSection11**

## <a name="open-in-full-screen-mode"></a>Tam ekran modunda açma
Belirli bir rapor ile tam ekran modunda açmak için, kalın yazılmış parametreyi ekleyin:

    mspbi://app/OpenReport?ReportObjectId=<36-character-report-id>**&openFullScreen=true**

Örneğin: 

mspbi://app/OpenReport?ReportObjectId=500217de-50f0-4af1-b345-b81027224033&openFullScreen=true

## <a name="add-context-optional"></a>Bağlam ekleme (isteğe bağlı)
Ayrıca dizeye bağlam da ekleyebilirsiniz. Ardından bize ulaşmanız gerekirse verilerimizi uygulamanıza yönelik olarak filtrelemek için bu bağlamı kullanabiliriz. Bağlantıya `&context=<app-name>` ekleyin

Örneğin, şu URL'nin vurgulanan bölümüne bakın: 

https://powerbi.com/groups/me/reports/df9f0e94-31df-450b-b97f-4461a7e4d300/**&context=SlackDeepLink**

## <a name="next-steps"></a>Sonraki adımlar
Geri bildiriminiz gelecekte neler yapacağımıza karar verme konusunda bize yardımcı olur, bu nedenle Power BI mobil uygulamalarında görmek istediğiniz diğer özellikleri oylamayı unutmayın. 

* [Mobil cihazlar için Power BI uygulamaları](mobile-apps-for-mobile-devices.md)
* Bizi Twitter'da takip edin: @MSPowerBI
* [Power BI Topluluğu](http://community.powerbi.com/)'nda sohbete katılın
* [Power BI nedir?](power-bi-overview.md)

