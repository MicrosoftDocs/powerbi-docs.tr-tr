---
title: Power BI görsellerinde görsel etkileşimleri
description: Bu makalede Power BI görsellerinin görsel etkileşimlerine izin vermesi gerekip gerekmediğini denetleme işlemi açıklanır.
author: shaym83
ms.author: shaym
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: f2fb2d451deb63b5e9c08472654e28d0e1a469db
ms.sourcegitcommit: b602cdffa80653bc24123726d1d7f1afbd93d77c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70236636"
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
