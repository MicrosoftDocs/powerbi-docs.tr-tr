---
title: "Power BI'daki halka grafikler (Eğitim)"
description: "Eğitim: Power BI'daki halka grafikler"
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
ms.openlocfilehash: 2f428095eb57c5358770f1d6d8572316d2b84c37
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2017
---
# <a name="doughnut-charts-in-power-bi-tutorial"></a>Power BI'daki halka grafikler (Eğitim)
Halka grafik de pasta grafiği gibi parçaların bütünle olan ilişkisini gösterir. Tek fark ortasının boş ve bir etiket veya simge yerleştirmeye müsait olmasıdır.

## <a name="create-a-doughnut-chart"></a>Halka grafik oluşturma
Birlikte ilerleyebilmek için Power BI'da oturum açın ve **Veri Al** \> **Örnekler** \> **Perakende Analizi Örneği** \> **Bağlan**'ı seçin. 

1. Panoda **Total Stores** kutucuğunu seçerek "Retail Analysis Sample" raporunu açın.
2. **Raporu düzenle**'yi seçerek raporu Düzenleme Görünümü'nde açın.
3. [Yeni bir rapor sayfası ekleyin](power-bi-report-add-page.md).
4. Bu yılın satışlarını kategorilere ayrılmış şekilde gösteren bir Halka grafik oluşturun.
   
   * **Alanlar** bölmesinde **Sales** \> **Last Year Sales** seçeneğini belirleyin.
   * Halka grafiğe dönüştürün. Last Year Sales verileri **Değerler** alanında yoksa oraya sürükleyin.
     
       ![](media/power-bi-visualization-doughnut-charts/convertdonut.png)
   * **Item** \> **Category**'yi seçerek **Açıklama** alanına ekleyin. 
     
       ![](media/power-bi-visualization-doughnut-charts/doughnuttutorial.png)

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

