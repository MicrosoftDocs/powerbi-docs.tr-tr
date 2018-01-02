---
title: "Power BI'daki dağılım grafikleri (Eğitim)"
description: "Eğitim: Power BI'daki dağılım grafikleri"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: PVcfPoVE3Ys
qualityfocus: identified
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/27/2017
ms.author: mihart
ms.openlocfilehash: c1801db4135d6d97a940e593de37ca2886194b53
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2017
---
# <a name="scatter-charts-and-bubble-charts-in-power-bi-tutorial"></a>Power BI'daki dağılım grafikleri ve kabarcık grafikleri (Eğitim)
Dağılım grafiğinde her zaman, biri yatay eksende bir sayısal veri kümesi gösteren, diğeri ise dikey eksen üzerinde bir sayısal değer kümesi gösteren iki değer ekseni bulunur. Grafik, X ve Y sayısal değerlerinin kesişim noktalarını görüntüler ve bu değerleri tekli veri noktalarına dönüştürür. Bu veri noktaları, verilere bağlı olarak yatay eksende eşit veya eşit olmayan şekilde dağıtılabilir.

Kabarcık grafiğinde veri noktaları yerine kabarcıklar kullanılır ve kabarcık *boyutu* verilerin farklı bir boyutunu gösterir.

![](media/power-bi-visualization-scatter/power-bi-bubble-chart.png)

## <a name="when-to-use-a-scatter-chart-or-bubble-chart"></a>Dağılım grafiğinin ve kabarcık grafiğinin kullanım alanları
### <a name="scatter-charts-are-a-great-choice"></a>Dağılım grafikleri aşağıdaki durumlarda harika bir seçimdir:
* 2 (dağılım) veya 3 (kabarcık) **sayısal** değer arasındaki ilişkiyi göstermek için.
* iki sayı grubunu xy koordinatı üzerinde bir dizi olarak çizmek için.
* yatay eksenin ölçeğini değiştirmek istediğiniz durumlarda çizgi grafiğin yerine    
* yatay ekseni logaritmik ölçeğe dönüştürmek için.
* ikili veya gruplanmış değer kümeleri içeren çalışma sayfası verilerini göstermek için. Dağılım grafiğinde eksenlerin ölçeğini ayrı ayrı ayarlayarak gruplanmış değerlerle ilgili daha fazla bilgiye yer verebilirsiniz.
* doğrusal veya doğrusal olmayan eğilimler, gruplar ve aykırı değerler gibi büyük veri kümelerindeki desenleri göstermek için.
* zamanı dikkate almadan büyük değerli veri noktalarını karşılaştırmak için. Dağılım grafiğine ne kadar çok veri eklerseniz o kadar iyi karşılaştırmalar yapabilirsiniz.

### <a name="bubble-charts-are-a-great-choice"></a>Kabarcık grafikler aşağıdaki durumlarda harika bir seçimdir:
* verilerinizde her biri değer kümesi içeren 3 veri dizisi varsa.
* finansal verileri sunmak için.  Farklı kabarcık boyutları, belirli değerleri vurgulama açısından kullanışlıdır.
* çeyrek dairelerle birlikte kullanmak için.

## <a name="create-a-scatter-chart"></a>Dağılım grafiği oluşturma
<iframe width="560" height="315" src="https://www.youtube.com/embed/PVcfPoVE3Ys?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

1. Perakende Analizi Örneği'ni [Düzenleme Görünümü](service-interact-with-a-report-in-editing-view.md)'nde açın ve [yeni bir rapor sayfası ekleyin](power-bi-report-add-page.md).
2. Alanlar bölmesinden **Sales** > **Sales Per Sq Ft** ve **Sales** > **Total Sales Variance %** alanlarını seçin.
3. Alanlar bölmesinden **District > District** seçeneğini belirleyin.
   
    ![](media/power-bi-visualization-scatter/pbi_scatter_chart_pre_convert.png)
4. Sonucu dağılım grafiğine dönüştürün. Görsel Öğeler bölmesinde Dağılım grafiği simgesini seçin.
   ![](media/power-bi-visualization-scatter/pbi_scatter_chart_icon.png).
5. **District** öğesini **Ayrıntılar** bölmesinden **Açıklama**'ya sürükleyin.
   
    ![](media/power-bi-visualization-scatter/pbi_scatter_chart_new.png)

Şimdi elimizde Y ekseninde Total Sales Variance % verisini, X ekseninde ise Sales Per Square Feet verisini gösteren bir dağılım grafiğimiz var.  Veri noktası renkleri bölgeleri göstermektedir.  Şimdi üçüncü boyutu ekleyelim.

## <a name="create-a-bubble-chart"></a>Kabarcık grafiği oluşturma
1. Alanlar bölmesinden **Sales** > **This Year Sales** > **Değer** öğesini **Boyut** alanına sürükleyin. 
   
   ![](media/power-bi-visualization-scatter/pbi_scatter_chart_size.png)
2. Bir kabarcığın üzerine gelin.  Kabarcığın boyutu **This Year Sales** değerini yansıtır.
   
    ![](media/power-bi-visualization-scatter/pbi_scatter_chart_hover.png)
3. İsteğe bağlı olarak [görselleştirme renklerini, etiketlerini, başlıklarını, arka planını ve diğer öğeleri biçimlendirebilirsiniz](service-getting-started-with-color-formatting-and-axis-properties.md).

## <a name="considerations-and-troubleshooting"></a>Önemli Noktalar ve Sorun Giderme
### <a name="your-scatter-chart-has-only-one-data-point"></a>**Dağılım grafiğinizde tek bir veri noktası var**
Dağılım grafiğinizde X ve Y eksenindeki tüm değerleri toplayan yalnızca bir veri noktası mı var?  Ya da tek bir yatay veya dikey çizgi üzerindeki tüm değerleri mi topluyor?

![](media/power-bi-visualization-scatter/pbi_scatter_tshoot1.png)

**Ayrıntılar** bölümüne bir alan ekleyerek Power BI'a değerleri nasıl gruplandırması gerektiğini anlatın. Alanın, çizmek istediğiniz her nokta için benzersiz olması gerekir.  
Basit bir satır numarası ve kimlik alanı kullanabilirsiniz:

![](media/power-bi-visualization-scatter/pbi_scatter_tshoot.png)

Verilerinizde bu bilgiler yoksa X ve Y değerlerinizden her noktada benzersiz verileri tutacak bir alan oluşturabilirsiniz:

![](media/power-bi-visualization-scatter/pbi_scatter_tshoot2.png)

Yeni bir alan oluşturmak için [Power BI Desktop Sorgu Düzenleyicisi'ni kullanarak veri kümenize bir Dizin Sütunu ekleyin](desktop-add-custom-column.md).  Ardından bu sütunu görselleştirmenizin **Ayrıntılar** bölümüne ekleyin.

## <a name="next-steps"></a>Sonraki adımlar
 [Power BI'daki görselleştirme türleri](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Ücretsiz deneyin!](https://powerbi.com/)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

