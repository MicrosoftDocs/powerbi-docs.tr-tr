---
title: Bir ekli analiz uygulamasına hizmet sorumlusu ve uygulama gizli dizisi ile Power BI içeriği katıştırarak daha iyi tümleşik BI içgörüleri sağlama
description: Azure Active Directory uygulama hizmet sorumlusu ve uygulama gizli dizisi kullanarak ekli analizin kimliğini doğrulamayı öğrenin. Power BI tümleşik analiz kullanarak daha iyi tümleşik BI içgörüleri elde edin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: how-to
ms.custom: ''
ms.date: 02/04/2021
ms.openlocfilehash: 6a322d331dce9fd989a93545745cf7feb2d9eb70
ms.sourcegitcommit: afdc9d41da6a4fced63030648d3f976425131732
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/05/2021
ms.locfileid: "99569980"
---
# <a name="embed-power-bi-content-with-service-principal-and-an-application-secret"></a>Hizmet sorumlusu ve uygulama gizli dizisiyle Power BI içeriği ekleme

Hizmet sorumlusu, bir Azure AD uygulamasının Power BI hizmet içeriğine ve API’lerine erişmesine izin vermek için kullanılan bir kimlik doğrulaması yöntemidir.

Bir Azure Active Directory (Azure AD) uygulaması oluşturduğunuzda, bir [hizmet sorumlusu nesnesi](/azure/active-directory/develop/app-objects-and-service-principals#service-principal-object) oluşturulur. Yalnızca *hizmet sorumlusu* olarak da bilinen hizmet sorumlusu nesnesi, Azure AD’nin uygulamanızın kimliğini doğrulamasına olanak sağlar. Kimlik doğrulandıktan sonra uygulama, Azure AD kiracı kaynaklarına erişebilir.

Hizmet sorumlusu, kimlik doğrulaması yapmak için Azure AD uygulamasının *Uygulama Kimliğini* ve şunlardan birini kullanır:

* Sertifika
* Uygulama gizli dizisi

Bu makalede, *Uygulama Kimliği* ve *Uygulama gizli dizisi* kullanılarak hizmet sorumlusu kimlik doğrulaması açıklanmaktadır.

>[!NOTE]
>Azure AD arka uç hizmetlerinizin güvenliğini, gizli diziler yerine sertifikaları kullanarak sağlamanızı önerir.
>* [Gizli dizileri veya sertifikaları kullanarak Azure AD’den erişim belirteçlerini alma hakkında daha fazla bilgi edinin](/azure/architecture/multitenant-identity/client-assertion).
>* Çözümünüzün güvenliğini sertifika kullanarak sağlamak için bu makaledeki yönergeleri izledikten sonra [Hizmet sorumlusu ve sertifikayla Power BI içeriği ekleme](embed-service-principal-certificate.md) makalesine geçin.

## <a name="method"></a>Yöntem

Ekli analizlerle hizmet sorumlusunu ve uygulama kimliğini kullanmak için şu adımları izleyin:

1. [Azure AD uygulaması](/azure/active-directory/manage-apps/what-is-application-management) oluşturun.

    1. Azure AD uygulamasının gizli dizisini oluşturun.
    
    2. Uygulamanın *Uygulama Kimliğini* ve *Uygulama gizli dizisini* alın.

    >[!NOTE]
    >Bu adımlar, **1. Adım**’da açıklanmaktadır. Azure AD uygulaması oluşturma hakkında daha fazla bilgi için [Azure AD uygulaması oluşturma](/azure/active-directory/develop/howto-create-service-principal-portal) makalesine göz atın.

2. Bir Azure AD güvenlik grubu oluşturun.

3. Power BI hizmeti yönetici ayarlarını etkinleştirin.

4. Hizmet sorumlusunu çalışma alanınıza ekleyin.

5. İçeriğinizi ekleyin.

> [!IMPORTANT]
> Hizmet sorumlusunun Power BI ile kullanımını etkinleştirdikten sonra, uygulamanın AD izinleri artık geçerli olmaz. Bundan sonra uygulamanın izinleri Power BI yönetim portalı üzerinden yönetilir.

## <a name="step-1---create-an-azure-ad-app"></a>1\. Adım: Azure AD uygulaması oluşturma

Bu yöntemlerden birini kullanarak Azure AD uygulaması oluşturun:

* [Uygulamayı Microsoft Azure portalında oluşturma](embed-service-principal.md#creating-an-azure-ad-app-in-the-microsoft-azure-portal)

* [Uygulamayı PowerShell kullanarak oluşturma](embed-service-principal.md#creating-an-azure-ad-app-using-powershell)

### <a name="creating-an-azure-ad-app-in-the-microsoft-azure-portal"></a>Microsoft Azure portalında Azure AD uygulaması oluşturma

1. [Microsoft Azure](https://ms.portal.azure.com/#allservices)’da oturum açın.

2. **Uygulama kayıtlarını** arayın ve **Uygulama kayıtları** bağlantısına tıklayın.

    ![azure uygulaması kaydı](media/embed-service-principal/azure-app-registration.png)

3. **Yeni kayıt**’a tıklayın.

    ![yeni kayıt](media/embed-service-principal/new-registration.png)

4. Gereken bilgileri doldurun:
    * **Ad**: Uygulamanız için bir ad girin
    * **Desteklenen hesap türleri**: Desteklenen hesap türlerini seçin
    * (İsteğe bağlı) **Yeniden Yönlendirme URI’si**: Gerekirse bir URI girin

5. **Kaydet**’e tıklayın.

6. Kaydolduktan sonra, *Uygulama Kimliğini* **Genel Bakış** sekmesinde bulabilirsiniz. Daha sonra kullanmak için *Uygulama Kimliğini* kopyalayıp kaydedin.

    ![Genel Bakış sekmesinde Uygulama Kimliğinin alınacağı yeri gösteren ekran görüntüsü.](media/embed-service-principal/application-id.png)

7. **Sertifikalar ve gizli diziler** sekmesine tıklayın.

     ![Azure portalında bir uygulamanın Sertifikalar ve gizli diziler bölmesini gösteren ekran görüntüsü.](media/embed-service-principal/certificates-and-secrets.png)

8. **Yeni istemci gizli dizisine** tıklayın.

    ![Sertifikalar ve gizli diziler bölmesindeki Yeni istemci gizli dizisi düğmesini gösteren ekran görüntüsü.](media/embed-service-principal/new-client-secret.png)

9. *İstemci gizli dizisi ekle* penceresinde açıklama girin, istemci gizli dizisinin süresinin ne zaman dolmasını istediğinizi belirleyin ve **Ekle**’ye tıklayın.

10. *İstemci gizli dizisi* değerini kopyalayıp kaydedin.

    ![Sertifikalar ve gizli diziler bölmesindeki bulanık gizli dizi değerini gösteren ekran görüntüsü.](media/embed-service-principal/client-secret-value.png)

    >[!NOTE]
    >Siz bu pencereden çıktıktan sonra gizli dizi değeri gizlendiğinden, yeniden görüntüleyip kopyalayamazsınız.

### <a name="creating-an-azure-ad-app-using-powershell"></a>PowerShell kullanarak Azure AD uygulaması oluşturma

Bu bölüm, [PowerShell](/powershell/azure/create-azure-service-principal-azureps) kullanarak yeni bir Azure AD uygulaması oluşturmaya yönelik örnek betik içerir.

```powershell
# The app ID - $app.appid
# The service principal object ID - $sp.objectId
# The app key - $key.value

# Sign in as a user that's allowed to create an app
Connect-AzureAD

# Create a new Azure AD web application
$app = New-AzureADApplication -DisplayName "testApp1" -Homepage "https://localhost:44322" -ReplyUrls "https://localhost:44322"

# Creates a service principal
$sp = New-AzureADServicePrincipal -AppId $app.AppId

# Get the service principal key
$key = New-AzureADServicePrincipalPasswordCredential -ObjectId $sp.ObjectId
```

## <a name="step-2---create-an-azure-ad-security-group"></a>2\. Adım: Azure AD güvenlik grubu oluşturma

Hizmet sorumlunuz Power BI içeriklerinize ve API’lerinize erişemez. Hizmet sorumlusuna erişim vermek için Azure AD’de bir güvenlik grubu oluşturun ve oluşturduğunuz hizmet sorumlusunu bu güvenlik grubuna ekleyin.

Azure AD güvenlik grubu oluşturmanın iki yolu vardır:
* [El ile (Azure’da)](embed-service-principal.md#create-a-security-group-manually)
* [PowerShell'i kullanma](embed-service-principal.md#create-a-security-group-using-powershell)

### <a name="create-a-security-group-manually"></a>El ile güvenlik grubu oluşturma

El ile Azure güvenlik grubu oluşturmak için [Temel grup oluşturma ve Azure Active Directory kullanarak üye ekleme](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal) makalesindeki yönergeleri izleyin. 

### <a name="create-a-security-group-using-powershell"></a>PowerShell kullanarak güvenlik grubu oluşturma

Güvenlik grubu oluşturmak ve bu güvenlik grubuna uygulama eklemek için örnek betik aşağıda verilmiştir.

>[!NOTE]
>Hizmet sorumlusu erişimini kuruluşun tamamı için etkinleştirmek istiyorsanız bu adımı atlayın.

```powershell
# Required to sign in as admin
Connect-AzureAD

# Create an Azure AD security group
$group = New-AzureADGroup -DisplayName <Group display name> -SecurityEnabled $true -MailEnabled $false -MailNickName notSet

# Add the service principal to the group
Add-AzureADGroupMember -ObjectId $($group.ObjectId) -RefObjectId $($sp.ObjectId)
```

## <a name="step-3---enable-the-power-bi-service-admin-settings"></a>3\. Adım: Power BI hizmeti yönetici ayarlarını etkinleştirme

Bir Azure AD uygulamasının Power BI içeriğine ve API’lerine erişebilmesi için, bir Power BI yöneticisinin Power BI yönetici portalında hizmet sorumlusu erişimini etkinleştirmesi gerekir.

Azure AD’de oluşturduğunuz güvenlik grubunu **Geliştirici ayarlarının** belirli bir güvenlik grubu bölümüne ekleyin.

>[!IMPORTANT]
>Hizmet sorumluları, etkinleştirilmiş oldukları tüm kiracı ayarlarına erişebilir. Yönetici ayarlarınıza bağlı olarak bu, belirli güvenlik gruplarını veya kuruluşun tamamını içerir.
>
>Hizmet sorumlusu erişimini belirli kiracı ayarlarıyla sınırlamak için yalnızca belirli güvenlik gruplarına erişim izni verin. Dilerseniz hizmet sorumluları için ayrılmış bir güvenlik grubu oluşturabilir ev bu grubu istediğiniz kiracı ayarlarından dışlayabilirsiniz.

>[!div class="mx-imgBorder"]
>:::image type="content" source="media/embed-service-principal/admin-portal.png" alt-text="Power BI hizmetindeki yönetici seçeneklerinde bulunan geliştirici ayarlarını gösteren ekran görüntüsü.":::

## <a name="step-4---add-the-service-principal-to-your-workspace"></a>4\. Adım: Hizmet sorumlusunu çalışma alanınıza ekleme

Power BI hizmetindeki raporlar, panolar ve veri kümeleri gibi Azure AD uygulama erişim yapıtlarınızı etkinleştirmek için, hizmet sorumlusu varlığını veya hizmet sorumlunuzu içeren güvenlik grubunu çalışma alanınıza üye veya yönetici olarak ekleyin.

>[!NOTE]
>Bu bölümde, kullanıcı arabirimi yönergeleri sağlanır. Ayrıca, [Gruplar - grup kullanıcı API’si eklemeyi](/rest/api/power-bi/groups/addgroupuser) kullanarak çalışma alanına bir hizmet sorumlusu veya güvenlik grubu ekleyebilirsiniz.

1. Erişimini etkinleştirmek istediğiniz çalışma alanına gidin ve **Daha fazla** menüsünden **Çalışma alanı erişimini** seçin.

    :::image type="content" source="media/embed-service-principal/workspace-access.png" alt-text="Power BI çalışma alanının Daha fazla menüsündeki Çalışma alanı erişimi düğmesini gösteren ekran görüntüsü.":::

2. **Erişim** bölmesindeki metin kutusuna aşağıdakilerden birini ekleyin:

    * **Hizmet sorumlunuz**. Hizmet sorumlunuzun adı, Azure AD uygulamanızın *Görünen adı* olur ve Azure AD uygulamasının genel bakış sekmesinde görünür.

    * Hizmet sorumlunuzu içeren **güvenlik grubu**.

3. Açılan menüden **Üye**'yi veya **Yönetici**'yi seçin.

4. **Ekle**’yi seçin.

### <a name="add-a-service-principal-as-a-workspace-member-using-powershell"></a>PowerShell ile hizmet sorumlusunu bir çalışma alanı üyesi olarak ekleme

Bu bölümde [PowerShell](/powershell/azure/create-azure-service-principal-azureps) kullanıp bir hizmet sorumlusunu çalışma alanı üyesi olarak eklemeyi gösteren bir örnek betik yer alır.

```powershell
Login-PowerBI

# Service Principal Object ID for the created Service Principal
$SPObjectId = 'XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX'

$pbiWorkspace = Get-PowerBIWorkspace -Name "YourWorkspaceName"

Add-PowerBIWorkspaceUser -Id $pbiWorkspace.Id -AccessRight Member -PrincipalType App -Identifier $SPObjectId 

```

### <a name="add-a-security-group-as-a-workspace-member-using-powershell"></a>PowerShell ile güvenlik grubunu bir çalışma alanı üyesi olarak ekleme

Bu bölümde [PowerShell](/powershell/azure/create-azure-service-principal-azureps) kullanıp bir güvenlik grubunu çalışma alanı üyesi olarak eklemeyi gösteren bir örnek betik yer alır.

```powershell
Login-PowerBI

# Security Group Object ID for the created Security Group
$SGObjectId = 'XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX'

$pbiWorkspace = Get-PowerBIWorkspace -Name "YourWorkspaceName"

Add-PowerBIWorkspaceUser -Id $pbiWorkspace.Id -AccessRight Member -PrincipalType Group -Identifier $SGObjectId 

```

## <a name="step-5---embed-your-content"></a>5\. Adım: İçeriğinizi ekleme

[İçeriğinizi örnek bir uygulamanın](embed-sample-for-customers.md) veya kendi uygulamanızın içine ekleyebilirsiniz.

İçeriğinizi ekledikten sonra [üretime taşımaya](move-to-production.md) hazırsınızdır.

>[!NOTE]
>İçeriğinizin güvenliğini sertifika kullanarak sağlamak için [Hizmet sorumlusu ve sertifikayla Power BI içeriği ekleme](embed-service-principal-certificate.md) makalesindeki adımları izleyin.

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

* Hizmet sorumlusu yalnızca [yeni çalışma alanlarıyla](../../collaborate-share/service-create-the-new-workspaces.md) çalışır.
* Hizmet sorumlusu kullanırken **Çalışma Alanım** desteklenmez.
* Üretime geçilirken bir kapasite gerekir.
* Hizmet sorumlusunu kullanarak Power BI portalında oturum açamazsınız.
* Power BI yönetim portalındaki geliştirici ayarlarında hizmet sorumlusunu etkinleştirmek için Power BI yönetici hakları gereklidir.
* [Kuruluşunuz için eklenen](embed-sample-for-your-organization.md) uygulamalar hizmet sorumlusunu kullanamaz.
* [Veri akışları](../../transform-model/dataflows/dataflows-introduction-self-service.md) yönetimi desteklenmez.
* Hizmet sorumlusu yalnızca bazı salt okunurdur yönetim API 'Lerini destekler. Salt okunurdur yönetici API 'Leri için hizmet sorumlusu desteğini etkinleştirmek üzere kiracınızda Power BI hizmeti yönetici ayarlarını etkinleştirmeniz gerekir. Daha fazla bilgi için bkz. [salt okuma yönetici API 'leri için hizmet sorumlusu kimlik doğrulamasını etkinleştirme](../../admin/read-only-apis-service-principal-authentication.md).
* [Azure Analysis Services](/azure/analysis-services/analysis-services-overview) veri kaynağıyla hizmet sorumlusu kullanırken, hizmet sorumlusunun kendisinin Azure Analysis Services örneği izinleri olmalıdır. Bu amaçla hizmet sorumlusu içeren bir güvenlik grubu kullanmak işe yaramaz.

## <a name="next-steps"></a>Sonraki adımlar

>[!div class="nextstepaction"]
>[Uygulamayı kaydetme](register-app.md)

> [!div class="nextstepaction"]
>[Müşterileriniz için Power BI Embedded](embed-sample-for-customers.md)

>[!div class="nextstepaction"]
>[Hizmet sorumlusu ve sertifika kullanarak ekleme](embed-service-principal-certificate.md)

>[!div class="nextstepaction"]
>[Azure Active Directory'deki uygulama ve hizmet sorumlusu nesneleri](/azure/active-directory/develop/app-objects-and-service-principals)

>[!div class="nextstepaction"]
>[Hizmet sorumlusuyla şirket içi veri ağ geçidinde satır düzeyi güvenlik kullanma](embedded-row-level-security.md#on-premises-data-gateway-with-service-principal)