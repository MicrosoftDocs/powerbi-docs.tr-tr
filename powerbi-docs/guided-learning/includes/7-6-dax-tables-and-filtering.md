---
ms.openlocfilehash: 5bc0d3bbfb2c2b67b56e6406646f6131a360b97d
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "73800201"
---
**DAX** ile Excel formül dili arasındaki tek büyük fark DAX'ın tek bir değerle sınırlı kalmak yerine *tabloların tamamını* ifadeler arasında geçirmenize olanak tanımasıdır. Etkili bir özellik olarak DAX, tabloları ifadelerinde filtrelemenize ve ardından, filtrelenen değer kümesiyle çalışmanızı sağlar.

![](media/7-6-dax-tables-and-filtering/dax-tables-filtering_1.png)

DAX ile tamamen yeni, hesaplanmış tablolar oluşturabilir ve ardından bunların üzerinde diğer herhangi bir tabloda olduğu şekilde (veri modelinizdeki diğer tablolar ile bunların arasında ilişki kurma da dahil) işlem yapabilirsiniz.

## <a name="dax-table-functions"></a>DAX tablo işlevleri
DAX aşağıdakiler de dahil olmak üzere zengin bir **tablo** işlevleri kümesine sahiptir:

* FILTER
* ALL
* VALUES
* DISTINCT
* RELATEDTABLE

Bu işlevler değer yerine eksiksiz bir tablo döndürür. Genellikle, döndürülen tabloyu son değer olarak kullanmak yerine, **table** işlevinin sonuçlarını sonraki çözümleme işlemlerinde daha kapsamlı bir ifadenin parçası olarak kullanırsınız. Bir tablo işlevi kullandığınızda sonuçların, kendilerine ait sütunların ilişkilerini devralacağını unutmayın.

Her işlev bir tablo kullandığı ve döndürdüğü sürece ifadenizde tablo işlevlerini karıştırabilirsiniz. Örneğin, aşağıdaki DAX ifadesini inceleyin:

    FILTER (ALL (Table), Condition)

Bu ifade *Tablo*'nun tamamına filtre ekleyerek geçerli olan tüm filtre içeriğini yok sayar.

DISTINCT işlevi, geçerli bağlamda da görünür halde olan bir sütunun benzersiz değerlerini döndürür. Bu nedenle yukarıdaki DAX ifadesi örneğinde, bu ifadede **ALL** işlevinin kullanılması filtreleri yok sayarken **ALL** işlevinin **DISTINCT** ile değiştirilmesi filtreleri korur.

## <a name="counting-values-with-dax"></a>DAX ile değerleri sayma
Aşağıda Power BI rapor oluşturucularının yaygın olarak yanıt aradığı bir soru verilmiştir:

* Bu sütunda kaç değer var?

Bu, önünüzde bir tablo görüntüleniyorken yanıtlanması kolay bir soru olabilir ancak DAX dilinde, özellikle de tablolar arasında bir ilişki söz konusu olduğunda farklı bir yaklaşım sergilenir.

Örneğin, Power BI ve DAX düzgün şekilde çapraz olarak dizine alınmamış değerler içerir. DAX, gelen ilişki bozuksa her alanda boşluklar içeren ilgili tabloya yeni bir satır ekler ve bilgi tutarlılığı sağlamak için bu yeni satırı, dizinden çıkarılmış satıra bağlar. İşleviniz, genellikle **ALL** işlevi kullanılırken olduğu gibi boş satırlar içeriyorsa bu boş satırlar söz konusu sütun için döndürülen değer sayısına dahil edilir.

Ayrıca DAX işlevlerini kullanarak tamamen hesaplanmış tablolar da oluşturabilirsiniz. DAX kullanılarak oluşturulmuş tablolarda **NAME** ve **TABLE** işlevleri gereklidir. Hesaplanmış tablolar, ilişki oluşturma da dahil olmak üzere diğer tüm tablolar gibi kullanılabilir.

> Video içeriğini sağladığı için [SQLBI'dan Alberto Ferrari](https://www.sqlbi.com/learning-dax)'ye teşekkür ederiz
> 
> 

