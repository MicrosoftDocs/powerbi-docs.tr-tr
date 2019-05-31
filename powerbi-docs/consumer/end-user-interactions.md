---
title: Rapordaki görsellerin etkileşim kurma biçimini anlama
description: Power BI son kullanıcılarına rapora sayfasındaki görseller arasındaki etkileşimi açıklayan belge.
author: mihart
manager: kvivek
ms.custom: seodec18
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 05/29/2019
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 7148a52d7c7475fbe685f83b1e1cc325521460db
ms.sourcegitcommit: d88cc6a87d4ba82ad2c4d496a3634f927e4ac529
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/30/2019
ms.locfileid: "66413154"
---
# <a name="how-visuals-cross-filter-each-other-in-a-power-bi-report"></a>Görseller bir Power BI raporunda birbirini nasıl çapraz filtreler?
Power BI'ın en önemli özelliklerinden biri, rapor sayfasındaki tüm görsellerin birbirine bağlı olmasıdır. Görsellerin birinde bir veri noktası seçtiğinizde sayfadaki aynı verileri içeren diğer tüm görseller de seçime göre değişir. 

![etkileşim kuran görsellerin videosu](media/end-user-interactions/interactions.gif)

Varsayılan olarak, bir veri noktasının bir rapor sayfasındaki tek bir görselleştirmede çapraz filtre seçtiğinizde, çapraz vurgulama, sayfadaki diğer görselleştirmelere detaya gidin. 

Bu yararlı olabilir verilerinizde bir değeri tanımlamak amacıyla diğerine katkıda bulunur. Örneğin, halka grafiğe Moderation segmenti seçerek grafiği aya göre toplam birim her sütun, Kesimden katkısı vurgular ve sağ taraftaki çizgi grafik filtre.

![Görüntü görsellerin etkileşim kurma](media/end-user-interactions/power-bi-interactions.png)

Bkz. [Filtreleme ve vurgulama hakkında](../power-bi-reports-filters-and-highlighting.md). 

Sayfadaki görseller arasındaki etkileşim rapor *tasarımcısı* tarafından belirlenir. Tasarımcılar görsel etkileşimlerini açıp kapatabilir ve varsayılan çapraz filtreleme, çapraz vurgulama ve ayrıntıya inme davranışını değiştirebilir. 
  
> [!NOTE]
> Görselleştirmeleri filtrelemek ve vurgulamak için **Filtreler**  bölmesini kullandığınızda gerçekleşen davranış ile burada açıklanan davranış arasındaki farkı belirtmek için *çapraz filtreleme* ve *çapraz vurgulama* terimleri kullanılmıştır.  

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme
- Raporunuzu destekleyen bir görselleştirmeniz varsa [ayrıntılara](../power-bi-visualization-drill-down.md), varsayılan olarak, bir görselleştirmenin ayrıntısına inmek rapor sayfasındaki diğer görselleştirmeler üzerinde bir etkisi yoktur.     
- VisualA visualB ile etkileşim kurmak için kullandığınız visualA görsel düzeyinde filtreler için visualB uygulanır.

## <a name="next-steps"></a>Sonraki adımlar
[Rapor filtrelerini kullanma](../power-bi-how-to-report-filter.md)
