---
title: Azure AD B2B ile içerikleri dış konuk kullanıcılara dağıtma
description: Power BI, İşletmeler Arası Azure Active Directory (Azure AD B2B) aracılığıyla dış konuk kullanıcılarla içerik paylaşma imkanı sunar.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 09/09/2019
ms.author: kfollis
LocalizationGroup: Administration
ms.openlocfilehash: 25b136bfa15b00333400b80781d968d0b40d9779
ms.sourcegitcommit: a72567f26c1653c25f7730fab6210cd011343707
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83564524"
---
# <a name="distribute-power-bi-content-to-external-guest-users-with-azure-ad-b2b"></a>Azure AD B2B ile Power BI içeriklerini dış konuk kullanıcılara dağıtma

Power BI, İşletmeler Arası Azure Active Directory (Azure AD B2B) aracılığıyla dış konuk kullanıcılarla içerik paylaşma imkanı sunar.
Kuruluşunuz Azure AD B2B'yi kullanarak dış kullanıcılarla paylaşım yapılmasını tek bir yerden etkinleştirir ve yönetir. Dış kullanıcılar varsayılan olarak yalnızca tüketim izinlerine sahiptir. Ayrıca, kuruluşunuzun dışından konuk kullanıcılara kuruluşta bulunan içeriği düzenleme ve yönetme izni verebilirsiniz.

Bu makalede Power BI'da Azure AD B2B'ye temel giriş bilgileri sağlanır. Daha fazla bilgi için bkz. [Azure Active Directory B2B'yi kullanarak Power BI içeriğini dış konuk kullanıcılara dağıtma](../guidance/whitepaper-azure-b2b-power-bi.md).

## <a name="enable-access"></a>Erişimi etkinleştirme

Konuk kullanıcıları davet etmeden önce Power BI yönetim portalında [Dış kullanıcılarla içerik paylaşma](service-admin-portal.md#export-and-sharing-settings) özelliğini etkinleştirdiğinizden emin olun. Bu seçenek etkinleştirildiğinde bile kullanıcının konuk kullanıcılar davet edebilmek için Azure Active Directory’de izni olması gerekir ve bu izin Konuk Davet Eden rolü aracılığıyla verilir. 

[Harici konuk kullanıcıların kuruluş içeriklerini düzenlemelerine ve yönetmelerine izin ver](service-admin-portal.md#allow-external-guest-users-to-edit-and-manage-content-in-the-organization) seçeneği, konuk kullanıcılara çalışma alanlarındaki içeriği görme ve oluşturma imkanı tanımanızı sağlar ve kuruluşunuzun Power BI'ına göz atmak da buna dahildir.

> [!NOTE]
> [Dış kullanıcılarla içerik paylaşma](service-admin-portal.md#export-and-sharing-settings) ayarı, Power BI'ın kuruluşunuza dış kullanıcı davet edilmesine izin verip vermeyeceğini denetler. Daveti kabul eden dış kullanıcı kuruluşunuzda Azure AD B2B konuk kullanıcısı olur. Power BI deneyiminin her tarafındaki kişi seçicilerde bu kullanıcılar gösterilir. Ayar devre dışı bırakıldığında kuruluşunuzdaki mevcut konuk kullanıcılar erişim sahibi oldukları tüm öğelere erişmeye ve kişi seçici deneyimlerinde listelenmeye devam eder. Buna ek olarak, [planlanmış davet](#planned-invites) yaklaşımıyla eklenen konuklar da kişi seçicilerde gösterilir. Konuk kullanıcıların Power BI’a erişimini engellemek için Azure AD koşullu erişim ilkesi kullanın.

## <a name="who-can-you-invite"></a>Kimleri davet edebilirsiniz?

Gmail.com, outlook.com ve hotmail.com gibi kişisel hesaplar da dahil olmak üzere çoğu e-posta adresini kullanan konuk kullanıcılar kuruluşunuza davet edilebilir. Azure AD B2B'de bu adresler *sosyal kimlik* olarak adlandırılır.

[Power BI for US Government](service-govus-overview.md) gibi kamu bulutuyla ilişkilendirilmiş kullanıcıları davet edemezsiniz.

## <a name="invite-guest-users"></a>Konuk kullanıcı davet etme

Konuk kullanıcıları kuruluşunuza davet ederken ilk seferinde davet göndermeniz yeterlidir. Kullanıcıları davet etmek için planlı veya geçici davetleri kullanın.

Geçici davetleri kullanmak için aşağıdaki özellikleri kullanın:
* Rapor ve Pano paylaşımı
* Uygulama erişimi listesi

Geçici davetler, çalışma alanı erişim listeleri için desteklenmez. Bu kullanıcıları kuruluşunuza eklemek için [planlanmış davetler yaklaşımını](#planned-invites) kullanın. Dış kullanıcı kuruluşunuza bir konuk olarak dahil olduktan sonra çalışma alanı erişim listesine ekleyin.

### <a name="planned-invites"></a>Planlanmış davetler

Hangi kullanıcıları davet edeceğinizi biliyorsanız planlı davetleri kullanın. Azure portalı veya PowerShell aracılığıyla davet gönderebilirsiniz. Kişileri davet edebilmek için kiracı yöneticisi olmanız gerekir.

Azure portalda davet göndermek için aşağıdaki adımları izleyin.

1. [Azure portalda](https://portal.azure.com)**Azure Active Directory**'yi seçin.

1. **Yönet** bölümünde **Kullanıcılar** > **Tüm kullanıcılar** > **Yeni konuk kullanıcı**'yı seçin.

    ![Yeni konuk kullanıcı seçeneği gösterilen Azure portalının ekran görüntüsü.](media/service-admin-azure-ad-b2b/azure-ad-portal-new-guest-user.png)

1. **E-posta adresini** girin ve **kişisel ileti** ekleyin.

    ![Azure AD Portalı Yeni Konuk Kullanıcı iletişim kutusunun ekran görüntüsü.](media/service-admin-azure-ad-b2b/azure-ad-portal-invite-message.png)

1. **Davet et** seçeneğini belirleyin.

Birden fazla konuk davet etmek için PowerShell'i kullanın. Daha fazla bilgi için bkz. [Azure AD B2B işbirliği kodu ve PowerShell örnekleri](/azure/active-directory/b2b/code-samples/).

Kullanıcının, aldığı e-posta davetindeki **Get Started** (Başlayın) seçeneğini belirlemesi gerekir. Konuk kullanıcı, bu işlemden sonra kiracıya eklenir.

![Konuk kullanıcı e-posta davetinin ekran görüntüsü.](media/service-admin-azure-ad-b2b/guest-user-invite-email.png)

### <a name="ad-hoc-invites"></a>Geçici davetler

Dilediğiniz zaman dış kullanıcıyı davet etmek için, onu paylaşım kullanıcı arabirimi aracılığıyla panonuza veya raporunuza ya da erişim sayfası aracılığıyla uygulamanıza ekleyin. Bir uygulamayı kullanması için bir dış kullanıcıyı davet ederken ne yapılacağına ilişkin bir örnek burada verilmiştir.

![Power BI'da Uygulama erişim listesine eklenen Dış kullanıcının ekran görüntüsü.](media/service-admin-azure-ad-b2b/power-bi-app-access.png)

Konuk kullanıcı, uygulamayı kendisiyle paylaştığınızı belirten bir e-posta alır.

![Konuk kullanıcıyla paylaşılan uygulamaya ilişkin e-postanın ekran görüntüsü](media/service-admin-azure-ad-b2b/guest-user-invite-email-2.png)

Konuk kullanıcının, kuruluşuna ait e-posta adresi ile oturum açması gerekir. Oturum açtıktan sonra daveti kabul etmesine yönelik bir istem alır. Oturum açma işleminden sonra konuk kullanıcı için uygulama açılır. Kullanıcının uygulamaya dönmek için bağlantıya yer işareti eklemesi veya e-postayı kaydetmesi gerekir.


## <a name="licensing"></a>Lisanslama

Paylaştığınız içeriği görüntüleyebilmesi için konuk kullanıcının düzgün lisansa sahip olması gerekir. Kullanıcının düzgün lisansı olduğundan emin olmanın üç yolu vardır: Power BI Premium'u kullanma, bir Power BI Pro lisansı atama veya konuğun Power BI Pro lisansını kullanma.

[Kuruluştaki içeriği düzenleyebilen ve yönetebilen konuk kullanıcıların](service-admin-portal.md#allow-external-guest-users-to-edit-and-manage-content-in-the-organization) çalışma alanlarına içerik eklemek veya içeriği başkalarıyla paylaşmak için Power BI Pro lisansına sahip olması gerekir.

### <a name="use-power-bi-premium"></a>Power BI Premium kullanma

Çalışma alanının [Power BI Premium kapasitesine](service-premium-what-is.md) atanması, konuk kullanıcının uygulamayı bir Power BI Pro lisansına ihtiyaç duymadan kullanabilmesine olanak sağlar. Power BI Premium uygulamaların artırılmış yenileme sıklığı, ayrılmış kapasite ve büyük model boyutları gibi başka özelliklerden de yararlanmasına izin verir.

![Power BI Premium ile konuk kullanıcı deneyiminin diyagramı.](media/service-admin-azure-ad-b2b/license-approach-1.png)

### <a name="assign-a-power-bi-pro-license-to-guest-user"></a>Konuk kullanıcıya Power BI Pro lisansı atama

Konuk kullanıcıya kiracınızdaki bir Power BI Pro lisansının atanması, konuk kullanıcının kiracıdaki içeriği görüntülemesine olanak sağlar. Lisansları atama hakkında daha fazla bilgi için bkz. [Lisanslar sayfasında kullanıcılara lisans atama](/office365/admin/manage/assign-licenses-to-users#assign-licenses-to-users-on-the-licenses-page). Konuk kullanıcılara Pro lisansları atamadan önce, Microsoft'la aranızdaki sözleşmenin koşullarına uyduğunuzdan emin olmak için Microsoft hesap temsilcinize ulaşın.

![Kiracınızdaki bir Pro lisansını atama ile konuk kullanıcı deneyiminin grafiği.](media/service-admin-azure-ad-b2b/license-approach-2.png)

### <a name="guest-user-brings-their-own-power-bi-pro-license"></a>Konuk kullanıcının kendi Power BI Pro lisansına sahip olması

Konuk kullanıcı zaten kendi kiracısında atanmış bir Power BI Pro lisansına sahiptir.

![Kendi lisansını getiren kullanıcılarla konuk kullanıcı deneyiminin diyagramı.](media/service-admin-azure-ad-b2b/license-approach-3.png)

## <a name="guest-users-who-can-edit-and-manage-content"></a>İçeriği düzenleyebilen ve yönetebilen konuk kullanıcılar

[Harici konuk kullanıcıların kuruluş içeriklerini düzenlemelerine ve yönetmelerine izin ver](service-admin-portal.md#allow-external-guest-users-to-edit-and-manage-content-in-the-organization) özelliğini kullanırken, belirtilen konuk kullanıcılar kuruluşunuzun Power BI'ına ek erişim elde eder. İzin verilen konuklar izne sahip oldukları içeriği görebilir, Giriş'e erişebilir, çalışma alanlarına göz atabilir, uygulamaları yükleyebilir, erişim listesinde bulundukları yeri görebilir ve çalışma alanları içeriğine katkıda bulunabilir. Yeni çalışma alanı deneyiminin kullanıldığı çalışma alanları oluşturabilir ve bu çalışma alanlarının Yöneticisi olabilir. Bazı sınırlamalar geçerlidir. Önemli Noktalar ve Sınırlamalar bölümünde bu kısıtlamalar listelenir.
 
İzin verilen konukların Power BI'da oturum açmalarına yardımcı olmak için onlara Kiracı URL'sini sağlayın. Kiracı URL'sini bulmak için şu adımları izleyin.

1. Power BI hizmetinde üst taraftaki menüden yardım simgesini ( **?** ) ve ardından **Power BI Hakkında**'yı seçin.

2. **Kiracı URL'si** öğesinin yanındaki değere bakın. Kiracı URL'nizi izin verilen konuk kullanıcılarınızla paylaşın.

    ![Konuk kullanıcı kiracı URL'sinin gösterildiği Power BI Hakkında iletişim kutusunun ekran görüntüsü.](media/service-admin-azure-ad-b2b/power-bi-about-dialog.png)

## <a name="considerations-and-limitations"></a>Önemli Noktalar ve Sınırlamalar

* Varsayılan olarak, dış Azure AD B2B konukları yalnızca içeriğin tüketimiyle sınırlandırır. Dış Azure AD B2B konukları uygulamaları, panoları ve raporları görüntüleyebilmenin yanı sıra panolar ile raporlara yönelik olarak verileri dışarı aktarabilir ve e-posta abonelikleri oluşturabilir. Çalışma alanlarına erişemez veya kendi içeriklerini yayımlayamazlar. Bu kısıtlamaları kaldırmak için [Harici konuk kullanıcıların kuruluş içeriklerini düzenlemelerine ve yönetmelerine izin ver](service-admin-portal.md#allow-external-guest-users-to-edit-and-manage-content-in-the-organization) özelliğini kullanabilirsiniz.

* Konuk kullanıcıları davet etmek için bir Power BI Pro lisansı gerekir. Pro Deneme kullanıcıları Power BI’da konuk kullanıcı davet edemez.

* Bazı deneyimler [kuruluştaki içeriği düzenleyebilen ve yönetebilen konuk kullanıcılar](service-admin-portal.md#allow-external-guest-users-to-edit-and-manage-content-in-the-organization) tarafından kullanılamaz. Raporları güncelleştirmek veya yayımlamak için, Power BI Desktop dosyalarını karşıya yüklerken Veri Al'ı kullanmak da dahil olmak üzere Power BI hizmeti web kullanıcı arabirimini kullanmaları gerekir.  Aşağıdaki deneyimler desteklenmez:
    * Power BI Desktop'tan Power BI hizmetine doğrudan yayımlama
    * Konuk kullanıcılar Power BI hizmetindeki hizmet veri kümelerine bağlanmak için Power BI Desktop kullanamaz
    * Microsoft 365 Gruplarına bağlanan klasik çalışma alanları:
        * Konuk kullanıcılar bu çalışma alanlarını oluşturamaz ve bunların Yöneticisi olamaz
        * Konuk kullanıcılar üye olabilir
    * Çalışma alanı erişim listeleri için geçici davet gönderme desteklenmez
    * Konuk kullanıcılarda Excel için Power BI Publisher desteklenmez
    * Konuk kullanıcılar Power BI Gateway yükleyemez ve bunu kuruluşunuza bağlayamaz
    * Konuk kullanıcılar kuruluşun tamamına yayımlayan uygulamalar yükleyemez
    * Konuk kullanıcılar kurumsal içerik paketlerini kullanamaz, oluşturamaz, güncelleştiremez veya yükleyemez
    * Konuk kullanıcılar Excel'de Çözümle özelliğini kullanamaz
    * Konuk kullanıcılar yorumlarda @mentioned olarak yer alamaz
    * Konuk kullanıcılar abonelikleri kullanamaz
    * Bu özelliği kullanan konuk kullanıcıların iş veya okul hesabı olmalıdır. 
    
* Kişisel hesaplarını kullanan konuk kullanıcılar oturum açma kısıtlamalarından kaynaklanan daha fazla sınırlamayla karşılaşır.
    * Power BI hizmetindeki tüketim deneyimlerini bir web tarayıcısı aracılığıyla kullanabilirler
    * Power BI Mobil uygulamalarını kullanamazlar.
    * Bir iş veya okul hesabının gerekli olduğu durumda kimlik bilgilerini sağlamak üzere oturum açamazlar.

* Bu özellik şu anda Power BI SharePoint Online raporu web bölümüyle kullanılamaz.

* Dış konuk kullanıcıların kuruluşunuz genelinde yapabileceklerini sınırlayabilen Active Directory Ayarları vardır. Bunlar Power BI ortamınıza da uygulanır. Aşağıdaki belgelerde bu ayarlar açıklanır:
    * [Dış İşbirliği Ayarlarını Yönetme](/azure/active-directory/b2b/delegate-invitations#configure-b2b-external-collaboration-settings)
    * [Belirli kuruluşlardan B2B kullanıcılarına gönderilen davetlere izin verme veya engelleme](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)
    * [Konuk kullanıcıların Power BI hizmetine erişmesine izin verme veya bunu engelleme](/azure/active-directory/conditional-access/overview)
    
* Kuruluşunuzun dışıyla paylaşım, ulusal bulutlarda desteklenmez. Bunun yerine kuruluşunuzda dış kullanıcıların içeriğe erişmek için kullanabilecekleri kullanıcı hesapları oluşturun. 

* Doğrudan bir konuk kullanıcıyla paylaşım yaptığınızda Power BI onlara bağlantı içeren bir e-posta gönderir. E-posta gönderilmesini önlemek için konuk kullanıcıyı bir güvenlik grubuna ekleyin ve güvenlik grubu ile paylaşım yapın.  

## <a name="next-steps"></a>Sonraki adımlar

Satır düzeyi güvenliğin nasıl çalıştığını öğrenmek ve daha ayrıntılı bilgi edinmek için teknik incelemeyi gözden geçirin: [Azure AD B2B kullanarak Power BI içeriklerini dış konuk kullanıcılara dağıtma](https://aka.ms/powerbi-b2b-whitepaper).

Azure AD B2B hakkında daha fazla bilgi için bkz. [Azure AD B2B işbirliği nedir?](/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b/).