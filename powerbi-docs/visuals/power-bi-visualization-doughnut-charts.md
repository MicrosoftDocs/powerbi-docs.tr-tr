---
title: Power BI'da halka grafikler
description: Power BI'da halka grafikler
author: msftrien
ms.reviewer: mihart
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 05/05/2020
ms.author: rien
LocalizationGroup: Visualizations
ms.openlocfilehash: 24788b16718e1223bdd2040d42a67e4f175b8371
ms.sourcegitcommit: 5ccab484cf3532ae3a16acd5fc954b7947bd543a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/06/2020
ms.locfileid: "93413074"
---
# <a name="create-and-use-doughnut-charts-in-power-bi"></a>Power BI'da halka grafik oluşturma ve kullanma

[!INCLUDE[consumer-appliesto-nyyn](../includes/consumer-appliesto-nyyn.md)]

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

Halka grafik de pasta grafiği gibi parçaların bütünle olan ilişkisini gösterir. Tek fark ortasının boş ve bir etiket veya simge yerleştirmeye müsait olmasıdır.

## <a name="prerequisite"></a>Önkoşul

Bu öğreticide [Perakende Analizi örneği .PBIX dosyası](https://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix) kullanılmıştır.

1. Menü çubuğunun sol üst köşesinden **Dosya** > **Aç** ’ı seçin
   
2. **Perakende Analizi örneği PBIX dosyasının** kopyasını bulun

1. **Perakende Analizi örneği PBIX dosyasını** rapor görünümünde ![Rapor görünümü simgesinin ekran görüntüsü.](media/power-bi-visualization-kpi/power-bi-report-view.png) açın.

1. Seç ![Sarı sekmenin ekran görüntüsü.](media/power-bi-visualization-kpi/power-bi-yellow-tab.png) yeni bir sayfa ekleyin.


> [!NOTE]
> Raporunuzu bir Power BI iş arkadaşınızla paylaşmak için her ikinizin de bireysel Power BI Pro lisanslarınızın olması veya raporun Premium kapasitede depolanması gerekir.    

## <a name="create-a-doughnut-chart"></a>Halka grafik oluşturma

1. Boş bir rapor sayfasında başlayın ve Alanlar bölmesinden **Satış** \> **Geçen Yılın Satışları** ’nı seçin.  
   
3. Görsel Öğeler bölmesinde çubuk grafiğinizi halka grafiğe dönüştürmek için halka grafik simgesini ![halka grafik simgesi](media/power-bi-visualization-doughnut-charts/power-bi-icon.png) seçin. **Last Year Sales** , **Değerler** alanında görüntülenmiyorsa oraya sürükleyin.
     
   ![Halka seçili görselleştirme bölmesi](media/power-bi-visualization-doughnut-charts/power-bi-doughnut-chart.png)

4. **Item** \> **Category** 'yi seçerek **Açıklama** alanına ekleyin. 
     
    ![Alanlar bölmesinin yanındaki halka](media/power-bi-visualization-doughnut-charts/power-bi-doughnut-done.png)

5. İsteğe bağlı olarak [grafik metninin boyutunu ve rengini ayarlayabilirsiniz](power-bi-visualization-customize-title-background-and-legend.md). 

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme
* Halka grafikteki değerlerin toplamının %100 olması gerekir.
* Çok fazla kategori kullanılması durumunda grafiği okumak ve yorumlamak zor olabilir.
* Halka grafikler, bölümleri birbirleriyle karşılaştırmaktan çok belirli bir bölümü bütünle karşılaştırma durumlarında kullanışlıdır. 

## <a name="next-steps"></a>Sonraki adımlar
[Power BI'da huni grafikleri](power-bi-visualization-funnel-charts.md)

[Power BI'daki görselleştirme türleri](power-bi-visualization-types-for-reports-and-q-and-a.md)


