---
title: "Veri kümesi oluşturma"
description: "Adım Adım Kılavuz - Bir veri kümesine veri gönderme - Power BI'da veri kümesi oluşturma"
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
ms.openlocfilehash: b45a6f76a710bc158d0d1763ca10f2125164952a
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="step-3-create-a-dataset-in-power-bi"></a>3. Adım: Power BI'da veri kümesi oluşturma
Bu makale [bir veri kümesine veri gönderme](walkthrough-push-data.md) adım adım kılavuzunun bir parçasıdır.

Bir veri kümesine veri gönderme kılavuzunun [Kimlik doğrulaması erişim belirteci alma](walkthrough-push-data-get-token.md) başlıklı **2. Adım**'ında, **Azure AD**'de kimlik doğrulaması gerçekleştirmek için bir belirteç alırsınız. Bu adımda, [Veri Kümesi Oluştur](https://msdn.microsoft.com/library/mt203562.aspx) işlemini çağırmak için belirteci kullanırsınız.

Bir REST kaynağına çağrı yapmak için, kaynağın yerini belirleyen bir URL kullanır ve Power BI hizmeti kaynağına, veri kümesini tanımlayan bir JavaScript Nesne Gösterimi (JSON) dizesi gönderirsiniz. Power BI hizmetinin kullanmak istediğiniz bölümü bir REST kaynağı tarafından tanımlanır. Veri kümesine veri gönderme işlemi için hedef kaynak bir **Veri Kümesidir**. Veri kümesini tanımlayan URL şudur: https://api.PowerBI.com/v1.0/myorg/datasets. Bir grupta veri gönderiyorsanız URL https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets olur.

Bir Power BI REST işleminin kimliğini doğrulamak için, [Kimlik doğrulaması erişim belirteci alma](walkthrough-push-data-get-token.md) bölümünde edindiğiniz belirteci bir istek üst bilgisine eklersiniz:

[Veri Kümesi Oluştur](https://msdn.microsoft.com/library/mt203562.aspx) işlemini çağırdığınızda, yeni bir veri kümesi oluşturulur. Power BI REST API'sini kullanmaya yönelik örnekler için bkz. [APIARY'deki Power BI REST API'si](http://docs.powerbi.apiary.io/).

![](media/walkthrough-push-data-create-dataset/powerbi-developer-create-dataset.png)

Power BI'da veri kümesi oluşturma işlemi aşağıda açıklanmıştır.

## <a name="create-a-dataset-in-power-bi"></a>Power BI'da veri kümesi oluşturma
> [!NOTE]
> Başlamadan önce, [bir veri kümesine veri gönderme](walkthrough-push-data.md) kılavuzundaki adımları izlediğinizden emin olun.
> 
> 

1. [2. Adım: Kimlik doğrulaması erişim belirteci alma](walkthrough-push-data-get-token.md) bölümünde oluşturduğunuz Konsol Uygulaması projesinde, Program.cs'ye **using System.Net;** ve **using System.IO;** dizelerini ekleyin.
2. Program.cs'ye aşağıdaki kodu ekleyin.
3. Konsol Uygulaması'nı çalıştırın ve Power BI hesabınızda oturum açın. Konsol Penceresinde **Dataset Created** ifadesini görmeniz gerekir. Ayrıca, yeni veri kümesini görmek için Power BI'da oturum açabilirsiniz.

**Veri kümesine veri gönderme örneği**

Bu kodu Program.cs'ye ekleyin.

* static void Main(string[] args) bölümüne:
  
    ```
    static void Main(string[] args)
    {
        //Get an authentication access token
        token = GetToken();
  
        //Create a dataset in Power BI
        CreateDataset();
    }
    ```
* Bir CreateDataset() yöntemi ekleyin:
  
    ```
    #region Create a dataset in Power BI
    private static void CreateDataset()
    {
        //TODO: Add using System.Net and using System.IO
  
        string powerBIDatasetsApiUrl = "https://api.powerbi.com/v1.0/myorg/datasets";
        //POST web request to create a dataset.
        //To create a Dataset in a group, use the Groups uri: https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets
        HttpWebRequest request = System.Net.WebRequest.Create(powerBIDatasetsApiUrl) as System.Net.HttpWebRequest;
        request.KeepAlive = true;
        request.Method = "POST";
        request.ContentLength = 0;
        request.ContentType = "application/json";
  
        //Add token to the request header
        request.Headers.Add("Authorization", String.Format("Bearer {0}", token));
  
        //Create dataset JSON for POST request
        string datasetJson = "{\"name\": \"SalesMarketing\", \"tables\": " +
            "[{\"name\": \"Product\", \"columns\": " +
            "[{ \"name\": \"ProductID\", \"dataType\": \"Int64\"}, " +
            "{ \"name\": \"Name\", \"dataType\": \"string\"}, " +
            "{ \"name\": \"Category\", \"dataType\": \"string\"}," +
            "{ \"name\": \"IsCompete\", \"dataType\": \"bool\"}," +
            "{ \"name\": \"ManufacturedOn\", \"dataType\": \"DateTime\"}" +
            "]}]}";
  
        //POST web request
        byte[] byteArray = System.Text.Encoding.UTF8.GetBytes(datasetJson);
        request.ContentLength = byteArray.Length;
  
        //Write JSON byte[] into a Stream
        using (Stream writer = request.GetRequestStream())
        {
            writer.Write(byteArray, 0, byteArray.Length);
  
            var response = (HttpWebResponse)request.GetResponse();
  
            Console.WriteLine(string.Format("Dataset {0}", response.StatusCode.ToString()));
  
            Console.ReadLine();
        }
    }
    #endregion
    ```

Sonraki adımda [bir Power BI tablosuna satır eklemek için veri kümesi alma](walkthrough-push-data-get-datasets.md) işlemi gösterilmektedir.

[Tam kod listesi](#code) aşağıdadır.

<a name="code"/>

## <a name="complete-code-listing"></a>Tam kod listesi
    using System;
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    using System.Net;
    using System.IO;

    namespace walkthrough_push_data
    {
        class Program
        {
            private static string token = string.Empty;

            static void Main(string[] args)
            {

                //Get an authentication access token
                token = GetToken();

                //Create a dataset in Power BI
                CreateDataset();

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


            #region Create a dataset in Power BI
            private static void CreateDataset()
            {
                //TODO: Add using System.Net and using System.IO

                string powerBIDatasetsApiUrl = "https://api.powerbi.com/v1.0/myorg/datasets";
                //POST web request to create a dataset.
                //To create a Dataset in a group, use the Groups uri: https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets
                HttpWebRequest request = System.Net.WebRequest.Create(powerBIDatasetsApiUrl) as System.Net.HttpWebRequest;
                request.KeepAlive = true;
                request.Method = "POST";
                request.ContentLength = 0;
                request.ContentType = "application/json";

                //Add token to the request header
                request.Headers.Add("Authorization", String.Format("Bearer {0}", token));

                //Create dataset JSON for POST request
                string datasetJson = "{\"name\": \"SalesMarketing\", \"tables\": " +
                    "[{\"name\": \"Product\", \"columns\": " +
                    "[{ \"name\": \"ProductID\", \"dataType\": \"Int64\"}, " +
                    "{ \"name\": \"Name\", \"dataType\": \"string\"}, " +
                    "{ \"name\": \"Category\", \"dataType\": \"string\"}," +
                    "{ \"name\": \"IsCompete\", \"dataType\": \"bool\"}," +
                    "{ \"name\": \"ManufacturedOn\", \"dataType\": \"DateTime\"}" +
                    "]}]}";

                //POST web request
                byte[] byteArray = System.Text.Encoding.UTF8.GetBytes(datasetJson);
                request.ContentLength = byteArray.Length;

                //Write JSON byte[] into a Stream
                using (Stream writer = request.GetRequestStream())
                {
                    writer.Write(byteArray, 0, byteArray.Length);

                    var response = (HttpWebResponse)request.GetResponse();

                    Console.WriteLine(string.Format("Dataset {0}", response.StatusCode.ToString()));

                    Console.ReadLine();
                }
            }
            #endregion
        }
    }


[Sonraki Adım >](walkthrough-push-data-get-datasets.md)

## <a name="next-steps"></a>Sonraki adımlar
[Bir Power BI tablosuna satır eklemek için veri kümesi alma](walkthrough-push-data-get-datasets.md)  
[Kimlik doğrulaması erişim belirteci alma](walkthrough-push-data-get-token.md)  
[Veri Kümesi oluşturma](https://msdn.microsoft.com/library/mt203562.aspx)  
[Power BI Panolarına veri gönderme](walkthrough-push-data.md)  
[Overview of Power BI REST API (Power BI REST API'sine Genel Bakış)](overview-of-power-bi-rest-api.md)  
[Power BI Rest API başvurusu](https://msdn.microsoft.com/library/mt147898.aspx)  
[APIARY'deki Power BI REST API'si](http://docs.powerbi.apiary.io/)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

