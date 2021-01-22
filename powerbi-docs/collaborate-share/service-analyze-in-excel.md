---
title: Power BI için Excel’de analiz etme
description: Microsoft Excel’de Power BI veri kümelerini analiz etme
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.custom: contperf-fy20q4
ms.service: powerbi
ms.subservice: pbi-collaborate-share
ms.topic: how-to
ms.date: 01/20/2021
LocalizationGroup: Reports
ms.openlocfilehash: e708e5001e49841d01b60cfc8712d37b990102f2
ms.sourcegitcommit: 77912d4f6ef2a2b1ef8ffccc50691fe5b38ee97a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98687132"
---
# <a name="analyze-in-excel"></a>Excel’de çözümleme
**Excel’de Çözümle** ile Power BI veri kümelerini Excel’e getirebilir, ardından PivotTable’ları, grafikleri, dilimleyicileri ve diğer Excel özelliklerini kullanarak bu verileri görüntüleyebilir ve bunlarla etkileşimli çalışabilirsiniz. **Excel’de Çözümle** özelliğini kullanmak için önce özelliği Power BI’dan indirmeniz, yüklemeniz ve ardından Excel’de kullanmak üzere bir veya birden fazla veri kümesi seçmeniz gerekir. 

![Excel’de çözümleme](media/service-analyze-in-excel/analyze-excel-00a.png)

Bu makalede Excel’de Çözümle özelliğini nasıl yükleyip kullanacağınız gösterilir, sınırlamaları açıklanır ve sonraki bazı adımlar sağlanır. Şunları öğreneceksiniz:

* [Excel’de Çözümle özelliğini yükleme](#install-analyze-in-excel)
* [Power BI verilerine bağlanma](#connect-to-power-bi-data)
* [Excel’i kullanarak verileri analiz etme](#use-excel-to-analyze-the-data)
* [Çalışma kitabınızı kaydetme ve paylaşma](#saving-and-sharing-your-new-workbook)
* [Gereksinimler](#requirements)

Şimdi işe girişelim ve yükleme işlemini başlatalım.

## <a name="install-analyze-in-excel"></a>Excel’de Çözümle özelliğini yükleme

**Excel’de Çözümle** özelliğini Power BI hizmetinde sağlanan bağlantılardan yüklemeniz gerekir. Power BI bilgisayarınızdaki Excel’in sürümünü algılar ve uygun sürümü (32 bit veya 64 bit) otomatik olarak indirir. Aşağıdaki bağlantıyı kullanarak Power BI hizmeti oturum açabilirsiniz:

* [Power BI’da oturum açma](https://app.powerbi.com)

Oturum açtıktan ve Power BI hizmeti tarayıcınızda çalışıyorsa, sağ üst köşedeki **diğer seçenekler** (...) seçeneğini belirleyin ve ardından **Excel güncelleştirmelerinde > indir**' i seçin. Bu menü öğesi Excel’de Çözümle güncelleştirmelerinin yeni yüklemeleri için geçerlidir.

![Power BI Giriş sayfasından Excel’de Çözümle’yi indirin](media/service-analyze-in-excel/analyze-excel-02.png)

Alternatif olarak, Power BI hizmetinde analiz etmek istediğiniz veri kümesine gidebilir ve veri kümesi, rapor veya başka bir Power BI öğesi için **Diğer seçenekler**’i seçebilirsiniz. Aşağıdaki resimde gösterildiği gibi, görüntülenen menüde **Excel’de Çözümle**’yi seçin.

![Veri kümesinden Excel'de Çözümleme](media/service-analyze-in-excel/analyze-excel-01.png)

Her iki şekilde de Power BI Excel’de Çözümle özelliğini yükleyip yüklemediğinizi algılar, yüklemediyseniz indirmeniz istenir. 

![Güncelleştirme gerekiyor](media/service-analyze-in-excel/analyze-excel-03.png)

İndirmeyi seçerseniz Power BI yüklediğiniz Excel’in sürümünü algılar ve Excel’de Çözümle yükleyicisinin uygun sürümünü indirir. Tarayıcınızın alt kısmında veya tarayıcı indirmenin ilerleme durumunu gösterdiği konumda indirme durumunu görürsünüz. 

![Güncelleştirmeler indiriliyor](media/service-analyze-in-excel/analyze-excel-04.png)

İndirme işlemi tamamlandığında yükleyiciyi (.msi) çalıştırarak Excel’de Çözümle’yi yükleyin. Yükleme işleminin adı Excel’de Çözümle özelliğinin adından farklıdır; bu ad **Microsoft Analysis Services OLE DB Sağlayıcısı** veya benzer bir ad olacaktır.

![Analysis Services OLE DB sağlayıcısını yükleyen güncelleştirmeler](media/service-analyze-in-excel/analyze-excel-05.png)

Tamamlandıktan sonra Power BI hizmetinde bir rapor (veya başka bir Power BI veri öğesi, örneğin bir veri kümesi) seçip bunu Excel’de analiz etmeye hazır olursunuz.

## <a name="connect-to-power-bi-data"></a>Power BI verilerine bağlanma

Power BI hizmetinde, Excel'de analiz etmek istediğiniz veri kümesine veya rapora gidin ve ardından:

1. **Diğer seçenekler** menüsünü seçin.

1. Görüntülenen menü öğeleri arasından **Excel’de Çözümle** öğesini seçin.

    Aşağıdaki resimde rapor seçimi gösterilir.

    ![Güncelleştirmeler yükleniyor](media/service-analyze-in-excel/analyze-excel-06.png)
    
    >[!NOTE]
    >Rapor menüsünden Excel'de Çözümle'yi seçerseniz, Excel'e getirilenin raporun temel veri kümesi olduğunu unutmayın.

    Ardından Power BI hizmeti, veri kümesinin **Excel’de Çözümle** özelliğiyle kullanılmak üzere tasarlanan (ve yapılandırılan) bir Excel dosyası oluşturur ve tarayıcınızda bir indirme işlemi başlar.
    
    ![Excel dosyasını indirme](media/service-analyze-in-excel/analyze-in-excel-download-xlsx.png)

    Dosya adı, türetildiği veri kümesi (ya da rapor veya başka bir veri kaynağı) ile eşleşir. Dolayısıyla raporun adı *Quarterly Report* olduğunda indirilen dosya **Quarterly Report.xlsx** olur.

    >[!Note]
    >Excel'de Çözümle artık ODC dosyası yerine Excel dosyası indirir. Bu da Power BI'dan dışarı aktarılan verilerde veri korumasını etkinleştirir. İndirilen Excel dosyası, Excel'de Çözümle için seçilen veri kümesindeki duyarlılık etiketini devralır.

3. Excel dosyasını başlatın.

    >[!NOTE]
    >Dosyayı ilk kez açtığınızda [Korumalı görünüm](https://support.microsoft.com/en-gb/office/what-is-protected-view-d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653?ui=en-us&rs=en-gb&ad=gb) ve [Güvenilir belge](https://support.microsoft.com/en-us/office/trusted-documents-cf872bd8-47ec-4c02-baa5-1fdba1a11b53) ayarlarına bağlı olarak **Düzenlemeyi Etkinleştir**'i ve ardından **İçeriği Etkinleştir**'i kullanmanız gerekebilir.
    >
    >![Korumalı görünüm düzenlemeyi etkinleştirme başlığının ekran görüntüsü](media/service-analyze-in-excel/protected-view-enable-editing-banner.png)
    >
    >![Güvenilir belge içeriği etkinleştirme başlığının ekran görüntüsü](media/service-analyze-in-excel/trusted-document-enable-content-banner.png)

Power BI’ı PivotTable aracılığıyla analiz etmek için Excel kullanırken, Power BI duyarlılık etiketi devralmayı Excel’e genişletir. Power BI veri kümesine uygulanan bir duyarlılık etiketi, Excel’de bir PivotTable oluşturduğunuzda Excel dosyasına otomatik olarak uygulanır. 

Veri kümesindeki etiket sonradan daha kısıtlayıcı olacak şekilde değiştirilirse Excel dosyasına uygulanan etiket, Excel’de veri yenilenmesinin ardından otomatik olarak güncelleştirilir. Veri kümesi daha az kısıtlayıcı olacak şekilde değiştirilirse etiket devralma veya güncelleştirme gerçekleşmez.

Excel’de el ile ayarlanmış olan duyarlılık etiketlerinin üzerine, veri kümesinin etiketi tarafından otomatik olarak yazılmaz. Bir Excel dosyasında el ile ayarlanmış duyarlılık etiketi varsa bu etiketi yükseltmeye yönelik bir ilke ipucu önerisi görüntülenir. 

Daha fazla bilgi için bkz. [Power BI’da duyarlılık etiketlerini uygulama](../admin/service-security-apply-data-sensitivity-labels.md).


## <a name="use-excel-to-analyze-the-data"></a>Excel’i kullanarak verileri analiz etme

Düzenlemeyi ve içeriği etkinleştirdikten sonra Excel size Power BI veri kümesinden analiz edilmeye hazır boş bir **PivotTable** ve **Alanlar** gösterir.

![Veri bağlantılı Excel](media/service-analyze-in-excel/analyze-in-excel-connected.png)

Excel dosyası, Power BI'daki veri kümenize bağlanan bir MSOLAP bağlantı dizesi içeriyor. Siz verilerle çalışırken veya verileri çözümlerken Excel, söz konusu veri kümesini Power BI'da sorgular ve sonuçları Excel'e döndürür. Söz konusu veri kümesi DirectQuery kullanarak canlı bir veri kaynağına bağlanırsa Power BI, veri kaynağını sorgular ve sonuçları Excel'e döndürür.

Power BI’daki verilere bağlantı artık kurulduğundan, Excel'de tıpkı yerel bir veri kümesiyle çalışır gibi söz konusu veritabanını analiz edebilir, PivotTable'lar ve grafikler oluşturabilirsiniz.

**Excel’de Çözümle**, özellikle şu veri kaynaklarına bağlanan veri kümeleri ve raporlar için yararlıdır:

* *Analysis Services Tablosal* veya *Çok Boyutlu* veri kaynakları
* Veri Çözümleme İfadeleri (DAX) kullanılarak oluşturulan model ölçülerinin bulunduğu veri modelleri içeren Excel çalışma kitapları veya Power BI Desktop dosyaları.

> [!IMPORTANT]
> **Excel'de Çözümle** özelliğinin kullanılması, verileri tüm ayrıntı düzeylerinde veri kümesine erişim izni olan tüm kullanıcıların kullanımına sunar.

Excel’de Çözümle özelliğini kullanmaya başladığınızda dikkate alınması gereken ve çözülmesi için fazladan bir veya iki adım gerektirebilen bir dizi öğe vardır. Bu olasılıklar aşağıdaki bölümlerde açıklanmıştır. 


### <a name="sign-in-to-power-bi"></a>Power BI'da oturum açma
Tarayıcınız üzerinden Power BI'da oturum açmış olsanız da ilk kez Excel'de yeni bir Excel dosyasını açtığınız zaman Power BI hesabınızla Power BI'da oturum açmanız istenebilir. Bu, Excel ile Power BI arasındaki bağlantının kimliğini doğrular.

### <a name="users-with-multiple-power-bi-accounts"></a>Birden çok Power BI hesabı olan kullanıcılar
Bazı kullanıcıların birden fazla Power BI hesabı vardır. Siz de bunlardan biriyseniz, bir hesapla Power BI’da oturum açmış olabilirsiniz ama Excel’de Çözülme özelliğinde kullanılan veri kümesine erişimizin olan hesap diğer hesabınız olabilir. Bu durumda, bir **Yasak** hatası ya da Excel'de Çözümle'de kullanılmakta olan bir veri kümesine erişim sağlamaya çalışırken oturum açma hatası görebilirsiniz.

Bu durum gerçekleşirse yeniden oturum açma fırsatı size sağlanacaktır. Bu fırsat sağlandığında, Excel'de Çözümle'nin erişmekte olduğu veri kümesine erişimi olan Power BI hesabınızla oturum açabilirsiniz. Ayrıca Excel'deki üst şeritte, şu anda oturum açılan hesabı belirleyen adınızı da seçebilirsiniz. Oturumu kapatın ve diğer hesabınızla yeniden oturum açın.


## <a name="saving-and-sharing-your-new-workbook"></a>Yeni çalışma kitabınızı kaydetme ve paylaşma

Power BI veri kümesiyle oluşturduğunuz Excel çalışma kitabını, aynı diğer çalışma kitapları gibi **kaydedebilirsiniz**. Ancak Power BI'da yayımlanabilen ve içeri aktarılabilen çalışma kitapları sadece veriyi tablolarda bulunduran veya bir veri modeli olan çalışma kitapları olabileceği için çalışma kitabını Power BI'da yayımlayamazsınız veya içeri aktaramazsınız. Yeni çalışma kitabının Power BI'daki veri kümesine sadece bağlantısı olduğundan, bu çalışma kitabını Power BI'da yayımlamak veya içeri aktarmak, yerimizde saymak olur.

Çalışma kitabınızı kaydettikten sonra kuruluşunuzdaki diğer Power BI kullanıcılarıyla paylaşabilirsiniz. 

Çalışma kitabınızı paylaştığınız bir kullanıcı bunu açtığında, PivotTable'larınızı ve verilerinizi çalışma kitabının en son kaydedilme anındaki gibi görür ve bu, verilerin son sürümü olmayabilir. En son verileri almak için kullanıcıların **Veri** şeridindeki **Yenile** düğmesini kullanmaları gerekir. Çalışma kitabı Power BI'daki bir veri kümesine bağlandığı için, çalışma kitabını yenilemeye çalışan kullanıcıların Power BI'da oturum açması ve bu yöntemle ilk kez güncelleştirme yapacakları zaman gerekli Excel güncelleştirmelerini yüklemesi gerekir.

Kullanıcıların veri kümesini yenilemeleri gerektiğinden ve Excel Online'da dış bağlantıları yenileme desteklenmediğinden kullanıcıların çalışma kitabını bilgisayarlarındaki Excel masaüstü sürümüyle açması önerilir.

> [!NOTE]
> Power BI kiracılarının yöneticileri, *Power BI Yönetici Portalı*'nı kullanarak, Analysis Services (AS) veritabanlarında barındırılan şirket içi veri kümelerinde **Excel'de Çözümle** kullanımını devre dışı bırakabilir. Bu seçenek devre dışı bırakıldığında **Excel'de Çözümle** AS veritabanları için devre dışı olur ancak diğer veri kümeleri için kullanılabilir olmaya devam eder.


## <a name="other-ways-to-access-power-bi-datasets-from-excel"></a>Excel’den Power BI veri kümelerine erişmenin diğer yolları
Belirli Office SKU’larına sahip kullanıcılar Excel’deki **Veri Al** özelliğini kullanarak da Excel’in içinden Power BI veri kümelerine bağlanabilir. SKU’nuz bu özelliği desteklemiyorsa **Veri Al** menü seçeneği görüntülenmez.

Aşağıdaki resimde gösterildiği gibi **Veri** şerit menüsünde **Veri Al > Power BI veri kümesinden** öğesini seçin.

![Veri Al menüsünü kullanma](media/service-analyze-in-excel/analyze-excel-10.png)

Bir bölme görüntülenir. Bu bölmede erişiminiz olan veri kümelerine göz atabilir, veri kümelerinin onaylandığını veya yükseltildiğini görebilir ve söz konusu veri kümelerine veri koruma etiketlerinin uygulanıp uygulanmadığını saptayabilirsiniz. 

Verileri bu yolla Excel’e alma hakkında daha fazla bilgi için, Excel belgelerinde [Power BI veri kümelerinden PivotTable oluşturma](https://support.office.com/article/31444a04-9c38-4dd7-9a45-22848c666884) konusuna bakın.

Ayrıca Excel’de **Veri Türleri** galerisindeki **öne çıkan tablolara** erişebilirsiniz. Öne çıkan tablolar hakkında daha fazla bilgi edinmek ve bu tablolara erişmeyi öğrenmek için bkz. [Excel’de Power BI öne çıkan tablolarına erişme (önizleme)](service-excel-featured-tables.md).

## <a name="requirements"></a>Gereksinimler
**Excel 'de çözümle** özelliğini kullanmaya yönelik bazı gereksinimler şunlardır:

* **Excel'de Çözümle**, Microsoft Excel 2010 SP1 ve sonraki sürümlerde desteklenir.
* Excel PivotTable'ları, sayısal alanların sürükle ve bırak ile toplama özelliğini desteklemez. Power BI'daki veri kümenizin *önceden tanımlanmış ölçülere sahip olması gerekir*. [Ölçü oluşturma](../transform-model/desktop-measures.md) hakkında bilgi edinin.
* Bazı kuruluşların Grup İlkesi kuralları, Excel'e gerekli olan **Excel'de Çözümle** güncelleştirmelerinin yüklenmesini engelleyebilir. Güncelleştirmeleri yükleyemiyorsanız yöneticinizle görüşün.
* **Excel'de Çözümle** özelliği, veri kümesinin Power BI Premium’da olmasını veya kullanıcının Power BI Pro lisansına sahip olmasını gerektirir. Lisans türleri arasındaki işlevsellik farkları hakkında daha fazla bilgi edinmek için _Power BI fiyatlandırması_ konusunun [Power BI özelliklerinin karşılaştırması](https://powerbi.microsoft.com/pricing/) bölümüne bakın.
* Kullanıcılar, temel alınan veri kümesi üzerinde izinleri varsa Excel’de Çözümle özelliği aracılığıyla veri kümelerine bağlanabilir.  Bir Kullanıcı, veri kümesini içeren çalışma alanında üye rolü olması veya bir çalışma alanında ya da veri kümesini içeren bir uygulamadaki bir veri kümesi için derleme iznine sahip olmak gibi birkaç şekilde bu izne sahip olabilir. [Veri kümeleri için oluşturma izni](../connect-data/service-datasets-build-permissions.md) hakkında daha fazla bilgi edinin.
* Konuk kullanıcılar, başka bir kiracının gönderdiği (kaynağından kaynaklı) veri kümeleri için **Excel 'de çözümle** özelliğini kullanamaz. 
* **Excel 'de çözümle** Power BI hizmeti bir özelliktir ve Power BI Rapor Sunucusu veya Power BI Embedded kullanılamaz. 
* **Excel’de Çözümle** seçeneği yalnızca Microsoft Windows çalıştıran bilgisayarlarda desteklenir.


**Excel 'de çözümle** özelliğini kaldırmanız gerekiyorsa, bilgisayarınızdaki **Program Ekle veya Kaldır** sistem ayarını kullanın.

## <a name="limitations-and-considerations"></a>Sınırlamalar ve önemli noktalar

- Satır düzeyi güvenlik (RLS) Excel 'de analiz için desteklenir. RLS, veri modeli düzeyinde zorlanır ve rapordaki verilere erişen tüm kullanıcılara her zaman uygulanır. [Satır düzeyi güvenlik](../admin/service-admin-rls.md)hakkında daha fazla bilgi edinin.
- Excel'de Çözümle özelliğini kullanırken beklemediğiniz bir sonuç aldığınız veya özelliğin beklediğiniz şekilde çalışmadığı durumlarla karşılaşabilirsiniz. Sık karşılaşılan sorunların çözümleri için bkz. [Excel 'de çözümle sorunlarını giderme](desktop-troubleshooting-analyze-in-excel.md) .

## <a name="next-steps"></a>Sonraki adımlar

Aşağıdaki makaleler de ilginizi çekebilir:

* [Power BI Desktop'ta çapraz rapor detaylandırma özelliğini kullanma](../create-reports/desktop-cross-report-drill-through.md)
* [Power BI Desktop’ta dilimleyicileri kullanma](../visuals/power-bi-visualization-slicers.md)
* [Excel'de Çözümleme sorunlarını giderme](desktop-troubleshooting-analyze-in-excel.md)
* [Excel’de Power BI öne çıkan tablolarına erişme (önizleme)](service-excel-featured-tables.md).
* [Power BI'da duyarlılık etiketlerini uygulama](../admin/service-security-apply-data-sensitivity-labels.md)
