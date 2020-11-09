---
title: Veri akışları ile Makine Öğrenimi ve Bilişsel Hizmetleri kullanma
description: Veri akışlarıyla makine öğrenmesi ve otomatik makine öğrenmesi hizmetlerini kullanmaya genel bakış
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
ms.date: 10/01/2020
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: a2622d2d3da5e4149e93a2b4b6f04dc87b55d9e1
ms.sourcegitcommit: 4ac9447d1607dfca2e60948589f36a3d64d31cb4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92917039"
---
# <a name="ai-with-dataflows"></a>Veri akışları ve yapay zeka

Bu makalede veri akışlarıyla yapay zeka hizmetlerini nasıl kullanabileceğinizi göreceksiniz. Bu makalede incelenen konular şunlardır:

* Bilişsel Hizmetler
* Otomatik Makine Öğrenmesi
* Azure Machine Learning Tümleştirmesi

## <a name="cognitive-services-in-power-bi"></a>Power BI'da Bilişsel Hizmetler

Power BI'da Bilişsel Hizmetler ile, Veri Akışları için self servis veri hazırlığında verileri zenginleştirmek için [Azure Bilişsel Hizmetler](https://azure.microsoft.com/services/cognitive-services/)'den farklı algoritmalar uygulayabilirsiniz.

Bugün desteklenen hizmetler [Yaklaşım Analizi](https://docs.microsoft.com/azure/cognitive-services/text-analytics/how-tos/text-analytics-how-to-sentiment-analysis), [Anahtar İfade Ayıklama](https://docs.microsoft.com/azure/cognitive-services/text-analytics/how-tos/text-analytics-how-to-keyword-extraction), [Dil Algılama](https://docs.microsoft.com/azure/cognitive-services/text-analytics/how-tos/text-analytics-how-to-language-detection) ve [Resim Etiketleme](https://docs.microsoft.com/azure/cognitive-services/computer-vision/concept-tagging-images)'dir. Dönüştürmeler Power BI Hizmetinde yürütülür ve Azure Bilişsel Hizmetler aboneliği gerekmez. Bu özellik için Power BI Premium gerekir.

### <a name="enabling-ai-features"></a>**AI özelliklerini etkinleştirme**

Bilişsel hizmetler EM2, A2 veya P1 ve üstü Premium kapasite düğümleri için desteklenir. Bilişsel hizmetleri çalıştırmak için kapasitede ayrı bir AI iş yükü kullanılır. Genel önizleme (Haziran 2019 öncesi) sırasında bu iş yükü varsayılan olarak devre dışı bırakılmıştı. Power BI'da bilişsel hizmetleri kullanmadan önce yönetim portalının kapasite ayarlarında AI iş yükünün etkinleştirilmesi gerekir. İş yükleri bölümünde AI iş yükünü açmalı ve bu iş yükünün kullanmasını istediğiniz en büyük bellek miktarını tanımlamalısınız. Önerilen bellek sınırı %20'dir. Bu sınırın aşılması sorgunun yavaşlamasına neden olur.

![Power BI'da bilişsel hizmetler](media/service-cognitive-services/cognitive-services-01.png)

### <a name="getting-started-with-cognitive-services-in-power-bi"></a>**Power BI’da Bilişsel Hizmetler’i kullanmaya başlama**

Bilişsel Hizmetler dönüştürmeleri, [veri akışları için Self Servis Veri Hazırlığının](https://powerbi.microsoft.com/blog/introducing-power-bi-data-prep-wtih-dataflows/) bir parçasıdır. Verilerinizi Bilişsel Hizmetler'le zenginleştirmek için başlangıç olarak veri akışını düzenleyin.

![Veri akışını düzenleme](media/service-cognitive-services/cognitive-services-02.png)

Power Query Düzenleyicisi'nin üst şeridindeki **AI İç görüler** düğmesini seçin.

![Power Query Düzenleyicisi'nde AI içgörüler](media/service-cognitive-services/cognitive-services-03.png)

Açılan pencerede kullanmak istediğiniz işlevi ve dönüştürmek istediğiniz verileri seçin. Bu örnekte, inceleme metnini içeren sütunun yaklaşımını puanlıyorum.

![İşlev seçme](media/service-cognitive-services/cognitive-services-04.png)

**Cultureinfo** , metnin dilini belirtmeye yönelik isteğe bağlı bir giriştir. Bu alanda bir ISO kodu beklenir. Cultureinfo için giriş olarak bir sütunu veya statik bir alanı kullanabilirsiniz. Bu örnekte tüm sütun için dil olarak İngilizce (en) belirtilmiştir. Bu alanı boş bırakırsanız, Power BI işlevi uygulamadan önce dili otomatik olarak algılar. Ardından **Çağır** 'ı seçin.

![Çağır'ı seçin](media/service-cognitive-services/cognitive-services-05.png)

İşlevi çağırdıktan sonra, sonuç tabloya yeni bir sütun olarak eklenir. Dönüştürme de sorguya uygulanmış bir adım olarak eklenir.

![Yeni sütun oluşturulur](media/service-cognitive-services/cognitive-services-06.png)

İşlev birden çok çıkış alanı döndürürse, işlevin çağrılması birden çok çıkış alanının kaydını içeren yeni bir sütun ekler.

Verilerinize bir veya birden çok değeri sütun olarak eklemek için genişletme seçeneğini kullanın.

![Sütunu genişletme](media/service-cognitive-services/cognitive-services-07.png)

### <a name="available-functions"></a>**Kullanılabilir işlevler**

Bu bölümde Power BI'da Bilişsel Hizmetler'le kullanılabilen işlevler açıklanır.

#### <a name="detect-language"></a>**Dili Algıla**

Dil algılama işlevi metin girişini değerlendirir ve her alan için dil adını ve ISO tanımlayıcısını döndürür. Bu işlev dilin bilinmediği rastgele metinleri toplayan veri sütunlarında kullanışlıdır. İşlev, giriş olarak metin biçiminde veriler bekler.

Metin Analizi 120 dile kadar tanır. Daha fazla bilgi için [desteklenen dillere](https://docs.microsoft.com/azure/cognitive-services/text-analytics/text-analytics-supported-languages) bakın.

#### <a name="extract-key-phrases"></a>**Anahtar İfadeleri Ayıklama**

**Anahtar İfade Ayıklama** işlevi yapılandırılmamış metinleri değerlendirir ve her metin alanı için bir anahtar ifade listesi döndürür. İşlev, giriş olarak bir metin alanı gerektirir ve **Cultureinfo** için isteğe bağlı girişi kabul eder. (Bu makalenin başlarındaki **Başlarken** bölümüne bakın).

Anahtar ifade ayıklama, üzerinde çalışması için işleve daha büyük metin öbekleri verdiğinizde daha iyi sonuç verir. Bu, küçük metin bloklarında daha iyi çalışan yaklaşım analizinin tam tersidir. Her iki işlemden de en iyi sonuçları almak için, girişleri buna göre yeniden yapılandırmayı göz önünde bulundurun.

#### <a name="score-sentiment"></a>**Yaklaşım Puanlama**

**Yaklaşım Puanlama** işlevi metin girişini değerlendirir ve her belge için 0 (olumsuz) ile 1 (olumlu) arasında bir yaklaşım puanı döndürür. Bu işlev sosyal medyada, müşteri incelemelerinde ve tartışma forumlarında olumlu ve olumsuz yaklaşımı algılamak için yararlıdır.

Metin Analizi'nde 0 ile 1 arasında bir yaklaşım puanı oluşturmak için makine öğrenmesi sınıflandırma algoritması kullanılır. 1'e yaklaşan puanlar olumlu yaklaşımı ve 0'a yaklaşan puanlar olumsuz yaklaşımı gösterir. Model, yaklaşım ilişkilendirmeleri için çok büyük bir metinle önceden eğitilir. Şu anda kendi eğitim verilerinizi sağlamanız mümkün değildir. Model, metin analizi sırasında metin işleme, kısmi konuşma analizi, sözcük değiştirme ve sözcük ilişkilendirmeleri gibi tekniklerin bir bileşimini kullanır. Algoritma hakkında daha fazla bilgi için bkz. [Metin Analizine Giriş](/archive/blogs/machinelearning/machine-learning-and-text-analytics).

Yaklaşım analizi, metindeki belirli bir varlığın yaklaşımını ayıklamak yerine giriş alanının tamamında gerçekleştirilir. Uygulamada, büyük metin blokları yerine bir veya iki tümce içeren belgelerde puanlama doğruluğu gelişme eğilimi gösterir. Nesnellik değerlendirmesi aşamasında, model bir bütün olarak giriş alanının nesnel olduğunu veya yaklaşım içerdiğini saptar. Büyük ölçüde nesnel olan bir giriş alanı yaklaşım algılama aşamasına ilerletilmez; sonuçta 0,50 puan alır ve başka işlem yapılmaz. İşlem hattında ilerleyen giriş alanları için, sonraki aşamada giriş alanında algılanan yaklaşımın derecesine bağlı olarak 0,50'nin üstünde veya altında bir puan oluşturulur.

Şu anda Yaklaşım Analizi İngilizce, Almanca, İspanyolca ve Fransızcayı desteklemektedir. Diğer diller önizleme aşamasındadır. Daha fazla bilgi için bkz. [Desteklenen diller](https://docs.microsoft.com/azure/cognitive-services/text-analytics/text-analytics-supported-languages).

#### <a name="tag-images"></a>**Resimleri Etiketleme**

**Resimleri Etiketleme** işlevi 2.000'den fazla nesneye, canlıya, manzaraya ve eyleme dayanarak etiketler döndürür. Etiketler belirsizse veya bilinen gerçeklere uymuyorsa, etiketin anlamını bilinen ayar bağlamında netleştirmek için çıkışta 'ipuçları' sağlanır. Etiketler taksonomi olarak düzenlenmez ve devralınan hiyerarşiler yoktur. Bir içerik etiketi koleksiyonu, tam tümceler halinde biçimlendirilmiş insan tarafından okunabilir dilde görüntülenen bir görüntü 'açıklamasının' temelini oluşturur.

Resmi karşıya yükledikten veya resim URL'sini belirttikten sonra, Görüntü İşleme algoritmaları resimde tanımlanan nesnelere, canlılara ve eylemlere dayanarak etiketlerin çıkışını yapar. Etiketleme ön plandaki kişi gibi ana konuyla sınırlı değildir; ortamı (iç mekan veya dış mekan), mobilyaları, araçları, bitkileri, hayvanları, aksesuarları ve gereçleri de içerir.

Bu işleve giriş olarak bir resim URL'si ve base 64 alanı gerekir. Şu anda resim etiketleme İngilizce, İspanyolca, Japonca, Portekizce ve Basitleştirilmiş Çinceyi desteklemektedir. Daha fazla bilgi için bkz. [Desteklenen diller](https://docs.microsoft.com/rest/api/cognitiveservices/computervision/tagimage/tagimage#uri-parameters).

## <a name="automated-machine-learning-in-power-bi"></a>Power BI’da Otomatikleştirilmiş Makine Öğrenmesi

Veri akışları için otomatik makine öğrenmesi (AutoML), iş analistlerinin Makine Öğrenmesi (ML) modellerini doğrudan Power BI’da eğitmesine, doğrulamasına ve çağırmasına olanak tanır. Analistlerin modeli eğitmeye yönelik giriş verilerini belirtmek için veri akışlarını kullanabileceği yeni bir ML modeli oluşturmak için basit bir deneyim içerir. Hizmet en ilgili özellikleri otomatik olarak ayıklar, uygun bir algoritma seçer ve ML modelini ayarlayıp doğrular. Bir model eğitildikten sonra Power BI, doğrulama sonuçlarını içeren bir raporu otomatik olarak oluşturur. Model daha sonra veri akışı içindeki yeni veya güncelleştirilmiş veriler üzerinde çağrılabilir.

![Makine öğrenmesi ekranı](media/service-machine-learning-automated/automated-machine-learning-power-bi-01.png)

Otomatik makine öğrenmesi, Power BI Premium ve Embedded kapasitelerinde barındırılan veri akışları için kullanılabilir.

### <a name="working-with-automl"></a>AutoML ile çalışma

Veri akışları, büyük veriler için self servis veri hazırlığı sunar. AutoML, veri akışlarıyla tümleşiktir ve makine öğrenmesi modellerini Power BI içinden oluşturmak için veri hazırlığı çalışmalarınızdan yararlanmanızı sağlar.

Power BI’da AutoML, veri analistlerinin Power BI becerilerini kullanarak basitleştirilmiş bir deneyimle makine öğrenmesi modelleri oluşturmak için veri akışlarını kullanmasına olanak tanır. ML modellerinin oluşturulmasının altında yatan veri biliminin büyük bölümü Power BI ile otomatikleştirilir. AutoML, oluşturulan modelin kaliteli olduğundan ve ML modelinizi oluşturmak için kullanılan işlemin görünürlüğünü sağladığından emin olmaya yönelik korumalara sahiptir.

AutoML, veri akışları için **İkili Tahmin** , **Sınıflandırma** ve **Regresyon Modelleri** ’nin oluşturulmasını destekler. Bunlar, denetimli makine öğrenmesi tekniklerinin türleridir. Diğer bir deyişle, diğer gözlemlerin sonuçlarını tahmin etmek için geçmiş gözlemlerin bilinen sonuçlarını öğrenirler. Bir AutoML modelinin eğitimine yönelik giriş veri kümesi, bilinen sonuçlarla **etiketlenmiş** bir kayıt kümesidir.

Power BI’da AutoML, modellerinizi oluşturmak için [Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/service/overview-what-is-azure-ml)'in [otomatik ML](https://docs.microsoft.com/azure/machine-learning/service/concept-automated-ml) özelliğini tümleştirir. Ancak, Power BI’da AutoML kullanmak için bir Azure aboneliğinizin olması gerekmez. ML modellerini eğitme ve barındırma işlemi tamamen Power BI hizmeti tarafından yönetilir.

Bir ML modeli eğitildikten sonra AutoML, ML modelinizin olası performansını açıklayan bir Power BI raporunu otomatik olarak oluşturur. AutoML, girişleriniz arasında, modeliniz tarafından döndürülen tahminleri etkileyen başlıca etkileyicileri vurgulayarak açıklanabilirliği ön plana çıkarır. Rapor ayrıca modelin önemli ölçümlerini içerir.

Oluşturulan raporun diğer bölümlerinde modelin istatistiksel özeti ve eğitim ayrıntıları gösterilir. İstatistiksel özet, modelin standart veri bilimi performans ölçümlerini görmek isteyen kullanıcıları ilgilendirir. Eğitim ayrıntıları, modelinizi oluşturmak için çalıştırılan tüm yinelemeleri, ilişkili modelleme parametreleriyle birlikte özetler. Ayrıca, ML modelini oluşturmak için her bir girişin nasıl kullanıldığını açıklar.

Daha sonra ML modelinizi puanlama için verilerinize uygulayabilirsiniz. Veri akışı yenilendiğinde, verileriniz ML modelinizdeki tahminlerle güncelleştirilir. Power BI ayrıca ML modelinin ürettiği her tahmin için ayrı bir açıklama içerir.

### <a name="creating-a-machine-learning-model"></a>Makine öğrenmesi modeli oluşturma

Bu bölümde bir AutoML modelinin nasıl oluşturulacağı açıklanmaktadır.

#### <a name="data-prep-for-creating-an-ml-model"></a>ML modeli oluşturmak için veri hazırlığı

Power BI’da bir makine öğrenmesi modeli oluşturmak için öncelikle ML modelini eğitmek için kullanılan geçmiş sonuç bilgilerini içeren bir veri akışı oluşturmanız gerekir. Ayrıca, tahmin etmeye çalıştığınız sonuç için güçlü bir tahmin olabilecek herhangi bir iş ölçümünün hesaplanmış sütunlarını ekleyebilirsiniz. Veri akışınızı yapılandırma hakkında ayrıntılı bilgi için bkz. [Veri akışı yapılandırma ve kullanma](dataflows-configure-consume.md).

AutoML bir makine öğrenmesi modelini eğitmek için belirli veri gereksinimlerine sahiptir. Bu gereksinimler, ilgili model türlerine göre aşağıdaki bölümlerde açıklanmıştır.

#### <a name="configuring-the-ml-model-inputs"></a>ML modeli girişlerini yapılandırma

Bir AutoML modeli oluşturmak için, veri akışı varlığının **Eylemler** sütunundaki ML simgesini seçin ve **Makine öğrenmesi modeli ekle** seçeneğini belirleyin.

![Makine öğrenmesi modeli ekleme](media/service-machine-learning-automated/automated-machine-learning-power-bi-02.png)

ML modeli oluşturma işleminde size kılavuzluk eden sihirbazın bulunduğu basitleştirilmiş bir deneyim başlatılır. Sihirbaz aşağıdaki adımları içerir.

**1. Geçmiş verilerini içeren varlığı ve tahminini istediğiniz sonuç alanını seçin**

Sonuç alanı, aşağıdaki görüntüde gösterildiği gibi ML modeli eğitimine yönelik etiket özniteliğini tanımlar.

![Geçmiş sonuç verilerini seçme](media/service-machine-learning-automated/automated-machine-learning-power-bi-03.png)

**2. Model türü seçin**

Sonuç alanını belirttiğinizde AutoML, eğitilme olasılığı en yüksek ML modelini önermek üzere etiket verilerini analiz eder. Aşağıda gösterildiği gibi "Farklı bir model seçin" seçeneğine tıklayarak farklı bir model türü seçebilirsiniz.

![Model seçme](media/service-machine-learning-automated/automated-machine-learning-power-bi-04.png)

> [!NOTE]
> Bazı model türleri, seçtiğiniz veriler için desteklenmeyebilir ve bu nedenle devre dışı bırakılabilir. Yukarıdaki örnekte, sonuç alanı olarak bir metin sütunu seçildiği için Regresyon devre dışı bırakılmıştır.

**3. Modelin öngörücü sinyal olarak kullanmasını istediğiniz girişleri seçin**

AutoML, ML modeli eğitimi için kullanılabilecek girişleri önermek amacıyla seçili varlığın bir örneğini analiz eder. Seçili olmayan alanların yanında açıklamalar verilir. Belirli bir alanda çok fazla farklı değer veya yalnızca bir değer varsa ya da çıkış alanı ile düşük veya yüksek bağıntı varsa, bunun yapılması önerilmez.

Sonuç alanına (veya etiket alanına) bağlı olan hiçbir giriş, kendi performansını etkileyeceğinden ML modelini eğitmek için kullanılmamalıdır. Bu tür alanlar "çıkış alanı ile kuşku verici düzeyde yüksek bağıntılı" olarak işaretlenir. Bu alanları eğitim verilerine eklemek, modelin doğrulama veya test verileri üzerinde iyi performans gösterdiği ancak puanlama için üretimde kullanıldığında aynı performansı gerçekleştiremediği etiket sızıntısı durumuna neden olur. Etiket sızıntısı, eğitim modeli performansı doğru olamayacak kadar iyi olduğunda AutoML modellerinde olası bir sorun olabilir.

Bu özellik önerisi bir veri örneğini temel aldığı için kullanılan girişleri gözden geçirmeniz gerekir. Seçimleri yalnızca modelin incelemesini istediğiniz alanları içerecek şekilde değiştirme seçeneğiniz vardır. Ayrıca, varlık adının yanındaki onay kutusunu seçerek tüm alanları seçebilirsiniz.

![Giriş alanlarını özelleştirme](media/service-machine-learning-automated/automated-machine-learning-power-bi-05.png)

**4. Modelinizi adlandırma ve yapılandırmanızı kaydetme**

Son adımda, modeli adlandırabilir ve Kaydet ve eğit’i seçerek ML modelinin eğitimini başlatabilirsiniz. Hızlı sonuçlar görmek için eğitim süresini azaltmayı veya en iyi modeli elde etmek için eğitim süresini artırmayı seçebilirsiniz.

![Modelinizi adlandırma](media/service-machine-learning-automated/automated-machine-learning-power-bi-06.png)

#### <a name="ml-model-training"></a>ML modeli eğitimi

AutoML modellerinin eğitimi, veri akışını yenilemenin bir parçasıdır. AutoML ilk olarak verilerinizi eğitim için hazırlar.
AutoML, sağladığınız geçmiş verileri eğitim ve test veri kümelerine böler. Test veri kümesi, eğitimin ardından model performansını doğrulamak için kullanılan bir gizleme kümesidir. Bunlar veri akışında **Eğitim ve Test** varlıkları olarak uygulanır. AutoML, model doğrulaması için çapraz doğrulamayı kullanır.

Ardından, her giriş alanı analiz edilir ve görevlendirme yapılır. Bu işlem eksik değerlerin yerine değiştirilen değerleri getirir. AutoML tarafından birkaç farklı görevlendirme stratejisi kullanılır. Sayısal özellikler olarak ele alınan giriş özniteliklerinin atanması için sütun değerlerinin ortalaması kullanılır. Kategori özellikleri olarak ele alınan giriş özniteliklerinin atanması için AutoML sütun değerlerinin modunu kullanır. Atama için kullanılan değerlerin ortalaması ve modu, alt örneği alınmış eğitim veri kümesinde AutoML çerçevesi tarafından hesaplanır.

Ardından, örnekleme ve normalleştirme gereken şekilde verilerinize uygulanır. Sınıflandırma modelleri için, AutoML giriş verilerini çok katmanlı örnekleme aracılığıyla çalıştırır ve satır sayılarının tümü için eşit olduğundan emin olmak üzere sınıfları dengeler.

AutoML, veri türüne ve istatistiksel özelliklerine göre her bir seçili giriş alanına birkaç dönüşüm uygular. AutoML, ML modelinizi eğitirken kullanılacak özellikleri eğitmek için bu dönüşümleri kullanır.

AutoML modellerinin eğitim süreci, en iyi performansa sahip modeli bulmak için farklı modelleme algoritmalarına ve hiper parametre ayarlarına sahip 50'ye kadar yinelemeden oluşur. AutoML gözlemlenen bir performans iyileşmesi olmadığını fark ederse eğitim daha az yinelemeyle sona erebilir. Bu modellerin her birinin performansı, gizleme testi veri kümesiyle doğrulama yapılarak değerlendirilir. Bu eğitim adımı sırasında AutoML, bu yinelemelerin eğitimi ve doğrulanması için birkaç işlem hattı oluşturur. Veri kümenizin boyutuna ve kullanılabilir kapasite kaynaklarına bağlı olarak, modellerin performansını değerlendirme işlemi sihirbazda yapılandırılmış eğitim süresine kadar birkaç dakika ile birkaç saat arasında sürebilir.

Bazı durumlarda, oluşturulan son model daha iyi tahmine dayalı performans sağlamak için birden çok modelin kullanıldığı grup öğrenmesini kullanabilir.

#### <a name="automl-model-explainability"></a>AutoML modelinin açıklanabilirliği

Model eğitildikten sonra AutoML, giriş özellikleri ile model çıkışı arasındaki ilişkiyi analiz eder. Her giriş özelliği için gizleme test veri kümesinin model çıkışındaki değişikliğin büyüklüğünü değerlendirir. Bu, _özelliğin önemi_ olarak bilinir. Bu işlem, eğitim tamamlandıktan sonra yenilemenin bir parçası olarak gerçekleşir. Bu nedenle, yenileme işleminiz sihirbazda yapılandırılan eğitim süresinden daha uzun sürebilir.

![Özelliğin önemi](media/service-machine-learning-automated/automated-machine-learning-power-bi-07.png)

#### <a name="automl-model-report"></a>AutoML model raporu

AutoML, genel özellik önemiyle birlikte doğrulama sırasında modelin performansını özetleyen bir Power BI raporu oluşturur. Veri akışı yenilemesi başarılı olduktan sonra bu rapora Makine Öğrenmesi Modeli sekmesinden erişilebilir. Rapor, ML modelinin gizleme test verilerine uygulanması ve bilinen sonuç değerleriyle tahminlerin karşılaştırılması sonucunda elde edilecek sonuçları özetler.

Performansını anlamak için model raporunu gözden geçirebilirsiniz. Ayrıca, modelin önemli etkileyicilerinin bilinen sonuçlar hakkındaki iş öngörüleriyle uyumlu olduğunu doğrulayabilirsiniz.

Rapordaki model performansını açıklamak için kullanılan grafikler ve ölçüler model türüne bağlıdır. Bu performans grafikleri ve ölçümler aşağıdaki bölümlerde açıklanmıştır.

Rapordaki ek sayfalar, modelle ilgili istatistiksel ölçümleri bir veri bilimi perspektifinden açıklayabilir. Örneğin, **İkili Tahmin** raporu bir kazanç grafiği ve modelin ROC eğrisini içerir.

Raporlar ayrıca modelin nasıl eğitildiğine ilişkin açıklama içeren bir **Eğitim Ayrıntıları** sayfası ve yineleme çalıştırmalarının her birindeki model performansını açıklayan bir grafik içerir.

![Eğitim ayrıntıları](media/service-machine-learning-automated/automated-machine-learning-power-bi-08.png)

Bu sayfadaki başka bir bölümde, giriş alanında algılanan tür ve eksik değerleri doldurmak için kullanılan atama yöntemi açıklanmaktadır. Ayrıca son model tarafından kullanılan parametreleri içerir.

![Model hakkında daha fazla bilgi](media/service-machine-learning-automated/automated-machine-learning-power-bi-09.png)

Oluşturulan model grup öğrenmesi kullanıyorsa, **Eğitim Ayrıntıları** sayfasında grubu oluşturan her bir üyenin ağırlığını ve parametrelerini gösteren bir grafik de bulunur.

![Gruptaki ağırlık](media/service-machine-learning-automated/automated-machine-learning-power-bi-10.png)

### <a name="applying-the-automl-model"></a>AutoML modelini uygulama

Oluşturulan ML modelinin performansından memnunsanız, veri akışınız yenilendiğinde modeli yeni veya güncelleştirilmiş verilere uygulayabilirsiniz. Bu işlemi, model raporunda sağ üst köşedeki **Uygula** düğmesini veya Makine Öğrenmesi Modelleri sekmesindeki ML Modeli Uygula düğmesini seçerek yapabilirsiniz.

ML modelini uygulamak için, uygulanması gereken varlığın adını ve model çıkışı için bu varlığa eklenecek sütunların ön ekini belirtmeniz gerekir. Sütun adları için varsayılan ön ek, model adıdır. _Uygula_ işlevi, model türüne özgü ek parametreler içerebilir.

ML modelinin uygulanması, çıkış varlığında puan veren her bir satır için tahminler ve kişiselleştirilmiş açıklamalar içeren iki yeni veri akışı varlığı oluşturur. Örneğin, _PurchaseIntent_ modelini _OnlineShoppers_ varlığına uygularsanız, çıkış **OnlineShoppers zenginleştirilmiş PurchaseIntent** ve **OnlineShoppers zenginleştirilmiş PurchaseIntent açıklamaları** varlıklarını oluşturur. Zenginleştirilmiş varlıktaki her satır için **Açıklamalar** , giriş özelliğine göre zenginleştirilmiş açıklamalar varlığındaki birden fazla satıra bölünür. **ExplanationIndex** , zenginleştirilmiş açıklamalar varlığındaki satırları zenginleştirilmiş varlıktaki satırla eşlemeye yardımcı olur.

![Sorgu düzenleyicisi](media/service-machine-learning-automated/automated-machine-learning-power-bi-11.png)

PQO işlev tarayıcısında Yapay Zeka İçgörülerini kullanarak aynı çalışma alanındaki herhangi bir veri akışında varlıklara Power BI AutoML modelini de uygulayabilirsiniz. Böylece, aynı çalışma alanında başkaları tarafından oluşturulan modelleri, modeli içeren veri akışının sahibi olma zorunluluğu olmadan kullanabilirsiniz. Power Query, çalışma alanındaki tüm Power BI ML modellerini keşfeder ve bunları dinamik Power Query işlevleri olarak kullanıma sunar.  Power Query Düzenleyicisi’nin şeridinden bu işlevlere erişerek veya M işlevini doğrudan çağırarak da bunları çağırabilirsiniz. Bu işlevsellik şu anda yalnızca Power BI veri akışlarında ve Power BI hizmetindeki Power Query Online'da desteklenmektedir. Bunun AutoML sihirbazı kullanılarak bir veri akışında ML modellerinin uygulanmasından çok farklı olduğunu unutmayın. Bu yöntem kullanılarak oluşturulan bir açıklamalar varlığı yoktur ve veri akışının sahibi olmadığınız sürece model eğitimi raporlarına erişemezsiniz veya modeli yeniden eğitemezsiniz. Kaynak modeli düzenlenirse (giriş alanları eklenerek veya kaldırılarak) ya da model veya kaynak veri akışı silinirse bu bağımlı veri akışı bozulur.

![PQO İşlev tarayıcısını kullanarak model uygulama](media/service-machine-learning-automated/automated-machine-learning-power-bi-20.png)

Modeli uyguladıktan sonra, veri akışı her yenilendiğinde AutoML tahminlerinizi güncel tutar.

Bir Power BI raporundaki ML modelinden içgörü ve tahminleri kullanmak için, **dataflows** bağlayıcısını kullanarak Power BI Desktop’tan çıkış varlığına bağlanabilirsiniz.

### <a name="binary-prediction-models"></a>İkili Tahmin modelleri

Daha resmi adıyla **ikili sınıflandırma modelleri** olarak bilinen İkili Tahmin modelleri, bir veri kümesini iki grup halinde sınıflandırmak için kullanılır. Bunlar, ikili sonucu olan olayları tahmin etmek için kullanılır. Örneğin, bir satış fırsatının dönüştürüp dönüştürmeyeceği, bir hesabın değişip değişmeyeceği, bir faturanın zamanında ödenip ödenmeyeceği, bir işlemin hileli olup olmadığı vb.

İkili Tahmin modelinin çıkışı, hedef sonuca ulaşma olasılığını tanımlayan bir olasılık puandır.

#### <a name="training-a-binary-prediction-model"></a>İkili Tahmin modelini eğitme

Önkoşullar:

- Her sonuç sınıfı için en az 20 satır geçmiş veri gereklidir

İkili Tahmin modeli oluşturma işlemi, yukarıdaki **ML modeli girişlerini yapılandırma** bölümünde açıklanan diğer AutoML modelleriyle aynı adımları izler. Tek fark, en çok ilgilendiğiniz hedef sonuç değerini seçebileceğiniz "Bir model seçin" adımındadır. Model doğrulama sonuçlarını özetleyecek otomatik olarak oluşturulan raporda kullanılacak sonuçlar için kolay etiketler de sağlayabilirsiniz.

![İkili tahmin sihirbazı](media/service-machine-learning-automated/automated-machine-learning-power-bi-12.png)

#### <a name="binary-prediction-model-report"></a>İkili Tahmin modeli raporu

İkili Tahmin modeli, bir kaydın hedef sonuca ulaşma olasılığını çıkış olarak oluşturur. Rapor, olasılık eşiğinin üstünde ve altındaki puanların nasıl yorumlandığını etkileyen bir dilimleyici içerir.

Rapor, modelin performansını _Gerçek Pozitifler, Hatalı Pozitifler, Gerçek Negatifler ve Hatalı Negatifler_ cinsinden açıklar. Gerçek Pozitifler ve Gerçek Negatifler, çıkış verilerindeki iki sınıfın doğru şekilde tahmin edilmiş sonuçlardır. Hatalı Pozitifler, Hedef sonuca ulaşacağı tahmin edilen ancak gerçekte ulaşmayan kayıtlardır. Buna karşılık, Hatalı Negatifler Hedef sonuca ulaşmış ancak ulaşmadığı tahmin edilen kayıtlardır.

Duyarlılık ve Yakalama gibi ölçüler, öngörülen sonuçlar üzerinde olasılık eşiğinin etkisini anlatmaktadır. Duyarlık ile Yakalama arasında dengeli bir uzlaşma sağlayan eşiği seçmek için olasılık eşiği dilimleyicisini kullanabilirsiniz.

![Doğruluk önizlemesi](media/service-machine-learning-automated/automated-machine-learning-power-bi-13.png)

Rapor ayrıca en yüksek kârı üretmek için hedeflenmesi gereken nüfus alt kümesini tanımlamaya yardımcı olacak bir Maliyet-Fayda analizi de içerir. Hedeflemenin tahmini birim maliyeti ve hedef sonucu elde etmenin birim kazancı bilinen Maliyet-Kazanç analizinde kârın en üst düzeye çıkarılması amaçlanır. Bu aracı kullanarak, kârı en üst düzeye çıkarmak için grafikteki maksimum noktaya göre olasılık eşiğinizi seçebilirsiniz. Bu grafiği, olasılık eşiği seçiminizin kâr veya maliyetini hesaplamak üzere de kullanabilirsiniz.

![Maliyet Kazancı](media/service-machine-learning-automated/automated-machine-learning-power-bi-14.png)

Model raporunun **Doğruluk Raporu** sayfasında, _Kümülatif Kazançlar_ grafiği ve modelin ROC eğrisi bulunur. Bunlar, model performansının istatistiksel ölçüleridir. Raporlar gösterilen grafiklerin açıklamalarını içerir.

![Doğruluk raporu ekranı](media/service-machine-learning-automated/automated-machine-learning-power-bi-15.png)

#### <a name="applying-a-binary-prediction-model"></a>İkili Tahmin modeli uygulama

İkili tahmin modelini uygulamak için, ML modelinden tahminleri uygulamak istediğiniz verileri içeren varlığı belirtmeniz gerekir. Diğer parametreler, çıkış sütunu adı önekini ve tahmin edilen sonucun sınıflandırılmasına yönelik olasılık eşiğini içerir.

![Tahmin girişleri](media/service-machine-learning-automated/automated-machine-learning-power-bi-16.png)

Bir İkili Tahmin modeli uygulandığında zenginleştirilmiş çıkış varlığına dört çıkış sütunu ekler: **Outcome** , **PredictionScore** , **PredictionExplanation** ve **ExplanationIndex**. Model uygulandığında, varlıktaki sütun adları belirtilen ön eki alır.

**PredictionScore** , hedef sonuca ulaşma olasılığını tanımlayan bir olasılık puanıdır.

**Outcome** sütunu tahmin edilen sonuç etiketini içerir. Eşiği aşma olasılıklarını içeren kayıtların hedef sonuca ulaşma olasılığı yüksek olarak tahmin edilir ve bu kayıtlar True olarak etiketlenir. Eşiğin altındaki kayıtlar, sonuca ulaşma olasılığı düşük olarak tahmin edilir ve False olarak etiketlenir.

**PredictionExplanation** sütunu, giriş özelliklerinin **PredictionScore** üzerinde sahip olduğu etki ile birlikte bir açıklama içerir.

### <a name="classification-models"></a>Sınıflandırma modelleri

Sınıflandırma modelleri, bir veri kümesini birden çok grup veya sınıfa ayırmak için kullanılır. Birden çok olası sonuçtan birine ulaşabilecek olayları tahmin etmek için kullanılır. Örneğin, müşterinin çok yüksek, yüksek, orta veya düşük Ömür Değerine sahip olma olasılığı, varsayılan riskin Yüksek, Orta, Düşük veya Çok Düşük olması vb.

Sınıflandırma modelinin çıkışı, bir kaydın belirli bir sınıfa yönelik ölçütlere ulaşmasının olasılığını belirleyen bir olasılık puandır.

#### <a name="training-a-classification-model"></a>Sınıflandırma modeli eğitimi

Sınıflandırma modeline ait eğitim verilerinizi içeren giriş varlığının, bilinen sonuçları tanımlayan geçmiş sonuç alanı olarak bir dize veya tam sayı alanına sahip olması gerekir.

Önkoşullar:

- Her sonuç sınıfı için en az 20 satır geçmiş veri gereklidir

Sınıflandırma modeli oluşturma işlemi, yukarıdaki **ML modeli girişlerini yapılandırma** bölümünde açıklanan diğer AutoML modelleriyle aynı adımları izler.

#### <a name="classification-model-report"></a>Sınıflandırma modeli raporu

Sınıflandırma modeli raporu, ML modelinin gizleme test verilerine uygulanmasıyla ve bir kaydın tahmin edilen sınıfı gerçek bilinen sınıfla karşılaştırılarak oluşturulur.

Model raporu, bilinen her sınıf için doğru ve yanlış sınıflandırılmış kayıtların dökümünden oluşan bir grafik içerir.

![Model raporu](media/service-machine-learning-automated/automated-machine-learning-power-bi-17.png)

Sınıfa özgü daha fazla ayrıntıya gitmek, bilinen bir sınıfa yönelik tahminlerin nasıl dağıtıldığına ilişkin bir analiz sağlar. Bu analiz, söz konusu bilinen sınıfın kayıtlarının hatalı sınıflandırılabileceği diğer sınıfları gösterir.

Rapordaki model açıklaması her sınıf için en iyi tahmin unsurlarını da içerir.

Sınıflandırma modeli raporu ayrıca bu makalenin önceki kısımlarında yer alan **AutoML model raporu** bölümünde açıklandığı gibi diğer model türlerinin sayfalarına benzer bir Eğitim Ayrıntıları sayfası içerir.

#### <a name="applying-a-classification-model"></a>Sınıflandırma modelini uygulama

Bir Sınıflandırma ML modelini uygulamak için, giriş verileri ve çıkış sütunu adı ön ekiyle birlikte varlığı belirtmeniz gerekir.

Bir Sınıflandırma modeli uygulandığında zenginleştirilmiş çıkış varlığına beş çıkış sütunu ekler: **ClassificationScore** , **ClassificationResult** , **ClassificationExplanation** , **ClassProbabilities** ve **ExplanationIndex**. Model uygulandığında, varlıktaki sütun adları belirtilen ön eki alır.

**ClassProbabilities** sütunu, her olası sınıfın kaydına ait olasılık puanlarının listesini içerir.

**ClassificationScore** , bir kaydın belirli bir sınıfa yönelik ölçütlere ulaşma olasılığını tanımlayan bir olasılık yüzdesidir.

**ClassificationResult** sütunu, kayıt için en yüksek olasılıkla tahmin edilen sınıfı içerir.

**ClassificationExplanation** sütunu, giriş özelliklerinin **ClassificationScore** üzerinde sahip olduğu etki ile birlikte bir açıklama içerir.

### <a name="regression-models"></a>Regresyon modelleri

Regresyon modelleri, sayısal bir değeri tahmin etmek için kullanılır. Örneğin, bir satış kaynağından gerçekleştirilme olasılığı yüksek olan gelir, bir hesabın ömür değeri, ödenme olasılığı yüksek bir alacak faturasının tutarı, bir faturanın ödenebileceği tarih vb.

Regresyon modelinin çıkışı, tahmin edilen değerdir.

#### <a name="training-a-regression-model"></a>Regresyon modeli eğitimi

Regresyon modeline ait eğitim verilerinizi içeren giriş varlığının, bilinen sonuç değerlerini tanımlayan sonuç alanı olarak bir sayısal alana sahip olması gerekir.

Önkoşullar:

- Regresyon modeli için en az 100 satır geçmiş veri gereklidir

Regresyon modeli oluşturma işlemi, yukarıdaki **ML modeli girişlerini yapılandırma** bölümünde açıklanan diğer AutoML modelleriyle aynı adımları izler.

#### <a name="regression-model-report"></a>Regresyon modeli raporu

Diğer AutoML model raporları gibi Regresyon raporu da modelin gizleme test verilerine uygulanmasından elde edilen sonuçları temel alır.

Model raporu, tahmin edilen değerleri gerçek değerlerle karşılaştıran bir grafik içerir. Bu grafikte köşegenden uzaklık, tahmindeki hatayı gösterir.

Fazlalık hata grafiği, gizleme testi veri kümesindeki farklı değerler için ortalama hata yüzdesinin dağılımını gösterir. Yatay eksen, grubun gerçek değerinin ortalamasını, söz konusu aralıktaki sıklığı veya değer sayısını gösteren kabarcığın boyutuyla temsil eder. Dikey eksen ortalama fazlalık hatasıdır.

![Fazlalık hata grafiği](media/service-machine-learning-automated/automated-machine-learning-power-bi-18.png)

Regresyon modeli raporu ayrıca yukarıdaki **AutoML model raporu** bölümünde açıklandığı gibi diğer model türlerinin raporlarına benzer bir Eğitim Ayrıntıları sayfası içerir.

#### <a name="applying-a-regression-model"></a>Regresyon modelini uygulama

Bir Regresyon ML modelini uygulamak için, giriş verileri ve çıkış sütunu adı ön ekiyle birlikte varlığı belirtmeniz gerekir.

![Regresyon uygulama](media/service-machine-learning-automated/automated-machine-learning-power-bi-19.png)

Bir Regresyon modeli uygulandığında zenginleştirilmiş çıkış varlığına üç çıkış sütunu ekler: **RegressionResult** , **RegressionExplanation** ve **ExplanationIndex**. Model uygulandığında, varlıktaki sütun adları belirtilen ön eki alır.

**RegressionResult** sütunu, giriş alanlarını temel alarak kaydın tahmin edilen değerini gösterir. **RegressionExplanation** sütunu, giriş özelliklerinin **RegressionResult** üzerinde sahip olduğu etki ile birlikte bir açıklama içerir.

## <a name="azure-machine-learning-integration-in-power-bi"></a>Power BI'da Azure Machine Learning tümleştirmesi

Pek çok kuruluş işleriyle ilgili daha iyi öngörüler ve tahminler elde etmek için **Machine Learning** modellerini kullanıyor. Raporlarınızda, panolarınızda ve diğer analizlerinizde bu modelleri görselleştirme ve içgörüleri çağırma olanağı, bu içgörüleri en çok ihtiyaç duyan işletme kullanıcılarına yaymanıza yardımcı olabilir.  Power BI şimdi sorunsuz işaretleyip tıklama hareketlerini kullanarak Azure Machine Learning'de barındırılan modellerden gelen içgörüleri birleştirmenizi basitleştirir.

Bu özelliği kullanmak için bir veri bilimcisi Azure portalını kullanarak BI analistine Azure ML modeli üzerinde erişim verebilir.  Ardından, her oturumun başlangıcında Power Query kullanıcının erişimi olan tüm Azure ML modellerini keşfeder ve bunları dinamik Power Query işlevleri olarak kullanıma sunar.  Kullanıcı Power Query Düzenleyicisi'nin şeridinden bu işlevlere erişerek bunları çağırabileceği gibi M işlevini doğrudan da çağırabilir. Ayrıca Power BI bir satır kümesi için Azure ML modelini çağırırken erişim isteklerini otomatik toplu iş olarak işleyerek daha iyi bir performans elde edebilir.

Bu işlevsellik şu anda yalnızca Power BI veri akışlarında ve Power BI hizmetindeki Power Query çevrimiçinde desteklenmektedir.

Veri akışları hakkında daha fazla bilgi edinmek için bkz. [Veri akışlarına giriş ve self servis veri hazırlığı](dataflows-introduction-self-service.md).

Azure Machine Learning hakkında daha fazla bilgi edinmek için bkz:

- Genel Bakış:  [Azure Machine Learning nedir?](https://docs.microsoft.com/azure/machine-learning/service/overview-what-is-azure-ml)
- Azure Machine Learning için Hızlı Başlangıçlar ve Öğreticiler:  [Azure Machine Learning Belgeleri](https://docs.microsoft.com/azure/machine-learning/)

> [!NOTE]
> Azure Machine Learning tümleştirmesini kullanmak için Power BI Premium aboneliği gerekir.

### <a name="granting-access-to-the-azure-ml-model-to-a-power-bi-user"></a>Power BI kullanıcısına Azure ML modeli üzerinde erişim verme

Power BI'dan Azure ML modeline erişmek için, kullanıcının Azure aboneliğine **Okuma** erişimi olmalıdır.  Ek olarak:

- Machine Learning Studio (klasik) modelleri için, Machine Learning Studio (klasik) web hizmetine **Okuma** erişiminiz olmalıdır
- Machine Learning modelleri için, Machine Learning çalışma alanına **Okuma** erişiminiz olmalıdır

Bu makaledeki adımlarda Power BI kullanıcısına Azure ML hizmetinde barındırılan model üzerinde erişim verme işlemi açıklanır. Bu sayede bu modele bir Power Query işlevi olarak erişebilirler.  Diğer ayrıntılar için bkz. [RBAC'yi ve Azure portalını kullanarak erişimi yönetme](https://docs.microsoft.com/azure/role-based-access-control/role-assignments-portal).

1. [Azure portalında](https://portal.azure.com) oturum açın.

2. **Abonelikler** sayfasına gidin. **Abonelikler** sayfasını, Azure portalının gezinti menüsündeki **Tüm Hizmetler** listesi aracılığıyla bulabilirsiniz.

    [ ![Azure abonelikleri sayfası](media/service-machine-learning-integration/machine-learning-integration-01.png) ](media/service-machine-learning-integration/machine-learning-integration-01.png#lightbox)

3. Aboneliğinizi seçin.

    [ ![Aboneliğinizi seçme](media/service-machine-learning-integration/machine-learning-integration-02.png) ](media/service-machine-learning-integration/machine-learning-integration-02.png#lightbox)

4. **Erişim Denetimi (IAM)** öğesini ve sonra da **Ekle** düğmesini seçin.

    [ ![Erişim denetimi IAM](media/service-machine-learning-integration/machine-learning-integration-03.png) ](media/service-machine-learning-integration/machine-learning-integration-03.png#lightbox)

5. Rol olarak **Okuyucu** 'yu seçin. Azure ML modeline erişim vermek istediğiniz Power BI kullanıcısını seçin.

    [ ![Rol olarak Okuyucu'yu seçme](media/service-machine-learning-integration/machine-learning-integration-04.png) ](media/service-machine-learning-integration/machine-learning-integration-04.png#lightbox)

6. **Kaydet** 'i seçin.

7. Kullanıcıya belirli bir Machine Learning Studio (klasik) web hizmeti *veya* modeli barındıran Machine Learning çalışma alanı üzerinde **Okuma** erişimi vermek için üç ile altı arasındaki adımları yineleyin.

### <a name="schema-discovery-for-machine-learning-models"></a>Machine Learning modelleri için şema bulma

Veri bilimcileri Machine Learning için makine öğrenmesi modellerini geliştirir hatta dağıtırken öncelikli olarak Python kullanır.  Model için şema dosyası oluşturma görevini otomatikleştirmenize yardımcı olan Machine Learning Studio'dan (klasik) farklı olarak, Machine Learning'de veri bilimcisinin Python kullanarak şema dosyasını açıkça oluşturması gerekir.

Bu şema dosyası, Machine Learning modelleri için dağıtılan web hizmetine dahil edilmelidir. Şemayı web hizmeti için otomatik olarak oluşturmak isterseniz, dağıtılan modelin giriş betiğinde bir giriş/çıkış örneği sağlamalısınız. Lütfen [Azure Machine Learning hizmeti belgelerine sahip Dağıtım modellerindeki Otomatik Swagger şema oluşturma alt bölümüne (İsteğe bağlı)](https://docs.microsoft.com/azure/machine-learning/how-to-deploy-and-where#optional-define-model-web-service-schema) bakın. Bu bağlantı, şema oluşturma deyimlerine sahip örnek giriş betiğini içerir. 

Özellikle, giriş betiğindeki *\@input_schema* ve *\@output_schema* işlevleri, *input_sample* ve *output_sample* değişkenlerindeki giriş ve çıkış örneği biçimlerine başvurur ve dağıtım sırasında web hizmeti için bir OpenAPI (Swagger) belirtimi oluşturmak üzere bu örnekleri kullanır.

Bu şema oluşturma yönergeleri, giriş betiği güncelleştirilerek, Azure Machine Learning SDK kullanan otomatik makine öğrenimi denemeleri kullanılarak oluşturulan modellere de uygulanmalıdır.

> [!NOTE]
> Azure Machine Learning görsel arabirimi kullanılarak oluşturulan modeller şu anda şema oluşturmayı desteklemiyor ancak daha sonraki sürümlerde destekleyecek. 

### <a name="invoking-the-azure-ml-model-in-power-bi"></a>Power BI'da Azure ML modelini çağırma

Size erişim verilmiş olan herhangi bir Azure ML modelini veri akışınız içinde doğrudan Power Query Düzenleyicisi'nden çağırabilirsiniz. Azure ML modellerine erişmek için, aşağıdaki resimde gösterildiği gibi Azure ML modelinizden gelen içgörülerle zenginleştirmek istediğiniz varlığa ilişkin **Düzenle** düğmesini seçin.

[ ![Power BI hizmeti - varlığı düzenleme](media/service-machine-learning-integration/machine-learning-integration-05.png) ](media/service-machine-learning-integration/machine-learning-integration-05.png#lightbox)

**Düzenle** düğmesi seçildiğinde veri akışınızdaki varlıklar için Power Query Düzenleyicisi açılır.

[ ![Power Query Düzenleyicisi](media/service-machine-learning-integration/machine-learning-integration-06.png) ](media/service-machine-learning-integration/machine-learning-integration-06.png#lightbox)

Şeritte **Yapay Zeka İçgörüleri** düğmesini seçin ve ardından gezinti menüsünden _Azure Machine Learning Modelleri_ klasörünü seçin. Erişiminiz olan tüm Azure ML modelleri burada Power Query işlevleri olarak listelenir. Ayrıca, Azure ML modeli için giriş parametreleri de otomatik olarak ilgili Power Query işlevinin parametreleri olarak eşlenir.

Azure ML modelini çağırmak için, açılan listeden seçilen tüm varlık sütunlarını giriş olarak belirtebilirsiniz. Sütun simgesini giriş iletişim kutusunun sol tarafına doğru döndürerek giriş olarak bir sabitin kullanılmasını da belirtebilirsiniz.

[ ![sütun seçme](media/service-machine-learning-integration/machine-learning-integration-07.png) ](media/service-machine-learning-integration/machine-learning-integration-07.png#lightbox)

Azure ML modeli çıkışının önizlemesini varlık tablosunda yeni bir sütun olarak görüntülemek için **Çağır** 'ı seçin. Ayrıca model çağrısını da sorgu için uygulanmış bir adım olarak görürsünüz.

[ ![Çağır'ı seçme](media/service-machine-learning-integration/machine-learning-integration-08.png) ](media/service-machine-learning-integration/machine-learning-integration-08.png#lightbox)

Model birden çok çıkış parametresi döndürürse, bunlar çıkış sütununda bir kayıt olarak gruplandırılır. Sütunu genişletip ayrı sütunlarda tek tek çıkış parametreleri oluşturabilirsiniz.

[ ![sütunu genişletme](media/service-machine-learning-integration/machine-learning-integration-09.png) ](media/service-machine-learning-integration/machine-learning-integration-09.png#lightbox)

Veri akışınızı kaydettikten sonra, varlık tablosundaki yeni veya güncelleştirilmiş satırlar için veri akışını her yenilediğinizde model otomatik olarak çağrılır.

## <a name="next-steps"></a>Sonraki adımlar

Bu makalede, Power BI hizmetinde Veri Akışları için Otomatik Makine Öğrenmesi’ne genel bir bakış verilmiştir. Aşağıdaki makaleler de yararlı olabilir.

- [Öğretici: Power BI’da Makine Öğrenmesi modeli oluşturma ](../../connect-data/service-tutorial-build-machine-learning-model.md)
- [Öğretici: Power BI’da Bilişsel Hizmetler’i kullanma](../../connect-data/service-tutorial-use-cognitive-services.md)
- [Öğretici: Power BI'da Machine Learning Studio (klasik) modelini çağırma (Önizleme)](../../connect-data/service-tutorial-invoke-machine-learning-model.md)

Aşağıdaki makaleler veri akışları ve Power BI hakkında daha fazla bilgi sunmaktadır:

* [Veri akışlarına giriş ve self servis veri hazırlığı](dataflows-introduction-self-service.md)
* [Veri akışı oluşturma](dataflows-create.md)
* [Veri akışı yapılandırma ve kullanma](dataflows-configure-consume.md)
* [Veri akışı depolama alanını Azure Data Lake 2. Nesil kullanacak şekilde yapılandırma](dataflows-azure-data-lake-storage-integration.md)
* [Veri akışlarının Premium özellikleri](dataflows-premium-features.md)
* [Veri akışı sınırlamaları ve önemli noktalar](dataflows-features-limitations.md) 