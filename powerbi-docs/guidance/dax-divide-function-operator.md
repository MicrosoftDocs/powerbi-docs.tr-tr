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
ms.openlocfilehash: c20a366ef657e851ef77a9649dbcc8b66b67dac0
ms.sourcegitcommit: f77b24a8a588605f005c9bb1fdad864955885718
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2019
ms.locfileid: "74695209"
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

DIVIDE işlevinin alternatif değer döndürüp döndürmeyeceğini dikkatli bir şekilde düşünün. Ölçümler için, anlamlı bir sonucun hesaplanamadığı durumlarda genellikle BOŞLUK döndürülmesi daha iyi bir tasarımdır. Daha fazla bilgi için bkz. [BOŞLUK'ları değerlere dönüştürmekten kaçınma](dax-avoid-converting-blank.md).

## <a name="next-steps"></a>Sonraki adımlar

Bu makale hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

- [Veri Çözümleme İfadeleri (DAX) Başvurusu](/dax/)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
