---
title: Power BI Rapor Oluşturucusu’nda rapor planlama
description: Power BI Report Builder çok çeşitli sayfalandırılmış raporlar oluşturmanıza olanak tanır. Kullanışlı, kolay anlaşılır raporlar oluşturmak için önce planlamak yararlı olur.
author: maggiesMSFT
ms.author: maggies
ms.date: 07/25/2019
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
ms.assetid: 79113505-1ce8-4f8c-9260-d861838f7813
ms.openlocfilehash: 2ed8dfd07cf5d7d04869b3bf2253bca09adbc0ba
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96416260"
---
# <a name="planning-a-report-in-power-bi-report-builder"></a>Power BI Rapor Oluşturucusu’nda rapor planlama

[!INCLUDE [applies-to](../includes/applies-to.md)] [!INCLUDE [yes-service](../includes/yes-service.md)] [!INCLUDE [yes-paginated](../includes/yes-paginated.md)] [!INCLUDE [yes-premium](../includes/yes-premium.md)] [!INCLUDE [no-desktop](../includes/no-desktop.md)] 

Power BI Report Builder çok çeşitli sayfalandırılmış raporlar oluşturmanıza olanak tanır. Örneğin özet veya ayrıntılı satış verilerini, pazarlama ve satış eğilimlerini, işlem raporlarını veya panoları gösteren raporlar oluşturabilirsiniz. Ayrıca satış siparişleri, ürün katalogları ve form mektupları gibi zengin biçimlendirilmiş metinlerden yararlanan raporlar da oluşturabilirsiniz. Bu raporların hepsi Rapor Oluşturucusu'ndaki aynı temel yapı taşlarının farklı bileşimleri kullanılarak oluşturulur. Kullanışlı, kolay anlaşılır raporlar oluşturmak için önce planlamak yararlı olur. Başlamadan önce şu noktaları göz önünde bulundurmak isteyebilirsiniz:  
  
## <a name="in-what-format-do-you-want-the-report-to-appear"></a>Raporun hangi biçimde gösterilmesini istiyorsunuz?
  
Power BI portalında olduğu gibi bir tarayıcıda raporları çevrimiçi işleyebilir ya da Excel, Word veya PDF gibi başka biçimlerde dışarı aktarabilirsiniz. Raporunuzun son biçiminin ne olacağı önemli bir konudur çünkü tüm dışarı aktarma biçimlerinde tüm özellikler kullanılamaz. 
  
## <a name="in-what-structure-do-you-want-to-present-the-data"></a>Verileri hangi yapıda göstermek istiyorsunuz?
  
Verileri göstermek için tablo, matris (çapraz tablo veya PivotTable raporuna benzer), grafik, serbest biçim yapıları arasından seçim yapabilir veya bunların herhangi bir bileşimini kullanabilirsiniz. Daha fazla bilgi için bkz. [Power BI Rapor Oluşturucusu'nda Tablolar, Matrisler ve Listeler](report-builder-tables-matrices-lists.md).  
  
## <a name="how-do-you-want-your-report-to-look"></a>Raporunuzun nasıl görünmesini istiyorsunuz?
  
Rapor Oluşturucusu raporunuzun okunmasını kolaylaştırmak, önemli bilgilerini vurgulamak, hedef kitlenizin raporda gezinmesine yardımcı olmak için rapora ekleyebileceğiniz çok çeşitli rapor öğeleri sağlar. Raporun nasıl görünmesini istediğinizi bilirseniz metin kutuları, dikdörtgenler, resimler ve çizgiler gibi rapor öğelerine ihtiyacınız olup olmadığını belirleyebilirsiniz. Ayrıca öğeleri göstermek veya gizlemek, belge haritası eklemek, detaylandırma raporları veya alt raporları eklemek ya da başka raporlara bağlanmak isteyebilirsiniz.   
  
## <a name="should-the-data-be-filtered"></a>Veriler filtrelenecek mi?
  
Raporun kapsamını belirli kullanıcılar veya konumları ya da belirli bir zaman aralığını içerecek şekilde daraltmak isteyebilirsiniz. Rapor verilerini filtrelemek için parametreleri kullanarak yalnızca istediğiniz verileri alın ve görüntüleyin. Daha fazla bilgi için bkz. [Power BI Rapor Oluşturucusu’nda rapor parametreleri](paginated-reports-parameters.md).  
  
## <a name="do-you-need-to-create-calculations"></a>Hesaplamalar oluşturmanız gerekiyor mu? 
  
Bazen veri kaynağınız ve veri kümeleriniz raporunuz için gereken alanları tam olarak içermez. Bu durumda kendi hesaplanan alanlarınızı oluşturmanız gerekir. Örneğin satır öğesi satış tutarını elde etmek için birim fiyatını miktarla çarpmak isteyebilirsiniz. İfadeler koşullu biçimlendirmeyi ve diğer gelişmiş özellikleri sağlam için de kullanılır. Daha fazla bilgi için bkz. [Power BI Rapor Oluşturucusu'nda ifadeler](report-builder-expressions.md).  
  
## <a name="do-you-want-to-hide-report-items-initially"></a>Başlangıçta rapor öğelerini gizlemek istiyor musunuz?
  
Rapor ilk çalıştırıldığında veri bölgeleri, gruplar ve sütunlar gibi rapor öğelerini gizlemek isteyip istemediğinizi düşünün. Örneğin başlangıçta bir özet tablo gösterebilir ve daha sonra ayrıntılı verilere gidebilirsiniz. 
  
## <a name="how-are-you-going-to-deliver-your-report"></a>Raporunuzu nasıl teslim edeceksiniz?  
  
Raporunuzu yerel bilgisayarınıza kaydedebilir ve raporla çalışmaya devam edebilirsiniz veya kendi bilgilerinizle yerel olarak çalıştırabilirsiniz. Bununla birlikte raporunuzu başkalarıyla paylaşmak için raporu Power BI'a kaydetmeniz gerekir. Power BI'a kaydedilmesi başkalarının istediklerinde raporu çalıştırmasına olanak tanır. Alternatif olarak bir abonelik ayarlayabilir ve rapor teslimini diğer bireylere e-postayla yapabilirsiniz. Tercih ederseniz raporun belirli bir dışarı aktarma biçiminde teslim edilmesini sağlayabilirsiniz. 
  
## <a name="next-steps"></a>Sonraki adımlar

- [Power BI Premium’da sayfalandırılmış raporlar nelerdir?](paginated-reports-report-builder-power-bi.md)
