---
title: Power BI geçişine genel bakış
description: Farklı bir üçüncü taraf iş zekası aracından Power BI’a geçişi planlamayı ve yönetmeyi öğrenin.
author: peter-myers
ms.author: v-pemyer
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi
ms.topic: conceptual
ms.date: 08/20/2020
ms.openlocfilehash: 8f8e58f61d2baa66cd0baf351857656588cfbe9f
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96419257"
---
# <a name="power-bi-migration-overview"></a>Power BI geçişine genel bakış

Yönetilen self-servis iş zekası sunma (SSBI), kurumsal iş zekasının verimli şekilde sunulmasını sağlama ve ekonomik baskıları giderme olanağı tanıyan bir veri kültürünün sürdürülmesi gibi nedenlerden ötürü her geçen gün daha fazla müşteri Power BI’ı standartlaştırıyor. Bu Power BI geçişi makaleleri serisi, üçüncü taraf bir iş zekası aracından Power BI’a geçişin planlanması ve gerçekleştirilmesine ilişkin rehberlik sunmayı amaçlar.

Power BI geçişi serisi şu makaleleri içerir:

1. Power BI geçişine genel bakış (bu makale)
1. [Power BI’a geçişe hazırlanma](powerbi-migration-pre-migration-steps.md)
1. [Power BI’a geçiş yapmak için gereksinimleri toplama (1. aşama)](powerbi-migration-requirements.md)
1. [Power BI’a geçiş yapmak için dağıtımı planlama (2. aşama)](powerbi-migration-planning.md)
1. [Power BI’a geçiş yapmak için kavram kanıtı yönetme (3. aşama)](powerbi-migration-proof-of-concept.md)
1. [Power BI’a geçiş yapmak için içerik oluşturma (4. aşama)](powerbi-migration-create-validate-content.md)
1. [Power BI’a dağıtma (5. aşama)](powerbi-migration-deploy-support-monitor.md)
1. [Müşteri Power BI geçişlerinden öğrenme](powerbi-migration-learn-from-customers.md)

İki varsayım bulunur: Kuruluşunuzda eski bir iş zekası platformu kullanılıyor ve içeriğin ve kullanıcıların resmi olarak Power BI’a geçirilmesi kararlaştırıldı. Bu seri, öncelikli olarak Power BI hizmetinin geçirilmesine odaklanır. Bu makale serisinde ele alınan konuların yanı sıra, ulusal bulut müşteriler için diğer hususlar geçerli olabilir.

Aşağıdaki diyagramda, Power BI’ın kuruluşunuza dağıtılmasına yönelik dört yüksek düzey aşamayı görebilirsiniz.

:::image type="content" source="media/powerbi-migration-overview/migrate-to-powerbi-high-level-overview.png" alt-text="Aşağıdaki tabloda açıklanan dört yüksek düzey aşamayı gösteren görüntü.":::

|Aşama|Açıklama|
|--------|-----------|
|![1\. aşama.](media/common/icon-01-red-30x30.png)|**Power BI’ı ayarlama ve değerlendirme.** İlk aşama, ilk Power BI mimarisini oluşturmayı kapsar. Bu noktada, ön dağıtım ve idare planlaması işlenir ve yatırım getirisi ve/veya maliyet avantajı analizine ilişkin Power BI değerlendirmeleri yapılır.|
|![2\. aşama.](media/common/icon-02-red-30x30.png)|**Power BI’da hızla yeni çözümler oluşturun.** İkinci aşamada, self servis iş zekası yazarları Power BI’ı ihtiyaçlara uygun şekilde kullanıp değerlendirmeye başlayabilir ve Power BI’dan hızla değer elde edilebilir. 2\. aşamadaki etkinliklerde Power BI gibi yeni bir iş zekası aracının benimsenmesi açısından kritik olan çevikliğe ve hızla iş değeri elde etmeye odaklanılır. Bu nedenle, 3. aşamadaki geçiş etkinlikleriyle yan yana gerçekleşen etkinlikler, şemanın 2. aşamasında gösterilir.|
|![3\. aşama.](media/common/icon-03-red-30x30.png)|**İş zekası varlıklarını eski platformdan Power BI’a geçirme.** Üçüncü aşamada Power BI’a geçiş yapma ele alınır. Bu, Power BI geçişi makalelerine ilişkin bu serinin odak noktasını oluşturur. Sonraki bölümde beş özel geçiş aşaması ele alınır.|
|![4\. Aşama.](media/common/icon-04-red-30x30.png)|**Power BI’ı benimseme, yönetme ve izleme.** Son aşama, veri kültürünü geliştirme, iletişim ve eğitim gibi devam eden etkinliklerden oluşur. Bu etkinlikler, Power BI’ın etkili şekilde uygulanmasını önemli ölçüde etkiler. Kuruluşunuza uygun idare ve güvenlik ilkeleri ve işlemlerinin olması ve ölçeklendirme, büyüme ve sürekli olarak gelişme olanağı sunan denetim ve izleme özelliklerinin bulunması önemlidir.|

> [!IMPORTANT]
> Resmi Power BI geçişi, yeni bir Power BI çözümünün oluşturulmasıyla neredeyse her zaman paralel gerçekleşir. _Power BI çözümü_, hem verilerin hem de raporların kullanımını kapsayan genel bir terimdir. Bir Power BI Desktop (.pbix) dosyası bir veri modelini veya raporu ya da her ikisini içerebilir. Verilerin yeniden kullanılabilmesi için [veri modelini raporlardan ayırma](../guidance/report-separate-from-model.md) işlemini yapmanız önerilir. Ancak, bu işlem gerekli değildir.
>
> Resmi geçişi planlayıp gerçekleştirirken yeni gereksinimleri yazmak için Power BI’ı kullanın. Bu, daha fazla destek elde etmenize yardımcı olur. Eş zamanlı aşamalar, içerik yazarlarına Power BI’a ilişkin faydalı gerçek dünya deneyimi sunar.

## <a name="five-stages-of-a-power-bi-migration"></a>Power BI geçişinin beş aşaması

Bu diyagramın 3. aşamasında Power BI’a geçişe yönelik bilgiler sunulur. Bu aşamada beş genel adım bulunur.

:::image type="content" source="media/powerbi-migration-overview/migrate-to-powerbi-five-stages.png" alt-text="Bir Power BI geçişinin aşamalarını (sonraki bölümde açıklanmıştır) gösteren görüntü.":::

Önceki diyagramda gösterilen adımlar şunlardır:

- [Geçiş öncesi adımları](#pre-migration-steps)
- [1. aşama: Gereksinimleri toplama ve önceliklendirme](#stage-1-gather-requirements-and-prioritize)
- [2. aşama: Dağıtımı planlama](#stage-2-plan-for-deployment)
- [3. aşama: Kavram kanıtı yönetme](#stage-3-conduct-proof-of-concept)
- [4. aşama: İçerik oluşturma ve doğrulama](#stage-4-create-and-validate-content)
- [5. aşama: Dağıtım, destek ve izleme](#stage-5-deploy-support-and-monitor)

### <a name="pre-migration-steps"></a>Geçiş öncesi adımları

Geçiş öncesi adımları, içerik eski bir iş zekası platformundan Power BI’a geçirilmeden önce göz önünde bulundurulan adımları içerir. Genelde ilk kiracı düzeyi dağıtım planlamasını içerir. Bu etkinlikler hakkında daha fazla bilgi edinmek için bkz. [Power BI’a geçiş yapmaya hazırlanma](powerbi-migration-pre-migration-steps.md).

### <a name="stage-1-gather-requirements-and-prioritize"></a>1\. aşama: Gereksinimleri toplama ve önceliklendirme

1\. aşamada bilgi toplamaya ve tek bir çözüme ilişkin geçişin planlanmasına odaklanılır. Bu işlemin yinelemeli olması ve kapsamının makul boyutlu bir çalışma olarak belirlenmesi gerekir. 1\. aşamanın sunduğu çıkış, geçirilecek öncelikli rapor ve verilere ilişkin bir envanteri içerir. Çalışma düzeyinin tam olarak tahmin edilebilmesi için 2. ve 3. aşamadaki ek etkinliklerin yapılması gerekir. 1\. aşamadaki etkinlikler hakkında daha fazla bilgi edinmek için bkz. [Power BI’a geçiş yapmak için gereksinimleri toplama](powerbi-migration-requirements.md).

### <a name="stage-2-plan-for-deployment"></a>2\. aşama: Dağıtımı planlama

1\. aşamada tanımlanan gereksinimlerin her çözümde karşılanmasına yönelik bilgiler 2. aşamada sunulur. Yinelemeli ve doğrusal olmayan işleme kılavuzluk edecek olabildiğince fazla ayrıntı 2. aşamada çıkış olarak sunulur. Kavram kanıtı oluşturma (3. aşama) işlemi bu aşamayla paralel olarak gerçekleşebilir. Çözüm oluşturulurken (4. aşama), dağıtım planlamasına ilişkin kararları etkileyen ek bilgiler ortaya çıkabilir. 2\. aşamada gerçekleştirilen bu dağıtım planlaması türü çözüm düzeyine odaklanır ve kurumsal düzeyde alınan kararlara uyum sağlar. 2\. aşamadaki etkinlikler hakkında daha fazla bilgi edinmek için bkz. [Power BI’a geçiş yapmak için dağıtımı planlama](powerbi-migration-planning.md).

### <a name="stage-3-conduct-proof-of-concept"></a>3\. aşama: Kavram kanıtı yönetme

3\. aşamada, bilinmeyenlerin ele alınmasına ve risklerin olabildiğince erken azaltılmasına odaklanılır. Dağıtım planlamasıyla (2. aşama) birlikte yinelemeli olarak gerçekleştirilebilen teknik kavram kanıtları (POC), varsayımların doğrulanmasına yardımcı olur. Bu aşamada, çıkış olarak dar kapsamlı bir Power BI çözümü elde edilir. POC’nin tek kullanımlık bir çalışma olmasını amaçlamıyoruz. Ancak, bunun üretime hazır hale getirilmesi için 4. aşamada muhtemelen ek işlem yapılması gerekecek. Bu bağlamda, kuruluşunuzda bu etkinliği prototip, pilot, örnek, hızlı başlangıç veya en sade ürün (MVP) olarak adlandırabilirsiniz. POC yönetme her zaman gerekmez ve işlem resmi olmayan yöntemlerle de gerçekleştirilebilir. 3\. aşamadaki etkinlikler hakkında daha fazla bilgi edinmek için bkz. [Power BI’a geçiş yapmak için kavram kanıtı yönetme](powerbi-migration-proof-of-concept.md).

### <a name="stage-4-create-and-validate-content"></a>4\. Aşama: İçerik oluşturma ve doğrulama

4\. aşamada, POC’nin bir üretime hazır çözüme dönüştürülmesi için gereken işlemler yapılır. Bu aşamada, çıkış olarak tamamlanmış ve dağıtım ortamında doğrulanmış bir Power BI çözümü elde edilir. Çözümün 5. aşamada dağıtıma hazır olması gerekir. 4\. aşamadaki etkinlikler hakkında daha fazla bilgi edinmek için bkz. [Power BI’a geçirilecek içeriği oluşturma](powerbi-migration-create-validate-content.md).

### <a name="stage-5-deploy-support-and-monitor"></a>5\. aşama: Dağıtım, destek ve izleme

5\. aşama, yeni Power BI çözümünün üretime dağıtılmasına odaklanır. Bu aşamada, çıkış olarak iş kullanıcılarının etkin olarak kullandığı bir üretim çözümü elde edilir. Çevik bir metodoloji kullanılırken, gelecekteki bir yinelemeyle sunulacak bazı planlı geliştirmelerin olması kabul edilebilir. Power BI’a ilişkin güvenlik düzeyinize bağlı olarak (riskleri ve kullanıcılar için hizmet kesintisini en aza indirme gibi) aşamalı bir dağıtım yapabilirsiniz. Ya da, ilk olarak küçük bir pilot kullanıcı grubuna dağıtım yapabilirsiniz. Bu aşamada, destek ve izleme de önemlidir ve bunların sürekli olarak gerçekleştirilmesi gerekir. 5\. aşamadaki etkinlikler hakkında daha fazla bilgi edinmek için bkz. [Power BI’a geçiş yapma](powerbi-migration-deploy-support-monitor.md).

> [!TIP]
> Power BI geçişi makalelerine ilişkin bu seride ele alınan kavramların çoğu, standart bir Power BI uygulama projesi için de geçerlidir.

## <a name="consider-migration-reasons"></a>Geçiş nedenlerini değerlendirme

Verimli ve iyi durumda olan bir veri kültürü elde etme, çoğu kuruluşun temel amacıdır. Power BI, bu amaca ulaşmanızı kolaylaştıran harika bir araçtır. Power BI’a geçiş yapmaya ilişkin en sık rastlanan üç neden şunlardır:

- Self servis iş zekası kullanıcısı topluluğunu güçlendiren yeni özellikler sunarak **yönetilen self servis iş zekası olanağı tanıyın**. Power BI, bilgilere erişimi ve karar alma sürecini daha geniş kapsamlı olarak sunar ve bulunması güç olabilen uzman becerilere yönelik gereksinimi azaltır.
- Mevcut iş zekası araçlarının karşılamadığı gereksinimleri karşılamak, karmaşıklık düzeyini azaltmak, sahip olma maliyetini azaltmak ve/veya şu anda kullanımda olan birden fazla iş zekası aracını standartlaştırmak için **kurumsal iş zekasını daha verimli şekilde sunun**.
- Daha az kaynak, zaman ve çalışan ile daha fazla verimlilik elde etmek için **ekonomik baskıları giderin**.

## <a name="achieve-power-bi-migration-success"></a>Power BI geçişini başarıyla tamamlama

Her geçiş işlemi biraz farklıdır. Geçiş, kuruluşun yapısına, veri stratejilerine, veri yönetiminin olgunluk düzeyine ve kurumsal hedeflere bağlı olarak farklılık gösterebilir. Ancak, Power BI geçişini başarıyla tamamlayan tüm müşterilerin belirli uygulamaları gerçekleştirdiğini belirledik.

- **İdari destekleyici:** İşlemin başında bir idari destekleyici belirleyin. Bu rol için kuruluşta iş zekasını etkin olarak destekleyen ve geçişten olumlu bir değer elde edilmesi için kişisel çabalarda bulunan bir kişinin seçilmesi gerekir. Genelde, idari destekleyici Power BI ile ilgili sonuçlara ilişkin en yüksek yetkiye ve sorumluluğa sahip olur.
- **Eğitim, destek ve iletişim:** Bunun bir teknoloji girişiminden daha fazlası olduğunu unutmayın. Tüm iş zekası veya analiz projeleri insan teşebbüslü olduğundan kullanıcılara yönelik eğitime ve desteğe erken yatırım yapın. Ayrıca, yapılan tüm işlemleri ve bunların sebeplerini tüm paydaşlara açıkça bildiren ve gerçekçi beklentiler oluşturan bir iletişim planı oluşturun. Paydaşların görüşlerini almak için iletişim planınıza bir geri bildirim döngüsü ekleyin.
- **Hızla elde edilen kazançlar:** İlk olarak, somut iş değeri sunan ve baskı oluşturan değerli öğelere öncelik verin. Tüm raporları eski iş zekası platformunda olduğu gibi geçirmekten ziyade yeniden tasarlanan raporları işlerken raporun yanıtlamaya çalıştığı iş sorusuna ve uygulanacak eyleme odaklanın.
- **Modernleştirme ve iyileştirmeler:** Değişiklik yapmaya hevesli olun. Geçişler, geliştirme sağlamaya yönelik fırsatlar sunabilir. Örneğin, geçiş ile verilerin el ile hazırlanması gereksinimi ortadan kaldırılabilir veya tek bir rapor ile sınırlı tutulan iş kurallarının kapsamı genişletebilir. Uygun olan durumlarda mevcut çözümleri yeniden düzenlemeyi, modernleştirmeyi ve birleştirmeyi değerlendirin. Bu, birden fazla raporu tek bir raporda birleştirilme veya bir süredir kullanılmayan eski yapıtların ortadan kaldırılma gibi işlemleri içerebilir.
- **Sürekli öğrenme:** Sürekli olarak öğrenin ve uyum sağlarken aşamalı bir yaklaşım kullanmaya hazırlanın. Değeri hızla elde etmek için kısa ve yinelemeli döngülerle çalışın. Bilinmeyen riskini azaltmak, varsayımları doğrulamak ve yeni özellikler hakkında bilgi edinmek için küçük POC’ler tamamlamayı alışkanlık haline getirin. Power BI, aylık güncellenen bir bulut hizmeti olduğundan, geliştirmelerden haberdar olmak ve uygun olan yerlerde değişiklik yapmak önemlidir.
- **Değişime direnme:** Değişime karşı farklı düzeylerde direnme gösterilebileceğini unutmayın. Bazı kullanıcılar yeni bir aracı kullanmayı öğrenmek istemeyebilir. Farklı bir iş zekası aracında uzmanlaşmak için zaman harcayıp çaba göstermiş olan bazı çalışanlar bu değişim ile endişeye kapılabilir. Bu durum, özellikle merkezi olmayan kuruluşlarda şirket içi politik çalkantılara neden olabilir.
- **Kısıtlamalar:** Finansman, zaman tahminleri ve dahil olan herkesin rolü ve sorumlulukları gibi yönleri de kapsayan geçiş planını oluştururken gerçekçi olun.

## <a name="acknowledgments"></a>Teşekkürler

Bu makale serisi, [Coates Data Strategies](https://www.coatesdatastrategies.com/)’in sahibi olan Veri Platformu MVP’si Melissa Coates tarafından yazıldı. Bu seriye katkıda bulunan ve bunu gözden geçiren kişiler şunlardır: Marc Reguera, Venkatesh Titte, Patrick Baumgartner, Tamer Farag, Richard Tkachuk, Matthew Roche, Adam Saxton, Chris Webb, Mark Vaillancourt, Daniel Rubiolo, David Iseminger ve Peter Myers.

## <a name="next-steps"></a>Sonraki adımlar

[Bu Power BI geçişi serisinin sonraki makalesi](powerbi-migration-pre-migration-steps.md), Power BI’a geçiş yaparken uygulanan geçiş öncesi adımlara ilişkin bilgileri içerir.

Diğer faydalı kaynakları da inceleyebilirsiniz:

- [Microsoft’un BI dönüşümü](center-of-excellence-microsoft-business-intelligence-transformation.md)
- [Power BI kuruluş dağıtımı planlama teknik incelemesi](https://aka.ms/PBIEnterpriseDeploymentWP)
- [SSRS raporlarını Power BI’a geçirme](migrate-ssrs-reports-to-power-bi.md)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
- Önerileriniz mi var? [Power BI'ı geliştirmek için fikirlerinizi paylaşın](https://ideas.powerbi.com/)

Deneyimli Power BI iş ortakları, kuruluşunuzun başarıyla geçiş yapmasına yardımcı olabilir. Bir Power BI iş ortağından yardım almak için [Power BI iş ortağı portalını](https://powerbi.microsoft.com/partners/) ziyaret edin.
