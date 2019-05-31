---
title: Microsoft Power BI Premium kapasite senaryoları
description: Power BI Premium kapasite senaryoları açıklar.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/09/2019
ms.custom: seodec18
LocalizationGroup: Premium
ms.openlocfilehash: 1d666a6702515a935d93549d026f207848f2bca8
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65565348"
---
# <a name="premium-capacity-scenarios"></a>Premium kapasite senaryoları

Bu makalede, Power BI premium kapasiteler burada uygulanmıştır gerçek dünya senaryoları açıklar. Sık karşılaşılan sorunlar ve zorlukları, ayrıca sorunlarını tanımlaması nasıl açıklanmaktadır ve bunları gidermek:

- [Veri kümeleri güncel tutma](#keeping-datasets-up-to-date)
- [Veri kümeleri tanımlayan yavaş yanıt](#identifying-slow-responding-datasets)
- [Düzensiz yavaş yanıtlanan için nedenleri tanımlayan veri kümeleri](#identifying-causes-for-sporadically-slow-responding-datasets)
- [Yeterli bellek olup olmadığını belirleme](#determining-whether-there-is-enough-memory)
- [Yeterli CPU olup olmadığını belirleme](#determining-whether-there-is-enough-cpu)

Adımları, grafik ve tablo örneklerinin yanı sıra arasındadır **Power BI Premium kapasite ölçümleri uygulama** Power BI yönetici erişimi olacaktır.

## <a name="keeping-datasets-up-to-date"></a>Veri kümeleri güncel tutma

Rapor verileri bazen eski veya "eski" olduğu görüldü, kullanıcıların şikayet olduğunda bu senaryoda, bir araştırma tetiklendi.

Uygulamada, yönetici etkileşimde **yeniler** görsel tarafından veri kümelerini sıralama **en fazla bekleme zamanı** azalan düzende istatistikleri. Bu görsel çalışma alanı adına göre gruplandırılmış en uzun bekleme süresini sahip veri kümeleri açığa yardımcı olur.

![Veri kümesini yenilemeleri maksimum bekleme süresi, çalışma alanı tarafından gruplandırılmış göre azalan düzende sıralandı](media/service-premium-capacity-scenarios/dataset-refreshes.png)

İçinde **saatlik ortalama Yenile bekleme süresini** visual, bunlar yenileme bekleme süresini tutarlı bir şekilde her gün 4 saat yaklaşık tepe dikkat edin.

![Yenileme yoğun düzenli olarak 4 saat bekler.](media/service-premium-capacity-scenarios/peak-refresh-waits.png)

Bu sonuçları için birkaç olası açıklamalar şunlardır:

- Çok fazla sayıda yenileme denemesi kapasite düğümü tarafından tanımlanan sınırları aşma aynı anda gerçekleşen. Bu durumda, varsayılan bellek ayırma ile P1 üzerinde altı eşzamanlı yenileme.

- Yenilenecek veri kümeleri (en az 2 x tam yenileme için gerekli bellek gerektiren) kullanılabilir belleğe sığmayacak kadar büyük olabilir.
- Bellek kullanım artış verimsiz Power Query mantıksal veri kümesi yenilemesi sırasında elde edilen. Meşgul bir kapasitesi, bu depo, bazen yenileme başarısız ve büyük olasılıkla diğer rapor görünümü işlemleri kapasite etkileyen fiziksel sınırı ulaşabilirsiniz.
- Bellekte kalması için gereken sık Sorgulanmış veri kümeleri, diğer veri kümelerine sınırlı kullanılabilir bellek nedeniyle yenileme yeteneğini etkileyebilir.

Araştırmanıza yardımcı olmak için Power BI yönetici bakabilirsiniz:

- Kullanılabilir bellek yenilenecek veri kümesi boyutu x 2'den az olduğunda, verileri anında kullanılabilir düşük bellekle yeniler.
- Değil yenilenir ve yenileme önce değil bellek içinde etkileşimli trafiği yenileme yoğun saatlerde göstermek için henüz başladı. veri kümeleri. Hangi veri kümelerinin belirli bir zamanda belleğe yüklenen görmek için veri kümeleri adreste bir Power BI yönetici bakabilirsiniz **veri kümeleri** uygulama sekmesinde. Yönetici çubuklardan birine tıklayarak filtresi için belirli bir süre sonra çapraz **saatlik yüklenen veri kümesi sayar**. Aşağıdaki görüntüde, yerel bir depo birden fazla veri kümesi zamanlanmış yenilemeleri başlangıcını geciktirebilir belleğe yüklenen ne zaman bir saat gösterir.
- Başlatmak için zamanlanan veri yenilemeleri, artan veri kümesi çıkarmaları alma yerleştirin. Çıkarmaları var. yenileme saatten önce çok fazla sayıda farklı etkileşimli raporlar sunarak yüksek bellek baskısı nedeniyle oluştu belirtebilirsiniz. **Saatlik veri kümesi çıkarmaları ve bellek tüketimi** visual çıkarmaları artış açıkça belirtebilirsiniz.

Aşağıdaki görüntüde yüklenen veri kümeleri içinde yerel bir depo gösterilmektedir etkileşimli sorgulama kullandınız, yenilemeleri başlangıcı ertelendi. Bir zaman diliminde seçerek **saatlik yüklenen veri kümesi sayar** visual alanları arası filtre **veri kümesi boyutları** visual.

![Yerel bir depo yüklenen veri kümelerinde etkileşimli sorgulama Gecikmeli Başlangıç gecikebilir önerir](media/service-premium-capacity-scenarios/hourly-loaded-dataset-counts.png)

Power BI yönetici olarak başlatmak veri yenileme için kullanılabilir yeterli bellek olduğundan emin olmak için adımları izleyerek bu sorunu çözmek deneyebilirsiniz:

- Veri kümesi bağlantı kuruluyor sahipleri ve bunları isteyen kademelendirme ve veri çıkışı boşluk zamanlamaları yenileyin.
- Veri kümesi azaltma gereksiz panolar veya Pano kaldırarak sorgu yükünü kutucukları, özellikle de satır düzeyinde güvenlik zorlama.
- Power Query mantıksal iyileştirerek veri yenilemeleri ' hızlandırma. Hesaplanmış sütunları veya tabloları modelleme geliştirin. Veri kümesi boyutları azaltın veya artımlı veri yenileme gerçekleştirmek için daha büyük veri kümelerinden yapılandırın.

## <a name="identifying-slow-responding-datasets"></a>Veri kümeleri tanımlayan yavaş yanıt

Kullanıcılar belirli raporları açmak için çok uzun sürdü şikayet olduğunda bu senaryoda, bir araştırma başladı ve bazen askıda kalabilir.

Uygulamada, Power BI yönetici kullanabilir **sorgu süreleri** kötü performansa veri kümeleri, veri kümelerine göre azalan düzende sıralayarak belirlemek için görsel **ortalama süresi**. Veri kümelerinin ne sıklıkta sorgulanır görebilmeniz için bu görsel sorgu sayısı, veri kümesi de gösterir.

![Kötü performansa veri kümeleri](media/service-premium-capacity-scenarios/worst-performing-datasets.png)

Yönetici başvurabilir **sorgu süre dağılımı** görsel, genel bir kümelenmiş sorgu performansı dağılımını gösterir (< 30ms, = 0 100ms) filtrelenmiş bir dönem. Genellikle, sınav zamanı bir saniye veya daha kısa, çoğu kullanıcı tarafından duyarlı kabul sorgular; uzun süren sorgular, hatalı performans algısı oluşturma eğilimindedir.

**Saatlik sorgu süre dağılımı** visual ne zaman kapasite performans algılanan bir saatlik sürelere belirlemek Power BI Yöneticisi olarak zayıf sağlar. Daha büyük çubuğunu temsil sorgu süreleri bir saniye içinde daha büyük kullanıcıların kötü performans algılamalarını risk ayırır.

Görsel etkileşimlidir ve bir segmenti çubuk seçildiğinde, karşılık gelen **sorgu süreleri** Tablo rapor sayfasında visual temsil ettiği veri kümelerini göstermek için çapraz filtre. Bu çapraz filtreleme kolayca belirlemek Power BI yönetici, veri kümeleri yavaş yanıt verir.

Aşağıdaki görüntüde göre filtrelenmiş bir görsel gösterir **saatlik sorgu süresi dağıtımları**, kötü performansa veri kümelerinin bir saatlik demet odaklanan. 

![Veri kümeleri gerçekleştirmek daha da kötüsü filtrelenmiş saatlik sorgu süresi dağıtımları visual gösterir](media/service-premium-capacity-scenarios/hourly-query-duration-distributions.png)

Belirli bir saat timespan zayıf performanslı kümesinde belirlendiğinde, Power BI yönetici kötü performans tarafından aşırı yüklenmiş bir kapasite nedeniyle veya veri kümesini veya raporu nedeniyle kötü tasarlanmış araştırabilirsiniz. Bunlar başvurabilir **sorgu bekleme süreleri** görsel ve tarafından Ortalama Sorgu bekleme süresi azalan sıralama veri kümeleri. Sorguları büyük bir yüzdesini bekliyor, yüksek talep veri kümesi için büyük olasılıkla çok sayıda sorgu bekler neden olur. Ortalama Sorgu bekleme süresi önemli ölçüde ise (> 100 ms), veri kümesini ve en iyi duruma getirme yaptıklarını varsa görmek için raporu gözden geçirmekte olabilir. Örneğin, daha az görsellerin üzerinde rapor sayfaları ya da bir DAX ifadesi iyileştirme verilir.

![Zayıf performans gösteren veri kümelerini görüntülemek için sorgu bekleme süreleri görsel yardımcı olur](media/service-premium-capacity-scenarios/query-wait-times.png)

Sorgu bekleme süresi sırasında olay birikmesine veri kümelerinde birkaç olası nedeni vardır:

- Yetersiz modeli tasarımı, ölçü ifadelerini veya hatta rapor Tasarım - katkıda bulunmak tüm koşullar, yüksek düzeyde CPU kullanan sorguları uzun süre çalışan. Bu, CPU iş parçacığı kullanılabilir hale gelir ve en yüksek çalışma saatleri sırasında yaygın olarak görülen bir konvoy etkisi (Düşünme trafiği Başınızı) oluşturabilirsiniz kadar beklenecek yeni sorgular zorlar. **Sorgu beklemeleri** sayfası, veri kümeleri yüksek Ortalama Sorgu bekleme süresini sahip olup olmadığını belirlemek için ana kaynak olacaktır.
- Çok sayıda eş zamanlı kapasite kullanıcılar (yüz binlerce) aynı rapor veya veri kümesi kullanma. Daha iyi tasarlanmış veri kümeleri, hatalı bir eşzamanlılık eşikten yüksek gerçekleştirebilirsiniz. Bu genellikle diğer veri kümelerini Göster sorgu sayısına yönelik önemli ölçüde daha yüksek bir değer gösteren tek bir veri kümesi tarafından gösterilir (örneğin, bir veri kümesi ile karşılaştırıldığında için 300 K sorgular. < 30 bin sorguları diğer tüm veri kümeleri için). Bu veri kümesi basamaklandırmak başlayacak için bir sorgu bekler, şurada görülebilir noktada **sorgu süreleri** visual.
- Veri kümeleri içine ve dışına bellek sık geçerken çok yavaş neden sorgulanan aynı anda birçok farklı veri kümeleri. Veri kümesi belleğe yüklendiğinde, yavaş performans sorunu yaşayan kullanıcı sonuçlanır. Onaylamak için Power BI yöneticinize başvurabilir **saatlik veri kümesi çıkarmaları ve bellek tüketimi** görsel, çok sayıda veri kümeleri belleğe yüklenen gösterebilir art arda çıkarıldığına.

## <a name="identifying-causes-for-sporadically-slow-responding-datasets"></a>Düzensiz yavaş yanıtlanan için nedenleri tanımlayan veri kümeleri

Kullanıcıların rapor görselleri bazen yavaş yanıt veya yanıt veremez duruma, ancak yazıldıkça yeterince hızlı yanıt veren diğer zamanlarda açıklanan olduğunda bu senaryoda, bir araştırma başladı.

Uygulama içinde **sorgu süreleri** bölümü, aşağıdaki şekilde sorunlu veri kümesini bulmak için kullanılan:

- İçinde **sorgu süreleri** visual yönetici veri kümesini veri kümesi (sorgulanan en üst veri kümeleri başlayarak) tarafından filtrelenir ve çapraz filtre uygulanmış çubuklarında incelenirken **saatlik sorgu dağıtımları** visual.
- Ne zaman bir tek bir saatlik çubuğu gösterdi önemli değişiklikler, bu veri kümesi için başka bir saatlik çubukları ve tüm sorgu süresi grupları arasındaki oran (örneğin, oranlarla renkler arasında değişikliği önemli ölçüde), bu veri kümesi ara sıra bir değişiklik gösterilen anlamına gelir performans.
- Zayıf performanslı sorguların düzensiz bir kısmını gösteren bir saatlik çubukları, söz konusu veri kümesi tarafından diğer veri kümelerine etkinlikleri tarafından neden bir gürültülü komşu etkisi burada etkilendiğini bir TimeSpan değeri gösterilir.

Bir veri kümesi performans önemli bir setback oluştu burada gösterildiği bir saat 30 Ocak aşağıdaki resim "(3,10s]"yürütme süre demetine. boyutu tarafından belirtilen Bu bir saatlik çubuğunu gürültülü komşu etkisi olası veri kümeleri görünmesini bu süre boyunca, belleğe yüklenmiş tüm veri kümelerini gösterir.

![Büyük bir bölümü tarafından kötü performans gösteren çubuk](media/service-premium-capacity-scenarios/worst-performing-queries.png)

(Örneğin, sırasında 30 Ocak yukarıdaki resimde) sorunlu bir timespan tanımlandıktan sonra Power BI yönetici tüm veri kümesi filtreleri kaldırın ardından hangi veri kümelerinin bu süre boyunca etkin bir şekilde sorgulandığını belirlemek için yalnızca bu timespan göre filtreleyin. Gürültülü komşu efekt için sabah veri kümesi, genellikle üst sorgulanan veri kümesi veya Ortalama Sorgu en uzun süresi aşağıdakilerden olur.

Bu soruna bir çözüm, veri kümeleri üzerinde farklı Premium kapasite veya veri kümesi boyutu, tüketim gereksinimleri ve veri desenleri yenilerseniz paylaşılan kapasite üzerinde farklı çalışma alanları desteklenir sabah dağıtmak için olabilir.

Bu durumun tersi de geçerli olabilir. Power BI yönetici, ne zaman bir veri kümesi sorgu performansını önemli ölçüde artıran kez belirleyin ve sonra ne kayboldu bakın. Bu noktada belirli bilgileri eksikse, ardından, neden olan soruna işaret edecek şekilde yardımcı olabilir.

## <a name="determining-whether-there-is-enough-memory"></a>Yeterli bellek olup olmadığını belirleme

Kapasite, iş yüklerini tamamlanması için yeterli bellek olup olmadığını belirlemek için Power BI yöneticinize başvurabilir **tüketilen bellek yüzdelerini** görsel **veri kümeleri** uygulama sekmesinde. **Tüm** (toplam) bellek olup olmadığı, etkin olarak sorgulanan işlenen veya bağımsız olarak belleğe yüklenen veri kümeleri tarafından kullanılan belleği temsil eder. **Etkin** belleği, etkin olarak işlenmekte olan veri kümeleri tarafından kullanılan belleği temsil eder.

Bu, tüm (toplam) arasında bir boşluk gösteren gibi görsel sağlıklı bir kapasitede görünür ve etkin bellek:

![Sağlıklı bir kapasite tüm (toplam) arasında bir boşluk gösterilir ve etkin bellek](media/service-premium-capacity-scenarios/memory-healthy-capacity.png)

Bellek baskısı yaşayan bir kapasitede etkin bellek ve yakınsamaya, ek veri kümeleri belleğe daha sonra yüklemek imkansız olduğu anlamına gelen toplam bellek ve aynı görsele açıkça gösterilir. Bu durumda, Power BI yönetici tıklayabilirsiniz **kapasite yeniden** (içinde **Gelişmiş Seçenekler** Yönetim Portalı'nın kapasite ayarları alanının). Kapasite sonuçları, tüm veri kümeleri olduğu bellekten Temizlenen ve bunları belleğe gerektirdiği (yenileme) sorguları veya veri olarak yeniden yüklemek izin verme yeniden başlatılıyor.

![** İle yakınsamaya etkin ** bellek ** tüm ** bellek](media/service-premium-capacity-scenarios/memory-unhealthy-capacity.png)

## <a name="determining-whether-there-is-enough-cpu"></a>Yeterli CPU olup olmadığını belirleme

Genel olarak, kapasite 's ortalama CPU kullanımı % 80 aşağısına kalmalıdır. Bu değer aşan CPU doygunluğu kapasitesine yaklaşıyor anlamına gelir.

CPU doygunluğu etkilerini, işlemler, tüm işlemleri işlemek çalışır gibi çok sayıda CPU bağlamları geçiş gerçekleştirme kapasite nedeniyle gereken daha uzun sürüyor. ifade edilir. Çok sayıda eş zamanlı sorguları ile Premium kapasitede, bu yüksek sorgu bekleme süresini tarafından belirtilir. Normalden daha yavaş yanıt hızı yüksek sorgu bekleme süresini bir sonucu var. CPU görüntüleyerek Doygunluk düzeyine ne zaman Power BI yönetici kolayca tanımlayabilirsiniz **saatlik sorgu bekleme süresi dağıtımları** visual. Dönemsel en yüksek sayılar sorgu bekleme süresi olası CPU doygunluğu sayılarını gösterir.

![Dönemsel en yüksek sayılar sorgu bekleme süresi olası CPU doygunluğu sayılarını gösterir](media/service-premium-capacity-scenarios/peak-query-wait-times.png)

Bunlar için CPU doygunluğu katkıda, benzer bir desen bazen arka plan işlemlerinde algılanabilir. Power BI yönetici düzenli bir depo için CPU doygunluğu zaman (büyük olasılıkla diğer devam eden bir veri kümesini yenilemeleri ve/veya etkileşimli sorgular nedeniyle) belirtebilirsiniz. belirli bir dataset için yenileme zamanları bakabilirsiniz. Bu örnekte, söz konusu **sistem** uygulama görünümünde mutlaka açığa CPU'nun % 100 olduğundan. **Sistem** görüntüleyen saatlik ortalamalar, ancak CPU yoğun işlem birkaç dakika içinde bekleme süresini ani gösterilir, doygun.

CPU doygunluğu etkisini görmek için daha fazla küçük farklar vardır. Bekleme sorguların sayısını önemli olsa da, sorgu bekleme süresi her zaman bir dereceye kadar Ölçek performans düşüşüne neden olmadan gerçekleşir. Bazı veri kümeleri (ile karmaşıklığı ya da boyutunu gösteren daha uzun Ortalama Sorgu süresini) diğerlerinden daha fazla CPU doygunluğu etkilerini fazladır. Bu veri kümelerini kolayca belirlemek için Power BI yönetici değişiklikleri çubukların rengini birleşimde arayabilirsiniz **bekleyin saatlik zaman dağıtım** visual. Aykırı çubuğu kapsamlı sonra bunlar sorgu beklediği sırada olan veri kümeleri için bakın ve Ortalama Sorgu süresi ile karşılaştırıldığında Ortalama Sorgu bekleme zaman da bakın. Bu iki ölçüm aynı büyüklük ve veri kümesi için sorgu iş yükü Önemsiz olduğundan, veri kümesi tarafından yetersiz CPU etkilenir olasıdır.

Bir veri kümesi her veri bloğu sırasında CPU doygunluğu výsledek kısa ani artışlara yüksek sıklık düzeyi sorgular (örneğin, bir oturumda eğitim), birden çok kullanıcı tarafından tüketilen bu etki özellikle görünür olabilir. Bu durumda, bu veri kümesi üzerinde önemli bir sorgu bekleme süresini (gürültülü komşu etkisi) kapasite diğer veri kümelerinde etkileyen yanı sıra yaşadı.

Bazı durumlarda, Power BI yöneticileri veri kümesi sahipleri daha az oluşturmak isteyebilirsiniz (düzenli aralıklarla herhangi bir veri kümesi ile hangi sorguların yenilemek için önbelleğe alınan kutucuklar) bir Pano yerine bir rapor oluşturarak geçici sorgu iş yükü. Bu, Pano yüklendiğinde ani önlemeye yardımcı olabilir. CPU doygunluğu, veri kümesine değiştirme yapmadan önlemek için verimli bir yöntem olabilir ancak bu çözümü her zaman iş gereksinimlerini mümkün olmayabilir.

## <a name="acknowledgements"></a>Onayları

Bu makale, Peter Myers, veri platformu MVP ve bağımsız BI Uzmanı ile yazılmıştır [Bitsel çözümleri](https://www.bitwisesolutions.com.au/).

## <a name="next-steps"></a>Sonraki adımlar

> [!div class="nextstepaction"]
> [Premium kapasiteler uygulaması ile izleme](service-admin-premium-monitor-capacity.md)    
> [!div class="nextstepaction"]
> [Yönetim Portalı'nda izleme kapasiteleri](service-admin-premium-monitor-portal.md)   

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)

||||||