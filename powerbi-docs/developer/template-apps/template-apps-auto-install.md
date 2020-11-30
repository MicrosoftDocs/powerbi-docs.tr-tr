---
title: Müşterileriniz için şablon uygulaması yükleme yapılandırmasını otomatikleştirme
description: Şablon uygulaması yükleme yapılandırmasını otomatikleştirmeyi öğrenin.
author: PaulInbar
ms.author: painbar
ms.topic: conceptual
ms.service: powerbi
ms.subservice: powerbi-developer
ms.date: 11/23/2020
ms.openlocfilehash: f44c687f3cae883ae78c3907e4be224d8cd0ced4
ms.sourcegitcommit: 9d033abd9c01a01bba132972497dda428d7d5c12
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95550593"
---
# <a name="automated-configuration-of-a-template-app-installation"></a>Şablon uygulaması yüklemesini otomatik yapılandırma

Şablon uygulamaları, müşterilerin ellerindeki verilerden içgörü almaya başlamasını sağlayan harika bir yöntemdir. Şablon uygulamaları, müşterileri verilerine bağlayıp istedikleri gibi özelleştirebilecekleri önceden oluşturulmuş raporlar sunarak hızlı bir şekilde çalışmaya başlamalarını sağlar.

Müşteriler her zaman verilerine bağlanma konusunda ayrıntılı bilgi sahibi olmayabilir ve şablon uygulaması yükleme sırasında bu bilgileri sağlamak zorunda olmak işlerini zorlaştırabilir.

Veri hizmetleri sağlayıcısıysanız ve müşterilerinizin verilerini hizmetinize almalarına yardımcı olmak için bir şablon uygulaması oluşturduysanız, şablon uygulamanızın parametrelerini yapılandırma sürecini otomatikleştirerek müşterilerinizin şablon uygulamanızı daha kolay bir şekilde yüklemesini sağlayabilirsiniz. Müşteriler portalınızda oturum açtıktan sonra sizin hazırladığınız özel bir bağlantıya tıklar. Bu işlemi ardından başlatılan otomasyon süreci gerekli bilgileri toplar, şablon uygulaması parametrelerine ön yapılandırma uygular ve müşteriyi uygulamayı yükleyebileceği Power BI hesabına yönlendirir. Burada müşterinin tek yapması gereken Yükle'ye tıklayıp veri kaynağında kimlik doğrulaması yapmaktır. Hepsi bu kadar! 

Müşteri deneyimi aşağı gösterilmiştir.

![Otomatik uygulama yükleme sürecindeki kullanıcı deneyimi.](media/template-apps-auto-install/high-level-flow.png)

Bu makalede şablon uygulaması yükleme yapılandırmasını otomatikleştirmeye yönelik temel akış, önkoşullar, temel adımlar ve ihtiyacınız olan API'ler anlatılmıştır. Ancak hemen uygulamaya geçmek isterseniz [öğretici](template-apps-auto-install-tutorial.md) bölümüne atlayabilir, burada hazırladığımız Azure İşlevi kullanan basit bir örnek uygulamayı kullanarak şablon uygulaması yükleme yapılandırmasını otomatikleştirebilirsiniz.

## <a name="basic-flow"></a>Temel akış

Şablon uygulaması yükleme yapılandırmasını otomatikleştirmenin temel akışı şu şekildedir:

1. Kullanıcı, ISV portalında oturum açar ve verilen bağlantıya tıklar. Bu işlem otomatik akışı başlatır. ISV'nin portalı bu aşamada kullanıcıya özgü yapılandırmayı hazırlar.

2. ISV, kiracıya kayıtlı [hizmet sorumlusunu (yalnızca uygulama belirteci)](../embedded/embed-service-principal.md) temel alan bir **yalnızca uygulama** belirteci alır.

3. ISV, [Power BI REST API'lerini](https://docs.microsoft.com/rest/api/power-bi/) kullanarak ISV tarafından hazırlanan kullanıcıya özgü parametre yapılandırmasını içeren bir **Yükleme Bileti** oluşturur.

4. ISV, yükleme biletini içeren bir ```POST``` yeniden yönlendirme yöntemini kullanarak kullanıcıyı Power BI'a yönlendirir.

5. Kullanıcı, yükleme biletiyle kendi Power BI hesabına yönlendirilir ve şablon uygulamasını yüklemesi istenir. Kullanıcı Yükle'ye tıkladığında şablon uygulaması yüklenir.

>[!Note]
>Parametre değerleri, ISV tarafından yükleme biletinin oluşturulması sırasında yapılandırılır ancak veri kaynağıyla ilgili kimlik bilgileri yalnızca kullanıcı tarafından yükleme sürecinin son aşamalarında sağlanır. Bu sayede üçüncü tarafların kullanımına sunulmaz ve kullanıcı ile şablon uygulaması veri kaynakları arasında güvenli bağlantı kurulmuş olur.

## <a name="prerequisites"></a>Önkoşullar

Şablon uygulamanızda önceden yapılandırılmış yükleme deneyimi sunmak için aşağıdaki önkoşullar gereklidir:

* **Power BI Pro lisansı**. Power BI Pro’ya kaydolmadıysanız, başlamadan önce [ücretsiz deneme için kaydolun](https://powerbi.microsoft.com/pricing/).

* Kendi **Azure Active Directory kiracısı** kurulumunuz. Kurulum yönergeleri için bkz. [Azure Active Directory kiracısı oluşturma](https://docs.microsoft.com/power-bi/developer/embedded/create-an-azure-active-directory-tenant).

* Yukarıda belirtilen kiracıda kayıtlı bir **hizmet sorumlusu (yalnızca uygulama belirteci)** . Daha fazla ayrıntı için bkz. [Hizmet sorumlusu ve uygulama gizli dizisiyle Power BI içeriği ekleme](https://docs.microsoft.com/power-bi/developer/embedded/embed-service-principal). Uygulamayı **sunucu tarafı web uygulaması** olarak kaydettiğinizden emin olun. Sunucu tarafı web uygulamasını kaydederek bir uygulama gizli dizisi oluşturursunuz. Bu aşamada *Uygulama Kimliği* (İstemci Kimliği) ve *Uygulama Gizli Dizisi* (İstemci Gizli Dizisi) bilgilerini sonraki adımlar için kaydetmeniz gerekir.

* Yüklenmeye hazır parametreli **şablon uygulaması**. Şablon uygulaması, uygulamanızı Azure Active Directory'ye (Azure AD) kaydettiğiniz kiracıda oluşturulmuş olmalıdır. Daha fazla bilgi için bkz. [şablon uygulaması ipuçları](https://docs.microsoft.com/power-bi/connect-data/service-template-apps-tips.md) veya [Power BI'da şablon uygulaması oluşturma](https://docs.microsoft.com/power-bi/connect-data/service-template-apps-create). Şablon uygulamasıyla ilgili aşağıdaki bilgileri sonraki adımlar için kaydetmeniz gerekir:
     * Uygulama oluşturulurken [Şablon uygulamasının özelliklerini tanımlama](../../connect-data/service-template-apps-create.md#define-the-properties-of-the-template-app) işleminde yer alan yükleme URL'sinin sonunda görünen *Uygulama Kimliği*, *Paket Anahtarı* ve *Sahip Kimliği*. Bu bağlantıya ulaşmak için şablon uygulamasının [Sürüm Yönetimi](../../connect-data/service-template-apps-create.md#manage-the-template-app-release) alanından **Bağlantı al**'a da tıklayabilirsiniz.

    * Şablon uygulamasının veri kümesinde tanımlanmış olan *Parametre Adları*. Büyük/küçük harfe duyarlı olan parametre adlarını [Şablon uygulamasının özelliklerin tanımlama](../../connect-data/service-template-apps-create.md#define-the-properties-of-the-template-app) adımının **Parametre Ayarları** sekmesinden veya Power BI veri kümesi ayarları sayfasından da alabilirsiniz.

    >[!NOTE]
    >AppSource üzerinde genel kullanıma açık olmasa dahi yükleme için hazır olan şablon uygulamanızın önceden yapılandırılmış yükleme sürecini test edebilirsiniz. Ancak kiracınızın dışındaki kullanıcıların şablon uygulamanızı yükleme amacıyla otomatik uygulama yükleme işlemini kullanabilmeleri için şablon uygulamasının [Power BI Uygulamaları marketinde](https://app.powerbi.com/getdata/services) genel kullanıma açık olması gerekir. Bu nedenle oluşturduğunuz otomatik yükleme uygulamasını kullanarak şablon uygulamanızı dağıtmadan önce [İş Ortağı Merkezi](https://docs.microsoft.com/azure/marketplace/partner-center-portal/create-power-bi-app-offer)'ne yayımlamayı unutmayın.

## <a name="main-steps-and-apis"></a>Temel adımlar ve API'ler

Aşağıdaki bölümlerde şablon uygulaması yükleme yapılandırmasını otomatikleştirme sürecinin temel adımları ve ihtiyacınız olan API'ler anlatılmıştır. Çoğu adım [Power BI REST API'leri](https://docs.microsoft.com/rest/api/power-bi/) ile gerçekleştirilir ancak aşağıdaki kod örneklerinde **.NET SDK** kullanılmıştır.

## <a name="step-1-create-a-power-bi-client-object"></a>1\. Adım: Power BI istemci nesnesi oluşturma 

Power BI REST API'lerini kullanabilmeniz için **Azure AD**'den [hizmet sorumlunuza](../embedded/embed-service-principal.md) ait bir **erişim belirteci** almanız gerekir. [Power BI REST API’lerine](https://docs.microsoft.com/rest/api/power-bi/) çağrı yapmadan önce, Power BI uygulamanız için [Azure AD erişim belirteci](../embedded/get-azuread-access-token.md#access-token-for-non-power-bi-users-app-owns-data) almanız gerekir.
**Erişim belirtecinizle** Power BI İstemcisi'ni oluşturmak için, [Power BI REST API'leriyle](https://docs.microsoft.com/rest/api/power-bi/) etkileşim kurmanızı sağlayacak Power BI istemci nesnenizi oluşturmanız gerekir. Power BI istemci nesnesini oluşturmak için **AccessToken** öğesini **_Microsoft.Rest.TokenCredentials_* _ nesnesine sarmanız gerekir.

```csharp
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.Rest;
using Microsoft.PowerBI.Api.V2;

var tokenCredentials = new TokenCredentials(authenticationResult.AccessToken, "Bearer");

// Create a Power BI Client object. it's used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Your code to goes here.
}
```

## <a name="step-2-create-an-install-ticket"></a>2\. Adım: Yükleme bileti oluşturma

Kullanıcılarınızı Power BI'a yönlendirmek için kullanacağınız bir yükleme bileti oluşturun. Bu işlem için _ *CreateInstallTicket** API'si kullanılır.
* [Template Apps CreateInstallTicket](https://docs.microsoft.com/rest/api/power-bi/templateapps/createinstallticket)

[Örnek uygulamanın](https://github.com/microsoft/Template-apps-examples/tree/master/Developer%20Samples/Automated%20Install%20Azure%20Function/InstallTemplateAppSample) [InstallTemplateApp/InstallAppFunction.cs](https://github.com/microsoft/Template-apps-examples/blob/master/Developer%20Samples/Automated%20Install%20Azure%20Function/InstallTemplateAppSample/InstallTemplateApp/InstallAppFunction.cs) dosyasında şablon uygulaması yükleme ve yapılandırma adımları için yükleme bileti oluşturma örneği gösterilmiştir.


Aşağıda şablon uygulaması *CreateInstallTicket* REST API'sinin kullanıldığı bir kod örneği verilmiştir.
```csharp
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// Create Install Ticket Request.
InstallTicket ticketResponse = null;
var request = new CreateInstallTicketRequest()
{
    InstallDetails = new List<TemplateAppInstallDetails>()
    {
        new TemplateAppInstallDetails()
        {
            AppId = Guid.Parse(AppId),
            PackageKey = PackageKey,
            OwnerTenantId = Guid.Parse(OwnerId),
            Config = new TemplateAppConfigurationRequest()
            {
                Configuration = Parameters
                                    .GroupBy(p => p.Name)
                                    .ToDictionary(k => k.Key, k => k.Select(p => p.Value).Single())
            }
        }
    }
};

// Issue the request to the REST API using .NET SDK
InstallTicket ticketResponse = await client.TemplateApps.CreateInstallTicketAsync(request);
```

## <a name="step-3-redirect-users-to-power-bi-with-the-ticket"></a>3\. Adım: Biletle kullanıcıları Power BI'a yönlendirme

Yükleme biletini oluşturduktan sonra kullanıcılarınızı şablon uygulaması yükleme ve yapılandırma adımlarını sürdürmek üzere Power BI'a yönlendirebilirsiniz. Bunu yapmak için şablon uygulamasının yükleme URL'sinde ```POST``` yöntemi yeniden yönlendirmesi, istek gövdesinde ise yükleme bileti kullanabilirsiniz.

```POST``` isteklerini kullanarak yeniden yönlendirme gerçekleştirmeye yönelik birçok farklı yöntem vardır. Senaryoya ve kullanıcılarınızın portalla ya da hizmetle etkileşim kurma şekline göre bir seçim yapabilirsiniz.

Genellikle test amacıyla kullanılan basit örneklerden birinde yükleme sonrasında kendisini otomatik olarak gönderen gizli bir alana sahip bir form kullanılır.

```javascript
<html>
    <body onload='document.forms["form"].submit()'>
        <!-- form method is POST and action is the app install URL -->
        <form name='form' action='https://app.powerbi.com/....' method='post' enctype='application/json'>
            <!-- value should be the new install ticket -->
            <input type='hidden' name='ticket' value='H4sI....AAA='>
        </form>
    </body>
</html>
```

Aşağıda yükleme biletini barındıran ve kullanıcıları otomatik olarak Power BI'a yönlendiren [örnek uygulama](https://github.com/microsoft/Template-apps-examples/tree/master/Developer%20Samples/Automated%20Install%20Azure%20Function/InstallTemplateAppSample) yanıtı gösterilmiştir. Bu Azure İşlevinin yanıtı, yukarıdaki html örneğinde gördüğünüz otomatik olarak kendi kendini gönderen formla aynıdır.

```csharp
...
    return new ContentResult() { Content = RedirectWithData(redirectUrl, ticket.Ticket), ContentType = "text/html" };
}

...

public static string RedirectWithData(string url, string ticket)
{
    StringBuilder s = new StringBuilder();
    s.Append("<html>");
    s.AppendFormat("<body onload='document.forms[\"form\"].submit()'>");
    s.AppendFormat("<form name='form' action='{0}' method='post' enctype='application/json'>", url);
    s.AppendFormat("<input type='hidden' name='ticket' value='{0}' />", ticket);
    s.Append("</form></body></html>");
    return s.ToString();
}
```

>[!Note]
>```POST``` tarayıcı yeniden yönlendirmelerini kullanmaya yönelik birçok farklı yöntem mevcut olsa da her zaman hizmet gereksinimlerinize ve kısıtlamalara göre en güvenli yöntemi kullanmanız gerekir. Bazı güvenli olmayan yeniden yönlendirme yöntemlerinin, kullanıcılarınızın veya hizmetinizin güvenlik sorunlarıyla karşı karşıya kalmasına neden olabileceğini unutmayın.

## <a name="step-4-move-your-automation-to-production"></a>4\. Adım: Otomasyonunuzu üretim ortamına taşıma

Tasarladığınız otomasyon senaryosu hazırsa üretim ortamına taşımayı unutmayın.

## <a name="next-steps"></a>Sonraki adımlar

* Şablon uygulaması yükleme yapılandırmasını otomatikleştirmek için basit bir Azure İşlevinin kullanıldığı [öğreticiyi](template-apps-auto-install-tutorial.md) deneyin.

* Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
