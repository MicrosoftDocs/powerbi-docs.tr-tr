---
ms.openlocfilehash: 3966521d158c244487638be4117f98ea570e1f28
ms.sourcegitcommit: a5853ef44ed52e80eabee3757bb6887fa400b75b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73800199"
---
Size **DAX**'ı tanıtmak için tasarlanan Power BI **Destekli Öğrenme** bölümüne hoş geldiniz.

**Veri Çözümleme İfadeleri** anlamına gelen **DAX**, Power BI genelinde kullanılan (arka planda Power BI tarafından da kullanılır) formül dilidir. DAX, Power Pivot ve SSAS Tablosu gibi diğer Microsoft tekliflerinde de yer alır ancak bu Destekli Öğrenme konularında, DAX dilinin nasıl kullanıldığına ve Power BI'da sizin tarafınızdan nasıl kullanılabileceğine odaklanılmıştır.

## <a name="dax-and-this-guided-learning-video-series"></a>DAX ve Destekli Öğrenme video serisi
Bu **Destekli Öğrenme** bölümünde; ünlü DAX uzmanı [Alberto Ferrari](https://www.sqlbi.com/learning-dax) tarafından açıklandığı (ve sayısız deneyimle öğrenildiği) şekilde DAX ile ilgili temel kavramları ve bilgileri (DAX üzerinde düşünme, DAX dilinin çalışma şekli ve en kullanışlı özellikler) anlatmak amaçlanmıştır.

![Alberto Ferrari'nin portresi](media/7-1-intro-to-dax/intro_dax_6_alberto_ferrari.png)

**DAX** ile ilgili bu **Destekli Öğrenme** bölümündeki videolarda temel DAX bilgileri, DAX formül dilinin nasıl çalıştığına ilişkin bir bakış açısıyla anlatılmaktadır. Bu, sıfırdan DAX formülleri oluştururken kullanışlı olmakla birlikte **Sorgu Düzenleyicisi**'nde sorgular oluşturduğunuz sırada Power BI'ın bu tür DAX formüllerini nasıl oluşturduğunu anlamaya yönelik olarak da oldukça faydalıdır.

## <a name="in-this-video---introduction-to-dax"></a>Bu videoda - DAX'a giriş
DAX, basit ve kolay kavramlara sahip olsa da güçlü bir dildir. DAX dilinde bazı benzersiz programlama kavramları ve desenler kullanılır. Bu da onun tam olarak kullanılmasını ve anlaşılmasını zor hale getirebiliyor. Geleneksel dil öğrenme biçimleri DAX diline yönelik en iyi yaklaşım olmayabilir. Bu nedenle bu videoda, daha sonraki Power BI çalışmalarınızda size yardımcı olacak kavramların ve teorinin açıklanması amaçlanmıştır.

DAX *işlevsel bir dildir*. Başka bir deyişle, yürütülen kodun tamamı bir işlevde barındırılır.

DAX dilinde işlevler, iç içe geçmiş diğer işlevleri, koşullu ifadeleri ve değer başvurularını içerebilir. DAX'ta yürütme işlemi en içteki işlevden veya parametreden başlar ve dışarı doğru devam eder. Power BI'da DAX formülleri tek bir satır olarak yazılır. Bu nedenle işlevlerinizi doğru bir şekilde biçimlendirmek okunabilirlik açısından önemlidir.

Tablolarla çalışmak üzere tasarlanan DAX iki birincil veri türü içerir: **Sayısal** ve **Diğer**. **Sayısal** veri türü *tamsayıları*, *ondalıkları* ve *para birimlerini* içerebilir. **Diğer** veri türünde ise *dizeler* ve *ikili nesneler* yer alabilir. Bu nedenle, DAX işlevinizi bir sayı türü üzerinde çalışacak şekilde oluşturmanız halinde işlevinizin diğer tüm Sayısal veriler üzerinde de çalışacağından emin olabilirsiniz.

DAX, işleç aşırı yüklemesini kullanır. Böylece, hesaplamalarınızda veri türlerini karıştırabilir ve sonuçların girişlerde kullanılan veri türlerine göre değişmesini sağlayabilirsiniz. Dönüştürmenin otomatik olarak gerçekleşmesi, Power BI'da çalışırken kullandığınız sütunların veri türlerini bilmeniz gerekmediğinin yanı sıra dönüştürme işleminin belirli durumlarda beklenmedik şekillerde sonuçlanabileceği anlamına da gelir. İşleçlerinizin beklendiği gibi çalışmasını sağlamak için, kullandığınız verileri anlamakta yarar vardır.

Power BI'da sıklıkla kullanacağınız bir veri türü bulunur: **DateTime**. **Tarih/Saat**, hem tamsayı hem de ondalık kısımları içeren bir kayan noktalı değer olarak depolanır. Tarih/Saat, 1 Mart 1900 tarihinden sonraki herhangi bir zaman aralığına ilişkin hesaplamalar için tutarlı bir şekilde kullanılabilir.

> Video içeriğini sağladığı için [SQLBI'dan Alberto Ferrari](https://www.sqlbi.com/learning-dax/?utm_source=powerbi&utm_medium=marketing&utm_campaign=after-summit)'ye teşekkür ederiz
> 
> 

