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
ms.openlocfilehash: 4e9989bb7a34a89cb6244a2378d6660a5079fc82
ms.sourcegitcommit: 6bc66f9c0fac132e004d096cfdcc191a04549683
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/06/2020
ms.locfileid: "91748115"
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