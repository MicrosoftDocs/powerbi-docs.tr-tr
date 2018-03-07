---
title: "Basit Alan grafiği (Eğitim)"
description: "Eğitim: Basit Alan grafiği."
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
ms.date: 01/20/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: c4a7a90a8647b4a5d2c76cefbba5041a6e31607d
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/24/2018
---
# <a name="basic-area-chart-tutorial"></a>Basit Alan grafiği (Eğitim)
Basit alan grafiği (katmanlı alan grafiği olarak da bilinir) çizgi grafiğini temel alır. Eksen ve çizgi arasındaki alan, hacmi gösteren renklerle doldurulur. 

Alan grafikleri, zaman içindeki değişimin büyüklüğünü vurgular ve bir eğilime ilişkin toplam değere dikkat çekmek için kullanılabilir. Örneğin, zaman içindeki kârı gösteren veriler, bir alan grafiğinde toplam kârı vurgulayacak şekilde gösterilebilir.

![](media/power-bi-visualization-basic-area-chart/powerbi-area-chartnew.png)

## <a name="when-to-use-a-basic-area-chart"></a>Basit alan grafikleri ne zaman kullanılır?
Basit alan grafikleri aşağıdaki durumlarda harika bir seçimdir:

* zaman serilerindeki hacim eğilimlerini görmek ve karşılaştırmak için 
* fiziksel olarak hesaplanabilen bir kümeyi temsil eden ayrı seriler için

### <a name="prerequisites"></a>Önkoşullar
 - Power BI hizmeti
 - Perakende Analizi örneği

Birlikte ilerlemek için Power BI'da oturum açıp **Veri Al \> Örnekler \> Perakende Analizi Örneği > Bağlan**'ı seçtikten sonra **Panoya git** seçeneğini belirleyin. 

## <a name="create-a-basic-area-chart"></a>Basit alan grafiği oluşturma
 

1. "Retail Analysis Sample" panosunda, **Total Stores** kutucuğunu seçerek "Retail Analysis Sample" raporunu açın.
2. **Raporu düzenle**'yi seçerek raporu Düzenleme Görünümü'nde açın.
3. Raporun alt kısmında bulunan sarı artı simgesini (+) seçerek yeni bir rapor sayfası ekleyin.
4. İçinde bulunulan yılın ve geçen yılın satışlarını aya göre görüntüleyen bir alan grafiği oluşturun.
   
   a. ALANLAR bölmesinde **Sales \> Last Year Sales** ve **This Year Sales > Değer** seçeneğini belirleyin.

   ![](media/power-bi-visualization-basic-area-chart/power-bi-bar-chart.png)

   b.  GÖRSEL ÖĞELER bölmesinden Alan grafiği simgesini seçerek grafiği, basit bir alan grafiğine dönüştürün.

   ![](media/power-bi-visualization-basic-area-chart/convertchart.png)
   
   c.  **Eksen** kutusuna eklemek üzere **Time \> Month** seçeneğini belirleyin.   
   ![](media/power-bi-visualization-basic-area-chart/powerbi-area-chartnew.png)
   
   d.  Grafiği aya göre görüntülemek için, üç nokta (görselin sağ üst köşesinde) simgesini seçin ve **Sıralama Ölçütü: Month** seçeneğini belirleyin.

## <a name="highlighting-and-cross-filtering"></a>Vurgulama ve çapraz filtreleme
FİLTRELER bölmesinin kullanımı hakkında bilgi için bkz. [Bir rapora filtre ekleme](power-bi-report-add-filter.md).

Grafiğinizdeki belirli bir alanı vurgulamak için ilgili alanı veya üst kenarlığını seçin.  Diğer görselleştirme türlerinin aksine, sayfada başka görselleştirmeler varken basit alan grafiklerini vurguladığınızda rapor sayfasındaki diğer görselleştirmeler için çapraz filtre uygulanmaz. Ancak alan grafikleri, rapor sayfasındaki diğer görselleştirmeler tarafından tetiklenen çapraz filtrelemelerden etkilenir. Daha fazla bilgi edinmek için bkz. [Raporlardaki görsel etkileşimler](service-reports-visual-interactions.md)

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme
* Basit alan grafikleri, katmanlı alanlardaki kapatma nedeniyle değer karşılaştırmaları için kullanışlı değildir. Power BI, alanlardaki çakışmaları göstermek için saydamlıktan yararlanır. Ancak, bu özellik yalnızca iki veya üç farklı alanda düzgün bir şekilde çalışır. Eğilimi üçten fazla ölçüyle karşılaştırmak için çizgi grafikleri kullanmayı deneyin. Hacmi üçten fazla ölçüyle karşılaştırmak için ise ağaç haritası kullanmayı deneyin.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI'daki raporlar](service-reports.md)  
[Power BI raporlarındaki görselleştirmeler](power-bi-report-visualizations.md)  
[Power BI - Temel Kavramlar](service-basic-concepts.md)  
Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

