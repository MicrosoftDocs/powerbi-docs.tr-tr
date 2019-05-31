---
title: Satır eklemek için veri kümesi alma
description: Veri göndermeye ilişkin adım adım kılavuz - Bir Power BI tablosuna satır eklemek için veri kümesi alma
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: madia
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 02/05/2019
ms.openlocfilehash: c0a70339e8336f3e7b93b40ad8a99dcb87715812
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65710243"
---
# <a name="step-4-get-a-dataset-to-add-rows-into-a-power-bi-table"></a>4. Adım: Power BI tablosuna satır eklemek için veri kümesi alma

Bu makale, [bir veri kümesine veri gönderme](walkthrough-push-data.md) ayrıntılı kılavuzunun bir parçasıdır.

Bir veri kümesine veri gönderme işleminin **3. adımında** ([Power BI'da bir veri kümesi oluşturma](walkthrough-push-data-create-dataset.md)), Power BI'da bir veri kümesi oluşturmak için [Veri Kümesi Oluştur](https://docs.microsoft.com/rest/api/power-bi/datasets) işlemini gerçekleştirdiniz. Bu adımda, bir veri kümesi kimliği almak için [Veri Kümelerini Al](https://docs.microsoft.com/rest/api/power-bi/datasets/getdatasets) işlemini ve Newtonsoft.Json'u kullanacaksınız. Bir veri kümesine satır eklemek için 4. adımdaki veri kümesi kimliğini kullanın. 

Bir Power BI veri kümesine veri göndermek için veri kümesindeki tabloya başvurmanız gerekir. Veri kümesindeki bir tabloya başvurmak için öncelikle bir **Veri Kümesi Kimliği** almanız gerekir. [Kimliğe Göre Veri Kümesi Al](https://docs.microsoft.com/rest/api/power-bi/datasets/getdatasetbyid) işlemini kullanarak bir **Veri Kümesi Kimliği** edinin. **Kimliğe Göre Veri Kümesi Al** işlemi, Power BI'daki tüm veri kümelerinin listesini içeren bir JSON dizesi döndürür. Bir JSON dizesini seri durumdan çıkarmak için önerilen yöntem, [Newtonsoft.Json](http://www.newtonsoft.com/json) kullanmaktır.

Bir veri kümesinin nasıl alınacağı aşağıda açıklanmıştır.

## <a name="get-a-power-bi-dataset"></a>Bir Power BI veri kümesi alma

> **NOT**: Başlamadan önce, [bir veri kümesine veri gönderme](walkthrough-push-data.md) kılavuzundaki adımları izlediğinizden emin olun.

1. 2. Adım: Veri göndermeye ilişkin adım adım kılavuz, [Kimlik doğrulaması erişim belirteci alma](walkthrough-push-data-get-token.md) kapsamında oluşturduğunuz Konsol Uygulaması projesinde Newtonsoft.Json NuGet paketini yükleyin. Paket aşağıdaki gibi yüklenir:

     a. Visual Studio 2015'te **Araçlar** > **NuGet Paket Yöneticisi** > **Paket Yöneticisi Konsolu**'nu seçin.

     b. **Paket Yöneticisi Konsolu**'na şunu girin: Install-Package Newtonsoft.Json.
2. Paket yüklendikten sonra Program.cs'ye şunu ekleyin: **using Newtonsoft.Json;** .
3. Bir **Veri Kümesi Kimliği** almak için Program.cs'ye aşağıda bulunan kodu ekleyin.
4. Konsol Uygulaması'nı çalıştırın ve Power BI hesabınızda oturum açın. Konsol Penceresinde, bir kimliğin izlediği **Dataset ID:** (Veri Kümesi Kimliği:) ifadesini görmeniz gerekir.

**Veri kümesi alma işlemi örneği**

Program.cs'ye aşağıdaki kodu ekleyin.

* static void Main(string[] args) bölümüne:
  
  ```csharp
  static void Main(string[] args)
  {
  
    //Get an authentication access token
    token = GetToken();
  
    //Create a dataset in Power BI
    CreateDataset();
  
    //Get a dataset to add rows into a Power BI table
    string datasetId = GetDataset();
  }
  ```
* Bir GetDatset() yöntemi ekleyin:
  
  ```csharp
    #region Get a dataset to add rows into a Power BI table
    private static string GetDataset()
    {
        string powerBIDatasetsApiUrl = "https://api.powerbi.com/v1.0/myorg/datasets";
        //POST web request to create a dataset.
        //To create a Dataset in a group, use the Groups uri: https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets
        HttpWebRequest request = System.Net.WebRequest.Create(powerBIDatasetsApiUrl) as System.Net.HttpWebRequest;
        request.KeepAlive = true;
        request.Method = "GET";
        request.ContentLength = 0;
        request.ContentType = "application/json";
  
        //Add token to the request header
        request.Headers.Add("Authorization", String.Format("Bearer {0}", token));
  
        string datasetId = string.Empty;
        //Get HttpWebResponse from GET request
        using (HttpWebResponse httpResponse = request.GetResponse() as System.Net.HttpWebResponse)
        {
            //Get StreamReader that holds the response stream
            using (StreamReader reader = new System.IO.StreamReader(httpResponse.GetResponseStream()))
            {
                string responseContent = reader.ReadToEnd();
  
                //TODO: Install NuGet Newtonsoft.Json package: Install-Package Newtonsoft.Json
                //and add using Newtonsoft.Json
                var results = JsonConvert.DeserializeObject<dynamic>(responseContent);
  
                //Get the first id
                datasetId = results["value"][0]["id"];
  
                Console.WriteLine(String.Format("Dataset ID: {0}", datasetId));
                Console.ReadLine();
  
                return datasetId;
            }
        }
    }
    #endregion
  ```

Sonraki adımda [bir Power BI tablosuna satır ekleme](walkthrough-push-data-add-rows.md) işlemi gösterilmektedir.

[Tam kod listesi](#code) aşağıdadır.

<a name="code"/>

## <a name="complete-code-listing"></a>Tam kod listesi

```csharp
using System;
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using System.Net;
using System.IO;
using Newtonsoft.Json;

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

            //Get a dataset to add rows into a Power BI table
            string datasetId = GetDataset();

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

        #region Get a dataset to add rows into a Power BI table
        private static string GetDataset()
        {
            string powerBIDatasetsApiUrl = "https://api.powerbi.com/v1.0/myorg/datasets";
            //POST web request to create a dataset.
            //To create a Dataset in a group, use the Groups uri: https://api.PowerBI.com/v1.0/myorg/groups/{group_id}/datasets
            HttpWebRequest request = System.Net.WebRequest.Create(powerBIDatasetsApiUrl) as System.Net.HttpWebRequest;
            request.KeepAlive = true;
            request.Method = "GET";
            request.ContentLength = 0;
            request.ContentType = "application/json";

            //Add token to the request header
            request.Headers.Add("Authorization", String.Format("Bearer {0}", token));

            string datasetId = string.Empty;
            //Get HttpWebResponse from GET request
            using (HttpWebResponse httpResponse = request.GetResponse() as System.Net.HttpWebResponse)
            {
                //Get StreamReader that holds the response stream
                using (StreamReader reader = new System.IO.StreamReader(httpResponse.GetResponseStream()))
                {
                    string responseContent = reader.ReadToEnd();

                    //TODO: Install NuGet Newtonsoft.Json package: Install-Package Newtonsoft.Json
                    //and add using Newtonsoft.Json
                    var results = JsonConvert.DeserializeObject<dynamic>(responseContent);

                    //Get the first id
                    datasetId = results["value"][0]["id"];

                    Console.WriteLine(String.Format("Dataset ID: {0}", datasetId));
                    Console.ReadLine();

                    return datasetId;
                }
            }
        }
        #endregion
    }
}
```

[Sonraki Adım >](walkthrough-push-data-add-rows.md)

## <a name="next-steps"></a>Sonraki adımlar

[Bir Power BI tablosuna satır ekleme](walkthrough-push-data-add-rows.md)  
[Newtonsoft.Json](http://www.newtonsoft.com/json)  
[Get Datasets (Veri Kümelerini Al)](https://docs.microsoft.com/rest/api/power-bi/datasets/getdatasets)  
[Power BI'a veri gönderme](walkthrough-push-data.md)  
[Overview of Power BI REST API (Power BI REST API'sine Genel Bakış)](overview-of-power-bi-rest-api.md)  
[Power BI REST API başvurusu](https://docs.microsoft.com/rest/api/power-bi/)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)