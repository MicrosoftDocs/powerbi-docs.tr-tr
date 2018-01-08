---
title: "Power BI tarafından desteklenen Öngörü türleri"
description: "Power BI ile Hızlı Öngörüler Öngörüleri görüntüleme."
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
ms.date: 12/20/2017
ms.author: mihart
ms.openlocfilehash: 53e5e67da9bacd9fc9dcbb770747823647aa3a3c
ms.sourcegitcommit: 6ea8291cbfcb7847a8d7bc4e2b6abce7eddcd0ea
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="types-of-insights-supported-by-power-bi"></a>Power BI tarafından desteklenen öngörü türleri
## <a name="how-does-insights-work"></a>Öngörüler nasıl çalışır?
Power BI ilgi çekici olabilecek öngörüleri keşfetmek için bir karmaşık algoritma kümesi uygulayarak veri kümenizin farklı alt kümelerinde hızlıca arama yapar. Power BI, ayrılan bir sürede bir veri kümesinin mümkün olduğu kadar büyük bir kısmını tarar.

Bir veri kümesi veya pano kutucuğunda öngörü çalıştırabilirsiniz.   

## <a name="what-types-of-insights-can-we-find"></a>Hangi öngörü türlerini bulabiliriz?
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
[Power BI öngörüleri](service-insights.md)

Bir veri kümesine sahipseniz [bu veri kümesini öngörüler için en iyi duruma getirebilirsiniz](service-insights-optimize.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

