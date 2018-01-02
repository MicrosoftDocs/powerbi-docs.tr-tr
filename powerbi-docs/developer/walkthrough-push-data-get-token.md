---
title: "Kimlik doğrulaması erişim belirteci alma"
description: "Veri göndermeye ilişkin adım adım kılavuz - Kimlik doğrulaması erişim belirteci alma"
services: powerbi
documentationcenter: 
author: guyinacube
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 08/10/2017
ms.author: asaxton
ms.openlocfilehash: 068baa78315bfc7e4f7078ed47596a480dbe3765
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="step-2-get-an-authentication-access-token"></a>2. Adım: Kimlik doğrulaması erişim belirteci alma
Bu makale, [bir veri kümesine veri gönderme](walkthrough-push-data.md) ayrıntılı kılavuzunun bir parçasıdır.

Bir veri kümesine veri göndermenin **1. adımı** [Uygulamayı Azure AD'ye kaydetme](walkthrough-push-data-register-app-with-azure-ad.md) kapsamında bir istemci uygulamasını Azure AD'ye kaydettiniz. Bu adımda bir kimlik doğrulaması erişim belirteci alırsınız. Power BI uygulamaları **Azure AD** ile tümleştirilerek güvenli oturum açmanız ve uygulamanız için yetkilendirme sağlanır. **Azure AD**'de kimlik doğrulaması ve Power BI kaynaklarına erişim için bir belirteç kullanılır.

Bir kimlik doğrulaması erişim belirteci aşağıdaki gibi alınır.

## <a name="get-an-authentication-access-token"></a>Kimlik doğrulaması erişim belirteci alma
> **NOT**: Başlamadan önce [bir veri kümesine veri gönderme](walkthrough-push-data.md) ayrıntılı kılavuzundaki adımları uyguladığınızdan emin olun.
> 
> 

1. Visual Studio 2015'te bir **Konsol Uygulaması** projesi oluşturun.
2. [.NET NuGet paketi için Azure AD Kimlik Doğrulama Kitaplığı](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)'nı yükleyin. Bir .NET uygulamasında kimlik doğrulaması güvenlik belirteci almak için bu paketi kullanın. Paket aşağıdaki gibi yüklenir:
   
     a. Visual Studio 2015'te **Araçlar** > **NuGet Paket Yöneticisi** > **Paket Yöneticisi Konsolu**'nu seçin.
   
     b. **Paket Yöneticisi Konsolu**'na şunu girin: Install-Package Microsoft.IdentityModel.Clients.ActiveDirectory -Version 2.21.301221612.
3. Program {...} sınıfına aşağıdaki kodu ekleyin.
4. "{ClientID}" yerine uygulamayı kaydederken aldığınız **İstemci Kimliği**'ni girin. Bkz. [Uygulamayı Azure AD'ye kaydetme](walkthrough-push-data-register-app-with-azure-ad.md).
5. Microsoft.IdentityModel.Clients.ActiveDirectory paketini yükledikten sonra Program.cs'ye **using Microsoft.IdentityModel.Clients.ActiveDirectory;** ifadesini ekleyin.
6. Konsol Uygulaması'nı çalıştırın ve Power BI hesabınızda oturum açın. Konsol Penceresi'nde bir belirteç dizesi görmeniz gerekir.

**Kimlik doğrulama güvenlik belirtecini almak için örnek kod**

Bu kodu Program {...}'e ekleyin.

* İşlemleri çağırmak için bir belirteç değişkeni:
  
  ```
  private static string token = string.Empty;
  
  static void Main(string[] args)
  {
  }
  ```
* static void Main(string[] args) bölümüne:
  
  ```
  static void Main(string[] args)
  {
    //Get an authentication access token
    token = GetToken();
  }
  ```
* GetToken() yöntemi ekleyin:

```
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
           string authorityUri = "https://login.windows.net/common/oauth2/authorize";

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

Bir kimlik doğrulama belirteci aldıktan sonra herhangi bir Power BI işlemini çağırabilirsiniz. Sonraki adım bir panoya veri göndermek amacıyla bir veri kümesi oluşturmak için [Veri Kümesi Oluştur](https://msdn.microsoft.com/library/mt203562.aspx) işleminin nasıl çağrılacağını gösterir.

Sonraki adım, [Power BI'da veri kümesi oluşturma](walkthrough-push-data-create-dataset.md)yı gösterir.

[Tam kod listesi](#code) aşağıdadır.

<a name="code"/>

## <a name="complete-code-listing"></a>Tam kod listesi
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
                string authorityUri = "https://login.windows.net/common/oauth2/authorize";

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


[Sonraki Adım >](walkthrough-push-data-create-dataset.md)

## <a name="next-steps"></a>Sonraki adımlar
[Power BI'da bir veri kümesi oluşturma](walkthrough-push-data-create-dataset.md)  
[Bir uygulamayı Azure AD'ye kaydetme](walkthrough-push-data-register-app-with-azure-ad.md)  
[.NET NuGet paketi için Azure AD Kimlik Doğrulama Kitaplığı](https://www.nuget.org/packages/Microsoft.IdentityModel.Clients.ActiveDirectory/)  
[Power BI veri kümelerine veri gönderme](walkthrough-push-data.md)  
[Overview of Power BI REST API (Power BI REST API'sine Genel Bakış)](overview-of-power-bi-rest-api.md)  
[Power BI REST API başvurusu](https://msdn.microsoft.com/library/mt147898.aspx)  
Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)
