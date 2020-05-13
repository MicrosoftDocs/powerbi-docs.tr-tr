---
title: Oturum açmış Power BI kullanıcılarını bulma
description: Kiracı yöneticisiyseniz ve Power BI'da kimin oturum açtığını görmek istiyorsanız, görünürlük elde etmek için Azure Active Directory erişim ve kullanım raporlarını kullanabilirsiniz.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 09/09/2019
ms.author: kfollis
LocalizationGroup: Administration
ms.openlocfilehash: 32ca01d06f4fc8c3f90f73bf8137349eed0220a6
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83129799"
---
# <a name="find-power-bi-users-that-have-signed-in"></a>Oturum açmış Power BI kullanıcılarını bulma

Kiracı yöneticisiyseniz ve Power BI'da kimin oturum açtığını görmek istiyorsanız, görünürlük elde etmek için [Azure Active Directory erişim ve kullanım raporlarını](/azure/active-directory/reports-monitoring/concept-sign-ins) kullanın.

> [!NOTE]
> **Oturum açma işlemleri**raporu yararlı bilgiler sunar ancak her kullanıcının sahip olduğu lisans türünü tanımlamaz. Lisansları görüntülemek için Microsoft 365 yönetim merkezini kullanın.

## <a name="requirements"></a>Gereksinimler

Tüm kullanıcılar (yönetici olmayanlar dahil) kendi oturum açma işlemlerini içeren raporu görebilir ancak tüm kullanıcıları kapsayan bir rapor oluşturmak için aşağıdaki gereksinimleri karşılamanız gerekir.

* Kiracınızın bununla ilişkili bir Azure Active Directory Premium lisansına sahip olması gerekir.

* Şu rollerden birine atanmış olmanız gerekir: Genel Yönetici, Güvenlik Yöneticisi veya Güvenlik Okuyucusu.

## <a name="use-the-azure-portal-to-view-sign-ins"></a>Oturum açma etkinliklerini görüntülemek için Azure portalı kullanma

Oturum açma etkinliğini görüntülemek için aşağıdaki adımları izleyin.

1. **Azure portalda** **Azure Active Directory**'yi seçin.

1. **İzleme** bölümünde **Oturum açma işlemleri**'ni seçin.
   
    ![Azure arabiriminin, Azure Active Directory ve Oturum Açma işlemleri seçenekleri vurgulanmış ekran görüntüsü.](media/service-admin-access-usage/azure-portal-sign-ins.png)

1. Uygulamayı **Microsoft Power BI** veya **Power BI Gateway** olarak filtreleyin ve **Uygula**'yı seçin.

    **Microsoft Power BI**, hizmetle ilgili oturum açma etkinliğine filtrelerken, **Power BI Gateway**, şirket içi ver ağ geçidine özgü oturum açma etkinliğine filtreler.
   
    ![Oturum açma işlemleri filtresinin, Uygulamalar alanı vurgulanmış ekran görüntüsü.](media/service-admin-access-usage/sign-in-filter.png)

## <a name="export-the-data"></a>Verileri dışarı aktarma

[Bir oturum açma raporunu](/azure/active-directory/reports-monitoring/quickstart-download-sign-in-report) iki biçimden biriyle indirebilirsiniz: CSV dosyası veya JSON dosyası.

![İndirme düğmesinin ekran görüntüsü.](media/service-admin-access-usage/download-sign-in-data-csv.png)

**Oturum açma işlemleri** raporunun üstünde, **İndir** seçeneğini ve ardından aşağıdaki seçeneklerden birini belirleyin:

* O sırada filtrelenmiş veri için bir CSV dosyası indirmek için **CSV**.

* O sırada filtrelenmiş veri için bir JSON dosyası indirmek için **JSON**.

## <a name="data-retention"></a>Veri saklama

Oturum açma verileri 30 güne kadar saklanabilir. Daha fazla bilgi için bkz. [Azure Active Directory rapor saklama ilkeleri](/azure/active-directory/reports-monitoring/reference-reports-data-retention).

## <a name="next-steps"></a>Sonraki adımlar

[Kuruluşunuzda denetim özelliğini kullanma](service-admin-auditing.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)