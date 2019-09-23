---
title: Bir Power BI görselinden verileri dışarı aktarma
description: Bir rapor görselindeki ve pano görselindeki verileri dışarı aktarıp Excel'de görüntüleyin.
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: jtlLGRKBvXY
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 09/11/2019
ms.author: mihart
LocalizationGroup: Consumers
ms.openlocfilehash: 3ab3b7a96fb629b303263b1ccf5c2f31603300b4
ms.sourcegitcommit: a97c0c34f888e44abf4c9aa657ec9463a32be06f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2019
ms.locfileid: "71073144"
---
# <a name="export-data-from-a-visual"></a>Bir görseldeki verileri dışarı aktarma
Bir görselin oluşturulması için kullanılan verileri görmek isterseniz [söz konusu verileri Power BI’da görüntüleyebilir](end-user-show-data.md) ya da bir Excel'e aktarabilirsiniz. Verileri dışarı aktarma seçeneği belirli bir tür veya lisansa ek olarak veri kümesi ve rapor için düzenleme izinleri gerektirir. Dışarı aktaramıyorsanız, Power BI yöneticinizle iletişime geçin. 

## <a name="from-a-visual-on-a-power-bi-dashboard"></a>Bir Power BI panosunda bulunan görselden

1. Bir Power BI panosu başlatın. Burada ***Pazarlama ve satış örneği*** uygulamasındaki panoyu kullanacağız. Bu uygulamayı [AppSource.com adresinden indirebilirsiniz](https://appsource.microsoft.com/en-us/product/power-bi/microsoft-retail-analysis-sample.salesandmarketingsample-preview?flightCodes=e2b06c7a-a438-4d99-9eb6-4324ce87f282).

    ![Uygulama panosu](media/end-user-export/power-bi-dashboards.png)

2. Bir görselin üzerine gelerek üç nokta (...) seçeneğini görüntüleyin ve tıklayarak eylem menüsünü gösterin.

    ![Üç nokta seçildiğinde görünen menü](media/end-user-export/power-bi-action-menu.png)

3. **Excel'e Aktar**’ı seçin.

4. Bundan sonra ne olacağı, kullandığınız tarayıcıya bağlıdır. Dosyayı kaydetmeniz istenebilir veya tarayıcının altında dışarı aktarılmış dosyanın bir bağlantısını görebilirsiniz. 

    ![Dışarı aktarılmış dosya bağlantısını gösteren Chrome tarayıcısı](media/end-user-export/power-bi-dashboard-exports.png)

5. Dosyayı Excel'de açın.  

    ![Excel’de Yılbaşından Bugüne Toplam Birim Sayısı](media/end-user-export/power-bi-excel.png)


## <a name="from-a-visual-in-a-report"></a>Bir raporda bulunan görselden
Bir rapordaki görselden verileri .csv veya .xlsx (Excel) biçiminde dışarı aktarabilirsiniz. 

1. Bir panoda, temel alınan raporu açmak için kutucuk seçin.  Bu örnekte, yukarıdakiyle aynı görseli seçiyoruz, *Yılbaşından Bugüne Toplam Birimler Var %* . 

    ![Vurgulanan pano kutucuğu](media/end-user-export/power-bi-export-reports.png)

    Bu kutucuk *Satış ve Pazarlama Örneği* raporundan oluşturulduğu için bu rapor açılır. Ayrıca, seçili kutucuk görselini içeren sayfada açılır. 

2. Rapordaki kutucuğu seçin. Sağ taraftaki **Filtreler** bölmesine dikkat edin. Bu görsele filtreler uygulanmıştır. Filtreler hakkında daha fazla bilgi için bkz. [Raporda filtre kullanma](end-user-report-filter.md).

    ![Filtre bölmesi seçildi](media/end-user-export/power-bi-export-filter.png)


3. Görselleştirmenin sağ üst köşesinde bulunan üç nokta simgesini seçin. **Verileri dışarı aktar** seçeneğini belirleyin.

    ![Açılan menüden seçilen Verileri dışarı aktar](media/end-user-export/power-bi-export-report.png)

4. Özetlenen verileri veya Temel alınan verileri dışarı aktarma seçeneklerini görürsünüz. *Satış ve pazarlama örneği* uygulamasını kullanıyorsanız, **Temel alınan veriler** devre dışı olacaktır. Ancak her iki seçeneğin de etkinleştirildiği raporlarla karşılaşabilirsiniz. Farkı hakkında bir açıklama aşağıda verilmiştir.

    **Özetlenmiş veriler**: Görselde gördükleriniz için verileri dışarı aktarmak istiyorsanız bu seçeneği belirtin.  Bu tür bir dışarı aktarma işlemi size yalnızca görseli oluşturmak için kullanılan verileri gösterir. Görselde uygulanmış filtreler varsa, dışarı aktardığınız veriler de filtrelenecektir. Örneğin, bu görsel için dışa aktarma işlemi yalnızca 2014 ve merkezi bölgenin verilerini ve yalnızca dört üreticinin verilerini içerir: VanArsdel, Natura, Aliqui ve Pirum.
  

    **Temel alınan veriler**: Görselde gördüklerinize **ek olarak** temel alınan veri kümesinden ek verileri dışarı aktarmak istiyorsanız bu seçeneği belirleyin.  Buna veri kümesinde bulunmasına karşın görselde kullanılmayan veriler dahil olabilir. 

    ![Temel alınan veya özetlenmiş verileri seçtiğiniz menü](media/end-user-export/power-bi-export-option.png)

5. Bundan sonra ne olacağı, kullandığınız tarayıcıya bağlıdır. Dosyayı kaydetmeniz istenebilir veya tarayıcının altında dışarı aktarılmış dosyanın bir bağlantısını görebilirsiniz. 

    ![Microsoft Edge tarayıcısında dışarı aktarılan dosya görüntüleme](media/end-user-export/power-bi-export-edge-browser.png)


6. Dosyayı Excel'de açın. Dışarı aktarılan veri miktarını, panodaki aynı görselden dışarı aktardığımız verilerle karşılaştırın. Fark, bu dışarı aktarmanın **Temel alınan verileri** içermesidir. 

    ![Örnek Excel](media/end-user-export/power-bi-underlying.png)

## <a name="next-steps"></a>Sonraki adımlar

[Görsel oluşturmak için kullanılan verileri görüntüleme](end-user-show-data.md)