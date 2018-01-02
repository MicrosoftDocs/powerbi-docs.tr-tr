---
title: "Bir uygulamayı Azure AD'ye kaydetme"
description: "İzlenecek yol - Veri kümesine veri gönderme - Bir uygulamayı Azure AD'ye kaydetme"
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
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 08/10/2017
ms.author: asaxton
ms.openlocfilehash: e5c1629ea6b90ec52a3c567916a9f686eb4d1bee
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="step-1-register-an-app-with-azure-ad"></a>1. Adım: Bir uygulamayı Azure AD'ye kaydetme
Bu makale, [veri kümelerine veri göndermeye](walkthrough-push-data.md) ilişkin adım adım kılavuzun bir parçasıdır.

Power BI veri kümelerine veri gönderebilmek için ilk olarak uygulamanızı Azure AD'ye kaydetmeniz gerekir. Bunun nedeni, Azure AD'de uygulamanızı tanımlayan bir **İstemci Kimliği** edinecek olmanızdır. Azure AD, **İstemci Kimliği** olmadan uygulamanızın kimliğini doğrulayamaz.

> **Not**: Bir uygulamayı Power BI'a kaydedebilmeniz için öncelikle [Power BI'a kaydolmanız](create-an-azure-active-directory-tenant.md) gerekir.
> 
> 

Bir uygulamayı Azure AD'ye kaydetmeye ilişkin adımlar aşağıda açıklanmıştır.

## <a name="register-an-app-in-azure-ad"></a>Bir Uygulamayı Azure AD'ye kaydetme
1. dev.powerbi.com/apps adresine gidin.
2. **Sign in with your existing account** (Mevcut hesabınızla oturum açın) seçeneğine tıklayın ve Power BI hesabınızda oturum açın.
3. **App Name** (Uygulama Adı) alanına bir uygulama adı (örneğin, "Örnek veri gönderme uygulaması") girin.
4. **App Type** (Uygulama Türü) için **Native app** (Yerel uygulama) seçeneğini belirleyin.
5. **Redirect URL** (Yönlendirme URL'si) alanına **https://login.live.com/oauth20_desktop.srf** gibi bir URL girin. **Native client app** (Yerel istemci uygulaması) için yönlendirme URI'si girildiğinde, **Azure AD**'ye kimliği doğrulanacak belirli uygulama ile ilgili daha ayrıntılı bilgi sağlanmış olur. İstemci uygulamaları için standart URI şu şekildedir: https://login.live.com/oauth20_desktop.srf.
6. **Choose APIs to access** (Erişilecek API'leri seçin) bölümünde **Read and Write All Datasets** (Tüm Veri Kümelerini Okuma ve Yazma) seçeneğini belirleyin. Tüm Power BI uygulama izinleri için bkz. [Power BI İzinleri](power-bi-permissions.md).
7. **Register app**'e (Uygulamayı kaydet) tıklayın ve oluşturulan **İstemci Kimliğini** kaydedin. **İstemci Kimliği**, Azure AD'de uygulamayı tanımlar.

**Power BI'a Uygulama Kaydetme** sayfanız aşağıdaki gibi görünür:

![](media/walkthrough-push-data-register-app-with-azure-ad/powerbi-developer-sample-register-app.png)

Sonraki adımda, [kimlik doğrulaması erişim belirteci alma](walkthrough-push-data-get-token.md) işlemini nasıl gerçekleştireceğiniz gösterilmiştir.

[Sonraki Adım >](walkthrough-push-data-get-token.md)

## <a name="next-steps"></a>Sonraki adımlar
[Power BI'a kaydolma](create-an-azure-active-directory-tenant.md)  
[Kimlik doğrulaması erişim belirteci alma](walkthrough-push-data-get-token.md)  
[İzlenecek yol: Veri kümelerine veri gönderme](walkthrough-push-data.md)  
[Uygulamaları kaydetme](register-app.md)  
[Overview of Power BI REST API (Power BI REST API'sine Genel Bakış)](overview-of-power-bi-rest-api.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

