---
title: 1\. Bölüm, Bir Power BI raporuna görselleştirme ekleme
description: 1\. Bölüm, Bir Power BI raporuna görselleştirme ekleme
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: IkJda4O7oGs
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/17/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: c5838d12351c06d0a76a975c9c473b1c00856d97
ms.sourcegitcommit: 90aa7ea5fcc7cf0fd7f6c3c1efeff5f27e8ef0dd
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/20/2019
ms.locfileid: "67299162"
---
# <a name="part-1-add-visualizations-to-a-power-bi-report"></a>1\. Bölüm, Bir Power BI raporuna görselleştirme ekleme

Bu makalede bir raporda görselleştirme oluşturma hakkında özet bilgiler verilmektedir. Bu, hem Power BI hizmeti hem Power BI Desktop için geçerlidir. Daha ayrıntılı içerik için bu serinin [2. Bölümüne bakın](power-bi-report-add-visualizations-ii.md). Rapor tuvali üzerinde farklı görsel oluşturma, düzenleme ve biçimlendirme yöntemlerini gösteren Amanda'yı izleyin. Ardından [Satış ve Pazarlama örneğini](../sample-datasets.md) kullanarak kendi raporunuzu oluşturun.

<iframe width="560" height="315" src="https://www.youtube.com/embed/IkJda4O7oGs" frameborder="0" allowfullscreen></iframe>

## <a name="open-a-report-and-add-a-new-page"></a>Rapor açma ve yeni sayfa ekleme

1. Bir [raporu Düzenleme Görünümü'nde](../service-interact-with-a-report-in-editing-view.md) açın.

    Bu eğitimde [Satış ve Pazarlama örneği](../sample-datasets.md) kullanılmaktadır.

1. **Alanlar** bölmesi görünür değilse ok simgesini seçerek açın.

   ![](media/power-bi-report-add-visualizations-i/pbi_nancy_fieldsfiltersarrow.png)

1. Rapora boş bir sayfa ekleyin.

## <a name="add-visualizations-to-the-report"></a>Rapora görselleştirme ekleme

1. **Alanlar** bölmesindeki alanlardan birini seçerek bir görselleştirme oluşturun.

    **SalesFact** > **Sales $** gibi bir sayısal alanla başlayın. Power BI, tek sütun içeren bir sütun grafiği oluşturur.

    ![Tek sütun içeren bir sütun grafiğinin ekran görüntüsü.](media/power-bi-report-add-visualizations-i/pbi_onecolchart.png)

    Öte yandan **Name** ve **Product** gibi bir kategori alanıyla da başlayabilirsiniz. Power BI bir tablo oluşturur ve söz konusu alanı da **Değerler**'e ekler.

    ![Tablo oluşturmak için Product'ı ve ardından kategoriyi seçen bir kişinin GIF resmi.](media/power-bi-report-add-visualizations-i/pbi_agif_createchart3.gif)

    Öte yandan **Geo** > **City** gibi bir coğrafi alanla da başlayabilirsiniz. Power BI ve Bing Haritalar bir harita görselleştirmesi oluşturur.

    ![Harita görselleştirmesinin ekran görüntüsü.](media/power-bi-report-add-visualizations-i/power-bi-map.png)

1. Bir görselleştirme oluşturup türünü değiştirin. **Product** > **Category** ve ardından **Product** > **Count of Product** seçimlerini yaparak ikisini de **Değerler** kutusuna ekleyin.

   ![Değerler kutusunun vurgulandığı Alanlar bölmesinin ekran görüntüsü.](media/power-bi-report-add-visualizations-i/part1table1.png)

1. **Yığılmış sütun grafiği** simgesini seçerek görselleştirmeyi sütun grafik haline getirin.

   ![Yığılmış sütun grafiği simgesinin vurgulandığı Görselleştirmeler bölmesinin ekran görüntüsü.](media/power-bi-report-add-visualizations-i/part1converttocolumn.png)

1. Raporunuzda oluşturduğunuz görselleştirmeleri [panonuza sabitleyebilirsiniz](../service-dashboard-pin-tile-from-report.md). Görselleştirmeyi sabitlemek için raptiye simgesini ![Raptiye simgesinin ekran görüntüsü.](media/power-bi-report-add-visualizations-i/pinnooutline.png) seçin.

   ![Raptiye simgesinin vurgulandığı bir sütun grafiği görselleştirmesinin ekran görüntüsü.](media/power-bi-report-add-visualizations-i/part1pin1.png)
  
## <a name="next-steps"></a>Sonraki adımlar

 Devam edin:

* [2. Bölüm: Power BI raporuna görselleştirme ekleme](power-bi-report-add-visualizations-ii.md) bölümünden devam edin

* Rapordaki [görselleştirmelerle etkileşim kurun](../consumer/end-user-reading-view.md).

* [Görselleştirmelerle daha fazlasını yapın](power-bi-report-visualizations.md).

* [Raporunuzu kaydedin](../service-report-save.md).
