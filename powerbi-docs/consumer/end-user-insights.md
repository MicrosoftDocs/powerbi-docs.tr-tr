---
title: Pano kutucuklarında içgörüleri çalıştırma ve görüntüleme
description: Power BI son kullanıcısı olarak, pano kutucuklarınız hakkındaki öngörüleri nasıl edineceğinizi öğrenin.
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: et_MLSL2sA8
ms.custom: seodec18
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2018
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: dd59f572da6bb3b62fa142ea7b7eab4aef5a3466
ms.sourcegitcommit: f25464d5cae46691130eb7b02c33f42404011357
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53180542"
---
# <a name="view-data-insights-on-dashboard-tiles-with-power-bi"></a>Power BI ile pano kutucuklarında veri içgörülerini görüntüleme
Panonuzdaki her görselleştirme kutucuğu, veri keşif dünyasına açılan bir yoldur. Bir kutucuğu seçtiğinizde açılan raporda bulunan veri kümesini filtreleyebilir, sıralayabilir ve ayrıntılarına inebilirsiniz. İçgörü çalıştırdığınızda Power BI veri keşfini sizin yerinize gerçekleştirir.

Verilerinizi temel alan ilgi çekici ve etkileşimli görselleştirmeler oluşturmak için hızlı öngörüler çalıştırın. Belirli bir pano kutucuğunda hızlı içgörüler çalıştırabilir ve hatta bir içgörü üzerinde içgörü çalıştırabilirsiniz!

Öngörü özelliği Microsoft Research ekibiyle birlikte geliştirilen ve sayısı artmaya devam eden [gelişmiş analiz algoritmaları kümesi](end-user-insight-types.md) üzerine kurulmuştur. Bu özelliği, daha fazla kullanıcının, verilerindeki öngörülere yeni ve sezgisel yöntemlerle ulaşmasını sağlamak için kullanmaya devam edeceğiz.

## <a name="run-insights-on-a-dashboard-tile"></a>Bir pano kutucuğu üzerinde öngörüler çalıştırma
Bir pano kutucuğunda içgörü çalıştırdığınızda Power BI yalnızca o pano kutucuğunu oluşturmak için kullanılan verilerde arama yapar. 

1. [Bir pano açın](end-user-dashboards.md).
2. Bir kutucuğun üzerine gelin, üç nokta (...) simgesini ve **İçgörüleri görüntüle**'yi seçin. 

    ![üç nokta menüsü modu](./media/end-user-insights/power-bi-hover.png)


3. Kutucuk, öngörü kartları sağ tarafta görüntülenecek şekilde [Odak modunda](end-user-focus.md) açılır.    
   
    ![Odak modu](./media/end-user-insights/pbi-insights-tile.png)    
4. Öngörülerden biri ilginizi mi çekti? İlgili öngörü kartını seçerek detaylandırabilirsiniz. Seçilen öngörü sol tarafta, yalnızca bu tek öngörüdeki verileri temel alan yeni öngörü kartları da sağ tarafta görüntülenir.    

 ## <a name="interact-with-the-insight-cards"></a>Öngörü kartlarıyla etkileşim kurma
Açık bir içgörünüz olduğunda keşfetmeye devam edin.

   * Tuval üzerinde görseli filtreleyin.  Filtreleri görüntülemek için sağ üst köşedeki oku seçerek Filtreler bölmesini genişletin.

     ![genişletilmiş içgörü ve Filtreler menüsü](./media/end-user-insights/power-bi-insights-on-insights.png)
   
   * İçgörü kartı üzerinde içgörü çalıştırın. Bunlar genellikle **ilgili içgörüler** olarak adlandırılır. Sağ üst köşede, ampul simgesini ![İçgörü al simgesi](./media/end-user-insights/power-bi-bulb-icon.png) veya **İçgörü al**’ı seçin.
     
     ![Öngörü Al simgesini gösteren menü çubuğu](./media/end-user-insights/power-bi-autoinsights-tile.png)
     
     Öngörü sol tarafta, yalnızca bu tek öngörüdeki verileri temel alan yeni kartlar da sağ tarafta görüntülenir.
     
     ![öngörüler seçeneğinde öngörüler](./media/end-user-insights/power-bi-insights-on-insights-new.png)

Özgün içgörü tuvaline geri dönmek için sol üst köşedeki **Odak modundan çık**'ı seçin.

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme
- **İçgörüleri görüntüle** komutu DirectQuery ile birlikte çalışmaz. Yalnızca Power BI'a yüklenmiş olan verilerle birlikte çalışır.
- **İçgörüleri görüntüle** tüm pano kutucuğu türleriyle çalışmaz. Örneğin özel görsellerle kullanılamaz.<!--[custom visuals](end-user-custom-visuals.md)-->


## <a name="next-steps"></a>Sonraki adımlar
[Kullanılabilir Hızlı Öngörü türleri](end-user-insight-types.md) hakkında daha fazla bilgi edinin

