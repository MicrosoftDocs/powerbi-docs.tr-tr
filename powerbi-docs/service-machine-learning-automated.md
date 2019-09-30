---
title: Power BI’da Otomatikleştirilmiş Makine Öğrenmesi (Önizleme)
description: Power BI’da Otomatik Makine Öğrenmesi (AutoML) kullanmayı öğrenin
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
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "61236843"
---
# <a name="automated-machine-learning-in-power-bi-preview"></a>Power BI’da Otomatikleştirilmiş Makine Öğrenmesi (Önizleme)

Veri akışları için otomatik makine öğrenmesi (AutoML), iş analistlerinin Makine Öğrenmesi modellerini doğrudan Power BI’da eğitmesine, doğrulamasına ve çağırmasına olanak tanır. Analistlerin modeli eğitmeye yönelik giriş verilerini belirtmek için veri akışlarını kullanabileceği yeni bir ML modeli oluşturmak için basit bir deneyim içerir. Hizmet en ilgili özellikleri otomatik olarak ayıklar, uygun bir algoritma seçer ve ML modelini ayarlayıp doğrular. Bir model eğitildikten sonra Power BI, analistlere performansı ve sonuçları açıklayan, doğrulama sonuçlarını içeren bir raporu otomatik olarak oluşturur. Model daha sonra veri akışı içindeki yeni veya güncelleştirilmiş veriler üzerinde çağrılabilir.

![Makine öğrenmesi ekranı](media/service-machine-learning-automated/automated-machine-learning-power-bi-01.png)

Otomatik makine öğrenmesi, Power BI Premium ve Embedded kapasitelerinde barındırılan veri akışları için kullanılabilir. AutoML bu önizlemede İkili Tahmin, Sınıflandırma ve Regresyon modelleri için makine öğrenmesi modellerini eğitmenize olanak sağlar.

## <a name="working-with-automl"></a>AutoML ile çalışma

[Power BI veri akışları](service-dataflows-overview.md), büyük veriler için self servis veri hazırlığı sunar. AutoML, makine öğrenmesi modellerini Power BI içinden oluşturmak için veri hazırlığı çalışmalarınızdan yararlanmanızı sağlar.

Power BI’da AutoML, veri analistlerinin Power BI becerilerini kullanarak basitleştirilmiş bir deneyimle makine öğrenmesi modelleri oluşturmak için veri akışlarını kullanmasına olanak tanır. ML modellerinin oluşturulmasının ardında yatan veri biliminin büyük bölümü, modelin iyi kalite ürettiğinden emin olmaya yönelik önlemler ve ML modelinizi oluşturmak için kullanılan işlem hakkında tam içgörü sağlayan bir görünürlük ile Power BI ile otomatikleştirilir.

AutoML, veri akışları için **İkili Tahmin**, **Sınıflandırma** ve **Regresyon** modellerinin oluşturulmasını destekler. Bunlar, denetimli makine öğrenmesi modellerinin türleridir. Diğer bir deyişle, diğer gözlemlerin sonuçlarını tahmin etmek için geçmiş gözlemlerin bilinen sonuçlarını öğrenirler. Bir AutoML modelinin eğitimine yönelik giriş veri kümesi, bilinen sonuçlarla **etiketlenmiş** bir kayıt kümesidir.

Power BI’da AutoML, modellerinizi oluşturmak için [Azure Machine Learning hizmetinin](https://docs.microsoft.com/azure/machine-learning/service/overview-what-is-azure-ml) [otomatik ML](https://docs.microsoft.com/azure/machine-learning/service/concept-automated-ml) özelliğini tümleştirir. Ancak, Power BI’da AutoML kullanmak için bir Azure aboneliğinizin olması gerekmez. ML modellerini eğitme ve barındırma işlemi tamamen Power BI hizmeti tarafından yönetilir.

Bir ML modeli eğitildikten sonra AutoML, ML modelinizin olası performansını açıklayan bir Power BI raporunu otomatik olarak oluşturur. AutoML, girişleriniz arasında, modeliniz tarafından döndürülen tahminleri etkileyen başlıca etkileyicileri vurgulayarak açıklanabilirliği ön plana çıkarır. Rapor ayrıca ML model türüne bağlı olarak modelin önemli ölçümlerini içerir.

Oluşturulan raporun diğer bölümlerinde modelin istatistiksel özeti ve eğitim ayrıntıları gösterilir. İstatistiksel özet, model için standart veri bilimi performans ölçümlerini görmek isteyen kullanıcıları ilgilendirir. Eğitim ayrıntıları, modelinizi oluşturmak için çalıştırılan tüm yinelemeleri, ilişkili modelleme parametreleriyle birlikte özetler. Ayrıca, ML modelini oluşturmak için her bir girişin nasıl kullanıldığını açıklar.

Daha sonra ML modelinizi puanlama için verilerinize uygulayabilirsiniz. Veri akışı yenilendiğinde, ML modelinizden alınan tahminler otomatik olarak verilerinize uygulanır. Power BI ayrıca ML modelinin ürettiği her tahmin için ayrı bir açıklama içerir.

## <a name="creating-a-machine-learning-model"></a>Makine öğrenmesi modeli oluşturma

Bu bölümde bir AutoML öğrenme modelinin nasıl oluşturulacağı açıklanmaktadır. 

### <a name="data-prep-for-creating-an-ml-model"></a>ML modeli oluşturmak için veri hazırlığı

Power BI’da bir makine öğrenmesi modeli oluşturmak için öncelikle ML modelini eğitmek için kullanılan geçmiş sonuç bilgileriyle bir veri akışı oluşturmanız gerekir. Veri akışınızı yapılandırma hakkında ayrıntılı bilgi için bkz. [Power BI’da self servis veri akışı hazırlığı](service-dataflows-overview.md).

Geçerli yayında Power BI, ML modelini eğitmek için yalnızca tek bir varlık kullanır. Bu nedenle, geçmiş verileriniz birden fazla varlıktan oluşuyorsa verileri tek bir veri akışı varlığında el ile birleştirmeniz gerekir. Ayrıca, tahmin etmeye çalıştığınız sonuç için güçlü bir tahmin olabilecek herhangi bir iş ölçümünün hesaplanmış sütunlarını ekleyebilirsiniz.

AutoML bir makine öğrenmesi modelini eğitmek için belirli veri gereksinimlerine sahiptir. Bu gereksinimler, ilgili model türlerine göre aşağıdaki bölümlerde açıklanmıştır.

### <a name="configuring-the-ml-model-inputs"></a>ML modeli girişlerini yapılandırma

Bir AutoML modeli oluşturmak için, geçmiş verilerini içeren veri akışı varlığının **Eylemler** sütunundaki ML simgesini seçin ve **Makine öğrenmesi modeli ekle** seçeneğini belirleyin.

![Makine öğrenmesi modeli ekleme](media/service-machine-learning-automated/automated-machine-learning-power-bi-02.png)

ML modeli oluşturma işleminde size kılavuzluk eden sihirbazın bulunduğu basitleştirilmiş bir deneyim başlatılır. Sihirbaz aşağıdaki adımları içerir.

1. Geçmiş sonuç verilerini içeren varlığı ve tahminini istediğiniz alanı seçin
2. Görmek istediğiniz tahmin türüne göre bir model türü seçin
3. Modelin öngörücü sinyal olarak kullanmasını istediğiniz girişleri seçin
4. Modelinizi adlandırın ve yapılandırmanızı kaydedin

Geçmiş sonuç alanı, aşağıdaki görüntüde gösterildiği gibi ML modeli eğitimine yönelik etiket özniteliğini tanımlar.

![Geçmiş sonuç verilerini seçme](media/service-machine-learning-automated/automated-machine-learning-power-bi-03.png)

Geçmiş sonuç alanını belirttiğinizde, AutoML etiket verileri için eğitilebilecek ML modeli türlerini tanımlamak amacıyla bu verileri analiz eder ve eğitilebilecek en olası ML modeli türünü önerir. 

> [!NOTE]
> Bazı model türleri, seçtiğiniz veriler için desteklenmeyebilir.

AutoML ayrıca, ML modeli eğitimi için kullanılabilecek girişleri önermek amacıyla seçili varlıktaki tüm alanları analiz eder. Bu, yaklaşık bir işlemdir ve istatistiksel analizi temel alır, bu nedenle kullanılan girişleri gözden geçirmeniz gerekir. Geçmiş sonuç alanına (veya etiket alanına) bağlı olan hiçbir giriş, kendi performansını etkileyeceğinden ML modelini eğitmek için kullanılmamalıdır.

![Giriş alanlarını özelleştirme](media/service-machine-learning-automated/automated-machine-learning-power-bi-04.png)

Son adımda, modeli adlandırıp ayarlarını kaydedebilirsiniz.

Bu aşamada, ML modelini eğitme sürecini başlatan veri akışını yenilemeniz istenir.

### <a name="ml-model-training"></a>ML modeli eğitimi

AutoML modellerinin eğitimi, veri akışını yenilemenin bir parçasıdır. AutoML ilk olarak verilerinizi eğitim için hazırlar.

AutoML, sağladığınız geçmiş verileri eğitim ve test veri kümelerine böler. Test veri kümesi, eğitimin ardından model performansını doğrulamak için kullanılan bir gizleme kümesidir. Bunlar veri akışında **Eğitim ve Test** varlıkları olarak uygulanır. AutoML, model doğrulaması için çapraz doğrulamayı kullanır.

Ardından, her giriş alanı analiz edilir ve görevlendirme yapılır. Bu işlem eksik değerlerin yerine değiştirilen değerleri getirir. AutoML tarafından birkaç farklı görevlendirme stratejisi kullanılır. Ardından, gereken her türlü örnekleme ve normalleştirme, verilerinize uygulanır.

AutoML, her biri veri türüne ve istatistiksel özelliklerine göre seçilmiş giriş alanı olan birkaç dönüşüm uygular. AutoML, ML modelinizi eğitirken kullanılacak özellikleri eğitmek için bu dönüşümleri kullanır.

AutoML modellerinin eğitim süreci, en iyi performansa sahip modeli bulmak için farklı modelleme algoritmalarına ve hiper parametre ayarlarına sahip 50'ye kadar yinelemeden oluşur. Bu modellerin her birinin performansı, gizleme testi veri kümesiyle doğrulama yapılarak değerlendirilir. Bu eğitim adımı sırasında AutoML, bu yinelemelerin eğitimi ve doğrulanması için birkaç işlem hattı oluşturur. Veri kümenizin boyutuna ve kullanılabilir ayrılmış kapasite kaynaklarına bağlı olarak, modellerin performansını değerlendirme işlemi birkaç dakika ile birkaç saat arasında sürebilir.

Bazı durumlarda, oluşturulan son model daha iyi tahmine dayalı performans sağlamak için birden çok modelin kullanıldığı grup öğrenmesini kullanabilir.

### <a name="automl-model-explainability"></a>AutoML modelinin açıklanabilirliği

Model eğitildikten sonra AutoML, giriş özellikleri ile model çıkışı arasındaki ilişkiyi analiz eder. Her giriş özelliği için gizleme test veri kümesinin model çıkışındaki değişikliğin büyüklüğünü ve yönünü değerlendirir. Bu, *özelliğin önemi* olarak bilinir.

![Özelliğin önemi](media/service-machine-learning-automated/automated-machine-learning-power-bi-05.png)

### <a name="automl-model-report"></a>AutoML model raporu

AutoML, genel özellik önemiyle birlikte doğrulama sırasında modelin performansını özetleyen bir Power BI raporu oluşturur. Rapor, ML modelinin gizleme test verilerine uygulanması ve bilinen sonuç değerleriyle tahminlerin karşılaştırılması sonucunda elde edilecek sonuçları özetler.

Performansını anlamak için model raporunu gözden geçirebilirsiniz. Ayrıca, modelin önemli etkileyicilerinin bilinen sonuçlar hakkındaki iş öngörüleriyle uyumlu olduğunu doğrulayabilirsiniz.

Rapordaki model performansını açıklamak için kullanılan grafikler ve ölçüler model türüne bağlıdır. Bu performans grafikleri ve ölçümler aşağıdaki bölümlerde açıklanmıştır.

Rapordaki ek sayfalar, modelle ilgili istatistiksel ölçümleri bir veri bilimi perspektifinden açıklayabilir. Örneğin, **İkili Tahmin** raporu bir kazanç grafiği ve modelin ROC eğrisini içerir.

Raporlar ayrıca modelin nasıl eğitildiğine ilişkin açıklama içeren bir **Eğitim Ayrıntıları** sayfası ve yineleme çalıştırmalarının her birindeki model performansını açıklayan bir grafik içerir.

![Eğitim ayrıntıları](media/service-machine-learning-automated/automated-machine-learning-power-bi-06.png)

Bu sayfadaki başka bir bölümde, giriş alanları için eksik değerleri doldurmak üzere görevlendirme yönteminin nasıl kullanıldığı ve her giriş alanının modelde kullanılan özellikleri ayıklamak için nasıl dönüştürülebildiği açıklanmaktadır. Ayrıca son model tarafından kullanılan parametreleri içerir.

![Model hakkında daha fazla bilgi](media/service-machine-learning-automated/automated-machine-learning-power-bi-07.png)

Oluşturulan model grup öğrenmesi kullanıyorsa, **Eğitim Ayrıntıları** sayfasında grubu oluşturan her bir üyenin ağırlığını ve parametrelerini açıklayan bir bölüm de bulunur.

![Gruptaki ağırlık](media/service-machine-learning-automated/automated-machine-learning-power-bi-08.png)

## <a name="applying-the-automl-model"></a>AutoML modelini uygulama

Oluşturulan ML modelinin performansından memnunsanız, veri akışınız yenilendiğinde modeli yeni veya güncelleştirilmiş verilere uygulayabilirsiniz. Bu işlemi model raporundan sağ üst köşedeki **Uygula** düğmesini seçerek yapabilirsiniz.

ML modelini uygulamak için, uygulanması gereken varlığın adını ve model çıkışı için bu varlığa eklenecek sütunların ön ekini belirtmeniz gerekir. Sütun adları için varsayılan ön ek, model adıdır. *Uygula* işlevi, model türüne özgü ek parametreler içerebilir.

ML modelinin uygulanması, **zenginleştirilmiş <model_adı>** son ekiyle yeni bir veri akışı varlığı oluşturur. Örneğin, _PurchaseIntent_ modelini _OnlineShoppers_ varlığına uygularsanız, çıkış **OnlineShoppers zenginleştirilmiş PurchaseIntent** varlığını oluşturur.

Şu anda çıkış varlığı, Power Query düzenleyicisinde ML modeli sonuçlarının önizlemesi için kullanılamamaktadır. Çıkış sütunları sonuç olarak her zaman null gösterir. Sonuçları görüntülemek için, model uygulandığında **zenginleştirilmiş <model_adı> Önizlemesi** son ekiyle ikinci bir çıkış varlığı oluşturulur.

Sorgu Düzenleyicisinde sonuçların önizlemesini görmek için veri akışını yenilemeniz gerekir.

![Sorgu düzenleyicisi](media/service-machine-learning-automated/automated-machine-learning-power-bi-09.png)

Modeli uyguladığınızda, veri akışının yenilenmesi durumunda AutoML her zaman tahminlerinizi güncel tutar.

AutoML ayrıca çıkış varlığında puanladığı her satır için kişiselleştirilmiş bir açıklama içerir.

Bir Power BI raporundaki ML modelinden içgörü ve tahminleri kullanmak için, **dataflows** bağlayıcısını kullanarak Power BI Desktop’tan çıkış varlığına bağlanabilirsiniz.

## <a name="binary-prediction-models"></a>İkili Tahmin Modelleri

Daha resmi adıyla **ikili sınıflandırma modelleri** olarak bilinen İkili Tahmin modelleri, bir veri kümesini iki grup halinde sınıflandırmak için kullanılır. Bir satış fırsatının dönüştürüp dönüştürmeyeceği, bir hesabın değişip değişmeyeceği, bir faturanın zamanında ödenip ödenmeyeceği, bir işlemin hileli olup olmadığı vb. ikili sonucu olan olayları tahmin etmek için kullanılır.

Sonuç ikili olduğundan, Power BI bir ikili tahmin modelinin etiketinin Boole olmasını ve bilinen sonuçların **true** veya **false** olarak etiketlenmesini bekler. Örneğin, bir satış fırsatı dönüştürme modelinde kazanılan satış fırsatları true, kaybedilmiş olanlar false etiketlidir ve açık satış fırsatları null olarak etiketlenir.

İkili Tahmin modelinin çıkışı, true etiket değerine karşılık gelen sonucun elde edilme olasılığını tanımlayan bir olasılık puandır.

### <a name="training-a-binary-prediction-model"></a>İkili Tahmin modelini eğitme

İkili Tahmin modeli oluşturmak için, eğitim verilerinizi içeren giriş varlığının, bilinen geçmiş sonuçları tanımlamak için geçmiş sonuç alanı olarak bir Boole alanına sahip olması gerekir.

Önkoşullar:

* Geçmiş sonuç alanı olarak bir Boole alanı kullanılmalıdır
* Her sonuç sınıfı için en az 50 satır geçmiş veri gereklidir

Genel olarak, geçmiş sonuçlar farklı bir veri türündeki alanlarla tanımlanıyorsa bunları Power Query kullanarak Boole değerine dönüştürmek için bir hesaplanmış sütun ekleyebilirsiniz.

İkili Tahmin modeli oluşturma işlemi, yukarıdaki **ML modeli girişlerini yapılandırma** bölümünde açıklanan diğer AutoML modelleriyle aynı adımları izler.

### <a name="binary-prediction-model-report"></a>İkili Tahmin modeli raporu

İkili Tahmin modeli, bir kaydın Boole etiket değeri tarafından True olarak tanımlanan sonuca ulaşma olasılığını çıkarır. Rapor, olasılık eşiğinin üstünde ve altındaki puanların nasıl yorumlandığını etkileyen bir dilimleyici içerir.

Rapor, modelin performansını *Gerçek Pozitifler*, *Hatalı Pozitifler*, *Gerçek Negatifler* ve *Hatalı Negatifler* cinsinden açıklar. Gerçek Pozitifler ve Gerçek Negatifler, çıkış verilerindeki iki sınıfın doğru şekilde tahmin edilmiş sonuçlardır. Hatalı Pozitifler ise gerçekte False değerine sahip bir Boole etiketi olup True olarak tahmin edilmiş sonuçlardır. Buna karşılık, Hatalı Negatifler gerçek Boole etiketi değerinin True olmasına rağmen False olarak tahmin edildiği sonuçlardır.

Duyarlılık ve Yakalama gibi ölçüler, öngörülen sonuçlar üzerinde olasılık eşiğinin etkisini anlatmaktadır. Duyarlık ile Yakalama arasında dengeli bir uzlaşma sağlayan eşiği seçmek için olasılık eşiği dilimleyicisini kullanabilirsiniz.

![Doğruluk önizlemesi](media/service-machine-learning-automated/automated-machine-learning-power-bi-10.png)

Model raporunun **Doğruluk Raporu** sayfasında, *Kümülatif Kazançlar* grafiği ve modelin ROC eğrisi bulunur. Bunlar, model performansının istatistiksel ölçüleridir. Raporlar gösterilen grafiklerin açıklamalarını içerir.

![Doğruluk raporu ekranı](media/service-machine-learning-automated/automated-machine-learning-power-bi-11.png)

### <a name="applying-a-binary-prediction-model"></a>İkili Tahmin modeli uygulama

İkili tahmin modelini uygulamak için, ML modelinden tahminleri uygulamak istediğiniz verileri içeren varlığı belirtmeniz gerekir. Diğer parametreler, çıkış sütunu adı önekini ve tahmin edilen sonucun sınıflandırılmasına yönelik olasılık eşiğini içerir.

![Tahmin girişleri](media/service-machine-learning-automated/automated-machine-learning-power-bi-12.png)

Bir İkili Tahmin modeli uygulandığında zenginleştirilmiş çıkış varlığına üç çıkış sütunu ekler. Bunlar **PredictionScore**, **PredictionOutcome** ve **PredictionExplanation** sütunlarıdır. Model uygulandığında, varlıktaki sütun adları belirtilen ön eki alır.

**PredictionOutcome** sütunu tahmin edilen sonuç etiketini içerir. Eşiği aşma olasılıklarını içeren kayıtların sonuca ulaşma olasılığı yüksek olarak tahmin edilir, eşiğin altında kalanların ise sonuca ulaşma olasılığı düşük olarak tahmin edilir.

**PredictionExplanation** sütunu, giriş özelliklerinin **PredictionScore** üzerinde sahip olduğu etki ile birlikte bir açıklama içerir. Bu, tahmine yönelik giriş özelliklerinin ağırlıklarından oluşan JSON biçimli bir koleksiyondur.

## <a name="classification-models"></a>Sınıflandırma modelleri

Sınıflandırma modelleri, bir veri kümesini birden çok grup veya sınıfa ayırmak için kullanılır.  Bunlar, müşterinin çok yüksek, yüksek, orta veya düşük Ömür Değerine sahip olma olasılığı, varsayılan riskin Yüksek, Orta, Düşük veya Çok Düşük olması vb. birden çok olası sonuçtan birine sahip olabilecek olayları tahmin etmek için kullanılır.

Sınıflandırma modelinin çıkışı, bir kaydın belirli bir sınıfa yönelik ölçütlere ulaşmasının olasılığını belirleyen bir olasılık puandır.

### <a name="training-a-classification-model"></a>Sınıflandırma modeli eğitimi

Sınıflandırma modeline ait eğitim verilerinizi içeren giriş varlığının, bilinen geçmiş sonuçları tanımlayan geçmiş sonuç alanı olarak bir dize veya sayısal alana sahip olması gerekir.

Önkoşullar:

* Her sonuç sınıfı için en az 50 satır geçmiş veri gereklidir

Sınıflandırma modeli oluşturma işlemi, yukarıdaki **ML modeli girişlerini yapılandırma** bölümünde açıklanan diğer AutoML modelleriyle aynı adımları izler.

### <a name="classification-model-report"></a>Sınıflandırma modeli raporu

Sınıflandırma modeli raporu, ML modelinin gizleme test verilerine uygulanmasıyla ve bir kaydın tahmin edilen sınıfı gerçek bilinen sınıfla karşılaştırılarak oluşturulur.

Model raporu, bilinen her sınıf için doğru ve yanlış sınıflandırılmış kayıtların dökümünden oluşan bir grafik içerir.

![Model raporu](media/service-machine-learning-automated/automated-machine-learning-power-bi-13.png)

Sınıfa özgü daha fazla ayrıntıya gitmek, bilinen bir sınıfa yönelik tahminlerin nasıl dağıtıldığına ilişkin bir analiz sağlar. Bu analize, söz konusu bilinen sınıfın kayıtlarının hatalı sınıflandırılabileceği diğer sınıflar dahildir.

![Analiz raporu](media/service-machine-learning-automated/automated-machine-learning-power-bi-14.png)

Rapordaki model açıklaması her sınıf için en iyi tahmin unsurlarını da içerir.

Sınıflandırma modeli raporu ayrıca bu makalenin önceki kısımlarında yer alan **AutoML model raporu** bölümünde açıklandığı gibi diğer model türlerinin sayfalarına benzer bir Eğitim Ayrıntıları sayfası içerir.

### <a name="applying-a-classification-model"></a>Sınıflandırma modelini uygulama

Bir Sınıflandırma ML modelini uygulamak için, giriş verileri ve çıkış sütunu adı ön ekiyle birlikte varlığı belirtmeniz gerekir.

Bir Sınıflandırma modeli uygulandığında zenginleştirilmiş çıkış varlığına üç çıkış sütunu ekler. Bunlar **PredictionScore**, **PredictionClass** ve **PredictionExplanation** sütunlarıdır. Model uygulandığında, varlıktaki sütun adları belirtilen ön eki alır.

**PredictionClass** sütunu, kayıt için en yüksek olasılıkla tahmin edilen sınıfı içerir. **PredictionScore** sütunu, her olası sınıfın kaydına ait olasılık puanlarının listesini içerir.

**PredictionExplanation** sütunu, giriş özelliklerinin **PredictionScore** üzerinde sahip olduğu etki ile birlikte bir açıklama içerir. Bu, tahmine yönelik giriş özelliklerinin ağırlıklarından oluşan JSON biçimli bir koleksiyondur.

## <a name="regression-models"></a>Regresyon modelleri

Regresyon modelleri, bir satış kaynağından gerçekleştirilme olasılığı yüksek olan gelir, bir hesabın ömür değeri, ödenme olasılığı yüksek bir alacak faturasının tutarı, bir faturanın ödenebileceği tarih gibi bir değeri tahmin etmek için kullanılır.

Regresyon modelinin çıkışı, tahmin edilen değerdir.

### <a name="training-a-regression-model"></a>Regresyon modeli eğitimi

Regresyon modeline ait eğitim verilerinizi içeren giriş varlığının, bilinen geçmiş sonuç değerlerini tanımlayan geçmiş sonuç alanı olarak bir sayısal alana sahip olması gerekir.

Önkoşullar:

* Regresyon modeli için en az 100 satır geçmiş veri gereklidir

Regresyon modeli oluşturma işlemi, yukarıdaki **ML modeli girişlerini yapılandırma** bölümünde açıklanan diğer AutoML modelleriyle aynı adımları izler.

### <a name="regression-model-report"></a>Regresyon modeli raporu

Diğer AutoML model raporları gibi Regresyon raporu da modelin gizleme test verilerine uygulanmasından elde edilen sonuçları temel alır.

Model raporu, tahmin edilen değerleri gerçek değerle karşılaştıran bir grafik içerir. Bu grafikte köşegenden uzaklık, tahmindeki hatayı gösterir.

Fazlalık hata grafiği, gizleme testi veri kümesindeki farklı değerler için ortalama hata yüzdesinin dağılımını gösterir. Yatay eksen, grubun gerçek değerinin ortalamasını, söz konusu aralıktaki sıklığı veya değer sayısını gösteren kabarcığın boyutuyla temsil eder. Dikey eksen ortalama fazlalık hatasıdır.

![Fazlalık hata grafiği](media/service-machine-learning-automated/automated-machine-learning-power-bi-15.png)

Regresyon modeli raporu ayrıca yukarıdaki **AutoML model raporu** bölümünde açıklandığı gibi diğer model türlerinin raporlarına benzer bir Eğitim Ayrıntıları sayfası içerir.

### <a name="applying-a-regression-model"></a>Regresyon modelini uygulama

Bir Regresyon ML modelini uygulamak için, giriş verileri ve çıkış sütunu adı ön ekiyle birlikte varlığı belirtmeniz gerekir.

![Regresyon uygulama](media/service-machine-learning-automated/automated-machine-learning-power-bi-16.png)

Bir Regresyon modeli uygulandığında zenginleştirilmiş çıkış varlığına iki çıkış sütunu ekler. Bunlar **PredictionValue** ve **PredictionExplanation** sütunlarıdır. Model uygulandığında, varlıktaki sütun adları belirtilen ön eki alır.

**PredictionValue** sütunu, giriş alanlarını temel alarak kaydın tahmin edilen değerini gösterir. **PredictionExplanation** sütunu, giriş özelliklerinin **PredictionValue** üzerinde sahip olduğu etki ile birlikte bir açıklama içerir. Bu, giriş özelliklerinin ağırlıklarından oluşan JSON biçimli bir koleksiyondur.

## <a name="next-steps"></a>Sonraki adımlar

Bu makalede, Power BI hizmetinde Veri Akışları için Otomatik Makine Öğrenmesi’ne genel bir bakış verilmiştir. Aşağıdaki makaleler de yararlı olabilir.

* [Öğretici: Power BI’da Makine Öğrenmesi modeli oluşturma (Önizleme)](service-tutorial-build-machine-learning-model.md)
* [Öğretici: Power BI’da Bilişsel Hizmetler’i kullanma](service-tutorial-use-cognitive-services.md)
* [Öğretici: Power BI'da Machine Learning Studio modelini çağırma (Önizleme)](service-tutorial-invoke-machine-learning-model.md)
* [Power BI’da Bilişsel Hizmetler (Önizleme)](service-cognitive-services.md)
* [Power BI'da Azure Machine Learning tümleştirmesi (Önizleme)](service-machine-learning-integration.md)

Veri akışları hakkında daha fazla bilgi için şu makaleleri okuyabilirsiniz:
* [Power BI’da veri akışları oluşturma ve kullanma](service-dataflows-create-use.md)
* [Power BI Premium'da hesaplanan varlıkları kullanma](service-dataflows-computed-entities-premium.md)
* [Şirket içi veri kaynakları ile veri akışlarını kullanma](service-dataflows-on-premises-gateways.md)
* [Power BI veri akışları için geliştirici kaynakları](service-dataflows-developer-resources.md)
* [Veri akışları ve Azure Data Lake tümleştirmesi (Önizleme)](service-dataflows-azure-data-lake-integration.md)


