---
title: Power BI tarafından desteklenen Öngörü türleri
description: Power BI ile Hızlı Öngörüler Öngörüleri görüntüleme.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2018
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: eabe72a2aa44c87bed4ebc3f4c9ac65678dd4774
ms.sourcegitcommit: cd85d88fba0d9cc3c7a4dc03d2f35d2bd096759b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/12/2018
ms.locfileid: "53280248"
---
# <a name="types-of-insights-supported-by-power-bi"></a>Power BI tarafından desteklenen öngörü türleri
## <a name="how-does-insights-work"></a>Öngörüler nasıl çalışır?
Power BI ilgi çekici olabilecek öngörüleri keşfetmek için bir karmaşık algoritma kümesi uygulayarak veri kümenizin farklı alt kümelerinde hızlıca arama yapar. Power BI, ayrılan bir sürede bir veri kümesinin mümkün olduğu kadar büyük bir kısmını tarar.

Bir veri kümesi veya pano kutucuğunda öngörü çalıştırabilirsiniz.   

## <a name="what-types-of-insights-can-we-find"></a>Hangi öngörü türlerini bulabiliriz?
Kullandığımız bazı algoritmalar şunlardır:

## <a name="category-outliers-topbottom"></a>Kategori aykırı değerleri (üst/alt)
Modeldeki bir ölçü için bir boyutun bir veya iki üyesinin, boyutun diğer üyelerinden daha büyük değerlere sahip olduğu durumları vurgular.  

![Kategori aykırı değerleri örneği](./media/end-user-insight-types/pbi_auto_insight_types_category_outliers.png)

## <a name="change-points-in-a-time-series"></a>Zaman serilerindeki değişim noktaları
Verilere ilişkin bir zaman serisindeki eğilimlerde görülen önemli değişiklikleri vurgular.

![Zaman serilerindeki değişim noktaları örneği](./media/end-user-insight-types/pbi_auto_insight_types_changepoint.png)

## <a name="correlation"></a>Bağıntı
Veri kümesindeki bir boyuta göre değerlendirilen birden fazla ölçü arasında bağıntı görülen durumları algılar.

![Bağıntı örneği](./media/end-user-insight-types/pbi_auto_insight_types_correlation.png)

## <a name="low-variance"></a>Düşük Varyans
Veri noktalarının ortalamaya yakın olduğu durumları algılar.

![Düşük Varyans örneği](./media/end-user-insight-types/power-bi-low-variance.png)

## <a name="majority-major-factors"></a>Çoğunluk (Ana etkenler)
Bir toplam değerin çoğunluğunun, başka bir boyuta göre değerlendirildiğinde tek bir etkenle ilişkilendirilebildiği durumları bulur.  

![Ana etkenler örneği](./media/end-user-insight-types/pbi_auto_insight_types_majority.png)

## <a name="overall-trends-in-time-series"></a>Zaman serisindeki genel eğilimler
Zaman serisi verilerinde görülen yukarı veya aşağı yönlü eğilimleri algılar.

![Zaman serisindeki genel eğilimler örneği](./media/end-user-insight-types/pbi_auto_insight_types_trend.png)

## <a name="seasonality-in-time-series"></a>Zaman serisinde mevsimsellik
Zaman serisi verilerinde haftalık, aylık veya yıllık mevsimsellik gibi dönemsel düzenler bulur.

![Mevsimsellik örneği](./media/end-user-insight-types/pbi_auto_insight_types_seasonality_new.png)

## <a name="steady-share"></a>Düzenli paylaşım
Üst öğenin toplam değeri ile bir alt değerin payı arasında sürekli bir değişkene göre değerlendirilen bir üst-alt bağıntısının gözlemlendiği durumları vurgular.

![Düzenli paylaşım örneği](./media/end-user-insight-types/pbi_auto_insight_types_steadyshare.png)

## <a name="time-series-outliers"></a>Zaman serisi aykırı değerleri
Bir zaman serisindeki verilerde yer alan belirli tarihlerin veya saatlerin, diğer tarih/saat değerlerinden büyük ölçüde farklılık gösteren değerler içerdiği durumları algılar.

![Zaman serisi aykırı değerleri örneği](./media/end-user-insight-types/pbi_auto_insight_types_time_series_outliers.png)

## <a name="next-steps"></a>Sonraki adımlar
[Power BI öngörüleri](end-user-insights.md)

Bir veri kümesine sahipseniz [bu veri kümesini öngörüler için en iyi duruma getirebilirsiniz](../service-insights-optimize.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

