---
title: Rapordaki görsellerin etkileşim kurma biçimini anlama
description: Power BI son kullanıcılarına rapora sayfasındaki görseller arasındaki etkileşimi açıklayan belge.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 09/24/2019
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: b95df5c32d9058e4480d7af5e226a971ba581144
ms.sourcegitcommit: 02042995df12cc4e4b97eb8a369e62364eb5af36
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/25/2019
ms.locfileid: "71256284"
---
# <a name="how-visuals-cross-filter-each-other-in-a-power-bi-report"></a>Görseller bir Power BI raporunda birbirini nasıl çapraz filtreler?
Power BI'ın en önemli özelliklerinden biri, rapor sayfasındaki tüm görsellerin birbirine bağlı olmasıdır. Görsellerin birinde bir veri noktası seçtiğinizde sayfadaki aynı verileri içeren diğer tüm görseller de seçime göre değişir. 

![etkileşim kuran görsellerin videosu](media/end-user-interactions/interactions.gif)

Rapor sayfasındaki görselleştirmede bulunan bir veri noktası seçildiğinde, sayfadaki diğer görselleştirmeler için çapraz filtreleme, çapraz vurgulama ve detaya gitme işlemleri varsayılan olarak uygulanır. 

Bu, verilerinizdeki bir değerin farklı bir değere nasıl katkıda bulunduğunu belirlemek için yararlı olabilir. Örneğin, halka grafikteki Denetim segmentini seçtiğinizde, bu segmentin Aylara göre Topla birim grafiğindeki her sütuna yaptığı katkı vurgulanır ve sağdaki çizgi grafik filtrelenir.

![görsellerin etkileşimi görüntüsü](media/end-user-interactions/power-bi-interactions.png)

Bkz. [Filtreleme ve vurgulama hakkında](../power-bi-reports-filters-and-highlighting.md). 

Sayfadaki görseller arasındaki etkileşim rapor *tasarımcısı* tarafından belirlenir. Tasarımcılar görsel etkileşimlerini açıp kapatabilir ve varsayılan çapraz filtreleme, çapraz vurgulama ve ayrıntıya inme davranışını değiştirebilir. 
  
> [!NOTE]
> Görselleştirmeleri filtrelemek ve vurgulamak için **Filtreler**  bölmesini kullandığınızda gerçekleşen davranış ile burada açıklanan davranış arasındaki farkı belirtmek için *çapraz filtreleme* ve *çapraz vurgulama* terimleri kullanılmıştır.  

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme
- Raporunuzun [detaya gitmeyi](../power-bi-visualization-drill-down.md) destekleyen bir görselleştirmesi varsa, bir görselleştirmede detaya gidildiğinde rapor sayfasındaki diğer görselleştirmeler varsayılan olarak bundan etkilenmez.     
- B görseliyle etkileşim kurmak için A görselini kullanırsanız, A görselinin görsel düzeyi filtreleri B görseline uygulanır.

## <a name="next-steps"></a>Sonraki adımlar
[Rapor filtrelerini kullanma](../power-bi-how-to-report-filter.md)
