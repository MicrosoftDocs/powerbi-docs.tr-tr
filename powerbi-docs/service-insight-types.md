---
title: "Power BI tarafından desteklenen Hızlı Öngörü türleri"
description: "Power BI ile Hızlı Öngörüler."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/03/2017
ms.author: mihart
ms.openlocfilehash: 13f5614cf121b17d8ae4dff9653f5789372f7f49
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2017
---
# <a name="types-of-quick-insights-supported-by-power-bi"></a>Power BI tarafından desteklenen Hızlı Öngörü türleri
## <a name="how-does-quick-insights-work"></a>Hızlı Öngörüler nasıl çalışır?
Power BI ilgi çekici olabilecek öngörüleri keşfetmek için bir karmaşık algoritma kümesi uygulayarak veri kümenizin farklı alt kümelerinde hızlıca arama yapar. Power BI, ayrılan bir sürede bir veri kümesinin mümkün olduğu kadar büyük bir kısmını tarar.

Bir veri kümesine veya kutucuğa (İlgili Öngörüler) yönelik olarak Hızlı Öngörüleri çalıştırabilirsiniz.   

## <a name="what-types-of-quick-insights-can-we-find"></a>Hangi Hızlı Öngörü türlerini bulabiliriz?
Kullandığımız bazı algoritmalar şunlardır:

## <a name="category-outliers-topbottom"></a>Kategori aykırı değerleri (üst/alt)
Modeldeki bir ölçü için bir boyutun bir veya iki üyesinin, boyutun diğer üyelerinden daha büyük değerlere sahip olduğu durumları vurgular.  

![](media/service-insight-types/pbi_auto_insight_types_category_outliers.png)

## <a name="change-points-in-a-time-series"></a>Zaman serilerindeki değişim noktaları
Verilere ilişkin bir zaman serisindeki eğilimlerde görülen önemli değişiklikleri vurgular.

![](media/service-insight-types/pbi_auto_insight_types_changepoint.png)

## <a name="correlation"></a>Bağıntı
Veri kümesindeki bir boyuta göre değerlendirilen birden fazla ölçü arasında bağıntı görülen durumları algılar.

![](media/service-insight-types/pbi_auto_insight_types_correlation.png)

## <a name="low-variance"></a>Düşük Varyans
Veri noktalarının ortalamaya yakın olduğu durumları algılar.

![](media/service-insight-types/power-bi-low-variance.png)

## <a name="majority-major-factors"></a>Çoğunluk (Ana etkenler)
Bir toplam değerin çoğunluğunun, başka bir boyuta göre değerlendirildiğinde tek bir etkenle ilişkilendirilebildiği durumları bulur.  

![](media/service-insight-types/pbi_auto_insight_types_majority.png)

## <a name="overall-trends-in-time-series"></a>Zaman serisindeki genel eğilimler
Zaman serisi verilerinde görülen yukarı veya aşağı yönlü eğilimleri algılar.

![](media/service-insight-types/pbi_auto_insight_types_trend.png)

## <a name="seasonality-in-time-series"></a>Zaman serisinde mevsimsellik
Zaman serisi verilerinde haftalık, aylık veya yıllık mevsimsellik gibi dönemsel düzenler bulur.

![](media/service-insight-types/pbi_auto_insight_types_seasonality_new.png)

## <a name="steady-share"></a>Düzenli paylaşım
Üst öğenin toplam değeri ile bir alt değerin payı arasında sürekli bir değişkene göre değerlendirilen bir üst-alt bağıntısının gözlemlendiği durumları vurgular.

![](media/service-insight-types/pbi_auto_insight_types_steadyshare.png)

## <a name="time-series-outliers"></a>Zaman serisi aykırı değerleri
Bir zaman serisindeki verilerde yer alan belirli tarihlerin veya saatlerin, diğer tarih/saat değerlerinden büyük ölçüde farklılık gösteren değerler içerdiği durumları algılar.

![](media/service-insight-types/pbi_auto_insight_types_time_series_outliers.png)

## <a name="next-steps"></a>Sonraki adımlar
[Power BI Hızlı Öngörüler](service-insights.md)

Bir veri kümesine sahipseniz [bu veri kümesini Hızlı Öngörüler için en iyi duruma getirebilirsiniz](service-insights-optimize.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

