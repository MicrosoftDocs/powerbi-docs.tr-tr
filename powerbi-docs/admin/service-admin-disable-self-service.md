---
title: Self servis kaydolma ve satın alma işlemlerini etkinleştirme veya devre dışı bırakma
description: Yöneticiler için, kullanıcıların Power BI hizmetine kaydolma ve lisans satın alma veya yükseltme olanağını devre dışı bırakma hakkında nasıl yapılır bilgileri.
author: mihart
ms.author: mihart
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: how-to
ms.date: 01/31/2021
ms.custom: licensing support
LocalizationGroup: Administration
ms.openlocfilehash: 80e263cc6e67c28b7593fcf10aea4c81c9f4af86
ms.sourcegitcommit: f7330dabb9cd8bce90bb2efec3e3273a11578f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2021
ms.locfileid: "99494317"
---
# <a name="enable-or-disable-self-service-sign-up-and-purchasing"></a>Self servis kaydolma ve satın alma işlemlerini etkinleştirme veya devre dışı bırakma

## <a name="what-is-self-service"></a>Self Servis nedir?

Self servis, bir kuruluştaki (iş veya okul) kişilerin kendi kuruluşlarının aboneliğine göre ücretleşeceğini veya ücretsiz hizmetler kullanmasını istemeden kuruluşunuzun kendi adına işlem yapması gerekmeden kaydolmasına yönelik bir özellik anlamına gelir. Bireysel bir Microsoft Web sitesine gider, kuruluşunun sunduğu bir bulut hizmeti bulur ve bu hizmete kaydolmak için kuruluş e-posta adreslerini kullanır. 

Çoğu durumda, kuruluş bu hizmete bir abonelik için ücret ödemiştir. Diğer durumlarda, tek kullanıcı ilk Kullanıcı olur ve hizmetin Yöneticisi olur. Deneme veya ücretsiz lisans için satın alma gerekmez. Ancak Power BI Pro için kuruluş, aylık ücreti ödemekten sorumludur. 

Microsoft 365 Yöneticisi olarak, deneme, lisans ve abonelikler için kimin kaydoldığına bakabilirsiniz.

> [!NOTE]
> Self Servis kaydolma, Ulusal bulutlar veya kamu müşterileri için değil yalnızca ticari bulut müşterileri için geçerlidir.

## <a name="when-to-use-self-service-sign-up-and-purchase"></a>Self Servis kaydolma ve satın alma ne zaman kullanılır?

### <a name="self-service-is-a-good-idea"></a>Self servis iyi bir fikirdir: 

- Daha büyük ve merkezi olmayan kuruluşların (iş veya okul), bireylerin genellikle kendi kullanımları için SaaS (hizmet olarak yazılım) lisansları satın alma esnekliği verildiği. 
- Yalnızca bir Power BI Pro lisansı satın alması gereken tek kişi veya küçük kuruluşlar için veya yalnızca birkaç lisans.
- Power BI denemeden ilgilenen bireyler için, tüm kuruluş için bir abonelik satın almadan önce yeterlilikte.
- Power BI ücretsiz lisansa sahip geçerli kullanıcılar için, artık içerik oluşturup paylaşmak ve kendilerini Power BI Pro bir denemeye yükseltmek ister. 

### <a name="you-may-want-to-disable-self-service-when"></a>Self servis hizmetini devre dışı bırakmak isteyebilirsiniz:

- Kuruluşunuz uyumluluk, mevzuata, güvenlik ve idare ihtiyaçlarını karşılamak için satın alma süreçlerini sunmaktadır. Tüm Power BI Pro lisanslarının, tanımlı işlemlere göre onaylandığından ve yönetildiğinden emin olmanız gerekir. 
- Kuruluşunuz, zorunlu eğitim veya veri koruma ilkelerinin Kullanıcı bildirimi gibi yeni Power BI Pro kullanıcılarına yönelik gereksinimlere sahiptir.
- Kuruluşunuz, veri gizliliği veya diğer sorunlar nedeniyle Power BI hizmeti kullanımını yasaklar ve Power BI ücretsiz lisansların atanmasını çok yakından denetmaktır.
- Tüm Power BI Pro lisanslarının kurumsal anlaşma kapsamında olduğundan emin olmak için, anlaşmalı/indirimli lisanslama tarifelerinin avantajlarından yararlanın.
- Power BI ücretsiz lisansa sahip geçerli kullanıcılar için, bir Power BI Pro lisansını denemekten veya doğrudan satın almanızdan istemde bulunur. Kuruluşunuz, güvenlik, gizlilik veya gider nedeniyle bu kullanıcıların yükseltmesini istemiyor olabilir.


## <a name="enable-and-disable-self-service"></a>Self servis hizmetini etkinleştirme ve devre dışı bırakma

Yönetici olarak, self servis kaydolma özelliğinin etkinleştirileceğini veya devre dışı bırakılacağını siz belirlersiniz. Ayrıca, kuruluşunuzdaki kullanıcıların kendi lisansını almak için self servis satın alımları yapıp yapamayacağını da belirlersiniz. 

Self servis kaydolma özelliğini kapatmak, kullanıcıların veri görselleştirmeleri ve analizi için Power BI’ı keşfetmelerini engeller. Tek kaydolmayı engellediyseniz kuruluşunuz için Power BI (ücretsiz) lisansları alıp bunları kullanıcılara atamanız faydalı olabilir. 

> [!NOTE]
>Bir Microsoft Bulut çözüm sağlayıcısı (CSP) aracılığıyla Power BI edindiyseniz, bu ayar kullanıcıların ayrı ayrı kaydolmasını engellemek için devre dışı bırakılabilir. CSP'niz, kuruluşunuzun genel yöneticisi olarak da hareket edebilir ve bu ayarı değiştirmenize yardımcı olmaları için onlarla iletişim kurmanız gerekebilir.
>


 Self Servis kaydolma ve satın alma işlemlerini denetleyen ayarları değiştirmek için PowerShell komutlarını kullanırsınız. 

- Tüm self servis kaydolma işlemlerini devre dışı bırakmak istiyorsanız, Azure AD PowerShell komutlarını kullanarak Azure Active Directory’deki **AllowAdHocSubscriptions** adlı bir ayarı değiştirin. [Self servis kaydolma özelliğini etkinleştirmek veya devre dışı bırakmak](#enable-or-disable-self-service-sign-up-for-your-organization) için bu makaledeki adımları izleyin. Bu seçenek, bulut tabanlı *tüm* Microsoft uygulamaları ve hizmetleri için self servis kaydolma özelliğini devre dışı bırakır.

- Kullanıcıların kendi Pro lisansını satın almasını engellemek istiyorsanız, MSCommerce PowerShell komutlarını kullanarak **AllowSelfServicePurchase** ayarını değiştirin. Bu ayar, belirli ürünler için self servis satın alma özelliğini kapatmanızı sağlar. [Power BI Pro lisanslarına ilişkin self servis satın alma özelliğini etkinleştirmek veya devre dışı bırakmak](#enable-or-disable-self-service-purchase-in-your-organization) için bu makaledeki adımları izleyin.

## <a name="enable-or-disable-self-service-sign-up-for-your-organization"></a>Kuruluşunuz için self servis kaydolma özelliğini etkinleştirme veya devre dışı bırakma

Self servis kaydolma etkinse, **AllowAdHocSubscriptions** değeri *true* olur. Bu ayarı *false* olarak değiştirdiğinizde ne olacağına göz atalım:

- Kuruluşunuzdaki yeni kullanıcıların ayrı ayrı kaydolmasının engellenmesi. Ayarı değiştirmeden önce Power BI kaydolan tüm kullanıcılar lisanslarını saklar.

- Zaten bir Power BI (ücretsiz) lisansına sahip kullanıcılar, tek bir Power BI Pro denemesine kaydolabilir.

- Yöneticinin tüm Power BI lisanslarını bir tane olması gereken yeni kullanıcılara ataması gerekecektir.

### <a name="before-you-begin"></a>Başlamadan önce

Bu adımlarda, **AllowAdHocSubscriptions** ayarının değerini değiştirmek için Azure Active Directory PowerShell komutları kullanılır. Bu komutların kullanılabilmesi için Azure AD PowerShell modülünü yüklemiş olmanız gerekir. PowerShell kullanma hakkında daha fazla bilgi için bkz. [Windows PowerShell ile çalışmaya başlama](/powershell/scripting/getting-started/getting-started-with-windows-powershell).

Azure AD modülünü yüklemek için Windows PowerShell'i yönetici olarak başlatın. Yerel yürütme ilkenizin betikleri çalıştırmanıza izin verdiğinden emin olun. Sorunlarla karşılaşırsanız, yerel ilkenizi nasıl değiştireceğinizi öğrenmek için bkz. [PowerShell yürütme ilkeleri](/powershell/module/microsoft.powershell.core/about/about_execution_policies#powershell-execution-policies).

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

## <a name="enable-or-disable-self-service-purchase-in-your-organization"></a>Kuruluşunuzda self servis satın almayı etkinleştirme veya devre dışı bırakma

Self servis satın alma etkinse, **AllowSelfServicePurchase** değeri *true* olur. Bu ayarı *false* olarak değiştirdiğinizde ne olacağına göz atalım:

- Kuruluşunuzdaki kullanıcıların kendi Power BI Pro lisansını satın alma engellenir. Ayarı değiştirmeden önce bir lisans satın alan tüm kullanıcılar lisanslarını tutar.

- Power BI (ücretsiz) lisansı olan kullanıcılar bireysel bir Power BI Pro lisansı alamaz. 

- Yöneticinin bir Pro lisansını bir tane ihtiyacı olan tüm kullanıcılara ataması gerekir.

### <a name="before-you-begin"></a>Başlamadan önce

Bu adımlarda, **AllowSelfServicePurchase** ayarının değerini değiştirmek için MSCommerce PowerShell komutları kullanılır. Bu komutların kullanılabilmesi için MSCommerce PowerShell modülünü yüklemiş olmanız gerekir. PowerShell kullanma hakkında daha fazla bilgi için bkz. [Windows PowerShell ile çalışmaya başlama](/powershell/scripting/getting-started/getting-started-with-windows-powershell).

MSCommerce modülünü yüklemek için Windows PowerShell'i yönetici olarak başlatın. Yerel yürütme ilkenizin betikleri çalıştırmanıza izin verdiğinden emin olun. Sorunlarla karşılaşırsanız, yerel ilkenizi nasıl değiştireceğinizi öğrenmek için bkz. [PowerShell yürütme ilkeleri](/powershell/module/microsoft.powershell.core/about/about_execution_policies#powershell-execution-policies).

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

## <a name="what-to-do-if-individuals-have-already-used-self-service"></a>Bireyler zaten self servis kullanıyorsa Yapılacaklar

Self Servis kaydolma ve satın alma, her ikisi de varsayılan olarak etkinleştirilmiştir. Bu, kuruluşunuzdaki kişilerin Power BI lisanslarını ve aboneliklerini zaten sahip olmasını sağlar. Herhangi bir eylem yapıp gördüğseniz de, zaten var olan nelerin açık olduğuna ilişkin bir resminiz olması gerekir.

Kiracınıza self-servis kaydolma üzerinden katılan kullanıcılara benzersiz bir lisans atanır. Yönetici panonuzun etkin kullanıcı bölmesinde bu lisansa göre filtreleme yapabilirsiniz. Bu yeni görünümü oluşturmak için aşağıdaki adımları izleyin.

1. Microsoft 365 yönetim merkezine gidin.

1. Gezinti bölmesinde, **Kullanıcılar** > **Etkin Kullanıcılar**’ı seçin.

1. Görünümler menüsünde **Özel görünüm ekle**'yi seçin.

1. Yeni görünümünüzü adlandırın ve Atanan ürün lisansı bölümünde Power BI (ücretsiz) veya Power BI Pro seçeneğini belirleyin.

    Görünüm başına yalnızca bir lisans seçebilirsiniz. Kuruluşunuzda hem Power BI (ücretsiz) hem de Power BI Pro lisansları varsa iki görünüm oluşturabilirsiniz.

1. Varsa eklemek istediğiniz diğer koşulları da girin ve **Ekle**'yi seçin.

    Yeni görünümü oluşturduktan sonra, görünüme Görünümler menüsünden erişebilirsiniz.


    > [!NOTE]
    > Kuruluşunuzun e-posta etki alanına bağlı bir Microsoft 365 ortamı yoksa, self servis kullanıcıları yeni, yalnızca bulut kullanıcı dizinine eklenmiştir. [Zaten oluşturulmuş olan kiracıların](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)bulunması, talep etmeniz ve devralmanız gerekebilir. 

## <a name="next-steps"></a>Sonraki adımlar

Power BI’da self servis satın alma ve Power Platform’un geri kalanı hakkında daha fazla bilgi için şu makalelere bakın:

- [Self servis satın alma hakkında SSS](/microsoft-365/commerce/subscriptions/self-service-purchase-faq#admin-capabilities)
- [MSCommerce PowerShell modülü için AllowSelfServicePurchase kullanma](/microsoft-365/commerce/subscriptions/allowselfservicepurchase-powershell)