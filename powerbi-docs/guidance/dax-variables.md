---
title: 'DAX: Formüllerinizi geliştirmek için değişkenleri kullanma'
description: DAX ifadelerinde değişken kullanma yönergeleri.
author: peter-myers
ms.author: kfollis
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi
ms.topic: conceptual
ms.date: 11/23/2019
ms.openlocfilehash: 9dcf6d957a9418d737a511f93fcda0e1978cc45d
ms.sourcegitcommit: fb529c4532fbbdfde7ce28e2b4b35f990e8f21d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2021
ms.locfileid: "99088362"
---
# <a name="dax-use-variables-to-improve-your-formulas"></a>DAX: Formüllerinizi geliştirmek için değişkenleri kullanma

Veri modelleyicisi olarak bazı DAX hesaplamalarını yazmak ve hatalarını ayıklamak zor olabilir. Karmaşık hesaplama gereksinimlerinin bileşik veya karmaşık ifadeler yazmayı gerektirdiği durumlarla sık karşılaşılır. Bileşik ifadeler iç içe birçok işlevin kullanılmasını ve bir olasılıkla ifade mantığının yeniden kullanılmasını içerebilir.

DAX formüllerinizde değişkenlerin kullanılması karmaşık ve verimli hesaplamalar yazmanıza yardımcı olur. Değişkenler şunları sağlayabilir:

- [Performansı geliştirme](#improve-performance)
- [Okunabilirliği geliştirme](#improve-readability)
- [Hata ayıklamayı basitleştirme](#simplify-debugging)
- [Karmaşıklığı azaltma](#reduce-complexity)

Bu makalede yıldan yıla (YoY) satış artışının örnek bir ölçüsünü kullanarak ilk üç avantajı göstereceğiz. (YoY satış artışının formülü şöyledir: satış dönemi _geçen yıl aynı dönemdeki daha az satış, _bölü_ geçen yılın aynı dönemindeki satış.)

Aşağıdaki ölçü tanımıyla başlayalım.

```dax
Sales YoY Growth % =
DIVIDE(
    ([Sales] - CALCULATE([Sales], PARALLELPERIOD('Date'[Date], -12, MONTH))),
    CALCULATE([Sales], PARALLELPERIOD('Date'[Date], -12, MONTH))
)
```

Ölçü doğru sonucu üretir ama yine de şimdi bunun nasıl geliştirilebileceğini görelim.

## <a name="improve-performance"></a>Performansı geliştirme

Formülde "geçen yıl aynı dönemdeki" değeri hesaplayan ifadenin yinelendiğine dikkat edin. Bu formül verimsizdir çünkü Power BI'ın aynı ifadeyi iki kez hesaplamasını gerektirir. Değişken kullanılarak ölçü tanımı daha verimli hale getirilebilir.

Aşağıdaki ölçü tanımı bir gelişmeyi temsil eder. "Geçen yıl aynı dönemdeki" sonucu **SalesPriorYear** adlı değişkene atamak için bir ifade kullanır. Bu değişken daha sonra RETURN ifadesinde iki kez kullanılır.

```dax
Sales YoY Growth % =
VAR SalesPriorYear =
    CALCULATE([Sales], PARALLELPERIOD('Date'[Date], -12, MONTH))
RETURN
    DIVIDE(([Sales] - SalesPriorYear), SalesPriorYear)
```

Ölçü doğru sonucu üretmeye devam eder ve bunu sorgu süresinin yarısı kadar bir zamanda yapar.

## <a name="improve-readability"></a>Okunabilirliği geliştirme

Önceki ölçü tanımında değişken adı seçiminin nasıl RETURN ifadesinin daha rahat anlaşılmasını sağladığına dikkat edin. İfade kısadır ve kendi kendini açıklar.

## <a name="simplify-debugging"></a>Hata ayıklamayı basitleştirme

Değişkenler formülde hata ayıklamanıza da yardımcı olabilir. Değişkene atanan ifadeyi test etmek için RETURN ifadesini geçici olarak yeniden yazıp çıkış olarak değişkeni alabilirsiniz.

Aşağıdaki ölçü tanımı yalnızca **SalesPriorYear** değişkenini döndürür. Hedeflenen RETURN ifadesini nasıl açıklama haline getirdiğine dikkat edin. Bu teknik sayesinde, hata ayıklama tamamlandığında bunu kolayca geri alabilirsiniz.

```dax
Sales YoY Growth % =
VAR SalesPriorYear =
    CALCULATE([Sales], PARALLELPERIOD('Date'[Date], -12, MONTH))
RETURN
    --DIVIDE(([Sales] - SalesPriorYear), SalesPriorYear)
    SalesPriorYear
```

## <a name="reduce-complexity"></a>Karmaşıklığı azaltma

DAX'ın önceki sürümlerinde değişkenler henüz desteklenmiyordu. Dış filtre bağlamlarına başvurmak amacıyla [EARLIER](/dax/earlier-function-dax) veya [EARLIEST](/dax/earliest-function-dax) DAX işlevlerini kullanmak için yeni filtre bağlamları ekleyen karmaşık ifadeler gerekiyordu. Ne yazık ki veri modelleyicilerine bu işlevin anlaşılması ve kullanılması zor geldi.

Değişkenler her zaman RETURN ifadenizin uyguladığı filtrelerin dışında değerlendirilir. Bu nedenle değiştirilmiş bir filtre bağlamında değişken kullandığınızda, EARLIEST işleviyle aynı sonucu elde eder. Dolayısıyla EARLIER veya EARLIEST işlevlerini kullanmaktan kaçınabilirsiniz. Diğer bir deyişle artık daha az karmaşık ve anlaşılması daha kolay formüller yazabilirsiniz.

Aşağıdaki **Subcategory** tablosuna eklenen hesaplanmış sütun tanımını düşünün. **Subcategory Sales** sütununun değerleri temelinde her ürün alt kategorisi için bir derece hesaplar.

```dax
Subcategory Sales Rank =
COUNTROWS(
    FILTER(
        Subcategory,
        EARLIER(Subcategory[Subcategory Sales]) < Subcategory[Subcategory Sales]
    )
) + 1
```

EARLIER işlevi, _geçerli satır bağlamında_**Subcategory Sales** sütun değerine başvurmak için kullanılır.

Hesaplanmış sütun tanımı EARLIER işlevi yerine bir değişken kullanılarak geliştirilebilir. **CurrentSubcategorySales** değişkeni _geçerli satır bağlamında_**Subcategory Sales** sütun değerini depolar ve RETURN ifadesi bunu değiştirilmiş filtre bağlamı içinde kullanır.

```dax
Subcategory Sales Rank =
VAR CurrentSubcategorySales = Subcategory[Subcategory Sales]
RETURN
    COUNTROWS(
        FILTER(
            Subcategory,
            CurrentSubcategorySales < Subcategory[Subcategory Sales]
        )
    ) + 1
```

## <a name="next-steps"></a>Sonraki adımlar

Bu makale hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

- [Veri Çözümleme İfadeleri (DAX) Başvurusu](/dax/)
- [VAR](/dax/var-dax) DAX makalesi
- Öğrenme yolu: [Power BI Desktop’ta DAX kullanma](/learn/paths/dax-power-bi/)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
- Önerileriniz mi var? [Power BI'ı geliştirmek için fikirlerinizi paylaşın](https://ideas.powerbi.com)