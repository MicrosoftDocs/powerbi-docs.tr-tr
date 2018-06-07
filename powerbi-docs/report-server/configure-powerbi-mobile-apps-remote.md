---
title: Uzaktan bir rapora Power BI iOS mobil uygulama erişimini yapılandırma
description: Rapor sunucunuz için uzaktan iOS mobil uygulamaları yapılandırmayı öğrenin.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-report-server
ms.topic: conceptual
ms.date: 05/22/2018
ms.author: maggies
ms.openlocfilehash: bbade67c9510b8d316364d991c09444712309514
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34722190"
---
# <a name="configure-power-bi-ios-mobile-app-access-to-a-report-server-remotely"></a>Uzaktan bir rapora Power BI iOS mobil uygulama erişimini yapılandırma

Bu makalede, kuruluşunuzun MDM aracını kullanarak bir rapor sunucusuna Power BI iOS mobil uygulama erişimini yapılandırma hakkında bilgi edineceksiniz. Bunu ayarlamak için IT yöneticileri, uygulamaya gönderilecek gerekli bilgilerle birlikte bir uygulama yapılandırma ilkesi oluşturur. 

 Daha sonra, rapor sunucusu bağlantısı zaten yapılandırıldığı için Power BI iOS mobil uygulama kullanıcıları kuruluşlarının rapor sunucusuna daha kolay bir şekilde bağlanabilir. 


## <a name="create-the-app-configuration-policy-in-mdm-tool"></a>MDM aracında uygulama yapılandırma ilkesi oluşturma 

Yönetici olarak, Microsoft Intune’da uygulama yapılandırma ilkesi oluşturmak için aşağıdaki adımları izlemeniz gerekir. Uygulama yapılandırma ilkesi oluşturma adımları ve deneyimi diğer MDM araçlarında farklı olabilir. 

1. MDM aracınızı bağlayın. 
2. Yeni bir uygulama yapılandırma ilkesi oluşturun ve adlandırın. 
3. Bu uygulama yapılandırma ilkesinin dağıtılacağı kullanıcıları seçin. 
4. Anahtar-değer çiftleri oluşturun. 

Aşağıdaki tabloda çiftler açıklanmıştır.

|Anahtar  |Tür  |Açıklama  |
|---------|---------|---------|
| com.microsoft.powerbi.mobile.ServerURL | Dize | Rapor Sunucusu URL'si </br> Http/https ile başlamalıdır |
| com.microsoft.powerbi.mobile.ServerUsername | Dize | [isteğe bağlı] </br> Sunucuya bağlanmak için kullanılacak kullanıcı adı. </br> Bir tane yoksa, uygulama kullanıcıdan bağlantı için kullanıcı adı girmesini ister.| 
| com.microsoft.powerbi.mobile.ServerDisplayName | Dize | [isteğe bağlı] </br> Varsayılan değer “Rapor sunucusu” şeklindedir </br> Sunucuyu temsil etmek üzere uygulamada kullanılan kolay ad | 
| com.microsoft.powerbi.mobile.OverrideServerDetails | Boole | True varsayılan değerdir </br> “True” olarak ayarlanırsa mobil cihazda zaten mevcut olan tüm Rapor Sunucusu tanımlarını geçersiz kılar (zaten yapılandırılmış mevcut sunucular silinir). </br> Geçersiz Kılma ayarının True olarak belirlenmesi de kullanıcının bu yapılandırmayı kaldırmasını engeller. </br> “False” olarak ayarlandığında mevcut tüm ayarlar tutulurken gönderilen değerler eklenir. </br> Mobil uygulamada aynı sunucu URL’si zaten yapılandırılmışsa, uygulama bu yapılandırmayı olduğu gibi bırakır ve kullanıcıdan aynı sunucu için yeniden kimlik doğrulamasını istemez. |

Intune kullanarak yapılandırma ilkesini ayarlama örneği aşağıda verilmiştir.

![Intune yapılandırma ayarları](media/configure-powerbi-mobile-apps-remote/power-bi-ios-remote-configuration-settings.png)

## <a name="end-users-connecting-to-a-report-server"></a>Bir rapor sunucusuna bağlanan son kullanıcılar

Uygulama yapılandırma ilkesini yayımladıktan sonra, bu ilke için tanımlanmış dağıtım listesine ait olan kullanıcılar ve cihazlar, Power BI iOS mobil uygulamasını başlattıklarında aşağıdaki deneyimi yaşarlar. 

1. Mobil uygulamalarının bir rapor sunucusu ile yapılandırıldığına dair bir ileti görürler ve **Oturum aç**’a dokunurlar.

    ![Rapor sunucusunda oturum açma](media/configure-powerbi-mobile-apps-remote/power-bi-config-server-sign-in.png)

2.  **Sunucuya bağlan** sayfasında rapor sunucusu ayrıntıları zaten doldurulmuştur. **Bağlan**’a dokunurlar.

    ![Doldurulmuş rapor sunucusu ayrıntıları](media/configure-powerbi-mobile-apps-remote/power-bi-ios-remote-configure-connect-server.png)

3. Kimlik doğrulaması için bir parola girip **Oturum aç**’a dokunurlar. 

    ![Doldurulmuş rapor sunucusu ayrıntıları](media/configure-powerbi-mobile-apps-remote/power-bi-config-server-address.png)

Artık KPI’leri ve rapor sunucusunda depolanmış Power BI raporlarını görüntüleyebilir ve etkileşimde bulunabilirler.

## <a name="next-steps"></a>Sonraki adımlar
[Yönetici genel bakışı](admin-handbook-overview.md)  
[Power BI Rapor Sunucusu'nu yükleme](install-report-server.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)

