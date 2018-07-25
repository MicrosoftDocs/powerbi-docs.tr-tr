---
title: Power BI hizmeti içerik paketi programına genel bakış
description: İçerik Paketi Sertifika Programı
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 02/20/2018
ms.author: maggies
ms.openlocfilehash: 4a5d124ffd213c54d628ff15e32ece18e56913eb
ms.sourcegitcommit: 3a287ae4ab16d1e76caed651bd8ae1a1738831cd
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/19/2018
ms.locfileid: "39157560"
---
# <a name="overview-of-the-power-bi-service-content-pack-program"></a>Power BI hizmeti içerik paketi programına genel bakış
İçerik paketleri, kullanıcıların bir kaynaktan hemen öngörü edinmesine olanak sağlayan bir hazır içerik dizisidir. İçerik paketleri genellikle belirli bir iş senaryosuna odaklanarak bir rol, etki alanı veya iş akışına yönelik öngörüler sağlar.

ISV'ler, müşterilerin kendi hesaplarıyla bağlanmasına ve örnek oluşturmasına olanak sağlayan şablon içerik paketleri oluşturabilir. Etki alanı uzmanları olarak, işletme kullanıcıları tarafından kolayca kullanılabilecek şekilde verilerin kilidini açabilirler. İçerik paketleri, müşterilerinize raporlama altyapısına büyük yatırımlar yapmadan geçici izleme ve çözümleme olanağı sunar.

ISV tarafından oluşturulan bu şablon içerik paketleri, Power BI içerik paketi galerisi (app.powerbi.com/getdata/services) ve Microsoft AppSource (appsource.microsoft.com) üzerinden genel kullanıma sunulmak üzere Power BI ekibine gönderilebilir. Genel kullanıma açık içerik paketi deneyimine ilişkin bir örneğe [buradan](template-content-pack-experience.md) ulaşabilirsiniz.

## <a name="overview"></a>Genel Bakış
Bir şablon içerik paketi geliştirmeye ve göndermeye yönelik genel işlem birden çok adımda tamamlanır.

 ![İşlem](media/service-content-pack-overview/developer-content-pack-overview.png)

1. [Gereksinimleri gözden geçirin](#requirements) ve yerine getirdiğinizden emin olun
2. Power BI Desktop'ta [içerik oluşturun](template-content-pack-authoring.md#queries)
3. Power BI.com'da [bir pano oluşturun](template-content-pack-authoring.md#dashboard)
4. Kuruluşunuzda [içerik paketini kendiniz test edin](template-content-pack-testing.md)
5. İçeriği yayımlanması için Power BI'a [gönderin](template-content-pack-testing.md#submission)

<a name="requirements"></a>

## <a name="requirements"></a>Gereksinimler
Bir içerik paketi oluşturmak ve paketi Power BI hizmetinde ve AppSource'ta yayımlanmak üzere göndermek için aşağıdaki gereksinimleri karşılamanız gerekir:

* İşletme kullanıcıları tarafından kullanılan bir SaaS uygulamanız olmalıdır.
* SaaS uygulamanız, Power BI'da görselleştirilebilen kullanıcı verileri içermelidir.
* SaaS uygulamanız, genel İnternet üzerinden erişilebilen bir API'ye sahip olmalıdır. İdeal olarak API, API veya bir OData akışı temelli bir REST'tir. Power BI içerik paketleri; Temel Kimlik Doğrulaması, OAuth 2.0 ve API Anahtarı gibi birden çok kimlik doğrulaması türünü destekler. 
* SaaS uygulamanızın içerik paketi yayımlamak için onaylanmış olması gerekir. İsteklerinizi pbiservicesapps@microsoft.com adresine gönderin. Her bir gönderi uygunluğa ve kullanım beklentisine göre değerlendirilmektedir. 
* İş ortağı sözleşmesi imzalanmalıdır. Bu, paketi [gönderme adımında](template-content-pack-testing.md#submission) yapılır.

Teknik gereksinimler hakkında daha fazla ayrıntı için lütfen [yazma](template-content-pack-authoring.md) bölümünü inceleyin.

## <a name="business-scenario"></a>İş senaryosu
İçerik paketleri, belirli bir iş senaryosuna odaklanan öngörüler ve ölçümler sağlar. Hedef kitlenizi ve içerik paketinden elde edecekleri faydayı anlamak, kullanıcılarınızın, sunduğunuz içeriği başarıyla kullanmalarını sağlamanızı kolaylaştırır.

### <a name="tips"></a>İpuçları
* Hedef kitlenizi ve gerçekleştirmeye çalıştıkları görevi tanımlayın  
* Belirli bir zaman aralığına (son 90 gün) veya son N sonuca odaklanın  
* Yalnızca senaryonuzla ilgili tabloları/sütunları içeri aktarın  
* Ayrı benzersiz senaryolar için birden fazla içerik paketi sunmayı düşünün  

## <a name="frequently-asked-questions"></a>Sık sorulan sorular
**Üçüncü taraf olarak, sahip olmadığım bir SaaS uygulaması için Power BI Hizmeti içerik paketi oluşturabilir miyim?**

İçerik paketi hizmette yayımlanmadan önce SaaS uygulamasının sahibiyle bir iş ortağı sözleşmesi imzalanması gerekmektedir. Bir üçüncü taraf olarak, SaaS uygulama sahibiyle iş ortağı sözleşmesinin imzalanması konusunda kolaylık sağlamanız gerekir.

**Hizmetim için bir genel geliştirici API'sine sahip değilim. Yine de verileri doğrudan veri depolama alanından çeken bir Power BI hizmeti içerik paketi oluşturabilir miyim?**

Hayır, Power BI hizmeti içerik paketleri için genel İnternet üzerinden erişilebilir bir geliştirici API'si gereklidir.

**Hangi API'ler hizmet içerik paketleri tarafından desteklenir ve bunlar hangi kimlik doğrulaması türleri ile çalışabilir?**

Power BI hizmeti içerik paketleri herhangi bir REST API'sini veya OData akışını destekler. Power BI; Temel Kimlik Doğrulaması, OAuth 2.0 ve Web API Anahtarı'nı içeren birden çok kimlik doğrulaması türüyle çalışabilir. [Yazma](template-content-pack-authoring.md#dashboard) makalesinde teknik gereksinimler ile ilgili daha fazla ayrıntı bulabilirsiniz.

**Power BI'da yayımlanan bir içerik paketim var. Bunu nasıl güncelleştirebilirim?**

Yayımlanan içerik paketleri ayda bir kez güncelleştirilebilir. Geçerli ayın son gününden önce [pbiservicesapps@microsoft.com](mailto:pbiservicesapps@microsoft.com) adresine gönderilen güncelleştirme istekleri bir sonraki ayın ilk haftasında yayımlanır.

**Hizmet İçerik Paketleri hakkında başka sorularım da var. Sizinle nasıl iletişim kurabilirim?**

[pbiservicesapps@microsoft.com](mailto:pbiservicesapps@microsoft.com) adresinden e-posta ile sorularınızı bize gönderebilirsiniz

## <a name="support"></a>Destek
Geliştirme sırasında destek almak için lütfen [https://powerbi.microsoft.com/support](https://powerbi.microsoft.com/support) adresine gidin. Bu sayfa etkin şekilde izlenmekte ve yönetilmektedir. Müşteri olayları hızla ilgili ekibe aktarılmaktadır.

## <a name="next-step"></a>Sonraki adım
[Yazma](template-content-pack-authoring.md)