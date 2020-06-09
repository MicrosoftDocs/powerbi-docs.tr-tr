---
title: Self servis kaydolma ve satın alma işlemlerini etkinleştirme veya devre dışı bırakma
description: Yöneticiler için, kullanıcıların Power BI hizmetine kaydolma ve lisans satın alma veya yükseltme olanağını devre dışı bırakma hakkında nasıl yapılır bilgileri.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/08/2020
ms.author: kfollis
ms.custom: licensing support
LocalizationGroup: Administration
ms.openlocfilehash: 751db634ceb9e7d6349b35f7348b09e0c0d648ed
ms.sourcegitcommit: 3f864ec22f99ca9e25cda3a5abda8a5f69ccfa8e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2020
ms.locfileid: "84160077"
---
# <a name="enable-or-disable-self-service-sign-up-and-purchasing"></a>Self servis kaydolma ve satın alma işlemlerini etkinleştirme veya devre dışı bırakma

Çoğu kuruluşta, self servis kaydolma varsayılan olarak etkindir. Kuruluşunuzdaki bireysel kullanıcılar, iş veya okul hesaplarını kullanarak Power BI’a kaydolabilir. Ayrıca kullanıcılar Power BI Pro gerektiren bir özelliği kullanmaya çalıştığında, bu kullanıcılara doğrudan bir Pro lisansı satın alma seçeneği de sunulabilir. Yönetici olarak, self servis kaydolma özelliğinin etkinleştirileceğini veya devre dışı bırakılacağını siz belirlersiniz. Ayrıca, kuruluşunuzdaki kullanıcıların kendi lisanslarını almak için self servis satın alma işlemleri yapıp yapamayacağını da denetleyebilirsiniz.

> [!NOTE]
>Bir Microsoft Bulut Çözümü Sağlayıcısı (CSP) aracılığıyla Power BI edindiyseniz, bu ayar kullanıcıların ayrı ayrı kaydolmasını engellemek için devre dışı bırakılabilir. CSP'niz, kuruluşunuzun genel yöneticisi olarak da hareket edebilir ve bu ayarı değiştirmenize yardımcı olmaları için onlarla iletişim kurmanız gerekebilir.
>
>

Self servis kaydolma ve satın alma işlemlerini denetleyen ayarları değiştirmek için PowerShell komutlarını kullanırsınız. Kuruluşunuzdaki kullanıcıların self servis kaydolma veya self servis satın alma işlemleri yapıp yapamayacağını denetleyen iki ayar vardır.

- Tüm self servis kaydolma işlemlerini devre dışı bırakmak istiyorsanız, Azure AD PowerShell komutlarını kullanarak Azure Active Directory’deki **AllowAdHocSubscriptions** adlı bir ayarı değiştirin. [Self servis kaydolma özelliğini etkinleştirmek veya devre dışı bırakmak](#enable-or-disable-self-service-signup) için bu makaledeki adımları izleyin. Bu seçenek, bulut tabanlı *tüm* Microsoft uygulamaları ve hizmetleri için self servis kaydolma özelliğini devre dışı bırakır.

- Kullanıcıların kendi Pro lisansını satın almasını engellemek istiyorsanız, MSCommerce PowerShell komutlarını kullanarak **AllowSelfServicePurchase** ayarını değiştirin. Bu ayar, belirli ürünler için self servis satın alma özelliğini kapatmanızı sağlar. [Power BI Pro lisanslarına ilişkin self servis satın alma özelliğini etkinleştirmek veya devre dışı bırakmak](#enable-or-disable-self-service-purchase) için bu makaledeki adımları izleyin.

## <a name="enable-or-disable-self-service-signup"></a>Self servis kaydolma özelliğini etkinleştirme veya devre dışı bırakma

Self servis kaydolma etkinse, **AllowAdHocSubscriptions** değeri *true* olur. Bu ayarı *false* olarak değiştirdiğinizde ne olacağına göz atalım:

- True olan ayarı false olarak değiştirirseniz, kuruluşunuzdaki yeni kullanıcıların ayrı ayrı kaydolması engellenir. Ayarı değiştirmeden önce Power BI'a kaydolmuş olan tüm kullanıcılar lisanslarını korur.

- Ayarı false olarak değiştirdiğinizde, zaten Power BI (ücretsiz) lisansına sahip olan kullanıcılar yine de bireysel Power BI Pro deneme sürümüne kaydolabilir.

- Yöneticinin, Power BI lisansı gereken yeni kullanıcılara bu lisansların tümünü ataması gerekir.

### <a name="before-you-begin"></a>Başlamadan önce

Bu adımlarda, **AllowAdHocSubscriptions** ayarının değerini değiştirmek için Azure Active Directory PowerShell komutları kullanılır. Bu komutların kullanılabilmesi için Azure AD PowerShell modülünü yüklemiş olmanız gerekir. PowerShell kullanma hakkında daha fazla bilgi için bkz. [Windows PowerShell ile çalışmaya başlama](https://docs.microsoft.com/powershell/scripting/getting-started/getting-started-with-windows-powershell?view=powershell-7).

Azure AD modülünü yüklemek için Windows PowerShell'i yönetici olarak başlatın. Yerel yürütme ilkenizin betikleri çalıştırmanıza izin verdiğinden emin olun. Sorunlarla karşılaşırsanız, yerel ilkenizi nasıl değiştireceğinizi öğrenmek için bkz. [PowerShell yürütme ilkeleri](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?view=powershell-7#powershell-execution-policies).

Azure AD modülünü yüklemek için şu komutu çalıştırın:

```powershell
Install-Module MSOnline
```

### <a name="change-the-self-service-signup-policy"></a>Self servis kaydolma ilkesini değiştirme

PowerShell’de, Azure AD’ye bağlanmak için şu komutu çalıştırın:

```powershell
Connect-MsolService
```

Yönetici kimlik bilgilerinizi oturum açma iletişim kutusuna girerek, gerekli olabilecek iki öğeli kimlik doğrulaması işlemlerini tamamlayın. Doğrulama işleminden sonra, PowerShell penceresine geri dönersiniz.

Geçerli ayarı görüntülemek için aşağıdaki komutu çalıştırın. Çıkış, "fl" anahtarı kullanılarak biçimlendirilen bir listeye gönderilir.

```powershell
Get-MsolCompanyInformation | fl AllowAdHocSubscriptions
```

Geçerli ayarı değiştirmek için şu komutu çalıştırın:

```powershell
Set-MsolCompanySettings -AllowAdHocSubscriptions $false
```

Bu komutu çalıştırdıktan sonra, self servis kaydolma tüm kullanıcılar için devre dışı bırakılır. Tekrar açmak için bu komutu yeniden çalıştırın ve değeri $true olarak ayarlayın.

## <a name="enable-or-disable-self-service-purchase"></a>Self servis satın alma özelliğini etkinleştirme veya devre dışı bırakma

Self servis satın alma etkinse, **AllowSelfServicePurchase** değeri *true* olur. Bu ayarı *false* olarak değiştirdiğinizde ne olacağına göz atalım:

- True olan ayarı false olarak değiştirirseniz, kuruluşunuzdaki kullanıcıların kendi Power BI Pro lisanslarını satın alması engellenir. Ayarı değiştirmeden önce lisans satın almış olan tüm kullanıcılar lisanslarını korur.

- Ayarı false olarak değiştirirseniz, Power BI (ücretsiz) lisansına sahip olan kullanıcılar bireysel Power BI Pro lisansı alamaz. 

- Yöneticinin, Pro lisansı gereken tüm kullanıcılara bu lisansı ataması gerekir.

### <a name="before-you-begin"></a>Başlamadan önce

Bu adımlarda, **AllowSelfServicePurchase** ayarının değerini değiştirmek için MSCommerce PowerShell komutları kullanılır. Bu komutların kullanılabilmesi için MSCommerce PowerShell modülünü yüklemiş olmanız gerekir. PowerShell kullanma hakkında daha fazla bilgi için bkz. [Windows PowerShell ile çalışmaya başlama](https://docs.microsoft.com/powershell/scripting/getting-started/getting-started-with-windows-powershell?view=powershell-7).

MSCommerce modülünü yüklemek için Windows PowerShell'i yönetici olarak başlatın. Yerel yürütme ilkenizin betikleri çalıştırmanıza izin verdiğinden emin olun. Sorunlarla karşılaşırsanız, yerel ilkenizi nasıl değiştireceğinizi öğrenmek için bkz. [PowerShell yürütme ilkeleri](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?view=powershell-7#powershell-execution-policies).

MSCommerce modülünü yüklemek için şu komutu çalıştırın:

```powershell
Install-Module -name MSCommerce
```

### <a name="change-the-self-service-signup-policy"></a>Self servis kaydolma ilkesini değiştirme

PowerShell’de, bağlanmak için şu komutu çalıştırın:

```powershell
Connect-MSCommerce
```

Yönetici kimlik bilgilerinizi oturum açma iletişim kutusuna girerek, gerekli olabilecek iki öğeli kimlik doğrulaması işlemlerini tamamlayın. Doğrulama işleminden sonra, PowerShell penceresi başarılı bir bağlantı gösterir.

Geçerli ayarı görüntülemek için aşağıdaki komutu çalıştırın. Metnin kesilmesini önlemek için çıkış, "fl" anahtarı kullanılarak biçimlendirilen bir listeye gönderilir.

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase | fl
```

Bireysel bir ürünün **ProductId** öğesini sağlayarak bu ürün için self servis satın alma özelliğine izin veren ayarı devre dışı bırakabilirsiniz. Power BI hizmetinin geçerli ayarını değiştirmek için şu komutu çalıştırın:

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0L3PB -Enabled $False
```

Bu komutu çalıştırdıktan sonra, Power BI’ın self servis satın alma özelliği tüm kullanıcılar için devre dışı bırakılır. Tekrar açmak için bu komutu yeniden çalıştırın ve değeri $true olarak ayarlayın.

## <a name="next-steps"></a>Sonraki adımlar

Power BI’da self servis satın alma ve Power Platform’un geri kalanı hakkında daha fazla bilgi için şu makalelere bakın:

- [Self servis satın alma hakkında SSS](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/self-service-purchase-faq?view=o365-worldwide#admin-capabilities)
- [MSCommerce PowerShell modülü için AllowSelfServicePurchase kullanma](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/allowselfservicepurchase-powershell?view=o365-worldwide)
