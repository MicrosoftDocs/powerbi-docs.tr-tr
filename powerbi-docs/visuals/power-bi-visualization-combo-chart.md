---
title: Power BI'da Birleşik Grafik
description: Birleşik haritalar ile ilgili bu eğitimde, birleşik haritaları ne zaman kullanacağınızın yanı sıra Power BI hizmetinde ve Power BI Desktop'ta nasıl oluşturacağınız açıklanmaktadır.
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: lnv66cTZ5ho
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/22/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: e461480f53f4a97aeb4282e64a8a03eb8e1418d1
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66187779"
---
# <a name="combo-chart-in-power-bi"></a>Power BI'da Birleşik Grafik
Power BI'daki birleşik harita, çizgi grafik ile sütun grafiği içeren tek bir görselleştirmedir. Bu 2 grafiği tek bir görselleştirmede birleştirdiğinizde verileri daha hızlı şekilde karşılaştırabilirsiniz.

Birleşik haritalarda bir veya daha fazla Y ekseni bulunabilir.

## <a name="when-to-use-a-combo-chart"></a>Birleşik Haritaları ne zaman kullanırsınız?
Birleşik haritalar aşağıdaki durumlarda harika bir seçimdir:

* aynı X eksenine sahip bir çizgi grafiğiniz ve sütun grafiğiniz olduğunda.
* farklı değer aralıklarına sahip birden fazla ölçüyü karşılaştırmak istediğinizde.
* iki ölçü arasındaki bağıntıyı tek bir görselleştirmede sunmak istediğinizde.
* bir ölçünün, başka bir ölçü tarafından tanımlanan hedefi karşılayıp karşılamadığını kontrol etmek istediğinizde.
* tuval alanını tasarruflu bir şekilde kullanmak istediğinizde.

### <a name="prerequisites"></a>Önkoşullar
Birleşik haritalar Power BI hizmetinde ve Power BI Desktop'ta kullanılabilir. Bu eğitimde, Birleşik harita oluşturmak için Power BI hizmeti kullanılmaktadır. Birlikte ilerlemek için Power BI hizmetini açın ve "Perakende Analizi" örneğine bağlanın. ([İlgili yönergeler aşağıda verilmiştir](#create)).


## <a name="create-a-basic-single-axis-combo-chart"></a>Basit, tek eksenli bir Birleşik Harita oluşturma
Aşağıdaki videoda Will, Satış ve Pazarlama örneğini kullanarak bir birleşik harita oluşturmaktadır.

<iframe width="560" height="315" src="https://www.youtube.com/embed/lnv66cTZ5ho?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>  

<a name="create"></a> Kendi birleşik haritanızı oluşturmak için Power BI hizmetinde oturum açıp **Veri Al \> Örnekler \> Perakende Analizi Örneği > Bağlan > Panoya git** seçeneğini belirleyin.

1. "Retail Analysis Sample" panosunda, **Total Stores** kutucuğunu seçerek "Retail Analysis Sample" raporunu açın.
2. **Raporu düzenle**'yi seçerek raporu Düzenleme Görünümü'nde açın.
3. Yeni bir rapor sayfası ekleyin.
4. Bu yılın satış verilerini ve aya göre brüt kârı görüntüleyen bir sütun grafiği oluşturun.

    a.  Alanlar bölmesinde **Sales** \> **This Year Sales** > **Değer** seçeneğini belirleyin.

    b.  **Sales** \> **Gross Margin This Year** alanını **Değer** kutusuna sürükleyin.

    c. **Eksen** kutusuna eklemek üzere **Time** \> **FiscalMonth** alanını seçin.

    ![](media/power-bi-visualization-combo-chart/combotutorial1new.png)
5. Görselleştirmenin sağ üst köşesindeki üç nokta (...) simgesini seçin ve **Sıralama Ölçütü: FiscalMonth** seçeneğini belirleyin. Sıralama düzenini değiştirmek için, üç nokta simgesini tekrar seçin ve **Artan düzende sırala** veya **Azalan düzende sırala**'yı seçin.

6. Sütun grafiğini bir birleşik haritaya dönüştürün. İki birleşik haritalar vardır: **Çizgi ve yığılmış sütun** ile **Çizgi ve kümelenmiş sütun**. Sütun grafiği seçiliyken **Görsel Öğeler** bölmesinde **Çizgi ve kümelenmiş sütun grafiği**'ni seçin.

    ![](media/power-bi-visualization-combo-chart/converttocombo_new2.png)
7. **Alanlar** bölmesinden **Sales** \> **Last Year Sales** alanını **Çizgi Değerleri** demetine sürükleyin.

   ![](media/power-bi-visualization-combo-chart/linevaluebucket.png)

   Birleşik haritanız aşağıdaki gibi görünmelidir:

   ![](media/power-bi-visualization-combo-chart/combochartdone-new.png)

## <a name="create-a-combo-chart-with-two-axes"></a>İki eksenli birleşik harita oluşturma
Bu görevde brüt kâr ile satış verilerini karşılaştıracağız.

1. İzleyen yeni bir çizgi grafik oluşturun **Gross Margin last year %** tarafından **FiscalMonth**. **Ay**’a göre ve **Artan düzende** sıralamak için üç nokta simgesini seçin.  
Ocak ayında brüt kâr %35'lerdeyken Nisan'da %45 ile zirveye ulaşıyor, Temmuz'da düşüyor ve Ağustos'ta tekrar zirveye çıkıyor. Geçen yıla ve bu yıla ait satış verilerini karşılaştırdığımızda benzer bir desen ile karşılaşacak mıyız?

   ![](media/power-bi-visualization-combo-chart/combo1_new.png)
2. **This Year Sales > Değer** ve **Last Year Sales** alanlarını çizgi grafiğe ekleyin. **Gross Margin Last Year %** alanının ölçeği, **Sales** alanının ölçeğinden çok daha küçük olduğundan karşılaştırma işlemi zorlaşır.      

   ![](media/power-bi-visualization-combo-chart/flatline_new.png)
3. Görselin okunmasını ve yorumlanmasını daha kolay hale getirmek için çizgi grafiği Çizgi ve Yığılmış Sütun grafiğine dönüştürün.

   ![](media/power-bi-visualization-combo-chart/converttocombo_new.png)
4. **Gross Margin Last Year %** alanını **Sütun Değerleri** demetinden alıp **Çizgi Değerleri** demetine sürükleyin. Power BI iki eksen oluşturarak veri kümelerinin farklı şekilde ölçeklenmesine olanak sağlar; sol eksende dolar cinsinden satış değeri gösterilirken sağ eksende yüzde ölçülür. Ve sorumuzun cevabını görüyoruz; evet, benzer bir desen görüyoruz.

   ![](media/power-bi-visualization-combo-chart/power-bi-clustered-combo.png)    

## <a name="add-titles-to-the-axes"></a>Eksenlere başlık ekleme
1. Boya rulosu simgesini ![](media/power-bi-visualization-combo-chart/power-bi-paintroller.png) seçin ve Biçimlendirme bölmesini açın.
2. **Y Ekseni** seçeneklerini genişletmek için aşağı oku seçin.
3. İçin **y ekseni (sütun)** ayarlayın **konumu** için **sol**ayarlayın **başlık** için **üzerinde**,  **Stil** için **yalnızca başlığı göster**, ve **görüntüleme birimleri** olarak **milyonlarca**.

   ![](media/power-bi-visualization-combo-chart/power-bi-open-y.png)
4. Altında **y ekseni (sütun)** , görene kadar aşağı kaydırın **Sonrakini Göster**. Y ekseni için pek çok seçenek olduğundan, her iki kaydırma çubukları kullanmak zorunda kalabilirsiniz. Çizgi grafik bölümünü birleşik harita biçimlendirme seçenekleri göster ikincil bölümünde görüntüler.

   ![](media/power-bi-visualization-combo-chart/power-bi-secondary.png)
5. **Y Ekseni (Satır)** için **Konum**'u **Sağ**, **Başlık**'ı **Açık**, **Stil**'i ise **Yalnızca başlığı göster** olarak ayarlayın.

   Artık birleşik haritanız başlıkları olan iki eksen görüntüler.

   ![](media/power-bi-visualization-combo-chart/power-bi-2-titles.png)

6. İsteğe bağlı olarak metin yazı tipini, boyutunu, rengini değiştirebilir; grafiğin görünümünü ve okunabilirliğini geliştirmek için diğer biçimlendirme seçeneklerini ayarlayabilirsiniz.

Bu noktada aşağıdakileri yapmak isteyebilirsiniz:

* [Birleşik haritayı pano kutucuğu olarak ekleme](../service-dashboard-tiles.md).
* [Raporu kaydedin](../service-report-save.md).
* [Raporu engelli kişiler için daha kolay erişilebilir hale getirin](../desktop-accessibility.md).

## <a name="cross-highlighting-and-cross-filtering"></a>Çapraz vurgulama ve çapraz filtreleme

Birleşik haritalarda bir sütun veya satır vurgulandığında, rapor sayfasındaki diğer görselleştirmeler için çapraz vurgu ve çapraz filtre uygulanır ve bu, tam tersi için de geçerlidir. Bu varsayılan davranışı değiştirmek için [görsel etkileşimlerinden](../service-reports-visual-interactions.md) yararlanın.

## <a name="next-steps"></a>Sonraki adımlar

[Power BI'daki halka grafikler](power-bi-visualization-doughnut-charts.md)

[Power BI'daki görselleştirme türleri](power-bi-visualization-types-for-reports-and-q-and-a.md)
