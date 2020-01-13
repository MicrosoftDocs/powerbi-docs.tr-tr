---
title: Rapordaki görsellerin etkileşim kurma biçimini anlama
description: Power BI son kullanıcılarına rapora sayfasındaki görseller arasındaki etkileşimi açıklayan belge.
author: mihart
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 12/18/2019
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: dc8dad0417ac2ed6498fb7612900ebdbb0ce2a18
ms.sourcegitcommit: 4359baa43ca01b179d28ec59f4e61ba8c07ee288
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75303860"
---
# <a name="how-visuals-cross-filter-each-other-in-a-power-bi-report"></a>Görseller bir Power BI raporunda birbirini nasıl çapraz filtreler?
Power BI'ın en önemli özelliklerinden biri, rapor sayfasındaki tüm görsellerin birbirine bağlı olmasıdır. Görsellerin birinde bir veri noktası seçtiğinizde sayfadaki aynı verileri içeren diğer tüm görseller de seçime göre değişir. 

![etkileşim kuran görsellerin videosu](media/end-user-interactions/interactions.gif)

## <a name="how-visuals-interact-with-each-other"></a>Görsellerin birbiriyle etkileşimi

Rapor sayfasındaki görselde bulunan bir veri noktası seçildiğinde, sayfadaki diğer görseller için çapraz filtreleme veya çapraz vurgulama işlemleri varsayılan olarak uygulanır. Sayfadaki görseller arasındaki etkileşim rapor *tasarımcısı* tarafından belirlenir. *Tasarımcılar* görsel etkileşimlerini açıp kapatabilir ve varsayılan çapraz filtreleme, çapraz vurgulama ve [detaylandırma](end-user-drill.md) davranışını değiştirebilir. 

Henüz hiyerarşilerle ve detaylandırmayla karşılaşmadıysanız, [Power BI'da detaya gitme](end-user-drill.md) konusunu okuyarak bu konudaki her şeyi öğrenebilirsiniz. 

### <a name="cross-filtering-and-cross-highlighting"></a>Çapraz filtreleme ve çapraz vurgulama

Çapraz filtreleme ve çapraz vurgulama verilerinizdeki bir değerin farklı bir değere nasıl katkıda bulunduğunu belirlemek için yararlı olabilir. Görselleri filtrelemek ve vurgulamak için **Filtreler**  bölmesini kullandığınızda gerçekleşen davranış ile burada açıklanan davranış arasındaki farkı belirtmek için *çapraz filtreleme* ve *çapraz vurgulama* terimleri kullanılmıştır.  

Aşağıdaki rapor sayfalarına bakarken bu terimleri tanımlayalım. "Total category volume by segment" (Segmente göre toplam kategori hacmi) halka grafiğinin iki değeri vardır: "Moderation" ve "Convenience". 

![Rapor sayfası](media/end-user-interactions/power-bi-interactions-before.png)

1. **Moderation** segmentini seçtiğimizde ne olduğuna bakalım.

    ![Halka grafiğin Moderation segmenti seçildikten sonra rapor sayfası](media/end-user-interactions/power-bi-interactions-after.png)

2. **Çapraz filtreleme** uygun olmayan verileri kaldırır. Grafikte **Moderation** segmentinin seçilmesi çizgi grafiğe çapraz filtre uygular. Çizgi grafikte şimdi yalnızca Moderation segmentinin veri noktaları görüntülenir. 

3. **Çapraz vurgulama** tüm özgün veri noktalarını korur ama seçiminize uygun olmayan bölümü soluk görüntüler. Halka grafikte **Moderation** segmentinin seçilmesi sütun grafiğe çapraz vurgulama uygular. Sütun grafik Convenience segmentine uygun olan tüm verileri soluk görüntüler ve Moderation segmentine uygun olan tüm verileri vurgular. 


## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme
- Raporunuzun [detaya gitmeyi](end-user-drill.md) destekleyen bir görseli varsa, bir görselde detaya gidildiğinde rapor sayfasındaki diğer görseller varsayılan olarak bundan etkilenmez.     
- Rapor sayfasında diğer görseller çapraz filtrelenirken ve çapraz vurgulanırken görsel düzeyinde filtreler korunur. Bu neden VisualA'nın rapor tasarımcısı tarafından uygulanan veya sizin uyguladığınız görsel düzeyinde filtreleri varsa ve visualB ile etkileşim kurmak için visualA'yı kullanıyorsanız, visualA'daki görsel düzeyinde filtreler visualB'ye uygulanır.

    ![Halka grafiğin Moderation segmenti seçildikten sonra rapor sayfası](media/end-user-interactions/power-bi-visual-filters.png)

## <a name="next-steps"></a>Sonraki adımlar
[Rapor filtrelerini kullanma](../power-bi-how-to-report-filter.md)    


[Filtreleme ve vurgulama hakkında](end-user-report-filter.md). 
