---
title: Power BI ve Azure için aynı hesabı kullanma
description: Power BI ve Azure için aynı hesap oturum açma bilgilerini kullanma
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 09/09/2019
ms.author: kfollis
LocalizationGroup: Troubleshooting
ms.openlocfilehash: 4f1f8947827500ec89d189e17f8ab2189caaff93
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83138984"
---
# <a name="using-the-same-account-for-power-bi-and-azure"></a>Power BI ve Azure için aynı hesabı kullanma

Hem Power BI hem de Azure kullanıcısıysanız parolanızı iki kez yazmadan her iki hizmet için de aynı oturum açma bilgilerini kullanmak isteyebilirsiniz.

Power BI'da oturum açmak için, iş veya okul e-posta adresinizle ilişkili kuruluş hesabınızı kullanırsınız.  Azure'da oturum açmak içinse bir Microsoft hesabı veya kuruluş hesabınızı kullanmanız gerekir.

Hem Azure hem de Power BI için aynı oturum açma bilgilerini kullanmak istiyorsanız Azure'da kuruluş hesabınızla oturum açtığınızdan emin olun.

**Azure'da Microsoft hesabımla oturum açtıysam ne olur?**

Aşağıdaki adımları izleyerek Azure'da kuruluş hesabınızı bir ortak yönetici olarak ekleyebilirsiniz:

1. [Azure portalında](https://portal.azure.com/) oturum açın. Birden fazla Azure dizininde etkin bir kullanıcıysanız **Abonelikler**'i seçin ve yalnızca düzenlemek istediğiniz dizin ile abonelikler görüntülenecek şekilde filtreleme yapın.

1. Gezinti bölmesinde **Erişim denetimi (IAM)** ve sonra **Ekle** \> **Ortak yönetici ekle**’yi seçin.

    ![Azure portalında ortak yönetici ekleme](media/service-admin-how-to-use-the-same-account-as-azure/add-co-administrator.png)

1. Kuruluş hesabınızla ilişkili e-posta adresini girin ve **Ekle**’yi seçin.

1. Daha sonra Azure portalında oturum açacağınız zaman kuruluş e-posta adresinizi kullanın.

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)