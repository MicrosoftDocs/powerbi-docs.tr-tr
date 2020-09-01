---
title: Doğal dil özelliğini içeri aktarma, Live Connect ve Direct Query ile kullanma
description: Bu makalede, Soru-Cevap özelliğinin Power BI’da sunulan farklı veri kaynağı türleriyle nasıl çalıştığını inceleyeceğiz. Dizin oluşturma ve önbelleğe alma kavramlarını da ele alacağız.
author: mohaali
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/19/2020
ms.author: mohaali
ms.openlocfilehash: 85ecc5adc55daee86922c39e417db1cac5ba4a52
ms.sourcegitcommit: 0f807d3c74e5202b6e6a95fad49f2787928b9613
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/21/2020
ms.locfileid: "88706244"
---
# <a name="use-natural-language-with-import-live-connect-and-direct-query"></a>Doğal dil özelliğini içeri aktarma, Live Connect ve Direct Query ile kullanma

Power BI’da sunulan Soru-Cevap özelliği, verilere ilişkin soru sormak için doğal dili kullanarak verilerinizden hızla yanıt almanıza olanak tanır. Bu makale, desteklenen her yapılandırmanın performansını artırmak için dizin oluşturma ve önbelleğe alma özelliklerini kullanmaya ilişkin bilgileri içerir.

## <a name="what-data-sources-are-supported-in-qa"></a>Soru-Cevap özelliğinde hangi veri kaynakları desteklenir?

Soru-Cevap, aşağıdaki yapılandırmalarda desteklenir:

- İçeri Aktarma modu
- Live Connect modu – Şirket içi SQL Server Analysis Services, Azure Analysis Services veya Power BI veri kümelerini kullanarak
- Direct Query – Azure Synapse, Azure SQL ve SQL Server 2019. Diğer kaynaklar Direct Query modunda çalışabilir. Ancak, bu kaynaklar resmi olarak desteklenmez.

Varsayılan olarak, Soru-Cevap görselini kullandığınızda Soru-Cevap özelliği raporda etkinleştirilir. Direct Query veya Live Connect kullanıyorsanız bir istem görüntülenir. Seçeneklere giderek bir rapor için doğal dil özelliklerini açabilir veya kapatabilirsiniz.

![Soru-Cevap masaüstü seçenekleri](media/qna-desktop-options.png)

Daha fazla bilgi için bkz. [Power BI Soru-Cevap sınırlamaları](q-and-a-limitations.md).

## <a name="how-does-indexing-work-with-qa"></a>Dizin oluşturma Soru-Cevap ile nasıl birlikte çalışır?

Soru-Cevap özelliği etkinleştirildiğinde hızla bir dizin oluşturulur. Bu dizin, kullanıcıya gerçek zamanlı geri bildirim sunar ve kullanıcının sorularının yorumlanmasına yardımcı olur. Dizinin oluşturulması zaman alabilir ve dizinde aşağıdaki öğeler ve sınırlamalar bulunur.

- Soru-Cevap aracında açıkça kapatılmadığı sürece tüm sütun adları ve tabloları dizine eklenir.
- 100 karakterden kısa metin değerleri için dizin oluşturulur. 100 karakterden uzun metin değerleri için dizin oluşturulmaz. 
- Soru-Cevap, dizininde en fazla 5 milyon benzersiz değeri depolar. Bu eşik aşılırsa dizin tüm olası değerleri tutmaz ve Soru-Cevap özelliğinden alınan sonuçların doğruluğu düşebilir.
- Dizin oluşturma işlemi sırasında hata oluşursa, dizin kısmi durumda kalır ve sonraki yenilemede yeniden oluşturulur (bu işlem sonraki bölümde açıklanır).

## <a name="how-often-is-the-index-refreshed-and-cached"></a>Dizin ne sıklıkta yenilenir ve önbelleğe alınır?

Power BI Desktop’ta, Soru-Cevap özelliği kullanıldığında dizin oluşturulur. Dizinin oluşturulduğunu bildiren küçük bir simge görüntülenir. Bu süre içinde, öneriler de dahil olmak üzere Soru-Cevap görselinin yüklenmesi zaman alabilir.

Power BI hizmetinde, yayımlama/yeniden yayımlama ve yenileme işlemleriyle birlikte dizin yeniden oluşturulur. Soru-Cevap dizini her zaman otomatik olarak oluşturulmaz ve veri kümesi yenilemelerinin iyileştirilmesi için bazen isteğe bağlı bir planlamayı temel alır. Direct Query için, Direct Query kaynağındaki etkinin azaltılması amacıyla veriler için günde en fazla bir kez dizin oluşturacağız.

## <a name="next-steps"></a>Sonraki adımlar

Doğal dili raporlarınıza tümleştirmek için kullanabileceğiniz çeşitli yollar vardır. Daha fazla bilgi için şu makalelere bakın:

* [Soru-Cevap görseli](../visuals/power-bi-visualization-q-and-a.md)
* [Soru-Cevap en iyi yöntemler](q-and-a-best-practices.md)
