---
title: "Katıştırılmış uygulamanızla ilgili sorunları giderme"
description: "Bu makalede, Power BI'dan içerik katıştırma sırasında karşılaşabileceğiniz bazı yaygın sorunlar açıklanmaktadır."
services: powerbi
documentationcenter: 
author: guyinacube
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
ms.date: 11/27/2017
ms.author: asaxton
ms.openlocfilehash: f6ffc56f524da84e865d17981faddef58534c785
ms.sourcegitcommit: 8f72ce6b35aa25979090a05e3827d4937dce6a0d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/27/2017
---
# <a name="troubleshooting-your-embedded-application"></a>Katıştırılmış uygulamanızla ilgili sorunları giderme

Bu makalede, Power BI'dan içerik katıştırma sırasında karşılaşabileceğiniz bazı yaygın sorunlar açıklanmaktadır.

## <a name="app-registration"></a>Uygulama kaydı

**Uygulama kaydı hatası**

Azure portalı veya Power BI uygulaması kayıt sayfasındaki hata iletileri, yetersiz ayrıcalıktan bahsedecektir. Bir uygulama kaydı için Azure AD kiracısında yönetici olmanız ya da yönetici olmayan kullanıcılar için uygulama kayıtlarının etkinleştirilmiş olması gerekir.

**Power BI Hizmeti yeni bir Uygulama kaydı sırasında Azure portalında görünmüyor**

En az bir kullanıcının Power BI'a kaydolmuş olması gerekir. API listesinde **Power BI Hizmetini** görmüyorsanız hiçbir kullanıcı Power BI'a kaydolmamış demektir.

## <a name="rest-api"></a>REST API

**401 kodunu döndüren API çağrısı**

Daha fazla araştırmak için Fiddler ile yakalama gerekebilir. Azure AD'de kayıtlı uygulama için gerekli izin kapsamı eksik olabilir. Azure portalındaki Azure AD için uygulama kaydında gerekli kapsamın mevcut olduğunu doğrulayın.

**403 kodunu döndüren API çağrısı**

Daha fazla araştırmak için Fiddler ile yakalama gerekebilir. Bir 403 hatasının birkaç nedeni olabilir.

* Azure AD kimlik doğrulama belirtecinin kullanım süresi dolmuştur.
* Kimliği doğrulanmış kullanıcı, grubun (uygulama çalışma alanı) bir üyesi değildir.
* Kimliği doğrulanmış kullanıcı, grubun (uygulama çalışma alanı) bir yöneticisi değildir.
* Yetkilendirme üst bilgisi doğru listelenmemiş olabilir. Yazım hatası olmadığından emin olun.

GenerateToken çağrılmadan önce uygulamanın arka ucunun kimlik doğrulaması belirtecini yenilemesi gerekebilir.

```
    GET https://wabi-us-north-central-redirect.analysis.windows.net/metadata/cluster HTTP/1.1
    Host: wabi-us-north-central-redirect.analysis.windows.net
    ...
    Authorization: Bearer eyJ0eXAiOi...
    ...
 
    HTTP/1.1 403 Forbidden
    ...
     
    {"error":{"code":"TokenExpired","message":"Access token has expired, resubmit with a new access token"}}
```

**Etkin kimlik sağlanırken belirteç oluşturulamıyor**

GenerateToken, etkin kimlik sağlandığında birkaç nedenden dolayı başarısız olabilir.

* Veri kümesi etkin kimliği desteklemiyor
* Kullanıcı adı sağlanmadı
* Rol sağlanmadı
* DatasetId sağlanmadı
* Kullanıcı doğru izinlere sahip değil

Hangisi olduğunu doğrulamak için aşağıdakileri deneyin.

* [Veri kümesi al](https://msdn.microsoft.com/library/mt784653.aspx) komutunu yürütün. IsEffectiveIdentityRequired özelliği doğru mu?
* Kullanıcı adı her EffectiveIdentity için zorunludur.
* IsEffectiveIdentityRolesRequired doğruysa Rol gereklidir.
* DatasetId her EffectiveIdentity için zorunludur.
* Analysis Services için ana kullanıcı bir ağ geçidi yöneticisi olmak zorundadır.

## <a name="data-sources"></a>Veri kaynakları

**ISV aynı veri kaynağı için farklı kimlik bilgilerine sahip olmak istiyor**

Bir veri kaynağında, bir ana kullanıcı için tek kimlik bilgisi kümesi olabilir. Farklı kimlik bilgileri kullanmanız gerekiyorsa ek ana kullanıcılar oluşturun. Ardından, her ana kullanıcı bağlamında farklı kimlik bilgileri atayın ve kullanıcının Azure AD belirtecini kullanarak ekleyin.

## <a name="content-rendering"></a>İçerik işleme

**Katıştırılmış içeriği işleme veya kullanma girişimi başarısız oldu veya zaman aşımına uğradı**

Ekleme belirtecinin son kullanma tarihinin geçmediğinden emin olun. Ekleme belirtecinin son kullanma tarihini kontrol ettiğinizden ve yenilediğinizden emin olun. Daha fazla bilgi için bkz. [JavaScript SDK kullanarak belirteci yenileme](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Refresh-token-using-JavaScript-SDK-example).

**Rapor veya pano yüklenmiyor**

Kullanıcı raporu veya panoyu göremiyorsa rapor ya da panonun powerbi.com'a doğru şekilde yüklendiğinden emin olun. Rapor veya pano, powerbi.com'a yüklenmezse uygulamanızda çalışmaz.

**Rapor veya Pano yavaş çalışıyor**

Power BI Desktop'tan veya powerbi.com'da dosyayı açın ve uygulamanızla veya API'leri eklemeyle ilgili sorunları elemek için performansın kabul edilebilir olduğunu doğrulayın.

## <a name="tools-for-troubleshooting"></a>Sorun giderme araçları

### <a name="fiddler-trace"></a>Fiddler ile İzleme

[Fiddler](http://www.telerik.com/fiddler), Telerik tarafından kullanıma sunulup HTTP trafiğini izleyen ücretsiz bir araçtır.  İstemci makinesinden Power BI API'lerindeki gelen ve giden trafiği görebilirsiniz. Bu sayede hataları ve diğer ilgili bilgileri görüntüleyebilirsiniz.

![Fiddler ile İzleme](../includes/media/gateway-onprem-tshoot-tools-include/fiddler.png)

### <a name="f12-in-browser-for-front-end-debugging"></a>Ön uç hata ayıklama için Tarayıcıda F12

F12 tarayıcınızda geliştirici penceresini açar. Bu, ağ trafiğini ve diğer bilgileri görüntüleme olanağı sağlar.

![F12 Tarayıcı hata ayıklama](media/embedded-troubleshoot/browser-f12.png)

Sık sorulan soruların cevapları için bkz. [Power BI Embedded hakkında SSS](embedded-faq.md).

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)