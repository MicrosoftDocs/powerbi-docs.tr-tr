---
title: Popüler stokları Power BI analiz edin
description: Popüler stokları Power BI analiz edin
author: paulinbar
ms.author: painbar
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: how-to
ms.date: 02/09/2021
LocalizationGroup: Connect to services
ms.openlocfilehash: 934451c06927237fd252d60102e2e5db73e31bc1
ms.sourcegitcommit: de3b45cad5ae21c77692ce4490e21de01d21e6f3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/10/2021
ms.locfileid: "100082894"
---
# <a name="analyze-popular-stocks-with-power-bi"></a>Popüler stokları Power BI analiz edin

Hisse senedi Market uygulaması, Power BI analiz yolculuğuna başlamak için size birden çok KPI gösterir. Bu uygulamayı, popüler hisse senetleri ve ETFs için haftalık, aylık veya yıllık eğilimleri de izlemek üzere kullanabilirsiniz. Uygulama, hisse senedi, sektör odaklı dağıtım, cıvata bantların ve hatta zaman içinde popüler hisse senetleri için performans karşılaştırmaları izlemeyle birlikte Power BI işlem halinde gösterir.

Uygulamanın dört Pano özellikleri:
* **ETF panosu**: dört ana dizin için kapatma eğilimlerini gösterir. 
* **Hisse senetleri ve ETFs karşılaştırması**: normalleştirilmiş grafikler, stokları ve efleri karşılaştırmanızı kolaylaştırır.
* **Hisse senedi performans analizi**: eğilimler, hacim, Erkek LC ve baba bantlarını kapatmak için görsellerle seçili hisse senedi analizlerinin ayrıntılı analizini sağlar.
* **Sektör odaklı dağıtım**: stok performansını kesime göre kesmeniz için izin verir.

Gezinti tarafı bölmesini veya sayfanın sağ üst köşesindeki ileri ve geri oklarını kullanarak panolar arasında gezinebilirsiniz.

![Hisse senedi uygulamasının ekran görüntüsü.](media/service-connect-to-analyze-stocks/stocks-app.png)

## <a name="etf-dashboard"></a>ETF panosu

ETF panosu, dört ana dizinin kapanış eğilimlerini gösteren görsellere sahiptir. 
* **NASDAQ**: NASDAQ Bileşik DIZIN, NASDAQ exchange üzerinde 3.000 ' den fazla hisse senedi içindeki değişikliği ölçer.
* **S&p 500**: s&p 500, büyük harfli ABD eşlerini en iyi şekilde ölçer olarak kabul edilir.
* **Aşağı Uludağ**: aşağı Jones, BT sektörünün Microsoft gibi liderlerinin Pazar artışını gösterir. Aşağı, bu dizin altındaki hisse senetleri, günün sonuna kadar kapandığı konusunda aşağı
* **Russat2000**: russel 2000, karşılıklı fon için en yaygın kıyaslamaya yöneliktir. Russata 2000 kapanış eğilimi görseli, 2000 ' ten fazla düşük aralıklı hisse senedi hakkında yatırım kılavuzu sağlamak için kullanılabilir.

Panonun en üstünde çalışan bir başlık, sayfada gösterilen dört dizin için geçerli günün kapanışını ve önceki günlerin fiyat değişikliğini gösterir.

Varsayılan görünüm-grafik görünümü-eğilimin zaman içinde ne kadar önemli değiştiğini anlamanıza yardımcı olur. Bir hafta, ay veya yıl için eğilimi görmeyi seçmek üzere panonun sol üst kısmındaki zaman ölçeği düğmelerini kullanabilirsiniz. Belirli bir günün tam veri noktasını almak için işaretçiyi grafiğin üzerine getirin.

![ETF Dashboard Graph görünümünün ekran görüntüsü.](media/service-connect-to-analyze-stocks/etf-dashboard-graph.png)  

X ekseninde, saat dönemini ve y ekseninde bir kapanış değeri görürsünüz.

Panonun sağ üst köşesindeki geçiş anahtarına tıklayarak bir Candlestick grafiğine geçiş yapabilirsiniz. Candlestick görünümünde her bir veri noktası için açık, yüksek, düşük ve kapalı fiyatlarını görebilirsiniz. Belirli bir günün tam veri noktasını almak için işaretçiyi grafiğin üzerine getirin.

![ETF Dashboard Candlestick görünümünün ekran görüntüsü.](media/service-connect-to-analyze-stocks/etf-dashboard-candlestick.png)

## <a name="stocks-and-etfs-comparison"></a>Hisse senetleri ve ETFs karşılaştırması

Hisse senetleri ve ETFs karşılaştırma panosu, seçili hisse senetleri ve ETFs 'yi karşılaştırmayı kolaylaştıran iki normalleştirilmiş grafik gösterir.

![Stok karşılaştırma panosu seçim düğmesi ekran görüntüsü.](media/service-connect-to-analyze-stocks/stocks-comparison-dashboard.png)

Bu sayfayı kullanmak için öncelikle karşılaştırmak istediğiniz stokları seçin. 
1. Stok karşılaştırma panosunun **seçme seçimlerini Seç** düğme  ![ ekran görüntüsüne tıklayın.](media/service-connect-to-analyze-stocks/stocks-comparison-dashboard-select.png)
1. Görüntülenen **hisse senedi Seç** sayfasında, önceki seçimleri kaldırmak için **Temizle** ' ye tıklayın ve ardından  ![ Stok karşılaştırma panosunun görüntüsünü karşılaştırmak istediğiniz stokları seçin.](media/service-connect-to-analyze-stocks/stocks-comparison-dashboard-select-clear.png)
1. **Uygula**'ya tıklayın.

İlgilendiğiniz stokları seçtikten sonra, karşılaştırmak istediğiniz belirli bir stokları seçmek için aşağı açılan oku kullanın.

![Stok karşılaştırma panosunun ekran görüntüsü açılan menü.](media/service-connect-to-analyze-stocks/stocks-comparison-dashboard-select-dropdown.png)

## <a name="stock-performance-analysis"></a>Hisse senedi performans analizi

 Hisse senedi performans analizi panosu, önceki günün kapatma, kapatma, açma, yüksek ve düşük gibi seçili hisse senedi hakkında önemli KPI 'ler gösterir. Analiz için seçtiğiniz hisse senetleri arasından görmek istediğiniz stoku seçmek için açılan listeyi seçin. Seçtiğiniz stoğa tıklandıktan sonra değerin değişme olduğunu görürsünüz.

![Hisse senedi performans analizi seçme ekran görüntüsü.](media/service-connect-to-analyze-stocks/stocks-performance-select.png)
 
### <a name="closing-trend"></a>Kapanış eğilimi

Seçili hisse senedi için kapatma eğilimi görebilir ve sayfanın sol üst kısmındaki düğmelere tıklayarak bunu ay görünümü veya yıl görünümüne geçirebilirsiniz. Yılda bir görünüm olması, söz konusu stokun hangi bölümünde elde edilen veya kayıp değer görbaşlamanıza yardımcı olur.

![Seçili hisse senetleri için kapanış eğilimlerini ekran görüntüsü](media/service-connect-to-analyze-stocks/stocks-performance-closing-trend.png)  

### <a name="volume"></a>Birim

Bir sonraki görsele doğru kaydırarak seçili hisse senedi hacmine göz atabilirsiniz. Yılın söz konusu bölümünde stok hacmini görmek için bir zaman aralığı üzerine gelebilmeniz gerekir.

![Seçili hisse senedi hacminin ekran görüntüsü](media/service-connect-to-analyze-stocks/stocks-performance-volume.png)
 
### <a name="ohlc-chart"></a>DIRENLC grafiği

Tek seferde belirli bir hisse senedi için dört ana veri noktası gösterdiklerinden, der LC grafikleri oldukça yararlı olur. Bu nedenle, sayfada bir sonraki görselde, seçili stokun açık, kapanış, yüksek ve düşük olduğunu gösteren DIRENLC görselini görürsünüz. Ayrıca, hareketli ortalamayı değiştirerek verilerin daha ayrıntılı görünmesini sağlayabilirsiniz. 

![DIRENÜ LC ekran görüntüsü](media/service-connect-to-analyze-stocks/stocks-performance-ohlc.png)

### <a name="bollinger-band"></a>Kalın bant

Kalın şeritler, eğilimleri göstermek için karmaşık matematik kullanır. IBU ve diğer üç satırı görebileceğiniz bir dizi KPI 'nin sayısını görebilirsiniz. Orta satırda hareketli ortalama gösterilmektedir. En üstteki çizgi belirli sayıda standart sapma tarafından, alt çizgi ise standart bir sapmayla aşağı doğru kaydırmasıdır.

![Baba bandı ekran görüntüsü.](media/service-connect-to-analyze-stocks/stocks-performance-bollinger.png) 

## <a name="sectorwise-distribution"></a>Sectorwise dağıtımı

Sektör odaklı dağıtım sayfasında, çeşitli hisse senetleri ve bunların ait olduğu pazarı görürsünüz. Kesimlerden birine tıkladığınızda, hisse senetleri filtrelenmiş olur ve seçilen kesime ait olan hisse senetleri görünmeye başlar. 

![Sektör temelli dağıtımın ekran görüntüsü.](media/service-connect-to-analyze-stocks/sector-wise-distribution.png)
 
Daha sonra, önceki kapatma, kapatma ve fark gibi önemli KPI 'ları görmek için stokun üzerine gelebilmeniz gerekir. Bu fark, stokun dün ne kadar kazanıldığını veya kaybediltiğini anlamanıza yardımcı olur.

![Sektör odaklı dağıtım ayrıntısı ekran görüntüsü.](media/service-connect-to-analyze-stocks/sector-wise-distribution-detail.png)

Bu kategorideki tüm stokları görmek için aşağı kaydırma yapabilirsiniz.
 
Farklı sektörlerde pazar dağılımını görmek için, en üstten aşağı doğru olan kesimlerin, son güne ait kapanış fiyatlarıyla en yüksek farka sahip olduğunu gösteren "sektör temelinde dağıtım" Görseliniz vardır.

![Farklı kesimlerin Pazar dağılımı ekran görüntüsü](media/service-connect-to-analyze-stocks/stocks-comparison-based-on-sector.png)


## <a name="next-steps"></a>Sonraki adımlar

* [Power BI şablon uygulamaları nelerdir?](service-template-apps-overview.md)
* [Power BI’da şablon uygulaması oluşturma](service-template-apps-create.md)
* [Kuruluşunuzda şablon uygulamalarını yükleme ve dağıtma](service-template-apps-install-distribute.md)
* Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
