---
title: 2. Bölüm, Bir Power BI raporuna görselleştirme ekleme
description: 2. Bölüm, Bir Power BI raporuna görselleştirme ekleme
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 08/23/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 01051ab47304713fe3cf0f9128f5cd99af58bffe
ms.sourcegitcommit: e17fc3816d6ae403414cf5357afbf6a492822ab8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/04/2018
ms.locfileid: "52830229"
---
# <a name="part-2-add-visualizations-to-a-power-bi-report"></a>2. Bölüm, Bir Power BI raporuna görselleştirme ekleme
[1. Bölüm](power-bi-report-add-visualizations-ii.md)'de alan adlarının yanında bulunan onay kutularını seçerek temel görselleştirmeler oluşturdunuz.  2. Bölüm'de sürükle bırak işlevini nasıl kullanacağınızı ve her türlü görselleştirmeyi oluşturmak ve değiştirmek için **Alanlar** ve **Görsel Öğeler** bölmelerini tam olarak nasıl kullanabileceğinizi öğreneceksiniz.

### <a name="prerequisites"></a>Önkoşullar
- [Bölüm 1](power-bi-report-add-visualizations-ii.md)
- Power BI Desktop - Power BI hizmeti veya Power BI Desktop kullanılarak, raporlara görsel öğeler eklenebilir. Bu öğretici, Power BI Desktop uygulamasını kullanır. 
- [Perakende Analizi örneği](http://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix)

## <a name="create-a-new-visualization"></a>Yeni görselleştirme oluşturma
Bu eğitim kapsamında Perakende Analizi veri kümesini derinlemesine inceleyeceğiz ve birkaç anahtar görselleştirme oluşturacağız.

### <a name="open-a-report-and-add-a-new-blank-page"></a>Bir rapor açın ve boş bir sayfa ekleyin.
1. Power BI Desktop’ta Perakende Analizi örneği .PBIX dosyasını açın. 
   ![](media/power-bi-report-add-visualizations-ii/power-bi-open-desktop.png)   

2. Tuvalin alt kısmında bulunan sarı artı simgesini seçerek yeni sayfa ekleyin.

### <a name="add-a-visualization-that-looks-at-this-years-sales-compared-to-last-year"></a>Bu yılın satışlarıyla geçen yılın satışlarının karşılaştırılmasının incelendiği bir görselleştirme ekleyin.
1. **Sales** tablosundan, **This Year Sales** > **Değer** ve **Last Year Sales** öğelerini seçin. Power BI, bir sütun grafik oluşturur.  Bu verinin ilginizi çektiğini farz ederek daha derinlemesine inceleyelim. Aylara göre satışların görünümü nasıl?  
   
   ![](media/power-bi-report-add-visualizations-ii/power-bi-barchart.png)
2. Time tablosundan **FiscalMonth** öğesini **Eksen** alanına sürükleyin.  
   ![](media/power-bi-report-add-visualizations-ii/power-bi-month.png)
3. [Görselleştirmeyi değiştirerek](power-bi-report-change-visualization-type.md) bir Alan grafiğine dönüştürün.  Aralarından seçim yapabileceğiniz pek çok görselleştirme türü bulunur. Hangi türü kullanacağınıza karar vermek için [her birinin açıklamasına, en iyi uygulama ipuçlarına ve eğitimlere](power-bi-visualization-types-for-reports-and-q-and-a.md) başvurabilirsiniz. Görsel Öğeler bölmesinden Alan grafiği simgesini ![](media/power-bi-report-add-visualizations-ii/power-bi-areachart.png) seçin.
4. Üç nokta simgesini seçip ardından **Sıralama Ölçütü: FiscalMonth** seçeneğini belirleyerek görselleştirmeyi sıralayın.
5. Görselleştirmeyi seçerek ve ana hat dairelerinden birini yakalayıp sürükleyerek [görselleştirmeyi yeniden boyutlandırın](power-bi-visualization-move-and-resize.md). Kaydırma çubuğunu ortadan kaldırmak için yeterince geniş ve bir başka görselleştirme eklememiz için alan bırakacak kadar da küçük olmasını sağlayın.
   
   ![](media/power-bi-report-add-visualizations-ii/pbi_part2_7b.png)
6. [Raporu kaydedin](../service-report-save.md).

### <a name="add-a-map-visualization-that-looks-at-sales-by-location"></a>Konuma göre satışları gösteren bir harita görselleştirmesi ekleyin.
1. **Store** tablosundan **Territory** öğesini seçin. Power BI, Territory'nin bir konum olduğunu algılayarak bir harita görselleştirmesi oluşturur.  
   ![](media/power-bi-report-add-visualizations-ii/power-bi-map.png)
2. **Total Stores** öğesini Boyut alanına sürükleyin.  
   ![](media/power-bi-report-add-visualizations-ii/power-bi-map2.png)
3. Bir açıklama ekleyin.  Veriyi mağaza adına göre görmek için **Chain** öğesini Açıklama alanına sürükleyin.  
   ![](media/power-bi-report-add-visualizations-ii/power-bi-legend.png)

## <a name="next-steps"></a>Sonraki adımlar
* [Power BI raporlarındaki görselleştirmeler](power-bi-report-visualizations.md) hakkında daha fazla bilgi.  
* Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

