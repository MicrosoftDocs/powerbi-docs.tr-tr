---
title: "Power BI'daki Soru-Cevap özelliği ile soru sormaya ilişkin ipuçları ve püf noktaları"
description: "Power BI'daki Soru-Cevap özelliği ile soru sormaya ilişkin ipuçları ve püf noktaları"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/18/2018
ms.author: jastru
ms.openlocfilehash: 5d9b65448fced78bf3eb4ed02c84e1561d2d209a
ms.sourcegitcommit: d803e85bb0569f6b357ba0586f5702c20d27dac4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/19/2018
---
# <a name="tips-for-asking-questions-in-power-bi-qa"></a>Power BI Soru-Cevap özelliği ile soru sormaya ilişkin ipuçları
## <a name="words-and-terminology-that-qa-recognizes"></a>Soru-Cevap tarafından tanınan sözcükler ve terminoloji
Anahtar sözcükler listesi kapsamlı değildir.  Power BI'ın bir anahtar sözcüğü tanıyıp tanımadığını görmenin en iyi yolu, anahtar sözcüğü soru kutusuna yazarak deneme yapmaktır.  Sözcüğün veya terimin gri olması, Power BI tarafından geçerli bağlamda veya hiçbir bağlamda tanınmadığı anlamına gelir.

Aşağıdaki listede geniş zaman kullanılmaktadır, ancak çoğu durumda tüm fiil zamanları tanınır. Örneğin, "is" sözcüğü; are, was, were, will be, have, has, had, will have, has got, do, does, did sözcüklerini de kapsar.  "sort" sözcüğü ise sorted ve sorting sözcüklerini kapsar.  Bunun yanı sıra Power BI, bir sözcüğün tekil ve çoğul hallerini de tanır ve kapsar. Örneğin Power BI, "year" ve "years" sözcüklerini tanır.

> [!NOTE]
> Soru-Cevap [iPad, iPhone ve iPod touch cihazlarıyla iOS için Microsoft Power BI uygulamasında](mobile-apps-ios-qna.md) da kullanılabilir.
> 
> 

Bir veri kümesinin sahibiyseniz müşterileriniz için Soru-Cevap sonuçlarını iyileştirmek üzere ifadeler ve eş anlamlı sözcükler ekleyin.

**Toplamalar**: total, sum, amount, number, quantity, count, average, most, least, fewest, largest, smallest, highest, biggest, maximum, max, greatest, lowest, littlest, minimum, min

**Artikeller**: a, an, the

**Boş ve Boole**: blank, empty, null, prefixed with "non" or "non-", empty string, empty text, true, t, false, f

**Karşılaştırmalar**: vs, versus, compared to, compared with

**Bağlaçlar**: and, or, each of, with, versus, &, and, but, nor, along with, in addition to

**Kısaltmalar**: Soru-Cevap hemen hemen tüm kısaltmaları tanır, deneyin.  Bazı örnekler şunlardır: didn't, haven't, he'd, he's, isn't, it's, she'll, they'd, weren't, where'll, who's, won't, wouldn't.

**Tarihler**: Power BI, çoğu tarih terimini (day, week, month, year, quarter, decade vb.) ve farklı biçimde yazılan birçok tarihi tanır (aşağıdakilere bakın). Power BI ayrıca şu anahtar sözcükleri de tanır: MonthName, Days 1-31, decade.

Örnekler: January 3rd of 1995, January 3rd 1995, jan 03 1995, 3 Jan 1995, the 3rd of January, January 1995, 1995 January, 1995-01, 01/1995, ay adları.

**Göreli tarihler**: today, right now, current time, yesterday, tomorrow, the current, next, the coming, last, previous, ago, before now, sooner than, after, later than, from, at, on, from now, after now, in the future, past, last, previous, within, in, over, N days ago, N days from now, next, once, twice.

Örnek: count of orders in the past 6 days. (son 6 güne ait siparişlerin sayısı)

**Eşitlik (Aralık)**: in, equal to, =, after, is more than, in, between, before

Örnekler: Order year is before 2012? (sipariş yılı 2012'den önce olanlar) Price equals between 10 and 20? (fiyatı 10 ile 20 arasında olanlar) Is the age of John greater than 40? (John'un yaşı 40'tan fazla mı?) Total sales in 200-300? (toplam satış değeri 200-300 arasında olanlar)

**Eşitlik (Değer)**: is, equal, equal to, in, of, for, within, is in, is on

Örnekler: Which products are green? (Hangi ürünler yeşil?) Order date equals 2012. (sipariş tarihi 2012 olanlar) Is the age of John 40? (John'un yaşı 40 mı?) Total sales that is not equal to 200? (toplam satış değeri 200'den farklı olanlar) Order date of 1/1/2016. (sipariş tarihi 01/01/2016 olanlar) 10 in price? (fiyat değeri 10 olanlar) Green for color? (yeşil renkte olanlar) 10 in price? (fiyat değeri 10 olanlar)

**Adlar**: Veri kümesindeki bir sütun, "name" ifadesini içeriyorsa (ör. EmployeeName) Soru-Cevap, söz konusu sütundaki değerlerin ad olduğunu anlar ve bu sayede "which employees are named robert" (Hangi çalışanların adı Robert?) gibi sorular sorabilirsiniz.

**Zamirler**: he, him, himself, his, she, herself, her, hers, it, itself, its, they, their, them, themselves, theirs, this, these, that, those

**Sorgu komutları**: sorted, sort by, direction, group, group by, by, show, list, display, give me, name, just, only, arrange, rank, compare, to, with, against, alphabetically, ascending, descending, order

**Aralık**: greater, more, larger, above, over, >, less, smaller, fewer, below, under, <,  at least, no less than, >=, at most, no more than, <=, in, between, in the range of, from, later, earlier, sooner, after, on, at, later than, after, since, starting with, starting from, ending with

**Zamanlar**: am, pm, o'clock, noon, midnight, hour, minute, second, hh:mm:ss

Örnekler: 10 pm, 10:35 pm, 10:35:15 pm, 10 oclock, noon, midnight, hour, minute, second.

**Üst N** (düzen, sıralama): top, bottom, highest, lowest, first, last, next, earliest, newest, oldest, latest, most recent, next

**Görsel türleri**: Power BI'da yerleşik olarak bulunan tüm görsel türleri.  Görsel Öğeler bölmesinde seçenek olarak mevcut olan tüm görselleri sorunuza ekleyebilirsiniz.  Bu konudaki tek istisna, Görsel Öğeler bölmesine elle eklemiş olduğunuz [özel görsellerdir](power-bi-custom-visuals.md).

Örnek: show districts by month and sales total as bar chart (bölgeleri aya ve satış toplamına göre çubuk grafik olarak göster)

**Wh (ilişki, belirtili)**: when, where, which, who, whom, how many, how much, how many times, how often, how frequently, amount, number, quantity, how long, what

## <a name="qa-helps-you-phrase-the-question"></a>Soru-Cevap soruyu oluşturmanıza yardımcı olur
Soru-Cevap, yanıtın sorulan soruyu mümkün olduğu kadar doğru şekilde yansıtmasını sağlamaya çalışır. Bunu birkaç şekilde yapar. Bunların tümünde işlemi tam olarak veya kısmen kabul edebilir ya da hiç etmeyebilirsiniz. Siz sorunuzu yazarken Soru-Cevap:

* Sözcükleri ve soruları otomatik olarak tamamlar. Tanınan sözcükleri, temel alınan çalışma kitaplarına yönelik sık kullanılan soruları ve geçerli yanıtlar döndüren önceden kullanılmış soruları otomatik olarak tamamlama gibi çeşitli stratejiler kullanır. Birden fazla otomatik tamamlama seçeneği mevcutsa bunlar açılan listede sunulur.
* Yazımı düzeltir.
* Yanıtın önizlemesini görselleştirme biçiminde sunar. Görselleştirme siz soruyu yazdıkça ve düzenledikçe güncelleştirilir. (Enter tuşuna basmanızı beklemez.)
* İmleci soru kutusuna tekrar taşıdığınızda, temel alınan veri kümelerinden elde edilen değişiklik terimlerini otomatik olarak önerir.
* Temel alınan veri kümelerindeki verilere göre soruyu yeniden yazar. Soru-Cevap, kullandığınız sözcükleri temel alınan veri kümelerindeki eş anlamlı sözcüklerle değiştirir ve bu da, Soru-Cevap özelliğinin sorunuzu anladığından emin olmanıza yardımcı olur.
* Anlamadığı sözcükleri gri renkte gösterir.

## <a name="combine-results-from-more-than-one-dataset"></a>Birden fazla veri kümesinden alınan sonuçları birleştirme
Power BI'ın en güçlü özelliklerinden biri de farklı veri kümelerine ait verileri birleştirebilmesidir.  Bu nedenle, sorularınızı tek bir veri kümesiyle sınırlamayın; birden fazla veri kümesinden veri alan sorular sorun. Örneğin, panom Perakende Analizi Örneği'nden ve il nüfusu veri kümesinden kutucuklar içeriyorsa *show count of stores by state population as bar chart descending* (il nüfusuna göre mağazaların sayısını azalan düzende çubuk grafik olarak göster) isteğinde bulunabilirim.

## <a name="dont-stop-now"></a>Durmayın
Soru-Cevap, sonuçlarınızı görüntüledikten sonra konuşmaya devam edin! Daha fazla öngörü elde etmek için görselleştirmenin ve Soru-Cevap'ın etkileşimli özelliklerini kullanın.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI'daki Soru-Cevap](power-bi-q-and-a.md) özelliğine geri dönün  

[Power BI - Temel Kavramlar](service-basic-concepts.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

