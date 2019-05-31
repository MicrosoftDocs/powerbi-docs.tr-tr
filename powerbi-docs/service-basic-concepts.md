---
title: Power BI hizmetinde tasarımcılara yönelik temel kavramlar
description: Power BI hizmeti çalışma alanları, panoları, raporları, veri kümeleri ve çalışma kitapları.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
featuredvideoid: B2vd4MQrz4M
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/25/2019
ms.author: maggies
LocalizationGroup: Get started
ms.openlocfilehash: ff962335b573c6dd2a03ae5ab4633c1042a77059
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "64770786"
---
# <a name="basic-concepts-for-designers-in-the-power-bi-service"></a>Power BI hizmetinde tasarımcılara yönelik temel kavramlar

Bu makalenin amacı Power BI hizmetinde yolunuzu bulmanızı sağlamaktır: farklı öğeler nelerdir, birlikte nasıl çalışırlar ve bunlarla nasıl çalışabilirsiniz? Zaten [Power BI hizmetine kaydolduysanız](service-self-service-signup-for-power-bi.md) ve [veri eklediyseniz](service-get-data.md) bu makaleden daha iyi yararlanabilirsiniz. Bir tasarımcı olarak, normal iş akışınız genellikle Power BI Desktop'ta raporlar oluşturmakla başlar. Ardından bunları Power BI hizmetine yayımlarsınız ve burada raporlarda değişiklik yapmaya devam edebilirsiniz. Ayrıca Power BI hizmetinde raporlarınızı temel alan panolar da oluşturabilirsiniz. 

Bu makale için, henüz kendi raporlarınız yoksa [Power BI örnek içerik paketini](sample-datasets.md#the-power-bi-samples-as-content-packs) yüklemeyi deneyin.

![Tarayıcıda Power BI hizmeti Giriş ekranı](media/service-basic-concepts/power-bi-home-screen.png)

Power BI hizmetini tarayıcıda açtığınızda kendi Giriş ekranınızdan başlarsınız. Burada görebileceğiniz öğeler şunlardır:

1. Gezinti bölmesi (sol gezinti bölmesi)
2. Office 365 uygulama başlatıcısı
3. Power BI giriş düğmesi
4. Simge düğmeleri (ayarlar, yardım ve geri bildirim gibi)
5. Arama kutusu
6. Sık kullanılan panonun kutucukları
7. Sık kullanılan panolar ve raporlar

Raporlarınızın ve panolarınızın son kullanıcıları tarayıcıdaki Power BI hizmeti deneyimine aynı şekilde başlar.

Daha sonra bu özelliklerin ayrıntısına ineceğiz ancak şimdi bazı Power BI kavramlarını inceleyelim. Öte yandan önce bu videoyu izlemeniz de faydalı olabilir.  Videoda Will, temel kavramları inceliyor ve sizi Power BI hizmetinde bir tura çıkarıyor.

<iframe width="560" height="315" src="https://www.youtube.com/embed/B2vd4MQrz4M" frameborder="0" allowfullscreen></iframe>


## <a name="power-bi-concepts"></a>Power BI kavramları
Power BI'ın başlıca 4 yapı taşı şunlardır: **_panolar_** , **_raporlar_** , **_çalışma kitapları_** ve **_veri kümeleri_** . Bunların tamamı **_çalışma alanları_** halinde düzenlenmiştir. Dört yapı taşını ayrıntılı olarak incelemeden önce çalışma alanlarını anlamanız önemli olduğundan bu kavramla başlayacağız.

## <a name="workspaces"></a>Çalışma alanları
Çalışma alanları, Power BI'daki panolar, raporlar, çalışma kitapları ve veri kümeleri için kapsayıcı görevi görür. İki tür çalışma alanı vardır: *Çalışma alanım* ve*uygulama çalışma alanları*. Peki *uygulama* nedir? Power BI *uygulaması*, kuruluşunuzun Power BI son kullanıcılarına ana ölçümleri sunmak için oluşturulmuş bir pano ve rapor koleksiyonudur. Uygulamalar etkileşimlidir ama son kullanıcılar bunları düzenleyemez.

- *Çalışma alanım*, Power BI müşterilerinin kendi içeriği üzerinde çalışma yapabileceği kişisel çalışma alanıdır. Çalışma Alanım sayfasına yalnızca siz erişebilirsiniz. Çalışma Alanım sayfanızda panoları ve raporları paylaşabilirsiniz. Panolar ve raporlar üzerinde işbirliği yapmak veya uygulama oluşturmak istiyorsanız, bir uygulama çalışma alanında çalışmak istersiniz.      
-  *Uygulama çalışma alanlarını* iş arkadaşlarınızla işbirliği yapmak ve içerik paylaşmak için kullanabilirsiniz. Bu alanlarda ayrıca kuruluşunuz için uygulama oluşturabilir, yayımlayabilir ve yönetebilirsiniz. Bunları bir Power BI uygulamasını oluşturacak içerik için hazırlık alanı ve kapsayıcı olarak düşünebilirsiniz. Uygulama çalışma alanlarınıza iş arkadaşlarınızı ekleyerek panolar, raporlar, çalışma kitapları ve veri kümeleri üzerinde işbirliği yapabilirsiniz. Tüm uygulama çalışma alanı üyelerinin Power BI Pro lisansları gerekir. Uygulama kullanıcılarının, uygulamalara erişim sahibi olan iş arkadaşlarınız, mutlaka Pro lisanslarına gerek yoktur. Daha fazla bilgi edinin [yeni çalışma alanlarında](service-create-the-new-workspaces.md).  

Genel olarak paylaşma hakkında daha fazla bilgi için başlayın [panolar çalışmanızı paylaşmanın yolları](service-how-to-collaborate-distribute-dashboards-reports.md).

Şimdi Power BI'ın yapı taşlarına geçelim. Veriler olmadan panonuz veya raporunuz olamayacağından (boş panolarınız veya raporlarınız olabilir ancak bunlar veri içerene kadar kullanışlı değildir) **veri kümeleriyle** başlayalım.

## <a name="datasets"></a>Veri kümeleri
Bir *veri kümesi*, *içeri aktardığınız* veya *bağlandığınız* bir veri koleksiyonudur. Power BI, her türden veri kaynağına bağlanmanın ve bunları içeri aktarmanın yanı sıra hepsini tek bir yerde toplamanızı sağlar.  

Veri kümeleri, *çalışma alanlarıyla* ilişkilendirilmiştir ve tek bir veri kümesi, birden fazla çalışma alanına ait olabilir. Bir çalışma alanını açtığınızda ilişkilendirilmiş veri kümeleri, **Veri kümeleri** sekmesinde listelenir. Listelenen her bir veri kümesi tek bir veri kaynağını (örneğin; OneDrive'daki bir Excel çalışma kitabı veya tablosal bir şirket içi SSAS veri kümesi). Desteklenen birçok veri kaynağı olmakla birlikte yenilerini eklemeye de hiç ara vermiyoruz. Listesine bakın [Power BI ile kullanabileceğiniz veri kümesi türleri](service-get-data.md).

Aşağıdaki örnekte "Sales and marketing" uygulama çalışma alanını seçtim ve **Veri kümeleri** sekmesine tıkladım.

![Veri kümeleri seçildi](media/service-basic-concepts/power-bi-datasets.png)

**BİR** veri kümesi...

* bir veya daha fazla çalışma alanında tekrar tekrar kullanılabilir.
* birçok farklı raporda kullanılabilir.
* Söz konusu veri kümesindeki görselleştirmeler farklı birçok panoda görüntülenebilir.

  ![Veri kümesi diyagramı](media/service-basic-concepts/drawing2.png)

[Bir veri kümesine bağlanmak veya veri kümesini içeri aktarmak](service-get-data.md) için sol gezinti bölmesinin en altındaki **Veri Al**'ı seçin. İlgili kaynağa bağlanmak veya kaynağı içeri aktarmak ve veri kümesini etkin çalışma alanına eklemek için yönergeleri uygulayın. Yeni veri kümeleri sarı yıldız işareti ile gösterilir. Power BI'da gerçekleştirdiğiniz çalışmalar, temel alınan veri kümesinde değişikliğe neden olmaz.

Bir çalışma alanı üyesi tarafından eklenen veri kümeleri ile diğer çalışma alanı üyeleri için kullanılabilir bir *yönetici*, *üye*, veya *katkıda bulunan* rol.

Veri kümeleri yenilenebilir, yeniden adlandırılabilir, araştırılabilir ve kaldırılabilir. Veri kümesi kullanarak sıfırdan rapor oluşturabilir veya [hızlı öngörülerden](service-insights.md) faydalanabilirsiniz.  Veri kümesi kullanan raporları ve panoları görmek için **İlişkilileri görüntüle**'yi seçin. Araştırmak için veri kümesini seçmeniz gerekir. Aslında burada yaptığınız, veri kümesini, verilerinizin detaylarına gitmeye ve görselleştirmeler oluşturmaya başlayabileceğiniz rapor düzenleyicisinde açmaktır. Öyleyse, yeni konumuz olan raporlara geçelim.

### <a name="dig-deeper"></a>Derinlemesine
* [Power BI Premium nedir?](service-premium-what-is.md)
* [Power BI için veri alma](service-get-data.md)
* [Power BI için örnek veri kümeleri](sample-datasets.md)

## <a name="reports"></a>Raporlar
Power BI raporu çizgi grafikler, haritalar ve ağaç haritaları gibi görselleştirmeler içeren bir veya birden fazla sayfadan oluşur. Görselleştirmelere **_görseller_** adı da verilir. Bir rapordaki görselleştirmelerin tümü tek bir veri kümesinden gelir. Raporlar Power bı'da sıfırdan oluşturmak, bunları iş arkadaşlarınızın sizinle paylaştığı panolarla içeri aktarın veya Excel, Power BI Desktop, veritabanları ve SaaS uygulamalarına veri kümelerine bağlandığında, Power BI bunları oluşturabilirsiniz.  Örneğin, Power View sayfaları içeren bir Excel çalışma kitabına bağlandığınızda Power BI, söz konusu sayfaları temel alan bir rapor oluşturur. Bir SaaS uygulamasına bağlandığınızda ise Power BI, önceden oluşturulmuş bir raporu içeri aktarır.

Raporları görüntülemek ve raporlarla etkileşimli çalışmak için iki mod vardır: *Okuma Görünümü'nde* ve *düzenleme görünümü*. Bir raporu açtığınızda, Okuma Görünümü'nde açılır. Düzenleme izinlerine sahip sonra gördüğünüz **Raporu Düzenle** sol üst köşedeki ve raporu düzenleme Görünümü'nde görüntüleyebilirsiniz.  Bir raporu bir çalışma alanında, herkesle olup olmadığını bir *yönetici*, *üye*, veya *katkıda bulunan* rol düzenleyebilir. İçin tüm araştırma, tasarlama erişimleri, oluşturma ve paylaşma özelliklerine düzenleme için bu raporu görüntüleyin. Bunlar raporu paylaştığınız kişiler keşfedebilir ve Okuma Görünümü'nde bir raporla etkileşim kurma.   

Bir çalışma alanını açtığınızda ilişkilendirilmiş raporlar, **Raporlar** sekmesinde listelenir. Listelenen her bir rapor, temel alınan veri kümelerinden yalnızca birine dayalı bir veya daha fazla görselleştirme sayfasını temsil eder. Bir raporu açmak için seçin.

Uygulamayı açtığınızda bir pano ile sunulur.  Rapordan sabitlenmiş pano kutucuklarını (ilerleyen bölümlerde kutucuklar ayrıntılı olarak anlatılır) seçerek kaynak raporlara erişebilirsiniz. Tüm kutucukların raporlardan sabitlenmediğini, bir rapora ulaşmak için birden fazla kutucuğa tıklamanız gerekebileceğini unutmayın.

Raporlar varsayılan olarak Okuma Görünümü'nde açılır.  Raporu, Düzenleme Görünümü'nde açmak için **Raporu düzenle**'yi seçmeniz yeterlidir (gerekli izinlere sahipseniz).

Aşağıdaki örnekte, "Sales and marketing" uygulama çalışma alanını seçtim ve miyim sekmesine tıkladım **raporları**.

![Raporlar seçildi](media/service-basic-concepts/power-bi-reports.png)

**BİR** rapor...

* tek bir çalışma alanında yer alır.
* Bu çalışma alanı içindeki birden fazla panoyla ilişkilendirilebilir. Gelen bir rapor birden fazla Panoda görünebilir sabitlenmiş bir kutucuk.
* bir veri kümesindeki veriler kullanılarak oluşturulabilir. Power BI Desktop, birden fazla veri kaynağı tek bir veri kümesine bir raporda birleştirebilir ve söz konusu raporun Power BI'a aktarılabilir.

  ![Raporlar diyagramı](media/service-basic-concepts/drawing3new.png)

### <a name="dig-deeper"></a>Derinlemesine
- [Bir veri kümesini içeri aktararak Power BI hizmetinde bir rapor oluşturma](service-report-create-new.md)
- [Raporları Power BI mobil uygulamaları için en iyi duruma getirme](desktop-create-phone-report.md)

## <a name="dashboards"></a>Panolar
*Pano*, **Power BI hizmetinde** sizin oluşturduğunuz veya bir iş arkadaşınız tarafından **Power BI hizmetinde** oluşturulup sizinle paylaşılan bir öğedir. Bir veya daha fazla kutucuk ve pencere öğesi içeren (veya hiç içermeyen) tek bir tuvaldir. Bir rapordan veya [Soru-Cevap](power-bi-q-and-a.md) özelliğinden sabitlenmiş olan her bir kutucuk, veri kümesinden oluşturulmuş ve panoya sabitlenmiş tek bir [görselleştirme](power-bi-report-visualizations.md) görüntüler. Rapor sayfalarının tamamı da bir panoya tek bir kutucuk olarak sabitlenebilir. Panonuza, bu genel bakış konusunda ele alınamayacak kadar fazla sayıda yöntemle kutucuklar ekleyebilirsiniz. Daha fazla bilgi edinmek için bkz. [Power BI'daki pano kutucukları](service-dashboard-tiles.md).

Panolar neden oluşturulur?  Nedenlerden bazıları şunlardır:

* karar vermek için gereken tüm bilgileri tek bir bakışta görmek.
* işinizle ilgili en önemli bilgileri izlemek.
* tüm iş arkadaşlarının aynı doğrultuda ilerlediğinden, aynı bilgileri görüntülediğinden ve kullandığından emin olmak.
* bir işletme, ürün, iş birimi veya pazarlama kampanyası vb. için durumu izlemesi yapmak
* geniş bir panonun kişiselleştirilmiş (sizin için önemli olan tüm ölçümleri içeren) bir görünümünü oluşturmak.

Bir çalışma alanını açtığınızda ilişkilendirilmiş panolar, **Panolar** sekmesinde listelenir. Bir panoyu açmak için seçin. Bir uygulamayı açtığınızda bir pano görüntülenir.  Her bir pano, temel alınan veri kümelerinin belirli bir alt kümesine ilişkin özelleştirilmiş bir görünümü temsil eder.  Pano size aitse temel alınan veri kümelerinde de düzenleme erişimi sahibi olursunuz.  Pano sizinle paylaşıldıysa panoyla ve temel alınan raporlarla etkileşim kurabilirsiniz ancak yaptığınız değişiklikleri kaydedemezsiniz.

[Pano paylaşmak](service-share-dashboards.md) için kullanabileceğiniz birçok farklı yöntem vardır. Pano paylaşmak için Power BI Pro gerekir ve bu uygulama paylaşılan bir panoyu görüntülemek için de gerekli olabilir.

**BİR** pano...

* tek bir çalışma alanıyla ilişkilendirilir
* birçok farklı veri kümesindeki görselleştirmeleri görüntüleyebilir
* birçok farklı rapordaki görselleştirmeleri görüntüleyebilir
* diğer araçlardan (örneğin, Excel) sabitlenen görselleştirmeleri görüntüleyebilir

  ![Pano seçildi](media/service-basic-concepts/drawing1.png)

### <a name="dig-deeper"></a>Derinlemesine
* [Boş bir pano oluşturun ve veri alma](service-dashboard-create.md) .
* [Bir panoyu yineleme](service-dashboard-copy.md)
* [Bir panonun telefon görünümünü oluşturma](service-create-dashboard-mobile-phone-view.md)


## <a name="workbooks"></a>Çalışma kitapları
Çalışma kitapları özel bir veri kümesi türüdür. Yukarıdaki **Veri kümeleri** bölümünü okuduysanız, çalışma kitapları hakkında da bilmeniz gereken hemen her şeyi biliyorsunuzdur. Ancak Excel çalışma kitaplarının Power BI'da neden bazen **Veri kümesi**, bazen de **Çalışma kitabı** olarak sınıflandırıldığını merak ediyor olabilirsiniz.

Excel dosyalarını **Veri al** komutuyla kullandığınızda dosyada *İçeri Aktar* veya *Bağlan* seçeneklerine sahip olursunuz. Bağlan'ı seçtiğinizde çalışma kitabınız, Power BI'da tıpkı Excel Online'daki gibi görünecektir. Ancak, Excel Online'dan farklı olarak çalışma sayfalarınızdaki öğeleri doğrudan panolarınıza sabitlemenize yardımcı olacak harika özellikler edineceksiniz.

Çalışma kitabınızı Power BI'da düzenleyemezsiniz. Ancak, bazı değişiklikler yapmanız gerekirse Düzenle'ye tıklayıp çalışma kitabınızı Excel Online'da düzenlemeyi veya bilgisayarınızdaki Excel'de açmayı tercih edebilirsiniz. Yaptığınız değişiklikler OneDrive'daki çalışma kitabına kaydedilir.

### <a name="dig-deeper"></a>Derinlemesine
* [Excel çalışma kitabı dosyalarından veri alma](service-excel-workbook-files.md)
* [Excel'deki içeriği Power BI'da yayımlama](service-publish-from-excel.md)


## <a name="a-dashboard-in-my-workspace"></a>Çalışma Alanım'da bir pano
Çalışma alanlarını ve yapı taşlarını inceledik. Şimdi bunları bir araya getirelim ve Power BI hizmetinde pano deneyimini oluşturan parçaları gözden geçirelim.

![Tarayıcıda Power BI hizmeti](media/service-basic-concepts/completenewest.png)

### <a name="1-navigation-pane-left-nav"></a>1. **Gezinti bölmesi** (sol gezinti bölmesi)
Gezinti bölmesini kullanarak çalışma alanlarınızı ve Power BI yapı taşlarını (panolar, raporlar, çalışma kitapları ve veri kümeleri) bulup aralarında geçiş yapabilirsiniz.  

  ![Gezinti bölmesi](media/service-basic-concepts/power-bi-navigation.png)

* [Power BI'a veri kümesi, rapor ve pano eklemek için](service-get-data.md) **Veri Al**'ı seçin.
* Gezinti bölmesini bu simgeyi kullanarak genişletip daraltabilirsiniz ![gezinti bölmesi simgesi](media/service-basic-concepts/expand-icon.png)geçin.
* **Sık Kullanılanlar**'ı seçerek sık kullandığınız içerikleri açabilir veya yönetebilirsiniz.
* **Son görüntülenen**'i seçerek en son incelediğiniz içeriği görüntüleyebilir ve açabilirsiniz
* **Uygulamalar**'ı seçerek bir uygulamayı görüntüleyebilir, açabilir veya silebilirsiniz.
* İş arkadaşlarınızdan biri sizinle bir içerik mi paylaştı? Aradığınız içeriği bulmak ve sıralamak için **Benimle paylaşılan**'ı seçebilirsiniz.
* **Çalışma alanları**'nı seçerek çalışma alanlarınızı görüntüleyebilir ve açabilirsiniz.

Şu öğelere tek tıklayın:

* bir simgeyi veya başlığı içerik görünümünde açabilirsiniz
* sağ ok simgesinden (>) Sık Kullanılanlar, Son Görüntülenen ve Çalışma Alanları menülerini açabilirsiniz.
* **Çalışma Alanım**'daki kaydırılabilir pano, rapor, çalışma kitabı ve veri kümesi listesini görüntülemek için köşeli çift ayraç simgesi.

### <a name="2-canvas"></a>2. **Tuval**
Bir pano açtığımız için tuval alanında görselleştirme kutucukları görüntülenir. Örneğin, rapor düzenleyicisini açmış olsaydık tuval alanında bir rapor sayfası görüntülenecekti.

Panolar [kutucuklardan](service-dashboard-tiles.md) oluşur.  Kutucuklar Düzenleme görünümü'nde, Soru-Cevap'ta ve başka panolarda oluşturulur; ayrıca Excel'den, SSRS'den ve daha fazlasından sabitlenebilir. Doğrudan panoya eklenen özel kutucuk türüne [pencere öğesi](service-dashboard-add-widget.md) adı verilir. Bir panoda görünen kutucuklar buraya rapor oluşturucusu/sahibi tarafından özel olarak yerleştirilmiştir.  Bir panoya kutucuk ekleme eylemi *sabitleme* olarak adlandırılır.

![Power BI pano tuvali](media/service-basic-concepts/canvas.png)

Daha fazla bilgi için bkz. [Panolar](#dashboards) (yukarıda).

### <a name="3-qa-question-box"></a>3. **Soru-Cevap soru kutusu**
Verilerinizi araştırmanın bir yolu da soru sormak ve Power BI'dan görselleştirme biçiminde bir cevap almaktır. Soru-Cevap, bir panoya veya rapora içerik eklemek için kullanılabilir.

Soru-Cevap, panoya bağlı veri kümelerinde sorunuza cevap arar.  Söz konusu panoya sabitlenmiş en az bir kutucuğu bulunan veri kümelerine, bağlı veri kümeleri denir.

![Soru-Cevap soru kutusu](media/service-basic-concepts/power-bi-qna.png)

Siz sorunuzu yazmaya başlar başlamaz Soru-Cevap sizi Soru-Cevap sayfasına götürür. Yazdığınız sırada Soru-Cevap, başka bir şekilde ifade etme, otomatik doldurma, öneriler ve daha fazlasıyla doğru soruyu sormanıza ve en iyi cevabı almanıza yardımcı olur. Memnun olduğunuz bir görselleştirme (cevap) bulunduğunda bunu panonuza sabitleyin. Daha fazla bilgi için bkz. [Power BI'daki Soru-Cevap](power-bi-q-and-a.md).

### <a name="4-icon-buttons"></a>4. **Simge düğmeleri**
Sağ üst köşedeki simgeler; ayarlar, bildirimler, indirmeler, yardım alma ve Power BI ekibine geri bildirim sağlamaya yönelik kaynaklarınızdır. Panoyu **Tam ekran** modunda açmak için çift oku seçin.  

![simge düğmeleri](media/service-basic-concepts/power-bi-icons.png)

### <a name="5-dashboard-title-navigation-path-or-breadcrumbs"></a>5. **Pano başlığı** (Gezinti yolu veya içerik haritaları)
Etkin olan çalışma alanını ve panoyu belirlemek her zaman kolay olmayabileceğinden Power BI sizin için bir gezinti yolu oluşturur.  Bu örnekte çalışma alanını (Çalışma alanım) ve pano başlığını (Retail Analysis Sample) görüyoruz.  Bir rapor açmış olsaydık raporun adı gezinti yolunun sonuna eklenmiş olacaktı.  Yolun her bölümü etkin bir köprüdür.  

Pano başlığından sonra bir "C" simgesi olduğuna dikkat edin. Bu panonun [veri sınıflandırma etiketi](service-data-classification.md) "gizli" olarak belirlenmiştir. Bu etiket, verilerin hassasiyet ve güvenlik düzeyini tanımlar. Yöneticiniz veri sınıflandırma özelliğini etkinleştirdiyse her panoda varsayılan bir etiket kümesi bulunur. Pano sahiplerinin etiketi panonun güvenlik düzeyine göre değiştirmeleri gerekir.

![Veri sınıflandırma simgesi](media/service-basic-concepts/power-bi-title.png)

### <a name="6-office-365-app-launcher"></a>6. **Office 365 uygulama başlatıcısı**
Uygulama başlatıcısını kullanarak tüm Office 365 uygulamalarınıza tek tıkla ulaşabilirsiniz. Buradan e-posta, belgeler, takvim ve diğer uygulamaları hızla başlatabilirsiniz.

![Office uygulama başlatıcısı](media/service-basic-concepts/power-bi-waffle.png)

### <a name="7-power-bi-home"></a>7. **Power BI giriş**
**Power BI**'ın seçilmesi sizi Power BI giriş sayfasına döndürür.

   ![Hizmette "Power BI"](media/service-basic-concepts/version-new.png)

### <a name="8-labeled-icon-buttons"></a>8. **Etiketli simge düğmeleri**
Ekranın bu bölümünde içerikle (bu durumda pano) etkileşim kurmak için kullanabileceğiniz ek seçenekler bulunur.  Etiketli simgelerin yanı sıra, üç noktanın seçilmesi halinde panoyu yineleme, yazdırma ve yenileme gibi seçeneklerle de karşılaşılır.

   ![Etiketli simge düğmeleri](media/service-basic-concepts/power-bi-labeled-icons.png)

## <a name="next-steps"></a>Sonraki adımlar
- [Power BI nedir?](power-bi-overview.md)  
- [Power BI videoları](videos.md)  
- [Rapor düzenleyicisi: tura katılın](service-the-report-editor-take-a-tour.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)
