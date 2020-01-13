---
title: X ve Y ekseni özelliklerini özelleştirme
description: X ve Y ekseni özelliklerini özelleştirme
author: mihart
ms.reviewer: ''
featuredvideoid: 9DeAKM4SNJM
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 12/3/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 830fbe945405f8ad7aadd7ceac9fb1967daad22b
ms.sourcegitcommit: 97597ff7d9ac2c08c364ecf0c729eab5d59850ce
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2020
ms.locfileid: "75758118"
---
# <a name="customize-x-axis-and-y-axis-properties"></a>X ekseni ve Y ekseni özelliklerini özelleştirme

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

Bu öğreticide görsellerinizin X eksenini ve Y eksenini özelleştirmenin pek çok farklı yolunu öğreneceksiniz. Tüm görsellerin ekseni yoktur. Örneğin pasta grafiklerinde eksen bulunmaz. Özelleştirme seçenekleri de bir görselden diğerine farklılık gösterir. Bir makalenin kapsamına sığmayacak kadar çok seçenek vardır; bu nedenle en sık kullanılan bazı özelleştirmeleri inceleyerek Power BI rapor tuvalinde görsel **Biçim** bölmesini rahatlıkla kullanmanızı sağlayacağız.  

Amanda'nın X ve Y eksenlerini özelleştirmesini izleyin. Detaya gitme ve detaydan çıkma kullanılırken birleştirme işlemini denetlemenin farklı yollarını da gösterecek.

> [!NOTE]
> Bu videoda Power BI’ın eski bir sürümü kullanılmaktadır.

<iframe width="560" height="315" src="https://www.youtube.com/embed/9DeAKM4SNJM" frameborder="0" allowfullscreen></iframe>

## <a name="prerequisites"></a>Önkoşullar

- Power BI Desktop

- [Perakende Analizi Örneği](https://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix)


## <a name="add-a-new-visualization"></a>Yeni görselleştirme ekleme

Görselleştirmenizi özelleştirebilmek için önce oluşturmanız gerekir.

1. Power BI Desktop’ta Perakende Analizi örneğini açın.  

2. En alttaki sarı artı simgesini seçerek yeni bir sayfa ekleyin. 

    ![sarı artı işareti](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-new-page-icon.png)

1. **Görselleştirmeler** bölmesinden yığılmış sütun grafiği simgesini seçin. Bu işlem, rapor tuvalinize boş bir şablon ekler.

    ![Görselleştirmeler bölmesinin ve boş bir yığılmış sütun grafiğinin ekran görüntüsü](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-column-chart.png)

1. X ekseni değerlerini ayarlamak için **Alanlar** bölmesinde **Zaman** > **MaliAy** alanını seçin.

1. Y ekseni değerlerini ayarlamak için **Alanlar** bölmesinden **Satışlar** > **Önceki Yılın Satışları** ve **Satışlar** > **Bu Yılın Satışları** > **Değer** alanını seçin.

    ![Doldurulmuş yığılmış sütun grafiğinin ekran görüntüsü.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-build-visual.png)

    Artık X eksenini özelleştirebilirsiniz. Power BI, görselleştirmenizi biçimlendirmek için neredeyse sınırsız sayıda seçenek sunar. 

## <a name="customize-the-x-axis"></a>X eksenini özelleştirme
X ekseninde özelleştirebileceğiniz birçok seçenek vardır. X eksenine veri etiketi ve başlık ekleyebilir, var olanları değiştirebilirsiniz. Kategoriler için çubukların, sütunların, çizgilerin ve alanların genişliğini, boyutunu ve doldurma özelliklerini değiştirebilirsiniz. Değerler için de görüntüleme birimlerini, ondalık basamakları ve kılavuz çizgilerini düzenleyebilirsiniz. Aşağıdaki örnekte bir sütun grafiğinin özelleştirilmesi gösterilmiştir. Seçenekleri tanımanız için burada birlikte birkaç özelleştirme seçeneği ekleyeceğiz. Geri kalanları da sonrasında kendiniz keşfedebilirsiniz.

### <a name="customize-the-x-axis-labels"></a>X ekseni etiketlerini özelleştirme
X ekseni etiketleri, grafiğin sütunlarının altında görüntülenir. Etiketler şu anda açık gri renkte, küçük ve okunmaları zor. Şimdi bunu değiştirelim.

1. **Görselleştirmeler** bölmesinde **Biçim** (boya rulosu simgesi ![Boya rulosu simgesinin ekran görüntüsü](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-paintroller-icon.png)) öğesini seçin. Bunu yaptığınızda özelleştirme seçenekleri açılır.

2. X ekseni seçeneklerini genişletin.

   ![X Ekseni seçeneklerinin ekran görüntüsü.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-axis-x.png)

3. **X ekseni** kaydırıcısını **Açık** konuma getirin.

    ![Açık kaydırıcının ekran görüntüsü.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-slider-on.png)

    Bazı durumlarda X eksenini **Kapalı** duruma getirmek isteyebilirsiniz. Görselleştirme, etiket olmadan anlaşılabilir durumda olabilir veya rapor sayfası kalabalık olduğu için daha fazla veriye yer açma gereksinimi duyuyor olabilirsiniz.

4. Metin rengini, boyutunu ve yazı tipini biçimlendirin:

    - **Renk**: Siyahı seçin

    - **Metin boyutu**: *14* girin

    - **Yazı tipi ailesi**: **Arial Black** seçin

    - **İç dolgu**: *%40* girin

        ![Açılı etiketleri gösteren ekran görüntüsü](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-formatting-x.png)
    
5. X ekseni metninin açılı olarak görünmesini istemiyor olabilirsiniz. Burada birkaç seçeneğiniz vardır. 
    - Metin boyutunu 14'ten daha küçük bir değerle değiştirin.
    - Görselleştirmeyi büyütün. 
    - **Minimum kategori genişliği** değerini artırarak daha az sütun görüntüleyin ve kaydırma çubuğu ekleyin. 
    
    Burada ikinci seçeneği tercih ettik ve görselleştirmeyi daha geniş hale getirmek için yeniden boyutlandırma çubuklarından birini tuttuk. Artık metni açılı olarak veya kaydırma çubuğu ile görüntülemeye gerek duymadan 14 nokta metni görüntüleyebiliyor. 

   ![Yatay etiketlere sahip grafik ve biçimlendirme bölmesi](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-stretch.png)

### <a name="customize-the-x-axis-title"></a>X ekseni başlığını özelleştirme
X ekseni başlığı **Açık** olduğunda X ekseni etiketlerinin altında X ekseni başlığı görüntülenir. 

1. İlk olarak X ekseni başlığını **Açık** konuma getirin.  

    ![Başlık kaydırıcısı](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-title-on.png)

    Göreceğiniz ilk şey, görselleştirmenizde artık varsayılan bir X ekseni başlığı olduğudur.  Bu örnekte ad **FiscalMonth** olur.

   ![Altında başlığı bulunan grafik](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-x-title.png)

1. Başlığın metin rengini, boyutunu ve yazı tipini biçimlendirin:

    - **Başlık rengi**: Turuncu seçin

    - **Eksen başlığı**: *Mali Ay* (boşluk bırakarak) yazın

    - **Başlık metin boyutu**: *18* girin

    Özelleştirmeleri bitirdikten sonra yığılmış sütun grafiğiniz aşağıdakine benzer görünecektir:

    ![Özelleştirilmiş yığılmış sütun grafiğinin ekran görüntüsü.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-x-title-formatted.png)

1. Yaptığınız değişiklikleri kaydedin ve sonraki bölüme geçin. Yaptığınız tüm değişiklikleri geri almanız gerekirse, **X Ekseni** özelleştirme bölmesinin altındaki **Varsayılana geri dön** seçeneğini belirleyin. Ardından Y Ekseninizi özelleştireceksiniz.

## <a name="customize-the-y-axis"></a>Y eksenini özelleştirme
Y ekseninde özelleştirilebilecek birçok özellik vardır. Veri etiketi, Y ekseni başlığı ve kılavuz çizgileri ekleyip var olanları değiştirebilirsiniz. Değerler için görüntüleme birimlerini, ondalık basamakları, başlangıç ve bitiş noktalarını değiştirebilirsiniz. Kategoriler için de çubukların, sütunların, çizgilerin ve alanların genişliğini, boyutunu ve doldurma özelliklerini düzenleyebilirsiniz. 

Aşağıdaki örnekte sütun grafiğini özelleştirme işlemleri devam ettirilmektedir. Seçenekleri tanımanız için burada birlikte birkaç değişiklik yapacağız. Geri kalanları da sonrasında kendiniz keşfedebilirsiniz.

### <a name="customize-the-y-axis-labels"></a>Y ekseni etiketlerini özelleştirme
Y ekseni etiketleri varsayılan olarak sol tarafta gösterilir. Etiketler şu anda açık gri renkte, küçük ve okunmaları zor. Şimdi bunu değiştirelim.

1. Y ekseni seçeneklerini genişletin.

   ![X ekseni seçeneklerinin ekran görüntüsü.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-axis-y.png)

1. **Y Ekseni** kaydırıcısını **Açık** konuma getirin.  

    ![Açık kaydırıcının ekran görüntüsü.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-y-axis-on.png)

    Daha fazla veriye yer açmak için Y eksenini kapatmak isteyebilirsiniz.

1. Metin rengini, boyutunu ve yazı tipini biçimlendirin:

    - **Renk**: Siyahı seçin

    - **Metin boyutu**: *10* girin

    - **Görüntüleme birimleri**: **Milyon**'u seçin

    ![Y ekseni biçimlendirilmiş grafik](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-formatting-y.png)

### <a name="customize-the-y-axis-title"></a>Y ekseni başlığını özelleştirme
Y ekseni başlığı **Açık** olduğunda Y ekseni etiketlerinin yanında Y ekseni başlığı görüntülenir. Bu görselleştirme için Y ekseni başlığının görüntülenmesi görseli geliştirmediğinden, **Başlık** seçeneğini **Kapalı** olarak bırakın. Bu öğreticinin ilerleyen bölümlerinde çift eksenli bir görsele Y ekseni başlıklarını ekleyeceğiz. 

### <a name="customize-the-gridlines"></a>Kılavuz çizgilerini özelleştirme
Rengi değiştirerek ve darbeyi artırarak kılavuz çizgilerini belirginleştirin:

- **Renk**: Turuncu seçin

- **Darbe**: *2* girin

Bu özelleştirmelerin ardından sütun grafiğiniz aşağıdakine benzer şekilde görünür:

![Özelleştirilmiş Y Ekseninin bulunduğu grafiğin ekran görüntüsü.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-gridline.png)

## <a name="customizing-visualizations-with-dual-y-axes"></a>Çift Y eksenli görselleştirmeleri özelleştirme

Bazı görselleştirmelerde iki Y ekseni bulunabilir. Birleşik haritalar buna iyi bir örnektir. Çift Y eksenini biçimlendirmek için satış ve brüt kar eğilimlerini karşılaştıran bir birleşik harita oluşturacağız.  

### <a name="create-a-chart-with-two-y-axes"></a>İki Y Eksenli bir grafik oluşturun

1. Sütun grafiğini seçip *Çizgi ve yığılmış sütun* grafiği olarak değiştirin. Bu tür görseller tek bir çizgi grafik değerini ve birden çok yığılabilir sütun değerini destekler. 

    ![Çizgi ve yığılmış sütun grafiği seçeneğinin vurgulandığı Görselleştirmeler bölmesinin ekran görüntüsü.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-combo.png)
   

2. Alanlar bölmesindeki **Satış** > **Brüt Kar Önceki Yıl %** değerini **Satır Değerleri** kutusuna sürükleyin.

    ![Üç değerin de net bir şekilde gösterildiği çizgi ve yığılmış sütun grafiğin ekran görüntüsü.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-add-line.png)

    
3. Görselleştirmeyi yeniden biçimlendirerek açılı X ekseni etiketlerini kaldırın. 

   ![Birleşik harita ve Biçimlendirme bölmesi, yazı tipi boyutu 12'ye düşürülmüş](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-font-size.png)

   Power BI iki Y ekseni oluşturarak değerlerin farklı ölçeklendirilmesine olanak tanır. Sol taraftaki eksen satış doları tutarını ölçer ve sağ taraf eksen de brüt kar yüzdesini ölçer.

### <a name="format-the-second-y-axis"></a>İkinci Y eksenini biçimlendirme
Görselleştirmeye tek bir biçimlendirilmiş Y ekseniyle başladığımız için Power BI, aynı ayarlarla ikinci bir Y ekseni ekledi. Ancak bunu değiştirebiliriz. 

1. **Görselleştirmeler** bölmesinde biçim seçeneklerini görüntülemek için boya rulosu simgesini seçin.

1. Y ekseni seçeneklerini genişletin.

1. **İkincili göster** seçeneğini bulana kadar ekranı aşağı kaydırın. Bu seçeneğin **Açık** olduğundan emin olun. İkincil Y ekseni, çizgi grafiği temsil eder.

   ![İkincili göster seçeneğinin ekran görüntüsü.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-show-secondary.png)

1. (İsteğe bağlı) İki eksenin yazı tipi rengini, boyutunu ve görüntüleme birimini özelleştirin. Sütun ekseni veya çizgi ekseni için **Konum** değerini değiştirirseniz iki eksen yer değiştirir.

### <a name="add-titles-to-both-axes"></a>Her iki eksene başlık ekleme

Bu düzeyde karmaşık olan görselleştirmelerde eksen başlıklarının eklenmesi faydalıdır.  Başlıklar, iş arkadaşlarınızın görselleştirmeniz ile anlatılanları anlamasına yardımcı olur.

1. **Y Ekseni (Sütun)** ve **Y Ekseni (Satır)** için **Başlık** değerini **Açık** olarak ayarlayın.

1. Her ikisi için de **Stil** seçeneğini **Yalnızca başlığı göster** olarak ayarlayın.

   ![Başlık ve Stil seçeneklerinin ekran görüntüsü.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-show-title.png)

1. Artık birleşik haritanız başlıkları olan iki eksen gösterir.

   ![Özelleştirilmiş çift Y Ekseni olan grafiğin ekran görüntüsü.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-titles-on.png)

1. Başlıkları biçimlendirin. Bu örnekte başlıklardan birini kısalttık ve ikisinin birden yazı tipi boyutunu küçülttük. 
    - Yazı tipi boyutu: **9**
    - İlk Y ekseninin (sütun grafiği) **Eksen başlığı** kısaltıldı: Önceki yılın ve bu yılın satışları

    ![Tam başlıkları görüntülenen birleşik haritanın ekran görüntüsü.](media/power-bi-visualization-customize-x-axis-and-y-axis/power-bi-dual.png)



Daha fazla bilgi için bkz. [Power BI'da renk biçimlendirmeye ilişkin ipuçları ve püf noktaları](service-tips-and-tricks-for-color-formatting.md) ve [Görselleştirme başlıklarını, açıklamaları ve arka planları özelleştirme](power-bi-visualization-customize-title-background-and-legend.md). Yeni başlık biçimlendirme seçenekleri çok yakında kullanıma sunulacak. 

## <a name="next-steps"></a>Sonraki adımlar

- [Power BI raporlarındaki görselleştirmeler](power-bi-report-visualizations.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)
