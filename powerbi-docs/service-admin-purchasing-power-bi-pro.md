---
title: Power BI Pro lisanslarını satın alma ve atama
description: Kullanıcılarınızın Power BI hizmetindeki içeriğe erişebilmesi ve iş arkadaşlarıyla işbirliği yapabilmesi için Power BI Pro lisansları satın alma ve atama hakkında bilgi edinin.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: quickstart
ms.date: 10/29/2019
ms.author: kfollis
LocalizationGroup: Administration
ms.openlocfilehash: ebaf32bbf84dcbb8efd8516fd0a1ab01011f2d63
ms.sourcegitcommit: f77b24a8a588605f005c9bb1fdad864955885718
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2019
ms.locfileid: "74698498"
---
# <a name="purchase-and-assign-power-bi-pro-user-licenses"></a>Power BI Pro kullanıcı lisansları satın alma ve atama

Power BI Pro, kullanıcıların Power BI hizmetinde diğer kullanıcılar tarafından yayımlanmış raporları ve panoları okuyup etkileşimde bulunmasına ve diğer Power BI Pro kullanıcılarıyla içerik paylaşıp işbirliği yapmasına olanak tanıyan bireysel bir kullanıcı lisansıdır. Yalnızca Power BI Pro kullanıcı lisansı olan kullanıcılar içerik yayımlayabilir veya diğer kullanıcılarla içerik paylaşabilir ya da içerik bir Power BI Premium kapasitesinde barındırılmadığı sürece diğer kullanıcılar tarafından oluşturulan içeriği tüketebilir. Daha fazla bilgi için bkz. [Lisans türüne göre Power BI özellikleri](service-features-license-type.md).

## <a name="purchase-and-assign-power-bi-pro-user-licenses"></a>Power BI Pro kullanıcı lisansları satın alma ve atama

Bu makalede, Microsoft 365 yönetim merkezinde Power BI Pro kullanıcı lisansları satın alma işlemi ve daha sonra yöneticilerin bu lisansları tekil kullanıcılara atamak için sahip olduğu iki seçenek açıklanmaktadır: Microsoft 365 yönetim merkezi ve Azure portalı (bir seçenek belirleyin).

### <a name="prerequisites"></a>Önkoşullar

Microsoft 365 yönetim merkezinde lisans satın alıp atamak için Microsoft 365’te **[Genel yönetici veya Faturalama yöneticisi](https://support.office.com/article/about-office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)** rolünün üyesi olmanız gerekir.

Azure portalında lisansları atamak için, Power BI'ın Azure Active Directory aramalarında kullandığı Azure aboneliğinin sahibi olmanız gerekir.

### <a name="purchase-licenses-in-microsoft-365"></a>Microsoft 365’te lisans satın alma

Microsoft 365 yönetim merkezinde Power BI Pro lisansları satın almak için şu adımları izleyin:

1. [Microsoft 365 yönetim merkezini](https://portal.office.com/adminportal/home#/homepage) açın.

2. Gezinti bölmesinde **Faturalama** > **Abonelikler**'i seçin.

    ![Gezinti bölmesi](media/service-admin-purchasing-power-bi-pro/service-purchasing-power-bi-pro-01.png)

3. **Abonelikler** sayfasının sağ üst köşesindeki **Abonelik ekle** öğesini seçin.

    ![Abonelik](media/service-admin-purchasing-power-bi-pro/service-purchasing-power-bi-pro-02.png)

4. İstediğiniz abonelik teklifini bulun:

    **Kurumsal Paket** bölümünde **Office 365 Kurumsal E5**’i seçin.

    ![Office E5 aboneliği](media/service-admin-purchasing-power-bi-pro/service-purchasing-power-bi-pro-03.png)

    **Diğer Planlar** bölümünde **Power BI Pro**’yu seçin.

    ![Power BI aboneliği](media/service-admin-purchasing-power-bi-pro/service-purchasing-power-bi-pro-04.png)

5. İstediğiniz abonelik için üç noktanın ( **. . .** ) üzerine imleci getirin ve **Şimdi satın al**’ı seçin.

    ![Şimdi Satın Al](media/service-admin-purchasing-power-bi-pro/service-purchasing-power-bi-pro-05.png)

6. Faturalama tercihinize göre **Aylık ödeme** veya **Tam yıllık ödeme** seçeneğini belirleyin.

7. **Kaç tane kullanıcı istiyorsunuz?** bölümüne istediğiniz lisans sayısını girin ve işlemi tamamlamak için **Şimdi kullanıma al**’ı seçin.

8. Satın alınan aboneliğin şimdi **Abonelikler** sayfasında listelendiğini doğrulayın.

   ![Alınan abonelik](media/service-admin-purchasing-power-bi-pro/service-purchasing-power-bi-pro-06.png)

9. İlk satın alma sonrasında daha fazla lisans eklemek için **Abonelikler** sayfasından **Power BI Pro**’yu ve sonra **Lisans Ekle/Kaldır**’ı seçin.

### <a name="assign-licenses-in-the-microsoft-365-admin-center"></a>Microsoft 365 yönetim merkezinde lisans atama

Bireysel kullanıcı hesaplarına Power BI Pro lisansları atamak için şu adımları izleyin:

1. [Microsoft 365 yönetim merkezini](https://portal.office.com/adminportal/home#/homepage) açın.

2. Gezinti bölmesinde **Kullanıcılar**’ı genişletin ve sonra **Etkin kullanıcılar**’ı seçin.

    ![Etkin kullanıcılar](media/service-admin-purchasing-power-bi-pro/service-assigning-power-bi-pro-licenses-05.png)

3. Bir kullanıcı seçin, ardından **Ürün lisansları** altında **Düzenle**’yi seçin.

    ![Ürün lisanslarını düzenleme](media/service-admin-purchasing-power-bi-pro/service-assigning-power-bi-pro-licenses-06.png)

4. **Power BI Pro** altında ayarı **Açık** duruma getirin, ardından **Kaydet**’i seçin.

    ![Ürün lisansları açık](media/service-admin-purchasing-power-bi-pro/service-assigning-power-bi-pro-licenses-07.png)

5. Seçilen hesabın **Durum** bölümünde Power BI Pro lisansının başarıyla atandığını doğrulayın.

    ![Lisans durumunu doğrulama](media/service-admin-purchasing-power-bi-pro/service-assigning-power-bi-pro-licenses-08.png)

### <a name="assign-licenses-in-the-azure-portal"></a>Azure portalında lisans atama

Bireysel kullanıcı hesaplarına Power BI Pro lisansları atamak için şu adımları izleyin:

1. [Azure portalını](https://ms.portal.azure.com/#@microsoft.onmicrosoft.com/dashboard/private/39bc3cf7-31a4-43f6-954c-f2d69ca2f0) açın.

2. Gezinti bölmesinde **Azure Active Directory**'yi seçin.

    ![Azure Active Directory](media/service-admin-purchasing-power-bi-pro/service-assigning-power-bi-pro-licenses-01.png)

3. **Azure Active Directory** altında **Lisanslar**’ı seçin.

    ![Lisanslar](media/service-admin-purchasing-power-bi-pro/service-assigning-power-bi-pro-licenses-02.png)

4. **Lisanslar** altında **Tüm ürünler**’i, ardından **Power BI Pro**’yu seçerek lisanslı kullanıcıların listesini görüntüleyin.

    ![Lisanslar - tüm ürünler](media/service-admin-purchasing-power-bi-pro/service-assigning-power-bi-pro-licenses-03.png)

5. Bir kullanıcı hesabına Power BI Pro lisansı eklemek için **Ata**’yı seçin.

    ![Lisans atama](media/service-admin-purchasing-power-bi-pro/service-assigning-power-bi-pro-licenses-04.png)

## <a name="next-steps"></a>Sonraki adımlar

Lisansları atadıktan sonra Power BI Pro hakkında daha fazla bilgi edinebilirsiniz.

[Kuruluşunuzda Power BI lisansları](service-admin-licensing-organization.md)

[Oturum açmış Power BI kullanıcılarını bulma](service-admin-access-usage.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
