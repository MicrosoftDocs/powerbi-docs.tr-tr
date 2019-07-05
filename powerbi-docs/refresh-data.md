---
title: Power BI'da veri yenileme
description: Bu makalede, Power BI’ın veri yenileme özellikleri ve bu özelliklerin bağımlılıkları kavramsal düzeyde açıklanmaktadır.
author: mgblythe
manager: kfile
ms.reviewer: kayu
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 06/12/2019
ms.author: mblythe
LocalizationGroup: Data refresh
ms.openlocfilehash: 2760731e7be1216c4ec8755884467eca9d7eb4c4
ms.sourcegitcommit: 8dee40f07d284ec84a8afa0100359f146e1dd88b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2019
ms.locfileid: "67418791"
---
# <a name="data-refresh-in-power-bi"></a>Power BI'da veri yenileme

Power BI, veriden içgörüye ve içgörüden eyleme hızla geçmenize olanak tanır. Ancak, Power BI rapor ve panolarınızdaki verilerin güncel olduğundan emin olmanız gerekir. Verileri yenilemeyi bilmek, doğru sonuçların sunulması için genellikle kritik öneme sahiptir.

Bu makalede, Power BI’ın veri yenileme özellikleri ve bu özelliklerin bağımlılıkları kavramsal düzeyde açıklanmaktadır. Sık karşılaşılan yenileme sorunlarını önlemeye yönelik en iyi yöntemler ve ipuçları da sunulmaktadır. İçerik, veri yenilemenin nasıl çalıştığını anlamanıza yardımcı olacak bir temel oluşturur. Veri yenilemeyi yapılandırmaya yönelik hedefli, adım adım yönergeler için bu makalenin sonunda bulunan Sonraki adımlar kısmında listelenen öğreticilere ve nasıl yapılır kılavuzlarına başvurun.

## <a name="understanding-data-refresh"></a>Veri yenilemeyi anlama

Her veri yenilediğinizde Power BI’ın temel alınan veri kaynaklarını sorgulaması, muhtemelen kaynak verileri bir veri kümesine yüklemesi, rapor ve panolarınızdaki tüm görselleştirmeleri güncelleştirmesi gerekir. Bu görselleştirmeler güncelleştirilmiş veri kümesini kullanır. Tüm süreç, aşağıdaki kısımlarda açıklandığı gibi veri kümelerinizin depolama modlarına bağlı olarak birden çok aşamadan oluşur.

Power BI’ın veri kümelerinizi, raporlarınızı ve panolarınızı nasıl yenilediğini anlamak için aşağıdaki kavramları bilmeniz gerekir:

- **Depolama modları ve veri kümesi türleri**: Power BI’ın desteklediği depolama modları ve veri kümesi türlerinin farklı yenileme gereksinimleri bulunur. Oluşan tüm değişiklikleri görmek için verileri Power BI’a yeniden aktarmayı veya verileri doğrudan kaynağında sorgulamayı seçebilirsiniz.
- **Power BI yenileme türleri**: Veri kümesi özelliklerinden bağımsız olarak çeşitli yenileme türlerini bilmeniz, bir yenileme işlemi esnasında Power BI’ın zamanını hangi işlemlerde geçireceğini anlamanıza yardımcı olabilir. Bu ayrıntıları depolama modu özellikleri ile birleştirerek, bir veri kümesi için **Şimdi Yenile** seçeneğini belirlediğinizde Power BI’ın tam olarak ne yapacağını daha iyi anlayabilirsiniz.

### <a name="storage-modes-and-dataset-types"></a>Depolama modları ve veri kümesi türleri

Bir Power BI veri kümesi, çeşitli veri kaynaklarında bulunan verilere erişmek için aşağıdaki modlardan birinde çalışabilir. Daha fazla bilgi için bkz. [Power BI Desktop’ta depolama modu](desktop-storage-mode.md).

- İçeri aktarma modu
- DirectQuery modu
- LiveConnect modu
- Gönderim modu

Aşağıdaki diyagram, depolama modunu temel alarak farklı veri akışlarını gösterir. En önemli nokta, sadece İçeri aktarma modundaki veri kümelerinin bir veri kaynağı yenileme işlemini gerektirmesidir. Yalnızca bu tür veri kümeleri verileri veri kaynaklarından içeri aktardığından ve içeri aktarılan veriler düzenli veya geçici olarak güncelleştirilebileceğinden, bu tür veri kümeleri yenileme gerektirir. DirectQuery veri kümeleri ve Analysis Services’a yönelik LiveConnect modundaki veri kümeleri, verileri içeri aktarmaz. Bunlar, her kullanıcı etkileşiminde, temel alınan veri kaynağını sorgular. Gönderim modundaki veri kümeleri, veri kaynaklarına doğrudan erişmez, verileri Power BI’a sizin göndermenizi bekler. Veri kümesi yenileme gereksinimleri, depolama moduna/veri kümesi türüne göre farklılık gösterir.

![Depolama modları ve veri kümesi türleri](media/refresh-data/storage-modes-dataset-types-diagram.png)

#### <a name="datasets-in-import-mode"></a>İçeri aktarma modundaki veri kümeleri

Power BI, verileri özgün veri kaynaklarından veri kümesine aktarır. Veri kümesine gönderilen Power BI rapor ve pano sorguları, içeri aktarılan tablo ve sütunlardaki sonuçları döndürür. Bu tür veri kümelerini belirli bir nokta kopyası olarak düşünebilirsiniz. Power BI verileri kopyaladığından, temel alınan veri kaynaklarından değişiklikleri getirmek amacıyla veri kümesini yenilemeniz gerekir.

Power BI verileri önbelleğe aldığından, İçeri aktarma modu veri kümesi boyutları çok büyük olabilir. Kapasite başına en yüksek veri kümesi boyutları için aşağıdaki tabloya bakın. Veri kümeleriniz bir yenileme işlemi esnasında kullanılabilir olan en yüksek kaynak miktarından daha fazlasını gerektirirse yenileme sorunları oluşabilir. Bu sorunları önlemek için en yüksek veri kümesi boyutlarının oldukça altında kalın.

| Kapasite türü | Veri kümesi boyutu üst sınırı |
| --- | --- |
| Paylaşılan, A1, A2 veya A3 | 1 GB |
| A4 veya P1 | 3 GB |
| A4 veya P2 | 6 GB |
| A6 veya P3 | 10 GB |
| | |

#### <a name="datasets-in-directqueryliveconnect-mode"></a>DirectQuery/LiveConnect modundaki veri kümeleri

Power BI, verileri DirectQuery/LiveConnect modunda çalışan bağlantılar üzerinden içeri aktarmaz. Bunun yerine veri kümesi, bir rapor veya pano tarafından sorgulandığında, temel alınan veri kaynağındaki sonuçları döndürür. Power BI sorguları dönüştürüp veri kaynağına iletir.

DirectQuery modu ve LiveConnect modu, sorguların kaynağa Power BI tarafından iletilmesi yönünden benzer olsa da, Power BI’ın LiveConnect modunda sorguları dönüştürmesinin gerekmediğine dikkat edilmelidir. Sorgular doğrudan, paylaşılan kapasitedeki veya Premium kapasitedeki kaynakları tüketmeden veritabanını barındıran Analysis Services örneğine gider.

Power BI verileri içeri aktarmadığından veri yenileme işlemi çalıştırmanız gerekmez. Ancak, bir sonraki yenileme türleri kısmında açıklandığı gibi, Power BI kutucuk yenilemelerini ve olası rapor yenilemelerini yine de gerçekleştirir. Kutucuk, panoya sabitlenen bir rapor görselidir ve kutucukların güncel sonuçları göstermesi için pano kutucuğu yenilemeleri yaklaşık her saatte bir gerçekleştirilir. Aşağıdaki ekran görüntüsünde olduğu gibi zamanlamayı veri kümesi ayarlarından değiştirebilir veya **Şimdi Yenile** seçeneğini kullanarak kendiniz bir pano güncelleştirmesini zorlayabilirsiniz.

![Yenileme zamanlaması](media/refresh-data/refresh-schedule.png)

> [!NOTE]
> **Veri kümeleri** sekmesinin **Zamanlanmış önbellek yenilemesi** bölümü, içeri aktarma modundaki veri kümeleri için kullanılamaz. Power BI, her zamanlanmış veya isteğe bağlı veri yenilemesinde kutucukları otomatik olarak yenilediğinden, bu veri kümeleri için ayrı bir kutucuk yenilemesi gerekmez.

#### <a name="push-datasets"></a>Gönderme veri kümeleri

Gönderme veri kümeleri, veri kaynağının resmi tanımını içermedikleri için Power BI’da bir veri yenilemesi yapmanızı gerektirmez. Verilerinizi, Azure Stream Analytics gibi harici bir hizmet veya işlem aracılığıyla veri kümesine göndererek bu veri kümelerini yenilersiniz. Bu, Power BI ile gerçek zamanlı analiz için sık kullanılan bir yaklaşımdır. Power BI, gönderme veri kümesinde kullanılan tüm kutucuklar için önbellek yenilemelerini yine de gerçekleştirir. Ayrıntılı bilgi için bkz. [Öğretici: Stream Analytics ve Power BI: Akış verilerine yönelik gerçek zamanlı bir analiz panosu](/azure/stream-analytics/stream-analytics-power-bi-dashboard).

> [!NOTE]
> Gönderme Modunun, [Power BI REST API’si sınırlamaları](developer/api-rest-api-limitations.md) bölümünde belgelendiği gibi bazı sınırlamaları bulunur.

### <a name="power-bi-refresh-types"></a>Power BI yenileme türleri

Power BI yenileme işlemi, veri yenileme, OneDrive yenilemesi, sorgu önbelleklerinin yenilenmesi, kutucuk yenileme ve rapor görsellerinin yenilenmesi gibi birden çok yenileme türünden oluşabilir. Power BI, belirli bir veri kümesi için gereken yenileme adımlarını otomatik olarak belirlese de, bunların bir yenileme işleminin karmaşıklığını ve süresini nasıl etkilediğini bilmeniz gerekir. Hızlı başvuru için aşağıdaki tabloya bakın.

| Depolama modu | Veri yenileme | OneDrive yenilemesi | Sorgu önbellekleri | Kutucuk yenileme | Rapor görselleri |
| --- | --- | --- | --- | --- | --- |
| İçeri Aktar | Zamanlanmış ve isteğe bağlı | Bağlı veri kümeleri için evet | Premium kapasitede etkinleştirildiyse | Otomatik olarak ve isteğe bağlı | Hayır |
| DirectQuery | Uygulanamaz | Bağlı veri kümeleri için evet | Premium kapasitede etkinleştirildiyse | Otomatik olarak ve isteğe bağlı | Hayır |
| LiveConnect | Uygulanamaz | Bağlı veri kümeleri için evet | Premium kapasitede etkinleştirildiyse | Otomatik olarak ve isteğe bağlı | Evet |
| Gönder | Uygulanamaz | Uygulanamaz | Pratik değil | Otomatik olarak ve isteğe bağlı | Hayır |
| | | | | | |

#### <a name="data-refresh"></a>Veri yenileme

Power BI kullanıcıları için verilerin yenilenmesi, genellikle bir yenileme zamanlamasını temel alarak veya isteğe bağlı olarak verileri özgün veri kaynaklarından bir veri kümesine aktarmaktan ibarettir. Günlük olarak birden çok veri kümesi yenilemesi gerçekleştirebilirsiniz. Bu, temel alınan kaynak verileri sıkça değişiyorsa gerekli olabilir. Power BI, paylaşılan kapasitedeki veri kümelerini günlük sekiz yenileme ile sınırlar. Veri kümesi bir Premium kapasitede bulunuyorsa, günde 48’e kadar yenileme yapabilirsiniz. Daha fazla bilgi için bu makalenin ilerleyen kısımlarında bulunan zamanlanmış yenileme yapılandırma bölümüne göz atın.

Günlük yenileme sınırlamasında, hem zamanlanmış hem de isteğe bağlı olarak yapılan yenilemelerin birleşik toplamının dikkate alındığının unutulmaması önemlidir. Aşağıdaki ekran görüntüsünde gösterildiği gibi, veri kümesi menüsünde **Şimdi Yenile**’yi seçerek bir isteğe bağlı yenilemeyi tetikleyebilirsiniz. Power BI REST API’sini kullanarak, veri yenilemeyi programlama yoluyla da tetikleyebilirsiniz. Kendi yenileme çözümünüzü oluşturmak istiyorsanız [Veri Kümeleri - Veri Kümesini Yenileme](/rest/api/power-bi/datasets/refreshdataset) bölümüne göz atın.

![Şimdi yenile](media/refresh-data/refresh-now.png)

> [!NOTE]
> Veri yenilemelerinin 2 saatten kısa bir sürede tamamlanması gerekir. Veri kümeleriniz daha uzun yenileme işlemleri gerektiriyorsa, veri kümesini bir Premium kapasiteye geçirmeyi düşünebilirsiniz. Premium’da en uzun yenileme süresi 5 saattir.

#### <a name="onedrive-refresh"></a>OneDrive yenilemesi

Veri kümelerinizi ve raporlarınızı bir Power BI Desktop dosyasını, Excel çalışma kitabını, OneDrive veya SharePoint Online’da bulunan bir virgülle ayrılmış değer (.csv) dosyasını temel alarak oluşturduysanız Power BI, OneDrive yenilemesi olarak bilinen farklı türde bir yenileme gerçekleştirir. Daha fazla bilgi için bkz. [Power BI için dosyalardan veri alma](service-get-data-from-files.md).

Power BI’ın, veri kaynağındaki verileri bir veri kümesine aktardığı veri kümesi yenileme işleminin aksine, OneDrive yenilemesi esnasında veri kümeleri ve raporlar kendi kaynak dosyalarıyla eşitlenir. Power BI, OneDrive veya SharePoint Online’daki bir dosyaya bağlı veri kümesinin eşitleme gerektirip gerektirmediğini varsayılan olarak yaklaşık saatte bir denetler. Geçmiş eşitleme döngülerini incelemek için yenileme geçmişindeki OneDrive sekmesini denetleyin. Aşağıdaki ekran görüntüsü örnek bir veri kümesinin tamamlanan eşitleme döngüsünü gösterir.

![Yenileme geçmişi](media/refresh-data/refresh-history.png)

Yukarıdaki ekran görüntüsünde gösterildiği gibi, Power BI bu OneDrive yenilemesini **Zamanlanmış** yenileme olarak tanımlar. Ancak, yenileme aralığının yapılandırılması mümkün değildir. OneDrive yenilemesini sadece veri kümesinin ayarlarından devre dışı bırakabilirsiniz. Power BI’daki veri kümelerinizin ve raporlarınızın, değişiklikleri kaynak dosyalardan otomatik olarak almasını istemiyorsanız yenilemeyi devre dışı bırakmak faydalı olur.

Aşağıdaki ekran görüntüsünde gösterildiği gibi, veri kümesi OneDrive veya SharePoint Online’daki bir dosyaya bağlıysa, veri kümesi ayarları sayfasında sadece **OneDrive Kimlik Bilgileri** ve **OneDrive yenilemesi** bölümlerinin gösterildiğine dikkat edin. OneDrive veya SharePoint Online’daki bir kaynak dosyasına bağlı olmayan veri kümeleri için bu bölümler gösterilmez.

![OneDrive Kimlik Bilgileri ve OneDrive yenilemesi](media/refresh-data/onedrive-credentials-refresh.png)

Veri kümesi için OneDrive yenilemesini devre dışı bırakırsanız, veri kümesi menüsünden **Şimdi Yenile**’yi seçerek veri kümenizi isteğe bağlı olarak eşitleyebilirsiniz. Power BI, isteğe bağlı yenileme kapsamında Online veya SharePoint Online’daki kaynak dosyanın Power BI’daki veri kümesinden daha güncel olup olmadığını denetler ve dosya güncelse veri kümesini eşitler. **Yenileme geçmişi**, bu etkinlikleri **OneDrive** sekmesindeki isteğe bağlı yenilemeler olarak listeler.

OneDrive yenilemesinin özgün veri kaynaklarından veri çekmediğini aklınızda bulundurun. OneDrive yenilemesi, aşağıdaki diyagramda gösterildiği gibi meta veriler ve .pbix, .xslx veya .csv dosyasındaki veriler ile Power BI’daki kaynakları güncelleştirir. Power BI, veri kümesinin veri kaynaklarındaki en güncel verilerin alındığından emin olmak için isteğe bağlı yenileme kapsamında bir veri yenileme işlemi tetikler. **Zamanlanmış** sekmesine geçerseniz **Yenileme geçmişi** bölümünden bunu doğrulayabilirsiniz.

![OneDrive yenilemesi diyagramı](media/refresh-data/onedrive-refresh-diagram.png)

OneDrive veya SharePoint Online’a bağlı bir veri kümesi için OneDrive yenilemesini etkin tutup zamanlamaya göre bir veri yenileme gerçekleştirmek isterseniz, zamanlamayı Power BI veri yenilemesi OneDrive yenilemesinden sonra olacak şekilde yapılandırın. Örneğin, OneDrive veya SharePoint Online’da her akşam 01:00’de kaynak dosyasını güncelleştirmesi için kendi hizmet veya işleminizi oluşturduysanız, Power BI’a veri yenileme işlemini başlatmadan önce OneDrive yenilemesini tamamlaması için yeterli olacak süreyi tanımak üzere zamanlanmış yenilemeyi 02:30’da gerçekleşecek şekilde yapılandırabilirsiniz.

#### <a name="refresh-of-query-caches"></a>Sorgu önbelleklerini yenileme

Veri kümeniz bir Premium kapasitede bulunuyorsa, aşağıdaki ekran görüntüsünde gösterildiği gibi sorgu önbelleğe alma özelliğini etkinleştirerek ilişkili rapor ve panoların performansını geliştirebilirsiniz. Sorgu önbelleğe alma, sorgu sonuçlarını korumak için Premium kapasiteden kendi yerel önbelleğe alma hizmetini kullanmasını ister ve temel alınan veri kaynağının o sonuçları işlemesini önler. Daha fazla bilgi için bkz. [Power BI Premium'da sorgu önbelleğe alma](power-bi-query-caching.md).

![Sorgu önbelleğe alma](media/refresh-data/query-caching.png)

Ancak, veri yenilemenin ardından daha önce önbelleğe alınmış sorgu sonuçları geçerliliğini yitirir. Power BI önbelleğe alınan bu sonuçları atar ve bunları yeniden oluşturması gerekir. Bu nedenle, sorgu önbelleğe alma özelliği, (günde 48 kez gibi) sıkça yenilediğiniz veri kümeleri ile ilişkili olan raporlar ve panolar için pek faydalı olmayabilir.

#### <a name="tile-refresh"></a>Kutucuk yenileme

Power BI, panolarınızda yer alan her kutucuk görseli için bir önbellek tutar ve veriler değiştiğinde kutucuk önbelleklerini proaktif bir şekilde güncelleştirir. Diğer bir deyişle kutucuk yenileme, bir veri yenilemesinden sonra otomatik olarak gerçekleşir. Bu, hem zamanlanmış hem de isteğe bağlı gerçekleştirilen yenileme işlemleri için geçerlidir. Ayrıca, bir panonun sağ üst bölümündeki üç nokta (...) simgesini seçerek ve **Pano kutucuklarını yenile** seçeneğini belirleyerek kutucuk yenileme işlemi yapabilirsiniz.

![Pano kutucuklarını yenile](media/refresh-data/refresh-dashboard-tiles.png)

Bu işlem otomatik olarak gerçekleştiği için, kutucuk yenilemeyi veri yenilemenin bir iç parçası olarak düşünebilirsiniz. Ayrıca, yenileme süresinin kutucuk sayısıyla birlikte arttığını görebilirsiniz. Kutucuk yenileme ek yükü önemli olabilir.

Power BI, varsayılan olarak her kutucuk için tek bir önbellek tutar. Ancak, [Power BI ile satır düzeyinde güvenlik (RLS)](service-admin-rls.md) makalesinde anlatıldığı gibi kullanıcı rollerini temel alarak veri erişimini kısıtlamak için dinamik güvenlik kullanırsanız, Power BI’ın her rol ve kutucuk için bir önbellek tutması gerekir. Kutucuk önbelleklerinin sayısı rollerin sayısıyla katlanır.

[Analysis Services tablosal modeli ile dinamik satır düzeyinde güvenlik](desktop-tutorial-row-level-security-onprem-ssas-tabular.md) öğreticisinde vurgulandığı gibi, veri kümeniz RLS ile bir Analysis Services veri modeline canlı bağlantı kullanırsa bu durum daha karmaşık hale gelebilir. Bu durumda, Power BI’ın her kutucuk ve panoyu görüntüleyen her kullanıcı için bir önbellek tutması gerekir. Bu tür veri yenileme işleminin kutucuk yenileme kısmının, verileri kaynağından getirmek için harcadığı süreyi aşması, nadir gerçekleşen bir durum değildir. Kutucuk yenileme hakkında daha fazla ayrıntı için bkz. [Kutucuk hatalarıyla ilgili sorunları giderme](refresh-troubleshooting-tile-errors.md).

#### <a name="refresh-of-report-visuals"></a>Rapor görsellerini yenileme

Bu yenileme, sadece Analysis Services’e canlı bağlantılarla ilgili olduğu için daha az önem taşır. Power BI, bu bağlantılar için rapor görsellerinin son durumunu önbelleğe alır. Böylece, raporu tekrar görüntülediğinizde Power BI’ın Analysis Services tablosal modelini sorgulaması gerekmez. Power BI, rapor ile bir rapor filtresini değiştirme gibi etkileşimler kurduğunuzda, tablosal modeli sorgular ve rapor görsellerini otomatik olarak güncelleştirir. Bir raporun eski verileri gösterdiğinden şüpheleniyorsanız, aşağıdaki ekran görüntüsünde gösterildiği gibi tüm rapor görsellerinde bir yenileme işlemi yapılmasını tetiklemek için raporun Yenile düğmesini de seçebilirsiniz.

![Rapor görsellerini yenileme](media/refresh-data/refresh-report-visuals.png)

## <a name="review-data-infrastructure-dependencies"></a>Veri altyapısı bağımlılıklarını inceleme

Depolama modu ne olursa olsun, temel alınan veri kaynakları erişilebilir olmadıkça hiçbir veri yenilemesi başarıyla tamamlanamaz. Başlıca üç veri erişimi senaryosu bulunur:

- Şirket içinde bulunan veri kaynaklarını kullanan veri kümesi
- Buluttaki veri kaynaklarını kullanan veri kümesi
- Hem şirket içi hem de bulut kaynaklarındaki verileri kullanan veri kümesi

### <a name="connecting-to-on-premises-data-sources"></a>Şirket içi veri kaynaklarına bağlanma

Veri kümeniz, Power BI’ın doğrudan ağ bağlantısı üzerinden erişemediği bir veri kaynağını kullanıyorsa, yenileme zamanlamasını etkinleştirebilmeniz veya isteğe bağlı veri yenilemesi gerçekleştirebilmeniz için bu veri kümesine yönelik bir ağ geçidi bağlantısı yapılandırmanız gerekir. Veri ağ geçitleri ve nasıl çalıştıkları hakkında daha fazla bilgi edinmek için bkz. [Şirket içi veri ağ geçitleri nedir?](service-gateway-getting-started.md)

Aşağıdaki seçenekler mevcuttur:

- Gerekli veri kaynağı tanımı ile bir kurumsal ağ geçidi seçme
- Kişisel veri ağ geçidi dağıtma

> [!NOTE]
> Ağ geçidi gerektiren veri kaynaklarının listesini bu makalede bulabilirsiniz: [Veri kaynağınızı yönetme - İçeri Aktarma/Zamanlanmış Yenileme](service-gateway-enterprise-manage-scheduled-refresh.md).

#### <a name="using-an-enterprise-data-gateway"></a>Kurumsal ağ geçidi kullanma

Microsoft, veri kümesini şirket içi veri kaynağına bağlamak için kişisel ağ geçidinin yerine kurumsal veri ağ geçidinin kullanılmasını önerir. Ağ geçidinin doğru yapılandırıldığından emin olun. Ağ geçidinin en son güncelleştirmelere ve gerekli tüm veri kaynağı tanımlarına sahip olması gerekir. Veri kaynağı tanımı, Power BI’a, belirtilen kaynağa yönelik olarak bağlantı uç noktalarını, kimlik doğrulaması modunu ve kimlik bilgilerini de içeren bağlantı bilgilerini sağlar. Bir ağ geçidinde veri kaynaklarını yönetme hakkında daha fazla bilgi için bkz. [Veri kaynağınızı yönetme - içeri aktarma/zamanlanmış yenileme](service-gateway-enterprise-manage-scheduled-refresh.md).

Ağ geçidi yöneticisiyseniz, veri kümesini bir kurumsal ağ geçidine kolayca bağlayabilirsiniz. Yönetici izinleriyle, ağ geçidini hızla güncelleştirip varsa eksik veri kaynaklarını ekleyebilirsiniz. Hatta, eksik bir veri kaynağını doğrudan veri kümesi ayarları sayfasından ağ geçidinize ekleyebilirsiniz. Aşağıdaki ekran görüntüsünde gösterildiği gibi, veri kaynaklarını görüntülemek için iki durumlu düğmeyi genişletip **Ağ geçidine ekle** bağlantısını seçin. Öte yandan, ağ geçidi yöneticisi değilseniz, ağ geçidi yöneticisine istenen veri kaynağı tanımını eklemeye yönelik bir istek göndermek için görüntülenen iletişim bilgilerini kullanın.

![Ağ geçidine ekleme](media/refresh-data/add-to-gateway.png)

> [!NOTE]
> Veri kümesi sadece bir tane ağ geçidi bağlantısını kullanabilir. Diğer bir deyişle, birden çok ağ geçidi bağlantısı üzerinden şirket içi veri kaynaklarına erişim mümkün değildir. Buna uygun olarak, gerekli tüm veri kaynağı tanımlarını aynı ağ geçidine eklemeniz gerekir.

#### <a name="deploying-a-personal-data-gateway"></a>Kişisel veri ağ geçidini dağıtma

Kurumsal veri ağ geçidine erişiminiz yoksa ve veri kümelerini yöneten tek kişi sizseniz (yani diğerleriyle veri kaynaklarını paylaşmanız gerekmiyorsa), bir veri ağ geçidini kişisel modda dağıtabilirsiniz. **Ağ geçidi bağlantısı** bölümünde, **Yüklü kişisel ağ geçidiniz yok** seçeneğinin altından **Şimdi yükle**’yi belirleyin. [Şirket içi veri ağ geçidi (kişisel mod)](service-gateway-personal-mode.md) bölümünde belgelendiği gibi, kişisel veri ağ geçidinin bazı sınırlandırmaları bulunur.

Kurumsal veri ağ geçidinin aksine, kişisel ağ geçidine veri kaynağı tanımları eklemeniz gerekmez. Bunun yerine, aşağıdaki ekran görüntüsünde gösterildiği gibi veri kaynağı yapılandırmasını, veri kümesi ayarlarındaki **Veri kaynağı kimlik bilgileri** bölümünü kullanarak yönetirsiniz.

![Ağ geçidi için veri kaynağı kimlik bilgilerini yapılandırma](media/refresh-data/configure-data-source-credentials-gateway.png)

> [!NOTE]
> Kişisel veri ağ geçidi DirectQuery/LiveConnect modundaki veri kümelerini desteklemez. Veri kümesi ayarları sayfası bunu yüklemenizi isteyebilir, ancak kişisel ağ geçidiniz varsa ağ geçidi bağlantısını yapılandıramazsınız. Bu tür veri kümelerini destekleyecek bir kurumsal veri ağ geçidiniz bulunduğundan emin olun.

### <a name="accessing-cloud-data-sources"></a>Bulut veri kaynaklarına erişim

Power BI ve kaynak arasında doğrudan ağ bağlantısı oluşturulabilirse, Azure SQL DB gibi bulut veri kaynaklarını kullanan veri kümeleri bir veri ağ geçidine gerek duymaz. Buna uygun olarak, veri kümesi ayarlarındaki **Veri kaynağı kimlik bilgileri** bölümünü kullanarak bu veri kaynaklarının yapılandırmasını yönetebilirsiniz. Aşağıdaki ekran görüntüsünde gösterildiği gibi, ağ geçidi bağlantısı yapılandırmanız gerekmez.

![Ağ geçidi olmadan veri kaynağı kimlik bilgilerini yapılandırma](media/refresh-data/configure-data-source-credentials.png)

### <a name="accessing-on-premises-and-cloud-sources-in-the-same-source-query"></a>Şirket içi kaynaklara ve bulut kaynaklarına aynı kaynak sorgusunda erişme

Veri kümesi, birden çok kaynaktan veri alabilir ve bu kaynaklar şirket içinde veya bulutta yer alabilir. Ancak, önceki bölümlerde belirtildiği gibi, bir veri kümesi sadece tek bir ağ geçidi bağlantısını kullanabilir. Bulut veri kaynakları, ağ geçidi gerektirmese de veri kümesi hem şirket içi hem de bulut kaynaklarına tek bir karma sorguda bağlanırsa ağ geçidi gerekir. Bu senaryoda, Power BI’ın bulut veri kaynakları için de bir ağ geçidi kullanması gerekir. Aşağıdaki diyagram, bu türden bir veri kümesinin veri kaynaklarına nasıl eriştiğini gösterir.

![Bulut ve şirket içi veri kaynakları](media/refresh-data/cloud-on-premises-data-sources-diagram.png)

> [!NOTE]
> Veri kümesi, şirket içi ve bulut kaynaklarına bağlanmak için ayrı karma sorguları kullanırsa, Power BI şirket içi kaynaklara erişmek için bir ağ geçidi bağlantısını ve bulut kaynaklarına bağlanmak için de bir doğrudan ağ bağlantısını kullanır. Karma sorgu şirket içi ve bulut kaynaklarındaki verileri birleştirirse veya eklerse, Power BI bulut kaynakları için de ağ geçidi bağlantısına geçer.

Power BI veri kümeleri, kaynak verilere erişmek ve bunları almak için Power Query’yi kullanır. Aşağıdaki karma listelemesi, şirket içi kaynağındaki ve bulut kaynağındaki verileri birleştiren sorgunun basit bir örneğini gösterir.

```
Let

    OnPremSource = Sql.Database("on-premises-db", "AdventureWorks"),

    CloudSource = Sql.Databases("cloudsql.database.windows.net", "AdventureWorks"),

    TableData1 = OnPremSource{[Schema="Sales",Item="Customer"]}[Data],

    TableData2 = CloudSource {[Schema="Sales",Item="Customer"]}[Data],

    MergedData = Table.NestedJoin(TableData1, {"BusinessEntityID"}, TableData2, {"BusinessEntityID"}, "MergedData", JoinKind.Inner)

in

    MergedData
```

Ağ geçidini, şirket içi ve bulut kaynaklarındaki verileri birleştirmeyi veya eklemeyi destekleyecek şekilde yapılandırmak için iki seçeneğiniz bulunur:

- Şirket içi veri kaynaklarına ek olarak bulut kaynağı için veri kaynağı tanımını ağ geçidine ekleyin.
- **Kullanıcının bulut veri kaynaklarına, bu ağ geçidi kümesi aracılığıyla yenileme yapma izni ver** onay kutusunu işaretleyin.

![Ağ geçidi kümesi aracılığıyla yenileme](media/refresh-data/refresh-gateway-cluster.png)

Yukarıdaki ekran görüntüsünde olduğu gibi, **Kullanıcının bulut veri kaynaklarına, bu ağ geçidi kümesi aracılığıyla yenileme yapma izni ver** onay kutusunu etkinleştirirseniz Power BI, veri kümesi ayarlarında kullanıcının **Veri kaynağı kimlik bilgileri** bölümünün altında bulut kaynağı için tanımladığı yapılandırmayı kullanabilir. Bu, ağ geçidi yapılandırmasının ek yükünü azaltmaya yardımcı olabilir. Öte yandan, ağ geçidinizin oluşturduğu bağlantılar üzerinde daha fazla denetime sahip olmak istiyorsanız bu onay kutusunu etkinleştirmemeniz gerekir. Bu durumda, desteklemek istediğiniz her bulut kaynağına yönelik açık bir veri kaynağı tanımını ağ geçidinize eklemeniz gerekir. Onay kutusunu etkinleştirip bulut kaynağınız için açık veri kaynağı tanımlarını bir ağ geçidine eklemeniz de mümkündür. Bu durumda, ağ geçidi eşleşen tüm kaynaklar için veri kaynağı tanımlarını kullanır.

### <a name="configuring-query-parameters"></a>Sorgu parametrelerini yapılandırma

Power Query kullanarak oluşturduğunuz karma sorgular veya M sorguları, basit adımlardan parametreli yapılara kadar karmaşıklık yönünden farklılık gösterebilir. Yukarıdaki listeleme, AdventureWorks veritabanında bulunan belirli bir tabloya erişmek için _SchemaName_ ve _TableName_ adlı iki parametre kullanan küçük bir örnek karma sorguyu gösterir.

```
let

    Source = Sql.Database("SqlServer01", "AdventureWorks"),

    TableData = Source{[Schema=SchemaName,Item=TableName]}[Data]

in

    TableData
```

> [!NOTE]
> Sorgu parametreleri sadece İçeri aktarma modundaki veri kümeleri için desteklenir. DirectQuery/LiveConnect modu, sorgu parametresi tanımlarını desteklemez.

Parametreli veri kümesinin doğru veriye eriştiğinden emin olmak için, veri kümesi ayarlarında karma sorgu parametrelerini yapılandırmanız gerekir. [Power BI REST API](/rest/api/power-bi/datasets/updateparametersingroup)’sini kullanarak parametreleri programlama yoluyla da güncelleştirebilirsiniz. Aşağıdaki ekran görüntüsü, yukarıdaki karma sorguyu kullanan veri kümesi için sorgu parametrelerini yapılandırmayı sağlayan kullanıcı arabirimini gösterir.

![Sorgu parametrelerini yapılandırma](media/refresh-data/configure-query-parameters.png)

> [!NOTE]
> Power BI, dinamik veri kaynakları olarak da bilinen parametreli veri kaynağı tanımlarını şu anda desteklemez. Örneğin, Sql.Database("SqlServer01", "AdventureWorks") veri erişimi işlevini parametreli hale getiremezsiniz. Veri kümeniz dinamik veri kaynaklarını kullanıyorsa, Power BI bilinmeyen veya desteklenmeyen veri kaynakları algıladığını bildirir. Power BI’ın veri kaynaklarını tanımlayıp bunlara bağlanabilmesini istiyorsanız, veri erişimi işlevlerinizdeki parametreleri statik değerlerle değiştirmeniz gerekir. Daha fazla bilgi çin bkz. [Yenileme için desteklenmeyen veri kaynağıyla ilgili sorunları giderme](service-admin-troubleshoot-unsupported-data-source-for-refresh.md).

## <a name="configure-scheduled-refresh"></a>Zamanlanmış yenileme yapılandırma

Power BI ve veri kaynaklarınız arasındaki bağlantıyı oluşturma, bir veri yenilemesini yapılandırırken karşılaşılan açık ara en zorlu görevdir. Geri kalan adımlar oldukça basittir ve yenileme zamanlamasını ayarlamayı ve yenileme hatası bildirimlerini etkinleştirmeyi içerir. Adım adım yönergeler için [Zamanlanmış yenilemeyi yapılandırma](refresh-scheduled-refresh.md) nasıl yapılır kılavuzuna göz atın.

### <a name="setting-a-refresh-schedule"></a>Yenileme zamanlamasını ayarlama

**Zamanlanmış yenileme** bölümünde, veri kümesini yenileme sıklığını ve zaman aralıklarını tanımlayabilirsiniz. Önceden de belirtildiği gibi, veri kümeniz paylaşılan kapasitedeyse sekize, Power BI Premium’da ise 48’e kadar yenileme sıklığı yapılandırabilirsiniz. Aşağıdaki ekran görüntüsü, on iki saatlik bir zaman aralığında gerçekleştirilen yenileme zamanlamasını gösterir.

![Zamanlanmış yenileme yapılandırma](media/refresh-data/configure-scheduled-refresh.png)

Yenileme zamanlaması yapılandırıldıktan sonra, veri kümesi ayarları sayfası yukarıdaki ekran görüntüsünde gösterildiği gibi bir sonraki yenileme zamanını size bildirir. Örneğin, ağ geçidi ve veri kaynağı yapılandırmanız için veriyi daha erken yenilemek istiyorsanız, sol gezinti bölmesindeki veri kümesi menüsünde bulunan **Şimdi Yenile** seçeneğini kullanarak isteğe bağlı yenileme gerçekleştirin. İsteğe bağlı yenilemeler bir sonraki zamanlanmış yenileme süresini etkilemez ancak bu makalenin önceki bölümlerinde açıklandığı gibi günlük yenileme sınırınızdan düşülür.

Yapılandırılmış yenileme zamanının, Power BI’ın bir sonraki planlanan işlemi yapmaya başladığı kesin zaman olmayabileceğini unutmayın. Power BI, zamanlanmış yenilemelere en iyi çaba ilkesine göre başlar. Hedef, yenilemeyi zamanlanan zaman aralığının 15 dakika içerisinde başlatmaktır. Ancak, hizmet gerekli kaynakları daha erken ayıramazsa, bir saati bulabilen gecikmeler ortaya çıkabilir.

> [!NOTE]
> Power BI, dört kez art arda hata oluşursa veya hizmet tarafından, geçersiz ya da süresi dolmuş kimlik bilgileri gibi yapılandırma güncelleştirmesi gerektiren kurtarılamaz bir hata algılanırsa, yenileme zamanlamanızı devre dışı bırakır. Art arda oluşabilecek hata eşiğini değiştirmek mümkün değildir.

### <a name="getting-refresh-failure-notifications"></a>Yenileme hatası bildirimlerini alma

Power BI varsayılan olarak, yenileme hatalarının oluşması durumunda zamanında müdahale edilebilmesi için veri kümesi sahibine e-posta aracılığıyla yenileme hatası bildirimleri gönderir. Hizmet, art arda hatalar oluşması nedeniyle hizmet zamanlamanızı devre dışı bıraktığında da Power BI size bir bildirim gönderir. Microsoft, **Yenileme hatası bildirim e-postalarını bana gönder** onay kutusunu etkin bırakmanızı önerir.

Power BI, yalnızca yenileme hataları oluştuğunda değil aynı zamanda hizmet, zamanlanmış bir yenileme esnasında eylemsizlik nedeniyle durakladığında da bildirim gönderir. İki ay boyunca, bir veri kümesinde oluşturulan panoyu veya raporu hiçbir kullanıcı ziyaret etmezse, Power BI o veri kümesinin etkin olmadığını varsayar. Bu durumda Power BI, veri kümesinin sahibine hizmetin veri kümesi için yenileme zamanlamasını duraklattığını bildiren bir e-posta iletisi gönderir. Bu tür bildirimlerin bir örneği için aşağıdaki ekran görüntüsüne bakın.

![Duraklatılan yenileme için e-posta](media/refresh-data/email-paused-refresh.png)

Zamanlanmış yenilemeye devam etmek için,bu veri kümesi kullanılarak oluşturulan bir raporu veya panoyu ziyaret edin ya da **Şimdi Yenile** seçeneğini kullanarak veri kümesini kendiniz yenileyin.

### <a name="checking-refresh-status-and-history"></a>Yenileme durumunu ve geçmişini denetleme

Veri kümelerinizi, hata bildirimlerinin yanı sıra yenileme hataları için de düzenli aralıklarla denetlemek iyi bir fikirdir. Bunu yapmanın hızlı yollarından biri, çalışma alanında bulunan veri kümelerinin listesini görüntülemektir. Hataların küçük bir uyarı simgesiyle gösterildiği veri kümeleri. Aşağıdaki ekran görüntüsünde gösterildiği gibi, ek bilgi edinmek için uyarı simgesini seçin. Belirli yenileme hatalarıyla ilgili daha fazla bilgi almak için bkz. [Yenileme senaryolarıyla ilgili sorunları giderme](refresh-troubleshooting-refresh-scenarios.md).

![Yenileme durumu uyarısı](media/refresh-data/refresh-status-warning.png)

Uyarı simgesi, mevcut veri kümesi sorunlarının belirtilmesine yardımcı olur. Ancak, yenileme geçmişini arada bir denetlemek de iyi bir fikirdir. Adından da anlaşılacağı gibi yenileme geçmişi, geçmişteki eşitleme döngülerinin başarılı veya başarısız olma durumlarını incelemenize olanak tanır. Örneğin, ağ geçidi yöneticisi, süresi dolmuş bir dizi veritabanı kimlik bilgisini güncelleştirmiş olabilir. Aşağıdaki ekran görüntüsünde görüldüğü gibi yenileme geçmişi, etkilenen yenileme işleminin ne zaman tekrar çalışmaya başlamadığını gösteriyor.

![Yenileme geçmiş iletileri](media/refresh-data/refresh-history-messages.png)

> [!NOTE]
> Yenileme geçmişini görüntülemenizi sağlayan bağlantıyı veri kümesi ayarlarında bulabilirsiniz. Yenileme geçmişini, [Power BI REST API](/rest/api/power-bi/datasets/getrefreshhistoryingroup)’sini kullanarak programlama yoluyla da alabilirsiniz. Özel bir çözüm kullanarak, birden fazla veri kümesinin yenileme geçmişini daha merkezi bir şekilde izleyebilirsiniz.

## <a name="best-practices"></a>En iyi yöntemler

Veri kümelerinizin yenileme geçmişini düzenli olarak denetleme, raporlarınızın ve panolarınızın mevcut verileri kullandığından emin olmak için benimseyebileceğiniz en önemli en iyi deneyimlerden biridir. Sorun bulursanız, bunları en kısa sürede çözün ve gerekirse veri kaynağı sahipleri ve ağ geçidi yöneticileriyle iletişim kurun.

Buna ek olarak, veri kümeleriniz için güvenilir veri yenileme işlemleri oluşturmaya ve bunları korumaya yönelik aşağıdaki önerileri göz önünde bulundurun:

- Özellikle, veri kümeleriniz Power BI Premium’da bulunuyorsa, yenilemelerinizi yoğunluğun daha az olduğu saatler için zamanlayın. Veri kümeleriniz için yenileme döngülerini daha geniş bir zaman penceresine dağıtırsanız, kullanılabilir kaynaklara aşırı derecede yüklenen yoğunlukların oluşmasını engellemeye yardımcı olabilirsiniz. Yenileme döngüsünün geç başlatılması, kaynağın aşırı yüklendiğinin bir göstergesidir. Bir Premium kapasite tamamen tükendiyse, Power BI bir yenileme döngüsünü atlayabilir.
- Yenileme sınırlarını göz önünde bulundurun. Kaynak verisi sıkça değişiyorsa veya veri hacmi önemli ölçüdeyse, kaynaktaki artan yük ve sorgu performansındaki etkisi kabul edilebilir düzeyde olduğu sürece, İçeri aktarma modunun yerine DirectQuery/LiveConnect modunu kullanmayı düşünebilirsiniz. İçeri aktarma modundaki bir veri kümesini sürekli yenilemekten kaçının. Ancak DirectQuery/LiveConnect modunun, geri döndürülen veriler için bir milyon satır sınırı ve çalışan sorgular için 225 saniyelik yanıt süresi sınırı gibi, [Power BI Desktop'ta DirectQuery'yi kullanma](desktop-use-directquery.md) bölümünde belgelenen bazı sınırlamaları bulunur. Bu sınırlamalar yine de İçeri aktarma modunu kullanmanızı gerektirebilir. Çok büyük veri hacimleri için [Power BI’da toplamaları](desktop-aggregations.md) kullanmayı düşünebilirsiniz.
- Veri kümesi yenileme sürenizin en fazla yenileme süresini aşmadığından emin olun. Yenileme süresini denetlemek için Power BI Desktop’ı kullanın. 2 saatten daha uzun sürüyorsa, veri kümenizi Power BI Premium’a geçirmeyi düşünebilirsiniz. Paylaşılan kapasitede veri kümeniz yenilenemez olabilir. 1 GB’tan büyük veya yenilenmesi birkaç saat süren veri kümeleri için [Power BI Premium’da artımlı yenilemeyi](service-premium-incremental-refresh.md) kullanmayı da düşünebilirsiniz.
- Veri kümelerinizi, raporlarınızın ve panolarınızın kullandığı tabloları ve sütunları içerecek şekilde iyileştirin. Karma sorgularınızı iyileştirin ve eğer mümkünse dinamik veri kaynağı tanımlarını ve yüksek maliyetli DAX hesaplamalarını kullanmaktan kaçının. Yüksek bellek kullanımına ve işlem ek yüküne sahip oldukları için özellikle bir tablodaki her satırı test eden DAX işlevlerinden kaçının.
- Power BI’ın verimli kaynak sorguları oluşturabilmesi için Power BI Desktop ile aynı gizlilik ayarlarını uygulayın. Power BI Desktop’ın gizlilik ayarlarını yayımlamadığını göz önünde bulundurun. Veri kümenizi yayımladıktan sonra, ayarları veri kaynağı tanımlarında kendiniz yeniden uygulamanız gerekir.
- Özellikle [satır düzeyinde güvenlik (RLS)](service-admin-rls.md) kullanıyorsanız, panolarınızda kullandığınız görsellerin sayısını sınırlayın. Bu makalenin önceki bölümlerinde açıklandığı gibi, aşırı sayıda pano kutucuğu, yenileme süresini önemli ölçüde artırabilir.
- Veri kümelerinizi şirket içi veri kaynaklarına bağlamak için güvenilir bir kurumsal veri ağ geçidi dağıtımı kullanın. Ağ geçidinin kullanılamıyor veya aşırı yüklenmiş olması gibi ağ geçidiyle ilgili hataların oluştuğunu fark ederseniz, mevcut kümeye ek ağ geçitleri eklemek veya yeni bir küme dağıtmak (ölçeği artırmak veya ölçeği genişletmek) için ağ geçidi yöneticileriyle iletişim kurun.
- Zamanlanmış yenilemeler esnasındaki veri içeri aktarma işlemlerinin, DirectQuery/LiveConnect veri kümelerinde bulunan ve her kullanıcı etkileşiminde veri kaynaklarını sorgulayan raporların ve panoların performansını etkilememesi için, İçeri aktarılan veri kümeleri ve DirectQuery/LiveConnect veri kümeleri için ayrı veri ağ geçitleri kullanın.
- Power BI’ın, yenileme hatası bildirimlerini e-posta olarak size gönderebildiğinden emin olun. İstenmeyen posta filtreleri e-posta iletilerini engelleyebilir veya iletileri kolayca fark edemeyeceğiniz ayrı klasörlere taşıyabilir.

## <a name="next-steps"></a>Sonraki adımlar

[Zamanlanmış yenileme yapılandırma](refresh-scheduled-refresh.md)  
[Yenileme ile ilgili sorun giderme araçları](service-gateway-onprem-tshoot.md)  
[Yenileme ile ilgili sorun giderme senaryoları](refresh-troubleshooting-refresh-scenarios.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)
