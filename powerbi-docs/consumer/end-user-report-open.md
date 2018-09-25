---
title: Power BI hizmetinde bir raporu Okuma görünümü veya Düzenleme görünümü'nde açma
description: Power BI raporunu Okuma görünümü veya Düzenleme görünümünde açma
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 05/18/2018
ms.author: mihart
ms.openlocfilehash: fe1916b2b287dffd59bf4535cc07e13d10d01321
ms.sourcegitcommit: 70192daf070ede3382ac13f6001e0c8b5fb8d934
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/22/2018
ms.locfileid: "46565809"
---
# <a name="open-a-report-in-power-bi-service-apppowerbicom"></a>Power BI hizmetinde (app.powerbi.com) bir raporu açma
Raporlar Power BI hizmeti, Power BI Desktop, Power BI Mobil ve hatta Power BI Embedded'da kullanılabilir. Bu makalede, raporları ***Power BI hizmetinde*** açma konusu ele alınmıştır.

Power BI hizmetinde raporları görüntülemek ve onlarla etkileşim kurmak için kullanabileceğiniz iki mod vardır: [Okuma görünümü ve Düzenleme görünümü](end-user-reading-view.md). Okuma görünümü, özellikle rapor *kullanıcıları* için tasarlanmıştır ve tüm kullanıcılar tarafından kullanılabilir; Düzenleme görünümü ise yalnızca rapor *oluşturucuları* ve rapor sahipleri tarafından kullanılabilir. 

## <a name="open-a-report-from-a-workspace-via-the-reports-content-view-list"></a>Bir raporu çalışma alanından açma (**Raporlar** içerik görünümü listesi aracılığıyla)

1. İşleme bir çalışma alanında başlayın ve tüm raporları görüntülemek için **Raporlar** sekmesini seçin.  
   
   ![Bir çalışma alanının raporlar sekmesi](./media/end-user-report-open/power-bi-open-report.png)
2. Rapor adını seçerek söz konusu raporu Okuma görünümü'nde açın.  
   
    ![Okuma görünümü’nde rapor](./media/end-user-report-open/power-bi-reading-view.png)
3. [Okuma Görünümü'nde yapabileceğiniz çok şey vardır](end-user-reading-view.md).  Bu örnek raporda birden fazla sayfa vardır. Bu nedenle rapor tuvalinin en altındaki sekmeleri keşfederek başlayabilirsiniz. 

## <a name="open-a-report-from-a-dashboard"></a>Bir raporu panodan açma
Raporu açmak için kullanabileceğiniz birçok yöntem vardır. Örneğin bir panodan başlayabilir ve rapordan oluşturulan bir kutucuğu seçebilirsiniz.  Bir kutucuğu seçtiğinizde rapor Okuma Görünümü'nde açılır. Birlikte ilerleyebilmek için, [Sales and Marketing Sample panosunu açın](../sample-datasets.md).

1. Bir pano açın ve kutucuk seçin.

   [Soru-Cevap ile oluşturulan](../service-dashboard-pin-tile-from-q-and-a.md) bir kutucuğu seçerseniz Soru-Cevap ekranı açılır. [Panodaki **Kutucuk ekle** pencere öğesi kullanılarak oluşturulan](../service-dashboard-add-widget.md) bir kutucuğu seçerseniz söz konusu pencere öğesini düzenleyebileceğiniz sihirbaz açılır.  

2.  Bu örnekte, "Total Units YTD..." sütun grafiği kutucuğunu seçmeyi tercih ettik.

    ![kutucuğun seçili olduğu pano](./media/end-user-report-open/power-bi-dashboard.png)

3.  İlişkili rapor Okuma görünümü'nde açılır. "YTD Category" adlı sayfada olduğumuza dikkat edin. Bu, panodan seçtiğimiz sütun grafiğinin yer aldığı rapor sayfasıdır.

    ![Okuma görünümü’nde açık rapor](./media/end-user-report-open/power-bi-report.png)

4. Okuma görünümü'nde kalın veya raporu Düzenleme görünümü'nde açmak için **Raporu düzenle** seçeneğini belirleyin. Raporun yalnızca düzenleme izinlerine sahip olan kullanıcılar tarafından Düzenleme görünümü'nde açılabileceğini unutmayın.

    ![Raporu düzenle simgesini gösteren rapor düzenleyicisi](./media/end-user-report-open/power-bi-edit-report.png)

## <a name="create-a-brand-new-report-from-a-dataset"></a>Bir veri kümesinden yepyeni bir rapor oluşturma
Bir raporu açmanın diğer bir yolu da bu işlem için veri kümelerini kullanmaktır. İşleme bir veri kümesinden başladığınızda boş bir rapor tuvali ile karşılaşırsınız. Bu nedenle bu yöntem, sahip oldukları veri kümesini temel alan yeni bir rapor oluşturmak isteyen rapor *oluşturucuları* için önerilir. Yukarıdaki örnekte olduğu gibi, birlikte ilerleyebilmek için [Sales and Marketing Sample uygulamasını](../sample-datasets.md) indirin.

1. İşleme bir raporun temelini oluşturacak şekilde kullanmak istediğiniz veri kümesini içeren çalışma alanından başlayın.

   ![Uygulama çalışma alanlarını görüntüleyen sol gezinti bölmesi](./media/end-user-report-open/power-bi-workspace.png)

2. Bu çalışma alanındaki tüm veri kümelerinin listesini görüntülemek için **Veri kümeleri** sekmesini seçin. Bu, **Veri kümeleri** içerik görünümü listesi olarak adlandırılır.
   
   ![veri kümeleri listesi](./media/end-user-report-open/power-bi-dataset.png)

1. Veri kümesini bulun ve veri kümesini Düzenleme görünümü'nde açmak için **Rapor oluştur** simgesini seçin. Bir veri kümesi için düzenleme izinlerine sahip değilseniz veri kümesini açamazsınız. 
   
    ![Rapor oluştur simgesinin bulunduğu veri kümesi](./media/end-user-report-open/power-bi-create-report.png)

3. Veri kümesi, rapor düzenleyicisinde açılır. Araştırmaya başlamanız ve görselleştirmeler oluşturmanız için kullanımınıza hazır olan veri alanları sağ tarafta görüntülenir. 

   ![rapor tuvali](./media/end-user-report-open/power-bi-blank-canvas.png)

##  <a name="still-more-ways-to-open-a-report"></a>Raporları açmak için kullanabileceğiniz yöntemler bunlarla sınırlı değildir
Power BI hizmetinde gezinme konusunda daha yetkin hale geldikçe sizin için en uygun iş akışlarını keşfedeceksiniz. Raporlara erişmek için kullanabileceğiniz diğer yöntemlerden bazıları aşağıda verilmiştir:
- Sol gezinti bölmesindeki **Sık Kullanılanlar**, **Son görüntülenen**, **Uygulamalar** ve **Benimle paylaşılan** sekmelerini kullanma. 
- [İlişkilileri görüntüle](end-user-related.md) seçeneğini kullanma
- Bir kullanıcı [sizinle paylaşımda bulunduğunda](../service-share-reports.md) veya [uyarı ayarladığınızda](../service-set-data-alerts.md) aldığınız e-postayı kullanma    
- [Bildirim merkezinizi](end-user-notification-center.md) kullanma    
- ve daha fazlası

## <a name="next-steps"></a>Sonraki adımlar
[Power BI'daki raporlar](end-user-reports.md) hakkında daha fazla bilgi edinin

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)  

