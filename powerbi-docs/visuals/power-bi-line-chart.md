---
title: Power BI çizgi grafikler
description: Power BI çizgi grafikler
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/07/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 0654dccf55b1e13f26d8ecaabee0349f0e56afc6
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65535802"
---
# <a name="line-charts-in-power-bi"></a>Power BI çizgi grafikler
Bir çizgi grafik noktalarla ve düz bir çizgiyle bağlanmış veri noktalarının bir dizisidir. Bir çizgi grafik, bir veya daha çok satırı olabilir. Çizgi grafiklerin X ve Y ekseni sahip. 

![Basit bir çizgi grafik](media/power-bi-line-charts/power-bi-line.png)

## <a name="create-a-line-chart"></a>Bir çizgi grafik oluşturun
Bu yönergeleri kullanın satış ve pazarlama örneği uygulama kategoriye göre bu yılın satışları görüntüleyen bir çizgi grafik oluşturmak için. Örneği takip etmek için örnek uygulamayı appsource.com alın.

1. Boş bir rapor sayfasında başlayın. Power BI hizmetini kullanıyorsanız raporu [Düzenleme Görünümü](../service-interact-with-a-report-in-editing-view.md)'nde açtığınızdan emin olmanız gerekir.

2. Alanlar bölmesinden seçin **SalesFact** \> **toplam birimler**seçip **tarih** > **ay**.  Power BI rapor tuvalinde bir sütun grafik oluşturur.

    ![Alanlar bölmesinden seçin](media/power-bi-line-charts/power-bi-step1.png)

4. Görsel öğeler bölmesinden çizgi grafiği şablonunu seçerek bir çizgi grafiğe dönüştürün. 

    ![çizgi grafiğe dönüştürme](media/power-bi-line-charts/power-bi-convert-to-line.png)
   

4. Çizgi grafik 2012 2014 yıllara ait verileri göstermek için filtreleyin. Filtreler bölmesi, daraltılmışsa, artık genişletin. Alanlar bölmesinden seçin **tarih** \> **yıl** ve filtreleri bölmesine sürükleyin. Başlığı altında bırak **bu görsel filtreler**. 
     
    ![Alanlar bölmesinde yanındaki satır](media/power-bi-line-charts/power-bi-year-filter.png)

    Değişiklik **Gelişmiş filtreler** için **temel filtreler** seçip **2012**, **2013** ve **2014**.

    ![Yıl için filtre](media/power-bi-line-charts/power-bi-filter-year.png)

6. İsteğe bağlı olarak [grafik metninin boyutunu ve rengini ayarlayabilirsiniz](power-bi-visualization-customize-title-background-and-legend.md). 

    ![Yazı tipi boyutunu artırın ve Y axisfont değiştirin](media/power-bi-line-charts/power-bi-line-3years.png)

## <a name="add-additional-lines-to-the-chart"></a>Grafiğe bir ek satırlar ekleyin
Çizgi grafikler, birçok farklı satırlara sahip olabilir. Ve satırlardaki değerlerin bazı durumlarda, bu nedenle bunlar birlikte düzgün gösterme kaliteleri olabilir. Ardından satırları tarafından temsil edilen değeri çok farklı olduğunda grafiğimizde biçimlendirmeyi öğrenin ve grafik bizim geçerli ek satırlar ekleme sırasında bakalım. 

### <a name="add-additional-lines"></a>Ek satırları ekleyin
Tüm bölgeler için toplam birimler grafiği tek bir satır olarak bakarak yerine, şimdi bölgeye göre toplam birimler kullanıma bölün. Ek satırları sürükleyerek ekleyin **coğrafi** > **bölge** gösterge kutusu için.

   ![Her bölge için bir satır](media/power-bi-line-charts/power-bi-line-regions.png)


### <a name="use-two-y-axes"></a>İki Y ekseni kullan
Toplam satış ve toplam birimler aynı grafikte bakmak istersek? Satış rakamları, çizgi grafik kullanılabilmesini birim numaraları çok daha yüksektir. Aslında, toplam birimler için kırmızı çizgi sıfır gibi görünüyor.

   ![yüksek oranda değerleri ayrışan](media/power-bi-line-charts/power-bi-diverging.png)

Yüksek oranda ayrılan değerler bir grafikte görüntülenecek bir birleşik harita kullanın. Okuyarak tüm birleşik haritalar hakkında bilgi edinebilirsiniz [Power bı'daki birleşik haritalar](power-bi-visualization-combo-chart.md). Bizim örneğimizde biz satış ve toplam birimi birlikte bir grafikte ikinci bir Y ekseni ekleyerek görüntüleyebilirsiniz. 

   ![yüksek oranda değerleri ayrışan](media/power-bi-line-charts/power-bi-dual-axes.png)

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme
* Bir çizgi grafik çift Y eksenleri sahip olamaz.  Bir birleşik harita kullanmanız gerekir.
* Yukarıdaki örneklerde, grafiklerde yazı tipi boyutunu artırın, yazı tipi rengini değiştirme, eksen başlıklarını ekleyin, gösterge ve Grafik başlığı Merkezi, her iki ekseni ve sıfır başlatma için uygulanmıştır. Biçimlendirme bölmesini (Boya rulosu simgesi) gelmeyen bir dizi bunları istediğiniz gibi grafikler görünümü sağlama seçeneği vardır. Bilgi edinmek için en iyi yolu, biçimlendirme bölmesini açmak ve araştırmak sağlamaktır.

## <a name="next-steps"></a>Sonraki adımlar

[Power BI'daki görselleştirme türleri](power-bi-visualization-types-for-reports-and-q-and-a.md)


