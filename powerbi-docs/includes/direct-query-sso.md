---
title: dosya dahil etme
description: dosya dahil etme
services: powerbi
author: mgblythe
ms.service: powerbi
ms.topic: include
ms.date: 05/31/2019
ms.author: mblythe
ms.openlocfilehash: 94b6959b6bcbf250e54a353e8b725b6c9e5a2e30
ms.sourcegitcommit: c539726c9c180e899a8a34443e3fda2b9848beb2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66448378"
---
## <a name="single-sign-on"></a>Çoklu oturum açma

Azure SQL DirectQuery veri kümesini hizmette yayımladıktan sonra son kullanıcılarınız için Azure Active Directory (Azure AD) OAuth2 aracılığıyla çoklu oturum açmayı (SSO) etkinleştirebilirsiniz.

SSO özelliğini etkinleştirmek için veri kümesinin ayarlarına gidip **Veri Kaynakları** sekmesini açın ve SSO kutusunu işaretleyin.

![Azure SQL DQ iletişim kutusunu yapılandırma](media/direct-query-sso/sso-dialog.png)

SSO seçeneği etkinleştirildiğinde ve kullanıcılarınız veri kaynağının üstünde derlenen raporlara eriştiğinde, Power BI, kimliği doğrulanmış sorgulardaki Azure AD kimlik bilgilerini Azure SQL veritabanına veya veri ambarına gönderir. Bu sayede Power BI, veri kaynağı seviyesinde yapılandırılmış olan güvenlik ayarlarını uygular.

SSO seçeneği bu veri kaynağını kullanan tüm veri kümelerinde geçerli olur. İçeri aktarma senaryoları için kullanılan kimlik doğrulama yöntemini etkilemez.

> [!Note]
> Azure Multi-Factor Authentication (MFA) desteklenmiyor. Azure SQL DirectQuery ile SSO kullanmak isteyen kullanıcıların MFA'dan muaf tutulması gerekir.