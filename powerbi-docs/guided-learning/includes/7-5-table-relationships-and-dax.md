---
ms.openlocfilehash: 679c3e8c3d94c93899e9dcfae1e57f4b678fb218
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "73800198"
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

> Video içeriğini sağladığı için [SQLBI'dan Alberto Ferrari](https://www.sqlbi.com/learning-dax)'ye teşekkür ederiz
> 
> 

