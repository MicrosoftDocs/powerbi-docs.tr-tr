---
title: Power BI uygulama yapılandırma ayarları
description: MDM aracını kullanarak Power BI'ın davranışını özelleştirme
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 01/15/2020
ms.author: painbar
ms.openlocfilehash: 58b2f96b069815af448352b3b54875dc4d6b27ee
ms.sourcegitcommit: 02342150eeab52b13a37b7725900eaf84de912bc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2020
ms.locfileid: "76538279"
---
# <a name="remotely-configure-power-bi-app-using-mobile-device-management-mdm-tool"></a>Mobil cihaz yönetimi (MDM) aracını kullanarak Power BI uygulamasını uzaktan yapılandırma

iOS ve Android için Power BI Mobil uygulaması Intune gibi mobil cihaz yönetimi (MDM) hizmetleri yöneticilerinin uygulamanın davranışını özelleştirmesine olanak tanıyan uygulama ayarlarını destekler.

Power BI Mobil uygulaması aşağıdaki yapılandırma senaryolarını destekler:

* Rapor Sunucusu yapılandırması (iOS ve Android)
* Veri koruma ayarları (iOS ve Android)
* Etkileşim ayarları (Android)

## <a name="report-server-configuration-ios-and-android"></a>Rapor sunucusu yapılandırması (iOS ve Android)

iOS ve Android için Power BI uygulaması yöneticilerin kayıtlı cihazlara uzaktan Rapor Sunucusu yapılandırması "göndermesine" olanak tanır.

| Anahtar | Tür | Açıklama |
|---|---|---|
| com.microsoft.powerbi.mobile.ServerURL | Dize | Report Sunucusu URL'si.<br><br>http/https ile başlamalıdır.|
| com.microsoft.powerbi.mobile.ServerUsername | Dize | [isteğe bağlı]<br><br>Sunucuya bağlanmak için kullanılacak kullanıcı adı.<br><br>Bir tane yoksa, uygulama kullanıcıdan bağlantı için kullanıcı adı girmesini ister.|
| com.microsoft.powerbi.mobile.ServerDisplayName | Dize | [isteğe bağlı]<br><br>Varsayılan değer “Rapor sunucusu” şeklindedir<br><br>Sunucuyu temsil etmek üzere uygulamada kullanılan kolay ad. |
| com.microsoft.powerbi.mobile.OverrideServerDetails | Boole | [isteğe bağlı]<br><br>True varsayılan değerdir. True olarak ayarlanırsa mobil cihazda zaten mevcut olan tüm Rapor Sunucusu tanımlarını geçersiz kılar. Önceden yapılandırılmış olan sunucular silinir. Geçersiz Kılma ayarının True olarak belirlenmesi de kullanıcının bu yapılandırmayı kaldırmasını engeller.<br><br>False olarak ayarlandığında mevcut tüm ayarlar tutulurken gönderilen değerler eklenir. Mobil uygulamada aynı sunucu URL’si zaten yapılandırılmışsa, uygulama bu yapılandırmayı olduğu gibi bırakır. Uygulama, kullanıcıdan aynı sunucu için yeniden kimlik doğrulamasını istemez. |

## <a name="data-protection-settings-ios"></a>Veri koruma ayarları (iOS)

iOS ve Android için Power BI uygulaması yöneticilere güvenlik ve gizlilik ayarları için varsayılan yapılandırmayı özelleştirme olanağı sağlar. Kullanıcıları Power BI uygulamasına erişirken Face ID, Touch ID veya geçiş kodu sağlamaya zorlayabilirsiniz.

| Anahtar | Tür | Açıklama |
|---|---|---|
| com.microsoft.powerbi.mobile.ForceDeviceAuthentication | Boole | Varsayılan değerdir False’tur. <br><br>Kullanıcıların cihazlarından uygulamaya erişmek için TouchID veya FaceID gibi biyometri verilerini sağlaması istenebilir. Gerektiğinde biyometri verileri kimlik doğrulamasına ek olarak kullanılır.<br><br>Uygulama koruma ilkeleri kullanılıyorsa, çift erişim istemlerini önlemek için Microsoft bu ayarın devre dışı bırakılmasını önerir. |

## <a name="interaction-settings-android"></a>Etkileşim ayarları (Android)

Kuruluştaki kullanıcı grupları arasında varsayılan etkileşim ayarlarının değiştirilmesi gerektiğinde karar verilirse, Android için Power BI uygulaması yöneticilere etkileşim ayarlarını yapılandırma olanağı sunar. 

| Anahtar | Tür | Değerler | Açıklama |
|---|---|---|---|
| com.microsoft.powerbi.mobile.ReportTapInteraction | Dize |  <nobr>tek dokunma</nobr><br><nobr>iki kez dokunma</nobr> | Görsele dokunulduğunda bir veri noktasının seçilip seçilmeyeceğini yapılandırın. |
| ccom.microsoft.powerbi.mobile.RefreshAction | Dize |  <nobr>yenilemek için çekme</nobr><br>düğmesini seçin | Kullanıcının raporu yenileme düğmesine sahip olup olmayacağını veya çekerek yenileme özelliğini kullanıp kullanmayacağını yapılandırın. |
| com.microsoft.powerbi.mobile.FooterAppearance | Dize |  yerleşik<br>dinamik | Rapor alt bilgisinin raporun altına yerleştirilip yerleştirilmeyeceğini veya otomatik olarak gizlenip gizlenmeyeceğini yapılandırın. |

## <a name="deploying-app-configuration-settings"></a>Uygulama yapılandırma ayarlarını dağıtma

Aşağıdaki adımlar uygulama yapılandırma ilkesi oluşturmanız için gereken adımlardır. Yapılandırma ilkesini oluşturduktan sonra, ilkenin ayarlarını kullanıcı gruplarına atayabilirsiniz.

1. MDM aracınızı bağlayın.
2. Yeni bir uygulama yapılandırma ilkesi oluşturun ve adlandırın.
3. Bu uygulama yapılandırma ilkesinin dağıtılacağı kullanıcıları seçin.
4. Kullanıcılarınıza göndermek istediğiniz ayar için anahtar-değer çiftleri oluşturun.

Intune portalı yöneticilerin uygulama yapılandırma ilkeleri yoluyla bu ayarları Power BI uygulamasına kolayca dağıtmasını sağlar. Bununla birlikte tüm MDM sağlayıcıları desteklenir. Intune kullanmıyorsanız, bu ayarların nasıl dağıtıldığını öğrenmek için MDM belgelerinize bakmanız gerekir.

## <a name="next-steps"></a>Sonraki adımlar

* Power BI mobil uygulamasını [App store](https://apps.apple.com/app/microsoft-power-bi/id929738808)'dan ve [Google play](https://play.google.com/store/apps/details?id=com.microsoft.powerbim&amp;amp;clcid=0x409)'den alın
* [Twitter'da @MSPowerBI hesabını takip edin](https://twitter.com/MSPowerBI)
* [Power BI Topluluğu](https://community.powerbi.com/)'ndaki sohbetlere katılın
