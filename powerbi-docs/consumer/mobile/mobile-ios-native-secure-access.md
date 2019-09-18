---
title: Cihazın yerel kimliğiyle Power BI verilerini koruma
description: Power BI verilerinize erişebilmeniz için ek kimlik bilgileri isteyecek şekilde iOS uygulamanızı yapılandırmayı öğrenin
author: mshenhav
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 06/07/2019
ms.author: mshenhav
ms.openlocfilehash: b7418c9579a439a18a30a967947c15d58693fd44
ms.sourcegitcommit: 52aa112ac9194f4bb62b0910c4a1be80e1bf1276
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2019
ms.locfileid: "66816835"
---
# <a name="protect-power-bi-app-with-face-id-touch-id-or-passcode"></a>Power BI uygulamasını Face ID, Touch ID veya geçiş koduyla koruma 

Birçok durumda Power BI'da yönetilen veriler gizlidir; bunların korunması ve yalnızca yetkili kullanıcıların bu verilere erişebilmesi gerekir. 

Power BI iOS uygulaması ek kimlik bilgileri yapılandırarak verilerinizi korumanıza olanak sağlar. Uygulamayı her başlattığınızda veya arka plandan ön plana getirdiğinizde Face ID, Touch ID veya geçiş kodu sağlamanız gerekir.

| ![iPhone](./media/tutorial-mobile-apps-ios-qna/iphone-logo-50-px.png) | ![iPad](./media/tutorial-mobile-apps-ios-qna/ipad-logo-50-px.png) |
|:--- |:--- |
| iPhone'lar |iPad'ler |

## <a name="turn-on-face-id-touch-id-or-passcode-in-app-setting"></a>Uygulama ayarında Face ID, Touch ID veya geçiş kodunu açma

Power BI'da ek kimlik bilgileri kullanmak için **Gizlilik ve Güvenlik**'in altındaki uygulama ayarına gidin. Cihazınızın özelliklerine bağlı olarak Face ID, Touch ID veya geçiş kodunu açma seçeneğini görürsünüz.

![Power BI iOS uygulama ayarı sayfası](./media/mobile-ios-native-secure-access/mobile-ios-native-secured-setting.png)

Bu ayar açıldıktan sonra, Power BI'ı her başlattığınızda veya arka plandan ön plana getirdiğinizde uygulamaya erişebilmek için kimliğinizi sağlamanız istenir. 

Face ID, Touch ID veya geçiş kodu isteme kararı, cihazın özelliklerine bağlı olarak iOS tarafından verilir. Cihazınız Face ID'yi destekliyorsa Face ID kullanmanız gerekir. Touch ID'yi destekliyorsa Touch ID kullanmanız gerekir. İkisi de desteklenmiyorsa geçiş kodunu sağlamanız gerekir.

![Power BI iOS Face ID](./media/mobile-ios-native-secure-access/mobile-ios-native-secured-faceid.png)

## <a name="use-mdm-to-enforce-face-id-touch-id-or-passcode"></a>Face ID, Touch ID veya geçiş kodunu zorunlu tutmak için MDM kullanma

Bazı kuruluşların güvenlik ilkeleri ve uyumluluk gereksinimleri gizli iş verilerine erişebilmeniz için ek kimlik bilgileri girmenizi zorunlu tutar. 

Power BI mobil iOS uygulaması yöneticilerin Microsoft Intune'dan ve diğer mobil cihaz yönetimi (MDM) çözümlerinden uygulama yapılandırma ayarlarını göndererek bu ayarı denetlemelerine olanak tanır. Yöneticiler uygulama koruma ilkesini kullanarak bu ayarı tüm kullanıcılar için veya bir grup kullanıcı için açabilir.

|Anahtar  |Tür  |Açıklama  |
|---------|---------|---------|
| com.microsoft.powerbi.mobile.ForceDeviceAuthentication | Boole | Varsayılan değerdir False’tur. <br>True olarak ayarlandığında, uygulama kullanıcıları uygulamada Power BI verilerini görüntüleyebilmek için önce Face ID, Touch ID veya geçiş koduyla kendilerini tanıtmaya zorlar. Cihazlarında Face ID, Touch ID veya geçiş kodu yapılandırılmamış olan kullanıcıların, Power BI'a erişebilmek için bunu yapılandırmaları gerekir.  |

## <a name="next-steps"></a>Sonraki adımlar

[MDM kullanarak Power BI iOS uygulamasını uzaktan yapılandırma](mobile-app-configuration.md)
