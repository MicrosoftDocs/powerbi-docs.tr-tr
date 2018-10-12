---
title: Power BI'da halka grafikler
description: Power BI'da halka grafikler
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 09/24/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: ab292964bb1b6b1f4218d41c46eb2c28c82a034c
ms.sourcegitcommit: ce8332a71d4d205a1f005b703da4a390d79c98b6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2018
ms.locfileid: "47416763"
---
# <a name="doughnut-charts-in-power-bi"></a>Power BI'da halka grafikler
Halka grafik de pasta grafiği gibi parçaların bütünle olan ilişkisini gösterir. Tek fark ortasının boş ve bir etiket veya simge yerleştirmeye müsait olmasıdır.

## <a name="create-a-doughnut-chart"></a>Halka grafik oluşturma
Bu yönergelerde bu yılın satışlarını kategorilere ayrılmış şekilde gösteren bir Halka grafik oluşturmak üzere Retail Analysis Sample kullanılmaktadır. Yönergeleri takip etmek için Power BI hizmeti veya Power BI Desktop [örneğini indirin](../sample-datasets.md).

1. [Boş bir rapor sayfasında](../power-bi-report-add-page.md) başlayın. Power BI hizmetini kullanıyorsanız raporu [Düzenleme Görünümü](../service-interact-with-a-report-in-editing-view.md)'nde açtığınızdan emin olmanız gerekir.

2. Alanlar bölmesinde **Sales** \> **Last Year Sales** seçeneğini belirleyin.  
   
3. Görsel Öğeler bölmesinde çubuk grafiğinizi halka grafiğe dönüştürmek için halka grafik simgesini ![halka grafik simgesi](media/power-bi-visualization-doughnut-charts/power-bi-icon.png) seçin. **Last Year Sales**, **Değerler** alanında görüntülenmiyorsa oraya sürükleyin.
     
   ![Halka seçili görselleştirme bölmesi](media/power-bi-visualization-doughnut-charts/power-bi-doughnut-chart.png)

4. **Item** \> **Category**'yi seçerek **Açıklama** alanına ekleyin. 
     
    ![Alanlar bölmesinin yanındaki halka](media/power-bi-visualization-doughnut-charts/power-bi-doughnut-done.png)

5. İsteğe bağlı olarak [grafik metninin boyutunu ve rengini ayarlayabilirsiniz](power-bi-visualization-customize-title-background-and-legend.md). 

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme
* Halka grafikteki değerlerin toplamının %100 olması gerekir.
* Çok fazla kategori kullanılması durumunda grafiği okumak ve yorumlamak zor olabilir.
* Halka grafikler, bölümleri birbirleriyle karşılaştırmaktan çok belirli bir bölümü bütünle karşılaştırma durumlarında kullanışlıdır. 

## <a name="next-steps"></a>Sonraki adımlar
[Power BI'da huni grafikleri](power-bi-visualization-funnel-charts.md)

[Power BI'daki görselleştirme türleri](power-bi-visualization-types-for-reports-and-q-and-a.md)


