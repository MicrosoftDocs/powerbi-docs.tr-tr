---
title: "\"Kurumsal SSL sertifikasına güvenilmiyor\" hatalarını giderme"
description: 'Power BI Android uygulamasında oturum açarken şu iletiyi görebilirsiniz: "Kurumsal SSL sertifikanıza güvenilmediği için kimlik doğrulaması yapılamadı'
.": ''
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: how-to
ms.date: 03/11/2020
ms.author: painbar
ms.openlocfilehash: 85e295b2320f8aecca2176149ce37c0a25ad2bd2
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85237463"
---
# <a name="fixing-corporate-ssl-certificate-is-untrusted---power-bi"></a>"Kurumsal SSL sertifikanıza güvenilmiyor" hatasını düzeltme - Power BI
Microsoft Power BI Android uygulamasında oturum açarken şu iletiyi görebilirsiniz: "Bu cihaz, kurumsal SSL sertifikanıza güvenmediği için kimlik doğrulaması yapılamadı. Şirketinizin BT yöneticisiyle iletişime geçin." 

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
Özel kimlik doğrulama sunucusu kullanıyorsanız kurumsal kimlik doğrulama sunucusundaki SSL sertifikası geçersiz olabilir. Kuruluşunuzun BT ekibiyle birlikte [bu makaledeki](https://support.microsoft.com/help/3203929/using-adal-to-authenticate-from-android-devices-fails-if-additional-ce) yönergeleri izleyerek kurumsal kimlik doğrulaması sunucusunun yapılandırmasını test edin.

## <a name="next-steps"></a>Sonraki adımlar
* Android uygulama mağazasından [Android uygulamasını indirme](https://go.microsoft.com/fwlink/?LinkID=544867).
* Sorular? [Power BI Topluluğu'na sorun](https://community.powerbi.com/) 

