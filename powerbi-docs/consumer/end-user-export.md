---
title: Bir Power BI görselinden verileri dışarı aktarma
description: Bir rapor görselindeki ve pano görselindeki verileri dışarı aktarıp Excel'de görüntüleyin.
author: mihart
ms.reviewer: cmfinlan
featuredvideoid: jtlLGRKBvXY
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 02/20/2020
ms.author: mihart
LocalizationGroup: Consumers
ms.openlocfilehash: 6f653bd14f71d0d8409dbb8c3653515198cc6c40
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83279469"
---
# <a name="export-data-from-a-visual"></a>Bir görseldeki verileri dışarı aktarma

[!INCLUDE[consumer-appliesto-yyny](../includes/consumer-appliesto-yyny.md)]

[!INCLUDE [power-bi-service-new-look-include](../includes/power-bi-service-new-look-include.md)]

Bir görselin oluşturulması için kullanılan verileri görmek isterseniz [söz konusu verileri Power BI’da görüntüleyebilir](end-user-show-data.md) ya da bir Excel'e aktarabilirsiniz. Verileri dışarı aktarma seçeneği belirli bir tür veya lisansa ek olarak veri kümesi ve rapor için düzenleme izinleri gerektirir. Dışarı aktaramıyorsanız, Power BI yöneticinizle iletişime geçin. Verileri dışarı aktarmak için Power BI Pro lisansına ihtiyacınız vardır. Bu kullanıcı başına Pro lisansı veya Premium kapasite lisansı olan bir kuruluşta kullanıcı başına Pro lisansı olabilir. Bu tür lisanslar genellikle rapor *tüketiciler* tarafından değil rapor *tasarımcıları* tarafından kullanılır. Daha fazla bilgi edinmek için bkz. [Hangi lisansa sahibim?](end-user-license.md).


## <a name="from-a-visual-on-a-power-bi-dashboard"></a>Bir Power BI panosunda bulunan görselden

1. Bir Power BI panosu başlatın. Burada ***Pazarlama ve satış örneği*** uygulamasındaki panoyu kullanacağız. Bu uygulamayı [AppSource.com adresinden indirebilirsiniz](https://appsource.microsoft.com/en-us/product/power-bi/microsoft-retail-analysis-sample.salesandmarketingsample
).

    ![Uygulama panosu](media/end-user-export/power-bi-dashboards.png)

2. Bir görselin üzerine gelerek **Diğer seçenekler** (...) seçeneğini ortaya çıkarın ve tıklayarak eylem menüsünü görüntüleyin.

    ![Üç nokta seçildiğinde görünen menü](media/end-user-export/power-bi-options-menu.png)

3. **CSV'ye Aktar**’ı seçin.

4. Bundan sonra ne olacağı, kullandığınız tarayıcıya bağlıdır. Dosyayı kaydetmeniz istenebilir veya tarayıcının altında dışarı aktarılmış dosyanın bir bağlantısını görebilirsiniz. 

    ![Dışarı aktarılmış dosya bağlantısını gösteren Chrome tarayıcısı](media/end-user-export/power-bi-dashboard-exports.png)

5. Dosyayı Excel'de açın. 

    > [!NOTE]
    > Veriler üzerinde izinleriniz yoksa, Excel'e dışarı aktaramaz veya Excel'de açamazsınız.  

    ![Excel’de Yılbaşından Bugüne Toplam Birim Sayısı](media/end-user-export/power-bi-excel.png)


## <a name="from-a-visual-in-a-report"></a>Bir raporda bulunan görselden
Bir rapordaki görselden verileri .csv veya .xlsx (Excel) biçiminde dışarı aktarabilirsiniz. 

1. Bir panoda, temel alınan raporu açmak için kutucuk seçin.  Bu örnekte, yukarıdakiyle aynı görseli seçiyoruz, *Yılbaşından Bugüne Toplam Birimler Var %* . 

    ![Vurgulanan pano kutucuğu](media/end-user-export/power-bi-export-reports.png)

    Bu kutucuk *Satış ve Pazarlama Örneği* raporundan oluşturulduğu için bu rapor açılır. Ayrıca, seçili kutucuk görselini içeren sayfada açılır. 

2. Raporda görseli seçin. Sağ taraftaki **Filtreler** bölmesine dikkat edin. Bu görsele filtreler uygulanmıştır. Filtreler hakkında daha fazla bilgi için bkz. [Raporda filtre kullanma](end-user-report-filter.md).

    ![Filtre bölmesi seçildi](media/end-user-export/power-bi-export-filter.png)


3. Görselleştirmenin sağ üst köşesinde **Diğer seçenekler (...)** öğesini seçin. **Verileri dışarı aktar** seçeneğini belirleyin.

    ![Açılan menüden seçilen Verileri dışarı aktar](media/end-user-export/power-bi-export-report.png)

4. Özetlenen verileri veya Temel alınan verileri dışarı aktarma seçeneklerini görürsünüz. *Satış ve pazarlama örneği* uygulamasını kullanıyorsanız, **Temel alınan veriler** devre dışı olacaktır. Ancak her iki seçeneğin de etkinleştirildiği raporlarla karşılaşabilirsiniz. Farkı hakkında bir açıklama aşağıda verilmiştir.

    **Özetlenmiş veriler**: Görselde şu anda gördükleriniz için verileri dışarı aktarmak istiyorsanız bu seçeneği belirtin.  Bu tür bir dışarı aktarma işlemi size yalnızca görselin şu anki durumunu oluşturmak için kullanılan verileri gösterir. Görselde uygulanmış filtreler varsa, dışarı aktardığınız veriler de filtrelenecektir. Örneğin, bu görsel için dışa aktarma işlemi yalnızca 2014 ve merkezi bölgenin verilerini ve yalnızca dört üreticinin verilerini içerir: VanArsdel, Natura, Aliqui ve Pirum. Görselinizin toplamaları (toplam, ortalama vb.) varsa, dışarı aktarma da toplanacaktır. 
  

    **Temel alınan veriler**: Görselde gördüklerinize **ek olarak** temel alınan veri kümesinden ek verileri dışarı aktarmak istiyorsanız bu seçeneği belirleyin.  Buna veri kümesinde bulunmasına karşın görselde kullanılmayan veriler dahil olabilir. Görselde uygulanmış filtreler varsa, dışarı aktardığınız veriler de filtrelenecektir.  Görselinizin toplamaları (toplam, ortalama vb.) varsa, dışarı aktarma işlemi toplamayı kaldırır; temelde verileri düzleştirir. 

    ![Temel alınan veya özetlenmiş verileri seçtiğiniz menü](media/end-user-export/power-bi-export-underlying.png)

5. Bundan sonra ne olacağı, kullandığınız tarayıcıya bağlıdır. Dosyayı kaydetmeniz istenebilir veya tarayıcının altında dışarı aktarılmış dosyanın bir bağlantısını görebilirsiniz. 

    ![Microsoft Edge tarayıcısında dışarı aktarılan dosya görüntüleme](media/end-user-export/power-bi-export-edge-browser.png)

    > [!NOTE]
    > Veriler üzerinde izinleriniz yoksa, Excel'e dışarı aktaramaz veya Excel'de açamazsınız.  


6. Dosyayı Excel'de açın. Dışarı aktarılan veri miktarını, panodaki aynı görselden dışarı aktardığımız verilerle karşılaştırın. Fark, bu dışarı aktarmanın **Temel alınan verileri** içermesidir. 

    ![Örnek Excel](media/end-user-export/power-bi-underlying.png)

## <a name="next-steps"></a>Sonraki adımlar

[Görsel oluşturmak için kullanılan verileri görüntüleme](end-user-show-data.md)