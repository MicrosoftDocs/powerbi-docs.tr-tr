---
title: Kimlik bilgilerini şifreleme
description: İzlenecek yol - Şirket İçi Ağ Geçidi veri kaynakları için kimlik bilgilerini şifreleme
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 01/08/2020
ms.openlocfilehash: b1fc4a505aa993c606743eefb6e8fb8c0379317d
ms.sourcegitcommit: 4b926ab5f09592680627dca1f0ba016b07a86ec0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/10/2020
ms.locfileid: "75836617"
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

Kimlik bilgileri değerini, ağ geçidinin ortak anahtarını kullanarak şifreleyin. Ortak anahtar boyutu, ağ geçidi sürümüne göre değişebilir.

PowerBI-CSharp GitHub deposundan ([PowerBI-CSharp/sdk/PowerBI.Api/Extensions/V2/](https://github.com/microsoft/PowerBI-CSharp/tree/master/sdk/PowerBI.Api/Extensions/V2)) ulaşabileceğini SDK kodundaki örneği inceleyin.

- [AsymmetricKeyEncryptor.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/AsymmetricKeyEncryptor.cs)
- [Asymmetric1024KeyEncryptionHelper.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/Asymmetric1024KeyEncryptionHelper.cs)
- [AsymmetricHigherKeyEncryptionHelper.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/AsymmetricHigherKeyEncryptionHelper.cs)
- [AuthenticatedEncryption.cs](https://github.com/microsoft/PowerBI-CSharp/blob/master/sdk/PowerBI.Api/Extensions/V2/AuthenticatedEncryption.cs)