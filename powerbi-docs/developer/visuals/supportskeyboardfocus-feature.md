---
title: supportsKeyboardFocus özelliği
description: Bu makalede Power BI görsellerinde supportsKeyboardFocus özelliğini kullanma adımları ve bu özelliğin gereksinimleri açıklanır.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 04/30/2020
ms.openlocfilehash: c8cf0f4e896b8a44764d1c363c597182f55d30b3
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83276525"
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

Power BI ile görsel geliştirmeyi denemek için bkz. [Power BI görseli geliştirme](custom-visual-develop-tutorial.md).
