---
title: 'DAX: DIVIDE işleviyle bölme işlecini (/) karşılaştırma'
description: DAX DIVIDE işlevinin ne zaman kullanılacağı konusunda rehberlik.
author: peter-myers
manager: asaxton
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 09/09/2019
ms.author: v-pemyer
ms.openlocfilehash: 7516aaedb886e7b9e0f57ed76f0a7c5e40efbd6d
ms.sourcegitcommit: 6a44cb5b0328b60ebe7710378287f1e20bc55a25
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70877845"
---
# <a name="dax-divide-function-vs-divide-operator-"></a>DAX: DIVIDE işleviyle bölme işlecini (/) karşılaştırma

Bu makale DAX ifadeleri tanımlayan veri modelleyicilerine yöneliktir.

## <a name="background"></a>Arka Plan

Bir payı paydaya bölmek için DAX ifadesi yazarken, [DIVIDE](/dax/divide-function-dax) işlevini veya bölme işlecini (/ - eğik çizgi) kullanmayı seçebilirsiniz.

DIVIDE işlevini kullandığınızda pay ve payda ifadelerini geçirmeniz gerekir. İsteğe bağlı olarak alternatif bir sonucu temsil eden bir değer de geçirebilirsiniz.

```dax

DIVIDE(<numerator>, <denominator> [,<alternateresult>])

```

DIVIDE işlevi sıfıra bölme durumlarını otomatik olarak işleyecek şekilde tasarlanmıştır. Alternatif sonuç geçirilmezse ve payda sıfır veya BOŞLUK ise işlev BOŞLUK döndürür. Alternatif sonuç geçirilirse BOŞLUK yerine o sonuç döndürülür.

DIVIDE işlevinin kullanışlı olmasının nedeni ifadenizde önce payda değerinin test edilmesi gereğini ortadan kaldırmasıdır. Bu işlev payda değerinin test edilmesi açısından [IF](/dax/if-function-dax) işlevinden de daha iyidir. Sıfıra göre bölüm kontrol etmek pahalı olduğu için performans kazancı önemlidir. Ayrıca DIVIDE işlevi kullanıldığında sonuçta daha kısa ve zarif bir ifade elde edilir.

## <a name="example"></a>Örnek

Aşağıdaki ölçü ifadesi güvenli bir bölme üretir ama dört DAX işlevinin kullanılmasını gerektirir.

```dax

=IF(OR(ISBLANK([Sales]), [Sales] == 0), BLANK(), [Profit] / [Sales])

```

Bu ölçü ifadesi daha verimli ve zarif bir şekilde aynı sonuca ulaşır.

```dax

=DIVIDE([Profit], [Sales])

```

## <a name="recommendations"></a>Öneriler

Paydanın sıfır veya BOŞLUK _döndürebilecek_ bir ifade olduğu her durumda DIVIDE işlevini kullanmanızı öneririz.

Paydanın sabit değer olduğu durumlarda bölme işlecini kullanmanızı öneririz. Bu durumda bölmenin başarılı olması garanti edilir ve ifadeniz gereksiz testten kaçınacağı için daha iyi bir performans gösterir.

DIVIDE işlevinin alternatif değer döndürüp döndürmeyeceğini dikkatle düşünmelisiniz. Ölçüler için bu genellikle BOŞLUK döndürmesinden daha iyi bir tasarımdır. Çünkü rapor görselleri özetlemeler BOŞLUK olduğunda varsayılan olarak gruplandırmaları ortadan kaldırır. Bu sayede görsel verilerin bulunduğu gruplara odaklanabilir. Gerektiğinde "Veri İçermeyen Öğeleri Göster" seçeneğini etkinleştirerek filtre bağlamındaki tüm grupları (değer veya BOŞLUK döndürenler) görüntüleyecek şekilde görseli yapılandırabilirsiniz.
