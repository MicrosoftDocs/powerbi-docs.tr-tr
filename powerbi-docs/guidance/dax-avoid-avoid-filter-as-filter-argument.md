---
title: 'DAX: FILTER’ı bir filtre bağımsız değişkeni olarak kullanmaktan kaçınma'
description: FILTER işlevini filtre bağımsız değişkeni olarak kullanma kılavuzu.
author: peter-myers
ms.author: v-pemyer
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi
ms.topic: conceptual
ms.date: 12/30/2019
ms.openlocfilehash: 651b4f1323738809e19c0ee42f1dbe71f7bc3998
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96394348"
---
# <a name="dax-avoid-using-filter-as-a-filter-argument"></a>DAX: FILTER’ı bir filtre bağımsız değişkeni olarak kullanmaktan kaçınma

Veri modelleyicisi olarak değiştirilen bir filtre bağlamında değerlendirilmesi gereken DAX ifadelerini yazmanız gerekebilir. Örneğin "kar marjı yüksek ürünler" ile ilgili satışları hesaplamak için bir ölçü tanımı yazabilirsiniz. Bu hesaplamayı makalenin ilerleyen bölümlerinde açıklayacağız.

> [!NOTE]
> Bu makale özellikle içeri aktarılan tabloları filtreleyen model hesaplamalarıyla ilgilidir.

[CALCULATE](/dax/calculate-function-dax) ve [CALCULATETABLE](/dax/calculatetable-function-dax) DAX işlevleri, önemli ve kullanışlı işlevlerdir. Bu işlevleri kullanarak filtre ekleyen veya kaldıran ya da ilişki yollarını değiştiren hesaplamalar yazabilirsiniz. Bunun için filtre bağımsız değişkenlerinin Boole ifadeleri, tablo ifadeleri veya özel filtre işlevleri şeklinde geçirilmesi gerekir. Bu makalede yalnızca Boole ve tablo ifadelerini inceleyeceğiz.

Aşağıda yer alan ve tablo ifadesi kullanarak kırmızı renkli ürünlerin satışını hesaplayan ölçü tanımını inceleyin. Bu tanım, **Product** tablosuna uygulanmış olabilecek tüm filtrelerin yerini alacaktır.

```dax
Red Sales =
CALCULATE(
    [Sales],
    FILTER('Product', 'Product'[Color] = "Red")
)
```

CALCULATE işlevi, [FILTER](/dax/filter-function-dax) DAX işlevi tarafından döndürülen bir tablo ifadesini kabul eder ve **Product** tablosunun her bir satırı için filtre ifadesini değerlendirir. Bu şekilde doğru sonuca yani kırmızı renkli ürünlerin satış rakamlarına ulaşır. Ancak Boole ifadesi kullanarak bu sonucu çok daha verimli bir şekilde elde etmek mümkündür.

Aşağıda tablo ifadesi yerine Boole ifadesini kullanan geliştirilmiş ölçü tanımı verilmiştir. [KEEPFILTERS](/dax/keepfilters-function-dax) DAX işlevi **Color** sütununa eklenmiş mevcut tüm filtrelerin korunmasını ve bunların üzerine yazılmamasını güvence altına alır.

```dax
Red Sales =
CALCULATE(
    [Sales],
    KEEPFILTERS('Product'[Color] = "Red")
)
```

Mümkün olduğunca filtre bağımsız değişkenlerini Boole ifadeleri olarak geçirmeniz önerilir. Bunun nedeni, içeri aktarılan model tablolarının bellek içi sütun depoları olmasıdır. Bunlar, sütunları bu şekilde filtrelemek üzere özel olarak iyileştirilmiştir.

Ancak filtre bağımsız değişkeni olarak kullanılan Boole ifadeleri için geçerli olan kısıtlamalar vardır. Kısıtlamalar şunlardır:

- Sütunlar, diğer sütunlarla karşılaştırılamaz
- Ölçüye başvuru yapılamaz
- İç içe CALCULATE işlevleri kullanılamaz
- Bir tabloyu tarayan veya döndüren işlevler kullanılamaz

Bu da daha karmaşık filtre gereksinimleri için tablo ifadelerini kullanmanız gerektiği anlamına gelir.

Şimdi farklı bir ölçü tanımını inceleyelim.

```dax
High Margin Product Sales =
CALCULATE(
    [Sales],
    FILTER(
        'Product',
        'Product'[ListPrice] > 'Product'[StandardCost] * 2
    )
)
```

_Kar marjı yüksek ürünler_, liste fiyatı standart maliyetinin iki katından fazla olan ürünlerdir. Bu örnekte FILTER işlevi kullanılmalıdır. Bunun nedeni, filtre ifadesinin Boole ifadesi için fazla karmaşık olmasıdır.

Burada bir örnek daha vardır. Bu kez satışların hesaplanması gerekir ancak yalnızca kar elde edilen aylar dahil edilmelidir.

```dax
Sales for Profitable Months =
CALCULATE(
    [Sales],
    FILTER(
        VALUES('Date'[Month]),
        [Profit] > 0)
    )
)
```

Bu örnekte FILTER işlevi de kullanılmalıdır. Bunun nedeni, **Profit** ölçüsünün değerlendirilerek kar elde edilmeyen hariç tutulmasının gerekmesidir. Filtre bağımsız değişkeni olarak kullanılması durumunda Boole ifadelerinde ölçü kullanılamaz.

## <a name="recommendations"></a>Öneriler

En iyi performans için mümkün olduğunda filtre bağımsız değişkeni olarak Boole ifadelerini kullanmanız önerilir.

Bu nedenle FILTER işlevi yalnızca gerekli olduğunda kullanılmalıdır. Bunu, karmaşık filtreye sahip sütun karşılaştırmaları gerçekleştirmek için kullanabilirsiniz. Bu sütun karşılaştırmaları şunları içerebilir:

- Ölçüler
- Diğer sütunlar
- [OR](/dax/or-function-dax) DAX işlevini veya OR mantıksal işlecini (||) kullanma

## <a name="next-steps"></a>Sonraki adımlar

Bu makale hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

- [Veri Çözümleme İfadeleri (DAX) Başvurusu](/dax/)
- [Filtre işlevleri (DAX)](/dax/filter-function-dax)
- Öğrenme yolu: [Power BI Desktop’ta DAX kullanma](/learn/paths/dax-power-bi/)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
- Önerileriniz mi var? [Power BI'ı geliştirmek için fikirlerinizi paylaşın](https://ideas.powerbi.com)