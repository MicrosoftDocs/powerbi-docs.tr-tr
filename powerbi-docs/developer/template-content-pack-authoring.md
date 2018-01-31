---
title: "Power BI'da şablon içerik paketi yazma"
description: "Şablon İçerik Paketi Yazma"
services: powerbi
documentationcenter: 
author: markingmyname
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
ms.date: 10/09/2017
ms.author: maghan
ms.openlocfilehash: 9b8de53534c94ad995e2d953cfc6994b93915bd8
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2018
---
# <a name="author-template-content-packs-in-power-bi"></a>Power BI'da şablon içerik paketi yazma
Şablon içerik paketleri yazmak için Power BI Desktop ve PowerBI.com kullanılır. İçerik paketiniz dört bileşenden oluşur:

* Verilere [bağlanmanıza](../desktop-connect-to-data.md), verileri [dönüştürmenize](../desktop-query-overview.md) ve [parametreleri](https://powerbi.microsoft.com/blog/deep-dive-into-query-parameters-and-power-bi-templates/) tanımlamanıza olanak sağlayan sorgular  
* [İlişkiler](../desktop-create-and-manage-relationships.md), [ölçüler](../desktop-measures.md) ve Soru-Cevap iyileştirmeleri oluşturmak için kullanılan veri modeli  
* Verilerinize yönelik öngörüler sağlamaya ilişkin görselleri ve filtreleri içeren rapor [sayfaları](../desktop-report-view.md)  
* Sağlanan öngörülere ilişkin bir genel bakış sunan [pano](../service-dashboards.md) ve [kutucuklar](../service-dashboard-create.md)  

Belirtilen bileşenler birer Power BI özelliği olarak tanıdık gelebilir. İçerik paketi oluşturma söz konusuysa bunlardan her biri için göz önünde bulundurulması gereken daha fazla unsur vardır.

<a name="queries"></a>

## <a name="queries"></a>Sorgular
Şablon içerik paketleri için, Power BI Desktop'ta geliştirilen sorgular veri kaynağınızla bağlantı kurmak ve verileri içeri aktarmak için kullanılır. Sorgular, tutarlı bir şema döndürmek için gereklidir ve Zamanlanmış Veri yenilemede desteklenir (doğrudan sorgu desteklenmez).

Şablon içerik paketleri, içerik paketi başına yalnızca tek bir veri kaynağını destekler, bu nedenle sorgularınızı dikkatli bir şekilde tanımlamanız gerekir. Tek bir veri kaynağı, aynı kimlik doğrulamasını gerektiren bir kaynak olarak tanımlanır. Tüm çağrıların aynı API uç noktasına yönelik olması ve aynı kimlik doğrulamasını kullanması koşuluyla farklı sorgularda birden çok API çağrısı gerçekleştirebilirsiniz. Power BI içerik paketleri, farklı kimlik doğrulamalarını gerektiren birden fazla kaynağı desteklemez.

### <a name="connect-to-your-api"></a>API'nize bağlanma
Öncelikle, sorgularınızı oluşturmaya başlamak üzere Power BI Destktop'tan API'nize bağlanmanız gerekir.

API'nize bağlanmak için, Power BI Desktop'ta kullanıma hazır olarak sunulan Veri Bağlayıcıları kullanabilirsiniz. Web Veri Bağlayıcısını (Veri Al -> Web) kullanarak Rest API'nize bağlanabilir veya OData akışınıza bağlanmak için (Veri Al -> OData akışı) OData bağlayıcısını kullanabilirsiniz. Bu bağlayıcıların, yalnızca API'nizde Temel Kimlik Doğrulaması'nın desteklenmesi halinde kullanıma hazır olarak çalışacağını lütfen unutmayın.

> [!NOTE]
> API'niz OAuth 2.0 veya Web API Key gibi başka bir kimlik doğrulaması türünü kullanıyorsa Power BI Desktop'ın API'nize başarılı bir şekilde bağlanmasına ve API'nizde kimlik doğrulamasına olanak sağlamak üzere kendi Veri Bağlayıcınızı geliştirmeniz gerekir. [Buradaki](https://aka.ms/DataConnectors) Veri Bağlayıcılar belgelerine göz atarak İçerik Paketiniz için kendi Veri Bağlayıcınızı geliştirme ile ilgili ayrıntılara ulaşabilirsiniz. 
> 
> 

### <a name="consider-the-source"></a>Kaynakla ilgili önemli noktalar
Sorgular, veri modeline dahil edilecek verileri tanımlar. Sisteminizin boyutuna bağlı olarak bu sorgular, müşterilerinizin iş senaryonuza uygun, kullanışlı boyutlarla çalışmasını sağlamak için filtreler de içermelidir.

Power BI içerik paketleri aynı anda birden çok sorguyu farklı kullanıcılar için eşzamanlı olarak yürütebilir.  Azaltma ve eşzamanlılık stratejinizi önceden planlayın ve içerik paketinizi hataya dayanıklı hale getirme ile ilgili sorularınızı bize yöneltin.

### <a name="schema-enforcement"></a>Şema uygulama
Sorgularınızın sisteminizdeki değişikliklere dayanıklı olmasını sağlayın; şemadaki değişiklikler veri modelini bozabilir. Kaynağın bazı sorgular için null/eksik şema sonucu döndürme olasılığına karşı boş bir tablo döndürebilir veya kullanıcınız için anlam ifade eden özel hata iletileri görüntülemeyi tercih edebilirsiniz.

### <a name="parameters"></a>Parametreler
Power BI Desktop'taki [parametreler](https://powerbi.microsoft.com/blog/deep-dive-into-query-parameters-and-power-bi-templates/), kullanıcılarınızın, kullanıcı tarafından alınan verileri özelleştiren giriş değerleri sağlamasına olanak sağlar. Ayrıntılı sorgular veya raporlar oluşturmaya zaman harcadıktan sonra yeniden çalışma yapmak zorunda kalmamak için parametreler hakkında önceden düşünün.

> [!NOTE]
> Şablon içerik paketleri şu anda yalnızca metin parametrelerini desteklemektedir. Diğer parametre türleri geliştirme sırasında kullanılabilir ancak [test](template-content-pack-testing.md#templates) kısmında kullanıcılar tarafından girilen tüm değerlerin değişmez değer olması gerekir.
> 
> 

### <a name="additional-query-tips"></a>Ek sorgu ipuçları
* Tüm sütunların düzgün bir şekilde yazıldığından emin olun  
* Sütunlarda bilgilendirici adlar bulunmalıdır (bkz. Soru-Cevap)  
* Paylaşılan mantık için işlevleri veya sorguları kullanabilirsiniz  
* Gizlilik düzeyleri şu anda hizmette desteklenmemektedir. Gizlilik düzeyleri hakkında bir istem alırsanız ilgili yolları kullanmak için sorguyu yeniden oluşturmanız gerekir  

## <a name="data-model"></a>Veri Modeli
İyi tanımlanmış bir veri modeli, müşterilerinizin içerik paketiyle kolay ve sezgisel bir şekilde etkileşime geçmesine olanak sağlar. Power BI Desktop'ta veri modelini oluşturun.

> [!NOTE]
> Basit modellemenin (yazma ve sütun adları) büyük bir kısmı [sorgularda](#queries) gerçekleştirilmelidir.
> 
> 

### <a name="qa"></a>Soru-Cevap
Modelleme, Soru-Cevap'ın müşterileriniz için döndürdüğü sonuçların ne kadar iyi olduğunu da etkiler. Yaygın olarak kullanılan sütunlar için eş anlamlı sözcükler eklediğinizden ve sütunlarınızın [sorgularda](#queries) düzgün bir şekilde adlandırıldığından emin olun.

### <a name="additional-data-model-tips"></a>Ek veri modeli ipuçları
* Tüm değer sütunlarında biçimlendirme uygulanmış olmalıdır
    >[!NOTE]
    >Türlerin sorguya dahil edilmesi gerekir.  
* Tüm ölçülerde biçimlendirme uygulanmış olmalıdır  
* Varsayılan Özetleme belirlenmelidir. Uygun olduğunda (örneğin, benzersiz değerler söz konusu olduğunda), varsayılan özetlemenin "Özetleme" olarak belirlenmesi gerekir  
* Uygun olduğunda, Veri Kategorisi'nin belirlenmiş olması gerekir  
* İlişkiler gereken şekilde ayarlanmalıdır  

## <a name="reports"></a>Raporlar
Rapor sayfaları, içerik paketinizde bulunan verilere ilişkin ek öngörüler sağlar. İçerik paketinizde üzerinde durulmaya çalışılan, işle ilgili önemli sorulara cevap vermek için rapor sayfalarını kullanın. Power BI Desktop'ı kullanarak raporu oluşturun.

> [!NOTE]
> Bir içerik paketinde yalnızca tek bir rapor bulunabilir. Senaryonuzun belirli bölümlerini ele almak için farklı sayfalardan yararlanabilirsiniz.
> 
> 

### <a name="additional-report-tips"></a>Ek rapor ipuçları
* Çapraz filtreleme için sayfa başına birden fazla görsel kullanın  
* Görselleri dikkatli bir şekilde (çakışma olmayacak şekilde) hizalayın  
* Sayfa düzeninin "4:3" veya"16:9" modunda olması gerekir  
* Sunulan tüm toplamaların (ortalamalar, benzersiz değerler) mantıklı olması gerekir  
* Dilimlemenin mantıksal sonuçlar vermesi gerekir  
* Logonun en azından üstteki raporda görünmesi gerekir  
* Öğeler, mümkün olduğu ölçüde istemcinin renk düzeninde olmalıdır  

<a name="dashboard"></a>

## <a name="dashboard"></a>Pano
Pano, müşterileriniz için içerik paketinizle etkileşime yönelik temel noktadır. Mevcut içeriklere, özellikle de iş senaryonuza yönelik önemli ölçümlere ilişkin bir genel bakış içermelidir.

Şablon içerik paketiniz için bir pano oluşturmak üzere, Veri Al > Dosyalar yolunu izleyerek PBIX dosyanızı karşıya yükleyin veya doğrudan Power BI Desktop'ta yayımlayın.

> [!NOTE]
> Şablon içerik paketleri şu anda içerik paketi başına tek bir rapor ve veri kümesi gerektirir. Birden çok rapordan/veri kümesinden elde edilen içerikleri içerik paketinde kullanılan panoya sabitlemeyin.
> 
> 

### <a name="additional-dashboard-tips"></a>Ek pano ipuçları
* Panonuzdaki kutucukların tutarlı olması için, sabitleme işlemi sırasında aynı temayı gözetin  
* Tüketicilerin içerik paketinin nereden geldiğini anlamasını sağlamak için temaya bir logo sabitleyin  
* Çoğu ekran çözünürlüğü için önerilen düzen, 5-6 küçük kutucuk genişliğindedir  
* Tüm pano kutucuklarının uygun başlıklara/alt başlıklara sahip olması gerekir  
* Farklı senaryolar için panoda dikey veya yatay gruplandırmalar oluşturmayı tercih edebilirsiniz  

<a name="restrictions"></a>

## <a name="summary-of-restrictions"></a>Kısıtlamalara ilişkin özet
Yukarıdaki bölümlerde belirtildiği gibi, şu anda içerik paketleri bazı kısıtlamalara tabidir:  

| Destekleniyor | *Desteklenmiyor* |
| --- | --- |
| PBI Desktop'ta oluşturulan veri kümeleri |*Başka içerik paketlerindeki veya Excel dosyaları gibi girişlerdeki veri kümeleri* |
| Bulutta Zamanlanmış Veri yenileme için desteklenen veri kaynağı |*Doğrudan sorgular veya şirket içi bağlantılar desteklenmez* |
| Tutarlı bir şema veya hatalar döndüren (uygun olduğunda) sorgular |*Dinamik veya özel şemalar* |
| Veri kümesi başına bir veri kaynağı |*Karma gibi çoklu veri kaynakları veya çoklu veri kaynağı olarak algılanan URL'ler* |
| Metin türündeki parametreler |*Diğer parametre türleri (tarih gibi) veya "izin verilen değerler listesi"* |
| Tek bir pano, rapor ve veri kümesi |*Birden çok pano, rapor veya veri kümesi* |

## <a name="next-step"></a>Sonraki adım
[İçerik Paketi Testi ve Gönderim](template-content-pack-testing.md)

