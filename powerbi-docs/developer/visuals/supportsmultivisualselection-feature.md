---
title: supportsMultiVisualSelection özelliği
description: Bu makalede Power BI görsellerinde supportsMultiVisualSelection özelliğini kullanma adımları ve bu özelliğin gereksinimleri açıklanır.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 04/30/2020
ms.openlocfilehash: 091bdeb4eeb4c979ccf0e79476eb081895fae2e1
ms.sourcegitcommit: 50b21718a167c2b131313b4135c8034c6f027597
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/14/2020
ms.locfileid: "92049419"
---
# <a name="use-the-supportsmultivisualselection-feature"></a>supportsMultiVisualSelection özelliğini kullanma

`supportsMultiVisualSelection` özelliği, bir rapordaki birden çok görselde seçim işlevini kullanmanızı sağlar.

## <a name="example"></a>Örnek

Birden fazla görselin bulunduğu bir raporda iki değer seçerek diğer görsellere de uygulanmasını sağlayabilirsiniz. Örneğin [Perakende Analizi örneğindeki](../../create-reports/sample-retail-analysis.md) görsellerden birinde **Fashions Direct**'i seçin. CTRL tuşuna basılı tutarak başka bir görselde **Oca** değerini seçin. Yaptığınız seçimler bu özelliğin kullanılmasını destekleyen diğer rapor görsellerine de uygulanır. Diğer görsellerin kapsamı **Fashions Direct** ve **Oca** değerine göre değişir.

## <a name="requirements"></a>Gereksinimler

Bu özellik için API v3.2.0 veya üzeri gerekir.

Bu özellik görüntü görsellerine uygulanamaz. Temel sürücü, ayrıştırma ağacı, Soru-Cevap görselleri, metin kutusu ve ölçer grafikleri gibi bazı gelişmiş görsellere de uygulanamaz.

## <a name="usage"></a>Kullanım

`supportsMultiVisualSelection` özelliğini kullanmak için aşağıdaki kodu görselinizin `capabilities.json` dosyasına ekleyin.

```json
    {   
            ...
        "supportsMultiVisualSelection": true
            ...
    }
```

## <a name="next-steps"></a>Sonraki adımlar

Power BI kavramları hakkında daha fazla bilgi için bkz. [Power BI'daki görseller](power-bi-visuals-concept.md).

Power BI ile görsel geliştirmeyi denemek için bkz. [Power BI daire kartı geliştirme](develop-circle-card.md).
