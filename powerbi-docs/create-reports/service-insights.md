---
title: Veri kümenizden otomatik veri içgörüleri oluşturma
description: Veri kümeleriniz ve pano kutucuklarınız hakkındaki öngörüleri nasıl edineceğinizi öğrenin.
author: maggiesMSFT
ms.reviewer: ''
featuredvideoid: et_MLSL2sA8
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
ms.date: 09/28/2020
ms.author: maggies
LocalizationGroup: Dashboards
ms.openlocfilehash: 79148389a697feb2a3d2e2cba0b919eb59632ff7
ms.sourcegitcommit: d153cfc0ce559480c53ec48153a7e131b7a31542
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91524478"
---
# <a name="generate-data-insights-on-your-dataset-automatically-with-power-bi"></a>Power BI ile veri kümenizden otomatik veri içgörüleri oluşturma
Yeni bir veri kümeniz var ve keşfetmeye nereden başlayacağınızı bilemiyor musunuz?  Hızla bir pano mu oluşturmanız gerekiyor?  Gözünüzden kaçmış olabilecek öngörülere göz atmak mı istiyorsunuz?

Verilerinizi temel alan ilgi çekici görselleştirmeler oluşturmak için hızlı içgörüler çalıştırın. Bu makalede bir veri kümesinin tamamında hızlı içgörü (hızlı içgörüler) çalıştırma adımları verilmiştir. İsterseniz [belirli bir pano kutucuğunu temel alan hızlı içgörüler ](../consumer/end-user-insights.md) (kapsamlı içgörüler) de çalıştırabilirsiniz. Bir öngörü üzerinde bile hızlı öngörüler çalıştırabilirsiniz!

> [!NOTE]
> İçgörüler DirectQuery ile birlikte çalışmaz. Yalnızca Power BI’a yüklenmiş olan verilerle birlikte çalışır.
> 

İçgörü özelliği, Microsoft Research ekibi tarafından sürekli olarak geliştirilen [gelişmiş analitik algoritmaları](../consumer/end-user-insight-types.md) temel alır. İnsanların verileriyle ilgili içgörülere yeni ve sezgisel bir şekilde ulaşmasına yardımcı olmak için bu algoritmaları kullanmaya devam ediyoruz. [Verilerinizi hızlı içgörüler için iyileştirmeyi](service-insights-optimize.md) öğrenmek de isteyebilirsiniz.

## <a name="run-quick-insights-on-a-dataset"></a>Bir veri kümesi üzerinde hızlı öngörüler çalıştırma
Bir veri kümesi üzerinde hızlı içgörüler çalıştıran ve içgörülerden birini Odak modunda açan Amanda'yı izleyin. Amanda, içgörüyü panoya kutucuk olarak sabitleyip pano kutucuğuyla ilgili içgörüler alıyor.

<iframe width="560" height="315" src="https://www.youtube.com/embed/et_MLSL2sA8" frameborder="0" allowfullscreen></iframe>


Şimdi sıra sizde. [Tedarikçi Kalite Analizi örneğini](sample-supplier-quality.md) kullanarak içgörüleri keşfedin.

1. **Veri Kümeleri** sekmesinden **Diğer seçenekler** (...) ve sonra **Hızlı içgörüler alın**’ı seçin.
   
    ![Veri Kümeleri sekmesi](media/service-insights/power-bi-ellipses.png)
   
    ![Üç nokta menüsü](media/service-insights/power-bi-tab.png)
2. Power BI [çeşitli algoritmalar](../consumer/end-user-insight-types.md) kullanarak veri kümenizdeki eğilimleri arar.
   
    ![Öngörüler aranıyor iletişim kutusu](media/service-insights/pbi_autoinsightssearching.png)
3. Öngörüleriniz saniyeler içinde hazır duruma gelir.  Görselleştirmeleri görüntülemek için **Öngörüleri görüntüle**'yi seçin.
   
    ![Başarılı iletisi](media/service-insights/pbi_autoinsightsuccess.png)
   
    > [!NOTE]
    > Bazı veri kümelerindeki veriler istatistiksel olarak önemsiz olduğundan bu veri kümelerinde içgörü oluşturulamaz.  Daha fazla bilgi için bkz. [Verilerinizi öngörüler için en iyi duruma getirme](service-insights-optimize.md).
    > 
    
4. Görselleştirmeler, en fazla 32 ayrı öngörü kartını destekleyen özel bir **Hızlı Öngörüler** tuvalinde görüntülenir. Her kartta bir grafik veya graf ile kısa bir açıklama bulunur.
   
    ![Hızlı Öngörüler tuvali](media/service-insights/power-bi-insights.png)

## <a name="interact-with-the-insight-cards"></a>Öngörü kartlarıyla etkileşim kurma

1. Kartlardan birinin üzerine gelin ve görselleştirmeyi bir panoya eklemek için raptiye simgesini seçin.

2. Bir kartın üzerine gelin, **Diğer seçenekler** (...) ve sonra **İçgörüleri görüntüle**’yi seçin. 

    İçgörü ekranı Odak modunda açılır.
   
    ![İçgörü Odak modu](media/service-insights/power-bi-insight-focus.png)
3. Odak modunda şunları yapabilirsiniz:
   
   * Görselleştirmeleri filtreleyebilirsiniz. **Filtreler** bölmesi zaten açık değilse, pencerenin sağ tarafındaki oku seçerek genişletin.

       ![Genişletilmiş İçgörü Filtreleri menüsü](media/service-insights/power-bi-insights-filter-new.png)
   * **Görseli sabitle**'yi seçerek içgörü kartını bir panoya sabitleyebilirsiniz.
   * İçgörüyü kart üzerinde çalıştırın. Bu durum genellikle *kapsama alınmış içgörüler* olarak adlandırılır. Sağ üst köşede, ampul simgesini ![İçgörü al simgesi](media/service-insights/power-bi-bulb-icon.png) veya **İçgörü al**’ı seçin.
     
       ![İçgörü Al simgesi](media/service-insights/pbi-autoinsights-tile.png)
     
     Sol tarafta içgörü görüntülenir. Yalnızca bu tek içgörüdeki verileri temel alan yeni kartlar sağ tarafta görüntülenir.
     
       ![İçgörüler üzerinde içgörüler](media/service-insights/power-bi-insights-on-insights-new.png)
4. Özgün öngörü tuvaline geri dönmek için sol üst köşedeki **Odak modundan çık**'ı seçin.

## <a name="next-steps"></a>Sonraki adımlar
- Bir veri kümesine sahipseniz [bu veri kümesini Hızlı İçgörüler için en iyi duruma getirebilirsiniz](service-insights-optimize.md).
- [Kullanılabilir Hızlı İçgörü türleri](../consumer/end-user-insight-types.md) hakkında bilgi edinin.

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/).
