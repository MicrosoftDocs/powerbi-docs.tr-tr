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
ms.openlocfilehash: 6ad986308fb82f8191829d29654bb96b55d0fbd0
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83272707"
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

Power BI ile görsel geliştirmeyi denemek için bkz. [Power BI görseli geliştirme](custom-visual-develop-tutorial.md).
