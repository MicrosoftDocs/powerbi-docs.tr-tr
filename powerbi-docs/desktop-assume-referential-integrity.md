---
title: Power BI Desktop'taki Bilgi tutarlılığı varsay ayarı
description: DirectQuery ile Power BI Desktop'ın bilgi tutarlılığı varsayma işlemini nasıl gerçekleştireceğini öğrenin
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/07/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 1e4e13ddf098d68d48fcbe968c325e9a9458b3df
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65239903"
---
# <a name="assume-referential-integrity-settings-in-power-bi-desktop"></a>Power BI Desktop'ta Bilgi tutarlılığı varsay ayarları
**DirectQuery** kullanarak bir veri kaynağına bağlanırken, veri kaynağınızda daha verimli sorgular çalıştırılmasını sağlamak için **Bilgi Tutarlılığı Varsay** seçeneğini kullanabilirsiniz. Bu özellik, temel alınan verilere ilişkin bazı gereksinimlere sahiptir ve yalnızca **DirectQuery** ile kullanılabilir.

**Bilgi tutarlılığı varsay** ayarı, veri kaynağındaki sorguların **OUTER JOIN** yerine **INNER JOIN** deyimlerini kullanmasını sağlar ve böylece sorgu verimliliği artar.

![](media/desktop-assume-referential-integrity/assume-referential-integrity_1.png)

## <a name="requirements-for-using-assume-referential-integrity"></a>Bilgi tutarlılığı varsay ayarını kullanmaya ilişkin gereksinimler
Bu gelişmiş bir ayardır ve yalnızca, verilere **DirectQuery** kullanılarak bağlanıldığında etkinleştirilir. **Bilgi tutarlılığı varsay** ayarının düzgün çalışabilmesi için aşağıdaki gereksinimler söz konusudur:

* İlişkide **From** sütununda bulunan veriler hiçbir zaman *Null* veya *boş* olmaz
* **From** sütunundaki her bir değer için **To** sütununda karşılık gelen bir değer bulunur

Bu bağlamda **From** sütunu, *Tek - Çok* ilişkisindeki *Çok* kısmıdır veya *Birebir* ilişkide birinci tablodaki sütundur.

## <a name="example-of-using-assume-referential-integrity"></a>Bilgi tutarlılığı varsay ayarının kullanımına ilişkin örnek
Aşağıdaki örnekte, **Bilgi tutarlılığı varsay**'ın veri bağlantılarında kullanıldığında nasıl davrandığı gösterilmiştir. Örnekte bir **Orders** tablosu, **Products** tablosu ve **Depots** tablosu bulunan bir veri kaynağına bağlanılmıştır.

1. **Orders** tablosunu ve **Products** tablosunu gösteren aşağıdaki görüntüde **Orders[ProductID]** ve **Products[ProductID]** arasında bilgi tutarlılığı olduğuna dikkat edin. **Orders** tablosundaki **[ProductID]** sütunu hiçbir zaman *Null* değildir ve tüm değerler **Products** tablosunda da görünür. Bu nedenle, daha verimli sorgular elde etmek için **Bilgi tutarlılığı varsay** ayarlanmalıdır. (Bu ayar kullanıldığında, görsellerde gösterilen değerler değişmez.)
   
   ![](media/desktop-assume-referential-integrity/assume-referential-integrity_2.png)
2. Sonraki görüntüde **Orders[DepotID]** ve **Depots[DepotID]** arasında hiçbir bilgi tutarlılığı olmadığına dikkat edin. Bunun nedeni, bazı *Orders* değerleri için **DepotID** değerinin *Null* olmasıdır. Bu nedenle, **Bilgi Tutarlılığı Varsay** ayarı *belirlenmemelidir*.
   
   ![](media/desktop-assume-referential-integrity/assume-referential-integrity_3.png)
3. Son olarak, aşağıdaki tablolarda **Orders[CustomerID]** ve **Customers[CustID]** arasında hiçbir bilgi tutarlılığı yoktur. **CustomerID**, *Customers* tablosunda bulunmayan bazı değerler (bu örnekte *CustX*) içerir. Bu nedenle, **Bilgi Tutarlılığı Varsay** ayarı *belirlenmemelidir*.
   
   ![](media/desktop-assume-referential-integrity/assume-referential-integrity_4.png)

## <a name="setting-assume-referential-integrity"></a>Bilgi tutarlılığı varsay ayarı
Bu özelliği etkinleştirmek için aşağıdaki görüntüde gösterildiği üzere **Bilgi tutarlılığı varsay**'ın yanındaki onay kutusunu seçin.

![](media/desktop-assume-referential-integrity/assume-referential-integrity_1.png)

Bu ayar seçili olduğunda, verilerde *Null* değer veya eşleşmeyen satır olmadığı doğrulanır. *Ancak*, çok yüksek sayıda değer içeren durumlarda doğrulamadan sonra bilgi tutarlılığı sorunları olmayacağı garanti edilemez.

Ayrıca doğrulama işlemi, ilişkinin düzenlendiği sırada gerçekleşir ve verilerde daha sonra yapılan değişiklikleri *yansıtmaz*.

## <a name="what-happens-if-you-incorrectly-set-assume-referential-integrity"></a>Bilgi tutarlılığı varsay ayarını yanlışlıkla ayarlarsanız ne olur?
Verilerde bilgi tutarlılığı sorunları varken **Bilgi tutarlılığı varsay**'ı ayarlamanız hata oluşmasına neden olmaz. Ancak, verilerde görünür tutarsızlıklar oluşmasına neden olur. Örneğin, yukarıda açıklanan **Depots** tablosu ile ilişki örneğinde sonuç aşağıdaki gibi olur:

* Toplam *Order Qty* değerini gösteren bir görsel, 40 değerini görüntüler
* Toplam *Order Qty by Depot City* değerini gösteren bir görsel, toplamda yalnızca *30* değerini görüntüler. Bunun nedeni, **DepotID** değeri *Null* olan Order ID 1 verilerinin dahil edilmemesidir.

## <a name="next-steps"></a>Sonraki adımlar
[DirectQuery](desktop-use-directquery.md) hakkında daha fazla bilgi edinin

[Power BI'daki İlişkiler](desktop-create-and-manage-relationships.md) hakkında daha fazla bilgi edinin

[Power BI Desktop'taki İlişki Görünümü](desktop-relationship-view.md) hakkında daha fazla bilgi edinin.

