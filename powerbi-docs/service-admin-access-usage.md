---
title: Oturum açmış Power BI kullanıcılarını bulma
description: Kiracı yöneticisiyseniz ve Power BI oturumu açmış olan kullanıcıları görmek istiyorsanız Azure Active Directory erişim ve kullanım raporlarını kullanabilirsiniz.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 10/31/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: f685a900465cc0f1b635aad7609aaae4356da6b3
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2019
ms.locfileid: "54284645"
---
# <a name="find-power-bi-users-that-have-signed-in"></a>Oturum açmış Power BI kullanıcılarını bulma

Kiracı yöneticisiyseniz ve Power BI oturumu açmış olan kullanıcıları görmek istiyorsanız [Azure Active Directory erişim ve kullanım raporlarını](/azure/active-directory/reports-monitoring/concept-sign-ins) kullanabilirsiniz.

<iframe width="640" height="360" src="https://www.youtube.com/embed/1AVgh9w9VM8?showinfo=0" frameborder="0" allowfullscreen></iframe>

> [!NOTE]
> Etkinlik raporu faydalı bilgiler sunar ancak her kullanıcının sahip olduğu lisans türünü tanımlamaz. Lisansları görüntülemek için Office 365 yönetim merkezini kullanın.

## <a name="requirements"></a>Gereksinimler

Tüm kullanıcılar (yönetici olmayanlar dahil) kendi oturum açma işlemlerini içeren raporu görebilir ancak tüm kullanıcıları kapsayan bir rapor oluşturmak için aşağıdaki gereksinimleri karşılamanız gerekir.

* Kiracınızın ilgili Azure AD Premium lisansına sahip olması gerekir.

* Şu rollerden birinde olmalısınız: Genel Yönetici, Güvenlik Yöneticisi veya Güvenlik Okuyucusu.

## <a name="use-the-azure-portal-to-view-sign-ins"></a>Oturum açma etkinliklerini görüntülemek için Azure portalı kullanma

Oturum açma etkinliğini görüntülemek için aşağıdaki adımları izleyin.

1. **Azure portalda** **Azure Active Directory**'yi seçin.

1. **İzleme** bölümünde **Oturum açma işlemleri**'ni seçin.
   
    ![Azure AD oturum açma işlemleri](media/service-admin-access-usage/azure-portal-sign-ins.png)

1. Uygulamayı **Microsoft Power BI** veya **Power BI Gateway** olarak filtreleyin ve **Uygula**'yı seçin.

    **Microsoft Power BI**, hizmetle ilgili oturum açma etkinliğini gösterecek şekilde filtreleme yaparken **Power BI Gateway**, Şirket içi ağ geçidiyle ilgili oturum açma etkinliğini gösterecek şekilde filtre uygular.
   
    ![Oturum açma işlemlerini filtreleme](media/service-admin-access-usage/sign-in-filter.png)

## <a name="export-the-data"></a>Verileri dışarı aktarma

Oturum açma verilerini dışarı aktarmak için kullanabileceğiniz iki seçenek vardır: csv dosyası indirme veya PowerShell'i kullanma. Oturum açma raporunun en üstünde aşağıdaki seçeneklerden birini belirleyin:

* **İndir**: Filtrelenmiş verileri içeren bir csv dosyası indirilir.

* **Betik**: Filtrelenmiş verilere özgü bir PowerShell betiği indirilir. Betikteki filtreyi istediğiniz şekilde güncelleştirebilirsiniz.

![csv dosyası veya betik indirme](media/service-admin-access-usage/download-sign-in-data-csv.png)

## <a name="data-retention"></a>Veri saklama

Oturum açma verileri 30 güne kadar saklanabilir. Daha fazla bilgi için bkz. [Azure Active Directory report retention policies (Azure Active Directory rapor saklama ilkeleri)](/azure/active-directory/reports-monitoring/reference-reports-data-retention).

## <a name="next-steps"></a>Sonraki adımlar

[Kuruluşunuzda denetim özelliğini kullanma](service-admin-auditing.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)

