---
title: Power BI'da birleşik harita
description: Birleşik haritalar ile ilgili bu eğitimde, birleşik haritaları ne zaman kullanacağınızın yanı sıra Power BI hizmetinde ve Power BI Desktop'ta nasıl oluşturacağınız açıklanmaktadır.
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: lnv66cTZ5ho
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/23/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: e4b7b4b336b376f6ccec0bc0fe56de107ab8bd09
ms.sourcegitcommit: 7d52401f50944feaaa112c84113ee47f606dbf68
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/13/2019
ms.locfileid: "67124194"
---
# <a name="combo-chart-in-power-bi"></a>Power BI'da birleşik harita

Power BI'daki birleşik harita, çizgi grafik ile sütun grafiği içeren tek bir görselleştirmedir. Bu iki grafiği tek bir görselleştirmede birleştirdiğinizde verileri daha hızlı karşılaştırabilirsiniz.

Birleşik haritalarda bir veya daha fazla Y ekseni bulunabilir.

## <a name="when-to-use-a-combo-chart"></a>Birleşik haritaları ne zaman kullanırsınız?

Birleşik haritalar aşağıdaki durumlarda harika bir seçimdir:

* Aynı X eksenine sahip bir çizgi grafiğinizle bir sütun grafiğiniz olduğunda.

* Farklı değer aralıklarına sahip birden fazla ölçüyü karşılaştırmak istediğinizde.

* İki ölçü arasındaki bağıntıyı tek bir görselleştirmede sunmak istediğinizde.

* Bir ölçünün, başka bir ölçü tarafından tanımlanan hedefi karşılayıp karşılamadığını kontrol etmek istediğinizde.

* Tuval alanını tasarruflu kullanmak istediğinizde.

## <a name="prerequisites"></a>Önkoşullar

Birleşik haritalar Power BI hizmetinde ve Power BI Desktop'ta kullanılabilir. Bu eğitimde, birleşik harita oluşturmak için Power BI hizmeti kullanılmaktadır. Power BI'da oturum açmak için kullanıcı kimlik bilgilerinizin olduğundan emin olun.

Aşağıdaki videoda Will, Satış ve Pazarlama örneğini kullanarak bir birleşik harita oluşturmaktadır.

<iframe width="560" height="315" src="https://www.youtube.com/embed/lnv66cTZ5ho?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>  

## <a name="create-a-basic-single-axis-combo-chart"></a>Basit, tek eksenli bir birleşik harita oluşturma

Konuyu takip etmek için Power BI hizmetini açın ve **Perakende Analizi örneğine** bağlanın. Kendi birleşik haritanızı oluşturmak için Power BI'da oturum açın ve **Veril Al**  > **Örnekler** > **Perakende Analiz Örneği** > **Bağlan**’ı seçin. **Perakende Analizi Örneği** panosu açılır.

1. "Perakende Analizi Örneği" panosunda **Total Stores** kutucuğunu seçerek **Store Sales Overview** raporunu açın.

1. **Raporu düzenle**'yi seçerek raporu Düzenleme Görünümü'nde açın.

1. Sayfanın en altındaki **+** simgesini seçerek yeni bir rapor sayfası ekleyin.

1. Bu yılın satış verilerini ve aya göre brüt kârı gösteren bir sütun grafiği oluşturun.

    1. Alanlar bölmesinde **Sales** \> **This Year Sales** > **Değer** seçeneğini belirleyin.

    1. **Sales** \> **Gross Margin This Year** alanını **Değer** kutusuna sürükleyin.

    1. **Eksen** kutusuna eklemek üzere **Time** \> **FiscalMonth** alanını seçin.

        ![Yeni oluşturulan sütun grafiğinin ekran görüntüsü.](media/power-bi-visualization-combo-chart/combotutorial1new.png)

1. Görselleştirmenin sağ üst köşesindeki üç nokta simgesini seçin ve **Sıralama Ölçütü > FiscalMonth** seçeneğini belirleyin. Sıralama düzenini değiştirmek için, üç nokta simgesini tekrar seçin ve **Artan düzende sırala** veya **Azalan düzende sırala**'yı seçin.

1. Sütun grafiğini bir birleşik haritaya dönüştürün. İki birleşik haritalar vardır: **Çizgi ve yığılmış sütun** ile **Çizgi ve kümelenmiş sütun**. Sütun grafiği seçiliyken **Görsel Öğeler** bölmesinde **Çizgi ve kümelenmiş sütun grafiği**'ni seçin.

    ![Çizgi ve kümelenmiş sütun grafiği seçeneğinin vurgulandığı görselleştirme bölmesinin ekran görüntüsü.](media/power-bi-visualization-combo-chart/converttocombo_new2.png)

1. **Alanlar** bölmesinden **Sales**  >  **Last Year Sales** alanını **Çizgi Değerleri** kutusuna sürükleyin.

    ![Last Year Sales değerinin Çizgi Değerleri kutusuna sürüklendiği ekran görüntüsü.](media/power-bi-visualization-combo-chart/linevaluebucket.png)

    Birleşik haritanız aşağıdaki gibi görünmelidir:

    ![Last Year Sales satırı değerinin eklendiği sütun grafiğinin ekran görüntüsü.](media/power-bi-visualization-combo-chart/combochartdone-new.png)

## <a name="create-a-combo-chart-with-two-axes"></a>İki eksenli birleşik harita oluşturma

Bu görevde brüt kâr ile satış verilerini karşılaştıracağız.

1. **Gross Margin Last Year %** verilerini **Month** ölçütüne göre gösteren yeni bir çizgi grafik oluşturun. **Ay**’a göre ve **Artan düzende** sıralamak için üç nokta simgesini seçin.

    ![Yeni çizgi grafiğin ekran görüntüsü.](media/power-bi-visualization-combo-chart/combo1_new.png)

     Ocak ayında brüt kâr %35'lerdeyken Nisan'da %45 ile zirveye ulaşıyor, Temmuz'da düşüyor ve Ağustos'ta tekrar zirveye çıkıyor. Geçen yıla ve bu yıla ait satış verilerini karşılaştırdığımızda benzer bir desen ile karşılaşacak mıyız?

1. **This Year Sales** > **Value** ve **Last Year Sales** alanlarını çizgi grafiğe ekleyin. **Gross Margin Last Year %** alanının ölçeği, **Sales** alanının ölçeğinden çok daha küçüktür. Bunları karşılaştırmak zordur.

    ![Value ve Last Year Sales’in eklendiği çizgi grafiğin ekran görüntüsü.](media/power-bi-visualization-combo-chart/flatline_new.png)

1. Görselin okunmasını ve yorumlanmasını daha kolay hale getirmek için çizgi grafiği Çizgi ve Yığılmış Sütun grafiğine dönüştürün.

    ![Çizgi ve yığılmış sütun grafiği seçeneğinin vurgulandığı görselleştirme bölmesinin ekran görüntüsü.](media/power-bi-visualization-combo-chart/converttocombo_new.png)

1. **Gross Margin Last Year %** alanını **Sütun Değerleri** demetinden alıp **Çizgi Değerleri** demetine sürükleyin. 

    ![Çizgi ve yığılmış sütun grafiğinin ekran görüntüsü](media/power-bi-visualization-combo-chart/power-bi-combochart.png)

    Power BI iki eksen oluşturur ve hizmetin veri kümelerini farklı ölçeklendirmesini sağlar. Sol taraf satış dolarını ölçer ve sağ taraf yüzdeyi ölçer. Ve sorumuzun yanıtını görürüz: Evet, gerçekten benzer bir desen görüyoruz.

## <a name="add-titles-to-the-axes"></a>Eksenlere başlık ekleme

1. Boya rulosu simgesini ![Boya rulosu simgesinin ekran görüntüsü.](media/power-bi-visualization-combo-chart/power-bi-paintroller.png) seçerek Biçimlendirme bölmesini açın.

1. **Y Ekseni** seçeneklerini genişletmek için aşağı oku seçin.

1. **Y ekseni (Sütun)** için şu seçenekleri belirleyin:

    | Ayar | Değer |
    | ------- | ----- |
    | Konum | **Sol**’u seçin. |
    | Birimleri görüntüle | **Milyon**’u seçin. |
    | Başlık | Kaydırıcıyı **Açık** konumuna getirin. |
    | Stil | **Yalnızca başlığı göster**’i seçin. |
    | İkincili göster | Kaydırıcıyı **Açık** konumuna getirin.  Bu ayar, birleşik haritanın çizgi grafik bölümünü biçimlendirmeye ilişkin seçenekleri gösterir. |

1. **Y ekseni (Çizgi)** için şu seçenekleri belirleyin:

    | Ayar | Değer |
    | ------- | ----- |
    | Konum | **Sağ**’ı seçin. |
    | Başlık | Kaydırıcıyı **Açık** konumuna getirin. |
    | Stil | **Yalnızca başlığı göster**’i seçin. |

    Artık birleşik haritanız başlıkları olan iki eksen gösterir.

    ![Başlıkların açık olduğu Çizgi ve yığılmış sütun grafiğinin ekran görüntüsü.](media/power-bi-visualization-combo-chart/power-bi-titles-on.png)

1. İsteğe bağlı olarak metin yazı tipini, boyutunu, rengini değiştirebilir; grafiğin görünümünü ve okunabilirliğini geliştirmek için diğer biçimlendirme seçeneklerini ayarlayabilirsiniz.

Bu noktada aşağıdakileri yapmak isteyebilirsiniz:

* [Birleşik haritayı pano kutucuğu olarak ekleme](../service-dashboard-tiles.md).

* [Raporu kaydedin](../service-report-save.md).

* [Raporu engelli kişiler için daha kolay erişilebilir hale getirin](../desktop-accessibility.md).

## <a name="cross-highlighting-and-cross-filtering"></a>Çapraz vurgulama ve çapraz filtreleme

Birleşik haritalarda bir sütun veya satır vurgulandığında, rapor sayfasındaki diğer görselleştirmeler için çapraz vurgu ve çapraz filtre uygulanır. Bu varsayılan davranışı değiştirmek için [görsel etkileşimlerinden](../service-reports-visual-interactions.md) yararlanın.

## <a name="next-steps"></a>Sonraki adımlar

[Power BI'daki halka grafikler](power-bi-visualization-doughnut-charts.md)

[Power BI'daki görselleştirme türleri](power-bi-visualization-types-for-reports-and-q-and-a.md)