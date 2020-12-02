---
title: Power BI'da birleşik harita
description: Birleşik haritalar ile ilgili bu eğitimde, birleşik haritaları ne zaman kullanacağınızın yanı sıra Power BI hizmetinde ve Power BI Desktop'ta nasıl oluşturacağınız açıklanmaktadır.
author: mihart
ms.author: mihart
ms.reviewer: mihart
featuredvideoid: lnv66cTZ5ho
ms.service: powerbi
ms.subservice: pbi-visuals
ms.topic: conceptual
ms.date: 06/18/2020
LocalizationGroup: Visualizations
ms.openlocfilehash: f5731f8660fc27e6aef44878f5410819ce0c0eae
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96409942"
---
# <a name="create-and-use-combo-charts-in-power-bi"></a>Power BI'da birleşik haritalar oluşturma ve kullanma

[!INCLUDE[consumer-appliesto-nyyn](../includes/consumer-appliesto-nyyn.md)]

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

Power BI'daki birleşik harita, çizgi grafik ile sütun grafiği içeren tek bir görselleştirmedir. Bu 2 grafiği tek bir görselleştirmede birleştirdiğinizde verileri daha hızlı şekilde karşılaştırabilirsiniz.

Birleşik haritalarda bir veya daha fazla Y ekseni bulunabilir.

## <a name="when-to-use-a-combo-chart"></a>Birleşik haritalar ne zaman kullanılır?
Birleşik haritalar aşağıdaki durumlarda harika bir seçimdir:

* aynı X eksenine sahip bir çizgi grafiğiniz ve sütun grafiğiniz olduğunda.
* farklı değer aralıklarına sahip birden fazla ölçüyü karşılaştırmak istediğinizde.
* iki ölçü arasındaki bağıntıyı tek bir görselleştirmede sunmak istediğinizde.
* bir ölçünün, başka bir ölçü tarafından tanımlanan hedefi karşılayıp karşılamadığını kontrol etmek istediğinizde.
* tuval alanını tasarruflu bir şekilde kullanmak istediğinizde.

> [!NOTE]
> Raporunuzu bir Power BI iş arkadaşınızla paylaşmak için her ikinizin de bireysel Power BI Pro lisanslarınızın olması veya raporun Premium kapasitede depolanması gerekir.

### <a name="prerequisites"></a>Önkoşullar
Bu öğreticide [Perakende Analizi örneği .PBIX dosyası](https://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix) kullanılmıştır.

1. Menü çubuğunun sol üst köşesinden **Dosya** > **Aç**’ı seçin
   
2. **Perakende Analizi örneği PBIX dosyasının** kopyasını bulun

1. **Perakende Analizi örneği PBIX dosyasını** rapor görünümünde ![Rapor görünümü simgesinin ekran görüntüsü.](media/power-bi-visualization-kpi/power-bi-report-view.png) açın.

1. Seç ![Sarı sekmenin ekran görüntüsü.](media/power-bi-visualization-kpi/power-bi-yellow-tab.png) yeni bir sayfa ekleyin.



## <a name="create-a-basic-single-axis-combo-chart"></a>Basit, tek eksenli bir Birleşik Harita oluşturma
Aşağıdaki videoda Will, Satış ve Pazarlama örneğini kullanarak bir birleşik harita oluşturmaktadır.
   > [!NOTE]
   > Bu videoda Power BI Desktop’ın eski bir sürümü kullanılmaktadır.
   > 
   > 
<iframe width="560" height="315" src="https://www.youtube.com/embed/lnv66cTZ5ho?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>  

<a name="create"></a>

1. Boş bir rapor sayfasında başlayın ve bu yılın satış verilerini ve aya göre brüt kârı görüntüleyen bir sütun grafiği oluşturun.

    a.  Alanlar bölmesinde **Sales** \> **This Year Sales** > **Değer** seçeneğini belirleyin.

    b.  **Sales** \> **Gross Margin This Year** alanını **Değer** kutusuna sürükleyin.

    c. **Eksen** kutusuna eklemek üzere **Time** \> **FiscalMonth** alanını seçin.

    ![birleşik öğretici örneği](media/power-bi-visualization-combo-chart/combotutorial1new.png)
5. Görselleştirmenin sağ üst köşesindeki **Diğer seçenekler**’i (...) ve **Sıralama ölçütü > FiscalMonth** öğesini seçin. Sıralama düzenini değiştirmek için, üç nokta simgesini tekrar seçin ve **Artan düzende sırala** veya **Azalan düzende sırala**'yı seçin. Bu örnekte **Artan düzende sırala** kullanılacaktır.

6. Sütun grafiğini bir birleşik haritaya dönüştürün. İki birleşik haritalar vardır: **Çizgi ve yığılmış sütun** ile **Çizgi ve kümelenmiş sütun**. Sütun grafiği seçiliyken **Görsel Öğeler** bölmesinde **Çizgi ve kümelenmiş sütun grafiği**'ni seçin.

    ![birleşik harita dönüştürme örneği](media/power-bi-visualization-combo-chart/converttocombo-new2.png)
7. **Alanlar** bölmesinden **Sales** \> **Last Year Sales** alanını **Çizgi Değerleri** demetine sürükleyin.

   ![Son Yılın Satışları’nı gösteren çizgi değerleri](media/power-bi-visualization-combo-chart/linevaluebucket.png)

   Birleşik haritanız aşağıdaki gibi görünmelidir:

   ![birleşik harita bitti örneği](media/power-bi-visualization-combo-chart/combochartdone-new.png)

## <a name="create-a-combo-chart-with-two-axes"></a>İki eksenli birleşik harita oluşturma
Bu görevde brüt kâr ile satış verilerini karşılaştıracağız.

1. **Gross Margin Last Year %** verilerini **FiscalMonth** ölçütüne göre gösteren yeni bir çizgi grafik oluşturun. **Ay**’a göre ve **Artan düzende** sıralamak için üç nokta simgesini seçin.  
Ocak ayında brüt kâr %35'lerdeyken Nisan'da %45 ile zirveye ulaşıyor, Temmuz'da düşüyor ve Ağustos'ta tekrar zirveye çıkıyor. Geçen yıla ve bu yıla ait satış verilerini karşılaştırdığımızda benzer bir desen ile karşılaşacak mıyız?

   ![birleşik harita örnek satışları](media/power-bi-visualization-combo-chart/combo1-new.png)
2. **This Year Sales > Değer** ve **Last Year Sales** alanlarını çizgi grafiğe ekleyin. **Gross Margin Last Year %** alanının ölçeği, **Sales** alanının ölçeğinden çok daha küçük olduğundan karşılaştırma işlemi zorlaşır.      

   ![birleşik harita düz çizgi örneği](media/power-bi-visualization-combo-chart/flatline-new.png)
3. Görselin okunmasını ve yorumlanmasını daha kolay hale getirmek için çizgi grafiği Çizgi ve Yığılmış Sütun grafiğine dönüştürün.

   ![birleşik haritaya dönüştürme örneği](media/power-bi-visualization-combo-chart/converttocombo-new.png)

4. **Gross Margin Last Year %** alanını **Sütun Değerleri** demetinden alıp **Çizgi Değerleri** demetine sürükleyin. Power BI iki eksen oluşturarak veri kümelerinin farklı şekilde ölçeklenmesine olanak sağlar; sol eksende dolar cinsinden satış değeri gösterilirken sağ eksende yüzde ölçülür. Ve sorumuzun cevabını görüyoruz; evet, benzer bir desen görüyoruz.

   ![küme birleşik harita örneği](media/power-bi-visualization-combo-chart/power-bi-clustered-combo.png)    

## <a name="add-titles-to-the-axes"></a>Eksenlere başlık ekleme
1. Boya rulosu simgesini ![boya rulosu simgesi](media/power-bi-visualization-combo-chart/power-bi-paintroller.png) seçerek Biçimlendirme bölmesini açın.
1. **Y Ekseni** seçeneklerini genişletmek için aşağı oku seçin.
1. **Y Ekseni (Sütun)** için **Konum**'u **Sol**, **Başlık**’ı **Açık**, **Stil**’i **Yalnızca başlığı göster** ve **Birimleri görüntüle**’yi **Milyon** olarak ayarlayın.

   ![birleşik harita açık y örneği](media/power-bi-visualization-combo-chart/power-bi-open-y.png)
4. **Y Ekseni (Sütun)** altında **İkincili göster** seçeneğini görene kadar sayfayı aşağı kaydırın. Y eksenleri için çok sayıda seçenek olduğundan, her iki kaydırma çubuğunu da kullanmanız gerekebilir. İkinci göster bölümünde, birleşik haritanın çizgi grafik bölümünü biçimlendirmeye ilişkin seçenekler gösterilir.

   ![birleşik harita ikincil örneği](media/power-bi-visualization-combo-chart/power-bi-secondary.png)
5. **Y Ekseni (Satır)** için **Konum**'u **Sağ**, **Başlık**'ı **Açık**, **Stil**'i ise **Yalnızca başlığı göster** olarak ayarlayın.

   Artık birleşik haritanız başlıkları olan iki eksen görüntüler.

   ![birleşik harita başlıkları örneği](media/power-bi-visualization-combo-chart/power-bi-2-titles.png)

6. İsteğe bağlı olarak metin yazı tipini, boyutunu, rengini değiştirebilir; grafiğin görünümünü ve okunabilirliğini geliştirmek için diğer biçimlendirme seçeneklerini ayarlayabilirsiniz.

Bu noktada aşağıdakileri yapmak isteyebilirsiniz:

* [Birleşik haritayı pano kutucuğu olarak ekleme](../create-reports/service-dashboard-tiles.md).
* [Raporu kaydedin](../create-reports/service-report-save.md).
* [Raporu engelli kişiler için daha kolay erişilebilir hale getirin](../create-reports/desktop-accessibility-overview.md).

## <a name="cross-highlighting-and-cross-filtering"></a>Çapraz vurgulama ve çapraz filtreleme

Birleşik haritalarda bir sütun veya satır vurgulandığında, rapor sayfasındaki diğer görselleştirmeler için çapraz vurgu ve çapraz filtre uygulanır ve bu, tam tersi için de geçerlidir. Bu varsayılan davranışı değiştirmek için [görsel etkileşimlerinden](../create-reports/service-reports-visual-interactions.md) yararlanın.

## <a name="next-steps"></a>Sonraki adımlar

[Power BI'daki halka grafikler](power-bi-visualization-doughnut-charts.md)

[Power BI'daki görselleştirme türleri](power-bi-visualization-types-for-reports-and-q-and-a.md)
