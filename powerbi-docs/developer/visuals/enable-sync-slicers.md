---
title: Eşitleme dilimleyicilerini etkinleştirme
description: Power BI Görselleri için eşitleme dilimleyicileri ekleme
author: EugeneElkin
ms.author: v-evelk
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 9966475e8bcaccad2090451b47ef09ef0a9af125
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425034"
---
# <a name="sync-slicers"></a>Eşitleme Dilimleyicileri

[Eşitleme Dilimleyicileri](https://docs.microsoft.com/power-bi/desktop-slicers)’ni desteklemek için özel dilimleyici görselinizin API 1.13 veya daha yeni bir sürümü kullanması gerekir.

İkinci gerekli görünüş, `capabilities.json` öğesindeki etkin seçeneğidir (aşağıdaki örneğe bakın).

```json
{
    ...
    "supportsHighlight": true,
    "suppressDefaultTitle": true,
    "supportsSynchronizingFilterState": true,
    "sorting": {
        "default": {}
    }
}
```

`capabilities.json` öğesinde yapılan değişikliklerden sonra, özel dilimleyici görselinize tıkladığınızda Eşitleme Dilimleyicileri seçeneği panelini görebilirsiniz.

> [!NOTE]
> Dilimleyicinizde 1’den fazla alan varsa (kategori veya ölçü), Eşitleme Dilimleyicileri birden fazla alanı desteklemediği için özellik devre dışı bırakılır.

![Eşitleme dilimleyicileri paneli](./media/sync-slicers-panel.png)

Panelde, dilimleyici görünürlüğünüzün ve filtrelemesinin birkaç rapor sayfasına uygulanabildiğini görebilirsiniz.
