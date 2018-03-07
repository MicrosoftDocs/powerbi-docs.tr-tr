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
ms.date: 02/05/2018
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: cd266118fa560b3d637a85b352f8c1f03d137ec6
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/24/2018
---
# <a name="directquery-and-sap-hana"></a>DirectQuery ve SAP HANA
**DirectQuery** kullanarak **SAP HANA** veri kaynaklarına doğrudan bağlanabilirsiniz. HANA’ya bağlanmak için iki seçenek vardır:

* **HANA’ya çok boyutlu bir kaynak olarak davranma (varsayılan):** Şu anda önizlemededir ve yeni varsayılan ayardır. Bu durumdaki davranış, Power BI SAP Business Warehouse veya Analysis Services gibi diğer çok boyutlu kaynaklara bağlanmaya benzer. Bu ayar kullanılarak HANA’ya bağlanılırken tek bir analiz veya hesaplama görünümü seçilir ve bu görünümün tüm ölçüleri, hiyerarşileri ve öznitelikleri alan listesinde sunulur. Görseller oluşturulurken toplu veriler her zaman HANA’dan alınır. Bu normal olan ve önerilen yaklaşımdır.

* **HANA’ya ilişkisel bir kaynak olarak davranma:** Bu durumda, Power BI HANA’ya ilişkisel bir kaynak olarak davranır. Bu daha yüksek düzeyde esneklik sağlar, ancak ölçülerin beklendiği gibi toplandığından emin olmak ve performans sorunlarından kaçınmak için dikkatli olunması gerekir.

Bağlanmak için kullanılan yaklaşım genel bir araç seçeneği tarafından belirlenir ve bu seçenek, aşağıdaki görüntüde gösterildiği gibi **Dosya > Seçenekler ve ayarlar** seçilip **Seçenekler > DirectQuery** seçildikten sonra  **HANA'ya bir ilişkisel kaynak olarak davran** seçeneği belirlenerek ayarlanır. 

![](media/desktop-directquery-sap-hana/directquery-sap-hana_01a.png)

**SAP HANA bağlayıcısının** şu an **Önizleme** aşamasında olduğunu ve daha önce bahsedilen seçeneğin görünmesi için önce bunun etkinleştirilmesinin gerektiğini unutmayın. Yeni SAP HANA önizleme deneyimini etkinleştirmek için aşağıdaki görüntüde gösterildiği gibi **Seçenekleri > Önizleme özellikleri** altında bunu seçin.

![](media/desktop-directquery-sap-hana/directquery-sap-hana_01b.png)

HANA'ya bir ilişkisel kaynak olarak davranma seçeneği, oluşturulan tüm *yeni* bağlantılar için kullanılan yaklaşımı belirler. Geçerli rapordaki hiçbir mevcut HANA bağlantısı üzerinde ya da diğer açık raporlardaki bağlantılar üzerinde etkisi yoktur. Bu nedenle, geçerli durumda seçenek işaretli değilse **Veri Al** kullanılarak HANA’ya yeni bir bağlantı eklendiğinde bu bağlantının HANA’ya çok boyutlu bir kaynak olarak davranması sağlanır. Bununla birlikte, HANA’ya bağlanan farklı bir rapor açılırsa bu rapor, *oluşturulduğu zaman* ayarlanan seçeneği göre davranmaya devam eder. Başka bir deyişle, Şubat 2018’den önce oluşturulan ve HANA’ya bağlanan tüm raporlar, HANA’ya ilişkisel bir kaynak olarak davranmaya devam eder. 

Bu iki yaklaşımdaki davranışlar birbirinden çok farklıdır ve mevcut bir raporun bir davranıştan diğerine geçirilmesi mümkün değildir. 

Bu iki yaklaşımın her birine ilişkin diğer ayrıntılara sırasıyla göz atalım.

## <a name="treat-hana-as-a-multi-dimensional-source-default"></a>HANA’ya çok boyutlu bir kaynak olarak davranma (varsayılan)

Bu, varsayılan davranıştır ve şu anda önizlemededir. Bu önizleme özelliğini etkinleştirmek için önceki bölümde açıklanan adımları izleyerek önizleme seçeneğini etkinleştirin. 

**Seçenekler > Önizleme özellikleri** bölümünden bu **Önizleme** özelliği etkinleştirildiğinde (bu ayarı yapmaya yönelik adımlar için önceki bölüme bakın), tüm yeni HANA bağlantıları varsayılan olarak bu bağlantı yöntemini kullanır ve HANA’ya çok boyutlu bir kaynak olarak davranır. Bir HANA bağlantısına ilişkisel bir kaynak olarak davranmak için **Dosya > Seçenekler ve ayarlar**’ı seçip **Direct Query > HANA'ya bir ilişkisel kaynak olarak davran** altındaki kutuyu işaretlemelisiniz. Bu özellik **Önizlemede** olduğu sürece, çok boyutlu yaklaşım kullanılarak oluşturulan raporlar Power BI hizmetinde *yayımlanamaz* ve bunun yapılması durumunda rapor Power BI hizmetinde açılınca hatalar oluşur.  

HANA’ya çok boyutlu bir kaynak olarak bağlanılırken aşağıdakiler geçerli olur:

* **Veri Al Gezgini**’nde tek bir HANA görünümü seçilebilir. Tek tek ölçü veya özniteliklerin seçilmesi mümkün değildir. Verilerin içeri aktarılmasından ya da HANA’ya ilişkisel bir kaynak olarak davranılırken DirectQuery kullanılmasından farklı olarak bağlanma sırasında sorgu tanımlanmaz. Bu durum, bu bağlantı yöntemi seçilirken doğrudan bir HANA SQL sorgusu kullanmanın mümkün olmadığı anlamına da gelir.

* Seçili görünümün tüm ölçüleri, hiyerarşileri ve öznitelikleri alan listesinde görüntülenir. 

* Bir ölçü bir görselde kullanılırken görsel için gerekli bir toplama düzeyinde ölçü değerini almak üzere HANA sorgulanır. Bu nedenle, eklenebilir olmayan ölçülerle (sayaçlar, oranlar, vb.) işlem yapılırken tüm toplamalar HANA tarafından gerçekleştirilir ve Power BI tarafından başka toplama gerçekleştirilmez. 

* HANA’dan her zaman doğru toplama değerlerinin elde edilebilmesini sağlamak için belirli kısıtlamaların uygulanması gerekir. Örneğin, hesaplanan sütunlar eklemek ya da birden çok HANA görünümünden alınan verileri aynı raporda birleştirmek mümkün değildir. 

HANA’ya çok boyutlu bir kaynak olarak davranılması, alternatif *ilişkisel* yaklaşım tarafından sağlanan düzeyde yüksek esneklik sağlamaz, ancak daha basittir ve daha karmaşık HANA ölçüleri ile işlem yapılırken doğru toplama değerlerinin elde edilmesini ve genel olarak performansın yükselmesin sağlar. 

**Alan** listesi, HANA görünümünden alınan tüm ölçülerin, özniteliklerin ve hiyerarşilerin listesini içerir. Bu bağlantı yöntemi kullanılırken geçerli olan aşağıdaki davranışlara dikkat edin:

* En az bir hiyerarşiye dahil edilen herhangi bir öznitelik varsayılan olarak gizlenir. Bununla birlikte, bunlar gerekirse alan listesinden **Gizli öğeleri görüntüle** seçilerek görülebilir. Bunlar gerekirse aynı bağlam menüsünden görünür hale getirilebilir.

* HANA’da bir öznitelik başka bir özniteliği etiketi olarak kullanacak şekilde tanımlanabilir. Örneğin, **Ürün** (1,2,3, vb. değerlerine sahip) öğesi **ProductName** (Bisiklet,Gömlek,Eldiven vb. değerlerine sahip) öğesini etiket olarak kullanabilir. Bu durumda, alan listesinde Bisiklet, Gömlek, Eldiven, vb. değerlerine sahip **Ürün** adlı tek bir alan gösterilir, ancak bu değerlerin sıralanması ve benzersizlik durumlarının belirlenmesi 1,2,3 anahtar değerlerine göre gerçekleştirilir. Gerekirse temel anahtar değerlerine erişim imkanı tanıyan gizli bir **Product.Key** sütunu da oluşturulur. 

Temel alınan HANA’da tanımlanan tüm değişkenler bağlanma sırasında görüntülenir ve gerekli değerler girilebilir. Bu değerler daha sonra şeritten **Sorguları Düzenle** seçeneği belirlenip görüntülenen açılan menüden **Değişkenleri Düzenle** seçilerek değiştirilebilir. 

HANA’dan her zaman doğru toplama verilerinin alınabilmesini sağlama gereksinimi göz önünde bulundurulduğunda, izin verilen modelleme işlemleri DirectQuery’nin kullanıldığı genel duruma göre daha kısıtlıdır. Bununla birlikte, ölçü tanımlama, alanları yeniden adlandırıp gizleme ve görüntü biçimleri tanımlama dahil olmak üzere birçok ekleme ve değişiklik yapılabilir. Yenileme sırasında tüm bu değişiklikler korunur ve HANA görünümünde yapılan tüm çakışmayan değişiklikler uygulanır. 

### <a name="additional-modelling-restrictions"></a>Modellemeye ilişkin Ek Kısıtlamalar

DirectQuery kullanılarak SAP HANA’ya bağlanılırken (çok boyutlu kaynak olarak davranma) geçerli olan birincil ek modelleme kısıtlamaları şunlardır: 

* **Hesaplanmış sütunlar desteklenmez:** Hesaplanmış sütun oluşturma özelliği devre dışıdır. Bu, hesaplanmış sütunlar oluşturan Gruplandırma ve Kümeleme özelliklerinin de kullanılamadığı anlamına gelir.
* **Ölçüler için ek sınırlamalar:** Ölçülerde kullanılabilen DAX ifadelerinde, SAP HANA tarafından sunulan destek düzeyini yansıtan ek sınırlamalar söz konusudur.
* **İlişki tanımlama desteği yoktur:** Bir raporun içinde yalnızca tek bir görünüm sorgulanabilir ve bu nedenle ilişki tanımlama desteklenmez.
* **Veri Görünümü yoktur:** **Veri Görünümü** normalde tabloda ayrıntı düzeyindeki verileri gösterir. SAP HANA gibi OLAP kaynakların yapısı gereği bu görünüm, SAP HANA üzerinden kullanılamaz.
* **Sütun ve ölçü ayrıntıları sabittir:** Alan listesinde görülebilen sütunlar ve ölçüler listesi, temel alınan kaynak tarafından sabitlenmiştir ve değiştirilemez. Örneğin, bir sütunu silmek ya da veri türünü değiştirmek mümkün değildir (ancak yeniden adlandırmak mümkündür).
* **DAX'taki ek sınırlamalar:** Ölçü tanımlamalarında kullanılabilecek DAX'ta, kaynaktaki sınırlamaları yansıtan ek sınırlamalar söz konusudur. Örneğin, bir tablo üzerinden toplama işlevini kullanmak mümkün değildir.

### <a name="additional-visualization-restrictions"></a>Görselleştirmelere ilişkin Ek Kısıtlamalar

DirectQuery kullanılarak SAP HANA’ya bağlanılırken (çok boyutlu kaynak olarak davranma) görsellerde birkaç kısıtlama söz konusudur: 
* **Sütunlarda toplama yoktur:** Bir görseldeki sütun için toplamayı değiştirmek mümkün değildir ve toplama her zaman *Özetleme* şeklindedir.

## <a name="treat-hana-as-a-relational-source"></a>HANA'ya bir ilişkisel kaynak olarak davran 

HANA’ya ilişkisel bir kaynak olarak bağlanma seçilirken bazı ek esneklik seçenekleri kullanılabilir hale gelir. Örneğin, hesaplanan sütunlar oluşturabilir, birden çok HANA görünümden veri ekleyebilir ve sonuçta elde edilen tablolar arasında ilişki oluşturabilirsiniz. Bununla birlikte, SAP HANA bu şekilde kullanılırken, aşağıdakilerin sağlanması için bağlantılara nasıl davranıldığına ilişkin belirli boyutların anlaşılması önemlidir: 

* SAP HANA görünümü eklenebilir olmayan ölçüler (örneğin; basit toplamlar yerine ayrı sayımlar veya ortalamalar) içeriyorsa sonuçlar beklendiği gibi olur.
* Sonuçta elde edilen sorguların verimli olması

**Veri Al** veya **Soru Düzenleyicisi**'nde tanımlanan sorgu ile bir toplama işlemi gerçekleştirirken SQL Server gibi bir ilişkisel kaynağın davranışını açıklayarak işe başlamakta fayda vardır. Sonraki örnekte, **Sorgu Düzenleyicisi**'nde tanımlanan bir sorgu, *ProductID*'ye göre ortalama fiyat sonucunu döndürmektedir.  

![](media/desktop-directquery-sap-hana/directquery-sap-hana_01.png)

Veri Power BI'a aktarılıyorsa (DirectQuery kullanmak yerine) aşağıdaki sonuç elde edilir:

* Veri, **Sorgu Düzenleyicisi**'nde oluşturulan sorgu tarafından tanımlanan toplam düzeyinde içeri aktarılır. Örneğin, ürüne göre ortalama fiyat. Bu işlemle, *ProductID* ve *AveragePrice* olmak üzere görsellerde kullanılabilecek iki sütunlu bir tablo elde edilir.
* Bir görselde, sonraki herhangi bir toplama işlemi (*Toplam*, *Ortalama*, *Minimum* ve diğerleri gibi), içeri aktarılan bu veriler üzerinden gerçekleştirilir. Örneğin, bir görsele *AveragePrice* eklendiğinde varsayılan olarak *Toplam* toplama işlemi kullanılır ve her bir *ProductID* için *AveragePrice* üzerinden toplam döndürülür. Bu örnekte 13,67 sonucu elde edilir. Aynı durum, görselde kullanılan tüm alternatif toplama işlevleri (*Minimum*, *Ortalama* vb. gibi) için de geçerlidir. Örneğin, *AveragePrice*'ın *Ortalama* değeri, temel alınan tablodaki 6 kaydın *Price* ortalaması (5,17) yerine, 6,66, 4 ve 3 değerlerinin 4,56'ya denk gelen ortalamasını döndürür.
  
İçeri aktarma yerine **DirectQuery** (aynı ilişkisel kaynak üzerinden) kullanılıyorsa aynı semantik geçerli olur ve tam olarak aynı sonuçlar elde edilir:  

* Aynı sorgu ele alındığında, veriler gerçekte içeri aktarılmasa bile raporlama katmanına mantıksal olarak aynı veriler sunulur.

* Bir görselde bulunan herhangi bir sonraki toplama işlemi (*Toplam*, *Ortalama*, *Minimum* ve diğerleri gibi), yine sorgudan alınan mantıksal tablo üzerinden gerçekleştirilir. *AveragePrice*'ın *Ortalama* değerini içeren bir görsel yine aynı 4,56 değerini döndürür.
  
Şimdi de bağlantıya ilişkisel bir kaynak olarak davranıldığında SAP HANA’yı ele alalım. Power BI, SAP HANA'da her ikisi de ölçüler içeren *Analitik Görünümleri* ve *Hesaplama Görünümleri* ile birlikte çalışabilir. Yine de bugünkü SAP HANA yaklaşımı, bu bölümde daha önce açıklanan ilkelerle aynı doğrultudadır: **Veri Al** veya **Sorgu Düzenleyicisi**'nde tanımlanan sorgu, kullanılabilir verileri belirler, ardından bir görselde gerçekleştirilen sonraki toplama işlemleri bu veriler üzerinden yapılır ve hem İçeri Aktar hem de DirectQuery seçeneği için aynı durum geçerlidir.  
Ancak, HANA'nın yapısı göz önünde bulundurulduğunda başlangıçtaki **Veri Al** iletişim kutusunda veya **Sorgu Düzenleyicisi**'nde tanımlanan sorgu her zaman bir toplama sorgusudur ve genellikle, kullanılacak olan gerçek toplamın, HANA görünümü tarafından tanımlandığı ölçüleri içerir.

Yukarıdaki SQL Server örneğinin eşdeğeri olarak, görünümde *Average of Price* olarak tanımlı *ID*, *ProductID*, *DepotID*'yi içeren ve *AveragePrice* dahil olmak üzere ölçüler barındıran bir HANA görünümü bulunur.  
    
**Veri Al** deneyimi kullanılırken yapılan seçimler **ProductID** ve **AveragePrice** ölçüsüne yönelikse bu toplama verilerini isteyen ve görünüm üzerinden gerçekleştirilecek olan bir sorgu tanımlanıyor demektir. (Önceki örnekte, kolaylık sağlaması açısından HANA SQL'in tam söz dizimiyle eşleşmeyen sözde SQL kullanılmıştır.) Bir görselde tanımlanan diğer toplamalar, bu sorgudan elde edilen sonuçlar için toplam değeri yeniden hesaplar. Bu, SQL Server için yukarıda açıklandığı gibi hem İçeri aktar hem de DirectQuery seçeneği için geçerlidir. DirectQuery seçeneğinde, **Veri Al** veya **Sorgu Düzenleyicisi**'nden yapılan sorgu, HANA'ya gönderilen tek bir sorgu içindeki bir alt seçimde kullanılır ve bu nedenle, diğer toplama işlemlerinden önce tüm verilerin okunacağı anlamına gelmez.  

Tüm bu dikkat gerektiren noktalar ve davranışlar, HANA üzerinden DirectQuery kullanılırken aşağıdaki önemli noktalara dikkat edilmesini gerektirir:  

* HANA'daki ölçü eklenebilir olmadığında (örneğin, basit bir *Toplam*, *Minimum* veya *Maksimum* olmadığında) görsellerde gerçekleştirilen diğer toplama işlemlerine dikkat edilmelidir.

* **Veri Al** veya **Sorgu Düzenleyicisi**'nde, gerekli verileri almak için yalnızca gerekli sütunlar dahil edilmelidir. Bu durumda, sonuç bir sorgu olacaktır ve bu sorgu, HANA'ya gönderilebilecek makul bir sorgu olmalıdır. Örneğin, sonraki görsellerde gerekli olabileceği düşünülerek düzinelerce sütun seçilirse DirectQuery için bile basit bir görselde, alt seçimde kullanılan toplama sorgusunun düzinelerce sorgu içereceği ve bu durumda genellikle düşük bir performans göstereceği anlamına gelir.
  
Bir örneğe göz atalım. Aşağıdaki örnekte gösterildiği gibi, **Veri Al** iletişim kutusunda *OrderQuantity* ölçüsüyle birlikte beş sütun (**CalendarQuarter**, **Color**, **LastName**, **ProductLine**, **SalesOrderNumber**) seçilmesi, daha sonra Min OrderQuantity'yi içeren basit bir görsel oluşturulduğunda HANA'ya aşağıdaki SQL sorgusunun gönderilmesine neden olur. Gölgeli öğe alt seçimdir ve **Veri Al** / **Sorgu Düzenleyicisi**'nden yapılan sorguyu içerir. Bu alt seçim çok yüksek bir kardinalite sonucu verirse elde edilen HANA performansı büyük olasılıkla düşük olacaktır.  

![](media/desktop-directquery-sap-hana/directquery-sap-hana_03.png)

   
Bu davranış nedeniyle, **Veri Al** veya **Sorgu Düzenleyicisi**'nde seçilen öğelerin gerekli öğelerle sınırlı tutulması önerilir. Bu durumda yine HANA için makul bir sorgu elde edilecektir.  

## <a name="best-practices"></a>En İyi Yöntemler 

SAP HANA’ya bağlanmaya yönelik her iki yaklaşım için, özellikle de iyi bir performans sağlamaya yönelik olan DirectQuery kullanma önerileri HANA için de geçerlidir. Bu öneriler [Power BI'da DirectQuery kullanma](desktop-directquery-about.md) makalesinde ayrıntılı olarak açıklanmıştır.
   
## <a name="limitations"></a>Sınırlamalar

Aşağıdaki tabloda, tam olarak desteklenmeyen veya Power BI kullanıldığında farklı davranan tüm SAP HANA özellikleri listelenmiştir. 

* **Üst Alt Öğe Hiyerarşileri**: Üst alt öğe hiyerarşileri Power BI'da görünmez.
Power BI, HANA’ya SQL arabirimini kullanarak erişir ve SQL aracılığıyla üst alt öğe hiyerarşilerine tam olarak erişilemez.
* **Diğer hiyerarşi meta verileri**: Power BI’da hiyerarşilerin temel yapısı gösterilir, ancak bazı hiyerarşi meta verileri (düzensiz hiyerarşiler için davranışı denetleme gibi) etkili olmaz.
Tekrar belirtmek gerekirse, bunun nedeni SQL arabirimi tarafından uygulanan kısıtlamalardır.
* **SSL kullanarak bağlanma**: SSL kullanacak şekilde yapılandırılmış SAP HANA örneklerine bağlanamazsınız.
Öznitelik görünümleri için destek: Power BI, Analitik görünümlere ve Hesaplama görünümlerine erişebilir, ancak Öznitelik görünümlerine doğrudan bağlanamaz.
* **Katalog nesneleri için destek**: Power BI, Katalog nesnelerine bağlanamaz.
* **Yayımlama işleminden sonra Değişkenleri değiştirme**: Rapor yayımlandıktan sonra doğrudan Power BI hizmetinde herhangi bir HANA değişkenini değiştiremezsiniz. 
 
## <a name="known-issues"></a>Bilinen sorunlar 
Aşağıdaki listede, Power BI kullanılarak SAP HANA’ya (DirectQuery) bağlanılırken yaşandığı bilinen tüm sorunlar açıklanmıştır. 

* **Sayaçlar ve diğer ölçüler sorgulanırken HANA sorunu**: Bir Analitik Görünüme bağlanılıyorsa HANA’dan yanlış veriler döndürülür ve aynı görsele bir Sayaç ölçüsü ile diğer bazı oran ölçüleri eklenir. Bu, 2128928 numaralı SAP Notu’nda ele alınmıştır (Hesaplanan Sütun ve Sayaç sorgulanırken beklenmeyen sonuçlar). Bu durumda oran ölçüsü yanlış olur. 

* **Tek HANA sütunundan birden çok Power BI sütunu**: Bir HANA sütununun birden çok hiyerarşide kullanıldığı bazı hesaplama görünümleri için HANA bunu iki ayrı öznitelik olarak kullanıma sunar. Bu, Power BI'da iki sütun oluşturulmasıyla sonuçlanır.  Bu sütun varsayılan olarak gizlidir, ancak hiyerarşiler veya sütunlar ile doğrudan ilgili olan hiçbir sorgu doğru şekilde davranmaz. 
 
## <a name="next-steps"></a>Sonraki adımlar

DirectQuery hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

* [Power BI'da DirectQuery](desktop-directquery-about.md)
* [DirectQuery tarafından desteklenen veri kaynakları](desktop-directquery-data-sources.md)
* [DirectQuery ve SAP BW](desktop-directquery-sap-bw.md)
* [Şirket içi veri ağ geçidi](service-gateway-onprem.md)

