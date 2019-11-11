---
title: Power BI iOS uygulama yapılandırma ayarları
description: MDM aracını kullanarak iOS için Power BI'ın davranışını özelleştirme
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 06/07/2019
ms.author: mshenhav
ms.openlocfilehash: c2d619489b042e523c559a16dab249b268389cd5
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73879424"
---
# <a name="remotely-configure-power-bi-ios-app-using-mobile-device-management-mdm-tool"></a>Mobil cihaz yönetimi (MDM) aracını kullanarak Power BI iOS uygulamasını uzaktan yapılandırma

iOS için Power BI Mobil uygulaması yöneticilerin Office 365 ve Intune gibi mobil cihaz yönetimi (MDM) araçları için uygulamanın davranışını özelleştirmesine olanak tanıyan uygulama ayarlarını destekler.

iOS için Power BI Mobil uygulaması aşağıdaki yapılandırma senaryolarını destekler:

- Rapor Sunucusu yapılandırması
- Veri koruma ayarları

## <a name="report-server-configuration"></a>Rapor sunucusu yapılandırması

Power BI iOS uygulaması yöneticilerin kayıtlı cihazlarla uzaktan Rapor Sunucusu yapılandırması "göndermesine" olanak tanır.

| Anahtar | Tür | Açıklama |
|---|---|---|
| com.microsoft.powerbi.mobile.ServerURL | Dize | Report Sunucusu URL'si.<br><br>http/https ile başlamalıdır.|
| com.microsoft.powerbi.mobile.ServerUsername | Dize | [isteğe bağlı]<br><br>Sunucuya bağlanmak için kullanılacak kullanıcı adı.<br><br>Bir tane yoksa, uygulama kullanıcıdan bağlantı için kullanıcı adı girmesini ister.|
| com.microsoft.powerbi.mobile.ServerDisplayName | Dize | [isteğe bağlı]<br><br>Varsayılan değer “Rapor sunucusu” şeklindedir<br><br>Sunucuyu temsil etmek üzere uygulamada kullanılan kolay ad. |
| com.microsoft.powerbi.mobile.OverrideServerDetails | Boole | [isteğe bağlı]<br><br>True varsayılan değerdir. True olarak ayarlanırsa mobil cihazda zaten mevcut olan tüm Rapor Sunucusu tanımlarını geçersiz kılar. Önceden yapılandırılmış olan sunucular silinir. Geçersiz Kılma ayarının True olarak belirlenmesi de kullanıcının bu yapılandırmayı kaldırmasını engeller.<br><br>False olarak ayarlandığında mevcut tüm ayarlar tutulurken gönderilen değerler eklenir. Mobil uygulamada aynı sunucu URL’si zaten yapılandırılmışsa, uygulama bu yapılandırmayı olduğu gibi bırakır. Uygulama, kullanıcıdan aynı sunucu için yeniden kimlik doğrulamasını istemez. |

## <a name="data-protection-setting"></a>Veri koruma ayarı

Power BI iOS uygulaması yöneticilere güvenlik ve gizlilik ayarları için varsayılan yapılandırmayı özelleştirme olanağı sağlar. Kullanıcıları Power BI uygulamasına erişirken Face ID, Touch ID veya geçiş kodu sağlamaya zorlayabilirsiniz.

| Anahtar | Tür | Açıklama |
|---|---|---|
| com.microsoft.powerbi.mobile.ForceDeviceAuthentication | Boole | Varsayılan değerdir False’tur. <br><br>Kullanıcıların cihazlarından uygulamaya erişmek için TouchID veya FaceID gibi biyometri verilerini sağlaması istenebilir. Gerektiğinde biyometri verileri kimlik doğrulamasına ek olarak kullanılır.<br><br>Uygulama koruma ilkeleri kullanılıyorsa, çift erişim istemlerini önlemek için Microsoft bu ayarın devre dışı bırakılmasını önerir. |

## <a name="deploying-app-configuration-settings"></a>Uygulama yapılandırma ayarlarını dağıtma

Aşağıdaki adımlar uygulama yapılandırma ilkesi oluşturmanızı sağlayacaktır. Yapılandırma ilkesi oluşturulduktan sonra, ilkenin ayarlarını kullanıcı gruplarına atayabilirsiniz.

1. MDM aracınızı bağlayın.

2. Yeni bir uygulama yapılandırma ilkesi oluşturun ve adlandırın.

3. Bu uygulama yapılandırma ilkesinin dağıtılacağı kullanıcıları seçin.

4. Kullanıcılarınıza göndermek istediğiniz ayar için anahtar-değer çiftleri oluşturun.

Intune portalı yöneticilerin uygulama yapılandırma ilkeleri yoluyla bu ayarları Power BI iOS uygulamasına kolayca dağıtmasını sağlar.
Bununla birlikte tüm MDM sağlayıcıları desteklenir. Intune kullanmıyorsanız, bu ayarların nasıl dağıtıldığını öğrenmek için MDM belgelerinize bakmanız gerekir.

## <a name="next-steps"></a>Sonraki adımlar

* [Power BI iPhone mobil uygulamasını](https://go.microsoft.com/fwlink/?LinkId=522062) indirin
* [Twitter'da @MSPowerBI sayfasını](https://twitter.com/MSPowerBI) takip edin
* [Power BI Topluluğu](https://community.powerbi.com/)'ndaki sohbetlere katılın
