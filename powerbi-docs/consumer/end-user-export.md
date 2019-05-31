---
title: Bir Power BI görselinden verileri dışarı aktarma
description: Bir rapor görseli ve Pano görsel verileri dışarı aktarma ve Excel'de görüntüleyebilirsiniz.
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: jtlLGRKBvXY
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 4/9/2019
ms.author: mihart
LocalizationGroup: Consumers
ms.openlocfilehash: d4384db8e05a69b138e76377e7c7b845867fa881
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "61063858"
---
# <a name="export-data-from-visual"></a>Visual Studio'dan verileri dışarı aktarma
Bir görseli oluşturmak için kullanılan verileri görmek istiyorsanız, [söz konusu verileri Power BI'da görüntüleyebilir](end-user-show-data.md) veya bu verileri Excel'e aktarabilirsiniz. Verileri dışarı aktarma seçeneği, belirli bir tür veya lisansı gerektirir ve içerik izinlerini düzenleyin. Dışarı aktaramadığınız, Power BI yöneticinizle birlikte denetleyin. 

## <a name="from-a-visual-on-a-power-bi-dashboard"></a>Power BI panosunda bir Görselden

1. Power BI panosunda başlatın. Panodan burada kullandığımız ***pazarlama ve satış örnek*** uygulama. Yapabilecekleriniz [bu uygulamayı AppSource.com ' indirin](https://appsource.microsoft.com/en-us/product/power-bi/microsoft-retail-analysis-sample.salesandmarketingsample-preview?flightCodes=e2b06c7a-a438-4d99-9eb6-4324ce87f282).

    ![](media/end-user-export/power-bi-dashboard.png)

2. Üç nokta (...) açığa çıkarmak için bir görselin üzerine gelin ve Eylem menüsünü görüntülemek için tıklayın.

    ![](media/end-user-export/power-bi-dashboard-export-visual.png)

3. Seçin **Excel'e**.

4. Sonraki işlemin ne kullanmakta olduğunuz tarayıcı üzerinde bağlıdır. Dosya ya da, Mayıs kaydetmek için istenebilir tarayıcı alt kısmındaki dışarı aktarılan dosyanın bir bağlantısını bakın. 

    ![](media/end-user-export/power-bi-export-browser.png)

5. Dosyayı Excel'de açın.  

    ![](media/end-user-export/power-bi-excel.png)


## <a name="from-a-visual-in-a-report"></a>Bir rapordaki bir Görselden
Verileri bir rapordaki bir görseldeki .csv veya .xlsx (Excel) olarak dışarı aktarabilirsiniz biçimi. 

1. Bir Panoda bağlantılı raporu açmak için bir kutucuk seçin.  Bu örnekte biz aynı görsel olarak yukarıdaki seçeneğini belirliyoruz *toplam birimler YTD Var %* . 

    ![](media/end-user-export/power-bi-export-report.png)

    Bu kutucuk oluşturulduktan sonra *satış ve pazarlama örneği* açar raporun oluşturulduğu rapor. Ve seçili döşemeyi görseli içeren sayfa açılır. 

2. Raporda kutucuğu seçin. Bildirim **filtreleri** sağ bölmesinde. Bu görsele uygulanan filtreler sahiptir. Filtreler hakkında daha fazla bilgi edinmek için [rapor filtrelerini kullanma](end-user-report-filter.md).

    ![](media/end-user-export/power-bi-export-filters.png)


3. Görselleştirmenin sağ üst köşesinde bulunan üç nokta simgesini seçin. Seçin **verileri dışarı aktar**.

    ![](media/end-user-export/power-bi-export-report2.png)

4. Summarized veya temel verilerini dışarı aktarmak için seçenekler görürsünüz. Kullanıyorsanız *satış ve pazarlama örneği* uygulamayı **temel alınan veriler** devre dışı bırakılır. Ancak, burada iki seçenek de etkin raporları karşılaşabilirsiniz. Fark açıklaması aşağıda verilmiştir.

    **Özetlenmiş veriler**: görselde görmek için verileri dışarı aktarmak istiyorsanız bu seçeneği belirleyin.  Bu tür bir dışarı aktarma, görseli oluşturmak için kullanılan verileri gösterir. Görsel uygulanan filtreler varsa, verdiğiniz veri da filtrelenir. Örneğin, bu görsel için yalnızca 2014 için veri ve orta bölgesinde ve dört üreticileri için yalnızca veri dışa aktarma içerecek: VanArsdel, Natura, Aliqui ve Prirum.
  

    **Temel alınan veriler**: görselde görmek için verileri dışarı aktarmak istiyorsanız bu seçeneği **artı** temel alınan veri kümesine ilişkin ek veriler.  Bu veri kümesinde yer alan ancak görselde kullanılmayan verileri içerebilir. 

    ![](media/end-user-export/power-bi-export-report3.png)

5. Sonraki işlemin ne kullanmakta olduğunuz tarayıcı üzerinde bağlıdır. Dosya ya da, Mayıs kaydetmek için istenebilir tarayıcı alt kısmındaki dışarı aktarılan dosyanın bir bağlantısını bakın. 

    ![](media/end-user-export/power-bi-export-edge.png)


7. Dosyayı Excel'de açın. Biz Panoda aynı görseli öğesinden dışarı aktarılan verileri dışarı veri miktarı karşılaştırın. Bu dışarı aktarma içerdiğini fark **temel alınan veriler**. 

    ![](media/end-user-export/power-bi-underlying.png)

