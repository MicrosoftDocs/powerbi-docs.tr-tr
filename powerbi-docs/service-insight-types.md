---
title: Power BI tarafından desteklenen Öngörü türleri
description: Power BI ile Hızlı Öngörüler Öngörüleri görüntüleme.
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 03/02/2018
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: 44b59019f1955258716e23fb2dd55182134cc6a2
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34250618"
---
# <a name="types-of-insights-supported-by-power-bi"></a>Power BI tarafından desteklenen öngörü türleri
## <a name="how-does-insights-work"></a>Öngörüler nasıl çalışır?
Power BI ilgi çekici olabilecek öngörüleri keşfetmek için bir karmaşık algoritma kümesi uygulayarak veri kümenizin farklı alt kümelerinde hızlıca arama yapar. Power BI, ayrılan bir sürede bir veri kümesinin mümkün olduğu kadar büyük bir kısmını tarar.

Bir veri kümesi veya pano kutucuğunda öngörü çalıştırabilirsiniz.   

## <a name="what-types-of-insights-can-we-find"></a>Hangi öngörü türlerini bulabiliriz?
Kullandığımız bazı algoritmalar şunlardır:

## <a name="category-outliers-topbottom"></a>Kategori aykırı değerleri (üst/alt)
Modeldeki bir ölçü için bir boyutun bir veya iki üyesinin, boyutun diğer üyelerinden daha büyük değerlere sahip olduğu durumları vurgular.  

![Kategori aykırı değerleri örneği](media/service-insight-types/pbi_auto_insight_types_category_outliers.png)

## <a name="change-points-in-a-time-series"></a>Zaman serilerindeki değişim noktaları
Verilere ilişkin bir zaman serisindeki eğilimlerde görülen önemli değişiklikleri vurgular.

![Zaman serilerindeki değişim noktaları örneği](media/service-insight-types/pbi_auto_insight_types_changepoint.png)

## <a name="correlation"></a>Bağıntı
Veri kümesindeki bir boyuta göre değerlendirilen birden fazla ölçü arasında bağıntı görülen durumları algılar.

![Bağıntı örneği](media/service-insight-types/pbi_auto_insight_types_correlation.png)

## <a name="low-variance"></a>Düşük Varyans
Veri noktalarının ortalamaya yakın olduğu durumları algılar.

![Düşük Varyans örneği](media/service-insight-types/power-bi-low-variance.png)

## <a name="majority-major-factors"></a>Çoğunluk (Ana etkenler)
Bir toplam değerin çoğunluğunun, başka bir boyuta göre değerlendirildiğinde tek bir etkenle ilişkilendirilebildiği durumları bulur.  

![Ana etkenler örneği](media/service-insight-types/pbi_auto_insight_types_majority.png)

## <a name="overall-trends-in-time-series"></a>Zaman serisindeki genel eğilimler
Zaman serisi verilerinde görülen yukarı veya aşağı yönlü eğilimleri algılar.

![Zaman serisindeki genel eğilimler örneği](media/service-insight-types/pbi_auto_insight_types_trend.png)

## <a name="seasonality-in-time-series"></a>Zaman serisinde mevsimsellik
Zaman serisi verilerinde haftalık, aylık veya yıllık mevsimsellik gibi dönemsel düzenler bulur.

![Mevsimsellik örneği](media/service-insight-types/pbi_auto_insight_types_seasonality_new.png)

## <a name="steady-share"></a>Düzenli paylaşım
Üst öğenin toplam değeri ile bir alt değerin payı arasında sürekli bir değişkene göre değerlendirilen bir üst-alt bağıntısının gözlemlendiği durumları vurgular.

![Düzenli paylaşım örneği](media/service-insight-types/pbi_auto_insight_types_steadyshare.png)

## <a name="time-series-outliers"></a>Zaman serisi aykırı değerleri
Bir zaman serisindeki verilerde yer alan belirli tarihlerin veya saatlerin, diğer tarih/saat değerlerinden büyük ölçüde farklılık gösteren değerler içerdiği durumları algılar.

![Zaman serisi aykırı değerleri örneği](media/service-insight-types/pbi_auto_insight_types_time_series_outliers.png)

## <a name="next-steps"></a>Sonraki adımlar
[Power BI öngörüleri](service-insights.md)

Bir veri kümesine sahipseniz [bu veri kümesini öngörüler için en iyi duruma getirebilirsiniz](service-insights-optimize.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

