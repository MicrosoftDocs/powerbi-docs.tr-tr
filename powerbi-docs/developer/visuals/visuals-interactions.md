---
title: Power BI görsellerinde görsel etkileşimleri
description: Bu makalede Power BI görsellerinin görsel etkileşimlerine izin vermesi gerekip gerekmediğini denetleme işlemi açıklanır.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: how-to
ms.date: 06/18/2019
ms.openlocfilehash: 1fb4f7d5950ab18a74dcacfdfef9c3ada90512c4
ms.sourcegitcommit: 6bbc3d0073ca605c50911c162dc9f58926db7b66
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79378950"
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
