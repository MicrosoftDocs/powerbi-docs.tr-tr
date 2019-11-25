---
title: Kimlik doğrulaması erişim belirteci alma
description: Veri göndermeye ilişkin adım adım kılavuz - Kimlik doğrulaması erişim belirteci alma
author: KesemSharabi
ms.author: kesharab
ms.reviewer: madia
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 05/29/2019
ms.openlocfilehash: 5a96085791e8bd211ebe26b2d149c7b2ad92fc2f
ms.sourcegitcommit: c395fe83d63641e0fbd7c98e51bbab224805bbcc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74264839"
---
# <a name="step-2-get-an-authentication-access-token"></a>2\. Adım: Kimlik doğrulaması erişim belirteci alma

Bu makale, [Power BI veri kümelerine veri gönderme](walkthrough-push-data.md) serisinin ikinci adımıdır.

Birinci adımda [Azure AD'de bir istemci uygulamasını kaydettiniz](walkthrough-push-data-register-app-with-azure-ad.md). Bu adımda bir kimlik doğrulaması erişim belirteci alırsınız. Uygulamanıza güvenli oturum açma ve yetkilendirme sağlamak için Power BI uygulamaları Azure Active Directory ile tümleştirilmiştir. Uygulamanız Azure AD'de kimlik doğrulaması yapmak ve Power BI kaynaklarına erişmek için bir belirteç kullanılır.

## <a name="get-an-authentication-access-token"></a>Kimlik doğrulaması erişim belirteci alma

Başlamadan önce, [Power BI veri kümelerine veri gönderme](walkthrough-push-data.md) serisinin [önceki adımını](walkthrough-push-data-register-app-with-azure-ad.md) tamamladığınızdan emin olun. 

Bu yordam için Visual Studio 2015 veya üzeri gerekir.

1. Visual Studio'da yeni bir C# **Konsol Uygulaması** projesi oluşturun.

2. [.NET NuGet paketi için Azure AD Kimlik Doğrulama Kitaplığı](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/2.22.302111727)'nı yükleyin. .Net uygulamanıza kimlik doğrulaması güvenlik belirtecini almak için bu paket gerekir. 

     a. **Araçlar** > **NuGet Paket Yöneticisi** > **Paket Yöneticisi Konsolu**'nu seçin.

     b. **Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612** girin

     c. Program.cs dosyasına `using Microsoft.IdentityModel.Clients.ActiveDirectory;` ekleyin.

3. Bu adımlardan sonra listelenen örnek kodu Program.cs'ye ekleyin.

4. "{ClientID}" terimini [serinin önceki makalesinde](walkthrough-push-data-register-app-with-azure-ad.md) uygulamanızı kaydederken aldığınız **İstemci Kimliği**'yle değiştirin.

5. Konsol uygulamanızı çalıştırın ve Power BI hesabınızda oturum açın. 

   Konsol penceresinde bir belirteç dizesi gösterilmelidir.

**Kimlik doğrulama güvenlik belirtecini almak için örnek kod**

Bu kodu Program {...}'e ekleyin.

* İşlemleri çağırmak için bir belirteç değişkeni: 
  
  ```csharp
  private static string token = string.Empty;
  
  static void Main(string[] args)
  {
  }
  ```
* static void Main(string[] args) bölümüne:
  
  ```csharp
  static void Main(string[] args)
  {
    //Get an authentication access token
    token = GetToken();
  }
  ```
* GetToken() yöntemi ekleyin:

```csharp
       #region Get an authentication access token
       private static string GetToken()
       {
           // TODO: Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612
           // and add using Microsoft.IdentityModel.Clients.ActiveDirectory

           //The client id that Azure AD created when you registered your client app.
           string clientID = "{Client_ID}";

           //RedirectUri you used when you register your app.
           //For a client app, a redirect uri gives Azure AD more details on the application that it will authenticate.
           // You can use this redirect uri for your client app
           string redirectUri = "https://login.live.com/oauth20_desktop.srf";

           //Resource Uri for Power BI API
           string resourceUri = "https://analysis.windows.net/powerbi/api";

           //OAuth2 authority Uri
           string authorityUri = "https://login.microsoftonline.net/common/";

           //Get access token:
           // To call a Power BI REST operation, create an instance of AuthenticationContext and call AcquireToken
           // AuthenticationContext is part of the Active Directory Authentication Library NuGet package
           // To install the Active Directory Authentication Library NuGet package in Visual Studio,
           //  run "Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory" from the nuget Package Manager Console.

           // AcquireToken will acquire an Azure access token
           // Call AcquireToken to get an Azure token from Azure Active Directory token issuance endpoint
           AuthenticationContext authContext = new AuthenticationContext(authorityUri);
           string token = authContext.AcquireToken(resourceUri, clientID, new Uri(redirectUri)).AccessToken;

           Console.WriteLine(token);
           Console.ReadLine();

           return token;
       }

       #endregion
```

Bir kimlik doğrulama belirteci aldıktan sonra herhangi bir Power BI işlemini çağırabilirsiniz.

Bu serinin sonraki makalesinde [Power BI'da veri kümesi oluşturma](walkthrough-push-data-create-dataset.md) işlemi gösterilir.


## <a name="complete-code-listing"></a>Tam kod listesi

```csharp
using System;
using Microsoft.IdentityModel.Clients.ActiveDirectory;

namespace walkthrough_push_data
{
    class Program
    {
        private static string token = string.Empty;

        static void Main(string[] args)
        {

            //Get an authentication access token
            token = GetToken();

        }

        #region Get an authentication access token
        private static string GetToken()
        {
            // TODO: Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612
            // and add using Microsoft.IdentityModel.Clients.ActiveDirectory

            //The client id that Azure AD created when you registered your client app.
            string clientID = "{Client_ID}";

            //RedirectUri you used when you register your app.
            //For a client app, a redirect uri gives Azure AD more details on the application that it will authenticate.
            // You can use this redirect uri for your client app
            string redirectUri = "https://login.live.com/oauth20_desktop.srf";

            //Resource Uri for Power BI API
            string resourceUri = "https://analysis.windows.net/powerbi/api";

            //OAuth2 authority Uri
            string authorityUri = "https://login.microsoftonline.com/common/";

            //Get access token:
            // To call a Power BI REST operation, create an instance of AuthenticationContext and call AcquireToken
            // AuthenticationContext is part of the Active Directory Authentication Library NuGet package
            // To install the Active Directory Authentication Library NuGet package in Visual Studio,
            //  run "Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory" from the nuget Package Manager Console.

            // AcquireToken will acquire an Azure access token
            // Call AcquireToken to get an Azure token from Azure Active Directory token issuance endpoint
            AuthenticationContext authContext = new AuthenticationContext(authorityUri);
            string token = authContext.AcquireToken(resourceUri, clientID, new Uri(redirectUri)).AccessToken;

            Console.WriteLine(token);
            Console.ReadLine();

            return token;
        }

        #endregion

    }
}
```



## <a name="next-steps"></a>Sonraki adımlar

[Bu serinin sonraki makalesi > Power BI'da veri kümesi oluşturma](walkthrough-push-data-create-dataset.md)

[Overview of Power BI REST API (Power BI REST API'sine Genel Bakış)](overview-of-power-bi-rest-api.md)  
[Power BI REST API'leri](https://docs.microsoft.com/rest/api/power-bi/)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)