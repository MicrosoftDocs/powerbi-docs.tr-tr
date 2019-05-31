---
title: Basit Alan grafiği
description: Basit Alan grafiği.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 09/24/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 02d81a4ebb92ec199887109c7f2d9afcb6449eda
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "61393278"
---
# <a name="basic-area-chart"></a>Basit Alan grafiği
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

   b.  Görsel öğeler bölmesinden Alan grafiği simgesini seçerek grafiği, basit bir alan grafiğine dönüştürün.

   ![](media/power-bi-visualization-basic-area-chart/convertchart.png)
   
   c.  **Eksen** kutusuna eklemek üzere **Time \> Month** seçeneğini belirleyin.   
   ![](media/power-bi-visualization-basic-area-chart/powerbi-area-chartnew.png)
   
   d.  Grafiği aya göre görüntülemek için, üç nokta (görselin sağ üst köşesinde) simgesini seçin ve **Sıralama Ölçütü: Month** seçeneğini belirleyin. Sıralama düzenini değiştirmek için, üç nokta simgesini tekrar seçin ve **Artan düzende sırala** veya **Azalan düzende sırala**'yı seçin.

## <a name="highlighting-and-cross-filtering"></a>Vurgulama ve çapraz filtreleme
Filtreler bölmesini kullanma hakkında bilgi için bkz. [Bir rapora filtre ekleme](../power-bi-report-add-filter.md).

Grafiğinizdeki belirli bir alanı vurgulamak için ilgili alanı veya üst kenarlığını seçin.  Diğer görselleştirme türlerinin aksine, sayfada başka görselleştirmeler varken basit alan grafiklerini vurguladığınızda rapor sayfasındaki diğer görselleştirmeler için çapraz filtre uygulanmaz. Ancak alan grafikleri, rapor sayfasındaki diğer görselleştirmeler tarafından tetiklenen çapraz filtrelemelerden etkilenir. 

1. Alan grafiğinizi seçip başka bir rapor sayfasına (CTRL-C ve CTRL-V) kopyalayarak deneyin.
2. Gölgeli alanlardan birini ve ardından diğer gölgeli alanı seçin. Sayfadaki diğer görsel öğelerde hiçbir etki olmadığını fark edeceksiniz.

    ![Alan grafiğinde seçili bu yılın satışları](media/power-bi-visualization-basic-area-chart/power-bi-select-area.png)

3. Şimdi, sayfadaki diğer görsel öğelerden birinde, sütun grafik çubuğu veya çizgi grafikteki ay gibi bir öğe seçin. Alan grafiği üzerindeki filtreleme etkisine dikkat edin.  

    ![Ft Oglethorpe çubuğu seçilir](media/power-bi-visualization-basic-area-chart/power-bi-filter.png) 

Daha fazla bilgi edinmek için bkz. [Raporlardaki görsel etkileşimler](../service-reports-visual-interactions.md)


## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme   
* [Raporu engelli kişiler için daha kolay erişilebilir hale getirme](../desktop-accessibility.md)
* Basit alan grafikleri, katmanlı alanlardaki kapatma nedeniyle değer karşılaştırmaları için kullanışlı değildir. Power BI, alanlardaki çakışmaları göstermek için saydamlıktan yararlanır. Ancak, bu özellik yalnızca iki veya üç farklı alanda düzgün bir şekilde çalışır. Eğilimi üçten fazla ölçüyle karşılaştırmak için çizgi grafikleri kullanmayı deneyin. Hacmi üçten fazla ölçüyle karşılaştırmak için ise ağaç haritası kullanmayı deneyin.

## <a name="next-step"></a>Sonraki adım
[Power BI'daki raporlar](power-bi-visualization-card.md)  

