---
title: Alternatif e-posta adresi kullanma
description: Alternatif e-posta adresi kullanma
services: powerbi
documentationcenter: 
author: markingmyname
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 08/09/2017
ms.author: maghan
LocalizationGroup: Troubleshooting
ms.openlocfilehash: c97f60e39d68060c8eb3396bac4eb7725dab9c86
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/24/2018
---
# <a name="using-an-alternate-email-address"></a>Alternatif e-posta adresi kullanma
Varsayılan olarak Power BI'daki etkinliğinizle ilgili güncelleştirmeler, Power BI'a kaydolurken kullandığınız e-posta adresine gönderilir.  Örneğin size gönderilen paylaşım davetiyeleri bu adrese yönlendirilir.

Bazen bu e-postaların Power BI'a kaydolurken kullandığınız e-posta adresinin yerine alternatif bir e-posta adresine teslim edilmesini isteyebilirsiniz.

## <a name="updating-through-office-365-personal-info-page"></a>Office 365 kişisel bilgiler sayfasından güncelleştirme
1. [Office 365 kişisel bilgiler sayfanıza](https://portal.office.com/account/#personalinfo) gidin.  Gerekirse Power BI için kullandığınız e-posta adresini ve parolayı kullanarak oturum açın.
2. Kişi ayrıntıları bölümündeki düzenle bağlantısına tıklayın.  
   
   > [!NOTE]
   > Düzenle bağlantısının görünmemesi e-posta adresinizin Office 365 yöneticiniz tarafından yönetildiği anlamına gelir. Bu durumda e-posta adresinizi güncelleştirmek için yöneticinizle irtibata geçmeniz gerekir.
   > 
   > 
   
   ![](media/service-admin-alternate-email-address-for-power-bi/contact-details.png)
3. Alternatif e-posta alanına Power BI güncelleştirmelerinin gönderilmesini istediğiniz e-posta adresini gidin.

> [!NOTE]
> Bu ayarı değiştirdiğinizde hizmet güncelleştirmeleri, bültenler ve diğer tanıtım amaçlı gönderiler için kullanılan e-posta adresi değişmez.  Bunlar her zaman Power BI'a kaydolurken kullandığınız e-posta adresine gönderilir.
> 
> 

## <a name="updating-with-powershell"></a>PowerShell ile güncelleştirme
Alternatif e-posta adresini Azure Active Directory için PowerShell aracılığıyla da güncelleştirebilirsiniz. Bunun için [Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser) komutunu kullanmanız gerekir.

```
Set-AzureADUser -ObjectId john@contoso.com -OtherMails "otheremail@somedomain.com"
```

Daha fazla bilgi için bkz. [Azure Active Directory PowerShell Sürüm 2](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

