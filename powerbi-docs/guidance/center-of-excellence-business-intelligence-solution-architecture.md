---
title: Üstün Başarı Merkezi'nde iş zekası çözümü mimarisi
description: Sağlam bir iş zekası platformu tasarlama ve geliştirme aşamalarında dikkate almanız gerekenleri öğrenin.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 08/19/2020
ms.author: v-pemyer
ms.openlocfilehash: fe55c789f5af644a802bc5c5f648315744a074be
ms.sourcegitcommit: f73ea4b9116ad186817ec5cc5d5f487d49cc0cb0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/20/2020
ms.locfileid: "88638692"
---
# <a name="bi-solution-architecture-in-the-center-of-excellence"></a>Üstün Başarı Merkezi'nde iş zekası çözümü mimarisi

Bu makale, BT uzmanlarına ve BT yöneticilerine yöneliktir. COE’de iş zekası çözümü mimarisi ve kullanılan farklı teknolojiler hakkında bilgi edineceksiniz. Azure, Power BI ve Excel, bu teknolojilerden bazılarıdır. Bu çözümleri birlikte kullanarak ölçeklenebilir ve veri temelli bir bulut iş zekası platformu oluşturabilirsiniz.

Sağlam bir iş zekası platformu oluşturmak, bir köprü inşa etmeye benzer. Kaynakta bulunan verileri dönüştürüp zenginleştirerek veri tüketicilerine sunan bir aracıdır. Böyle bir karmaşık yapıyı tasarlamak için mühendis gözüyle bakmanız gerekir ancak sürecin sonucunda mümkün olan en yaratıcı ve en faydalı BT mimarilerinden birini tasarlamış olursunuz. Büyük bir kuruluşun iş zekası çözüm mimarisi şunları içerebilir:

- Veri kaynakları
- Veri alımı
- Büyük veri / veri hazırlama
- Veri ambarı
- İş zekası anlam modelleri
- Raporlar

:::image type="content" source="media/center-of-excellence-business-intelligence-solution-architecture/azure-business-intelligence-platform.png" alt-text="Veri kaynaklarından başlayarak veri alımı, büyük veri, depolama, veri ambarı, iş zekası anlam modeli, raporlama ve makine öğrenmesini kapsayan iş zekası platformu mimarisi diyagramını gösteren diyagram.":::

Platformun belirli talepleri karşılaması gerekir. Özellikle iş hizmetlerinin ve veri tüketicilerinin beklentilerini karşılayacak ölçeğe ve performansa sahip olmalıdır. Aynı zamanda en küçük bileşeninden itibaren güvenli olacak şekilde tasarlanmalıdır. Ayrıca zaman içinde yeni veriler ve ilgi alanları çevrimiçi ortama geçeceğinden değişikliğe uyum sağlayabilecek kadar dayanıklı olmalıdır.

## <a name="frameworks"></a>Framework’ler

Microsoft olarak en başından itibaren çerçeve geliştirmeye yatırım yaparak sistem benzeri bir yaklaşımı benimsedik. Teknik ve iş süreci çerçeveleri, tasarımın ve mantığın yeniden kullanılma imkanını artırarak tutarlı bir sonuç elde edilmesini sağlar. Bu çerçeveler ayrıca birçok farklı teknolojiden faydalanarak mimarinin esnek olmasını sağlamanın yanı sıra tekrarlanabilir süreçler sayesinde mühendislik yükünü kolaylaştırır ve azaltır.

İyi tasarlanmış çerçevelerin veri kökeni, etki analizi, iş mantığı bakımı, sınıflandırma yönetimi ve idarenin kolaylaştırılması gibi konularda daha fazla görünürlük sağladığını öğrendik. Ayrıca geliştirme süreçleri hızlanırken büyük ekiplerde işbirliği yapmak daha kolay ve verimli hale geldi.

Bu makalede çerçevelerimizden birkaçını inceleyeceğiz.

## <a name="data-models"></a>Veri modelleri

Veri modelleri, verilerin yapılandırılması ve bunlara erişim sağlanması konusunda denetim sağlar. İş hizmetleri ve veri tüketicileri açısından veri modelleri, iş zekası platformuna erişmek için kullandıkları arabirimdir.

Bir iş zekası platformu üç farklı türde model sunabilir:

- Kurumsal modeller
- İş zekası anlam modelleri
- Makine öğrenmesi (ML) modelleri

### <a name="enterprise-models"></a>Kurumsal modeller

**Kurumsal modeller**, BT mimarları tarafından tasarlanır ve sürdürülür. Bu modeller bazen boyut modelleri veya veri reyonları olarak da adlandırılır. Veriler genellikle boyut ve olgu tabloları olarak ilişkisel biçimde depolanır. Bu tablolarda birçok farklı sistemden alınarak birleştirilen temizlenmiş ve zenginleştirilmiş depolanır ve bu tablolar raporlama ve analiz için yetkili kaynak görevi görür.

Kurumsal modeller, raporlama ve iş zekası için tutarlı ve tek bir veri kaynağı sağlar. Bunlar bir kez oluşturulur ve kurumsal standart olarak paylaşılır. İdare ilkeleri, verilerin güvenliğini sağlar ve bu sayede müşteri bilgileri veya finansal bilgiler gibi hassas veri kümelerine ihtiyaca göre erişim sağlanır. Tutarlılık sağlamak ve verilerle kalitenin güvenilirlik düzeyini belirlemek için adlandırma kuralları kullanılır.

Bir bulut iş zekası platformunda kurumsal modeller [Azure Synapse'teki bir Synapse SQL havuzuna](/azure/synapse-analytics/sql-data-warehouse/sql-data-warehouse-overview-what-is#synapse-sql-pool-in-azure-synapse) dağıtılabilir. Bu durumda Synapse SQL havuzu, kuruluşun hızlı ve sağlam içgörüler için güvenebileceği tek veri sürümü haline gelir.

### <a name="bi-semantic-models"></a>İş zekası anlam modelleri

**İş zekası anlam modelleri**, kurumsal katmanlar üzerine uygulanan anlam katmanını temsil eder. Bu katmanlar iş zekası geliştiricileri ve iş kullanıcıları tarafından oluşturulur ve bakımları da yine onlar tarafından yapılır. İş zekası geliştiricileri, kurumsal modellerdeki verileri kullanan temel iş zekası anlam modellerini oluşturur. İş kullanıcıları daha küçük ölçekli ve bağımsız modeller oluşturabilir ya da temel anlam modellerini departman kaynakları veya dış kaynaklarla zenginleştirebilirler. İş zekası anlam modelleri genelde tek bir konu alanına odaklanır ve geniş ölçekte paylaşılır.

Verilerin yanı sıra kavramları, ilişkileri, kuralları ve standartları belirleyen iş zekası anlam modelleri de iş özellikleri sunar. Bu şekilde veri ilişkilerini tanımlayan ve iş kurallarını hesaplama işlemleri olarak kapsülleyen sezgisel ve kolay anlaşılır yapılar haline gelirler. Bu yapılar ayrıca ayrıntılı veri izinleri de uygulayarak doğru kişilerin doğru verilere erişmesini sağlar. Ayrıca sorgu performansını artırarak terabayt boyutundaki veriler için dahi çok hızlı yanıt veren etkileşimli analizler sunar. Kurumsal modellerde olduğu gibi, iş zekası anlam modelleri de tutarlılık sağlamak için adlandırma kurallarından faydalanır.

İş zekası geliştiricileri, iş zekası anlam modellerini bulut iş zekası platformlarında [Azure Analysis Services](/azure/analysis-services/) veya [Power BI Premium kapasitelerine](../admin/service-premium-what-is.md#dedicated-capacities) dağıtabilir. Raporlama ve analiz katmanı olarak Power BI kullanıyorsanız dağıtımı da oraya yapmanız önerilir. Bu ürünler farklı depolama modellerini destekler ve bu sayede veri modeli tablolarının verilerini önbelleğe almalarını veya sorguları doğrudan temel alınan veri kaynağına geçiren bir teknoloji olan [DirectQuery](directquery-model-guidance.md)'yi kullanmalarını mümkün kılar. DirectQuery, model tabloları büyük veri birimlerini temsil ettiğinde veya gerçek zamanlıya yakın sonuçlar sunma ihtiyacı söz konusu olduğunda ideal depolama modudur. İki depolama modu birlikte kullanılabilir: [Bileşik modeller](composite-model-guidance.md), farklı depolama alanı modlarını kullanan tabloları tek bir modelde birleştirir.

Yoğun olarak sorgulanan modeller için [Azure Load Balancer](/azure/load-balancer/load-balancer-overview), sorgu yükünü model çoğaltmaları arasında eşit bir şekilde dağıtabilir. Bu hizmet, uygulamalarınızı ölçeklendirerek yüksek oranda kullanılabilir iş zekası anlam modelleri oluşturmanızı sağlar.

### <a name="machine-learning-models"></a>Makine öğrenmesi modelleri

[**Makine öğrenmesi (ML) modelleri**](/windows/ai/windows-ml/what-is-a-machine-learning-model), veri bilimcileri tarafından oluşturulur ve bakımları da yine onlar tarafından yapılır. Bu modeller çoğunlukla veri gölündeki ham kaynaklar kullanılarak geliştirilir.

Eğitilen makine öğrenmesi modelleri, verilerinizdeki desenleri ortaya çıkarabilir. Çoğu durumda bu desenleri kullanarak verileri zenginleştirmek için kullanılabilecek tahminler elde edilebilir. Örneğin satın alma davranışı kullanılarak müşteri erimesi veya segment müşterileri tahmin edilebilir. Tahmin sonuçları kurumsal modellere eklenerek müşteri segmentine göre analiz gerçekleştirilebilir.

Bulut iş zekası platformunda [Azure Machine Learning](/azure/machine-learning/overview-what-is-azure-ml) ile makine öğrenmesi modellerini eğitebilir, dağıtabilir, otomatikleştirebilir, yönetebilir ve izleyebilirsiniz.

## <a name="data-warehouse"></a>Veri ambarı

İş zekası platformlarının merkezinde, kurumsal modellerinizi barındıran veri ambarı bulunur. Kurumsal modellere raporlama, iş zekası ve veri bilimi için tasdikli veriler sunan (kayıt sistemi ve merkez olarak) bir kaynaktır.

İş kolu (LOB) uygulamaları dahil olmak üzere çoğu iş hizmeti, yetkili ve idare edilen kurumsal bilgi kaynağı olarak veri ambarından faydalanabilir.

Microsoft olarak veri ambarımızı [Azure Data Lake Storage 2. Nesil](/azure/storage/blobs/data-lake-storage-introduction) (ADLS 2. Nesil) ve Azure Synapse Analytics üzerinde tutuyoruz.

:::image type="content" source="media/center-of-excellence-business-intelligence-solution-architecture/azure-data-warehouse.png" alt-text="Azure Synapse Analytics ile Azure Data Lake Storage 2. Nesil arasındaki bağlantıyı gösteren görüntü.":::

- **ADLS 2. Nesil**, Azure üzerinde kurumsal veri gölü oluşturmak için Azure Depolama temelinden faydalanmayı sağlar. Yüzlerce gigabit aktarım hızını sürdürürken, petabaytlarca bilginin depolanmasını da sağlayabilecek şekilde tasarlanmıştır. Ayrıca depolama alanı ve işlem maliyeti de düşüktür. Bunun yanında verilerinizi Hadoop Dağıtılmış Dosya Sistemi'nde (HDFS) olduğu gibi yönetmenizi ve aynı şekilde erişim sağlamanızı mümkün kılmak için Hadoop uyumlu erişim desteği sunar. Aslında [Azure HDInsight](/azure/hdinsight/), [Azure Databricks](/azure/azure-databricks/what-is-azure-databricks) ve Azure Synapse Analytics hizmetlerinin tamamı ADLS 2. Nesil üzerinde depolanan verilere erişebilir. Bu nedenle bir iş zekası platformunda ham kaynak verilerinin, yarı işlenmiş veya hazırlanmış verilerin ve üretime hazır verilerin depolanması için iyi bir seçenektir. Biz tüm iş verilerimizi bu platformda depoluyoruz.
- **Azure Synapse Analytics**, kurumsal veri ambarı özellikleriyle Büyük Veri analizini bir araya getiren bir analiz hizmetidir. Her ölçekte sunucusuz isteğe bağlı veya sağlanmış kaynakları kullanarak, kendi koşullarınızla verileri sorgulama özgürlüğü getirir. Azure Synapse Analytics'in bileşenlerinden biri olan ve tam kapsamlı T-SQL tabanlı analiz işlemlerini destekleyen Synapse SQL, boyut ve olgu tablolarınızı kapsayan kurumsal modellerinizi barındırmak için idealdir. Basit [Polybase T-SQL](/sql/relational-databases/polybase/polybase-guide) sorgularını kullanarak tabloları ADLS 2. Nesil'den verimli bir şekilde yükleyebilirsiniz. Ardından [MPP](/azure/synapse-analytics/sql-data-warehouse/massively-parallel-processing-mpp-architecture#synapse-sql-mpp-architecture-components)'nin gücünden faydalanarak yüksek performanslı analiz gerçekleştirebilirsiniz.

### <a name="business-rules-engine-framework"></a>İş Kuralları Altyapısı çerçevesi

Veri ambarı katmanında uygulanabilen iş mantıklarını kapsayan bir katalog oluşturmak için bir **İş Kuralları Altyapısı** (BRE) çerçevesi geliştirdik. BRE birçok farklı anlama gelebilir ancak veri ambarı bağlamında ilişkisel tablolarda hesaplanmış sütunlar oluşturma açısından yararlıdır. Bu hesaplanmış sütunlar genellikle matematiksel hesaplamalar veya koşullu deyimlerin kullanıldığı ifadeler olarak gösterilir.

Burada amaç, iş mantığını çekirdek iş zekası kodundan ayırmaktır. İş kuralları geleneksel olarak SQL saklı yordamlarına sabit olarak kodlanıyordu ve bu da genellikle iş gereksinimleri değiştiğinde yapılması gereken bakım çalışmalarının kapsamının artmasına neden oluyordu. Bir BRE içindeki iş kuralları bir kez tanımlanıp farklı veri ambarı varlıklarına uygulanarak birden çok kez kullanılabilir. Hesaplama mantığının değiştirilmesi gerekirse bu işlemin bütün saklı yordamlarda değil yalnızca tek bir noktada yapılması gerekir. Bunun bir avantajı daha vardır. BRE çerçevesi, otomatik olarak güncelleştirilen belgeler oluşturan bir dizi rapor aracılığıyla kullanıma sunulabilecek uygulanmış iş mantığı konusunda saydamlık ve görünürlük sağlar.

## <a name="data-sources"></a>Veri kaynakları

Veri ambarı, neredeyse tüm veri kaynaklarında bulunan verileri birleştirebilir. Genellikle satış, pazarlama ve finans gibi konuya özgü verilerin depolandığı ilişkisel veritabanları olan iş kolu uygulaması veri kaynaklarını temel alır. Bu veritabanları bulutta veya şirket içinde barındırılabilir. Özellikle web günlükleri veya cihazlardan gelen IoT verileri gibi diğer veri kaynakları dosya tabanlı olabilir. Veriler ayrıca Hizmet Olarak Yazılım (SaaS) satıcılarından da alınabilir.

Microsoft olarak iç sistemlerimizden bazılarını, operasyon verilerini ham dosya biçimlerini kullanarak ADLS 2. Nesil'e aktaracak şekilde tasarladık. Veri gölümüze ek olarak diğer kaynak sistemleri; ilişkisel iş kolu uygulamalarını, Excel çalışma kitaplarını, diğer dosya tabanlı kaynakları ve Ana Veri Yönetimi (MDM) ile özel veri depolarını kapsar. MDM depoları, ana verilerimizi yöneterek verilerin yetkili, standart ve doğrulanmış sürümlerine sahip olmamızı mümkün kılar.

## <a name="data-ingestion"></a>Veri alımı

Düzenli aralıklarla ve işlerin temposuna göre kaynak sistemlerde bulunan veriler alınarak veri ambarına yüklenir. Bu işlem günde bir kez veya daha sık aralıklarla gerçekleştirilebilir. Veri alımı sırasında veriler ayıklanır, dönüştürülür ve yüklenir. Bu işlem alternatif olarak ayıklama, yükleme ve dönüştürme şeklinde de gerçekleştirilebilir. Burada fark, dönüştürme işleminin gerçekleştirildiği yerdir. Dönüştürme sırasında veriler temizlenir, tümleştirilir standart ve uyumlu hale getirilir. Daha fazla bilgi için bkz. [Ayıklama, dönüştürme ve yükleme (ETL)](/azure/architecture/data-guide/relational-data/etl).

Burada nihai amaç, kurumsal modelinize doğru verileri mümkün olduğunca hızlı ve verimli bir şekilde yüklemektir.

Microsoft'ta biz [Azure Data Factory](/azure/data-factory/introduction) (ADF) kullanıyoruz. Hizmetler dış kaynak sistemlerinden veri gölümüze doğru gerçekleştirilen veri doğrulamalarını, dönüşümlerini ve toplu yükleme işlemlerini zamanlamak ve düzenlemek için kullanılıyor. Verileri paralel bir şekilde ve büyük ölçekte işlemek için özel çerçeveler tarafından yönetiliyor. Ayrıca sorun giderme ve performans izlemesine ek olarak belirli koşullar karşılandığında uyarı bildirimlerini tetiklemek için kapsamlı günlük kayıtları tutuluyor.

Bu süreçte veri bilimine özgü dönüşümler Azure bulut hizmetleri platformu için iyileştirilmiş olan Apache Spark tabanlı bir analiz platformu olan [Azure Databricks](/azure/azure-databricks/what-is-azure-databricks) tarafından gerçekleştiriliyor. Bu platform ayrıca Python not defterlerini kullanarak makine öğrenmesi modellerini oluşturuyor ve yürütüyor. Bu makine öğrenmesi modellerinden alınan puanlar, veri ambarına yüklenerek tahminler kurumsal uygulamalar ve raporlarla tümleştiriliyor. Azure Databricks, veri gölündeki dosyalara doğrudan erişim sağladığından verileri kopyalama veya alma gereksinimini ortadan kaldırıyor veya en aza indiriyor.

:::image type="content" source="media/center-of-excellence-business-intelligence-solution-architecture/azure-data-ingestion.png" alt-text="Azure Databricks ile Azure Data Lake Storage 2. Nesil üzerinden verileri alan ve veri işlem hatlarını düzenleyen Azure Data Factory hizmetini gösteren görüntü.":::

### <a name="ingestion-framework"></a>Alım çerçevesi

Yapılandırma tablolarından ve yordamlardan oluşan bir **alım çerçevesi** geliştirdik. Bu çerçeve, yüksek hızda ve en az kodla büyük miktarda veri almak için veri temelli bir yaklaşımı destekliyor. Kısaca ifade etmek gerekirse bu çerçeve, veri ambarına yüklenecek verilerin alım sürecini basitleştiriyor.

Çerçeve; kaynak türü, sunucu, veritabanı, şema ve tablo ile ilgili ayrıntılar gibi veri kaynağı ve veri hedefiyle ilgili bilgileri depolayan yapılandırma tablolarından faydalanıyor. Bu tasarım yaklaşımı sayesinde belirli ADF işlem hatları veya [SQL Server Integration Services (SSIS)](/sql/integration-services/sql-server-integration-services) paketleri geliştirmemize ihtiyaç kalmıyor. Bunun yerine yordamları istediğimiz dilde yazarak dinamik olarak oluşturulan ve çalışma zamanında yürütülen ADF işlem hatları oluşturuyoruz. Bu sayede veri alımı, kolayca çalışır duruma getirilebilen bir yapılandırma haline geliyor. Eskiden bunu yapmak için sabit kodlamalı ADF veya SSIS paketleri oluşturma amacıyla çok fazla geliştirme yapılması gerekiyordu.

Alım çerçevesi, yukarı akış kaynak şeması değişikliklerinin işlenmesi sürecini de basitleştirecek şekilde tasarlanmıştır. Şema değişiklikleri algılandığında kaynak sisteme yeni eklenen öznitelikleri almak için yapılandırma verilerini el ile veya otomatik olarak güncelleştirmek oldukça kolaydır.

### <a name="orchestration-framework"></a>Düzenleme çerçevesi

Veri işlem hatlarımızı çalışır duruma getirmek ve düzenlemek için bir **düzenleme çerçevesi** geliştirdik. Bu çerçevede, bir dizi yapılandırma tablosunu temel alan veri temelli bir tasarım kullanılıyor. Bu tablolar, işlem hattı bağımlılıklarını ve kaynak verileri hedef veri yapılarıyla eşleme şeklini ifade eden meta verileri depoluyor. Bu uyarlamalı çerçevenin geliştirilmesi için yapılan yatırım meyvelerini vermiştir ve artık her bir veri hareketini sabit kodlamaya gerek yoktur.

## <a name="data-storage"></a>Veri depolama alanı

Veri gölünde daha sonra kullanılmak üzere çok miktarda ham veri ve hazırlama veri dönüşümleri depolanabilir.

Microsoft'ta tek gerçeklik kaynağı olarak ADLS 2. Nesil hizmetini kullanıyoruz. Bu hizmet, ham verilerin yanı sıra hazırlanmış verileri ve üretime hazır verileri depoluyor. Büyük veri analizi için yüksek oranda ölçeklenebilir ve düşük maliyetli veri gölü çözümü sunuyor. Yüksek performanslı dosya sisteminin gücünü çok büyük ölçekle birleştiren, analiz iş yükleri için iyileştirilmiş olan bu sistem içgörüye ulaşma zamanını kısaltıyor.

ADLS 2. Nesil, iki sistemin de en iyi özelliklerini sunuyor. Blob depolama alanı olmasının yanı sıra ayrıntılı erişim denetimleriyle yapılandırılan yüksek performanslı bir dosya sistemi ad alanı olarak hizmet veriyor.

İyileştirilen veriler sonraki aşamada bir ilişkisel veritabanında depolanarak kurumsal modeller için güvenlik, idare ve yönetilebilirlik özelliklerine sahip yüksek performanslı ve yüksek oranda ölçeklenebilir bir veri deposu sunuyor. Konuya özgü veri reyonları Azure Synapse Analytics'te depolanarak Azure Databricks veya PolyBase T-SQL sorgularıyla yükleniyor.

## <a name="data-consumption"></a>Veri tüketimi

Raporlama katmanındaki iş hizmetleri, veri ambarından alınan kurumsal verileri kullanır. Bu hizmetler ayrıca geçici analiz veya veri bilimi görevleri için doğrudan veri gölündeki verilere erişir.

Veri gölü, kurumsal modeller ve iş zekası anlam modelleri olmak üzere tüm katmanlarda ayrıntılı izinler uygulanır. Bu izinler, veri tüketicilerinin yalnızca erişim iznine sahip oldukları verileri görebilmesini sağlar.

Microsoft olarak Power BI raporlarına ve panolarına ek olarak [Power BI sayfalandırılmış raporlarını](../paginated-reports/paginated-reports-report-builder-power-bi.md) kullanıyoruz. Özellikle finansal raporlama alanında raporlama ve geçici analiz işlemlerinin bazıları Excel'de yapılıyor.

Veri modellerimiz hakkında başvuru bilgileri sağlayan veri dizinlerini yayımlıyoruz. Bu dizinleri kullanıcılarımıza sunarak iş zekası platformumuz hakkında bilgi sahibi olmalarını sağlıyoruz. Sözlükler; varlıklar, biçimler, yapı, veri kökeni, ilişkiler ve hesaplamalar hakkında açıklamalarla model tasarımları hakkında bilgi sunuyor. Veri kaynaklarımızın kolay keşfedilebilir ve anlaşılır olmasını sağlamak için [Azure Veri Kataloğu](/azure/data-catalog/overview)'nu kullanıyoruz.

Veri tüketim desenleri genellikle role göre değişiklik gösterir:

- **Veri analistleri** doğrudan temel iş zekası anlam modellerine bağlanır. İhtiyaç duydukları tüm verileri ve mantığı içeren temel iş zekası anlam modelleri, canlı bağlantıları kullanarak Power BI raporu veya panosu oluşturabilir. Modelleri departmana özgü verilerle genişletmeleri gerektiğinde Power BI [bileşik modelleri](composite-model-guidance.md) oluştururlar. Temel iş zekası anlam modelleri, Excel’i kullanarak elektronik tablo stilinde raporlara ihtiyaç duyulduğunda temel iş zekası anlam modellerini veya departmana özgü iş zekası anlam modellerini temel alan raporları oluşturabilir.
- **İş zekası geliştiricileri** ve operasyonel rapor yazarları doğrudan kurumsal modellere bağlanır. Bu kullanıcılar, Power BI Desktop'ı kullanarak canlı bağlantı analiz raporları oluşturur. Bu kullanıcılar, T-SQL kullanarak Azure Synapse Analytics kurumsal modellerindeki verilere veya DAX ya da MDX kullanarak Power BI anlam modellerine erişmek için yerel SQL sorguları yazarak operasyonel türde iş zekası raporlarını Power BI sayfalandırılmış raporları biçiminde oluşturabilir.
- **Veri bilimcileri** doğrudan veri gölündeki verilere bağlanır. Bu kullanıcılar Azure Databricks ve Python not defterlerini kullanarak genellikle deneysel olan ve üretim ortamında kullanım için özel beceriler gerektiren makine öğrenmesi modelleri geliştirir.

:::image type="content" source="media/center-of-excellence-business-intelligence-solution-architecture/azure-data-warehouse-consumption.png" alt-text="Azure Synapse Analytics’in Power BI, Excel ve Azure Machine Learning ile kullanılmasını gösteren görüntü.":::

## <a name="next-steps"></a>Sonraki adımlar

Bu makale hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

- [Azure Synapse Analytics ile Azure'da kurumsal iş zekası](/azure/architecture/reference-architectures/data/enterprise-bi-synapse)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
- Önerileriniz mi var? [Power BI'ı geliştirmek için fikirlerinizi paylaşın](https://ideas.powerbi.com/)

### <a name="professional-services"></a>Profesyonel hizmetler

Sertifikalı Power BI iş ortakları, kuruluşunuzun COE’yi başarıyla ayarlamasına yardımcı olabilir. İş ortakları, size uygun maliyetli eğitim veya veri denetimi hizmeti sunabilir. Bir Power BI iş ortağından yardım almak için [Power BI iş ortağı portalını](https://powerbi.microsoft.com/partners/) ziyaret edin.

Deneyimli danışmanlık iş ortaklarıyla da etkileşime geçebilirsiniz. Bu iş ortakları, Power BI’ı [incelemenize](https://appsource.microsoft.com/marketplace/consulting-services?product=power-bi&serviceType=assessment&country=ALL&region=ALL), [değerlendirmenize](https://appsource.microsoft.com/marketplace/consulting-services?product=power-bi&serviceType=proof-of-concept&country=ALL&region=ALL) veya [uygulamanıza](https://appsource.microsoft.com/marketplace/consulting-services?product=power-bi&serviceType=implementation&country=ALL&region=ALL&page=1) yardımcı olabilir.
