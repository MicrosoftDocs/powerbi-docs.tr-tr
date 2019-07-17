---
title: Power BI’da şablon uygulaması yazma ipuçları
description: İyi şablon uygulamaları hazırlamak için sorgular, veri modelleri, raporlar ve panolar yazmaya yönelik ipuçları
author: teddybercovitz
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 06/26/2019
ms.author: tebercov
ms.openlocfilehash: 5e34601c3ebacb3cfd8a4a5ddeb282756d0f700b
ms.sourcegitcommit: 1789815c87e306b1427a5838655d30d3b9ba1d29
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2019
ms.locfileid: "67791816"
---
# <a name="tips-for-authoring-template-apps-in-power-bi"></a>Power BI’da şablon uygulaması yazma ipuçları

Power BI’da [şablon uygulamanızı yazarken](service-template-apps-create.md), bu sürecin bir bölümü çalışma alanı oluşturma, test etme ve üretim lojistiğinden oluşur. Ama bu sürecin bir diğer önemli bölümünün de rapor ve pano yazma olduğu açıktır. Yazma sürecini dört ana bileşene ayırabiliriz. Bu bileşenler üzerinde çalışmak mümkün olan en iyi şablon uygulamasını oluşturmanıza yardımcı olur:

* **Sorgularla**, verilere [bağlanıp](desktop-connect-to-data.md) onları [dönüştürür](desktop-query-overview.md) ve [parametreleri](https://powerbi.microsoft.com/blog/deep-dive-into-query-parameters-and-power-bi-templates/) tanımlarsınız. 
* **Veri modelinde**, [ilişkileri](desktop-create-and-manage-relationships.md) ve [ölçüleri](desktop-measures.md) oluşturur, Soru-Cevap geliştirmeleri yaparsınız.  
* **[Rapor sayfaları](desktop-report-view.md)** verilerinize yönelik içgörüler sağlayan görseller ve filtreler içerir.  
* **[Panolar](consumer/end-user-dashboards.md)** ve [kutucuklar](service-dashboard-create.md) sağlanan içgörülere genel bir bakış sunar.
* Örnek veriler, uygulamanızın yüklenmesinin hemen ardından bulunabilmesini sağlar.

Belirtilen bileşenler birer Power BI özelliği olarak tanıdık gelebilir. Şablon uygulaması oluştururken, her bileşende dikkate alınacak başka noktalar da vardır. Diğer ayrıntılar için aşağıdaki bölümlere bakın.

<a name="queries"></a>

## <a name="queries"></a>Sorgular
Şablon uygulamaları için, Power BI Desktop'ta geliştirilen sorgular veri kaynağınızla bağlantı kurmak ve verileri içeri aktarmak için kullanılır. Bu sorgular, tutarlı bir şema döndürmek için gereklidir ve Zamanlanmış Veri yenilemede desteklenir (DirectQuery desteklenmez).

### <a name="connect-to-your-api"></a>API'nize bağlanma
Öncelikle, sorgularınızı oluşturmaya başlamak için Power BI Desktop'tan API'nize bağlanmanız gerekir.

API'nize bağlanmak için, Power BI Desktop'ta sunulan Veri Bağlayıcılarını kullanabilirsiniz. Web Veri Bağlayıcısını (Veri Al -> Web) kullanarak Rest API'nize bağlanabilir veya OData akışınıza bağlanmak için (Veri Al -> OData akışı) OData bağlayıcısını kullanabilirsiniz.

> [!NOTE]
> Şablon uygulamaları şu anda özel bağlayıcıları desteklememektedir, bazı bağlayıcı kullanımı durumlarında riski azaltmak için Odatafeed Auth 2.0 kullanarak arama yapmanız veya bağlayıcınız için sertifikasyon isteğinde bulunmanız önerilir. Bağlayıcı geliştirme ve sertifika alma ayrıntıları için bkz. [Veri Bağlayıcıları belgeleri](https://aka.ms/DataConnectors).

### <a name="consider-the-source"></a>Kaynakla ilgili önemli noktalar
Sorgular, veri modeline dahil edilen verileri tanımlar. Sisteminizin boyutuna bağlı olarak bu sorgular, müşterilerinizin iş senaryonuza uygun, kullanışlı boyutlarla çalışmasını sağlamak için filtreler de içermelidir.

Power BI şablon uygulamaları aynı anda birden çok sorguyu farklı kullanıcılar için eşzamanlı olarak yürütebilir.  Azaltma ve eşzamanlılık stratejinizi önceden planlayın ve şablon uygulamanızı hataya dayanıklı hale getirme ile ilgili sorularınızı bize yöneltin.

### <a name="schema-enforcement"></a>Şema uygulama
Sorgularınızın sisteminizdeki değişikliklere dayanıklı olmasını sağlayın; şemadaki değişiklikler veri modelini bozabilir. Kaynağın bazı sorgular için null veya eksik şema sonucu döndürme olasılığına karşı boş bir tablo veya anlamlı bir özel hata iletisi döndürmeyi göz önünde bulundurun.

### <a name="parameters"></a>Parametreler
Power BI Desktop'taki [parametreler](https://powerbi.microsoft.com/blog/deep-dive-into-query-parameters-and-power-bi-templates/), kullanıcılarınızın, kullanıcı tarafından alınan verileri özelleştiren giriş değerleri sağlamasına olanak sağlar. Ayrıntılı sorgular veya raporlar oluşturmaya zaman harcadıktan sonra yeniden çalışma yapmak zorunda kalmamak için parametreler hakkında önceden düşünün.

> [!NOTE]
> Şablon uygulamaları Any ve Binary dışındaki tüm parametreleri destekler.
>

### <a name="additional-query-tips"></a>Ek sorgu ipuçları

* Tüm sütunların düzgün bir şekilde yazıldığından emin olun.
* Sütunlarda bilgilendirici adlar bulunmalıdır (bkz. [Soru-Cevap](#qa)).  
* Paylaşılan mantık için işlevleri veya sorguları kullanabilirsiniz.  
* Gizlilik düzeyleri şu anda hizmette desteklenmez. Gizlilik düzeyleriyle ilgili bir istemle karşılaşırsanız, göreli yolları kullanacak şekilde sorguyu yeniden yazmanız gerekebilir.  

## <a name="data-models"></a>Veri modelleri

İyi tanımlanmış bir veri modeli, müşterilerinizin şablon uygulamasıyla kolay ve sezgisel bir etkileşim kurmasına olanak sağlar. Veri modelini Power BI Desktop'ta oluşturun.

> [!NOTE]
> Basit modellemenin (yazma ve sütun adları) büyük bölümünü [sorgularda](#queries) gerçekleştirmelisiniz.

### <a name="qa"></a>Soru-Cevap
Modelleme, Soru-Cevap'ın müşterileriniz için döndürdüğü sonuçların ne kadar iyi olacağını da etkiler. Yaygın olarak kullanılan sütunlar için eş anlamlı sözcükler eklediğinizden ve [sorgularda](#queries) sütunlarınızı düzgün adlandırdığınızdan emin olun.

### <a name="additional-data-model-tips"></a>Ek veri modeli ipuçları

Şunları yapmayı unutmayın:

* Tüm değer sütunlarına biçimlendirme uygulayın. Sorguya türleri uygulayın.  
* Tüm ölçülerinize biçimlendirme uygulayın.
* Varsayılan özetlemeyi ayarlayın. Özellikle, uygun olduğunda (örneğin, benzersiz değerler söz konusu olduğunda) varsayılan özetlemenin "Özetleme" olarak ayarlanması gerekir.  
* Uygun olduğunda veri kategorisini ayarlayın.  
* Gerekirse ilişkileri ayarlayın.  

## <a name="reports"></a>Raporlar
Rapor sayfaları, şablon uygulamanızda bulunan verilere ilişkin ek içgörüler sağlar. Şablon uygulamanızda üzerinde durulmaya çalışılan, işle ilgili önemli sorulara cevap vermek için rapor sayfalarını kullanın. Power BI Desktop'ı kullanarak raporu oluşturun.


### <a name="additional-report-tips"></a>Ek rapor ipuçları

* Çapraz filtreleme için sayfa başına birden fazla görsel kullanın.  
* Görselleri dikkatli bir şekilde (çakışma olmayacak şekilde) hizalayın.  
* Sayfa düzeni "4:3" veya"16:9" moduna ayarlanır.  
* Sunulan tüm toplamaların (ortalamalar, benzersiz değerler) mantıklı olması gerekir.  
* Dilimlemenin mantıksal sonuçlar vermesi gerekir.  
* Logonun en azından en üstteki raporda görünmesi gerekir.  
* Öğeler, mümkün olduğunca istemcinin renk düzeninde olmalıdır.  

<a name="dashboard"></a>

## <a name="dashboards"></a>Panolar
Pano, müşterileriniz için şablon uygulamanızla etkileşime yönelik temel noktadır. Mevcut içeriklere, özellikle de iş senaryonuza yönelik önemli ölçümlere ilişkin bir genel bakış içermelidir.

Şablon uygulamanıza pano oluşturmak için, Veri Al > Dosyalar yolunu izleyerek PBIX dosyanızı karşıya yükleyin veya doğrudan Power BI Desktop'ta yayımlayın.


### <a name="additional-dashboard-tips"></a>Ek pano ipuçları

* Panonuzdaki kutucukların tutarlı olması için, sabitleme işlemi sırasında aynı temayı gözetin.  
* Tüketicilerin içerik paketinin nereden geldiğini anlamasını sağlamak için temaya bir logo sabitleyin.  
* Çoğu ekran çözünürlüğü için önerilen düzen, 5-6 küçük kutucuk genişliğindedir.  
* Tüm pano kutucuklarının uygun başlıklara/alt başlıklara sahip olması gerekir.  
* Farklı senaryolar için panoda dikey veya yatay gruplandırmalar oluşturmayı tercih edebilirsiniz.  

## <a name="sample-data"></a>Örnek veriler
Şablon uygulamaları, uygulama oluşturma işlemi sırasında çalışma alanındaki önbellek verilerini uygulamanın bir parçası olarak sarmalar:

* Verilere bağlanmadan önce yükleyicinin uygulama işlevlerini ve amacını anlamasını sağlar.
* Yükleyiciyi uygulama özelliklerini daha iyi araştırmaya yönlendiren bir deneyim oluşturarak uygulama veri kümelerine bağlamayı sağlar.

Uygulamayı oluşturmadan önce kaliteli örnek verilere sahip olmanızı öneririz. Uygulama rapor ve panolarının verilerle dolu olduğundan emin olun.

## <a name="publishing-on-appsource"></a>AppSource’da yayımlama
Şablon uygulamaları AppSource’da yayımlanabilir; uygulamanızı AppSource’a göndermeden önce şu yönergeleri izleyin:

* Şablon uygulamalarını, yükleyicinin uygulamanın neler yapabileceğini anlamasına yardımcı olacak ilgi çekici örnek verilerle oluşturduğunuzdan emin olun (boş rapor ve panolar onaylanmaz).
Şablon uygulamaları yalnızca örnek veriler içeren uygulamaları destekler; statik uygulama onay kutusunu işaretlediğinizden emin olun. [Daha fazla bilgi](https://docs.microsoft.com/power-bi/service-template-apps-create#create-the-test-template-app)
* Genelde yalnızca değerli işlevleri olan uygulamalar AppSource'da genel kullanım için onaylanabilir. Yalnızca örnek veri içeriği olan uygulamaların rehberlik veya istatistiksel değeri olmalıdır.
* Doğrulama ekibinin izleyeceği, verilere bağlanmak için gereken kimlik bilgilerini ve parametreleri de içeren yönergeler ekleyin.
* Uygulamanın, Power BI'da ve CPP teklifinizde bir Uygulama simgesi içermesi gerekir. [Daha fazla bilgi](https://docs.microsoft.com/power-bi/service-template-apps-create#create-the-test-template-app)
* Yapılandırılmış giriş sayfası. [Daha fazla bilgi](https://docs.microsoft.com/power-bi/service-template-apps-create#create-the-test-template-app)
* [Power BI Uygulama teklifi](https://docs.microsoft.com/azure/marketplace/cloud-partner-portal/power-bi/cpp-power-bi-offer) belgelerine uyduğunuzdan emin olun.
* Uygulamanızda bir pano varsa boş olmadığından emin olun.
* Uygulamayı göndermeden önce uygulama bağlantısını kullanarak yükleyin; veri kümesini bağlayabildiğinizden ve uygulama deneyiminin planladığınız gibi olduğundan emin olun.
* Şablon uygulaması çalışma alanına bpix’i yüklemeden önce gereksiz tüm bağlantıları kaldırdığınızdan emin olun.
* Kullanıcılarınız üzerinde en fazla etkiyi yaratmak ve dağıtım onayı almak için Power BI'ın [Raporlar ve görseller için en iyi tasarım yöntemlerini](https://docs.microsoft.com/power-bi/visuals/power-bi-visualization-best-practices) izleyin.

## <a name="known-limitations"></a>Bilinen sınırlamalar

| Öne çıkan özelliği | Bilinen Sınırlama |
|---------|---------|
|İçerik:  Veri kümeleri   | Tam olarak bir veri kümesi bulunmalıdır. Yalnızca Power BI Desktop’ta oluşturulan veri kümelerine (.pbix dosyaları) izin verilir. <br>Desteklenmez: Diğer şablon uygulamalarından veri kümeleri, çalışma alanları arası veri kümeleri, sayfalandırılmış raporlar (.rdl dosyaları), Excel çalışma kitapları |
|İçerik: Panolar | Gerçek zamanlı kutucuklara izin verilmez (diğer bir deyişle, veri kümelerini gönderme veya akış sağlama desteği yok) |
|İçerik: Veri akışları | Desteklenmez: Veri akışları |
|Dosyaların içeriği | Yalnızca PBIX dosyalarına izin verilir. <br>Desteklenmez: .rdl dosyaları (sayfalandırılmış raporlar), Excel çalışma kitapları   |
| Veri kaynakları | Bulutta Zamanlanmış Veri yenileme için desteklenen veri kaynaklarına izin verilir. <br>Desteklenmez: <li> DirectQuery</li><li>Canlı bağlantılar (Azure AS yok)</li> <li>Şirket içi veri kaynakları (kişisel ve kurumsal ağ geçitleri desteklenmez)</li> <li>Gerçek zamanlı (gönderim veri kümesi desteği yok)</li> <li>Bileşik modeller</li></ul> |
| Veri kümesi: çalışma alanları arası | Çalışma alanları arası veri kümelerine izin verilmez  |
| Sorgu parametreleri | Desteklenmez: "Any" veya "Binary" türündeki parametreler veri kümesi için yenileme işlemini engeller |
| Özel görseller | Yalnızca genel kullanıma açık özel görseller desteklenir. [Özel kuruluş görselleri](power-bi-custom-visuals-organization.md) desteklenmez |

## <a name="next-steps"></a>Sonraki adımlar

[Power BI şablon uygulamaları nedir?](service-template-apps-overview.md)
