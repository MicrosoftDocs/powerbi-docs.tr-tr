---
title: 'Öğretici: Power BI (Önizleme) bir Machine Learning modeli derlemeyi'
description: Bu öğreticide Machine Learning modeli Power bı'da oluşturun.
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.custom: connect-to-services
ms.topic: tutorial
ms.date: 03/29/2019
ms.author: davidi
LocalizationGroup: Connect to services
ms.openlocfilehash: 611d6f6c923e6cb68af94840c4266a0b6dee7651
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "61407192"
---
# <a name="tutorial-build-a-machine-learning-model-in-power-bi-preview"></a>Öğretici: Power BI (Önizleme) bir Machine Learning modeli derlemeyi

Bu öğretici makalesinde kullandığınız **Machine Learning otomatik** oluşturmak ve Power bı'da ikili bir tahmin modeli uygulamak için. Varlıkları kullanarak veri akışı eğitmek ve makine öğrenme modeli doğrudan Power bı'da doğrulamak için tanımlanan ve öğretici Power BI veri akışı oluşturmaya yönelik yönergeleri içerir. Daha sonra bu modeli Puanlama için Öngörüler oluşturmak için kullanırız.

İlk olarak ikili tahmin makine öğrenme modeli, bir çevrimiçi oturumu öznitelikleri kümesi temel alınarak çevrimiçi adamın satın alma amacını tahmin etmek için oluşturacaksınız. Bu alıştırma için bir Kıyaslama machine learning veri kümesi kullanılır. Bir modeli eğitilir sonra Power BI model sonuçlarını açıklayan bir doğrulama raporu otomatik olarak oluşturur. Ardından, doğrulama raporunu gözden geçirin ve model Puanlama için verilerinizi uygulanır.

Bu öğreticide adımlar oluşur:

> [!div class="checklist"]
> * Girdi verilerini bir veri akışı oluşturma
> * Oluşturma ve makine öğrenme modeli eğitme
> * Model doğrulama raporunu gözden geçirin
> * Bir veri akışı varlık modeli geçerlidir
> * Power BI raporunda model puanlanmış çıkışı kullanma

## <a name="create-a-dataflow-with-the-input-data"></a>Girdi verilerini bir veri akışı oluşturma

Bu öğreticinin ilk bölümü, girdi verilerini bir veri akışı oluşturmaktır. Bu işlem, veri alma ile başlayarak aşağıdaki bölümlerde gösterildiği gibi birkaç adım alır.

### <a name="get-data"></a>Veri al

Bir veri akışı oluşturmanın ilk adımı, veri kaynaklarınızı hazır olmasını sağlamaktır. Bu örnekte, bir machine learning veri kümesinden bir dizi içinde bir satınalma culminated bazıları, çevrimiçi oturumlarda kullanırız. Veri kümesi, modeli eğitmek için kullanacağız bu oturumları hakkındaki öznitelikleri kümesi içerir.

Veri kümesi UC Irvine Web sitesinden indirebilirsiniz.  Ayrıca bu, aşağıdaki bağlantıdan Bu öğreticinin amacı doğrultusunda sahip olduğumuz: [online_shoppers_intention.csv](https://raw.githubusercontent.com/santoshc1/PowerBI-AI-samples/master/Tutorial_AutomatedML/online_shoppers_intention.csv).

### <a name="create-the-entities"></a>Varlık oluşturma

Veri akışınızda varlıkları oluşturmak için, Power BI hizmetinde oturum açın ve AI önizlemesinin etkinleştirildiği ayrılmış kapasitenizdeki çalışma alanına gidin.

Bir çalışma alanı zaten sahip değilseniz, birini seçerek oluşturabilirsiniz **çalışma alanları** seçin ve Power BI hizmetinde sol gezinti menüsünde **uygulama çalışma alanı oluşturma** bölmenin altındaki, görünür. Bu çalışma alanı ayrıntılarını girmek için sağ taraftaki bir paneli açılır. Bir çalışma alanı adı girin ve seçin **Gelişmiş**. Çalışma alanını ayrılmış kapasitenin radyo düğmesini kullanarak kullanır ve açık AI önizlemesi sahip bir adanmış kapasite örneği atandığından emin olun. Sonra **Kaydet**'i seçin.

![Çalışma alanı oluşturma](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-01.png)

Çalışma alanı oluşturulduktan sonra seçebileceğiniz **atla** Hoş Geldiniz ekranında, aşağıdaki görüntüde gösterildiği gibi sağ alt.

![Bir çalışma alanı varsa atlayın](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-02.png)

Seçin **veri akışlarını (Önizleme)** sekmesi. Seçin **Oluştur** çalışma alanının sağ ve ardından üstünde düğme **veri akışı**.

![Veri akışı oluşturma](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-03.png)

**Yeni varlıklar ekle**'yi seçin. Böylece bir **Power Query** tarayıcıda Düzenleyicisi.

![Yeni varlık ekleme](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-04.png)

Seçin **metin/CSV dosyası** veri kaynağı olarak, aşağıdaki görüntüde gösterilen.

![Metin/CSF dosya seçildi](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-05.png)

İçinde **veri kaynağına bağlanma** sonraki görüntülenir, aşağıdaki bağlantı yapıştırın *online_shoppers_intention.csv* içine **dosya yolu veya URL** kutusuna ve ardından seçin **Sonraki**.

`https://raw.githubusercontent.com/santoshc1/PowerBI-AI-samples/master/Tutorial_AutomatedML/online_shoppers_intention.csv`

![Dosya yolu](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-06.png)

Power Query Editor CSV dosyasındaki verilerin önizlemesini gösterir. Seçin **dönüştürme tablosu** seçin ve komut Şerit **ilk satırı başlığı olarak kullan** görünen menüden. Bu ekler _üstbilgileri yükseltilen_ sorgu adımla **uygulanan adımların** ekranın sağ taraftaki bölümü. Değerini değiştirerek daha kolay adı için sorgu adlandırabilirsiniz **adı** kutusu sağ bölmede bulunan. Örneğin, sorgu adını değiştirebilir _çevrimiçi ziyaretçi_.

![Kolay bir adla değiştirin](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-07.png)

Bu veri kümesi içinde öznitelik veri türlerinden bazıları _sayısal_ veya _Boole_, bu dizeler olarak yorumlanıp ancak **Power Query**. Aşağıdaki türler için aşağıda sütunları değiştirmek için her bir sütun başlığına üst öznitelik türü simgesini seçin:

* **Ondalık sayı:** Administrative_Duration; Informational_Duration; ProductRelated_Duration; BounceRates; ExitRates; PageValues; SpecialDay
* **True/False:** Hafta sonu; Gelir

![Veri türünü değiştirme](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-08.png)

**İkili tahmin** eğitim modeli geçmiş gözlemlerdir sonuçlarını tanımlayan bir etiket olarak Boole bir alan gerektirir. Bu veri kümesinde _gelir_ öznitelik, satın alma gösterir ve bu öznitelik, bir Boolean olarak zaten mevcuttur. Bu nedenle, etiket için hesaplanmış bir sütun eklemeniz gerekmez. Diğer veri kümelerine bir Boole sütunu var olan etiket öznitelikleri dönüştürmek zorunda kalabilirsiniz.

Seçin **Bitti** güç sorgu Düzenleyicisi'ni kapatmak için düğme. Bu varlıkları listesi ile gösterilir ve _çevrimiçi ziyaretçiler_ veri ekledik. Seçin **Kaydet** sağ üst köşede, veri akışı için bir ad belirtin ve ardından **Kaydet** aşağıdaki görüntüde gösterildiği gibi iletişim.

![Veri akışı kaydedin](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-09.png)

### <a name="refresh-the-dataflow"></a>Veri akışını yenileme

Bir bildirim görüntülenen veri akışı sonuçlarında, veri akışı kaydedildiğini belirten. Seçin **Şimdi Yenile** veri akışı veri kaynağından almak için.

![Şimdi yenile](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-10.png)

Sağ üst köşedeki **Kapat**'ı seçin ve veri akışını yenileme işleminin tamamlanmasını bekleyin.

Kullanarak, veri akışı yenileyebilirsiniz **eylemleri** komutları. Yenileme tamamlandıktan sonra veri akışı zaman damgasını gösterir.

![Yenileme zaman damgası](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-11.png)

## <a name="create-and-train-a-machine-learning-model"></a>Oluşturma ve makine öğrenme modeli eğitme

Yenileme tamamlandıktan sonra veri akışı seçin. Makine öğrenme modeli eklemek için seçin **uygulamak ML model** düğmesine **eylemleri** eğitim verilerini ve etiket bilgilerinizi içeren bir temel varlık listeleyin ve ardından **Ekle bir Machine learning modeli**.

![Makine öğrenmesi modeli ekle](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-12.png)

Bizim machine learning modeli oluşturmak için ilk adım, tahmin etmek istediğiniz etiket alanı da dahil olmak üzere geçmiş verileri belirlemektir. Model, bu verileri kullanarak oluşturulur.

Kullanmakta olduğumuz dataset söz konusu olduğunda, bu, **gelir** alan. Seçin **gelir** seçin ve 'geçmiş sonuç alanı' değeri olarak **sonraki**.

![Geçmiş verileri seçme](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-13.png)

Ardından, biz machine learning modeli oluşturmak için türü seçmeniz gerekir. Power BI tespit ettik geçmiş sonuç alanı değerleri analiz eder ve bu alan tahmin etmek için oluşturulan makine öğrenimi modelleri türlerini önerir.

Bu durumda, biz olup bir kullanıcı bir satın alma veya yapar, ikili bir sonucu tahmin beri seçin **ikili tahmin** model türünü ve ardından İleri için.

![Seçili ikili tahmin](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-14.png)

Ardından, Power BI, verilerin ön bir tarama yapar ve model kullanabilirsiniz girişleri önerir. Model için kullanılan giriş alanlarını özelleştirme seçeneğiniz var. Bizim seçkin veri kümesinde, tüm alanları seçmek için varlık adının yanındaki onay kutusunu seçin. Seçin **sonraki** girişleri kabul etmek için.

![Sonraki onay kutusunu işaretleyin](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-15.png)

Son adımda, biz model doğrulama sonuçlarını özetler otomatik olarak oluşturulan raporda kullanılacak sonuçlar için kolay etiketler yanı sıra modelimiz için bir ad sağlamanız gerekir. Sonraki modeli adlandırmanız sahibiz _satın alma amacını tahmin_ve true ve false etiketleri aynı _satın alma_ ve _No-satın alma_. Sonra **Kaydet**'i seçin.

![Modeli kaydedin](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-16.png)

Machine learning modelimizi artık eğitim için hazırdır. Seçin **Şimdi Yenile** modeli eğitmek başlatmak için.

![Şimdi yenile](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-17.png)

Örnekleme, geçmiş verilerinizi normalleştirme ve iki yeni varlıklara veri kümeniz bölme eğitim sürecine başlayacağız *satın alma amacını tahmin eğitim verilerini* ve *satın alma, hedefi tahmin test etme Veri*.

Veri kümesi boyutuna bağlı olarak, eğitim işlem birkaç dakika veya birkaç saat için herhangi bir yere sürebilir. Bu noktada, modelde gördüğünüz **makine öğrenimi Modellerinizi** veri akışı sekmesi. _Hazır_ durumu modeli eğitimi için kuyruğa alındı veya eğitim altında olduğunu gösterir.

![Eğitim için hazır](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-18.png)

Model eğitimi olsa da, görüntülemek veya veri akışı düzenlemek mümkün olmayacaktır. Model verdiğini onaylayın eğitim ve veri akışı durumu doğrulandı. Bu işlemde bir veri yenileme olarak görünür **veri akışlarını** çalışma alanının sekmesi.

![İşlemde](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-19.png)

Model eğitiminin tamamlandıktan sonra veri akışı bir güncelleştirilmiş yenileme zamanını görüntüler. Model, giderek eğitildi olduğunu onaylayabilirsiniz **makine öğrenimi Modellerinizi** veri akışı sekmesindedir. Oluşturduğunuz model durumu olarak göstermelidir **Trained** ve **son eğitilen** zaman artık güncelleştirilmelidir.

![Üzerinde en son eğitim](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-20.png)

## <a name="review-the-model-validation-report"></a>Model doğrulama raporunu gözden geçirin

Model doğrulama raporunu gözden geçirmek için **makine öğrenimi modelleri, s** seçmediğiniz **performans raporu görüntülemek ve modeli geçerlidir** düğmesine **eylemleri** modeli için sütun . Bu rapor, makine öğrenimi modelinizi nasıl gerçekleştirmek büyük olasılıkla açıklar.

İçinde **Model performansını** select rapor sayfasının **anahtarı öğrenilenler** modeliniz için üst adaylarının görüntülemek için. Sonuç dağıtım ile ilgili bir tahmin unsuru nasıl ilişkili görmek için adaylarının birini seçebilirsiniz.

![Model performansını](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-21.png)

Kullanabileceğiniz **olasılık eşiği** modeli için geri çağırma ve duyarlık üzerindeki etkisini incelemek için dilimleyici Model performansını sayfasında.

![Olasılık eşiği](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-22.png)

Raporun diğer sayfalarında modeli için istatistiksel performans ölçümlerini açıklanmaktadır.

Rapor ayrıca, girişler ve kullanılan son modelin hiperparametreleri özellikleri nasıl ayıklanan çalıştırılan farklı yinelemeleri açıklayan bir eğitim Ayrıntıları sayfası içerir.

## <a name="apply-the-model-to-a-dataflow-entity"></a>Bir veri akışı varlık modeli geçerlidir

Seçin **Uygula modeli** veri akışı yenilendikten sonra bu modeli çağırmak için raporun üstündeki düğmesi. İçinde **Uygula** iletişim kutusunda, model uygulanabilir kaynak verilere sahip bir hedef varlık belirtebilirsiniz.

![Modeli uygulayın](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-23.png)

İstendiğinde, gereken **Yenile** modelinizi sonuçlarını önizlemek için veri akışı.

Uygulama modeli oluşturur, yeni varlık soneki ile **< model_adı > zenginleştirilmiş** modeli uygulandığı varlığa eklenir. Örneğimizde, modele uygulama **OnlineShoppers** varlığı oluşturur **OnlineShoppers zenginleştirilmiş satın alma amacını tahmin**, modelin tahmin edilen çıktıdan içerir.

Uygulama ikili bir tahmin modeli tahmin edilen sonucu, olasılık puanı ve tahmini için üst kayda özgü öğrenilenler üç sütun ekler, her sütun adıyla belirtilen önek.

![Üç sütun sonucu](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-24.png)

Bilinen bir sorun nedeniyle zenginleştirilmiş varlık puanlanmış çıkış sütunlarında yalnızca Power BI Desktop'tan erişilebilir. Bu hizmetin önizlemesini görmek için bir özel Önizleme varlığı kullanmanız gerekir.

Veri akışı yenileme tamamlandıktan sonra seçebileceğiniz **OnlineShoppers zenginleştirilmiş satın alma hedefi tahmin Önizleme** sonuçlarını görüntülemek için varlık.

![Sonuçları görüntüleyin](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-25.png)

## <a name="using-the-scored-output-from-the-model-in-a-power-bi-report"></a>Power BI raporunda model puanlanmış çıkışı kullanma

Machine learning modeli puanlanmış çıkışı kullanmak için veri akışlarını Bağlayıcısı'nı kullanarak, veri akışı için Power BI Desktop'tan bağlanabilirsiniz. **OnlineShoppers zenginleştirilmiş satın alma amacını tahmin** varlık artık Power BI raporlarındaki modelinizdeki Öngörüler birleştirmek için kullanılabilir.

## <a name="next-steps"></a>Sonraki adımlar

Bu öğreticide, oluşturulan ve aşağıdaki adımları kullanarak Power bı'daki bir ikili bir tahmin modeli uygulanır:

* Girdi verilerini bir veri akışı oluşturma
* Oluşturma ve makine öğrenme modeli eğitme
* Model doğrulama raporunu gözden geçirin
* Bir veri akışı varlık modeli geçerlidir
* Power BI raporunda model puanlanmış çıkışı kullanma

Power BI, Machine Learning Otomasyonu hakkında daha fazla bilgi için bkz. [otomatik Machine Learning (Önizleme) Power bı'da](service-machine-learning-automated.md).
