---
title: "Power BI'da SAP HANA için DirectQuery"
description: "SAP HANA ile DirectQuery kullanımında dikkat edilmesi gerekenler"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/12/2017
ms.author: davidi
ms.openlocfilehash: d6f863df59d7374c792f1e1ac16db3a04ad99d87
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="directquery-and-sap-hana"></a>DirectQuery ve SAP HANA
**DirectQuery**'yi kullanarak **SAP HANA** veri kaynaklarına doğrudan bağlanabilirsiniz.

Aşağıdakilerin sağlandığından emin olmak için, **SAP HANA** kullanırken bu bağlantıların nasıl ele alındığına ilişkin bazı unsurları anlamakta yarar vardır:

* SAP HANA görünümü, eklenebilir olmayan ölçüler (örneğin; basit toplamlar yerine ayrı sayımlar veya ortalamalar) içerdiğinde sonuçların beklendiği gibi olması
* Sonuçta elde edilen sorguların verimli olması

**Veri Al** veya **Soru Düzenleyicisi**'nde tanımlanan sorgu ile bir toplama işlemi gerçekleştirdiğinde **SQL Server** gibi bir ilişkisel kaynağın davranışını açıklayarak işe koyulmakta fayda vardır. Sonraki örnekte, **Sorgu Düzenleyicisi**'nde tanımlanan bir sorgu, **ProductID**'ye göre ortalama fiyat sonucunu döndürmektedir.

![](media/desktop-directquery-sap-hana/directquery-sap-hana_01.png)

Veri Power BI'a aktarılıyorsa (DirectQuery kullanmak yerine) aşağıdaki sonuç elde edilir:

* Veri, **Sorgu Düzenleyicisi**'nde oluşturulan sorgu tarafından tanımlanan toplam düzeyinde içeri aktarılır. Örneğin, ürüne göre ortalama fiyat. Bu işlemle, *ProductID* ve *AveragePrice* olmak üzere görsellerde kullanılabilecek iki sütunlu bir tablo elde edilir.
* Bir görselde, sonraki herhangi bir toplama işlemi (*Toplam*, *Ortalama*, *Minimum* ve diğerleri gibi), içeri aktarılan bu veriler üzerinden gerçekleştirilir.  Örneğin, bir görsele *AveragePrice* eklendiğinde varsayılan olarak *Toplam* toplama işlemi kullanılır ve her bir *ProductID* için *AveragePrice* üzerinden toplam döndürülür. Bu örnekte, 13,67 sonucu elde edilir. Aynı durum, görselde kullanılan tüm alternatif toplama işlevleri (*Minimum*, *Ortalama* vb. gibi) için de geçerlidir. Örneğin, *AveragePrice*'ın *Ortalama* değeri, temel alınan tablodaki 6 kaydın *Price* ortalaması (5,17) *yerine*, 4,56'ya denk gelen 6,66, 4 ve 3 değerlerinin ortalamasını döndürür.

İçeri aktarma yerine **DirectQuery** kullanılırsa aynı semantik geçerli olur ve tam olarak aynı sonuçlar elde edilir:

* Aynı sorgu ele alındığında, veriler gerçekte içeri aktarılmasa bile raporlama katmanına mantıksal olarak aynı veriler sunulur.
* Bir görselde bulunan herhangi bir sonraki toplama işlemi (*Toplam*, *Ortalama*, *Minimum* ve diğerleri gibi), yine sorgudan alınan mantıksal tablo üzerinden gerçekleştirilir. *AveragePrice*'ın *Ortalama* değerini içeren bir görsel yine aynı 4,56 değerini döndürür.

Şimdi **SAP HANA**'yı değerlendirelim. Power BI, SAP HANA'da her ikisi de ölçüler içeren *Analitik Görünümleri* ve *Hesaplama Görünümleri* ile birlikte çalışabilir. Yine de bugünkü SAP HANA yaklaşımı, daha önceden tanımlanan ilkeler doğrultusundadır: **Veri Al** veya **Sorgu Düzenleyicisi**'nde tanımlanan sorgu, kullanılabilir verileri belirler, ardından bir görselde gerçekleştirilen sonraki toplama işlemleri bu veriler üzerinden yapılır ve hem İçeri Aktar hem de DirectQuery seçeneği için aynı durum geçerlidir.

Ancak, HANA'nın yapısı göz önünde bulundurulduğunda başlangıçtaki **Veri Al** iletişim kutusunda veya **Sorgu Düzenleyicisi**'nde tanımlanan sorgu her zaman bir toplama sorgusudur ve genellikle, kullanılacak olan gerçek toplamın, HANA görünümü tarafından tanımlandığı ölçüleri içerir.

Yukarıdaki SQL Server örneğinin eşdeğeri olarak, görünümde **Average of Price** olarak tanımlı **ID**, **ProductID**, **DepotID**'yi içeren ve **AveragePrice** dahil olmak üzere ölçüler barındıran bir HANA görünümü bulunur.

![](media/desktop-directquery-sap-hana/directquery-sap-hana_02.png)

**Veri Al** deneyimi kullanılırken yapılan seçimler **ProductID** ve **AveragePrice** ölçüsüne yönelikse bu toplama verilerini isteyen ve görünüm üzerinden gerçekleştirilecek olan bir sorgu tanımlanıyor demektir. (Yukarıdaki örnekte, kolaylık sağlaması açısından HANA SQL'in tam söz dizimiyle eşleşmeyen sözde SQL kullanılmıştır.) Bir görselde tanımlanan diğer toplamalar, bu sorgudan elde edilen sonuçlar için toplam değeri yeniden hesaplar. **SQL Server** için yukarıda açıklandığı gibi, bu, hem İçeri aktar hem de DirectQuery seçeneği için geçerlidir. DirectQuery seçeneğinde, **Veri Al** veya **Sorgu Düzenleyicisi**'nden yapılan sorgu, HANA'ya gönderilen tek bir sorgu içindeki bir alt seçimde kullanılır ve bu nedenle, diğer toplama işlemlerinden önce tüm verilerin okunacağı anlamına gelmez.

Bu durum, HANA üzerinden DirectQuery kullanılırken aşağıdaki önemli noktaların ortaya çıkmasına neden olur:

* HANA'daki ölçü eklenebilir olmadığında (örneğin, basit bir *Toplam*, *Minimum* veya *Maksimum* olmadığında) görsellerde gerçekleştirilen diğer toplama işlemlerine dikkat edilmelidir.
* **Veri Al** veya **Sorgu Düzenleyicisi**'nde, gerekli verileri almak için yalnızca gerekli sütunlar dahil edilmelidir. Bu durumda, sonuç bir sorgu olacaktır ve bu sorgu, HANA'ya gönderilebilecek makul bir sorgu olmalıdır. Örneğin, sonraki görsellerde gerekli olabileceği düşünülerek düzinelerce sütun seçilirse DirectQuery için bile basit bir görselde, alt seçimde kullanılan toplama sorgusunun düzinelerce sorgu içereceği ve bu durumda genellikle düşük bir performans göstereceği anlamına gelir.

Bir örneğe göz atalım. Aşağıdaki örnekte gösterildiği gibi, **Veri Al** iletişim kutusunda OrderQuantity ölçüsüyle birlikte beş sütun (CalendarQuarter, Color, LastName, ProductLine, SalesOrderNumber) seçilmesi, daha sonra Min OrderQuantity'yi içeren basit bir görsel oluşturulduğunda HANA'ya aşağıdaki SQL sorgusunun gönderilmesine neden olur. Gölgeli kısım alt seçimdir ve **Veri Al** / **Sorgu Düzenleyicisi**'nden yapılan sorguyu içerir. Bu alt seçim çok yüksek bir kardinalite sonucu verirse elde edilen HANA performansı büyük olasılıkla düşük olacaktır.

![](media/desktop-directquery-sap-hana/directquery-sap-hana_03.png)

Bu nedenle, **Veri Al** veya **Sorgu Düzenleyicisi**'nde seçilen öğelerin gerektiği kadar öğeyle sınırlı tutulması önerilir. Bu durumda yine HANA için makul bir sorgu elde edilecektir.

### <a name="next-steps"></a>Sonraki adımlar
DirectQuery hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

* [Power BI'da DirectQuery](desktop-directquery-about.md)
* [DirectQuery tarafından desteklenen veri kaynakları](desktop-directquery-data-sources.md)
* [DirectQuery ve SAP BW](desktop-directquery-sap-bw.md)
* [Şirket içi veri ağ geçidi](service-gateway-onprem.md)

