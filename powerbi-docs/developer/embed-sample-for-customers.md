---
title: Müşterileriniz için uygulamanıza Power BI içeriği eklemek için tümleşik analiz
description: Müşterileriniz için tümleşik analize yönelik Power BI API’lerini kullanarak bir raporu, panoyu veya kutucuğu bir uygulamayla tümleştirmeyi veya uygulamaya eklemeyi öğrenin. Tümleşik analiz yazılımını, tümleşik analiz araçlarını veya tümleşik iş zekası araçlarını kullanarak Power BI’ı uygulamanızla tümleştirmeyi öğrenin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
ms.topic: tutorial
ms.service: powerbi
ms.subservice: powerbi-developer
ms.custom: seodec18
ms.date: 04/02/2019
ms.openlocfilehash: 24a9c0069cb80a20a84823655437a27a4f6c0e9e
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73877709"
---
# <a name="tutorial-embed-power-bi-content-into-an-application-for-your-customers"></a>Öğretici: Müşterileriniz için Power BI içeriğini bir uygulamaya ekleme

**Azure’da Power BI Embedded** veya **Office’te Power BI Embedded** ile verilerin sahibi uygulamadır örneğini kullanarak raporları, panoları veya kutucukları bir uygulamaya ekleyebilirsiniz. **Verilerin sahibi uygulamadır** örneği, eklenmiş analiz platformu olarak Power BI’ı kullanan bir uygulamanız olması durumunda kullanılır. Bir **ISV** veya **geliştirici** olarak, tamamen tümleşik ve etkileşimli bir uygulamada raporlar, panolar veya kutucuklar görüntüleyen Power BI içeriği oluşturabilirsiniz. Üstelik kullanıcıların Power BI lisansı olması gerekmez. Bu öğreticide, müşterileriniz için Power BI JavaScript API’siyle birlikte Power BI .NET SDK’sını kullanıp bir raporu uygulama ile tümleştirme işlemi gösterilir.

![Power BI Rapor Ekleme](media/embed-sample-for-customers/embed-sample-for-customers-035.png)

Bu öğreticide aşağıdakilerin nasıl yapılacağını öğreneceksiniz:
> [!div class="checklist"]
> * Azure’da bir uygulama kaydetme.
> * Bir uygulamaya Power BI raporu ekleme.

## <a name="prerequisites"></a>Önkoşullar

Başlamak için şunlara sahip olmalısınız:

* [Power BI Pro hesabı](../service-self-service-signup-for-power-bi.md) (Power BI Pro hesabınızda oturum açmak için bir kullanıcı adıyla paroladan oluşan ana hesap) veya [hizmet sorumlusu (yalnızca uygulama belirteci)](embed-service-principal.md).
* [Azure Active Directory kiracınız](create-an-azure-active-directory-tenant.md) ayarlanmış olmalıdır.

**Power BI Pro**’ya kaydolmadıysanız başlamadan önce [ücretsiz deneme için kaydolun](https://powerbi.microsoft.com/pricing/).

## <a name="set-up-your-embedded-analytics-development-environment"></a>Eklediğiniz analiz geliştirme ortamını ayarlama

Raporları, panoları veya kutucukları uygulamanıza eklemeye başlamadan önce ortamınızın Power BI ile ekleme işlevlerine izin verdiğinden emin olmanız gerekir.

Hızla çalışmaya başlayıp ortam oluşturma ve rapor ekleme işlemi boyunca adım adım size yol gösteren örnek bir uygulamayı indirmek için [Ekleme kurulum aracı](https://aka.ms/embedsetup/AppOwnsData) bölümünün üzerinden geçebilirsiniz.

Ancak, ortamı el ile ayarlamayı seçerseniz aşağıdaki adımlara devam edebilirsiniz.

### <a name="register-an-application-in-azure-active-directory-azure-ad"></a>Azure Active Directory'de (Azure AD) bir uygulamayı kaydetme

Uygulamanızın [Power BI REST API'lerine](https://docs.microsoft.com/rest/api/power-bi/) erişmesini sağlamak için [uygulamanızı Azure Active Directory'ye kaydedin](register-app.md). Uygulamanızı kaydettiğinizde uygulamanız için bir kimlik oluşturabilir ve Power BI REST kaynaklarıyla ilgili izinleri belirleyebilirsiniz. Uygulama kaydına nasıl başlayacağınız, ana hesap mı yoksa [hizmet sorumlusu ](embed-service-principal.md) mu kullanmak istediğinize bağlıdır.

İzlediğiniz yöntem, Azure'a kaydettiğiniz uygulamanın türünü etkiler.

Ana hesap kullanarak devam ediyorsanız, **Yerel** uygulama kaydetme işlemini kullanın. Yerel uygulama kullanmanızın nedeni etkileşimli olmayan bir oturum açma yöntemiyle çalışmanızdır.

Öte yandan hizmet sorumlusu kullanarak devam ederseniz, **sunucu tarafı web uygulaması** kaydetme işlemini kullanmalısınız. Sunucu tarafı web uygulamasını kaydederek bir uygulama gizli dizisi oluşturursunuz.

## <a name="set-up-your-power-bi-environment"></a>Power BI ortamınızı ayarlama

### <a name="create-a-workspace"></a>Çalışma alanı oluşturma

Müşterileriniz için raporlar, panolar ve kutucuklar yerleştiriyorsanız, çalışma alanı içine içeriğinizi yerleştirmeniz gerekir. Ayarlayabileceğiniz farklı türlerde çalışma alanları vardır: [geleneksel çalışma alanları](../service-create-workspaces.md) veya [yeni çalışma alanları](../service-create-the-new-workspaces.md). *Ana* hesap kullanıyorsanız, hangi tür çalışma alanı kullandığınız önemli değildir. Ama uygulamanızda oturum açarken *[hizmet sorumlusu](embed-service-principal.md)* kullanıyorsanız, yeni çalışma alanlarını kullanmanız gerekir. Her iki senaryoda da, hem *ana* hesap hem de *hizmet sorumlusu* uygulamaya katılan çalışma alanlarında yönetici olmalıdır.

### <a name="create-and-publish-your-reports"></a>Raporlarınızı oluşturma ve yayımlama

Power BI Desktop'ı kullanarak raporlarınızı ve veri kümelerinizi oluşturabilir, ardından bu raporları çalışma alanında yayımlayabilirsiniz. Bu görevi gerçekleştirmenin iki yolu vardır: Son kullanıcı olarak, raporları bir ana hesapla (Power BI Pro lisansı) geleneksel çalışma alanına yayımlayabilirsiniz. Hizmet sorumlusu kullanıyorsanız, raporları [Power BI REST API'lerini](https://docs.microsoft.com/rest/api/power-bi/imports/postimportingroup) kullanarak yeni çalışma alanlarına yayımlayabilirsiniz.

Aşağıdaki adımlar PBIX raporunuzu Power BI çalışma alanınıza yayımlama işleminde yol gösterir.

1. GitHub'dan örnek [Blog Tanıtımı](https://github.com/Microsoft/powerbi-desktop-samples)’nı indirin.

    ![rapor örneği](media/embed-sample-for-customers/embed-sample-for-customers-026-1.png)

2. **Power BI Desktop**’ta örnek PBIX raporunu açın.

   ![PBI desktop raporu](media/embed-sample-for-customers/embed-sample-for-customers-027.png)

3. **Çalışma alanlarında** yayımlayın. Bu işlem, ana hesap (Power Pro lisansı) veya hizmet sorumlusu kullanmanıza göre farklılık gösterir. Ana hesap kullanıyorsanız, raporunuzu Power BI Desktop aracılığıyla yayımlayabilirsiniz.  Şimdi hizmet sorumlusu kullanıyorsanız Power BI REST API'lerini kullanmanız gerekir.

## <a name="embed-content-using-the-sample-application"></a>Örnek uygulamayı kullanarak içeriği ekleme

Bu örnek tanıtım amacıyla bilerek basit tutulmuştur. Uygulama gizli dizisinin veya ana hesap kimlik bilgilerinin korunması size veya geliştiricilerinize bağlıdır.

Örnek uygulamayı kullanarak içeriğinizi eklemeye başlamak için aşağıdaki adımları izleyin.

1. [Visual Studio](https://www.visualstudio.com/)'yu (sürüm 2013 veya üzeri) indirin. En son [NuGet paketini](https://www.nuget.org/profiles/powerbi) indirdiğinizden emin olun.

2. Başlamak için GitHub’dan [Verilerin Sahibi Uygulamadır örneğini](https://github.com/Microsoft/PowerBI-Developer-Samples) indirin.

    ![Verilerin Sahibi Uygulamadır uygulama örneği](media/embed-sample-for-customers/embed-sample-for-customers-026.png)

3. Örnek uygulamada **Web.config** dosyasını açın. Uygulamayı çalıştırmak için doldurmanız gereken alanlar vardır. **AuthenticationType** olarak **MasterUser** veya **ServicePrincipal**'ı seçebilirsiniz. Seçtiğiniz kimlik doğrulama yöntemine bağlı olarak, tamamlanması gereken farklı alanlar vardır.

    > [!Note]
    > Bu örnekte varsayılan **AuthenticationType** MasterUser'dır.

    <center>

    | **MasterUser** <br> (Power BI Pro lisansı) | **ServicePrincipal** <br> (yalnızca uygulama belirteci)|
    |---------------|-------------------|
    | [applicationId](#application-id) | [applicationId](#application-id) |
    | [workspaceId](#workspace-id) | [workspaceId](#workspace-id) |
    | [reportId](#report-id) | [reportId](#report-id) |
    | [pbiUsername](#power-bi-username-and-password) |  |
    | [pbiPassword](#power-bi-username-and-password) |  |
    |  | [applicationsecret](#application-secret) |
    |  | [tenant](#tenant) |

   </center>

    ![Web Config dosyası](media/embed-sample-for-customers/embed-sample-for-customers-030.png)

### <a name="application-id"></a>Uygulama Kimliği

Bu öznitelik her iki AuthenticationType ayarı (ana hesap ve [hizmet sorumlusu](embed-service-principal.md)) için de gereklidir.

**applicationId** bilgilerini **Azure**’daki **Uygulama Kimliği** ile doldurun. Uygulama, izin istediğiniz kullanıcılara kendini tanıtmak için **applicationId** değerini kullanır.

**applicationId** değerini almak için aşağıdaki adımları izleyin:

1. [Azure portalında](https://portal.azure.com) oturum açın.

2. Sol gezinti bölmesinde **Tüm Hizmetler**'i, sonra da **Uygulama Kayıtları**'nı seçin.

    ![Uygulama kaydı araması](media/embed-sample-for-customers/embed-sample-for-customers-003.png)

3. **applicationId** değerinin gerektiği uygulamayı seçin.

    ![Uygulama Seçme](media/embed-sample-for-customers/embed-sample-for-customers-006.png)

4. GUID olarak listelenen bir **Uygulama Kimliği** vardır. Bu **Uygulama Kimliği**’ni uygulamanın **applicationId** değeri olarak kullanın.

    ![applicationId](media/embed-sample-for-customers/embed-sample-for-customers-007.png)

### <a name="workspace-id"></a>Çalışma Alanı Kimliği

Bu öznitelik her iki AuthenticationType ayarı (ana hesap ve [hizmet sorumlusu](embed-service-principal.md)) için de gereklidir.

**workspaceId** bilgisini Power BI’daki çalışma alanı (grup) GUID’si ile doldurun. Bu bilgiyi Power BI hizmetinin oturumu açıkken URL'den alabileceğiniz gibi Powershell'i kullanarak da alabilirsiniz.

URL <br>

![workspaceId](media/embed-sample-for-customers/embed-sample-for-customers-031.png)

Powershell <br>

```powershell
Get-PowerBIworkspace -name "App Owns Embed Test"
```

   ![powershell'den workspaceId](media/embed-sample-for-customers/embed-sample-for-customers-031-ps.png)

### <a name="report-id"></a>Rapor Kimliği

Bu öznitelik her iki AuthenticationType ayarı (ana hesap ve [hizmet sorumlusu](embed-service-principal.md)) için de gereklidir.

**reportId** bilgisini Power BI’daki rapor GUID’si ile doldurun. Bu bilgiyi Power BI hizmetinin oturumu açıkken URL'den alabileceğiniz gibi Powershell'i kullanarak da alabilirsiniz.

URL<br>

![reportId](media/embed-sample-for-customers/embed-sample-for-customers-032.png)

Powershell <br>

```powershell
Get-PowerBIworkspace -name "App Owns Embed Test" | Get-PowerBIReport
```

![powershell'den reportId](media/embed-sample-for-customers/embed-sample-for-customers-032-ps.png)

### <a name="power-bi-username-and-password"></a>Power BI kullanıcı adı ve parolası

Bu öznitelikler yalnızca AuthenticationType ayarı ana hesap olduğunda gereklidir.

Kimlik doğrulaması için [hizmet sorumlusu](embed-service-principal.md) kullanıyorsanız, kullanıcı adı ve parola özniteliklerini doldurmanız gerekmez.

* **pbiUsername** bilgisini Power BI ana hesabıyla doldurun.
* **pbiPassword** bilgisini Power BI ana hesabının parolasıyla doldurun.

### <a name="application-secret"></a>Uygulama gizli dizisi

Bu öznitelik yalnızca [hizmet sorumlusu](embed-service-principal.md) AuthenticationType ayarı için gereklidir.

**ApplicationSecret** alanına **Azure**'daki **Uygulama kayıtları** bölümünden alacağınız **Anahtarlar** bilgilerini girin.  Bu öznitelik [hizmet sorumlusu](embed-service-principal.md) kullanıldığında çalışır.

**ApplicationSecret** değerini almak için aşağıdaki adımları izleyin:

1. [Azure portalında](https://portal.azure.com) oturum açın.

2. Sol gezinti bölmesinde **Tüm hizmetler**'i, sonra da **Uygulama kayıtları**'nı seçin.

    ![Uygulama kaydı araması](media/embed-sample-for-customers/embed-sample-for-customers-003.png)

3. **ApplicationSecret** değerini kullanması gereken uygulamayı seçin.

    ![Bir uygulama seçin](media/embed-sample-for-customers/embed-sample-for-customers-0038.png)

4. **Yönet**’in altında **Sertifikalar ve gizli diziler**’i seçin.

5. **Yeni istemci gizli dizileri**’ni seçin.

6. **Açıklama** kutusuna bir ad girin ve bir süre seçin. Ardından **Kaydet**’i seçerek uygulamanız için **Değer**’i alın. Anahtar değerini kaydettikten sonra **Anahtarlar** bölmesini kapattığınızda değer alanı yalnızca gizlenmiş olarak gösterilir. Bu aşamada anahtar değerini alamazsınız. Anahtar değerini kaybederseniz Azure portalında yeni bir anahtar değeri oluşturun.

    ![Anahtar değeri](media/embed-sample-for-customers/embed-sample-for-customers-042.png)

### <a name="tenant"></a>Kiracı

Bu öznitelik yalnızca [hizmet sorumlusu](embed-service-principal.md) AuthenticationType ayarı için gereklidir.

**tenant** bilgisini Azure kiracı kimliğinizle doldurun. Bu bilgiyi Power BI hizmetinin oturumu açıkken [Azure AD yönetim merkezinden](/onedrive/find-your-office-365-tenant-id) alabileceğiniz gibi Powershell'i kullanarak da alabilirsiniz.

### <a name="run-the-application"></a>Uygulamayı çalıştırma

1. **Visual Studio**’da **Çalıştır**’ı seçin.

    ![Uygulamayı çalıştırma](media/embed-sample-for-customers/embed-sample-for-customers-033.png)

2. Ardından **Rapor Ekle**’yi seçin. Test etmeyi seçtiğiniz içeriğe (raporlar, panolar veya kutucuklar) bağlı olarak uygulamada bu seçeneği belirleyin.

    ![İçerik seçme](media/embed-sample-for-customers/embed-sample-for-customers-034.png)

3. Artık raporu örnek uygulamada görüntüleyebilirsiniz.

    ![Uygulamayı görüntüleme](media/embed-sample-for-customers/embed-sample-for-customers-035.png)

## <a name="embed-content-within-your-application"></a>İçeriği uygulamanızın içine ekleme

İçeriğinizi ekleme adımları [Power BI REST API’leri](https://docs.microsoft.com/rest/api/power-bi/) ile uygulanabilse de, bu makalede açıklanan örnek kodlar **.NET SDK** ile hazırlanır.

Uygulamanıza müşterileriniz için içerik ekleme işlemi, **Azure AD**’den ana hesabınız veya [hizmet sorumlunuz](embed-service-principal.md) için bir **erişim belirteci** alınmasını gerektirir. [Power BI REST API’lerine](https://docs.microsoft.com/rest/api/power-bi/) çağrı yapmadan önce, Power BI uygulamanız için [Azure AD erişim belirteci](get-azuread-access-token.md#access-token-for-non-power-bi-users-app-owns-data) almanız gerekir.

**Erişim belirtecinizle** Power BI İstemcisi'ni oluşturmak için, [Power BI REST API'leriyle](https://docs.microsoft.com/rest/api/power-bi/) etkileşim kurmanızı sağlayacak Power BI istemci nesnenizi oluşturmanız gerekir. Power BI istemci nesnesini oluşturmak için **AccessToken** öğesini ***Microsoft.Rest.TokenCredentials*** nesnesine sarmanız gerekir.

```csharp
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.Rest;
using Microsoft.PowerBI.Api.V2;

var tokenCredentials = new TokenCredentials(authenticationResult.AccessToken, "Bearer");

// Create a Power BI Client object. it's used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Your code to embed items.
}
```

### <a name="get-the-content-item-you-want-to-embed"></a>Eklemek istediğiniz içerik öğesini alma

Eklemek istediğiniz öğeye ilişkin bir başvuru almak için Power BI istemci nesnesini kullanabilirsiniz.

Burada belirli bir çalışma alanının ilk raporunu nasıl alacağınızı gösteren bir kod örneği vardır.

*Eklemek istediğiniz içerik öğesini (rapor, pano veya kutucuk) alma örneği, [örnek uygulama](https://github.com/Microsoft/PowerBI-Developer-Samples) içindeki Services\EmbedService.cs dosyasında sağlanır.*

```csharp
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// You need to provide the workspaceId where the dashboard resides.
ODataResponseListReport reports = await client.Reports.GetReportsInGroupAsync(workspaceId);

// Get the first report in the group.
Report report = reports.Value.FirstOrDefault();
```

### <a name="create-the-embed-token"></a>Ekleme belirtecini oluşturma
JavaScript API’sinden kullanılabilecek bir ekleme belirteci oluşturun. İki tür API vardır; ilk grup her biri belirli bir öğe için ekleme belirteci oluşturan beş API içerir. Yalnızca bir API içeren ikinci grup ise birden çok öğe eklemek için kullanılabilecek bir belirteç üretir.

**Belirli bir öğe için ekleme belirteci oluşturmaya yönelik API'ler**

Bu API’lerle oluşturulan ekleme belirteci, eklediğiniz öğeye özeldir. Bu API'lerle bir Power BI öğesi (rapor, pano veya kutucuk gibi) eklediğiniz her durumda öğe için yeni bir ekleme belirteci oluşturmanız gerekir.
* [Panolar GenerateTokenInGroup](https://docs.microsoft.com/rest/api/power-bi/embedtoken/dashboards_generatetokeningroup)
* [Veri kümeleri GenerateTokenInGroup](https://docs.microsoft.com/rest/api/power-bi/embedtoken/datasets_generatetokeningroup)
* [Raporlar GenerateTokenForCreateInGroup](https://docs.microsoft.com/rest/api/power-bi/embedtoken/reports_generatetokenforcreateingroup)
* [Raporlar GenerateTokenInGroup](https://docs.microsoft.com/rest/api/power-bi/embedtoken/reports_generatetokeningroup)
* [Kutucuklar GenerateTokenInGroup](https://docs.microsoft.com/rest/api/power-bi/embedtoken/tiles_generatetokeningroup)

Bir rapor, pano veya kutucuk için ekleme belirteci oluşturma örnekleri, [örnek uygulama](https://github.com/Microsoft/PowerBI-Developer-Samples) içinde aşağıdaki dosyalarda bulunabilir.
* Services\EmbedService.cs
* Models\EmbedConfig.cs
* Models\TileEmbedConfig.cs

Raporlar GenerateTokenInGroup ekleme belirteci API’sini kullanmaya yönelik bir kod örneği aşağıda verilmiştir.
```csharp
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// Generate Embed Token.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");
EmbedToken tokenResponse = client.Reports.GenerateTokenInGroup(workspaceId, report.Id, generateTokenRequestParameters);

// Generate Embed Configuration.
var embedConfig = new EmbedConfig()
{
    EmbedToken = tokenResponse,
    EmbedUrl = report.EmbedUrl,
    Id = report.Id
};
```

**Birden çok öğe için ekleme belirteci oluşturmaya yönelik API**<a id="multiEmbedToken"></a>

[Belirteç Oluşturma](https://docs.microsoft.com/rest/api/power-bi/embedtoken/generatetoken) ekleme API’si, birden çok öğeyi eklemek için kullanılabilecek bir belirteç oluşturur.

Ayrıca, bir raporu eklerken veri kümesini dinamik olarak seçmek için kullanılabilir. API’nin bu kullanımı hakkında daha fazla bilgi için bkz. [dinamik bağlama](embed-dynamic-binding.md).


Bu API'yi kullanma örneklerinden biri aşağıda verilmiştir.
 
```csharp
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

var reports = new List<GenerateTokenRequestV2Report>()
{ 
    new GenerateTokenRequestV2Report()
    {
        AllowEdit = false,
        Id = report1.Id
    },
    new GenerateTokenRequestV2Report()
    {
        AllowEdit = true,
        Id = report2.Id
    }
};

var datasets= new List<GenerateTokenRequestV2Dataset>()
{
    new GenerateTokenRequestV2Dataset(dataset1.Id),
    new GenerateTokenRequestV2Dataset(dataset2.Id),
    new GenerateTokenRequestV2Dataset(dataset3.Id),
};

var targetWorkspaces = new List<GenerateTokenRequestV2TargetWorkspace>()
{
    new GenerateTokenRequestV2TargetWorkspace(workspace1.Id),
    new GenerateTokenRequestV2TargetWorkspace(workspace2.Id),
};

var request = new GenerateTokenRequestV2()
{
    Datasets = datasetsRequestDetails ?? null,
    Reports = reportsRequestDetails,
    TargetWorkspaces = targetWSRequestdetials ?? null,
};

var token = client.GetClient().EmbedToken.GenerateToken(request);
```

### <a name="load-an-item-using-javascript"></a>JavaScript kullanarak öğe yükleme

JavaScript kullanarak web sayfanızdaki bir div öğesine rapor yükleyebilirsiniz.

JavaScript API kullanan tam bir örnek için [Playground aracı](https://microsoft.github.io/PowerBI-JavaScript/demo)'nı kullanabilirsiniz. Deneme Alanı aracı, farklı türde Power BI Embedded örnekleri ile yürütmenin hızlı bir yoludur. Ayrıca [PowerBI-JavaScript wiki](https://github.com/Microsoft/powerbi-javascript/wiki) sayfasını ziyaret ederek JavaScript API’si hakkında daha fazla bilgi alabilirsiniz.

Burada, **EmbedConfig** modeliyle **TileEmbedConfig** modelinin yanı sıra rapor görünümünü de kullanan bir örnek verilmiştir.

*Rapor, pano veya kutucuk görünümü ekleme örneği, [örnek uygulama](#embed-content-using-the-sample-application) içindeki Views\Home\EmbedReport.cshtml, Views\Home\EmbedDashboard.cshtml veya Views\Home\Embedtile.cshtml dosyasında sağlanır.*

```javascript
<script src="~/scripts/powerbi.js"></script>
<div id="reportContainer"></div>
<script>
    // Read embed application token from Model
    var accessToken = "@Model.EmbedToken.Token";

    // Read embed URL from Model
    var embedUrl = "@Html.Raw(Model.EmbedUrl)";

    // Read report Id from Model
    var embedReportId = "@Model.Id";

    // Get models. models contains enums that can be used.
    var models = window['powerbi-client'].models;

    // Embed configuration used to describe what and how to embed.
    // This object is used when calling powerbi.embed.
    // This also includes settings and options such as filters.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'report',
        tokenType: models.TokenType.Embed,
        accessToken: accessToken,
        embedUrl: embedUrl,
        id: embedReportId,
        permissions: models.Permissions.All,
        settings: {
            filterPaneEnabled: true,
            navContentPaneEnabled: true
        }
    };

    // Get a reference to the embedded report HTML element
    var reportContainer = $('#reportContainer')[0];

    // Embed the report and display it within the div container.
    var report = powerbi.embed(reportContainer, config);
</script>
```

## <a name="move-to-production"></a>Üretime geçme

Uygulamanızın geliştirme aşamasını tamamladığınıza göre şimdi adanmış kapasite ile çalışma alanınızı destekleme işlemine geçmelisiniz. 

> [!Important]
> Üretime geçmek için adanmış kapasite gerekir. Tüm çalışma alanları (raporları veya panoları içeren çalışma alanı ile veri kümesini içeren çalışma alanı) bir kapasiteye atanmalıdır.

### <a name="create-a-dedicated-capacity"></a>Adanmış kapasite oluşturma

Adanmış kapasite oluşturduğunuzda, müşteriniz için özel olarak ayrılmış bir kaynaktan yararlanabilirsiniz. İki tür kapasiteden birini seçebilirsiniz:
* **Power BI Premium** - *EM* ve *P* şeklinde iki SKU ailesinde kullanılabilen kiracı düzeyindeki bir Office 356 aboneliği. Power BI içeriği eklerken bu çözüm *Power BI ekleme* olarak adlandırılır. Bu abonelikle ilgili daha fazla bilgi için bkz. [Power BI Premium nedir?](../service-premium-what-is.md)
* **Azure Power BI Embedded** - [Microsoft Azure portalından](https://portal.azure.com) ayrılmış kapasite satın alabilirsiniz. Bu abonelik *A* SKU’ları kullanır. Power BI Embedded kapasitesi oluşturma hakkında ayrıntılı bilgi için bkz. [Azure portalında Power BI Embedded kapasitesi oluşturma](azure-pbie-create-capacity.md).
> [!NOTE]
> A SKU’larla, ÜCRETSİZ Power BI lisansını kullanarak Power BI içeriğine erişemezsiniz.

Aşağıdaki tabloda her SKU'nun kaynakları ve limitleri açıklanmaktadır. İhtiyaçlarınıza en uygun kapasiteyi öğrenmek için [Senaryom için hangi SKU’yu satın almalıyım?](https://docs.microsoft.com/power-bi/developer/embedded-faq#power-bi-now-offers-three-skus-for-embedding-a-skus-em-skus-and-p-skus-which-one-should-i-purchase-for-my-scenario) tablosuna bakın.

| Kapasite Düğümleri | Toplam sanal çekirdek sayısı | Arka uç sanal çekirdek sayısı | RAM (GB) | Ön uç sanal çekirdek sayısı | DirectQuery/Canlı Bağlantı (saniyede) | Model Yenileme Paralelliği |
| --- | --- | --- | --- | --- | --- | --- |
| EM1/A1 | 1 | 0,5 | 2.5 | 0,5 | 3,75 | 1 |
| EM2/A2 | 2 | 1 | 5 | 1 | 7,5 | 2 |
| EM3/A3 | 4 | 2 | 10 | 2 | 15 | 3 |
| P1/A4 | 8 | 4 | 25 | 4 | 30 | 6 |
| P2/A5 | 16 | 8 | 50 | 8 | 60 | 12 |
| P3/A6 | 32 | 16 | 100 | 16 | 120 | 24 |
| | | | | | | |

### <a name="development-testing"></a>Geliştirme testi

Pro lisanslarına sahip ekleme belirteçlerinin kullanılması, geliştirme testlerine yöneliktir. Bu nedenle, bir Power BI ana hesabının veya hizmet sorumlusunun oluşturabileceği ekleme belirteçlerinin sayısı sınırlıdır. Adanmış kapasite için üretim ortamında ekleme yapmak gerekir. Adanmış kapasiteyle oluşturabileceğiniz ekleme belirteçlerinin sayısıyla ilgili bir sınır yoktur. Geçerli eklenmiş kullanımı yüzde cinsinden gösteren kullanım değerini denetlemek için [Kullanılabilir Özellikler](https://docs.microsoft.com/rest/api/power-bi/availablefeatures/getavailablefeatures) bölümüne gidin. Kullanım miktarı ana hesabı temel alır.

Daha fazla bilgi için [Tümleşik analiz kapasite planlaması teknik incelemesi](https://aka.ms/pbiewhitepaper).

### <a name="assign-a-workspace-to-a-dedicated-capacity"></a>Adanmış kapasiteye çalışma alanı atama

Adanmış kapasite oluşturduktan sonra, çalışma alanınızı bu adanmış kapasiteye atayabilirsiniz.

[Hizmet sorumlusu](embed-service-principal.md) kullanarak çalışma alanına adanmış kapasite atamak için [Power BI REST API'sini](https://docs.microsoft.com/rest/api/power-bi/capacities/groups_assigntocapacity) kullanın. Power BI REST API'lerini kullanırken [hizmet sorumlusu nesne kimliğini](embed-service-principal.md#how-to-get-the-service-principal-object-id) kullandığınızdan emin olun.

**Ana hesap** kullanarak çalışma alanına adanmış kapasite atamak için aşağıdaki adımları izleyin.

1. **Power BI hizmetinde**, çalışma alanlarını genişletin ve içeriğinizi eklemek için kullandığınız çalışma alanına yönelik olan üç noktayı seçin. Ardından **Çalışma alanlarını düzenle**’yi seçin.

    ![Çalışma Alanını Düzenleme](media/embed-sample-for-customers/embed-sample-for-customers-036.png)

2. **Gelişmiş**’i genişletin, ardından **Adanmış kapasite**’yi etkinleştirin, sonra da oluşturduğunuz adanmış kapasiteyi seçin. Sonra **Kaydet**'i seçin.

    ![Adanmış kapasite atama](media/embed-sample-for-customers/embed-sample-for-customers-024.png)

3. **Kaydet**’i seçtikten sonra, çalışma alanının yanında bir **baklava** işareti görmeniz gerekir.

    ![Kapasiteye bağlanmış çalışma alanı](media/embed-sample-for-customers/embed-sample-for-customers-037.png)

## <a name="next-steps"></a>Sonraki adımlar

Bu öğreticide müşterileriniz için bir uygulamaya Power BI içeriği eklemeyi öğrendiniz. Kuruluşunuz için de Power BI içeriği ekleme denemeleri yapabilirsiniz.

> [!div class="nextstepaction"]
>[Kuruluşunuz için ekleme](embed-sample-for-your-organization.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
