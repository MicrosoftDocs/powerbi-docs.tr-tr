---
title: Power BI Rapor Oluşturucusu’nda rapor planlama
description: Power BI Sayfalandırılmış Rapor Oluşturucusu çok çeşitli sayfalandırılmış raporlar oluşturmanıza olanak tanır. Kullanışlı, kolay anlaşılır raporlar oluşturmak için önce planlamak yararlı olur.
ms.date: 06/06/2019
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.assetid: 79113505-1ce8-4f8c-9260-d861838f7813
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: fd4a318d7a61f6f2298de6b9d5d23ad2ae063d28
ms.sourcegitcommit: 797bb40f691384cb1b23dd08c1634f672b4a82bb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/12/2019
ms.locfileid: "66840522"
---
# <a name="planning-a-report-in-power-bi-report-builder"></a>Power BI Rapor Oluşturucusu’nda rapor planlama
  Power BI Sayfalandırılmış Rapor Oluşturucusu çok çeşitli sayfalandırılmış raporlar oluşturmanıza olanak tanır. Örneğin özet veya ayrıntılı satış verilerini, pazarlama ve satış eğilimlerini, işlem raporlarını veya panoları gösteren raporlar oluşturabilirsiniz. Ayrıca satış siparişleri, ürün katalogları ve form mektupları gibi zengin biçimlendirilmiş metinlerden yararlanan raporlar da oluşturabilirsiniz. Bu raporların hepsi Rapor Oluşturucusu'ndaki aynı temel yapı taşlarının farklı bileşimleri kullanılarak oluşturulur. Kullanışlı, kolay anlaşılır raporlar oluşturmak için önce planlamak yararlı olur. Başlamadan önce şu noktaları göz önünde bulundurmak isteyebilirsiniz:  
  
## <a name="in-what-format-do-you-want-the-report-to-appear"></a>Raporun hangi biçimde gösterilmesini istiyorsunuz?
  
Power BI portalında olduğu gibi bir tarayıcıda raporları çevrimiçi işleyebilir ya da Excel, Word veya PDF gibi başka biçimlerde dışarı aktarabilirsiniz. Raporunuzun son biçiminin ne olacağı önemli bir konudur çünkü tüm dışarı aktarma biçimlerinde tüm özellikler kullanılamaz. 
  
## <a name="in-what-structure-do-you-want-to-present-the-data"></a>Verileri hangi yapıda göstermek istiyorsunuz?
  
Verileri göstermek için tablo, matris (çapraz tablo veya PivotTable raporuna benzer), grafik, serbest biçim yapıları arasından seçim yapabilir veya bunların herhangi bir bileşimini kullanabilirsiniz. Daha fazla bilgi için bkz. [Power BI Rapor Oluşturucusu'nda Tablolar, Matrisler ve Listeler](report-builder-tables-matrices-lists.md).  
  
## <a name="how-do-you-want-your-report-to-look"></a>Raporunuzun nasıl görünmesini istiyorsunuz?
  
Rapor Oluşturucusu raporunuzun okunmasını kolaylaştırmak, önemli bilgilerini vurgulamak, hedef kitlenizin raporda gezinmesine yardımcı olmak için rapora ekleyebileceğiniz çok çeşitli rapor öğeleri sağlar. Raporun nasıl görünmesini istediğinizi bilirseniz metin kutuları, dikdörtgenler, resimler ve çizgiler gibi rapor öğelerine ihtiyacınız olup olmadığını belirleyebilirsiniz. Ayrıca öğeleri göstermek veya gizlemek, belge haritası eklemek, detaylandırma raporları veya alt raporları eklemek ya da başka raporlara bağlanmak isteyebilirsiniz.   
  
## <a name="should-the-data-be-filtered"></a>Veriler filtrelenecek mi?
  
Raporun kapsamını belirli kullanıcılar veya konumları ya da belirli bir zaman aralığını içerecek şekilde daraltmak isteyebilirsiniz. Rapor verilerini filtrelemek için parametreleri kullanarak yalnızca istediğiniz verileri alın ve görüntüleyin. Daha fazla bilgi için bkz. [Power BI Rapor Oluşturucusu’nda rapor parametreleri](paginated-reports-parameters.md).  
  
## <a name="do-you-need-to-create-calculations"></a>Hesaplamalar oluşturmanız gerekiyor mu? 
  
     Sometimes, your data source and datasets do not contain the exact fields that you need for your report. In that situation, you might have to create your own calculated fields. For example, you might want to multiply the price per unit times the quantity to get a line item sales amount. Expressions are also used to provide conditional formatting and other advanced features. For more information, see [Expressions in Power BI Report Builder](report-builder-expressions.md).  
  
## <a name="do-you-want-to-hide-report-items-initially"></a>Başlangıçta rapor öğelerini gizlemek istiyor musunuz?
  
Rapor ilk çalıştırıldığında veri bölgeleri, gruplar ve sütunlar gibi rapor öğelerini gizlemek isteyip istemediğinizi düşünün. Örneğin başlangıçta bir özet tablo gösterebilir ve daha sonra ayrıntılı verilere gidebilirsiniz. 
  
## <a name="how-are-you-going-to-deliver-your-report"></a>Raporunuzu nasıl teslim edeceksiniz?  
  
     You can save your report to your local computer and continue to work on it, or run it locally for your own information. However, to share your report with others, you need to save the report to Power BI. Saving it to Power BI lets others run it whenever they want to. Alternatively, you can set up a subscription and e-mail delivery of the report to other individuals. You can have the report delivered in a specific export format if you prefer. 
  
## <a name="next-steps"></a>Sonraki adımlar

- [Power BI Premium’da sayfalandırılmış raporlar nelerdir?](paginated-reports-report-builder-power-bi.md)
