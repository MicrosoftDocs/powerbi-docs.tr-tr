---
title: "Yöneticiler için Power BI Desktop oturum açma formunu yönetme seçenekleri"
description: "Power BI Desktop açılırken ilk olarak görüntülenen oturum açma formunu nasıl yönetebileceğinizi öğrenin."
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.date: 01/24/2018
ms.author: davidi
ms.openlocfilehash: 519f8b56b5086292addf577d969a707a6d6efcc8
ms.sourcegitcommit: 5e1f7d2673efe25c47b9b9f315011055bfe92c8f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/09/2018
---
# <a name="how-administrators-can-manage-the-power-bi-desktop-sign-in-form"></a>Yöneticiler için Power BI Desktop oturum açma formunu yönetme seçenekleri
Power BI Desktop uygulaması ilk kez açıldığında bir oturum açma formu görüntülenir. Devam etmek için, istenen bilgiler girilebilir veya Power BI'da oturum açılabilir. Yöneticiler bu formu kayıt defteri anahtarı kullanarak yönetebilir. 

![Power BI Desktop için ilk oturum açma formu](media/desktop-admin-sign-in-form/sign-in-form.png)

Yöneticiler aşağıdaki kayıt defteri anahtarını kullanarak oturum açma formunu devre dışı bırakabilir. Bu, genel ilkeler kullanılarak kuruluşun tamamına da uygulanabilir.

```
Key: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Power BI Desktop
valueName: ShowLeadGenDialog
```

0 değeri girildiğinde iletişim kutusu devre dışı bırakılır.

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

