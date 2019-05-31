---
title: Power BI hizmetindeki ve Power BI Desktop'taki rapor görselleştirmelerine genel bakış
description: Microsoft Power BI'daki görselleştirmelere (görsellere) genel bakış.
author: mihart
ms.author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: SYk_gWrtKvM
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/28/2019
LocalizationGroup: Visualizations
ms.openlocfilehash: d470a262bd8a5e6590746fb07889b1230f5cfc25
ms.sourcegitcommit: 8bf2419b7cb4bf95fc975d07a329b78db5b19f81
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66375657"
---
# <a name="visualizations-in-power-bi-reports"></a>Power BI raporlarındaki görselleştirmeler

Görselleştirmeler (başka bir deyişle görseller) verilerden elde edilen öngörüleri görüntüler. Power BI raporları bir görsel içeren tek sayfadan oluşabileceği gibi görsellerle dolu birçok sayfa da içerebilir. Power BI hizmetinde görseller [raporlardan veya panolardan sabitlenebilir](../service-dashboard-pin-tile-from-report.md).

Rapor arasında ayrım yapmak önemlidir *tasarımcıları* ve rapor *tüketiciler* oluşturma veya değiştirme rapor kişi sizseniz sonra bir tasarımcı olan.  Tasarımcılar, raporu ve kendi temel alınan veri kümesi için düzenleme izinlerine sahip. Power BI Desktop'ta bu, veri kümesini Veri görünümünde açabileceğiniz ve Rapor görünümünde görseller oluşturabileceğiniz anlamına gelir. Power BI hizmetinde bu açabilirsiniz veri kümesi veya rapor rapor düzenleyicisinde anlamına gelir [düzenleme görünümü](../consumer/end-user-reading-view.md). Bir rapor veya pano [sizinle paylaşıldıysa](../consumer/end-user-shared-with-me.md) rapor **kullanıcısı** olursunuz. Rapora ve içerdiği görsellerle etkileşime girmeye yönelik mümkün olacaktır, ancak büyük değişiklikleri kaydetmek mümkün olmayacaktır.

Doğrudan Power BI'daki GÖRSEL ÖĞELER bölmesinden kullanabileceğiniz çok sayıda farklı görsel türü vardır.

![](media/power-bi-report-visualizations/power-bi-templates.png)

Daha da fazla seçenek için [Microsoft AppSource topluluk sitesini](https://appsource.microsoft.com) ziyaret edip Microsoft ve topluluk tarafından sağlanan [özel görselleri](../developer/custom-visual-develop-tutorial.md) bulabilir ve [indirebilirsiniz](https://appsource.microsoft.com/marketplace/apps?page=1&product=power-bi-visuals).

<iframe width="560" height="315" src="https://www.youtube.com/embed/SYk_gWrtKvM?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>


  Power BI'da yeniyseniz veya bilgilerinizi tazelemek istiyorsanız Power BI görselleştirmeleri ile ilgili temel bilgileri edinmek için aşağıdaki bağlantıları kullanın.  Alternatif olarak, daha da fazla faydalı bilgiye ulaşmak için İçindekiler (bu makalenin sol tarafında) başlıklı bölümümüzü kullanabilirsiniz.

## <a name="add-a-visualization-in-power-bi"></a>Power BI'da görselleştirme ekleme

Rapor sayfalarınızda [görselleştirmeler oluşturun](power-bi-report-add-visualizations-i.md). [Kullanılabilir görselleştirmelere ve görselleştirmelere ilişkin mevcut eğitimlere](power-bi-visualization-types-for-reports-and-q-and-a.md) göz atın. 

## <a name="upload-a-custom-visualization-and-use-it-in-power-bi"></a>Özel görselleştirme yükleme ve bunu Power BI'da kullanma

Kendi oluşturduğunuz veya [Microsoft AppSource topluluk sitesinde](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals) bulduğunuz bir özel görselleştirmeyi ekleyin. Yaratıcılığınızı konuşturmak mı istiyorsunuz? Kaynak kodumuzu inceleyin, yeni bir görselleştirme türü oluşturmak için [geliştirici araçlarımızı](../developer/custom-visual-develop-tutorial.md) kullanın ve [bunu toplulukla paylaşın](../developer/office-store.md). Özel görsel geliştirme hakkında daha fazla bilgi edinmek için, [Power BI özel görseli geliştirme](../developer/custom-visual-develop-tutorial.md) bağlantısını ziyaret edin.

## <a name="change-the-visualization-type"></a>Görselleştirme türünü değiştirme

Verilerinize en çok hangisinin uyduğunu görmek için [görselleştirme türünü değiştirmeyi](power-bi-report-change-visualization-type.md) deneyin.

## <a name="pin-the-visualization"></a>Görselleştirmeyi sabitleme

Power BI hizmetinde görselleştirmeyi istediğiniz hale getirdikten sonra kutucuk olarak [bir panoya sabitleyebilirsiniz](../service-dashboard-pin-tile-from-report.md). Sabitledikten sonra, raporda kullanılan görselleştirmeyi değiştirmeniz halinde panodaki kutucuk değişmez. Görselleştirme bir çizgi grafik ise raporda Halka grafik olarak değiştirmiş olsanız bile çizgi grafik olarak kalır.

## <a name="limitations-and-considerations"></a>Sınırlamalar ve önemli noktalar
- Veri kaynağı ve alan (ölçüler veya sütunlardan) bağlı olarak, bir görsel yavaş yükleyebilir.  10-20 toplam alanları, hem okunabilirlik ve Performans nedeniyle Görsellere sınırlama öneririz. 

- Görseller için üst sınır 100 alanlar (ölçüler veya sütunlardan) ' dir. Görselinizi yüklenemezse, alanların sayısını azaltın.   

## <a name="next-steps"></a>Sonraki adımlar

* [Power BI'daki görselleştirme türleri](power-bi-visualization-types-for-reports-and-q-and-a.md)
* [Özel görseller](../power-bi-custom-visuals.md)