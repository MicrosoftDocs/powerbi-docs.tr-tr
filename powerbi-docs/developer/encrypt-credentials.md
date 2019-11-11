---
title: Kimlik bilgilerini şifreleme
description: İzlenecek yol - Şirket İçi Ağ Geçidi veri kaynakları için kimlik bilgilerini şifreleme
author: mahirdiab
ms.author: madia
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 02/04/2019
ms.openlocfilehash: 4747d548f8b02806c1e7b1359d140b09039e09d8
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73863863"
---
# <a name="encrypt-credentials"></a>Kimlik bilgilerini şifreleme

[Power BI Rest API'sini](https://docs.microsoft.com/rest/api/power-bi/) kullanarak **kurumsal şirket içi ağ geçidinin** altında [Create Datasource](https://docs.microsoft.com/rest/api/power-bi/gateways/createdatasource) veya [Update Datasource](https://docs.microsoft.com/rest/api/power-bi/gateways/updatedatasource) çağrısı yaptığınızda, kimlik bilgileri değeri ağ geçidinin genel anahtarı kullanılarak şifrelenmelidir.

.NET'te kimlik bilgilerinin nasıl şifrelendiğini gösteren aşağıdaki kod örneğine bakın.

Aşağıdaki EncodeCredentials yöntemine sağlanan kimlik bilgileri, bu kimlik bilgilerinin türüne bağlı olarak şu biçimlerden birinde olmalıdır:

**Temel / Windows kimlik bilgileri**

```csharp
var credentials = "{\"credentialData\":[{\"name\":\"username\", \"value\":\"john\"},{\"name\":\"password\", \"value\":\"*****\"}]}";
```

**Anahtar kimlik bilgileri**

```csharp
var credentials = "{\"credentialData\":[{\"name\":\"key\", \"value\":\"ec....LA=\"}]}";
```

**OAuth2 kimlik bilgileri**

```csharp
var credentials = "{\"credentialData\":[{\"name\":\"accessToken\", \"value\":\"eyJ0....fwtQ\"}]}";
```

**Anonim kimlik bilgileri**

```csharp
var credentials = "{\"credentialData\":\"\"}";
```

**Kimlik bilgilerini şifreleme**

```csharp
public static class AsymmetricKeyEncryptionHelper
{

    private const int SegmentLength = 85;
    private const int EncryptedLength = 128;

    public static string EncodeCredentials(string credentials, string publicKeyExponent, string publicKeyModulus)
    {
        using (RSACryptoServiceProvider rsa = new RSACryptoServiceProvider(EncryptedLength * 8))
        {
            var parameters = rsa.ExportParameters(false);
            parameters.Exponent = Convert.FromBase64String(publicKeyExponent);
            parameters.Modulus = Convert.FromBase64String(publicKeyModulus);
            rsa.ImportParameters(parameters);
            return Encrypt(credentials, rsa);
        }
    }

    private static string Encrypt(string plainText, RSACryptoServiceProvider rsa)
    {
        byte[] plainTextArray = Encoding.UTF8.GetBytes(plainText);

        // Split the message into different segments, each segment's length is 85. So the result may be 85,85,85,20.
        bool hasIncompleteSegment = plainTextArray.Length % SegmentLength != 0;

        int segmentNumber = (!hasIncompleteSegment) ? (plainTextArray.Length / SegmentLength) : ((plainTextArray.Length / SegmentLength) + 1);

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
```