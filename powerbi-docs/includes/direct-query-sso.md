---
title: dosya dahil etme
description: dosya dahil etme
services: powerbi
author: davidiseminger
ms.service: powerbi
ms.topic: include
ms.date: 05/31/2019
ms.author: davidi
ms.openlocfilehash: eec30d11c1bd99271416ab1a3a2dbb581687e315
ms.sourcegitcommit: f77b24a8a588605f005c9bb1fdad864955885718
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2019
ms.locfileid: "74698336"
---
## <a name="single-sign-on"></a>Çoklu oturum açma

Azure SQL DirectQuery veri kümesini hizmette yayımladıktan sonra son kullanıcılarınız için Azure Active Directory (Azure AD) OAuth2 aracılığıyla çoklu oturum açmayı (SSO) etkinleştirebilirsiniz.

SSO özelliğini etkinleştirmek için veri kümesinin ayarlarına gidip **Veri Kaynakları** sekmesini açın ve SSO kutusunu işaretleyin.

![Azure SQL DQ iletişim kutusunu yapılandırma](media/direct-query-sso/sso-dialog.png)

SSO seçeneği etkinleştirildiğinde ve kullanıcılarınız veri kaynağının üstünde derlenen raporlara eriştiğinde, Power BI, kimliği doğrulanmış sorgulardaki Azure AD kimlik bilgilerini Azure SQL veritabanına veya veri ambarına gönderir. Bu sayede Power BI, veri kaynağı seviyesinde yapılandırılmış olan güvenlik ayarlarını uygular.

SSO seçeneği bu veri kaynağını kullanan tüm veri kümelerinde geçerli olur. İçeri aktarma senaryoları için kullanılan kimlik doğrulama yöntemini etkilemez.

> [!Note]
> Azure Multi-Factor Authentication (MFA) desteklenmiyor. Azure SQL DirectQuery ile SSO kullanmak isteyen kullanıcıların MFA'dan muaf tutulması gerekir.