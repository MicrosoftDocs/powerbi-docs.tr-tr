---
title: Power BI'da veri akışlarını oluşturma ve kullanma
description: Power BI’da veri akışları oluşturma ve kullanmayı öğrenin
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 01/15/2020
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: 403537f8cd18948c99cc4dffb911009771a8b806
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "80404748"
---
# <a name="creating-and-using-dataflows-in-power-bi"></a>Power BI'da veri akışlarını oluşturma ve kullanma

**Power BI**'da sağlanan gelişmiş veri hazırlama olanağıyla, veri akışı olarak adlandırılan bir veri koleksiyonu oluşturabilir ve bunu kullanarak çeşitli kaynaklardan iş verilerine bağlanabilir, verileri temizleyebilir, dönüştürebilir ve ardından bu veri akışını Power BI depolama alanına yükleyebilirsiniz.

**Veri akışı**, Power BI hizmetindeki çalışma alanlarında oluşturulan ve yönetilen bir *varlık* koleksiyonudur (varlıklar, tablolara benzer). Veri akışınızda varlıkları ekleyip düzenleyebilir, ayrıca doğrudan veri akışınızı oluşturduğunuz çalışma alanından veri yenileme zamanlamalarını yönetebilirsiniz.

Veri akışını oluşturduktan sonra, **Power BI Desktop**'ı veya **Power BI hizmetini** kullanarak Power BI veri akışlarına yerleştirdiğiniz verileri temel alan veri kümeleri, raporlar, panolar ve uygulamalar oluşturabilir, bu yolla iş etkinliklerinizle ilgili içgörüler kazanabilirsiniz.

![Power BI’da veri akışlarını kullanma](media/service-dataflows-create-use/dataflows-create-use_01a.png)

Veri akışını kullanmanın başlıca üç adımı vardır:

1. Bu işlemi rahatça yapacak şekilde tasarlanmış Microsoft araçlarını kullanarak veri akışını yazma
2. Veri akışınıza getirmek istediğiniz verilerin yenileme sıklığını zamanlama
3. Power BI Desktop kullanıp veri akışınızdan yararlanarak veri kümesini oluşturma 

Aşağıdaki bölümlerde, bu adımlardan her birini gözden geçirecek ve her adımı tamamlamak için sağlanan araçları tanıyacağız. Haydi başlayalım.

## <a name="creating-a-dataflow"></a>Veri akışı oluşturma
Veri akışı oluşturmak için, tarayıcıda Power BI hizmetini başlatın ve ardından aşağıdaki ekranda gösterildiği gibi sol taraftaki gezinti bölmesinden **çalışma alanını** (veri akışları Power BI hizmetindeki *my-workspace* içinde kullanılamaz) seçin. İçinde yeni veri akışı oluşturmak üzere yeni bir çalışma alanı da oluşturabilirsiniz. 

![Power BI'da veri akışı oluşturma](media/service-dataflows-create-use/dataflows-create-use_02a.png)

Veri akışı oluşturabileceğiniz bir **çalışma alanındayken**, tuvalin sağ üst kısmında **+ Oluştur** düğmesi görüntülenir. **+ Oluştur** düğmesini seçin ve sonra açılan listeden **Veri Akışı**'nı seçin. 

Her veri akışının *tek bir sahibi* olduğunu ve bu sahibin, veri akışını oluşturan kişi olduğunu bilmeniz önemlidir. Veri akışını yalnızca sahibi düzenleyebilir. Veri akışının oluşturulduğu çalışma alanı üzerinde okuma ve yazma izinleri olan tüm **çalışma alanı** üyeleri, bu makalenin devamında açıklandığı gibi **Power BI Desktop**'ın içinden veri akışına bağlanabilir.

![Power BI hizmetinde veri akışı oluşturmaya yönelik +Oluştur düğmesi](media/service-dataflows-create-use/dataflows-create-use_03a.png)

Buradan, sonraki bölümde daha ayrıntılı açıkladığımız **Varlıklar** ekleyebilirsiniz.

![Veri akışına Varlık ekleme](media/service-dataflows-create-use/dataflows-create-use_04a.png)

### <a name="add-entities"></a>Varlıkları ekleme

**Varlık**, veritabanlarındaki tablolara çok benzeyen ve verileri depolamak için kullanılan bir alan kümesidir. Aşağıdaki resimde, Power BI'a veri alabileceğiniz veri kaynaklarından bazıları gösterilmiştir.

![Varlıkları eklemek için veri kaynağı seçme](media/service-dataflows-create-use/dataflows-create-use_05a.png)

Veri kaynağı seçtiğinizde, aşağıdaki resimde gösterildiği gibi veri kaynağına bağlanırken kullanılacak hesap da dahil olmak üzere bağlantı ayarlarını sağlamanız istenir.

![Veri kaynağına bağlanma](media/service-dataflows-create-use/dataflows-create-use_06.png)

Bağlantı kurulduktan sonra, varlığınız için hangi verilerin kullanılacağını seçebilirsiniz. Veriler ve kaynak seçildikten sonra, Power BI veri akışınızdaki verileri yenilenmiş durumda tutmak için veri kaynağına art arda yeniden bağlanır. Bu bağlanmaların sıklığını bu kurulum işleminin sonraki adımlarında siz seçersiniz.

![Varlık için kullanılacak verileri seçme](media/service-dataflows-create-use/dataflows-create-use_07.png)

Varlıkta kullanılacak verileri seçtikten sonra, veri akışı düzenleyicisini kullanarak bu verileri veri akışınızda kullanılırken gereken biçime getirebilir veya dönüştürebilirsiniz.

### <a name="using-the-dataflow-editor"></a>Veri akışı düzenleyicisini kullanma

Veri kaynağınızdan varlığınız için kullanılacak verileri seçtikten sonra, veri seçiminizi varlığınız için en uygun biçimde şekillendirebilirsiniz. Bunun için, **Power BI Desktop**'taki **Power Query Düzenleyicisi**'ne benzeyen Power Query düzenleme deneyimini kullanırsınız. Power BI Desktop için [Sorguya genel bakış](desktop-query-overview.md) makalesinde, Power Query hakkında daha fazla bilgi edinebilirsiniz (Power Query, Power BI Desktop'a Power Query Düzenleyicisi olarak eklenmiştir). 

Sorgu Düzenleyicisi'nin her adımda oluşturduğu kodu görmek veya kendi şekillendirme kodunuzu oluşturmak isterseniz **Gelişmiş Düzenleyici**'yi kullanabilirsiniz. 

![Gelişmiş düzenleyiciyi kullanma](media/service-dataflows-create-use/dataflows-create-use_07b.png)

### <a name="dataflows-and-the-common-data-model-cdm"></a>Veri akışları ve Ortak Veri Modeli (CDM)

Veri akışı varlıkları, iş verilerinizi Common Data Model ile (Microsoft’un standartlaştırılmış şeması) kolayca eşlemenizi, bunu Microsoft ve üçüncü taraf verileriyle zenginleştirmenizi, makine öğrenmesine basitleştirilmiş erişim elde etmenizi sağlayan yeni araçlar içerir. İş verilerinize zeka ve eyleme dönüştürülebilir içgörüler getirmek için bu yeni özelliklerden yararlanılabilir. Sorguları Düzenleme adımındaki tüm dönüştürmeleri tamamladıktan sonra, veri kaynağı tablolarınızdaki sütunları Common Data Model ile de tanımlanan standart varlık alanlarına eşleyebilirsiniz. Standart varlıkların ortak veri modeliyle tanımlanan, bilinen bir şeması vardır.

[Ortak Veri Modeli nedir?](https://docs.microsoft.com/powerapps/common-data-model/overview) makalesinde, bu yaklaşım hakkında ve Ortak Veri Modeli hakkında daha fazla bilgi bulabilirsiniz.

Veri akışınızla Ortak Veri Modeli'nden yararlanmak için, **Sorguları Düzenle** iletişim kutusunda **Standart ile Eşle**'ye tıklayın. Görüntülenen **Varlıkları Eşle** ekranında, eşlemek istediğiniz standart varlığı seçebilirsiniz.

![Standart varlık ile eşleme](media/service-dataflows-create-use/dataflows-create-use_08.png)

Kaynak sütunu standart alana eşlediğinizde aşağıdakiler gerçekleşir:

1. Kaynak sütun standart alanın adını alır (adlar farklıysa sütun yeniden adlandırılır)
2. Kaynak sütun standart alanın veri türünü alır

Ortak Veri Modeli standart varlığını korumak için, eşlenmeyen tüm standart alanlar *Null* değeri alır.

Eşlemenin sonucunda özel alanlar içeren bir standart varlık elde etmeyi güvence altına almak için, eşlenmeyen tüm kaynak sütunlar olduğu gibi kalır.

Seçimlerinizi tamamladıktan sonra, varlığınız ile onun veri ayarları kaydedilmeye hazır olduğunda menüden **Kaydet**’i seçebilirsiniz. **Varlık ekle** düğmesini seçerek birden çok varlık oluşturabileceğinizi ve oluşturduğunuz sorgularla varlıkları geliştirmek için varlıkları düzenleyebileceğinizi unutmayın.

![Varlık eşlemesini kaydetme](media/service-dataflows-create-use/dataflows-create-use_09.png)

**Kaydet**'i seçtiğinizde, veri akışınızı adlandırmanız ve bir açıklama sağlamanız istenir.

![Yeni veri akışı için ad ve açıklama](media/service-dataflows-create-use/dataflows-create-use_10.png)

Hazır olduğunuzda ve **Kaydet** düğmesini seçtiğinizde, **veri akışınızın** oluşturulduğunu bildiren bir pencere gösterilir. 

![Veri akışı kaydedildi](media/service-dataflows-create-use/dataflows-create-use_11.png)

Harika! Artık bir sonraki adım olan veri kaynaklarınızın yenileme sıklığını zamanlama adımına hazırsınız.

## <a name="schedule-the-refresh-frequency"></a>Yenileme sıklığını zamanlama

Veri akışınız kaydedildikten sonra, bağlantılı veri kaynaklarınızdan her biri için yenileme sıklığını zamanlamak istersiniz.

Power BI veri akışlarında, verilerinizin güncelliğini korumak için Power BI veri yenileme işlemi kullanılır. **Power BI hizmetindeki** **çalışma alanı** bölümünde, aşağıdaki resimde gösterildiği gibi veri akışlarınız da dahil olmak üzere bilgilerinizin listelendiği bir alan koleksiyonu vardır.

![Power BI hizmetinde veri akışlarını yönetme](media/service-dataflows-create-use/dataflows-create-use_12.png)

Önceki resimde yer alan *Dynamics veri akışı* girdisi, önceki bölümde oluşturduğunuz veri akışıdır. Yenilemeyi zamanlamak için, aşağıdaki resimde gösterildiği gibi **Eylemler** bölümünün altında **Yenilemeyi zamanla** simgesini seçin. 

![Eylemler bölümünde Yenilemeyi zamanla düğmesi](media/service-dataflows-create-use/dataflows-create-use_13.png)

**Yenilemeyi zamanla** simgesini seçtiğinizde **Yenilemeyi zamanla** bölmesine ulaşırsınız. Bu bölme veri akışı yenileme sıklığını ve zamanını ayarlamanıza olanak tanır.

![Yenilemeyi zamanlama ayarları](media/service-dataflows-create-use/dataflows-create-use_14.png)

Yenilemeyi zamanlama hakkında daha fazla bilgi için, Power BI veri kümelerinin yenileme davranışının açıklandığı [zamanlanmış yenilemeyi yapılandırma](refresh-scheduled-refresh.md) hakkındaki makaleye bakın. Veri akışları, yenileme ayarları açısından Power BI veri kümeleriyle aynı davranışlara sahiptir. 


## <a name="connect-to-your-dataflow-in-power-bi-desktop"></a>Power BI Desktop’taki veri akışınıza bağlanma

Veri akışınızın oluşturduktan ve modeli dolduracak her veri kaynağının yenileme sıklığını zamanladıktan sonra, **Power BI Desktop** içinden veri akışınıza bağlanma adımı olan üçüncü ve son adıma hazırsınız. 

Veri akışına bağlanmak için, aşağıdaki resimde gösterildiği gibi Power BI Desktop'ta **Veri Al > Power BI > Power BI veri akışları (Beta)** öğesini seçin.

![Power BI Desktop’tan veri akışlarına bağlanma](media/service-dataflows-create-use/dataflows-create-use_15.png)

Buradan, veri akışınızı kaydettiğiniz **çalışma alanına** gidin, veri akışını seçin ve sonra oluşturduğunuz varlıkları listeden seçin.

Ayrıca, veri akışınızın adını ve diğer birçok veri akışı varlığı içinde varlıklarınızı hızla bulmak için, pencerenin üst kısmındaki **arama çubuğunu** da kullanabilirsiniz.

Varlığı ve ardından **Yükle** düğmesini seçtiğinizde, varlıklar **Power BI Desktop**'taki **Alanlar** bölmesinde gösterilir ve bunlar diğer herhangi bir veri kümesindeki **tablolarla** aynı şekilde görünür ve davranır.

## <a name="using-dataflows-stored-in-azure-data-lake-storage-gen2"></a>Azure Data Lake Storage 2. Nesil’de depolanan veri akışlarını kullanma

Bazı kuruluşlar, veri akışlarının oluşturma ve yönetimi için kendi depolama alanını kullanmayı isteyebilir. Gereksinimleri izleyip izinleri düzgün şekilde yönetirseniz Azure Data Lake Storage 2. Nesil ile veri akışlarını tümleştirebilirsiniz. Bu yaklaşımın tüm gereksinimlerinin belgelerine, [Veri akışları ve Azure Data Lake tümleştirmesi (Önizleme)](service-dataflows-azure-data-lake-integration.md) adlı genel bakış belgesinden itibaren erişilebilir.


## <a name="troubleshooting-data-connections"></a>Veri bağlantısı sorunlarını giderme

Bazı durumlarda veri akışlarının veri kaynaklarına bağlanırken sorunlarla karşılaşılabilir. Bu bölümde bu tür sorunların çıkması durumunda sorun giderme ipuçları sağlanır. 

* **Salesforce bağlayıcısı** - Veri akışlarıyla Salesforce için deneme hesabı kullanıldığında, bağlantı hatası oluşur ve hiçbir bilgi sağlanmaz. Bu sorunu çözmek için, test ederken üretim Salesforce hesabı veya geliştirici hesabı kullanın.

* **SharePoint bağlayıcısı** - Alt klasör veya belge eklemeden SharePoint sitesinin kök adresini sağladığınızdan emin olun. Örneğin, şuna benzer bir bağlantı kullanın: `https://microsoft.sharepoint.com/teams/ObjectModel/` 

* **JSON Dosya bağlayıcısı**: Şu anda bir JSON dosyasına yalnızca temel kimlik doğrulaması kullanarak bağlanabilirsiniz.  Bir JSON dosyasına URL içinden kimlik bilgileri sağlayarak bağlanma işlemi (ör. `https://XXXXX.blob.core.windows.net/path/file.json?sv=2019-01-01&si=something&sr=c&sig=123456abcdefg`. ) şu anda **desteklenmiyor**.  

* **Azure SQL Veri Ambarı**: Veri akışları şu anda Azure SQL Veri Ambarı için Azure Active Directory (AAD) kimlik doğrulamasını desteklemiyor. Bu senaryoda Temel kimlik doğrulaması kullanın.

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

Veri akışlarıyla ilgili bilinen birkaç sınırlama vardır ve bunlar aşağıdaki listede açıklanmaktadır.

* Veri akışının çıkışı şu türlerden birinde olmalıdır: *Tarih/Saat, Ondalık Sayı, Metin, Tamsayı, Tarih/Saat/Bölge, Doğru/Yanlış, Tarih, Saat*
* Şu anda veri akışlarının içinde dinamik işlevler desteklenmemektedir


## <a name="next-steps"></a>Sonraki Adımlar

Bu makalede kendi **veri akışınızı** oluşturma ve bundan yararlanmak için **Power BI Desktop**'ta veri kümesi ve rapor oluşturma işlemleri açıklanmıştır. Aşağıdaki makaleler, veri akışlarını kullanırken gerekecek diğer bilgiler ve senaryolar açısından yararlıdır:

* [Veri akışları ile self servis veri hazırlığı](service-dataflows-overview.md)
* [Power BI Premium'da hesaplanan varlıkları kullanma](service-dataflows-computed-entities-premium.md)
* [Şirket içi veri kaynakları ile veri akışlarını kullanma](service-dataflows-on-premises-gateways.md)
* [Power BI veri akışları için geliştirici kaynakları](service-dataflows-developer-resources.md)
* [Veri akışları ve Azure Data Lake tümleştirmesi (Önizleme)](service-dataflows-azure-data-lake-integration.md)

Ortak Veri Modeli hakkında daha fazla bilgi için genel bakış makalesini okuyabilirsiniz:
* [Ortak Veri Modeli - genel bakış ](https://docs.microsoft.com/powerapps/common-data-model/overview)
* [GitHub'da Ortak Veri Modeli şeması ve varlıkları hakkında daha fazla bilgi edinin](https://github.com/Microsoft/CDM)

İlgili Power BI Desktop makaleleri:

* [Power BI Desktop'tan Power BI hizmetindeki veri kümelerine bağlanma](desktop-report-lifecycle-datasets.md)
* [Power BI Desktop'ta sorgulara genel bakış](desktop-query-overview.md)

İlgili Power BI hizmeti makaleleri:
* [Zamanlanmış yenileme yapılandırma](refresh-scheduled-refresh.md)
