---
title: Power BI'da şelale grafikler
description: Power BI'da şelale grafikler
author: msftrien
ms.reviewer: mihart
featuredvideoid: maTzOJSRB3g
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 12/5/2019
ms.author: rien
LocalizationGroup: Visualizations
ms.openlocfilehash: ce3c52774326bd9fc66fecde7496fefb1cf6888c
ms.sourcegitcommit: 5ccab484cf3532ae3a16acd5fc954b7947bd543a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/06/2020
ms.locfileid: "93412131"
---
# <a name="waterfall-charts-in-power-bi"></a>Power BI'da şelale grafikler

[!INCLUDE[consumer-appliesto-nyyn](../includes/consumer-appliesto-nyyn.md)]

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

Şelale grafikleri, Power BI değer ekleyip çıkardıkça değişen toplamı gösterir. Bunlar, bir başlangıç değerinin (net gelir gibi) bir dizi pozitif ve negatif değişiklikten nasıl etkilendiğini anlamak için faydalıdır.

Artış ve azalmaları hızla fark edebilmeniz için sütunlar renk kodludur. Başlangıç değeri ve son değer sütunları genellikle [yatay eksende başlar](https://support.office.com/article/Create-a-waterfall-chart-in-Office-2016-for-Windows-8de1ece4-ff21-4d37-acd7-546f5527f185#BKMK_Float "yatay eksende başlat") ve ara değerler de yüzen sütunlar olarak görünür. Bu stil nedeniyle şelale grafikler köprü grafikleri olarak da adlandırılır.

## <a name="when-to-use-a-waterfall-chart"></a>Şelale grafikler ne zaman kullanılır?

Şelale grafikler aşağıdaki durumlarda harika bir seçimdir:

* Zamanda, serilerde veya farklı kategorilerde ölçü değişikliği yaptığınızda.

* Toplam değere etki eden büyük değişiklikleri denetlemek için.

* Çeşitli gelir kaynaklarını göstererek şirketinizin yıllık kârının çizimini yapmak ve toplam kâra (veya zarara) ulaşmak için.

* Şirketinizin bir yılın başındaki ve sonundaki çalışan sayısını göstermek için.

* Her ay kazandığınız ve harcadığınız para tutarını ve hesabınızın değişen bakiyesini görselleştirmek için.

## <a name="prerequisite"></a>Önkoşul

Bu öğreticide [Perakende Analizi örneği .PBIX dosyası](https://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix) kullanılmıştır.

1. Menü çubuğunun sol üst köşesinden **Dosya** > **Aç** ’ı seçin
   
2. **Perakende Analizi örneği PBIX dosyasının** kopyasını bulun

1. **Perakende Analizi örneği PBIX dosyasını** rapor görünümünde ![Rapor görünümü simgesinin ekran görüntüsü.](media/power-bi-visualization-kpi/power-bi-report-view.png) açın.

1. Seç ![Sarı sekmenin ekran görüntüsü.](media/power-bi-visualization-kpi/power-bi-yellow-tab.png) yeni bir sayfa ekleyin.

> [!NOTE]
> Raporunuzu bir Power BI iş arkadaşınızla paylaşmak için her ikinizin de bireysel Power BI Pro lisanslarınızın olması veya raporun Premium kapasitede depolanması gerekir.    

## <a name="create-a-waterfall-chart"></a>Bir şelale grafik oluşturma

Aya göre satış varyansını (tahmini satış ile gerçek satış karşılaştırması) görüntüleyen bir şelale grafik oluşturacaksınız.

### <a name="build-the-waterfall-chart"></a>Şelale grafiği oluşturma

1. **Alanlar** bölmesinde **Sales**  > **Total Sales Variance** alanını seçin.

   ![Sales > Total Sales Variance’ın seçili olduğu ve sonuçta elde edilen görselin gösterildiği ekran görüntüsü.](media/power-bi-visualization-waterfall-charts/power-bi-bar.png)

1. Şelale simgesini seçerek ![Şelale simgesinin ekran görüntüsü](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-icon.png)

    ![Görsel öğe şablonları](media/power-bi-visualization-waterfall-charts/convert-waterfall.png)

1. **Kategori** kutusuna eklemek üzere **Time** > **FiscalMonth** alanını seçin.

    ![şelale](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-month.png)

### <a name="sort-the-waterfall-chart"></a>Şelale grafiğini sıralama

1. Power BI’ın şelale grafiğini aya göre kronolojik olarak sıraladığından emin olun. Grafiğin sağ üst köşesinden **Diğer seçenekler** (...) düğmesini seçin.

    Bu örnek için **Sıralama ölçütü** 'nü ve **FiscalMonth** öğesini seçin. Seçiminizin yanındaki sarı gösterge, belirttiğiniz seçeneğin ne zaman uygulandığını gösterir.

    ![Sıralama ölçütü > FiscalMonth seçin](media/power-bi-visualization-waterfall-charts/power-bi-sort-by-fiscalmonth.png)
    
    Ayları kronolojik düzende görüntülemek için **Artan düzende sırala** 'yı seçin. Önceki adımda olduğu gibi **Artan düzende sırala** seçeneğinin solunda sarı bir gösterge olup olmadığını kontrol edin. Bu, belirlediğiniz seçeneğin uygulandığını gösterir.

    ![Sıralama ölçütü > Artan düzende sırala’yı seçin](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-ascending.png)

    

    Grafiğinizin FiscalMonth için Ocak'tan Ağustos'a kadar sıralandığına dikkat edin.  

### <a name="explore-the-waterfall-chart"></a>Şelale grafiğini keşfetme

Aydan aya değişikliklere en çok katkıda bulunan öğeleri görmek için biraz daha ayrıntıya inin.

1.  **Depolama** > **Bölge** ’yi seçtiğinizde **Bölge** , **Döküm** demetine eklenir.

    ![Ekran görüntüsü, Döküm alanına Bölge ekleme işlemini gösterir.](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-breakdown.png)

    Power BI görselleştirmeye başka veriler eklemek için **Döküm** 'deki değeri kullanır. Her mali ay için artışa ve azalmaya en çok katkıda bulunan beş öğeyi ekler. Diğer bir deyişle şimdi Şubat ayının tek veri noktası yerine altı veri noktası vardır.  

    ![Çözümleme demetindeki Mağazayı gösterir](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-breakdown-default.png)

    Sizi yalnızca en çok katkıda bulunan iki öğenin ilgilendirdiğini varsayalım.

1. **Biçim** bölmesinde **Kırılım** ’ı seçin ve **En yüksek kırılım** ’ı **2** olarak ayarlayın.

    ![Biçim > Kırılım](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-breakdown-two.png)

    Hızlı bir gözden geçirmeyle şelale grafiğinizde hem negatif hem de pozitif olarak harekete en çok katkıda bulunan bölgelerin Ohio ve Pennsylvania olduğunu görüyoruz.

    ![Şelale grafiği](media/power-bi-visualization-waterfall-charts/power-bi-axis-waterfall.png)

## <a name="next-steps"></a>Sonraki adımlar

* [Power BI raporunda görsellerin etkileşim kurma biçimini değiştirme](../create-reports/service-reports-visual-interactions.md)

* [Power BI'daki görselleştirme türleri](power-bi-visualization-types-for-reports-and-q-and-a.md)

