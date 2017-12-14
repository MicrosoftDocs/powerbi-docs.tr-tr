---
title: "Power BI'da Hızlı Öngörüler edinin"
description: "Power BI hizmetindeki Hızlı Öngörüler özelliğini çalıştırma ve kullanma hakkında belge."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: et_MLSL2sA8
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/01/2017
ms.author: mihart
ms.openlocfilehash: 8b069f29737992817d20396007864cc8c005ca99
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2017
---
# <a name="quick-insights-with-power-bi"></a>Power BI ile Hızlı Öngörüler
Yeni bir veri kümeniz var ve keşfetmeye nereden başlayacağınızı bilemiyor musunuz?  Hızla bir pano mu oluşturmanız gerekiyor?  Gözünüzden kaçmış olabilecek öngörülere hızla göz atmak mı istiyorsunuz?

Verilerinizi temel alan ilgi çekici ve etkileşimli görselleştirmeler oluşturmak için Hızlı Öngörüler özelliğini çalıştırın. Hızlı Öngörüler, bir veri kümesinin tamamında (Hızlı Öngörüler) veya belirli bir pano kutucuğu üzerinde (Kapsamlı Öngörüler) çalıştırılabilir. Hızlı Öngörüler'i bir Öngörü üzerinde bile çalıştırabilirsiniz!

> **NOT**: Hızlı Öngörüler DirectQuery ile birlikte çalışmaz. Yalnızca Power BI'a yüklenmiş olan verilerle birlikte çalışır.
> 
> 

Hızlı Öngörüler özelliği Microsoft Research ekibiyle birlikte geliştirilen ve sayısı artmaya devam eden [gelişmiş analiz algoritmaları kümesi](service-insight-types.md) üzerine kurulmuştur. Bu özelliği, daha fazla kullanıcının, verilerindeki öngörülere yeni ve sezgisel yöntemlerle ulaşmasını sağlamak için kullanmaya devam edeceğiz.

## <a name="run-quick-insights-on-a-dataset"></a>Hızlı Öngörüler'i bir veri kümesi üzerinde çalıştırma
Bir veri kümesi üzerinde Hızlı Öngörüler özelliğini çalıştıran, Öngörü'leri Odak modunda açan, Hızlı Öngörüler'den birini panosuna kutucuk olarak sabitleyen ve Hızlı Öngörüler'i bir görsel için kullanan Amanda'yı izleyin.

<iframe width="560" height="315" src="https://www.youtube.com/embed/et_MLSL2sA8" frameborder="0" allowfullscreen></iframe>


Şimdi sıra sizde. [Tedarikçi Kalite Analizi örneğini](sample-supplier-quality.md) kullanarak Hızlı Öngörüler'i keşfedin.

1. **Veri kümeleri** sekmesinden üç nokta simgesini (...) ve **Öngörü Al**'ı seçin.
   
    ![](media/service-insights/power-bi-ellipses.png)
   
    ![](media/service-insights/power-bi-tab.png)
2. Power BI [çeşitli algoritmalar](service-insight-types.md) kullanarak veri kümenizdeki eğilimleri arar.
   
    ![](media/service-insights/pbi_autoinsightssearching.png)
3. Öngörüleriniz saniyeler içinde hazır duruma gelir.  Görselleştirmeleri görüntülemek için **Öngörüleri Görüntüle**'yi seçin.
   
    ![](media/service-insights/pbi_autoinsightsuccess.png)
   
   > **NOT**: Bazı veri kümelerindeki veriler istatistiksel olarak önemsiz olduğundan bu veri kümelerinde Hızlı Öngörüler oluşturulamaz.  Daha fazla bilgi için bkz. [Verilerinizi Hızlı Öngörüler için en iyi duruma getirme](service-insights-optimize.md).
   > 
   > 
4. Görselleştirmeler, en fazla 32 ayrı öngörü kartını destekleyen özel bir **Hızlı Öngörüler** tuvalinde görüntülenir. Her kartta bir grafik veya graf ile kısa bir açıklama bulunur.
   
    ![](media/service-insights/power-bi-insights.png)

## <a name="interact-with-the-quick-insight-cards"></a>Hızlı Öngörüler kartlarıyla etkileşim kurma
  ![](media/service-insights/pbi_hover.png)

1. Kartlardan birinin üzerine gelin ve görselleştirmeyi bir panoya eklemek için raptiye simgesini seçin.
2. Kartlardan birinin üzerine gelin ve kartı tam ekran görüntülemek için Odak modu simgesini seçin.
   
    ![](media/service-insights/power-bi-insight-focus.png)
3. Odak modunda şunları yapabilirsiniz:
   
   * Görselleştirmeleri [filtreleyebilirsiniz](service-interact-with-a-report-in-reading-view.md).  Filtreleri görüntülemek için sağ üst köşedeki oku seçerek Filtreler bölmesini genişletin.
     
        ![](media/service-insights/power-bi-insights-filter-new.png)
   * Raptiye ![](media/service-insights/power-bi-pin-icon.png)  simgesini veya **Görseli sabitle**'yi seçerek öngörü kartını bir panoya sabitleyebilirsiniz.
   * Kart üzerinde Hızlı Öngörüler özelliğini çalıştırın. Bu işlem **Kapsamlı Hızlı Öngörüler** olarak adlandırılır. Sağ üst köşedeki ampul simgesini ![](media/service-insights/power-bi-bulb-icon.png)  veya **Öngörü Al**'ı seçin.
     
       ![](media/service-insights/pbi-autoinsights-tile.png)
     
     Hızlı Öngörüler sol tarafta, yalnızca tek bir Hızlı Öngörü'deki verileri temel alan yeni kartlar da sağ tarafta görüntülenir.
     
       ![](media/service-insights/power-bi-insights-on-insights-new.png)
4. Özgün Hızlı Öngörüler tuvaline geri dönmek için sol üst köşedeki **Odak modundan çık**'ı seçin.

## <a name="run-quick-insights-on-a-dashboard-tile"></a>Hızlı Öngörüler'i bir pano kutucuğu üzerinde çalıştırma
Öngörüleri bir veri kümesinin tamamında aramak yerine aramanızı tek bir pano kutucuğunu oluşturmak için kullanılan verilerle sınırlayabilirsiniz. Bu işlem **Kapsamlı Hızlı Öngörüler** olarak adlandırılır.

1. Bir pano açın.
2. Bir kutucuk seçin ve [kutucuğu Odak modunda açın](service-focus-mode.md).
3. Sol üst köşedeki **Öngörü Al**'ı seçin.
   
    ![](media/service-insights/pbi-autoinsights-tile.png)
4. Power BI, kutucuğun sağ tarafında öngörü kartlarını görüntüler.
   
    ![](media/service-insights/pbi-insights-tile.png)
5. Öngörülerden biri ilginizi mi çekti? İlgili öngörü kartını seçerek detaylandırabilirsiniz. Seçilen Hızlı Öngörü sol tarafta, yalnızca tek bir Hızlı Öngörü'deki verileri temel alan yeni öngörü kartları da sağ tarafta görüntülenir.
6. Verileri detaylandırmaya devam edin ve ilginizi çeken bir Hızlı Öngörü bulduğunuzda sağ üst köşedeki **Görseli sabitle**'yi seçerek görselini panonuza sabitleyin. Dilerseniz ilgili veri kümesinin sahibine geri bildirim göndererek bulduğunuz Hızlı Öngörü'nün faydalı olup olmadığını belirtebilirsiniz.
   
    ![](media/service-insights/useful.png)

## <a name="next-steps"></a>Sonraki adımlar
Bir veri kümesine sahipseniz [bu veri kümesini Hızlı Öngörüler için en iyi duruma getirebilirsiniz](service-insights-optimize.md)

[Kullanılabilir Hızlı Öngörü türleri](service-insight-types.md) hakkında daha fazla bilgi edinin

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

