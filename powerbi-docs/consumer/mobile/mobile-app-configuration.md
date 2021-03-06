---
title: Power BI uygulama yapılandırma ayarları
description: MDM aracını kullanarak Power BI'ın davranışını özelleştirme
author: paulinbar
ms.author: painbar
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: how-to
ms.date: 07/14/2020
ms.openlocfilehash: a867c0480e9c0762d1594016fb807cab8261c14c
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96414611"
---
# <a name="remotely-configure-power-bi-app-using-mobile-device-management-mdm-tool"></a>Mobil cihaz yönetimi (MDM) aracını kullanarak Power BI uygulamasını uzaktan yapılandırma

iOS ve Android için Power BI Mobil uygulaması Intune gibi mobil cihaz yönetimi (MDM) hizmetleri yöneticilerinin uygulamanın davranışını özelleştirmesine olanak tanıyan uygulama ayarlarını destekler.

Power BI Mobil uygulaması aşağıdaki yapılandırma senaryolarını destekler:

* Rapor Sunucusu yapılandırması (iOS ve Android)
* Veri koruma ayarları (iOS ve Android)
* Çoklu oturum açmayı devre dışı bırakma (iOS ve Android)
* Etkileşim ayarları (iOS ve Android)

## <a name="report-server-configuration-ios-and-android"></a>Rapor sunucusu yapılandırması (iOS ve Android)

iOS ve Android için Power BI uygulaması yöneticilerin kayıtlı cihazlara uzaktan Rapor Sunucusu yapılandırması "göndermesine" olanak tanır.

| Anahtar | Tür | Açıklama |
|---|---|---|
| com.microsoft.powerbi.mobile.ServerURL | Dize | Report Sunucusu URL'si.<br><br>http/https ile başlamalıdır.|
| com.microsoft.powerbi.mobile.ServerUsername | Dize | [isteğe bağlı]<br><br>Sunucuya bağlanmak için kullanılacak kullanıcı adı.<br><br>Bir tane yoksa, uygulama kullanıcıdan bağlantı için kullanıcı adı girmesini ister.|
| com.microsoft.powerbi.mobile.ServerDisplayName | Dize | [isteğe bağlı]<br><br>Varsayılan değer "Rapor sunucusu" şeklindedir<br><br>Sunucuyu temsil etmek üzere uygulamada kullanılan kolay ad. |
| com.microsoft.powerbi.mobile.OverrideServerDetails | Boole | [isteğe bağlı]<br><br>True varsayılan değerdir. True olarak ayarlanırsa mobil cihazda zaten mevcut olan tüm Rapor Sunucusu tanımlarını geçersiz kılar. Önceden yapılandırılmış olan sunucular silinir. Geçersiz Kılma ayarının True olarak belirlenmesi de kullanıcının bu yapılandırmayı kaldırmasını engeller.<br><br>False olarak ayarlandığında mevcut tüm ayarlar tutulurken gönderilen değerler eklenir. Mobil uygulamada aynı sunucu URL’si zaten yapılandırılmışsa, uygulama bu yapılandırmayı olduğu gibi bırakır. Uygulama, kullanıcıdan aynı sunucu için yeniden kimlik doğrulamasını istemez. |

## <a name="data-protection-settings-ios-and-android"></a>Veri koruma ayarları (iOS ve Android)

iOS ve Android için Power BI mobil uygulaması yöneticilere güvenlik ve gizlilik ayarları için varsayılan yapılandırmayı özelleştirme olanağı sağlar. iOS için, kullanıcıları Power BI mobil uygulamasına erişirken Face ID, Touch ID veya geçiş kodu sağlamaya zorlayabilirsiniz. Android için, kullanıcıları biyometrik kimlik doğrulaması (Parmak İzi Kimliği) kullanmaya zorlayabilirsiniz.

| Anahtar | Tür | Açıklama |
|---|---|---|
| com.microsoft.powerbi.mobile.ForceDeviceAuthentication | Boole | Varsayılan değerdir False’tur. <br><br>Kullanıcıların cihazlarından uygulamaya erişmek için TouchID veya FaceID (iOS) ya da Parmak İzi Kimliği (Android) gibi biyometri verilerini sağlaması istenebilir. Gerektiğinde biyometri verileri kimlik doğrulamasına ek olarak kullanılır.<br><br>Uygulama koruma ilkeleri kullanılıyorsa, çift erişim istemlerini önlemek için Microsoft bu ayarın devre dışı bırakılmasını önerir. |

>[!NOTE]
>Veri koruma ayarları yalnızca biyometrik kimlik doğrulamasını destekleyen Android cihazlarında uygulanır.

## <a name="disable-single-sign-on-ios-and-android"></a>Çoklu oturum açmayı devre dışı bırakma (iOS ve Android)

Power BI mobil uygulaması, kullanıcının kullanıcı adı ve parola sağlaması gereken sayıyı en düşük düzeye indirerek varsayılan olarak tek bir kullanıcı için kolay çoklu oturum açma deneyimi sağlar. Bu çoklu oturum açma davranışı, cihazın kullanıcının kişisel cihazı olduğu ve bu cihaz ile içindeki uygulamaları tek bir kullanıcının kullandığı varsayımına dayanır.

Yöneticiler, uygulamayı çoklu oturumu devre dışı bırakıp oturum açtığı sırada açıkça kullanıcının parolasını soracak şekilde uzaktan yapılandırmak için uygulama yapılandırma dosyasındaki **DisableSingleSignOn** ayarını açabilir.

Bu, yalnızca uzak yapılandırma aracılığıyla yapılandırılan salt yönetici bir ayardır. Son kullanıcı bu ayarı değiştiremez.

| Anahtar | Tür | Açıklama |
|---|---|---|
| com.microsoft.powerbi.mobile.DisableSingleSignOn | Boole | Varsayılan değerdir False’tur.<br><br>Kullanıcı oturumunu kapattıktan sonra uygulama mevcut kimlik bilgilerini yeniden kullanmaz, ancak sonraki kullanıcıdan kimliğini doğrulayıp Power BI hizmetine bağlanması için bir parola sağlamasını ister.
 |

## <a name="interaction-settings-ios-and-android"></a>Etkileşim ayarları (iOS ve Android)

Kuruluştaki kullanıcı grupları arasında varsayılan etkileşim ayarlarının değiştirilmesi gerektiğinde karar verilirse, iOS ve Android için Power BI uygulaması yöneticilere etkileşim ayarlarını yapılandırma olanağı sunar.

>[!NOTE]
>Tüm etkileşimler şu anda tüm cihazlarda desteklenmemektedir. Cihazlarda mevcut kullanılabilirliği gösteren bir grafik için bkz. [Rapor etkileşimi ayarlarını yapılandırma](mobile-app-interaction-settings.md).

| Anahtar | Tür | Değerler | Açıklama |
|---|---|---|---|
| com.microsoft.powerbi.mobile.ReportTapInteraction | Dize |  <nobr>tek dokunma</nobr><br><nobr>iki kez dokunma</nobr> | Bir görsele dokunulduğunda bir veri noktasının seçilip seçilmeyeceğini yapılandırın. |
| com.microsoft.powerbi.mobile.EnableMultiSelect | Boole |  <nobr>True</nobr><br><nobr>False</nobr> | Bir veri noktasına dokunmanın geçerli seçimin yerini alıp almayacağını veya geçerli seçime eklenip eklenmeyeceğini yapılandırın. |
| com.microsoft.powerbi.mobile.RefreshAction | Dize |  <nobr>yenilemek için çekme</nobr><br>düğmesini seçin | Kullanıcının raporu yenileme düğmesine sahip olup olmayacağını veya çekerek yenileme özelliğini kullanıp kullanmayacağını yapılandırın. |
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