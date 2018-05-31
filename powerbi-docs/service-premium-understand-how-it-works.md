---
title: Power BI Premium kapasite bellek kullanımı ve en iyi duruma getirme
description: Power BI Premium kapasite bellek kullanımını ve en iyi duruma getirmeyi anlayın.
ms.date: 04/30/2018
ms.topic: conceptual
ms.service: powerbi
ms.component: powerbi-admin
ms.author: susuresh
ms.reviewer: susuresh
author: suds001
manager: kfile
ms.openlocfilehash: 03c5e56c5f516bb1f09f51463d4c533185fbb63c
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
ms.locfileid: "34298470"
---
# <a name="power-bi-premium-capacity-resource-management-and-optimization"></a>Power BI Premium kapasite kaynak yönetimi ve en iyi duruma getirme

Bu makalede, Power BI premium hizmetinin kaynakları nasıl yönettiği ve çözümünüzü planlama ve en iyi duruma getirme konusunda verdiği ipuçları açıklanmaktadır.

## <a name="premium-capacity-memory-management"></a>Premium kapasite bellek yönetimi

 Premium kapasite bellek, şunlar tarafından kullanılır:

* Yüklü veri kümeleri tarafından kullanılan bellek
* Veri kümesi yenileme (hem zamanlanmış hem de talep üzerine) işlemi tarafından kullanılan bellek
* Rapor sorguları tarafından kullanılan bellek

Kapasitenizdeki yayımlanmış bir veri kümesi için istek yapıldığında, bu veri kümesi kalıcı depolama alanından belleğe yüklenir (bu durum görüntü yükü olarak adlandırılır). Veri kümesinin bellekte yüklü olarak tutulması, bu veri kümesine yönelik gelecek sorgulara hızlı yanıt vermeye yardımcı olur. Veri kümesini bellekte yüklü olarak tutmak için gereken belleğe ek olarak, rapor sorguları ve veri kümesi de ek bellek tüketir.

### <a name="dataset-memory-estimation"></a>Veri kümesi bellek tahmini

Belleğe bir veri kümesi yüklemeyi denediğinizde Power BI, veri kümesinin istenen komutu tamamlaması için gerekecek bellek miktarını tahmin eder. Bellekteki veri kümelerinin boyutu, diske kaydedildiğinde olan boyuttan daha büyük olma eğilimindedir. Bir veri kümesinin yenilenmesi sırasında, bellek kapasitesi bellek boş olduğunda gerekenden en az iki kat fazla miktarda bellek gerektirir.

### <a name="overcommitting-capacity-eviction-and-reloading-of-datasets"></a>Fazla işleme kapasitesi, çıkarma ve veri kümelerini yeniden yükleme

Power BI Premium, kapasitenizi aşırı işleme avantajını sunar. Örneğin, kapasite belleğinin tutabileceğinden daha fazla veri kümesi yayımlayabilirsiniz. Kapasitenizdeki yayımlanmış veri kümeleri kapasiteye sığabilenden daha fazla belleğe gereksinim duyuyorsa, veri kümelerinin bazıları kalıcı bir depolama alanında ayrıca depolanır. Kalıcı depolama alanı, kapasitelerinizin her biri ile ilişkili 100 TB depolama alanının bir parçasıdır.

Öyleyse hangi veri kümeleri bellekte kalır ve diğer veri kümelerine ne olur? Daha önce açıklandığı gibi, bir veri kümesine yönelik istek yapıldığında istek belleğe yüklenir (görüntü yükü). İstek bir rapor sorgusu ya da yenileme işlemi olabilir.

Kapasitenizi fazla işlediğinizde kapasiteniz de bellek baskısı ile karşılaşabilir. Kapasite bellek baskısıyla karşılaştığında (yeni bir veri kümesinin yüklenmesi gerektiğinden veya bazı yüklü veri kümelerinin üzerindeki sorguların bellek gereksinimini artırdığından) düğüm, kapasite belleğini kullanan *bir veya daha fazla veri kümesini çıkarır*. Etkin olmayan veri kümeleri (halihazırda yürütülmekte olan bir sorgu/yenileme işlemi olmayanlar) ilk önce çıkarılır ve çıkarma sırası 'en önce kullanılan' (LRU) düzenine göredir. Çıkarılan veri kümesine yeni komutlar verilirse, hizmet muhtemelen diğer veri kümelerini çıkararak bunu belleğe yeniden yüklemeyi dener. Bu davranış, kapasitenin kendi belleğinin tutabileceğinden çok daha fazla veri kümesine hizmet vermesine olanak tanıyarak daha verimli bir kullanım sağlar.

Bir veri kümesinin belleğe yüklenmesi oldukça pahalı bir işlemdir. Veri kümesi boyutuna bağlı olarak, bu işlem küçük veri kümeleri için birkaç saniye ile yaklaşık 10 GB’lik veri kümeleri gibi büyük veri kümeleri için onlarca saniye veya dakika arasında sürebilir. Premium kapasite, en önce kullanılan veri kümelerini bellekte mümkün olduğunca uzun süre tutarak kapasitenin yeniden yüklenmesi gereken sayıyı en aza indirmeye çalışır. Ek bellek gerektiğinde, bazı veri kümelerinin çıkarılması gerekir ve sistem, kullanıcı deneyimini en az etkileyen veri kümesini seçmeye çalışır. Ek bellek gerektiğinde, bazı veri kümelerinin çıkarılması gerekir ve sistem, kullanıcı deneyimini en az etkileyen veri kümesini seçmeye çalışır. Örneğin, sistem son birkaç dakika içinde etkin bir şekilde kullanılmış veri kümelerini, çok kısa süre içinde tekrar sorgulanma olasılıkları yüksek olduğu için çıkarmaktan kaçınır.

Çıkarma işlemi hızlı bir işlemdir. Veri kümesi çıkarma sırasında etkin bir şekilde kullanılmıyorsa, kullanıcı çıkarma işleminden çok fazla etki belirleyemez. Ancak, çok fazla veri kümesi aynı anda etkin olarak kullanılıyorsa ve hepsini tutmak için yeterli bellek yoksa, çok sayıda çıkarma gerçekleşebilir. Bu durum, veri kümelerinin sürekli olarak çıkarılıp yeniden yüklendiği bir ‘taşma’ durumuna yol açabilir ve kullanıcılar, yanıt sürelerinde ve performansta belirgin bir düşüş görebilir.

### <a name="dataset-refresh-memory-requirement-competing-with-an-active-dataset-memory-requirement"></a>Etkin bir veri kümesi bellek gereksinimi ile çakışan veri kümesi yenileme bellek gereksinimi

Veri kümeleri, kullanıcılar tarafından bir zamanlamaya göre ya da talep üzerine yenilenebilir. Daha önce açıklandığı gibi, tam yenilemeler için gereken bellek, yüklü ve boştaki veri kümelerinin bellek boyutunun en az iki katıdır. Yenileme başlamadan önce bir yenileme bellek gereksinimi tahmin edilir. Toplam bellek gereksinimi kapasitedeki kullanılabilir bellekten daha fazla ise bazı veri kümeleri çıkarılır. Çıkarma adayları, en eski kullanılan veri kümeleri sırasına göre seçilir. Diğer bir deyişle hizmet, bellekte mümkün olduğunca en son kullanılan veri kümelerini tutmaya çalışır.

Çıkarmaya rağmen gerekli bellek mevcut değilse, yenileme tekrar denenmek üzere sıraya alınır. Hizmet başarılı olana veya yeni bir yenileme eylemi başlayana kadar yeniden deneme yapar.

Kapasitedeki herhangi bir veri kümesine yönelik etkileşimli bir sorgu düzenlenirse ve devam eden bir yenileme nedeniyle yeterli bellek yoksa, bu istek başarısız olur ve kullanıcı tarafından yeniden denenmesi gerekir.

## <a name="cpu-resource-management-in-premium-capacity"></a>Premium kapasitede CPU kaynak yönetimi

CPU kaynaklarının iki adet birincil tüketicisi vardır:

- Raporlardan sorgular
- Yenileme (işleme)

### <a name="queries-from-reports"></a>Raporlardan sorgular

Rapor sorguları, kapasitenizin CPU kaynaklarını tüketir. Raporunuzda bazı verimsiz sorgular varsa ya da çok sayıda eşzamanlı kullanıcınız varsa, rapor çok fazla CPU kaynağı tüketebilir ve mevcut kapasiteniz yükü işlemek için yeterli olmayabilir.

### <a name="refresh-parallelization-policy"></a>Yenileme paralelleştirme ilkesi

Bellek, veri kümelerinin yenilenmesini kısıtlayabilen tek kaynak değildir. Bir sunucudaki sanal çekirdeklerin sayısı da bir faktör olabilir. Her yenileme işlemi belirli bir sayıda sanal çekirdek gerektirdiği için, birbirine paralel olarak çalışabilecek yenileme işlemlerinin sayısı sınırlıdır. SKU başına sınır, aşağıdaki tabloda ayrıntılı olarak gösterilmiştir. Bu sınırların dışına çıkan ek yenileme işlemleri sıraya alınır.

 | SKU  | Arka uç sanal çekirdek sayısı  | Model yenileme paralelliği   |
 | --- | --- | --- |
 | A1  | 0.5  | 1  |
 | A2  | 1  | 2  |
 | A3  | 2  | 3  |
 | A4  | 4  | 6  |
 | A5  | 8  | 12  |
 | A6  | 16  | 24  |
 | EM1  | 0.5  | 1  |
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

Bazı yaygın senaryolar ve hizmet tarafından gerçekleştirilen eylemler aşağıda açıklanmıştır:

 **Zamanlanmış yirmi yenileme işleminin tamamının aynı anda gönderilmesi** – Power BI ilk *x* yenilemeyi aynı anda başlatmayı dener. *x* değeri, bu SKU’nun yenileme paralelleştirme ilkesi ile belirlenir. Power BI etkin olmayan veri kümelerini (yakın zamanda kullanılmayan veri kümeleri) çıkararak yeterli bellek elde edemiyorsa, *x* yenilemenin tümü aynı anda başlatılmaz. Başlatılamayan yenileme işlemleri, başlayabilene kadar sıraya alınır.

 **Aynı anda çalışan iki yenileme ve yalnızca birini tamamlamak için yeterli bellek olması** – Tamamlanabilen yenileme başlatılır. Diğeri daha sonra tekrar denenir.

 **Birkaç veri kümesi yenilenirken çok sayıda veri kümesinin sorgulanması** – Yeterli bellek yoksa, Power BI etkileşimli sorgulara öncelik vermek üzere etkin yenilemeleri durdurmaya çalışır. Bunun yapılması, yenileme performansını düşürür.

 **Veri kümesinin mevcut kapasite boyutunda yenilenmesi için çok fazla bellek gerekmesi** – Yenileme başarısız olur. Çıkarma yoluyla daha fazla bellek elde etmek için bir deneme yapılmaz.

 **Bellekte büyük bir ani artışı olan tek bir veri kümesinin olması** – Ani artış etkin olmayan veri kümeleri çıkarılarak elde edilebilecek bellek miktarından büyükse, ani artışı işlemeye yetecek bellek oluncaya kadar yenileme tekrar denenir.

 **Tüm etkin olmayan veri kümeleri ve yenilemeler çıkarılarak yeterli bellek elde edemeyen bir veri kümesi için sorgu yürütülmesi** - Bu sorgular başarısız olur. Bu tür iş yükü gereksinimleri için daha yüksek kapasite satın alınabilir.

## <a name="troubleshooting-and-testing"></a>Sorun giderme ve test etme

Raporlar yavaşsa veya yanıt vermiyorsa, raporunuzda yalnızca bir kullanıcı için test ederek başlayın. Ardından, limiti bulmak için eş zamanlı kullanıcı yükünü artırmaya başlayın. Çoğu durumda, DAX (rapor sorguları) değerinin ayarlanması raporlarınızın performansını çarpıcı biçimde değiştirebilir (ve kapasiteniz tarafından desteklenen eş zamanlı kullanıcı sayısını artırabilir).

Farklı SKU’ları test etmek ve beklenen iş yükünüz için en iyi Premium SKU’yu belirlemek üzere Azure’daki Power BI Embedded kapasitesini kullanın. Power BI Embedded A4 SKU’su P1, A5 = P2 ve A6 = P3’e eşittir. Azure’da, Azure portalından ölçeği artırıp azaltarak SKU’lar arasında kolayca geçiş yapabilirsiniz. İş yükünüz için en çok işe yarayan SKU’yu bulup testi tamamladığınızda, SKU’yu silebilirsiniz.

Bazı durumlarda, bilgisayarınızdaki modelin PBIX dosyasını açmak ve bellek ile CPU tüketimini denetlemek, sorun hakkında çok fazla bilgi verir. Bu işlem çok büyük modellerde işe yaramaz ancak daha küçük olan bazı modeller için modeli bilgisayarınızdan açmayı, yenilemeyi ve sorgulamayı deneyin. Modeli açtığınızda model boyutunu, belleği ve CPU’yu kontrol edin. Yenilemeyi ve sorgulamayı deneyin. Görev yöneticisini kullanarak yerel PBIX dosyası için CPU ve Bellek tüketimini denetleyin). Bazı durumlarda, bilgisayarınızdaki ölçümler P1/ P2 gibi daha düşük bir premium kapasitenin çözümünüz için işe yaramayabileceğini belirtebilir.
