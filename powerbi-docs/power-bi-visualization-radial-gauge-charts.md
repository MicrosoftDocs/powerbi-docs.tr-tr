---
title: "Power BI'daki radyal ölçer grafikleri (Eğitim)"
description: "Eğitim: Power BI'daki radyal ölçer grafikleri"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: xmja6Epqa
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/27/2017
ms.author: mihart
ms.openlocfilehash: 7299b95cb3dd1fab4edce1764c69e1b2657ef547
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="radial-gauge-charts-in-power-bi-tutorial"></a>Power BI'daki radyal ölçer grafikleri (Eğitim)
Radyal ölçerler dairesel bir yay içerir ve belirli bir hedefe/KPI'ye yönelik ilerlemeyi ölçen tek bir değer görüntüler.  Hedef veya hedef değer çizgi (iğne) ile gösterilir. Hedefe yönelik ilerleme gölgelendirme ile gösterilir.  İlerlemeyi gösteren değer ise yayın içinde kalın olarak gösterilir. Olası tüm değerler, minimumdan (en soldaki değer) başlayıp maksimumda (en sağdaki değer) sonlanacak şekilde yay boyunca eşit olarak dağılır.

Aşağıdaki örnekte, Satış ekibimizin aylık ortalama satışlarını izleyen bir araba satıcısı olduğumuzu varsayacağız. Hedefimiz olan 140 değeri siyah bir iğneyle gösterilmektedir.  Mümkün olan minimum ortalama satışı 0, maksimum ortalama satışı ise 200 olarak belirledik.  Mavi gölge, bu ay ortalama yaklaşık 120 satışa ulaştığımızı gösteriyor. Şanslıyız ki hedefimize ulaşmak için bir haftamız daha var.

![](media/power-bi-visualization-radial-gauge-charts/gauge_m.png)

## <a name="when-to-use-a-radial-gauge"></a>Radyal ölçer ne zaman kullanılır?
Radial ölçerler şunlar için harika bir seçimdir:

* bir hedefe yönelik ilerlemeyi göstermek.
* KPI gibi bir yüzde değerini göstermek.
* tek bir ölçünün durumunu göstermek.
* hızlıca taranıp anlaşılabilen bilgiler görüntülemek.

## <a name="create-a-basic-radial-gauge"></a>Basit bir radyal ölçer oluşturma
Bu yönergeler Financial Sample'a yöneliktir. Birlikte ilerleyebilmek için, bilgisayarınıza [örneği indirin](http://go.microsoft.com/fwlink/?LinkID=521962), Power BI'da oturum açın ve **Veri Al \> Dosyalar \>  Yerel Dosya > Aç** yolunu izleyin. 

Alternatif olarak, Will şu tek ölçümlü görselleri oluştururken ona eşlik edebilirsiniz: ölçerler, kartlar ve KPI'ler.

<iframe width="560" height="315" src="https://www.youtube.com/embed/xmja6EpqaO0?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

### <a name="step-1-open-the-financial-sample-excel-file"></a>1. Adım: Financial Sample Excel dosyasını açın.
1. [Örnek Financial Excel dosyasını indirin](sample-financial-download.md).
2. **Veri Al \> Dosyalar** seçeneğini belirleyip, dosyayı kaydettiğiniz konuma giderek dosyayı Power BI'da açın. **İçeri aktar**'ı seçin. Financial Sample, çalışma alanınıza bir veri kümesi olarak eklenir.
3. **Financial Sample**'ı seçerek Araştır modunda açın.

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
1. [Raporu kaydedin](service-report-save.md).
2. [Ölçer grafiğini pano kutucuğu olarak ekleyin](service-dashboard-tiles.md). 

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

## <a name="next-steps"></a>Sonraki adımlar
[Power BI'daki görselleştirme türleri](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Bir rapora görselleştirme ekleme](power-bi-report-add-visualizations-i.md)

[Panoya görselleştirme sabitleme](service-dashboard-pin-tile-from-report.md)

[Power BI - Temel Kavramlar](service-basic-concepts.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

