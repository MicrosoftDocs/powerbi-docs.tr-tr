---
title: Vurgulama
description: Power BI Görselleri’nde veri noktası seçimlerini vurgulama
author: KesemSharabi
ms.author: kesharab
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 4ff2187dc99d4e790b08c11f55a37e31e85693ad
ms.sourcegitcommit: e2de2e8b8e78240c306fe6cca820e5f6ff188944
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/23/2019
ms.locfileid: "71193987"
---
# <a name="highlight-data-points-in-power-bi-visuals"></a>Power BI Görselleri’nde veri noktalarını vurgulama

Varsayılan olarak, bir öğe seçildiğinde `dataView` nesnesindeki `values` dizisi yalnızca seçilen değerlere filtrelenecektir. Sayfadaki tüm diğer görsellerin yalnızca seçili verileri görüntülemesini sağlar.

![Varsayılan davranış ‘dataView’ı’ vurgula](./media/highlight-dataview.png)

`capabilities.json` öğenizdeki `supportsHighlight` özelliğini `true` olarak ayarlarsanız, bir `highlights` dizisi ile birlikte tam, filtrelenmemiş `values` dizisini alırsınız. `highlights` dizisi, değerler dizisiyle aynı uzunlukta olur ve seçili olmayan tüm değerler `null` olarak ayarlanır. Bu özellik etkinken, `values` dizisini `highlights` dizisiyle karşılaştırarak uygun verileri vurgulama görselin sorumluluğudur.

![‘DataView’ supporthighlight’ı vurgula](./media/highlight-dataview-supports.png)

Örnekte, 1 çubuğun seçili olduğunu fark edeceksiniz. Bu, vurgular dizisindeki tek değerdir. Birden fazla seçimin ve kısmi vurgunun olabileceği de göz önünde bulundurulmalıdır. Değerlerde karşılık gelen sayısal değer bulunur. Vurgu dizileri mevcuttur ancak farklıdır.
