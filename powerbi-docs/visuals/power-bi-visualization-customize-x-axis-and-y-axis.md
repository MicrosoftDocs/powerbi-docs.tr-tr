---
title: X ve Y ekseni özelliklerini özelleştirme
description: X ve Y ekseni özelliklerini özelleştirme
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: 9DeAKM4SNJM
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 01/20/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: e49b5ddab09c32662beb04ce70e5dc7606d92f59
ms.sourcegitcommit: 67336b077668ab332e04fa670b0e9afd0a0c6489
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44744993"
---
# <a name="customize-x-axis-and-y-axis-properties"></a>X ve Y ekseni özelliklerini özelleştirme
Bu eğitimde görsellerinizin x eksenini ve y eksenini özelleştirmenin pek çok farklı yolunu öğreneceksiniz. Tüm görsellerde eksenler bulunmaz ve tüm görseller özelleştirilemez; örneğin Pasta grafiklerde eksen bulunmaz. Özelleştirme seçenekleri görsellere göre farklılık gösterir. Tek bir makalede ele alınamayacak kadar çok seçenek vardır. Bu nedenle en sık kullanılan bazı eksenlere ilişkin özelleştirmeleri inceleyerek Power BI rapor tuvalinde görsel biçimlendirme sekmesini rahatlıkla kullanmanızı sağlayacağız.  

> [!NOTE]
> Bu sayfa hem Power BI hizmeti hem Power BI Desktop için geçerlidir. **Biçim** (boya rulosu simgesi ![](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-paintroller.png) ) seçiliyken kullanılabilen bu özelleştirmeler Power BI Desktop'ta da kullanılabilir.  
>
>

Amanda'nın X ve Y eksenlerini nasıl özelleştirdiğini izleyin ve detaydan çıkma ve detaya gitme işlevlerini kullanırken birleştirmeyi denetlemeye ilişkin çeşitli yöntemleri öğrenin. Ardından, Perakende Analizi örneği ile kendiniz denemek için videonun altındaki adım adım yönergeleri uygulayın.

<iframe width="560" height="315" src="https://www.youtube.com/embed/9DeAKM4SNJM" frameborder="0" allowfullscreen></iframe>


## <a name="customizing-visualization-x-axes-in-reports"></a>Raporlarda görselleştirme X eksenlerini özelleştirme
## <a name="create-a-stacked-chart-visualization"></a>Yığılmış grafik görselleştirmesi oluşturma
Power BI hizmetinde oturum açın ve **Retail Analysis Sample** raporunu [Düzenleme Görünümü](../service-interact-with-a-report-in-editing-view.md)'nde açın. Örneği takip etmek için [Perakende Analizi örneğine bağlanın](../sample-datasets.md).

1. Bu yılın ve geçen yılın satış değerlerini mali aya göre gösteren yeni bir sütun grafik oluşturun.
2. Yığılmış sütun grafiğe dönüştürün.

    ![](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-create-chart.png)

## <a name="customize-the-x-axis"></a>X eksenini özelleştirme
1. Görsel Öğeler ve Filtreler bölmesinde özelleştirme seçeneklerini görüntülemek için **Biçim** (boya rulosu simgesi ![](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-paintroller.png) ) öğesini seçin.
2. X ekseni seçeneklerini genişletin.

   ![](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-x-axis.png)
3. Açık (veya Kapalı) kaydırıcısını seçerek X eksenini etkinleştirin veya devre dışı bırakın. Şimdilik **Açık** durumunda bırakın.  Daha fazla veri için alan ayırmak üzere X eksenini kapatmak isteyebilirsiniz.

    ![](media/power-bi-visualization-customize-x-axis-and-y-axis/onoffslider.png)
4. Metin rengini, boyutunu ve yazı tipini biçimlendirin. Bu örnekte **Renk** için siyah, **Metin Boyutu** için 14 ve **Yazı Tipi** için Arial Black seçeneğini belirledik.  
5. X ekseni Başlığını **Açık** duruma getirin ve X ekseninin adını görüntüleyin; bu durumda, **FiscalMonth** şeklindedir.  
6. Başlığın metin rengini, boyutunu ve yazı tipini biçimlendirin.  Bu örnekte **Başlık rengi** için turuncu, **Eksen başlığı** için **Fiscal Month** ve **Başlık metin boyutu** için 21 seçeneğini belirledik.
7. FiscalMonth değerine göre sıralamak için grafiğin sağ üst köşesindeki üç noktayı (...) ve ardından **Sıralama Ölçütü: FiscalMonth** seçeneğini belirleyin.

    Bu özelleştirmelerin ardından sütun grafiğiniz aşağıdakine benzer şekilde görünür:

     ![](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-customize-axis.png)

Şu ana dek yaptığınız tüm X ekseni özelleştirmelerini geri almak için **X ekseni** özelleştirme bölmesinin altındaki **Varsayılana Geri Dön** seçeneğini belirleyin.

## <a name="customize-the-y-axis"></a>Y eksenini özelleştirme
1. Y ekseni seçeneklerini genişletin.

   ![](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-y-axis.png)

2. Açık (veya Kapalı) kaydırıcısını seçerek Y eksenini açın veya kapatın. Şimdilik **Açık** durumunda bırakın.  Daha fazla veri için alan ayırmak üzere Y eksenini kapatmak isteyebilirsiniz.
   
    ![](media/power-bi-visualization-customize-x-axis-and-y-axis/onoffslider.png)
3. Y Ekseni **Konumunu** sağ olarak ayarlayın.
4. Metin rengini, boyutunu ve yazı tipini biçimlendirin. Bu örnekte **Renk** için siyah, **Metin Boyutu** için 14 ve **Yazı Tipi** için Arial Black seçeneğini belirledik.  
5. **Görüntüleme birimleri** seçeneğini Milyon olarak ve **Değer ondalık basamakları** seçeneğini sıfır olarak bırakın.
6. Bu görselleştirme için Y ekseni başlığının görüntülenmesi görseli geliştirmediğinden **Başlık** seçeneğini Kapalı olarak bırakın.  
7. **Renk** seçeneğini koyu gri olarak değiştirerek ve **Darbe genişliği** değerini 2'ye artırarak kılavuz çizgilerini belirginleştirin.

    Bu özelleştirmelerin ardından sütun grafiğiniz aşağıdakine benzer şekilde görünür:

     ![](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-y-axis-complete.png)

## <a name="customizing-visualizations-with-dual-y-axes"></a>Çift y eksenli görselleştirmeleri özelleştirme
Mağaza sayısının satış üzerindeki etkisini gösteren bir Birleşik harita oluşturun.  Bu, [Birleşik harita Eğitimi](power-bi-visualization-combo-chart.md)'nde oluşturulan aynı grafiktir. Ardından çift y eksenini biçimlendirin.

### <a name="create-a-chart-with-two-y-axes"></a>İki Y eksenli bir grafik oluşturun
1. **Time > FiscalMonth** tarafından **Sales > Gross Margin last year %** değerini izleyen yeni bir çizgi grafiği oluşturun.
2. Üç noktayı (...) ve ardından **Sıralama ölçütü: Month** seçeneğini belirleyerek görseli sıralayın

    ![](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-line-chart.png)

> [NOTE]: For help sorting by month, see [sorting by other criteria](../power-bi-report-change-sort.md#other)
> 1. Ocak ayında brüt kâr %35'lerdeyken Nisan'da %45 ile zirveye ulaşıyor, Temmuz'da düşüyor ve Ağustos'ta tekrar zirveye çıkıyor. Geçen yıla ve bu yıla ait satış verilerini karşılaştırdığımızda benzer bir desen ile karşılaşacak mıyız?
> 2. **This Year Sales > Değer** ve **Last Year Sales** alanlarını çizgi grafiğe ekleyin. Geçen yıla ait brüt kâr yüzdesini gösteren **Gross Margin Last Year %** alanının (0M% kılavuz çizgisi boyunca görüntülenen mavi çizgi) ölçeği, satış verilerini gösteren **Sales** alanının ölçeğinden çok daha küçük olduğundan karşılaştırma işlemi zorlaşır. Y ekseni etiket yüzdeleri mantıksızdır.      

   ![](media/power-bi-visualization-customize-x-axis-and-y-axis/flatline_new.png)
5. Görselin okunmasını ve yorumlanmasını daha kolay hale getirmek için çizgi grafiği Çizgi ve Yığılmış Sütun grafiğine dönüştürün.

   ![](media/power-bi-visualization-customize-x-axis-and-y-axis/converttocombo_new.png)

6. **Gross Margin Last Year %** alanını **Sütun Değerleri** demetinden alıp **Çizgi Değerleri** demetine sürükleyin. Artık yukarıda oluşturduğumuz yığılmış sütun grafiğimiz ***ve*** bir çizgi grafiğimiz vardır.  (İsteğe bağlı olarak, eksen yazı tipi rengini ve boyutunu biçimlendirmek üzere yukarıda öğrendiklerinizi uygulayın.)
   

   Power BI iki eksen oluşturarak veri kümelerinin farklı şekilde ölçeklenmesini sağlar; sol eksende dolar cinsinden para değeri gösterilirken sağ eksende yüzde ölçülür.

   ![](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-dual-axes-new.png)

### <a name="format-the-secondary-y-axis"></a>İkincil y eksenini biçimlendirme
1. **Görsel Öğeler** bölmesinde, biçimlendirme seçeneklerini görüntülemek için boya rulosu simgesini seçin.
2. Aşağı oku seçerek Y Ekseni seçeneklerini genişletin.
3. **Sonrakini göster** seçeneklerini bulana dek listeyi kaydırın. **Sonrakini Göster** seçeneğini **Kapalı** yerine **Açık** olarak ayarlayın.

   ![](media/power-bi-visualization-customize-x-axis-and-y-axis/combo3.png)

   ![](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-dual-axes.png)
4. (İsteğe bağlı) İki ekseni özelleştirin. Sütun ekseni veya çizgi ekseni için **Konum** değerini değiştirirseniz iki eksen yer değiştirir.

   ![](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-y-axes-options.png)

### <a name="add-titles-to-both-axes"></a>Her iki eksene başlık ekleme
Bu düzeyde karmaşık olan görselleştirmelerde eksen başlıklarının eklenmesi faydalıdır.  Başlıklar, iş arkadaşlarınızın görselleştirmeniz ile anlatılanları anlamasına yardımcı olur.

1. **Y Ekseni (Sütun)** ve **Y Ekseni (Satır)** için **Başlık** değerini **Açık** olarak ayarlayın.
2. **Stil** seçeneğini **Yalnızca başlığı göster** olarak ayarlayın.

   ![](media/power-bi-visualization-customize-x-axis-and-y-axis/yaxissettings.png)
3. Artık Birleşik haritanız başlıkları olan iki eksen görüntüler.

   ![](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-combo-chart.png)

Daha fazla bilgi için bkz. [Renk biçimlendirme, etiketleme ve eksen özellikleri ile ilgili ipuçları ve püf noktaları](service-tips-and-tricks-for-color-formatting.md).

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme
X ekseni rapor sahibi tarafından tarih türü olarak kategorize edilirse **Tür** seçeneği görüntülenir ve sürekli veya kategorik arasında seçim yapabilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI raporlarındaki görselleştirmeler](power-bi-report-visualizations.md) hakkında daha fazla bilgi

[B](power-bi-visualization-customize-title-background-and-legend.md)[aşlıkları, arka planları ve açıklamaları özelleştirme](power-bi-visualization-customize-title-background-and-legend.md)

[Renkleri ve eksen özelliklerini özelleştirme](service-getting-started-with-color-formatting-and-axis-properties.md)

[Power BI - Temel Kavramlar](../service-basic-concepts.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)
