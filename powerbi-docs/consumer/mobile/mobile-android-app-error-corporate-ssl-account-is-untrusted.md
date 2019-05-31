---
title: "\"Kurumsal SSL sertifikasına güvenilmiyor\" hatalarını giderme"
description: 'Power BI Android uygulamasında oturum açarken şu iletiyi görebilirsiniz: "Kurumsal SSL sertifikanıza güvenilmediği için kimlik doğrulaması yapılamadı'
.": ''
author: mshenhav
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 05/18/2018
ms.author: mshenhav
ms.openlocfilehash: de103412e21e0d26d20058e2d4e1fb9a8a5449bf
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "61341363"
---
# <a name="fixing-corporate-ssl-certificate-is-untrusted---power-bi"></a>"Kurumsal SSL sertifikanıza güvenilmiyor" hatasını düzeltme - Power BI
Microsoft Power BI Android uygulamasında oturum açarken şu iletiyi görebilirsiniz: "Bu cihaz, kurumsal SSL sertifikanıza güvenmediği için kimlik doğrulaması yapılamadı. Lütfen şirketinizin BT yöneticisiyle iletişime geçin." 

Yapmanız gereken işlemler genelde Android cihazınızdaki işletim sistemine göre değişiklik gösterir ancak bu hataya neden olabilecek başka durumlar da vardır.

## <a name="on-android-7-or-later"></a>Android 7 veya üzeri cihazlarda
**Chrome** adlı uygulama için güncelleştirme olup olmadığını denetleyin ve güncelleştirmeyi yükleyin.

## <a name="on-android-6-and-earlier"></a>Android 6 veya öncesi cihazlarda
Cihazınıza System Webview uygulamasının güncelleştirilmiş sürümünün yüklenmesi gerekebilir. Bu uygulama cihazınızda yüklü olabilir ve bu durumda yalnızca **Güncelleştir**'e tıklamanız yeterli olacaktır.

System Webview uygulaması cihazınızda yüklü değilse:

1. Android cihazınızda Power BI uygulamasını kapatın.
2. Google Play Store'u açın ve Google Inc. tarafından yayımlanan **System Webview** uygulamasını arayın.
3. Uygulamayı yükleyin.
4. Power BI uygulamasını yeniden başlatıp oturum açın.

## <a name="time-zone-settings"></a>Saat dilimi ayarları
Cihazınızın saat dilimi ayarları hatalı olabilir. 

**Ayarlar** > **Sistem** > **Tarih ve saat** sayfasına gidip kontrol edin.

## <a name="custom-authentication-server"></a>Özel kimlik doğrulama sunucusu
Özel kimlik doğrulama sunucusu kullanıyorsanız kurumsal kimlik doğrulama sunucusundaki SSL sertifikası geçersiz olabilir. Lütfen kuruluşunuzun BT ekibiyle birlikte [bu makaledeki](https://support.microsoft.com/en-us/help/3203929/using-adal-to-authenticate-from-android-devices-fails-if-additional-ce) yönergeleri izleyerek kurumsal kimlik doğrulaması sunucusunun yapılandırmasını test edin.

## <a name="next-steps"></a>Sonraki adımlar
* Android uygulama mağazasından [Android uygulamasını indirme](http://go.microsoft.com/fwlink/?LinkID=544867).
* Sorularınız mı var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/) 

