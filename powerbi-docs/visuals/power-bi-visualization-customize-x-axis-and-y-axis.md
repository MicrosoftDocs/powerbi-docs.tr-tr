---
title: X Ekseni ve Y Ekseni özelliklerini özelleştirme
description: X Ekseni ve Y Ekseni özelliklerini özelleştirme
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: 9DeAKM4SNJM
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/24/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 3bfe84acdf73fcb5ace791c9a84943262d0f73ab
ms.sourcegitcommit: 1c96b65a03ec0a0612e851dd58c363f4d56bca38
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2019
ms.locfileid: "67390089"
---
# <a name="customize-x-axis-and-y-axis-properties"></a>X Ekseni ve Y Ekseni özelliklerini özelleştirme

Bu eğitimde görsellerinizin X Eksenini ve Y Eksenini özelleştirmenin pek çok farklı yolunu öğreneceksiniz. Tüm görsellerin ekseni yoktur. Örneğin pasta grafiklerinde eksen bulunmaz. Özelleştirme seçenekleri de bir görselden diğerine farklılık gösterir. Bir makalenin kapsamına sığmayacak kadar çok seçenek vardır; bu nedenle en sık kullanılan bazı eksenlere ilişkin özelleştirmeleri inceleyerek Power BI rapor tuvalinde görsel **Biçim** bölmesini rahatlıkla kullanmanızı sağlayacağız.  

> [!NOTE]
> Bu sayfa hem Power BI hizmeti hem Power BI Desktop için geçerlidir. **Biçim** (boya rulosu ![Boya rulosu simgesinin ekran görüntüsü.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-paintroller.png)) simgesi seçiliyken kullanılabilen bu özelleştirmeler Power BI Desktop'ta da kullanılabilir.

Amanda'nın X ve Y Eksenlerini özelleştirmesini izleyin. Detaya gitme ve detaydan çıkma kullanılırken birleştirme işlemini denetlemenin farklı yollarını gösterecek.

<iframe width="560" height="315" src="https://www.youtube.com/embed/9DeAKM4SNJM" frameborder="0" allowfullscreen></iframe>

## <a name="prerequisites"></a>Önkoşullar

- Power BI hizmeti

- Perakende Analizi Örneği raporu

## <a name="customize-visualization-x--and-y-axes-in-reports"></a>Raporlardaki görselleştirme X ve Y Eksenlerini özelleştirme

Örneği takip etmek için [Power BI hizmetinde](https://app.powerbi.com) oturum açın ve [Perakende Analizi Örneği](../sample-datasets.md) raporunu [Raporu düzenleme](../service-interact-with-a-report-in-editing-view.md) görünümünde açın.

### <a name="create-a-stacked-column-chart-visualization"></a>Yığılmış sütun grafiği görselleştirmesi oluşturma

Görselleştirmenizi özelleştirebilmek için önce oluşturmanız gerekir.

1. Power BI hizmetinde **Çalışma Alanım**'ı genişletin.

1. Ekranı aşağı kaydırın ve **Veri kümeleri** listesinden **Perakende Analizi Örneği**'ni seçin.

1. **Görselleştirmeler** bölmesinden yığılmış sütun grafiği simgesini seçin.

    ![Görselleştirmeler bölmesinin ve boş bir yığılmış sütun grafiğinin ekran görüntüsü](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-stacked-column-chart.png)

1. X Ekseni değerlerini ayarlamak için **Alanlar** bölmesinde **Time** > **FiscalMonth** alanını seçin.

1. Y Ekseni değerlerini ayarlamak için **Alanlar** bölmesinden **Sales** > **Last Year Sales** ve **Sales** > **This Year Sales** > **Value** alanını seçin.

    ![Doldurulmuş yığılmış sütun grafiğinin ekran görüntüsü.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-create-chart.png)

### <a name="customize-the-x-axis"></a>X Eksenini özelleştirme

Artık X Eksenini özelleştirebilirsiniz.

1. **Görselleştirmeler** bölmesinde özelleştirme seçeneklerini görüntülemek için **Biçim** (boya rulosu simgesi ![Boya rulosu simgesinin ekran görüntüsü.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-paintroller.png)) öğesini seçin.

1. X ekseni seçeneklerini genişletin.

   ![X Ekseni seçeneklerinin ekran görüntüsü.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-x-axis.png)

1. **X Ekseni** kaydırıcısını **Açık** konuma getirin.

    ![Açık kaydırıcının ekran görüntüsü.](media/power-bi-visualization-customize-x-axis-and-y-axis/onoffslider.png)

    Daha fazla veriye yer açmak için X Eksenini kapatmak isteyebilirsiniz.

1. Metin rengini, boyutunu ve yazı tipini biçimlendirin:

    - **Renk**: Siyahı seçin

    - **Metin boyutu**: *14* girin

    - **Yazı tipi ailesi**: **Arial Black** seçin

1. **Başlık** seçeneğini **Açık** konuma getirerek X Ekseninin adını görüntüleyin. Bu örnekte ad **FiscalMonth** olur.

1. Başlığın metin rengini, boyutunu ve yazı tipini biçimlendirin:

    - **Başlık rengi**: Turuncu seçin

    - **Eksen başlığı**: *Fiscal Month* girin

    - **Başlık metin boyutu**: *21* girin

Özelleştirmeleri bitirdikten sonra yığılmış sütun grafiğiniz aşağıdakine benzer görünecektir:

![Özelleştirilmiş yığılmış sütun grafiğinin ekran görüntüsü.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-customize-axis.png)

Yaptığınız değişiklikleri kaydedin ve sonraki bölüme geçin.

Yaptığınız tüm değişiklikleri geri almanız gerekirse, **X Ekseni** özelleştirme bölmesinin altındaki **Varsayılana geri dön** seçeneğini belirleyin.

### <a name="customize-the-y-axis"></a>Y Eksenini özelleştirme

Ardından Y Ekseninizi özelleştireceksiniz.

1. Y ekseni seçeneklerini genişletin.

   ![X ekseni seçeneklerinin ekran görüntüsü.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-y-axis.png)

1. **Y Ekseni** kaydırıcısını **Açık** konuma getirin.  

    ![Açık kaydırıcının ekran görüntüsü.](media/power-bi-visualization-customize-x-axis-and-y-axis/onoffslider.png)

    Daha fazla veriye yer açmak için Y Eksenini kapatmak isteyebilirsiniz.

1. Y Ekseni **Konumunu** **Sağ** olarak ayarlayın.

1. Metin rengini, boyutunu ve yazı tipini biçimlendirin:

    - **Renk**: Siyahı seçin

    - **Metin boyutu**: *14* girin

    - **Yazı tipi ailesi**: **Arial Black** seçin

1. **Görüntüleme birimleri** seçeneğini **Milyon** olarak ve **Değer ondalık basamakları** seçeneğini *0* olarak ayarlayın.

1. Bu görselleştirme için Y ekseni başlığının görüntülenmesi görseli geliştirmediğinden, **Başlık** seçeneğini **Kapalı** olarak bırakın.  

1. Rengi değiştirerek ve darbeyi artırarak kılavuz çizgilerini belirginleştirin:

    - **Renk**: Koyu gri seçin

    - **Darbe**: *2* girin

Bu özelleştirmelerin ardından sütun grafiğiniz aşağıdakine benzer şekilde görünür:

![Özelleştirilmiş Y Ekseninin bulunduğu grafiğin ekran görüntüsü.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-y-axis-complete.png)

## <a name="customizing-visualizations-with-dual-y-axes"></a>Çift Y Eksenli görselleştirmeleri özelleştirme

Önce mağaza sayısının satış üzerindeki etkisini gösteren bir birleşik harita oluşturacaksınız. Bu, [Birleşik harita eğitimi](power-bi-visualization-combo-chart.md) sırasında oluşturulan aynı grafiktir. Ardından çift Y Eksenini biçimlendireceksiniz.

### <a name="create-a-chart-with-two-y-axes"></a>İki Y Eksenli bir grafik oluşturun

1. **Time > FiscalMonth** tarafından **Sales > Gross Margin last year %** değerini izleyen yeni bir çizgi grafiği oluşturun.

    ![Yeni çizgi grafiğin ekran görüntüsü.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-line-chart.png)

    > [!NOTE]
    > Aylara göre sıralarken yardım almak için bkz. [Başka ölçütler kullanarak sıralama](../consumer/end-user-change-sort.md#other).

    January Gross Margin yüzdesi %35'di, Nisan ayında %45 ile zirve yaptı, Temmuz ayında düştü ve Ağustos'ta yeniden zirve yaptı. Geçen yıla ve bu yıla ait satış verilerini karşılaştırdığımızda benzer bir desen ile karşılaşacak mıyız?

1. **This Year Sales > Değer** ve **Last Year Sales** alanlarını çizgi grafiğe ekleyin.

    ![Eklenen yeni verilerle çizgi grafiğin ekran görüntüsü.](media/power-bi-visualization-customize-x-axis-and-y-axis/flatline_new.png)

    Geçen yıla ait brüt kâr yüzdesini gösteren **Gross Margin Last Year %** alanının (**0M%** kılavuz çizgisi boyunca görüntülenen mavi çizgi) ölçeği, satış verilerini gösteren **Sales** alanının ölçeğinden çok daha küçük olduğundan karşılaştırma işlemi zorlaşır. Y ekseni etiket yüzdeleri mantıksızdır.

1. Görselin okunmasını ve yorumlanmasını daha kolay hale getirmek için çizgi grafiği Çizgi ve yığılmış sütun grafiğine dönüştürün.

   ![Çizgi ve yığılmış sütun grafiği seçeneğinin vurgulandığı Görselleştirmeler bölmesinin ekran görüntüsü.](media/power-bi-visualization-customize-x-axis-and-y-axis/converttocombo_new.png)

1. **Gross Margin Last Year %** alanını **Sütun Değerleri** demetinden alıp **Çizgi Değerleri** demetine sürükleyin.

    ![Üç değerin de net bir şekilde gösterildiği çizgi ve yığılmış sütun grafiğin ekran görüntüsü.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-dual-axes.png)

    Şimdi ilk bölümde oluşturduğunuz yığılmış sütun grafiğin üzerine yerleştirilmiş bir çizgi grafiğiniz oldu. İsteğe bağlı olarak, eksen yazı tipi rengini ve boyutunu biçimlendirmek üzere yukarıda öğrendiklerinizi uygulayın.

   ![Özelleştirilmiş çizgi ve yığılmış sütun grafiğinin ekran görüntüsü.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-dual-axes-new.png)

   Power BI iki Y Ekseni oluşturarak veri kümelerinin farklı ölçeklendirilmesine olanak tanır. Sol taraftaki eksen doları ölçer ve sağ taraf eksen de yüzdeyi ölçer.

### <a name="format-the-secondary-y-axis"></a>İkincil Y Eksenini biçimlendirme

1. **Görselleştirmeler** bölmesinde biçim seçeneklerini görüntülemek için boya rulosu simgesini seçin.

1. Y ekseni seçeneklerini genişletin.

1. **İkincili göster** seçeneğini bulana kadar ekranı aşağı kaydırın. Bu seçeneğin **Açık** olduğundan emin olun.

   ![İkincili göster seçeneğinin ekran görüntüsü.](media/power-bi-visualization-customize-x-axis-and-y-axis/combo3.png)

1. (İsteğe bağlı) İki ekseni özelleştirin. Sütun ekseni veya çizgi ekseni için **Konum** değerini değiştirirseniz iki eksen yer değiştirir.

### <a name="add-titles-to-both-axes"></a>Her iki eksene başlık ekleme

Bu düzeyde çok karmaşık olan görselleştirmelerde eksen başlıklarının eklenmesi faydalıdır.  Başlıklar, iş arkadaşlarınızın görselleştirmeniz ile anlatılanları öğrenmesine yardımcı olur.

1. **Y Ekseni (Sütun)** ve **Y Ekseni (Satır)** için **Başlık** değerini **Açık** olarak ayarlayın.

1. Her ikisi için de **Stil** seçeneğini **Yalnızca başlığı göster** olarak ayarlayın.

   ![Başlık ve Stil seçeneklerinin ekran görüntüsü.](media/power-bi-visualization-customize-x-axis-and-y-axis/yaxissettings.png)

1. Artık birleşik haritanız başlıkları olan iki eksen gösterir.

   ![Özelleştirilmiş çift Y Ekseni olan grafiğin ekran görüntüsü.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-combo-chart.png)

Daha fazla bilgi için bkz. [Power BI'da renk biçimlendirmeye ilişkin ipuçları ve püf noktaları](service-tips-and-tricks-for-color-formatting.md).

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme

X Ekseni rapor sahibi tarafından tarih türü kategorisine ayrılmışsa **Tür** seçeneği görüntülenir ve sürekli veya kategorik arasında seçim yapabilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

- [Power BI raporlarındaki görselleştirmeler](power-bi-report-visualizations.md)

- [Görselleştirme başlıklarını, göstergelerini ve arka planlarını özelleştirme](power-bi-visualization-customize-title-background-and-legend.md)

- [Renk biçimlendirme ve eksen özelliklerini kullanmaya başlama](service-getting-started-with-color-formatting-and-axis-properties.md)

- [Power BI hizmeti müşterilerine yönelik temel kavramlar](../consumer/end-user-basic-concepts.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)
