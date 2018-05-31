---
title: Power BI'da şelale grafikler
description: Power BI'da şelale grafikler
services: powerbi
documentationcenter: ''
author: mihart
manager: kfile
backup: ''
editor: ''
tags: ''
featuredvideoid: maTzOJSRB3g
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/20/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 101680bd353237af61a885155acd2fcd66a35404
ms.sourcegitcommit: 493f160d04ed411ff4741c599adc63ba1f65230f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33812622"
---
# <a name="waterfall-charts-in-power-bi"></a>Power BI'da şelale grafikler
Şelale grafikler, değerler eklenirken veya çıkarılırken değişen toplamı gösterir. Bir başlangıç değerinin (örneğin, net gelir) bir dizi pozitif ve negatif değişiklikten nasıl etkilendiğini anlamak için faydalıdır.

Artış ve azalışları hızlıca görebilmeniz için sütunlar renk kodludur. Başlangıç değeri ve son değer sütunları genellikle [yatay eksende başlar](https://support.office.com/article/Create-a-waterfall-chart-in-Office-2016-for-Windows-8de1ece4-ff21-4d37-acd7-546f5527f185#BKMK_Float "start on the horizontal axis") ve ara değerler, yüzen sütun şeklinde görünür. Bu "görünüm" nedeniyle şelale grafikler köprü grafikleri olarak da adlandırılır.

<iframe width="560" height="315" src="https://www.youtube.com/embed/qKRZPBnaUXM" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

## <a name="when-to-use-a-waterfall-chart"></a>Şelale grafikler ne zaman kullanılır?
Şelale grafikler aşağıdaki durumlarda harika bir seçimdir:

* zaman serilerinde veya farklı kategorilerde ölçü değişikliği yaptığınızda
* toplam değere etki eden büyük değişiklikleri denetlemek için
* çeşitli gelir kaynaklarını göstererek şirketinizin yıllık kârının çizimini yapmak ve toplam kâra (veya zarara) ulaşmak için.
* şirketinizin bir yılın başındaki ve sonundaki çalışan sayısını göstermek için
* her ay kazandığınız ve harcadığınız para tutarını ve hesabınızın değişen bakiyesini görselleştirmek için. 

## <a name="create-a-waterfall-chart"></a>Bir şelale grafik oluşturma
Aya göre satış varyansını (tahmini satış ile gerçek satış karşılaştırması) görüntüleyen bir şelale grafik oluşturacağız. Birlikte ilerlemek için Power BI'da oturum açın ve **Veril Al \> Örnekler \> Perakende Analizi Örneği**'ni seçin. 

1. **Veri Kümeleri** sekmesini seçin ve yeni "Retail Analysis Sample" veri kümesine gidin.  Veri kümesini rapor düzenleme görünümünde açmak için **Rapor oluştur** simgesini seçin. 
   
    ![](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-report.png)
2. **Alanlar** bölmesinde, **Sales \> Total Sales Variance** seçeneğini belirleyin. **Total Sales Variance** **Y Ekseni**'nde değilse bu eksene sürükleyin.
3. Grafiği bir **Şelale**'ye dönüştürün. 
   
    ![](media/power-bi-visualization-waterfall-charts/convertwaterfall.png)
4. **Kategori** kutusuna eklemek üzere **Time** \> **FiscalMonth** alanını seçin. 
   
    ![](media/power-bi-visualization-waterfall-charts/power-bi-waterfall.png)
5. Şelale grafiği kronolojik olarak sıralayın. Grafiğin sağ üst köşesinden üç nokta (...) simgesini seçin ve **FiscalMonth** seçeneğini belirleyin.
   
    ![](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-sort.png)
   
    ![](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-sorted.png)
6. Aydan aya değişikliklere en çok katkıda bulunan öğeleri görmek için biraz daha ayrıntıya inin. **Store** > **Territory** alanını **Kırılım** demetine sürükleyin.
   
    ![](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-breakdown.png)
7. Varsayılan olarak, Power BI aya göre artış ve azalışa en çok katkıda bulunan 5 öğeyi ekler. Ancak biz yalnızca en çok katkıda bulunan 2 öğeyle ilgileniyoruz.  Biçimlendirme bölmesinde **Kırılım**'ı seçin ve **En yüksek çözümlemeler** ayarını 2 olarak belirleyin.
   
    ![](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-breakdown-maximum.png)
   
    Hızlı bir gözden geçirmeyle şelale grafiğimizde negatif ve pozitif olarak harekete en çok katkıda bulunan bölgelerin Ohio ve Pennsylvania olduğunu görüyoruz. 
   
    ![](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-axis.png)
8. Bu ilgi çekici bir bulgu. Ohio ve Pennsylvania, bu 2 bölgedeki satışlar diğer bölgelere göre çok daha yüksek olduğu için mi böyle büyük bir etkiye sahip?  Bunu kontrol edebiliriz. Bölgeye göre satışları inceleyen bir harita oluşturun.  
   
    ![](media/power-bi-visualization-waterfall-charts/power-bi-map.png)
   
    Haritamız teorimizi destekler niteliktedir.  Harita, bu 2 bölgenin, geçen yıl (kabarcık boyutu) ve bu yılın en yüksek satış değerlerine sahip olduğunu göstermektedir.

## <a name="highlighting-and-cross-filtering"></a>Vurgulama ve çapraz filtreleme
Filtreler bölmesini kullanma hakkında bilgi için bkz. [Bir rapora filtre ekleme](power-bi-report-add-filter.md).

Bir şelale grafikte sütunların vurgulanması, rapor sayfasındaki diğer görselleştirmelerde çapraz filtre uygular. (Vurgulamayı değiştirerek farklı sonuçlar elde edebilirsiniz.) Ancak, Total sütunu vurgulamayı tetiklemez veya çapraz filtrelemeye yanıt vermez.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI'daki raporlar](service-reports.md)

[Power BI'daki görselleştirme türleri](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Power BI raporlarındaki görselleştirmeler](power-bi-report-visualizations.md)

[Power BI - Temel Kavramlar](service-basic-concepts.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

