---
title: 'DAX: VALUES yerine SELECTEDVALUE kullanma'
description: SELECTEDVALUE işlevlerinin ne zaman kullanılacağına yönelik rehber.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/20/2019
ms.author: v-pemyer
ms.openlocfilehash: 6aef2c06cc62668ea7dea9fe404e294d1a5faa93
ms.sourcegitcommit: f77b24a8a588605f005c9bb1fdad864955885718
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2019
ms.locfileid: "74700490"
---
# <a name="dax-use-selectedvalue-instead-of-values"></a>DAX: VALUES yerine SELECTEDVALUE kullanma

Veri modelleyicisi olarak bazen bir sütunun belirli bir değere göre filtrelenip filtrelenmediğini test etmek için bir DAX ifadesi yazmanız gerekir.

Önceki DAX sürümlerinde bu gereksinim, üç DAX işlevi içeren bir desen kullanılarak güvenli bir şekilde karşılanıyordu. Söz konusu işlevler [IF](/dax/if-function-dax), [HASONEVALUE](/dax/hasonevalue-function-dax) ve [VALUES](/dax/values-function-dax) işlevleridir. Aşağıdaki ölçü tanımı bir örnek oluşturur. Yalnızca Avustralyalı müşterilere yapılan satışlar için satış vergisi tutarını hesaplar.

```dax
Australian Sales Tax =
IF(
    HASONEVALUE(Customer[Country-Region]),
    IF(
        VALUES(Customer[Country-Region]) = "Australia",
        [Sales] * 0.10
    )
)
```

Örnekte HASONEVALUE işlevi yalnızca **Country-Region** sütununu tek bir değer filtrelediğinde TRUE döndürür. TRUE olduğunda VALUES işlevi "Australia" değişmez değeriyle karşılaştırılır. VALUES işlevi TRUE döndürdüğünde, **Sales** ölçüsü 0,10 ile çarpılır (%10'u temsil eder). Sütunu birden çok değer filtrelediği için HASONEVALUE işlevi FALSE döndürürse, ilk IF işlevi BLANK döndürür.

HASONEVALUE işlevinin kullanılması bir savunma tekniğidir. **Country-Region** sütununu birden çok değerin filtrelemesi mümkün olduğundan, bu gereklidir. Böyle bir durumda VALUES işlevi birden çok satırdan oluşmuş bir tablo döndürür. Birden çok satırdan oluşmuş bir tablonun skaler değerle karşılaştırılması hata sonucu döndürür.

## <a name="recommendation"></a>Öneri

[SELECTEDVALUE](/dax/selectedvalue-function) işlevini kullanmanızı öneririz. Bu makalede açıklanan desenle aynı sonucu, ama daha etkili ve şık bir şekilde verir.

Örnek ölçü tanımı şimdi SELECTEDVALUE işlevi kullanılarak yeniden yazılmıştır.

```dax
Australian Sales Tax =
IF(
    SELECTEDVALUE(Customer[Country-Region]) = "Australia",
    [Sales] * 0.10
)
```

> [!TIP]
> SELECTEDVALUE işlevinde bir _alternatif sonuç_ değeri geçirilebilir. Sütuna hiç filtre uygulanmazsa veya birden çok filtre uygulanırsa alternatif sonuç değeri döndürülür.

## <a name="next-steps"></a>Sonraki adımlar

Bu makale hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

- [Veri Çözümleme İfadeleri (DAX) Başvurusu](/dax/)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
