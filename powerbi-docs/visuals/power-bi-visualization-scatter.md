---
title: Power BI’daki dağılım, kabarcık ve noktalı çizim grafikleri
description: Power BI’daki dağılım grafiği, noktalı çizim grafikleri ve kabarcık grafikleri
author: mihart
ms.reviewer: amac
featuredvideoid: PVcfPoVE3Ys
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/21/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: a03ac63caf8da96cd7e786c99c8a8dcd36f45a75
ms.sourcegitcommit: 7f27b9eb0e001034e672050735ab659b834c54a3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74311688"
---
# <a name="scatter-charts-bubble-charts-and-dot-plot-charts-in-power-bi"></a>Power BI’daki dağılım grafikleri, kabarcık grafikleri ve noktalı çizim grafikleri

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

Dağılım grafiğinde her zaman iki değer ekseni bulunur: biri yatay eksende bir sayısal veri kümesini, diğeri ise dikey eksen üzerinde bir sayısal değer kümesini gösterir. Grafik, X ve Y sayısal değerlerinin kesişim noktalarını görüntüler ve bu değerleri tekli veri noktalarına dönüştürür. Power BI bu veri noktalarını yatay eksende eşit olarak veya eşit olmayacak şekilde dağıtılabilir. Bu, grafiğin temsil ettiği verilere bağlıdır.

Will'in bir dağılım grafiği oluşturduğu bu videoyu izleyip aşağıdaki adımları kullanarak kendiniz bir dağılım grafiği oluşturun.
   > [!NOTE]
   > Bu videoda Power BI Desktop’ın eski bir sürümü kullanılmaktadır.
   > 
   > 
<iframe width="560" height="315" src="https://www.youtube.com/embed/PVcfPoVE3Ys?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

Veri noktalarının sayısını en fazla 10.000 olarak ayarlayabilirsiniz.  

## <a name="when-to-use-a-scatter-chart-bubble-chart-or-a-dot-plot-chart"></a>Dağılım grafiğinin, kabarcık grafiğinin ve noktalı çizim grafiğinin kullanım alanları

### <a name="scatter-and-bubble-charts"></a>Dağılım ve kabarcık grafikleri

Dağılım grafiği, iki sayısal değerin arasındaki ilişkiyi gösterir. Kabarcık grafiğinde veri noktaları yerine kabarcıklar kullanılır ve kabarcığın *boyutu* farklı bir üçüncü veri boyutunu temsil eder.

![Örnek kabarcık grafiği ekran görüntüsü.](media/power-bi-visualization-scatter/power-bi-bubble-chart.png)

Dağılım grafikleri aşağıdaki durumlarda harika bir seçimdir:

* İki sayısal değer arasındaki ilişkiyi göstermek için.

* İki sayı grubunu tek bir x ve y koordinat dizisi olarak çizmek için.

* Yatay eksenin ölçeğini değiştirmek istediğiniz durumlarda çizgi grafiğin yerine kullanmak için.

* Yatay ekseni logaritmik ölçeğe dönüştürmek için.

* İkili veya gruplanmış değer kümeleri içeren çalışma sayfası verilerini göstermek için.

    > [!TIP]
    > Dağılım grafiğinde eksenlerin ölçeğini ayrı ayrı ayarlayarak gruplanmış değerlerle ilgili daha fazla bilgiye yer verebilirsiniz.

* Doğrusal veya doğrusal olmayan eğilimler, gruplar ve aykırı değerler gibi büyük veri kümelerindeki desenleri göstermek için.

* Zamanı dikkate almadan çok sayıda veri noktasını karşılaştırma.  Bir dağılım grafiğine ne kadar veri eklerseniz yapabileceğiniz karşılaştırmalar da o kadar iyi olur.

Dağılım grafiklerinin sizin için yapabildiklerine ek olarak, kabarcık grafikleri de aşağıdaki durumlarda harika bir seçimdir:

* Verilerinizde her biri değer kümesi içeren üç veri dizisi varsa.

* Finansal verileri sunmak için.  Farklı kabarcık boyutları, belirli değerleri vurgulama açısından kullanışlıdır.

* Çeyrek dairelerle birlikte kullanmak için.

### <a name="dot-plot-charts"></a>Noktalı çizim grafikleri

Noktalı çizim grafiği, kabarcık grafiğine ve dağılım grafiğine benzer ancak X ekseninde kategorik veriler çizmek için kullanılır.

![Noktalı çizim grafiği ekran görüntüsü.](media/power-bi-visualization-scatter/power-bi-dot-plot.png)

X ekseni üzerinde kategorik veriler dahil etmek istiyorsanız harika bir seçimdir.

## <a name="prerequisites"></a>Önkoşullar

Bu öğreticide [Perakende Analizi örneği .PBIX dosyası](https://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix) kullanılmıştır.

1. Menü çubuğunun sol üst köşesinden **Dosya** > **Aç**’ı seçin
   
2. **Perakende Analizi örneği PBIX dosyasının** kopyasını bulun

1. **Perakende Analizi örneği PBIX dosyasını** rapor görünümünde ![Rapor görünümü simgesinin ekran görüntüsü.](media/power-bi-visualization-kpi/power-bi-report-view.png) açın.

1. Seç ![Sarı sekmenin ekran görüntüsü.](media/power-bi-visualization-kpi/power-bi-yellow-tab.png) yeni bir sayfa ekleyin.


## <a name="create-a-scatter-chart"></a>Dağılım grafiği oluşturma

1. Boş bir rapor sayfasında başlayın ve **Alanlar** bölmesinden şu alanları seçin:

    * **Satış** > **Fit Kare Başına Satış**

    * **Satış** > **Toplam Satış Varyansı %**

    * **Bölge** > **Bölge**

    ![Seçtiğiniz alanlar işaretlenmiş olarak Küme sütunu grafiği, Görsel öğeler bölmesi ve Alanlar bölmesi ekran görüntüsü.](media/power-bi-visualization-scatter/power-bi-bar-chart.png)

1. **Görselleştirme** bölmesinde ![Dağılım grafiği ekran görüntüsü simgesini](media/power-bi-visualization-scatter/power-bi-scatter-chart-icon.png) seçin. küme sütunu grafiğini bir dağılım grafiğine dönüştürmek için.

   ![Küme sütunu grafiğinin dağılım grafiğine dönüşmesi ekran görüntüsü.](media/power-bi-visualization-scatter/power-bi-scatter-new.png)

1. **District** öğesini **Ayrıntılar** bölmesinden **Açıklama**'ya sürükleyin.

    Power BI, Y ekseninde **Toplam Satış Varyansı %** verisini, X ekseninde ise **Fit Kare Başına Satış** verisi gösteren bir dağılım grafiğini görüntüler. Veri noktası renkleri bölgeleri göstermektedir:

    ![Dağılım grafiğinin ekran görüntüsü.](media/power-bi-visualization-scatter/power-bi-scatter2.png)

Şimdi üçüncü boyutu ekleyelim.

## <a name="create-a-bubble-chart"></a>Kabarcık grafiği oluşturma

1. **Alanlar** bölmesinden, **Satış** > **Bu Yılın Satışları** > **Değer** öğesini **Boyut** kutusuna sürükleyin. Veri noktaları, satış değeriyle orantılı bir şekilde hacimlere genişler.

   ![Satış Değerinin Boyut kutusuna eklenmesiyle dağılım grafiğinin kabarcık grafiğine dönüşmesi ekran görüntüsü.](media/power-bi-visualization-scatter/power-bi-scatter-chart-size.png)

1. Bir kabarcığın üzerine gelin. Kabarcığın boyutu **This Year Sales** değerini yansıtır.

    ![araç ipuçlarını görüntüleme](media/power-bi-visualization-scatter/pbi-scatter-chart-hover.png)

1. Kabarcık grafiğinizde gösterilecek veri noktalarının sayısını ayarlamak için **Görsel Öğeler** bölmesinin **Biçim** bölümünde **Genel**’i genişletin ve **Veri Hacmi**'ni ayarlayın.

    ![Biçim simgesi, Genel açılan öğesi ve Veri Hacmi seçeneği çağrılan Görsel Öğeler bölmesi ekran görüntüsü.](media/power-bi-visualization-scatter/pbi-scatter-data-volume.png)

    Veri hacmi üst sınırını 10.000’e kadar herhangi bir sayıya ayarlayabilirsiniz. Daha yüksek sayıya ulaştıkça iyi performanstan emin olmak için öncelikle test etmeniz önerilir.

    > [!NOTE]
    > Daha fazla veri noktası, yükleme süresinin uzamasına neden olabilir. Raporları, ölçeğin üst uçlarında sınır koyarak yayımlamayı seçerseniz, raporlarınızı web ve mobilde test ettiğinizden emin olun. Grafiğin performansının kullanıcılarınızın beklentileriyle eşleştiğini doğrulayabilirsiniz.

1. Görselleştirme renklerini, etiketlerini, başlıklarını, arka planını ve daha fazlasını biçimlendirmeye devam edin. [Erişilebilirliği artırmak](../desktop-accessibility.md) için her satıra işaretçi şekilleri eklemeyi deneyin. İşaretçi şeklini seçmek için **Şekiller**’i genişletin ve bir **İşaretçi şekli**’ni seçin ve bir şekil belirleyin.

    ![İşaretçi şekli seçeneği çağrılan Şekiller açılan öğesi ekran görüntüsü.](media/power-bi-visualization-scatter/pbi-scatter-marker.png)

    İşaret şeklini baklava, üçgen veya kare olarak değiştirebilirsiniz. Her çizgi için farklı bir işaretçi şekli kullanılması, rapor kullanıcılarının çizgileri (veya alanları) daha kolay bir şekilde ayırt edebilmesini sağlar.

1. Görselleştirmenize ek bilgi eklemek için ![Analiz bölmesi simgesinin ekran görüntüsü.](media/power-bi-visualization-scatter/power-bi-analytics.png) Analiz bölmesini açın.  
    - Ortanca çizgisi ekleyin. **Ortanca çizgisi** > **Ekle**'yi seçin. Power BI varsayılan olarak *fit kare başına Satışlar* için bir ortanca çizgisi ekler. 10 veri noktası olduğunu görebildiğimiz ve ortancanın her tarafta beş veri noktası ile oluşturulacağını bildiğimiz için bu çok faydalı değildir. Bunun yerine **Ölçü** seçeneğini *Toplam satış varyansı yüzdesi* olarak değiştirin.  

        ![Ortanca çizgisi eklenen balon grafiğinin ekran görüntüsü.](media/power-bi-visualization-scatter/power-bi-analytics-median.png)

    - X ekseni ölçüsünün hangi noktalarının Y ekseni ölçüsüne kıyasla daha yüksek bir değere sahip olduğunu göstermek için simetri gölgelendirmesi ekleyin. Bunun tam tersi de geçerlidir. Analiz bölmesinde simetri gölgelendirmesini açtığınızda Power BI, geçerli ekseninizin üst ve alt sınırlarına göre dağılım grafiğinizin arka planını simetrik olarak gösterir. Bu, özellikle x ve y ekseniniz için farklı bir eksen aralığınız olduğunda, bir veri noktasının hangi eksen ölçüsünü tercih ettiğini belirlemenin çok hızlı bir yoludur.

        a. **Toplam satış varyansı yüzdesi** alanını **Geçen yılın brüt kar yüzdesi** olarak değiştirin

        ![Ortanca çizgisi eklenen balon grafiğinin ekran görüntüsü.](media/power-bi-visualization-scatter/power-bi-format-symmetry.png)

        b. Analiz bölmesinden **Simetri gölgelendirme** ekleyin. Gölgelendirmeden, Hosiery’nin (pembe gölgeli alandaki yeşil balon) mağaza kare ölçüsü başına satışları yerine brüt karı tercih eden tek kategori olduğunu görebiliriz. 

        ![Simetri gölgelendirme eklenen balon grafiğinin ekran görüntüsü.](media/power-bi-visualization-scatter/power-bi-symmetry.png)

    - Verilerinize yönelik ilginç içgörüleri bulmak için Analiz bölmesini keşfetmeye devam edin. 

        ![Simetri gölgelendirme eklenen balon grafiğinin ekran görüntüsü.](media/power-bi-visualization-scatter/power-bi-analytics-example.png)

## <a name="create-a-dot-plot-chart"></a>Noktalı çizim grafiği oluşturma

Noktalı çizim grafiği oluşturmak için sayısal **X ekseni** alanını kategorik bir alanla değiştirin.

**X Ekseni** bölmesinden **Fit kare başına satış** girişini kaldırıp **Bölge** > **Bölge Yöneticisi** ile değiştirin.

![Yeni noktalı çizim grafiği ekran görüntüsü.](media/power-bi-visualization-scatter/power-bi-dot-plot-squares.png)

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme

### <a name="your-scatter-chart-has-only-one-data-point"></a>Dağılım grafiğinizde tek bir veri noktası var

Dağılım grafiğinizde X ve Y eksenindeki tüm değerleri toplayan yalnızca bir veri noktası mı var?  Ya da tek bir yatay veya dikey çizgi üzerindeki tüm değerleri mi topluyor?

![Bir veri noktası olan dağılım grafiği ekran görüntüsü.](media/power-bi-visualization-scatter/pbi-scatter-tshoot1.png)

**Ayrıntılar** kutusuna bir alan ekleyerek Power BI'a değerleri nasıl gruplandırması gerektiğini anlatın. Alanın, çizmek istediğiniz her nokta için benzersiz olması gerekir. Basit bir satır numarası ve kimlik alanı yeterli olur.

![Ayrıntılar kutusuna RowNum eklenmiş ekran görüntüsü.](media/power-bi-visualization-scatter/pbi-scatter-tshoot.png)

Verilerinizde bu bilgiler yoksa X ve Y değerlerinizden her noktada benzersiz verileri tutacak bir alan oluşturabilirsiniz:

![Ayrıntılar kutusuna TempTime eklenmiş ekran görüntüsü.](media/power-bi-visualization-scatter/pbi-scatter-tshoot2.png)

Yeni bir alan oluşturmak için [Power BI Desktop Sorgu Düzenleyicisi'ni kullanarak veri kümenize bir Dizin Sütunu ekleyin](../desktop-add-custom-column.md). Ardından bu sütunu görselleştirmenizin **Ayrıntılar** bölümüne ekleyin.

## <a name="next-steps"></a>Sonraki adımlar

* [Power BI dağılım grafiklerinde yüksek yoğunluklu örnekleme](desktop-high-density-scatter-charts.md)

* [Power BI'daki görselleştirme türleri](power-bi-visualization-types-for-reports-and-q-and-a.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)
