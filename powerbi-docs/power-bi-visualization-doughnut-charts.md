---
title: Power BI'da halka grafikler
description: Power BI'da halka grafikler
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 12/23/2017
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 5d8be3d160e8ea37ba9814c7bd78c3ad5a751d3b
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34294208"
---
# <a name="doughnut-charts-in-power-bi"></a>Power BI'da halka grafikler
Halka grafik de pasta grafiği gibi parçaların bütünle olan ilişkisini gösterir. Tek fark ortasının boş ve bir etiket veya simge yerleştirmeye müsait olmasıdır.

## <a name="create-a-doughnut-chart"></a>Halka grafik oluşturma
Bu yönergelerde bu yılın satışlarını kategorilere ayrılmış şekilde gösteren bir Halka grafik oluşturmak üzere Retail Analysis Sample kullanılmaktadır. Yönergeleri takip etmek için Power BI hizmeti (app.powerbi.com) veya Power BI Desktop [örneğini indirin](sample-datasets.md).

1. [Boş rapor sayfasıyla](power-bi-report-add-page.md) başlayın ve **SalesStage** \> **Sales Stage** alanını seçin. Power BI hizmetini kullanıyorsanız raporu [Düzenleme Görünümü](service-interact-with-a-report-in-editing-view.md)'nde açtığınızdan emin olmanız gerekir.

2. Alanlar bölmesinde **Sales** \> **Last Year Sales** seçeneğini belirleyin.  
   
3. Görsel Öğeler bölmesinde çubuk grafiğinizi halka grafiğe dönüştürmek için halka grafik simgesini ![halka grafik simgesi]() seçin. **Last Year Sales**, **Değerler** alanında görüntülenmiyorsa oraya sürükleyin.
     
   ![](media/power-bi-visualization-doughnut-charts/power-bi-doughnut-chart.png)

4. **Item** \> **Category**'yi seçerek **Açıklama** alanına ekleyin. 
     
    ![](media/power-bi-visualization-doughnut-charts/power-bi-doughnut-done.png)

5. İsteğe bağlı olarak [grafik metninin boyutunu ve rengini ayarlayabilirsiniz](power-bi-visualization-customize-title-background-and-legend.md). 

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme
* Halka grafikteki değerlerin toplamının %100 olması gerekir.
* Çok fazla kategori kullanılması durumunda grafiği okumak ve yorumlamak zor olabilir.
* Halka grafikler, bölümleri birbirleriyle karşılaştırmaktan çok belirli bir bölümü bütünle karşılaştırma durumlarında kullanışlıdır. 

## <a name="next-steps"></a>Sonraki adımlar
[Power BI'daki raporlar](service-reports.md)

[Power BI'daki görselleştirme türleri](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Power BI raporlarındaki görselleştirmeler](power-bi-report-visualizations.md)

[Power BI - Temel Kavramlar](service-basic-concepts.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

