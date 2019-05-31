---
title: Bir raporu filtreleyebilir ve arkadaşlarınızla - Power BI paylaşma
description: Power BI raporuna filtre uygulamayı ve bu raporu kuruluşunuzdaki iş arkadaşlarınızla paylaşmayı öğrenin.
author: maggiesMSFT
manager: kfile
ms.reviewer: lukaszp
featuredvideoid: 0tUwn8DHo3s
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/24/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 5f3808884e63521ec1dd775d876f1cf707bbe56b
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "64770687"
---
# <a name="filter-a-power-bi-report-and-share-it-with-coworkers"></a>Power BI raporu filtreleyebilir ve iş arkadaşlarınızla paylaşma
*Paylaşım*, kullanıcıların, panolarınıza ve raporlarınıza erişmesini sağlamanın iyi bir yoludur. Bir raporun filtrelenmiş bir sürümünü paylaşmak istediğinizde ne olur? Bu, yalnızca belirli bir şehre veya satış temsilcisine ya da yıla ait verileri gösteren bir rapor olabilir. Deneyin bir raporu filtreleme ve paylaşımı ya da özel bir URL oluşturuluyor. Alıcılar bunu ilk kez açtığında rapor filtrelenecektir. URL'yi değiştirerek filtreyi kaldırabilirler. 

Power BI ayrıca [işbirliği yapmak ve raporlarınızı dağıtmak için çeşitli yollar sunar](service-how-to-collaborate-distribute-dashboards-reports.md). Paylaşımda siz ve alıcılarınız için bir [Power BI Pro lisansı](service-features-license-type.md) gereklidir veya içerik [Premium kapasitede](service-premium-what-is.md) olmalıdır. 

## <a name="two-ways-to-filter-a-report"></a>Bir rapora filtre uygulamak için iki yol

### <a name="set-a-filter"></a>Bir filtre ayarlayın

Raporu [Düzenleme görünümü](consumer/end-user-reading-view.md)'nde açın, filtreyi uygulayın ve raporu kaydedin.
   
Bu örnekte, yalnızca **Territory**'nin **NC**'ye eşit olduğu değerleri göstermek için [Perakende Analizi örneği](sample-tutorial-connect-to-the-samples.md)'ni filtreliyoruz.
   
![Rapor filtresi bölmesi](media/service-share-reports/power-bi-filter-report2.png)

### <a name="create-a-filter-in-the-url"></a>URL'de bir filtre oluşturun

Aşağıdakini rapor sayfası URL'sinin sonuna ekleyin:
   
?filter=*tabloadı*/*alanadı* eq *değer*
   
Alan türü number, datetime veya dize olması gerekir. *tabloadı* veya *alanadı* değerleri boşluk içeremez.
   
Bizim örneğimizde, tablonun adı **Store**, alanın adı **Territory** ve filtrelemek istediğimiz değer **NC**'dir:
   
?filter=Store/Territory eq 'NC'
   
![Filtrelenmiş rapor URL'si](media/service-share-reports/power-bi-filter-url3.png)
   
Tarayıcınız eğik çizgileri, boşlukları ve kesme işaretlerini göstermek için özel karakterler ekler; böylece, aşağıdaki gibi bir URL elde edersiniz:
   
app.powerbi.com/groups/me/reports/010ae9ad-a9ab-4904-a7a1-xxxxxxxxxxxx/ReportSection2?filter=Store%252FTerritory%20eq%20%27NC%27

Makaleye göz atın [URL'ye sorgu dizesi parametrelerini kullanarak bir raporu filtreleme](service-url-filters.md) çok daha fazla ayrıntı için.

## <a name="share-the-filtered-report"></a>Filtrelenmiş rapor paylaşma

1. Olduğunda, [raporu paylaşmak](service-share-dashboards.md)temizleyin **alıcılara e-posta bildirimi gönder** onay kutusu.

    ![Raporu paylaş iletişim kutusu](media/service-share-reports/power-bi-share-report-dialog.png)

4. Daha önce oluşturduğunuz filtreyi içeren bağlantıyı gönderin.

## <a name="next-steps"></a>Sonraki adımlar
* Geri bildirimde bulunmak ister misiniz? [Power BI Topluluğu sitesine](https://community.powerbi.com/) giderek önerilerinizi belirtin.
* [Panolar ve raporlar üzerinde nasıl işbirliği yapabilir ve bunları nasıl paylaşabilirim?](service-how-to-collaborate-distribute-dashboards-reports.md)
* [Bir panoyu paylaşma](service-share-dashboards.md)
* Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/).

