---
title: Soru-Cevap özelliği ile soru sormaya ilişkin ipuçları ve püf noktaları
description: Power BI'daki Soru-Cevap özelliği ile soru sormaya ilişkin ipuçları ve püf noktaları
author: mihart
ms.reviewer: Mohammad
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: how-to
ms.date: 03/11/2020
ms.author: mihart
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 891795eec35fbead6d66370d59db511917d4eb26
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85235445"
---
# <a name="tips-for-asking-questions-in-power-bi-qa"></a>Power BI Soru-Cevap özelliği ile soru sormaya ilişkin ipuçları

[!INCLUDE[consumer-appliesto-yyny](../includes/consumer-appliesto-yyny.md)]

## <a name="words-and-terminology-that-qa-recognizes"></a>Soru-Cevap tarafından tanınan sözcükler ve terminoloji
Bu sayfadaki bu anahtar sözcük listesi çok kapsamlı değildir.  Power BI'ın bir anahtar sözcüğü tanıyıp tanımadığını görmenin en iyi yolu, anahtar sözcüğü soru kutusuna yazarak deneme yapmaktır.  Sözcük veya terim gri gösteriliyorsa, Power BI onu tanımıyor demektir.

Aşağıdaki listede geniş zaman kullanılmaktadır, ancak çoğu durumda tüm fiil zamanları tanınır. Örneğin "is" sözcüğü: **are**, **was**, **were**, **will be**, **have**, **has**, **had**, **will have**, **has got**, **do**, **does**, **did** sözcüklerini de kapsar.  "sort" sözcüğü ise **sorted** ve **sorting** sözcüklerini kapsar.  Bunun yanı sıra Power BI, bir sözcüğün tekil ve çoğul hallerini de tanır ve kapsar. 

> [!NOTE]
> Soru-Cevap aynı zamanda [iPad, iPhone ve iPod touch cihazlarıyla iOS için Microsoft Power BI uygulamasında](mobile/mobile-apps-ios-qna.md) da kullanılabilir.
>  


|Kategori  |Anahtar Sözcükler  |Sütun3  |
|---------|---------|---------|
|**Toplamlar**     | total, sum, amount, number, quantity, count, average, most, least, fewest, largest, smallest, highest, biggest, maximum, max, greatest, lowest, littlest, minimum, min          |
|     |         |         
**Makaleler**     |  a, an, the              |
|     |         |         
|**Boş ve Boole**     |   blank, empty, null, prefixed with "non" veya "non-" ön ekli, boş dize, boş metin, true, t, false, f          |
|     |         |         |
|**Karşılaştırmalar**     |   vs, versus, compared to, compared with            |
|     |         |         |
|**Bağlaçlar**     |  and, or, each of, with, versus, &, and, but, nor, along with, in addition to       |         
|          |         |
|**Karşıtlıklar**     |  Soru-Cevap hemen hemen tüm karşıtlıkları tanır, deneyin.  Bazı örnekler şunlardır: didn't, haven't, he'd, he's, isn't, it's, she'll, they'd, weren't, who's, won't, wouldn't          |
|        |         |
|**Tarihler**     |       Power BI, çoğu tarih terimini (day, week, month, year, quarter, decade vb.) ve farklı biçimde yazılan birçok tarihi tanır (aşağıdakilere bakın). Power BI ayrıca şu anahtar sözcükleri de tanır: MonthName, Days 1-31, decade. Örnekler: January 3rd of 1995, January 3rd 1995, jan 03 1995, 3 Jan 1995, the 3rd of January, January 1995, 1995 January, 1995-01, 01/1995, ay adları         |
|        |         |
|**Göreli tarihler**     |   today, right now, current time, yesterday, tomorrow, the current, next, the coming, last, previous, ago, before now, sooner than, after, later than, from, at, on, from now, after now, in the future, past, last, previous, within, in, over, N days ago, N days from now, next, once, twice.|
|    |  Örnek: count of orders in the past 6 days. (son 6 güne ait siparişlerin sayısı)  |            |
|        |         |
|**Eşitlik (Aralık)**     |   in, equal to, =, after, is more than, in, between, before  |
|  |Örnekler: Order year is before 2012? (sipariş yılı 2012'den önce olanlar) Price equals between 10 and 20? (fiyatı 10 ile 20 arasında olanlar) Is the age of John greater than 40? (John'un yaşı 40'tan fazla mı?) Total sales in 200-300? (toplam satış değeri 200-300 arasında olanlar)              |
|        |         |
|**Eşitlik (Değer)**     |   is, equal, equal to, in, of, for, within, is in, is on |
|   | Örnekler: Hangi ürünler yeşildir? Order date equals 2012. (sipariş tarihi 2012 olanlar) Is the age of John 40? (John'un yaşı 40 mı?) Total sales that aren't equal to 200? (toplam satış değeri 200'den farklı olanlar) Order date of 1/1/2016. (sipariş tarihi 01/01/2016 olanlar) 10 in price? (fiyat değeri 10 olanlar) Green for color? (yeşil renkte olanlar) 10 in price? (fiyat değeri 10 olanlar)              |
|        |         |
|**Adlar**     |       Veri kümesindeki bir sütun "name" sözcüğünü içeriyorsa (örneğin, EmployeeName), Soru-Cevap bu sütundaki değerlerin adlar olduğunu anlar. "Which employees are named robert" (hangi çalışanların adı Robert'tır?) gibi sorular sorabilirsiniz.          |
|        |         |
**Zamirler**  | he, him, himself, his, she, herself, her, hers, it, itself, its, they, their, them, themselves, theirs, this, these, that, those
|**Sorgu komutları**     |    sorted, sort by, direction, group, group by, by, show, list, display, give me, name, just, only, arrange, rank, compare, to, with, against, alphabetically, ascending, descending, order             |
|        |         |
|**Aralık**     |      greater, more, larger, above, over, >, less, smaller, fewer, below, under, <,  at least, no less than, >=, at most, no more than, <=, in, between, in the range of, from, later, earlier, sooner, after, on, at, later than, after, since, starting with, starting from, ending with           |
|        |         |
**Saatler**  |am, pm, o'clock, noon, midnight, hour, minute, second, hh:mm:ss  |
|  |  Örnekler: 10 pm, 10:35 pm, 10:35:15 pm, 10 oclock, noon, midnight, hour, minute, second.  |
|  |  |
|**Üst N**     |     (düzen, sıralama): top, bottom, highest, lowest, first, last, next, earliest, newest, oldest, latest, most recent, next            |
|        |         |
|**Görsel türleri**     |  Power BI'da yerleşik olarak bulunan tüm görsel türleri.  Görsel Öğeler bölmesinde seçenek olarak mevcut olan tüm görselleri sorunuza ekleyebilirsiniz.  Bu kurala yönelik tek istisna, Görsel Öğeler bölmesine elle eklemiş olduğunuz [Power BI görselleridir](../developer/visuals/power-bi-custom-visuals.md).  |
|  |  Örnek: show districts by month and sales total as bar chart (bölgeleri aya ve satış toplamına göre çubuk grafik olarak göster)               |
|        |         |
|**Wh (ilişki, belirtili)**  | when, where, which, who, whom, how many, how much, how many times, how often, how frequently, amount, number, quantity, how long, what                |

## <a name="qa-helps-you-phrase-the-question"></a>Soru-Cevap soruyu oluşturmanıza yardımcı olur
Soru-Cevap sorulan soruyu anlamak ve yanıtlamak için elinden gelenin en iyisini yapar. Çeşitli yollarla anlamaya çalışır. Bu ifadelerin tümünde işlemi tam olarak veya kısmen kabul edebilir ya da hiç etmeyebilirsiniz. Siz sorunuzu yazarken Soru-Cevap:

* Sözcükleri ve soruları otomatik olarak tamamlar. Tanınan sözcükleri, depolanan soruları ve geçerli yanıtlar döndüren önceden kullanılmış soruları otomatik olarak tamamlama gibi çeşitli stratejiler kullanır. Birden fazla otomatik tamamlama seçeneği varsa, bunlar açılan listede sunulur.
* Yazımı düzeltir.
* Yanıtın önizlemesini görsel biçiminde sunar. Görsel siz soruyu yazdıkça ve düzenledikçe güncelleştirilir. (Enter tuşuna basmanızı beklemez.)
* İmleci soru kutusuna tekrar taşıdığınızda, temel alınan veri kümelerinden elde edilen değişiklik terimlerini önerir.
* Temel alınan veri kümelerindeki verilere göre soruyu yeniden yazar. Soru-Cevap, kullandığınız sözcükleri temel alınan veri kümelerindeki eş anlamlı sözcüklerle değiştirir. Farklı şekilde ifade edilen metni okuyarak Soru-Cevap'ın sorunuzu anlayıp anlamadığını belirleyebilirsiniz. 
* anlamadığı sözcüklere bir çift alt çizgi ekler.
* anladığı sözcüklere bir tek alt çizgi ekler.
* teriminiz bulunamadığında veya sorunuz sonuç döndürmediğinde rapor veya pano sahibiyle iletişim kurmanıza olanak tanır.

## <a name="dont-stop-now"></a>Durmayın
Soru-Cevap, sonuçlarınızı görüntüledikten sonra konuşmaya devam edin! Daha fazla içgörü elde etmek için görselin ve Soru-Cevap’ın etkileşimli özelliklerini kullanın.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI'daki Soru-Cevap](end-user-q-and-a.md) özelliğine geri dönün  

[Power BI - Temel Kavramlar](end-user-basic-concepts.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)

