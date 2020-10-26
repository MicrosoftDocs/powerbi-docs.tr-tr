---
title: Power BI mobil Windows uygulamasında Çoklu Oturum Açma
description: Power BI mobil Windows uygulamasında Çoklu Oturum Açma (SSO) hakkında daha fazlasını öğrenin. SSO, çalışmak istediğiniz tüm uygulamalara ve kaynaklara tek kullanıcı hesabıyla yalnızca bir kez oturum açarak erişmeniz anlamına gelir.
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: how-to
ms.date: 03/11/2020
ms.author: painbar
ms.openlocfilehash: 41ddc6e0c9a4f4f2c9b5687194e043bb1ef80bec
ms.sourcegitcommit: 6b436f6ed872cbc040ed6e2d3ac089c08fc78daf
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/09/2020
ms.locfileid: "91928275"
---
# <a name="single-sign-on-in-the-power-bi-mobile-windows-app"></a>Power BI mobil Windows uygulamasında Çoklu Oturum Açma

Power BI mobil Windows uygulamasında Çoklu Oturum Açma (SSO) hakkında daha fazlasını öğrenin. SSO, çalışmak istediğiniz tüm uygulamalara ve kaynaklara tek kullanıcı hesabıyla yalnızca bir kez oturum açarak erişmeniz anlamına gelir. Oturum açtıktan sonra, tekrar kimlik doğrulaması yapmanız gerekmeden tüm bu uygulamalara erişebilirsiniz. 

Power BI Windows uygulaması, Azure Active Directory’de tümleşik olduğundan, birincil kuruluş hesabınızı yalnızca etki alanına katılmış cihazlarınızda değil, Power BI hizmetinde oturma açmak için de kullanabilirsiniz. Windows Phone’da Power BI’ı görüntülüyorsanız, Power BI için kullandığınız hesabın, cihaz ayarlarında bir iş veya okul hesabı olarak yapılandırıldığından emin olun.  

SSO yalnızca Azure Active Directory tarafından yönetilen Windows cihazlar için etkinleştirilir.

>[!NOTE]
>**Windows 10 Mobile kullanan telefonlar** için Power BI mobil uygulama desteği, 16 Mart 2021’de sona erecektir. [Daha fazla bilgi ](/legal/powerbi/powerbi-mobile/power-bi-mobile-app-end-of-support-for-windows-phones)

## <a name="sign-in-with-sso"></a>SSO ile oturum açma

Oturum açma işlemini kolaylaştırmak için, uygulamayı ilk kez yüklerken uygulama otomatik olarak SSO kullanarak Power BI hizmetinde kimliğinizi doğrulamaya çalışır. Yalnızca bu işlem başarılı olmazsa uygulama sizden Power BI kimlik bilgilerinizi sağlamanızı ister.  

Windows için Power BI mobil uygulamasını zaten kullanıyorsanız, uygulamanın yeni sürümüne yükseltme yaptığınızda da SSO’yu kullanabilirsiniz. Uygulama oturumunu kapatın, uygulamayı kapatıp yeniden açın. Uygulama yeniden açıldığında otomatik olarak Power BI hizmetine karşı kimlik doğrulaması yapmak için geçerli Windows kimlik bilgilerinizi kullanmaya çalışır. 

Power BI’da oturum açmak için geçerli Windows etkin oturum kimlik bilgilerinizi kullanmak istemiyorsanız, **Ayarlar**’a gidin, oturumu kapatın ve farklı kimlik bilgileriyle oturum açın. 
 
## <a name="next-steps"></a>Sonraki adımlar

- [Windows 10 için Power BI mobil uygulamasını kullanmaya başlama](mobile-windows-10-phone-app-get-started.md)
- Sorular? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
