---
title: Power BI'da şelale grafikler
description: Power BI'da şelale grafikler
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: maTzOJSRB3g
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/24/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 3ab200194d89eb15892dc4f452079eb56df8a608
ms.sourcegitcommit: e2de2e8b8e78240c306fe6cca820e5f6ff188944
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/23/2019
ms.locfileid: "71191403"
---
# <a name="waterfall-charts-in-power-bi"></a>Power BI'da şelale grafikler

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

Şelale grafikleri, Power BI değer ekleyip çıkardıkça değişen toplamı gösterir. Bunlar, bir başlangıç değerinin (net gelir gibi) bir dizi pozitif ve negatif değişiklikten nasıl etkilendiğini anlamak için faydalıdır.

Artış ve azalmaları hızla fark edebilmeniz için sütunlar renk kodludur. Başlangıç değeri ve son değer sütunları genellikle [yatay eksende başlar](https://support.office.com/article/Create-a-waterfall-chart-in-Office-2016-for-Windows-8de1ece4-ff21-4d37-acd7-546f5527f185#BKMK_Float "start on the horizontal axis") ve ara değerler, yüzen sütun şeklinde görünür. Bu stil nedeniyle şelale grafikler köprü grafikleri olarak da adlandırılır.

   > [!NOTE]
   > Bu videoda Power BI Desktop’ın eski bir sürümü kullanılmaktadır.
   > 
   > 

<iframe width="560" height="315" src="https://www.youtube.com/embed/qKRZPBnaUXM" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

## <a name="when-to-use-a-waterfall-chart"></a>Şelale grafikler ne zaman kullanılır?

Şelale grafikler aşağıdaki durumlarda harika bir seçimdir:

* Zamanda, serilerde veya farklı kategorilerde ölçü değişikliği yaptığınızda.

* Toplam değere etki eden büyük değişiklikleri denetlemek için.

* Çeşitli gelir kaynaklarını göstererek şirketinizin yıllık kârının çizimini yapmak ve toplam kâra (veya zarara) ulaşmak için.

* Şirketinizin bir yılın başındaki ve sonundaki çalışan sayısını göstermek için.

* Her ay kazandığınız ve harcadığınız para tutarını ve hesabınızın değişen bakiyesini görselleştirmek için.

## <a name="prerequisite"></a>Önkoşul

Bu öğreticide [Perakende Analizi örneği .PBIX dosyası](http://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix) kullanılmıştır.

1. Menü çubuğunun sol üst köşesinden **Dosya** > **Aç**’ı seçin
   
2. **Perakende Analizi örneği PBIX dosyasının** kopyasını bulun

1. **Perakende Analizi örneği PBIX dosyasını** rapor görünümünde ![Rapor görünümü simgesinin ekran görüntüsü.](media/power-bi-visualization-kpi/power-bi-report-view.png) açın.

1. Seç ![Sarı sekmenin ekran görüntüsü.](media/power-bi-visualization-kpi/power-bi-yellow-tab.png) yeni bir sayfa ekleyin.


## <a name="create-a-waterfall-chart"></a>Bir şelale grafik oluşturma

Aya göre satış varyansını (tahmini satış ile gerçek satış karşılaştırması) görüntüleyen bir şelale grafik oluşturacaksınız.

1. **Alanlar** bölmesinde **Sales**  > **Total Sales Variance** alanını seçin.

   ![Sales > Total Sales Variance’ın seçili olduğu ve sonuçta elde edilen görselin gösterildiği ekran görüntüsü.](media/power-bi-visualization-waterfall-charts/power-bi-first-value.png)

1. Şelale simgesini seçerek ![Şelale simgesinin ekran görüntüsü](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-icon.png)

    ![Görsel öğe şablonları](media/power-bi-visualization-waterfall-charts/convert-waterfall.png)

1. **Kategori** kutusuna eklemek üzere **Time** > **FiscalMonth** alanını seçin.

    ![şelale](media/power-bi-visualization-waterfall-charts/power-bi-waterfall.png)

1. Power BI’ın şelale grafiğini kronolojik olarak sıraladığından emin olun. Grafiğin sağ üst köşesinden üç noktayı (...) seçin.

    Bu örnekte **Artan düzende sırala**’yı seçeceğiz

    **Artan Düzende Sırala** seçeneğinin solunda sarı bir gösterge olup olmadığını kontrol edin. Bu, belirlediğiniz seçeneğin uygulandığını gösterir.

    ![Sıralama ölçütü > Artan düzende sırala’yı seçin](media/power-bi-visualization-waterfall-charts/power-bi-sort-by.png)

    Ardından, **Sıralama ölçütü**’ne tıklayıp **FiscalMonth** seçeneğini belirleyeceğiz. Önceki adımda olduğu gibi, seçiminizin yanındaki sarı gösterge, belirlediğiniz seçeneğin uygulandığı anlamına gelir.

    ![Sıralama ölçütü > FiscalMonth seçin](media/power-bi-visualization-waterfall-charts/power-bi-sort-by-fiscal-month.png)

    X ekseni değerlerine bakarak **Oca**’dan **Ağu**’ya kadar düzgün sıralandığını görebilirsiniz.

    Aydan aya değişikliklere en çok katkıda bulunan öğeleri görmek için biraz daha ayrıntıya inin.

1.  **Depolama** > **Bölge**’yi seçtiğinizde **Bölge**, **Döküm** demetine eklenir.

    ![Çözümleme demetindeki Mağazayı gösterir](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-breakdown.png)

    Varsayılan olarak, Power BI aya göre artışa ve azalmaya en çok katkıda bulunan beş öğeyi ekler. Aşağıdaki görüntüde görselleştirme bölmemiz daha fazla veri içerecek şekilde genişletilmiştir. 

    ![Çözümleme demetindeki Mağazayı gösterir](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-breakdown-initial.png)

    Sizi yalnızca en çok katkıda bulunan iki öğe ilgilendirir.

1. **Biçim** bölmesinde **Kırılım**’ı seçin ve **En yüksek kırılım**’ı **2** olarak ayarlayın.

    ![Biçim > Kırılım](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-breakdown-maximum.png)

    Hızlı bir gözden geçirmeyle şelale grafiğinizde hem negatif hem de pozitif olarak harekete en çok katkıda bulunan bölgelerin Ohio ve Pennsylvania olduğunu görüyoruz.

    ![Şelale grafiği](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-axis.png)

## <a name="next-steps"></a>Sonraki adımlar

* [Power BI raporunda görsellerin etkileşim kurma biçimini değiştirme](../service-reports-visual-interactions.md)

* [Power BI'daki görselleştirme türleri](power-bi-visualization-types-for-reports-and-q-and-a.md)
