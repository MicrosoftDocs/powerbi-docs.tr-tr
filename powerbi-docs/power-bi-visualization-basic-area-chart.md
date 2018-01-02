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
ms.date: 09/27/2017
ms.author: mihart
ms.openlocfilehash: 42e068b11c22c32f1a6736a6ca8f9020594fb40a
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="basic-area-chart-tutorial"></a>Basit Alan grafiği (Eğitim)
Basit alan grafiği (katmanlı alan grafiği olarak da bilinir) çizgi grafiğini temel alır. Eksen ve çizgi arasındaki alan, hacmi gösteren renklerle doldurulur. 

Alan grafikleri, zaman içindeki değişimin büyüklüğünü vurgular ve bir eğilime ilişkin toplam değere dikkat çekmek için kullanılabilir. Örneğin, zaman içindeki kârı gösteren veriler, bir alan grafiğinde toplam kârı vurgulayacak şekilde gösterilebilir.

![](media/power-bi-visualization-basic-area-chart/powerbi-area-chartnew.png)

## <a name="when-to-use-a-basic-area-chart"></a>Basit alan grafikleri ne zaman kullanılır?
Basit alan grafikleri aşağıdaki durumlarda harika bir seçimdir:

* zaman serilerindeki hacim eğilimlerini görmek ve karşılaştırmak için 
* fiziksel olarak hesaplanabilen bir kümeyi temsil eden ayrı seriler için

## <a name="create-a-basic-area-chart"></a>Basit alan grafiği oluşturma
Birlikte ilerleyebilmek için, Power BI'da oturum açın ve **Veri Al \> Örnekler \> Perakende Analizi Örneği** seçeneğini belirleyin. 

1. "Retail Analysis Sample" panosunda, **Total Stores** kutucuğunu seçerek "Retail Analysis Sample" raporunu açın.
2. **Raporu düzenle**'yi seçerek raporu Düzenleme Görünümü'nde açın.
3. Yeni bir rapor sayfası ekleyin.
4. İçinde bulunulan yılın ve geçen yılın satışlarını aya göre görüntüleyen bir alan grafiği oluşturun.
   
   a.  **Alanlar bölmesinde**, **Sales \> Last Year Sales** ve **This Year Sales > Value** seçeneklerini belirleyin.
   
   b.  Grafiği bir basit alan grafiğine dönüştürün.    
   ![](media/power-bi-visualization-basic-area-chart/convertchart.png)
   
   c.  **Eksen** kutusuna eklemek üzere **Time \> Month** seçeneğini belirleyin.   
   ![](media/power-bi-visualization-basic-area-chart/powerbi-area-chartnew.png)
   
   d.  Grafiği aya göre görüntülemek için, üç nokta (görselin sağ üst köşesinde) simgesini seçin ve **Sıralama Ölçütü: Month** seçeneğini belirleyin.

## <a name="highlighting-and-cross-filtering"></a>Vurgulama ve çapraz filtreleme
Filtreler bölmesini kullanma hakkında bilgi için bkz. [Bir rapora filtre ekleme](power-bi-report-add-filter.md).

Bir alanı seçmek için söz konusu alanın içine veya üstünde bulunan çizgiye tıklayın.  Basit alan grafikleri, rapor sayfasındaki diğer görselleştirmelere çapraz filtreleme uygulamaz. Ancak alan grafikleri, rapor sayfasındaki diğer görselleştirmeler tarafından tetiklenen çapraz filtrelemelerden etkilenir.

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme
* Basit alan grafikleri, katmanlı alanlardaki kapatma nedeniyle değer karşılaştırmaları için kullanışlı değildir. Power BI, alanlardaki çakışmaları göstermek için saydamlıktan yararlanır. Ancak, bu özellik yalnızca iki veya üç farklı alanda düzgün bir şekilde çalışır. Eğilimi üçten fazla ölçüyle karşılaştırmak için çizgi grafikleri kullanmayı deneyin. Hacmi üçten fazla ölçüyle karşılaştırmak için ise ağaç haritası kullanmayı deneyin.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI'daki raporlar](service-reports.md)  
[Power BI raporlarındaki görselleştirmeler](power-bi-report-visualizations.md)  
[Power BI - Temel Kavramlar](service-basic-concepts.md)  
Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

