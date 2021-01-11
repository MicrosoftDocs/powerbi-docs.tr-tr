---
title: Daha iyi tümleşik BI içgörüleri için Power BI tümleşik analizlerindeki supportsMultiVisualSelection özelliği
description: Bu makalede Power BI görsellerinde supportsMultiVisualSelection özelliğini kullanma adımları ve bu özelliğin gereksinimleri açıklanır. Power BI tümleşik analiz kullanarak daha iyi tümleşik BI içgörüleri elde edin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 04/30/2020
ms.openlocfilehash: 9e6b17a4576f2354a5cbecc0c3a965a5611784ee
ms.sourcegitcommit: eeaf607e7c1d89ef7312421731e1729ddce5a5cc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2021
ms.locfileid: "97887949"
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
