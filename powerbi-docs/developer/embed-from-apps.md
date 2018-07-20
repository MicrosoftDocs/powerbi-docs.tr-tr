---
title: Uygulamalardan rapor veya pano ekleme
description: Uygulama çalışma alanından değil bir Power BI uygulamasından rapor veya pano tümleştirmeyi ya da eklemeyi öğrenin.
author: markingmyname
ms.author: maghan
ms.date: 07/13/2018
ms.topic: how-to
ms.service: powerbi
ms.component: powerbi-developer
ms.custom: mvc
manager: kfile
ms.openlocfilehash: 2817ccb25fc9aa6d3e8150c776558366dcf0ccb6
ms.sourcegitcommit: 0c870a006e525447497e678484874a2f137b9abd
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/17/2018
ms.locfileid: "39088851"
---
# <a name="embed-reports-or-dashboards-from-apps"></a>Uygulamalardan rapor veya pano ekleme

**Power BI**'da, ilişkili **pano** ve **raporları** bir araya getirip kuruluşunuzda kalabalık gruplara yayımlamak için uygulamalar oluşturabilirsiniz. Bu uygulamaları, tüm kullanıcılarınız Power BI kullandığında ve onlarla Power BI uygulamalarını kullanarak içerik paylaşma imkanınız olduğunda kullanabilirsiniz. Yayımlanmış bir Power BI uygulamasından üçüncü taraf uygulamasına içerik ekleme konusunda birkaç pratik adım paylaşmak istiyoruz.

## <a name="how-to-grab-report-embed-url-for-embedding"></a>Ekleme için rapor ekleme URL'si alma

1. Kendinizle paylaşarak veya başka bir kullanıcının bu akışı izlemesini sağlayarak uygulamayı bir kullanıcı çalışma alanında ("Çalışma Alanım") başlatın.

2. İstediğiniz raporu Power BI hizmetinde açın.

3. SharePoint Online'da Dosya->Ekle yolunu izleyin ve rapor ekleme URL'sini oradan alın (aşağıdaki ekran görüntüsüne bakın) veya GetReports/GetReport REST API'sine çağrı yaparak yanıttan ilgili rapor embedURL alanını ayıklayın (uygulama, kullanıcının çalışma alanında başlatıldığından REST çağrısında URL'nin içinde çalışma alanı tanımlayıcısı olmadığından emin olun).

4. 3. adımda aldığınız ekleme URL'sini JS SDK'sı ile birlikte kullanın.

    ![Uygulamalardan ekleme](media/embed-from-apps/embed-from-app.png)

## <a name="how-to-grab-dashboard-embed-url-for-embedding"></a>Ekleme için pano ekleme URL'si alma

1. Kendinizle paylaşarak veya başka bir kullanıcının bu akışı izlemesini sağlayarak uygulamayı bir kullanıcı çalışma alanında ("Çalışma Alanım") başlatın.

2. GetDashboards REST API'sine çağrı yaparak yanıttan ilgili pano embedURL alanını ayıklayın (uygulama, kullanıcının çalışma alanında başlatıldığından REST çağrısında URL'nin içinde çalışma alanı tanımlayıcısı olmadığından emin olun).

3. 4. adımda aldığınız ekleme URL'sini JS SDK'sı ile birlikte kullanın.

## <a name="next-steps"></a>Sonraki Adımlar

Üçüncü taraf müşterileriniz ve kuruluşunuz için uygulama çalışma alanlarından içerik ekleme konularına da göz atın.

> [!div class="nextstepaction"]
>[Üçüncü taraf müşteriler için ekleme](embed-sample-for-customers.md)

> [!div class="nextstepaction"]
>[Kuruluşunuz için ekleme](embed-sample-for-your-organization.md)