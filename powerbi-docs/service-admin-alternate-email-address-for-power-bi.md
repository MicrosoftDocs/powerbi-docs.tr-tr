---
title: Alternatif e-posta adresi kullanma
description: Alternatif e-posta adresi kullanma
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 11/01/2018
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 5998f4b63a168c3056a5464844d008bd657ef7c9
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2019
ms.locfileid: "54294296"
---
# <a name="using-an-alternate-email-address"></a>Alternatif e-posta adresi kullanma

Power BI'a kaydolurken bir e-posta adresi belirtirsiniz. Power BI, hizmet etkinlikleriyle ilgili güncelleştirmeleri göndermek için varsayılan olarak bu adresi kullanır. Örneğin size gönderilen paylaşım davetiyeleri bu adrese yönlendirilir.

Bazı durumlarda bu e-postaların kayıt sırasında kullandığınızdan farklı bir e-posta adresine teslim edilmesini isteyebilirsiniz. Bu makalede Office 365 ve PowerShell'de alternatif e-posta adresi belirtme adımları anlatılmaktadır. Makalede ayrıca e-posta adreslerinin Azure Active Directory'de (Azure AD) nasıl çözümlendiği de gösterilmektedir.

> [!NOTE]
> Alternatif bir e-posta adresi belirtmek, Power BI'ın hizmet güncelleştirmeleri, bültenler ve diğer tanıtım amaçlı yazışmalar için kullandığı e-posta adresini etkilemez.  Bu yazışmalar her zaman Power BI'a kaydolurken kullandığınız e-posta adresine gönderilir.

## <a name="use-office-365"></a>Office 365'i kullanma

Office 365'te alternatif adres belirtmek için aşağıdaki adımları izleyin.

1. [Office 365 kişisel bilgiler sayfasını](https://portal.office.com/account/#personalinfo) açın. Gerekirse Power BI için kullandığınız e-posta adresini ve parolayı kullanarak oturum açın.

1. Soldaki menüden **Kişisel bilgiler**'i seçin.

1. **Kişi ayrıntıları** bölümünde **Düzenle**'yi seçin.

    Bilgilerinizi düzenleyemiyorsanız e-posta adresiniz Office 365 yöneticiniz tarafından yönetiliyor demektir. E-posta adresinizi güncelleştirmek için yöneticinize başvurun.

    ![Kişi ayrıntıları](media/service-admin-alternate-email-address-for-power-bi/contact-details.png)

1. **Alternatif e-posta** alanına Power BI güncelleştirmelerinin gönderilmesini istediğiniz e-posta adresini gidin.

## <a name="use-powershell"></a>PowerShell'i kullanma

PowerShell'de alternatif adres belirtmek için [Set-AzureADUser](/powershell/module/azuread/set-azureaduser/) komutunu kullanın.

```powershell
Set-AzureADUser -ObjectId john@contoso.com -OtherMails "otheremail@somedomain.com"
```

## <a name="email-address-resolution-in-azure-ad"></a>Azure AD'de e-posta adresi çözümlemesi

Power BI için bir Azure AD ekleme belirtecini yakalarken üç farklı e-posta türü kullanabilirsiniz:

* Bir kullanıcının Azure AD hesabıyla ilişkili ana e-posta adresi

* UserPrincipalName (UPN) e-posta adresi

* *Diğer e-posta adresi* dizisi özniteliği

Power BI, kullanılacak e-posta adresini şu sıralamaya göre seçer:

1. Azure AD kiracısının kullanıcı nesnesindeki posta özniteliği mevcutsa Power BI, e-posta adresi için söz konusu posta özniteliğini kullanır.

1. UPN e-postası bir **\*.onmicrosoft.com** etki alanı e-posta adresi (“\@” simgesinden sonra gelen bilgiler) *değilse* Power BI, e-posta adresi için bu posta özniteliğini kullanır.

1. Azure AD kullanıcı nesnesinde *diğer e-posta adresi* dizisi özniteliği mevcutsa söz konusu listedeki ilk e-posta adresi (bu öznitelikte e-postalardan oluşan bir liste olabileceği için) kullanılır.

1. Yukarıdaki koşulların hiçbiri mevcut değilse UPN adresi kullanılır.

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

