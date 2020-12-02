---
title: Yöneticiler için Power BI Desktop oturum açma formunu yönetme seçenekleri
description: Power BI Desktop açılırken ilk olarak görüntülenen oturum açma formunu nasıl yönetebileceğinizi öğrenin.
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: how-to
ms.date: 04/15/2019
ms.openlocfilehash: 633d71326009881b22b7b7d235316b4ebe5c132f
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96386893"
---
# <a name="administrators-manage-the-power-bi-desktop-sign-in-form"></a>Yöneticiler: Power BI Desktop oturum açma formunu yönetme
Power BI Desktop uygulaması ilk kez açıldığında bir oturum açma formu görüntülenir. Devam etmek için, istenen bilgiler girilebilir veya Power BI'da oturum açılabilir. Yöneticiler bu formu kayıt defteri anahtarı kullanarak yönetir. 

![Power BI Desktop için ilk oturum açma formunun ekran görüntüsü.](media/desktop-admin-sign-in-form/sign-in-form.png)

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

