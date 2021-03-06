---
title: Power BI Sorgu Düzenleyicisi'nde Python kullanma
description: Gelişmiş analiz için Power BI Desktop Sorgu Düzenleyicisi'nde Python kullanma
author: otarb
ms.author: otarb
ms.reviewer: ''
ms.service: powerbi
ms.subservice: pbi-data-sources
ms.topic: how-to
ms.date: 06/18/2018
LocalizationGroup: Connect to data
ms.openlocfilehash: fac0b396abd6cde87e7e3b738e53480ce34eba88
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96405181"
---
# <a name="use-python-in-query-editor"></a>Sorgu Düzenleyicisi'nde Python kullanma
İstatistik uzmanları, veri bilimciler ve veri analistleri tarafından yaygın olarak kullanılan bir programlama dili olan **Python**, Power BI Desktop'taki **Sorgu Düzenleyicisi**'nde kullanılabilir. Python programlama dilinin **Sorgu Düzenleyicisi** ile bu şekilde tümleştirilmesi, Python kullanarak veri temizlemenin yanı sıra veri kümelerinde eksik verilerin tamamlanması, tahminler ve kümeleme gibi gelişmiş veri şekillendirme ve analiz işlemleri gerçekleştirmenize olanak sağlar. **Python** güçlü bir dildir ve bu dili veri modelinizi hazırlamanın yanı sıra raporlar oluşturmak için **Sorgu Düzenleyicisi**'nde kullanabilirsiniz.

## <a name="installing-python"></a>Python yükleme
**Python** programlama dilini Power BI Desktop'taki **Sorgu Düzenleyicisi**'nde kullanabilmek için yerel makinenize **Python**'ı yüklemeniz gerekir. **Python**’ı [Resmi Python indirme sayfası](https://www.python.org/) ve [Anaconda](https://anaconda.org/anaconda/python/) da dahil olmak üzere birçok konumdan ücretsiz olarak indirim yükleyebilirsiniz.

## <a name="using-python-in-query-editor"></a>Sorgu Düzenleyicisi'nde Python Kullanma
**Python** programlama dilinin **Sorgu Düzenleyicisi**’nde nasıl kullanılacağını göstermek için, birlikte ilerleyebilmek üzere [buradan indirebileceğiniz](https://download.microsoft.com/download/F/8/A/F8AA9DC9-8545-4AAE-9305-27AD1D01DC03/EuStockMarkets_NA.csv) bir .CSV dosyasını temel alan borsa veri kümesinden alınmış örnekten yararlanacağız. Bu örneğe yönelik adımlar aşağıda verilmiştir:

1. Öncelikle verilerinizi **Power BI Desktop**'a yükleyin. Bu örnekte, *EuStockMarkets_NA.csv* dosyasını yükleyin ve **Power BI Desktop**’taki **Giriş** şeridinden **Veri Al > CSV** seçeneğini belirleyin.
   
   ![CSV seçimini gösteren, Power BI Desktop’taki Veri Al şeridinin ekran görüntüsü.](media/desktop-python-in-query-editor/python-in-query-editor-1.png)
2. Dosyayı seçip **Aç** seçeneğini belirlediğinizde, CSV, **CSV dosyası** iletişim kutusunda görüntülenir.
   
   ![Seçili CSV’yi gösteren CSV dosyası iletişim kutusunun ekran görüntüsü.](media/desktop-python-in-query-editor/python-in-query-editor-2.png)
3. Veriler yüklendikten sonra CSV, Power BI Desktop'taki **Alanlar** bölmesinde yer alır.
   
   ![Yüklenmiş verileri gösteren Alanlar bölmesinin ekran görüntüsü.](media/desktop-python-in-query-editor/python-in-query-editor-3.png)
4. **Power BI Desktop**'taki **Giriş** sekmesinde bulunan **Sorguları Düzenle** seçeneğini belirleyerek **Sorgu Düzenleyicisi**'ni açın.
   
   ![Sorguları Düzenle seçimini gösteren, Power BI Desktop’taki Sorgu Düzenleyicisi’nin ekran görüntüsü.](media/desktop-python-in-query-editor/python-in-query-editor-4.png)
5. **Dönüştür** sekmesinde, **Python Betiğini Çalıştır** seçeneğini belirleyerek **Python Betiğini Çalıştır** düzenleyicisini görüntüleyin. (Bir sonraki adımda gösterilmiştir.) Tıpkı aşağıdaki görüntüde göremediğiniz diğer satırlar gibi, 15 ve 20 numaralı satırlar için eksik veri sorununun gözlemlendiğine dikkat edin. Söz konusu satırların Python tarafından nasıl doldurulabildiği (veya doldurulacağı) aşağıdaki adımlarda gösterilmiştir.
   
   ![Veri satırlarını gösteren Dönüştür sekmesinin ekran görüntüsü.](media/desktop-python-in-query-editor/python-in-query-editor-5.png)
6. Bu örnek için aşağıdaki betik kodunu gireceğiz:
   
    ```python
       import pandas as pd
       completedData = dataset.fillna(method='backfill', inplace=False)
       dataset["completedValues"] =  completedData["SMI missing values"]
   ```

   > [!NOTE]
   > Önceki betik kodunuzun düzgün bir şekilde çalışması için Python ortamınızda *pandas* kitaplığının yüklü olması gerekir. Pandas'ı yüklemek için Python yüklemenizde şu komutu çalıştırın: |      > pip install pandas
   > 
   > 
   
   **Python Betiğini Çalıştır** iletişim kutusuna yerleştirilen kod aşağıdaki gibi görünür:
   
   ![Betik kodunu gösteren Python betiğini çalıştır iletişim kutusunun ekran görüntüsü.](media/desktop-python-in-query-editor/python-in-query-editor-5b.png)
7. **Tamam**’ı seçmemizin ardından **Sorgu Düzenleyicisi**, veri gizliliği ile ilgili bir uyarı görüntüler.
   
   ![Veri gizliliği hakkında uyarı gösteren Sorgu Düzenleyicisi bölmesinin ekran görüntüsü.](media/desktop-python-in-query-editor/python-in-query-editor-6.png)
8. Python betiklerinin Power BI hizmetinde düzgün bir şekilde çalışabilmesi için, tüm veri kaynaklarının *genel* olarak ayarlanması gerekir. Gizlilik ayarları ve etkileri hakkında daha fazla bilgi için bkz. [Gizlilik Düzeyleri](../admin/desktop-privacy-levels.md).
   
   ![Genel olarak ayarlandığını gösteren Gizlilik düzeyleri iletişim kutusunun ekran görüntüsü.](media/desktop-python-in-query-editor/python-in-query-editor-7.png)
   
   **Alanlar** bölmesinde *completedValues* adlı yeni bir sütunla karşılaşırız. 15 ve 18 numaralı satırlar gibi birkaç eksik veri öğesinin bulunduğuna dikkat edin. Bu sorunun Python tarafından nasıl giderildiğini bir sonraki bölümde görebilirsiniz.
   

Yalnızca beş Python betiği satırı sayesinde **Sorgu Düzenleyicisi**, eksik değerleri bir tahmin modeli ile doldurur.

## <a name="creating-visuals-from-python-script-data"></a>Python betiği verilerinden görseller oluşturma
Artık Python betik kodunun *pandas* kitaplığını kullanarak eksik değerleri aşağıdaki görüntüde gösterildiği gibi nasıl tamamladığını görmek için bir görsel oluşturabiliriz:

![Özgün verileri ve Pandas kitaplığındaki eksik değerlerin tamamlanmış halini gösteren görselin ekran görüntüsü.](media/desktop-python-in-query-editor/python-in-query-editor-8.png)

Söz konusu görsel ve **Power BI Desktop**’ı kullanarak oluşturmak isteyebileceğimiz diğer görseller tamamlandıktan sonra, içerdiği Python betikleriyle birlikte **Power BI Desktop** dosyasını (.pbix dosyası olarak kaydedilen) kaydedebilir ve Power BI hizmetinde kullanabilirsiniz.

> [!NOTE]
> Bu adımlar uygulandığında elde edilen bir .pbix dosyasının nasıl göründüğünü merak ediyor musunuz? Şanslısınız. Bu örneklerde kullanılan tamamlanmış **Power BI Desktop** dosyasını [buradan](https://download.microsoft.com/download/A/B/C/ABCF5589-B88F-49D4-ADEB-4A623589FC09/Complete%20Values%20with%20Python%20in%20PQ.pbix) indirebilirsiniz.

.pbix dosyasını Power BI hizmetine yüklemenizin ardından, veri yenilemeye (hizmette) ve görsellerin hizmette güncelleştirilmesine (görsellerin güncelleştirilmesi için verilerin Python'a erişmesi gerekir) olanak sağlamak için uygulamanız gereken birkaç adım daha kalır. Bu adımlar aşağıda verilmiştir:

* **Veri kümesi için zamanlanmış yenilemeyi etkinleştirme**: Python betiklerinizi içeren veri kümenizin bulunduğu çalışma kitabı için zamanlanmış yenilemeyi etkinleştirmek için, **Personal Gateway** ile ilgili bilgiler de sunan [Zamanlanmış yenileme yapılandırma](refresh-scheduled-refresh.md) makalesine bakın.
* **Personal Gateway'i yükleme**: Dosyanın bulunduğu ve Python'ın yüklü olduğu konuma bir **Personal Gateway** yüklenmesi gerekir; Power BI hizmetinin söz konusu çalışma kitabına erişmesi ve güncelleştirilen görselleri yeniden işlemesi gerekir. [Personal Gateway yükleme ve yapılandırma](service-gateway-personal-mode.md) hakkında daha fazla bilgi edinebilirsiniz.

## <a name="limitations"></a>Sınırlamalar
Python betikleri içeren ve **Sorgu Düzenleyicisi**'nde oluşturulmuş sorgulara yönelik bazı sınırlamalar bulunur:

* Tüm Python veri kaynağı ayarlarının *Genel* olarak belirlenmesi ve **Sorgu Düzenleyicisi**'nde oluşturulmuş tüm diğer adımların da genel olarak ayarlanması gerekir. Veri kaynağı ayarlarına ulaşmak için, **Power BI Desktop**'ta **Dosya > Seçenekler ve ayarlar > Veri kaynağı ayarları** seçeneğini belirleyin.
  
  ![Veri kaynağı ayarları seçimini gösteren, Power BI Desktop’taki Dosya menüsünün ekran görüntüsü.](media/desktop-python-in-query-editor/python-in-query-editor-9.png)
  
  **Veri Kaynağı Ayarları** iletişim kutusunda, veri kaynaklarını seçin ve ardından **İzinleri Düzenle...** seçeneğini belirleyip **Gizlilik Düzeyi** ayarının *Genel* olarak seçildiğinden emin olun.
  
  ![Gizlilik Düzeyi’nin Genel olarak ayarlandığını gösteren Veri kaynağı ayarları iletişim kutusunun ekran görüntüsü.](media/desktop-python-in-query-editor/python-in-query-editor-10.png)    
* Python görselleriniz veya veri kümeniz için zamanlanmış yenilemeyi etkinleştirmek üzere, **Zamanlanmış yenileme** özelliğini etkinleştirmeniz ve çalışma kitabı ile Python yüklemesinin bulunduğu bilgisayara **Personal Gateway** yüklemeniz gerekir. Her iki konuya yönelik daha fazla bilgi için, bu makaledeki, daha fazla bilgi edinmeye yönelik bağlantıların sunulduğu önceki bölüme bakın.
* İç içe yerleştirilmiş tablolar (tabloların tablosu) şu anda desteklenmemektedir 

Python ve özel sorgular ile çok çeşitli işlemler gerçekleştirebilirsiniz. Keşfetmeye devam edin ve verilerinizi tam da görünmelerini istediğiniz biçimde şekillendirin.
