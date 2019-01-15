---
title: Uygulamalardan rapor veya pano ekleme
description: Uygulama çalışma alanından değil bir Power BI uygulamasından rapor veya pano tümleştirmeyi ya da eklemeyi öğrenin.
author: markingmyname
ms.author: maghan
ms.topic: how-to
ms.service: powerbi
ms.subservice: powerbi-developer
ms.custom: mvc
manager: kfile
ms.date: 11/27/2018
ms.openlocfilehash: 4125f44165fbbc063b782290b7c67da9993d5157
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2019
ms.locfileid: "54286324"
---
# <a name="embed-reports-or-dashboards-from-apps"></a>Uygulamalardan rapor veya pano ekleme

Power BI'da ilişkili panoları ve raporları tek bir yerde bir araya getirmek için uygulama oluşturabilirsiniz. Ardından, uygulamaları kuruluşunuzdaki büyük kullanıcı gruplarına yayımlarsınız. Bu uygulamaların kullanımı, tüm kulanıcılarınız Power BI kullanıcısı olduğunda geçerlidir. Yani Power BI uygulamalarını kullanarak bunlarla içerik paylaşabilirsiniz. Bu makalede, yayımlanmış bir Power BI uygulamasından üçüncü taraf uygulamasına içerik ekleme hakkında birkaç pratik adım yer almaktadır.

## <a name="grab-a-report-embedurl-for-embedding"></a>Ekleme için rapor embedURL edinme

1. Bir kullanıcı çalışma alanında (**My Workspace**) uygulamanın örneğini oluşturun. Kendinizle paylaşın veya başka bir kullanıcıya bu süreçte kılavuzluk edin.

2. İstediğiniz raporu Power BI hizmetinde açın.

3. **Dosya** > **SharePoint Online’a Ekle** öğesine gidin ve rapor embedURL’yi alın. Aşağıdaki anlık görüntüde bir embedURL örneği gösterilir. Alternatif olarak, GetReports/GetReport REST API’sini çağırabilir ve ilgili rapor embedURL alanını yanıttan ayıklayabilirsiniz. Uygulamanın örneği kullanıcının çalışma alanında oluşturulduğundan, REST çağrısında URL’nin parçası olarak bir çalışma sayfası tanımlayıcısı olmamalıdır.

    ![Uygulamalardan ekleme](media/embed-from-apps/embed-from-app.png)

4. JavaScript SDK'sı ile 3. adımda alınan embedURL’yi kullanın.

## <a name="grab-a-dashboard-embedurl-for-embedding"></a>Ekleme için pano embedURL edinme

1. Bir kullanıcı çalışma alanında (**My Workspace**) uygulamanın örneğini oluşturun. Kendinizle paylaşın veya başka bir kullanıcıya bu süreçte kılavuzluk edin.

2. GetDashboards REST API’sine çağrı yapın ve ilgili pano embedURL alanını yanıttan ayıklayın. Uygulamanın örneği kullanıcının çalışma alanında oluşturulduğundan, REST çağrısında URL’nin parçası olarak bir çalışma sayfası tanımlayıcısı olmamalıdır.

3. JavaScript SDK'sı ile 2. adımda alınan embedURL’yi kullanın.

## <a name="next-steps"></a>Sonraki adımlar

Üçüncü taraf müşterileriniz ve kuruluşunuz için uygulama çalışma alanlarından içerik ekleme konularına göz atın:

> [!div class="nextstepaction"]
>[Üçüncü taraf müşteriler için ekleme](embed-sample-for-customers.md)

> [!div class="nextstepaction"]
>[Kuruluşunuz için ekleme](embed-sample-for-your-organization.md)
