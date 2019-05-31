---
title: Power BI’da Otomatikleştirilmiş Makine Öğrenmesi (Önizleme)
description: Power BI'da otomatik Machine Learning (AutoML) kullanmayı öğrenin
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/02/2019
ms.author: davidi
LocalizationGroup: conceptual
ms.openlocfilehash: 894e92687a6283ce71b253bd4dc635aca0c4673f
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "61236843"
---
# <a name="automated-machine-learning-in-power-bi-preview"></a>Power BI’da Otomatikleştirilmiş Makine Öğrenmesi (Önizleme)

(AutoML) için veri akışlarını otomatik makine eğitmek, doğrulamak ve makine öğrenimi modelleri Power bı'da doğrudan çağırmak, iş analistleri sağlar. Bu, analistlerin modeli eğitmek için giriş verileri belirtmek için veri akışlarını burada kullanabilirsiniz yeni ML model oluşturmaya yönelik basit bir deneyimi içerir. Hizmet otomatik olarak en uygun özellikler ayıklar, uygun bir algoritmayı seçer ve ayarlar ve ML modeli doğrular. Power BI, otomatik olarak bir modeli eğitilir sonra performans açıklayan doğrulama sonuçları ve analistleri için sonuçları içeren bir rapor oluşturur. Model veri akışı içindeki tüm yeni veya güncelleştirilmiş verileri sonra çağrılabilir.

![Machine learning ekranı](media/service-machine-learning-automated/automated-machine-learning-power-bi-01.png)

Otomatik makine öğrenimi, yalnızca Power BI Premium ve katıştırılmış kapasiteleri barındırılan bir veri akışı için kullanılabilir. Bu önizleme sürümünde AutoML ikili tahmin, Sınıflandırma ve regresyon modellerini için makine öğrenimi modellerini eğitmenize sağlar.

## <a name="working-with-automl"></a>AutoML ile çalışma

[Power BI veri akışlarını](service-dataflows-overview.md) büyük veriler için Self Servis veri hazırlığı sunar. AutoML veri hazırlık çalışmalarınızı Power BI içinden makine öğrenimi modelleri oluşturmak için yararlanmasını sağlar.

Power bı'da AutoML yalnızca Power BI becerilerinizi kullanarak veri analistleri, makine öğrenimi modellerini basitleştirilmiş bir deneyim oluşturmak için veri akışlarını kullanmasını sağlar. Veri bilimi oluşturmayı ML modelleri arkasında çoğunu otomatik olarak Power BI tarafından üretilen modeli kaliteli ve ML model oluşturmak için kullanılan işlem tam bir anlayış sağlamak için görünürlük olduğundan emin olmak için guardrails ile.

AutoML oluşturulmasını destekleyen **ikili tahmin**, **sınıflandırma**, ve **regresyon** modelleri için veri akışı. Bu, diğer gözlemler sonuçlarını tahmin etmek için geçmiş gözlemlerdir bilinen sonuçlardan öğrenin, yani, denetimli makine öğrenimi modelleri türleridir. AutoML modeli eğitimi için giriş veri kümesi kayıtları kümesidir **etiketli** bilinen sonuçları ile.

Power bı'da AutoML tümleşir [ML otomatik](https://docs.microsoft.com/azure/machine-learning/service/concept-automated-ml) gelen [Azure Machine Learning hizmeti](https://docs.microsoft.com/azure/machine-learning/service/overview-what-is-azure-ml) , ML modelleri oluşturmak için. Ancak, Power BI'da AutoML kullanmak için Azure aboneliği gerekmez. Eğitim ve ML modelleri barındırma sürecini tamamen Power BI hizmeti tarafından yönetilir.

ML model eğitildi sonra AutoML ML modeliniz olası performansının açıklayan bir Power BI raporu otomatik olarak oluşturur. AutoML explainability, kilit, modeli tarafından döndürülen Öngörüler etkileyen girişlerinizi arasında vurgulayarak vurgular. Rapor modeli, ML model türüne bağlı olarak ilişkin ana ölçümleri de içerir.

Oluşturulan raporun diğer sayfalarında modeli ve eğitim ayrıntılarını istatistiksel özetini gösterir. İstatistiksel özeti modeli için performans standart veri bilimi ölçümleri görmek istediğiniz kullanıcılar ilgilendirir. Eğitim ayrıntıları ilişkili modelleme parametrelerle, modelinizi oluşturmak için çalıştırılan tüm yinelemeleri özetler. Ayrıca, her bir giriş ML model oluşturmak için nasıl kullanıldığını açıklar.

Ardından, ML model Puanlama için verilerinizi uygulayabilirsiniz. Veri akışı yenilendiğinde ML modeliniz ait tahminlerin verilerinizi otomatik olarak uygulanır. Power BI ayrıca ML model üreten her belirli tahmin puanı için bireyselleştirilmiş bir açıklama içerir.

## <a name="creating-a-machine-learning-model"></a>Makine öğrenme modeli oluşturma

Bu bölümde bir AutoML learning modeli oluşturmayı açıklar. 

### <a name="data-prep-for-creating-an-ml-model"></a>ML model oluşturmak için veri hazırlama

Power BI'da bir machine learning modeli oluşturmak için öncelikle ML modeli eğitmek için kullanılan geçmiş sonucu bilgilerle veriler için bir veri akışı oluşturmanız gerekir. Veri akışı yapılandırma hakkında daha fazla bilgi için bkz [Self Servis veri hazırlama Power BI'da](service-dataflows-overview.md).

Geçerli sürümde, Power BI ML modeli eğitmek için yalnızca tek bir varlık verilerini kullanır. Bu nedenle, geçmiş verilerinizi birden çok varlık oluşuyorsa, tek bir veri akışı varlığa verileri el ile birleştirmelisiniz. Hesaplanmış sütunlar tahmin etmeye çalıştığınız sonucu için güçlü adaylarının olabilecek herhangi bir iş ölçümler için de eklemeniz gerekir.

AutoML, makine öğrenme modeli eğitimi için belirli veri gereksinimleri vardır. Bu gereksinimler, ilgili modeli türlerine göre aşağıdaki bölümlerde açıklanmıştır.

### <a name="configuring-the-ml-model-inputs"></a>ML model girişleri yapılandırılıyor

Bir AutoML modeli oluşturmak için ML simgesini seçin. **eylemleri** sütunu seçin ve geçmiş verileri veri akışı varlık **makine öğrenme modeli Ekle**.

![Makine öğrenme modeli ekleme](media/service-machine-learning-automated/automated-machine-learning-power-bi-02.png)

Basitleştirilmiş bir deneyim, ML model oluşturma işleminde size yol gösterecek bir sihirbaz oluşan başlatılır. Sihirbaz aşağıdaki basit adımları içerir.

1. Varlık geçmiş sonuç verileri ve tahmin istediğiniz alanı seçin
2. Görmek istediğiniz tahmin türüne göre bir model türü seçin
3. Tahmine dayalı sinyalleri kullanılacak modelini istediğiniz girişleri seçin
4. Model adı ve yapılandırmanızı kaydedin

Aşağıdaki görüntüde gösterilen ML model eğitimi için etiket özniteliği geçmiş sonuç alanı tanımlar.

![Geçmiş sonuç verileri seçme](media/service-machine-learning-automated/automated-machine-learning-power-bi-03.png)

Geçmiş sonuç alanı belirttiğinizde, AutoML ilişkin verileri eğitilmiş ML modelleri türlerini tanımlamak üzere etiket verileri analiz eder ve eğitim büyük olasılıkla ML model türü önerir. 

> [!NOTE]
> Bazı model türleri için seçtiğiniz verileri desteklenmiyor olabilir.

AutoML ML modeli eğitmek için kullanılan girişleri önermek için seçilen varlığın tüm alanları da analiz eder. Bu işlem yaklaşık bir değerdir ve kullanılan girişleri gözden geçirmeniz gereken şekilde istatistiksel çözümleme dayanır. Geçmiş sonuç alanı (veya etiket alanı) bağımlı olan tüm girişleri, bunlar performansını etkiler. bu yana ML modeli eğitmek için kullanılmamalıdır.

![Giriş alanlarını özelleştirme](media/service-machine-learning-automated/automated-machine-learning-power-bi-04.png)

Son adımda, model adını ve ayarlarını kaydedin.

Bu aşamada başlar ML model eğitim işlemlerinde veri akışı Yenile istenir.

### <a name="ml-model-training"></a>ML model eğitimi

Eğitim AutoML modelleri, veri akışı yenileme parçasıdır. AutoML verilerinizi eğitim için ilk hazırlar.

Eğitim ve test sağladığınız geçmiş verileri AutoML böler. Test veri kümesini eğitim sonra model performansını doğrulamak için kullanılan bir gizleme kümesidir. Bunlar olarak gerçekleşen **eğitim ve test** varlıklarda veri akışı. AutoML çapraz doğrulama, model doğrulama için kullanır.

Ardından, her giriş alanı analiz edilir ve değiştirilen değerlerle değer yerini alan imputation uygulanır. Birkaç farklı imputation stratejileri AutoML tarafından kullanılır. Ardından, tüm gerekli örnekleme ve normalleştirme verilerinize uygulanır.

AutoML geçerlidir birkaç dönüşümleri olan veri türünü ve istatistiksel özelliklerini göre seçilen her giriş alanı. ML modeliniz eğitim kullanmak için özellikler ayıklamak için bu dönüştürmeleri AutoML kullanır.

Eğitim işlem AutoML modelleri için en çok 50 yinelemeler farklı modelleme algoritmaları ve performansı en iyi modeli bulmak için hiper parametre ayarları oluşur. Her biri bu modeller performansını doğrulama gizleme test veri kümesi ile tarafından değerlendirilir. Bu eğitim adımı sırasında AutoML eğitim ve bu yinelemeler doğrulama için birkaç işlem hatları oluşturur. Model performansını değerlendirme işleminin süresi, herhangi bir yere birkaç saat, ayrılmış kapasite kaynakları ve veri kümeniz boyutuna bağlı olarak birkaç dakika sürebilir.

Bazı durumlarda, oluşturulan son modelin learning, Tahmine dayalı daha iyi bir performans sağlamak üzere birden çok modeli kullanıldığı topluluğu kullanabilir.

### <a name="automl-model-explainability"></a>AutoML modeli explainability

Eğitilen modelin sonra AutoML giriş özellikleri ve model çıktısını arasındaki ilişkiyi analiz eder. Bu değişiklik gizleme test veri giriş her özellik için model çıktısını yönünü ve büyüklük değerlendirir. Bu olarak bilinir *özellik önem*.

![Özellik önem derecesi](media/service-machine-learning-automated/automated-machine-learning-power-bi-05.png)

### <a name="automl-model-report"></a>AutoML modeli rapor

AutoML model performansını genel özellik önem yanı sıra, doğrulama sırasında özetleyen bir Power BI rapor oluşturur. Rapor sonuçları ML model gizleme test verilerine uygulanan ve Öngörüler bilinen sonucu değerlerle karşılaştırmak özetler.

Performansı anlamak için model raporu gözden geçirebilirsiniz. Ayrıca, kilit modelin bilinen sonuçlar hakkında iş öngörülerle Hizala doğrulayabilirsiniz.

Grafikler ve ölçüleri rapordaki model performansını açıklamak için kullanılan model türüne bağlıdır. Bu performans grafiklerini ve ölçüler aşağıdaki bölümlerde açıklanmıştır.

Ek rapor sayfalarındaki bir veri bilimi açısından modeli hakkında istatistiksel ölçüler açıklayabilir. Örneğin, **ikili tahmin** kazanç grafik ve modelin ROC eğrisi rapor içerir.

Raporları de bir **Eğitim ayrıntıları** nasıl model eğitim almış ve model performansını her yineleme açıklayan bir grafik içeren bir açıklama içeren sayfasında çalışır.

![Eğitim ayrıntıları](media/service-machine-learning-automated/automated-machine-learning-power-bi-06.png)

Bu sayfada başka bir bölüme modelinde kullanılan özellikler ayıklamak için her girdi alanına dönüştürüldü nasıl nasıl imputation yöntemi eksik değerler için giriş alanlarını doldurmak için de kullanılan açıklar. Ayrıca, son model tarafından kullanılan parametreler içerir.

![Daha fazla bilgi için model](media/service-machine-learning-automated/automated-machine-learning-power-bi-07.png)

Oluşturulan model topluluğu öğrenme kullanıyorsa, ardından **Eğitim ayrıntıları** sayfa parametrelerini yanı sıra topluluğu bağlı her modelinde ağırlığını açıklayan bir bölümü de içerir.

![Topluluğu içinde ağırlık](media/service-machine-learning-automated/automated-machine-learning-power-bi-08.png)

## <a name="applying-the-automl-model"></a>AutoML modeli uygulama

Oluşturulan ML model performansını memnun kalırsanız, veri akışı yenilendiğinde, yeni veya güncelleştirilmiş verilerin uygulayabilirsiniz. Model rapordan seçerek bunu yapabilirsiniz **Uygula** sağ üst köşesindeki düğme.

ML model uygulamak için bu varlık için model çıktısını eklenecek sütunları için varlık için bunun uygulanması gerekir ve bir önek adını belirtmeniz gerekir. Sütun adları için varsayılan model adını önekidir. *Uygula* işlevi için model türü belirli ek parametreler içerebilir.

ML model uygulama, yeni bir veri akışı varlık sonekiyle oluşturur **< model_adı > zenginleştirilmiş**. Örneğin, uygularsanız, _PurchaseIntent_ için model _OnlineShoppers_ varlık, çıktı üretir **OnlineShoppers zenginleştirilmiş PurchaseIntent**.

Şu anda, çıktı varlık Power Query Düzenleyicisi'nde ML model sonuçlarını önizlemek için kullanılamaz. Çıkış sütunu, sonuç olarak null gösterir. İkinci sonuçlarını görüntülemek için varlık sonekine sahip çıkış **< model_adı > Önizleme zenginleştirilmiş** modeli uygulandığında oluşturulur.

Sorgu Düzenleyicisi'nde sonuçlarını önizlemek için veri akışı yenilemeniz gerekir.

![Sorgu Düzenleyicisi](media/service-machine-learning-automated/automated-machine-learning-power-bi-09.png)

Model uyguladığınızda, veri akışı yenilendiğinde AutoML her zaman, Öngörüler güncel kalmasını sağlar.

AutoML, ayrıca çıktı varlığındaki puanlar, her satır için bireyselleştirilmiş bir açıklama içerir.

Power BI raporunda Öngörüler ve tahminler ML modelinden kullanmak için çıktı varlığına Power BI Desktop kullanarak bağlanabilir **veri akışlarını** bağlayıcı.

## <a name="binary-prediction-models"></a>İkili tahmin modellerini

Daha eski adıyla bilinen ikili tahmin modellerini **ikili sınıflandırma modellerini**, bir veri kümesi ikiye sınıflandırmak için kullanılır. Bir hesap karmaşıklığı olsun, fatura zamanında ödenmez olup olmadığını mı satış fırsatı dönüştürülecek gibi ikili bir sonucu olabilir olayları öngörmek için kullanılırlar; bir işlem sahte vb. olup olmadığı.

Sonucu ikili olduğundan, Power BI ile etiketlenmiş bilinen sonuçları bir Boolean olmasını ikili bir tahmin modeli etiketi bekliyor **true** veya **false**. Örneği için bir satış fırsatı dönüştürme modelde kazanılmış satış fırsatları true olarak etiketlenmiştir, kaybolmuş o false etiketlenir ve açık satış fırsatları null olarak etiketlenir.

Çıkış ikili bir tahmin modeli true olan bir etiket değerine karşılık gelen sonuç elde ettiği olasılığını tanımlayan bir olasılık puanı alınır.

### <a name="training-a-binary-prediction-model"></a>İkili bir tahmin modeli

Eğitim verilerinizi içeren giriş varlığı ikili bir tahmin modeli oluşturmak için son bilinen sonuçlarını tanımlamak için geçmiş sonuç alanı bir Boole alanı olmalıdır.

Ön koşullar:

* Bir Boolean alan geçmiş sonuç alanı kullanılmalıdır
* Bir en az 50 satır geçmiş verilerin sonuçlar her bir sınıf için gereklidir.

Genel olarak, geçmiş sonuçlarını başka bir veri türüne alanlarla tanımladıysanız, bu Power Query kullanarak bir Boole değeri dönüştürmek için hesaplanmış bir sütun ekleyebilirsiniz.

İkili bir tahmin modeli aynı izleyen için bölümünde açıklanan diğer AutoML modelleri oluşturma işlemi adımları **ML model girişlerini yapılandırma** yukarıda.

### <a name="binary-prediction-model-report"></a>İkili tahmin modeli rapor

İkili bir tahmin modeli bir çıktı olarak bir kayıt Boole etiket değeri True olarak tanımlanan sonucu elde edecek bir olasılık oluşturur. Rapor Dilimleyici üstünde ve altında olasılık eşiği puanları yorumlanma şeklini etkiler olasılık eşiği için içerir.

Rapor modeli açısından performansını açıklar *doğru pozitif sonuçlar*, *hatalı pozitif sonuçları*, *True negatif* ve *False negatif*. Gerçek pozitif sonuç ve gerçek negatif sonuç verileri iki sınıfları için doğru şekilde tahmin sonuçlarını var. Hatalı pozitif sonuçları gerçek değeri False Boolean etiketi gerekiyordu, ancak doğru olarak tahmin sonuçlar ' dir. Buna karşılık, yanlış negatif burada gerçek Boole etiket değerinin True olduğu ancak False tahmin sonuçlar ' dir.

Ölçüler, duyarlık ve geri çağırma, gibi tahmin edilen sonuçları temel olasılık eşiği etkisini açıklar. Duyarlık ve geri çağırma arasında dengeli bir dağılım elde eden bir eşiği seçmek için olasılık eşiği Dilimleyici kullanabilirsiniz.

![Doğruluk Önizleme](media/service-machine-learning-automated/automated-machine-learning-power-bi-10.png)

**Doğruluğu rapor** model rapor sayfasını içerir *toplu kazançlar* grafiği ve ROC eğrisi için model. Bu model performansını istatistiksel yöntemleridir. Raporlar, gösterilen grafikleri açıklamalarını içerir.

![Doğruluk rapor ekranı](media/service-machine-learning-automated/automated-machine-learning-power-bi-11.png)

### <a name="applying-a-binary-prediction-model"></a>İkili bir tahmin modeli uygulama

İkili bir tahmin modeli uygulamak için Öngörüler ML modelinden uygulamak istediğiniz verileri içeren varlık belirtmeniz gerekir. Diğer parametreler, çıkış sütun adı ön eki ve tahmin edilen sonucu sınıflandırmak için olasılık eşiği içerir.

![Tahmin girişleri](media/service-machine-learning-automated/automated-machine-learning-power-bi-12.png)

İkili bir tahmin modeli uygulandığında zenginleştirilmiş çıktı varlığına üç çıktı sütunu ekler. Bunlar **PredictionScore**, **PredictionOutcome** ve **PredictionExplanation**. Sütun adları varlık modeli uygulandığında Belirtilen önek sahip.

**PredictionOutcome** sütun tahmin edilen sonucu etiketi içerir. Eşiği aşan olasılıklar kayıtlarla sonucu elde etmek üzere olası olarak tahmin ve altındaki sonucu elde etmek üzere olası tahmin.

**PredictionExplanation** sütun içeren giriş özellikleri olan üzerinde belirli etki tarayamadığına **PredictionScore**. Bu giriş özellikleri tahmin için ağırlıkları, JSON biçimli koleksiyonudur.

## <a name="classification-models"></a>Sınıflandırma modelleri

Sınıflandırma modelleri, bir veri kümesi birden çok grup veya sınıf sınıflandırmak için kullanılır.  Bir müşteri çok yüksek, yüksek, Orta veya düşük ömrü değeri olasılığı olup gibi birden çok olası sonuçlarını birine sahip olabilir olayları öngörmek için kullanılırlar; Varsayılan riski yüksek, Orta, düşük veya çok düşük olup; ve benzeri.

Bir kaydın belirli bir sınıfın ölçütleri elde edecek olasılığını tanımlayan bir olasılık puanı, sınıflandırma modeli çıktıdır.

### <a name="training-a-classification-model"></a>Sınıflandırma modeli

Sınıflandırma modeli için eğitim verilerinizi içeren giriş varlığı, son bilinen sonuçlarını tanımlayan geçmiş sonuç alanı bir dize veya sayısal alan olması gerekir.

Ön koşullar:

* Bir en az 50 satır geçmiş verilerin sonuçlar her bir sınıf için gereklidir.

İçin bir sınıflandırma modeli aynı aşağıdaki bölümünde açıklanan diğer AutoML modelleri oluşturma işlemi adımları **ML model girişlerini yapılandırma** yukarıda.

### <a name="classification-model-report"></a>Sınıflandırma modeli rapor

Sınıflandırma modeli rapor ML model gizleme için uygulama tarafından üretilen test verileri ve bir kayıt için tahmin edilen sınıf gerçek bilinen sınıfı ile karşılaştırma.

Model rapor dökümü bilinen her sınıf için doğru ve hatalı sınıflandırılmış kayıtları içeren bir grafik içerir.

![Rapor modeli](media/service-machine-learning-automated/automated-machine-learning-power-bi-13.png)

Bir başka sınıf özel ayrıntılı Öngörüler bilinen bir sınıf için nasıl dağıtıldığını analiz sağlar. Bu sınıf bilinen kayıtlarını bildireceğinizi olasılığı olan diğer sınıflar içerir.

![Analiz raporu](media/service-machine-learning-automated/automated-machine-learning-power-bi-14.png)

Rapor modeli açıklamada her sınıf için üst adaylarının de içerir.

Sınıflandırma modeli rapor ayrıca bölümünde açıklandığı gibi diğer model türleri için sayfalara benzer bir eğitim Ayrıntıları sayfası içerir **AutoML model rapor** bu makalenin üst kısmındaki.

### <a name="applying-a-classification-model"></a>Bir sınıflandırma modeli uygulama

Sınıflandırma ML model uygulamak isterseniz girdi verilerini ve çıktı sütun adı ön eki ile varlık belirtmeniz gerekir.

Bir sınıflandırma modeli uygulandığında, üç sütun zenginleştirilmiş çıktı varlığına çıkış biçimi ekler. Bunlar **PredictionScore**, **PredictionClass** ve **PredictionExplanation**. Sütun adları varlık modeli uygulandığında Belirtilen önek sahip.

**PredictionClass** sütun kaydı için büyük olasılıkla tahmin edilen sınıf içerir. **PredictionScore** sütun kayıt olası her sınıf için olasılık puanları listesini içerir.

**PredictionExplanation** sütun içeren giriş özellikleri olan üzerinde belirli etki tarayamadığına **PredictionScore**. Bu giriş özellikleri tahmin için ağırlıkları, JSON biçimli koleksiyonudur.

## <a name="regression-models"></a>Regresyon modelleri

Regresyon modelleri, bir satış işlem, bir hesap yaşam süresi değeri, fatura ödeme tarih Ücretli büyük olasılıkla alacak bir fatura tutarı getireceği büyük olasılıkla gelir gibi bir değeri tahmin etmek için kullanılır , ve benzeri.

Bir regresyon modeli çıktı tahmin edilen bir değerdir.

### <a name="training-a-regression-model"></a>Bir regresyon modeli eğitimi

Bir regresyon modeli için eğitim verilerini içeren giriş varlığı, son bilinen sonuç değerleri tanımlar. geçmiş sonuç alanı sayısal alan olması gerekir.

Ön koşullar:

* 100 satır geçmiş verilerin en az bir regresyon modeli için gereklidir

İçin aynı bir regresyon modeli aşağıdaki bölümünde açıklanan diğer AutoML modelleri oluşturma işlemi adımları **ML model girişlerini yapılandırma** yukarıda.

### <a name="regression-model-report"></a>Regresyon modeli rapor

Diğer AutoML modeli raporları gibi regresyon rapor modeli gizleme test verileri uygulama sonuçları temel alır.

Model rapor tahmin edilen değerlere gerçek değeri karşılaştıran bir grafik içerir. Bu grafikte, çapraz mesafe tahmin hata gösterir.

Kalan hata grafik gizleme test kümesinde farklı değerler için ortalama hata yüzde dağılımını gösterir. Yatay eksen, söz konusu aralıktaki sıklığı veya değerlerin sayısını gösteren Kabarcık boyutu ile gerçek değer için grup ortalaması temsil eder. Dikey eksen ortalama kalan hatadır.

![Kalan hata grafiği](media/service-machine-learning-automated/automated-machine-learning-power-bi-15.png)

Regresyon modeli rapor ayrıca bölümünde açıklandığı gibi diğer model türleri için raporları gibi bir eğitim Ayrıntıları sayfası içerir **AutoML model rapor** yukarıda.

### <a name="applying-a-regression-model"></a>Bir regresyon modeli uygulama

Regresyon ML model uygulamak isterseniz girdi verilerini ve çıktı sütun adı ön eki ile varlık belirtmeniz gerekir.

![Bir regresyon Uygula](media/service-machine-learning-automated/automated-machine-learning-power-bi-16.png)

Bir regresyon modeli uygulandığında zenginleştirilmiş çıktı varlığına iki çıkış sütunu ekler. Bunlar **PredictionValue**, ve **PredictionExplanation**. Sütun adları varlık modeli uygulandığında Belirtilen önek sahip.

**PredictionValue** sütunu giriş alanlara göre kayıt için tahmin edilen bir değer içeriyor. **PredictionExplanation** sütun içeren giriş özellikleri olan üzerinde belirli etki tarayamadığına **PredictionValue**. Bu giriş özellikleri kalınlığını, JSON biçimli koleksiyonudur.

## <a name="next-steps"></a>Sonraki adımlar

Bu makalede, Power BI hizmetinde veri akışı için Machine Learning otomatik genel bir bakış sağlanan. Aşağıdaki makaleler de yararlı olabilir.

* [Öğretici: Power BI (Önizleme) bir Machine Learning modeli derlemeyi](service-tutorial-build-machine-learning-model.md)
* [Öğretici: Power BI’da Bilişsel Hizmetler’i kullanma](service-tutorial-use-cognitive-services.md)
* [Öğretici: Power BI'da Machine Learning Studio modelini çağırma (Önizleme)](service-tutorial-invoke-machine-learning-model.md)
* [Power BI’da Bilişsel Hizmetler (Önizleme)](service-cognitive-services.md)
* [Power BI'da Azure Machine Learning tümleştirmesi (Önizleme)](service-machine-learning-integration.md)

Veri akışları hakkında daha fazla bilgi için şu makaleleri okuyabilirsiniz:
* [Power BI’da veri akışları oluşturma ve kullanma](service-dataflows-create-use.md)
* [Hesaplanan varlıkları üzerinde Power BI Premium kullanma](service-dataflows-computed-entities-premium.md)
* [Şirket içi veri kaynakları ile veri akışlarını kullanma](service-dataflows-on-premises-gateways.md)
* [Power BI veri akışı için geliştirici kaynaklar](service-dataflows-developer-resources.md)
* [Veri akışları ve Azure Data Lake tümleştirmesi (Önizleme)](service-dataflows-azure-data-lake-integration.md)


