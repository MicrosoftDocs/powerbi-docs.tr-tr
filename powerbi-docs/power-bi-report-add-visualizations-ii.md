---
title: "2. Bölüm: Bir Power BI raporuna görselleştirme ekleme (Eğitim)"
description: "Eğitim: 2. Bölüm: Bir Power BI raporuna görselleştirme ekleme"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/23/2018
ms.author: mihart
ms.openlocfilehash: 40d6ee1f1448856b444201532caffd4b8c904c85
ms.sourcegitcommit: c3be4de522874fd73fe6854333b379b85619b907
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/24/2018
---
# <a name="part-2-add-visualizations-to-a-power-bi-report-tutorial"></a>2. Bölüm: Bir Power BI raporuna görselleştirme ekleme (Eğitim)
[1. Bölüm](power-bi-report-add-visualizations-ii.md)'de alan adlarının yanında bulunan onay kutularını seçerek temel görselleştirmeler oluşturdunuz.  2. Bölüm'de sürükle bırak işlevini nasıl kullanacağınızı ve her türlü görselleştirmeyi oluşturmak ve değiştirmek için **Alanlar** ve **Görsel Öğeler** bölmelerini tam olarak nasıl kullanabileceğinizi öğreneceksiniz.

### <a name="prerequisites"></a>Önkoşullar
- [Bölüm 1](power-bi-report-add-visualizations-ii.md)
- Power BI hizmeti - Power BI hizmeti veya Power BI Desktop kullanılarak, raporlara görsel öğeler eklenebilir. Bu öğretici, Power BI hizmetini kullanır. 
- Perakende Analizi örneği

## <a name="create-a-new-visualization"></a>Yeni görselleştirme oluşturma
Bu eğitim kapsamında Perakende Analizi veri kümesini derinlemesine inceleyeceğiz ve birkaç anahtar görselleştirme oluşturacağız.

### <a name="open-a-report-and-add-a-new-blank-page"></a>Bir rapor açın ve boş bir sayfa ekleyin.
1. Perakende Analizi örneğini kaydettiğiniz çalışma alanını açın. **Retail Analysis Sample**'ı seçerek raporu Okuma Görünümü'nde açın.
   
   ![](media/power-bi-report-add-visualizations-ii/power-bi-open-report.png)
2. **Raporu düzenle**'yi seçerek raporu Düzenleme Görünümü'nde açın.
   
   ![](media/power-bi-report-add-visualizations-ii/editreport1.png)
3. Tuvalin alt kısmında bulunan sarı artı simgesini seçerek [Yeni sayfa ekle](power-bi-report-add-page.md)'yin.
   
   ![](media/power-bi-report-add-visualizations-ii/pbi_addreportpage.png)

### <a name="add-a-visualization-that-looks-at-this-years-sales-compared-to-last-year"></a>Bu yılın satışlarıyla geçen yılın satışlarının karşılaştırılmasının incelendiği bir görselleştirme ekleyin.
1. **Sales** tablosundan, **This Year Sales** > **Değer** ve **Last Year Sales** öğelerini seçin. Power BI, bir sütun grafik oluşturur.  Bu verinin ilginizi çektiğini farz ederek daha derinlemesine inceleyelim. Aylara göre satışların görünümü nasıl?  
   
   ![](media/power-bi-report-add-visualizations-ii/pbi_part2_4bnew.png)
2. Time tablosundan **Month** öğesini **Eksen** alanına sürükleyin.  
   ![](media/power-bi-report-add-visualizations-ii/pbi_part2_5newnew.png)
3. [Görselleştirmeyi değiştirerek](power-bi-report-change-visualization-type.md) bir Alan grafiğine dönüştürün.  Aralarından seçim yapabileceğiniz pek çok görselleştirme türü bulunur. Hangi türü kullanacağınıza karar vermek için [her birinin açıklamasına, en iyi uygulama ipuçlarına ve eğitimlere](power-bi-visualization-types-for-reports-and-q-and-a.md) başvurabilirsiniz. Görsel Öğeler bölmesinden Alan grafiği simgesini seçin.
4. Üç nokta simgesini seçip ardından **Sıralama Ölçütü: Month** seçeneğini belirleyerek görselleştirmeyi sıralayın.
5. Görselleştirmeyi seçerek ve ana hat dairelerinden birini yakalayıp sürükleyerek [görselleştirmeyi yeniden boyutlandırın](power-bi-visualization-move-and-resize.md). Kaydırma çubuğunu ortadan kaldırmak için yeterince geniş ve bir başka görselleştirme eklememiz için alan bırakacak kadar da küçük olmasını sağlayın.
   
   ![](media/power-bi-report-add-visualizations-ii/pbi_part2_7b.png)
6. [Raporu kaydedin](service-report-save.md).

### <a name="add-a-map-visualization-that-looks-at-sales-by-location"></a>Konuma göre satışları gösteren bir harita görselleştirmesi ekleyin.
1. **Store** tablosundan **Territory** öğesini seçin. Power BI, Territory'nin bir konum olduğunu algılayarak bir harita görselleştirmesi oluşturur.  
   ![](media/power-bi-report-add-visualizations-ii/pbi_part2_8newnew.png)
2. **Total Stores** öğesini Boyut alanına sürükleyin.  
   ![](media/power-bi-report-add-visualizations-ii/power-bi-add-visual-to-a-reportnew.png)
3. Bir açıklama ekleyin.  Veriyi mağaza adına göre görmek için **Chain** öğesini Açıklama alanına sürükleyin.  
   ![](media/power-bi-report-add-visualizations-ii/power-bi-add-visual-to-a-report-3new.png)

## <a name="next-steps"></a>Sonraki adımlar
* Alanlar bölmesi ile ilgili daha fazla bilgi için bkz. [Rapor düzenleyicisi: Tura katılın](service-the-report-editor-take-a-tour.md).   
* Görselleştirmelerinizi nasıl filtreleyeceğinizi ve vurgulayacağınızı öğrenmek için bkz. [Power BI raporlarındaki filtreler ve vurgulama](power-bi-reports-filters-and-highlighting.md).  
* [Power BI raporlarındaki görselleştirmeler](power-bi-report-visualizations.md) hakkında daha fazla bilgi.  
* Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

