---
title: Power BI Embedded hakkında sık sorulan sorular
description: Power BI Embedded hakkında sık sorulan sorular ve cevaplar listesini inceleyin.
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 05/22/2019
ms.openlocfilehash: 1bdc31d550573b926d45776307b8fcade95f0dc0
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66222166"
---
# <a name="frequently-asked-questions-about-power-bi-embedded"></a>Power BI Embedded hakkında sık sorulan sorular

* Başka sorularınız varsa [Power BI Topluluğu'na sorun](http://community.powerbi.com/).
* Sorununuz hâlâ çözülmedi mi? [Power BI destek sayfasını](https://powerbi.microsoft.com/support/) ziyaret edin.

## <a name="general"></a>Genel

### <a name="what-is-power-bi-embedded"></a>Power BI Embedded nedir?

[Microsoft Power BI Embedded (PBIE)](azure-pbie-what-is-power-bi-embedded.md) uygulama geliştiricilerinin kendi veri Görselleştirmelerini ve kontrollerini sıfırdan oluşturmaya gerek kalmadan çarpıcı, tam etkileşimli raporları uygulamalarına izin verir.

### <a name="who-is-the-target-audience-for-power-bi-embedded"></a>Power BI Embedded kimler içindir?

Geliştiriciler ve yazılım şirketleri, uygulamalar kodlama olarak da bilinen bağımsız yazılım satıcılarına (ISV).

### <a name="how-is-power-bi-embedded-different-from-power-bi-the-service"></a>Power BI Embedded hangi açıdan Power BI hizmetinden farklıdır?

Power BI, kuruluşlara en kritik iş verilerini tek bir görünümde sunan hizmet olarak yazılım analiz çözümüdür.

Görsel analitik kararlar, müşterilerine yardımcı olmak için uygulamalarına eklemek isteyen ISV'ler için Microsoft Power BI Embedded geliştirmiştir. Bu ISV'ler kendilerini kendi analiz çözümü oluşturmak zorunda kalmaktan ödemek zorunda kalmamasını sağlar. [Ekli analiz](embedding.md) iş kullanıcılarının iş verilerine erişebilmesini ve uygulama içinde öngörü oluşturulabilmesi için sorgular yürütün sağlar.


### <a name="what-is-the-difference-between-power-bi-premium-and-power-bi-embedded"></a>Power BI Premium ve Power BI Embedded arasındaki fark nedir?

Power BI Premium, kuruluş, iş ortakları, müşterilerine ve tedarikçileri tek bir görünümde sunan eksiksiz bir BI çözümü isteyen kuruluşlara olarak kapasitesidir. Power BI Premium kuruluşların karar almasına yardımcı olur. Power BI Premium, kullanıcıların mobil uygulamaları, dahili olarak geliştirilmiş uygulamaları aracılığıyla veya Power BI portalı içeriği olanak tanıyan bir SaaS ürünüdür.

Power BI Embedded uygulamalarına görseller eklemek isteyen ISV'ler içindir. Power BI Embedded, uygulama geliştiricilerine yönelik olduğundan ve kuruluş içindekiler veya dışındakiler dahil olmak üzere tüm uygulama kullanıcıları Power BI Embedded kapsamında depolanan içerikleri kullanabildiğinden Power BI Embedded müşterilerinizin karar almasına yardımcı olur. Power BI Embedded paylaşamazsınız aracılığıyla tek tıklamayla kapasite içerik yayımlamak için Web veya SharePoint için tek tıklamayla yayımlama.

### <a name="what-is-the-microsoft-recommendation-for-when-a-customer-should-buy-power-bi-premium-vs-power-bi-embedded"></a>Microsoft bir müşterinin hangi durumlarda Power BI Premium ve hangi durumlarda Power BI Embedded satın almasını önerir?

Microsoft, kuruluşlar Power BI Premium, bir kurumsal sınıf, Self Servis bulut iş Zekası çözümü satın önerir. ISV'lerin bulut destekli katıştırılmış analiz bileşenleri için Power BI Embedded satın öneririz. Ancak, bir müşteri, ürün satın alma konusunda bir kısıtlama vardır.

Burada uygulamaları eklemek, ek bir ISV (tipik olarak büyük), kuruluş içinde önceden paketlenmiş Power BI hizmetinin ek avantajlarından yararlanabilmek için P SKU kullanmak istediği bazı durumlar olabilir. Bazı Kuruluşlar, yalnızca iş uygulamaları oluşturmak ve bunlara analiz eklemek istediklerinde ve önceden paketlenmiş Power BI hizmetini kullanmak istemediklerinde Azure'da A SKU kullanabilir.

### <a name="how-many-embed-tokens-can-i-create"></a>Kaç tane ekleme belirteci oluşturabilirim?

Ekleme belirteçleri PRO lisansına sahip olmaları amaçlanmıştır geliştirme testi için bir Power BI Yöneticisi için hesap veya [hizmet sorumlusu](embed-service-principal.md) yalnızca sınırlı sayıda belirteçleri oluşturabilirsiniz. Üretim ortamında ekleme yapmak için [kapasite satın alın](#technical). Kaç tane ekleme belirteçleri bir kapasite satın aldığınızda oluşturabileceğiniz için sınır yoktur. Geçerli eklenmiş kullanımı yüzde cinsinden gösteren kullanım değerini denetlemek için [Kullanılabilir Özellikler](https://docs.microsoft.com/rest/api/power-bi/availablefeatures) bölümüne gidin.

## <a name="technical"></a>Teknik

### <a name="what-is-the-difference-between-the-a-skus-in-azure-and-the-em-skus-in-office-365"></a>Azure’da A SKU ile Office 365’te EM SKU arasındaki fark nedir?

Powerbı.com bir hizmet (SaaS) çözümü ile sosyal işbirliği, e-posta aboneliği ve diğer özellikleri gibi çok sayıda özellik kuruluş yazılım gibidir. PowerBI.com içerik, katıştırılmış analiz çözümü yönetmek ve Kiracı düzeyi ayarları ISV'ler yardımcı olur.

Power BI Embedded API'leri geliştiriciler hizmet (PaaS) ayarlama gibi bir Platform katıştırılmış analiz çözümü oluşturmak için kullanabileceğiniz olur.

Özellik farkları kısmi bir listesi aşağıda verilmiştir.

| Öne çıkan özelliği | Power BI Embedded | Power BI Premium Kapasitesi | Power BI Premium Kapasitesi |
|----------------------------------------------------------------------------------|-------------------|---------------------------|---------------------------|
|   | (A SKU'lar) | (EM SKU'lar) | (P SKU'lar) |
| Power BI Uygulaması çalışma alanından yapıtları ekleme | Azure kapasitesi | Office 365 kapasitesi | Office 365 kapasitesi |
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
|Kullanım örnekleri | Kendi uygulamanıza içerik ekleme | <li> Kendi uygulamanıza içerik ekleme <br><br><br> <li> MS Office uygulamalarına içerik ekleme: <br> - [SharePoint](https://powerbi.microsoft.com/blog/integrate-power-bi-reports-in-sharepoint-online/) <br> - [Teams (mobil uygulama hariç)](https://powerbi.microsoft.com/blog/power-bi-teams-up-with-microsoft-teams/) <br> - [Dynamics 365](https://docs.microsoft.com/dynamics365/customer-engagement/basics/add-edit-power-bi-visualizations-dashboard) | <li> Kendi uygulamanıza içerik ekleme <br><br><br> <li> MS Office uygulamalarına içerik ekleme: <br> - [SharePoint](https://powerbi.microsoft.com/blog/integrate-power-bi-reports-in-sharepoint-online/) <br> - [Teams (mobil uygulama hariç)](https://powerbi.microsoft.com/blog/power-bi-teams-up-with-microsoft-teams/) <br> - [Dynamics 365](https://docs.microsoft.com/dynamics365/customer-engagement/basics/add-edit-power-bi-visualizations-dashboard) <br><br><br> <li> [Power BI hizmeti](https://powerbi.microsoft.com/) aracılığıyla Power BI kullanıcılarıyla içerik paylaşma  |
|Faturalama |Saatlik |Aylık |Aylık |
|Taahhüt  |Taahhütsüz |Yıllık  |Aylık/Yıllık |
|Ayrım |Tam esneklik; Azure portalında veya API'ler ile kaynaklar duraklatılabilir/sürdürülebilir, ölçek artırılabilir/azaltılabilir  |SharePoint Online ve Microsoft Teams (mobil uygulama hariç) içerik eklemek için kullanabilirsiniz |Uygulamalarda katıştırma birleştirilebilir ve Power BI Hizmeti aynı kapasitede kullanılabilir |

### <a name="what-are-the-prerequisites-to-create-a-pbie-capacity-in-azure"></a>Azure’da PBIE kapasitesi oluşturmanın önkoşulları nelerdir?

* Kuruluş dizininizde (Microsoft hesapları desteklenmez) oturum açın.
* Power BI kiracısına sahip olmalıdır, dizininizde en az bir kullanıcı Power BI için diğer bir deyişle, kaydolmuş. 
* Kuruluş dizininizde bir Azure aboneliğinizin olması gerekir.

### <a name="how-can-i-monitor-power-bi-embedded-capacity-consumption"></a>Power BI Embedded kapasite tüketimini nasıl izleyebilirim?

* [Power BI Yönetim portalını](../service-admin-portal.md#power-bi-embedded) kullanarak.

* Power BI’daki [ölçüm uygulamasını](https://review.docs.microsoft.com/power-bi/service-admin-premium-monitor-capacity) indirerek.

* [Azure tanılama günlüğüne kaydetmeyi](azure-pbie-diag-logs.md) kullanarak.

### <a name="can-my-capacity-scale-automatically-to-adjust-to-my-app-consumption"></a>My kapasite my app tüketimi ayarlamak için otomatik olarak ölçeklendirebilir miyim?

Varken Hayır otomatik ölçekleme, tüm API'leri herhangi bir zamanda ölçeklendirmek kullanılabilir.

### <a name="why-creatingscalingresuming-a-capacity-results-in-putting-the-capacity-into-a-suspended-state"></a>Kapasite oluşturma/ölçeklendirme/serbest bırakma işlemi neden kapasitenin askıya alınma durumuna geçmesine neden oluyor?

Kapasite (Ölçek/devam et/Oluştur) sağlama başarısız olabilir. Kapasite 's ProvisioningState denetlemek için alma ayrıntıları API kullanabilirsiniz: [Kapasiteler - Ayrıntıları Alma](https://docs.microsoft.com/rest/api/power-bi-embedded/capacities/getdetails).

### <a name="can-i-only-create-power-bi-embedded-capacities-in-a-specific-region"></a>Yalnızca belirli bir bölgede mi Power BI Embedded kapasiteleri oluşturabilirim?

[Çoklu coğrafya (Önizleme)](embedded-multi-geo.md) özelliği ile, Power BI ana kiracı konumunuzdan farklı bir bölgede [Power BI Embedded kapasitesi](azure-pbie-create-capacity.md) satın alabilirsiniz

### <a name="how-can-i-find-my-pbi-tenant-region"></a>My PBI Kiracı bölge nasıl bulabilirim?

PBI portalı PBI Kiracı bölgenizde bulmak için kullanabilirsiniz.

[https://app.powerbi.com/](https://app.powerbi.com/) > ? > Power BI Hakkında

![Power BI Hakkında](media/embedded-faq/about-01.png)
![Kiracı bölgesi](media/embedded-faq/tenant-location-01.png)

### <a name="what-does-the-cloud-solution-provider-csp-channel-support"></a>Hangi bulut çözümü sağlayıcısı (CSP) kanal destekliyor mu?

* CSP abonelik türüyle kiracınız için PBIE oluşturabilirsiniz
* İş ortağı hesabı müşteri kiracısında oturum açabilir ve müşteri kiracısı için PBIE satın alabilir. Power BI kapasite yöneticisi olarak müşteri kiracısı kullanıcısını belirtin

### <a name="why-do-i-get-an-unsupported-account-message"></a>Neden desteklenmeyen hesap iletisi alıyorum?

Power BI için kuruluş hesabıyla kaydolmanız gerekir. Bir Microsoft hesabı kullanarak Power BI'a kaydolurken desteklenmez.

### <a name="can-i-use-apis-to-create-and-manage-azure-capacities"></a>Oluşturup Azure kapasitelerinin yönetmek için API'leri kullanabilir miyim?

Evet, Powershell cmdlet'leri ve Azure Resource Manager REST API'leri PBIE kaynakları oluşturup yönetmek için kullanabileceğiniz vardır.

* [REST API'leri](https://docs.microsoft.com/rest/api/power-bi-embedded/)
* [PowerShell cmdlet'leri](https://docs.microsoft.com/powershell/module/azurerm.powerbiembedded/)

### <a name="what-is-the-pbi-embedded-dedicated-capacity-role-in-a-pbi-embedded-solution"></a>PBI Embedded çözümünde PBI Embedded adanmış kapasite rolü nedir?

İçin [çözümünüzü üretime yükseltme](embed-sample-for-customers.md#move-to-production), uygulamanızın kullandığı Power BI içeriğini (uygulama çalışma alanı) Power BI Embedded (A SKU) bir kapasiteye atamanız gerekir.

### <a name="in-what-azure-regions-is-pbi-embedded-available"></a>Hangi Azure bölgelerinde PBI ekli var mı?

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

### <a name="what-is-power-bi-embeddeds-authentication-model"></a>Power BI Embedded ' ın kimlik doğrulama modeli nedir?

Azure AD ana kullanıcı (bir belirlenen Power BI Pro lisanslı kullanıcısı) kimlik doğrulaması için ya da ile kullanmak Power BI Embedded devam [hizmet sorumlusu](embed-service-principal.md) Power BI'da uygulama kimliğini doğrulamak için.  

 Bir ISV, kendi kimlik doğrulama ve yetkilendirme için kendi uygulamalarında uygulayabilirsiniz.

Zaten bir Azure AD kiracınız varsa mevcut dizininizi kullanabilirsiniz. Ayrıca yeni bir oluşturabilirsiniz, katıştırılmış uygulama içeriğinizin güvenliği için Azure AD kiracısı.

Bir AAD belirteci almak için [Azure Active Directory Kimlik Doğrulama Kitaplıkları](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries)'ndan birini kullanabilirsiniz. Birden fazla platformda kullanılabilen istemci kitaplıkları vardır.

### <a name="my-application-already-uses-aad-for-user-authentication-how-can-we-use-this-identity-when-authenticating-to-power-bi-in-a-user-owns-data-scenario"></a>Uygulamam zaten Kullanıcı Kimlik Doğrulaması için AAD kullanır. "Verilerin Kullanıcıya Ait" olduğu bir senaryoda Power BI'da kimlik doğrulaması yaparken bu Kimliği nasıl kullanabiliriz?

Standart OAuth üzerinde-behalf-of akışı olan (<https://docs.microsoft.com/azure/active-directory/develop/web-api>). Power BI hizmeti (gerekli kapsamlarla) izinleri istemek için uygulamanızı yapılandırmanız gerekir. Uygulamanız için kullanıcı belirteci aldıktan sonra ADAL API kullanıcı erişimini kullanarak AcquireTokenAsync için yalnızca çağrı token ve kaynak kimliği Power BI kaynak URL'sini belirtin:

```csharp
var context = new AD.AuthenticationContext(authorityUrl);
var userAssertion = new AD.UserAssertion(userAccessToken);
var clientAssertion = new AD.ClientAssertionCertificate(MyAppId, MyAppCertificate)
var authenticationResult = await context.AcquireTokenAsync(resourceId, clientAssertion, userAssertion);
```

### <a name="what-object-id-is-the-service-principal-object-id"></a>Hangi hizmet sorumlusu nesne kimliği kimliğidir nesne?

*Nesne kimliği* kayıtlı bir uygulama ana ekranından uygulama nesnesi kimliğidir.

Nesne Kimliği bulundu *uygulama yerel dizinde yönetilen > Özellikleri* kullanması gereken hizmet sorumlusu nesne kimliği bir bölümdür. Başvuru işlemleri için bir hizmet sorumlusu veya hizmet sorumlusu nesne kimliği değişiklik yapmak için bu nesne kimliği: Bir hizmet sorumlusu yönetici olarak bir çalışma alanına uygulama gibi.

### <a name="how-is-power-bi-embedded-different-from-other-azure-services"></a>Power BI Embedded hangi açıdan diğer Azure hizmetlerinden farklıdır?

Azure'da Power BI Embedded satın almadan önce bir Power BI hesabınızın olması gerekir. Power BI Embedded dağıtılan bölgeniz, Power BI hesabınızda belirler. Azure'da Power BI Embedded kaynağınızı yöneterek:

* Ölçeği artırın/azaltın
* Kapasite yöneticileri ekleyin
* Hizmeti duraklatın/sürdürün

Power BI Embedded kapasitenize çalışma alanları atamak/çalışma alanının atamasını kaldırmak için PowerBI.com'u kullanın.

### <a name="what-are-the-supported-deploy-regions"></a>Dağıtım bölgeleri desteklenen nelerdir?

Avustralya Güneydoğu, Batı ABD, Batı ABD 2, Batı Avrupa, Birleşik Krallık Güney, Brezilya Güney, Doğu ABD 2, Güneydoğu Asya, Hindistan Batı, Japonya Doğu, Kuzey Avrupa, Kuzey Orta ABD, Orta Güney ABD, Orta Kanada.

### <a name="what-content-pack-data-types-can-you-embed"></a>Hangi içerik paketi veri türleri, katıştırabilirsiniz?

*Olamaz* ekleme **panolar** ve **kutucukları** içerik paketi veri kümelerinden oluşturulan. Ancak, *olabilir* ekleme **raporları** bir içerik paketi veri kümesinden oluşturulmuş.

### <a name="what-is-the-difference-between-using-row-level-security-rls-vs-javascript-filters"></a>Satır düzeyi güvenlik (RLS) vs kullanarak arasındaki fark nedir? JavaScript filtrelerini kullanmanın ne farkı vardır?

Genellikle Karışıklığı önlemek için geçici bir yöntem denetleme hakkında ne olduğu için RLS JavaScript filtreleri kullanmak için belirli bir kullanıcı görebilirsiniz, ve diğer kullanıcı görünümü en iyi duruma getirme hakkında.

RLS’de, ISV geliştiricisi model oluşturma ve ekleme belirteci oluşturmanın bir parçası olarak veri filtrelemesini denetler. Son kullanıcı yalnızca ISV’nin görmesine izin verdiği kadarını görür. Bu durumda kullanıcı filtrelenenlerden daha azını görmeyi seçebilir ancak RLS yapılandırmasını atlayarak izin verilenden daha fazlasını göremez.

İstemci tarafı filtreleme (JavaScript), ISV ne başlangıç görünümü son kullanıcının gördüğü karar verebilirsiniz, ancak son kullanıcı, görünüm için geçerli olabilecek değişiklikleri kontrol edemezsiniz. Kullanıcı Javascript istemci kodu, arka uçta filtreleme veri tetikleyebilirsiniz olduğundan, güvenli düşünülmez.

Diğer ayrıntılar için bkz. [RLS ve JavaScript filtreleri](embedded-row-level-security.md#using-rls-vs-javascript-filters).

### <a name="how-do-i-manage-permissions-for-service-principals-with-power-bi"></a>Power BI ile hizmet sorumlularının izinlerini nasıl yönetebilirim?

Etkinleştirdikten sonra [hizmet sorumlusu](embed-service-principal.md) Power BI ile kullanmak için uygulamanın AD izinlerini artık etkili değildir. Bundan sonra uygulamanın izinleri Power BI yönetim portalı üzerinden yönetilir.

Hizmet sorumluları tüm Power BI kiracı ayarları için izinleri kendi güvenlik grubundan devralır. İzinleri kısıtlamak için bir adanmış güvenlik grubuna için hizmet sorumluları oluşturma ve eklemek **belirli güvenlik grupları hariç** ilgili, etkin Power BI ayarlarının listesi.

Bu durum, hizmet sorumlusunu yeni çalışma alanına bir **yönetici** olarak eklediğinizde önemlidir. Bu görevi [API'ler](https://docs.microsoft.com/rest/api/power-bi/groups/addgroupuser) aracılığıyla veya Power BI hizmetiyle yönetebilirsiniz.

### <a name="when-to-use-an-application-id-vs-a-service-principal-object-id"></a>Uygulama kimliği ve hizmet sorumlusu nesne kimliği ne zaman kullanılır?

**[Uygulama kimliği](embed-sample-for-customers.md#application-id)** , kimlik doğrulaması için uygulama kimliği geçirilirken erişim belirtecini oluşturmak için kullanılır.

İşlemlerde hizmet sorumlusuna başvurmak veya değişiklikler yapmak için (örneğin, hizmet sorumlusunu çalışma alanına yönetici olarak uygulama) **[hizmet sorumlusu nesne kimliğini](embed-service-principal.md#how-to-get-the-service-principal-object-id)** kullanırsınız.

### <a name="can-you-manage-an-on-premises-data-gateway-with-service-principal"></a>Şirket içi veri ağ geçidini hizmet sorumlusuyla yönetebilir misiniz?

Şirket içi veri ağ geçidini, ana hesapla yaptığınız gibi [hizmet sorumlusunu](embed-service-principal.md) kullanarak yönetemezsiniz.

Ana hesapla, veri ağ geçidini yükleyebilir, ağ geçidine kullanıcı ekleyebilir, veri kaynaklarına bağlanabilir ve diğer yönetim görevlerini yerine getirebilirsiniz.

Hizmet sorumlusuyla, SQL Server Analysis Services (SSAS) şirket içi canlı bağlantı veri kaynağını kullanarak [satır düzeyi güvenliği (RLS)](embedded-row-level-security.md#on-premises-data-gateway-with-service-principal-preview) yapılandırabilirsiniz. Bu şekilde, hizmet sorumlusu kullanarak **Power BI Embedded** ile tümleştirildiğinde SSAS'de kullanıcıları ve onların erişimini yönetebilirsiniz.

### <a name="can-you-sign-into-the-power-bi-service-with-service-principal"></a>Hizmet sorumlusuyla Power BI hizmetinde oturum açabilir misiniz?

Hayır; hizmet sorumlusunu kullanarak Power BI'da oturum açamazsınız.

Ayrıca, yalnızca ekleme belirteci oluşturduğunuzda, dış uygulamalarda (SaaS embed) bir kullanıcı olarak içerik kullanamazsınız.

### <a name="what-are-the-best-practices-to-improve-performance"></a>Performansı artırmak için en iyi yöntemler nelerdir?

[Power BI Embedded performansı](embedded-performance-best-practices.md)

## <a name="licensing"></a>Lisanslama

### <a name="how-do-i-purchase-power-bi-embedded"></a>Power BI Embedded'ı nasıl satın alabilirim?

Power BI Embedded Azure üzerinden sunulmaktadır.

### <a name="what-happens-if-i-already-purchased-power-bi-premium-and-now-i-want-some-power-bi-embedded-in-azure-benefits"></a>Zaten Power BI Premium satın aldım ve artık bazı Power BI Embedded Azure avantaj istiyorum ne olur?

Müşteriler, geçerli sözleşme döneminin sonuna kadar tüm mevcut Power BI Premium'u satın alma işlemleri için ödeme yapmaya devam ve daha sonra bu noktada, kendi Power BI Premium'u satın alma işlemleri gerektiği şekilde geçiş yapabilirsiniz.

### <a name="do-i-still-have-to-buy-power-bi-premium-to-get-access-to-power-bi-embedded"></a>Power BI Embedded'a erişmek için yine de Power BI Premium satın almam gerekiyor mu?

Hayır; Power BI Embedded, müşterilerinize çözümünüzü sunmak ve dağıtmak üzere ihtiyaç duyduğunuz Azure tabanlı kapasiteyi içermektedir.

### <a name="whats-the-purchase-commitment-for-power-bi-embedded"></a>Power BI Embedded satın alma taahhüdü nedir?

Müşteriler kullanımlarını saatlik olarak değiştirebilir. Power BI Embedded hizmeti için aylık veya yıllık taahhüt yoktur.

### <a name="how-does-the-usage-of-power-bi-embedded-show-up-on-my-bill"></a>Power BI Embedded kullanımı faturamda nasıl gösterilir?

Power BI Embedded dağıtılan düğüm türlerine dayalı tahmini bir saatlik ücrete göre faturalandırılır. Kullanım olsa bile kaynağınız etkin olduğu sürece faturalandırılırsınız. Faturalandırmayı durdurmak için kaynağınızı duraklatmak gerekir.

### <a name="who-needs-a-power-bi-pro-license-for-power-bi-embedded-and-why"></a>Power BI Embedded için kimlerin Power BI Pro lisansı alması gerekir ve bunun nedeni nedir?

Bir Power BI Pro lisansına sahip olması veya [hizmet sorumlusu](embed-service-principal.md) REST API'lerini kullanma. Raporları Power BI çalışma alanına eklemek için Analistin bir Power BI Pro lisansı veya hizmet sorumlusu gerekir. Power BI kiracısını ve kapasitesini yönetmesi için bir yönetici gereklidir Power BI Pro lisansına sahip.

Power BI Embedded katıştırılan içeriği ve yönetmek için Power BI portal kullanımına izin verir, çünkü doğru depolarda raporlara erişmek için PowerBI.com içindeki uygulama kimliğini doğrulamak için Power BI Pro lisansı gereklidir.

Bununla birlikte, kendi uygulamasının içinde [ekli raporlar oluşturmak/düzenlemek](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Create-Report-in-Embed-View) için, son kullanıcının bir Pro lisansına ihtiyacı yoktur, hatta bir Power BI kullanıcısı olması bile gerekmez.

### <a name="can-i-get-started-for-free"></a>Ücretsiz olarak başlayabilir miyim?

Evet, Power BI Embedded için [Azure kredilerinizi](https://azure.microsoft.com/free/) kullanabilirsiniz.

### <a name="can-i-get-a-trial-experience-for-power-bi-embedded-in-azure"></a>Azure'da Power BI Embedded için bir deneme sürümü alabilir miyim?

Power BI Embedded Azure kapsamında olduğundan, bu hizmetle kullanmak mümkün mü [Azure'a kaydolurken tanınan 200 ABD Doları kredi](https://azure.microsoft.com/free/).

### <a name="is-power-bi-embedded-available-for-national-clouds-us-government-germany-china"></a>Power BI Embedded, ulusal bulutlarda (ABD, Almanya, Çin) kullanılabilir mi?

Power BI Embedded, ayrıca kullanılabilir [Ulusal Bulutlar](embed-sample-for-customers-national-clouds.md).

### <a name="is-power-bi-embedded-available-for-non-profits-and-educational"></a>Power BI Embedded kâr amacı gütmeyen ve eğitim kuruluşları için kullanılabilir mi?

Kar amacı gütmeyen ve eğitim kurumları için Azure fiyatlandırması gereksinimleri olmadan özel yoktur.

## <a name="power-bi-workspace-collection"></a>Power BI Çalışma Alanı Koleksiyonu

### <a name="what-is-power-bi-workspace-collection"></a>Power BI Çalışma Alanı Koleksiyonu nedir?

**Power BI çalışma alanı koleksiyonu** (**Power BI Embedded** sürüm 1) dayalı bir çözüm **Power BI çalışma alanı koleksiyonu** Azure kaynak. Bu çözüm, **Power BI Çalışma Alanı Koleksiyonu** çözümü altındaki Power BI içeriğini, özel API’leri ve Power BI’da uygulama kimliğini doğrulamak amacıyla çalışma alanı koleksiyonu anahtarlarını kullanarak müşterileriniz için **Power BI Embedded** uygulamaları oluşturmanıza olanak tanır.

### <a name="can-i-migrate-from-power-bi-workspace-collection-to-power-bi-embedded"></a>Power BI Çalışma Alanı Koleksiyonundan Power BI Embedded’e geçiş yapabilir miyim?

1. **Power BI Çalışma Alanı Koleksiyonu** içeriğini Power BI - https://docs.microsoft.com/power-bi/developer/migrate-from-powerbi-embedded#content-migration sürümüne kopyalamak için geçiş aracını kullanabilirsiniz.

2. İlk olarak, Power BI içeriği kullanan **Power BI Embedded** uygulama POC’si ile başlayın.

3. Üretime hazır olduğunuzda **Power BI Embedded** ayrılmış kapasitesi satın alın ve Power BI içeriğinizi (çalışma alanı) bu kapasiteye atayın.

    > [!Note]
    > Bir **Power BI Embedded** çözümü ile paralel olarak derleme yaparken **Power BI Çalışma Alanı Koleksiyonu**’nu kullanmaya devam edebilirsiniz. Hazır olduğunuzda, müşterinizi yeni **Power BI Embedded** çözümüne geçirebilir ve **Power BI Çalışma Alanı Koleksiyonu** çözümünü kullanımdan kaldırabilirsiniz.

Daha fazla bilgi için lütfen [Power BI Çalışma Alanı Koleksiyonu içeriğini Power BI Embedded'e geçirme](https://docs.microsoft.com/power-bi/developer/migrate-from-powerbi-embedded) bölümüne başvurun.

### <a name="is-power-bi-workspace-collection-on-a-deprecation-path"></a>Power BI çalışma alanı koleksiyonu kullanımdan kaldırma yola mi?

Evet, ancak zaten kullanan müşteriler **Power BI çalışma alanı koleksiyonu** çözüm kullanımdan kaldırma kadar kullanmaya devam edebilir. Müşteriler ayrıca yeni çalışma alanı koleksiyonları ve hala **Power BI Çalışma Alanı Koleksiyonu** çözümünü kullanan herhangi bir **Power BI Embedded** uygulaması oluşturabilir.

Ancak, bu da yeni özellikler için eklenmez gelir **Power BI çalışma alanı koleksiyonu** çözümler. Müşterilerin yeni geçişini planlama öneriyoruz **Power BI Embedded** çözüm.

### <a name="when-is-power-bi-workspace-collection-support-discontinued"></a>Power BI Çalışma Alanı Koleksiyonu desteği ne zaman sona erecek?

Halihazırda **Power BI Çalışma Alanı Koleksiyonları** çözümünü kullanan müşteriler, çözümü Haziran 2018 sonuna ya da destek sözleşmelerinin sonuna kadar kullanmaya devam edebilir.

### <a name="in-what-regions-can-i-create-a-pbi-workspace-collection"></a>Hangi bölgelerde PBI çalışma alanı koleksiyonu oluşturabilir miyim?

Avustralya Güneydoğu, Brezilya Güney, Kanada Orta, Doğu ABD 2, Doğu Japonya, ABD Orta Kuzey, Kuzey Avrupa, Orta Güney ABD, Güneydoğu Asya, UK Güney, Batı Avrupa, Batı Hindistan ve Batı ABD bölgeleri kullanılabilir.

### <a name="why-should-i-migrate-from-pbi-workspace-collection-to-power-bi-embedded"></a>Power BI Çalışma Alanı Koleksiyonundan Power BI Embedded’e neden geçiş yapmalıyım?

Vardır bazı yeni **Power BI Embedded** çözüm özellikleri ve yetenekleri ile yapamayacağınız **Power BI çalışma alanı koleksiyonu**.

Özelliklerden bazıları şunlardır:
* PBI veri kaynakları desteklenir. Yalnızca iki **Power BI çalışma alanı koleksiyonu** veri kaynakları desteklenmektedir. 
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

Azure AD'ye kayıtlı uygulamaları düzenlemeyi öğrenmek için bkz. [Hızlı başlangıç: Azure Active Directory’de uygulamayı güncelleştirme](https://docs.microsoft.com/azure/active-directory/develop/quickstart-v1-update-azure-ad-app).

### <a name="how-can-i-edit-my-power-bi-user-profile-or-data"></a>Power BI kullanıcı profilimi veya verilerimi nasıl düzenleyebilirim?

Power BI verilerinizi düzenleme hakkında bilgiyi [burada](https://docs.microsoft.com/power-bi/service-basic-concepts) bulabilirsiniz.

Daha fazla bilgi için bkz. [Ekli uygulamanızın sorunlarını giderme](embedded-troubleshoot.md).

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)
