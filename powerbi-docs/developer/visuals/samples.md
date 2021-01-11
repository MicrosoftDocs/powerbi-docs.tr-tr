---
title: Daha iyi tümleşik BI içgörüleri için, Power BI tümleşik analizlerinde Power BI görsel örnekleri
description: Bu makalede dilimleyiciler, 20’den fazla grafik türü, WebGL ve R görselleri ile betikleri içeren örnek Power BI görselleri sunulur. Power BI tümleşik analiz kullanarak daha iyi tümleşik BI içgörüleri elde edin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 03/17/2019
ms.openlocfilehash: 3da805a10a8b43dc7b1f1750583a79494557d519
ms.sourcegitcommit: eeaf607e7c1d89ef7312421731e1729ddce5a5cc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2021
ms.locfileid: "97888501"
---
# <a name="samples-of-power-bi-visuals"></a>Örnek Power BI görselleri

Bu Power BI görsellerini GitHub’dan indirebilir, kullanabilir ve değiştirebilirsiniz. Bu örnekler, Power BI ile geliştirme yaparken oluşan yaygın durumların nasıl ele alınacağını gösterir.

## <a name="slicers"></a>Dilimleyiciler

Dilimleyici, rapordaki diğer görselleştirmelerde gösterilen veri bölümünü daraltır. Dilimleyiciler, Power BI’da verileri filtrelemenin pek çok yolundan biridir.

| <img src="media/samples/chiclet-slicer.png" alt="Screenshot shows Chiclet Slicer." width="200">  | <img src="media/samples/timeline-slicer.png" alt="Screenshot shows Timeline slicer." width="200"> | <img src="media/samples/sample-slicer.png" alt="Screenshot shows Slicer sample." width="200">|
| ------------- | ------------- | -------------|
| [Chiclet Slicer](https://github.com/Microsoft/powerbi-visuals-chicletslicer/)  </br>Diğer görsellerde kanvas içi bir filtre olarak davranan görüntü veya metin düğmelerini gösterin | [Timeline slicer](https://github.com/Microsoft/powerbi-visuals-timeline/) </br>Tarihe göre filtreleyen grafiksel tarih aralığı seçicisi | [Dilimleyici örneği](https://github.com/Microsoft/powerbi-visuals-sampleslicer/) </br>Gelişmiş Filtreleme API’sinin kullanımını gösterir

## <a name="charts"></a>Grafikler

Çubuk grafikler, pasta grafikleri Word Cloud ve diğerlerini içeren galerimizden ilham alın.

| <img src="media/samples/aster-plot.png" alt="Screenshot shows Aster Plot." width="200">  | <img src="media/samples/bullet-chart.png" alt="Screenshot shows Bullet chart." width="200"> | <img src="media/samples/Chord.png" alt="Screenshot shows Chord." width="200">|
| ------------- | ------------- | -------------|
| [Aster Plot](https://github.com/Microsoft/powerbi-visuals-asterplot/)  </br>Standart halka grafiğinin, tarama açısını yönlendirmek için ikinci bir değer kullanılarak elde edilen farklı bir yorumu | [Madde işareti grafiği](https://github.com/Microsoft/powerbi-visuals-bulletchart/) </br>Hedefleri izlemeye yönelik bağlam sağlamak için fazladan görsel öğeleri olan çubuk grafiği | [Chord](https://github.com/Microsoft/powerbi-visuals-chord/) </br>Bir matristeki verilerin arasındaki ilişkileri görüntüleyen bir grafiksel yöntem
| <img src="media/samples/dot-plot.png" alt="Screenshot shows Dot plot." width="200"> | <img src="media/samples/dual-kpi.png" alt="Screenshot shows Dual K P I." width="200">| <img src="media/samples/enhanced-scatter.png" alt="Screenshot shows Enhanced Scatter." width="200"> 
| [Noktalı çizim](https://github.com/Microsoft/powerbi-visuals-dotplot/) </br>Sıklık dağıtımını harika bir görselle gösterir | [Dual KPI](https://github.com/Microsoft/powerbi-visuals-dualkpi/) </br>Eğilimlerini birleşik bir zaman çizgisi üzerinde göstererek iki ölçüyü zaman ekseninde verimli bir şekilde görselleştirir | [Gelişmiş Dağılım](https://github.com/Microsoft/powerbi-visuals-enhancedscatter/) </br>Mevcut dağılım grafiğindeki iyileştirmeler
| <img src="media/samples/forcegraph.png" alt="Screenshot shows Force Graph." width="200">| <img src="media/samples/gantt.png" alt="Screenshot shows Gantt." width="200">| <img src="media/samples/table-heatmap.png" alt="Screenshot shows Table Heatmap." width="200">
| [Kuvvet Grafı](https://github.com/Microsoft/powerbi-visuals-forcegraph/) </br>Varlıklar arasındaki bağlantıları göstermek için yararlı olan, eğimli bir yola sahip kuvvet düzeni şeması | [Gantt](https://github.com/Microsoft/powerbi-visuals-gantt/) </br>Proje zaman çizelgesini veya kaynaklarla yapılan zamanlamayı gösteren bir çubuk grafiği | [Table Heatmap](https://github.com/Microsoft/powerbi-visuals-heatmap/) </br>Tabloda renkler kullanarak verileri kolayca ve sezgisel bir şekilde karşılaştırın
| <img src="media/samples/histogram-chart.png" alt="Screenshot shows Histogram chart." width="200"> | <img src="media/samples/linedot-chart.png" alt="Screenshot shows LineDot chart." width="200"> | <img src="media/samples/mekko-chart.png" alt="Screenshot shows Mekko chart." width="200"> 
| [Histogram grafiği](https://github.com/Microsoft/powerbi-visuals-histogram/) </br>Verilerin sürekli bir aralık veya belirli bir zaman dilimi içindeki dağıtımını görselleştirir | [LineDot grafiği](https://github.com/Microsoft/powerbi-visuals-linedotchart/) </br>Hedef kitlenin verilere ilgisini çeken, animasyonlu noktaları olan animasyonlu çizgi grafiği | [Mekko chart](https://github.com/Microsoft/powerbi-visuals-mekkochart/) </br>Yüzde 100 yığılmış sütun grafiği ile yüzde 100 yığılmış çubuk grafiğinin bir karışımı tek bir görünümde birleştirilir
| <img src="media/samples/multikpi.png"alt="Çoklu KPI'yi gösteren ekran görüntüsü." width="200"> | <img src="media/samples/powerkpi.png"alt="Power KPI'yi gösteren ekran görüntüsü." width="200"> | <img src="media/samples/powerkpi-matrix.png"alt="Power KPI Matrisi'ni gösteren ekran görüntüsü." width="200"> 
| [Çoklu KPI](https://github.com/microsoft/PowerBI-visuals-MultiKPI/) </br> Birden çok mini grafik içeren destekleyici verilere sahip bir anahtar KPI içeren güçlü bir Çok KPI’lı görselleştirme | [Power KPI](https://github.com/microsoft/PowerBI-visuals-PowerKPI/) </br>Geçerli veriler, değer ve varyanslar için çok satırlı grafik ve etiketler ile güçlü bir KPI Göstergesi | [Power KPI Matrix](https://github.com/microsoft/PowerBI-visuals-PowerKPIMatrix/) </br>Dengeli karneleri ve sınırsız sayıdaki ölçümler ile KPI’ları kısa, kolay okunabilir bir listede izleyin
| <img src="media/samples/pulse-chart.png" alt="Screenshot shows Pulse chart." width="200">| <img src="media/samples/radar-chart.png" alt="Screenshot shows Radar chart." width="200"> | <img src="media/samples/sankey-chart.png" alt="Screenshot shows Sankey chart." width="200"> 
| [Eğilim grafiği](https://github.com/Microsoft/powerbi-visuals-pulsechart/) </br>Ana olayların açıklamalarını içeren bu çizgi grafiği, hikayelerin verilerle anlatılması için mükemmeldir| [Radar chart](https://github.com/Microsoft/powerbi-visuals-radarchart/) </br>Öznitelikleri karşılaştırmak için yararlı olan, tek bir kategorik eksen üzerinde çizilmiş birden çok ölçüyü gösterir | [Sankey chart](https://github.com/Microsoft/powerbi-visuals-sankey/) </br>Serinin genişliğinin akışın miktarına orantılı olduğu akış şeması
| <img src="media/samples/stream-graph.png" alt="Screenshot shows Stream graph." width="200"> | <img src="media/samples/sunburst.png" alt="Screenshot shows Sunburst chart." width="200">| <img src="media/samples/tornado.png" alt="Screenshot shows Tornado chart." width="200">
| [Akış grafiği](https://github.com/Microsoft/powerbi-visuals-streamgraph/) </br>Sıklıkla zaman içindeki değerleri görüntülemek için kullanılan, düzgün ilişkilendirmeli bir yığılmış alan grafiği | [Güneş ışığı grafiği](https://github.com/Microsoft/powerbi-visuals-sunburst/) </br>Hiyerarşik verileri bir şekilde görselleştirmek için çok düzeyli halka grafiği| [Tornado chart](https://github.com/Microsoft/powerbi-visuals-tornado/) </br>İki grup arasındaki değişkenlerin göreli önemini karşılaştırma
 | <img src="media/samples/word-cloud.png" alt="Screenshot shows Word Cloud." width="200">
 | [Word Cloud](https://github.com/Microsoft/powerbi-visuals-wordcloud/) </br>Verilerinizde sık geçen metinlerden eğlendirici bir görsel oluşturun

## <a name="webgl"></a>WebGL

WebGL, web içeriğinin bir HTML tuvalinde 2B ve 3B işleme yapmak için OpenGL ES 2.0 sürümünü temel alan bir API kullanmasına izin verir.

| <img src="media/samples/globe-map.png" alt="Screenshot shows Globe Map." width="250">|
| ------------- |
| [Dünya Haritası](https://github.com/Microsoft/powerbi-visuals-globemap/) </br>Konumları etkileşimli bir 3B haritaya çizme

## <a name="r-visuals"></a>R görselleri

Bu örnekler, R görsellerinin ve betiklerinin analitik ve görsel gücünden nasıl yararlanılabileceğini gösterir.

| <img src="media/samples/association-rules.png" alt="Screenshot shows Association rules." width="200">| <img src="media/samples/clustering.png" alt="Screenshot shows Clustering." width="200">| <img src="media/samples/clustering-with-outliers.png" alt="Screenshot shows Clustering with outliers." width="200">|
|------------- |------------- |------------- |------------- |
| [İlişkilendirme kuralları](https://github.com/Microsoft/powerbi-visuals-assorules/) </br>If-then deyimlerini kullanarak ilişkili değil gibi görünen veriler arasındaki ilişkileri ortaya çıkarma | [Kümeleme](https://github.com/Microsoft/powerbi-visuals-clustering-kmeans/) </br>K-ortalamalar algoritmasını kullanarak verilerinizdeki benzerlik gruplarını bulma | [Aykırı değerler ile kümeleme](https://github.com/microsoft/PowerBI-visuals-dbscan/) </br>Verilerinizdeki benzerlik gruplarını ve aykırı değerleri bulma
| <img src="media/samples/correlation-plot.png" alt="Screenshot shows Correlation plot." width="200"> | <img src="media/samples/decision-tree-chart.png" alt="Screenshot shows Decision tree chart." width="200"> | <img src="media/samples/forecasting-tbats.png" alt="Screenshot shows Forecasting T B A T S." width="200"> 
| [Bağıntı çizimi](https://github.com/Microsoft/powerbi-visuals-corrplot/) </br>Bir veri tablosundaki en ilişkili değişkenleri vurgulama | [Karar ağacı grafiği](https://github.com/Microsoft/powerbi-visuals-decision-tree/) </br>Özyinelemeli bölümlendirme kullanarak istatistiksel olasılığı belirlemeye yönelik şematik, ağaç şeklindeki diyagram | [TBATS Tahmini](https://github.com/Microsoft/powerbi-visuals-forcasting-tbats/) </br>TBATS modelini kullanarak, birden çok mevsimselliğe sahip serilere yönelik zaman serisi tahmin etme
| <img src="media/samples/forecasting-with-ARIMA.png" alt="Screenshot shows Forecasting with ARIMA." width="200"> | <img src="media/samples/funnel-plot.png" alt="Screenshot shows Funnel plot." width="200"> | <img src="media/samples/outliers-detection.png" alt="Screenshot shows Outliers detection." width="200"> 
| [ARIMA ile Tahmin](https://github.com/Microsoft/powerbi-visuals-forcastingarima/) </br>Autoregressive Integrated Moving Avg (ARIMA) kullanarak tarihsel verilere göre gelecek değerleri tahmin etme | [Huni grafiği](https://github.com/Microsoft/powerbi-visuals-funnel/) </br>Huni grafiği kullanarak verilerinizdeki aykırı değerleri bulma | [Aykırı değerleri algılama](https://github.com/Microsoft/powerbi-visuals-outliers-det/) </br>En uygun yöntemi ve çizimi kullanarak verilerinizdeki aykırı değerleri bulma
| <img src="media/samples/spline-chart.png" alt="Screenshot shows Spline chart." width="200"> | <img src="media/samples/time-series-decomposition-chart.png" alt="Screenshot shows Time Series decomposition chart." width="200"> | <img src="media/samples/time-series-forecasting-chart.png" alt="Screenshot shows Time series forecasting chart." width="200">
| [Eğri grafik](https://github.com/Microsoft/powerbi-visuals-spline/) </br>Gürültülü verileri görselleştirme ve anlama | [Zaman serisi ayrıştırma grafiği](https://github.com/Microsoft/powerbi-visuals-timeseriesdecomposition/) </br>“Loess kullanarak Mevsimsellik ve Eğilim ayrıştırması” kullanarak zaman serisi bileşenlerini anlama | [Zaman serilerini tahmin etme grafiği](https://github.com/Microsoft/powerbi-visuals-forcasting-exp/) </br>Önceden gözlemlenen değerleri temel alarak gelecek değerleri tahmin etmek için üstel düzeltme modeli kullanma

## <a name="next-steps"></a>Sonraki adımlar

Power BI görseli oluşturmayı denemek için bkz. [Power BI daire kartı görseli geliştirme](develop-circle-card.md).
