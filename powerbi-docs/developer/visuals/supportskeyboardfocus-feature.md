---
title: Daha iyi tümleşik BI içgörüleri için, Power BI tümleşik analizlerindeki supportsKeyboardFocus özelliği
description: Bu makalede Power BI görsellerinde supportsKeyboardFocus özelliğini kullanma adımları ve bu özelliğin gereksinimleri açıklanır. Power BI tümleşik analiz kullanarak daha iyi tümleşik BI içgörüleri elde edin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 04/30/2020
ms.openlocfilehash: 5ba87db8118076de4bf13abc0280223f9f04f871
ms.sourcegitcommit: eeaf607e7c1d89ef7312421731e1729ddce5a5cc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2021
ms.locfileid: "97887972"
---
# <a name="use-the-supportskeyboardfocus-feature"></a>supportsKeyboardFocus özelliğini kullanma

Bu makalede Power BI görsellerinde `supportsKeyboardFocus` özelliğinin nasıl kullanılacağı açıklanır.
`supportsKeyboardFocus` özelliği, görselin veri noktalarında yalnızca klavyeyi kullanarak gezinmeyi sağlar.

Görsellerde klavye ile gezinme hakkında daha fazla bilgi için bkz. [Klavye ile gezinme](../../create-reports/desktop-accessibility-consuming-tools.md#keyboard-navigation).

## <a name="example"></a>Örnek

`supportsKeyboardFocus` özelliğini kullanan bir görsel açın. Görsel içinde herhangi bir veri noktasını seçin ve Sekme tuşuna basın. Sekme tuşuna her bastığınızda odak bir sonraki veri noktasına geçer. Vurgulanan veri noktasını seçmek için Enter tuşuna basın.

![supportsKeyboardFocus örneği](./media/supportskeyboardfocus-feature/supports-keyboard-focus-example.png)

## <a name="requirements"></a>Gereksinimler

Bu özellik için API v2.1.0 veya üzeri gerekir.

Bu özellik, görüntü görselleri hariç tüm görsellere uygulanabilir.

## <a name="usage"></a>Kullanım

`supportsKeyboardFocus` özelliğini kullanmak için aşağıdaki kodu görselinizin *capabilities.json* dosyasına ekleyin.
Bu özellik, odağın klavye ile görsele geçirilebilmesini sağlar.

```json
    {   
            ...
        "supportsKeyboardFocus": true
            ...
    }

```

## <a name="next-steps"></a>Sonraki adımlar

Erişilebilirlik özellikleri hakkında daha fazla bilgi edinmek için bkz. [Power BI raporlarını erişilebilirlik için tasarlama](../../create-reports/desktop-accessibility-creating-reports.md).

Power BI ile görsel geliştirmeyi denemek için bkz. [Power BI daire kartı görseli geliştirme](develop-circle-card.md).
