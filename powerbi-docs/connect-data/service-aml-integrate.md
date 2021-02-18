---
title: 'Öğretici: Power BI’da bir Azure Machine Learning modeli kullanma'
titleSuffix: Azure Machine Learning
description: Power BI’da bir Azure Machine Learning modeli kullanmayı öğrenin.
services: machine-learning
ms.service: machine-learning
ms.subservice: core
ms.topic: tutorial
ms.author: samkemp
author: samuel100
ms.reviewer: sdgilley, maggies
ms.date: 02/17/2021
ms.openlocfilehash: 91ba29a09cfdd434c52794e83651736c2b796b1e
ms.sourcegitcommit: fb408dfd39943dbec990a16bcf204671beb4f0aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/18/2021
ms.locfileid: "100655642"
---
# <a name="tutorial-consume-azure-machine-learning-models-in-power-bi"></a>Öğretici: Power BI’da Azure Machine Learning modellerini kullanma

Bu öğretici, makine öğrenmesi modelini temel alan bir Power BI raporu oluşturma konusunda size yol gösterir. Bu öğreticinin sonunda şunları yapabileceksiniz:

> [!div class="checklist"]
> * Power BI’da (Azure Machine Learning kullanılarak dağıtılan) makine öğrenmesi modellerini puanlama.
> * Power Query Düzenleyicisi'nde bir Azure Machine Learning modeline bağlanma.
> * Bu modeli temel alan ve görselleştirme içeren bir rapor oluşturma.
> * Bu raporu Power BI hizmetinde yayımlama.
> * Rapor için zamanlanmış yenileme ayarlama.

## <a name="prerequisites"></a>Önkoşullar

Bu öğreticiye başlamadan önce şunları yapmanız gerekir:

- Azure Machine Learning’de bir makine öğrenmesi modeli eğitme ve dağıtma. Aşağıdaki üç Azure Machine Learning öğreticisinden birini kullanın: 

    - [Seçenek A: Kod](/azure/machine-learning/tutorial-power-bi-custom-model)
    - [Seçenek B: Tasarımcı](/azure/machine-learning/tutorial-power-bi-designer-model)
    - [Seçenek C: Otomatik ML](/azure/machine-learning/tutorial-power-bi-automated-model)

- [Ücretsiz Power BI denemesine](https://app.powerbi.com/signupredirect?pbi_source=web) kaydolun.
- Yerel bir bilgisayara [Power BI Desktop uygulamasını yükleyin](https://powerbi.microsoft.com/desktop/).

## <a name="create-the-data-model"></a>Veri modelini oluşturma

Power BI Desktop'ı açın ve **Veri Al**'ı seçin. **Veri Al** iletişim kutusunda **web** terimini arayın. **Web** kaynağını ve **Bağlan**’ı seçin.

:::image type="content" source="media/service-aml-integrate/pbi-get-data.png" alt-text="Web verilerini gösteren ekran görüntüsü.":::

Aşağıdaki URL’yi kopyalayıp **Web’den** iletişim kutusuna yapıştırın:

```txt 
https://www4.stat.ncsu.edu/~boos/var.select/diabetes.tab.txt
```

:::image type="content" source="media/service-aml-integrate/pbi-data.png" alt-text="Web url’sini gösteren ekran görüntüsü.":::

**Tamam**’ı seçin.

**Access Web içeriği**' nde, **anonim**  >  **Bağlan**' ı seçin.

:::image type="content" source="media/service-aml-integrate/anonymous-access-web-content.png" alt-text="Web içeriği için anonim erişimi gösteren ekran görüntüsü.":::

**Power Query Düzenleyicisi** penceresini açmak için **Verileri dönüştür**’ü seçin.

Power Query Düzenleyicisi'nin Giriş şeridinde **Azure Machine Learning** düğmesini seçin.

:::image type="content" source="media/service-aml-integrate/aml-button.png" alt-text="Power Query Düzenleyicisi'ni gösteren ekran görüntüsü.":::

Çoklu oturum açmayı kullanarak Azure hesabınızda oturum açtıktan sonra, kullanılabilir hizmetlerin listesini görürsünüz. Makine öğrenmesi modelini eğitme ve dağıtma öğreticisinde oluşturduğunuz **my-sklearn-service** öğesini seçin. 

Power Query sütunları sizin için otomatik olarak doldurur. Hizmet şemamızda, girişleri belirten bir Python dekoratörünüz olduğunu unutmayın. **Tamam**’ı seçin.

:::image type="content" source="media/service-aml-integrate/aml-pbi-run.png" alt-text="Azure Machine Learning Modellerini gösteren ekran görüntüsü.":::

**Tamam** seçildiğinde Azure Machine Learning hizmeti çağrılır. Hem veriler hem de uç nokta için bir veri gizliliği uyarısını tetikler.

:::image type="content" source="media/service-aml-integrate/data_privacy_warning.png" alt-text="Gizlilik uyarısını gösteren ekran görüntüsü.":::

**Devam**’ı seçin. Sonraki ekranda **Bu dosya için Gizlilik Düzeyi denetimlerini yoksay** > **Kaydet**’i seçin.

Veriler puanlandıktan sonra Power Query **AzureML.my-diabetes-model** adlı ek bir sütun oluşturur.

:::image type="content" source="media/service-aml-integrate/scored-data.png" alt-text="Eklenen puanlanmış sütunu gösteren ekran görüntüsü.":::

Hizmetin döndürdüğü veriler **liste** biçimindedir. 

> [!NOTE]
> Tasarımcı modelini dağıttıysanız bir **kayıt** görürsünüz.

Tahminleri almak için, **AzureML.My-diabetes-model** sütun üst bilgisinde çift başlı oku seçin > **yeni satırlara genişletin**.

:::image type="content" source="media/service-aml-integrate/expand-column.png" alt-text="Sütunu genişlet simgesini gösteren ekran görüntüsü.":::

Genişlettikten sonra AzureML.my-diabetes-model sütununda tahminleri görürsünüz.

:::image type="content" source="media/service-aml-integrate/after-expand.png" alt-text="Genişletmeyi gösteren ekran görüntüsü.":::

Veri modelinizi temizlemeyi tamamlamak için sonraki adımları izleyin.

1. **AzureML.my-diabetes-model** sütununu **tahmin edilen** olarak yeniden adlandırın.
1. **Y** sütununu **gerçek** olarak yeniden adlandırın.
1. **Gerçek** sütununun türünü değiştirin: Sütunu seçin ve sonra **Dönüştür** şeridinde **Veri Türü** > **Ondalık Sayı**’yı seçin.
1. **Tahmin edilen** sütununun türünü değiştirin: Bu sütunu seçin ve sonra **Dönüştür** şeridinde **Veri Türü** > **Ondalık Sayı**’yı seçin.
1. **Giriş** şeridinde **Kapat ve Uygula**'yı seçin.

## <a name="create-a-report-with-visualizations"></a>Görselleştirmelerle bir rapor oluşturma

Artık verilerinizi göstermek için bazı görselleştirmeler oluşturabilirsiniz.

1. **Görsel Öğeler** bölmesinde bir **Çizgi grafik** öğesini seçin. 
1. Çizgi grafik görseli seçiliyken:
1. **YAŞ** alanını **Eksen**’e sürükleyin.
1. **Gerçek** alanını **Değerler**’e sürükleyin.
1. **Tahmin edilen** alanını **Değerler**’e sürükleyin.

Çizgi grafiği yeniden boyutlandırarak sayfayı kaplamasını sağlayın. Raporunuzda şimdi yaşa göre dağılmış, biri tahmin edilen diğeri de gerçek değerleri gösteren iki çizginin bulunduğu tek bir çizgi grafik olacaktır.

:::image type="content" source="media/service-aml-integrate/report-viz.png" alt-text="Rapor görselleştirmesini gösteren ekran görüntüsü.":::

## <a name="publish-the-report"></a>Raporu yayımlama

İsterseniz daha fazla görselleştirme ekleyebilirsiniz. Bu öğreticide fazla uzatmadan raporu yayımlayacağız.

1. Raporu kaydedin.
1. **Dosya** > **Yayımla** > **Power BI’a yayımla**’yı seçin.
1. Power BI hizmetinde oturum açın.
1. **Çalışma Alanım**’ı seçin.
1. Rapor başarıyla yayımlandığında **<MY_PBIX_FILE.pbix> bağlantısını Power BI’da aç**'ı seçin. Power BI’daki rapor tarayıcınızda açılır.

     :::image type="content" source="media/service-aml-integrate/publish-success.png" alt-text="Başarılı yayımlama işlemini gösteren ekran görüntüsü.":::

## <a name="enable-datasets-to-refresh"></a>Veri kümelerinin yenilenmesini etkinleştirme

Veri kaynağının puanlama için yeni verilerle yenileneceği bir senaryoda, verilerin puanlanabilmesi için kimlik bilgilerinizi güncelleştirmeniz gerekir. 

Power BI hizmetindeki Çalışma Alanım’da, siyah başlık çubuğunda **Diğer seçenekler(...)**  > **Ayarlar** > **Ayarlar**’ı seçin.

:::image type="content" source="media/service-aml-integrate/settings-pbi.png" alt-text="Ayarları gösteren ekran görüntüsü.":::

**Veri kümeleri**’ni seçin, **Veri kaynağı kimlik bilgileri**’ni genişletin ve **Kimlik Bilgilerini Düzenle**’yi seçin.

:::image type="content" source="media/service-aml-integrate/data-refresh.png" alt-text="Kimlik bilgilerini yenilemeyi gösteren ekran görüntüsü.":::

Hem **azureMLFunctions** hem de **Web** yönergelerini izleyin. Gizlilik düzeyini seçtiğinizden emin olun. Şimdi veriler için **Zamanlanmış yenileme** ayarlayabilirsiniz. **Yenileme sıklığı** ve **Saat dilimi** seçin. Power BI’ın yenileme hatası bildirimleri gönderebileceği bir e-posta adresi de seçebilirsiniz.

:::image type="content" source="media/service-aml-integrate/schedule-refresh.png" alt-text="Veri kümesi ve puanlama yenilemesini gösteren ekran görüntüsü.":::

**Uygula**’yı seçin.

>[!NOTE]
> Veriler yenilendiğinde, verileri puanlama amacıyla Azure Machine Learning uç noktanıza da gönderir.

## <a name="clean-up-resources"></a>Kaynakları temizleme

>[!IMPORTANT]
>Oluşturduğunuz kaynakları diğer Azure Machine Learning öğreticileri ve nasıl yapılır makaleleri için önkoşul olarak kullanabilirsiniz.

Oluşturduğunuz kaynakları kullanmayı planlamıyorsanız ücret ödememek için bunları silin.

1. Azure portalının en sol tarafındaki **Kaynak gruplarını** seçin.
 
1. Listeden oluşturduğunuz kaynak grubunu seçin.

1. **Kaynak grubunu sil**'i seçin.

   ![Azure portalda kaynak grubu silmek için yapılan seçimlerin ekran görüntüsü.](./media/service-aml-integrate/delete-resources.png)

1. Kaynak grubu adını girin. Ardından **Sil**’i seçin.
1. Power BI hizmetindeki Çalışma Alanım’da raporu ve ilgili veri kümesini silin. Power BI Desktop'ı veya bilgisayarınızdaki raporu silmenize gerek yoktur. Power BI Desktop ücretsizdir.

## <a name="next-steps"></a>Sonraki adımlar

Bu öğretici serisinde, yeni verilerin Azure Machine Learning puanlama uç noktanıza göre puanlanması için Power BI’da zamanlamayı ayarlamayı öğrendiniz.
