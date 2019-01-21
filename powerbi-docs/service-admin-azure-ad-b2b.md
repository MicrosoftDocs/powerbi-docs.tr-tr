---
title: Azure AD B2B ile içerikleri dış konuk kullanıcılara dağıtma
description: Power BI, İşletmeler Arası Azure Active Directory (Azure AD B2B ) ile tümleşerek Power BI içeriklerinin kuruluş dışındaki kullanıcılara güvenli bir şekilde dağıtılmasına olanak sağlar.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 11/02/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 7e76f03a3795976aebd1480dc77a579c9245ed9e
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2019
ms.locfileid: "54282069"
---
# <a name="distribute-power-bi-content-to-external-guest-users-with-azure-ad-b2b"></a>Azure AD B2B ile Power BI içeriklerini dış konuk kullanıcılara dağıtma

Power BI, işletmeler arası Azure Active Directory (Azure AD B2B) ile tümleşerek Power BI içeriklerinin kuruluşunuz dışındaki kullanıcılara güvenli bir şekilde dağıtılmasına olanak sağlar ve bu sırada iç verilerin de denetimini elinde bulundurur.

## <a name="enable-access"></a>Erişimi etkinleştirme

Konuk kullanıcıları davet etmeden önce Power BI yönetici portalında [dışarı aktarma ve paylaşım ayarları](service-admin-portal.md#export-and-sharing-settings) özelliğini etkinleştirdiğinizden emin olun.

## <a name="who-can-you-invite"></a>Kimleri davet edebilirsiniz?

Gmail.com, outlook.com ve hotmail.com gibi kişisel hesaplar da dahil olmak üzere herhangi bir e-posta adresini kullanan konuk kullanıcılar davet edebilirsiniz. Azure AD B2B'de bu adresler *sosyal kimlik* olarak adlandırılır.

## <a name="invite-guest-users"></a>Konuk kullanıcı davet etme

Davetler, yalnızca bir dış konuk kullanıcının kuruluşunuza ilk kez davet edilmesi sırasında gereklidir. Kullanıcıları davet etmek için faydalanabileceğiniz iki yöntem vardır: planlı davetler ve geçici davetler.

### <a name="planned-invites"></a>Planlanmış davetler

Hangi kullanıcıları davet edeceğinizi biliyorsanız planlı davetleri kullanın. Daveti Azure portal veya PowerShell aracılığıyla gönderebilirsiniz. Kişileri davet edebilmek için kiracı yöneticisi olmanız gerekir.

Azure portalda davet göndermek için aşağıdaki adımları izleyin.

1. [Azure portalda](https://portal.azure.com) **Azure Active Directory**'yi seçin.

1. **Yönet** bölümünde **Kullanıcılar** > **Tüm kullanıcılar** > **Yeni konuk kullanıcı** yolunu izleyin.

    ![Azure AD Portalı - Yeni Konuk Kullanıcı](media/service-admin-azure-ad-b2b/azuread-portal-new-guest-user.png)

1. **E-posta adresini** girin ve **kişisel ileti** ekleyin.

    ![Azure AD Portalı - yeni konuk kullanıcı davet mesajı](media/service-admin-azure-ad-b2b/azuread-portal-invite-message.png)

1. **Davet et** seçeneğini belirleyin.

Birden fazla konuk davet etmek için PowerShell'i kullanın. Daha fazla bilgi için bkz. [Azure AD B2B işbirliği kodu ve PowerShell örnekleri](/azure/active-directory/b2b/code-samples/).

Kullanıcının, aldığı e-posta davetindeki **Get Started** (Başlayın) seçeneğini belirlemesi gerekir. Konuk kullanıcı, bu işlemden sonra kiracıya eklenir.

![Konuk kullanıcı e-posta daveti](media/service-admin-azure-ad-b2b/guest-user-invite-email.png)

### <a name="ad-hoc-invites"></a>Geçici davetler

Dilediğiniz zaman davet gerçekleştirmek için dış kullanıcıyı, paylaşım kullanıcı arabirimi aracılığıyla panonuza veya raporunuza ya da erişim sayfası aracılığıyla uygulamanıza ekleyin. Bir uygulamayı kullanması için bir dış kullanıcıyı davet ederken ne yapılacağına ilişkin bir örnek burada verilmiştir.

![Uygulama erişim listesine eklenmiş dış kullanıcı](media/service-admin-azure-ad-b2b/power-bi-app-access.png)

Konuk kullanıcı, uygulamanın kendisiyle paylaşıldığını belirten bir e-posta alır.

![Konuk kullanıcıyla paylaşılan uygulamaya ilişkin e-posta](media/service-admin-azure-ad-b2b/guest-user-invite-email2.png)

Konuk kullanıcının, kuruluşuna ait e-posta adresi ile oturum açması gerekir. Konuk kullanıcı, oturum açtıktan sonra, daveti kabul etmesine yönelik bir istemle karşılaşır. Oturum açma işleminden sonra konuk kullanıcı, uygulama içeriğine yönlendirilir. Uygulamaya dönmek için bağlantıya yer işareti ekleyebilir veya e-postayı kaydedebilir.

## <a name="licensing"></a>Lisanslama

Konuk kullanıcının paylaşılan uygulamayı görüntüleyebilmesi için doğru lisansa sahip olması gerekir. Bunu gerçekleştirmeye yönelik üç seçenek vardır: Power BI Premium'u kullanma, bir Power BI Pro lisansı atama veya konuğun Power BI Pro lisansını kullanma.

### <a name="use-power-bi-premium"></a>Power BI Premium kullanma

Uygulama çalışma alanının [Power BI Premium kapasitesine](service-premium.md) atanması, konuk kullanıcının uygulamayı bir Power BI Pro lisansına ihtiyaç duymadan kullanabilmesine olanak sağlar. Power BI Premium, uygulamaların, artırılmış yenileme sıklığı, ayrılmış kapasite ve büyük model boyutları gibi başka özelliklerden de yararlanmasına izin verir.

![Power BI Premium kullanma](media/service-admin-azure-ad-b2b/license-approach1.png)

### <a name="assign-a-power-bi-pro-license-to-guest-user"></a>Konuk kullanıcıya Power BI Pro lisansı atama

Konuk kullanıcıya kiracınızdaki bir Power BI Pro lisansının atanması, konuk kullanıcının kiracıdaki içeriği görüntülemesine olanak sağlar.

![Kiracınızdaki bir Pro lisansını atama](media/service-admin-azure-ad-b2b/license-approach2.png)

### <a name="guest-user-brings-their-own-power-bi-pro-license"></a>Konuk kullanıcının kendi Power BI Pro lisansına sahip olması

Konuk kullanıcı zaten kendi kiracısında atanmış bir Power BI Pro lisansına sahiptir.

![Konuk kullanıcının kendi lisansına sahip olması](media/service-admin-azure-ad-b2b/license-approach3.png)

## <a name="considerations-and-limitations"></a>Önemli Noktalar ve Sınırlamalar

* Dış B2B konukları, yalnızca içeriğin kullanımıyla sınırlandırılır. Dış B2B konukları uygulamaları, panoları ve raporları görüntüleyebilmenin yanı sıra panolar ile raporlara yönelik olarak verileri dışarı aktarabilir ve e-posta abonelikleri oluşturabilir. Çalışma alanlarına erişemez veya kendi içeriklerini yayımlayamazlar.

* Bu özellik şu anda Power BI mobil uygulamalarıyla kullanılamaz. Mobil cihazlardaki tarayıcılarda, Azure AD B2B kullanılarak paylaşılan Power BI içeriklerini görüntüleyebilirsiniz.

* Bu özellik şu anda Power BI SharePoint Online raporu web bölümüyle kullanılamaz.

## <a name="next-steps"></a>Sonraki adımlar

Satır düzeyi güvenliğin nasıl çalıştığını öğrenmek ve daha ayrıntılı bilgi edinmek için teknik incelemeye göz atın: [Azure AD B2B kullanarak Power BI içeriklerini dış konuk kullanıcılara dağıtma](https://aka.ms/powerbi-b2b-whitepaper).

Azure AD B2B ile ilgili daha fazla bilgi için bkz. [Azure AD B2B işbirliği nedir?](/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b/).
