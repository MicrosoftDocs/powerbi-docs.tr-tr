---
ms.openlocfilehash: 06ee6ad7ade46d811c6340d905150c6dd3810c55
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "61273627"
---
DAX ile verilerinizi şekillendirmek, biçimlendirmek veya başka şekilde analiz etmek için kullanabileceğiniz birçok işlev vardır. Bu işlevler bir dizi kategoride gruplandırılabilir:

* **Toplama** işlevleri
* **Sayma** işlevleri
* **Mantıksal** işlevler
* **Bilgi** işlevleri
* **Metin** işlevleri
* **Tarih** işlevleri

Excel ile benzer şekilde, Power BI Desktop **Formül Çubuğu**'na formülünüzü yazmaya başladığınızda, kullanılabilir işlevlerin bir listesi görüntülenir. Bu liste, hangi işlevi seçmek istediğinizi belirlemenize yardımcı olur. Klavyenizdeki **yukarı** ve **aşağı** ok tuşlarını kullanarak mevcut işlevlerden herhangi birini seçebilir ve kısa bir açıklama görüntüleyebilirsiniz.

Power BI o ana kadar yazdığınız harflerle eşleşen işlevleri görüntüler. *S* yazmanız halinde yalnızca *S* ile başlayan işlevler listelenir. *Su* yazarsanız yalnızca adında *Su* harf dizisini *içeren* işlevler listelenir. (İşlevlerin *Su* ile başlaması gerekmez; bu harf dizisini içermesi yeterlidir.)

![](media/7-3-dax-functions/dax-functions_1.png)

Bu şekilde deneme amaçlı olarak DAX dilini kolayca kullanabilir ve Power BI'da kullanılabilen çeşitli DAX işlevlerinden her birini bulabilirsiniz. Tek yapmanız gereken yazmaya başlamaktır. Power BI size eşlik eder.

DAX formülü girmeye başlamayı öğrendiğimize göre bu işlev kategorilerinden her birine sırayla göz atalım.

## <a name="aggregation-functions"></a>Toplama işlevleri
DAX, aşağıdaki yaygın olarak kullanılan işlevler de dahil olmak üzere bir çok **toplama** işlevi içerir:

* SUM
* AVERAGE
* MIN
* MAX
* SUMX (ve diğer *X* işlevleri)

Yalnızca sayısal sütunlarda çalışan bu işlevleri genellikle aynı anda yalnızca bir sütunda toplama yapmak için kullanabilirsiniz.

Ancak, **X** ile biten özel toplama işlevleri (**SUMX** gibi) ile birden çok sütunda çalışılabilir. Bu işlevler tablonun tamamında yinelenir ve ifadeyi her bir satır için değerlendirir.

## <a name="counting-functions"></a>Sayma işlevleri
DAX'taki sık kullanılan **sayma** işlevleri şunları içerir:

* COUNT
* COUNTA
* COUNTBLANK
* COUNTROWS
* DISTINCTCOUNT

Bu işlevlerle benzersiz değerler, boş olmayan değerler ve tablo satırları gibi farklı öğeler sayılır.

## <a name="logical-functions"></a>Mantıksal işlevler
DAX'taki **mantıksal** işlev koleksiyonu şunları içerir:

* AND
* OR
* NOT
* IF
* IFERROR

Bu özel işlevler *işleçler* ile de ifade edilebilir. Örneğin; **AND**, DAX formülünüzde **&&** olarak yazılabilir (değiştirilebilir).

Formülünüzde ikiden fazla koşula ihtiyacınız olduğunda işleçleri ( **&&** gibi) kullanabilirsiniz ancak aksi halde, DAX kodunuzun okunabilirliği için işlevin adını (**AND** gibi) doğrudan kullanmak en iyi yöntemdir.

## <a name="information-functions"></a>Bilgi işlevleri
DAX'taki **Bilgi** işlevleri şunları içerir:

* ISBLANK
* ISNUMBER
* ISTEXT
* ISNONTEXT
* ISERROR

Bu işlevlerden belirli durumlarda faydalanabileceğiniz gibi, veri türünü sağlamaları için bu işlevlere bağlı kalmak yerine sütunlarınızın veri türlerini önceden bilmekte de yarar vardır.

DAX'ta hem değerleri *toplamak* hem de *karşılaştırmak* için **MAX** ve **MIN** işlevleri kullanılır.

## <a name="text-functions"></a>Metin işlevleri
DAX'taki **metin** işlevleri şunları içerir:

* CONCATENTATE
* REPLACE
* SEARCH
* UPPER
* FIXED

Bu **metin** işlevleri Excel'de aynı ada sahip işlevlerle oldukça benzer şekilde çalışır. Bu nedenle Excel'de metin işlevlerinin işlenme biçimine aşinaysanız bir adım öndesiniz demektir. Aksi halde, dilediğiniz zaman bu işlevleri Power BI'da deneme amaçlı olarak kullanabilir ve davranışları hakkında daha fazla bilgi edinebilirsiniz.

## <a name="date-functions"></a>Tarih işlevleri
DAX şu **Tarih** işlevlerini içerir:

* DATE
* HOUR
* NOW
* EOMONTH
* WEEKDAY

Bu işlevler *tarih* değerlerindeki bilgileri hesaplamak ve ayıklamak için kullanılabilir ancak bir veri tablosunun kullanıldığı akıllı zaman gösterimi için geçerli değildir.

> Video içeriğini sağladığı için [SQLBI'dan Alberto Ferrari](http://www.sqlbi.com/learning-dax)'ye teşekkür ederiz
> 
> 

