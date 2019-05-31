---
title: Otomatik olarak kuruluşunuz için ekleme yaparken Power BI uygulamaları yükle
description: Kuruluşunuz için ekleme yaparken otomatik olarak uygulama yükleme Power BI hakkında bilgi edinin.
ms.subservice: powerbi-developer
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.topic: how-to
ms.service: powerbi
ms.custom: ''
ms.date: 04/16/2019
ms.openlocfilehash: bb9ba5531c2a23f15ccbf98261e246ab7080aecb
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "61376218"
---
# <a name="auto-install-power-bi-apps-when-embedding-for-your-organization"></a>Kuruluşunuz için ekleme yaparken otomatik yüklenecek Power BI uygulamaları

Bir uygulamadan içerik eklemek için ekleme kullanıcı olmalıdır [uygulamaya erişim](../service-create-distribute-apps.md). Uygulama kullanıcı için yüklenir, ardından ekleme sorunsuz bir şekilde çalışır. Daha fazla bilgi için [raporlar veya panolar uygulamasından](embed-from-apps.md). Tüm uygulamalar olabilecek Powerbı.com'da tanımlamak mümkündür [otomatik olarak yüklenen](https://powerbi.microsoft.com/blog/automatically-install-apps/). Ancak, bu eylem Kiracı düzeyinde gerçekleştirilir ve tüm uygulamalar için geçerlidir.

## <a name="auto-install-app-on-embedding"></a>Otomatik yüklenecek uygulama ekleme

Bir kullanıcı bir uygulama, ancak uygulama erişimi varsa, ardından başarısız katıştırma yüklü değil. Uygulama eklerken bu hataları önlemek için otomatik uygulamasının yüklenmesi ve ekleme sırasında izin verebilirsiniz. Bu eylem kullanıcı eklemeye çalışırsa uygulama yüklü değilse, bunu otomatik olarak sizin için yüklü olduğu anlamına gelir. Bu nedenle, istediğiniz içeriği hemen kullanıcı için sorunsuz bir deneyim výsledek katıştırılmış.

## <a name="embed-for-power-bi-users-user-owns-data"></a>Power BI kullanıcıları (verilerin sahibi kullanıcıdır) ekleme

Kullanıcılarınız için uygulamaları otomatik yükleme izin vermek için uygulamanızı 'İçerik oluşturma' izni vermeniz gerekir, [uygulamanızı kaydetmek](register-app.md#register-with-the-power-bi-application-registration-tool), veya uygulamanızı zaten kaydolduysanız ekleyin.

![Register app içerik oluşturur](media/embed-auto-install-app/register-app-create-content.png)

Ardından, ekleme URL'sindeki uygulama Kimliğini sağlamanız gerekir. Uygulama Kimliği sağlamak için uygulama Oluşturucu öncelikle uygulamayı yükledikten sonra desteklenen birini kullanın gerekir [Power BI Rest API'si](https://docs.microsoft.com/rest/api/power-bi/) çağrıları - [Get Reports](https://docs.microsoft.com/rest/api/power-bi/reports/getreports) veya [Get Dashboards](https://docs.microsoft.com/rest/api/power-bi/dashboards/getdashboards). Daha sonra uygulama Oluşturucu REST API yanıtından ekleme URL'si gerekir. İçeriği bir uygulamadan ise uygulama kimliği URL'de görünür.  Ekleme URL'sini aldıktan sonra düzenli olarak eklemek için kullanabilirsiniz.

## <a name="secure-embed"></a>Güvenli ekleme

Uygulamaları otomatik yükleme kullanmak için uygulama Oluşturucu öncelikle uygulamayı yükledikten sonra raporu PowerBI.com üzerinde uygulamasına gidin ve normal bir biçimde bağlantısını alın gerekir. Tüm diğer kullanıcılarla bağlantı kullanan uygulamaya rapor ekleyebilir.

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

* Yalnızca, raporlar ve panolar bu senaryo için de ekleyebilirsiniz.

* Verilerin sahibinin uygulama ve SharePoint ekleme senaryoları için bu özellik şu anda desteklenmiyor.