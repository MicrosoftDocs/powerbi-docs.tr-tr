---
title: dosya dahil etme
description: dosya dahil etme
services: powerbi
author: davidiseminger
ms.service: powerbi
ms.topic: include
ms.date: 04/28/2020
ms.author: davidi
ms.openlocfilehash: ed87101fe7f5fadd24594d53bbd0ffb6f029faa4
ms.sourcegitcommit: 92b033ee7a6e36808371b247b7b41536cee6c2f6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2020
ms.locfileid: "90012863"
---
## <a name="single-sign-on"></a>Çoklu oturum açma

Azure SQL DirectQuery veri kümesini hizmette yayımladıktan sonra son kullanıcılarınız için Azure Active Directory (Azure AD) OAuth2 kullanarak çoklu oturum açmayı (SSO) etkinleştirebilirsiniz.

SSO özelliğini etkinleştirmek için veri kümesinin ayarlarına gidip **Veri Kaynakları** sekmesini açın ve SSO kutusunu işaretleyin.

![Azure SQL DQ iletişim kutusunu yapılandırma](media/direct-query-sso/sso-dialog.png)

SSO seçeneği etkinleştirildiğinde ve kullanıcılarınız veri kaynağının üstünde derlenen raporlara eriştiğinde, Power BI, kimliği doğrulanmış sorgulardaki Azure AD kimlik bilgilerini Azure SQL veritabanına veya veri ambarına gönderir. Bu seçenek sayesinde Power BI, veri kaynağı seviyesinde yapılandırılmış olan güvenlik ayarlarını uygular.

SSO seçeneği bu veri kaynağını kullanan tüm veri kümelerinde geçerli olur. İçeri aktarma senaryoları için kullanılan kimlik doğrulama yöntemini etkilemez.

> [!Note]
> Azure Multi-Factor Authentication (MFA) desteklenmiyor. DirectQuery ile SSO kullanmak isteyen kullanıcılar MFA'den muaf tutulmalıdır.
