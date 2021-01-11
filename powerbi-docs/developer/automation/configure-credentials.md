---
title: Power BI tümleşik analizleri için kimlik bilgilerini programlama ile yapılandırarak daha iyi tümleşik BI içgörüleri sağlama
description: Power BI'yı otomatikleştirirken kimlik bilgilerini programlama ile yapılandırma. Power BI tümleşik analiz kullanarak daha iyi tümleşik BI içgörüleri elde edin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: how-to
ms.date: 06/23/2020
ms.openlocfilehash: c87ca689d804c909ca3a6ca9544ac1a4568c8b86
ms.sourcegitcommit: eeaf607e7c1d89ef7312421731e1729ddce5a5cc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2021
ms.locfileid: "97887650"
---
# <a name="configure-credentials-programmatically-for-power-bi"></a>Kimlik bilgilerini Power BI için programlama yoluyla yapılandırma

Kimlik bilgilerini Power BI için programlama yoluyla yapılandırmak üzere bu makaledeki adımları izleyin.

>[!NOTE]
>* Çağıran kullanıcının bir veri kümesi sahibi veya ağ geçidi yöneticisi olması gerekir. Bir [hizmet sorumlusu](../embedded/embed-service-principal.md) da kullanabilirsiniz. Örneğin, hizmet sorumlusu veri kümesi sahibi olabilir.
>* Bulut veri kaynakları ve bunlara karşılık gelen kimlik bilgileri kullanıcı düzeyinde yönetilir.

## <a name="update-credentials-flow-for-data-sources"></a>Veri kaynakları için kimlik bilgisi akışını güncelleştirme

1. Veri kümesinin veri kaynaklarını bulmak için [Get Datasources](/rest/api/power-bi/datasets/getdatasourcesingroup) çağrısı yapın. Her veri kaynağının yanıt gövdesinde tür, bağlantı ayrıntıları, ağ geçidi ve veri kaynağı kimliği bulunur.

    ```csharp
    // Select a datasource
    var datasources = pbiClient.Datasets.GetDatasources(datasetId).Value;
    var datasource = datasources.First();
    ```

2. Kimlik bilgileri türüne bağlı olarak [Update Datasource Examples](/rest/api/power-bi/gateways/updatedatasource) komutuna göre kimlik bilgileri dizesi derleyin.

    # <a name="net-sdk-v3"></a>[.NET SDK v3](#tab/sdk3)

    ```csharp
    var credentials =  new BasicCredentials(username: "username", password :"*****");
    ```

    # <a name="net-sdk-v2"></a>[.NET SDK v2](#tab/sdk2)

     ```csharp
    var credentials = "{\"credentialData\":[{\"name\":\"username\", \"value\":\"john\"},{\"name\":\"password\", \"value\":\"*****\"}]}";
    ```

    ---

    >[!NOTE]
    >Bulut veri kaynaklarını kullanıyorsanız bu bölümde yer alan sonraki adımları izlemeyin. 1\. adımda aldığınız ağ geçidi ve veri kaynağı kimliklerini kullanıp [Veri Update Datasource](/rest/api/power-bi/gateways/updatedatasource) çağrısı yaparak kimlik bilgilerini belirleyin. 

3. Ağ geçidi ortak anahtarını almak için [Get Gateway](/rest/api/power-bi/gateways/getgateways) çağrısı yapın.

    ```csharp
    var gateway = pbiClient.Gateways.GetGatewayById(datasource.GatewayId);
    ```

4. Kimlik bilgilerini şifreleyin.

    # <a name="net-sdk-v3"></a>[.NET SDK v3](#tab/sdk3)

    ```csharp
    var credentialsEncryptor = new AsymmetricKeyEncryptor(gateway.publicKey);
    ```

    # <a name="net-sdk-v2"></a>[.NET SDK v2](#tab/sdk2)

    2\. adımdan Ağ Geçidi ortak anahtarı ile kimlik bilgileri dizesini şifreleyin. Ortak anahtar boyutu, ağ geçidi sürümüne göre değişebilir. [PowerBI-CSharp GitHub deposunda](https://github.com/microsoft/PowerBI-CSharp/tree/master/sdk/PowerBI.Api/Extensions) sağlanan aşağıdaki SDK kodu örneklerine bakın:
    * [AsymmetricKeyEncryptor.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/AsymmetricKeyEncryptor.cs)
    * [Asymmetric1024KeyEncryptionHelper.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/Asymmetric1024KeyEncryptionHelper.cs)
    * [AsymmetricHigherKeyEncryptionHelper.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/AsymmetricHigherKeyEncryptionHelper.cs)
    * [AuthenticatedEncryption.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/AuthenticatedEncryption.cs) 

    ---  

5. Şifrelenmiş kimlik bilgileriyle kimlik bilgisi ayrıntılarını derleyin.

    # <a name="net-sdk-v3"></a>[.NET SDK v3](#tab/sdk3)

    AssymetricKeyEncryptor sınıfını **3. Adımda** alınan ortak anahtarla kullanın.

    ```csharp
    var credentialDetails = new CredentialDetails(
            credentials,
            PrivacyLevel.Private,
            EncryptedConnection.Encrypted,
            credentialsEncryptor);
    ```


    # <a name="net-sdk-v2"></a>[.NET SDK v2](#tab/sdk2)

    ```csharp
    var credentialDetails = new CredentialDetails(
            credentials,
            CredentialTypeEnum.Basic,
            EncryptedConnectionEnum.Encrypted,
            EncryptionAlgorithmEnum.None,
            PrivacyLevelEnum.Private);
    ```

    ---

6. Kimlik bilgilerini ayarlamak için [Update Datasource](/rest/api/power-bi/gateways/updatedatasource) çağrısı yapın.

    ```csharp
    pbiClient.Gateways.UpdateDatasource(gatewayId, datasourceId, credentialDetails);
    ```

## <a name="configure-a-new-data-source-for-a-data-gateway"></a>Bir veri ağ geçidi için yeni bir veri kaynağı yapılandırma

1. Makinenize [Şirket içi veri ağ geçidini](https://powerbi.microsoft.com/gateway/) yükleyin.

2. Ağ geçidi kimliğini ve ortak anahtarını almak için [Get Gateways](/rest/api/power-bi/gateways/getgateways) çağrısı yapın.

    ```csharp
    // Select a gateway
    var gateways = pbiClient.Gateways.GetGateways().Value;
    var gateway = gateways.First();
    ```

3. Kimlik bilgisi ayrıntılarını, [veri kaynakları için kimlik bilgileri akışını güncelleştirme](#update-credentials-flow-for-data-sources) başlığı altında açıklandığı gibi, **2. adımda** alınan ağ geçidi ortak anahtarını kullanarak derleyin.

4. İstek gövdesini derleyin.

    ```csharp
    var request = new PublishDatasourceToGatewayRequest(
            dataSourceType: "SQL",
            connectionDetails: "{\"server\":\"myServer\",\"database\":\"myDatabase\"}",
            credentialDetails: credentialDetails,
            dataSourceName: "my sql datasource");
    ```

5. [Create Datasource](/rest/api/power-bi/gateways/createdatasource) API’sini çağırın.

    ```csharp
    pbiClient.Gateways.CreateDatasource(gateway.Id, request);
    ```

## <a name="credential-types"></a>Kimlik bilgisi türleri

[Power BI Rest API'sini](/rest/api/power-bi/) kullanarak **kurumsal şirket içi ağ geçidinin** altında [Create Datasource](/rest/api/power-bi/gateways/createdatasource) veya [Update Datasource](/rest/api/power-bi/gateways/updatedatasource) çağrısı yaptığınızda, kimlik bilgileri değeri ağ geçidinin genel anahtarı kullanılarak şifrelenmelidir.

>[!NOTE]
>.NET SDK v3, aşağıda listelenen .NET SDK v2 örneklerini de çalıştırır.

### <a name="windows-and-basic-credentials"></a>Windows ve temel kimlik bilgileri

# <a name="net-sdk-v3"></a>[.NET SDK v3](#tab/sdk3)

```csharp
// Windows credentials
var credentials = new WindowsCredentials(username: "john", password: "*****");

// Or

// Basic credentials
var credentials = new BasicCredentials(username: "john", password: "*****");

var credentialsEncryptor = new AsymmetricKeyEncryptor(publicKey);
var credentialDetails = new CredentialDetails(credentials, PrivacyLevel.Private, EncryptedConnection.Encrypted, credentialsEncryptor);
```

# <a name="net-sdk-v2"></a>[.NET SDK v2](#tab/sdk2)

```csharp
var credentials = "{\"credentialData\":[{\"name\":\"username\", \"value\":\"john\"},{\"name\":\"password\", \"value\":\"*****\"}]}";
```

---

### <a name="key-credentials"></a>Anahtar kimlik bilgileri

# <a name="net-sdk-v3"></a>[.NET SDK v3](#tab/sdk3)

```csharp
var credentials = new KeyCredentials("TestKey");
var credentialsEncryptor = new AsymmetricKeyEncryptor(publicKey);
var credentialDetails = new CredentialDetails(credentials, PrivacyLevel.Private, EncryptedConnection.Encrypted, credentialsEncryptor);
```

# <a name="net-sdk-v2"></a>[.NET SDK v2](#tab/sdk2)

```csharp
var credentials = "{\"credentialData\":[{\"name\":\"key\", \"value\":\"ec....LA=\"}]}";
```

---

**OAuth2 kimlik bilgileri**

# <a name="net-sdk-v3"></a>[.NET SDK v3](#tab/sdk3)

```csharp
var credentials = new OAuth2Credentials("TestToken");
var credentialsEncryptor = new AsymmetricKeyEncryptor(publicKey);
var credentialDetails = new CredentialDetails(credentials, PrivacyLevel.Private, EncryptedConnection.Encrypted, credentialsEncryptor);
```

# <a name="net-sdk-v2"></a>[.NET SDK v2](#tab/sdk2)

```csharp
var credentials = "{\"credentialData\":[{\"name\":\"accessToken\", \"value\":\"eyJ0....fwtQ\"}]}";
```

---

**Anonim kimlik bilgileri**

# <a name="net-sdk-v3"></a>[.NET SDK v3](#tab/sdk3)

```csharp
var credentials = new AnonymousCredentials();
var credentialDetails = new CredentialDetails(credentials, PrivacyLevel.Private, EncryptedConnection.NotEncrypted);
```

# <a name="net-sdk-v2"></a>[.NET SDK v2](#tab/sdk2)

```csharp
var credentials = "{\"credentialData\":\"\"}";
```

---

## <a name="troubleshooting"></a>Sorun giderme

### <a name="no-gateway-and-data-source-id-found-when-calling-get-data-sources"></a>Get Datasources çağrısı yapılırken hiçbir ağ geçidi ve veri kaynağı kimliği bulunamadı

Bu sorun, veri kümesinin bir ağ geçidine bağlı olmadığı anlamına gelir. Yeni bir veri kümesi oluşturulurken, her bulut bağlantısı için kimlik bilgileri olmayan bir veri kaynağı, kullanıcının bulut ağ geçidinde otomatik olarak oluşturulur. Bu ağ geçidi, bulut bağlantılarının kimlik bilgilerini depolamak için kullanılır.

Veri kümesini oluşturduktan sonra, veri kümesiyle tüm bağlantılar için eşleşen veri kaynaklarını içeren uygun bir ağ geçidi arasında otomatik bir bağlama oluşturulur. Bu tür bir ağ geçidi yoksa veya birden çok uygun ağ geçidi varsa otomatik bağlama başarısız olur.

Şirket içi veri kümelerini kullanıyorsanız, eksik olan şirket içi veri kaynaklarını oluşturun ve [Bind To Gateway](/rest/api/power-bi/datasets/bindtogateway) komutunu kullanarak veri kümesini bir ağ geçidine kendiniz bağlayın.

Bağlanabilecek ağ geçitlerini bulmak için [Discover Gateways](/rest/api/power-bi/datasets/discovergateways) komutunu kullanın.
