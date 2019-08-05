---
title: Görsellerin etkileşimleri
description: Power BI’ın görsel etkileşimlere izin verip vermemesi gerektiği nasıl denetlenir?
author: shaym83
ms.author: shaym
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 739e59c6da3c1e464e0462a928bc4f33ea0d01f8
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2019
ms.locfileid: "68424505"
---
# <a name="visuals-interactions"></a>Görsellerin etkileşimleri

Görseller, görselin görsel etkileşimlere izin verip vermeyeceğini belirten ‘allowInteractions’ bayrağının değerini sorgulayabilir.
Örneğin, görseller rapor görüntüleme veya düzenleme esnasında etkileşimlidir. Ancak, bir panoda görüntülendiklerinde etkileşimli olmazlar.
Bu etkileşimler tıklama, kaydırma, yakınlaştırma, seçme ve diğerleridir.
Bu bayrak ne olursa olsun, araç ipuçlarının tüm senaryolarda etkinleştirilmesi gerektiğini unutmayın.

‘allowInteractions’ bayrağı, IVisualHost arabiriminin üyesi olarak görselin başlatılması esnasında bir Boole olarak geçirilir.

‘allowInteractions’ bayrağı, görsellerin etkileşimli olmamasını gerektiren tüm Power BI senaryolarında (örneğin, Pano kutucukları) false olarak ayarlanır.
Aksi takdirde (örneğin, Rapor), ‘allowInteractions’ değeri true olarak ayarlanır.

Daha fazla bilgi için bkz. [SampleBarChart görsel deposu](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/59a47935d8f5272ce145fe804193599ddb7e2001)

```typescript
   ...
   let allowInteractions = options.host.allowInteractions;
   bars.on('click', function(d) {
       if (allowInteractions) {
           selectionManager.select(d.selectionId);
           ...
       }
   });
```
