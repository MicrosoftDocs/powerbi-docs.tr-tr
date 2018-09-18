---
title: Power BI'da dağılım grafikleri
description: Power BI'da Dağılım Grafikleri
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: PVcfPoVE3Ys
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/28/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 13bc26eaecdcc9b3a00f22f75f6f9a5322d823f6
ms.sourcegitcommit: 67336b077668ab332e04fa670b0e9afd0a0c6489
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44748902"
---
# <a name="scatter-charts-and-bubble-charts-in-power-bi"></a>Power BI'daki dağılım grafikleri ve kabarcık grafikleri
Dağılım grafiğinde her zaman, biri yatay eksende bir sayısal veri kümesi gösteren, diğeri ise dikey eksen üzerinde bir sayısal değer kümesi gösteren iki değer ekseni bulunur. Grafik, X ve Y sayısal değerlerinin kesişim noktalarını görüntüler ve bu değerleri tekli veri noktalarına dönüştürür. Bu veri noktaları, verilere bağlı olarak yatay eksende eşit veya eşit olmayan şekilde dağıtılabilir.

Kabarcık grafiğinde veri noktaları yerine kabarcıklar kullanılır ve kabarcık *boyutu* verilerin farklı bir boyutunu gösterir.

![](media/power-bi-visualization-scatter/power-bi-bubble-chart.png)

Veri noktalarının sayısını ayarlayabilirsiniz  

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

## <a name="create-a-scatter-chart"></a>Dağılım grafiği oluşturma
Will'in bir dağılım grafiği oluşturduğu bu videoyu izleyip aşağıdaki adımları kullanarak kendiniz bir dağılım grafiği oluşturun.

<iframe width="560" height="315" src="https://www.youtube.com/embed/PVcfPoVE3Ys?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>


Bu yönergelerde Perakende Analizi Örneği kullanılmaktadır. Yönergeleri takip etmek için Power BI hizmeti (app.powerbi.com) veya Power BI Desktop [örneğini indirin](../sample-datasets.md).   

1. [Boş rapor sayfası](../power-bi-report-add-page.md) oluşturmak için sarı artı simgesini seçin.
 
2. Alanlar bölmesinden aşağıdaki alanları seçin:
   - **Satış** > **Fit Kare Başına Satış**
   - **Satış** > **Toplam Satış Varyansı %**
   - **Bölge** > **Bölge**

     ![](media/power-bi-visualization-scatter/power-bi-bar-chart.png)

     Power BI hizmetini kullanıyorsanız raporu [Düzenleme Görünümü](../service-interact-with-a-report-in-editing-view.md)'nde açtığınızdan emin olmanız gerekir.

3. Sonucu dağılım grafiğine dönüştürün. Görsel Öğeler bölmesinde Dağılım grafiği simgesini seçin.

   ![](media/power-bi-visualization-scatter/pbi_scatter_chart_icon.png).

4. **District** öğesini **Ayrıntılar** bölmesinden **Açıklama**'ya sürükleyin. Burada, Y ekseninde **Toplam Satış Varyansı %** verisini, X ekseninde ise **Fit Kare Başına Satış** verisi gösteren bir dağılım grafiği görüntülenir. Veri noktası renkleri bölgeleri göstermektedir:

    ![](media/power-bi-visualization-scatter/power-bi-scatter.png)

Şimdi üçüncü boyutu ekleyelim.

## <a name="create-a-bubble-chart"></a>Kabarcık grafiği oluşturma

1. **Alanlar** bölmesinden, **Satış** > **Bu Yılın Satışları** > **Değer** öğesini **Boyut** alanına sürükleyin. Veri noktaları, satış değeriyle orantılı bir şekilde hacimlere genişler.
   
   ![](media/power-bi-visualization-scatter/power-bi-bubble.png)

2. Bir kabarcığın üzerine gelin. Kabarcığın boyutu **This Year Sales** değerini yansıtır.
   
    ![](media/power-bi-visualization-scatter/pbi_scatter_chart_hover.png)

3. Kabarcık grafiğinizde gösterilecek veri noktalarının sayısını ayarlamak için **Görsel Öğeler** bölmesinin **Biçim** bölümünde **Genel** kartını genişletin ve **Veri Hacmi**'ni ayarlayın. Veri hacmi üst sınırını 10.000’e kadar herhangi bir sayıya ayarlayabilirsiniz. Daha yüksek sayıya ulaştıkça iyi performanstan emin olmak için öncelikle test etmeniz önerilir. 

    ![Veri Hacmi](./media/power-bi-visualization-scatter/pbi_scatter_data_volume.png) 

   > [!NOTE]
   > Veri noktası sayısı arttığında yükleme süresi de uzayacağından, raporları ölçeğin uç sınırlarıyla yayımlamayı seçerseniz performansın kullanıcı beklentilerini karşılamasını sağlamak için raporlarınızı hem web üzerinde hem de mobil cihazlarda test ettiğinizden emin olun. Daha fazla sayıda veri noktası için, iyi performans sağlamak amacıyla sonuçları farklı form faktörleri üzerinde test etmeniz gerektiğini unutmayın.

4. [Görselleştirme renklerini, etiketlerini, başlıklarını, arka planını ve daha pek çok özelliğini biçimlendirebilirsiniz](service-getting-started-with-color-formatting-and-axis-properties.md). [Erişilebilirliği artırmak](../desktop-accessibility.md) için her satıra işaretçi şekilleri eklemeyi deneyin. Her çizgi için farklı bir İşaretçi şekli kullanılması, rapor kullanıcılarının çizgileri (veya alanları) daha kolay bir şekilde ayırt edebilmesini sağlar. İşaretçi şeklini seçmek için **Şekiller** kartını genişletin ve bir işaretçi şekli belirleyin.

      ![İşaretçi şekli](./media/power-bi-visualization-scatter/pbi_scatter_marker.png)

   İşaretçi şeklini baklava, üçgen veya kare olarak değiştirebilirsiniz:

   ![Kare işaretçi](./media/power-bi-visualization-scatter/pbi_scatter_chart_hover_square.png)


## <a name="considerations-and-troubleshooting"></a>Önemli Noktalar ve Sorun Giderme

### <a name="your-scatter-chart-has-only-one-data-point"></a>**Dağılım grafiğinizde tek bir veri noktası var**
Dağılım grafiğinizde X ve Y eksenindeki tüm değerleri toplayan yalnızca bir veri noktası mı var?  Ya da tek bir yatay veya dikey çizgi üzerindeki tüm değerleri mi topluyor?

![](media/power-bi-visualization-scatter/pbi_scatter_tshoot1.png)

**Ayrıntılar** bölümüne bir alan ekleyerek Power BI'a değerleri nasıl gruplandırması gerektiğini anlatın. Alanın, çizmek istediğiniz her nokta için benzersiz olması gerekir.  
Basit bir satır numarası ve kimlik alanı kullanabilirsiniz:

![](media/power-bi-visualization-scatter/pbi_scatter_tshoot.png)

Verilerinizde bu bilgiler yoksa X ve Y değerlerinizden her noktada benzersiz verileri tutacak bir alan oluşturabilirsiniz:

![](media/power-bi-visualization-scatter/pbi_scatter_tshoot2.png)

Yeni bir alan oluşturmak için [Power BI Desktop Sorgu Düzenleyicisi'ni kullanarak veri kümenize bir Dizin Sütunu ekleyin](../desktop-add-custom-column.md).  Ardından bu sütunu görselleştirmenizin **Ayrıntılar** bölümüne ekleyin.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI'daki görselleştirme türleri](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Ücretsiz deneme için kaydolun](https://powerbi.microsoft.com/get-started/)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

