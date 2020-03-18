---
title: Power BI görsellerinde Dilimleyicileri Eşitleme özelliğini etkinleştirme
description: Bu makalede Power BI görsellerine Dilimleyicileri Eşitleme özelliğini ekleme işlemi açıklanır.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: how-to
ms.date: 06/18/2019
ms.openlocfilehash: 88e7e4b83f303f2b366f276b5020194f55f21f25
ms.sourcegitcommit: 6bbc3d0073ca605c50911c162dc9f58926db7b66
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79380743"
---
# <a name="sync-slicers-in-power-bi-visuals"></a>Power BI görsellerinde dilimleyicileri eşitleme

[Dilimleyicileri Eşitleme](https://docs.microsoft.com/power-bi/desktop-slicers) özelliğini desteklemek için özel dilimleyici görselinizin API sürüm 1.13 veya üstünü kullanıyor olması gerekir.

Bunun yanı sıra, aşağıdaki kodda gösterildiği gibi bu seçeneği *capabilities.json* dosyasında da etkinleştirmelisiniz:

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

*Capabilities.json* dosyasını güncelleştirdikten sonra, özel dilimleyici görselinizi seçtiğinizde **Dilimleyicileri eşitle** seçeneklerini görebilirsiniz.

> [!NOTE]
> Dilimleyicileri Eşitleme özelliği birden fazla alanı desteklemez. Dilimleyicinizin birden fazla alanı varsa (**Kategori** veya **Ölçü**) özellik devre dışı bırakılır.

![“Dilimleyicileri eşitle” bölmesi](media/enable-sync-slicers/sync-slicers-panel.png)

**Dilimleyicileri eşitle** bölmesinde dilimleyici görünürlüğünüzün ve filtrelemesinin çeşitli rapor sayfalarına uygulanabildiğini görebilirsiniz.
