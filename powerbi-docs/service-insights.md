---
title: Power BI ile otomatik olarak veri içgörüleri oluşturma
description: Veri kümeleriniz ve pano kutucuklarınız hakkındaki öngörüleri nasıl edineceğinizi öğrenin.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
featuredvideoid: et_MLSL2sA8
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2018
ms.author: maggies
LocalizationGroup: Dashboards
ms.openlocfilehash: 9e1c4a3942c75f41dc105e424685d32badbf3866
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "61238648"
---
# <a name="generate-data-insights-automatically-with-power-bi"></a>Power BI ile otomatik olarak veri içgörüleri oluşturma
Yeni bir veri kümeniz var ve keşfetmeye nereden başlayacağınızı bilemiyor musunuz?  Hızla bir pano mu oluşturmanız gerekiyor?  Gözünüzden kaçmış olabilecek öngörülere göz atmak mı istiyorsunuz?

Verilerinizi temel alan ilgi çekici ve etkileşimli görselleştirmeler oluşturmak için hızlı öngörüler çalıştırın. Hızlı öngörüler, bir veri kümesinin tamamında (hızlı öngörüler) veya belirli bir pano kutucuğu üzerinde (kapsamlı öngörüler) çalıştırılabilir. Bir öngörü üzerinde bile hızlı öngörüler çalıştırabilirsiniz!

> [!NOTE]
> İçgörüler DirectQuery ile birlikte çalışmaz. Yalnızca Power BI’a yüklenmiş olan verilerle birlikte çalışır.
> 

Öngörü özelliği Microsoft Research ekibiyle birlikte geliştirilen ve sayısı artmaya devam eden [gelişmiş analiz algoritmaları kümesi](service-insight-types.md) üzerine kurulmuştur. Bu özelliği, daha fazla kullanıcının, verilerindeki öngörülere yeni ve sezgisel yöntemlerle ulaşmasını sağlamak için kullanmaya devam edeceğiz.

## <a name="run-quick-insights-on-a-dataset"></a>Bir veri kümesi üzerinde hızlı öngörüler çalıştırma
Bir veri kümesi üzerinde hızlı öngörüler çalıştıran, öngörüleri Odak modunda açan, öngörülerden birini panosuna kutucuk olarak sabitleyen ve bir görsel için öngörüler edinen Amanda'yı izleyin.

<iframe width="560" height="315" src="https://www.youtube.com/embed/et_MLSL2sA8" frameborder="0" allowfullscreen></iframe>


Şimdi sıra sizde. [Tedarikçi Kalite Analizi örneğini](sample-supplier-quality.md) kullanarak öngörüler keşfedin.

1. **Veri kümeleri** sekmesinde, üç nokta simgesini (...) ve **Öngörü al**'ı seçin.
   
    ![Veri Kümeleri sekmesi](media/service-insights/power-bi-ellipses.png)
   
    ![üç nokta menüsü](media/service-insights/power-bi-tab.png)
2. Power BI [çeşitli algoritmalar](service-insight-types.md) kullanarak veri kümenizdeki eğilimleri arar.
   
    ![Öngörüler aranıyor iletişim kutusu](media/service-insights/pbi_autoinsightssearching.png)
3. Öngörüleriniz saniyeler içinde hazır duruma gelir.  Görselleştirmeleri görüntülemek için **Öngörüleri görüntüle**'yi seçin.
   
    ![başarılı iletisi](media/service-insights/pbi_autoinsightsuccess.png)
   
    > [!NOTE]
    > Bazı veri kümelerindeki veriler istatistiksel olarak önemsiz olduğundan bu veri kümelerinde içgörü oluşturulamaz.  Daha fazla bilgi için bkz. [Verilerinizi öngörüler için en iyi duruma getirme](service-insights-optimize.md).
   > 
    
1. Görselleştirmeler, en fazla 32 ayrı öngörü kartını destekleyen özel bir **Hızlı Öngörüler** tuvalinde görüntülenir. Her kartta bir grafik veya graf ile kısa bir açıklama bulunur.
   
    ![Hızlı Öngörüler tuvali](media/service-insights/power-bi-insights.png)

## <a name="interact-with-the-insight-cards"></a>Öngörü kartlarıyla etkileşim kurma
  ![raptiye simgesi](media/service-insights/pbi_hover.png)

1. Kartlardan birinin üzerine gelin ve görselleştirmeyi bir panoya eklemek için raptiye simgesini seçin.
2. Bir kartın üzerine gelin, üç nokta (...) simgesini ve ardından **Öngörüleri görüntüle**'yi seçin. Böylece öngörü tam ekran olarak açılır.
   
    ![Öngörü tam ekranı](media/service-insights/power-bi-insight-focus.png)
3. Odak modunda şunları yapabilirsiniz:
   
   * Görselleştirmeleri filtreleyebilirsiniz.  Filtreleri görüntülemek için sağ üst köşedeki oku seçerek Filtreler bölmesini genişletin.
        ![genişletilmiş öngörü ve Filtreler menüsü](media/service-insights/power-bi-insights-filter-new.png)
   * Raptiye ![raptiye simgesi](media/service-insights/power-bi-pin-icon.png) simgesini veya **Görseli sabitle**’yi seçerek öngörü kartını bir panoya sabitleyin.
   * Kart üzerinde öngörüler çalıştırın. Bunlar genellikle **kapsamlı öngörüler** olarak adlandırılır. Sağ üst köşede, ampul simgesini ![Öngörü al simgesi](media/service-insights/power-bi-bulb-icon.png) veya **Öngörü al**’ı seçin.
     
       ![Öngörü Al simgesini gösteren menü çubuğu](media/service-insights/pbi-autoinsights-tile.png)
     
     Öngörü sol tarafta, yalnızca bu tek öngörüdeki verileri temel alan yeni kartlar da sağ tarafta görüntülenir.
     
       ![öngörüler seçeneğinde öngörüler](media/service-insights/power-bi-insights-on-insights-new.png)
4. Özgün öngörü tuvaline geri dönmek için sol üst köşedeki **Odak modundan çık**'ı seçin.

## <a name="run-insights-on-a-dashboard-tile"></a>Bir pano kutucuğu üzerinde öngörüler çalıştırma
Öngörüleri bir veri kümesinin tamamında aramak yerine aramanızı tek bir pano kutucuğunu oluşturmak için kullanılan verilerle sınırlayabilirsiniz. Bunlar da genellikle **kapsamlı öngörüler** olarak adlandırılır.

1. Bir pano açın.
2. Bir kutucuğun üzerine gelin, üç nokta (...) simgesini ve ardından **Öngörüleri görüntüle**'yi seçin. Kutucuk, öngörü kartları sağ tarafta görüntülenecek şekilde [Odak modunda](service-focus-mode.md) açılır.    
   
    ![Odak modu](media/service-insights/pbi-insights-tile.png)    
4. Öngörülerden biri ilginizi mi çekti? İlgili öngörü kartını seçerek detaylandırabilirsiniz. Seçilen öngörü sol tarafta, yalnızca bu tek öngörüdeki verileri temel alan yeni öngörü kartları da sağ tarafta görüntülenir.    
6. Verilerinizi ayrıntılı olarak incelemeye devam edin, ilginizi çeken bir öngörü bulduğunuzda sağ üst köşedeki **Görseli sabitle**'yi seçerek bu öngörüyü panonuza sabitleyin.

## <a name="next-steps"></a>Sonraki adımlar
Bir veri kümesine sahipseniz [bu veri kümesini Hızlı Öngörüler için en iyi duruma getirebilirsiniz](service-insights-optimize.md)

[Kullanılabilir Hızlı Öngörü türleri](service-insight-types.md) hakkında daha fazla bilgi edinin

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

