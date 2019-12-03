---
title: Kullanıcıların kimliğini doğrulama ve uygulamanız için Azure AD erişim belirteci alma
description: Power BI içeriği eklemek üzere bir uygulamayı Azure Active Directory'ye kaydetmeyi öğrenin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/04/2019
ms.openlocfilehash: cac59a4689eecd75c53ca1c62d7b097438b2ae53
ms.sourcegitcommit: 7f27b9eb0e001034e672050735ab659b834c54a3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74310829"
---
# <a name="get-an-azure-ad-access-token-for-your-power-bi-application"></a>Power BI uygulamanız için Azure AD erişim belirteci alma

Bu makalede Power BI uygulamalarınızda kullanıcıların kimliğini doğrulama ve [Power BI REST API](https://docs.microsoft.com/rest/api/power-bi/) ile kullanmak üzere bir erişim belirteci alma işlemleri gösterilir.

Uygulamanız REST API çağrısı yapmadan önce Azure Active Directory (Azure AD) **kimlik doğrulama erişim belirteci** almanız gerekir. Uygulamanız Power BI panolarına, kutucuklarına ve raporlarına erişmek için bir belirteç kullanır. Daha fazla bilgi edinmek için bkz. [OAuth 2.0 kod verme akışı kullanılarak Azure Active Directory web uygulamalarına erişimi yetkilendirme](https://docs.microsoft.com/azure/active-directory/develop/v1-protocols-oauth-code).

Erişim belirtecini alma yöntemi, içeriği ekleme şeklinize bağlı olarak değişiklik gösterir. Bu makalede iki farklı yaklaşım gösterilir.

## <a name="access-token-for-power-bi-users-user-owns-data"></a>Power BI kullanıcıları için erişim belirteci (veriler kullanıcıya aittir)

Bu örnek, kullanıcılarınızın kurumsal oturum açma bilgilerini kullanarak Azure AD'de el ile oturum açtığı durumlar için geçerlidir. Bu görev Power BI hizmeti erişimi olan kullanıcılar için içerik eklerken kullanılır.

### <a name="get-an-azure-ad-authorization-code"></a>Azure AD yetkilendirme kodunu alma

**Erişim belirteci** almanın ilk adımı, **Azure AD**'den bir yetkilendirme kodu almaktır. Aşağıdaki özelliklere sahip bir sorgu dizesi oluşturun ve bunu **Azure AD**'ye yönlendirin.

#### <a name="authorization-code-query-string"></a>Yetkilendirme kodu sorgu dizesi

```csharp
var @params = new NameValueCollection
{
    //Azure AD will return an authorization code. 
    //See the Redirect class to see how "code" is used to AcquireTokenByAuthorizationCode
    {"response_type", "code"},

    //Client ID is used by the application to identify themselves to the users that they are requesting permissions from.
    //You get the client id when you register your Azure app.
    {"client_id", Properties.Settings.Default.ClientID},

    //Resource uri to the Power BI resource to be authorized
    // https://analysis.windows.net/powerbi/api
    {"resource", Properties.Settings.Default.PowerBiAPI},

    //After user authenticates, Azure AD will redirect back to the web app
    {"redirect_uri", "https://localhost:13526/Redirect"}
};
```

Sorgu dizesi oluşturduktan sonra **Azure AD**'ye yönlendirerek **yetkilendirme kodu** alabilirsiniz.  Aşağıda **yetkilendirme kodu** sorgu dizesi oluşturmak ve **Azure AD**'ye yönlendirmek için kullanabileceğiniz tam kapsamlı bir C# yöntemi verilmiştir. Ardından **yetkilendirme kodunu** kullanarak bir **erişim belirteci** alırsınız.

Sonraki adımda redirect.aspx.cs dosyasında, [AuthenticationContext.AcquireTokenByAuthorizationCode](https://docs.microsoft.com/dotnet/api/microsoft.identitymodel.clients.activedirectory.authenticationcontext.acquiretokenbyauthorizationcodeasync?view=azure-dotnet#Microsoft_IdentityModel_Clients_ActiveDirectory_AuthenticationContext_AcquireTokenByAuthorizationCodeAsync_System_String_System_Uri_Microsoft_IdentityModel_Clients_ActiveDirectory_ClientCredential_System_String_) çağrısı yaparak belirteç oluşturulur.

#### <a name="get-authorization-code"></a>Yetkilendirme kodunu alma

```csharp
protected void signInButton_Click(object sender, EventArgs e)
{
    //Create a query string
    //Create a sign-in NameValueCollection for query string
    var @params = new NameValueCollection
    {
        //Azure AD will return an authorization code. 
        //See the Redirect class to see how "code" is used to AcquireTokenByAuthorizationCode
        {"response_type", "code"},

        //Client ID is used by the application to identify themselves to the users that they are requesting permissions from. 
        //You get the client id when you register your Azure app.
        {"client_id", Properties.Settings.Default.ClientID},

        //Resource uri to the Power BI resource to be authorized
        // https://analysis.windows.net/powerbi/api
        {"resource", Properties.Settings.Default.PowerBiAPI},

        //After user authenticates, Azure AD will redirect back to the web app
        {"redirect_uri", "https://localhost:13526/Redirect"}
    };

    //Create sign-in query string
    var queryString = HttpUtility.ParseQueryString(string.Empty);
    queryString.Add(@params);

    //Redirect authority
    //Authority Uri is an Azure resource that takes a client id to get an Access token
    // AADAuthorityUri = https://login.microsoftonline.com/common/
    string authorityUri = Properties.Settings.Default.AADAuthorityUri;
    var authUri = String.Format("{0}?{1}", authorityUri, queryString);
    Response.Redirect(authUri);
}
```

### <a name="get-an-access-token-from-authorization-code"></a>Yetkilendirme kodundan erişim belirteci alma

**Azure AD** **yetkilendirme kodu** ile web uygulamanıza yönlendirme yaptığında, bunu kullanarak erişim belirteci alabilirsiniz. Aşağıda yönlendirme sayfanızda ve default.aspx sayfasının `Page_Load` olayında kullanabileceğiniz örnek C# kodu verilmiştir.

**Microsoft.IdentityModel.Clients.ActiveDirectory** ad alanını [Active Directory Authentication Library](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/) NuGet paketinden alabilirsiniz.

```powershell
Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory
```

#### <a name="redirectaspxcs"></a>Redirect.aspx.cs

```csharp
using Microsoft.IdentityModel.Clients.ActiveDirectory;

protected void Page_Load(object sender, EventArgs e)
{
    //Redirect uri must match the redirect_uri used when requesting Authorization code.
    string redirectUri = String.Format("{0}Redirect", Properties.Settings.Default.RedirectUrl);
    string authorityUri = Properties.Settings.Default.AADAuthorityUri;

    // Get the auth code
    string code = Request.Params.GetValues(0)[0];

    // Get auth token from auth code
    TokenCache TC = new TokenCache();

    AuthenticationContext AC = new AuthenticationContext(authorityUri, TC);
    ClientCredential cc = new ClientCredential
        (Properties.Settings.Default.ClientID,
        Properties.Settings.Default.ClientSecret);

    AuthenticationResult AR = AC.AcquireTokenByAuthorizationCode(code, new Uri(redirectUri), cc);

    //Set Session "authResult" index string to the AuthenticationResult
    Session[_Default.authResultString] = AR;

    //Redirect back to Default.aspx
    Response.Redirect("/Default.aspx");
}
```

#### <a name="defaultaspx"></a>Default.aspx

```csharp
using Microsoft.IdentityModel.Clients.ActiveDirectory;

protected void Page_Load(object sender, EventArgs e)
{

    //Test for AuthenticationResult
    if (Session[authResultString] != null)
    {
        //Get the authentication result from the session
        authResult = (AuthenticationResult)Session[authResultString];

        //Show Power BI Panel
        signInStatus.Visible = true;
        signInButton.Visible = false;

        //Set user and token from authentication result
        userLabel.Text = authResult.UserInfo.DisplayableId;
        accessTokenTextbox.Text = authResult.AccessToken;
    }
}
```

## <a name="access-token-for-non-power-bi-users-app-owns-data"></a>Power BI kullanıcısı olmayan kişiler için erişim belirteci (veriler uygulamaya aittir)

Bu yaklaşım genelde verilere erişim izninin uygulamada olduğu bağımsız yazılım satıcısı (ISV) türü uygulamalarda kullanılır. Kullanıcıların Power BI kullanıcısı olması şart değildir ve kullanıcının kimlik doğrulaması ile erişim denetimi uygulama tarafından gerçekleştirilir.

### <a name="access-token-with-a-master-account"></a>Ana hesapla erişim belirteci

Bu yaklaşım için Power BI Pro kullanıcısı olan tek bir *ana* hesap kullanırsınız. Hesap kimlik bilgileri uygulamada depolanır. Uygulama bu depolanmış kimlik bilgilerini kullanarak Azure AD ile kimlik doğrulaması gerçekleştirir. Aşağıdaki örnek kod [App owns data örneğinden](https://github.com/guyinacube/PowerBI-Developer-Samples) alınmıştır

### <a name="access-token-with-service-principal"></a>Hizmet sorumlusuyla erişim belirteci

Bu yaklaşım için [yalnızca uygulama](embed-service-principal.md) belirteci olan bir **hizmet sorumlusu** kullanırsınız. Uygulama hizmet sorumlusunu kullanarak Azure AD ile kimlik doğrulaması gerçekleştirir. Aşağıdaki örnek kod [App owns data örneğinden](https://github.com/guyinacube/PowerBI-Developer-Samples) alınmıştır

#### <a name="embedservicecs"></a>EmbedService.cs

```csharp
var authenticationContext = new AuthenticationContext(AuthorityUrl);
       AuthenticationResult authenticationResult = null;
       if (AuthenticationType.Equals("MasterUser"))
       {
              // Authentication using master user credentials
              var credential = new UserPasswordCredential(Username, Password);
              authenticationResult = authenticationContext.AcquireTokenAsync(ResourceUrl, ApplicationId, credential).Result;
       }
       else
       {
             // Authentication using app credentials
             var credential = new ClientCredential(ApplicationId, ApplicationSecret);
             authenticationResult = await authenticationContext.AcquireTokenAsync(ResourceUrl, credential);
       }


m_tokenCredentials = new TokenCredentials(authenticationResult.AccessToken, "Bearer");
```

## <a name="troubleshoot"></a>Sorun giderme

Hata iletisi: "'AuthenticationContext' bir 'AcquireToken' tanımı içermiyor ve 'AuthenticationContext' türünde bir ilk bağımsız değişken kabul eden erişilebilir 'AcquireToken' genişletme metodu bulunamadı (bir kullanma yönergeniz veya derleme başvurunuz eksik olabilir mi?)".

   Bu hatayı görürseniz [Microsoft.IdentityModel.Clients.ActiveDirectory](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/2.22.302111727)'yi indirmeyi deneyin.

## <a name="next-steps"></a>Sonraki adımlar

Erişim belirtecini aldığınıza göre Power BI REST API'sini çağırarak içerik ekleyebilirsiniz. Bilgi edinmek için bkz. [Power BI içeriğinizi ekleme](embed-sample-for-customers.md#embed-content-within-your-application).

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
