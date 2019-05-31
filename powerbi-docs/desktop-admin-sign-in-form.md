---
title: Yöneticiler için Power BI Desktop oturum açma formunu yönetme seçenekleri
description: Power BI Desktop açılırken ilk olarak görüntülenen oturum açma formunu nasıl yönetebileceğinizi öğrenin.
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/15/2019
ms.author: davidi
ms.openlocfilehash: 5c31277b640b16882bef5c5f2cd9c56b441ede82
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "61329889"
---
# <a name="how-administrators-can-manage-the-power-bi-desktop-sign-in-form"></a>Yöneticiler için Power BI Desktop oturum açma formunu yönetme seçenekleri
Power BI Desktop uygulaması ilk kez açıldığında bir oturum açma formu görüntülenir. Devam etmek için, istenen bilgiler girilebilir veya Power BI'da oturum açılabilir. Yöneticiler bu formu kayıt defteri anahtarı kullanarak yönetir. 

![Power BI Desktop için ilk oturum açma formu](media/desktop-admin-sign-in-form/sign-in-form.png)

Yöneticiler aşağıdaki kayıt defteri anahtarını kullanarak oturum açma formunu devre dışı bırakır. Bu, genel ilkeler kullanılarak kuruluşun tamamına da gönderilebilir.

```
Key: HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Microsoft Power BI Desktop
valueName: ShowLeadGenDialog
```
Başarılı kendi yapılandırmalarına göre bazı müşteriler için aşağıdaki anahtarı de deneyebilirsiniz:

```
Key: HKEY_CURRENT_USER\SOFTWARE\Microsoft\Microsoft Power BI Desktop
valueName: ShowLeadGenDialog
```

0 değeri girildiğinde iletişim kutusu devre dışı bırakılır.




Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

