---
title: 2\. Bölüm, Bir Power BI raporuna görselleştirme ekleme
description: 2\. Bölüm, Bir Power BI raporuna görselleştirme ekleme
author: mihart
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 10/28/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 132c795724b6f3744e0648ac1f3229c5e6538a97
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "75758434"
---
# <a name="add-visuals-to-a-power-bi-report-part-2"></a>Power BI raporuna görsel ekleme (2. Bölüm)

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

[1. Bölüm](power-bi-report-add-visualizations-i.md)'de alan adlarının yanında bulunan onay kutularını seçerek temel görselleştirmeler oluşturdunuz.  2\. Bölüm'de sürükle bırak işlevini nasıl kullanacağınızı ve her türlü görselleştirmeyi oluşturmak ve değiştirmek için **Alanlar** ve **Görsel Öğeler** bölmelerini tam olarak nasıl kullanabileceğinizi öğreneceksiniz.


## <a name="create-a-new-visualization"></a>Yeni görselleştirme oluşturma
Bu öğreticide Perakende Analizi veri kümesini derinlemesine inceleyeceğiz ve birkaç temel görselleştirme oluşturacağız.

## <a name="prerequisites"></a>Önkoşullar

Bu öğreticide [Perakende analizi örneği PBIX dosyası](https://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix) kullanılmıştır.

1. Power BI Desktop menü çubuğunun sol üst kısmından **Dosya** > **Aç**’ı seçin
   
2. **Perakende Analizi örneği PBIX dosyasının** kopyasını bulun

1. **Perakende Analizi örneği PBIX dosyasını** rapor görünümünde ![Rapor görünümü simgesinin ekran görüntüsü.](media/power-bi-visualization-kpi/power-bi-report-view.png) açın.

1. Select ![Sarı sekmenin ekran görüntüsü.](media/power-bi-visualization-kpi/power-bi-yellow-tab.png) yeni bir sayfa ekleyin.

## <a name="add-visualizations-to-the-report"></a>Rapora görselleştirme ekleme

**Alanlar** bölmesindeki alanlardan birini seçerek bir görselleştirme oluşturun. Oluşturulan görselleştirme türü, seçilen alanın türüne bağlıdır. Power BI, sonuçları göstermek için kullanılacak görselleştirmeyi belirlemek için veri türünü kullanır. Görselleştirmeler bölmesinden farklı bir simge seçerek kullanılan görselleştirmeyi değiştirebilirsiniz. Tüm görselleştirmelerin verilerinizi göstermeyeceğini aklınızda bulundurun. Örneğin, coğrafi veriler bir huni grafiği veya çizgi grafik kullanılarak iyi görüntülenmez. 


### <a name="add-an-area-chart-that-looks-at-this-years-sales-compared-to-last-year"></a>Bu yılın satışlarıyla geçen yılın satışlarının karşılaştırılmasının incelendiği bir alan grafiği ekleyin

1. **Sales** tablosundan, **This Year Sales** > **Değer** ve **Last Year Sales** öğelerini seçin. Power BI, bir sütun grafik oluşturur.  Bu grafik ilginizi çektiği için daha derinlemesine incelemek istiyorsunuz. Aylara göre satışların görünümü nasıl?  
   
   ![Sütun grafiğini gösteren ekran görüntüsü](media/power-bi-report-add-visualizations-ii/power-bi-start.png)

2. Time tablosundan **FiscalMonth** öğesini **Eksen** alanına sürükleyin.  
   ![Eksen olarak FiscalMonth ile sütun grafiğini gösteren ekran görüntüsü](media/power-bi-report-add-visualizations-ii/power-bi-fiscalmonth.png)

3. [Görselleştirmeyi değiştirerek](power-bi-report-change-visualization-type.md) bir alan grafiğine dönüştürün.  Aralarından seçim yapabileceğiniz pek çok görselleştirme türü bulunur. Hangi türü kullanacağınıza karar vermek için [her birinin açıklamasına, en iyi uygulama ipuçlarına ve öğreticilere](power-bi-visualization-types-for-reports-and-q-and-a.md) başvurabilirsiniz. Görselleştirmeler bölmesinden alan grafiği simgesini ![Görselleştirmeler bölmesindeki Alan grafiği simgesi](media/power-bi-report-add-visualizations-ii/power-bi-area-chart.png) seçin.

4. **Diğer eylemler**’i (...) ve **Sıralama ölçütü** >  **FiscalMonth** öğesini seçerek görselleştirmeyi sıralayın.

5. Görselleştirmeyi seçerek ve ana hat dairelerinden birini yakalayıp sürükleyerek [görselleştirmeyi yeniden boyutlandırın](power-bi-visualization-move-and-resize.md). Kaydırma çubuğunu ortadan kaldırmak için yeterince geniş ve bir başka görselleştirme eklememiz için alan bırakacak kadar da küçük olmasını sağlayın.
   
   ![alan grafiği görselinin ekran görüntüsü](media/power-bi-report-add-visualizations-ii/pbi_part2_7b.png)
6. [Raporu kaydetme](../service-report-save.md).

### <a name="add-a-map-visualization-that-looks-at-sales-by-location"></a>Konuma göre satışları gösteren bir harita görselleştirmesi ekleyin.

1. **Store** tablosundan **Territory** öğesini seçin. **Total Stores** öğesini Boyut alanına sürükleyin. Power BI, Territory'nin bir konum olduğunu algılayarak bir harita görselleştirmesi oluşturur.  
   ![Alan grafiği](media/power-bi-report-add-visualizations-ii/power-bi-map1.png)

2. Bir açıklama ekleyin.  Verileri mağaza adına göre görmek için **Mağaza** > **Zincir** öğesini Gösterge alanına sürükleyin.  
   ![alanlar listesindeki Zincirden Gösterge demetindeki Zincire işaret eden oka sahip rapor tuvali](media/power-bi-report-add-visualizations-ii/power-bi-chain.png)

## <a name="next-steps"></a>Sonraki adımlar
* [Power BI raporlarındaki görselleştirmeler](power-bi-report-visualizations.md) hakkında daha fazla bilgi.  
* Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)

