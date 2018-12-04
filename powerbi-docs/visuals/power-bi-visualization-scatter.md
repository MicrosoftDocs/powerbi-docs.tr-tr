---
title: Power BI’daki dağılım, kabarcık ve noktalı çizim grafikleri
description: Power BI’daki dağılım grafiği, noktalı çizim grafikleri ve kabarcık grafikleri
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: PVcfPoVE3Ys
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 10/24/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 9b508964062146ff140bcb85b0b8b42e9bf4f68f
ms.sourcegitcommit: e17fc3816d6ae403414cf5357afbf6a492822ab8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/04/2018
ms.locfileid: "52830137"
---
# <a name="scatter-charts-bubble-charts-and-dot-plot-charts-in-power-bi"></a>Power BI’daki dağılım grafikleri, kabarcık grafikleri ve noktalı çizim grafikleri
Dağılım grafiğinde her zaman, biri yatay eksende bir sayısal veri kümesi gösteren, diğeri ise dikey eksen üzerinde bir sayısal değer kümesi gösteren iki değer ekseni bulunur. Grafik, X ve Y sayısal değerlerinin kesişim noktalarını görüntüler ve bu değerleri tekli veri noktalarına dönüştürür. Bu veri noktaları, verilere bağlı olarak yatay eksende eşit veya eşit olmayan şekilde dağıtılabilir.

Kabarcık grafiğinde veri noktaları yerine kabarcıklar kullanılır ve kabarcık *boyutu* verilerin farklı bir boyutunu gösterir.

![kabarcık grafiği oluşturma](media/power-bi-visualization-scatter/power-bi-bubble-chart.png)

Noktalı çizim grafiği, kabarcık grafiğine ve dağılım grafiğine benzer ancak onlardan farklı olarak X ekseninde sayısal veya kategorik veriler çizmenize imkan tanır. 

![kabarcık grafiği oluşturma](media/power-bi-visualization-scatter/power-bi-dot-plot.png)

Veri noktalarının sayısını en fazla 10.000 olarak ayarlayabilirsiniz.  

## <a name="when-to-use-a-scatter-chart-or-bubble-chart"></a>Dağılım grafiğinin ve kabarcık grafiğinin kullanım alanları
### <a name="scatter-charts-are-a-great-choice"></a>Dağılım grafikleri aşağıdaki durumlarda harika bir seçimdir:
* 2 (dağılım) veya 3 (kabarcık) **sayısal** değer arasındaki ilişkiyi göstermek için.
* İki sayı grubunu tek bir xy koordinat dizisi olarak çizme.
* yatay eksenin ölçeğini değiştirmek istediğiniz durumlarda çizgi grafiğin yerine    
* yatay ekseni logaritmik ölçeğe dönüştürmek için.
* ikili veya gruplanmış değer kümeleri içeren çalışma sayfası verilerini göstermek için. Dağılım grafiğinde eksenlerin ölçeğini ayrı ayrı ayarlayarak gruplanmış değerlerle ilgili daha fazla bilgiye yer verebilirsiniz.
* doğrusal veya doğrusal olmayan eğilimler, gruplar ve aykırı değerler gibi büyük veri kümelerindeki desenleri göstermek için.
* Zamanı dikkate almadan çok sayıda veri noktasını karşılaştırma.  Bir dağılım grafiğine ne kadar veri eklerseniz yapabileceğiniz karşılaştırmalar da o kadar iyi olur.

### <a name="bubble-charts-are-a-great-choice"></a>Kabarcık grafikler aşağıdaki durumlarda harika bir seçimdir:
* verilerinizde her biri değer kümesi içeren 3 veri dizisi varsa.
* finansal verileri sunmak için.  Farklı kabarcık boyutları, belirli değerleri vurgulama açısından kullanışlıdır.
* çeyrek dairelerle birlikte kullanmak için.

### <a name="dot-plot-charts-are-a-great-choice-in-place-of-a-scatter-or-bubble"></a>Noktalı çizim grafikleri şu durumlarda dağılım veya kabarcık yerine harika bir seçimdir:
* X ekseni üzerinde kategorik veriler dahil etmek istiyorsanız

## <a name="create-a-scatter-chart"></a>Dağılım grafiği oluşturma
Will'in bir dağılım grafiği oluşturduğu bu videoyu izleyip aşağıdaki adımları kullanarak kendiniz bir dağılım grafiği oluşturun.

<iframe width="560" height="315" src="https://www.youtube.com/embed/PVcfPoVE3Ys?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>


Bu yönergelerde Perakende Analizi Örneği kullanılmaktadır. Yönergeleri takip etmek için Power BI hizmeti (app.powerbi.com) veya Power BI Desktop [örneğini indirin](../sample-datasets.md).   

1. Boş bir rapor sayfası oluşturmak için, raporu Düzenleme görünümünde açın ve sarı artı simgesini seçin.
 
2. Alanlar bölmesinden aşağıdaki alanları seçin:
   - **Satış** > **Fit Kare Başına Satış**
   - **Satış** > **Toplam Satış Varyansı %**
   - **Bölge** > **Bölge**

     ![](media/power-bi-visualization-scatter/power-bi-bar-chart.png)

     Power BI hizmetini kullanıyorsanız raporu [Düzenleme Görünümü](../service-interact-with-a-report-in-editing-view.md)'nde açtığınızdan emin olmanız gerekir.

3. Sonucu dağılım grafiğine dönüştürün. Görsel Öğeler bölmesinde Dağılım grafiği simgesini seçin.

   ![](media/power-bi-visualization-scatter/power-bi-scatter-new.png).

4. **District** öğesini **Ayrıntılar** bölmesinden **Açıklama**'ya sürükleyin. Burada, Y ekseninde **Toplam Satış Varyansı %** verisini, X ekseninde ise **Fit Kare Başına Satış** verisi gösteren bir dağılım grafiği görüntülenir. Veri noktası renkleri bölgeleri göstermektedir:

    ![](media/power-bi-visualization-scatter/power-bi-scatter2.png)

Şimdi üçüncü boyutu ekleyelim.

## <a name="create-a-bubble-chart"></a>Kabarcık grafiği oluşturma

1. **Alanlar** bölmesinden, **Satış** > **Bu Yılın Satışları** > **Değer** öğesini **Boyut** alanına sürükleyin. Veri noktaları, satış değeriyle orantılı bir şekilde hacimlere genişler.
   
   ![noktalar, kabarcıklar haline gelir](media/power-bi-visualization-scatter/power-bi-scatter-chart-size.png)

2. Bir kabarcığın üzerine gelin. Kabarcığın boyutu **This Year Sales** değerini yansıtır.
   
    ![araç ipuçlarını görüntüleme](media/power-bi-visualization-scatter/pbi_scatter_chart_hover.png)

3. Kabarcık grafiğinizde gösterilecek veri noktalarının sayısını ayarlamak için **Görsel Öğeler** bölmesinin **Biçimlendirme** bölümünde **Genel** kartını genişletin ve **Veri Hacmi**'ni ayarlayın. Veri hacmi üst sınırını 10.000’e kadar herhangi bir sayıya ayarlayabilirsiniz. Daha yüksek sayıya ulaştıkça iyi performanstan emin olmak için öncelikle test etmeniz önerilir. 

    ![Veri Hacmi](media/power-bi-visualization-scatter/pbi_scatter_data_volume.png) 

   Veri noktası sayısı arttığında yükleme süresi de uzayacağından, raporları ölçeğin uç sınırlarıyla yayımlamayı seçerseniz performansın kullanıcı beklentilerini karşılamasını sağlamak için raporlarınızı hem web üzerinde hem de mobil cihazlarda test ettiğinizden emin olun. 

4. [Görselleştirme renklerini, etiketlerini, başlıklarını, arka planını ve daha pek çok özelliğini biçimlendirebilirsiniz](service-getting-started-with-color-formatting-and-axis-properties.md). [Erişilebilirliği artırmak](../desktop-accessibility.md) için her satıra işaretçi şekilleri eklemeyi deneyin. Her çizgi için farklı bir İşaretçi şekli kullanılması, rapor kullanıcılarının çizgileri (veya alanları) daha kolay bir şekilde ayırt edebilmesini sağlar. İşaretçi şeklini seçmek için **Şekiller** kartını genişletin ve bir işaretçi şekli belirleyin.

      ![İşaretçi şekli](media/power-bi-visualization-scatter/pbi_scatter_marker.png)

   İşaretçi şeklini baklava, üçgen veya kare olarak değiştirebilirsiniz:

   ![Kare işaretçi](media/power-bi-visualization-scatter/pbi_scatter_chart_hover_square.png)

## <a name="create-a-dot-plot"></a>Noktalı grafik oluşturma
Noktalı grafik oluşturmak için sayısal X ekseni alanını kategorik bir alanla değiştirin.

**X Ekseni** bölmesinden **Fit kare başına satış** girişini kaldırıp **Bölge > DM** ile değiştirin.
   
![yeni noktalı çizim](media/power-bi-visualization-scatter/power-bi-dot-plot-squares.png)


## <a name="considerations-and-troubleshooting"></a>Önemli Noktalar ve Sorun Giderme

### <a name="your-scatter-chart-has-only-one-data-point"></a>**Dağılım grafiğinizde tek bir veri noktası var**
Dağılım grafiğinizde X ve Y eksenindeki tüm değerleri toplayan yalnızca bir veri noktası mı var?  Ya da tek bir yatay veya dikey çizgi üzerindeki tüm değerleri mi topluyor?

![](media/power-bi-visualization-scatter/pbi_scatter_tshoot1.png)

**Ayrıntılar** bölümüne bir alan ekleyerek Power BI'a değerleri nasıl gruplandırması gerektiğini anlatın. Alan, çizmek istediğiniz her nokta için benzersiz olmalıdır; basit bir satır numarası veya kimlik alanı gibi.

![](media/power-bi-visualization-scatter/pbi_scatter_tshoot.png)

Verilerinizde bu bilgiler yoksa X ve Y değerlerinizden her noktada benzersiz verileri tutacak bir alan oluşturabilirsiniz:

![](media/power-bi-visualization-scatter/pbi_scatter_tshoot2.png)

Yeni bir alan oluşturmak için [Power BI Desktop Sorgu Düzenleyicisi'ni kullanarak veri kümenize bir Dizin Sütunu ekleyin](../desktop-add-custom-column.md).  Ardından bu sütunu görselleştirmenizin **Ayrıntılar** bölümüne ekleyin.

## <a name="next-steps"></a>Sonraki adımlar

[Yüksek yoğunluklu dağılım grafikleri](desktop-high-density-scatter-charts.md)

[Power BI'daki görselleştirme türleri](power-bi-visualization-types-for-reports-and-q-and-a.md)

