---
title: Daha iyi tümleşik BI içgörüleri için bir Power BI tümleşik analizleri uygulamasında Power BI içeriklerini tümleştirmek üzere uygulama kaydetme
description: Power BI içeriği eklemek üzere bir uygulamayı Azure Active Directory'ye kaydetmeyi öğrenin. Power BI tümleşik analiz kullanarak daha iyi tümleşik BI içgörüleri elde edin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: nishalit
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: how-to
ms.date: 04/02/2019
ms.openlocfilehash: 624e0a2838a08d1cf68ae58223fe979a56312b48
ms.sourcegitcommit: 1cad78595cca1175b82c04458803764ac36e5e37
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/19/2021
ms.locfileid: "98565942"
---
# <a name="register-an-azure-ad-application-to-use-with-power-bi"></a>Power BI ile kullanmak için Azure AD uygulamasını kaydetme

Power BI'ın tümleşik analiz özelliğini kullanmak için Azure'da bir Azure Active Directory (Azure AD) uygulaması kaydetmeniz gerekir. Azure AD uygulaması, Power BI REST kaynaklarıyla ilgili izinleri belirler ve [Power BI REST API'lerine](/rest/api/power-bi/) erişim izni verir.

## <a name="determine-your-embedding-solution"></a>Ekleme çözümünüzü belirleme

Uygulamanızı kaydetmeden önce sizin için en uygun çözümün aşağıdakilerden hangisi olduğuna karar verin:

* Müşterileriniz için ekleme
* Kuruluşunuz için ekleme

### <a name="embed-for-your-customers"></a>Müşterileriniz için ekleme

Müşterileriniz için tasarlanan bir uygulama oluşturmayı planlıyorsanız [müşterileriniz için ekleme](embed-sample-for-customers.md) çözümünü (*veriler uygulamaya aittir* olarak da bilinir) kullanın. Kullanıcıların uygulamanızı kullanabilmek için Power BI'da oturum açmaları veya Power BI lisansına sahip olmaları gerekmez. Uygulamanız, Power BI kimlik doğrulaması için aşağıdaki yöntemlerden birini kullanır:

* **Ana kullanıcı** hesabı (Power BI'da oturum açmak için kullanılan bir Power BI Pro lisansı)

* [Hizmet sorumlusu](embed-service-principal.md)

Müşterileriniz için ekleme çözümü genellikle bağımsız yazılım satıcıları (ISV) ve üçüncü taraflar için uygulama tasarlayan geliştiriciler tarafından kullanılır.

### <a name="embed-for-your-organization"></a>Kuruluşunuz için ekleme

Kullanıcıların Power BI kimlik doğrulaması için kimlik bilgilerini kullanmalarını gerektiren bir uygulama oluşturmayı planlıyorsanız [kuruluşunuz için ekleme](embed-sample-for-your-organization.md) çözümünü (*veriler kullanıcıya aittir* olarak da bilinir) kullanın.

Kuruluşunuz için ekleme çözümü genellikle kurumsal şirketler ve büyük kuruluşlar tarafından kullanılır ve şirket içi kullanıcılara yöneliktir.

## <a name="register-an-azure-ad-app"></a>Azure AD uygulamasını kaydetme

Bir Azure AD uygulamasını kaydetmenin en kolay yolu [Power BI ekleme kurulum aracını](https://app.powerbi.com/embedsetup) kullanmaktır. Bu araç, iki ekleme çözümü için de basit bir grafik arabirim üzerinden hızlı bir kayıt süreci sunar.

*Kuruluşunuz için ekleme* uygulaması oluşturuyorsanız ve Azure AD uygulamanızın üzerinde daha fazla kontrol sahibi olmak istiyorsanız Azure portalında el ile kaydedebilirsiniz.

> [!IMPORTANT]
> Bir Power BI uygulamasını kaydedebilmek için [Azure Active Directory kiracısına ve kuruluş kullanıcısına](create-an-azure-active-directory-tenant.md) sahip olmanız gerekir.

# <a name="embed-for-your-customers"></a>[Müşterileriniz için ekleme](#tab/customers)

Bu adımlarda bir Azure AD uygulamasını Power BI [müşterileriniz için ekleme](embed-sample-for-customers.md) çözümüne nasıl kaydedebileceğiniz anlatılmıştır.

[!INCLUDE[registration tool step 1](../../includes/register-tool-step-1.md)]

2. *Ekleme çözümü seçin* bölümünde **Müşterileriniz için ekleme**'yi seçin.

[!INCLUDE[registration tool step 3](../../includes/register-tool-step-3.md)]

4. *2. Adım: Uygulamanızı kaydetme* bölümünde bulunan alanları aşağıdaki şekilde doldurun:

    * **Uygulama Adı**: Uygulamanıza bir ad verin.

    * **API erişimi**: Uygulamanızın ihtiyaç duyduğu Power BI API'lerini (kapsam olarak da bilinir) seçin. *Tümünü seç*'i kullanarak tüm API'leri seçebilirsiniz. Power BI erişim izinleri hakkında daha fazla bilgi için bkz. [Microsoft kimlik platformu uç noktasında izinler ve onay](/azure/active-directory/develop/v2-permissions-and-consent).

5. **Kaydet**’i seçin.

    Azure AD uygulamanızın **Uygulama Kimliği**, *Özet* kutusunda gösterilir. Bu değeri daha sonra kullanmak üzere kopyalayın.

[!INCLUDE[registration tool steps 6-7](../../includes/register-tool-steps-6-7.md)]

8. *5. Adım: İzin verme* bölümünde **İzin ver**'i seçip açılan pencerede **Kabul et**'i seçin. Bunu yaptığınızda Azure AD uygulamanızın oturum açmış olan kullanıcıyla seçtiğiniz API'lere (kapsam olarak da bilinir) erişmesine izin verilir. Bu kullanıcı, **ana kullanıcı** olarak da bilinir.

9. (İsteğe bağlı) Bir Power BI çalışma alanı oluşturduysanız ve aracı kullanarak buraya içerik yüklediyseniz bu aşamada **Örnek uygulamayı indir**'i seçebilirsiniz. *Özet* kutusundaki tüm bilgileri kopyalamayı unutmayın.

[!INCLUDE[registration tool note](../../includes/register-tool-note.md)]

# <a name="embed-for-your-organization"></a>[Kuruluşunuz için ekleme](#tab/organization)

Bu adımlarda bir Azure AD uygulamasını Power BI [kuruluşunuz için ekleme](embed-sample-for-your-organization.md) çözümüne nasıl kaydedebileceğiniz anlatılmıştır.

[!INCLUDE[registration tool step 1](../../includes/register-tool-step-1.md)]

2. *Ekleme çözümü seçin* bölümünde **Kuruluşunuz için ekleme**'yi seçin.

[!INCLUDE[registration tool step 3](../../includes/register-tool-step-3.md)]

4. *2. Adım: Uygulamanızı kaydetme* bölümünde bulunan alanları aşağıdaki şekilde doldurun:

    * **Uygulama Adı**: Uygulamanıza bir ad verin.

    * **Giriş Sayfası URL'si**: Giriş sayfanız için bir URL girin.

    * **Yeniden Yönlendirme URL'si**: Kullanıcılar uygulamanızda oturum açtıktan sonra uygulama, Azure'dan bir kimlik doğrulaması kodu alırken bu adrese yönlendirilir. Şu seçeneklerden birini belirtin:

        * **Varsayılan URL kullan**: Bu seçenek otomatik olarak örnek bir tümleşik analiz uygulaması oluşturur ve indirir. Varsayılan URL: http://localhost:13526/.

        * **Özel URL kullan**: Bir tümleşik analiz uygulamanız varsa ve yeniden yönlendirme URL'si olarak kullanmak istediğiniz adresi biliyorsanız bu seçeneği belirleyin.

    * **API erişimi**: Uygulamanızın ihtiyaç duyduğu Power BI API'lerini (kapsam olarak da bilinir) seçin. *Tümünü seç*'i kullanarak tüm API'leri seçebilirsiniz. Power BI erişim izinleri hakkında daha fazla bilgi için bkz. [Microsoft kimlik platformu uç noktasında izinler ve onay](/azure/active-directory/develop/v2-permissions-and-consent).

5. **Kaydet**’i seçin.

    Azure AD uygulamanızın **Uygulama Kimliği** ve **Uygulama gizli dizisi** değerleri *Özet* kutusunda görüntülenir. Bu değerleri daha sonra kullanmak üzere kopyalayın.

[!INCLUDE[registration tool steps 6-7](../../includes/register-tool-steps-6-7.md)]

8. (İsteğe bağlı) Bir Power BI çalışma alanı oluşturduysanız ve aracı kullanarak buraya içerik yüklediyseniz bu aşamada **Örnek uygulamayı indir**'i seçebilirsiniz. *Özet* kutusundaki tüm bilgileri kopyalamayı unutmayın.

[!INCLUDE[registration tool note](../../includes/register-tool-note.md)]

# <a name="manual-registration"></a>[El ile kayıt](#tab/manual)

Azure AD el ile uygulama kaydı seçeneğini yalnızca aşağıdaki çözümlerden birini oluşturmak için kullanın:

* *Kuruluşunuz için ekleme* uygulaması.

* *Hizmet sorumlusu* ile *müşterileriniz için ekleme* uygulaması.

    >[!NOTE]
    >Bu seçeneği belirlerseniz Azure AD uygulamanızı kaydettikten sonra [Power BI izinleri eklemeniz](#change-your-azure-ad-apps-permissions) gerekir.

Uygulamalarınızı Azure Active Directory'ye kaydetme hakkında bilgi almak için bkz. [Azure Active Directory’ye uygulama kaydetme](/azure/active-directory/develop/quickstart-v2-register-an-app).

1. [Azure portalında](https://portal.azure.com) oturum açın.

2. Sayfanın sağ üst köşesinden hesabınızı seçerek Azure AD kiracınızı belirleyin.

3. **Uygulama kayıtları**’nı seçin. Bu seçeneği göremiyorsanız arama yapın.
 
4. *Uygulama kayıtları* bölümünde **Yeni kayıt**'ı seçin.

5. Şu alanları doldurun:

    * **Ad**: Uygulamanıza bir ad verin.

    * **Desteklenen hesap türü**: Uygulamayı kullanabilecek kişileri seçin.

6. (İsteğe bağlı) **Yeniden yönlendirme URL'si** bölümünde bir yeniden yönlendirme URL'si ekleyin.

7. **Kaydet**’i seçin. Uygulamanız kaydedildikten sonra uygulamanızın genel bakış sayfasına yönlendirilirsiniz. *Uygulama kimliği* değerini bu sayfada görebilirsiniz.

---

## <a name="change-your-azure-ad-apps-permissions"></a>Azure AD uygulamanızın izinlerini değiştirme

Uygulamanızı kaydettikten sonra izinlerinde değişiklikler yapabilirsiniz. İzin değişikliklerini program aracılığıyla veya Azure portalından gerçekleştirebilirsiniz.

>[!NOTE]
>Azure AD uygulama izinleri yalnızca *ana kullanıcı* kimlik doğrulama yöntemini kullanan *müşterileriniz için ekleme* çözümüyle kullanılabilir.

# <a name="azure"></a>[Azure](#tab/Azure)

Azure portalında uygulamanızı görüntüleyebilir ve izinlerinde değişiklikler yapabilirsiniz.

1. [Azure portalında](https://portal.azure.com) oturum açın.

2. Sayfanın sağ üst köşesinden hesabınızı seçerek Azure AD kiracınızı belirleyin.

3. **Uygulama kayıtları**’nı seçin. Bu seçeneği göremiyorsanız arama yapın.

4. **Sahip olunan uygulamalar** sekmesinde uygulamanızı seçin. Uygulamanın *Genel bakış* sekmesi açılır ve burada *Uygulama kimliği* değerini görebilirsiniz.

5. **API izinleri** sekmesini seçin.

6. İzin eklemek için şu adımları izleyin:

    1. **İzin ekle**'yi ve ardından **Power BI hizmeti**'ni seçin.

    2. **Temsilci İzinleri**'ni seçip istediğiniz izinleri ekleyin veya kaldırın.

    3. İşiniz bittiğinde **İzin ekle**'yi seçerek yaptığınız değişiklikleri kaydedin.

7. Bir izni kaldırmak için aşağıdaki adımları izleyin:

    1. İznin sağ tarafındaki üç nokta (...) simgesini seçin.
    
    2. **İzni kaldır**'ı seçin.
    
    3. *İzni kaldır* açılan penceresinde **Evet, kaldır**'ı seçin.

# <a name="http"></a>[HTTP](#tab/HTTP)

Azure AD uygulama izinlerinizi program aracılığıyla değiştirmek için kiracınızın içindeki var olan hizmet sorumlularını (kullanıcıları) almanız gerekir. Bunu nasıl yapacağınız hakkında bilgi almak için bkz. [servicePrincipal](/graph/api/resources/serviceprincipal).

1. Kiracınızdaki tüm hizmet sorumlularını almak için `Get servicePrincipal` API'sini `{ID}` olmadan çağırın.

2. `appId` özelliği *uygulamanızın kimliği* olan hizmet sorumlusunu bulun.

    ```json
    Post https://graph.microsoft.com/v1.0/servicePrincipals HTTP/1.1
    Authorization: Bearer ey..qw
    Content-Type: application/json
    {
    "accountEnabled" : true,
    "appId" : "{App_Client_ID}",
    "displayName" : "{App_DisplayName}"
    }
    ```

    >[!NOTE]
    >`displayName` isteğe bağlıdır.

3. `consentType` için şu değerlerden birini atayarak uygulamanıza Power BI izinleri verin:

    * `AllPrincipals`: Kiracıdaki tüm kullanıcılar adına izin vermek için yalnızca bir Power BI yöneticisi tarafından kullanılabilir.

    * `Principal`: Belirli bir kullanıcı adına izinler vermek için kullanılabilir. Bu seçeneği kullanıyorsanız `principalId={User_ObjectId}` özelliğini istek gövdesine ekleyin.

     ```json
     Post https://graph.microsoft.com/v1.0/OAuth2PermissionGrants HTTP/1.1
     Authorization: Bearer ey..qw
     Content-Type: application/json
     {
     "clientId":"{Service_Plan_ID}",
     "consentType":"AllPrincipals",
     "resourceId":"c78a3685-1ce7-52cd-95f7-dc5aea8ec98e",
     "scope":"Dataset.ReadWrite.All Dashboard.Read.All Report.Read.All Group.Read Group.Read.All Content.Create Metadata.View_Any Dataset.Read.All Data.Alter_Any",
     "expiryTime":"2018-03-29T14:35:32.4943409+03:00",
     "startTime":"2017-03-29T14:35:32.4933413+03:00"
     }
     ```

    >[!NOTE]
    >* **Ana kullanıcı** kullanıyorsanız Azure AD'nin onay istemesinden kaçınmak için izinleri ana hesaba vermeniz gerekir.
    >* `resourceId` *c78a3685-1ce7-52cd-95f7-dc5aea8ec98e* kiracıya bağımlıdır ve evrensel değildir. Bu değer, Azure AD'de *Power BI Hizmeti* uygulamasının *objectId* değeridir. Bu değeri Azure portalından almak için [Kurumsal uygulamalar > Tüm uygulamalar](https://portal.azure.com/#blade/Microsoft_AAD_IAM/StartboardApplicationsMenuBlade/AllApps) yolunu izleyip *Power BI Hizmeti* araması yapın.

4. `consentType` için bir değer atayarak Azure AD'ye uygulama izni verin.

    ```json
    Post https://graph.microsoft.com/v1.0/OAuth2PermissionGrants HTTP/1.1
    Authorization: Bearer ey..qw
    Content-Type: application/json
    {
    "clientId":"{Service_Plan_ID}",
    "consentType":"AllPrincipals",
    "resourceId":"61e57743-d5cf-41ba-bd1a-2b381390a3f1",
    "scope":"User.Read Directory.AccessAsUser.All",
    "expiryTime":"2018-03-29T14:35:32.4943409+03:00",
    "startTime":"2017-03-29T14:35:32.4933413+03:00"
    }
    ```

# <a name="c"></a>[C#](#tab/CSharp)

Azure AD uygulamanızın izinlerini C# kullanarak da değiştirebilirsiniz. Daha fazla bilgi için [oAuth2PermissionGrant](/graph/api/oauth2permissiongrant-get) API’sine göz atın. Sürecinizin bir bölümünü otomatikleştirmeyi düşünüyorsanız bu yöntem fayda sağlayabilir.

HTTP istekleri hakkında daha fazla bilgi için [HTTP sekmesine](register-app.md?tabs=customers%2CHTTP#change-your-azure-ad-apps-permissions) bakın.

```csharp
var graphClient = GetGraphClient();

currentState.createdApp = await graphClient.Applications
    .Request()
    .AddAsync(application);

System.Threading.Thread.Sleep(2000);

var passwordCredential = new PasswordCredential
{
    DisplayName = "Client Secret Created in C#"
};

currentState.createdSecret = await graphClient.Applications[currentState.createdApp.Id]
    .AddPassword(passwordCredential)
    .Request()
    .PostAsync();

var servicePrincipal = new ServicePrincipal
{
    AppId = currentState.createdApp.AppId
};

currentState.createdServicePrincipal = await graphClient.ServicePrincipals
    .Request()
    .AddAsync(servicePrincipal);

GraphServiceClient graphClient = new GraphServiceClient(authProvider);

// Use oAuth2PermissionGrant to change permissions
var oAuth2PermissionGrant = await graphClient.Oauth2PermissionGrants["{id}"]
               .Request()
               .GetAsync();
```

---

## <a name="next-steps"></a>Sonraki adımlar

>[!div class="nextstepaction"]
>[Power BI uygulamanız için Azure AD erişim belirteci alma](get-azuread-access-token.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)