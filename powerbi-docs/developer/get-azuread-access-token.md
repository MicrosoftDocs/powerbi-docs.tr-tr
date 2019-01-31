---
title: Kullanıcıların kimliğini doğrulama ve uygulamanız için Azure AD erişim belirteci alma
description: Power BI içeriği eklemek üzere bir uygulamayı Azure Active Directory'ye kaydetmeyi öğrenin.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 08/11/2017
ms.author: maghan
ms.openlocfilehash: f585d5a48ab38124d17110049cd7dd7d5da45164
ms.sourcegitcommit: a36f82224e68fdd3489944c9c3c03a93e4068cc5
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/31/2019
ms.locfileid: "55428774"
---
# <a name="authenticate-users-and-get-an-azure-ad-access-token-for-your-power-bi-app"></a>Power BI uygulamanız için kullanıcıların kimliğini doğrulama ve Azure AD erişim belirteci alma
Power BI uygulamalarınızda kullanıcıların kimliğini doğrulamayı ve REST API ile kullanmak üzere bir erişim belirteci almayı öğrenin.

Power BI REST API'sine çağrı yapmadan önce Azure Active Directory (Azure AD) **kimlik doğrulama erişim belirteci** (erişim belirteci) almanız gerekir. **Erişim belirteci**, uygulamanıza **Power BI** panolarına, kutucuklarına ve raporlarına erişim izni vermek için kullanılır. Azure Active Directory **erişim belirteci** akışı hakkında daha fazla bilgi edinmek için bkz. [Azure AD Yetkilendirme Kodu Verme Akışı](https://msdn.microsoft.com/library/azure/dn645542.aspx).

Erişim belirtecini alma yöntemi, içeriği ekleme şeklinize bağlı olarak değişiklik gösterir. Bu makalede iki farklı yaklaşım kullanılmaktadır.

## <a name="access-token-for-power-bi-users-user-owns-data"></a>Power BI kullanıcıları için erişim belirteci (veriler kullanıcıya aittir)
Bu örnek, kullanıcılarınızın kurumsal oturum açma bilgileri ile Azure AD'de oturum açtığı durumlar için geçerlidir. Bu yöntemi Power BI hizmetinde erişim sahibi oldukları içeriğe erişen Power BI kullanıcıları için içerik ekleyeceğinizde kullanabilirsiniz.

### <a name="get-an-authorization-code-from-azure-ad"></a>Azure AD'den yetkilendirme kodu alma
**Erişim belirteci** almanın ilk adımı, **Azure AD**'den bir yetkilendirme kodu almaktır. Bunu yapmak için aşağıdaki özelliklere sahip bir sorgu dizesi oluşturmanız ve bunu **Azure AD**'ye yönlendirmeniz gerekir.

**Yetkilendirme kodu sorgu dizesi**

```
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
    {"redirect_uri", "http://localhost:13526/Redirect"}
};
```

Sorgu dizesi oluşturduktan sonra **Azure AD**'ye yönlendirerek **yetkilendirme kodu** alabilirsiniz.  Aşağıda **yetkilendirme kodu** sorgu dizesi oluşturmak ve **Azure AD**'ye yönlendirmek için kullanabileceğiniz tam kapsamlı bir C# yöntemi verilmiştir. Yetkilendirme kodunu aldıktan sonra **erişim belirtecini** almak için bu **yetkilendirme kodunu** kullanmanız gerekir.

Sonraki adımda redirect.aspx.cs dosyasında, [AuthenticationContext.AcquireTokenByAuthorizationCode](https://msdn.microsoft.com/library/azure/dn479531.aspx) çağrısı yaparak belirteci oluşturabilirsiniz.

**Yetkilendirme kodunu alma**

```
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
        {"redirect_uri", "http://localhost:13526/Redirect"}
    };

    //Create sign-in query string
    var queryString = HttpUtility.ParseQueryString(string.Empty);
    queryString.Add(@params);

    //Redirect authority
    //Authority Uri is an Azure resource that takes a client id to get an Access token
    // AADAuthorityUri = https://login.microsoftonline.net/common/
    string authorityUri = Properties.Settings.Default.AADAuthorityUri;
    var authUri = String.Format("{0}?{1}", authorityUri, queryString);
    Response.Redirect(authUri);
}
```

### <a name="get-an-access-token-from-authorization-code"></a>Yetkilendirme kodundan erişim belirteci alma
Azure AD'den bir yetkilendirme kodu aldınız. **Azure AD**, **yetkilendirme kodu** ile web uygulamanıza yönlendirme yaptığında **yetkilendirme kodunu** kullanarak erişim belirteci alabilirsiniz. Aşağıda yönlendirme sayfanızda ve default.aspx sayfanızın Page_Load olayında kullanabileceğiniz örnek C# kodu verilmiştir.

**Microsoft.IdentityModel.Clients.ActiveDirectory** ad alanını [Active Directory Authentication Library](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/) NuGet paketinden alabilirsiniz.

```
Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory
```

**Redirect.aspx.cs**

```
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

**Default.aspx**

```
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
Bu yaklaşım genelde verilere erişim izninin uygulamada olduğu ISV türü uygulamalarda kullanılır. Kullanıcıların Power BI kullanıcısı olması şartı yoktur ve son kullanıcılar için kimlik doğrulaması ve erişim denetimi uygulama tarafından gerçekleştirilir.

Bu yaklaşım için Power BI Pro kullanıcısı olan tek bir *ana* hesap kullanmanız gerekir. Bu hesabın kimlik bilgileri uygulamada kayıtlıdır. Uygulama bu kayıtlı kimlik bilgilerini kullanarak Azure AD ile kimlik doğrulaması gerçekleştirir. Aşağıdaki örnek kod [App owns data örneğinden](https://github.com/guyinacube/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data) alınmıştır

**HomeController.cs**

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;

// Create a user password cradentials.
var credential = new UserPasswordCredential(Username, Password);

// Authenticate using created credentials
var authenticationContext = new AuthenticationContext(AuthorityUrl);
var authenticationResult = await authenticationContext.AcquireTokenAsync(ResourceUrl, ClientId, credential);

if (authenticationResult == null)
{
    return View(new EmbedConfig()
    {
        ErrorMessage = "Authentication Failed."
    });
}

var tokenCredentials = new TokenCredentials(authenticationResult.AccessToken, "Bearer");
```

**await** işlevini kullanma hakkında bilgi almak için bkz. [await (C# Başvurusu)](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/await)

## <a name="next-steps"></a>Sonraki adımlar
Erişim belirtecini aldığınıza göre Power BI REST API'sini çağırarak içerik ekleyebilirsiniz. İçerik ekleme hakkında bilgi almak için bkz. [Power BI panolarınızı, raporlarınızı ve kutucuklarınızı ekleme](embed-sample-for-customers.md#embed-your-content-within-your-application).

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)