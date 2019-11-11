---
title: Rapordaki görsellerin etkileşim kurma biçimini anlama
description: Power BI son kullanıcılarına rapora sayfasındaki görseller arasındaki etkileşimi açıklayan belge.
author: mihart
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 10/03/2019
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 28e6cea55b02fabddd0b2f118631a09c0344b66f
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73863085"
---
# <a name="how-visuals-cross-filter-each-other-in-a-power-bi-report"></a>Görseller bir Power BI raporunda birbirini nasıl çapraz filtreler?
Power BI'ın en önemli özelliklerinden biri, rapor sayfasındaki tüm görsellerin birbirine bağlı olmasıdır. Görsellerin birinde bir veri noktası seçtiğinizde sayfadaki aynı verileri içeren diğer tüm görseller de seçime göre değişir. 

![etkileşim kuran görsellerin videosu](media/end-user-interactions/interactions.gif)

## <a name="how-visuals-interact-with-each-other"></a>Görsellerin birbiriyle etkileşimi

Rapor sayfasındaki görselde bulunan bir veri noktası seçildiğinde, sayfadaki diğer görseller için çapraz filtreleme veya çapraz vurgulama işlemleri varsayılan olarak uygulanır. Sayfadaki görseller arasındaki etkileşim rapor *tasarımcısı* tarafından belirlenir. *Tasarımcılar* görsel etkileşimlerini açıp kapatabilir ve varsayılan çapraz filtreleme, çapraz vurgulama ve [detaylandırma](end-user-drill.md) davranışını değiştirebilir. 

Henüz hiyerarşilerle ve detaylandırmayla karşılaşmadıysanız, [Power BI'da detaya gitme](end-user-drill.md) konusunu okuyarak bu konudaki her şeyi öğrenebilirsiniz. 

Çapraz filtreleme ve çapraz vurgulama verilerinizdeki bir değerin farklı bir değere nasıl katkıda bulunduğunu belirlemek için yararlı olabilir. Örneğin, halka grafikteki Denetim segmentini seçtiğinizde, bu segmentin "Total units by Month" grafiğindeki her sütuna yaptığı katkı vurgulanır ve çizgi grafik filtrelenir.

![görsellerin etkileşimi görüntüsü](media/end-user-interactions/power-bi-interactions.png)

Bkz. [Filtreleme ve vurgulama hakkında](end-user-report-filter.md). 


  
> [!NOTE]
> Görselleri filtrelemek ve vurgulamak için **Filtreler**  bölmesini kullandığınızda gerçekleşen davranış ile burada açıklanan davranış arasındaki farkı belirtmek için *çapraz filtreleme* ve *çapraz vurgulama* terimleri kullanılmıştır.  

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme
- Raporunuzun [detaya gitmeyi](end-user-drill.md) destekleyen bir görseli varsa, bir görselde detaya gidildiğinde rapor sayfasındaki diğer görseller varsayılan olarak bundan etkilenmez.     
- B görseliyle etkileşim kurmak için A görselini kullanırsanız, A görselinin görsel düzeyi filtreleri B görseline uygulanır.

## <a name="next-steps"></a>Sonraki adımlar
[Rapor filtrelerini kullanma](../power-bi-how-to-report-filter.md)
