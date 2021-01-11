---
title: Daha iyi tümleşik BI içgörüleri için, Power BI tümleşik analizlerindeki Power BI görsellerinde Dilimleyicileri Eşitleme özelliğini etkinleştirme
description: Bu makalede Power BI görsellerine Dilimleyicileri Eşitleme özelliğini ekleme işlemi açıklanır. Power BI tümleşik analiz kullanarak daha iyi tümleşik BI içgörüleri elde edin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: how-to
ms.date: 06/18/2019
ms.openlocfilehash: bd69e05bba3e9449f9fb6f07bd9625dfb1ea0c08
ms.sourcegitcommit: eeaf607e7c1d89ef7312421731e1729ddce5a5cc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2021
ms.locfileid: "97885303"
---
# <a name="sync-slicers-in-power-bi-visuals"></a>Power BI görsellerinde dilimleyicileri eşitleme

[Dilimleyicileri Eşitleme](../../visuals/power-bi-visualization-slicers.md) özelliğini desteklemek için özel dilimleyici görselinizin API sürüm 1.13.0 veya üstünü kullanıyor olması gerekir.

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