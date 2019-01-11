---
title: Power BI Embedded hakkında sık sorulan sorular
description: Power BI Embedded hakkında sık sorulan sorular ve cevaplar listesini inceleyin.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 12/20/2018
ms.openlocfilehash: 3971651caf9be7e754f4232ffec8b4e4dbfdfe6d
ms.sourcegitcommit: 750f0bfab02af24c8c72e6e9bbdd876e4a7399de
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/04/2019
ms.locfileid: "54008431"
---
# <a name="frequently-asked-questions-about-power-bi-embedded"></a>Power BI Embedded hakkında sık sorulan sorular

* Başka sorularınız varsa [Power BI Topluluğu'na sorun](http://community.powerbi.com/).
* Sorununuz hâlâ çözülmedi mi? [Power BI destek sayfasını](https://powerbi.microsoft.com/support/) ziyaret edin.

## <a name="general"></a>Genel

### <a name="what-is-power-bi-embedded"></a>Power BI Embedded nedir?

Microsoft Power BI Embedded (PBIE) uygulama geliştiricilerin, kendi veri görselleştirmelerini ve kontrollerini sıfırdan oluşturmak için zaman ve para harcamadan nefes kesen, tam etkileşimli raporları uygulamalarına ekleyebilmelerini sağlar.

### <a name="who-is-the-target-audience-for-power-bi-embedded"></a>Power BI Embedded kimler içindir?

Kendi uygulamalarını yapan, bağımsız yazılım satıcıları (ISV'ler) olarak bilinen yazılım şirketleri ve geliştiriciler içindir.

### <a name="how-is-power-bi-embedded-different-from-power-bi-the-service"></a>Power BI Embedded hangi açıdan Power BI hizmetinden farklıdır?

Power BI Embedded, kendi uygulamalarını oluşturan ve sıfırdan bir analiz çözümü yaratmadan müşterilerinin karar almasını kolaylaştırmak üzere görsel öğeler eklemek isteyen geliştiriciler veya ISV'ler için tasarlanmıştır. Katıştırılmış analiz, iş kullanıcılarının iş verilerine erişebilmesini ve uygulama içerisinde bu verileri kullanarak öngörüler oluşturmak üzere sorgulama yapabilmesini sağlar.

Power BI, kuruluşlara en kritik iş verilerini tek bir görünümde sunan hizmet olarak yazılım analiz çözümüdür.

### <a name="what-is-the-difference-between-power-bi-premium-and-power-bi-embedded"></a>Power BI Premium ve Power BI Embedded arasındaki fark nedir?

Power BI Premium, kuruluşu, iş ortaklarını, müşterilerini ve sağlayıcılarını tek bir görünümde sunan eksiksiz bir İş Zekası çözümü isteyen kuruluşlar için kapasiteye göre tasarlanmıştır. Power BI Premium kuruluşların karar almasına yardımcı olur. Power BI Premium, bir SaaS ürünüdür ve kullanıcıların Power BI portal, mobil uygulama ile ve şirket içinde geliştirilen uygulamalar ile içeriği kullanabilmesini sağlar.

Power BI Embedded, uygulama oluşturan ve bu uygulamalara görseller eklemek isteyen geliştiriciler veya ISV'lere yöneliktir. Power BI Embedded, uygulama geliştiricilerine yönelik olduğundan ve kuruluş içindekiler veya dışındakiler dahil olmak üzere tüm uygulama kullanıcıları Power BI Embedded kapsamında depolanan içerikleri kullanabildiğinden Power BI Embedded müşterilerinizin karar almasına yardımcı olur. Power BI Embedded kapsamındaki içerik, tek tıklamayla Web'de veya SharePoint'te yayımlanarak paylaşılamaz ve SSRS raporlarını desteklemez.

### <a name="what-is-the-microsoft-recommendation-for-when-a-customer-should-buy-power-bi-premium-vs-power-bi-embedded"></a>Microsoft bir müşterinin hangi durumlarda Power BI Premium ve hangi durumlarda Power BI Embedded satın almasını önerir?

Microsoft, kuruluşların kurumsal sınıf, self servis bulut İş Zekası çözümü olarak Power BI Premium satın almasını ve ISV'lerin bulut destekli katıştırılmış analiz bileşenleri olarak Power BI Embedded satın almasını önerir. Ancak, müşterilerin satın alabileceği ürünlere ilişkin herhangi bir sınırlama yoktur.

Bir ISV (tipik olarak büyük), kuruluşunda önceden paketlenmiş Power BI hizmetinin ek avantajlarından yararlanmak ve uygulamalarına eklemek üzere P SKU kullanmak isteyebilir. Bazı kuruluşlar kullanmaya karar verebilir. Yalnızca iş uygulamaları oluşturmak ve bunlara analiz eklemek istediklerinde ve önceden paketlenmiş Power BI hizmetini kullanmak istemediklerinde Azure'da A SKU'lar kullanabilir.

### <a name="how-many-embed-tokens-can-i-create"></a>Kaç tane ekleme belirteci oluşturabilirim?

PRO lisansına sahip ekleme belirteçleri, geliştirmeye testlerine yöneliktir; bu nedenle, bir Power BI ana hesabının oluşturabileceği ekleme belirteçlerinin sayısı sınırlıdır. Üretim ortamında ekleme yapmak için [kapasite satın almanız](#technical) gerekir. Kapasite satın alındıktan sonra, oluşturabileceğiniz ekleme belirteçlerinin sayısıyla ilgili bir sınır yoktur. Geçerli eklenmiş kullanımı yüzde cinsinden gösteren kullanım değerini denetlemek için [Kullanılabilir Özellikler](https://docs.microsoft.com/rest/api/power-bi/availablefeatures) bölümüne gidin.

## <a name="technical"></a>Teknik

### <a name="what-is-the-difference-between-the-a-skus-in-azure-and-the-em-skus-in-office-365"></a>Azure’da A SKU ile Office 365’te EM SKU arasındaki fark nedir?

PowerBI.com bir Hizmet olarak Yazılım teklifinde sosyal iş birliği, e-posta aboneliği ve benzeri pek çok özelliği içeren kurumsal bir çözümdür

Power BI Embedded ise bir Hizmet olarak Platform teklifinde katıştırılmış analiz çözümü oluşturmak üzere geliştiriciler tarafından kullanılabilen bir dizi API'dir. Katıştırılmış analiz senaryosunda PowerBI.com, ISV'lerin ve geliştiricilerin analiz çözümü içeriklerini ve kiracı düzeyi ayarlarını yönetmesine yardımcı olmak üzere kullanılmalıdır.

Her bir seçenek ile kullanabileceğiniz farklılıklara ilişkin kısmi bir liste sunulmaktadır.

| Öne çıkan özelliği | Power BI Embedded | Power BI Premium Kapasitesi | Power BI Premium Kapasitesi |
|----------------------------------------------------------------------------------|-------------------|---------------------------|---------------------------|
|   | (A SKU'lar) | (EM SKU'lar) | (P SKU'lar) |
| Power BI Uygulaması çalışma alanlarından yapıtları ekleme | Azure kapasitesi | Office 365 kapasitesi | Office 365 kapasitesi |
| Katıştırılmış uygulamada Power BI raporlarını kullanma | Evet | Evet | Evet |
| Power BI raporlarını SharePoint'te kullanma | Hayır | Evet | Evet |
| Power BI raporlarını Dynamics'te kullanma | Hayır | Evet | Evet |
| Power BI raporlarını Teams'de kullanma (mobil uygulama hariç) | Hayır | Evet | Evet |
| ÜCRETSİZ Power BI lisansıyla içeriklere Powerbi.com ve Power BI mobilden erişme | Hayır | Hayır | Evet |
| MS Office uygulamalarına eklenmiş ÜCRETSİZ Power BI lisansıyla içeriklere erişme | Hayır | Evet | Evet |

### <a name="power-bi-now-offers-three-skus-for-embedding-a-skus-em-skus-and-p-skus-which-one-should-i-purchase-for-my-scenario"></a>Power BI artık ekleme için üç SKU sunar: A SKU, EM SKU ve P SKU. Benim durumumda hangisini satın almalıyım?

|  |A SKU (Power BI Embedded)  |EM SKU (Power BI Premium)  |P SKU (Power BI Premium)  |
|---------|---------|---------|---------|
|Satın alma  |Azure portalı |Office |Office |
|Kullanım örnekleri | Kendi uygulamanıza içerik ekleme | <li> Kendi uygulamanıza içerik ekleme <br><br></br> <li> MS Office uygulamalarına içerik ekleme: <br> - [SharePoint](https://powerbi.microsoft.com/blog/integrate-power-bi-reports-in-sharepoint-online/) <br> - [Teams (mobil uygulama hariç)](https://powerbi.microsoft.com/blog/power-bi-teams-up-with-microsoft-teams/) <br> - [Dynamics 365](https://docs.microsoft.com/dynamics365/customer-engagement/basics/add-edit-power-bi-visualizations-dashboard) | <li> Kendi uygulamanıza içerik ekleme <br><br></br> <li> MS Office uygulamalarına içerik ekleme: <br> - [SharePoint](https://powerbi.microsoft.com/blog/integrate-power-bi-reports-in-sharepoint-online/) <br> - [Teams (mobil uygulama hariç)](https://powerbi.microsoft.com/blog/power-bi-teams-up-with-microsoft-teams/) <br> - [Dynamics 365](https://docs.microsoft.com/dynamics365/customer-engagement/basics/add-edit-power-bi-visualizations-dashboard) <br><br></br> <li> [Power BI hizmeti](https://powerbi.microsoft.com/en-us/) aracılığıyla Power BI kullanıcılarıyla içerik paylaşma  |
|Faturalama |Saatlik |Aylık |Aylık |
|Taahhüt  |Taahhütsüz |Yıllık  |Aylık/Yıllık |
|Ayrım |Tam esneklik; Azure portalında veya API'ler ile kaynaklar duraklatılabilir/sürdürülebilir, ölçek artırılabilir/azaltılabilir  |SharePoint Online ve Microsoft Teams'de içerik eklemek için kullanılabilir (mobil uygulama hariç) |Uygulamalarda katıştırma birleştirilebilir ve Power BI Hizmeti aynı kapasitede kullanılabilir |

### <a name="what-are-the-prerequisites-to-create-a-pbie-capacity-in-azure"></a>Azure’da PBIE kapasitesi oluşturmanın önkoşulları nelerdir?

* Kuruluş dizininizde oturum açmanız gerekir (MSA hesapları desteklenmez).
* Power BI kiracısına sahip olmanız gerekir; diğer bir deyişle, dizininizde en az bir kullanıcının Power BI’ye kaydolmuş olması gerekir. 
* Kuruluş dizininizde bir Azure aboneliğinizin olması gerekir.

### <a name="how-can-i-monitor-power-bi-embedded-capacity-consumption"></a>Power BI Embedded kapasite tüketimini nasıl izleyebilirim?

* [Power BI Yönetim portalını](../service-admin-portal.md#power-bi-embedded) kullanarak.

* Power BI’daki [ölçüm uygulamasını](https://review.docs.microsoft.com/power-bi/service-admin-premium-monitor-capacity) indirerek.

* [Azure tanılama günlüğüne kaydetmeyi](azure-pbie-diag-logs.md) kullanarak.

### <a name="will-my-capacity-scale-automatically-to-adjust-to-the-consumption-of-my-app"></a>Kapasitem, uygulamamın kullanımına göre otomatik olarak ölçekleme sağlayacak mı?

Şu anda otomatik ölçekleme olanağı olmasa da tüm API'leri kullanarak dilediğiniz zaman ölçekleme yapabilirsiniz.

### <a name="why-creatingscalingresuming-a-capacity-results-in-putting-the-capacity-into-a-suspended-state"></a>Kapasite oluşturma/ölçeklendirme/serbest bırakma işlemi neden kapasitenin askıya alınma durumuna geçmesine neden oluyor?

Kapasite sağlama (ölçeklendirme/serbert bırakma/oluşturma) işlemi başarısız olabilir. Sağlama çağrısını yapan kişi, Ayrıntıları Alma API'sini kullanarak kapasitenin ProvisioningState değerini denetlemelidir: [Kapasiteler - Ayrıntıları Alma](https://docs.microsoft.com/rest/api/power-bi-embedded/capacities/getdetails).

### <a name="why-can-i-only-create-pbie-in-a-specific-region"></a>PBIE'yi neden yalnızca belirli bir bölgede oluşturabiliyorum?

PBIE kapasitelerini yalnızca PBI kiracı bölgenizde oluşturabilirsiniz.

### <a name="how-can-i-find-what-is-my-pbi-tenant-region"></a>PBI kiracı bölgemin ne olduğunu nasıl bulabilirim?

PBI Kiracı bölgenizin ne olduğunu anlamak için PBI portalını kullanabilirsiniz.

[https://app.powerbi.com/](https://app.powerbi.com/) > ? > Power BI Hakkında

![Power BI Hakkında](media/embedded-faq/about-01.png)
![Kiracı bölgesi](media/embedded-faq/tenant-location-01.png)

### <a name="what-is-supported-with-the-cloud-solution-provider-csp-channel"></a>Bulut Çözümü Sağlayıcısı (CSP) kanalıyla desteklenen özellikler nelerdir?

* CSP abonelik türüyle kiracınız için PBIE oluşturabilirsiniz
* İş ortağı hesabı müşteri kiracısında oturum açabilir ve müşteri kiracısı için PBIE satın alabilir. Power BI kapasite yöneticisi olarak müşteri kiracısı kullanıcısını belirtin

### <a name="why-do-i-get-an-unsupported-account-message"></a>Neden desteklenmeyen hesap iletisi alıyorum?

Power BI için kuruluş hesabıyla kaydolmanız gerekir. MSA (Microsoft hesabı) kullanarak Power BI'a kaydolma denemesi desteklenmez.

### <a name="can-i-use-apis-to-create--manage-azure-capacities"></a>Azure kapasitelerini oluşturmak ve yönetmek için API'leri kullanabilir miyim?

Evet, PBIE kaynaklarını oluşturmak ve yönetmek için kullanabileceğiniz Powershell cmdlet'leri ve Azure Resource Manager API'leri vardır.

* Rest API'leri - https://docs.microsoft.com/rest/api/power-bi-embedded/
* PowerShell cmdlet'leri - https://docs.microsoft.com/powershell/module/azurerm.powerbiembedded/

### <a name="what-is-the-pbi-embedded-dedicated-capacity-role-in-a-pbi-embedded-solution"></a>PBI Embedded çözümünde PBI Embedded adanmış kapasite rolü nedir?

[Çözümünüzü üretime yükseltmek](https://docs.microsoft.com/power-bi/developer/embedding-content#step-3-promote-your-solution-to-production) için Power BI içeriğinin (uygulamanızda kullandığınız uygulama çalışma alanı) bir Power BI Embedded (A SKU) kapasitesine atanmasına ihtiyacınız vardır.

### <a name="what-are-the-azure-regions-pbi-embedded-is-available"></a>PBI Embedded çözümünde hangi Azure bölgeleri kullanılabilir?

[PAM](https://ecosystemmanager.azurewebsites.net/home) (EcoManager) - bkz. Ürün kullanılabilirlik yöneticisi

Kullanılabilir bölgeler (16 - Power BI ile aynı bölgeler)

* ABD (6) - Doğu ABD, Doğu ABD 2, Orta Kuzey ABD, Orta Güney ABD, Batı ABD, Batı ABD 2
* Avrupa (2) - Kuzey Avrupa, Batı Avrupa
* Asya Pasifik (2) - Güneydoğu Asya, Doğu Asya
* Brezilya (1) - Brezilya Güney
* Japonya (1) - Japonya Doğu
* Avustralya (1) - Avustralya Güneydoğu
* Hindistan (1) - Batı Hindistan
* Kanada (1) - Kanada Orta
* Birleşik Krallık (1) - UK Güney

### <a name="what-is-the-authentication-model-for-power-bi-embedded"></a>Power BI Embedded kimlik doğrulama modeli nedir?

Power BI Embedded, Power BI'da uygulama kimliğini doğrulayarak ana kullanıcının (belirli bir Power BI Pro lisanslı kullanıcısı) kimliğini doğrulamak için Azure AD'den yararlanmaya devam edecektir.

Uygulama kullanıcılarının kimliklerini doğrulama ve yetkilendirme işlemleri, ISV tarafından gerçekleştirilecektir ve ISV, uygulamaları için kendi kimlik doğrulama modelini uygulayabilir.

Zaten bir Azure AD kiracınız varsa mevcut dizininizi kullanabilir veya katıştırılmış uygulama içeriğinizin güvenliği için yeni bir Azure AD kiracısı oluşturabilirsiniz.

Bir AAD belirteci almak için Azure Active Directory Kimlik Doğrulama Kitaplıkları - https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries içinden birini kullanabilirsiniz. Birden fazla platformda kullanılabilen istemci kitaplıkları vardır.

### <a name="my-application-already-uses-aad-for-user-authentication-how-can-we-use-this-identity-when-authenticating-to-power-bi-in-an-user-owns-data-scenario"></a>Uygulamam zaten Kullanıcı Kimlik Doğrulaması için AAD kullanır. "Verilerin Kullanıcıya Ait" olduğu bir senaryoda Power BI'da kimlik doğrulaması yaparken bu Kimliği nasıl kullanabiliriz?

Bu standart bir başkası adına OAuth akışıdır (https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios#web-application-to-web-api)) Uygulama Power BI hizmetine izin gerektirecek şekilde (gerekli kapsamlarla) yapılandırılmalıdır ve uygulamanıza kullanıcı belirteciniz olduğunda, kullanıcı erişim belirtecini kullanarak doğrudan ADAL API AcquireTokenAsync'e çağrı yapar ve kaynak kimliği olarak Power BI kaynak URL'sini belirtirsiniz. Aşağıda, bunun nasıl yapılabileceğini gösteren kod parçacığına bakın:

```csharp
var context = new AD.AuthenticationContext(authorityUrl);
var userAssertion = new AD.UserAssertion(userAccessToken);
var clientAssertion = new AD.ClientAssertionCertificate(MyAppId, MyAppCertificate)
var authenticationResult = await context.AcquireTokenAsync(resourceId, clientAssertion, userAssertion);
```

### <a name="how-is-power-bi-embedded-different-from-other-azure-services"></a>Power BI Embedded hangi açıdan diğer Azure hizmetlerinden farklıdır?

ISV/geliştiricinin, Azure'da Power BI Embedded'ı satın almadan önce bir Power BI hesabı olmalıdır. Power BI Embedded dağıtım bölgeniz, Power BI hesabınıza göre belirlenir. Azure'da Power BI Embedded kaynağınızı yöneterek:

* Ölçeği artırın/azaltın
* Kapasite yöneticileri ekleyin
* Hizmeti duraklatın/sürdürün

Power BI Embedded kapasitenize çalışma alanları atamak/çalışma alanının atamasını kaldırmak için PowerBI.com'u kullanın.

### <a name="what-deploy-regions-are-supported"></a>Hangi dağıtım bölgeleri desteklenir?

Avustralya Güneydoğu, Batı ABD, Batı ABD 2, Batı Avrupa, Birleşik Krallık Güney, Brezilya Güney, Doğu ABD 2, Güneydoğu Asya, Hindistan Batı, Japonya Doğu, Kuzey Avrupa, Kuzey Orta ABD, Orta Güney ABD, Orta Kanada.

### <a name="what-type-of-content-pack-data-can-be-embedded"></a>Ne tür içerik paketi verileri eklenebilir?

İçerik paketi veri kümelerinden oluşturulan **panolar** ve **kutucuklar** *eklenemez*, ancak bir içerik paketi veri kümesinden oluşturulan **raporlar** *eklenebilir*.

### <a name="what-is-the-difference-between-using-rls-vs-javascript-filters"></a>RLS ile JavaScript filtrelerini kullanmanın ne farkı vardır?

RLS ile JavaScript filtrelerinden hangisinin ne zaman kullanılacağı hakkında hep bir karışıklık vardır çünkü bir yöntem belirli bir kullanıcının neleri görebileceğini denetlerken diğeri kullanıcının görünümünü en iyi duruma getirmeye odaklanır.

RLS’de, ISV geliştiricisi model oluşturma ve ekleme belirteci oluşturmanın bir parçası olarak veri filtrelemesini denetler. Son kullanıcı yalnızca ISV’nin görmesine izin verdiği kadarını görür. Bu durumda kullanıcı filtrelenenlerden daha azını görmeyi seçebilir ancak RLS yapılandırmasını atlayarak izin verilenden daha fazlasını göremez.

İstemci tarafı filtrelemede (JavaScript), ISV son kullanıcının ilk görünümde neler göreceğini belirleyebilir ancak kullanıcının görünümün kendisinde gerçekleştirdiği değişiklikleri denetleyemez. Veri filtreleme arka uçta gerçekleşebilir ancak JavaScript istemcisi kodu tarafından tetiklenir ve bu nedenle son kullanıcı tarafından değiştirilebildiği için güvenli kabul edilmez.

Diğer ayrıntılar için bkz. [RLS ve JavaScript filtreleri](embedded-row-level-security.md#using-rls-vs-javascript-filters).

## <a name="licensing"></a>Lisanslama

### <a name="how-do-i-purchase-power-bi-embedded"></a>Power BI Embedded'ı nasıl satın alabilirim?

Power BI Embedded Azure üzerinden sunulmaktadır.

### <a name="what-happens-if-i-already-purchased-power-bi-premium-and-now-i-want-some-of-the-benefits-of-power-bi-embedded-in-azure"></a>Power BI Premium'u satın aldıysam ve Azure'da Power BI Embedded avantajlarının bazılarından yararlanmak istiyorsam ne yapmalıyım?

Müşteriler, geçerli sözleşme döneminin sonuna dek tüm mevcut Power BI Premium satın alma işlemleri için ödemelerine devam edecektir. Daha sonra gerektiği şekilde Power BI Premium ürünlerinde değişiklik yapabilirler.

### <a name="do-i-still-have-to-buy-power-bi-premium-to-get-access-to-power-bi-embedded"></a>Power BI Embedded'a erişmek için yine de Power BI Premium satın almam gerekiyor mu?

Hayır; Power BI Embedded, müşterilerinize çözümünüzü sunmak ve dağıtmak üzere ihtiyaç duyduğunuz Azure tabanlı kapasiteyi içermektedir.

### <a name="whats-the-purchase-commitment-for-power-bi-embedded"></a>Power BI Embedded satın alma taahhüdü nedir?

Müşteriler kullanımlarını saatlik olarak değiştirebilir. Power BI Embedded hizmeti için aylık veya yıllık taahhüt yoktur.

### <a name="how-does-the-usage-of-power-bi-embedded-show-up-on-my-bill"></a>Power BI Embedded kullanımı faturamda nasıl gösterilir?

Power BI Embedded dağıtılan düğüm türlerine dayalı tahmini bir saatlik ücrete göre faturalandırılır. Kaynağınız etkin olduğu sürece, kullanım olmasa bile ücretler fatura edilir. Ücretlerin fatura edilmesini durdurmak için kaynağınızı etkin bir şekilde duraklatmanız gerekir.

### <a name="who-needs-a-power-bi-pro-license-for-power-bi-embedded-and-why"></a>Power BI Embedded için kimlerin Power BI Pro lisansı alması gerekir ve bunun nedeni nedir?

Bir Power BI çalışma alanına rapor eklemesi gereken tüm analistlerin, REST API'leri kullanılmasını gerektiren tüm geliştiricilerin, Power BI kiracısını ve kapasitesini yönetmesi gereken tüm kiracı yöneticilerinin bir Power BI Pro lisansı alması gerekir.

Power BI Embedded katıştırılan içeriği yönetmek ve doğrulamak için Power BI kullanılmasına olanak tanıdığından doğru depolarda raporlara erişmek üzere PowerBI.com'da Uygulama kimliğini doğrulamak için Power BI Pro lisansı gereklidir.

Bununla birlikte, kendi uygulamasının içinde [ekli raporlar oluşturmak/düzenlemek](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Create-Report-in-Embed-View) için, son kullanıcının bir Pro lisansına ihtiyacı yoktur, hatta bir Power BI kullanıcısı olması bile gerekmez.

### <a name="can-i-get-started-for-free"></a>Ücretsiz olarak başlayabilir miyim?

Evet, Power BI Embedded için [Azure kredilerinizi](https://azure.microsoft.com/free/) kullanabilirsiniz.

### <a name="can-i-get-a-trial-experience-for-power-bi-embedded-in-azure"></a>Azure'da Power BI Embedded için bir deneme sürümü alabilir miyim?

Power BI Embedded Azure kapsamında yer aldığından hizmeti [Azure'a kaydolurken tanınan 200 ABD Doları kredi](https://azure.microsoft.com/free/) ile kullanabilirsiniz.

### <a name="is-power-bi-embedded-available-for-sovereign-clouds-us-government-germany-china"></a>Power BI Embedded, bağımsız bulutlarda (ABD, Almanya, Çin) kullanılabilir mi?

Power BI Embedded bazı [bağımsız bulutlarda](embed-sample-for-customers-sovereign-clouds.md) kullanılabilir. Bu hizmet Çin bulutunda henüz **kullanılamıyor**.

### <a name="is-power-bi-embedded-available-for-non-profits-and-educational"></a>Power BI Embedded kâr amacı gütmeyen ve eğitim kuruluşları için kullanılabilir mi?

Kâr amacı gütmeyen kuruluşlar ve eğitim kurumları Azure'ı satın alabilir. Azure'da bu tür müşteriler için özel fiyatlandırma yoktur.

## <a name="power-bi-workspace-collection"></a>Power BI Çalışma Alanı Koleksiyonu

### <a name="what-is-power-bi-workspace-collection"></a>Power BI Çalışma Alanı Koleksiyonu nedir?

**Power BI Çalışma Alanı Koleksiyonu** (**Power BI Embedded** Sürüm 1), **Power BI Çalışma Alanı Koleksiyonu** Azure kaynağını temel alan bir çözümdür. Bu çözüm, **Power BI Çalışma Alanı Koleksiyonu** çözümü altındaki Power BI içeriğini, özel API’leri ve Power BI’da uygulama kimliğini doğrulamak amacıyla çalışma alanı koleksiyonu anahtarlarını kullanarak müşterileriniz için **Power BI Embedded** uygulamaları oluşturmanıza olanak tanır.

### <a name="can-i-migrate-from-power-bi-workspace-collection-to-power-bi-embedded"></a>Power BI Çalışma Alanı Koleksiyonundan Power BI Embedded’e geçiş yapabilir miyim?

1. **Power BI Çalışma Alanı Koleksiyonu** içeriğini Power BI - https://docs.microsoft.com/power-bi/developer/migrate-from-powerbi-embedded#content-migration sürümüne kopyalamak için geçiş aracını kullanabilirsiniz.

2. İlk olarak, Power BI içeriği kullanan **Power BI Embedded** uygulama POC’si ile başlayın.

3. Üretime hazır olduğunuzda **Power BI Embedded** ayrılmış kapasitesi satın alın ve Power BI içeriğinizi (çalışma alanı) bu kapasiteye atayın.

> [!Note]
> Bir **Power BI Embedded** çözümü ile paralel olarak derleme yaparken **Power BI Çalışma Alanı Koleksiyonu**’nu kullanmaya devam edebilirsiniz. Hazır olduğunuzda, müşterinizi yeni **Power BI Embedded** çözümüne geçirebilir ve **Power BI Çalışma Alanı Koleksiyonu** çözümünü kullanımdan kaldırabilirsiniz.

Daha fazla bilgi için lütfen [Power BI Çalışma Alanı Koleksiyonu içeriğini Power BI Embedded'e geçirme](https://docs.microsoft.com/power-bi/developer/migrate-from-powerbi-embedded) bölümüne başvurun.

### <a name="is-power-bi-workspace-collection-on-a-path-to-be-deprecated"></a>Power BI Çalışma Alanı Koleksiyonu kullanım dışı bırakılacak mı?

Evet. Ancak halihazırda **Power BI Çalışma Alanı Koleksiyonu** çözümünü kullanan müşteriler kullanımdan kaldırılmasına kadar kullanmaya devam edebilir. Müşteriler ayrıca yeni çalışma alanı koleksiyonları ve hala **Power BI Çalışma Alanı Koleksiyonu** çözümünü kullanan herhangi bir **Power BI Embedded** uygulaması oluşturabilir.

Ancak, bu durum aynı zamanda hiçbir **Power BI Çalışma Alanı Koleksiyonu** çözümüne yeni özelliklerin eklenmeyeceği anlamına gelir ve bu müşterilerin yeni **Power BI Embedded** çözümüne geçişlerini planlamaları önerilir.

### <a name="when-will-power-bi-workspace-collection-support-be-discontinued"></a>Power BI Çalışma Alanı Koleksiyonu desteği ne zaman sona erecek?

Halihazırda **Power BI Çalışma Alanı Koleksiyonları** çözümünü kullanan müşteriler, çözümü Haziran 2018 sonuna ya da destek sözleşmelerinin sonuna kadar kullanmaya devam edebilir.

### <a name="in-what-regions-can-pbi-workspace-collection-be-created"></a>PBI Çalışma Alanı Koleksiyonu hangi bölgelerde oluşturulabilir?

Avustralya Güneydoğu, Brezilya Güney, Kanada Orta, Doğu ABD 2, Doğu Japonya, ABD Orta Kuzey, Kuzey Avrupa, Orta Güney ABD, Güneydoğu Asya, UK Güney, Batı Avrupa, Batı Hindistan ve Batı ABD bölgeleri kullanılabilir.

### <a name="why-should-i-migrate-from-pbi-workspace-collection-to-power-bi-embedded"></a>Power BI Çalışma Alanı Koleksiyonundan Power BI Embedded’e neden geçiş yapmalıyım?

**Power BI Embedded** çözümünde, **Power BI Çalışma Alanı Koleksiyonu** ile kullanamayacağınız yeni özellikler kullanıma sunulmuştur.

Özelliklerden bazıları şunlardır:

* **Power BI Çalışma Alanı Koleksiyonu** ile desteklenen iki veri kaynağı karşısında tüm PBI veri kaynakları desteklenmektedir. 
* Soru-cevap, yenileme, yer işaretleri, pano ve kutucuk ve pano ekleme ve özel menü gibi yeni özellikler yalnızca **Power BI Embedded** çözümünde desteklenir.
* Kapasite faturalama modeli.

## <a name="embedding-setup-tool"></a>Katıştırma kurulum aracı

### <a name="what-is-the-embedding-setup-tool"></a>Katıştırma kurulum aracı nedir?

[Katıştırma kurulum aracı](https://aka.ms/embedsetup), hızlıca kullanmaya başlamanıza ve bir örnek uygulama indirerek Power BI ile katıştırmaya başlamanıza olanak tanır.

### <a name="which-solution-should-i-choose"></a>Hangi çözümü seçmem gerekir?

* [Embedding for your customers](embedding.md#embedding-for-your-customers) seçeneği, Power BI hesabı olmayan kullanıcılar için panolar ve raporlar eklemenize olanak sağlar. [Embed for your customers](https://aka.ms/embedsetup/AppOwnsData) çözümünü çalıştırın.
* [Embedding for your organization](embedding.md#embedding-for-your-organization) seçeneği, Power BI hizmetinin kapsamını genişletmenize olanak tanır. [Embed for your organization](https://aka.ms/embedsetup/UserOwnsData) çözümünü çalıştırın.

### <a name="ive-downloaded-the-sample-app-which-solution-do-i-choose"></a>Örnek uygulamayı indirdim, hangi çözümü seçmem gerekiyor?

**Embed for your customers** deneyimi ile çalışıyorsanız *PowerBI-Developer-Samples.zip* dosyasını kaydedin ve sıkıştırmasını açın. Ardından *PowerBI-Developer-Samples-master\App Owns Data* klasörünü açın ve *PowerBIEmbedded_AppOwnsData.sln* dosyasını çalıştırın.

**Embed for your organization** deneyimi ile çalışıyorsanız *PowerBI-Developer-Samples.zip* dosyasını kaydedin ve sıkıştırmasını açın. Ardından *PowerBI-Developer-Samples-master\User Owns Data\integrate-report-web-app* klasörünü açın ve *pbi-saas-embed-report.sln* dosyasını çalıştırın.

### <a name="how-can-i-edit-my-registered-application"></a>Kayıtlı uygulamamı nasıl düzenleyebilirim?

AAD kayıtlı uygulamalarını düzenleme hakkında bilgiyi [burada](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications#updating-an-application) bulabilirsiniz.

### <a name="how-can-i-edit-my-power-bi-user-profile-or-data"></a>Power BI kullanıcı profilimi veya verilerimi nasıl düzenleyebilirim?

Power BI verilerinizi düzenleme hakkında bilgiyi [burada](https://docs.microsoft.com/power-bi/service-basic-concepts) bulabilirsiniz.

Daha fazla bilgi için lütfen bkz. [Ekli uygulamanızın sorunlarını giderme](embedded-troubleshoot.md).

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

### <a name="what-are-the-best-practices-to-improve-performance"></a>Performansı artırmak için en iyi yöntemler nelerdir?

[Power BI Embedded performansı](embedded-performance-best-practices.md)