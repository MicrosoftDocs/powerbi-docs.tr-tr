---
title: Bir Power BI tümleşik analiz uygulamasına hizmet sorumlusu ve sertifika ile Power BI içeriği ekleyerek daha iyi tümleşik BI içgörüleri sağlama
description: Azure Active Directory uygulama hizmet sorumlusu ve sertifika kullanarak Power BI tümleşik analizlerinde kimlik doğrulama hakkında bilgi edinin. Power BI tümleşik analiz kullanarak daha iyi tümleşik BI içgörüleri elde edin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: how-to
ms.custom: ''
ms.date: 11/23/2020
ms.openlocfilehash: 0e19f2c592f5a5249e80771edf4a16c02eb68708
ms.sourcegitcommit: 1cad78595cca1175b82c04458803764ac36e5e37
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/19/2021
ms.locfileid: "98565107"
---
# <a name="embed-power-bi-content-with-service-principal-and-a-certificate"></a>Hizmet sorumlusu ve sertifikayla Power BI içeriği ekleme

Sertifika tabanlı kimlik doğrulaması, Azure Active Directory (Azure AD) kullanılarak Windows, Android veya iOS cihazda bulunan ya da bir [Azure Key Vault](/azure/key-vault/basic-concepts)’ta tutulan bir istemci sertifikasıyla kimliğinizin doğrulanmasına olanak tanır.

Bu kimlik doğrulaması yönteminin kullanılması, döndürme veya iptal için CA kullanılarak merkezi bir yerden sertifikaların yönetilmesine olanak verir.

Azure AD’de [İstemci kimlik bilgisi akışları](https://github.com/AzureAD/microsoft-authentication-library-for-dotnet/wiki/Client-credential-flows) adlı GitHub sayfasında sertifikalar hakkında daha fazla bilgi edinebilirsiniz.

## <a name="method"></a>Yöntem

1. [İçeriğinizi hizmet sorumlusuyla ekleme](embed-service-principal.md).

2. [Sertifika oluşturma](embed-service-principal-certificate.md#step-2---create-a-certificate).

3. [Sertifikası kimlik doğrulaması ayarlama](embed-service-principal-certificate.md#step-3---set-up-certificate-authentication).

4. [Sertifikayı Azure Key Vault’tan alma](embed-service-principal-certificate.md#step-4---get-the-certificate-from-azure-key-vault).

5. [Hizmet sorumlusu ve sertifika kullanarak kimlik doğrulaması yapma](embed-service-principal-certificate.md#step-5---authenticate-using-service-principal-and-a-certificate).

## <a name="step-1---embed-your-content-with-service-principal"></a>1\. Adım: İçeriğinizi hizmet sorumlusuyla ekleme

İçeriğinizi hizmet sorumlusuyla eklemek için [Hizmet sorumlusu ve uygulama gizli dizisiyle Power BI içeriği ekleme](embed-service-principal.md) sayfasındaki yönergeleri izleyin.

>[!NOTE]
>Hizmet sorumlusu kullanılarak eklenmiş olan içeriğiniz varsa bu adımı atlayıp [2. adıma](embed-service-principal-certificate.md#step-2---create-a-certificate) geçin.

## <a name="step-2---create-a-certificate"></a>2\. Adım: Sertifika oluşturma

Güvenilir bir *Sertifika Yetkilisi*’nden bir sertifika temin edebilir veya kendiniz bir sertifika oluşturabilirsiniz.

Bu bölümde, [Azure Key Vault](/azure/key-vault/create-certificate) kullanılarak bir sertifika oluşturma ve genel anahtar içeren *.cer* dosyasını indirme işlemleri açıklanmaktadır.

1. [Microsoft Azure](https://ms.portal.azure.com/#allservices)’da oturum açın.

2. **Anahtar Kasaları**’nı arayın ve **Anahtar Kasaları** bağlantısına tıklayın.

    ![Azure portalındaki anahtar kasası bağlantısını gösteren ekran görüntüsü.](media/embed-service-principal-certificate/key-vault.png)

3. Sertifika eklemek istediğiniz anahtar kasasına tıklayın.

    ![Azure portalındaki anahtar kasalarının bulanık bir listesini gösteren ekran görüntüsü.](media/embed-service-principal-certificate/select-key-vault.png)

4. **Sertifikalar**’a tıklayın.

    ![Sertifikalar'ın vurgulandığı Anahtar kasaları sayfasını gösteren ekran görüntüsü.](media/embed-service-principal-certificate/certificates.png)

5. **Oluştur/İçeri Aktar**’a tıklayın.

    ![Oluştur/İçeri Aktar seçeneğinin vurgulandığı Sertifika bölmesini gösteren ekran görüntüsü.](media/embed-service-principal-certificate/generate.png)

6. **Sertifika oluştur** alanlarını aşağıdaki şekilde yapılandırın:

    * **Sertifika Oluşturma Yöntemi** - Genel

    * **Sertifika Adı** - Sertifikanız için bir ad girin

    * **Sertifika Yetkilisi (CA) Türü** - Otomatik olarak imzalanan sertifika

    * **Konu** - [X.500](https://wikipedia.org/wiki/X.500) ayırt edici adı

    * **DNS Adları** - 0 DNS adı

    * **Geçerlilik Süresi (ay)** - Sertifikanın geçerlilik süresini girin

    * **İçerik Türü** - PKCS #12

    * **Yaşam Süresi Eylem Türü** - Belirli bir yaşam süresi yüzdesinde otomatik olarak yeniler

    * **Yaşam Süresi Yüzdesi** - 80

    * **Gelişmiş İlke Yapılandırması** - Yapılandırılmamış

7. **Oluştur**'a tıklayın. Yeni oluşturulan sertifika varsayılan olarak devre dışı bırakılır. Etkinleştirilmeleri beş dakikaya kadar sürebilir.

8. Oluşturduğunuz sertifikayı seçin.

9. **CER biçiminde indir**’e tıklayın. İndirilen dosyada ortak anahtar yer alır.

    ![CER biçiminde indir düğmesini gösteren ekran görüntüsü.](media/embed-service-principal-certificate/download-cer.png)

## <a name="step-3---set-up-certificate-authentication"></a>3\. Adım: Sertifika kimlik doğrulaması ayarlama

1. Azure AD uygulamanızda **Sertifikalar ve gizli diziler** sekmesine tıklayın.

     ![Azure portalında bir uygulamanın Sertifikalar ve gizli diziler bölmesini gösteren ekran görüntüsü.](media/embed-service-principal/certificates-and-secrets.png)

2. **Sertifikayı karşıya yükle**’ye tıklayın ve bu öğreticinin [2. adımında](#step-2---create-a-certificate) oluşturup indirdiğiniz *.cer* dosyasını karşıya yükleyin. *.cer* dosyası ortak anahtarı içerir.

## <a name="step-4---get-the-certificate-from-azure-key-vault"></a>4\. Adım: Azure Key Vault’tan bir sertifikayı alma

Azure Key Vault’tan sertifikayı almak için Yönetilen Hizmet Kimliği’ni (MSI) kullanın. Bu işlem, hem ortak hem de özel anahtarları içeren *.pfx* sertifikasını almayı içerir.

Azure Key Vault’tan sertifikayı okumak için kod örneğine başvurun. Visual Studio kullanmak istiyorsanız [Visual Studio’yu MSI kullanacak şekilde yapılandırma](#configure-visual-studio-to-use-msi) sayfasına başvurun.

```csharp
private X509Certificate2 ReadCertificateFromVault(string certName)
{
    var serviceTokenProvider = new AzureServiceTokenProvider();
    var keyVaultClient = new KeyVaultClient(new KeyVaultClient.AuthenticationCallback(serviceTokenProvider.KeyVaultTokenCallback));
    CertificateBundle certificate = null;
    SecretBundle secret = null;
    try
    {
        certificate = keyVaultClient.GetCertificateAsync($"https://{KeyVaultName}.vault.azure.net/", certName).Result;
        secret = keyVaultClient.GetSecretAsync(certificate.SecretIdentifier.Identifier).Result;
    }
    catch (Exception)
    {
        return null;
    }

    return new X509Certificate2(Convert.FromBase64String(secret.Value));
}
```

## <a name="step-5---authenticate-using-service-principal-and-a-certificate"></a>5\. Adım: Hizmet sorumlusu ve sertifika kullanarak kimlik doğrulaması yapma

Azure Key Vault’a bağlanıp burada depolanan hizmet sorumlusunu ve sertifikayı kullanarak uygulamanızın kimliğini doğrulayabilirsiniz.

Azure Key Vault’a bağlanıp sertifikayı okumak için aşağıdaki koda bakın.

>[!NOTE]
>Kuruluşunuz tarafından oluşturulan bir sertifikaya zaten sahipseniz *.pfx* dosyasını Azure Key Vault’a yükleyin.

```csharp
// Preparing needed variables
var Scope = "https://analysis.windows.net/powerbi/api/.default"
var ApplicationId = "{YourApplicationId}"
var tenantSpecificURL = "https://login.microsoftonline.com/{YourTenantId}/"
X509Certificate2 certificate = ReadCertificateFromVault(CertificateName);

// Authenticating with a SP and a certificate
public async Task<AuthenticationResult> DoAuthentication(){
    IConfidentialClientApplication clientApp = null;
    clientApp = ConfidentialClientApplicationBuilder.Create(ApplicationId)
                                                    .WithCertificate(certificate)
                                                    .WithAuthority(tenantSpecificURL)
                                                    .Build();
    try
    {
        authenticationResult = await clientApp.AcquireTokenForClient(Scope).ExecuteAsync();
    }
    catch (MsalException)
    {
        throw;
    }
    return authenticationResult
}
```

## <a name="configure-visual-studio-to-use-msi"></a>Visual Studio’yu MSI kullanacak şekilde yapılandırma

Ekli çözümünüzü oluştururken Visual Studio’yu Yönetilen Hizmet Kimliği’ni (MSI) kullanacak şekilde yapılandırmanız yararlı olabilir. [MSI](/azure/active-directory/managed-identities-azure-resources/overview), Azure AD kimliğinizi yönetmenizi sağlayan bir özelliktir. Yapılandırıldıktan sonra, Visual Studio’nun Azure Key Vault’a göre kimlik doğrulaması yapmasını sağlar.

1. Projenizi Visual Studio’da açın.

2. **Araçlar** > **Seçenekler**’e tıklayın.

     ![Visual Studio'nun Araçlar menüsündeki Seçenekler düğmesini gösteren ekran görüntüsü.](media/embed-service-principal-certificate/visual-studio-options.png)

3. **Hesap Seçimi**’ni arayın ve **Hesap Seçimi**’ne tıklayın.

    ![Visual Studio'nun seçenekler penceresindeki Hesap seçimi seçeneğini gösteren ekran görüntüsü.](media/embed-service-principal-certificate/account-selection.png)

4. Azure Key Vault’unuz erişimi olan hesabı ekleyin.

## <a name="next-steps"></a>Sonraki adımlar

>[!div class="nextstepaction"]
>[Uygulamayı kaydetme](register-app.md)

> [!div class="nextstepaction"]
>[Müşterileriniz için Power BI Embedded](embed-sample-for-customers.md)

>[!div class="nextstepaction"]
>[Azure Active Directory'deki uygulama ve hizmet sorumlusu nesneleri](/azure/active-directory/develop/app-objects-and-service-principals)

>[!div class="nextstepaction"]
>[Hizmet sorumlusuyla şirket içi veri ağ geçidinde satır düzeyi güvenlik kullanma](embedded-row-level-security.md#on-premises-data-gateway-with-service-principal)