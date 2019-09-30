---
title: 'Öğretici: Power BI’da Makine Öğrenmesi modeli oluşturma (Önizleme)'
description: Bu öğreticide Power BI'da bir Makine öğrenmesi modeli oluşturacaksınız.
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
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "61407192"
---
# <a name="tutorial-build-a-machine-learning-model-in-power-bi-preview"></a>Öğretici: Power BI’da Makine Öğrenmesi modeli oluşturma (Önizleme)

Bu öğretici makalesinde **Otomatik Makine Öğrenmesi** kullanarak Power BI’da bir ikili tahmin modeli oluşturacak ve uygulayacaksınız. Öğretici, bir Power BI veri akışı oluşturmaya ve veri akışında tanımlanan varlıkları kullanarak doğrudan Power BI’da bir makine öğrenmesi modelini eğitme ve doğrulamaya yönelik kılavuz bilgilerini içerir. Daha sonra tahminler oluşturmak üzere bu modeli puanlama için kullanırız.

İlk olarak, İnternette alışveriş yapan tüketicilerin satın alma amacını bir dizi çevrimiçi oturum özniteliğine göre tahmin etmek üzere bir İkili Tahmin makine öğrenmesi modeli oluşturacaksınız. Bu alıştırma için bir referans makine öğrenmesi veri kümesi kullanılmaktadır. Model eğitildikten sonra Power BI, model sonuçlarını açıklayan bir doğrulama raporunu otomatik olarak oluşturur. Daha sonra doğrulama raporunu gözden geçirip puanlama için modeli verilerinize uygulayabilirsiniz.

Bu öğretici aşağıdaki adımlardan oluşur:

> [!div class="checklist"]
> * Giriş verileriyle veri akışı oluşturma
> * Makine öğrenmesi modeli oluşturma ve eğitme
> * Model doğrulama raporunu gözden geçirme
> * Modeli bir veri akışı varlığına uygulama
> * Modeldeki puanlanmış çıkışı bir Power BI raporunda kullanma

## <a name="create-a-dataflow-with-the-input-data"></a>Giriş verileriyle veri akışı oluşturma

Bu öğreticinin ilk kısmında giriş verileriyle bir veri akışı oluşturulacaktır. Bu işlem için, veri almayla başlayarak aşağıdaki bölümlerde gösterildiği gibi birkaç adım gerekir.

### <a name="get-data"></a>Veri al

Veri akışı oluşturmanın ilk adımı, veri kaynaklarınızı hazır hale getirmektir. Bu örnekte, bazıları satın almayla sonuçlanmış birkaç çevrimiçi oturumdaki makine öğrenmesi veri kümesini kullanacağız. Veri kümesi, bu oturumlarla ilgili olarak modelimizi eğitmek için kullanacağımız bir dizi öznitelik içerir.

Veri kümesini UC Irvine web sitesinden indirebilirsiniz.  Bu öğretici için aşağıdaki bağlantıdan şu dosyaya da ulaşabilirsiniz: [online_shoppers_intention.csv](https://raw.githubusercontent.com/santoshc1/PowerBI-AI-samples/master/Tutorial_AutomatedML/online_shoppers_intention.csv).

### <a name="create-the-entities"></a>Varlıkları oluşturma

Veri akışınızda varlıkları oluşturmak için, Power BI hizmetinde oturum açın ve AI önizlemesinin etkinleştirildiği ayrılmış kapasitenizdeki çalışma alanına gidin.

Henüz çalışma alanınız yoksa, Power BI hizmetinin sol gezinti menüsünde **Çalışma Alanları**'nı ve sonra görüntülenen panelin altındaki **Uygulama çalışma alanı oluştur**'u seçerek bir çalışma alanı oluşturabilirsiniz. Sağ tarafta, çalışma alanı ayrıntılarını girebileceğiniz bir panel açılır. Bir çalışma alanı adı girin ve **Gelişmiş**'i seçin. Radyo düğmesini kullanarak çalışma alanının Ayrılmış Kapasite kullandığını ve yapay zeka önizlemesi açık olan bir ayrılmış kapasite örneğine atandığını doğrulayın. Sonra **Kaydet**'i seçin.

![Çalışma alanı oluşturma](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-01.png)

Çalışma alanı oluşturulduktan sonra, aşağıdaki görüntüde gösterildiği gibi Hoş Geldiniz ekranının sağ alt kısmındaki **Atla**'yı seçebilirsiniz.

![Bir çalışma alanınız varsa atlayın](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-02.png)

**Veri Akışları (önizleme)** sekmesini seçin. Çalışma alanının sağ üst kısmındaki **Oluştur** düğmesini ve sonra **Veri akışı**'nı seçin.

![Veri akışı oluşturma](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-03.png)

**Yeni varlıklar ekle**'yi seçin. Bu işlem tarayıcıda **Power Query** düzenleyicisini başlatır.

![Yeni varlık ekleme](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-04.png)

Aşağıdaki görüntüde gösterilen **Metin/CSV Dosyası**’nı veri kaynağı olarak seçin.

![Text/CSF dosyası seçildi](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-05.png)

Daha sonra görüntülenen **Veri kaynağına bağlan** menüsünde, aşağıdaki *online_shoppers_intention.csv* bağlantısını **Dosya yolu veya URL** kutusuna yapıştırın ve sonra **İleri**’yi seçin.

`https://raw.githubusercontent.com/santoshc1/PowerBI-AI-samples/master/Tutorial_AutomatedML/online_shoppers_intention.csv`

![Dosya yolu](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-06.png)

Power Query Düzenleyicisi CSV dosyasındaki verilerin önizlemesini gösterir. Komut şeridinde **Tabloyu Dönüştür**'ü seçin ve sonra görüntülenen menüden **İlk satırı üst bilgi olarak kullan**'ı seçin. Bu seçim, ekranın sağ tarafındaki _Uygulanan adımlar_ bölümüne **Yükseltilen üst bilgiler** sorgu adımını ekler. Sağ bölmedeki **Ad** kutusunun değerini değiştirerek sorguya daha kolay bir ad verebilirsiniz. Örneğin, Sorgu adını _Çevrimiçi Ziyaretçi_ olarak değiştirebilirsiniz.

![Kolay bir adla değiştirme](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-07.png)

Bu veri kümesindeki bazı öznitelik veri türleri _sayısal_ veya _Boole_’dir, ancak bunlar **Power Query** tarafından dize olarak yorumlanabilir. Aşağıda listelenen sütunları aşağıdaki türlerle değiştirmek için her bir sütun başlığının en üstünde bulunan öznitelik türü simgesini seçin:

* **Ondalık sayı:** Administrative_Duration; Informational_Duration; ProductRelated_Duration; BounceRates; ExitRates; PageValues; SpecialDay
* **True/False:** Weekend; Revenue

![Veri türünü değiştirme](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-08.png)

Eğiteceğimiz **İkili Tahmin** modeli, geçmiş gözlemlerdeki sonuçları tanımlayan bir etiket olarak Boole alanı gerektirir. Bu veri kümesinde _Revenue_ özniteliği satın almayı işaret eder ve bu öznitelik zaten Boole olarak mevcuttur. Bu nedenle, etiket için hesaplanmış sütun eklememiz gerekmez. Diğer veri kümelerinde, var olan etiket özniteliklerini bir Boole sütununa dönüştürmeniz gerekebilir.

**Bitti** düğmesini seçerek Power Query Düzenleyicisi'ni kapatın. Bu seçim, eklediğimiz _Çevrimiçi Ziyaretçiler_ verilerini içeren varlık listesini gösterir. Aşağıdaki görüntüde gösterildiği gibi, sağ üst köşedeki **Kaydet**’i seçin, veri akışı için bir ad sağlayın ve sonra iletişim kutusunda **Kaydet**’i seçin.

![Veri akışını kaydetme](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-09.png)

### <a name="refresh-the-dataflow"></a>Veri akışını yenileme

Veri akışının kaydedilmesi sonucunda, veri akışınızın kaydedildiğini belirten bir bildirim gösterilir. Verileri kaynaktan veri akışına almak için **Şimdi yenile**'yi seçin.

![Şimdi yenile](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-10.png)

Sağ üst köşedeki **Kapat**'ı seçin ve veri akışını yenileme işleminin tamamlanmasını bekleyin.

Veri akışınızı yenilemek için **Eylemler** komutlarını da kullanabilirsiniz. Yenileme tamamlandığında veri akışı, zaman damgasını gösterir.

![Yenileme zaman damgası](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-11.png)

## <a name="create-and-train-a-machine-learning-model"></a>Makine öğrenmesi modeli oluşturma ve eğitme

Yenileme tamamlandıktan sonra veri akışını seçin. Bir makine öğrenmesi modeli eklemek için, eğitim verilerinizi ve etiket bilgilerini içeren temel varlığın **Eylemler** listesindeki **ML modeli uygula** düğmesini seçin ve sonra **Makine öğrenmesi modeli ekle**’yi seçin.

![Makine öğrenmesi modeli ekle](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-12.png)

Makine öğrenmesi modelimizi oluşturmanın ilk adımı, tahmin etmek istediğiniz etiket alanını içeren geçmiş verileri tanımlamaktır. Model, bu verilerden öğrenilerek oluşturulacaktır.

Kullandığımız veri kümesi söz konusu olduğunda burası **Revenue** alanıdır. 'Geçmiş sonuç alanı' değeri olarak **Revenue** ve sonra **İleri**’yi seçin.

![Geçmiş verileri seçme](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-13.png)

Bundan sonra, oluşturulacak makine öğrenmesi modelinin türünü seçmemiz gerekir. Power BI, belirlediğiniz geçmiş sonuç alanındaki değerleri analiz eder ve bu alanı tahmin etmek için oluşturulabilecek makine öğrenmesi modellerinin türlerini önerir.

Bu örnekte bir kullanıcının satın alıp almayacağına ilişkin ikili sonucu tahmin edeceğimiz için model türü olarak **İkili Tahmin**’i ve sonra İleri’yi seçin.

![İkili tahmin seçildi](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-14.png)

Daha sonra, Power BI verilerin ön taramasını yapar ve modelin kullanabileceği girişleri önerir. Model için kullanılan giriş alanlarını özelleştirme seçeneğiniz vardır. Seçkin veri kümemizde tüm alanları seçmek için varlık adının yanındaki onay kutusunu seçin. Girişleri kabul etmek için **İleri**’yi seçin.

![İleri onay kutusunu seçin](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-15.png)

Son adımda, modelimiz için bir ad ve ayrıca model doğrulama sonuçlarını özetleyecek otomatik olarak oluşturulan raporda kullanılacak sonuçlar için kolay etiketler sağlamamız gerekir. Ardından modeli _Satın Alma Amacı Tahmini_, true ve false etiketlerini ise _Satın Alma_ ve _Satın Alma Yok_ olarak adlandırmamız gerekir. Sonra **Kaydet**'i seçin.

![Modeli kaydetme](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-16.png)

Makine öğrenmesi modelimiz artık eğitim için hazırdır. Modeli eğitmeye başlatmak için **Şimdi Yenile**’yi seçin.

![Şimdi yenile](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-17.png)

Eğitim işlemi, geçmiş verilerinizi örnekleyip normalleştirme ve veri kümenizi *Satın Alma Amacı Tahmini Eğitim Verileri* ve *Satın Alma Amacı Tahmini Test Verileri* şeklinde iki varlığa bölme ile başlar.

Veri kümesinin boyutuna bağlı olarak eğitim işlemi birkaç dakika ile birkaç saat arasında sürebilir. Bu noktada, modeli veri akışının **Makine öğrenmesi modelleri** sekmesinde görebilirsiniz. _Hazır_ durumu, modelin eğitim için kuyruğa alındığını veya eğitim aşamasında olduğunu gösterir.

![Eğitime hazır](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-18.png)

Model eğitilirken veri akışını görüntüleyemez veya düzenleyemezsiniz. Model eğitilmekte ve doğrulanmakta olduğunu veri akışının durumu üzerinden onaylayabilirsiniz. Bu seçenek, çalışma alanının **Veri Akışları** sekmesinde bir veri yenileme sürüyor olarak görünür.

![Sürüyor](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-19.png)

Model eğitimi tamamlandıktan sonra veri akışı güncel bir yenileme saati gösterir. Veri akışındaki **Makine öğrenmesi modelleri** sekmesine giderek modelin eğitildiğini onaylayabilirsiniz. Oluşturduğunuz model, **Eğitildi** durumunu göstermelidir ve **Son Eğitim** zamanı güncellenmiş olmalıdır.

![Son eğitim tarihi](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-20.png)

## <a name="review-the-model-validation-report"></a>Model doğrulama raporunu gözden geçirme

Model doğrulama raporunu gözden geçirmek için, **Makine öğrenmesi modelleri** menüsünde, modelin **Eylemler** sütununa ait **Performans raporunu görüntüle ve modeli uygula** düğmesini seçin. Bu rapor, makine öğrenmesi modelinizin olası performansını açıklar.

Raporun **Model Performansı** sayfasında, modelinize yönelik en iyi tahmin unsurlarını görüntülemek için **Başlıca Etkileyiciler**’i seçin. Çıkış dağılımının bir tahmin unsuruyla ilişkisini görmek için ilgili tahmin unsurunu seçebilirsiniz.

![Model performansı](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-21.png)

Modelin Duyarlık ve Yakalama değerine etkisini incelemek için Model Performansı sayfasındaki **Olasılık Eşiği** dilimleyicisini kullanabilirsiniz.

![Olasılık eşiği](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-22.png)

Raporun diğer sayfaları, modelin istatistiksel performans ölçümlerini açıklar.

Bu rapor ayrıca, çalıştırılan farklı yinelemeleri, özelliklerin girişlerden nasıl ayıklandığını ve kullanılan son model için hiper parametreleri açıklayan bir Eğitim Ayrıntıları sayfasını içerir.

## <a name="apply-the-model-to-a-dataflow-entity"></a>Modeli bir veri akışı varlığına uygulama

Veri akışı yenilendiğinde bu modeli çağırmak için raporun üst kısmındaki **Modeli uygula** düğmesini seçin. **Uygula** iletişim kutusunda, modelin uygulanması gereken kaynak verilere sahip hedef varlığı belirtebilirsiniz.

![Modeli uygulayın](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-23.png)

Sorulduğunda, modelinizin sonuçlarının önizlemesini görmek için veri akışını **Yenilemeniz** gerekir.

Model uygulandığında, modeli uyguladığınız varlığın sonuna **zenginleştirilmiş <model_adı>** eki getirilerek yeni bir varlık oluşturulur. Örneğimizde, modeli **OnlineShoppers** varlığına uygulamak, modelin tahmin edilen sonucunu içeren **OnlineShoppers zenginleştirilmiş Satın Alma Amacı Tahmini**’ni oluşturur.

İkili Tahmin modeli uygulamak, tahmin edilen sonuç, olasılık puanı ve tahmin için kayda özel en önemli etkileyicileri içeren ve her biri belirtilen sütun adını ön ek olarak alan üç sütun ekler.

![Üç sonuç sütunu](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-24.png)

Bilinen bir sorun nedeniyle, zenginleştirilmiş varlıktaki puanlanmış çıkış sütunlarına yalnızca Power BI Desktop’tan erişilebilir. Hizmette bunların önizlemesini görmek için özel bir önizleme varlığı kullanmanız gerekir.

Veri akışı yenilemesi tamamlandıktan sonra sonuçları görüntülemek için **OnlineShoppers zenginleştirilmiş Satın Alma Amacı Tahmini Önizlemesi** varlığını seçebilirsiniz.

![Sonuçları görüntüleme](media/service-tutorial-build-machine-learning-model/tutorial-build-machine-learning-model-25.png)

## <a name="using-the-scored-output-from-the-model-in-a-power-bi-report"></a>Modeldeki puanlanmış çıkışı bir Power BI raporunda kullanma

Makine öğrenmesi modelinizdeki puanlanmış çıktıyı kullanmak için, Veri Akışı bağlayıcısını kullanarak Power BI Desktop’tan veri akışınıza bağlanabilirsiniz. **OnlineShoppers zenginleştirilmiş Satın Alma Amacı Tahmini** varlığı artık modelinizdeki tahminleri Power BI raporlarına eklemek için kullanılabilir.

## <a name="next-steps"></a>Sonraki adımlar

Bu öğreticide, aşağıdaki adımları kullanarak Power BI’da bir ikili tahmin modeli oluşturup uyguladınız:

* Giriş verileriyle veri akışı oluşturma
* Makine öğrenmesi modeli oluşturma ve eğitme
* Model doğrulama raporunu gözden geçirme
* Modeli bir veri akışı varlığına uygulama
* Modeldeki puanlanmış çıkışı bir Power BI raporunda kullanma

Power BI'da Machine Learning tümleştirmesi hakkında daha fazla bilgi için bkz. [Power BI'da Otomatik Makine Öğrenmesi (Önizleme)](service-machine-learning-automated.md).
