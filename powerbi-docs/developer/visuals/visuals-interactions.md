---
title: Power BI görsellerinde görsel etkileşimleri
description: Bu makalede Power BI görsellerinin görsel etkileşimlerine izin vermesi gerekip gerekmediğini denetleme işlemi açıklanır.
author: KesemSharabi
ms.author: kesharab
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 0155f0fce1bc0fec5c96aef1c7e1dc9cf64b122f
ms.sourcegitcommit: e2de2e8b8e78240c306fe6cca820e5f6ff188944
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/23/2019
ms.locfileid: "71193894"
---
# <a name="visual-interactions-in-power-bi-visuals"></a>Power BI görsellerinde görsel etkileşimleri

Görseller, görselin görsel etkileşimlerine izin verip vermeyeceğini belirten `allowInteractions` bayrağının değerini sorgulayabilir. Örneğin, görseller rapor görüntüleme veya düzenleme sırasında etkileşimlidir. Ama panoda görüntülenirken etkileşimli olmazlar. Bu etkileşimler *tıklama*, *kaydırma*, *yakınlaştırma*, *seçim* ve diğerleridir. 

> [!NOTE]
> Hangi bayrağın gösterildiğine bakmadan tüm senaryolarda araç ipuçlarını etkinleştirmelisiniz.

`allowInteractions` bayrağı, IVisualHost arabiriminin üyesi olarak görselin başlatılması sırasında bir Boole değeri olarak geçirilir.

Görsellerin etkileşimli olmamasını gerektiren Power BI senaryolarında (örneğin pano kutucukları) `allowInteractions` bayrağı `false` olarak ayarlanır. Aksi takdirde (örneğin Rapor) `allowInteractions` bayrağı `true` olarak ayarlanır.

Daha fazla bilgi için bkz. [SampleBarChart görsel deposu](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/59a47935d8f5272ce145fe804193599ddb7e2001).

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
