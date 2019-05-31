---
title: Oturum açmış Power BI kullanıcılarını bulma
description: Bir kiracı Yöneticisi olduğunuz ve Power BI'a kimin açtığını öğrenmek istiyorsanız görünürlük elde etmek için Azure Active Directory erişim ve kullanım raporlarını kullanabilirsiniz.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/23/2019
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: e513607dd89aee15f10145cf62bd461621cc12c0
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "64906744"
---
# <a name="find-power-bi-users-that-have-signed-in"></a>Oturum açmış Power BI kullanıcılarını bulma

Bir kiracı Yöneticisi olduğunuz ve Power BI'a kullanın kimin açtığını öğrenmek istiyorsanız [Azure Active Directory erişim ve kullanım raporlarını](/azure/active-directory/reports-monitoring/concept-sign-ins) görünürlük elde etmek için.

<iframe width="640" height="360" src="https://www.youtube.com/embed/1AVgh9w9VM8?showinfo=0" frameborder="0" allowfullscreen></iframe>

> [!NOTE]
> **Oturum açma işlemleri** rapor yararlı bilgiler sağlar, ancak her kullanıcının lisans türünü belirlemek değil. Lisansları görüntülemek için Microsoft 365 yönetim merkezini kullanın.

## <a name="requirements"></a>Gereksinimler

Tüm kullanıcılar (yönetici olmayanlar dahil) kendi oturum açma işlemlerini içeren raporu görebilir ancak tüm kullanıcıları kapsayan bir rapor oluşturmak için aşağıdaki gereksinimleri karşılamanız gerekir.

* Kiracınızın ilişkili bir Azure Active Directory Premium lisansı olması gerekir.

* Şu rollerden birinde olmalısınız: Genel Yönetici, Güvenlik Yöneticisi veya Güvenlik Okuyucusu.

## <a name="use-the-azure-portal-to-view-sign-ins"></a>Oturum açma etkinliklerini görüntülemek için Azure portalı kullanma

Oturum açma etkinliğini görüntülemek için aşağıdaki adımları izleyin.

1. **Azure portalda** **Azure Active Directory**'yi seçin.

1. **İzleme** bölümünde **Oturum açma işlemleri**'ni seçin.
   
    ![Vurgulanmış Azure Active Directory ve oturum açma seçenekleri ile Azure kullanıcı arabiriminin ekran görüntüsü.](media/service-admin-access-usage/azure-portal-sign-ins.png)

1. Uygulamayı **Microsoft Power BI** veya **Power BI Gateway** olarak filtreleyin ve **Uygula**'yı seçin.

    **Microsoft Power BI** ise oturum açma etkinliği filtrelerini ilgili hizmete **Power BI Gateway** için oturum açma etkinliği için şirket içi veri ağ geçidi belirli filtreler.
   
    ![Oturum açma filtrenin vurgulanmış uygulamaları alanıyla ekran görüntüsü.](media/service-admin-access-usage/sign-in-filter.png)

## <a name="export-the-data"></a>Verileri dışarı aktarma

Yapabilecekleriniz [bir oturum açma raporu indirme](/azure/active-directory/reports-monitoring/quickstart-download-sign-in-report) biçimlerden birindeki: bir CSV dosyası veya bir JSON dosyası.

![İndirme düğmesinin Ekran görüntüsü.](media/service-admin-access-usage/download-sign-in-data-csv.png)

Üst kısmındaki **oturum açma** rapor seçim **indirin** ve aşağıdaki seçeneklerden birini seçin:

* **CSV** yaptığınızda filtrelenmiş verileri için bir CSV dosyası indirilemedi.

* **JSON** yaptığınızda filtrelenmiş verileri için bir JSON dosyası indirilemedi.

## <a name="data-retention"></a>Veri saklama

Oturum açma verileri 30 güne kadar saklanabilir. Daha fazla bilgi için bkz. [Azure Active Directory rapor saklama ilkeleri](/azure/active-directory/reports-monitoring/reference-reports-data-retention).

## <a name="next-steps"></a>Sonraki adımlar

[Kuruluşunuzda denetim özelliğini kullanma](service-admin-auditing.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)