---
title: Kimlik bilgilerini şifreleme
description: 'İzlenecek yol: Şirket İçi Ağ Geçidi veri kaynakları için kimlik bilgilerini şifreleme'
author: mahirdiab
manager: eligr
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 04/02/2019
ms.author: mahirdiab
ms.openlocfilehash: 79ab3731abfdf972de1ee9d40456ebb0c5ebfa62
ms.sourcegitcommit: 80961ace38ff9dac6699f81fcee0f7d88a51edf4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/13/2019
ms.locfileid: "56223525"
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
