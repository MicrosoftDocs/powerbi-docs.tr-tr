---
title: Power BI raporlarını filtreleme ve iş arkadaşları ile paylaşma
description: Filtre uygulanmış bir Power BI raporunu kuruluşunuzdaki iş arkadaşlarınızla nasıl paylaşacağınızı öğrenin.
services: powerbi
documentationcenter: ''
author: maggiesMSFT
manager: kfile
backup: lukaszp
editor: ''
tags: ''
featuredvideoid: 0tUwn8DHo3s
qualityfocus: complete
qualitydate: 06/22/2016
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/18/2018
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 3e3e8c315baa96d1af1eeaf40c7b60648d0b797e
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/24/2018
---
# <a name="share-a-filtered-power-bi-report-with-your-coworkers"></a>Filtre uygulanmış bir Power BI raporunu iş arkadaşlarınızla paylaşın
*Paylaşım*, kullanıcıların, panolarınıza ve raporlarınıza erişmesini sağlamanın iyi bir yoludur. Power BI ayrıca [işbirliği yapmak ve raporlarınızı dağıtmak için çeşitli yollar sunar](service-how-to-collaborate-distribute-dashboards-reports.md).

Paylaşımda siz ve alıcılarınız için bir [Power BI Pro lisansı](service-free-vs-pro.md) gereklidir veya içerik [Premium kapasitede](service-premium.md) olmalıdır. Önerileriniz mi var? Power BI ekibi geri bildirimlerinize her zaman önem verir. [Power BI Topluluğu sitesine](https://community.powerbi.com/) gitmeye ne dersiniz?

Sizinle aynı e-posta etki alanında bulunan iş arkadaşlarınızla, Power BI hizmetinin birçok yerinden bir raporu paylaşabilirsiniz: Sık Kullanılanlar, En Son, Benimle Paylaşılanlar (sahip izin verirse), Çalışma Alanım veya diğer çalışma alanları. Bir raporu paylaştığınızda, paylaştığınız kişiler raporu görüntüleyebilir ve raporla etkileşim kurabilir ancak raporu düzenleyemez. [Satır düzeyi güvenlik (RLS)](service-admin-rls.md) uygulanmadığı sürece raporda sizin gördüğünüz verilerin aynılarını görürler. 

## <a name="filter-and-share-a-report"></a>Rapor filtreleme ve paylaşma
Bir raporun filtrelenmiş bir sürümünü paylaşmak istediğinizde ne olur? Bu, yalnızca belirli bir şehre veya satış temsilcisine ya da yıla ait verileri gösteren bir rapor olabilir. Bunun için bir özel URL oluşturmanız gerekir.

1. Raporu [Düzenleme görünümü](service-reading-view-and-editing-view.md)'nde açın, filtreyi uygulayın ve raporu kaydedin.
   
   Bu örnekte yalnızca **Territory**'nin **NC**'ye eşit olduğu değerleri göstermek için [Perakende Analizi örneği](sample-tutorial-connect-to-the-samples.md)'ni filtreliyoruz.
   
   ![Rapor filtresi bölmesi](media/service-share-reports/power-bi-filter-report2.png)
2. Aşağıdakini rapor sayfası URL'sinin sonuna ekleyin:
   
   ?filter=*tabloadı*/*alanadı* eq *değer*
   
    Alan **dize** türünde olmalıdır ve *tabloadı* veya *alanadı* boşluk içeremez.
   
   Bizim örneğimizde, tablonun adı **Store**, alanın adı **Territory** ve filtrelemek istediğimiz değer **NC**'dir:
   
    ?filter=Store/Territory eq 'NC'
   
   ![Filtrelenmiş rapor URL'si](media/service-share-reports/power-bi-filter-url3.png)
   
   Tarayıcınız eğik çizgileri, boşlukları ve kesme işaretlerini göstermek için özel karakterler ekler; böylece, aşağıdaki gibi bir URL elde edersiniz:
   
   app.powerbi.com/groups/me/reports/010ae9ad-a9ab-4904-a7a1-xxxxxxxxxxxx/ReportSection2?filter=Store%252FTerritory%20eq%20%27NC%27

3. [Raporu paylaşın](service-share-dashboards.md), ancak **Alıcılara e-posta bildirimi gönder** onay kutusunun işaretini kaldırın. 

    ![Raporu paylaş iletişim kutusu](media/service-share-reports/power-bi-share-report-dialog.png)

4. Daha önce oluşturduğunuz filtreyi içeren bağlantıyı gönderin.

## <a name="next-steps"></a>Sonraki adımlar
* Geri bildirimde bulunmak ister misiniz? [Power BI Topluluğu sitesine](https://community.powerbi.com/) giderek önerilerinizi belirtin.
* [Panolar ve raporlar üzerinde nasıl işbirliği yapabilir ve bunları nasıl paylaşabilirim?](service-how-to-collaborate-distribute-dashboards-reports.md)
* [Bir panoyu paylaşma](service-share-dashboards.md)
* Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/).

