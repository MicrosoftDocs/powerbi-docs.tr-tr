---
title: "Power BI yönetici rolünü anlama"
description: "Power BI hizmetinde içeri aktarılan veri kümeleri ve DirectQuery için satır düzeyi güvenliği yapılandırma."
services: powerbi
documentationcenter: 
author: guyinacube
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 09/05/2017
ms.author: asaxton
ms.openlocfilehash: be5b63ad969ed7c1a341489973832a9f10a8dd46
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2017
---
# <a name="understanding-the-power-bi-admin-role"></a>Power BI yönetici rolünü anlama
Kuruluşunuzda Power BI yönetici rolünü nasıl kullanabileceğiniz hakkında bilgi edinin.

<iframe width="640" height="360" src="https://www.youtube.com/embed/PQRbdJgEm3k?showinfo=0" frameborder="0" allowfullscreen></iframe>

Power BI Yönetici Portalı'na erişmesi gereken kullanıcılara, Office 365 yönetici erişimi verilmeden Power BI Hizmet Yöneticisi rolü atanabilir. Örneğin, Genel Yönetici rolü. Bu rol, kuruluşları için Power BI'ı yönetmekle görevlendirilen kişiler için tasarlanmıştır.

Office 365 kullanıcı yöneticileri, Office 365 Yönetim merkezi'nden veya PowerShell betiği aracılığıyla kullanıcıları Power BI yöneticisi olarak atayabilir. Rol atandığında kullanıcı [Power BI yönetici portalına](service-admin-portal.md) erişebilir. Burada, kiracı genelinde kullanım ölçümlerine erişebilir ve Power BI özelliklerinin kiracı genelindeki kullanımını kontrol edebilirler.

![](media/service-admin-role/powerbi-admin-portal.png)

## <a name="using-the-office-365-admin-center-to-assign-a-role"></a>Rol atamak için Office 365 Yönetim merkezi'ni kullanma
Office 365 Yönetim merkezi'ni kullanarak kullanıcılara Power BI Yönetici rolü atamak için aşağıdaki işlemleri gerçekleştirebilirsiniz.

1. Office 365 Yönetim merkezi'ne gidin ve **Kullanıcılar** > **Etkin Kullanıcılar**'ı seçin.
   
    ![](media/service-admin-role/powerbi-admin-users.png)
2. Rolü atamak istediğiniz kullanıcıyı seçin.
3. Roller için **Düzenle**'yi seçin.
   
    ![](media/service-admin-role/powerbi-admin-edit-roles.png)
4. **Özelleştirilmiş yönetici** > **Power BI hizmet yöneticisi**'ni seçin
   
    ![](media/service-admin-role/powerbi-admin-role.png)
5. **Kaydet**'i seçin.

Söz konusu kullanıcının rolünün **Power BI hizmet yöneticisi** olarak değiştiğini görürsünüz. Kullanıcı artık [Power BI yönetici portalına](service-admin-portal.md) erişebilir.

![](media/service-admin-role/powerbi-admin-role-set.png)

## <a name="using-powershell-to-assign-a-role"></a>Rol atamak için PowerShell'i kullanma
PowerShell komutunu çalıştırmak için Azure Active Directory PowerShell Modülü yüklü olmalıdır.

### <a name="download-azure-ad-powershell-module"></a>Azure AD PowerShell modülünü indirme
[Azure Active Directory PowerShell 2 Sürümünü indirin](https://github.com/Azure/azure-docs-powershell-azuread/blob/master/Azure%20AD%20Cmdlets/AzureAD/index.md)

[Azure Active Directory PowerShell 1.1.166.0 GA Sürümünü indirin](http://connect.microsoft.com/site1164/Downloads/DownloadDetails.aspx?DownloadID=59185)

### <a name="command-to-add-role-to-member"></a>Üyeye rol ekleme komutu
**Azure AD PowerShell v2 Komutu**

**Power BI Hizmet Yöneticisi** rolü için **ObjectId** bilgisini almanız gerekir. **ObjectId** bilgisini almak için [Get-AzureADDirectoryRole](https://docs.microsoft.com/powershell/azuread/v2/get-azureaddirectoryrole) komutunu çalıştırabilirsiniz

```
PS C:\Windows\system32> Get-AzureADDirectoryRole

ObjectId                             DisplayName                        Description
--------                             -----------                        -----------
00f79122-c45d-436d-8d4a-2c0c6ca246bf Power BI Service Administrator     Full access in the Power BI Service.
250d1222-4bc0-4b4b-8466-5d5765d14af9 Helpdesk Administrator             Helpdesk Administrator has access to perform..
3ddec257-efdc-423d-9d24-b7cf29e0c86b Directory Synchronization Accounts Directory Synchronization Accounts
50daa576-896c-4bf3-a84e-1d9d1875c7a7 Company Administrator              Company Administrator role has full access t..
6a452384-6eb9-4793-8782-f4e7313b4dfd Device Administrators              Device Administrators
9900b7db-35d9-4e56-a8e3-c5026cac3a11 AdHoc License Administrator        Allows access manage AdHoc license.
a3631cce-16ce-47a3-bbe1-79b9774a0570 Directory Readers                  Allows access to various read only tasks in ..
f727e2f3-0829-41a7-8c5c-5af83c37f57b Email Verified User Creator        Allows creation of new email verified users.
```

Bu örnekte, role ilişkin ObjectId değeri 00f79122-c45d-436d-8d4a-2c0c6ca246bf'dir.

Ayrıca kullanıcıya ilişkin **ObjectID** değerini de bilmeniz gerekir. [Get-AzureADUser](https://docs.microsoft.com/powershell/azuread/v2/get-azureaduser) komutunu çalıştırarak bu değere ulaşabilirsiniz.

```
PS C:\Windows\system32> Get-AzureADUser -SearchString 'tim@contoso.com'

ObjectId                             DisplayName UserPrincipalName      UserType
--------                             ----------- -----------------      --------
6a2bfca2-98ba-413a-be61-6e4bbb8b8a4c Tim         tim@contoso.com        Member
```

Üyeyi role eklemek için [Add-AzureADDirectoryRoleMember](https://docs.microsoft.com/powershell/azuread/v2/add-azureaddirectoryrolemember) komutunu çalıştırın.

| Parametre | Açıklama |
| --- | --- |
| ObjectId |Role ilişkin ObjectId. |
| RefObjectId |Üyelere ilişkin ObjectId. |

```
Add-AzureADDirectoryRoleMember -ObjectId 00f79122-c45d-436d-8d4a-2c0c6ca246bf -RefObjectId 6a2bfca2-98ba-413a-be61-6e4bbb8b8a4c
```

**Azure AD PowerShell v1 Komutu**

Azure AD v1 cmdlet'lerini kullanarak üyeleri bir role eklemek için [Add-MsolRoleMember](https://docs.microsoft.com/powershell/msonline/v1/add-msolrolemember) komutunu çalıştırırsınız.

```
Add-MsolRoleMember -RoleMemberEmailAddress "tim@contoso.com" -RoleName "Power BI Service Administrator"
```

## <a name="limitations-and-considerations"></a>Sınırlamalar ve önemli noktalar
Power BI Hizmet Yöneticisi rolü aşağıdakilere erişim sağlamaz.

* Office 365 Yönetim merkezi'nde kullanıcıları ve lisansları değiştirme olanağı.
* Denetim günlüklerine erişim. Daha fazla bilgi için bkz. [Kuruluşunuzda denetim özelliğini kullanma](service-admin-auditing.md).

## <a name="next-steps"></a>Sonraki adımlar
[Power BI yönetici portalı](service-admin-portal.md)  
[Add-AzureADDirectoryRoleMember](https://docs.microsoft.com/powershell/azuread/v2/add-azureaddirectoryrolemember)  
[Add-MsolRoleMember](https://docs.microsoft.com/powershell/msonline/v1/add-msolrolemember)  
[Kuruluşunuzda Power BI'ı denetleme](service-admin-auditing.md)  
[Kuruluşunuzda Power BI'ı yönetme](service-admin-administering-power-bi-in-your-organization.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na Sorun](http://community.powerbi.com/)

