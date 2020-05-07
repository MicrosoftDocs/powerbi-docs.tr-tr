---
title: 'DAX: DIVIDE işleviyle bölme işlecini (/) karşılaştırma'
description: DAX DIVIDE işlevinin ne zaman kullanılacağı konusunda rehberlik.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 09/09/2019
ms.author: v-pemyer
ms.openlocfilehash: 7eea15d4389afaac2ac69e2f26eaa38fe84e337b
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "75304183"
---
# <a name="dax-divide-function-vs-divide-operator-"></a>DAX: DIVIDE işleviyle bölme işlecini (/) karşılaştırma

Veri modelleyicisi olarak, bir payı paydaya bölmek için DAX ifadesi yazdığınızda [DIVIDE](/dax/divide-function-dax) işlevini veya bölme işlecini (/ - eğik çizgi) kullanmayı seçebilirsiniz.

DIVIDE işlevini kullandığınızda pay ve payda ifadelerini geçirmeniz gerekir. İsteğe bağlı olarak _alternatif bir sonucu_ temsil eden bir değer de geçirebilirsiniz.

```dax
DIVIDE(<numerator>, <denominator> [,<alternateresult>])
```

DIVIDE işlevi sıfıra bölme durumlarını otomatik olarak işleyecek şekilde tasarlanmıştır. Alternatif sonuç geçirilmezse ve payda sıfır veya BOŞLUK ise işlev BOŞLUK döndürür. Alternatif sonuç geçirildiğinde BOŞLUK yerine o sonuç döndürülür.

DIVIDE işlevinin kullanışlı olmasının nedeni ifadenizde önce payda değerinin test edilmesi gereğini ortadan kaldırmasıdır. Bu işlev payda değerinin test edilmesi açısından [IF](/dax/if-function-dax) işlevinden de daha iyidir. Sıfıra göre bölüm kontrol etmek pahalı olduğu için performans kazancı önemlidir. DIVIDE işlevi kullanıldığında sonuçta daha kısa ve zarif bir ifade elde edilir.

## <a name="example"></a>Örnek

Aşağıdaki ölçü ifadesi güvenli bir bölme üretir ama dört DAX işlevinin kullanılmasını gerektirir.

```dax
Profit Margin =
IF(
    OR(
        ISBLANK([Sales]),
        [Sales] == 0
    ),
    BLANK(),
    [Profit] / [Sales]
)
```

Bu ölçü ifadesi daha verimli ve zarif bir şekilde aynı sonuca ulaşır.

```dax
Profit Margin =
DIVIDE([Profit], [Sales])
```

## <a name="recommendations"></a>Öneriler

Paydanın sıfır veya BOŞLUK _döndürebilecek_ bir ifade olduğu her durumda DIVIDE işlevini kullanmanızı öneririz.

Paydanın sabit değer olduğu durumlarda bölme işlecini kullanmanızı öneririz. Bu durumda bölmenin başarılı olması garanti edilir ve ifadeniz gereksiz testten kaçınacağı için daha iyi bir performans gösterir.

DIVIDE işlevinin alternatif değer döndürüp döndürmeyeceğini dikkatli bir şekilde düşünün. Ölçüler için bu genellikle BOŞLUK döndürmesinden daha iyi bir tasarımdır. Özetlemeler BOŞLUK olduğunda rapor görselleri varsayılan olarak gruplandırmaları ortadan kaldırdığından, BOŞLUK döndürmesi daha iyidir. Bu sayede görsel verilerin bulunduğu gruplara odaklanabilir. Gerektiğinde [Veri içermeyen öğeleri göster](../desktop-show-items-no-data.md) seçeneğini etkinleştirerek filtre bağlamındaki tüm grupları (değer veya BOŞLUK döndürenler) görüntüleyecek şekilde görseli yapılandırabilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

Bu makale hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

- [Veri Çözümleme İfadeleri (DAX) Başvurusu](/dax/)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
