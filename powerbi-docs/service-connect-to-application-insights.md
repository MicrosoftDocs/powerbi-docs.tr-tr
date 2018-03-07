---
title: "Power BI ile Application Insights'a Bağlanma"
description: "Power BI için Application Insights"
services: powerbi
documentationcenter: 
author: SarinaJoan
manager: kfile
backup: maggiesMSFT
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: 04cc92bd33f342097b9952a744d8dfffced22bb3
ms.sourcegitcommit: d91b7bf18d5c504037134f375886633379f28ede
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/27/2018
---
# <a name="connect-to-application-insights-with-power-bi"></a>Power BI ile Application Insights'a Bağlanma
[Application Insights](https://azure.microsoft.com/documentation/articles/app-insights-overview/) telemetrisiyle güçlü, özel panolar oluşturmak için Power BI'ı kullanın. Uygulama telemetrinizi yeni yöntemlerle tasarlayın. Birden çok uygulama veya bileşen hizmetinden alınan ölçümleri tek bir panoda birleştirin. Power BI için Application Insights içerik paketinin ilk sürümünde kullanım ile ilgili yaygın ölçümlere (etkin kullanıcılar, sayfa görünümü, oturumlar, tarayıcı, ve işletim sistemi sürümü, kullanıcıların harita üzerindeki coğrafi dağılımı gibi) ilişkin pencere öğeleri bulunmaktadır.

[Power BI için Application Insights içerik paketine](https://app.powerbi.com/getdata/services/application-insights) bağlanın.

>[!NOTE]
>Bağlanabilmeniz için, Azure Preview Portal'daki uygulamanıza ilişkin Application Insights genel bakış dikey penceresine erişim gereklidir. Aşağıda, gereksinimlerle ilgili daha ayrıntılı bilgi verilmiştir.

## <a name="how-to-connect"></a>Bağlanma
1. Sol gezinti bölmesinin alt kısmındaki **Veri Al**'ı seçin.
   
    ![Veri Al düğmesi](media/service-connect-to-application-insights/pbi_getdata.png)
2. **Hizmetler** kutusundaki **Al** seçeneğini belirleyin.
   
    ![Hizmetler kutusundaki Al düğmesi](media/service-connect-to-application-insights/pbi_getservices.png)
3. **Application Insights** > **Al**'ı seçin.
   
    ![Application Insights içerik paketi](media/service-connect-to-application-insights/appinsights.png)
4. **Application Insights Resource Name** (Application Insights Kaynak Adı), **Resource Group** (Kaynak Grubu) ve **Subscription ID** (Abonelik Kimliği) de dahil olmak üzere bağlanmak istediğiniz uygulama ile ilgili bilgileri girin. Daha ayrıntılı bilgi için bkz. [Application Insights parametrelerinizi bulma](#FindingAppInsightsParams).
   
    ![Application Insights bağlantı iletişim kutusu](media/service-connect-to-application-insights/pbi_contpkappinsitconnectndialog.png)    
5. Bağlanmak için **Oturum Aç**'ı seçin ve karşınıza çıkan ekranlardaki yönergeleri uygulayın.
   
    ![Application Insights bağlantı oturum açma](media/service-connect-to-application-insights/pbi_contpkappinsitconnectn2.png)
6. İçeri aktarma işlemi otomatik olarak başlar. İşlem tamamlandığında bir bildirim gösterilir ve Gezinti Bölmesinde yeni bir pano, rapor ve veri kümesi (yıldız işaretiyle birlikte) görünür.  İçeri aktarılan verilerinizi görüntülemek için panoyu seçin.
   
    ![Application Insights panosu](media/service-connect-to-application-insights/pbi_contpkappinsitdash.png)

**Sırada ne var?**

* Panonun üst tarafındaki [Soru-Cevap kutusunda soru sormayı](power-bi-q-and-a.md) deneyin
* Panodaki [kutucukları değiştirin](service-dashboard-edit-tile.md).
* Bağlantılı raporu açmak için [bir kutucuk seçin](service-dashboard-tiles.md).
* Veri kümeniz günlük olarak yenilenecek şekilde zamanlanır ancak yenileme zamanlamasında değişiklik yapabilir veya **Şimdi Yenile** seçeneğini kullanarak istediğinizde veri kümenizi kendiniz de yenileyebilirsiniz

## <a name="whats-included"></a>Neleri kapsar?
Application Insights içerik paketi, aşağıdaki tablo ve ölçümleri içerir:  

    ´´´
    - ApplicationDetails  
    - UniqueUsersLast7Days   
    - UniqueUsersLast30Days   
    - UniqueUsersDailyLast30Days  
    - UniqueUsersByCountryLast7Days  
    - UniqueUsersByCountryLast30Days   
    - PageViewsDailyLast30Days   
    - SessionsLast7Days   
    - SessionsLast30Days  
    - PageViewsByBrowserVersionDailyLast30Days   
    - UniqueUsersByOperatingSystemLast7Days   
    - UniqueUsersByOperatingSystemLast30Days    
    - SessionsDailyLast30Days   
    - SessionsByCountryLast7Days   
    - SessionsByCountryLast30Days   
    - PageViewsByCountryDailyLast30Days  
    ´´´ 

<a name="FindingAppInsightsParams"></a>

## <a name="finding-parameters"></a>Parametreleri bulma
Kaynak Adı, Kaynak Grubu ve Abonelik Kimliği bilgilerinizin tamamını Azure Portal'da bulabilirsiniz. Ad'ı seçtiğinizde ayrıntılı bir görünüm açılır ve ihtiyacınız olan tüm değerleri bulmak için Temel Parçalar açılan listesini kullanabilirsiniz.

![Application Insights parametreleri](media/service-connect-to-application-insights/pbi_contpkappinsitparams.png)

Bu değerleri kopyalayıp Power BI'daki alanlara yapıştırın:

![Application Insights parametreleri](media/service-connect-to-application-insights/pbi_contpkappinsitparam2.png)

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile çalışmaya başlama](service-get-started.md)

[Power BI'da veri alma](service-get-data.md)

