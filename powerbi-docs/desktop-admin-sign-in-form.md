---
title: Yöneticiler için Power BI Desktop oturum açma formunu yönetme seçenekleri
description: Power BI Desktop açılırken ilk olarak görüntülenen oturum açma formunu nasıl yönetebileceğinizi öğrenin.
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 04/24/2018
ms.author: davidi
ms.openlocfilehash: 65bf0a39351b394232211af50692072f7cec7e89
ms.sourcegitcommit: 3f2f254f6e8d18137bae879ddea0784e56b66895
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
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

