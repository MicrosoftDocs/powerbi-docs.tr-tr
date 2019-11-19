---
title: 1\. Bölüm, Bir Power BI raporuna görselleştirme ekleme
description: 1\. Bölüm, Bir Power BI raporuna görselleştirme ekleme
author: mihart
ms.reviewer: ''
featuredvideoid: IkJda4O7oGs
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 10/28/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: d68abc7b4509595d4dfa3071dc56673e6af89e4f
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73871061"
---
# <a name="part-1-add-visualizations-to-a-power-bi-report"></a>1\. Bölüm, Bir Power BI raporuna görselleştirme ekleme

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

Bu makalede bir raporda görselleştirme oluşturma hakkında özet bilgiler verilmektedir. Bu, hem Power BI hizmeti hem Power BI Desktop için geçerlidir. Daha ayrıntılı içerik için bu serinin [2. Bölümüne bakın](power-bi-report-add-visualizations-ii.md). Rapor tuvali üzerinde farklı görsel oluşturma, düzenleme ve biçimlendirme yöntemlerini gösteren Amanda'yı izleyin. Ardından [Satış ve Pazarlama örneğini](../sample-datasets.md) kullanarak kendi raporunuzu oluşturun.

<iframe width="560" height="315" src="https://www.youtube.com/embed/IkJda4O7oGs" frameborder="0" allowfullscreen></iframe>

## <a name="prerequisites"></a>Önkoşullar

Bu eğitimde [Satış ve pazarlama PBIX dosyası](https://download.microsoft.com/download/9/7/6/9767913A-29DB-40CF-8944-9AC2BC940C53/Sales%20and%20Marketing%20Sample%20PBIX.pbix) kullanılmaktadır.

1. Power BI Desktop menü çubuğunun sol üst kısmından **Dosya** > **Aç**’ı seçin
   
2. **Satış ve pazarlama örneği PBIX dosyası** kopyanızı bulun

1. **Satış ve pazarlama örneği PBIX dosyasını** rapor görünümünde ![Rapor görünümü simgesinin ekran görüntüsü.](media/power-bi-visualization-kpi/power-bi-report-view.png) açın.

1. Seç ![Sarı sekmenin ekran görüntüsü.](media/power-bi-visualization-kpi/power-bi-yellow-tab.png) yeni bir sayfa ekleyin.

## <a name="add-visualizations-to-the-report"></a>Rapora görselleştirme ekleme

1. **Alanlar** bölmesindeki alanlardan birini seçerek bir görselleştirme oluşturun.

    **Sales** > **TotalSales** gibi bir sayısal alanla başlayın. Power BI, tek sütun içeren bir sütun grafiği oluşturur.

    ![Tek sütun içeren bir sütun grafiğinin ekran görüntüsü.](media/power-bi-report-add-visualizations-i/power-bi-column-chart.png)

    Öte yandan **Name** ve **Product** gibi bir kategori alanıyla da başlayabilirsiniz. Power BI bir tablo oluşturur ve söz konusu alanı da **Değerler**'e ekler.

    ![Dört kategoriye sahip bir tablonun ekran görüntüsü](media/power-bi-report-add-visualizations-i/power-bi-product.png)

    Öte yandan **Geo** > **City** gibi bir coğrafi alanla da başlayabilirsiniz. Power BI ve Bing Haritalar bir harita görselleştirmesi oluşturur.

    ![Harita görselleştirmesinin ekran görüntüsü.](media/power-bi-report-add-visualizations-i/power-bi-maps.png)

## <a name="change-the-type-of-visualization"></a>Görselleştirme türünü değiştirme

 Bir görselleştirme oluşturup türünü değiştirin. 
 
 1. **Product** > **Category** ve ardından **Product** > **Count of Product** seçimlerini yaparak ikisini de **Değerler** kutusuna ekleyin.

    ![Değerler kutusunun vurgulandığı Alanlar bölmesinin ekran görüntüsü.](media/power-bi-report-add-visualizations-i/power-bi-create-visual.png)

1. **Yığılmış sütun grafiği** simgesini seçerek görselleştirmeyi sütun grafik haline getirin.

   ![Yığılmış sütun grafiği simgesinin vurgulandığı Görselleştirmeler bölmesinin ekran görüntüsü.](media/power-bi-report-add-visualizations-i/power-bi-convert.png)

1. Görselin sıralama ölçütünü değiştirmek için **Diğer eylemler** (...) öğesini seçin.  Sıralamanın yönünü (artan veya azalan) ve sıralamak için kullanılan sütunu (**Sıralama ölçütü**) değiştirmek üzere sıralama seçeneklerini kullanın.

   ![Diğer eylemler açılır listesinin ekran görüntüsü.](media/power-bi-report-add-visualizations-i/power-bi-sort.png)
  
## <a name="next-steps"></a>Sonraki adımlar

 Devam edin:

* [2. Bölüm: Power BI raporuna görselleştirme ekleme](power-bi-report-add-visualizations-ii.md) bölümünden devam edin

* Rapordaki [görselleştirmelerle etkileşim kurun](../consumer/end-user-reading-view.md).

