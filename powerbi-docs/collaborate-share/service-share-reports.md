---
title: Power BI raporunu filtreleme ve paylaşma
description: Power BI raporuna filtre uygulamayı ve bu raporu kuruluşunuzdaki iş arkadaşlarınızla paylaşmayı öğrenin.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: lukaszp
featuredvideoid: 0tUwn8DHo3s
ms.service: powerbi
ms.subservice: pbi-collaborate-share
ms.topic: how-to
ms.date: 02/17/2021
LocalizationGroup: Share your work
ms.openlocfilehash: b29f44ec2dbf759f29aa3ef69173d0aa646347b3
ms.sourcegitcommit: fb408dfd39943dbec990a16bcf204671beb4f0aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/18/2021
ms.locfileid: "100655690"
---
# <a name="filter-and-share-a-power-bi-report"></a>Power BI raporunu filtreleme ve paylaşma
*Paylaşım*, kullanıcıların, panolarınıza ve raporlarınıza erişmesini sağlamanın iyi bir yoludur. Bir raporun filtrelenmiş bir sürümünü paylaşmak istediğinizde ne olur? Yalnızca belirli bir şehre, satış temsilcisine veya yıla ait verileri gösteren bir rapor istiyor olabilirsiniz. Bu makalede raporun nasıl filtrelendiği ve filtrelenmiş rapor sürümünün nasıl paylaşıldığı açıklanır. Filtrelenmiş raporu paylaşmanın bir diğer yolu da [rapor URL’sine sorgu parametreleri eklemektir](service-url-filters.md). Her iki durumda da alıcılar URL’yi ilk kez açtığında rapor filtrelenir. Rapordaki filtre seçimlerini temizleyebilirler.

![Rapor filtrelendi](media/service-share-reports/power-bi-share-filter-pane-report.png)

Power BI ayrıca [işbirliği yapmak ve raporlarınızı dağıtmak için başka yollar sunar](service-how-to-collaborate-distribute-dashboards-reports.md). Paylaşımda siz ve alıcılarınız için bir [Power BI Pro lisansı](../fundamentals/service-features-license-type.md) gereklidir veya içerik [Premium kapasitede](../admin/service-premium-what-is.md) olmalıdır. 

## <a name="follow-along-with-sample-data"></a>Örnek verilerle konuyu takip edin

Bu makalede Pazarlama ve Satış örneği şablon uygulamasını kullandık. Denemek ister misiniz? 

1. [Pazarlama ve Satış örneği şablon uygulamasını](https://appsource.microsoft.com/product/power-bi/microsoft-retail-analysis-sample.salesandmarketingsample?tab=Overview) yükleyin.
2. Uygulamayı seçin ve sonra da **Uygulamayı keşfet**’i seçin.

   ![Örnek verileri keşfedin](media/service-share-reports/power-bi-sample-explore-data.png)

3. Kalem simgesini seçerek, uygulamayı yüklediğiniz çalışma alanını açın.

    ![Uygulama düzenleme kalemi](media/service-share-reports/power-bi-edit-pencil-app.png)

4. Çalışma alanı içerik listesinde **Raporlar**’ı ve sonra da **Satış ve Pazarlama Örneği PBIX** raporunu seçin.

    ![Örnek raporu açın](media/service-share-reports/power-bi-open-sample-report.png)

    Artık konuyu takip etmeye hazırsınız.

## <a name="set-a-filter-in-the-report"></a>Raporda filtre ayarlama

[Düzenleme görünümünde](../consumer/end-user-reading-view.md) bir rapor açın ve filtre uygulayın.

Bu örnekte, Pazarlama ve Satış örneği şablon uygulamasının Yılbaşından Bugüne Kadar Kategori sayfasını, yalnızca **Region** değerinin **Central** değerine eşit olduğu değerleri gösterecek şekilde filtreliyoruz. 
 
![Rapor filtresi bölmesi](media/service-share-reports/power-bi-share-report-filter.png)

Raporu kaydedin.

## <a name="share-the-filtered-report"></a>Filtrelenmiş raporu paylaşma

1. **Paylaş**'ı seçin.

   ![Paylaş'ı seçme](media/service-share-reports/power-bi-share.png)

2. Bildirim yerine filtrelenmiş bağlantı gönderebilmek için **Alıcılara e-posta bildirimi gönder** seçeneğini temizleyin, **Geçerli filtreler ve dilimleyicilerle raporu paylaş**’ı ve sonra da **Paylaş**’ı seçin.

    ![Raporu filtrelerle paylaşma](media/service-share-reports/power-bi-share-with-filters.png)

4. Yeniden **Paylaş**'ı seçin.

   ![Paylaş'ı seçme](media/service-share-reports/power-bi-share.png)

5. **Erişim** sekmesini ve ardından **Paylaşılan rapor görünümlerini yönet**’i seçin.

    ![Paylaşılan rapor görünümlerini yönetin](media/service-share-reports/power-bi-manage-shared-report-views.png)

6. İstediğiniz URL’ye sağ tıklayın ve **Bağlantıyı kopyala**’yı seçin.

    ![Filtrelenmiş bağlantıyı kopyalayın](media/service-share-reports/power-bi-copy-filtered-link.png)

7. Bu bağlantıyı paylaştığınızda alıcılar filtrelenmiş raporunuzu görecektir. 

## <a name="limitations-and-considerations"></a>Sınırlamalar ve önemli noktalar
Raporları paylaşma ile ilgili olarak dikkat edilmesi gerekenler:

* İzinleri yöneterek, rapor veya panoları paylaşarak ya da uygulama yayımlayarak bir veri kümesi paylaştığınızda, [satır düzeyi güvenlik (RLS)](../admin/service-admin-rls.md) tarafından erişimleri sınırlanmadığı sürece tüm veri kümesine erişim vermiş olursunuz. Rapor yazarları, raporları görüntüleyip bunlarla etkileşim kurarken sütunları gizleme, görsellerdeki eylemleri sınırlandırma ve diğerleri gibi kullanıcı deneyimini özelleştiren özellikleri kullanabilir. Bu özelleştirilmiş kullanıcı deneyimleri, veri kümesinde hangi veri erişiminin erişebileceğini kısıtlamaz. Her bir kullanıcının kimlik bilgilerinin erişebilecekleri verileri belirlemesini sağlamak için veri kümesinde [satır düzeyi güvenlik (RLS)](../admin/service-admin-rls.md) kullanın.
* 90 gün içinde paylaşılan rapor görünümü bağlantısına hiç kimse erişildiyse, bağlantı otomatik olarak sona erer.  

## <a name="next-steps"></a>Sonraki adımlar
* [Power BI'da çalışmanızı paylaşmanın yolları](service-how-to-collaborate-distribute-dashboards-reports.md)
* [Bir panoyu paylaşma](service-share-dashboards.md)
* Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/).
* Geri bildirimde bulunmak ister misiniz? [Power BI Topluluğu sitesine](https://community.powerbi.com/) giderek önerilerinizi belirtin.
