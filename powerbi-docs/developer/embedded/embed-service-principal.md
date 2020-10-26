---
title: Hizmet sorumlusu ve uygulama gizli dizisiyle Power BI içeriği ekleme
description: Azure Active Directory uygulama hizmet sorumlusu ve uygulama gizli dizisi kullanarak ekli analizin kimliğini doğrulamayı öğrenin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: how-to
ms.custom: ''
ms.date: 10/15/2020
ms.openlocfilehash: 6f6a13f239d1bcfa7731361f4efcd129da7e2031
ms.sourcegitcommit: 1428acb6334649fc2d3d8ae4c42cfbc17e8f7476
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/19/2020
ms.locfileid: "92197760"
---
# <a name="embed-power-bi-content-with-service-principal-and-an-application-secret"></a>Hizmet sorumlusu ve uygulama gizli dizisiyle Power BI içeriği ekleme

[!INCLUDE[service principal overview](../../includes/service-principal-overview.md)]

Bu makalede, *Uygulama Kimliği* ve *Uygulama gizli dizisi* kullanılarak hizmet sorumlusu kimlik doğrulaması açıklanmaktadır.

>[!NOTE]
>Arka uç hizmetlerinizin güvenliğini, gizli diziler yerine sertifikaları kullanarak sağlamanızı öneririz.
>* [Gizli dizileri veya sertifikaları kullanarak Azure AD’den erişim belirteçlerini alma hakkında daha fazla bilgi edinin](/azure/architecture/multitenant-identity/client-assertion).
>* [Hizmet sorumlusu ve sertifikayla Power BI içeriği ekleme](embed-service-principal-certificate.md).

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

* Uygulamayı [Microsoft Azure portalında](https://portal.azure.com/#allservices) oluşturma.

* Uygulamayı [PowerShell](/powershell/azure/create-azure-service-principal-azureps) kullanarak oluşturma.

### <a name="creating-an-azure-ad-app-in-the-microsoft-azure-portal"></a>Microsoft Azure portalında Azure AD uygulaması oluşturma

[!INCLUDE[service create app](../../includes/service-principal-create-app.md)]

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
[!INCLUDE[service create steps two, three and four](../../includes/service-principal-create-steps.md)]

## <a name="step-5---embed-your-content"></a>5\. Adım: İçeriğinizi ekleme

İçeriğinizi örnek bir uygulamanın veya kendi uygulamanızın içine ekleyebilirsiniz.

* [Örnek uygulamayı kullanarak içeriği ekleme](embed-sample-for-customers.md#embed-content-using-the-sample-application)
* [İçeriği uygulamanızın içine ekleme](embed-sample-for-customers.md#embed-content-within-your-application)

İçeriğinizi ekledikten sonra [üretime taşımaya](embed-sample-for-customers.md#move-to-production) hazırsınızdır.

[!INCLUDE[service principal limitations](../../includes/service-principal-limitations.md)]

## <a name="next-steps"></a>Sonraki adımlar

>[!div class="nextstepaction"]
>[Uygulamayı kaydetme](register-app.md)

> [!div class="nextstepaction"]
>[Müşterileriniz için Power BI Embedded](embed-sample-for-customers.md)

>[!div class="nextstepaction"]
>[Azure Active Directory'deki uygulama ve hizmet sorumlusu nesneleri](/azure/active-directory/develop/app-objects-and-service-principals)

>[!div class="nextstepaction"]
>[Hizmet sorumlusuyla şirket içi veri ağ geçidinde satır düzeyi güvenlik kullanma](embedded-row-level-security.md#on-premises-data-gateway-with-service-principal)

>[!div class="nextstepaction"]
>[Hizmet sorumlusu ve sertifikayla Power BI içeriği ekleme](embed-service-principal-certificate.md)