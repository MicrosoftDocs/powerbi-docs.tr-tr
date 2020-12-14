---
title: Raporlardan Power BI panolarına kutucuk sabitleme
description: Bir rapordan bir kutucuğu Power BI panosuna sabitleyin.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
featuredvideoid: lJKgWnvl6bQ
ms.service: powerbi
ms.subservice: pbi-reports-dashboards
ms.topic: how-to
ms.date: 12/03/2020
LocalizationGroup: Dashboards
ms.openlocfilehash: ad3a38fa8aef4f5404196213ebd3c7b26d3fc3b8
ms.sourcegitcommit: cb6e0202de27f29dd622e47b305c15f952c5769b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2020
ms.locfileid: "96578418"
---
# <a name="pin-a-tile-to-a-power-bi-dashboard-from-a-report"></a>Raporlardan Power BI panolarına kutucuk sabitleme

[Pano kutucuğu](../consumer/end-user-tiles.md) eklemenin yollarından biri, bu işlemi bir [Power BI raporundan](../consumer/end-user-reports.md) gerçekleştirmektir. Bu kutucuklardan birini seçtiğinizde kutucuk raporda açılır.

Rapor sayfasının tamamı panoya sabitlenebilir ve bu işlem *canlı* kutucuk sabitleme olarak adlandırılır. Canlı kutucuk olarak adlandırılır çünkü panodaki kutucukla etkileşim kurabilirsiniz. Tek tek görselleştirme kutucuklarından farklı olarak, raporda yapılan değişiklikler otomatik olarak panoyla eşitlenir. Daha fazla bilgi için bkz. [Rapor sayfasının tamamını sabitleme](#pin-an-entire-report-page).

Sizinle veya Power BI Desktop'tan paylaşılmış olan raporlardan kutucuk sabitleyemezsiniz. 

> [!TIP]
> Bazı görselleştirmeler arka plan resimleri kullandığından, arka plan resmi fazla büyük olduğunda sabitleme çalışmayabilir. Resmin boyutunu azaltın veya resmi sıkıştırın.  
> 
> 

## <a name="pin-a-tile-from-a-report"></a>Bir rapordan kutucuk sabitleme
Aşağıdaki videoda Amanda, bir Power BI raporundan görseller ve resimler sabitleyerek bir pano oluşturmaktadır.
    

<iframe width="560" height="315" src="https://www.youtube.com/embed/lJKgWnvl6bQ" frameborder="0" allowfullscreen></iframe>

Şimdi Power BI örnek raporlarından birini kullanarak kendi panonuzu oluşturun.

1. Raporda, sabitlemek istediğiniz görselleştirmenin üzerine gelin ve raptiye simgesini seçin. ![Raptiye simgesi](media/service-dashboard-pin-tile-from-report/pbi_pintile_small.png). Bu işlemin ardından Power BI, **Panoya sabitle** ekranını açar.
   
     ![Panoya sabitle penceresi](media/service-dashboard-pin-tile-from-report/pbi_themes2.png)
2. Var olan bir panoya mı yoksa yeni bir panoya mı sabitlemek istediğinizi seçin.
   
   * **Var olan pano**: Açılan listeden panonun adını seçin. Sizinle paylaşılan panolar açılan listede görünmez.
   * **Yeni pano**: Yeni panonun adını girin.
3. Bazı durumlarda, sabitlediğiniz öğeye önceden bir *tema* uygulanmış olabilir. Örneğin, bir Excel çalışma kitabından sabitlenen görseller. Bu durumda, kutucuğa uygulanacak temayı seçin.
4. **Sabitle**'yi seçin.
   
   Sağ üst köşeye yakın bir noktada çıkan başarılı iletisi, görselleştirmenin bir kutucuk olarak panonuza eklendiğini bildirir.
   
   ![Başarılı iletisi](media/service-dashboard-pin-tile-from-report/pinsuccess.png)
5. Gezinti bölmesinden yeni kutucuk içeren panoyu seçin. [Kutucuğun görüntüsünü ve davranışını düzenleyin](service-dashboard-edit-tile.md) veya kutucuğu seçerek rapora dönün.

## <a name="pin-an-entire-report-page"></a>Bir rapor sayfasının tamamını sabitleme
Diğer bir seçenek de bir rapor sayfasının tamamını panoya sabitlemektir ve bu bir kerede birden çok görselleştirmeyi sabitlemenin kolay bir yoludur. Sayfanın tamamını sabitlediğinizde kutucuklar *canlı* olur. Başka bir deyişle kutucuklarla panoda etkileşim kurabilirsiniz. Rapor düzenleyicisinde herhangi bir görselleştirme üzerinde yaptığınız değişiklikler (filtre ekleme veya grafikte kullanılan alanları değiştirme gibi) pano kutucuğu için de geçerli olur.  

Daha fazla bilgi için bkz. [Rapor sayfasının tamamını sabitleme](service-dashboard-pin-live-tile-from-report.md).

## <a name="limitations"></a>Sınırlamalar
Bazı rapor biçimlendirme seçenekleri veya temalar, panoya sabitlediğiniz görsellere uygulanmaz.
- Sabitlenmiş kutucukta kenarlık, gölge ve arka plan ayarları yoksayılır.
- Kart görselleri için, değerde kullanılan metin panolarda “DIN” yazı tipi ailesi kullanılarak ve siyah metinle gösterilir. [Özel bir pano teması oluşturarak](service-dashboard-themes.md) bir panodaki tüm kutucukların metin rengini değiştirebilirsiniz.
- Koşullu biçimlendirme uygulanmaz.
- Görsellerin boyutu, kutucuğun boyutuna göre ayarlanır. Bu nedenle görsel raporda yeniden boyutlandırılmış gibi görünebilir ve rapor düzeni değişebilir.

## <a name="next-steps"></a>Sonraki adımlar
- [Panoların Power BI hizmeti tüketicileri için anlamı](../consumer/end-user-dashboards.md)
- [Power BI'daki pano kutucukları](../consumer/end-user-tiles.md)
- [Power BI'daki raporlar](../consumer/end-user-reports.md)
- [Power BI'da veri yenileme](../connect-data/refresh-data.md)
- [Power BI hizmetinde tasarımcılara yönelik temel kavramlar](../fundamentals/service-basic-concepts.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)
