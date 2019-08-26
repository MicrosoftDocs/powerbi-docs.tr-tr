---
title: Power Sorgu Düzenleyicisi’nde R kullanma
description: Gelişmiş çözümleme için Power BI Desktop Sorgu Düzenleyicisi'nde R programlama dilini kullanma
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 08/14/2019
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: e2a970ecbf7b341d4feaba4e90a862841ba8bb17
ms.sourcegitcommit: f6ac9e25760561f49d4257a6335ca0f54ad2d22e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69560908"
---
# <a name="use-r-in-query-editor"></a>Sorgu Düzenleyicisi'nde R kullanma

[**R**](https://mran.microsoft.com/documents/what-is-r) birçok istatistikçi, veri bilimci ve veri analistinin kullandığı güçlü bir programlama dilidir. Power BI Desktop **Sorgu Düzenleyicisi**’nde **R** dilini kullanarak şunları yapabilirsiniz:

* Veri modelleri hazırlama

* Rapor oluşturma

* Veri temizleme, gelişmiş veri şekillendirme ve sksik veri tamamlama, tahminler, kümeleme ile daha fazlasını içeren veri kümesi analizi gerçekleştirin.  

## <a name="install-r"></a>R yükleme

**R**'yi [Revolution Open indirme sayfası](https://mran.revolutionanalytics.com/download/) ve [CRAN Repository](https://cran.r-project.org/bin/windows/base/)’den ücretsiz olarak indirebilirsiniz.

### <a name="install-mice"></a>Mice yükleme

R ortamınızda [**mice** kitaplığı](https://www.rdocumentation.org/packages/mice/versions/3.5.0/topics/mice) yüklü olmalıdır. **Mice** olmadan örnek betik kodu düzgün çalışmaz. **Mice** paketi eksik verilerle başa çıkmaya yönelik bir yöntem uygular.

**Mice** yüklemek için:

1. R.exe programını başlatın (örneğin, C:\Program Files\Microsoft\R Open\R-3.5.3\bin\R.exe)  

2. Yükleme komutunu çalıştırın:

   ``` 
   >  install.packages('mice') 
   ```

## <a name="use-r-in-query-editor"></a>Sorgu Düzenleyicisi'nde R kullanma

**Sorgu Düzenleyicisi**’nde **R** kullanmayı göstermek için bir .csv dosyasında yer alan örnek bir borsa veri kümesi kullanacak ve aşağıdaki adımları uygulayacağız:

1. [**EuStockMarkets_NA.csv** dosyasını indirin](http://download.microsoft.com/download/F/8/A/F8AA9DC9-8545-4AAE-9305-27AD1D01DC03/EuStockMarkets_NA.csv). Dosyayı kaydettiğiniz yeri unutmayın.

1. Dosyayı **Power BI Desktop**’a yükleyin: **Ana Sayfa** şeridinden **Veri Al > Metin/CSV** öğesini seçin.

   ![](media/desktop-r-in-query-editor/r-in-query-editor_1.png)

1. Dosyayı kaydedin ve sonra **Aç**’ı seçin. CSV verileri **Metin/CSV dosyası** iletişim kutusunda görüntülenir.

   ![](media/desktop-r-in-query-editor/r-in-query-editor_2.png)

1. Veriler yüklendikten sonra **Alanlar** bölmesinde görebilirsiniz.

   ![](media/desktop-r-in-query-editor/r-in-query-editor_3.png)

1. **Sorgu Düzenleyicisi**’ni açmak için **Ana Sayfa** şeridinden **Sorguları Düzenle**’yi seçin.

   ![](media/desktop-r-in-query-editor/r-in-query-editor_4.png)

1. **Dönüştür** şeridinde **R Betiğini Çalıştır** öğesini seçin. **R Betiğini Çalıştır** düzenleyicisi görüntülenir.  

   Satır 15 ve 20’de, resimde göremediğiniz diğer satırlarda olduğu gibi eksik veriler bulunmaktadır. Söz konusu satırların R tarafından nasıl doldurulduğu aşağıdaki adımlarda gösterilmiştir.

   ![](media/desktop-r-in-query-editor/r-in-query-editor_5d.png)

1. Bu örnek için aşağıdaki betik kodunu girin. '&lt;Your File Path&gt;' değerini yerel dosya sisteminizdeki **EuStockMarkets_NA.csv** yoluyla değiştirdiğinizden emin olun; örneğin, C:/Users/John Doe/Documents/Microsoft/EuStockMarkets_NA.csv

    ```r
       dataset <- read.csv(file="<Your File Path>/EuStockMarkets_NA.csv", header=TRUE, sep=",")
       library(mice)
       tempData <- mice(dataset,m=1,maxit=50,meth='pmm',seed=100)
       completedData <- complete(tempData,1)
       output <- dataset
       output$completedValues <- completedData$"SMI missing values"
    ```

7. **Tamam**’ı seçmemizin ardından **Sorgu Düzenleyicisi**, veri gizliliği ile ilgili bir uyarı görüntüler.

   ![](media/desktop-r-in-query-editor/r-in-query-editor_6.png)
8. R betiklerinin Power BI hizmetinde düzgün şekilde çalışması için, tüm veri kaynaklarının **genel** olarak ayarlanması gerekir. Gizlilik ayarları ve etkileri hakkında daha fazla bilgi için bkz. [Gizlilik Düzeyleri](desktop-privacy-levels.md).

   ![](media/desktop-r-in-query-editor/r-in-query-editor_7.png)

   **Kaydet**'i seçtikten sonra betik çalışır. **Alanlar** bölmesinde **completedValues** adlı yeni bir sütunla karşılaşırız. 15 ve 18 numaralı satırlar gibi birkaç eksik veri öğesinin bulunduğuna dikkat edin. Bu sorunun R tarafından nasıl giderildiğini bir sonraki bölümde görebilirsiniz.

   Yalnızca beş R betiği satırı sayesinde **Sorgu Düzenleyicisi**, eksik değerleri bir tahmin modeli ile doldurur.

## <a name="create-visuals-from-r-script-data"></a>R betik verilerinden görseller oluşturma

Artık R betik kodunun, **mice** kitaplığını kullanarak eksik değerleri aşağıdaki görüntüde gösterildiği gibi nasıl tamamladığını görmek için bir görsel oluşturabiliriz:

![](media/desktop-r-in-query-editor/r-in-query-editor_8a.png)

Tamamlanan tüm görselleri bir **Power BI Desktop** .pbix dosyasına kaydedebilir ve veri modeli ile R betiklerini Power BI hizmetinde kullanabilirsiniz.

> [!NOTE]
> Bu adımların hepsi tamamlandıktan sonra [bir .pbix dosyası indirebilirsiniz](http://download.microsoft.com/download/F/8/A/F8AA9DC9-8545-4AAE-9305-27AD1D01DC03/Complete%20Values%20with%20R%20in%20PQ.pbix).

.pbix dosyasını Power BI hizmetine yükledikten sonra, hizmet verilerini yenilemeyi ve güncelleştirilmiş görselleri etkinleştirmek için ilave adımlar uygulamanız gerekir:  

* **Veri kümesi için zamanlanmış yenilemeyi etkinleştirme**: R betiklerinizi içeren veri kümenizin bulunduğu çalışma kitabı için zamanlanmış yenilemeyi etkinleştirmek için, **Kişisel Ağ Geçidi** ile ilgili bilgiler de sunan [Zamanlanmış yenileme yapılandırma](refresh-scheduled-refresh.md) makalesine bakın.

* **Kişisel Ağ Geçidi yükleme** - Dosya ve **R**’nin bulunduğu makinede bir **Kişisel Ağ Geçidi** yüklü olmalıdır. Power BI hizmeti, bu çalışma kitabına erişir ve güncelleştirilmiş görselleri yeniden oluşturur. Daha fazla bilgi için bkz. [Kişisel Ağ Geçidi yükleme ve yapılandırma](service-gateway-personal-mode.md).

## <a name="limitations"></a>Sınırlamalar

R betikleri içeren ve **Sorgu Düzenleyicisi**'nde oluşturulmuş sorgulara yönelik bazı sınırlamalar bulunur:

* Tüm R veri kaynağı ayarlarının **Genel** olarak ayarlanması gerekir. Bir **Sorgu Düzenleyicisi**’ndeki diğer tüm adımlar da genel olmalıdır. Veri kaynağı ayarlarına ulaşmak için, **Power BI Desktop**'ta **Dosya > Seçenekler ve ayarlar > Veri kaynağı ayarları** seçeneğini belirleyin.

  ![](media/desktop-r-in-query-editor/r-in-query-editor_9.png)

  **Veri Kaynağı Ayarları** iletişim kutusunda veri kaynaklarını ve sonra **İzinleri Düzenle...** öğesini seçin.  **Gizlilik Düzeyi**’ni **Genel** olarak ayarlayın.

  ![](media/desktop-r-in-query-editor/r-in-query-editor_10.png)    
* R görselleriniz veya veri kümeniz için zamanlanmış yenilemeyi etkinleştirmek üzere **Zamanlanmış yenileme** seçeneğini etkinleştirmeniz ve çalışma kitabı ile **R** yüklemesinin bulunduğu bilgisayara **Kişisel Ağ Geçidi** yüklemeniz gerekir. Her iki konuya yönelik daha fazla bilgi için, bu makaledeki, daha fazla bilgi edinmeye yönelik bağlantıların sunulduğu önceki bölüme bakın.

R ve özel sorgular ile çok çeşitli işlemler gerçekleştirebilirsiniz. Keşfetmeye devam edin ve verilerinizi tam da görünmelerini istediğiniz biçimde şekillendirin.

## <a name="next-steps"></a>Sonraki Adımlar

* [R’ye giriş](https://mran.microsoft.com/documents/what-is-r) 

* [Power BI Desktop'ta R betikleri çalıştırma](desktop-r-scripts.md) 

* [Power BI ile harici bir R IDE kullanma](desktop-r-ide.md) 

* [Power BI hizmetindeki R paketleri](service-r-packages-support.md)
