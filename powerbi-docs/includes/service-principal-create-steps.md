---
title: Hizmet sorumlusu oluşturma uygulaması
description: Hizmet sorumlusu oluşturma uygulaması
services: powerbi
author: KesemSharabi
ms.author: kesharab
ms.topic: include
ms.date: 10/15/2020
ms.custom: include file
ms.openlocfilehash: 0f6c74ddc5a7decc8c1a6444568de44d3adbbc68
ms.sourcegitcommit: 8561902ef0ad63b0881187a22f25d1aa1ec3bcbc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2020
ms.locfileid: "92210713"
---
## <a name="step-2---create-an-azure-ad-security-group"></a>2\. Adım: Azure AD güvenlik grubu oluşturma

Hizmet sorumlunuz Power BI içeriklerinize ve API’lerinize erişemez. Hizmet sorumlusuna erişim vermek için Azure AD’de bir güvenlik grubu oluşturun ve oluşturduğunuz hizmet sorumlusunu bu güvenlik grubuna ekleyin.

Azure AD güvenlik grubu oluşturmanın iki yolu vardır:
* El ile (Azure’da)
* PowerShell'i kullanma

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
>:::image type="content" source="../developer/embedded/media/embed-service-principal/admin-portal.png" alt-text="Power BI portalındaki yönetici seçeneklerinde bulunan geliştirici ayarlarını gösteren ekran görüntüsü.":::

## <a name="step-4---add-the-service-principal-to-your-workspace"></a>4\. Adım: Hizmet sorumlusunu çalışma alanınıza ekleme

Power BI hizmetindeki raporlar, panolar ve veri kümeleri gibi Azure AD uygulama erişim yapıtlarınızı etkinleştirmek için, hizmet sorumlusu varlığını çalışma alanınıza üye veya yönetici olarak ekleyin.

>[!NOTE]
>Bu bölümde, kullanıcı arabirimi yönergeleri sağlanır. Ayrıca, [Gruplar - grup kullanıcı API’si eklemeyi](/rest/api/power-bi/groups/addgroupuser) kullanarak çalışma alanına bir hizmet sorumlusu ekleyebilirsiniz.

1. Erişimini etkinleştirmek istediğiniz çalışma alanına gidin ve **Daha fazla** menüsünden **Çalışma alanı erişimini** seçin.

    :::image type="content" source="../developer/embedded/media/embed-service-principal/workspace-access.png" alt-text="Power BI portalındaki yönetici seçeneklerinde bulunan geliştirici ayarlarını gösteren ekran görüntüsü.":::

2. Hizmet sorumlusunu çalışma alanına **Yönetici** veya **Üye** olarak ekleyin.

    :::image type="content" source="../developer/embedded/media/embed-service-principal/add-service-principal-in-the-UI.png" alt-text="Power BI portalındaki yönetici seçeneklerinde bulunan geliştirici ayarlarını gösteren ekran görüntüsü.":::