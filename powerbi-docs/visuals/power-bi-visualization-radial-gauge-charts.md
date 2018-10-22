---
title: Power BI'da radyal ölçer grafikleri
description: Power BI'da Radyal Ölçer grafikleri
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: xmja6Epqa
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 09/21/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 71cde810f98a81ab5670b3ab04bc1cd502277c1c
ms.sourcegitcommit: ce8332a71d4d205a1f005b703da4a390d79c98b6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2018
ms.locfileid: "47416878"
---
# <a name="radial-gauge-charts-in-power-bi"></a>Power BI'da radyal ölçer grafikleri
Radyal ölçerler dairesel bir yay içerir ve belirli bir hedefe/KPI'ye yönelik ilerlemeyi ölçen tek bir değer görüntüler.  Hedef veya hedef değer çizgi (iğne) ile gösterilir. Hedefe yönelik ilerleme gölgelendirme ile gösterilir.  İlerlemeyi gösteren değer ise yayın içinde kalın olarak gösterilir. Olası tüm değerler, minimumdan (en soldaki değer) başlayıp maksimumda (en sağdaki değer) sonlanacak şekilde yay boyunca eşit olarak dağılır.

Aşağıdaki örnekte, Satış ekibimizin aylık ortalama satışlarını izleyen bir araba satıcısı olduğumuzu varsayacağız. Hedefimiz olan 140 değeri siyah bir iğneyle gösterilmektedir.  Mümkün olan minimum ortalama satışı 0, maksimum ortalama satışı ise 200 olarak belirledik.  Mavi gölge, bu ay ortalama yaklaşık 120 satışa ulaştığımızı gösteriyor. Şanslıyız ki hedefimize ulaşmak için bir haftamız daha var.

![](media/power-bi-visualization-radial-gauge-charts/gauge_m.png)

## <a name="when-to-use-a-radial-gauge"></a>Radyal ölçer ne zaman kullanılır?
Radial ölçerler şunlar için harika bir seçimdir:

* bir hedefe yönelik ilerlemeyi göstermek.
* KPI gibi bir yüzde değerini göstermek.
* tek bir ölçünün durumunu göstermek.
* hızlıca taranıp anlaşılabilen bilgiler görüntülemek.

### <a name="prerequisites"></a>Önkoşullar
 - Power BI hizmeti veya Power BI Desktop
 - Financial Sample adlı Excel çalışma kitabı: [Örneği doğrudan indirin](http://go.microsoft.com/fwlink/?LinkID=521962).

## <a name="create-a-basic-radial-gauge"></a>Basit bir radyal ölçer oluşturma
Bu yönergeler Power BI hizmeti için geçerlidir. Birlikte ilerlemek için Power BI hizmetinde oturum açtıktan sonra Financial Sample adlı Excel dosyasını açın.  

Alternatif olarak, Will şu tek ölçümlü görselleri oluştururken ona eşlik edebilirsiniz: ölçerler, kartlar ve KPI'ler.

<iframe width="560" height="315" src="https://www.youtube.com/embed/xmja6EpqaO0?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

### <a name="step-1-open-the-financial-sample-excel-file"></a>1. Adım: Financial Sample adlı Excel dosyasını açın.
1. Henüz indirmediyseniz [Financial Sample adlı örnek Excel dosyasını indirin](../sample-financial-download.md). Dosyayı kaydettiğiniz yeri unutmayın.

2. **Veri Al\> Dosyalar** seçeneğini belirleyip, dosyayı kaydettiğiniz konuma giderek dosyayı ***Power BI hizmetinde*** açın. **İçeri aktar**'ı seçin. Financial Sample, çalışma alanınıza bir veri kümesi olarak eklenir.

3. **Veri kümesi** içerik listesinden **Financial Sample**'ı seçerek bu veri kümesini Araştırma modunda açın.

    ![](media/power-bi-visualization-radial-gauge-charts/power-bi-dataset.png)

### <a name="step-2-create-a-gauge-to-track-gross-sales"></a>2. Adım: Brüt Satışı izlemeye yönelik bir ölçer oluşturma
1. **Alanlar** bölmesinde, **Gross Sales** seçeneğini belirleyin.
   
   ![](media/power-bi-visualization-radial-gauge-charts/grosssalesvalue_new.png)
2. Toplama işlemini **Ortalama** olarak değiştirin.
   
   ![](media/power-bi-visualization-radial-gauge-charts/changetoaverage_new.png)
3. Sütun Grafiğini ölçer olarak değiştirmek için ölçer simgesini ![](media/power-bi-visualization-radial-gauge-charts/gaugeicon_new.png) seçin.
   
   Varsayılan olarak, Power BI, geçerli değerin (bu örnekte, Ortalama Gross Sales) ölçerin ortasındaki değer olduğunun varsayıldığı bir Ölçer grafiği oluşturur. Ortalama Brüt Satış 182.760 ABD doları olduğundan, başlangıç değeri (Minimum) is 0 olarak, bitiş değeri ise (Maksimum) geçerli değerin iki katı olarak ayarlanır.
   
   ![](media/power-bi-visualization-radial-gauge-charts/gauge_no_target.png)

### <a name="step-3-set-a-target-value"></a>3. Adım: Hedef değer belirleme
1. **COGS**'yi **Hedef değer** kutusuna sürükleyin.
2. Toplama işlemini **Ortalama** olarak değiştirin.
   Power BI **$145.48K** olan hedef değerimizi gösteren bir iğne ekler. Hedefimize ulaştığımıza dikkat edin.
   
   ![](media/power-bi-visualization-radial-gauge-charts/gaugeinprogress_new.png)
   
   > [!NOTE]
   > Elle de bir hedef değer girebilirsiniz.  Aşağıdaki "Minimum, Maksimum ve Hedef değerleri belirlemek için biçimlendirme seçeneklerini kullanma" bölümüne bakın.
   > 
   > 

### <a name="step-4-set-a-maximum-value"></a>4. Adım: Maksimum değer belirleme
2. Adımda, Power BI, minimum (başlangıç) ve maksimum (bitiş) değerlerini otomatik olarak belirlemek için Değer alanını kullanmıştır.  Peki ya maksimum değeri kendiniz belirlemek isterseniz?  Mümkün olan maksimum değer olarak geçerli değerin iki katı yerine veri kümenizdeki en yüksek Brüt Satış değerini belirlemek istediğinizi varsayalım. 

1. **Alanlar** listesindeki **Gross Sales** alanını **Maksimum Değer** kutusuna sürükleyin.
2. Toplama işlemini **Maksimum** olarak değiştirin.
   
   ![](media/power-bi-visualization-radial-gauge-charts/setmaximum_new.png)
   
   Ölçer, yeni bir bitiş değeriyle (Brüt satıştaki 1,21 milyon değeri) yeniden çizilir.
   
   ![](media/power-bi-visualization-radial-gauge-charts/power-bi-final-gauge.png)

### <a name="step-5-save-your-report"></a>5. Adım: Raporunuzu kaydetme
1. [Raporu kaydedin](../service-report-save.md).
2. [Ölçer grafiğini pano kutucuğu olarak ekleyin](../service-dashboard-pin-tile-from-report.md). 

## <a name="use-formatting-options-to-manually-set-minimum-maximum-and-target-values"></a>Minimum, Maksimum ve Hedef değerleri belirlemek için biçimlendirme seçeneklerini kullanma
1. **Max of Gross Sales** alanını **Maksimum değer** kutusundan kaldırın.
2. Boya rulosu simgesini seçerek, biçimlendirme bölmesini açın.
   
   ![](media/power-bi-visualization-radial-gauge-charts/power-bi-roller.png)
3. **Ölçer ekseni**'ni genişletin ve **Minimum** ve **Maksimum** değerleri girin.
   
    ![](media/power-bi-visualization-radial-gauge-charts/power-bi-gauge-axis.png)
4. **COGS**'nin yanındaki onay işaretini kaldırarak geçerli hedef değeri silin.
   
    ![](media/power-bi-visualization-radial-gauge-charts/pbi_remove_target.png)
5. **Ölçer ekseni**'nin altında **Hedef** alanı göründüğünde, buraya bir değer girin.
   
    ![](media/power-bi-visualization-radial-gauge-charts/power-bi-gauge-target.png)
6. İsteğe bağlı olarak, ölçer grafiğinizi biçimlendirmeye devam edebilirsiniz.

## <a name="next-step"></a>Sonraki adım

[Power BI’daki ölçerler](power-bi-visualization-kpi.md)

[Power BI'daki görselleştirme türleri](power-bi-visualization-types-for-reports-and-q-and-a.md)