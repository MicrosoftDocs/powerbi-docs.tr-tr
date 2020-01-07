---
title: Yöneticiler için Power BI Desktop oturum açma formunu yönetme seçenekleri
description: Power BI Desktop açılırken ilk olarak görüntülenen oturum açma formunu nasıl yönetebileceğinizi öğrenin.
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/15/2019
ms.author: davidi
ms.openlocfilehash: b1ab5188ba8f5ccf54589d359f6f8ced1ada3060
ms.sourcegitcommit: 6272c4a0f267708ca7d38a45774f3bedd680f2d6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/06/2020
ms.locfileid: "73878855"
---
# <a name="how-administrators-can-manage-the-power-bi-desktop-sign-in-form"></a>Yöneticiler için Power BI Desktop oturum açma formunu yönetme seçenekleri
Power BI Desktop uygulaması ilk kez açıldığında bir oturum açma formu görüntülenir. Devam etmek için, istenen bilgiler girilebilir veya Power BI'da oturum açılabilir. Yöneticiler bu formu kayıt defteri anahtarı kullanarak yönetir. 

![Power BI Desktop için ilk oturum açma formu](media/desktop-admin-sign-in-form/sign-in-form.png)

Yöneticiler aşağıdaki kayıt defteri anahtarını kullanarak oturum açma formunu devre dışı bırakır. Bu, genel ilkeler kullanılarak kuruluşun tamamına da gönderilebilir.

```
Key: HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Microsoft Power BI Desktop
valueName: ShowLeadGenDialog
```
Ayrıca, yapılandırmalarına bağlı olarak bazı müşteriler için başarılı olan aşağıdaki anahtarı da deneyebilirsiniz:

```
Key: HKEY_CURRENT_USER\SOFTWARE\Microsoft\Microsoft Power BI Desktop
valueName: ShowLeadGenDialog
```

0 değeri girildiğinde iletişim kutusu devre dışı bırakılır.




Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)

