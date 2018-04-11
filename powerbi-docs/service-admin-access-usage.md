---
title: Oturum açmış Power BI kullanıcılarını bulma
description: Kiracı yöneticisiyseniz ve Power BI oturumu açmış olan kullanıcıları görmek istiyorsanız Azure Active Directory erişim ve kullanım raporlarını kullanabilirsiniz.
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
ms.date: 08/10/2017
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 0886fa6d4da745c95eb51e4e1fe3dfc9d5ddc599
ms.sourcegitcommit: 8552a34df8e6141eb704314c1a019992901d6e78
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2018
---
# <a name="find-power-bi-users-that-have-signed-in"></a>Oturum açmış Power BI kullanıcılarını bulma
Kiracı yöneticisiyseniz ve Power BI oturumu açmış olan kullanıcıları görmek istiyorsanız Azure Active Directory erişim ve kullanım raporlarını kullanabilirsiniz.

<iframe width="640" height="360" src="https://www.youtube.com/embed/1AVgh9w9VM8?showinfo=0" frameborder="0" allowfullscreen></iframe>

Etkinlik raporuna [yeni](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-activity-sign-ins) ve [klasik](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports) Azure Active Directory (Azure AD) portallarından erişebilirsiniz. Yukarıdaki videoda klasik portal kullanılmıştır ancak bu makalede yeni portal üzerinden gidilecektir.

> [!NOTE]
> Bu etkinlik raporu hem Power BI (Ücretsiz) hem de Pro sürüm kullanıcılarını içerir ancak bu kullanıcıları sahip oldukları lisanslara göre ayırmaz.
> 
> 

## <a name="requirements"></a>Gereksinimler
Oturum açma etkinliği raporunu görüntüleme gereksinimleri aşağıda belirtilmiştir.

* Verilere Genel Yönetici, Güvenlik Yöneticisi veya Güvenlik Okuyucusu rolündeki kullanıcılar erişebilir.
* Kullanıcılar (yönetici olmayanlar) kendi oturum açma etkinliklerine erişebilir.
* Tüm oturum açma etkinliği raporunu görebilmeniz için kiracınızın ilgili Azure AD Premium lisansına sahip olması gerekir.

## <a name="using-the-azure-portal-to-view-sign-ins"></a>Oturum açma etkinliklerini görüntülemek için Azure portalını kullanma
Oturum açma etkinliğini görüntülemek için Azure AD portalını kullanabilirsiniz.

1. **Azure portalı**'na gidin ve **Azure Active Directory**'yi seçin.
2. **Etkinlik** bölümünde **Oturum açma işlemleri**'ni seçin.
   
    ![](media/service-admin-access-usage/azure-portal-sign-ins.png)
3. Uygulamayı **Microsoft Power BI** veya **Power BI Gateway** olarak filtreleyin ve **Uygula**'yı seçin.
   
    **Microsoft Power BI**, hizmetle ilgili oturum açma etkinliğini gösterirken **Power BI Gateway** ise şirket içi ağ geçidiyle ilgili oturum açma etkinliğini gösterir.
   
    ![](media/service-admin-access-usage/sign-in-filter.png)

## <a name="export-the-data"></a>Verileri dışarı aktarma
Oturum açma verilerini dışarı aktarmak için kullanabileceğiniz iki seçenek vardır. Bunun için verileri csv dosyası biçiminde indirebilir veya PowerShell kullanabilirsiniz.

### <a name="download-csv"></a>csv dosyası indirme
Etkinlik ekranında araç çubuğunda yer alan **İndir**'i seçebilirsiniz. Bunu yaptığınızda filtrelenmiş verileri içeren bir csv dosyası indirilir.

![](media/service-admin-access-usage/download-sign-in-data-csv.png)

### <a name="powershell"></a>PowerShell
Oturum açma verilerini dışarı aktarmak için PowerShell kullanabilirsiniz. Azure AD belgelerinde bununla ilgili bir [örnek](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-api-sign-in-activity-samples#powershell-script) mevcuttur.

> [!NOTE]
> PowerShell örneğinin çalışması için [prerequisites to access the Azure AD reporting API (Azure AD raporlama API'sine erişmek için önkoşullar)](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-reporting-api-prerequisites) sayfasını incelediğinizden emin olun.
> 
> 

## <a name="data-retention"></a>Veri saklama
Oturum açma verileri 30 güne kadar saklanabilir. Daha fazla bilgi için bkz. [Azure Active Directory report retention policies (Azure Active Directory rapor saklama ilkeleri)](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-retention).

## <a name="next-steps"></a>Sonraki adımlar
[Azure Active Directory portalındaki oturum açma etkinliği raporları (Yeni Portal)](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-activity-sign-ins)  
[Erişim ve kullanım raporlarınızı görüntüleme (Klasik Portal)](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports#view-or-download-a-report)  
[Oturum açma örnek PowerShell betiği](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-api-sign-in-activity-samples#powershell-script)  
[Azure Active Directory report retention policies (Azure Active Directory rapor saklama ilkeleri)](https://docs.microsoft.com/azure/active-directory/active-directory-reporting-retention)  
[Kuruluşunuzda denetim özelliğini kullanma](service-admin-auditing.md)  
[Uzatılmış Pro Deneme Sürümünü etkinleştirme](service-extended-pro-trial.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)

