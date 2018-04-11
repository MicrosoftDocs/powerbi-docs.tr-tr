---
title: Power BI Pro lisansları atama
description: Power BI Pro lisansları atama
services: powerbi
documentationcenter: ''
author: mgblythe
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
ms.date: 03/22/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: cc22bfa635bb9d91624e6d4a5cdfe301d6478af6
ms.sourcegitcommit: 8552a34df8e6141eb704314c1a019992901d6e78
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2018
---
# <a name="assigning-power-bi-pro-licenses"></a>Power BI Pro lisansları atama

Yöneticiler, kullanıcılara Power BI Pro lisansları atamak için çeşitli yönetim portalları ve PowerShell cmdlet'leri arasından seçim yapabilir. Power BI lisans yönetimi, Azure Active Directory (Azure AD) tarafından desteklenir.

* Azure abonelik sahipleri, [Azure Portal](https://ms.portal.azure.com/#@microsoft.onmicrosoft.com/dashboard/private/39bc3cf7-31a4-43f6-954c-f2d69ca2f0)’daki Azure Active Directory dikey penceresini kullanabilir. 

* Genel yöneticiler ve Kullanıcı Hesabı yöneticileri, [Office 365 yönetim merkezini](https://portal.office.com/AdminPortal/Home#/homepage) kullanabilir.

## <a name="managing-power-bi-pro-licenses-in-the-azure-portal"></a>Azure Portal'da Power BI Pro lisanslarını yönetme

Power BI, temel hizmet olarak Azure AD’yi kullanır. Azure AD, satın alınan ürünlerle ilgili bilgiler gibi diğer ayarları depolarken, kullanıcı hesaplarını ve gruplarını depolar.

### <a name="assigning-licenses-to-individual-user-accounts"></a>Tek tek kullanıcı hesaplarına lisanslar atama

Azure aboneliğine sahipseniz, tek tek kullanıcı hesaplarına Pro lisansları atamak için şu adımları izleyin:

1. [Azure Portal](https://ms.portal.azure.com/#@microsoft.onmicrosoft.com/dashboard/private/39bc3cf7-31a4-43f6-954c-f2d69ca2f0)’a gidin. 

2. Sol gezinti çubuğunda Azure Active Directory'ye tıklayın.

    ![image](media/service-assigning-power-bi-pro-licenses/service-assigning-power-bi-pro-licenses-01.png)

3. Azure Active Directory dikey penceresinde Lisanslar’a tıklayın.

    ![image](media/service-assigning-power-bi-pro-licenses/service-assigning-power-bi-pro-licenses-02.png)

4. Lisanslar dikey penceresinde Tüm ürünler’e, ardından Power BI Pro’ya tıklayarak lisanslı kullanıcılar listesini görüntüleyin.

    ![image](media/service-assigning-power-bi-pro-licenses/service-assigning-power-bi-pro-licenses-03.png)

5. Ek bir kullanıcı hesabına Power BI Pro lisansı eklemek için Ata seçeneğine tıklayın.

    ![image](media/service-assigning-power-bi-pro-licenses/service-assigning-power-bi-pro-licenses-04.png)

> [!NOTE]
> Azure Portal'da çoğu lisanslama unsurları yönetilebilir, ancak Power BI Pro lisansları satın alınamaz. Power BI Pro aboneliği satın almak için Office 365 yönetim merkezini kullanın. Daha fazla bilgi için bkz. [Power BI Pro'yu satın alma](https://docs.microsoft.com/en-us/power-bi/service-admin-purchasing-power-bi-pro).
>

## <a name="managing-power-bi-pro-licenses-in-the-office-365-admin-center"></a>Office 365 yönetim merkezinde Power BI Pro lisanslarını yönetme

Genel yöneticiyseniz, Office 365 yönetim merkezinden Power BI Pro aboneliği satın alabilir ve kuruluş için ilişkili lisansları yönetebilirsiniz.

Office 365 yöneticisiyseniz, tek tek kullanıcı hesaplarına Pro lisansları atamak için şu adımları izleyin:

1. Office 365 yönetim merkezine gidin.

2. Sol gezinti bölmesinde Kullanıcılar’ı genişletin ve sonra Etkin kullanıcılar’a tıklayın.

    ![image](media/service-assigning-power-bi-pro-licenses/service-assigning-power-bi-pro-licenses-05.png)

3. Bir veya birden fazla kullanıcı seçin ve Ürün lisanslarını düzenle’ye tıklayın.

    ![image](media/service-assigning-power-bi-pro-licenses/service-assigning-power-bi-pro-licenses-06.png)

4. Power BI Pro bölümünde ayarı Açık olarak ayarlayın ve Kaydet’e tıklayın.

    ![image](media/service-assigning-power-bi-pro-licenses/service-assigning-power-bi-pro-licenses-07.png)

5. Seçilen hesaplar için Durum bölümünde Power BI Pro lisansının başarıyla atandığını doğrulayın.

    ![image](media/service-assigning-power-bi-pro-licenses/service-assigning-power-bi-pro-licenses-08.png)

> [!NOTE]
> Aboneliğinizde lisans kalmadıysa, sol gezinti bölmesindeki Faturalama’yı genişleterek daha fazla lisans ekleyin. Abonelikler sayfasından Power BI Pro aboneliğini seçin ve sonra Lisans Ekle/Kaldır seçeneğine tıklayın.
>

## <a name="next-steps"></a>Sonraki adımlar
[Kuruluşunuzda Power BI Pro](service-admin-power-bi-pro-in-your-organization.md)
</br>
[Uzatılmış Pro Deneme Sürümünü etkinleştirme](service-extended-pro-trial.md)
</br>
[Bireysel kullanıcılar için Power BI Hizmet sözleşmesi](https://powerbi.microsoft.com/terms-of-service/)
</br>
[Power BI Premium announcement (Power BI Premium duyurusu)](https://aka.ms/pbipremium-announcement)
</br>
[Oturum açmış Power BI kullanıcılarını bulma](service-admin-access-usage.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)