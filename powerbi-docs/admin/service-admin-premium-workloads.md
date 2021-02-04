---
title: Power BI Premium’da iş yüklerini yapılandırma
description: Power BI Premium kapasitesinde iş yüklerini yapılandırmayı öğrenin.
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-premium
ms.topic: how-to
ms.date: 11/11/2020
LocalizationGroup: Premium
ms.openlocfilehash: 62579a12588449e0119b96fb3a7c7da2ef7858e5
ms.sourcegitcommit: c33e53e1fab1f29872297524a7b4f5af6c806798
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/04/2021
ms.locfileid: "99532924"
---
# <a name="configure-workloads-in-a-premium-capacity"></a>Premium kapasitedeki iş yüklerini yapılandırma

Bu makalede, Power BI Premium kapasiteleri için iş yüklerini etkinleştirme ve yapılandırma açıklanmaktadır. Varsayılan olarak, kapasiteler yalnızca çalışan Power BI sorgularıyla ilişkili iş yüklerini destekler. **[AI (Bilişsel Hizmetler)](../transform-model/dataflows/dataflows-machine-learning-integration.md)** , **[Veri akışları](../transform-model/dataflows/dataflows-introduction-self-service.md)** ve **[Sayfalandırılmış raporlar](../paginated-reports/paginated-reports-save-to-power-bi-service.md)** için de ek iş yüklerini etkinleştirebilir ve yapılandırabilirsiniz.

> [!NOTE]
> Yakın zamanda Power BI Premium, şu anda önizleme aşamasında olan **Premium 2. Nesil** adlı yeni bir Premium sürümünü kullanıma sundu. Premium 2. Nesil, Premium kapasitelerinin yönetimini basitleştirecek ve yönetim yükünü azaltacak. Daha fazla bilgi için bkz. [Power BI Premium 2. Nesil (önizleme)](service-premium-what-is.md#power-bi-premium-generation-2-preview).
>
>Power BI Embedded Gen2 geliştirmelerini gözden geçirmek için [Power BI Embedded 2. nesil](../developer/embedded/power-bi-embedded-generation-2.md)bölümüne bakın.

## <a name="default-memory-settings"></a>Varsayılan bellek ayarları

Sorgu iş yükleri, Premium kapasite SKU’nuza göre belirlenen kaynaklar için iyileştirilmiştir ve bunlarla sınırlıdır. Premium kapasiteler ayrıca kapasitenizin kaynaklarını kullanabilen ek iş yüklerini de destekler. Bu iş yükleri için varsayılan bellek değerleri, SKU’nuz için kullanılabilir kapasite düğümlerini temel alır. En yüksek bellek ayarları kümülatif değildir. 


|                       | EM1 / A1                  | EM2 / A2                  | EM3 / A3                  | P1 / A4                  | P2 / A5                  | P3 / A6                   |
|-----------------------|---------------------------|---------------------------|---------------------------|--------------------------|--------------------------|---------------------------|
| **AI**                | Desteklenmeyen               | %40 varsayılan; %40 en küçük  | %20 varsayılan; %20 en küçük  | %20 varsayılan; %8 en küçük  | %20 varsayılan; %4 en küçük  | %20 varsayılan; %2 en küçük   |
| **Veri kümeleri**          | %100 varsayılan; %67 en küçük | %100 varsayılan; %40 en küçük | %100 varsayılan; %20 en küçük | %100 varsayılan; %8 en küçük | %100 varsayılan; %4 en küçük | %100 varsayılan; %2 en küçük  |
| **Veri akışları**         | %40 varsayılan; %40 en küçük  | %24 varsayılan; %24 en küçük  | %20 varsayılan; %12 en küçük  | %20 varsayılan; %5 en küçük  | %20 varsayılan; %3 en küçük  | %20 varsayılan; %2 en küçük   |
| **Sayfalandırılmış raporlar** | Desteklenmeyen               | Desteklenmeyen               | Desteklenmeyen               | %20 varsayılan; %10 en küçük | %20 varsayılan; %5 en küçük  | %20 varsayılan; %2,5 en küçük |

> [!NOTE]
> Şu anda önizleme aşamasında olan **Premium 2. Nesil**, bellek ayarlarının değiştirilmesini gerektirmez. Premium 2. Nesil’deki bellek, temeldeki sistem tarafından otomatik olarak yönetilir. 


## <a name="workload-settings"></a>İş yükü ayarları

Aşağıdaki bölümlerde, önceki tabloda açıklanan iş yükü ayarları hakkında daha fazla ayrıntı sağlanmaktadır. 

### <a name="ai-preview"></a>AI (Önizleme)

AI iş yükü Power BI'da bilişsel hizmetleri ve Otomatik Makine Öğrenmesi'ni kullanabilmenizi sağlar. İş yükü davranışını denetlemek için aşağıdaki ayarları kullanın.

| Ayar Adı | Açıklama |
|---------------------------------|----------------------------------------|
| **En Yüksek Bellek (%)** | Kapasitede AI işlemlerinin kullanabileceği en yüksek kullanılabilir bellek yüzdesi. |
| **Power BI Desktop’tan kullanıma izin ver** | Bu ayar gelecekte kullanım için ayrılmıştır ve tüm kiracılarda görüntülenmez. |
| **Makine öğrenmesi modelleri oluşturmaya izin ver** | İş analistlerinin doğrudan Power BI'da makine öğrenmesi modellerini eğitmesine, doğrulamasına ve çağırmasına izin verilip verilmeyeceğini belirtir. Daha fazla bilgi için bkz. [Power BI’da Otomatik Makine Öğrenmesi (Önizleme)](../transform-model/dataflows/dataflows-machine-learning-integration.md). |
| **AI istekleri için paralelliği etkinleştir** | AI isteklerinin paralel çalıştırılıp çalıştırılamayacağını belirtir. |
|  |  |

### <a name="datasets"></a>Veri kümeleri

Veri kümeleri iş yükü varsayılan olarak etkindir ve devre dışı bırakılamaz. İş yükü davranışını denetlemek için aşağıdaki ayarları kullanın. Ayarlardan bazıları için tablonun altında ek kullanım bilgileri verilir.

| Ayar Adı | Açıklama |
|---------------------------------|----------------------------------------|
| **En Yüksek Bellek (%)** | Kapasitede veri kümelerinin kullanabileceği en yüksek kullanılabilir bellek yüzdesi. |
| **XMLA Uç Noktası** | İstemci uygulamalarından gelen bağlantıların çalışma alanı ve uygulama düzeylerinde ayarlanan güvenlik grubu üyeliğini kabul edeceğini belirtir. Daha fazla bilgi için bkz. [İstemci uygulaması ve araçlarıyla veri kümelerine bağlanma](service-premium-connect-tools.md). |
| **En Fazla Ara Satır Sayısı** | DirectQuery tarafından döndürülen ara satır sayısı üst sınırı. Varsayılan değer 1000000'dur ve izin verilen değerler 100000 ile 2147483647 arasındadır. |
| **En Büyük Çevrimdışı Veri Kümesi Boyutu (GB)** | Bellekteki çevrimdışı veri kümesinin boyut üst sınırı. Bu, diskteki sıkıştırılmış boyuttur. SKU tarafından tanımlanan en yüksek sınır olan varsayılan değer 0’dır. İzin verilen aralık 0 ila kapasite boyutu sınırı arasındadır. |
| **En Büyük Sonuç Satır Kümesi Sayısı** | DAX sorgusunda döndürülen satır sayısı üst sınırı. Varsayılan değer -1'dir (sınır yok) ve izin verilen değerler 100000 ile 2147483647 arasındadır. |
| **Sorgu Belleği Sınırı (%)** | Çalışma yükünde MDX veya DAX sorgusu yürütmek için kullanılabilen belleğin en büyük yüzdesi. Varsayılan değer 0’dır ve bu, SKU’ya özgü otomatik sorgu belleği sınırının uygulanmasına neden olur. |
| **Sorgu Zaman Aşımı (saniye)** | Sorgu zaman aşımına uğramadan önce geçebilecek en uzun süre. Varsayılan değer 3600 saniyedir (1 saat). 0 değeri sorguların zaman aşımına uğramayacağını belirtir. |
| **Otomatik sayfa yenileme** | Premium çalışma alanlarının sabit aralıkları temel alarak otomatik sayfa yenileme özellikli raporları olmasına izin vermek için açma/kapatma düğmesi. |
| **Minimum yenileme aralığı** | Otomatik sayfa yenileme açıksa, sayfa yenileme aralığı için izin verilen minimum aralık. Varsayılan değer beş dakika ve izin verilen minimum değer de bir saniyedir. |
| **Değişiklik algılama ölçüsü** | Premium çalışma alanlarının değişiklik algılamasını temel alarak otomatik sayfa yenileme özellikli raporları olmasına izin vermek için açma/kapatma düğmesi. |
| **Minimum yürütme aralığı** | Değişiklik algılama ölçüsü açıksa en düşük yürütme aralığının veri değişikliklerini yoklamasına izin verilir. Varsayılan değer beş saniye, izin verilen minimum değer de bir saniyedir. |
|  |  |  |

#### <a name="max-intermediate-row-set-count"></a>En Büyük Ara Satır Kümesi Sayısı

Yoğun kaynak kullanılan veya kötü tasarlanmış raporların etkisini denetim altına almak için bu ayarı kullanın. DirectQuery veri kümesindeki bir sorgu kaynak veritabanından çok büyük bir sonuç getirirse, bellek kullanımında ve işlem yükünde ani bir artışa neden olabilir. Bu durum diğer kullanıcıların ve raporların yetersiz kaynak durumuyla karşılaşmasına yol açabilir. Bu ayarla kapasite yöneticisi tek bir sorgunun veri kaynağından kaç satır getirebileceğini belirleyebilir.

Alternatif olarak, kapasite varsayılan bir milyon satırdan daha fazlasını destekleyebiliyorsa daha fazla satır getirmek için bu ayarı artırın.

Bu ayarın yalnızca DirectQuery sorgularını etkilediğine, [En Büyük Sonuç Satır Kümesi Sayısı](#max-result-row-set-count)'nın ise DAX sorgularını etkilediğine dikkat edin.

#### <a name="max-offline-dataset-size"></a>En Büyük Çevrimdışı Veri Kümesi Boyutu

Rapor oluşturucularının kapasiteyi olumsuz etkileyebilecek büyük veri kümeleri yayımlamasını önlemek için bu ayarı kullanın. Veri kümesi belleğe yüklenene kadar Power BI'ın gerçek bellek içi boyutu belirleyemeyeceğini unutmayın. Çevrimdışı boyutu daha küçük olan bir veri kümesinin bellekte çevrimdışı boyutu daha büyük olandan daha fazla yer kaplaması mümkündür.

Bu ayarda belirttiğiniz boyuttan daha büyük bir veri kümeniz varsa, kullanıcı erişmeye çalıştığında veri kümesi yüklenemeyecektir. Ayrıca veri kümeleri iş yükü için yapılandırılmış En Fazla Bellek’ten büyük olan veri kümeleri de yüklenemeyebilir.

Sistemin performansını korumak için, yapılandırılan değerden bağımsız olarak en büyük çevrimdışı veri kümesi boyutuna ek SKU’ya özgü bir sabit tavan uygulanır. Bu sabit tavan, büyük veri boyutları için iyileştirilmiş Power BI veri kümelerine uygulanmaz. Daha fazla bilgi için bkz. [Power BI Premium'da büyük modeller](service-premium-large-models.md).

|                                               | EM1 / A1 | EM2 / A2 | EM3 / A3 | P1 / A4 | P2 / A5 | P3 / A6 |
|-----------------------------------------------|----------|----------|----------|---------|---------|---------|
| **En Yüksek Çevrimdışı Veri Kümesi Boyutu için sabit tavan** | 3 GB     | 5 GB     | 6 GB     | 10 GB   | 10 GB   | 10 GB   |

#### <a name="max-result-row-set-count"></a>En Büyük Sonuç Satır Kümesi Sayısı

Yoğun kaynak kullanılan veya kötü tasarlanmış raporların etkisini denetim altına almak için bu ayarı kullanın. DAX sorgusunda bu sınıra ulaşılırsa rapor kullanıcısı aşağıdaki hatayı görür. Hata ayrıntılarını kopyalayıp yöneticiye başvurması gerekir.

![Bu görsel için veri yüklenemedi](media/service-admin-premium-workloads/could-not-load-data.png)

Bu ayarın yalnızca DAX sorgularını etkilediğine, [En Büyük Ara Satır Kümesi Sayısı](#max-intermediate-row-set-count)'nın ise DirectQuery sorgularını etkilediğine dikkat edin.

#### <a name="query-memory-limit"></a>Sorgu Belleği Sınırı

Yoğun kaynak kullanılan veya kötü tasarlanmış raporların etkisini denetim altına almak için bu ayarı kullanın. Bazı sorgular ve hesaplamalar kapasitede çok fazla bellek kullanan ara sonuçlar verebilir. Bu durum diğer sorguların çok yavaş yürütülmesine, diğer veri kümelerinin kapasiteden çıkarılmasına ve kapasitenin diğer kullanıcılarının yetersiz bellek hataları almasına yol açabilir.

Bu ayar Power BI raporları, Excel’de Çözümle raporları ve ayrıca XMLA uç noktası üzerinden bağlanabilen diğer araçlar tarafından yürütülen tüm DAX ve MDX sorgularında geçerlidir.

Veri yenileme işlemlerinin de, veri kümesindeki veriler yenilendikten sonra pano kutucuklarını ve görsel önbelleklerini yenileme işlemi kapsamında DAX sorguları yürütebileceğini unutmayın. Bu tür sorgular da bu ayardan dolayı başarısız olabilir ve veri kümesindeki veriler başarıyla güncelleştirilmiş olsa bile veri yenileme işleminin başarısız durumda görünmesine yol açabilir.

Varsayılan ayar 0’dır ve bu, aşağıdaki SKU’ya özgü otomatik sorgu belleği sınırının uygulanmasına neden olur.

|                                  | EM1 / A1 | EM2 / A2 | EM3 / A3 | P1 / A4 | P2 / A5 | P3 / A6 |
|----------------------------------|----------|----------|----------|---------|---------|---------|
| **Otomatik Sorgu Belleği Sınırı** | 1 GB     | 2 GB     | 2 GB     | 6 GB    | 6 GB    | 10 GB   |

Sistemin performansını korumak için, kullanıcı tarafından yapılandırılan sorgu belleği sınırından bağımsız olarak, Power BI raporları tarafından yürütülen tüm sorgularda 10 GB’lık bir sabit tavan zorunlu tutulur. Bu sabit tavan Analysis Services protokolünü (XMLA olarak da bilinir) kullanan araçların gönderdiği sorgulara uygulanmaz. Bellek çok fazla bellek kullanıyorsa kullanıcıların sorguyu ve hesaplamalarını basitleştirmeyi göz önünde bulundurması gerekir.

#### <a name="query-timeout"></a>Sorgu Zaman Aşımı

Uzun süre çalışan ve kullanıcılar için raporların yavaş yüklenmesine neden olabilen sorguları daha iyi denetim altına almak için bu ayarı kullanın.

Bu ayar Power BI raporları, Excel’de Çözümle raporları ve ayrıca XMLA uç noktası üzerinden bağlanabilen diğer araçlar tarafından yürütülen tüm DAX ve MDX sorgularında geçerlidir.

Veri yenileme işlemlerinin de, veri kümesindeki veriler yenilendikten sonra pano kutucuklarını ve görsel önbelleklerini yenileme işlemi kapsamında DAX sorguları yürütebileceğini unutmayın. Bu tür sorgular da bu ayardan dolayı başarısız olabilir ve veri kümesindeki veriler başarıyla güncelleştirilmiş olsa bile veri yenileme işleminin başarısız durumda görünmesine yol açabilir.

Bu ayar tek bir sorgu için geçerlidir; veri kümesinin veya raporun güncelleştirilmesiyle ilişkili tüm sorguları çalıştırmak için gereken süreye uygulanmaz. Aşağıdaki örneği inceleyin:

- **Sorgu Zaman Aşımı** ayarı 1200 (20 dakika).
- Yürütülecek beş sorgu var ve her biri 15 dakika çalışıyor.

Tüm sorguların birleşik süresi 75 dakika ama bu ayar sınırına ulaşılmadı çünkü tek tek sorguların her birinin çalışması 20 dakikadan kısa sürdü.

Power BI raporlarının, kapasitede her sorgu için daha küçük bir zaman aşımı süresiyle bu varsayılan süreyi geçersiz kıldığına dikkat edin. Her sorgu için zaman aşımı normalde yaklaşık üç dakikadır.

#### <a name="automatic-page-refresh-preview"></a>Otomatik sayfa yenileme (önizleme)

Etkinleştirildiğinde otomatik sayfa yenileme, Premium kapasitenizdeki kullanıcıların, DirectQuery kaynakları için tanımlı bir aralıkta raporlarındaki sayfaları yenilemesine olanak sağlar. Kapasite yöneticisi olarak şunları yapabilirsiniz:

- Otomatik sayfa yenilemeyi açma ve kapatma
- Minimum yenileme aralığı tanımlama

Aşağıdaki görüntüde, otomatik yenileme aralığı ayarının konumu gösterilmektedir:

![otomatik yenileme aralığı için yönetici ayarı](media/service-admin-premium-workloads/automatic-refresh-interval.png)

Otomatik sayfa yenileme tarafından oluşturulan sorgular doğrudan veri kaynağına gider, bu nedenle kuruluşunuzda otomatik sayfa yenilemeye izin verirken bu kaynaklarda güvenilirliği ve yükü göz önünde bulundurmanız önemlidir. 

### <a name="dataflows"></a>Veri akışları

Veri akışları iş yükü verileri almak, dönüştürmek, tümleştirmek ve zenginleştirmek için veri akışları self servis veri hazırlığını kullanmanıza olanak tanır. İş yükü davranışını denetlemek için aşağıdaki ayarları kullanın.

| Ayar Adı | Açıklama |
|---------------------------------|----------------------------------------|
| **En Yüksek Bellek (%)** | Kapasitede veri akışlarının kullanabileceği en yüksek kullanılabilir bellek yüzdesi. |
| **Gelişmiş Veri Akışları Bilgi İşlem Altyapısı (Önizleme)** | Büyük ölçekli veri hacimleriyle çalışırken hesaplanan varlıkların 20 kata kadar daha hızlı hesaplanması için bu seçeneği etkinleştirin. **Yeni altyapıyı etkinleştirmek için kapasiteyi yeniden başlatmanız gerekir.** Daha fazla bilgi için bkz. [Gelişmiş veri akışları işlem altyapısı](#enhanced-dataflows-compute-engine). |
| **Kapsayıcı Boyutu** | Veri akışlarının, veri akışındaki her varlık için kullanabileceği kapsayıcı boyutu üst sınırı. Varsayılan değer 700 MB'tır. Daha fazla bilgi için bkz. [Kapsayıcı boyutu](#container-size). |
|  |  |

#### <a name="enhanced-dataflows-compute-engine"></a>Gelişmiş veri akışları işlem altyapısı

Yeni işlem altyapısından yararlanmak için veri alımını ayrı veri akışlarını bölün ve farklı veri akışlarındaki hesaplanan varlıklara dönüştürme mantığı ekleyin. Bu yaklaşımın önerilmesinin nedeni işlem altyapısının mevcut veri akışına başvuran veri akışları üzerinde çalışmasıdır. Veri alımı iş akışları üzerinde çalışmaz. Bu yönergenin izlenmesi en iyi performans için yeni işlem altyapısının birleştirmeler gibi dönüştürme adımlarını işlemesini güvence altına alır.

#### <a name="container-size"></a>Kapsayıcı boyutu

Veri akışı yenilenirken, veri akışı iş yükü veri akışındaki her varlık için bir kapsayıcı üretir. Her kapsayıcı, Kapsayıcı Boyutu ayarında belirtilen miktara kadar bellek alabilir. Tüm SKU'larda varsayılan değer 700 MB'tır. Aşağıdaki durumlarda bu ayarı değiştirmek isteyebilirsiniz:

- Veri akışlarının yenilenmesi fazla uzun sürüyor veya veri akışı yenilemesi zaman aşımından dolayı başarısız oluyor.
- Veri akışı varlıkları hesaplama adımları, örneğin birleştirme içeriyor.  

Veri akışı iş yükü performansını analiz etmek için [Power BI Premium Kapasite Ölçümleri](service-admin-premium-monitor-capacity.md) uygulamasını kullanmanız önerilir.

Bazı durumlarda kapsayıcı boyutunu artırmak performansı geliştirmeyebilir. Örneğin, veri akışı önemli hesaplamalar yapmadan verileri yalnızca kaynaktan alıyorsa, kapsayıcı boyutu değiştirmek büyük olasılıkla işe yaramayacaktır. Kapsayıcı boyutunun artırılması, Veri Akışı iş yükünün varlık yenileme işlemlerine daha fazla bellek ayırmasına olanak tanıyorsa yararlı olur. Daha fazla bellek ayrılması, yoğun işlem içeren varlıkların yenilenmesi için gereken süreyi kısaltabilir.

Kapsayıcı Boyutu değeri, Veri Akışları iş yükü için en yüksek bellek miktarını aşamaz. Örneğin P1 kapasitenin 25 GB belleği vardır. Veri Akışı iş yükünün En Yüksek Bellek (%) değeri %20 olarak ayarlandıysa Kapsayıcı Boyutu (MB) 5000'i aşamaz. Her durumda, daha yüksek bir değer ayarlamış olsanız bile Kapsayıcı Boyutu En Yüksek Bellek miktarını aşamaz.

### <a name="paginated-reports"></a>Sayfalandırılmış raporlar

Sayfalandırılmış raporlar iş yükü Power BI hizmetinde standart SQL Server Reporting Services biçimi temelinde sayfalandırılmış raporları çalıştırmanıza olanak tanır. İş yükü davranışını denetlemek için aşağıdaki ayarı kullanın.

| Ayar Adı | Açıklama |
|---------------------------------|----------------------------------------|
| **En Yüksek Bellek (%)** | Kapasitede sayfalandırılmış raporların kullanabileceği en yüksek kullanılabilir bellek yüzdesi. |
|  |  |

Sayfalandırılmış raporlar, rapor yazarları için özel kod ekleme özelliği de dahil olmak üzere SQL Server Reporting Services (SSRS) raporlarının günümüzde kullandığı özellikleri sunar.  Yazarlar bu sayede raporları dinamik olarak değiştirebilir, kod ifadelerine göre metin renklerini değiştirme gibi eylemler gerçekleştirebilir.  Uygun yalıtımı sağlamak için sayfalandırılmış raporlar kapasiteye özgü korumalı alan içinde çalıştırılır. Aynı kapasiteyle çalıştıran raporların arasında istenmeyen etkileşimler yaşanabilir. SSRS örneğine içerik yayımlayabilecek yazarları kısıtladığınız gibi sayfalandırılmış raporlarda da benzer bir uygulama gerçekleştirmeniz önerilir. Kapasiteye içerik yayımlayan yazarların kuruluş açısından güvenilir olduğundan emin olun. Birden fazla kapasite sağlayıp her birine farklı yazarlar atayarak ortamınızın güvenlik düzeyini artırabilirsiniz. 

Bazı durumlarda sayfalandırılmış raporlar iş yükü kullanılamaz hale gelebilir. Böyle bir durumda iş yükü Yönetici portalında bir hata durumu gösterir ve kullanıcılar rapor işleme için zaman aşımı değerlerini görürler. Bu sorunu gidermek için iş yükünü devre dışı bırakın ve sonra yeniden etkinleştirin.

## <a name="configure-workloads"></a>İş yüklerini yapılandırma

İş yüklerini yalnızca kullanılacakları zaman etkinleştirerek kapasitenizin kullanılabilir kaynaklarını en üst düzeye çıkarın. Bellek ayarını ve diğer ayarları, ancak belirlenmiş varsayılan ayarlarınızın kapasite kaynak gereksinimlerinizi karşılamadığı durumlarda değiştirin.

### <a name="to-configure-workloads-in-the-power-bi-admin-portal"></a>Power BI yönetici portalında iş yüklerini yapılandırmak için

1. **Kapasite ayarları** > **PREMIUM KAPASİTELER** içinde, bir kapasite seçin.

1. **DİĞER SEÇENEKLER** altında **İş Yükleri**’ni genişletin.

1. Bir veya daha fazla iş yükünü etkinleştirin ve **En Büyük Bellek** için ve diğer ayarlar için değer belirleyin.

1. **Apply** (Uygula) seçeneğini belirleyin.

### <a name="rest-api"></a>REST API

İş yükleri, [Kapasiteler](/rest/api/power-bi/capacities) REST API’leri kullanılarak etkinleştirilebilir ve bir iş yüküne atanabilir.

## <a name="monitoring-workloads"></a>İş yüklerini izleme

[Power BI Premium Kapasite Ölçümleri uygulaması](service-admin-premium-monitor-capacity.md), kapasitelerinizde etkinleştirilmiş iş yüklerini izlemek için veri kümesi, veri akışları ve sayfalandırılmış rapor ölçümleri sağlar. 


> [!IMPORTANT]
> Power BI Premium kapasitenizde performans ve güvenilirlik sorunlarına neden olan yüksek kaynak kullanımı sorunu yaşanıyorsa sorunu tanımlayıp çözmek için bildirim e-postaları alabilirsiniz. Bu, aşırı yüklenmiş kapasitelerde sorun gidermeye yönelik basitleştirilmiş bir yöntemdir. Daha fazla bilgi için bkz. [Kapasite ve güvenilirlik bildirimleri](service-interruption-notifications.md#capacity-and-reliability-notifications).


## <a name="next-steps"></a>Sonraki adımlar

[Power BI Premium kapasitelerini en iyi duruma getirme](service-premium-capacity-optimize.md)
[Veri akışlarıyla Power BI'da self servis veri hazırlığı](../transform-model/dataflows/dataflows-introduction-self-service.md)
[Power BI Premium'da sayfalandırılmış raporlar nedir?](../paginated-reports/paginated-reports-report-builder-power-bi.md)
[Power BI Desktop'ta otomatik sayfa yenileme (önizleme)](../create-reports/desktop-automatic-page-refresh.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)

Power BI, aşağıdaki iyileştirmelerle Power BI Premium deneyimini geliştiren bir önizleme teklifi olarak Power BI Premium 2. Nesil’i kullanıma sundu:
* Performans
* Kullanıcı başına lisanslama
* Daha yüksek ölçek
* İyileştirilmiş ölçümler
* Otomatik ölçeklendirme
* Azaltılmış yönetim yükü

Power BI Premium 2. Nesil hakkında daha fazla bilgi için bkz. [Power BI Premium 2. Nesil (önizleme)](service-premium-what-is.md#power-bi-premium-generation-2-preview).