---
title: Kuruluşunuz için tümleşik BI içgörüleri oluşturmak amacıyla Power BI tümleşik analizleri kullanarak ekleme yaparken Power BI uygulamalarını otomatik yükleme
description: Kuruluşunuz için tümleşik BI içgörüleri oluşturmak amacıyla Power BI tümleşik analizleri kullanarak ekleme yaparken Power BI uygulamalarını otomatik yükleme hakkında bilgi edinin.
author: KesemSharabi
ms.author: kesharab
ms.topic: how-to
ms.service: powerbi
ms.subservice: powerbi-developer
ms.custom: ''
ms.date: 04/16/2019
ms.openlocfilehash: 66ba3b7d573c86b32a91bc0a98cd5ec0775fec75
ms.sourcegitcommit: 1cad78595cca1175b82c04458803764ac36e5e37
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/19/2021
ms.locfileid: "98565845"
---
# <a name="auto-install-power-bi-apps-when-embedding-for-your-organization"></a>Kuruluşunuz için içerik eklerken Power BI uygulamalarını otomatik olarak yükleme

Uygulamadan içerik eklemek için, ekleme işlemini yapan kullanıcının [uygulamaya erişimi](../../collaborate-share/service-create-distribute-apps.md) olmalıdır. Uygulama kullanıcı için yüklendiyse ekleme işlemi sorunsuz çalışır. Daha fazla bilgi için bkz. [Uygulamadan raporlar veya panolar ekleme](./index.yml). PowerBI.com'da tüm uygulamaların [otomatik olarak yüklenebilmesini](https://powerbi.microsoft.com/blog/automatically-install-apps/) tanımlamak mümkündür. Bununla birlikte bu eylem kiracı düzeyinde yapılır ve tüm uygulamalar için geçerli olur.

## <a name="auto-install-app-on-embedding"></a>Ekleme sırasında uygulamayı otomatik olarak yükleme

Kullanıcının uygulamaya erişim varsa ama uygulama yüklenmemişse, ekleme başarısız olur. Bu nedenle uygulamadan içerik eklerken bu hatalardan kaçınmak için uygulamanın ekleme sırasında otomatik olarak yüklenmesine izin verebilirsiniz. Bu eylem, kullanıcının eklemeye çalıştığı uygulama yüklü değilse otomatik olarak yükleneceği anlamına gelir. Dolayısıyla istediğiniz içerik anında eklenir ve sonuçta kullanıcı için sorunsuz bir deneyim sağlanır.

## <a name="embed-for-power-bi-users-user-owns-data"></a>Power BI kullanıcıları için ekleme (Veriler kullanıcıya aittir)

Kullanıcılarınızda uygulamaların otomatik yüklenmesine izin vermek için, [uygulamanızı kaydederken](register-app.md#register-an-azure-ad-app) 'İçerik Oluşturma' izni vermeli veya uygulamanızı zaten kaydettiyseniz bu izni eklemelisiniz.

![İçerik oluşturan uygulamayı kaydetme](media/embed-auto-install-app/register-app-create-content.png)

Ardından ekleme URL'sinde uygulama kimliğini sağlamalısınız. Uygulama kimliğini sağlamak için, uygulama oluşturucunun önce uygulamayı yüklemesi ve ardından desteklenen [Power BI Rest API](/rest/api/power-bi/) çağrılarından ([Get Reports](/rest/api/power-bi/reports/getreports) veya [Get Dashboards](/rest/api/power-bi/dashboards/getdashboards)) birini kullanması gerekir. Sonra uygulama oluşturucu REST API yanıtından ekleme Url'sini almalıdır. İçerik bir uygulamadan geliyorsa uygulama kimliği URL'de gösterilir.  Ekleme URL'sini aldıktan sonra bunu kullanarak düzenli aralıklarla ekleyebilirsiniz.

## <a name="secure-embed"></a>Güvenli Ekleme

Uygulamaları otomatik yüklemeyi kullanmak için, uygulama sağlayıcının önce uygulamayı yüklemesi ve ardından PowerBI.com'da uygulamaya gitmesi, rapora gitmesi ve normal yollarla bağlantıyı alması gerekir. Uygulamaya erişimi olan diğer tüm kullanıcılar bağlantıyı kullanıp raporu ekleyebilir.

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

* Bu senaryoda yalnızca raporları ve panoları ekleyebilirsiniz.

* Bu özellik şu anda uygulamanın sahip olduğu verilerde ve SharePoint ekleme senaryolarında desteklenmemektedir.