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
ms.date: 12/23/2017
ms.author: mihart
ms.openlocfilehash: 44c248d1a99a10c69b3fb7c78e68320fdc5cd2b2
ms.sourcegitcommit: 259d7689bcb1683d4d63a245a9b02becea072139
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/17/2018
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
Will'in bir dağılım grafiği oluşturduğu bu videoyu izleyip aşağıdaki adımları kullanarak kendiniz bir dağılım grafiği oluşturun.

<iframe width="560" height="315" src="https://www.youtube.com/embed/PVcfPoVE3Ys?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>


Bu yönergelerde Perakende Analizi Örneği kullanılmaktadır. Yönergeleri takip etmek için Power BI hizmeti (app.powerbi.com) veya Power BI Desktop [örneğini indirin](sample-datasets.md).   

1. [Boş rapor sayfası](power-bi-report-add-page.md) ile başlayın ve **Sales** \> **Sales Per Sq Ft** ile **Sales** > **Total Sales Variance %** alanlarını seçin. Power BI hizmetini kullanıyorsanız raporu [Düzenleme Görünümü](service-interact-with-a-report-in-editing-view.md)'nde açtığınızdan emin olmanız gerekir.
 
2. Alanlar bölmesinden **District > District** seçeneğini belirleyin.
   
    ![](media/power-bi-visualization-scatter/power-bi-bar-chart.png)
4. Sonucu dağılım grafiğine dönüştürün. Görsel Öğeler bölmesinde Dağılım grafiği simgesini seçin.
   ![](media/power-bi-visualization-scatter/pbi_scatter_chart_icon.png).
5. **District** öğesini **Ayrıntılar** bölmesinden **Açıklama**'ya sürükleyin.
   
    ![](media/power-bi-visualization-scatter/power-bi-scatter.png)

Şimdi elimizde Y ekseninde Total Sales Variance % verisini, X ekseninde ise Sales Per Square Feet verisini gösteren bir dağılım grafiğimiz var.  Veri noktası renkleri bölgeleri göstermektedir.  Şimdi üçüncü boyutu ekleyelim.

## <a name="create-a-bubble-chart"></a>Kabarcık grafiği oluşturma
1. Alanlar bölmesinden **Sales** > **This Year Sales** > **Değer** öğesini **Boyut** alanına sürükleyin. 
   
   ![](media/power-bi-visualization-scatter/power-bi-bubble.png)
2. Bir kabarcığın üzerine gelin.  Kabarcığın boyutu **This Year Sales** değerini yansıtır.
   
    ![](media/power-bi-visualization-scatter/pbi_scatter_chart_hover.png)
3. İsteğe bağlı olarak [görselleştirme renklerini, etiketlerini, başlıklarını, arka planını ve diğer öğeleri biçimlendirebilirsiniz](service-getting-started-with-color-formatting-and-axis-properties.md).

## <a name="accessibility"></a>Erişilebilirlik

*İşaretçi şekillerini* kullanarak dağılım grafiğinizi veya kabarcık grafiğinizi engelli kişiler için daha kolay erişilebilir hale getirebilirsiniz. 

İşaretçi şeklini seçmek için **Görselleştirmeler** bölmesindeki **Biçim** bölümünü seçin, **Şekiller** bölümünü genişletin, ardından bir işaretçi şekli seçin.

![İşaretçi şekli](media/power-bi-visualization-scatter/pbi_scatter_marker.png)

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

