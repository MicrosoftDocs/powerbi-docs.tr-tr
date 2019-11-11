---
title: Kimlik bilgilerini Power BI için programlama yoluyla yapılandırma
description: Kimlik bilgilerini otomasyon amacıyla Power BI için programlama yoluyla yapılandırma
author: rkarlin
ms.author: rkarlin
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 02/25/2019
ms.openlocfilehash: 52daf96a4ff6ca7eac4d996f5891740538c88e74
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73875873"
---
# <a name="configure-credentials-programmatically-for-power-bi"></a>Kimlik bilgilerini Power BI için programlama yoluyla yapılandırma

Kimlik bilgilerini Power BI için programlama yoluyla yapılandırmak üzere bu adımları izleyin.

## <a name="configure-a-credential-flow-for-data-sources"></a>Veri kaynakları için bir kimlik bilgisi akışı yapılandırma

1. Veri kümesinin veri kaynaklarını bulmak için [Get Datasources](https://docs.microsoft.com/rest/api/power-bi/datasets/getdatasourcesingroup) çağrısı yapın. Her veri kaynağının yanıt gövdesinde tür, bağlantı ayrıntıları, ağ geçidi ve veri kaynağı kimliği bulunur.

    ```csharp
    var datasources = pbiClient.Datasets.GetDatasources(datasetId).Value;
    var datasource = datasources.First(); // select a datasource
    ```

2. Kimlik bilgileri türüne bağlı olarak [Update Datasource Examples](https://docs.microsoft.com/rest/api/power-bi/gateways/updatedatasource) komutuna göre kimlik bilgileri dizesi derleyin.

    ```csharp
    var credentials = "{\"credentialData\":[{\"name\":\"username\", \"value\":\"john\"},{\"name\":\"password\", \"value\":\"*****\"}]}";
    ```

3. Kimlik bilgisi ayrıntılarını derleyin.

    ```csharp
    var credentialDetails = new CredentialDetails(
                    credentials,
                    CredentialTypeEnum.Basic,
                    EncryptedConnectionEnum.Encrypted,
                    EncryptionAlgorithmEnum.None,
                    PrivacyLevelEnum.Private);
    ```

4. 1\. adımdaki ağ geçidi ile veri kaynağı kimliğini ve 4. adımdaki kimlik bilgisi ayrıntılarını kullanarak, kimlik bilgilerini ayarlamak için [Update Datasource](https://docs.microsoft.com/rest/api/power-bi/gateways/updatedatasource) çağrısı yapın.

    ```csharp
    pbiClient.Gateways.UpdateDatasource(gatewayId, datasourceId, credentialDetails);
    ```

### <a name="expired-on-premises-data-source-credentials-flow"></a>Süresi dolmuş şirket içi veri kaynağı kimlik bilgileri akışı

1. [Önceki senaryoda yer alan 1. ve 2. adımları izleyin](#configure-a-credential-flow-for-data-sources).

2. Ağ geçidi ortak anahtarını almak için [Get Gateway](https://docs.microsoft.com/rest/api/power-bi/gateways/getgateways) çağrısı yapın.

    ```csharp
    var gateway = pbiClient.Gateways.GetGatewayById(datasource.GatewayId);
    ```

3. RSA şifreleme algoritmasını kullanarak Ağ Geçidi ortak anahtarı ile kimlik bilgileri dizesini şifreleyin.

    Şifreleme için aşağıdaki yardımcı sınıfını kullanın:

    ```csharp
        public static class AsymmetricKeyEncryptionHelper
        {
            private const int SegmentLength = 85;
            private const int EncryptedLength = 128;

            /// <summary>

            /// Encrypts credentials using the RSA algorithm

            /// </summary>

            public static string EncodeCredentials(string credentialData, string publicKeyExponent, string publicKeyModulus)
            {
                using (RSACryptoServiceProvider rsa = new RSACryptoServiceProvider(EncryptedLength * 8))
                {
                    var parameters = rsa.ExportParameters(false);

                    parameters.Exponent = Convert.FromBase64String(publicKeyExponent);

                    parameters.Modulus = Convert.FromBase64String(publicKeyModulus);

                    rsa.ImportParameters(parameters);

                    return Encrypt(credentialData, rsa);
                }
            }

             private static string Encrypt(string plainText, RSACryptoServiceProvider rsa)
            {

                byte[] plainTextArray = Encoding.UTF8.GetBytes(plainText);

                // Split the message into different segments, each segment's length is 85. So, the result may be 85,85,85,20. 

                bool hasIncompleteSegment = plainTextArray.Length % SegmentLength != 0; 

                int segmentNumber = (!hasIncompleteSegment) ? (plainTextArray.Length / SegmentLength) : ((plainTextArray.Length SegmentLength) + 1);

                byte[] encryptedData = new byte[segmentNumber * EncryptedLength];

                int encryptedDataPosition = 0;

                for (var i = 0; i < segmentNumber; i++)
                {
                    int lengthToCopy;

                    if (i == segmentNumber - 1 && hasIncompleteSegment)

                        lengthToCopy = plainTextArray.Length % SegmentLength;

                    else

                        lengthToCopy = SegmentLength;

                    var segment = new byte[lengthToCopy];

                    Array.Copy(plainTextArray, i * SegmentLength, segment, 0, lengthToCopy);

                    var segmentEncryptedResult = rsa.Encrypt(segment, true);

                    Array.Copy(segmentEncryptedResult, 0, encryptedData, encryptedDataPosition, segmentEncryptedResult.Length);

                    encryptedDataPosition += segmentEncryptedResult.Length;

                }

                return Convert.ToBase64String(encryptedData);

            }

        }

        var encryptedCredentials = AsymmetricKeyEncryptionHelper.EncodeCredentials(credentials);
    ```

4. Şifrelenmiş kimlik bilgileriyle kimlik bilgileri ayrıntıları derleyin.

    ```csharp
    var credentialDetails = new CredentialDetails(
                    encryptedCredentials,
                    CredentialTypeEnum.Basic,
                    EncryptedConnectionEnum.Encrypted,
                    EncryptionAlgorithmEnum.RSA-OAEP,
                    PrivacyLevelEnum.Private);
    ```

5. Kimlik bilgilerini ayarlamak için [Update Datasource](https://docs.microsoft.com/rest/api/power-bi/gateways/updatedatasource) çağrısı yapın.

    ```csharp
    pbiClient.Gateways.UpdateDatasource(gatewayId, datasourceId, credentialDetails);
    ```

## <a name="configure-a-new-data-source-for-a-data-gateway"></a>Bir veri ağ geçidi için yeni bir veri kaynağı yapılandırma

1. Makinenize [Şirket içi veri ağ geçidini](https://powerbi.microsoft.com/gateway/) yükleyin.

2. Ağ geçidi kimliğini ve ortak anahtarını almak için [Get Gateways](https://docs.microsoft.com/rest/api/power-bi/gateways/getgateways) çağrısı yapın.

    ```csharp
    var gateways = pbiClient.Gateways.GetGateways().Value;
    var gateway = gateways.First(); // select a gateway
    ```

3. [Süresi dolmuş şirket içi veri kaynağı kimlik bilgileri akışı](#expired-on-premises-data source-credentials-flow-on-premises-data-gateway) adımında alınan ağ geçidi ortak anahtarını kullanarak önceki senaryoda olduğu gibi kimlik bilgisi ayrıntılarını derleyin.

4. İstek gövdesini derleyin.

    ```csharp
    var request = new PublishDatasourceToGatewayRequest(
    dataSourceType: "SQL",
    connectionDetails: "{\"server\":\"myServer\",\"database\":\"myDatabase\"}",
    credentialDetails: credentialDetails,
    dataSourceName: "my sql datasource");
    ```

5. [Create Datasource](https://docs.microsoft.com/rest/api/power-bi/gateways/createdatasource) API’sini çağırın.

    ```csharp
    pbiClient.Gateways.CreateDatasource(gateway.Id, request);
    ```

## <a name="troubleshooting"></a>Sorun giderme

### <a name="no-gateway-and-data-source-id-found-when-calling-get-data-sources"></a>Get Datasources çağrısı yapılırken hiçbir ağ geçidi ve veri kaynağı kimliği bulunamadı

Bu sorun, veri kümesinin bir ağ geçidine bağlı olmadığı anlamına gelir. Yeni bir veri kümesi oluşturulurken, her bulut bağlantısı için kimlik bilgileri olmayan bir veri kaynağı, kullanıcının bulut ağ geçidinde otomatik olarak oluşturulur. Bu ağ geçidi, bulut bağlantılarının kimlik bilgilerini depolamak için kullanılır.

Veri kümesini oluşturduktan sonra, veri kümesiyle tüm bağlantılar için eşleşen veri kaynaklarını içeren uygun bir ağ geçidi arasında otomatik bir bağlama yapılır. Bu tür bir ağ geçidi yoksa veya birden çok uygun ağ geçidi varsa otomatik bağlama başarısız olur.

Şirket içi veri kaynakları eksikse yenilerini oluşturun ve [Bind To Gateway](https://docs.microsoft.com/rest/api/power-bi/datasets/bindtogateway) komutunu kullanarak veri kümesini bir ağ geçidine kendiniz bağlayın.

Bağlanabilecek ağ geçitlerini bulmak için [Discover Gateways](https://docs.microsoft.com/rest/api/power-bi/datasets/discovergateways) komutunu kullanın.
