---
title: 'Hata: '
corporate: 
ssl: 
certificate: 
is: 
untrusted": 
'-': 
power: 
bi": 
description: "Power BI Android uygulamasında oturum açarken şu iletiyi görebilirsiniz: \"Kurumsal SSL sertifikanıza güvenilmediği için kimlik doğrulaması yapılamadı"
.": 
services: powerbi
documentationcenter: 
author: maggiesMSFT
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/13/2017
ms.author: maggies
ms.openlocfilehash: 4ef29c0cab96e21045f30805d7445aa34d37697a
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2017
---
# <a name="error-corporate-ssl-certificate-is-untrusted---power-bi"></a>Hata: "Kurumsal SSL sertifikanıza güvenilmiyor" - Power BI
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
Özel kimlik doğrulama sunucusu kullanıyorsanız kurumsal kimlik doğrulama sunucusundaki SSL sertifikası geçersiz olabilir. Yardım için lütfen kuruluşunuzun BT yöneticisiyle iletişime geçin.

## <a name="next-steps"></a>Sonraki adımlar
* Android uygulama mağazasından [Android uygulamasını indirme](http://go.microsoft.com/fwlink/?LinkID=544867).
* Sorularınız mı var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

