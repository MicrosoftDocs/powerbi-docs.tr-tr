---
title: Bir alternatif e-posta adresi kullanın
description: Bir alternatif e-posta adresi kullanın
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/23/2019
ms.author: mblythe
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 88432f55fc8cfeefa07b66ea68437bbb23f12531
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "64906633"
---
# <a name="use-an-alternate-email-address"></a>Bir alternatif e-posta adresi kullanın

Power BI'a kaydolurken bir e-posta adresi belirtirsiniz. Power BI, hizmet etkinlikleriyle ilgili güncelleştirmeleri göndermek için varsayılan olarak bu adresi kullanır. Örneğin size gönderilen paylaşım davetiyeleri bu adrese yönlendirilir.

Bazı durumlarda bu e-postaların kayıt sırasında kullandığınızdan farklı bir e-posta adresine teslim edilmesini isteyebilirsiniz. Bu makalede Office 365 ve PowerShell'de alternatif e-posta adresi belirtme adımları anlatılmaktadır. Makalede, Azure Active Directory (Azure AD) bir e-posta adresine nasıl çözümler de açıklanmaktadır.

> [!NOTE]
> Alternatif bir e-posta adresi belirtmek, Power BI'ın hizmet güncelleştirmeleri, bültenler ve diğer tanıtım amaçlı yazışmalar için kullandığı e-posta adresini etkilemez. Bu iletişim, her zaman Power BI'a kaydolurken kullandığınız e-posta adresine gönderilir.

## <a name="use-office-365"></a>Office 365'i kullanma

Office 365'te alternatif adres belirtmek için aşağıdaki adımları izleyin.

1. [Office 365 kişisel bilgiler sayfasını](https://portal.office.com/account/#personalinfo) açın. Uygulama isterse, e-posta adresi ve Power BI için kullandığınız parola oturum açın.

1. Soldaki menüden **Kişisel bilgiler**'i seçin.

1. **Kişi ayrıntıları** bölümünde **Düzenle**'yi seçin.

    Ayrıntılarınızı düzenleyemezsiniz, bu e-posta adresinizi Office 365 yöneticiniz yönetir anlamına gelir. E-posta adresinizi güncelleştirmek için yöneticinizle iletişime geçin.

    ![Kişi ayrıntıları](media/service-admin-alternate-email-address-for-power-bi/contact-details.png)

1. İçinde **alternatif e-posta** gibi Office 365, Power BI güncelleştirmeleri için kullanılacak e-posta adresi girin.

## <a name="use-powershell"></a>PowerShell'i kullanma

PowerShell'de alternatif adres belirtmek için [Set-AzureADUser](/powershell/module/azuread/set-azureaduser/) komutunu kullanın.

```powershell
Set-AzureADUser -ObjectId john@contoso.com -OtherMails "otheremail@somedomain.com"
```

## <a name="email-address-resolution-in-azure-ad"></a>Azure AD'de e-posta adresi çözümlemesi

Bir Azure yakalamak için AD ekleme belirteci için Power BI, e-posta adreslerini üç farklı türde birini kullanabilirsiniz:

* Bir kullanıcının Azure AD hesabıyla ilişkili ana e-posta adresi

* UserPrincipalName (UPN) e-posta adresi

* *Diğer e-posta adresi* dizisi özniteliği

Power BI, kullanılacak e-posta adresini şu sıralamaya göre seçer:

1. Azure AD kiracısının kullanıcı nesnesindeki posta özniteliği mevcutsa Power BI, e-posta adresi için söz konusu posta özniteliğini kullanır.

1. UPN e-postası bir **\*.onmicrosoft.com** etki alanı e-posta adresi ("\@" sembolünden sonra gelen bilgiler) *değilse* Power BI, e-posta adresi için bu posta özniteliğini kullanır.

1. Varsa *diğer e-posta adresi* Azure AD kullanıcı nesnesi dizisi özniteliği varsa, bu durumda Power BI ilk e-posta konusu listede (olabileceği için bu öznitelikte e-postaları listesi).

1. Yukarıdaki koşulların hiçbiri mevcut değilse Power BI UPN adresi kullanır.

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)