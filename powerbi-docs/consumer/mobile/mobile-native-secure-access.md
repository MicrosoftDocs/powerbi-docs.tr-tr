---
title: Cihazın yerel kimliğiyle Power BI verilerini koruma
description: Power BI verilerinize erişebilmeniz için ek kimlik bilgileri isteyecek şekilde iOS ve Android uygulamanızı yapılandırmayı öğrenin
author: paulinbar
ms.author: painbar
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: how-to
ms.date: 04/07/2020
ms.openlocfilehash: 9ca31aa16d74ab89b9af374244d2696f77dedac6
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96413070"
---
# <a name="protect-power-bi-app-with-face-id-touch-id-passcode-or-biometric-data"></a>Power BI uygulamasını Face ID, Touch ID, geçiş kodu veya biyometrik verilerle koruma 

Birçok durumda Power BI'da yönetilen veriler gizlidir; bunların korunması ve yalnızca yetkili kullanıcıların bu verilere erişebilmesi gerekir. 

iOS ve Android için Power BI uygulaması ek kimlik bilgileri yapılandırarak verilerinizi korumanıza olanak sağlar. Ardından uygulama her başlatıldığında veya ön plana getirildiğinde, kimlik doğrulaması yapmak gerekecektir. iOS’ta bu Face ID, Touch ID veya geçiş kodu sağlamak anlamına gelir. Android’de ise biyometrik veriler (Parmak İzi Kimliği) sağlamak anlamına gelir.

Aşağıdakiler için geçerlidir:

| ![iPhone](./media/mobile-native-secure-access/ios-logo-40-px.png) | ![iPad'ler](./media/mobile-native-secure-access/ios-logo-40-px.png) | ![Android telefon](././media/mobile-native-secure-access/android-logo-40-px.png) | ![Android tablet](././media/mobile-native-secure-access/android-logo-40-px.png) |
|:--- |:--- |:--- |:--- |
|iPhone'lar |iPad'ler |Android telefonlar |Android tabletler |

## <a name="turn-on-face-id-touch-id-or-passcode-on-ios"></a>iOS’ta Face ID, Touch ID veya geçiş kodunu açma

iOS için Power BI mobil uygulamasında ek kimlik bilgileri kullanmak için **Gizlilik ve Güvenlik**’in altındaki uygulama ayarına gidin. Face ID, Touch ID veya geçiş kodunu açma seçeneğini görürsünüz. Gördüğünüz seçenekler, cihazınızın özelliklerine bağlıdır.

![Power BI iOS uygulama ayarı sayfası](./media/mobile-native-secure-access/mobile-ios-native-secured-setting.png)

Bu ayar açıldıktan sonra, uygulamayı her başlattığınızda veya ön plana getirdiğinizde uygulamaya erişebilmek için kimliğinizi sağlamanız istenir.

Sağlamanız istenilen kimlik türü, cihazınızın özelliklerine bağlıdır. Cihazınız Face ID'yi destekliyorsa Face ID kullanmanız gerekir. Touch ID'yi destekliyorsa Touch ID kullanmanız gerekir. İkisi de desteklenmiyorsa geçiş kodunu sağlamanız gerekir. Aşağıdaki resimde Yüz Kimliği kimlik doğrulaması ekranı gösterilir.

![Power BI iOS Face ID](./media/mobile-native-secure-access/mobile-ios-native-secured-faceid.png)

## <a name="turn-on-biometric-data-fingerprint-id-on-android"></a>Android üzerinde biyometrik verileri (Parmak İzi Kimliği) açma

Android için Power BI mobil uygulamasında ek kimlik bilgileri kullanmak için **Gizlilik ve Güvenlik**’in altındaki uygulama ayarına gidin. Biyometrik verileri açma seçeneğini görürsünüz.

![Power BI Android uygulaması ayar sayfası](./media/mobile-native-secure-access/mobile-android-native-secured-setting.png)

Bu ayar açıldıktan sonra, uygulamayı her başlattığınızda veya ön plana getirdiğinizde uygulamaya erişebilmek için biyometrik verilerinizi (Parmak İzi Kimliği) sağlamanız istenir.

Aşağıdaki resimde parmak izi kimlik doğrulaması ekranı gösterilir.

![Android telefonda Ek kimlik doğrulaması gerekiyor iletisini gösteren ekran görüntüsü.](./media/mobile-native-secure-access/mobile-android-native-secured-fingerprint-id.png)

>[!NOTE]
>Mobil uygulamanın “Biyometrik Kimlik Doğrulaması Gerektir” ayarını kullanabilmek için önce Android cihazınızda biyometrik verileri ayarlamanız gerekir. Cihazınız biyometrik verileri desteklemiyorsa bu mobil uygulama ayarını kullanarak Power BI verilerinize yönelik erişimin güvenliğini sağlayamazsınız.
>
>Yöneticiniz, mobil uygulama için [güvenli erişimi uzaktan açtıysa](#mdm-enforcement-of-secure-access-to-your-power-bi-mobile-app) uygulamaya erişmek için, henüz yapmadıysanız cihazınızda biyometrik verileri ayarlamanız gerekir. Cihazınız biyometrik verileri desteklemiyorsa uzak ayar sizi etkilemez. Mobil uygulamanıza erişim, güvenli olmayan bir şekilde kalır.

## <a name="mdm-enforcement-of-secure-access-to-your-power-bi-mobile-app"></a>Power BI mobil uygulamanıza güvenli erişim için MDM’yi zorunlu kılma.

Bazı kuruluşların güvenlik ilkeleri ve uyumluluk gereksinimleri gizli iş verilerine erişebilmeniz için ek kimlik bilgileri girmenizi zorunlu tutar.

Bunu desteklemek için, Power BI mobil uygulaması yöneticilerin Microsoft Intune’dan ve diğer mobil cihaz yönetimi (MDM) çözümlerinden uygulama yapılandırma ayarlarını göndererek mobil uygulama güvenli erişim ayarını denetlemelerine olanak tanır. Yöneticiler uygulama koruma ilkesini kullanarak bu ayarı tüm kullanıcılar için veya bir grup kullanıcı için açabilir. Ayrıntılar için bkz. [Power BI mobil uygulamasını uzaktan yapılandırmak için MDM’yi kullanma](mobile-app-configuration.md#data-protection-settings-ios-and-android).

## <a name="next-steps"></a>Sonraki adımlar
* [MDM kullanarak Power BI mobil uygulamasını uzaktan yapılandırma](mobile-app-configuration.md)
