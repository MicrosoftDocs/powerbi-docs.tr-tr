---
title: Microsoft’un BI dönüşümü
description: Microsoft'un iş konusunda karar almak için gerekli olan veri kültürünü sağlama konusunda başarıya nasıl ulaştığını öğrenin. Şirketin iş zekası stratejisi ve vizyonu hakkında bilgi edinin.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/19/2020
ms.author: v-pemyer
ms.openlocfilehash: 1b4f86a0e3316cc774b0f1562112f0d6e5b19a4f
ms.sourcegitcommit: f73ea4b9116ad186817ec5cc5d5f487d49cc0cb0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/20/2020
ms.locfileid: "88638716"
---
# <a name="microsofts-bi-transformation"></a>Microsoft’un BI dönüşümü

Bu makale, BT uzmanlarına ve BT yöneticilerine yöneliktir. Verilerimizi varlık olarak kullanmamızı sağlayan iş zekası stratejimiz ve vizyonumuz hakkında bilgi edineceksiniz. Ayrıca Power BI ile iş konusunda karar almak için gerekli olan veri kültürünü sağlama konusunda başarıya nasıl ulaştığımızı öğreneceksiniz.

Önce bazı arka plan bilgileri: Günümüzde yaşanan hızlı veri artışı, tüketicileri ve işletmeleri etkilemektedir. Yüksek veri yoğunluğunun yaşandığı bu ortamda başarılı olmak için çok miktarda veriyi kısa ve öz içgörülere dönüştürebilen analistlere ve yöneticilere ihtiyaç vardır. Microsoft’un iş zekası araçlarında yaşanan gelişmeler, Microsoft’un da kendi verilerini keşfetme ve şirketi etkileyecek doğru içgörülere ulaşma şeklini değiştirmiştir.

Peki şirketinizin verilerle çalışma şeklini tamamen değiştirmek için siz neler yapabilirsiniz? Bunu anlamanıza yardımcı olmak için Microsoft'un iş zekası dönüşüm yolculuğuna bir göz atalım.

## <a name="microsoft-journey"></a>Microsoft'un yolculuğu

Microsoft olarak birkaç yıl öncesine kadar kuruluş kültürümüz, verilerin ve içgörülerin tam sahipliğinin kişilere ait olmasını tavsiye ediyordu. Bu durum ayrıca işleri standart bir şekilde yapma konusunda güçlü bir kültürel dirençle karşı karşıya kalmamıza neden oldu. Bunun sonucunda kuruluş kültürü, raporlama ve analiz konusunda güçlüklere yol açtı. Özellikle şunların ortaya çıkmasına neden oldu:

- Tutarsız veri tanımları, hiyerarşiler, ölçümler ve Ana Performans Göstergeleri (KPI). Örneğin her ülkenin yeni gelirleri bildirme yöntemi farklıydı. Tutarlılık yoktu ve bu da çok fazla karışıklığa neden oluyordu.
- Analistler zamanının %75'ini veri toplama ve derlemeyle geçiriyordu.
- Raporların %78'i "ofis ortamında" oluşturuluyordu.
- 350'den fazla merkezi hale getirilmiş finans aracı ve sistemi vardı.
- Yılda yaklaşık 30 milyon ABD doları, "gölge uygulamalar" için harcanıyordu.

Bu zorluklar nedeniyle işleri daha iyi nasıl yönetebileceğimiz konusunda düşünmeye başladık. Finans ekiplerine ve diğer iç ekiplere, iş gözden geçirme sürecini dönüştürme konusunda yönetici desteği verildi ve bunun sonucunda tek gerçeklik kaynağı olarak birleştirilmiş bir iş zekası platformu oluşturuldu. (Makalenin ilerleyen bölümlerinde iş zekası platformumuz hakkında daha fazla bilgi vereceğiz.) Bu yenilikler, sonunda iş gözden geçirmelerinin yoğun tablo görünümünden işle ilgili temel konulara odaklanan daha basit ve daha çok içgörüye sahip görsellere dönüştürülmesini sağladı.

Bu başarılı sonuca nasıl ulaştık? BT tarafından yönetilen merkezi bir iş zekası ortamı sunmak ve bunu self servis iş zekası (SSBI) ile genişletmek bizi başarıya ulaştırdı. Bunu iki şekilde ifade ediyoruz: _çekirdekte disiplin_ ve _uç birimlerde esneklik_.

### <a name="discipline-at-the-core"></a>Çekirdekte disiplin

Çekirdekte disiplin, BT ekibinin tek bir ana veri kaynağı oluşturarak denetimi elinde tutmasını ifade eder. Standartlaştırılmış kurumsal iş zekası sunma ve tutarlı sınıflandırmaları tanımlama, bu disiplinin bir parçasıdır. Daha da önemlisi veri izinleri tek bir merkezden uygulanarak çalışanların yalnızca ihtiyaç duydukları verileri okuyabilmeleri sağlanır.

İlk olarak iş zekası dönüşümümüzün bir teknoloji sorunu olmadığını anladık. Başarıya ulaşmak için önce başarıyı tanımlamayı ve ardından bunu anahtar ölçümlere dönüştürmeyi öğrendik. Verilerimizde tanımladığımız tutarlılığa erişmenin ne kadar önemli olduğunu göz ardı etmemek gerekir.

Dönüşüm süreci tek seferde tamamlanmadı. Yaklaşık 30 KPI içeren yan kuruluş karnesinin sunulmasını önceliklendirdik. Ardından birkaç yıl içinde konu alanlarının sayısını ve derinliğini kademeli olarak genişletip daha karmaşık KPI hiyerarşilerimizi oluşturduk. Bugün bu hiyerarşiler sayesinde müşteri düzeyindeki daha düşük düzeyde bulunan KPI'leri şirket düzeyindeki daha yüksek düzeyde bulunan KPI'lere doğru izleyebiliyoruz. Toplam KPI sayımız 2000'in üzerinde ve bunların her biri, kuruluş hedefleri için geçerli olan önemli bir başarı ölçütü. Artık şirket genelindeki kurumsal raporlar ve SSBI çözümleri iyi şekilde tanımlanmış, tutarlı ve güvenli KPI'ler sunuyor.

### <a name="flexibility-at-the-edge"></a>Uç birimde esneklik

Çekirdeğin uç birimlerinde bulunan Finans, Satış ve Pazarlama ekiplerindeki analistlerimiz daha esnek ve daha çevik hale geldi. Artık verileri daha hızlı bir şekilde analiz edebiliyorlar. Bu senaryo normalde _yönetilen self servis iş zekası (SSBI)_ olarak adlandırılıyor. Artık yönetilen SSBI hizmetinin BT çalışanları ve analistler için _karşılıklı fayda_ sağladığını biliyoruz. Daha da önemlisi standartlaştırma, bilgi ve verilerle iş zekası çözümlerimizin yeniden kullanımı sayesinde iyileştirmeler elde ettik. Şirket olarak merkezi iş zekası ile yönetilen SSBI arasında doğru dengeyi kurarak daha fazla değer ve sinerji yakaladık.

### <a name="our-solution"></a>Çözümümüz

**Starlight**; finans, satış, pazarlama ve mühendislik departmanları için destek sunan iç veri birleştirme ve analiz platformumuza verdiğimiz ad. Görevi ise sağlam, paylaşılan ve ölçeklenebilir bir veri platformu sunmak. Tamamen finans ekibi tarafından geliştirilmiş olan bu platform, günümüzde de en güncel Microsoft ürünlerini kullanarak çalışmaya devam etmektedir.

**KPI Gölü** bir Azure Data Lake örneği değildir. Bu, Microsoft SQL Server Analysis Services hizmeti kullanılarak Azure IaaS platformunda barındırılan bir Starlight destekli tablosal iş zekası anlam modelidir. İş zekası anlam modeli model 100’den fazla iç kaynaktan alınan verileri sunar ve sayısız hiyerarşiyi ve KPI’yı tanımlar. Görevi; finans, pazarlama ve satış ekipleri arasında iş performansı raporlama ve analiz ekiplerine destek olmaktır. Bunu yaparak birleşik iş zekası anlam modelleri aracılığıyla ilgili kaynaklardan zamanında, doğru ve yüksek performanslı içgörüler elde eder.

Tablosal iş zekası anlam modeli, ilk dağıtıldığında anlık ve ölçülebilir avantajlar sunduğu için heyecanlı bir deneyim yaşatmıştı. İlk sürüm C+E finans ve pazarlama iş zekası platformlarını merkezi hale getirmişti. Ardından geçen altı yılın sonunda ek iş içgörüsü çözümlerini birleştirecek şekilde genişletildi. Günümüzde gelişmeye ve global ile ticari iş gözden geçirmelerine ek olarak standart raporlama ve SSBI konusunda destek sunmaya devam ediyor. Benimsenme oranı yayımlandığı zamandan bugüne kadar 5 kat artarak bizim de başlangıçtaki beklentilerimizin ötesine geçti.

Önemli avantajları aşağıda verilmiştir:

- Yan kuruluş karnesi, dünya geneli iş gözden geçirmeleri ve finans, pazarlama, satış raporları ve analiz süreçlerimizi destekliyor.
- Analistlerin verilerde gizli olan içgörüleri keşfetmesini sağlayan self servis analizleri destekliyor.
- Teşvik ödemesi, pazarlama ve operasyon analizi, satış performansı ölçümleri, üst düzey liderlik gözden geçirmeleri ve yıllık planlama süreci için raporlama ve analiz işlemlerinin gerçekleştirilmesini sağlıyor.
- _Tek bir gerçeklik kaynağından_ otomatik ve dinamik raporlama ile analiz sunuyor.

**KPI Gölü** harika bir başarı öyküsüdür. Genellikle müşterilerimize en son teknolojilerimizin verimli bir şekilde kullanılarak neler yapılabileceğine örnek olarak gösterilmektedir. Beklendiği üzere bu durum çoğunu etkilemektedir.

#### <a name="how-it-works"></a>Nasıl çalışır?

Starlight platformu; alma, işleme ve yayımlama sürecindeki veri akışını yönetir:

1. Zamanlanmış bir şekilde sağlam ve çevik veri tümleştirmesi gerçekleştirilerek 100'den fazla ham veri kaynağında bulunan veriler birleştirilir. Kaynak veri sistemleri arasında ilişkisel veritabanları, Azure Data Lake Storage ve Azure Synapse veritabanları bulunabilir. Konu alanları finans, pazarlama, satış ve mühendisliktir.
2. Hazırlanan veriler, ana veriler ve iş mantığı kullanılarak uyumlu hale getirilir ve zenginleştirilir. Ardından veri ambarı tablolarına yüklenir. Tablosal iş zekası anlam modeli yenilenir.
3. Şirketin analistleri, tablosal iş zekası anlam modelinden içgörü ve analiz sunmak için Excel ve Power BI’ı kullanır. Bu model ayrıca iş sahiplerinin kendi işleri için ölçüm tanımları oluşturmalarını sağlar. Gerektiğinde Azure IaaS ve yük dengeleme kullanılarak ölçeklendirme gerçekleştirilir.

## <a name="deliver-success"></a>Başarıya ulaşma

Herkesin kendisindeki verilerin gerçek olduğunu kabul etmek istemesi ironik bir durumdur. Ancak bu durum bazı kuruluşlar için oldukça önemlidir. Veriler ve içgörüler üzerinde tam sahiplik elde etmek isteyen kullanıcılar nedeniyle gerçeğin birden fazla sürümü söz konusu olabilir. Bu kuruluşlar için bu tür yönetilmeyen yaklaşımlar genellikle işletmeyi başarıya taşımaz.

Bu nedenle bir _Üstün Başarı Merkezi'ne (COE)_ sahip olmanız gerektiğini düşünüyoruz. COE, şirket genelindeki ölçümlerin, tanımların ve daha birçok sürecin tanımlanmasından sorumlu olan merkezi bir ekiptir. Ayrıca insanları, süreçleri ve teknoloji bileşenlerini kapsamlı bir iş yetkinliği ve becerisi kümesi haline getiren bir işletme işlevidir.

Elimizde, kapsamlı ve sağlam bir COE ekibinin değer sunma ve işletme başarısını en üst düzeye çıkarma konusunda kritik öneme sahip olduğunu gösteren birçok kanıt var. Değişim girişimleri, standart süreçler, roller, yönergeler, en iyi yöntemler, destek, eğitim ve çok daha fazlası buna dahil edilebilir.

Daha fazla bilgi edinmek için sizi bu COE dizisindeki makaleleri okumaya davet ediyoruz. Kuruluşunuzun başarıya ulaşmak için değişikliği nasıl yönetmesi gerektiğini keşfetmenize yardımcı olmak isteriz.

## <a name="next-steps"></a>Sonraki adımlar

Bu makale hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

- [Üstün Başarı Merkezi oluşturma](center-of-excellence-establish.md)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
- Önerileriniz mi var? [Power BI'ı geliştirmek için fikirlerinizi paylaşın](https://ideas.powerbi.com/)

[Bu dizinin bir sonraki makalesinde](center-of-excellence-establish.md) bir COE'nin Microsoft'un sahip olduğu verilerden içgörü elde etmesini sağlayacak standartlaştırılmış analiz ve veri platformu oluşturmasına nasıl yardımcı olduğunu öğrenebilirsiniz.

### <a name="professional-services"></a>Profesyonel hizmetler

Sertifikalı Power BI iş ortakları, kuruluşunuzun COE’yi başarıyla ayarlamasına yardımcı olabilir. İş ortakları, size uygun maliyetli eğitim veya veri denetimi hizmeti sunabilir. Bir Power BI iş ortağından yardım almak için [Power BI iş ortağı portalını](https://powerbi.microsoft.com/partners/) ziyaret edin.

Deneyimli danışmanlık iş ortaklarıyla da etkileşime geçebilirsiniz. Bu iş ortakları, Power BI’ı [incelemenize](https://appsource.microsoft.com/marketplace/consulting-services?product=power-bi&serviceType=assessment&country=ALL&region=ALL), [değerlendirmenize](https://appsource.microsoft.com/marketplace/consulting-services?product=power-bi&serviceType=proof-of-concept&country=ALL&region=ALL) veya [uygulamanıza](https://appsource.microsoft.com/marketplace/consulting-services?product=power-bi&serviceType=implementation&country=ALL&region=ALL&page=1) yardımcı olabilir.
