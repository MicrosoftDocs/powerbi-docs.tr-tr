---
title: Power BI Premium kapasite bellek kullanımı ve en iyi duruma getirme
description: Power BI Premium kapasite bellek kullanımını ve en iyi duruma getirmeyi anlayın.
ms.date: 02/05/2019
ms.topic: conceptual
ms.service: powerbi
ms.subservice: powerbi-admin
ms.author: owend
ms.reviewer: owend
author: minewiskan
manager: kfile
ms.openlocfilehash: e31f67d978471f4dcc6472860fc5f8315212e563
ms.sourcegitcommit: 54d44deb6e03e518ad6378656c769b06f2a0b6dc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55794862"
---
# <a name="microsoft-power-bi-premium-capacity-resource-management-and-optimization"></a>Microsoft Power BI Premium kapasite kaynak yönetimi ve en iyi duruma getirme

Bu makalede Power BI Premium'un kaynakları nasıl yönettiği açıklanmakta, örnekler ve sorun giderme önerileri sunulmaktadır. Genel bakış için bkz. [Power BI Premium nedir?](service-premium.md).

## <a name="premium-capacity-memory-management"></a>Premium kapasite bellek yönetimi

 Premium kapasite bellek, şunlar tarafından kullanılır:

* Belleğe yüklenen veri kümeleri
* Veri kümesi yenileme (hem zamanlanmış hem de talep üzerine)
* Kapasitenin desteklediği iş yükleri
* Rapor sorguları

Kapasitenizdeki yayımlanmış bir veri kümesi için istek yapıldığında, bu veri kümesi kalıcı depolama alanından belleğe yüklenir (bu durum görüntü yükü olarak adlandırılır). Veri kümesinin bellekte yüklü olarak tutulması, bu veri kümesine yönelik gelecek sorgulara hızlı yanıt vermeye yardımcı olur. Veri kümesini bellekte yüklü olarak tutmak için gereken belleğe ek olarak, rapor sorguları ve veri kümesi de ek bellek tüketir.

### <a name="dataset-memory-estimation"></a>Veri kümesi bellek tahmini

Belleğe bir veri kümesi yüklemeyi denediğinizde Power BI, veri kümesinin istenen komutu tamamlaması için gerekecek bellek miktarını tahmin eder. Bellekteki veri kümelerinin boyutu, diske kaydedildiğinde olan boyuttan daha büyük olma eğilimindedir. Bir veri kümesinin yenilenmesi sırasında, Power BI için veri kümesi boşta olduğunda gerekenden en az iki kat fazla miktarda bellek gerekir.

### <a name="overcommitting-capacity-eviction-and-reloading-of-datasets"></a>Fazla işleme kapasitesi, çıkarma ve veri kümelerini yeniden yükleme

Power BI Premium, kapasitenizi *aşırı işleme* avantajını sunar. Örneğin, kapasitenizin tutabileceğinden daha fazla veri kümesi yayımlayabilirsiniz. Yayımlanmış veri kümeleri kapasitede bulunandan daha fazla belleğe gereksinim duyuyorsa, veri kümelerinin bazıları kalıcı bir depolama alanında ayrıca depolanır. Kalıcı depolama alanı, kapasitelerinizin her biri ile ilişkili 100 TB depolama alanının bir parçasıdır.

Öyleyse hangi veri kümeleri bellekte kalır ve diğer veri kümelerine ne olur? Daha önce açıklandığı gibi, bir veri kümesine yönelik istek yapıldığında istek belleğe yüklenir (görüntü yükü). İstek bir rapor sorgusu ya da yenileme işlemi olabilir. Kapasitenizi fazla işleme olasılığı mevcut olduğundan kapasite de bellek baskısı ile karşılaşabilir. Kapasite, bellek baskısıyla karşı karşıya kaldığında düğüm bir veya daha fazla veri kümesini bellekten *çıkarır*. Devre dışı olan veri kümeleri (sorgu/yenileme işlemi yürütülmeyen) önce çıkarılır. Çıkarma sırası, 'en önce kullanılan' (LRU) ölçütüne göre belirlenir. Çıkarılan veri kümesine yeni komutlar verilirse, hizmet muhtemelen diğer veri kümelerini çıkararak bunu belleğe yeniden yüklemeyi dener. Bu davranış, kapasitenin kendi belleğinin tutabileceğinden çok daha fazla veri kümesine hizmet vermesine olanak tanıyarak daha verimli bir kullanım sağlar.

Bir veri kümesinin belleğe yüklenmesi oldukça pahalı bir işlemdir. Veri kümesi boyutuna bağlı olarak, bu işlem küçük veri kümeleri için birkaç saniye ile yaklaşık 10 GB’lik veri kümeleri gibi önemli veri kümeleri için onlarca saniye veya dakika arasında sürebilir. Premium kapasite, en önce kullanılan veri kümelerini bellekte mümkün olduğunca uzun süre tutarak kapasitenin yeniden yüklenmesi gereken sayıyı en aza indirmeye çalışır. Ek bellek gerektiğinde, bazı veri kümelerinin çıkarılması gerekir ve sistem, kullanıcı deneyimini en az etkileyen veri kümesini seçmeye çalışır. Ek bellek gerektiğinde, bazı veri kümelerinin çıkarılması gerekir ve sistem, kullanıcı deneyimini en az etkileyen veri kümesini seçmeye çalışır. Örneğin sistem, son birkaç dakika içinde etkin olarak kullanılan veri kümelerini çıkarmaktan kaçınır. Bu veri kümelerinin kısa süre içinde yeniden sorgulanması olasıdır.

Çıkarma işlemi hızlı bir işlemdir. Veri kümesi çıkarma sırasında etkin bir şekilde kullanılmıyorsa, kullanıcı çıkarma işleminden çok fazla etki belirleyemez. Ancak, çok fazla veri kümesi aynı anda etkin olarak kullanılıyorsa ve hepsini tutmak için yeterli bellek yoksa, çok sayıda çıkarma gerçekleşebilir. Çok fazla veri kümesinin etkin olması, veri kümelerinin sürekli olarak çıkarılıp yeniden yüklendiği bir ‘taşma’ durumuna yol açabilir ve kullanıcılar, yanıt sürelerinde ve performansta belirgin bir düşüş görebilir.

### <a name="dataset-refresh-memory-requirement-competing-with-an-active-dataset-memory-requirement"></a>Etkin bir veri kümesi bellek gereksinimi ile çakışan veri kümesi yenileme bellek gereksinimi

Veri kümeleri, kullanıcılar tarafından bir zamanlamaya göre ya da talep üzerine yenilenebilir. Daha önce açıklandığı gibi, tam yenilemeler için gereken bellek, yüklü ve boştaki veri kümelerinin bellek boyutunun en az iki katıdır. Yenileme başlamadan önce bir yenileme bellek gereksinimi tahmin edilir. Toplam bellek gereksinimi kapasitedeki kullanılabilir bellekten daha fazla ise bazı veri kümeleri çıkarılır. Burada da çıkarma LRU ölçütüne göre belirlenir.

Çıkarmaya rağmen gerekli bellek mevcut değilse, yenileme tekrar denenmek üzere sıraya alınır. Hizmet başarılı olana veya yeni bir yenileme eylemi başlayana kadar yeniden deneme yapar.

Kapasitedeki herhangi bir veri kümesine yönelik etkileşimli bir sorgu düzenlenirse ve devam eden bir yenileme nedeniyle yeterli bellek yoksa, bu istek başarısız olur ve kullanıcı tarafından yeniden denenmesi gerekir.

### <a name="workloads"></a>İş Yükleri

Varsayılan olarak, **Power BI Premium** ve **Power BI Embedded** kapasiteleri yalnızca bulutta Power BI sorguları çalıştırmayla ilişkili iş yüklerini destekler. Şimdi iki ek iş yükü için önizleme desteği sunuyoruz: **Sayfalandırılmış raporlar** ve **Veri akışları**. Etkinleştirilmesi durumunda bu iş yükleri kapasitenizdeki bellek kullanımını etkileyebilir. Daha fazla bilgi için bkz. [İş yüklerini yapılandırma](service-admin-premium-manage.md#configure-workloads).

## <a name="cpu-resource-management-in-premium-capacity"></a>Premium kapasitede CPU kaynak yönetimi

CPU kaynaklarının iki adet birincil tüketicisi vardır:

* Raporlardan sorgular
* Yenileme (işleme)

### <a name="queries-from-reports"></a>Raporlardan sorgular

Rapor sorguları, kapasitenizin CPU kaynaklarını tüketir. Verimsiz sorgulara veya çok fazla eşzamanlı kullanıcıya sahip olan raporlar çok fazla CPU kaynağı kullanabilir. Var olan kapasiteniz, yükü işlemek için yeterli olmayabilir.

### <a name="refresh-parallelization-policy"></a>Yenileme paralelleştirme ilkesi

Bellek, veri kümelerinin yenilenmesini kısıtlayabilen tek kaynak değildir. Bir sunucudaki sanal çekirdeklerin sayısı da bir faktör olabilir. Her yenileme işlemi belirli bir sayıda sanal çekirdek gerektirdiği için, birbirine paralel olarak çalışabilecek yenileme işlemlerinin sayısı sınırlıdır. SKU başına sınır, aşağıdaki tabloda ayrıntılı olarak gösterilmiştir. Bu sınırların dışına çıkan ek yenileme işlemleri sıraya alınır.

 | SKU | Arka uç sanal çekirdek sayısı | Model yenileme paralelliği |
 | --- | --- | --- |
 | A1  | 0,5  | 1  |
 | A2  | 1  | 2  |
 | A3  | 2  | 3  |
 | A4  | 4  | 6  |
 | A5  | 8  | 12  |
 | A6  | 16  | 24  |
 | EM1  | 0,5  | 1  |
 | EM2  | 1  | 2  |
 | EM3  | 2  | 3  |
 | P1  | 4  | 6  |
 | P2  | 8  | 12  |
 | P3  | 16  | 24  |
 | P4  | 32  | 48  |
 | P5  | 64  | 96  |

 > [!TIP]
> Yenileme işlemleriniz gecikiyorsa, kapasitenizin desteklediği paralel yenilemelerin sayısını kontrol edin.

## <a name="example-scenarios"></a>Örnek senaryolar

Bazı yaygın senaryolar ve hizmet tarafından gerçekleştirilen eylemler aşağıda verilmiştir:

**Tümü aynı anda gönderilen yirmi zamanlanmış yenileme**. Power BI, ilk *x* yenileme işlemini aynı anda başlatmaya çalışır. *x* değeri, bu SKU’nun yenileme paralelleştirme ilkesi ile belirlenir. Power BI etkin olmayan veri kümelerini (yakın zamanda kullanılmayan veri kümeleri) çıkararak yeterli bellek elde edemiyorsa, *x* yenilemenin tümü aynı anda başlatılmaz. Başlatılamayan yenileme işlemleri, başlayabilene kadar sıraya alınır.

**Aynı anda çalışan iki yenileme ve yalnızca birini tamamlamak için yeterli bellek olması**. Tamamlanabilen yenileme başlatılır. Diğeri daha sonra tekrar denenir.

**Birkaç veri kümesi yenilenirken çok sayıda veri kümesinin sorgulanması**. Yeterli bellek yoksa, Power BI etkileşimli sorgulara öncelik vermek üzere etkin yenilemeleri durdurmaya çalışır. Bunun yapılması, yenileme performansını düşürür.

**Veri kümesinin mevcut kapasite boyutunda yenilenmesi için çok fazla bellek gerekmesi**. Yenileme başarısız olur. Çıkarma yoluyla daha fazla bellek elde etmek için bir deneme yapılmaz.

**Bellekte büyük bir ani artışı olan tek bir veri kümesinin olması**. Ani artış etkin olmayan veri kümeleri çıkarılarak elde edilebilecek bellek miktarından büyükse, ani artışı işlemeye yetecek bellek oluncaya kadar yenileme tekrar denenir.

**Tüm etkin olmayan veri kümeleri ve yenilemeler çıkarılarak yeterli bellek elde edemeyen bir veri kümesi için sorgu yürütülmesi**. Bu sorgular başarısız olur. Bu tür iş yükü gereksinimleri için daha yüksek kapasite satın alınabilir.

## <a name="troubleshooting-and-testing"></a>Sorun giderme ve test etme

Raporlar yavaşsa veya yanıt vermiyorsa, raporunuzda yalnızca bir kullanıcı için test ederek başlayın. Ardından, limiti bulmak için eş zamanlı kullanıcı yükünü artırmaya başlayın. Çoğu durumda DAX sorgularınızı ayarlamak raporlarınızın performansını önemli ölçüde değiştirebilir. Sorgu ayarlama, kapasitenizin desteklediği eşzamanlı kullanıcı sayısını da artırır. Olası performans sorunlarını tanımlamak için [kapasitenizi izleyin](service-admin-premium-monitor-capacity.md).

Farklı SKU’ları test etmek ve beklenen iş yükünüz için en iyi Premium SKU’yu belirlemek üzere Azure’daki Power BI Embedded kapasitesini kullanın. Power BI Embedded A4 SKU’su P1, A5 = P2 ve A6 = P3’e eşittir. Azure’da, Azure portalından ölçeği artırıp azaltarak SKU’lar arasında kolayca geçiş yapabilirsiniz. İş yükünüz için en çok işe yarayan SKU’yu bulup testi tamamladığınızda, SKU’yu silebilirsiniz.

Bazı durumlarda, bilgisayarınızdaki modelin Power BI Desktop (.pbix) dosyasını açmak ve bellek ile CPU tüketimini denetlemek, sorun hakkında çok fazla bilgi verir. Bu işlem çok büyük modellerde işe yaramaz ancak daha küçük olan bazı modeller için modeli bilgisayarınızdan açmayı, yenilemeyi ve sorgulamayı deneyin. Modeli açtığınızda model boyutunu, belleği ve CPU’yu kontrol edin. Yenilemeyi ve sorgulamayı deneyin. Görev yöneticisini kullanarak yerel dosya için CPU ve bellek tüketimini denetleyin. Bazı durumlarda, bilgisayarınızdaki ölçümler P1/ P2 gibi daha düşük bir premium kapasitenin çözümünüz için işe yaramayabileceğini belirtebilir.

## <a name="next-steps"></a>Sonraki adımlar

[Power BI Premium ve Power BI Embedded'da kapasiteleri yönetme](service-admin-premium-manage.md)