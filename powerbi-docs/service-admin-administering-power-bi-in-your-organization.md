---
title: "Kuruluşunuzda Power BI uygulamasını yönetme"
description: "Kuruluşunuzda Power BI uygulamasını yönetme"
services: powerbi
documentationcenter: 
author: guyinacube
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 11/28/2017
ms.author: asaxton
ms.openlocfilehash: 180e80ee327342b26849aa63a3910337737ac9ad
ms.sourcegitcommit: 7742f952c20695dfb475f74965c0065b02c01521
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/29/2017
---
# <a name="administering-power-bi-in-your-organization"></a>Kuruluşunuzda Power BI uygulamasını yönetme
Microsoft Power BI, kullanıcıların verileri görselleştirmesine, keşfettiklerini paylaşmasına, yeni ve kolay anlaşılır yollarla işbirliği yapmasına olanak sağlar. Daha fazla bilgi edinmek için bkz. [Power BI ile çalışmaya başlama](service-get-started.md).

Power BI yönetimi, farklı konumlardan gerçekleştirilebilir. Sık kullanılan iki konum aşağıda listelenmiştir.

> [!NOTE]
> Power BI yönetici portalına erişebilmeniz için hesabınızın, Office 365 veya Azure Active Directory'de **Genel Yönetici** olarak işaretlenmiş olması veya hesabınıza Power BI hizmet yöneticisi rolünün atanmış olması gerekir. Power BI hizmet yöneticisi rolü ile ilgili daha fazla bilgi için bkz. [Power BI yönetici rolünü anlama](service-admin-role.md).
> 
> 

* [Power BI Yönetici Portalı](https://app.powerbi.com/admin-portal)
* [Office 365 Yönetim Merkezi](https://portal.office.com/adminportal/home)

Power BI hizmet yöneticisi rolü ile ilgili daha fazla bilgi için bkz. [Power BI yönetici rolünü anlama](service-admin-role.md).

## <a name="whats-in-this-article"></a>Bu makalenin içindekiler
**Power BI'a kaydolma**

* [Kullanıcılar Power BI'a nasıl kaydolur?](#how-do-users-sign-up-for-power-bi)
* [Kuruluşumdaki bireysel kullanıcılar nasıl kaydolur?](#how-do-individual-users-in-my-organization-sign-up)
* [Kullanıcıların, var olan Office 365 kiracıma katılmalarını nasıl önleyebilirim?](#how-can-i-prevent-users-from-joining-my-existing-office-365-tenant)
* [Kullanıcıların, var olan Office 365 kiracıma katılmalarına nasıl izin verebilirim?](#how-can-i-allow-users-to-join-my-existing-office-365-tenant)
* [Kiracıda engelin etkin olduğunu nasıl doğrularım?](#how-do-i-verify-if-i-have-the-block-on-in-the-tenant)
* [Mevcut kullanıcılarımın Power BI'ı kullanmaya başlamasını nasıl önleyebilirim?](#how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi)
* [Mevcut kullanıcılarımın Power BI'a kaydolmasına nasıl izin veririm?](#how-can-i-allow-my-existing-users-to-sign-up-for-power-bi)

**Power BI Yönetimi**

* [Bu, şu anda kuruluşumdaki kullanıcıların kimliklerini yönetme biçimimi nasıl değiştirecek?](#how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today)
* [Power BI nasıl yönetilir?](#how-do-we-manage-power-bi)
* [Kullanıcılarım için Microsoft tarafından oluşturulan bir kiracıyı yönetme süreci nasıldır?](#what-is-the-process-to-manage-a-tenant-created-by-Microsoft-for-my-users)
* [Birden çok etki alanım olması halinde, kullanıcıların eklendiği Office 365 kiracısını denetleyebilir miyim?](#if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to)
* [Kayıtlı kullanıcıların Power BI lisansını nasıl kaldırabilirim?](#how-do-i-remove-power-bi-for-users-that-already-signed-up)
* [Kiracıma yeni kullanıcıların katıldığını nasıl anlarım?](#how-do-i-know-when-new-users-have-joined-my-tenant)
* [Hazırlıklı olmam gereken başka şeyler var mı?](#are-there-any-additional-things-i-should-be-prepared-for)
* [Bu ücretsiz olarak mı sunuluyor? Bu lisanslar için ücret ödemem gerekir mi?](#is-this-free-will-i-be-charged-for-these-licenses)
* [Power BI kiracım nerede bulunur?](#where-is-my-power-bi-tenant-located)
* [Power BI SLA'sı (Hizmet Düzeyi Sözleşmesi) nedir?](#what-is-the-power-bi-sla)

**Power BI'da Güvenlik**

* [Power BI ulusal, bölgesel ve sektöre özel uyumluluk gereksinimlerini karşılıyor mu?](#does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements)
* [Power BI'da güvenlik nasıl sağlanır?](#how-does-security-work-in-power-bi?)

## <a name="sign-up-for-power-bi"></a>Power BI'a kaydolma
### <a name="how-do-users-sign-up-for-power-bi"></a>Kullanıcılar Power BI'a nasıl kaydolur?
Power BI'a kaydolmak için [Power BI web sitesine](https://powerbi.microsoft.com) gidebilirsiniz. Ayrıca Office 365 yönetim merkezindeki hizmet satın alma sayfası aracılığıyla da kaydolabilirsiniz. Bir yönetici Power BI'a kaydolduğunda, erişimi olması gereken kullanıcılara kullanıcı lisansları atayabilir.

Ayrıca kuruluşunuzdaki bireysel kullanıcılar [Power BI web sitesine](https://powerbi.microsoft.com) giderek Power BI'a kaydolabilir. Kuruluşunuzdaki bir kullanıcı Power BI'e kaydolduğunda kullanıcıya otomatik olarak bir Power BI lisansı atanır. [Daha fazla bilgi](service-self-service-signup-for-power-bi.md)

### <a name="how-do-individual-users-in-my-organization-sign-up"></a>Kuruluşumdaki bireysel kullanıcılar nasıl kaydolur?
Kuruluşunuzdaki kullanıcılar için geçerli olabilecek üç senaryo vardır:

1. Senaryo: Kuruluşunuzda zaten bir Office 365 ortamı vardır ve Power BI'a kaydolacak kullanıcı bir Office 365 hesabına sahiptir.
Bu senaryoda, kullanıcının kiracıda (örneğin, contoso.com) bir iş veya okul hesabı var ancak Power BI hesabı yoksa Microsoft'un, mevcut planı söz konusu hesap için etkinleştirmesi yeterlidir. Daha sonra kullanıcı, Power BI hizmetinin nasıl kullanılacağı konusunda otomatik olarak bilgilendirilir.

2. Senaryo: Kuruluşunuzda zaten bir Office 365 ortamı vardır ancak Power BI'a kaydolacak kullanıcının bir Office 365 hesabı yoktur.
Bu senaryoda, kullanıcının kuruluşunuzun etki alanında (örneğin, contoso.com) bir e-posta adresi vardır ancak henüz Office 365 hesabı yoktur. Bu durumda, kullanıcı Power BI'a kaydolabilir ve otomatik olarak bir hesap edinir. Böylece kullanıcı Power BI hizmetine erişebilir. Örneğin, Nancy adlı bir çalışan iş e-posta adresiyle (örneğin, Nancy@contoso.com) kaydolursa Microsoft otomatik olarak Nancy'yi Contoso'nun Office 365 ortamına bir kullanıcı olarak ekler ve hesabı için Power BI'ı etkinleştirir.

3. Senaryo: Kuruluşunuzun e-posta etki alanınıza bağlı bir Office 365 ortamı yoktur.
Kuruluşunuzun Power BI'dan faydalanmak için gerçekleştirmesi gereken bir yönetim eylemi yoktur. Kullanıcılar yalnızca bulut kullanımına yönelik yeni bir kullanıcı dizinine eklenir, siz de kiracı yönetimini devralıp onları yönetme seçeneğine sahip olursunuz.

> [!IMPORTANT]
> Kuruluşunuz birden fazla e-posta etki alanına sahipse ve tüm e-posta adresi uzantılarının aynı kiracıda olmasını tercih ediyorsanız, kullanıcılar kaydolmadan önce tüm e-posta adresi etki alanlarını bir Azure Active Directory kiracısına ekleyin. Oluşturulan kullanıcıları kiracılar arasında taşımak için kullanılabilecek herhangi bir otomatik sistem yoktur. Bu işlemle ilgili daha fazla bilgi için, bu makaledeki [Birden çok etki alanım olması halinde, kullanıcıların eklendiği Office 365 kiracısını denetleyebilir miyim?](#if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to) bölümüne ve [Office 365'e etki alanı ve kullanıcı ekleme](https://support.office.com/article/Add-your-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611) başlıklı makaleye göz atın.
> 
> 

### <a name="how-can-i-prevent-users-from-joining-my-existing-office-365-tenant"></a>Kullanıcıların, var olan Office 365 kiracıma katılmalarını nasıl önleyebilirim?
Bir yönetici olarak, kullanıcıların Office 365 kiracınıza katılmasını önlemek için uygulayabileceğiniz yöntemler vardır. Katılımı engellerseniz kullanıcıların kaydolma denemeleri başarısızlıkla sonuçlanır ve kullanıcılar, kuruluşlarının yöneticisiyle iletişim kurmaya yönlendirilir. Otomatik lisans dağıtımını (örneğin, Eğitim için Office 365'te Öğrencilere, Fakültelere ve Eğitim Personeline yönelik planlar) devre dışı bıraktıysanız bu işlemi tekrarlamanıza gerek yoktur.

Bu adımlar için Windows PowerShell kullanımı gerekli değildir. Windows PowerShell ile çalışmaya başlamak için bkz. [PowerShell ile çalışmaya başlama kılavuzu](http://go.microsoft.com/fwlink/p/?LinkID=286814).

Aşağıdaki adımları uygulamak için [Windows PowerShell için Azure Active Directory Modülü](http://go.microsoft.com/fwlink/p/?LinkID=236297)'nün en son sürümünü (64 bit) yüklemeniz gerekir.

Bağlantıyı seçtikten sonra, yükleyici paketini çalıştırmak için **Çalıştır**'ı seçin.

**Kiracıya otomatik katılımı devre dışı bırakma**: Yönetilen bir kiracıya yeni kullanıcıların katılmasını önlemek için şu Windows PowerShell komutunu kullanın:

* Yeni kullanıcıların kiracıya otomatik katılımını devre dışı bırakmak için:
  
    $msolcred = get-credential   connect-msolservice -credential $msolcred
  
    Set-MsolCompanySettings - AllowEmailVerifiedUsers $false
* Yeni kullanıcıların kiracıya otomatik katılımını etkinleştirmek için:
  
    $msolcred = get-credential   connect-msolservice -credential $msolcred
  
    Set-MsolCompanySettings - AllowEmailVerifiedUsers $false

> [!NOTE]
> Bu engelleme işlemiyle, kuruluşunuzdaki yeni kullanıcıların Power BI'a kaydolması önlenir. Kuruluşunuzda yeni kaydolma işlemleri devre dışı bırakılmadan önce Power BI'a kaydolmuş olan kullanıcıların lisansları korunur. Hizmete daha önce kaydolmuş olan kullanıcıların Power BI erişimini kaldırmaya ilişkin yönergeler için [Lisansları Nasıl Kaldırabilirim?] konulu bölüme göz atın.
> 
> 

### <a name="how-can-i-allow-users-to-join-my-existing-office-365-tenant"></a>Kullanıcıların, var olan Office 365 kiracıma katılmalarına nasıl izin verebilirim?
Kullanıcıların kiracınıza katılmasına izin vermek için yukarıdaki soruda açıklanan komutun tersini çalıştırın.

Aşağıdaki adımları uygulamak için [Windows PowerShell için Azure Active Directory Modülü](http://go.microsoft.com/fwlink/p/?LinkID=236297)'nün en son sürümünü (64 bit) yüklemeniz gerekir.

    $msolcred = get-credential
    connect-msolservice -credential $msolcred

    Set-MsolCompanySettings -AllowEmailVerifiedUsers $true

### <a name="how-do-i-verify-if-i-have-the-block-on-in-the-tenant"></a>Kiracıda engelin etkin olduğunu nasıl doğrularım?
Aşağıdaki PowerShell betiğini çalıştırın.

Aşağıdaki adımları uygulamak için [Windows PowerShell için Azure Active Directory Modülü](http://go.microsoft.com/fwlink/p/?LinkID=236297)'nün en son sürümünü (64 bit) yüklemeniz gerekir.

    $msolcred = get-credential
    connect-msolservice -credential $msolcred

    Get-MsolCompanyInformation | fl allow*

### <a name="how-can-i-prevent-my-existing-users-from-starting-to-use-power-bi"></a>Mevcut kullanıcılarımın Power BI'ı kullanmaya başlamasını nasıl önleyebilirim?
Bir yönetici olarak, kullanıcıların Power BI'a kaydolmasını önlemek için uygulayabileceğiniz yöntemler vardır. Katılımı engellerseniz kullanıcıların kaydolma denemeleri başarısızlıkla sonuçlanır ve kullanıcılar, kuruluşlarının yöneticisiyle iletişim kurmaya yönlendirilir. Otomatik lisans dağıtımını (örneğin, Eğitim için Office 365'te Öğrencilere, Fakültelere ve Eğitim Personeline yönelik planlar) devre dışı bıraktıysanız bu işlemi tekrarlamanıza gerek yoktur. [Daha fazla bilgi](service-admin-service-free-in-your-organization.md#enable-or-disable-individual-user-sign-up-in-azure-active-directory)

Denetim **AllowAdHocSubscriptions** AAD ayarı tarafından gerçekleştirilir. Çoğu kiracıda bu ayar true olarak ayarlanmış, diğer bir deyişle etkinleştirilmiştir. Power BI uygulamasını bir iş ortağı aracılığıyla edindiyseniz varsayılan olarak false, diğer bir deyişle devre dışı olabilir.

Aşağıdaki adımları uygulamak için [Windows PowerShell için Azure Active Directory Modülü](http://go.microsoft.com/fwlink/p/?LinkID=236297)'nün en son sürümünü (64 bit) yüklemeniz gerekir.

1. İlk olarak, Office 365 kimlik bilgilerinizi kullanıp Azure Active Directory'de oturum açmanız gerekir. İlk satırda kimlik bilgileriniz istenir. İkinci satırda Azure Active Directory ile bağlantı kurulur.
   
     $msolcred = get-credential   connect-msolservice -credential $msolcred
2. Oturum açtıktan sonra aşağıdaki komutu kullanarak kiracınızın geçerli yapılandırmasını görebilirsiniz.
   
     Get-MsolCompanyInformation | fl AllowAdHocSubscriptions
3. Aşağıdaki komutu kullanarak AllowAdHocSubscriptions ayarını etkinleştirebilir ($true) veya devre dışı bırakabilirsiniz ($false).
   
     Set-MsolCompanySettings -AllowAdHocSubscriptions $true

> [!NOTE]
> AllowAdHocSubscriptions bayrağı, kuruluşunuzdaki çeşitli kullanıcı özelliklerini (kullanıcıların Azure Hak Yönetimi Hizmeti'ne kaydolabilmesi de dahil) denetlemek için kullanılır. Bu bayrağın değiştirilmesi bu özelliklerin tümünü etkiler.
> 
> 

### <a name="how-can-i-allow-my-existing-users-to-sign-up-for-power-bi"></a>Mevcut kullanıcılarımın Power BI'a kaydolmasına nasıl izin veririm?
Mevcut kullanıcılarınızın Power BI'a kaydolmasına izin vermek için, yukarıdaki soruda belirtilen komutu çalıştırın, ancak false yerine true değerini girin.

Aşağıdaki adımları uygulamak için [Windows PowerShell için Azure Active Directory Modülü](http://go.microsoft.com/fwlink/p/?LinkID=236297)'nün en son sürümünü (64 bit) yüklemeniz gerekir.

1. İlk olarak, Office 365 kimlik bilgilerinizi kullanıp Azure Active Directory'de oturum açmanız gerekir. İlk satırda kimlik bilgileriniz istenir. İkinci satırda Azure Active Directory ile bağlantı kurulur.
   
     $msolcred = get-credential   connect-msolservice -credential $msolcred
2. Oturum açtıktan sonra aşağıdaki komutu kullanarak kiracınızın geçerli yapılandırmasını görebilirsiniz.
   
     Get-MsolCompanyInformation | fl AllowAdHocSubscriptions
3. Aşağıdaki komutu kullanarak AllowAdHocSubscriptions ayarını etkinleştirebilir ($true) veya devre dışı bırakabilirsiniz ($false).
   
     Set-MsolCompanySettings -AllowAdHocSubscriptions $true

> [!NOTE]
> AllowAdHocSubscriptions bayrağı, kuruluşunuzdaki çeşitli kullanıcı özelliklerini (kullanıcıların Azure Hak Yönetimi Hizmeti'ne kaydolabilmesi de dahil) denetlemek için kullanılır. Bu bayrağın değiştirilmesi bu özelliklerin tümünü etkiler.
> 
> 

## <a name="administration-of-power-bi"></a>Power BI Yönetimi
### <a name="how-will-this-change-the-way-i-manage-identities-for-users-in-my-organization-today"></a>Bu, şu anda kuruluşumdaki kullanıcıların kimliklerini yönetme biçimimi nasıl değiştirecek?
Kuruluşunuzun bir Office 365 ortamı mevcutsa ve kuruluşunuzdaki tüm kullanıcıların Office 365 hesabı varsa kimlik yönetimi değişmez.

Kuruluşunuzun bir Office 365 ortamı var ancak kuruluşunuzdaki her kullanıcının Office 365 hesabı yoksa kiracıda bir kullanıcı oluşturup kullanıcının iş veya okul e-posta adresine göre lisans atarız. Bu, kuruluşunuzdaki kullanıcılar hizmete kaydoldukça, belirli herhangi bir zamanda yönettiğiniz kullanıcı sayısının artacağı anlamına gelir.

Dizininizi şirket içinde yönetiyor ve Active Directory Federasyon Hizmetleri'ni (AD FS) kullanıyorsanız Microsoft, kiracınıza kullanıcı eklemez ve kiracınıza katılmaya çalışan kullanıcılar kuruluşlarının yöneticisi ile iletişim kurmaya yönlendirilir.

Kuruluşunuzun, e-posta etki alanınıza bağlı bir Office 365 ortamı yoksa kimlik yönetme biçiminizde herhangi bir değişiklik olmaz. Kullanıcılar yalnızca bulut kullanımına yönelik yeni bir kullanıcı dizinine eklenir, siz de kiracı yönetimini devralıp onları yönetme seçeneğine sahip olursunuz.

### <a name="how-do-we-manage-power-bi"></a>Power BI nasıl yönetilir?
Power BI, kullanım istatistiklerini görüntüleyebileceğiniz bir yönetici portalı, kullanıcı ve grupları yönetmeniz için Office 365 yönetim merkezine yönelik bir bağlantı ve kiracı genelinde ayarları denetleme olanağı sağlar. 

> [!NOTE]
> Power BI yönetici portalına erişim elde etmek için hesabınızın Office 365 veya Azure Active Directory'de **Genel Yönetici** olarak işaretlenmesi gerekir.
> 
> 

Daha fazla bilgi için bkz. [Power BI Yönetici Portalı](service-admin-portal.md).

### <a name="what-is-the-process-to-manage-a-tenant-created-by-microsoft-for-my-users"></a>Kullanıcılarım için Microsoft tarafından oluşturulan bir kiracıyı yönetme süreci nasıldır?
Microsoft tarafından bir kiracı oluşturulduğunda aşağıdaki adımları uygulayarak söz konusu kiracıyı üstlenip yönetebilirsiniz:

1. Yönetmek istediğiniz kiracı etki alanıyla eşleşen bir e-posta adresi etki alanıyla Power BI'a kaydolarak söz konusu kiracıya katılın. Örneğin, Microsoft contoso.com kiracısını oluşturduysa kiracıya @contoso.com ile biten bir e-posta adresiyle katılmanız gerekir.
2. Etki alanı sahipliğini doğrulayarak yönetici denetimini üstlenin: Kiracıya katıldıktan sonra etki alanı sahipliğini doğrulayarak kendinizi *Genel Yönetici* rolüne yükseltebilirsiniz. Bunu yapmak için şu adımları uygulayın:
   
   1. [https://portal.office.com](https://portal.office.com) adresine gidin.
   2. Sol üst köşedeki uygulama başlatıcı simgesini ve ardından **Admin**'i (Yönetici) seçin.
   3. **Yönetici olun** sayfasındaki yönergeleri okuyup **Evet, yönetici olmak istiyorum** seçeneğini tıklayın.
      
      > [!NOTE]
      > Bu seçenek görünmüyorsa zaten bir Office 365 yöneticisi mevcuttur.
      > 
      > 

### <a name="if-i-have-multiple-domains-can-i-control-the-office-365-tenant-that-users-are-added-to"></a>Birden çok etki alanım olması halinde, kullanıcıların eklendiği Office 365 kiracısını denetleyebilir miyim?
Hiçbir işlem yapmamanız durumunda her bir kullanıcı e-postası etki alanı ve alt etki alanı için bir kiracı oluşturulur.

E-posta adresi uzantılarından bağımsız olarak tüm kullanıcıların aynı kiracıda olmasını istiyorsanız:

* Önceden bir hedef kiracı oluşturun veya mevcut bir kiracıyı kullanın, ardından ilgili kiracıda birleşmesini istediğiniz tüm etki alanlarını ve alt etki alanlarını ekleyin. Böylece bu etki alanları ve alt etki alanları ile biten e-posta adreslerine sahip tüm kullanıcılar, kaydolduğunda otomatik olarak hedef kiracıya katılır.

> [!IMPORTANT]
> Oluşturulan kullanıcıları kiracılar arasında taşımak için desteklenen herhangi bir otomatik sistem yoktur. Tek bir Office 365 kiracısına etki alanı ekleme hakkında bilgi edinmek için bkz. [Office 365'e etki alanı ve kullanıcı ekleme](https://support.office.com/article/Add-your-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611).
> 
> 

### <a name="how-do-i-remove-power-bi-for-users-that-already-signed-up"></a>Kayıtlı kullanıcıların Power BI lisansını nasıl kaldırabilirim?
Power BI'a kaydolmuş bir kullanıcının artık Power BI'a erişim sağlamasını istemiyorsanız kullanıcının Power BI lisansını kaldırabilirsiniz.

1. Office 365 yönetim merkezine gidin.
2. Sol gezinti çubuğunda **Kullanıcılar** > **Etkin Kullanıcılar**'ı seçin.
3. Lisansını kaldırmak istediğiniz kullanıcıyı bulup bu kullanıcının adını ve ardından **Düzenle**'yi seçin.
4. Kullanıcı ayrıntıları sayfasındaki sol gezinti çubuğunda **Lisanslar**'ı seçin.
5. İlgili hesaba uygulanan lisansa göre, **Power BI (ücretsiz)** veya **Power BI Pro** kutusunun işaretini kaldırın.
6. **Kaydet**'i seçin.

> [!NOTE]
> Kullanıcı lisanslarını toplu olarak yönetebilirsiniz. Bunu yapmak için birden fazla kullanıcıyı seçin ve **Düzenle** seçeneğini belirleyin.
> 
> 

### <a name="how-do-i-know-when-new-users-have-joined-my-tenant"></a>Kiracıma yeni kullanıcıların katıldığını nasıl anlarım?
Kiracınıza bu programın bir parçası olarak katılan kullanıcılara benzersiz bir lisans atanır. Yönetici panonuzun etkin kullanıcı bölmesinde bu lisansa göre filtreleme yapabilirsiniz.

Bu yeni görünümü oluşturmak için, Office 365 yönetim merkezinde **Kullanıcılar** > **Etkin Kullanıcılar** bölümüne gidin ve **Görünüm Seçin** menüsünde **Yeni Görünüm**'ü seçin. Yeni görünümünüzü adlandırın ve **Atanan lisans** bölümünde **Power BI (ücretsiz)** veya **Power BI Pro** seçeneğini belirleyin. Görünüm başına yalnızca bir lisans seçebilirsiniz. Kuruluşunuzda hem **Power BI (ücretsiz)** hem de **Power BI Pro** lisansları varsa iki görünüm oluşturmanız gerekir. Yeni görünüm oluşturulduktan sonra kiracınızda bu programa kayıtlı olan tüm kullanıcıları görebilirsiniz.

### <a name="are-there-any-additional-things-i-should-be-prepared-for"></a>Hazırlıklı olmam gereken başka şeyler var mı?
Parola sıfırlama isteklerinde bir artış ile karşılaşabilirsiniz. Bu işlem hakkında bilgi almak için bkz. [Bir kullanıcının parolasını sıfırlama](https://support.office.com/article/Reset-a-users-password-7a5d073b-7fae-4aa5-8f96-9ecd041aba9c).

Office 365 yönetim merkezinde standart işlemi uygulayarak kiracınızdan kullanıcı kaldırabilirsiniz. Ancak, kullanıcı kuruluşunuzun etkin bir e-posta adresine sahipse siz tüm kullanıcıların katılımını engellemediğiniz sürece tekrar katılabilir.

### <a name="is-this-free-will-i-be-charged-for-these-licenses"></a>Bu ücretsiz olarak mı sunuluyor? Bu lisanslar için ücret ödemem gerekir mi?
**Power BI (ücretsiz)** lisansları Power BI'ın ücretsiz olan sürümü içindir. Ek özelliklerle ilgileniyorsanız [Power BI Pro sürümüne](service-premium.md) göz atın.

### <a name="where-is-my-power-bi-tenant-located"></a>Power BI kiracım nerede bulunur?
Power BI kiracınızın konumunu (veri bölgesi olarak da bilinir) nasıl bulacağınız hakkında bilgi edinmek için bkz. [Power BI kiracım nerede bulunur?](service-admin-where-is-my-tenant-located.md)

### <a name="what-is-the-power-bi-sla"></a>Power BI SLA'sı nedir?
Power BI SLA'sı (Hizmet Düzeyi Sözleşmesi) hakkında bilgi edinmek için Microsoft Licensing web sitesinin **Licensing** (Lisanslama) bölümündeki [Licensing Terms and Documentation (Lisanslama ile ilgili Koşullar ve Belgeler)](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=37) makalesine başvurun.

## <a name="security-in-power-bi"></a>Power BI'da Güvenlik
### <a name="does-power-bi-meet-national-regional-and-industry-specific-compliance-requirements"></a>Power BI ulusal, bölgesel ve sektöre özel uyumluluk gereksinimlerini karşılıyor mu?
Power BI uyumluluğu hakkında daha fazla bilgi edinmek için bkz. [Microsoft Güven Merkezi](http://go.microsoft.com/fwlink/?LinkId=785324).

### <a name="how-does-security-work-in-power-bi"></a>Power BI'da güvenlik nasıl sağlanır?
Power BI, Office 365 temel alınarak oluşturulmuştur. Office 365'in altyapısında ise Azure Active Directory gibi Azure hizmetleri yer almaktadır. Power BI mimarisine genel bakış için bkz. [Power BI Güvenliği](service-admin-power-bi-security.md). 

## <a name="next-steps"></a>Sonraki adımlar
[Power BI yönetici portalı](service-admin-portal.md)  
[Power BI yönetici rolünü anlama](service-admin-role.md)  
[Power BI için self servis kayıt](service-self-service-signup-for-power-bi.md)  
[Kuruluşunuz için Power BI (ücretsiz)](service-admin-service-free-in-your-organization.md)  
[Power BI Pro'yu satın alma](service-admin-purchasing-power-bi-pro.md)  
[Power BI Premium nedir?](service-premium.md)  
[Power BI Premium'u satın alma](service-admin-premium-purchase.md)  
[Office 365 kullanıcı hesabı yönetimi](https://technet.microsoft.com/library/office-365-user-account-management.aspx)  
[Office 365 grup yönetimi](https://support.office.com/Article/Find-help-about-Groups-in-Office-365-7a9b321f-b76a-4d53-b98b-a2b0b7946de1)  
[Power BI ve Office 365'teki grubunuzu yönetme](service-manage-app-workspace-in-power-bi-and-office-365.md)  
[Power BI Premium teknik incelemesi](https://aka.ms/pbipremiumwhitepaper)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

