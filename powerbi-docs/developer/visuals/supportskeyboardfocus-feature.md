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
ms.openlocfilehash: 1e5a4cf8c80d8123d39fd2ab76898abc0c439ad9
ms.sourcegitcommit: 50b21718a167c2b131313b4135c8034c6f027597
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/14/2020
ms.locfileid: "92049396"
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
