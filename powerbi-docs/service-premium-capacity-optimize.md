---
title: Microsoft Power BI Premium kapasiteleri en iyi duruma getirme
description: Power BI Premium kapasiteleri için en iyi duruma getirme stratejileri açıklanır.
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
ms.openlocfilehash: 06712b6bcf57ca84ec03d2c7b99b32ea61ad8c71
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65565327"
---
# <a name="optimizing-premium-capacities"></a>Premium kapasiteler en iyi duruma getirme

Premium kapasite performans sorunları ortaya çıktığında, ortak bir ilk yaklaşım iyileştirmek veya çözümlerinizi kabul edilebilir yanıt süreleri geri yüklemek için ayarlanacak sağlamaktır. Açısından haklı bir gerekçesi sürece ek Premium kapasite satın alma önlemek için stratejinin.

Ek Premium kapasite gerekli olduğunda, bu makalede açıklanan iki seçenek vardır:

- Mevcut bir Premium kapasiteye ölçek artırma
- Yeni bir Premium kapasiteye ekleyin

Son olarak, test sonucuna yaklaşımlar ve Premium kapasite boyutlandırmasını, bu makalede.

## <a name="best-practices"></a>En iyi yöntemler

En iyi kullanımı ve performans alınmaya çalışılırken dahil olmak üzere bazı önerilen en iyi yöntem vardır:

- Uygulama çalışma alanları yerine kişisel çalışma alanlarını kullanma.
- İş açısından kritik ve Self Servis BI (SSBI) farklı kapasiteler ayırma.

  ![İş açısından kritik ve Self Servis BI farklı kapasiteler ayırma](media/service-premium-capacity-optimize/separate-capacities.png)

- Yalnızca Power BI Pro kullanıcıları ile içerik paylaşma bir adanmış kapasiteyle sunulan içeriği depolamak gerekmez olabilir.
- Adanmış kapasite belirli yenileme süresi elde etmek isteyen veya belirli özellikler gerekli olduğunda kullanın. Örneğin, büyük veri kümeleri veya sayfalandırılmış Raporlama ile.

### <a name="addressing-common-questions"></a>Sık sorulan sorular adresleme

Power BI Premium dağıtımları en iyi duruma getirme iş yükü gereksinimlerini, kullanılabilir kaynaklar ve etkili kullanımları içeren karmaşık bir konudur.

Bu makalede olası sorunlar ve açıklamalar ve tanımlama ve çözme hakkında bilgi açıklayan, yedi genel destek soruları ele alır.

### <a name="why-is-the-capacity-slow-and-what-can-i-do"></a>Yavaş kapasite neden olduğu ve neler yapabilirim?

Yavaş bir Premium kapasiteye katkıda bulunabilir birçok neden vardır. Bu sorunun daha fazla bilgi ne tarafından yavaş yöneliktir anlamak için gerektirir. Raporları yavaş misiniz? Veya yüklemek başarısız oluyor? Rapor görselleri yüklemek veya kullanıcıların bir raporla etkileşim kurduğunuzda güncelleştirmek yavaş misiniz? Alma bekleniyor veya daha önce karşılaştığınız tamamlanması uzun yenilenir?

Neden olma elde edilen, ardından araştırmaya başlayabilirsiniz. Aşağıdaki altı soruların yanıtları yardımcı olacak daha fazla gidermek için belirli sorunları.

### <a name="what-content-is-using-up-my-capacity"></a>Hangi içerik my kapasite kullanıyor mu?

Kullanabileceğiniz **Power BI Premium kapasite ölçümleri** uygulama kapasite ve performans ölçümleri workspace içerik için gözden geçirin. Bir Premium kapasiteye içinde depolanan tüm içerik için son yedi güne ait saat performans ölçümlerini ve kaynak kullanımını gözden geçirmek mümkündür. İzleme genellikle geneli ilgilendiren Premium kapasite performansıyla ilgili sorun giderme yapılacak ilk adımıdır.

İzlemek için ana ölçümler içerir:

- Ortalama CPU ve yüksek kullanım sayısı.
- Ortalama bellek ve yüksek kullanım sayısı ve bellek kullanımı belirli veri kümeleri, veri akışlarını ve sayfalandırılmış raporlar.
- Etkin veri belleğe.
- Ortalama ve en yüksek sorgu süreleri.
- Ortalama Sorgu bekleme süresini.
- Ortalama veri kümesi ve veri akışı defa yenileyin.

Power BI Premium kapasite ölçümleri uygulamada etkin bellek toplam kullanımı son üç dakika içinde bırakıldı çünkü çıkarılamadığı bir rapor için verilen bellek miktarını gösterir. Yenileme bekleme süresi yüksek bir ani değişiklik büyük ve/veya etkin bir veri kümesiyle ilişkili olabilir.

**Ortalama süreye göre ilk 5** zorlayıcı beş veri kümeleri, sayfalandırılmış raporlar ve veri akışlarını kapasite kaynak tüketmeye grafiğini vurgular. İçerik beş üst araştırma ve olası en iyi duruma getirme için aday listedir.

### <a name="why-are-reports-slow"></a>Neden raporlardır yavaş?

Aşağıdaki tablolar, olası sorunlar ve tanımlamak ve bunları işlemek için yol gösterir.

#### <a name="insufficient-capacity-resources"></a>Yeterli kapasite kaynakları

| Olası açıklamalar | Belirleme | Nasıl çözümleneceğini |
| --- | --- | --- |
| Toplam etkin yüksek bellek (model kullanılamaz çıkarılacak içinde son üç dakika kullanımda olduğu için).<br><br> Sorgu birden çok yüksek artış sürelerini bekleyin.<br><br> Birden çok yüksek yenileme artış sürelerini bekleyin. | Bellek ölçümleri izleyebilir \[ [1](#endnote-1)\]ve çıkarma sayıları \[ [2](#endnote-2)\]. | Model boyutunu küçültün veya DirectQuery moduna dönüştürün. Bkz: [modellerini iyileştirme](#optimizing-models) bu makaledeki bir bölüm.<br><br> Ölçek artırma kapasitesi.<br><br> İçeriği farklı bir kapasiteye atayın. |

#### <a name="inefficient-report-designs"></a>Verimsiz raporu tasarımı

| Olası açıklamalar | Belirleme | Nasıl çözümleneceğini |
| --- | --- | --- |
| Rapor sayfaları, çok fazla görselleri (etkileşimli filtreleme en az bir sorgu görsel başına tetikleyebilir) içerir.<br><br> Görselleri gerekenden daha fazla veri alın. | Rapor Tasarım gözden geçirin.<br><br> Rapor kullanıcıları raporlarla nasıl etkileşim kurduklarını anlamak için görüşme.<br><br> İzleme veri kümesi sorgu ölçümleri \[ [3](#endnote-3)\]. | Sayfa başına daha az görsellerle yöntemini yeniden tasarlamaya raporlar. |

#### <a name="dataset-is-slow-especially-when-reports-have-previously-performed-well"></a>Özellikle raporlar daha önce de gerçekleştirdiğinizde veri kümesi yavaş

| Olası açıklamalar | Belirleme | Nasıl çözümleneceğini |
| --- | --- | --- |
| Giderek daha büyük miktarda verileri içeri aktar.<br><br> RLS rolleri dahil olmak üzere, karmaşık veya verimsiz hesaplama mantığı.<br><br> Tam olarak en iyi duruma getirilmiş modeli.<br><br> (DQ/LC) Ağ geçidi gecikme süresi.<br><br> Yavaş DQ kaynak sorgusu yanıt sürelerini. | Model tasarımlar gözden geçirin.<br><br> Gateway performans sayaçları izleyin. | Bkz: [modellerini iyileştirme](#optimizing-models) bu makaledeki bir bölüm. |

#### <a name="high-concurrent-report-usage"></a>Yüksek eş zamanlı rapor kullanım

| Olası açıklamalar | Belirleme | Nasıl çözümleneceğini |
| --- | --- | --- |
| Yüksek sorgu bekleme süresini.<br><br> CPU doygunluğu.<br><br> DQ/LC bağlantı sınırları aşıldı. | CPU kullanımı izleme \[ [4](#endnote-4)\], sorgu bekleme süresini ve DQ/LC kullanımı \[ [5](#endnote-5) \] ölçümleri + sorgu süreleri. Eşzamanlılık sorunları geciktirmeye olmadığını gösterebilir. | Ölçek artırma kapasitesi veya içeriği farklı bir kapasiteye atayın.<br><br> Sayfa başına daha az görsellerle yöntemini yeniden tasarlamaya raporlar. |

**Notlar:**    
<a name="endnote-1"></a>\[1\] ortalama bellek kullanımı (GB) ve en yüksek bellek tüketimi (GB).   
<a name="endnote-2"></a>\[2\] veri kümesi çıkarmaları.   
<a name="endnote-3"></a>\[3\] Dataset sorgularında, veri kümesi Ortalama Sorgu süresi (ms), veri kümesi sayısı ve veri kümesi ortalama bekleme süresi (ms) bekleyin.   
<a name="endnote-4"></a>\[4\] yüksek CPU kullanımı sayısı ve CPU süresi (son yedi gün içinde) en yüksek kullanımı.   
<a name="endnote-5"></a>\[5\] DQ/LC yüksek kullanım sayısını ve en yüksek kullanımı (son yedi gün) süresini DQ/LC.   

### <a name="why-are-reports-not-loading"></a>Neden raporlardır değil yükleniyor?

Rapor yüklenemedi kapasitesi yeterli belleğe sahip ve aşırı ısıtılan emin işareti olur. Bu, yüklenen tüm modelleri etkin olarak sorgulanan ve bu nedenle çıkarılamadığı ve herhangi bir yenileme işlemi duraklatıldı veya Gecikmeli olduğunda ortaya çıkabilir. Power BI hizmetindeki veri kümesi için 30 saniye yüklemeyi deneyecek ve kullanıcı bir öneriyle kısa süre sonra yeniden denemek için hata düzgün bir şekilde bildirilir.

Şu anda rapor için yükleme hatalarını izlemek için ölçüm yoktur. Bu sorunun olası izleme sistem belleği, özellikle en yüksek kullanımı ve en yüksek kullanım süresini belirleyebilirsiniz. Yüksek veri kümesi çıkarmaları ve uzun veri kümesi yenileme ortalama bekleme süresi, bu sorun oluştuğunu Öner.

Bu oldukça nadiren gerçekleşir, bu bir öncelik sorunu olarak kabul edilebilir değil. Rapor kullanıcıları, Hizmet meşgul ve kısa bir süre sonra yeniden denemelidir bildirilir. Çok sık böyle bir durumda, Premium kapasite ölçeklendirme veya içeriği farklı bir kapasiteye atayarak sorun çözülebilir.

Kapasite yöneticileri (ve Power BI hizmet yöneticilerinin) izleyebilirsiniz **sorgu hatası** ölçüm bu durumda belirlemek için. Ayrıca Sistem aşırı yük durumunda tüm işlemleri sıfırlama kapasite yeniden başlatabilirsiniz.

### <a name="why-are-refreshes-not-starting-on-schedule"></a>Neden yenilemeleri zamanlama başlamıyor?

Zamanlanmış yenileme başlangıç zamanlarını garanti edilmez. Arka plan işlemleri üzerinde etkileşimli işlemleri, Power BI hizmetinde her zaman sıralayacağını geri çağırma. Yenileme iki koşul karşılandığında oluşabilecek arka plan işlemi şöyledir:

- Yeterli bellek yok
- Premium kapasite için desteklenen eşzamanlı yenileme sayısı aşılırsa değil

Koşulları karşılanmadığından, yenileme koşulları karşılığında olana kadar kuyruğa alınır.

Tam yenileme için en az iki geçerli veri kümesi bellek boyutu gerekli olduğunu hatırlayın. Yeterli bellek kullanılabilir durumda değilse, ardından yenileme başlamak olamaz kadar model çıkarma belleği serbest bırakır: bir veya daha fazla veri kümesinin etkin hale gelir ve çıkartılabilir kadar bu gecikmeler anlamına gelir.

1,5 katı arka uç yuvarlanan çekirdek, desteklenen en fazla eş zamanlı yenilemeleri sayısını ayarlandığını unutmayın.

Sonraki zamanlanmış yenileme başlamak önce başlamak olamaz, zamanlanmış yenileme başarısız olur. Arabiriminden el ile tetiklenen bir isteğe bağlı yenileme, en fazla üç kez başarısız olmadan önce çalıştırmayı dener.

Kapasite yöneticileri (ve Power BI hizmet yöneticilerinin) izleyebilirsiniz **ortalama Yenile bekleme süresi (dakika)** ölçüm zamanlanan süreden işlemi başlangıcı arasındaki ortalama gecikme belirlemek için.

Zamanında verileri etkilemek için bir yönetici öncelikli genellikle yenilerken, yeterli bellek'ın kullanılabilir olduğundan emin olun. Bu, bilinen yeterli kaynaklara sahip kapasiteler veri kümelerine yalıtma gerektirebilir. Yöneticileri basamaklandırmak veya çakışmaları en aza indirmek için zamanlanmış veri yenileme zamanları azaltmaya yardımcı olmak için veri kümesi sahipleri ile koordine mümkündür. Bir yöneticinin yenileme sıranın görüntülemek için mümkün olmadığını göz önünde bulundurun veya veri kümesi almak için zamanlar.

### <a name="why-are-refreshes-slow"></a>Neden yenilemeleri yavaş?

Yenilemeler yavaş - veya algılanan (önceki yaygın soru adresleri) yavaş olabilir.

Yenileme aslında yavaş olduğunda, bunu birkaç nedeni olabilir:

- Yetersiz CPU (yenileme çok CPU kullanımı yoğun olabilir).
- Yenileme (Bu koşullar recommence karşılığında olduğunda üzerinden başlatmak için yenileme gerektirir) duraklatma içinde elde edilen yetersiz bellek.
- Veri kaynağı sistem yanıt hızını, ağ gecikme süresi, geçersiz izinleri veya ağ geçidi aktarım hızı dahil olmak üzere, olmayan-kapasite nedeniyle.
- Veri hacmi - artımlı yapılandırmak için geçerli bir nedeniniz yenileyin, aşağıda açıklandığı gibi.

Kapasite yöneticileri (ve Power BI hizmet yöneticilerinin) izleyebilirsiniz **ortalama süre (dakika) yenileme** zamanla, karşılaştırma için bir Kıyaslama belirlemek için ölçüm ve **ortalama Yenile bekleme süresi (dakika)** ölçümleri arasındaki ortalama gecikmesini belirlemek için ortalama işlem başlangıcı zamanlanan saat arasındaki gecikme.

Artımlı yenileme, özellikle büyük model tablolar için veri yenileme süresi önemli ölçüde azaltabilir. Artımlı yenileme ile ilişkili dört avantajları vardır:

- **Yenilemeler daha hızlı** - yalnızca bir alt kümesini bir tablo yüklenirken, azalan CPU ve bellek kullanımı gerekir ve birden çok bölüm yenilerken paralellik daha yüksek olabilir.
- **Yenilemeler, yalnızca gerekli olduğunda gerçekleşir** -artımlı yenileme ilkeleri, yalnızca verilerin değiştiği yüklemek için yapılandırılabilir.
- **Yenilemeler daha güvenilir** -kısa çalışan geçici veri kaynağı sistemlerine bağlantılar için bağlantı kesilmesi daha az maruz kalabilir.
- **Modelleri kalır kesim** -geçmiş zaman bir kayan pencere dışında otomatik olarak kaldırmak için artımlı yenileme ilkeleri yapılandırılabilir.

Daha fazla bilgi için bkz. [artımlı yenileme Power BI Premium'da](service-premium-incremental-refresh.md).

### <a name="why-are-data-refreshes-not-completing"></a>Neden verilerdir değil Tamamlanıyor yenilenir?

Veri yenileme işlemi, ancak tamamlanamadığında, birkaç nedeni olabilir:

- Premium kapasitede, yalnızca bir model olsa yetersiz bellek, yani model çok büyük boyutudur.
- Veri kaynağı sistem bağlantı kesilmesi, geçersiz izinler veya ağ geçidi hata da dahil olmak üzere, olmayan-kapasite nedeniyle.

Kapasite yöneticileri (ve Power BI hizmet yöneticilerinin) izleyebilirsiniz **yenileme hataları nedeniyle bellek yetersiz** ölçümü.

## <a name="optimizing-models"></a>Modellerini iyileştirme

En iyi modeli tasarımı, etkili ve ölçeklenebilir bir çözüm sunmak için çok önemlidir. Ancak, kapsamlı bir açıklama sağlamak için bu makalenin kapsamı dışındadır olur. Bunun yerine, bu bölümde anahtar alanları için göz önünde bulundurarak modelleri iyileştirirken sağlar.

### <a name="optimizing-power-bi-hosted-models"></a>Power BI en iyi duruma getirme barındırılan modelleri

Premium kapasitede barındırılan modellerde en iyi duruma getirme, veritabanları ve model katmanına gerçekleştirilebilir.

Bir içeri aktarma modeli iyileştirmesi olasılıklarını göz önünde bulundurun:

![Bir içeri aktarma modeli iyileştirmesi olasılıklarını](media/service-premium-capacity-optimize/import-model-optimizations.png)

Veri kaynağı katmanında:

- İlişkisel veri kaynakları iyileştirilebilir hızlı olası yenileme emin olmak için uygun dizinleri uygulama, artımlı yenileme dönemlerine hizalama tablo bölümleri tanımlama ve hesaplamalar düzeniyle önceden tümleştirme veri tarafından (yerine hesaplanır tablolar ve sütunlar model) veya görünümlere hesaplama mantığı ekleme.
- İlişkisel olmayan veri kaynakları önceden ilişkisel depoları ile tümleştirilebilir.
- Ağ geçitleri tercihen yakın veri kaynakları için yeterli ağ bant genişliği ile ayrılmış makineye üzerinde yeterli kaynak bulunduğundan emin olun.

Model katmanında:

- Power Query sorgu tasarımlar en aza indirmek ya da karmaşık dönüşümleri ve özellikle de farklı veri kaynakları (veri ambarları, çıkartma-dönüştürme-yükleme aşamasında bunu) birleştirme kaldırın. Ayrıca, bu uygun bir veri kaynağı gizlilik düzeylerini sağlamaya ayarlanır, bu Power BI'ın yük sorguları birleşik bir sonuç üretmek için tam sonuçları gereğini ortadan kaldırmak için.
- Model yapısını yüklemek için verileri belirler ve model boyutu doğrudan bir etkiye sahiptir. Gereksiz verileri satırları (özellikle, geçmiş veriler) kaldırma sütunları kaldırarak ya (çoğaltamaz ayrıntılı veriler yükleniyor) özetlenmiş veri yükleme yüklenmesini önlemek amacıyla tasarlanabilir. Çarpıcı boyutu azaltma, depolamaz veya çok verimli bir şekilde Sıkıştır (özellikle metin sütunları) yüksek kardinalite sütunları kaldırarak gerçekleştirilebilir.
- İki yönlü filtreleme izin vermek için yeterli bir neden olmadıkça tek yönlü ilişkiler yapılandırarak modeli sorgu performansı artırılabilir. Ayrıca kullanmayı [CROSSFILTER](https://docs.microsoft.com/dax/crossfilter-function) yönlü filtreleme yerine işlevi.
- Bu model ve sonuç boyutunu uzun yenileme sürelerini artırır ancak toplama tablolar, hızlı sorgu yanıtları yükleme tarafından özetlenmiş veriler, önceden elde edebilirsiniz. Genellikle, toplama tabloları çok büyük modelleri veya bileşik model tasarımları için ayrılan.
- Hesaplanmış tablolar ve sütunlar model boyutunu artırabilir ve uzun yenileme kez neden. Verilerin gerçekleştirilmiş ya da veri kaynağı, hesaplanan, genellikle daha küçük depolama boyutu ve hızlı bir yenileme süresi gerçekleştirilebilir. Bu mümkün değilse, özel sütunlar Power Query kullanarak geliştirilmiş depolama sıkıştırma sunabilir.
- Ölçüler ve belki de pahalı formülleri önlemek için mantıksal yeniden yazma RLS kuralları için DAX ifadeleri ayarlamak için bir fırsat olabilir.
- Artımlı yenileme önemli ölçüde yenileme süresini kısaltmak ve bellek ve CPU tasarrufu yapar. Artımlı yenileme, model boyutları kırpma tutma geçmiş verileri kaldırmak için de yapılandırılabilir.
- Farklı ve çakışan sorgu desenleri olduğunda bir model iki modeli baştan tasarladık. Örneğin, 24 saat gecikme raporlar bazı mevcut üst düzey toplamalar tüm geçmişi ve can üzerinden tolerans. Diğer raporları, bugünün verileri ile ilgili bir kaygınız ve tek işlemler için ayrıntılı erişim gerekir. Tüm raporları karşılamak için tasarım yerine tek bir model, her gereksinim için en iyi duruma getirilmiş iki modeller oluşturun.

Bir DirectQuery modeli iyileştirmesi olasılıklarını göz önünde bulundurun. Model için temel alınan veri kaynağına sorgu isteği sorunlar gibi hızlı yanıt veren model sorgular sunmak için veri kaynağı iyileştirme önemlidir.

 ![İyileştirme olasılıklarına dair bir DirectQuery modeli için](media/service-premium-capacity-optimize/direct-query-model-optimizations.png)

Veri kaynağı katmanında:

- Veri kaynağı için iyileştirilmiş hızlı olası uygun dizinleri uygulama (model katmanında mümkün değildir) verileri önceden tümleştirerek sorgulama emin olmak için tablo bölümleri, düzeniyle tanımlama (dizinli görünümlerle), veri özetlenir ve Hesaplama en aza indirir. Doğrudan sorgular yalnızca filtre ve dizinli tabloları veya görünümleri arasında iç birleştirmeler gerçekleştirme ihtiyacınız olduğunda en iyi deneyimi elde edilir.
- Ağ geçitleri tercihen makinelerde adanmış, yeterli ağ bant genişliği ve veri kaynağı olarak yakınında yeterli kaynak bulunduğundan emin olun.

Model katmanında:

- Güç sorgu sorgu tasarımları hiçbir dönüştürme - uygulanması tercihen Aksi takdirde dönüştürmeler mutlak en az değerde tutmak çalışır.
- İki yönlü filtreleme izin vermek için yeterli bir neden olmadıkça tek yönlü ilişkiler yapılandırarak modeli sorgu performansı artırılabilir. Ayrıca, modeli ilişkileri (Bu durum söz konusu olduğunda) bilgi tutarlılığını zorunlu varsaymak yapılandırılmalıdır ve daha verimli İç birleşimler (yerine outer JOIN) kullanarak veri kaynağı sorguları neden olur.
- Power Query sorgu özel sütunları veya modeli hesaplanmış sütun oluşturmamaya özen gösterin: Bu veri kaynağı, mümkün olduğunda depolanabildiği.
- Ölçüler ve belki de pahalı formülleri önlemek için mantıksal yeniden yazma RLS kuralları için DAX ifadeleri ayarlamak için bir fırsat olabilir.

Bileşik bir model iyileştirmesi olasılıklarını göz önünde bulundurun. Geri çağırma bileşik bir model içeri aktarma ve DirectQuery tablolar bir karışımını sağlar.

![Bileşik bir model iyileştirmesi olasılıklarını](media/service-premium-capacity-optimize/composite-model-optimizations.png)

- Genellikle, içeri aktarma ve DirectQuery modelleri için en iyi duruma getirme, bu depolama modları kullanan bileşik model tablolara uygulanır.
- Genellikle, boyut türüyle tabloları (iş varlığı temsil eden) yapılandırarak dengeli bir tasarım elde etmek DirectQuery depolama modu olarak çift depolama modu ve türü olgu tabloları (genellikle büyük tablolar işletimsel bilgiler temsil eden) çaba. Çift depolama modu hem de içeri aktarma ve DirectQuery depolama modu ve bu sağlayan doğrudan bir yerel sorgu oluşturulurken kullanılacak en verimli depolama modu belirlemek Power BI hizmetinde anlamına gelir.
- Ağ geçitleri tercihen yakın veri kaynakları için yeterli ağ bant genişliği ile ayrılmış makineye üzerinde yeterli kaynaklara sahip olduğunuzdan emin olun
- DirectQuery depolama modu türü olgu tabloları özetlemek için kullanıldığında çarpıcı sorgu performansı geliştirmeleri alma depolama modunu sunabilir olarak toplamalar tabloları yapılandırılmış. Bu durumda, toplama tablo modeli boyutunu artırın ve yenileme süresini artırmak ve daha hızlı sorgular için kabul edilebilir bir tradeoff genellikle budur.

### <a name="optimizing-externally-hosted-models"></a>Modelleri barındırılan harici olarak en iyi duruma getirme

Birçok iyileştirme olasılıklarına dair ele [Power BI en iyi duruma getirme barındırılan modelleri](#optimizing-power-bi-hosted-models) bölüm geçerli da Azure Analysis Services ve SQL Server Analysis Services ile geliştirilen modelleri. Şu anda, bileşik bir model ve toplama tablolar gibi desteklenmeyen bazı özellikler Temizle durumlardır.

Harici olarak barındırılan veri kümeleri için ek bir konu ile ilgili olarak Power BI hizmetini barındıran bir veritabanıdır. Azure Analysis Services için Power BI kiracınızın (ana bölge) ile aynı bölgede Azure kaynağını oluşturma anlamına gelir. Iaas için SQL Server Analysis Services için aynı bölgede VM'yi barındıran anlamına gelir ve şirket içi için bu etkili bir ağ geçidi sağlama anlamına gelir.

Azure Analysis Services veritabanları ve SQL Server Analiz Hizmetleri tablo veritabanlarında modellerini belleğe tam olarak yüklenmesi gerektirir ve bunlar var. hiç kalmasını sorgulamayı destekleme konusunda zaman unutmayın ilgi, dallarınız kaynaklanıyor olabilir. Power BI hizmetinde gibi var. model yenileme işlemi sırasında çevrimiçi kalması durumunda yenilemek için yeterli bellek olması gerekir. Power BI hizmetinde, bellek kullanımı göre içine ve dışına modelleri otomatik olarak eski konsepti yoktur. Power BI Premium, bu nedenle, daha düşük bellek kullanımı ile modeli sorgulama en üst düzeye çıkarmak için daha etkili bir yaklaşım sunar.

## <a name="capacity-planning"></a>Kapasite planlama

Kullanılabilir bellek ve işlemci kaynaklarının ve sınırları ve kapasite üzerinde uygulanan bir Premium kapasite boyutunu belirler. Premium kapasiteler de önemli bir unsur sayısıdır oluşturmayla birden fazla Premium kapasiteleri iş yüklerini birbirinden yalıtmak yardımcı olabilir. Depolama kapasitesi düğüm başına 100 TB olduğu ve her türlü iş yükü için yeterli birden büyük olasılıkla budur unutmayın.

Premium kapasiteler sayısı ve boyutu belirleme, oluşturduğunuz özellikle ilk kapasiteleri için zor olabilir. Ortalama iş yükü temsil eden anlamak için kapasite boyutlandırmasını olduğunda ilk adımı, günlük kullanım bekleniyor. Tüm iş yükleri eşit olduğunu anlama açısından önemlidir. Örneğin - uzanan bir Spektrum - sonunda tek bir görsel içeren tek bir rapor sayfasının erişme 100 eşzamanlı kullanıcıya kolayca ulaşılabilir. Henüz - - spektrumun diğer ucunda 100 farklı raporlar erişme 100 eşzamanlı kullanıcıya her 100 görselleri rapor sayfasında gittiğini kapasite kaynakları çok farklı taleplerini olun.

Kapasite yöneticileri, bu nedenle faktörlerden ortamı, içerik ve beklediğiniz kullanım için belirli göz önünde bulundurmanız gerekir. Geçersiz kılma hedefi tutarlı sorgu süreleri, kabul edilebilir bekleme süresini ve çıkarma oranları göndermeye çalışırken kapasite kullanımını en üst düzeye sağlamaktır. Göz önünde bulundurmanız gereken faktörler şunları içerebilir:

- **Model boyutu ve veri özelliklerini** -içeri aktarma modelleri sorgulama veya yenilemeye izin belleğe tam yüklü olmalıdır. LC/DQ veri kümeleri, önemli bir işlemci süresi ve karmaşık bir ölçü veya RLS kuralları değerlendirilemiyor büyük olasılıkla önemli bellek gerektirebilir. Kapasite boyutu tarafından bellek ve işlemci boyutu ve LC/DQ sorgu aktarım kısıtlanmıştır.
- **Eş zamanlı active modelleri** -bunlar bellekte kaldığında farklı alma modelleri, eş zamanlı sorgulama en iyi yanıt süresi ve performans sunar. Kendi yenileme için izin vermek için ek belleğe sahip tüm yoğun olarak sorgulanan modellerini barındırmak için yeterli bellek olmalıdır.
- **İçeri aktarma model yenileme** -bellek ve işlemci kullanım özellikle yenileme türü (tam veya artımlı), süresi ve Power Query sorguları ve hesaplanmış tablo sütunu mantıksal karmaşıklığı etkileyebilir. Eşzamanlı yenileme kapasite boyutunu (1.5 x backend yuvarlanan çekirdek,) göre kısıtlanır.
- **Eş zamanlı sorguları** -çok sayıda eş zamanlı sorgu sonuçlanabilir yanıt zaman raporlarının işlemci veya LC/DQ bağlantıları kapasite sınırını aşıyor. Bu, özellikle çok sayıda görsel içeren bir rapor sayfaları için durum geçerlidir.
- **Veri akışlarını ve sayfalandırılmış raporlar** -kapasitesi, veri akışlarını ve her bir yapılandırılabilir maksimum kapasite bellek yüzdesi gerektiren ile sayfalandırılmış raporları desteklemek için yapılandırılabilir. Bellek, veri akışlarını için dinamik olarak ayrılır, ancak sayfalandırılmış raporlar için statik olarak ayrılır.

Bu etkenler yanı sıra kapasite yöneticileri birden fazla kapasite oluşturma düşünebilirsiniz. Birden çok kapasiteler izin vermek için iş yükü yalıtımı ve öncelikli iş yükleri kaynakları garanti olmak için yapılandırılabilir. Örneğin, iş açısından kritik iş yükleri, Self Servis BI (SSBI) iş yüklerini birbirinden ayırmak için iki kapasiteler oluşturulabilir. İş açısından kritik kapasite, bunları yalnızca BT departmanı için verilen erişim yazımıyla garanti edilen kaynaklarla sağlayarak büyük kurumsal modelleri yalıtmak için kullanılabilir. SSBI kapasite, iş analistleri için verilen erişimi olan daha küçük modelleri, artan sayıda barındırmak için kullanılabilir. SSBI kapasite bazen fazla sorgu veya yenileme bekler karşılaşabilirsiniz.

Zamanla, kapasite yöneticileri çalışma alanlarının kapasiteler arasında içerik çalışma alanları veya çalışma alanlarının kapasiteler arasında arasında taşıyarak ve kapasiteler ölçeği artırılabilen veya azaltılabilen dengeleyebilirsiniz. Genellikle, daha büyük konak modelleri, Ölçek artırma ve daha yüksek Eş zamanlılık için ölçeği.

Bir lisans satın alma çekirdek kiracıyla sağladığını unutmayın. Satın alındığında bir **P3** aboneliği oluşturun veya dört Premium kapasiteleri için yedekleme için kullanılabilir yani P3 veya P2 x 2 veya 4 x 1 x P1. Ayrıca, bir P2 kapasite P3 kapasiteye yükseltme önce göz önünde bulundurarak çekirdek bölme için iki P1 kapasiteler oluşturmak için verilebilir.

## <a name="testing-approaches"></a>Test yaklaşımları

Kapasite boyutunu karar sonra test denetimli bir ortamda oluşturarak gerçekleştirilebilir. Pratik ve ekonomik bir seçenek P1 kapasiteli bir A4 kapasite, P2 ile aynı boyutta olduğunu gösteren bir Azure (A SKU'lar) kapasite ve P3 kapasiteler A5 ve işler için A6 kapasiteler aynı boyutta sırasıyla oluşturmaktır. Azure kapasitelerinin hızla oluşturulabilen ve saatlik olarak faturalandırılır. Sınama aşaması tamamlandıktan sonra bu nedenle, bunlar kolayca maliyet tahakkuk durdurmak için silinebilir.

Test içeriği, Azure ve kapasite üzerinde oluşturulan çalışma alanlarına eklenen ve ardından tek bir kullanıcı gerçekçi ve temsili iş yükü sorguları oluşturmak için rapor çalıştırabilirsiniz. İçeri aktarma modelleri varsa, her model için bir yenileme ayrıca gerçekleştirilmesi gerekir. İzleme Araçları sonra kaynak kullanımını anlamak için tüm ölçümleri gözden geçirmek için kullanılabilir.

Testleri tekrarlanabilir önemlidir. Testlerinizi birkaç kez çalıştırmanız gerekir ve her seferinde yaklaşık aynı sonucu teslim. Bu sonuçları Ortalama tahmin etmeniz ve doğru üretim koşullar altında bir iş yükü tahmin etmek için kullanılabilir.

Stres testi oluşturmak için bir yük testi gerçekçi bir iş yükünün benzetimini yapmak için uygulama geliştirme göz önünde bulundurun. Bunu başarmak nasıl ayrıntılarını, bu makalenin kapsamı dışında olan. Bir kod örneği de dahil olmak üzere daha fazla bilgi için başvurmak [Power BI uygulamalarda yük testi yapma Visual Studio Yük testi ile](https://blogs.msdn.microsoft.com/charles_sterling/2018/04/04/webinar-load-testing-power-bi-applications-with-visual-studio-load-test/) Web Semineri.

## <a name="acknowledgements"></a>Onayları

Bu makale, Peter Myers, veri platformu MVP ve bağımsız BI Uzmanı ile yazılmıştır [Bitsel çözümleri](https://www.bitwisesolutions.com.au/).

## <a name="next-steps"></a>Sonraki adımlar

> [!div class="nextstepaction"]
> [Premium kapasite senaryoları](service-premium-capacity-scenarios.md)   
  
Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)

||||||