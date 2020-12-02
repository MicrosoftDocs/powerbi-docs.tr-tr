---
title: Üstün Başarı Merkezi oluşturma
description: Üstün Başarı Merkezi'nin doğru işletim modeli, paydaş etkileşimi, paylaşılan ve ayrılmış yatırımlar sayesinde Microsoft'un sahip olduğu verilerden içgörü elde etmesini sağlayacak standartlaştırılmış analiz ve veri platformu oluşturmasına nasıl yardımcı olduğunu öğrenin.
author: peter-myers
ms.author: v-pemyer
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi
ms.topic: conceptual
ms.date: 08/19/2020
ms.openlocfilehash: 90de33f85c0ede28b14e651414c311e4986a2172
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96394578"
---
# <a name="establish-a-center-of-excellence"></a>Üstün Başarı Merkezi oluşturma

Bu makale, BT uzmanlarına ve BT yöneticilerine yöneliktir. Kuruluşunuzda iş zekası ve analiz için Üstün Başarı Merkezi'ni (COE) nasıl oluşturacağınızı ve Microsoft'un bunu nasıl yaptığını öğreneceksiniz.

Bazıları COE'nin sadece bir yardım masası olduğunu düşünebilir ancak bu durum gerçeği yansıtmamaktadır.

Genellikle iş zekası ve analiz COE ekibi, bir iş zekası platformu kurma ve bakımını yapma konusunda sorumlu olan uzmanların bir araya gelmesiyle oluşturulmuş bir ekiptir. Bu ekip ayrıca tek bir gerçeklik kaynağı oluşturmaktan ve içgörüleri ortaya çıkarıp bunlara ulaşma süresini kısaltmak için şirket genelinde tutarlı ölçümler tanımlamaktan da sorumludur. Ancak COE, geniş kapsamlı bir terimdir. Bu nedenle farklı şekillerde uygulanıp yönetilebilir ve yapısıyla kapsamı kuruluşa göre değişiklik gösterebilir. Temelde her zaman doğru kişilere doğru zamanda veri ve içgörü becerisi sunan sağlam bir platform oluşturmayı hedefler. Ayrıca yaygınlaştırma, eğitim ve destek konusunda teşvik sunar. Microsoft'ta _[çekirdekte disiplin](center-of-excellence-microsoft-business-intelligence-transformation.md#discipline-at-the-core)_ olarak tanımlanır ve hem iş zekası platformu hem de tek gerçeklik kaynağı olarak sunulur.

Daha büyük kuruluşlarda birden fazla COE bulunabilir ve çekirdek COE, genellikle departman düzeyinde uygu COE'ler kullanılarak _genişletilir_. Bu örnekte uydu COE, sınıflandırmalar ve tanımlar konusunda bilgi sahibi olan ve çekirdekteki verileri _departmanları için_ anlamlı hale getirecek şekilde dönüştürmeyi bilen uzmanlardan oluşan bir gruptur. Departman analistlerine çekirdekteki verileri kullanma izni verilir ve bu analistler verilere güvenerek kendi raporlarında kullanır. Bu kişiler, dikkatle hazırlanmış olan temel boyutlara, olgulara ve iş mantığına dayanan çözümler oluşturur. Ayrıca bunları daha küçük ve departmana özgü veri kümeleri ve iş mantığıyla genişletebilirler. Daha da önemlisi, uydu COE'lerin bağlantısı asla kesilmez ve bu örnekler yalıtılmış bir şekilde çalışmaz. Microsoft'ta uydu COE'ler _[uç birimde esnekliği](center-of-excellence-microsoft-business-intelligence-transformation.md#flexibility-at-the-edge)_ teşvik eder.

Bu genişletilmiş senaryonun başarılı olması için departmanların _elini taşın altına koymaları gerekir_. Başka bir deyişle departmanlar, çekirdek COE'ye finansal yatırım yapmalıdır. Bu şekilde "haklarını alamama" veya gereksinimlerine gerekli önceliğin verilmemesi gibi bir endişe taşımazlar.

Bu senaryoyu desteklemek için çekirdek COE'nin, fon sağlayan departmanın gereksinimlerini karşılayacak şekilde ölçeklendirilmesi gerekir. Birden çok veri kümesi eklendikten sonra ölçek kümelerinin sağladığı maliyet avantajı kullanılabilir. Microsoft'ta merkezden çalışmanın daha ekonomik olduğu ve sonuçlara daha hızlı bir şekilde ulaşmayı sağladığı kısa süre içinde ortaya çıkmıştır. Yeni konu alanları eklendikçe tasarruf miktarı artmış ve platform genelinde fayda ve katkı sağlayarak temel alınan veri kültürümüzü güçlendirmiştir.

Şu örneğe göz atalım: İş zekası platformumuz finans, satış ve pazarlama departmanları için çekirdek boyutlar, olgular ve iş mantığı sunuyor. Ayrıca yüzlerce Ana Performans Göstergesi (KPI) de tanımlıyor. Power Platform kullanan bir analistin liderlik panosu hazırlaması gerekiyor. Gelir ve işlem hatları gibi KPI'lerden bazıları doğrudan iş zekası platformundan geliyor. Ancak diğerleri, işletmenin gereksinimleri nedeniyle daha ayrıntılı durumda. Power BI'a özgü bir özellik olan veri akışlarının kullanıcı benimsemesi konusunda bir KPI'ye ihtiyaç duyuluyor. Bu durumda analist, çekirdek iş zekası platformu verilerini departman verileriyle tümleştirmek için bir Power BI [bileşik modeli](composite-model-guidance.md) oluşturuyor. Ardından departmana özgü KPI'leri tanımlamak için gerekli iş mantığını ekliyor. Son olarak şirket genelindeki COE kaynaklarının yerel bilgiler ve verilerle desteklenmiş sürümünü kullanan yeni modelden faydalanarak liderlik panosunu oluşturuyor.

Burada önemli olan, çekirdek ile uydu COE'ler arasındaki sorumluluk paylaşımının departman analistlerinin bir veri platformunu yönetmek yerine yeni çözümler oluşturmaya odaklanmasını sağlamasıdır. Bazen uydu COE'ler ile çekirdek COE arasında karşılıklı fayda sağlayan bir ilişki dahi bulunabilir. Örneğin bir uydu COE tarafından tanımlanan yeni ölçümler (departman için faydalı olduğu bilinen) şirketin tamamı için faydalı çekirdek ölçümler olarak kullanılabilir ve çekirdek COE üzerinden sunulup desteklenebilir.

## <a name="bi-platform"></a>İş zekası platformu

Kuruluşunuzda COE yerine iş zekası ekibi veya grubu gibi farklı bir ad kullanılıyor olabilir. Zaten önemli olan adı değil yaptıklarıdır. Bunun için oluşturulmuş bir ekibiniz yoksa temel iş zekası uzmanlarınızı bir araya getirerek iş zekası platformunuzu oluşturmanız önerilir.

Microsoft'ta COE, İş Zekası Platformu olarak bilinir. Finans, satış ve pazarlama gibi şirketin farklı bölümlerini temsil eden birçok paydaş gruba sahiptir. [Paylaşılan özellikleri](#shared-capabilities) ve [ayrılmış teslimleri](#dedicated-deliveries) çalıştıracak şekilde organize edilmiştir.

:::image type="content" source="media/center-of-excellence-establish/business-intelligence-platform-operating-model.png" alt-text="Aşağıdaki bölümlerde anlatılan paylaşılan özellikleri ve ayrılmış teslimleri gösteren diyagram.":::

### <a name="shared-capabilities"></a>Paylaşılan özellikler

İş zekası platformunu kurmak ve çalıştırmak için paylaşılan özelliklere ihtiyaç duyulur. Bu özellikler, platformu fonlayan tüm paydaş grupları destekler. Bunlar aşağıdaki ekiplerden oluşur:

- **Çekirdek platformu mühendisliği:** İş zekası platformunu mühendis gözüyle tasarladık. Bu, veri alımı, verilerin zenginleştirilmek üzere işlenmesi ve analistler tarafından kullanılacak veri modelleri şeklinde sağlanmasına yönelik destek sunan bir çerçeve kümesidir. Çekirdek iş zekası platformunun özellikleri ile ilgili teknik tasarım ve uygulama aşamalarından da mühendisler sorumludur. Örneğin veri işlem hatlarını onlar tasarlayıp uygular.
- **Altyapı ve barındırma:** Tüm Azure hizmetlerinin sağlanması ve yönetilmesi, BT mühendislerinin sorumluluğundadır.
- **Destek ve operasyon:** Bu ekip, platformu çalışır halde tutar. Destek ekibi, veri izinleri gibi kullanıcı gereksinimleriyle ilgilenir. Operasyon ekibi platformun kesintisiz bir şekilde çalışmasını sağlayarak Hizmet Düzeyi Sözleşmelerinin (SLA) karşılanmasını sağlar, gecikme veya hata durumlarını bildirir.
- **Sürüm yönetimi:** Değişiklikler, teknik program yöneticileri (PM) tarafından yayımlanır. Değişiklikler, platform çerçevesinde yapılan güncelleştirmelerden iş zekası anlam modelleri için yapılan değişiklik isteklerine kadar çok çeşitli olabilir. Değişikliklerin herhangi bir hataya yol açmadığından emin olan son savunma hattını oluştururlar.

### <a name="dedicated-deliveries"></a>Ayrılmış teslimler

Her paydaş grubu için ayrılmış bir teslim ekibi vardır. Bu ekipler genellikle bir veri mühendisi, bir analiz mühendisi ve bir teknik PM'den oluşur ve tamamı paydaş grubu tarafından fonlanır.

## <a name="bi-team-roles"></a>İş zekası ekibindeki roller

Microsoft'un iş zekası platformu, uzmanlardan oluşan ölçeklenebilir ekipler tarafından işletilmektedir. Ekipler, ayrılmış ve paylaşılan kaynaklara göre belirlenir. Sahip olduğumuz güncel roller şunlardır:

- **Program yöneticileri:** PM'ler ayrılmış kaynaklardır. İş zekası ekibi ile paydaşlar arasında birincil iletişim noktası olarak görev yaparlar. Görevleri, paydaşların iş gereksinimlerini teknik belirtimlere dönüştürmektir. Ayrıca paydaş teslimlerinin önceliklendirmesini de onlar yapar.
- **Veritabanı liderleri:** Bunlar yeni veri kümelerinin merkezi veri ambarına eklenmesinden sorumlu olan ayrılmış kaynaklardır. Bir veri kümesini eklemek için uyumlu boyutların ayarlanması, iş mantığının ve özel özniteliklerin eklenmesi, standart adların belirlenmesi ve biçimlendirme yapılması gerekebilir.
- **Analiz liderleri:** İş zekası anlam modellerinin tasarlanmasından ve geliştirilmesinden sorumlu ayrılmış kaynaklardır. Standart adlandırma ve biçimlendirme kullanarak tutarlı bir mimari elde etmeye çalışırlar. Performans iyileştirmesi, görevlerinin önemli bir parçasıdır.
- **Operasyon ve altyapı:** Bunlar işleri ve veri işlem hatlarını yönetmekten sorumlu olan paylaşılan kaynaklardır. Ayrıca Azure aboneliklerini, Power BI kapasitelerini, sanal makineleri ve veri ağ geçitlerini yönetme sorumlulukları da vardır.
- **Destek:** Belge yazma, eğitim düzenleme, iş zekası anlam modeli değişikliklerini iletme ve kullanıcı sorularını yanıtlamadan sorumlu paylaşılan kaynaklardır.

## <a name="governance-and-compliance"></a>İdare ve uyum

PM liderleri her paydaş grubu için programlar arası idare ve gözetim sağlar. Temel amacı, yapılan BT yatırımlarının iş değerini artırdığından ve riskleri azalttığından emin olmaktır. İlerleme durumunu gözden geçirmek ve önemli girişimleri onaylamak için düzenli aralıklarla yönlendirme komitesi toplantıları düzenlenir.

## <a name="grow-your-own-community"></a>Kendi topluluğunuzu oluşturma

Şunları yaparak kuruluşunuzda kendi topluluğunuzu oluşturun ve bu topluluğu büyütün:

- Düzenli “Mesai Saatleri” etkinlikleri düzenleyerek iş zekası ekibine zaman ayırın ve topluluk üyelerine soru sorma, öneride bulunma, fikir paylaşma ve şikayet bildirme olanağı tanıyın.
- Destek sağlamak ve topluluk üyelerini soru sormaya ve gönderilen soruları yanıtlamaya teşvik etmek için bir Teams kanalı oluşturma.
- Resmi olmayan kullanıcı gruplarını yönetip yükseltin ve kullanıcıları katılım göstermeye ve fikir paylaşmaya teşvik edin.
- Belirli ürünlere ve iş zekası platformuna yönelik daha fazla resmi eğitim etkinliği gerçekleştirme. Ücretsiz kurs seti olarak sunulan ve ilk kez Power BI kullanan çalışanlara hizmeti tanıtan [Power BI Dashboard in a Day](https://powerbi.microsoft.com/diad/)’i çalışanlara sunun.

## <a name="next-steps"></a>Sonraki adımlar

Bu makale hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

- [COE’de iş zekası çözümü mimarisi](center-of-excellence-business-intelligence-solution-architecture.md)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
- Önerileriniz mi var? [Power BI'ı geliştirmek için fikirlerinizi paylaşın](https://ideas.powerbi.com/)

[Bu serinin sonraki makalesinde](center-of-excellence-business-intelligence-solution-architecture.md), COE’deki iş zekası çözüm mimarisi ve kullanılan farklı teknolojiler hakkında bilgi edineceksiniz.

### <a name="professional-services"></a>Profesyonel hizmetler

Sertifikalı Power BI iş ortakları, kuruluşunuzun COE’yi başarıyla ayarlamasına yardımcı olabilir. İş ortakları, size uygun maliyetli eğitim veya veri denetimi hizmeti sunabilir. Bir Power BI iş ortağından yardım almak için [Power BI iş ortağı portalını](https://powerbi.microsoft.com/partners/) ziyaret edin.

Deneyimli danışmanlık iş ortaklarıyla da etkileşime geçebilirsiniz. Bu iş ortakları, Power BI’ı [incelemenize](https://appsource.microsoft.com/marketplace/consulting-services?product=power-bi&serviceType=assessment&country=ALL&region=ALL), [değerlendirmenize](https://appsource.microsoft.com/marketplace/consulting-services?product=power-bi&serviceType=proof-of-concept&country=ALL&region=ALL) veya [uygulamanıza](https://appsource.microsoft.com/marketplace/consulting-services?product=power-bi&serviceType=implementation&country=ALL&region=ALL&page=1) yardımcı olabilir.
