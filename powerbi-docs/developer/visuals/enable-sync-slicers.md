---
title: Power BI görsellerinde Dilimleyicileri Eşitleme özelliğini etkinleştirme
description: Bu makalede Power BI görsellerine Dilimleyicileri Eşitleme özelliğini ekleme işlemi açıklanır.
author: KesemSharabi
ms.author: kesharab
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 47f0148528d1ccfd451aa8e8ed87b4bec99d087e
ms.sourcegitcommit: e2de2e8b8e78240c306fe6cca820e5f6ff188944
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/23/2019
ms.locfileid: "71194389"
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

![“Dilimleyicileri eşitle” bölmesi](./media/sync-slicers-panel.png)

**Dilimleyicileri eşitle** bölmesinde dilimleyici görünürlüğünüzün ve filtrelemesinin çeşitli rapor sayfalarına uygulanabildiğini görebilirsiniz.
