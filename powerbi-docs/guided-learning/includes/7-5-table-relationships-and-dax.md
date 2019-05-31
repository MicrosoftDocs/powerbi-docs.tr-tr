---
ms.openlocfilehash: cd6ea6fd52f929e2cd254214cf0e8c96e858f6c2
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "61273628"
---
Power BI, tamamen farklı veri kaynaklarından gelen tablolar da dahil olmak üzere birden çok tablo arasında ilişkiler oluşturmanızı sağlar. Power BI Desktop'ın **İlişkiler** görünümünde herhangi bir veri modeli için bu ilişkileri görebilirsiniz.

![](media/7-5-table-relationships-and-dax/dax-relationships_1.png)

## <a name="dax-relational-functions"></a>İlişkisel DAX işlevleri
DAX, oluşturulmuş ilişkiler bulunan tablolarla etkileşime geçmenizi sağlayan **ilişkisel işlevler** içerir.

DAX işlevlerini kullanarak bir sütunun değerini veya bir ilişkideki tüm satırları döndürebilirsiniz.

Örneğin, **RELATED** işlevi ilişkileri izleyip bir sütunun değerini, **RELATEDTABLE** işlevi ise ilişkileri izleyip yalnızca ilgili satırları içerecek şekilde filtrelenmiş bir tablonun tamamını döndürür.

![](media/7-5-table-relationships-and-dax/dax-relationships_2.png)

**RELATED** işlevi *çoğa bir* ilişkiler üzerinde, **RELATEDTABLE** işlevi ise *bire çok* ilişkiler üzerinde çalışır.

Birden çok tabloda değerler içeren ifadeler oluşturmak için ilişkisel işlevleri kullanabilirsiniz. DAX, ilişki zincirinin uzunluğu fark etmeksizin bu işlevlerle bir sonuç döndürür.

> Video içeriğini sağladığı için [SQLBI'dan Alberto Ferrari](http://www.sqlbi.com/learning-dax)'ye teşekkür ederiz
> 
> 

