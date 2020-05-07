---
title: Rapor Sunucusuna yönelik uzaktan mobil uygulama erişimini yapılandırma
description: Rapor sunucunuz için uzaktan mobil uygulamaları yapılandırmayı öğrenin.
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 11/07/2019
ms.author: painbar
ms.openlocfilehash: b84d7a23cf947b18302c761ff5f78143bf3356aa
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "73925872"
---
# <a name="configure-power-bi-mobile-app-access-to-report-server-remotely"></a>Power BI mobil uygulamasının Rapor Sunucusu’na erişimini uzaktan yapılandırma

Aşağıdakiler için geçerlidir:

| ![iPhone](./media/configure-powerbi-mobile-apps-remote/ios-logo-40-px.png) | ![Android telefon](./media/configure-powerbi-mobile-apps-remote/android-logo-40-px.png) |
|:--- |:--- |
| iOS |Android |

Bu makalede, kuruluşunuzun MDM aracını kullanarak Rapor Sunucusuna Power BI mobil uygulama erişimini yapılandırma hakkında bilgi edineceksiniz. IT yöneticileri, bunu yapılandırmak için uygulamaya gönderilecek gerekli bilgilerle birlikte bir uygulama yapılandırma ilkesi oluşturur. 

 Rapor Sunucusu bağlantısı zaten yapılandırıldığından Power BI mobil uygulama kullanıcıları kuruluşlarının Rapor Sunucusuna daha kolay bir şekilde bağlanabilir. 

## <a name="create-the-app-configuration-policy-in-mdm-tool"></a>MDM aracında uygulama yapılandırma ilkesi oluşturma 

Yönetici olarak, Microsoft Intune’da uygulama yapılandırma ilkesi oluşturmak için aşağıdaki adımları izlemeniz gerekir. Uygulama yapılandırma ilkesi oluşturma adımları ve deneyimi diğer MDM araçlarında farklı olabilir. 

1. MDM aracınızı bağlayın. 
2. Yeni bir uygulama yapılandırma ilkesi oluşturun ve adlandırın. 
3. Bu uygulama yapılandırma ilkesinin dağıtılacağı kullanıcıları seçin. 
4. Anahtar-değer çiftleri oluşturun. 

Aşağıdaki tabloda çiftler açıklanmıştır.

|Anahtar  |Tür  |Açıklama  |
|---------|---------|---------|
| com.microsoft.powerbi.mobile.ServerURL | Dize | Rapor Sunucusu URL'si <br> Http/https ile başlamalıdır |
| com.microsoft.powerbi.mobile.ServerUsername | Dize | [isteğe bağlı] <br> Sunucuya bağlanmak için kullanılacak kullanıcı adı. <br> Bir tane yoksa, uygulama kullanıcıdan bağlantı için kullanıcı adı girmesini ister.| 
| com.microsoft.powerbi.mobile.ServerDisplayName | Dize | [isteğe bağlı] <br> Varsayılan değer “Rapor sunucusu” şeklindedir <br> Sunucuyu temsil etmek üzere uygulamada kullanılan kolay ad | 
| com.microsoft.powerbi.mobile.OverrideServerDetails | Boole | True varsayılan değerdir <br>“True” olarak ayarlanırsa mobil cihazda zaten mevcut olan tüm Rapor Sunucusu tanımlarını geçersiz kılar. Önceden yapılandırılmış olan sunucular silinir. <br> Geçersiz Kılma ayarının True olarak belirlenmesi de kullanıcının bu yapılandırmayı kaldırmasını engeller. <br> “False” olarak ayarlandığında mevcut tüm ayarlar tutulurken gönderilen değerler eklenir. <br> Mobil uygulamada aynı sunucu URL’si zaten yapılandırılmışsa, uygulama bu yapılandırmayı olduğu gibi bırakır. Uygulama, kullanıcıdan aynı sunucu için yeniden kimlik doğrulamasını istemez. |

Intune kullanarak yapılandırma ilkesini ayarlama örneği aşağıda verilmiştir.

![Intune yapılandırma ayarları](media/configure-powerbi-mobile-apps-remote/power-bi-ios-remote-configuration-settings.png)

## <a name="end-users-connecting-to-report-server"></a>Rapor Sunucusuna bağlanan son kullanıcılar

 Uygulama yapılandırma ilkesini bir dağıtım listesi için yayımladığınızı düşünelim. Bu dağıtım listesine ait olan kullanıcılar ve cihazlar, mobil uygulamasını başlattıklarında aşağıdaki deneyimi yaşarlar. 

1. Mobil uygulamalarının Rapor Sunucusu ile yapılandırıldığına dair bir ileti görürler ve **Oturum aç**’a dokunurlar.

    ![Rapor sunucusunda oturum açma](media/configure-powerbi-mobile-apps-remote/power-bi-config-server-sign-in.png)

2.  **Sunucuya bağlan** sayfasında rapor sunucusu ayrıntıları zaten doldurulmuştur. **Bağlan**’a dokunurlar.

    ![Doldurulmuş rapor sunucusu ayrıntıları](media/configure-powerbi-mobile-apps-remote/power-bi-ios-remote-configure-connect-server.png)

3. Kimlik doğrulaması için bir parola girip **Oturum aç**’a dokunurlar. 

    ![Doldurulmuş rapor sunucusu ayrıntıları](media/configure-powerbi-mobile-apps-remote/power-bi-config-server-address.png)

Artık KPI’leri ve Rapor Sunucusunda depolanmış Power BI raporlarını görüntüleyebilir ve etkileşimde bulunabilirler.

## <a name="next-steps"></a>Sonraki adımlar

- [Azure AD Uygulama Ara Sunucusu ile Power BI Mobil’e uzaktan erişimi etkinleştirme](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-integrate-with-power-bi)
- [Yönetici genel bakışı](admin-handbook-overview.md)  
- [Power BI Rapor Sunucusu'nu yükleme](install-report-server.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)

