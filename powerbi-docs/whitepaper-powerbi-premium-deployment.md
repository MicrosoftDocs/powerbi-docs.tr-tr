---
title: Power BI Premium kapasitelerini yönetme ve dağıtma
description: Power BI Premium potansiyelini anlamak ve tasarlama, dağıtma, izleme ve sorun giderme ölçeklenebilir çözümler hakkında bilgi edinin.
author: mgblythe
ms.author: mblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 03/06/2019
LocalizationGroup: Premium
ms.openlocfilehash: fbae2a8b577c52ae597d44bd6ea9913510c4c65c
ms.sourcegitcommit: dc73e932c9982a4aa0b0ec5297fb9f94c6156bc5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66518558"
---
# <a name="deploying-and-managing-power-bi-premium-capacities"></a>Power BI Premium kapasitelerini yönetme ve dağıtma

**Özet:** Power BI Premium, kuruluşunuzdaki herkes için daha tutarlı bir performans, büyük veri hacimleri için destek ve birleşik bir Self Servis ve kurumsal BI platformu esnekliğini sunar. Bu düzey 300 teknik incelemedir özellikle Power BI yöneticileri ve içerik yazarlarının ve yayımcılar için yazıldı. Bu amaçlar, Power BI Premium potansiyelini anlamalarına yardımcı olmak ve tasarlama, dağıtma, izleme ve sorun giderme ölçeklenebilir çözümler yapılacağı açıklanmaktadır.

**Yazar:** [Peter Myers](https://www.linkedin.com/in/peterjsmyers) (veri platformu MVP ve bit düzeyinde çözümleriyle bağımsız BI uzmanı)

**Teknik Açıdan Gözden Geçirenler:** ADAM Saxton, Akshai Mirchandani, Bhavik satıcı, David Magar, Josh Caplan, Michael Blythe, Nimrod Shalit, yazan Matrat, Swati Gupta

**Uygulama hedefi:** Power BI hizmetinde, Power BI Premium ve Azure Power BI Embedded kapasitesi

> [!NOTE]
> Tarayıcınızdan **Yazdır**’ı ve ardından **PDF olarak kaydet**’i seçerek bu teknik incelemeyi yazdırabilir veya kaydedebilirsiniz.

## <a name="introducing-power-bi"></a>Power BI ile tanışın

Power BI, hızlı, bilgiye dayalı kararlar öngörüleri sunmak için tasarlanan bir İş analizi hizmetidir. Kendi sürümde bir 2015 itibaren hızlı bir şekilde en büyük kuruluşların en küçük çözümleri sunmak için kullanılan popüler bir hizmet haline gelmiştir kuruluşların.

Bunu iki şekilde kullanılabilir: Şirket içi ve bulut hizmeti olarak çözüm raporlama adlı **Power BI rapor sunucusu**. \[[1](#endnote-01)\]

Bir bulut hizmeti olarak bir-hizmet yazılım (SaaS) olduğu gibi Power BI \[ [2](#endnote-02)\]. Bu hizmetler ve geliştirme, dağıtma, yönetme, iş izlemek için çözüm paylaşın, kuruluşların uygulamalar kümesini temsil eder.

Power BI hizmetinde kapsamlı bir açıklamasını sağlamak için bu teknik incelemede amacınıza değil. Bunun yerine, Power BI Premium konusunun ilgili konuları odaklanır. Power BI hakkında genel bilgi için başvurmak için kapsamlı [Power BI belgeleri](service-admin-premium-multi-geo.md). İyi performans gösteren Kurumsal dağıtımlar elde etmeye odaklanın bir Power BI hizmetiyle daha ayrıntılı bir açıklaması için başvurmak için kapsamlı [Power BI Enterprise dağıtımı planlama](https://aka.ms/pbienterprisedeploy) teknik incelemesi.

Bu bölümde, bu teknik incelemede ait konu bağlamında tanıtır ve kapasite, Power BI içerik türleri, model depolama modları ve lisanslama açıklar. Bu konularda bir anlayış, başarılı bir şekilde dağıtma ve Power BI Premium'u yönetme için gereklidir.

### <a name="capacities"></a>Kapasiteler

**Kapasiteleri** barındırmak ve Power BI sunmak için kullanılan kaynakları (depolama, işlemci ve bellek) kümesini temsil eden bir çekirdek Power BI kavramı içerik olan getirin. Kapasiteleri ya da paylaşılan ayrılmış veya. A **paylaşılan kapasiteye** olduğu diğer Microsoft müşterilerle paylaşılır, while bir **adanmış kapasite** tek bir müşteriye tam olarak taahhüt eder. Adanmış kapasite tanıtılır [Premium kapasiteleri](#premium-capacities) konu.

Paylaşılan kapasitede, diğer müşterilerle paylaşılan hesaplama kaynaklarında iş yüklerini çalıştırın. Kapasite kaynakları paylaşmalıdır gibi sınırlamaları "serginin play", en fazla model boyutu (1 GB) ve en fazla günlük yenileme sıklığını (sekiz katı günlük) gibi emin olmak için uygulanmaktadır.

### <a name="workspaces"></a>Çalışma alanları

Power BI çalışma alanları kapasitelerini bulunduğu ve güvenlik, işbirliği ve dağıtım kapsayıcıları temsil ederler. Her Power BI kullanıcısı olarak bilinen bir kişisel çalışma alanı olan **çalışma Alanım**. İşbirliği ve dağıtımı etkinleştirmek için ek bir çalışma alanı oluşturulabilir ve bunlar olarak bilinen **uygulama çalışma alanları**. Varsayılan olarak, paylaşılan kapasitede çalışma alanları - kişisel çalışma alanlarını dahil olmak üzere - oluşturulur.

### <a name="power-bi-content-types"></a>Power BI içerik türleri

Power BI Premium konuları tanıtmak için Power BI mimarisinin temel içerik türleri dahil olmak üzere kapsamlı bir tartışma ile başlatmak önemlidir.

Tüm Power BI içeriğini depolanan ve Power BI içeriği için kapsayıcılar olan çalışma alanları içinde yönetilir. Her Power BI kullanıcısı için kendi kişisel çalışma alanı olsa da, genel en iyi uygulama çalışma alanları oluşturmaktır. Uygulama çalışma alanları co-ownership içeriği ve içerik üzerinde işbirliği yapma olanağı sağlar. Aşama ve uygulamaları olarak geniş kitlelere içerik dağıtmak için özelliği de sağlar.

Power BI içeriğini aşağıdaki çalışma alanlarında depolanır:

- Veri akışları
- Veri kümeleri
- Çalışma Kitapları
- Raporlar
- Panolar

#### <a name="dataflows"></a>Veri akışları

Power BI veri akışlarını kuruluşların farklı kaynaklardan verileri birleştirme yardımcı olur. Bunlar kaynağı olarak doğrudan raporlama için kullanılamaz ancak hazırlanan ve modeller, kullanım için hazırlanır veri olarak düşünülebilir. Bunlar, Microsoft Veri bağlayıcıları, şirket içi ve bulut tabanlı veri kaynaklarını veri alımı etkinleştirme kapsamlı koleksiyonunu yararlanın.

Veri akışlarını yalnızca oluşturulabilir ve uygulama çalışma alanları, yönetilen ve Azure Data Lake depolama Gen2 ortak veri modeli (CDM) içindeki varlıklar olarak depolanır. Genellikle, bunlar güncel verileri depolamak için düzeltildikçe yenilemek için zamanlanır.

Daha fazla bilgi için bkz [Self Servis veri hazırlama (Önizleme) Power BI'da](service-dataflows-overview.md) belge.

#### <a name="datasets"></a>Veri kümeleri

Power BI veri kümeleri, veri raporlama ve görselleştirme için hazır bir kaynağı temsil eder. Tarafından oluşturulan veri kümeleri, birçok tür vardır:

- Bir Power BI kapasite barındırılmayan var olan bir veri modeli bağlanma
- Bir modeli içeren bir Power BI Desktop dosyası karşıya yükleniyor
- (Bir veya daha fazla Excel tabloları ve/veya bir çalışma kitabı veri modeli içeren) bir Excel çalışma kitabını karşıya yükleme veya bir virgül ile ayrılmış değer (CSV) dosyasını karşıya yükleme
- Bir anında iletme oluşturmak için Power BI hizmetini kullanarak, akış veya karma akış veri kümesi

Akış veri kümeleri hariç \[ [3](#endnote-03)\], Analysis Services'ın olgun modelleme teknolojilerden yararlanan bir veri modeline veri kümesini temsil eder.

Belgelerde, bazen terimler veri kümeleri ve modelleri birbirinin yerine olduğunu unutmayın. Genellikle, bir Power BI hizmeti açısından bakıldığında, olarak adlandırılır bir **veri kümesi** , geliştirme açısından da olarak adlandırılır ve bir **model**. Bu teknik yazı bağlamında, bunlar aynı işe anlamına gelir.

##### <a name="externally-hosted-models"></a>Harici olarak barındırılan modelleri

Harici olarak barındırılan bir modele bağlanma içerir yükleme [şirket içi veri ağ geçidi](service-gateway-onprem.md) şirket içi veya sanal makine tarafından barındırılan olarak bir-hizmet altyapı (Iaas) olup olmadığını, SQL Server Analysis Services'e bağlanmak için. Azure Analysis Services, bir ağ geçidi gerektirmez. Model ilişkin mevcut yatırım varken genellikle bölümü kurumsal veri ambarı (EDW) oluşturan bu senaryo genellikle mantıklıdır. Power BI'ın gerçekleştirmeyi sağlayan bir **canlı bağlantı** (LC) Analysis Services ve Power BI rapor kullanıcı kimliğini kullanarak veri izinleri zorlayarak bunu yapar. SQL Server Analysis Services için hem çok boyutlu modeller (küpleri) hem de tablolu modellerde desteklenir. Aşağıdaki görüntüde gösterildiği gibi bir canlı bağlantı veri sorguları için harici olarak barındırılan modelleri geçirir.

![Bir canlı bağlantı veri sorguları için harici olarak barındırılan modelleri geçirir.](media/whitepaper-premium-deployment/live-connection-dataset.png)

##### <a name="power-bi-desktop-developed-models"></a>Power BI Desktop tarafından geliştirilen modelleri

Power BI Desktop - Power BI geliştirme için hedeflenen bir istemci uygulaması - Analysis Services tablolu modeline etkili olan bir model geliştirmektir kullanılabilir. Modelleri, verileri diğer veri kaynaklarıyla tümleştirilebilir veri akışı alma tarafından geliştirilebilir. Özellikleri üzerinde nasıl modelleme elde ederken olduğundan bu teknik incelemede kapsamı dışında üç farklı türleri - veya modları - Power BI Desktop kullanılarak geliştirilebilir modelleri bulunduğunu anlamak önemlidir. Bu modları olup veri modeline aktarılır veya veri kaynağındaki kaldığı belirler. Üç moddan şunlardır: Import, DirectQuery ve bileşik. Her modunun kapsamlı bir açıklama içinde ele alınacak [Model depolama modları](#model-storage-modes) konu.

Satır düzeyi güvenlik (belirli bir kullanıcı için alınan verileri sınırlamak için RLS), harici olarak barındırılan modelleri ve Power BI Desktop'ta geliştirilen model uygulayabilir. Örneğin, satış temsilcilerinin güvenlik grubuna atanan kullanıcılar yalnızca atanmış olan satış alımımın rapor verilerini görüntüleyebilir. RLS rolleri, dinamik veya statik olabilir. **Dinamik Rolleri** rapor kullanıcısı tarafından filtre sırada **statik rolleri** role atanmış tüm kullanıcılar için aynı filtre uygulayın.

##### <a name="excel-workbook-models"></a>Excel çalışma kitabı modelleri

Excel çalışma kitaplarını veya CSV göre veri kümeleri oluşturma dosyaları otomatik olarak oluşturulmasını bir modeli neden olur. Excel tabloları ve CSV verileri bir Excel çalışma kitabı veri modelini Power BI modeli oluşturmak için yorumlanabileceğinden modeli tabloları oluşturmak için içeri aktarılır. Her durumda, dosya verilerini bir modeline aktarılır.

Farklılıklar, sonra modeli temsil eden Power BI veri kümeleri hakkında yapılabilir:

- Power BI hizmetinde ya da barındırılan veya harici olarak Analysis Services tarafından barındırılan
- İçeri aktarılan verileri depolayabilir miyim veya bunların geçiş sorgu isteği temel alınan veri kaynakları veya her ikisinin bir karışımı verebilir

Modelleri temsil eden bir Power BI veri kümeleri hakkında önemli bilgiler bir özeti aşağıda verilmiştir:

- Barındırılan SQL Server Analysis Services modellerine LC sorguları gerçekleştirmek için bir ağ geçidi gerektirir.
- Veri alma power BI tarafından barındırılan modelleri
  - Böylece bunlar sorgulanabilir belleğe tam yüklü olması gerekir
  - Verilerin güncel kalmasını sağlamak için yenileme gerektirir ve kaynak verileri doğrudan Internet üzerinden erişilebilir değil, ağ geçitleri kapsaması gerekir
- DirectQuery (DQ) depolama modunu kullanması power BI tarafından barındırılan modelleri, kaynak veri bağlantısı gerektirir. Model sorgulandığında, Power BI geçerli verileri almak için kaynak verileri sorgular verir. Bu mod, kaynak verileri doğrudan Internet üzerinden erişilebilir değil, ağ geçitleri kapsaması gerekir.
- Modelleri belirli kullanıcıların veri erişimini sınırlamak için filtreleri zorlamayı RLS kurallarını zorla

Başarılı bir şekilde dağıtın ve Power BI Premium'u yönetme için modelleri barındırıldığı, kendi depolama modu, ağ geçitleri, içeri aktarılan verilerin boyutu bağımlılıkları anlamak ve türünü ve sıklığını yenilemek önemlidir. Bu tüm önemli bir etkisi Power BI Premium kaynaklara sahip olabilir. Ayrıca, modeli tasarım kendisini hesaplamaları ve veri hazırlık sorguları da dahil olmak üzere ilgili önemli noktalar Karışıma ekleyebilirsiniz.

Power BI tarafından barındırılan alma modelleri, zamanlamaya göre yenileyin veya olması isteğe bağlı Power BI hizmetinde bir kullanıcı tarafından tetiklenen anlamak önemlidir.

En iyi duruma getirilmiş modelleri tasarlama ele alınmıştır daha sonra bu teknik yazıda [en iyi duruma getirme modelleri](#optimizing-models) konu.

#### <a name="workbooks"></a>Çalışma Kitapları

Power BI çalışma kitapları, bir Power BI içerik tür \[ [4](#endnote-04)\]. Excel çalışma kitaplarını Power BI hizmetine yüklenir ve veri kümeleri (modeller) oluşturma karşıya yüklenen Excel çalışma kitapları ile karıştırılmamalıdır değildirler. Çalışma kitabı içerik türü Power BI hizmetinde ya da karşıya yüklenemedi veya OneDrive veya SharePoint Online'daki bulut depolama alanında kalır bir çalışma kitabı bağlantısını temsil eder.

Bu içerik türü için Power BI veri görselleştirmeleri bir veri kaynağı olarak kullanılabilir olmadığını anlamak önemlidir. Bunun yerine, bir çalışma kitabını Power BI hizmetinde olarak Excel Online'ı kullanarak açabilirsiniz. Bu içerik türünden ana amaç, eski Excel çalışma kitabı raporları erişilebilir Power BI hizmetinde ve Power BI panolarına sabitlenmiş olmak için kendi veri Görselleştirmelerini izin vermek için izin vermektir.

Daha fazla bilgi için bkz [Excel çalışma kitabı dosyalarından veri alma](service-excel-workbook-files.md) belge.

#### <a name="reports"></a>Raporlar

İki rapor türü vardır: Power BI raporları ve sayfalandırılmış raporlar.

**Power BI raporları** etkileşimli veri görselleştirmesi yalnızca tek bir veri kümesi için bağlayan deneyimler sağlar. Rapor özellikleri, olağanüstü bir dizi ile etkileşim kurmak için kullanıcı katılımı teşvik etmek için tasarlanan genellikle filtreleme, dilimleme, dahil olmak üzere çapraz filtreleme ve vurgulama, Yukarı ayrıntılara, detaya gitme, soru- cevap doğal, araştırıp bulma Dil sormasını, gezinti, spotlighting, görüntüleme yer işaretleri ve daha fazla odaklanan sayfa.

Bu teknik yazı bağlamında anlamak önemlidir nasıl Power BI mimarisi, Power BI rapor tasarımı ve Kullanıcı etkileşimlerine tüm Power BI hizmeti kaynakları üzerinde etkileyebilir:

- Yüklemek ve içeri aktarma modellerine göre raporlarla etkileşim kurmak için model (Power BI hizmetinde veya harici olarak barındırılan olup olmadığını) belleğe tam yüklü olmalıdır
- Veri modeli sorgulayarak almak için bir sorgu her rapor görselini sorunları
- Genel olarak, model sorgulanırken filtre ve dilimleyici etkileşimleri içerir. Örneğin, bir Dilimleyici seçimi değiştirme Varsayılan olarak - sayfasında her bir görselin yeniden yükleme gerektirir \[ [5](#endnote-05)\]
- Power BI raporlarını görüntüleme geçerli veri garanti ve rapor sayfanızı ve kendi görsellerinizi yeniden yüklemek için raporu yenilemek kullanıcının gerektirebilir
- Kullanıcılar ile soru görüşebilirsiniz & Power BI rapor tasarımı sağlayarak sorularınızı sormak için doğal dil özelliği izin verir ve veri kümesini Power BI tarafından barındırılan bir veri içeri aktarma modeli veya soru- cevap'ı etkinleştirmek için yapılandırılmış bir LC veri kümesini temsil eder.

**Sayfalandırılmış raporlar** yayını sağlayan ve SQL Server Raporlama Hizmetleri (SSRS) raporları oluşturma (\*.rdl biçimi). Kendi adından da anlaşılacağı gibi sayfalandırılmış raporlar gereksinimleri sabit sayfa boyutu yazdırmaya ihtiyaç dikte veya tümüyle genişletilmelidir veri değişken listeleri olduğunda yaygın olarak kullanılır. Örneğin, birden çok sayfa işleme (yerine bir görselde kaydırma) için tasarlanmış bir fatura ve yazdırma.

Seçim iki desteklenen rapor türleri sağlamak için rapor yazarları, bunları türünü seçmeye izin verme gereksinimlerine göre ve yönelik kullanın. Genellikle, Power BI raporları için keşfetmek ve sayfalandırılmış raporlar daha parametresi temelli sayfa düzenleri için uygun olsa, verilerden Öngörüler keşfetmek kullanıcının etkileşimli deneyimleri idealdir.

Rapor türü ne olursa olsun (filtrelerin veya parametrelerin değiştirildiğinde) esnek rapor yük ve veri güncelleştirmeleri elde güvenilir ve daha iyi performans gösteren bir kullanıcı deneyimi sunmak için zorunludur.

#### <a name="dashboards"></a>Panolar

Power BI panoları izleme deneyimler sunmak üzere tasarlanmıştır ve kavramsal olarak Power BI raporlarını çok farklı. Panoları, kutucukları değerler ve verilerle görselleştirmelerinde ifade etmek için tek bir cam bölmeyle ekranda için tasarlanmıştır. Genellikle, panoları etkileşimi bekleniyor bazı Pano Tasarımlı Power BI raporları ve daha az etkileşim deneyimleri sunar. Örneğin, bir sunucu odada olmayan dokunmatik ekran üzerinde sunulan bir katılımsız Pano. Başka bir önemli fark, panoları Power BI sırasında birden fazla veri kümesi kaynak verileri her zaman sadece tek bir veri kümesi tabanlı rapor kutucukları sunabilir olmasıdır.

Bir pano, hızlı bir şekilde yüklemek için tasarlanmıştır ve en güncel verileri (Power BI hizmetinde bilinen) hiç ifade etmek için zaman anlamak önemlidir. Bu kutucuk sorgu sonuçlarını önbelleğe alarak ulaşır ve her bir Pano için bunu yapar. Aslında, onu zorla dinamik RLS modellerde dayalı olarak bir Pano erişimi olan her bir kullanıcı için bunu yapmanız gerekir.

Power BI tarafından barındırılan alma modelleri hemen yenilenir sonra Power BI hizmetinde Pano sorgu önbelleklerini otomatik olarak güncelleştirir. LC ve DQ modelleri söz konusu olduğunda, veri kümesi sahibi düzeyde bir denetiminiz ne sıklıkta Power BI hizmetinde sık olarak 15 dakikada veya haftada bir seyrek olarak yapılandırılabilir önbelleği güncelleştirir sahiptir. LC sorgu önbelleği güncelleştirmelerini önce model meta verilerini, model yenileme önbellek son güncelleştirmeden bu yana gerçekleştirilen ve onu bir yenileme değil beri oluşmadığında önbelleğini güncelleştirmeye devam etmeyecek olup olmadığını belirlemek için sorgu unutmayın. Bu onay DQ modelleri için mümkün değildir ve bu nedenle güncelleştirmelerini önbelleğe kaynak verileri veya değişip değişmediğini olacağını.

Pano sorgu önbelleği temel alınarak DQ güncelleştirir ve LC modelleri hem Power BI hizmeti kaynaklarına hem de dış veri kaynaklarına önemli ölçüde etkileyebilir. Bir Azure Analysis Services modelinde, dinamik RLS zorlar, saatte bir yenilenir ve bu panoyu 100 kullanıcı ile paylaşılan alarak tüm 20 kutucuklar içeren Pano göz önünde bulundurun. Veri kümesi saatte yenilemek için yapılandırılmışsa, LC sorguları 2000'de en az (20 x 100) neden olur. Bu Power BI hizmetinde ve dış veri kaynakları üzerinde muazzam bir yük yerleştirin ve kullanılabilir kaynaklara uygulanan sınırları aşabilir. Kapasite kaynakları ve sınırları içinde açıklanmıştır [kapasite düğümleri](#capacity-nodes) konu.

Kullanıcılar bir panoyu Power BI hizmet kaynakları gerektiren çeşitli şekillerde etkileşim kurabilir. Özellikle, yönetici şunları yapabilir:

- Tüm ilgili Power BI tarafından barındırılan bir veri alma modelleri bir isteğe bağlı yenileme sonuçta panolara kutucuk yenileme tetiklemek
- Soru- cevap doğal dil özelliği ile soru sorun (Pano tasarımı izin verir ve veri kümesini Power BI tarafından barındırılan bir veri içeri aktarma modeli veya soru- cevap'ı etkinleştirmek için yapılandırılmış bir LC veri kümesi sağlama) için etkileşim kurun
- Power BI için hızlı Öngörüler özelliğini kullanma, bir temel alınan veri kümesi ve yanıt görüntülemek ve bunları (sağlayarak kutucuğu Power BI tarafından barındırılan bir veri içeri aktarma modeli olan bir veri kümesini temel alır) açıklayan görsellerle keşfedin
- Uyarıları gerektiren eşik değerleri - büyük olasılıkla olabildiğince sık saatlik - kutucuğuna ve eşikler aşıldığında kullanıcıları bilgilendirmek için karşılaştırmak için Power BI hizmetinde Pano kutucukları hakkında yapılandırma (kutucuk tek bir sayısal değer görüntüler ve dayanır sağlayarak bir Power BI tarafından barındırılan bir veri içeri aktarma modelidir veri kümesi)

### <a name="model-storage-modes"></a>Model depolama modları

Geri çağırma Power BI Desktop üç moddan birini bir model geliştirmenize olanak sağlar. İçin gerekçe her bir veri modeli depolama modu ve Power BI hizmeti kaynakları üzerinde olası etkilerini anlamak önemlidir. Bu bölüm, tüm üç moddan tanıtır. Bunlar bu teknik incelemede modelleri en iyi duruma getirme konusunda ileride daha ayrıntılı olarak açıklanmıştır.

#### <a name="import-mode"></a>İçeri aktarma modu

İçeri aktarma modu, bellek içi, tasarım esnekliği modelleyen için kullanılabilir sorgulama ilişkili son derece hızlı performans nedeniyle modeller geliştirin ve belirli Power BI hizmeti için özellikleri (soru- cevap, hızlı Öngörüler'i desteklemek için kullanılan en yaygın moddur VS.). Yeni bir Power BI Desktop çözüm oluşturulurken için varsayılan mod budur.

İçeri aktarılan veriler için her zaman depolandığını anlamak önemlidir disk ve tam olarak sorgulanan veya yenilenmesi belleğe yüklenmiş olması gerekir. Bir kez bellekte alma modelleri ışık hızında sorgu sonuçları elde edin. Kısmen belleğe yüklenen bir içeri aktarma modeli kavramı anlamak önemlidir.

Yenilendiğinde, veriler sıkıştırılmış ve en iyi duruma getirilmiş ve ardından diski VertiPaq depolama altyapısı tarafından depolanır. Diskten belleğe yüklendiğinde, 10 x sıkıştırma görmek mümkündür ve bu nedenle kaynak veri 10 GB için 1 GB boyutunda sıkıştırabilirsiniz beklediğiniz makul. Disk depolama boyutu, bu üstte bir % 20 indirim elde edebilirsiniz. \[[6](#endnote-06)\]

Tasarım esneklik üç yolla sağlanabilir. Veri modelleyen yapabilirsiniz:

- -Veri kaynağı türü ve biçim bağımsız olarak birden çok veri kaynaklarından alınan verileri önbelleğe alarak verileri tümleştirin
- Veri hazırlama sorguları oluştururken Power Query formülü (resmi olmayan adı M adlandırılır) dil işlevleri kümesinin tamamını yararlanın
- Veri çözümleme ifadeleri (DAX) işlevleri kümesinin tamamını iş mantığı, hesaplanmış sütunlar, hesaplanmış tablolar ve ölçümleri elde modeliyle geliştirme görselleştirmelerinden yararlanın

Aşağıdaki görüntüde gösterildiği gibi bir içeri aktarma modeli desteklenen veri kaynağı türlerinin herhangi bir sayıda verilerini tümleştirebilirsiniz.

![Bir içeri aktarma modeli desteklenen veri kaynağı türlerinin herhangi bir sayıda verilerini tümleştirebilirsiniz](media/whitepaper-premium-deployment/import-model.png)

Ancak, içeri aktarma modelleri ile ilişkili ilgi çekici avantajları olsa da, vardır dezavantajları çok:

- Power BI sayısı ve modelleri boyutu büyüdükçe, baskısı kullanılabilir kaynaklara yerleştirebilirsiniz modeli sorgulayabilirsiniz önce modelin tamamı belleğe yüklenmesi gerekir
- Model verileri yalnızca en son yenileme geçerli olarak ve bu nedenle alma modelleri, tercihen bir zamanlanmış olarak yenilenmesi gerekir
- Tam yenileme tüm tablodan tüm verileri kaldırmak ve veri kaynağından yeniden. Bu, çok zaman ve Power BI hizmeti ve veri kaynakları için kaynak açısından pahalı olabilir. Power BI, kesiliyor ve yeniden yükleme tüm tabloları kaçınabilirsiniz artımlı yenileme desteği vardır ve bu bölümünde ele alınmıştır [Optimizing Power BI-Hosted modelleri](#optimizing-power-bi-hosted-models) konu.

Power BI hizmeti kaynak açısından bakıldığında, içeri aktarma modelleri gerektirir:

- Sorgulanan veya yenilenmesi, model yüklemek için yeterli bellek
- İşleme ve verileri yenilemek için ek bellek kaynaklarının

#### <a name="directquery-mode"></a>DirectQuery modu

Model DirectQuery (DQ) modunda geliştirilen verileri içeri aktarmayın. Bunun yerine, bunlar yalnızca meta verilerden oluşur olduğunda sorgulanan temel alınan veri kaynağına sorunları yerel sorgular.

![Bir DirectQuery modeli, temel alınan veri kaynağına yerel sorgular sorunları](media/whitepaper-premium-deployment/direct-query-model.png)

DQ modeli geliştirirken dikkate alınması gereken iki ana nedeni vardır. -Bile veri azaltma yöntemleri uygulandığında - veri hacimlerini modeline veri yüklemek veya bulundurmanızı yenilemek için çok büyük olduğundan ilk neden olur. Raporlar ve panolar, zamanlanmış yenileme sınırları (48 kez bir gün için ayrılmış bir Kapasite) içinde elde edilebilecek olanların ötesinde "neredeyse gerçek zamanlı" verileri sunmak ihtiyacınız olduğunda ikinci nedenidir.

DQ modelleri ile ilişkili çeşitli avantajları vardır:

- İçeri aktarma model boyutu sınırları geçerli değildir
- Model yenileme gerektirmez
- Rapor kullanıcıları, en yeni verileri görebilir, rapor filtrelerini ve dilimleyicileri ile etkileşimde bulunurken ve geçerli veri almak için raporun tamamı yenileyebilirsiniz
- DQ modellerine göre Pano kutucukları olarak 15 dakikada otomatik olarak güncelleştirebilirsiniz

Ancak, çok sayıda dezavantajları ve DQ modelleriyle ilgili sınırlamalar vardır:

- Model üzerinde desteklenen tek bir veri kaynağını temel alması gerekir ve bu nedenle herhangi bir veri tümleştirme veri kaynağında zaten elde edilen gerekir. Desteklenen veri kaynakları olan birçok popüler veri deposu desteği ile ilişkisel ve analiz sistemleri \[ [7](#endnote-07)\].
- Performans (sorgular çok CPU kullanımı yoğun olabilir) Power BI hizmetinde ve (analitik sorgular için optimize edilmemiş) veri kaynağı büyük olasılıkla olumsuz etkileyen yavaş olabilir.
- Power Query sorguları, fazla karmaşık olamaz ve M ifadeler ve veri kaynağı tarafından anlaşılan yerel sorgular için yorumlanabileceğinden işlevler sınırlıdır
- DAX işlevleri, veri kaynağı tarafından anlaşılan yerel sorgular için yorumlanabileceğinden sınırlıdır ve hesaplanmış tablolar veya yerleşik Akıllı zaman gösterimi özellikleri için desteği yoktur
- Varsayılan olarak, bir milyondan fazla satır alınmasını gerektiren modeli sorguları başarısız olur
- Veri kaynağının geçici olduğunda özellikle raporlar ve Panolar ile birden çok görsel tutarsız sonuçlar görüntüleyebilirsiniz
- Soru- cevap ve hızlı Öngörüler desteklenmez

Power BI hizmeti kaynak açısından bakıldığında, DQ modelleri gerektirir:

- Modeli (yalnızca meta veriler) yüklemek için en az bellek zaman sorgulandı
- Bazen önemli bir işlemci kaynaklarını oluşturmak ve veri kaynağına gönderilen sorguları işlemek için

Daha fazla bilgi için bkz [Power BI Desktop'ta doğrudan sorgu kullanın](desktop-use-directquery.md) belge.

#### <a name="composite-mode"></a>Bileşik modu

Bileşik modunda geliştirilen modelleri için ayrı modeli tabloları depolama modu yapılandırma sağlar. Bu nedenle, içeri aktarma ve DQ tablolar bir karışımını destekler. Hesaplanan tablolar (DAX ile tanımlanır) ve birden çok DQ veri kaynakları da destekler.

Tablo depolama modu Import, DirectQuery veya çift yapılandırılabilir. Hem içeri aktar hem de DirectQuery çift depolama modu olarak yapılandırılmış bir tablo yer almaktadır ve bu sorgu tarafından sorgusu olarak kullanılacak en verimli modu belirlemek Power BI hizmeti sağlar.

![Bileşik bir model bir tablo düzeyinde yapılandırılan içeri aktarma ve DQ depolama modda birleşimidir.](media/whitepaper-premium-deployment/composite-model.png)

Bileşik model, içeri aktarma ve DirectQuery modları en iyi şekilde sunmak çaba harcar. Uygun şekilde yapılandırıldığında yakın gerçek zamanlı verileri veri kaynaklarından alma olanağı ile yüksek sorgu performansı bellekteki modelleri birleştirebilirsiniz.

Bileşik model geliştiren veri modelleyen alma ya da çift depolama modu ve türü olgu tablolarındaki DirectQuery modunda boyut türüyle tablolarını yapılandırmak olasıdır. Örneğin, çift modlu ve satış türü Olgu Tablosu DirectQuery modunda bir modeli ürün türü boyut tablosu ile göz önünde bulundurun. Product tablosunda hızlı ve verimli bir rapor Dilimleyici işlemek için bellekte sorgulanmasını. Sales tablosunda ilişkili ürün tabloya katılmış DirectQuery modunda ardından sorgulanan. İkinci sorgu, ürün ve satış tablolarını ve dilimleyici değerlerine göre filtreleme katılmak için tek bir etkin yerel sorgu oluşturulmasını sağlayabilir.

Genel olarak, avantajlar ve dezavantajlar, her modeli moduyla ilişkili tablo depolama modu bileşik modellerde uygulamak için kabul edilebilir.

Daha fazla bilgi için bkz [Power BI Desktop'ta bileşik modelleri kullanma](desktop-composite-models.md) belge.

### <a name="licensing"></a>Lisanslama

Power BI üç lisanstan sahiptir:

- Ücretsiz Power BI
- Power BI Pro
- Power BI Premium

**Ücretsiz Power BI** lisansı, Power BI hizmetinde oturum açın ve kendi kişisel çalışma alanı içinde modeller ve raporlar yayımlayarak çalışmak bireysel verir. Bu lisans'ı kullanarak Power BI içerik paylaşmak mümkün olmadığı anlamına anlamak önemlidir. Adından da anlaşılacağı gibi bu lisans ücretsizdir.

**Power BI Pro** lisans bireysel oluşturmak ve uygulama çalışma alanları işbirliği ve paylaşmak ve Power BI'ı dağıtmak içerik sağlar. Bunlar, ayrıca otomatik olarak verileri şirket içi veri kaynaklarından dahil olmak üzere güncel tutmak, veri kümeleri için yenileme yapılandırabilirsiniz. Ayrıca, Denetim ve verileri nasıl erişilme ve kullanılma yönetir. Bu lisans, kullanıcı Power BI Premium adanmış kapasiteyle ilişkili değilse diğer paylaşılan içerik almak için gereklidir.

**Power BI Premium** lisansı olan bir kiracı düzeyinde lisans ve içinde ele alınmıştır [Power BI Premium ile tanışın](#introducing-power-bi-premium) bölümü.

Power BI Lisansı hakkında daha fazla bilgi için bkz [Power BI fiyatlandırması](https://powerbi.microsoft.com/pricing/) sayfası.

## <a name="introducing-power-bi-premium"></a>Power BI Premium ile tanışın

Power BI Premium, Ölçek, güvenilir performans ve tahmin edilebilir maliyetler ile birleştirilmiş bir Self Servis ve kurumsal BI platformu sunar. Öncelikle bunun kuruluşunuz için Power BI hizmetini çalıştırmak için adanmış kaynaklar sunarak ulaşır.

Ayrıca, Power BI Premium, pek çok kuruluş özelliği sunar:

- Power BI içeriğini dış kullanıcılar dahil olmak üzere, sınırsız sayıda ücretsiz Power BI kullanıcıları için paylaşımı etkinleştirme, uygun maliyetli içerik dağıtımı
- Büyük veri kümesi boyutları için destek \[ [8](#endnote-08)\]
- Veri akışlarını veri kümeleri (günde en fazla 48 kez) ve daha yüksek yenileme hızı
- Artımlı yenileme veri akışlarını ve veri kümeleri
- Varlıklar ve dönüşümlerin Paralel yürütme veri akışı bağlı
- Sayfalandırılmış raporlar
- Şirket içinde raporlama için Power BI rapor sunucusu
- Uygulama kullanıcılarının (PaaS) adına uygulamalara içerik ekleme olanağı

Bu özelliklerin çoğu, etkili ve ölçeklenebilir Kurumsal çözümler sunma olanağı faydalanacaklarını ve ele alınmaktadır [en iyi duruma getirme Premium kapasiteleri](#optimizing-premium-capacities) bölümü.

### <a name="subscriptions-and-licensing"></a>Abonelikler ve lisanslar

Power BI Premium, Kiracı düzeyinde Office 365 aboneliği iki SKU (stok tutma birimi) ailelerinde kullanılabilir olan:

- **EM** ekleme için SKU'ları (EM1-EM3) bir yıllık taahhüt gerektiren aylık faturalandırılır
- **P** aylık veya yıllık taahhüt gerektiren SKU'lar (P1-P3) ekleme ve kurumsal özellikler için aylık olarak faturalandırılır ve Power BI rapor sunucusu şirket içi yüklemek için bir lisans içerir

Alternatif bir yaklaşım, tek bir SKU ailesi olan bir Azure Power BI Embedded aboneliği satın almaktır: **A** ekleme ve yalnızca test amacıyla kapasite SKU (A1-A6).

Kapasite oluşturmak için sanal çekirdekler tüm SKU'ların teslim \[ [9](#endnote-09)\], ancak EM SKU'ları için daha küçük bir ölçek ekleme kısıtlanır. Odak noktası bu teknik incelemede, P SKU'larında olsa da, ele alınmıştır çoğunu da A SKU için de geçerlidir.

Premium aboneliği aksine SKU'ları, Azure SKU'ları hiçbir zaman taahhüdü gerektirir ve saatlik olarak faturalandırılır. Bunlar yukarı ölçek etkinleştirme tam esneklik sunar, ölçeği, duraklatma, sürdürme ve silin.

Azure Power BI Embedded büyük ölçüde kapsamı Bu teknik incelemede dışındadır, ancak test ve iş yüklerini ölçmek için bir pratik ve ekonomik seçeneği olarak sınama yaklaşımları konuda ele alınan.

Azure SKU'ları hakkında daha fazla bilgi için bkz [Azure Power BI Embedded belgeleri](/azure/power-bi-embedded/).

Power BI Premium abonelikleri Microsoft 365 Yönetim merkezinde yöneticiler tarafından satın alınır. Özellikle, yalnızca Office 365 genel yönetici veya faturalama yöneticileri SKU satın alabilirsiniz.

Satın alındıktan sonra Kiracı alır - kapasiteler atamak için sanal çekirdekler karşılık gelen sayıda bu olarak bilinir **sanal çekirdek havuzu**. Örneğin, bir P3 SKU satın almak kiracıya 32 sanal çekirdek sağlar.

Daha fazla bilgi için bkz [Power BI Premium'u satın alma](service-admin-premium-purchase.md) belge.

### <a name="premium-capacities"></a>Premium kapasiteler

İş yükleri diğer müşteriler ile paylaşılan hesaplama kaynaklarında çalıştırıldığı paylaşılan kapasite aksine bir **ayrılmış kapasitesini** bir kuruluş tarafından özel kullanım içindir. Barındırılan içerik için güvenilir ve tutarlı bir performans sağlayan ayrılmış hesaplama kaynaklarını ile yalıtılır.

Bu teknik incelemede'nin odak noktası **Premium kapasite** , yani herhangi bir EM veya P SKU ile ilişkili.

#### <a name="capacity-nodes"></a>Kapasite düğümleri

Açıklandığı gibi abonelikler ve lisans konu, vardır iki Power BI Premium SKU ailesi: EM ve P. Tüm Power BI Premium SKU'ları ile her bir işlemci, bellek ve depolama oluşan kaynakları miktarını gösteren kapasite düğümleri mevcuttur. Kaynakların yanı sıra her SKU (DQ) DirectQuery ve canlı bağlantı (LC) bağlantıları saniye başına sayısı işletimsel bir üst sınırı yoktur ve paralel model sayısı yenilenir.

İşleme, ön uç ve arka uç arasında eşit olarak bölünür çekirdek, ayarlana sayıda elde edilir.

**Arka uç çekirdek** için temel Power BI işlevleri sorgu işleme, önbellek yönetimi, R services, model yenileme, doğal dil işleme (soru- cevap) ve raporlar ile resimlerin sunucu tarafında işlenmesi çalıştırma dahil olmak üzere, sorumludur. Arka uç sanal çekirdek, sabit bir birincil olan etkin bir veri kümesi da adlandırılır konak Modellerinizi kullanılacak bellek miktarını atanır.

**Ön uç sanal çekirdek** web hizmetinden, Pano ve rapor belge yönetiminden, erişim hakları yönetiminden, zamanlama, API'ler, yükler ve indirir ve genellikle kullanıcı için ilgili her şeyi deneyimleri sorumludur.

Depolama kapasitesi düğüm başına 100 TB için ayarlanır.

Kaynaklar ve her bir Premium SKU sınırları (ve bir SKU'eşdeğer boyutta) aşağıdaki tabloda açıklanmıştır.

| Kapasite düğümleri | Toplam sanal çekirdek sayısı | Arka uç sanal çekirdek sayısı | RAM (GB) | Ön uç sanal çekirdek sayısı | DQ/LC (/ sn) | Model yenileme paralellik |
| --- | --- | --- | --- | --- | --- | --- |
| EM1/A1 | 1 | 0,5 | 2.5 | 0,5 | 3.75 | 1 |
| EM2/A2 | 2 | 1 | 5 | 1 | 7.5 | 2 |
| EM3/A3 | 4 | 2 | 10 | 2 | 15 | 3 |
| P1/A4 | 8 | 4 | 25 | 4 | 30 | 6 |
| P2/A5 | 16 | 8 | 50 | 8 | 60 | 12 |
| P3/A6 | 32 | 16 | 100 | 16 | 120 | 24 |
| | | | | | | |

#### <a name="capacity-workloads"></a>Kapasite iş yükleri

Kapasite iş yükleri, kullanıcıların kullanımına sunulmasını hizmetleridir. Varsayılan olarak, Premium ve Azure kapasitelerinin devre dışı bırakılamaz Power BI sorguları çalıştırmayla ilişkili yalnızca bir veri kümesi iş yükünü destekler.

Ek iş yüklerinin sayfalandırılmış raporlar, veri akışlarını ve yapay ZEKA için etkinleştirilebilir. Her ek iş yükü, iş yükü tarafından kullanılabilecek maksimum bellek (olarak, toplam kullanılabilir belleğin yüzdesi cinsinden) yapılandırma gerektirir.

#### <a name="how-capacities-function"></a>Nasıl kapasiteler işlevi

Her zaman kapasite sınırları geçmeyen uygulanan sırada kapasite kaynaklarının kullanımını en iyi hale getirmek Power BI hizmetinde çalışır.

Kapasite operations olarak sınıflandırılan etkileşimli veya arka plan. Etkileşimli işlem istekleri oluşturma ve Kullanıcı etkileşimlerine (filtreleme, soru- cevap sorgulama, vb.) yanıt içerir. Genel olarak, içeri aktarma modeli sorgulama LC/DQ modelleri sorgulama CPU yoğunluklu olsa kaynak kullanımı yoğun bellek içiyle sınırlıdır. Arka plan işlemleri, veri akışı içerir ve model yenileme işlemleri ve Pano sorgu önbelleğe alın.

Etkileşimli işlem arka plan işlemleri olabilecek en iyi kullanıcı deneyimi sağlamak için her zaman önceliklendirilir anlamak önemlidir. Yetersiz kaynak varsa, arka plan işlemleri kaynakları boşaltmaya, işleme için kuyruğa eklenir. Veri kümesini yenilemeleri ve yapay ZEKA işlevleri gibi arka plan işlemleri, Power BI hizmeti tarafından durdurulan ortasında bir işlem olabilir ve bir kuyruğa eklenir.

Böylece bunlar sorgulanan güncelleştirilebilecek veya yenilenebilecek alma modelleri belleğe tam yüklü olması gerekir. Power BI hizmetini kullanarak kullanım algoritmaları en fazla kullanılabilir bellek kullanımını emin olmak için karmaşık ve kapasite fazla ulaşabileceği bellek yönetir: Mümkün olmakla birlikte çok içeri aktarma depolamak için bir Kapasite (en fazla 100 TB Premium kapasite başına) modelleri, kendi birleştirilmiş disk depolama alanı desteklenen belleği aşıyor (ve ek bellek sorgulama ve yenileme için gerekli olduğunda), ardından bunların tüm sırasında belleğe yüklenemiyor aynı anda.

İçeri aktarma modelleri bu nedenle - yüklenen ve - bellek kullanım göre kaldırılır. Bir içeri aktarma modeli sorgulanan (etkileşimli işlem) olduğunda ve henüz bellekte veya yenilenmesi gerektiğinde yüklenir (arka plan işlemi).

Bir modelin bellekten temizleme olarak da bilinen **çıkarma** , ve Power BI hızlı bir şekilde modelleri boyutuna bağlı olarak gerçekleştirebileceğiniz bir işlemdir. Kapasite herhangi bir bellek baskısı yaşamadığından, modelleri sadece belleğe yüklenir ve orada kalır. \[[10](#endnote-10) \] yetersiz bellek modeli yüklemek kullanılabilir duruma geldiğinde, ancak Power BI hizmetinde ilk belleği boşaltmak gerekir. Son üç dakika içinde kullanılmamış Modellerinizi arayan tarafından etkin olmayan duruma gelmiş modelleri algılayarak belleği bıraktığı \[ [11](#endnote-11)\]ve ardından bunları çıkarma. Hiçbir etkin olmayan modelleri çıkarmak için varsa, arka plan işlemleri için yüklenen modelleri çıkarmak Power BI hizmetinde arar. Bu yapay ZEKA iş yükü gibi arka plan iş yüklerinin çıkarma içerebilir. Başarısız oturum açma girişimlerinin 30 saniye sonra son çare \[ [11](#endnote-11)\], etkileşimli işlem başarısız sağlamaktır. Bu durumda, rapor kullanıcısı bir öneriyle kısa süre sonra yeniden denemek için hata düzgün bir şekilde bildirilir.

Veri kümesi çıkarma normal ve beklenen bir davranış olduğunu vurgulamak önemlidir. Yükleme ve modelleri, birleşik boyutları kullanılabilir bellek aşabilir kaldırma bellek kullanımını en üst düzeye çıkarmaya çalışır. Tasarıma göre ve rapor kullanıcılara tamamen şeffaf budur. Yüksek çıkarma oranları, kapasite yeterince kaynak var mutlaka gelmez. Sorgu veya yenileme yanıt hızı yüksek çıkarma oranları nedeniyle yaşıyorsa, ancak bir sorun haline olabilir.

Yenilemeler alma modelleri, her zaman modelleri belleğe yüklenmesi ve ek bellek işlenmesi için gerekli olan bellek kullanımı yoğun olur. Tam yenilemenin yaklaşık iki model tarafından gerekli bellek miktarını kullanabilirsiniz. Bu model bile işlenmekte olan zaman sorgulanabilir sağlar (sorgular gönderilir mevcut modeline yenilemesi tamamlandı ve yeni model verileri kullanılabilir kadar). Unutmayın, artımlı yenileme daha az bellek gerektirir ve daha hızlı işlemi tamamlanamadı ve böylece kapasite kaynakları Basıncı önemli ölçüde azaltabilir. Yenilemeler da CPU kullanımı yoğun olabilir modelleri için özellikle karmaşık Power Query dönüşümleri veya hesaplanan tabloları/sütunları ile karmaşık olan veya büyük tabloları temel alır.

Yenilemeler - sorgu gibi-model belleğe yüklenmesi gerekir. Yetersiz bellek varsa, Power BI hizmetinde etkin olmayan modelleri çıkarmak dener ve bu (tüm modelleri etkin olan) mümkün değilse, yenileme işi kuyruğa alındı. Yenileme genellikle çok yoğun CPU, daha fazla şekilde sorguları daha. Bu nedenle, x sayısı arka uç yuvarlanan çekirdek, 1.5 koymak eşzamanlı yenileme sayısı kapasitesi sınırı yoktur. Çok fazla eş zamanlı yenilemeleri varsa, zamanlanmış yenileme kuyruğa alınır. Bu durum gerçekleştiğinde, yenileme tamamlanması uzun sürer. İsteğe bağlı yenilemeleri (bir kullanıcı isteği veya API çağrısı tarafından tetiklenen) üç kez yeniden deneyecek Not \[ [11](#endnote-11)\]ve ardından değil yine de yeterli kaynaklar varsa başarısız olur.

## <a name="managing-power-bi-premium"></a>Power BI Premium'u yönetme

Power BI Premium'u yönetme abonelikleri satın alma ve oluşturmaya, yönetmeye ve Premium kapasiteleri izleme içerir.

### <a name="creating-and-managing-capacities"></a>Oluşturma ve kapasite yönetme

**Kapasite ayarlarını** sayfasının **Power BI yönetici** Portal, satın alınan sanal çekirdek sayısı ve kullanılabilir görüntüler (yani henüz bir kapasiteye atanması) ve Premium kapasiteleri listeler. Sayfa Office 365 genel Yöneticiler veya Power BI hizmet yöneticileri kullanılabilir çekirdek Premium kapasiteleri oluşturmak veya var olan Premium kapasiteleri değiştirmek için sağlar.

Premium kapasite oluştururken, yönetici tanımlamak için gereklidir:

- Kapasite adı (kiracıda benzersiz)
- Kapasite admin(s)
- Kapasite boyutu
- Veri yerleşikliği bölgesi \[ [12](#endnote-12)\]

En az bir kapasite Yöneticisi atanması gerekir. Kapasite Yöneticisi olarak atanabilmek kullanıcılar şunları yapabilir:

- Kapasiteye çalışma alanları atama
- Ek kapasite yöneticileri veya (kapasiteye çalışma alanlarını atamak bunları etkinleştirmek için) atama izinleri olan kullanıcılar eklemek için kullanıcı izinleri yönetme
- Sayfalandırılmış raporlar ve veri akışlarını iş yükleri için en fazla bellek kullanımını yapılandırmak için iş yüklerini yönetme
- Sistem aşırı yük durumunda tüm işlemleri sıfırlamak için kapasite yeniden \[ [13](#endnote-13)\]

Kapasite yöneticileri (açıkça çalışma alanı izinleri atamazsanız) çalışma alanı içeriğe erişemez ve bunlar tüm Power BI yönetici alanlarına (açıkça atanan sürece) kullanım ölçümleri, Denetim günlükleri veya Kiracı ayarları gibi erişiminiz yok. Önemlisi, kapasite yöneticileri yeni kapasiteler oluşturun veya mevcut kapasitelerin ölçeklendirmek için izniniz yok. Şirket Ayrıca, atanan bir temelinde kapasite-yalnızca yapabilirler sağlayarak, görüntüleme ve atanmış oldukları kapasiteleri yönetme.

Kapasite boyutu havuzunda kullanılabilir sanal çekirdek sayısına göre kısıtlı bir kullanılabilir SKU Seçenekleri listesinden seçilmelidir. Havuzundan diğerine kaynaklanan birden çok kapasiteler oluşturmak mümkündür veya daha fazla SKU satın. Örneğin, bir P3 SKU (32 çekirdek), üç kapasiteler oluşturmak için kullanılabilir: bir P2 (16 çekirdek) ve iki P1 (2 x 8 çekirdek). Gelişmiş performans ve ölçek elde edilebilir daha küçük boyutlu kapasiteler oluşturarak ve bu konuda açıklandığı [en iyi duruma getirme Premium kapasiteleri](#optimizing-premium-capacities) bölümü. Aşağıdaki görüntüde bir örnek kurulumu için beş Premium kapasiteleri oluşan kurgusal Contoso kuruluşundaki gösterilmektedir (P1 ve 2 x 3 x P3) içeren her uygulama çalışma alanları ve paylaşılan kapasiteye birkaç çalışma alanları.

![Kurgusal Contoso kuruluş için bir örnek Kurulumu](media/whitepaper-premium-deployment/contoso-organization-example.png)

Premium kapasite, Power BI kiracınızın hangi veri merkezleri (coğrafi bölgelerin tanımlanması) üzerinden Power BI içeriğini bulunduğu yönetim denetim sağlayan, giriş bölgesi dışında bir bölgeye atanabilir. \[[12](#endnote-12)\]

Power BI hizmeti yöneticileri ve Office 365 genel yöneticileri, Premium kapasiteleri değiştirebilirsiniz. Özellikle, yönetici şunları yapabilir:

- Kapasite boyutunu kaynakları ölçeğini artırabilir veya değiştirin. Ancak, bir P SKU, EM SKU için düşürme veya tam tersi yükseltmek mümkün değildir.
- Ekleme veya kaldırma kapasite yöneticileri
- Atama izinleri bulunan bir kullanıcı eklemek veya kaldırmak
- Ek iş yüklerinin Ekle Kaldır
- Bölgeleri değiştirme

Atama izinleri, belirli bir Premium kapasiteye çalışma alanı atamak için gereklidir. Kuruluşun tamamı, belirli kullanıcılar veya gruplar için izinleri verilebilir.

Varsayılan olarak, Power BI sorgularını çalıştırmayla ilgili iş yükleri Premium kapasiteleri destekler. Ayrıca, üç ek iş yüklerinin destekler: **Sayfalandırılmış raporlar**, **veri akışlarını**, ve **AI**. Her iş yükü, iş yükü tarafından kullanılabilecek maksimum bellek (olarak, toplam kullanılabilir belleğin yüzdesi cinsinden) yapılandırma gerektirir. En fazla bellek ayırmaları artırma'nün barındırılabilir etkin modelleri sayısı ve aktarım hızını yenilemeleri etkileyebilir anlamak önemlidir.

Bellek, dinamik olarak veri akışlarına ayrılsa da istatistiksel olarak sayfalandırılmış raporlara ayrılır. Statik olarak en fazla belleği tahsis etme nedenini sayfalandırılmış raporlar içerdiği kapasite alanı güvenli içinde çalışmasıdır. Modelleri yükleme için kullanılabilir belleği azaltır gibi raporları bellek ayarı sayfalandırılmış dikkatli olunması.

|                     | EM3                      | P1                       | P2                      | P3                       |
|---------------------|--------------------------|--------------------------|-------------------------|--------------------------|
| Sayfalandırılmış raporlar | YOK | %20 varsayılan; %10 en küçük | %20 varsayılan; %5 en küçük | %20 varsayılan; %2,5 en küçük |
| Veri akışları | %20 varsayılan; %8 en küçük  | %20 varsayılan; %4 en küçük  | %20 varsayılan; %2 en küçük | %20 varsayılan; %1 en küçük  |
| YAPAY ZEKA | YOK | % 20 varsayılan; en az %20  | %20 varsayılan; %10 en küçük | %20 varsayılan; %5 en küçük  |
| | | | | |

Premium kapasite siliniyor mümkündür ve kendi çalışma alanları ve içeriğinin silinmesine neden olmaz. Bunun yerine, tüm atanmış çalışma alanlarına paylaşılan kapasiteye taşınır. Premium kapasite farklı bir bölgede oluşturduğunuzda, çalışma alanı ana bölge paylaşılan kapasiteye taşınır.

### <a name="assigning-workspaces-to-capacities"></a>Kapasitelere artırmak için çalışma alanları atama

Çalışma alanlarını bir Premium kapasitede atanabilen **Power BI yönetici** **portalı** veya - bir uygulama çalışma alanının - **çalışma** bölmesi.

Kapasite yöneticileri yanı sıra Office 365 genel Yöneticiler veya Power BI hizmet yöneticileri, çalışma alanları atayabilir toplu halde **Power BI yönetici** **portalı**. Atanan toplu uygulayabilirsiniz:

- **Kullanıcılara göre çalışma alanları** : Bu kullanıcıların kişisel çalışma alanlarını dahil olmak üzere, sahip olduğu tüm çalışma alanlarını Premium kapasiteye atanır. Zaten farklı bir Premium kapasiteye atanmış olduğunda bu çalışma alanları yeniden atanmasını içerir. Ayrıca, kullanıcıların çalışma alanı atama izinleri atanır.

- **Belirli çalışma alanları**
- **Tüm kuruluşun çalışma alanlarını** : Kişisel çalışma alanlarını dahil olmak üzere tüm çalışma alanlarını Premium kapasiteye atanır. Ayrıca, tüm mevcut ve gelecekteki kullanıcılara çalışma alanı atama izinleri atanır. \[[14](#endnote-14)\]

Kullanarak, bir çalışma alanı Premium kapasiteye eklenebilir **çalışma** kullanıcı bölmesinde hem bir çalışma alanı yöneticisi olan ve atama izinlerine sahip.

![Bir çalışma alanı Premium kapasiteye atamak için çalışma alanı bölmesinde kullanma](media/whitepaper-premium-deployment/assign-workspace-capacity.png)

Çalışma alanı yöneticileri, bir çalışma alanına bir kapasiteden (paylaşılan kapasiteye) atama izni gerek kalmadan kaldırabilirsiniz. Çalışma alanını yeniden yerleştirir paylaşılan kapasiteye çalışma alanlarını adanmış kapasitelerini etkili bir şekilde kaldırılıyor. Desteklenen izinler'i aştığında kullanıcılar veya zamanlanmış yenileme askıya alınması, bir çalışma alanını Premium kapasiteden kaldırmak, örneğin, paylaşılan içeriği Power BI ücretsiz kullanılamaz hale výsledek olumsuz etkileri olabilecek bir not lisanslı Paylaşılan kapasite tarafından.

Power BI hizmetinde çalışma alanı Premium kapasiteye atanmış kolayca çalışma alanı adı daireler donatır baklava simgesi tarafından tanımlanır.

![Bir Premium kapasiteye atanmış bir çalışma alanı tanımlama](media/whitepaper-premium-deployment/premium-diamond-icon.png)

### <a name="monitoring-capacities"></a>İzleme kapasiteleri

Premium kapasiteler izleme kapasiteleri nasıl performans gösterdiğini anlamak yöneticilerine sağlar. Kapasiteleri kullanarak izlenebilir [Power BI Premium kapasite ölçümleri uygulama](service-admin-premium-monitor-capacity.md) veya [Power BI Yönetici portalına](service-admin-premium-monitor-portal.md).

#### <a name="interpreting-metrics"></a>Ölçümleri yorumlama

Ölçümler, kaynak kullanımı ve iş yükü etkinliği temel bir anlayış oluşturmak için izlenmelidir. Kapasite yavaşlar izlemek için hangi ölçümleri anlamak önemlidir ve sonuçları yapabilirsiniz.

İdeal olarak, sorgu rapor kullanıcıları duyarlı deneyimler sunun ve daha yüksek sorgu aktarım hızını sağlamak için bir saniye içinde tamamlanmalıdır. -Yenileme dahil olmak üzere - arka plan işlemlerini tamamlamak için daha uzun süreleri alırken genellikle daha düşük bir sorun olur.

Genel olarak, yavaş raporları bir Aşırı ısıtma kapasitesinin bir göstergesi olabilir. Raporları yüklenmesi başarısız olduğunda bir aşırı ısıtılan kapasitesinin bir göstergesi budur. Her iki durumda, kök nedeni de dahil olmak üzere birçok faktöre bağlı olabilir:

- **Sorguları başarısız** kesinlikle bellek baskısı belirtmek ve belleğe bir model yüklenemedi. Power BI hizmetinde, 30 saniye başarısız olmadan önce bir model yük dener.

- **Aşırı sorgu bekleme sürelerini** birkaç nedeni olabilir:
  - Power BI hizmete ilk gereksinimini modellere çıkarın ve How-to-edilecek sorgulanan modeli (tek başına daha yüksek veri kümesi çıkarma oranları göstergesidir kapasite stres uzun belirtmek bellek çok yavaş sorgu bekleme süresini tarafından eşlik sürece olmadığından geri çağırma) yükleyin
  - Model yükleme süreleri (büyük bir modelin belleğe yüklemek için özellikle bekleme)
  - Uzun süren sorgular
  - Çok fazla LC\DQ bağlantılar (kapasite sınırları aşan)
  - CPU doygunluğu
  - (Her görsel için bir sorgu olduğunu geri çağırma) sayfasındaki görsellerin aşırı sayıda ile karmaşık rapor tasarımları
- **Uzun süreler'ı sorgu** modeli tasarımı, özellikle birden fazla veri kümesi bir kapasitede etkin olan ve yalnızca bir veri kümesi uzun sorgu süreleri üretme için optimize edilmediğinden emin belirtebilirsiniz. Bu, kapasite yeterince kaynak var olduğunu ve soru veri kümesi iyinin ya da yalnızca yavaş olduğunu önerir. Diğer işlemler tarafından gerekli kaynaklara erişim engelleyebileceği uzun süre çalışan sorguların sorunlara neden olabilir.
- **Uzun yenileme zamanları bekleyin veya AI çağrı süreleri bekleyin** yetersiz bellek nedeniyle bellek kullanan çok sayıda etkin model belirtin veya sorunlu bir yenileme diğer engelliyor (paralel yenileme sınırları aşan) yeniler.

Daha ayrıntılı bir açıklaması ölçümleri kullanma ve sonraki bölümünde ele alınmıştır [en iyi duruma getirme Premium kapasiteleri](#optimizing-premium-capacities) bölümü.

## <a name="optimizing-premium-capacities"></a>Premium kapasiteler en iyi duruma getirme

Premium kapasite performans sorunları ortaya çıktığında, ortak bir ilk yaklaşım iyileştirmek veya dağıtılmış çözümleri, kabul edilebilir yanıt süreleri geri yüklemek için ayarlanacak sağlamaktır. Geçersiz kılma stratejinin gerekçe sürece ek Premium kapasite satın alma kaçınmaktır.

Ek Premium kapasite gerekli olduğunda, bu bölümde açıklanan daha sonra iki seçenek vardır:

- Premium kapasitesinin ölçeğini artırma
- Yeni bir Premium kapasiteye ekleyin

Son olarak, test yaklaşımları ve Premium kapasite boyutlandırmasını Bu bölümde sona erecektir.

### <a name="general-best-practices"></a>Genel en iyi yöntemler

En iyi sonucu elde etmek da kullanımı ve performans var. karttaki genel öneriler olarak uygulanabilecek bazı en iyi uygulamaları konusunda. Bu modüller şunlardır:

- Uygulama çalışma alanları yerine kişisel çalışma alanlarını kullanma
- İş açısından kritik ve Self Servis BI (SSBI) farklı kapasiteler ayırma

  ![İş açısından kritik ve Self Servis BI farklı kapasiteler ayırma](media/whitepaper-premium-deployment/separate-capacities.png)

- Yalnızca Power BI Pro kullanıcıları ile içerik paylaşımı, ayrılmış bir kapasite içeriği depolamak gerekmez olabilir
- Adanmış kapasite belirli yenileme süresi elde etmek isteyen olduğunda veya belirli özellikleri gerekli, örneğin büyük veri kümelerinin olduğunu veya Raporlama sayfalandırılmış kullanın

### <a name="addressing-common-questions"></a>Sık sorulan sorular adresleme

Power BI Premium dağıtımları en iyi duruma getirme, iş yükü gereksinimlerini, kullanılabilir kaynaklar ve etkili kullanımları içeren karmaşık bir konu olduğu.

Bu konuda olası sorunlar ve açıklamalar ve tanımlama ve çözme hakkında bilgi açıklayan, yedi genel destek soruları ele alır.

#### <a name="why-is-the-capacity-slow-and-what-can-i-do"></a>Yavaş kapasite neden olduğu ve neler yapabilirim?

Yavaş bir Premium kapasiteye katkıda bulunabilir birçok neden vardır. Bu sorunun daha fazla bilgi ne tarafından yavaş yöneliktir anlamak için gerektirir. Raporları yavaş misiniz? Veya yüklemek başarısız oluyor? Rapor görselleri yüklemek veya kullanıcıların bir raporla etkileşim kurduğunuzda güncelleştirmek yavaş misiniz? Yenilemeler beklenen ya da daha önce karşılaştığınız çok daha uzun sürüyor?

Neden olma elde edilen, ardından araştırmaya başlayabilirsiniz. Aşağıdaki altı soruların yanıtları yardımcı olacak daha fazla gidermek için belirli sorunları.

#### <a name="what-content-is-using-up-my-capacity"></a>Hangi içerik my kapasite kullanıyor mu?

Kullanabileceğiniz **Power BI Premium kapasite ölçümleri** uygulama kapasite ve performans ölçümleri workspace içerik için gözden geçirin. Bir Premium kapasiteye içinde depolanan tüm içerik için son yedi güne ait saat performans ölçümlerini ve kaynak kullanımını gözden geçirmek mümkündür. Bu genellikle geneli ilgilendiren Premium kapasite performansıyla ilgili sorun giderme yapılacak ilk adımdır.

İzlemek için ana ölçümler içerir:

- Ortalama CPU ve yüksek kullanım sayısı
- Ortalama bellek ve yüksek kullanım sayısı ve bellek kullanımı belirli veri kümeleri, veri akışlarını ve sayfalandırılmış raporlar
- Belleğe yüklenen active veri kümeleri
- Ortalama ve en yüksek sorgu süreleri
- Ortalama Sorgu bekleme süresini
- Ortalama veri kümesi ve veri akışı defa yenileyin
- Ortalama yapay ZEKA kez çağrılması ve kez bekleyin

Ayrıca, Power BI Premium kapasite ölçümleri uygulamada etkin bellek toplam son üç dakika içinde olduğundan çıkarılamadığı bir rapor için ayrılan bellek miktarını gösterir. Yenileme bekleme süresi yüksek bir ani değişiklik büyük ve/veya etkin bir veri kümesiyle ilişkili olabilir.

"İlk 5 tarafından ortalama süresi" grafiği zorlayıcı beş veri kümeleri, sayfalandırılmış raporlar, veri akışlarını ve yapay ZEKA çağrıları kapasite kaynak tüketmeye vurgular. Araştırma ve olası en iyi duruma getirme için en çok beş listelerinde içerik adaylardır.

#### <a name="why-are-reports-slow"></a>Neden raporlardır yavaş?

Aşağıdaki tablolar, olası sorunlar ve tanımlamak ve bunları işlemek için yol gösterir.

##### <a name="insufficient-capacity-resources"></a>Yeterli kapasite kaynakları

| Olası açıklamalar | Belirleme | Nasıl çözümleneceğini |
| --- | --- | --- |
| Toplam etkin yüksek bellek (model kullanılamaz çıkarılacak son üç dakika kullanımda olduğu için)<br><br> Birden çok yüksek sorgu bekleme süresini artış<br><br> Birden çok yüksek yenileme bekleme süresini artış | Bellek ölçümleri izleyebilir \[ [18](#endnote-18)\]ve çıkarma sayıları \[ [19](#endnote-19)\] | Model boyutunu küçültün veya DirectQuery moduna Dönüştür - bkz [en iyi duruma getirme modelleri](#optimizing-models) bu bölümdeki konu<br><br> Kapasitesinin ölçeğini artırma<br><br> İçeriği farklı bir kapasiteye atayın. |

##### <a name="inefficient-report-designs"></a>Verimsiz raporu tasarımı

| Olası açıklamalar | Belirleme | Nasıl çözümleneceğini |
| --- | --- | --- |
| Rapor sayfaları (etkileşimli filtreleme en az bir sorgu görsel başına tetikleyebilir) çok sayıda görsel içeren<br><br> Görselleri gerekenden daha fazla veri alma | Rapor Tasarım gözden geçirme<br><br> Raporlarla nasıl etkileşim kurduklarını anlamak için röportajı rapor kullanıcıları<br><br> İzleme veri kümesi sorgu ölçümleri \[ [20](#endnote-20)\] | Sayfa başına daha az görsellerle yöntemini yeniden tasarlamaya raporları |

##### <a name="dataset-slow-especially-when-reports-have-previously-performed-well"></a>Veri kümesi yavaş (özellikle zaman raporları daha önce de yapmadığınız)

| Olası açıklamalar | Belirleme | Nasıl çözümleneceğini |
| --- | --- | --- |
| Giderek daha büyük miktarda verileri içeri aktar<br><br> RLS rolleri dahil olmak üzere, karmaşık veya verimsiz hesaplama mantığı<br><br> Tam olarak en iyi duruma getirilmiş modeli<br><br> (DQ/LC) Ağ geçidi gecikme süresi<br><br> Yavaş DQ kaynak sorgu yanıt süreleri | Model Tasarım gözden geçirme<br><br> Ağ geçidi performans sayaçları | Bkz: [en iyi duruma getirme modelleri](#optimizing-models) bu bölümdeki konu |

##### <a name="high-concurrent-report-usage"></a>Yüksek eş zamanlı rapor kullanım

| Olası açıklamalar | Belirleme | Nasıl çözümleneceğini |
| --- | --- | --- |
| Yüksek sorgu bekleme süresini<br><br> CPU doygunluğu<br><br> DQ/LC bağlantı sınırları aşıldı | CPU kullanımı izleme \[ [21](#endnote-21)\], sorgu bekleme süresini ve DQ/LC kullanımı \[ [22](#endnote-22) \] ölçümleri + geciktirmeye yapabiliyorsanız sorgu süreleri: Eşzamanlılık sorunları gösterir | Kapasitesinin ölçeğini artırma veya içeriği farklı bir kapasiteye atayın.<br><br> Sayfa başına daha az görsellerle yöntemini yeniden tasarlamaya raporları |

#### <a name="why-are-reports-not-loading"></a>Neden raporlardır değil yükleniyor?

Raporları yüklemek başarısız bir eşleştirmenin senaryo ve kapasitesi yeterli belleğe sahip ve aşırı ısıtılan emin işareti andır. Bu, yüklenen tüm modelleri etkin olarak sorgulanan ve bu nedenle çıkarılamadığı ve herhangi bir yenileme işlemi duraklatıldı veya Gecikmeli olduğunda ortaya çıkabilir. Power BI hizmetindeki veri kümesi için 30 saniye yüklemeyi deneyecek ve kullanıcı bir öneriyle kısa süre sonra yeniden denemek için hata düzgün bir şekilde bildirilir.

Şu anda rapor için yükleme hatalarını izlemek için ölçüm yoktur. Bu sorunun olası izleme sistem belleği, özellikle en yüksek kullanımı ve en yüksek kullanım süresini belirleyebilirsiniz. Yüksek veri kümesi çıkarmaları ve uzun veri kümesi yenileme ortalama bekleme süresi, bu sorun oluştuğunu Öner.

Bu oldukça nadiren gerçekleşir, bu bir öncelik sorunu olarak kabul edilebilir değil. Rapor kullanıcıları, Hizmet meşgul ve kısa bir süre sonra yeniden denemelidir bildirilir. Çok sık böyle bir durumda, Premium kapasite ölçeklendirme veya içeriği farklı bir kapasiteye atayarak sorun çözülebilir.

Kapasite yöneticileri (ve Power BI hizmet yöneticilerinin) izleyebilirsiniz **sorgu hatası** ölçüm bu durumda belirlemek için. Ayrıca Sistem aşırı yük durumunda tüm işlemleri sıfırlama kapasite yeniden başlatabilirsiniz.

#### <a name="why-are-refreshes-not-starting-on-schedule"></a>Neden yenilemeleri zamanlama başlamıyor?

Zamanlanmış yenileme başlangıç zamanlarını garanti edilmez. Arka plan işlemleri üzerinde etkileşimli işlemleri, Power BI hizmetinde her zaman sıralayacağını geri çağırma. Yenileme iki koşul karşılandığında oluşabilecek arka plan işlemi şöyledir:

- Yeterli bellek yok
- Premium kapasite için desteklenen eşzamanlı yenileme sayısı aşılırsa değil

Koşulları karşılanmadığından, yenileme koşulları karşılığında olana kadar kuyruğa alınır.

Tam yenileme için en az iki geçerli veri kümesi bellek boyutu gerekli olduğunu hatırlayın. Yeterli bellek kullanılabilir durumda değilse, ardından yenileme başlamak olamaz kadar model çıkarma belleği serbest bırakır: bir veya daha fazla veri kümesinin etkin hale gelir ve çıkartılabilir kadar bu gecikmeler anlamına gelir.

1,5 katı arka uç yuvarlanan çekirdek, desteklenen en fazla eş zamanlı yenilemeleri sayısını ayarlandığını unutmayın.

Sonraki zamanlanmış yenileme başlamak önce başlamak olamaz, zamanlanmış yenileme başarısız olur. Arabiriminden el ile tetiklenen bir isteğe bağlı yenileme, en fazla üç kez başarısız olmadan önce çalıştırmayı dener.

Kapasite yöneticileri (ve Power BI hizmet yöneticilerinin) izleyebilirsiniz **ortalama Yenile bekleme süresi (dakika)** ölçüm zamanlanan süreden işlemi başlangıcı arasındaki ortalama gecikme belirlemek için.

Zamanında verileri etkilemek için bir yönetici öncelikli genellikle yenilerken, yeterli bellek'ın kullanılabilir olduğundan emin olun. Bu, bilinen yeterli kaynaklara sahip kapasiteler veri kümelerine yalıtma gerektirebilir. Yöneticileri basamaklandırmak veya çakışmaları en aza indirmek için zamanlanmış veri yenileme zamanları azaltmaya yardımcı olmak için veri kümesi sahipleri ile koordine mümkündür. Bir yöneticinin yenileme sıranın görüntülemek için mümkün olmadığını göz önünde bulundurun veya veri kümesi almak için zamanlar.

#### <a name="why-are-refreshes-slow"></a>Neden yenilemeleri yavaş?

Yenilemeler yavaş - veya algılanan (önceki yaygın soru adresleri) yavaş olabilir.

Yenileme aslında yavaş olduğunda, bunu birkaç nedeni olabilir:

- Yetersiz CPU (yenileme çok CPU kullanımı yoğun olabilir)
- Yenileme (Bu koşullar recommence karşılığında olduğunda üzerinden başlatmak için yenileme gerektirir) duraklatmak bunun sonucunda, yetersiz bellek
- Veri kaynağı sistem yanıt verme hızını, ağ gecikmesi, geçersiz izinler veya ağ geçidi aktarım hızı dahil olmak üzere, olmayan-kapasite nedeniyle
- Veri hacmi - artımlı yapılandırmak için geçerli bir nedeniniz yenileyin, aşağıda açıklandığı gibi

Kapasite yöneticileri (ve Power BI hizmet yöneticilerinin) izleyebilirsiniz **ortalama süre (dakika) yenileme** zamanla, karşılaştırma için bir Kıyaslama belirlemek için ölçüm ve **ortalama Yenile bekleme süresi (dakika)** ölçümleri arasındaki ortalama gecikmesini belirlemek için ortalama işlem başlangıcı zamanlanan saat arasındaki gecikme.

Artımlı yenileme, özellikle büyük model tablolar için veri yenileme süresi önemli ölçüde azaltabilir. Artımlı yenileme ile ilişkili dört avantajları vardır:

- **Yenilemeler daha hızlı** : Yalnızca bir alt kümesini bir tablo yüklenirken, azalan CPU ve bellek kullanımı ihtiyaç duyar ve birden çok bölüm yenilerken paralellik daha yüksek olabilir
- **Yenilemeler, yalnızca gerekli olduğunda gerçekleşir** : Yalnızca verilerin değiştiği yüklemek için artımlı yenileme ilkeleri yapılandırılabilir
- **Yenilemeler daha güvenilir** : Geçici veri kaynağı sistemlerine kısa çalışan bağlantılar için bağlantı kesilmesi daha az açıktır
- **Modelleri kalır kesim** : Bir kayan pencere süresinin ötesine geçmişi otomatik olarak kaldırmak için artımlı yenileme ilkeleri yapılandırılabilir

Daha fazla bilgi için bkz [artımlı yenileme Power BI Premium'da](service-premium-incremental-refresh.md) belge.

#### <a name="why-are-data-refreshes-not-completing"></a>Neden verilerdir değil Tamamlanıyor yenilenir?

Veri yenileme işlemi, ancak tamamlanamadığında, birkaç nedeni olabilir:

- Premium kapasitede, yalnızca bir model olsa yetersiz bellek, yani model boyutu çok büyük
- Veriler dahil olmak üzere, olmayan-kapasite nedeniyle sistem bağlantısının kesilmesi, geçersiz izinler veya ağ geçidi hata kaynağı

Kapasite yöneticileri (ve Power BI hizmet yöneticilerinin) izleyebilirsiniz **yenileme hataları nedeniyle bellek yetersiz** ölçümü.

#### <a name="why-are-ai-calls-failing"></a>Yapay ZEKA çağrılarıdır neden başarısız oluyor?

Yapay ZEKA çağrıları, birden çok nedenden dolayı başarısız olabilir. En az bellek gerekli AI başlatmak için iş yükü 5 GB'tır, ancak bu bazı giriş veri kümeleri için yeterli olmayabilir. Örneğin, otomatik makine öğrenme modeli eğitimi en az iki kere ve bazen birden çok kez giriş veri kümesi boyutu gerektirir. Ayrıca, tamamlanması iki saatten daha uzun sürerse bir yapay ZEKA çağrı sonlandırılır. Otomatik makine için en iyi modeli bu iki saat içinde bulunan iki saat içinde tamamlamak yoksa modeli eğitimi çağrılarını öğrenme döndürülür.  Yapay ZEKA çağrıları da öncelikli etkileşimli istekleri tarafından kesilebilir.

Yöneticiler, yapay ZEKA bekleme süresini alma önceliğe başka istekler işaretleri izlemeniz gerekir. Yöneticileri yeterli belleğe göre giriş veri boyutları yapay ZEKA iş yükü için kullanılabilir olduğunu da sağlayabilirsiniz. Bu, yapay ZEKA iş yükleri için yeterli kaynaklara sahip bilinen kapasiteler yalıtma içerebilir. Yöneticileri basamaklandırmak veya çakışmaları en aza indirmek için veri akışı yenileme zamanı azaltmak amacıyla veri akışı sahipleriyle birlikte koordine mümkündür. Unutmayın, yapay ZEKA çağrı sırası görüntülemek için bir yönetici için mümkün değildir.

### <a name="optimizing-models"></a>Modellerini iyileştirme

En iyi modeli tasarımı, etkili ve ölçeklenebilir bir çözüm sunmak için çok önemlidir. Ancak, bu teknik incelemede kapsamı dışındadır kapsamlı bir açıklama sunmaktır. Bunun yerine, bu bölümde anahtar alanları için göz önünde bulundurarak modelleri iyileştirirken sağlar.

#### <a name="optimizing-power-bi-hosted-models"></a>Power BI tarafından barındırılan modellerini iyileştirme

Premium kapasitede barındırılan en iyi duruma getirme modelleri, veri kaynakları ve model katmanına gerçekleştirilebilir.

Bir içeri aktarma modeli iyileştirmesi olasılıklarını göz önünde bulundurun:

![Bir içeri aktarma modeli iyileştirmesi olasılıklarını](media/whitepaper-premium-deployment/import-model-optimizations.png)

Veri kaynağı katmanında:

- İlişkisel veri kaynakları iyileştirilebilir hızlı olası yenileme emin olmak için uygun dizinleri uygulama, artımlı yenileme dönemlerine hizalama tablo bölümleri tanımlama ve hesaplamalar düzeniyle önceden tümleştirme veri tarafından (yerine hesaplanır tablolar ve sütunlar model) veya görünümlere hesaplama mantığı ekleme
- İlişkisel olmayan veri kaynakları ile ilişkisel depolar önceden tümleştirilebilir
- Ağ geçitleri tercihen yakın veri kaynakları için yeterli ağ bant genişliği ile ayrılmış makineye üzerinde yeterli kaynaklara sahip olduğunuzdan emin olun

Model katmanında:

- Power Query sorgu tasarımlar en aza indirmek ya da karmaşık dönüşümleri ve özellikle de farklı veri kaynakları (veri ambarları, çıkartma-dönüştürme-yükleme aşamasında bunu) birleştirme kaldırın. Ayrıca, uygun veri kaynağı gizlilik düzeylerini ayarlanmış olmasını sağlamak, bu Power BI'ın yük sorguları birleşik bir sonuç üretmek için tam sonuçları gerektiren önleyebilirsiniz.
- Model yapısını yüklemek için verileri belirler ve model boyutu doğrudan bir etkiye sahiptir. Gereksiz verileri satırları (özellikle, geçmiş veriler) kaldırma sütunları kaldırarak ya (çoğaltamaz ayrıntılı veriler yükleniyor) özetlenmiş veri yükleme yüklenmesini önlemek amacıyla tasarlanabilir. Çarpıcı boyutu azaltma, depolamaz veya çok verimli bir şekilde Sıkıştır (özellikle metin sütunları) yüksek kardinalite sütunları kaldırarak gerçekleştirilebilir.
- İki yönlü filtreleme izin vermek için yeterli bir neden olmadıkça tek yönlü ilişkiler yapılandırarak modeli sorgu performansı artırılabilir. Ayrıca iki yönlü filtreleme yerine CROSSFILTER işlevi kullanmayı düşünün.
- Bu model ve sonuç boyutunu uzun yenileme sürelerini artırır ancak toplama tablolar, hızlı sorgu yanıtları yükleme tarafından özetlenmiş veriler, önceden elde edebilirsiniz. Genellikle, toplama tabloları çok büyük modelleri veya bileşik model tasarımları için ayrılan.
- Hesaplanmış tablolar ve sütunlar model boyutunu artırabilir ve uzun yenileme kez neden. Verilerin gerçekleştirilmiş ya da veri kaynağında hesaplanan, genellikle daha küçük depolama boyutu ve hızlı bir yenileme süresi gerçekleştirilebilir. Bu mümkün değilse, özel sütunlar Power Query kullanarak geliştirilmiş depolama sıkıştırma sunabilir.
- Ölçüler ve belki de pahalı formülleri önlemek için mantıksal yeniden yazma RLS kuralları için DAX ifadeleri ayarlamak için bir fırsat olabilir.
- Artımlı yenileme önemli ölçüde yenileme süresini kısaltmak ve bellek ve CPU tasarrufu yapar. Artımlı yenileme, model boyutları kırpma tutma geçmiş verileri kaldırmak için de yapılandırılabilir.
- Farklı ve çakışan sorgu desenleri olduğunda bir model iki modeli baştan tasarladık. Örneğin, 24 saat gecikme raporlar bazı mevcut üst düzey toplamalar tüm geçmişi ve can üzerinden tolerans. Diğer raporları, bugünün verileri ile ilgili bir kaygınız ve tek işlemler için ayrıntılı erişim gerekir. Tüm raporları karşılamak için tasarım yerine tek bir model, her gereksinim için en iyi duruma getirilmiş iki modeller oluşturun.

Bir DirectQuery modeli iyileştirmesi olasılıklarını göz önünde bulundurun. Model, temel alınan veri kaynağına sorgu isteği sorunlar gibi hızlı yanıt veren model sorgular sunmak için veri kaynağı iyileştirme önemlidir.

 ![İyileştirme olasılıklarına dair bir DirectQuery modeli için](media/whitepaper-premium-deployment/direct-query-model-optimizations.png)

Veri kaynağı katmanında:

- Veri kaynağı için iyileştirilmiş hızlı olası uygun dizinleri uygulama (model katmanında mümkün değildir) verileri önceden tümleştirerek sorgulama emin olmak için tablo bölümleri, düzeniyle tanımlama (dizinli görünümlerle), veri özetlenir ve Hesaplama en aza indirir. Geçiş sorgular yalnızca filtre ve dizinli tabloları veya görünümleri arasında iç birleştirmeler gerçekleştirme ihtiyacınız olduğunda en iyi deneyimi elde edilir.
- Ağ geçitleri tercihen yakın veri kaynağı için yeterli ağ bant genişliği ile ayrılmış makineye üzerinde yeterli kaynaklara sahip olduğunuzdan emin olun

Model katmanında:

- Güç sorgu sorgu tasarımları hiçbir dönüştürme - uygulanması tercihen Aksi takdirde dönüştürmeler mutlak en az değerde tutmak girişimi
- İki yönlü filtreleme izin vermek için yeterli bir neden olmadıkça tek yönlü ilişkiler yapılandırarak modeli sorgu performansı artırılabilir. Ayrıca, modeli ilişkileri (Bu durum söz konusu olduğunda) bilgi tutarlılığını zorunlu varsaymak yapılandırılmalıdır ve daha verimli İç birleşimler (yerine outer JOIN) kullanarak veri kaynağı sorguları neden olur.
- Bu veri kaynağı, mümkün olduğunda depolanabildiği - Power Query sorgu özel sütunları veya modeli hesaplanmış sütun oluşturmaktan kaçının
- Ölçüler ve belki de pahalı formülleri önlemek için mantıksal yeniden yazma RLS kuralları için DAX ifadeleri ayarlamak için bir fırsat olabilir.

Bileşik bir model iyileştirmesi olasılıklarını göz önünde bulundurun. Geri çağırma bileşik bir model içeri aktarma ve DirectQuery tablolar bir karışımını sağlar.

![Bileşik bir model iyileştirmesi olasılıklarını](media/whitepaper-premium-deployment/composite-model-optimizations.png)

- Genellikle, içeri aktarma ve DirectQuery modelleri için en iyi duruma getirme konuları bu depolama modları kullanan bileşik model tablolara uygulanır.
- Genellikle, boyut türüyle tabloları (iş varlığı temsil eden) yapılandırarak dengeli bir tasarım elde etmek DirectQuery depolama modu olarak çift depolama modu ve türü olgu tabloları (genellikle büyük tablolar işletimsel bilgiler temsil eden) çaba. Çift depolama modu, hem içeri aktarma ve DirectQuery depolama modu ve bu geçiş için bir yerel sorgu oluşturulurken kullanılacak en verimli depolama modu belirlemek Power BI hizmetinde imkan tanıyan anlamına gelir.
- Ağ geçitleri tercihen yakın veri kaynakları için yeterli ağ bant genişliği ile ayrılmış makineye üzerinde yeterli kaynaklara sahip olduğunuzdan emin olun
- DirectQuery depolama modu türü olgu tabloları özetlemek için kullanıldığında çarpıcı sorgu performansı geliştirmeleri alma depolama modunu sunabilir olarak toplamalar tabloları yapılandırılmış. Bu durumda, toplama tablo modeli boyutunu artırın ve yenileme süresini artırmak ve daha hızlı sorgular için kabul edilebilir bir tradeoff genellikle budur.

#### <a name="optimizing-externally-hosted-models"></a>Harici olarak barındırılan modellerini iyileştirme

Birçok iyileştirme olasılıklarına dair ele [Optimizing Power BI-Hosted modelleri](#optimizing-power-bi-hosted-models) konu geçerli da Azure Analysis Services ve SQL Server Analysis Services ile geliştirilen modelleri. Şu anda, bileşik bir model ve toplama tablolar gibi desteklenmeyen bazı özellikler Temizle durumlardır.

Harici olarak barındırılan veri kümeleri için ek bir konu ile ilgili olarak Power BI hizmetini barındıran bir veritabanıdır. Azure Analysis Services için Power BI kiracınızın (ana bölge) ile aynı bölgede Azure kaynağını oluşturma anlamına gelir. Iaas için SQL Server Analysis Services için aynı bölgede VM'yi barındıran anlamına gelir ve şirket içi için bu etkili bir ağ geçidi sağlama anlamına gelir.

Azure Analysis Services veritabanları ve SQL Server Analiz Hizmetleri tablo veritabanlarında modellerini belleğe tam olarak yüklenmesi gerektirir ve bunlar var. hiç kalmasını sorgulamayı destekleme konusunda zaman unutmayın ilgi, dallarınız kaynaklanıyor olabilir. Power BI hizmetinde gibi var. model yenileme işlemi sırasında çevrimiçi kalması durumunda yenilemek için yeterli bellek olması gerekir. Power BI hizmetinde, bellek kullanımı göre içine ve dışına modelleri otomatik olarak eski konsepti yoktur. Power BI Premium, bu nedenle, daha düşük bellek kullanımı ile modeli sorgulama en üst düzeye çıkarmak için daha etkili bir yaklaşım sunar.

### <a name="capacity-planning"></a>Kapasite planlama

Kullanılabilir bellek ve işlemci kaynaklarının ve sınırları ve kapasite üzerinde uygulanan bir Premium kapasite boyutunu belirler. Premium kapasiteler de önemli bir unsur sayısıdır oluşturmayla birden fazla Premium kapasiteleri iş yüklerini birbirinden yalıtmak yardımcı olabilir. Depolama kapasitesi düğüm başına 100 TB olduğu ve her türlü iş yükü için yeterli birden büyük olasılıkla budur unutmayın.

Premium kapasiteler sayısı ve boyutu belirleme, oluşturduğunuz özellikle ilk kapasiteleri için zor olabilir. Ortalama iş yükü temsil eden anlamak için kapasite boyutlandırmasını olduğunda ilk adımı, günlük kullanım bekleniyor. Tüm iş yükleri eşit olduğunu anlama açısından önemlidir. Örneğin - uzanan bir Spektrum - sonunda tek bir görsel içeren tek bir rapor sayfasının erişme 100 eşzamanlı kullanıcıya kolayca ulaşılabilir. Henüz - - spektrumun diğer ucunda 100 farklı raporlar erişme 100 eşzamanlı kullanıcıya her 100 görselleri rapor sayfasında gittiğini kapasite kaynakları çok farklı taleplerini olun.

Kapasite yöneticileri, bu nedenle faktörlerden ortamı, içerik ve beklediğiniz kullanım için belirli göz önünde bulundurmanız gerekir. Geçersiz kılma hedefi tutarlı sorgu süreleri, kabul edilebilir bekleme süresini ve çıkarma oranları göndermeye çalışırken kapasite kullanımını en üst düzeye sağlamaktır. Göz önünde bulundurmanız gereken faktörler şunları içerebilir:

- **Model boyutu ve veri özelliklerini** : İçeri aktarma modelleri sorgulama veya yenileme izin belleğe tam yüklü olması gerekir. LC/DQ veri kümeleri, önemli bir işlemci süresi ve karmaşık bir ölçü veya RLS kuralları değerlendirilemiyor büyük olasılıkla önemli bellek gerektirebilir. Kapasite boyutu tarafından bellek ve işlemci boyutu ve LC/DQ sorgu aktarım kısıtlanmıştır.
- **Eş zamanlı active modelleri** : Bunlar bellekte kaldığında farklı alma modelleri, eş zamanlı sorgulama en iyi yanıt süresi ve performans sunar. Kendi yenileme için izin vermek için ek belleğe sahip tüm yoğun olarak sorgulanan modellerini barındırmak için yeterli bellek olmalıdır.
- **İçeri aktarma model yenileme** : Bellek ve işlemci kullanım özellikle yenileme türü (tam veya artımlı), süresi ve Power Query sorguları ve hesaplanmış tablo sütunu mantıksal karmaşıklığı etkileyebilir. Eşzamanlı yenileme kapasite boyutunu (1.5 x backend yuvarlanan çekirdek,) göre kısıtlanır.
- **Eş zamanlı sorguları** : Çok sayıda eş zamanlı sorgu sonuçlanabilir yanıt zaman raporlarının işlemci veya LC/DQ bağlantıları kapasite sınırını aşıyor. Bu, özellikle çok sayıda görsel içeren bir rapor sayfaları için durum geçerlidir.
- **Veri akışı, sayfalandırılmış raporlar ve yapay ZEKA işlevleri** : Kapasite, veri akışlarını, sayfalandırılmış raporlar ve yapay ZEKA İşlevler, her bir yapılandırılabilir maksimum kapasite bellek yüzdesi gerektiren ile destekleyecek şekilde yapılandırılabilir. Bellek için veri akışı dinamik olarak ayrılır, ancak sayfalandırılmış raporlar ve yapay ZEKA iş yükü için statik olarak ayrılır.

Bu etkenler yanı sıra kapasite yöneticileri birden fazla kapasite oluşturma düşünebilirsiniz. Birden çok kapasiteler izin vermek için iş yükü yalıtımı ve öncelikli iş yükleri kaynakları garanti olmak için yapılandırılabilir. Örneğin, iş açısından kritik iş yükleri, Self Servis BI (SSBI) iş yüklerini birbirinden ayırmak için iki kapasiteler oluşturulabilir. İş açısından kritik kapasite, bunları yalnızca BT departmanı için verilen erişim yazımıyla garanti edilen kaynaklarla sağlayarak büyük kurumsal modelleri yalıtmak için kullanılabilir. SSBI kapasite, iş analistleri için verilen erişimi olan daha küçük modelleri, artan sayıda barındırmak için kullanılabilir. SSBI kapasite bazen fazla sorgu veya yenileme bekler karşılaşabilirsiniz.

Zamanla, kapasite yöneticileri çalışma alanlarının kapasiteler arasında içerik çalışma alanları veya çalışma alanlarının kapasiteler arasında arasında taşıyarak ve kapasiteler ölçeği artırılabilen veya azaltılabilen dengeleyebilirsiniz. Genel olarak, daha büyük barındırmak için ölçeği modelleri, yedekleme ve daha yüksek Eş zamanlılık için ölçeği genişletme.

Bir lisans satın alma çekirdek kiracıyla sağladığını unutmayın. Satın alındığında bir **P3** aboneliği oluşturun veya dört Premium kapasiteleri için yedekleme için kullanılabilir yani P3 veya P2 x 2 veya 4 x 1 x P1. Ayrıca, bir P2 kapasite P3 kapasiteye yükseltme önce göz önünde bulundurarak çekirdek bölme için iki P1 kapasiteler oluşturmak için verilebilir.

### <a name="testing-approaches"></a>Test yaklaşımları

Kapasite boyutunu karar sonra test denetimli bir ortamda oluşturarak gerçekleştirilebilir. Pratik ve ekonomik bir seçenek P1 kapasiteli bir A4 kapasite, P2 ile aynı boyutta olduğunu gösteren bir Azure (A SKU'lar) kapasite ve P3 kapasiteler A5 ve işler için A6 kapasiteler aynı boyutta sırasıyla oluşturmaktır. Azure kapasitelerinin hızla oluşturulabilen ve saatlik olarak faturalandırılır. Sınama aşaması tamamlandıktan sonra bu nedenle, bunlar kolayca maliyet tahakkuk durdurmak için silinebilir.

Test içeriği, Azure ve kapasite üzerinde oluşturulan çalışma alanlarına eklenen ve ardından tek bir kullanıcı gerçekçi ve temsili iş yükü sorguları oluşturmak için rapor çalıştırabilirsiniz. İçeri aktarma modelleri varsa, her model için bir yenileme ayrıca gerçekleştirilmesi gerekir. İzleme Araçları sonra kaynak kullanımını anlamak için tüm ölçümleri gözden geçirmek için kullanılabilir.

Testleri tekrarlanabilir önemlidir: Testlerinizi birkaç kez çalıştırmanız gerekir ve her seferinde yaklaşık aynı sonucu teslim. Bu sonuçları Ortalama tahmin etmeniz ve doğru üretim koşullar altında bir iş yükü tahmin etmek için kullanılabilir.

Stres testi oluşturmak için bir yük testi gerçekçi bir iş yükünün benzetimini yapmak için uygulama geliştirme göz önünde bulundurun. Bunu başarmak nasıl ayrıntılarını bu teknik incelemede kapsamı dışında olan. Bir kod örneği de dahil olmak üzere daha fazla bilgi için başvurmak [yük testi Power BI uygulamaları Visual Studio Yük testi ile](https://blogs.msdn.microsoft.com/charles_sterling/2018/04/04/webinar-load-testing-power-bi-applications-with-visual-studio-load-test/) Web Semineri.

## <a name="exploring-real-world-scenarios"></a>Gerçek dünya senaryoları keşfetme

Bu bölümde, çeşitli gerçek hayat senaryolarında yaygın sorunlar veya zorlukları, bunları tanımlama ve bunları gidermek nasıl açıklamak için sunulacaktır:

- [Veri kümeleri güncel tutma](#keeping-datasets-up-to-date)
- [Veri kümeleri tanımlayan yavaş yanıt](#identifying-slow-responding-datasets)
- [Düzensiz yavaş yanıtlanan için nedenleri tanımlayan veri kümeleri](#identifying-causes-for-sporadically-slow-responding-datasets)
- [Yeterli bellek olup olmadığını belirleme](#determining-whether-there-is-enough-memory)
- [Yeterli CPU olup olmadığını belirleme](#determining-whether-there-is-enough-cpu)

Adımları, grafik ve tablo örneklerinin yanı sıra arasındadır **Power BI Premium kapasite ölçümleri uygulaması** (uygulama) Power BI yönetici erişimi olacaktır.

### <a name="keeping-datasets-up-to-date"></a>Veri kümeleri yukarı tarihine kadar tutma

Rapor verileri bazen eski veya "eski" olduğu görüldü, kullanıcıların şikayet olduğunda bu senaryoda, bir araştırma tetiklendi.

Uygulamada, yönetici etkileşimde **yeniler** görsel tarafından veri kümelerini sıralama **en fazla bekleme zamanı** azalan düzende istatistikleri. Bu kez, çalışma alanı adına göre gruplandırılmış tanımladığımız sahip veri kümeleri bekleyin Göster yardımcı olur.

![Veri kümesini yenilemeleri maksimum bekleme süresi, çalışma alanı tarafından gruplandırılmış göre azalan düzende sıralandı](media/whitepaper-premium-deployment/dataset-refreshes.png)

Buna ek olarak **saatlik ortalama Yenile bekleme süresini** visual, bunlar yenileme bekleme süresini tutarlı bir şekilde her gün 4 saat yaklaşık tepe dikkat edin.

![Yenileme yoğun düzenli olarak 4 saat bekler.](media/whitepaper-premium-deployment/peak-refresh-waits.png)

Bu sonuçları için birkaç olası açıklamalar şunlardır:

- Çok fazla yenileme denemeleri aynı zamanda, kapasite düğümü (varsayılan bellek ayırma ile P1 üzerinde altı eşzamanlı yenileme) tarafından uygulanan sınırları aşma gerçekleşen

- Yenilenecek veri kümeleri (en az 2 x tam yenileme için gerekli bellek gerektiren) kullanılabilir belleğe sığmayacak kadar büyük olabilir.
- Bellek kullanım artış verimsiz Power Query mantıksal veri kümesi yenilemesi sırasında elde edilen. Meşgul bir kapasitede Bu bazen yenileme başarısız ve büyük olasılıkla diğer rapor görünümü işlemleri kapasite etkileyen fiziksel sınırı ulaşabilirsiniz.
- Bellekte kalması için gereken sık Sorgulanmış veri kümeleri, diğer veri kümeleri, sınırlı kullanılabilir bellek nedeniyle yenileme yeteneğini etkileyebilir

Bu araştırmanıza yardımcı olmak için Power BI yönetici bakabilirsiniz:

- Veri yenileme, kullanılabilir bellek yenilenecek veri kümesi boyutu x 2'den az olduğunda anında kullanılabilir düşük bellekle
- Veri kümesi değil yenilenen ve bir yenileme önce bellekte değildi, ancak yenileme yoğun saatlerde etkileşimli trafiği gösterme başladı. Hangi veri kümelerinin bir Power BI belirli bir zamanda belleğe yüklenen görmek için yönetici veri kümeleri alanının bakabilirsiniz **veri kümeleri** uygulama ve çapraz filtre çubuklarında birinde tıklayarak belirli bir süre için sekmesinde **saatlik Veri kümesi sayıları yüklenen**. (Aşağıdaki görüntüde gösterilmiştir) yerel bir depo birden fazla veri kümesi zamanlanmış yenilemeleri başlangıcı gecikmesine neden belleğe yüklenen ne zaman bir saat gösterir
- Yüksek bellek baskısı yenileme saatten önce çok fazla sayıda farklı etkileşimli raporlar sunarak nedeniyle oluştu belirten başlatmak için zamanlanan veri yenilemeleri, artan veri kümesi çıkarmaları alma yerleştirin. **Saatlik veri kümesi çıkarmaları ve bellek tüketimi** visual çıkarmaları artış açıkça belirtebilirsiniz.

Aşağıdaki görüntüde yüklenen veri kümeleri içinde yerel bir depo gösterilmektedir etkileşimli sorgulama kullandınız, yenilemeleri başlangıcı ertelendi. Bir zaman diliminde seçerek **saatlik yüklenen veri kümesi sayar** visual alanları arası filtre **veri kümesi boyutları** visual.

![Yerel bir depo yüklenen veri kümelerinde etkileşimli sorgulama Gecikmeli Başlangıç gecikebilir önerir](media/whitepaper-premium-deployment/hourly-loaded-dataset-counts.png)

Power BI yönetici olarak başlatmak veri yenileme için kullanılabilir yeterli bellek olduğundan emin olmak için adımları izleyerek bu sorunu çözmek deneyebilirsiniz:

- Veri kümesi bağlantı kuruluyor sahipleri ve bunları isteyen kademelendirme ve veri alanı için yenileme zamanlamaları
- Veri kümesi azaltma gereksiz panolar veya Pano kaldırarak sorgu yükünü kutucukları, özellikle de satır düzeyinde güvenlik zorlama
- Power Query mantıksal iyileştirerek veri yenilemeleri ' hızlandırmak, model hesaplanan sütunları veya tabloları, veri kümesi boyutları azaltma veya artımlı veri gerçekleştirmek için daha büyük veri kümelerini yapılandırma yenileyin

### <a name="identifying-slow-responding-datasets"></a>Veri kümeleri tanımlayan yavaş yanıt

Bu senaryoda, kullanıcıların belirli raporları açmak için uzun sürdü şikayet zaman araştırma tetiklendi ve bazen askıda kalabilir.

Uygulamada, Power BI yönetici kullanabilir **sorgu süreleri** kötü performansa veri kümeleri, veri kümelerine göre azalan düzende sıralayarak belirlemek için görsel **ortalama süresi**. Veri kümelerinin ne sıklıkta sorgulanır görebilmeniz için bu görsel sorgu sayısı, veri kümesi de gösterir.

![Devamlılığımız kötü performansa veri kümeleri](media/whitepaper-premium-deployment/worst-performing-datasets.png)

Power BI yöneticinize başvurabilir **sorgu süre dağılımı** görsel, genel bir kümelenmiş sorgu performansı dağılımını gösterir (< 30ms, = 0-100ms, vb.) filtrelenmiş bir dönem. Genellikle, sınav zamanı bir saniye veya daha kısa, çoğu kullanıcı tarafından duyarlı kabul sorgular; uzun süren sorgular, hatalı performans algısı oluşturma eğilimindedir.

**Saatlik sorgu süre dağılımı** visual ne zaman kapasite performans algılanan bir saatlik sürelere belirlemek Power BI Yöneticisi olarak zayıf sağlar. Daha büyük çubuğunu temsil sorgu süreleri bir saniye içinde daha büyük kullanıcıların kötü performans algılamalarını risk ayırır.

Görsel etkileşimlidir ve bir segmenti çubuk seçildiğinde, karşılık gelen **sorgu süreleri** Tablo rapor sayfasında visual temsil ettiği veri kümelerini göstermek için çapraz filtre. Bu çapraz filtreleme kolayca belirlemek Power BI yönetici, veri kümeleri yavaş yanıt verir.

Aşağıdaki görüntüde göre filtrelenmiş bir görsel gösterir **saatlik sorgu süresi dağıtımları**, kötü performansa veri kümelerinin bir saatlik demet odaklanan. 

![Veri kümeleri gerçekleştirmek daha da kötüsü filtrelenmiş saatlik sorgu süresi dağıtımları visual gösterir](media/whitepaper-premium-deployment/hourly-query-duration-distributions.png)

Power BI yönetici, belirli 1 saatlik zaman aralığı düşük performanslı kümesinde belirlendiğinde, zayıf performans tarafından aşırı yüklenmiş bir kapasite nedeniyle veya veri kümesini veya raporu nedeniyle kötü tasarlanmış olup olmadığını araştırabilirsiniz. Bunu başarmak için bunlar başvurabilir **sorgu bekleme süreleri** görsel ve tarafından Ortalama Sorgu bekleme süresi azalan sıralama veri kümeleri. Sorguları büyük bir yüzdesini bekliyorsanız, yüksek talep veri kümesi için büyük olasılıkla pek çok sorgu bekler nedenidir. Ortalama Sorgu bekleme süresi önemli ölçüde ise (> 100ms), bu veri kümesini ve en iyi duruma getirme yaptıklarını varsa görmek için raporu gözden geçirmekte olabilir. Örneğin, belki de daha az görsellerin üzerinde rapor sayfaları ya da bir DAX ifadesi iyileştirme verilir.

![Zayıf performans gösteren veri kümelerini görüntülemek için sorgu bekleme süreleri görsel yardımcı olur](media/whitepaper-premium-deployment/query-wait-times.png)

Sorgu bekleme zaman yapıyı veri kümelerinde birkaç olası nedeni vardır:

- İyinin modeli tasarımı, ölçü ifadelerini veya hatta rapor Tasarım - katkıda bulunmak tüm koşullar, yüksek düzeyde CPU kullanan sorguları uzun süre çalışan. Bu, CPU iş parçacığı kullanılabilir hale gelir ve en yüksek çalışma saatleri sırasında yaygın olarak görülen bir konvoy etkisi (Düşünme trafiği Başınızı) oluşturabilirsiniz kadar beklenecek yeni sorgular zorlar. **Sorgu beklemeleri** sayfası, veri kümeleri yüksek Ortalama Sorgu bekleme süresini sahip olup olmadığını belirlemek için ana kaynak olacaktır.
- Çok sayıda eş zamanlı kapasite kullanıcılar (yüz binlerce) aynı rapor veya veri kümesi kullanma. Daha iyi tasarlanmış veri kümeleri, hatalı bir eşzamanlılık eşikten yüksek gerçekleştirebilirsiniz. Bu genellikle diğer veri kümelerini Göster sorgu sayısına yönelik önemli ölçüde daha yüksek bir değer gösteren tek bir veri kümesi tarafından gösterilir (yani 300K sorgular için bir veri kümesi ile karşılaştırıldığında < 30 bin sorguları diğer tüm veri kümeleri için). Sorgu beklemeleri basamaklandırmak bu veri kümesi başlar ve bu içinde görülür belirli bir noktada **sorgu süreleri** visual.
- Veri kümeleri içine ve dışına bellek sık geçerken çok yavaş neden sorgulanan aynı anda birçok farklı veri kümeleri. Veri kümesi belleğe yüklendiğinde, yavaş performans sorunu yaşayan kullanıcı sonuçlanır. Bunu doğrulamak için Power BI yöneticinize başvurabilir **saatlik veri kümesi çıkarmaları ve bellek tüketimi** görsel, çok sayıda veri kümeleri belleğe yüklenen gösterebilir art arda çıkarıldığına.

### <a name="identifying-causes-for-sporadically-slow-responding-datasets"></a>Düzensiz yavaş yanıtlanan için nedenleri tanımlayan veri kümeleri

Kullanıcıların rapor görselleri bazen düşünmüştür yavaş yanıt veya yanıt veremez duruma, ancak yazıldıkça yeterince hızlı yanıt veren diğer zamanlarda açıklanan olduğunda bu senaryoda, bir araştırma tetiklendi.

Uygulama içinde **sorgu süreleri** bölümü, aşağıdaki şekilde sorunlu veri kümesini bulmak için kullanılan:

- İçinde **sorgu süreleri** visual yönetici veri kümesini veri kümesi (sorgulanan en üst veri kümeleri başlayarak) tarafından filtrelenir ve çapraz filtre uygulanmış çubuklarında incelenirken **saatlik sorgu dağıtımları** visual.
- Ne zaman bir tek bir saatlik çubuğu gösterdi önemli değişiklikler, bu veri kümesi için başka bir saatlik çubukları ve tüm sorgu süresi grupları arasındaki oran (yani renkler arasındaki oranları değiştirir önemli ölçüde), bu veri kümesi ara sıra bir değişiklik gösterilen anlamına gelir performans.
- Zayıf performanslı sorguların düzensiz bir kısmını gösteren bir saatlik çubukları, söz konusu veri kümesi tarafından diğer veri kümelerine etkinlikleri tarafından neden bir gürültülü komşu etkisi burada etkilendiğini bir TimeSpan değeri gösterilir.

Bir veri kümesi performans önemli bir setback oluştu burada gösterildiği bir saat 30 Ocak aşağıdaki resim "(3,10s]"yürütme süre demetine. boyutu tarafından belirtilen Bu bir saatlik çubuğuna tıklayarak, bu nedenle gürültülü komşu etkisi aday sorunlu veri kümeleri görünmesini bu süre boyunca, belleğe yüklenmiş tüm veri kümelerini ortaya çıkarır.

![Büyük bir bölümü tarafından kötü performans gösteren çubuk](media/whitepaper-premium-deployment/worst-performing-queries.png)

Sorunlu bir zaman aralığı (yani sırasında Oca 30 yukarıdaki resimde) tanımlandıktan sonra Power BI Yöneticisi tüm veri kümesi filtreleri kaldırın ardından hangi veri kümelerinin bu süre boyunca etkin bir şekilde sorgulandığını belirlemek için yalnızca bu timespan göre filtreleyin. Gürültülü komşu efekt için sabah veri kümesi, genellikle üst sorgulanan veri kümesi veya Ortalama Sorgu en uzun süresi aşağıdakilerden olur.

Bu soruna bir çözüm, veri kümeleri üzerinde farklı Premium kapasite veya veri kümesi boyutu, tüketim gereksinimleri ve veri desenleri yenilerseniz paylaşılan kapasite üzerinde farklı çalışma alanları desteklenir sabah dağıtmak için olabilir.

Bu durumun tersi de geçerli olabilir. Power BI yönetici, ne zaman bir veri kümesi sorgu performansını önemli ölçüde artıran kez belirleyin ve sonra ne kayboldu bakın. Bu noktada belirli bilgileri eksikse, ardından, neden olan soruna işaret edecek şekilde yardımcı olabilir.

### <a name="determining-whether-there-is-enough-memory"></a>Belirleme olmadığını yeterli bellek yok

Kapasite, iş yüklerini tamamlanması için yeterli bellek olup olmadığını belirlemek için Power BI yöneticinize başvurabilir **tüketilen bellek yüzdelerini** görsel **veri kümeleri** uygulama sekmesinde. **Tüm** (toplam) bellek olup olmadığı, etkin olarak sorgulanan işlenen veya bağımsız olarak belleğe yüklenen veri kümeleri tarafından kullanılan belleği temsil eder. **Etkin** belleği, etkin olarak işlenmekte olan veri kümeleri tarafından kullanılan belleği temsil eder.

Bu, tüm (toplam) arasında bir boşluk gösteren gibi görsel sağlıklı bir kapasitede görünür ve etkin bellek:

![Sağlıklı bir kapasite tüm (toplam) arasında bir boşluk gösterilir ve etkin bellek](media/whitepaper-premium-deployment/memory-healthy-capacity.png)

Bellek baskısı yaşayan bir kapasitede etkin bellek ve yakınsamaya, o noktasında belleğe ek veri kümeleri imkansız olduğu anlamına gelen toplam bellek ve aynı görsele açıkça gösterilir. Bu durumda, Power BI yönetici tıklayabilirsiniz **kapasite yeniden** (içinde **Gelişmiş Seçenekler** Yönetim Portalı'nın kapasite ayarları alanının). Kapasite sonuçları, tüm veri kümeleri olduğu bellekten Temizlenen ve bunları belleğe gerektirdiği (yenileme) sorguları veya veri olarak yeniden yüklemek izin verme yeniden başlatılıyor.

![** İle yakınsamaya etkin ** bellek ** tüm ** bellek](media/whitepaper-premium-deployment/memory-unhealthy-capacity.png)

### <a name="determining-whether-there-is-enough-cpu"></a>Belirleme olmadığını yeterli CPU var.

Genel olarak, kapasite 's ortalama CPU kullanımı % 80 aşağısına kalmalıdır. Bu değer aşan CPU doygunluğu kapasitesine yaklaşıyor anlamına gelir.

CPU doygunluğu etkilerini işlemleri tüm işlemleri işlemek çalışır gibi birçok CPU bağlam geçişi gerçekleştirme kapasite nedeniyle izin verilenden daha uzun sürüyor olarak ifade edilir. Bir Premium kapasite ile çok sayıda eş zamanlı sorguları bu yüksek sorgu tarafından belirtilen kez bekleyin. Normalden daha yavaş yanıt hızı yüksek sorgu bekleme süresini bir sonucu var. CPU görüntüleyerek Doygunluk düzeyine ne zaman Power BI yönetici kolayca tanımlayabilirsiniz **saatlik sorgu bekleme süresi dağıtımları** visual. Dönemsel en yüksek sayılar sorgu bekleme süresi olası CPU doygunluğu sayılarını gösterir.

![Dönemsel en yüksek sayılar sorgu bekleme süresi olası CPU doygunluğu sayılarını gösterir](media/whitepaper-premium-deployment/peak-query-wait-times.png)

Bunlar için CPU doygunluğu katkıda, benzer bir desen bazen arka plan işlemlerinde algılanabilir. Power BI yönetici, yenileme saatlerini (büyük olasılıkla nedeniyle diğer devam eden bir veri kümesini yenilemeleri ve/veya etkileşimli sorgular) zaman CPU doygunluğu belirtebilir belirli bir dataset için düzenli bir depo için bakabilirsiniz. Bu örnekte, söz konusu **sistem** uygulama görünümünde mutlaka açığa CPU'nun % 100 olduğundan. **Sistem** görüntüleyen saatlik ortalamalar, ancak CPU yoğun işlem birkaç dakika içinde bekleme süresini ani gösterilir, doygun.

CPU doygunluğu etkisini görmek için daha fazla küçük farklar vardır. Bekleme sorguların sayısını önemli olsa da, sorgu bekleme süresi her zaman bir dereceye kadar Ölçek performans düşüşüne neden olmadan gerçekleşir. Bazı veri kümeleri (ile karmaşıklığı ya da boyutunu gösteren daha uzun Ortalama Sorgu süresini) diğerlerinden daha fazla CPU doygunluğu etkilerini fazladır. Bu veri kümelerini kolayca belirlemek için Power BI yönetici değişiklikleri çubukların rengini birleşimde arayabilirsiniz **bekleyin saatlik zaman dağıtım** visual. Aykırı çubuğu kapsamlı sonra bunlar sorgu beklediği sırada olan veri kümeleri için bakın ve Ortalama Sorgu süresi ile karşılaştırıldığında Ortalama Sorgu bekleme zaman da bakın. Bu iki ölçüm aynı büyüklük ve veri kümesi için sorgu iş yükü Önemsiz olduğundan, veri kümesi tarafından yetersiz CPU etkilenir olasıdır.

Bir veri kümesi her veri bloğu sırasında CPU doygunluğu bunun sonucunda yüksek sıklık düzeyi sorgular (yani bir oturumda eğitim), birden çok kullanıcı tarafından kısa ani artışlara tüketilen bu etki özellikle görünür olabilir. Bu durumda, bu veri kümesi üzerinde önemli bir sorgu bekleme süresini (gürültülü komşu etkisi) kapasite diğer veri kümelerinde etkileyen yanı sıra yaşadı.

Bazı durumlarda, Power BI yöneticileri veri kümesi sahipleri daha az oluşturmak isteyebilirsiniz (düzenli aralıklarla herhangi bir veri kümesi ile hangi sorguların yenilemek için önbelleğe alınan kutucuklar) bir Pano yerine bir rapor oluşturarak geçici sorgu iş yükü. Bu, Pano yüklendiğinde ani önlemeye yardımcı olabilir. CPU doygunluğu, veri kümesine değiştirme yapmadan önlemek için verimli bir yöntem olabilir ancak bu çözümü her zaman iş gereksinimlerini mümkün olmayabilir.

## <a name="conclusion"></a>Sonuç

Power BI Premium, kuruluşunuzdaki herkes için daha tutarlı bir performans, büyük veri hacimleri için destek ve birleşik bir Self Servis ve kurumsal BI platformu esnekliğini sunar. Bu düzey 300 teknik incelemedir özellikle Power BI yöneticileri ve içerik yazarlarının ve yayımcılar için yazıldı. Bu amaçlar, Power BI Premium potansiyelini anlamalarına yardımcı olmak ve tasarlama, dağıtma, izleme ve sorun giderme ölçeklenebilir çözümler yapılacağı açıklanmaktadır.

Power BI Premium kapasiteleri yönetmek ve dağıtmak için Yöneticiler ve geliştiriciler modeli nasıl çok iyi bir anlayış gerektirir kapasiteler işlevi, nasıl, izlenen ve yönetilebilen ve nasıl modelleri, için uygun şekilde yanıt vermek üzere iyileştirilebilir Performans sorunlarını ve performans sorunlarını ortaya.

## <a name="end-notes"></a>Son Notları

<a name="endnote-01"></a>\[1\] Bu teknik incelemede Power BI bulut hizmeti tarafından desteklenen yalnızca Power BI Premium ile ilgilidir ve Power BI rapor sunucusu, yüklemek için lisans gerekli durumuna kapsam içinde değil, dışında bu nedenle Power BI rapor sunucusu ile bazı yer alır Power BI Premium SKU'ları.

<a name="endnote-02"></a>\[2\] içeriği uygulama kullanıcılar adına katıştırılacak kullanıldığında bir bulut hizmeti olarak power BI, Platform olarak-a-hizmet (PaaS). Bu tür bir ekleme biri olan Power BI Premium farklı iki ürün ile gerçekleştirilebilir.

<a name="endnote-03"></a>\[3\] iletme, akış ve karma veri kümeleri Premium kapasiteleri içinde depolanmaz ve bu nedenle dağıtma, yönetme ve Premium kapasiteleri izleme önemli bir unsur değildir.

<a name="endnote-04"></a>\[4\] Excel çalışma kitaplarını Power BI içerik türü olarak Premium kapasiteleri içinde depolanmaz ve bu nedenle dağıtma, yönetme veya Premium kapasiteleri izleme önemli bir unsur değildir.

<a name="endnote-05"></a>\[5\] görseller, Dilimleyici etkileşimleri yok saymak için yapılandırılabilir. Daha fazla bilgi için bkz [Power BI raporlarındaki görselleştirme etkileşimleri](service-reports-visual-interactions.md) belge.

<a name="endnote-06"></a>\[6\] boyutu arasındaki fark, dosya için bellek Görev Yöneticisi'ni kullanarak Power BI Desktop dosya boyutu karşılaştırarak belirlenebilir.

<a name="endnote-07"></a>\[7\] Microsoft veri kaynakları için destek, SQL Server, Azure veri blokları, Azure HDInsight Spark (Beta), Azure SQL veritabanı ve Azure SQL veri ambarı içerir. Ek kaynaklar hakkında daha fazla bilgi için bkz [Power bı'da Directquery tarafından desteklenen veri kaynakları](desktop-directquery-data-sources.md) belge.

<a name="endnote-08"></a>\[8\] power BI Premium, en çok 10 GB boyutundaki bir Power BI Desktop (.pbix) dosyayı karşıya yüklemeyi destekler. Karşıya sonra veri kümelerini yenileme sonucunda boyutu 12 GB'a kadar büyüyebilir. En fazla karşıya yükleme boyutu SKU göre değişir. Daha fazla bilgi için bkz [büyük veri kümelerini Power BI Premium desteği](service-premium-large-datasets.md) belge.

<a name="endnote-09"></a>\[9\] SKU'ları daha az dört çekirdek adanmış altyapı üzerinde çalıştırmayın. EM1 ve EM2, A1 ve A2 SKU'ları de buna dahildir.

<a name="endnote-10"></a>\[10\] ender olsa da modelleri hizmet işlemleri nedeniyle bellekten kaldırılmış olabilir.

<a name="endnote-11"></a>\[11\] bu zamanlamaları herhangi bir zamanda değiştirilebilir.

<a name="endnote-12"></a>\[12\] bu şu anda önizlemede çoklu coğrafi olarak adlandırılır. Çoklu coğrafi dağıtımı için stratejinin için genellikle Kurumsal veya kamu uyumluluk yerine performans ve ölçek. Rapor ve Pano yükleme, giriş bölgesini meta veri isteklerine yine de içerir. Daha fazla bilgi için bkz [Power BI Premium (Önizleme) çoklu coğrafi desteği](service-admin-premium-multi-geo.md) belge.

<a name="endnote-13"></a>\[13\] kullanıcılar performans sorunlarına neden olabileceğini işleri ile Power BI hizmetinde aşırı yüklemesi, fazla karmaşık bir sorgu yazma, döngüsel başvurular, vb. oluşturmak mümkündür.

<a name="endnote-14"></a>\[14\] tüm kuruluşun çalışma alanları atama seçeneğini önerilmez ve daha hedefe yönelik bir yaklaşım tercih edilir. Genelde, bu üretim içerik için kişisel çalışma alanlarını kullanmak için en iyi yöntem değildir.

<a name="endnote-15"></a>\[15\] uygulamasında veya Azure portalında, ancak Power BI Yönetici portalı A SKU'ları izlemek mümkündür. Kaynak okuyucu rolüne uygulama eklenmedi A SKU'ları izlemek için raporun yenilenmesi başarısız olur. Daha fazla bilgi için bkz [İzleyici Power BI Premium ve Power BI Embedded kapasitelerini](service-admin-premium-monitor-capacity.md) belge.

<a name="endnote-16"></a>\[16\] yenilemeleri olmadığında yeterli CPU veya bellek başlatmak için bekleyebilir.

<a name="endnote-17"></a>\[17\] bellek veri kümesi boyutu % 20 tarafından diskte boyutundan daha büyük olabilir.

<a name="endnote-18"></a>\[18\] ortalama bellek kullanımı (GB) ve en yüksek bellek tüketimi (GB)

<a name="endnote-19"></a>\[19\] veri kümesi çıkarmaları

<a name="endnote-20"></a>\[20\] Dataset sorgularında, veri kümesi Ortalama Sorgu süresi (ms), veri kümesi bekleyin sayısı ve veri kümesi ortalama bekleme süresi (ms)

<a name="endnote-21"></a>\[21\] yüksek CPU kullanımı sayısı ve CPU süresi (son yedi gün içinde) en yüksek kullanımı

<a name="endnote-22"></a>\[22\] DQ/LC yüksek kullanımı sayısı ve en yüksek kullanımı (son yedi gün içinde) DQ/LC saati