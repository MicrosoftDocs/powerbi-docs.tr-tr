---
title: Microsoft Intune ile mobil uygulamaları yapılandırma
description: Power BI Mobil uygulamalarını Microsoft Intune ile yapılandırma. Bu makalede, uygulamayı ekleme ve dağıtma işlemleri açıklanır. Ayrıca güvenliği denetlemeye yönelik mobil uygulama ilkesinin nasıl oluşturulacağı da ele alınır.
author: paulinbar
ms.author: painbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: how-to
ms.date: 09/25/2020
LocalizationGroup: Administration
ms.openlocfilehash: 6ca9b241fe2d6f2914a603e722f2dd2c216e05df
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96408792"
---
# <a name="configure-mobile-apps-with-microsoft-intune"></a>Microsoft Intune ile mobil uygulamaları yapılandırma

Microsoft Intune, kuruluşların cihazları ve uygulamaları yönetmesine olanak sağlar. iOS ve Android için Power BI mobil uygulamaları Intune ile tümleştirilmiştir. Bu tümleştirme sayesinde cihazlarınızdaki uygulamayı yönetebilir ve güvenlik denetimi gerçekleştirebilirsiniz. Yapılandırma ilkeleri aracılığıyla erişim PIN'i gerektirme, verilerin uygulama tarafından işlenme şekli ve hatta uygulama kullanılmadığı sırada uygulama verilerini şifreleme gibi öğeleri denetleyebilirsiniz.

Microsoft Power BI mobil uygulaması, işinizle ilgili önemli bilgilere erişmenizi sağlar. Kuruluşunuzun yönetilen cihaz ve uygulama iş verilerinizle ilgili panoları ve raporları görüntüleyebilir, bunlarla etkileşim kurabilirsiniz. Desteklenen Intune uygulamaları hakkında daha fazla bilgi için bkz. [Microsoft Intune korumalı uygulamaları](/intune/apps/apps-supported-intune-apps).

## <a name="general-mobile-device-management-configuration"></a>Genel mobil cihaz yönetim yapılandırması

Bu makalede Intune'un düzgün yapılandırıldığı ve Intune'da kayıtlı cihazlarınızın bulunduğu varsayılmaktadır. Bu makale, Microsoft Intune için tam kapsamlı bir yapılandırma kılavuzu olarak hazırlanmamıştır. Intune hakkında daha fazla bilgi için bkz. [Intune nedir?](/intune/introduction-intune/).

Microsoft Intune, Microsoft 365'te Mobil Cihaz Yönetimi (MDM) ile birlikte bulunabilir. MDM'yi kullanıyorsanız cihaz, MDM'de kayıtlı olarak görünür ancak Intune'da yönetilebilir.

Son kullanıcıların Power BI uygulamasını cihazlarında kullanabilmesi için Intune yöneticisinin ilgili uygulamayı Intune'a eklemesi ve ayrıca son kullanıcılara ataması gerekir.

> [!NOTE]
> Intune'u yapılandırdıktan sonra iOS veya Android cihazınızda Power BI mobil uygulaması için arka planda veri yenileme özelliği kapatılır. Uygulamaya girdiğinizde Power BI, web üzerindeki Power BI hizmetinden verileri yeniler.

## <a name="step-1-add-the-power-bi-app-to-intune"></a>1\. Adım: Power BI'ı Intune'a ekleme

Power BI uygulamasını Intune'a eklemek için aşağıdaki konu başlıklarında sunulan adımları izleyin:
- [iOS mağaza uygulamalarını Microsoft Intune’a ekleme](/intune/apps/store-apps-ios)
- [Android mağazası uygulamalarını Microsoft Intune’a ekleme](/intune/apps/store-apps-android)

## <a name="step-2-assign-the-app-to-your-end-users"></a>2\. Adım: Uygulamayı son kullanıcılarınıza atama

Power BI uygulamasını Microsoft Intune'a ekledikten sonra kullanıcılara ve cihazlara atayabilirsiniz. Uygulamayı Intune ile yönetilmeyen cihazlara da atayabileceğinizi unutmayın.

Power BI uygulamasını kullanıcılara ve cihazlara atamak için bkz. [Microsoft Intune ile uygulamaları gruplara atama](/intune/apps/apps-deploy).

## <a name="step-3-create-and-assign-app-protection-policies"></a>3\. Adım: Uygulama koruma ilkesi oluşturma ve atama

Uygulama koruma ilkeleri (APP), kuruluş verilerinin yönetilen uygulama içinde güvende olmasını veya orada kalmasını sağlayan kurallardır. İlke, kullanıcı “kurumsal” verilere erişmeye veya bunları taşımaya çalıştığında uygulanan bir kural veya kullanıcı uygulamadayken yasaklanan veya izlenen bir eylemler kümesi olabilir. Yönetilen bir uygulama, uygulama koruma ilkelerinin uygulandığı ve Intune tarafından yönetilebilen bir uygulamadır.

Mobil Uygulama Yönetimi (MAM) uygulama koruma ilkeleri, uygulama içindeki kuruluş bilgilerini yönetmenizi ve korumanızı sağlar. Kayıtsız MAM (MAM-WE) ile, hassas veriler içeren iş veya okul ile ilgili uygulamalar, kendi cihazını getir (KCG) senaryolarında kişisel cihazlar dahil neredeyse her cihazdan yönetilebilir. Daha fazla bilgi için bkz. [Uygulama koruma ilkelerine genel bakış](/intune/apps/app-protection-policy).

Power BI uygulamasına yönelik uygulama koruma ilkesi oluşturmak ve atamak için [Uygulama koruma ilkesi oluşturma ve atama](/intune/apps/app-protection-policies) makalesindeki adımları izleyin.

## <a name="step-4-use-the-application-on-a-device"></a>4\. Adım: Uygulamayı bir cihazda kullanma

Yönetilen uygulamalar, şirketinizin destek biriminin ilgili uygulamada erişebildiğiniz şirket verilerini korumak üzere ayarlayabildiği uygulamalardır. Cihazınızdaki yönetilen uygulamadan şirket verilerine eriştiğinizde uygulamanın beklediğinizden farklı çalıştığını fark edebilirsiniz. Örneğin, korunan şirket verilerini kopyalayıp yapıştıramayabilir veya bu verileri belirli konumlara kaydedemeyebilirsiniz.

Son kullanıcılarınızın Power BI uygulamasını cihazlarında nasıl kullanabileceklerini anlamak için aşağıdaki makalelerde verilen adımları inceleyin:
- [iOS cihazınızdaki yönetilen uygulamaları kullanma](/intune-user-help/use-managed-apps-on-your-device-ios#how-do-i-get-managed-apps)
- [Android cihazınızdaki yönetilen uygulamaları kullanma](/intune-user-help/use-managed-apps-on-your-device-android)

## <a name="next-steps"></a>Sonraki adımlar

[Uygulama koruma ilkeleri oluşturma ve atama](/intune/app-protection-policies) 

[Mobil cihazlar için Power BI uygulamaları](../consumer/mobile/mobile-apps-for-mobile-devices.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)