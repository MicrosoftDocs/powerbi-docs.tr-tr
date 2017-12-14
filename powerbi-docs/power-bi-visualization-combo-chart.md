---
title: "Power BI'daki Birleşik Harita (Eğitim)"
description: "Bu belge, Power BI'da Birleşik Haritaları neden ve nasıl oluşturacağınızın açıklandığı videolu bir eğitimdir."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: lnv66cTZ5ho
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/27/2017
ms.author: mihart
ms.openlocfilehash: c00ba74501a411743036c4514750bccbbae3eb00
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2017
---
# <a name="combo-chart-in-power--tutorial"></a>Power BI'daki Birleşik Harita (Eğitim)
Power BI'daki birleşik harita, çizgi grafik ile sütun grafiği içeren tek bir görselleştirmedir. Bu 2 grafiği tek bir görselleştirmede birleştirdiğinizde verileri daha hızlı şekilde karşılaştırabilirsiniz.

Birleşik haritalarda bir veya daha fazla Y ekseni bulunabilir.

## <a name="when-to-use-a-combo-chart"></a>Birleşik Haritaları ne zaman kullanırsınız?
Birleşik haritalar aşağıdaki durumlarda harika bir seçimdir:

* aynı X eksenine sahip bir çizgi grafiğiniz ve sütun grafiğiniz olduğunda.
* farklı değer aralıklarına sahip birden fazla ölçüyü karşılaştırmak istediğinizde.
* iki ölçü arasındaki bağıntıyı tek bir görselleştirmede sunmak istediğinizde.
* bir ölçünün, başka bir ölçü tarafından tanımlanan hedefi karşılayıp karşılamadığını kontrol etmek istediğinizde.
* tuval alanını tasarruflu bir şekilde kullanmak istediğinizde.

## <a name="create-a-basic-single-axis-combo-chart"></a>Basit, tek eksenli bir Birleşik Harita oluşturma
Aşağıdaki videoda Will, Satış ve Pazarlama örneğini kullanarak bir birleşik harita oluşturmaktadır.

<iframe width="560" height="315" src="https://www.youtube.com/embed/lnv66cTZ5ho?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>


Kendi birleşik haritanızı oluşturmak için Power BI'da oturum açın ve **Veril Al \> Örnekler \> Perakende Analiz Örneği**'ni seçin. 

1. "Retail Analysis Sample" panosunda **Total Stores** kutucuğunu seçerek "Retail Analysis Sample" raporunu açın.
2. **Raporu düzenle**'yi seçerek raporu Düzenleme Görünümü'nde açın.
3. [Yeni bir rapor sayfası ekleyin](power-bi-report-add-page.md).
4. Bu yılın satış verilerini ve aya göre brüt kârı görüntüleyen bir sütun grafiği oluşturun.
   
    a.  Alanlar bölmesinde **Sales** \> **This Year Sales** > **Değer** seçeneğini belirleyin.
   
    b.  **Sales** \> **Gross Margin This Year** alanını **Değer** kutusuna sürükleyin.
   
    c.  **Eksen** kutusuna eklemek üzere **Time** \> **FiscalMonth** alanını seçin. 
   
    ![](media/power-bi-visualization-combo-chart/combotutorial1new.png)
5. Görselleştirmenin sağ üst köşesindeki üç nokta (...) simgesini seçin ve **Sıralama Ölçütü: FiscalMonth** seçeneğini belirleyin.
6. Sütun grafiğini bir birleşik haritaya dönüştürün. Sütun grafiği seçiliyken **Görsel Öğeler** bölmesinde **Çizgi ve kümelenmiş sütun grafiği**'ni seçin.
   
    ![](media/power-bi-visualization-combo-chart/converttocombo_new2.png)
7. **Alanlar** bölmesinden **Sales** \> **Last Year Sales** alanını **Çizgi Değerleri** demetine sürükleyin.
   
   ![](media/power-bi-visualization-combo-chart/linevaluebucket.png)
   
   Birleşik haritanız aşağıdaki gibi görünmelidir:
   
   ![](media/power-bi-visualization-combo-chart/combochartdone-new.png)

## <a name="create-a-combo-chart-with-two-axes"></a>İki eksenli birleşik harita oluşturma
Bu görevde brüt kâr ile satış verilerini karşılaştıracağız.

1. Geçen yılın brüt kâr yüzdesini aylara göre gösteren yeni bir çizgi grafik oluşturun.  Ocak ayında brüt kâr %35'lerdeyken Nisan'da %45 ile zirveye ulaşıyor, Temmuz'da düşüyor ve Ağustos'ta tekrar zirveye ulaşıyor. Geçen yıla ve bu yıla ait satış verilerini karşılaştırdığımızda benzer bir desen ile karşılaşacak mıyız?
   
   ![](media/power-bi-visualization-combo-chart/combo1_new.png)
2. **This Year Sales > Değer** ve **Last Year Sales** alanlarını çizgi grafiğe ekleyin. Geçen yıla ait brüt kâr yüzdesini gösteren **Gross Margin Last Year %** alanının ölçeği, satış verilerini gösteren **Sales** alanının ölçeğinden çok daha küçük olduğundan karşılaştırma işlemi zorlaşır.      
   
   ![](media/power-bi-visualization-combo-chart/flatline_new.png)
3. Görselin okunmasını ve yorumlanmasını daha kolay hale getirmek için çizgi grafiği Çizgi ve Yığılmış Sütun grafiğine dönüştürün.
   
   ![](media/power-bi-visualization-combo-chart/converttocombo_new.png)
4. **Gross Margin Last Year %** alanını **Sütun Değerleri** demetinden alıp **Çizgi Değerleri** demetine sürükleyin. Power BI iki eksen oluşturarak veri kümelerinin farklı şekilde ölçeklenmesini sağlar; sol eksende dolar cinsinden para değeri gösterilirken sağ eksende yüzde ölçülür.
   
   ![](media/power-bi-visualization-combo-chart/power-bi-combochart.png)    

## <a name="add-titles-to-the-axes"></a>Eksenlere başlık ekleme
1. Boya rulosu simgesini ![](media/power-bi-visualization-combo-chart/power-bi-paintroller.png) seçin ve Biçimlendirme bölmesini açın.
2. **Y Ekseni** seçeneklerini genişletmek için aşağı oku seçin.
3. **Y Ekseni (Sütun)** için **Konum**'u **Sol**, **Başlık**'ı **Açık**, **Stil**'i **Yalnızca başlığı göster** ve **Birimleri görüntüle**'yi **Milyon** olarak ayarlayın.
   
   ![](media/power-bi-visualization-combo-chart/power-bi-y-axis-column.png)
4. **Y Ekseni (Sütun)** bölümünde **Sonrakini göster**'in **Açık** olarak ayarlandığından emin olun. Bu ayar, birleşik haritanın çizgi grafik bölümünü biçimlendirmeye ilişkin seçenekleri görüntüler.
   
   ![](media/power-bi-visualization-combo-chart/power-bi-show-secondary.png)
5. **Y Ekseni (Satır)** için **Konum**'u **Sağ**, **Başlık**'ı **Açık**, **Stil**'i ise **Yalnızca başlığı göster** olarak ayarlayın.
   
   Artık birleşik haritanız başlıkları olan iki eksen görüntüler.
   
   ![](media/power-bi-visualization-combo-chart/power-bi-titles-on.png)

Bu noktada aşağıdakileri yapmak isteyebilirsiniz:

* [Birleşik haritayı pano kutucuğu olarak ekleme](service-dashboard-tiles.md).
* [Raporu kaydetme](service-report-save.md).

## <a name="highlighting-and-cross-filtering"></a>Vurgulama ve çapraz filtreleme
Filtreler bölmesini kullanma hakkında bilgi için bkz. [Bir rapora filtre ekleme](power-bi-report-add-filter.md).

Bir birleşik haritada sütunların veya satırların vurgulanması, rapor sayfasındaki diğer görselleştirmelerde çapraz filtre uygular ve bu, tam tersi için de geçerlidir.

## <a name="next-steps"></a>Sonraki adımlar
[Bir rapora görselleştirme ekleme](power-bi-report-add-visualizations-i.md)

[Power BI raporlarındaki görselleştirmeler](power-bi-report-visualizations.md)

[Power BI'daki görselleştirme türleri](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Power BI - Temel Kavramlar](service-basic-concepts.md)

[Ücretsiz deneyin!](https://powerbi.com/)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

