---
title: Power BI, O365 iş ortağı aboneliğine eklenemiyor
description: Power BI, bir Office 365 dağıtım iş ortağına eklenemiyor. Dağıtılmış model, Office 365 tarafından kullanılan bir satın alma modeli.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 11/01/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 912ed0be1e6a732db46e83f8a9b0757ad2801dab
ms.sourcegitcommit: c09241803664643e1b2ba0c150e525e1262ca466
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/08/2019
ms.locfileid: "52157414"
---
# <a name="unable-to-add-power-bi-to-office-365-partner-subscription"></a>Power BI, Office 365 iş ortağı aboneliğine eklenemiyor

Office 365 şirketlere, Office 365'i kendi çözümleriyle paketlenmiş ve tümleştirilmiş biçimde yeniden satma olanağı sunar ve son kullanıcılara satın alma, fatura ve destek için tek bir irtibat noktası sağlar.

Office 365 aboneliğinizin yanında Power BI'ı da edinmek istiyorsanız iş ortağınızla iletişime geçmenizi öneririz. İş ortağınız şu an için Power BI'ı sunmuyorsa farklı seçeneklere başvurabilirsiniz.

## <a name="work-with-your-partner-to-purchase-power-bi"></a>Power BI'ı satın almak için iş ortağınızla birlikte çalışma

Bir Power BI Pro veya Power BI Premium aboneliği satın almak istiyorsanız, sahip olduğunuz seçenekleri değerlendirmek için iş ortağınızla iletişim kurabilirsiniz:

* İş ortağınız, hizmeti kendisinden satın alabilmeniz için Power BI'ı portföyüne ekleyebilir.

* İş ortağınız sizi, Power BI'ı doğrudan Microsoft'tan veya Power BI'ı sunan başka bir iş ortağından satın alabileceğiniz bir modele geçirebilir.

## <a name="purchase-from-microsoft-or-another-channel"></a>Microsoft'tan veya başka bir kanaldan satın alma

İş ortağınızla aranızdaki ilişkiye bağlı olarak Power BI'ı doğrudan Microsoft'tan veya başka bir iş ortağından satın alma seçeneğine sahip olabilirsiniz. Office 365 yönetim portalından Power BI aboneliği ekleyip ekleyemediğinizi doğrulayabilirsiniz (Genel Yönetici veya Faturalama Yöneticisi rolüne sahip olmanız gerekir).

1. [Office 365 yönetim portalına](https://admin.microsoft.com/AdminPortal/Home#/homepage) gidin.

1. Sol taraftaki menüden **Faturalama**'yı açın:

    * **Abonelikler**'i görüyorsanız hizmeti doğrudan Microsoft'tan edinebilir veya Power BI'ı hizmetini sunan başka bir iş ortağıyla iletişime geçebilirsiniz.

        ![Abonelikler seçeneğinin bulunduğu Faturalama sayfası](media/service-admin-syndication-partner/billingsub.png)

    * **Abonelikler** seçeneği yoksa doğrudan Microsoft'tan veya başka bir iş ortağından satın alma imkanınız yoktur.

İş ortağınız Power BI hizmetini sunmuyorsa ve doğrudan Microsoft'tan veya başka bir iş ortağından satın alma seçeneğiniz de yoksa ücretsiz deneme için kaydolabilirsiniz.

## <a name="sign-up-for-a-free-trial"></a>Ücretsiz deneme için kaydolma

Power BI Pro için ücretsiz denemeye kaydolabilirsiniz. Deneme süresinin sonunda Power BI Pro'yu satın almasanız da birçok Power BI özelliğini sunan ücretsiz bir lisansa sahip olursunuz. Daha fazla bilgi için bkz. [Lisans türüne göre Power BI özellikleri](service-features-license-type.md).

### <a name="enable-ad-hoc-subscriptions"></a>Özel abonelikleri etkinleştirme

Özel abonelikler olarak da bilinen bireysel kaydolma işlemleri varsayılan olarak devre dışıdır. Bu durumda, kaydolmayı denediğinizde aşağıdaki iletiyi görürsünüz: *Microsoft Power BI için kayıt işlemi, BT departmanınız tarafından devre dışı bırakılmış*.

![Üzgünüz görüntüsü](media/service-admin-syndication-partner/sorry.png)

Özel abonelikleri etkinleştirmek için, iş ortağınızla iletişime geçip bu seçeneği kullanımınıza sunmasını isteyebilirsiniz. Kiracınızda yöneticiyseniz ve Azure Active Directory PowerShell komutlarını kullanmayı biliyorsanız özel abonelikleri kendiniz de etkinleştirebilirsiniz. [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2/)

1. Office 365 kimlik bilgilerinizi kullanıp Azure Active Directory'de oturum açın. Aşağıdaki betiğin ilk satırında sizden kimlik bilgileriniz istenir. İkinci satırda Azure Active Directory ile bağlantı kurulur.

    ```powershell
    $msolcred = get-credential
    connect-msolservice -credential $msolcred
    ```

    ![Kimlik bilgilerinizi girin](media/service-admin-syndication-partner/aad-signin.png)

1. Oturum açtıktan sonra geçerli `AllowAdHocSubscriptions` ayarını denetlemek için aşağıdaki komutu çalıştırın.

    ```powershell
    Get-MsolCompanyInformation
    ```

1. Ücretsiz kaydolma seçeneğini etkinleştirmek için aşağıdaki komutu çalıştırın.

    ```powershell
    Set-MsolCompanySettings -AllowAdHocSubscriptions $true
    ```

## <a name="next-steps"></a>Sonraki adımlar

[Kuruluşunuzda Power BI lisansları](service-admin-licensing-organization.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)