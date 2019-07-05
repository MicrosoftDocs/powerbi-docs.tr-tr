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
ms.openlocfilehash: c9ad87d851f52db6cd2720c9e3bd5d4bb7b189a7
ms.sourcegitcommit: 58c649ec5fd2447a0f9ca4c4d45a0e9fff2f1b6a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2019
ms.locfileid: "67408915"
---
# <a name="waterfall-charts-in-power-bi"></a>Power BI'da şelale grafikler

Şelale grafikleri, Power BI değer ekleyip çıkardıkça değişen toplamı gösterir. Bunlar, bir başlangıç değerinin (net gelir gibi) bir dizi pozitif ve negatif değişiklikten nasıl etkilendiğini anlamak için faydalıdır.

Artış ve azalmaları hızla fark edebilmeniz için sütunlar renk kodludur. Başlangıç değeri ve son değer sütunları genellikle [yatay eksende başlar](https://support.office.com/article/Create-a-waterfall-chart-in-Office-2016-for-Windows-8de1ece4-ff21-4d37-acd7-546f5527f185#BKMK_Float "start on the horizontal axis") ve ara değerler, yüzen sütun şeklinde görünür. Bu stil nedeniyle şelale grafikler köprü grafikleri olarak da adlandırılır.

<iframe width="560" height="315" src="https://www.youtube.com/embed/qKRZPBnaUXM" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

## <a name="when-to-use-a-waterfall-chart"></a>Şelale grafikler ne zaman kullanılır?

Şelale grafikler aşağıdaki durumlarda harika bir seçimdir:

* Zamanda, serilerde veya farklı kategorilerde ölçü değişikliği yaptığınızda.

* Toplam değere etki eden büyük değişiklikleri denetlemek için.

* Çeşitli gelir kaynaklarını göstererek şirketinizin yıllık kârının çizimini yapmak ve toplam kâra (veya zarara) ulaşmak için.

* Şirketinizin bir yılın başındaki ve sonundaki çalışan sayısını göstermek için.

* Her ay kazandığınız ve harcadığınız para tutarını ve hesabınızın değişen bakiyesini görselleştirmek için.

## <a name="prerequisites"></a>Önkoşullar

* Power BI hizmeti veya Power BI Desktop

* Perakende Analizi Örneği raporu

## <a name="get-the-retail-analysis-sample-report"></a>Perakende Analizi Örneği raporunu alma

Bu yönergelerde Perakende Analizi Örneği kullanılmaktadır. Bir görsel öğe oluşturmak için veri kümesinde ve raporda düzenleme izinlerine sahip olmanız gerekir. Neyse ki, Power BI örneklerinin tümü düzenlenebilir. Biri sizinle bir rapor paylaşırsa, raporda görselleştirmeler oluşturamazsınız. Örneği takip etmek için [Perakende Analizi Örneği raporunu](../sample-datasets.md) alın.

**Perakende Analizi Örneği** veri kümesini aldıktan sonra başlayabilirsiniz.

## <a name="create-a-waterfall-chart"></a>Bir şelale grafik oluşturma

Aya göre satış varyansını (tahmini satış ile gerçek satış karşılaştırması) görüntüleyen bir şelale grafik oluşturacaksınız.

1. **Çalışma Alanım**’dan **Veri kümeleri** > **Rapor oluştur**’u seçin.

    ![Veri kümeleri > Rapor oluştur ekran görüntüsü.](media/power-bi-visualization-waterfall-charts/power-bi-create-a-report.png)

1. **Alanlar** bölmesinde **Sales**  > **Total Sales Variance** alanını seçin.

   ![Sales > Total Sales Varience’ın seçili olduğu ve sonuçta elde edilen görselin gösterildiği ekran görüntüsü.](media/power-bi-visualization-waterfall-charts/power-bi-first-value.png)

1. Şelale simgesini seçerek ![Şelale simgesinin ekran görüntüsü](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-icon.png) grafiği ağaç haritasına dönüştürün.

    **Total Sales Variance** **Y Ekseni**'nde değilse bu eksene sürükleyin.

    ![Görsel öğe şablonları](media/power-bi-visualization-waterfall-charts/convertwaterfall.png)

1. **Kategori** kutusuna eklemek üzere **Time** > **FiscalMonth** alanını seçin.

    ![şelale](media/power-bi-visualization-waterfall-charts/power-bi-waterfall.png)

1. Power BI’ın şelale grafiğini kronolojik olarak sıraladığından emin olun. Grafiğin sağ üst köşesinden üç noktayı (...) seçin.

    **Artan Düzende Sırala** ve **FiscalMonth** seçeneklerinin solunda sarı bir gösterge olup olmadığını kontrol edin

    ![Sıralama ölçütü > FiscalMonth seçin](media/power-bi-visualization-waterfall-charts/power-bi-sort-by.png)

    X ekseni değerlerine bakarak **Oca**’dan **Ağu**’ya kadar düzgün sıralandığını görebilirsiniz.

    Aydan aya değişikliklere en çok katkıda bulunan öğeleri görmek için biraz daha ayrıntıya inin.

1. **Store** > **Territory** alanını **Kırılım** demetine sürükleyin.

    ![Çözümleme demetindeki Mağazayı gösterir](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-breakdown.png)

    Varsayılan olarak, Power BI aya göre artışa ve azalmaya en çok katkıda bulunan beş öğeyi ekler.

    ![Çözümleme demetindeki Mağazayı gösterir](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-breakdown-initial.png)

    Sizi yalnızca en çok katkıda bulunan iki öğe ilgilendirir.

1. **Biçim** bölmesinde **Kırılım**’ı seçin ve **En yüksek kırılım**’ı **2** olarak ayarlayın.

    ![Biçim > Kırılım](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-breakdown-maximum.png)

    Hızlı bir gözden geçirmeyle şelale grafiğinizde hem negatif hem de pozitif olarak harekete en çok katkıda bulunan bölgelerin Ohio ve Pennsylvania olduğunu görüyoruz.

    ![Şelale grafiği](media/power-bi-visualization-waterfall-charts/power-bi-waterfall-axis.png)

    Bu ilgi çekici bir bulgu. Ohio ve Pennsylvania, bu iki bölgedeki satışlar diğer bölgelere göre çok daha yüksek olduğu için mi böyle büyük bir etkiye sahip? Bunu kontrol edebilirsiniz.

1. Bu yılki satış değerini ve geçen yılki satışları bölgeye göre inceleyen bir harita oluşturun.

    ![PA ve Ohio’nun haritada yakın gösterimi](media/power-bi-visualization-waterfall-charts/power-bi-map.png)

    Harita, teorinizi destekler niteliktedir. Harita, bu iki bölgenin, geçen yıl (kabarcık boyutu) ve bu yılın en yüksek satış değerlerine sahip olduğunu göstermektedir.

## <a name="highlighting-and-cross-filtering"></a>Vurgulama ve çapraz filtreleme

[Filtreler](../power-bi-report-add-filter.md) bölmesinin kullanımı hakkında bilgi için bkz. **Düzenleme görünümünde rapora filtre ekleme**.

Bir şelale grafikte sütunların vurgulanması, rapor sayfasındaki diğer görselleştirmelerde çapraz filtre uygular (tersi de geçerlidir). Öte yandan **Toplam** sütunu vurgulamayı tetiklemez veya çapraz filtrelemeye yanıt vermez.

## <a name="next-steps"></a>Sonraki adımlar

* [Power BI raporunda görsellerin etkileşim kurma biçimini değiştirme](../service-reports-visual-interactions.md)

* [Power BI'daki görselleştirme türleri](power-bi-visualization-types-for-reports-and-q-and-a.md)
