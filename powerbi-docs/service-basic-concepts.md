---
title: Power BI - temel kavramlar
description: Power BI - temel kavramlar
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: B2vd4MQrz4M
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 05/31/2017
ms.author: mihart
ms.openlocfilehash: f20ea18fb46928bf7533caacf55a0cdb3d761571
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2017
---
# <a name="power-bi---basic-concepts-for-power-bi-service"></a>Power BI - Power BI hizmeti için temel kavramlar
<!-- Shared newnav Include -->
[!INCLUDE [newnavbydefault](./includes/newnavbydefault.md)]

Bu makalede, [Power BI'a kayıtlı ](service-self-service-signup-for-power-bi.md) ve [veri eklemiş](service-get-data.md) olduğunuz varsayılır.

Power BI hizmetini açtığınızda, bir ***pano*** görüntülenir. Power BI hizmeti panolarla Power BI Desktop'tan ayrılır.

![](media/service-basic-concepts/completenewer.png)

Power BI hizmetindeki kullanıcı arabiriminizde bulunan temel özellikler şunlardır:

1. gezinti çubuğu
2. kutucuklar içeren pano
3. Soru-Cevap soru kutusu
4. yardım ve geri bildirim düğmeleri
5. pano başlığı
6. Office 365 uygulama başlatıcısı
7. Power BI giriş düğmesi
8. Ek pano eylemleri

Daha sonra bu konunun ayrıntısına ineceğiz ancak şimdi bazı Power BI kavramlarını inceleyelim.

Alternatif olarak, bu makalenin geri kalanını okumadan önce bu videoyu da izleyebilirsiniz.  Videoda, Will temel kavramları inceler ve sizi Power BI hizmetinde bir tura çıkarır.

<iframe width="560" height="315" src="https://www.youtube.com/embed/B2vd4MQrz4M" frameborder="0" allowfullscreen></iframe>


## <a name="power-bi-concepts"></a>Power BI kavramları
Power BI'ın başlıca 3 yapı taşı şunlardır: ***panolar***, ***raporlar*** ve ***veri kümeleri***. Veriler olmadan panonuz veya raporunuz bulunamayacağından (boş panolarınız veya raporlarınız olabilir ancak bunlar veri içerene kadar kullanışlı değildir) **veri kümeleriyle** başlayalım.

## <a name="datasets"></a>Veri kümeleri
Bir *veri kümesi*, *içeri aktardığınız* veya *bağlandığınız* bir veri koleksiyonudur. Power BI, her türden veri kaynağına bağlanmanın ve bunları içeri aktarmanın yanı sıra hepsini tek bir yerde toplamanızı sağlar.  

Gezinti çubuğunda, bağlandığınız veya içeri aktardığınız veri kümeleri **Veri Kümeleri** başlığı altında yer alır. Listelenen her bir veri kümesi tek bir veri kaynağını (örneğin; OneDrive'daki bir Excel çalışma kitabı veya tablosal bir şirket içi SSAS veri kümesi). Desteklenen birçok veri kaynağı olmakla birlikte yenilerini eklemeye de hiç ara vermiyoruz. [Power BI ile kullanılabilen veri kümesi türlerinin listesine göz atın](service-get-data.md).

**BİR** veri kümesi...

* tekrar tekrar kullanılabilir.
* birçok farklı raporda kullanılabilir.
* Söz konusu veri kümesindeki görselleştirmeler farklı birçok panoda görüntülenebilir.
  
  ![](media/service-basic-concepts/drawing2.png)

[Bir veri kümesine bağlanmak veya veri kümesini içeri aktarmak](service-get-data.md) için **Veri Al** (gezinti çubuğunun alt kısmında) seçeneğini belirleyin ya da **Veri Kümeleri** başlığının yanındaki artı simgesini seçin. İlgili kaynağa bağlanmak veya kaynağı içeri aktarmak ve veri kümesini çalışma alanınıza eklemek için yönergeleri uygulayın. Yeni veri kümeleri, sol gezinti menüsünde sarı bir yıldız işaretiyle gösterilir. Power BI'da gerçekleştirdiğiniz çalışmalar temel alınan veri kümesinde değişikliğe neden olmaz.

Bir [***uygulama çalışma alanının*** parçasıysanız](service-collaborate-power-bi-workspace.md) çalışma alanının bir üyesi tarafından eklenen veri kümeleri, çalışma alanının diğer üyeleri tarafından da kullanılabilir.

Veri kümeleri yenilenebilir, yeniden adlandırılabilir, araştırılabilir, rapor oluşturmak için kullanılabilir ve kaldırılabilir. Araştırmak için veri kümesini seçmeniz gerekir. Aslında burada yaptığınız, veri kümesini, verilerinizin detaylarına gitmeye ve görselleştirmeler oluşturmaya başlayabileceğiniz rapor düzenleyicisinde açmaktır. Öyleyse, yeni konumuz olan raporlara geçelim.

### <a name="dig-deeper"></a>Derinlemesine:
* [Power BI Premium nedir?](service-premium.md)
* [Power BI için veri alma](service-get-data.md)
* [Power BI için örnek veri kümeleri ve içerik paketleri](sample-datasets.md)

## <a name="reports"></a>Raporlar
Bir Power BI raporu bir veya daha fazla sayfaya yayılmış görselleştirmelerden oluşur (çizgi grafikler, pasta grafikleri, ağaç haritaları ve çok daha fazlası gibi grafikler ve graflar). Görselleştirmelere ***görseller*** adı da verilir. Bir rapordaki görselleştirmelerin tümü tek bir veri kümesinden gelir. Raporlar Power BI'da sıfırdan oluşturulabilir, çalışma arkadaşlarınızın sizinle paylaştığı panolarla içeri aktarılabilir veya Excel, Power BI Desktop, veritabanları, SaaS uygulamaları ve [içerik paketlerine](service-organizational-content-pack-introduction.md) bağlanılarak oluşturulabilir.  Örneğin, Power View sayfaları içeren bir Excel çalışma kitabına bağlandığınızda Power BI, söz konusu sayfaları temel alan bir rapor oluşturur. Bir SaaS uygulamasına bağlandığınızda ise Power BI, önceden oluşturulmuş bir raporu içeri aktarır.

Raporlarla etkileşime girmeye yönelik 2 mod bulunur: [Okuma Görünümü](service-report-open-in-reading-view.md) ve [Düzenleme Görünümü](service-interact-with-a-report-in-editing-view.md).  Yalnızca raporu oluşturan kişi, ikincil sahipler ve izin verilen kişiler söz konusu rapor için ***Düzenleme Görünümü***'ndeki tüm araştırma, tasarım, oluşturma ve paylaşma özelliklerine erişebilir. Yukarıdakiler tarafından raporun paylaşıldığı kişiler ***Okuma Görünümü***'nü kullanarak söz konusu raporu araştırabilir ve bununla etkileşime geçebilir.   

Raporlarınız gezinti bölmesindeki **Raporlar** başlığı altında listelenir. Listelenen her bir rapor, temel alınan veri kümelerinden 1'ine dayalı 1 veya daha fazla görselleştirme sayfasını temsil eder. Bir raporu açmak için seçmeniz yeterlidir. Varsayılan olarak, rapor ilk önce Okuma Görünümü'nde açılır.  Raporu, Düzenleme Görünümü'nde açmak için **Raporu düzenle**'yi seçmeniz yeterlidir (gerekli izinlere sahipseniz).  Paylaşılan bir panoda bulunan raporlar gezinti çubuğunda listelenmiş olarak GÖRÜNMEZ. Bunun yerine, paylaşılan raporları, paylaşılan panodan doğrudan açmak için bir pano kutucuğunu seçebilirsiniz (Bu konu üzerinde daha fazla ayrıntı sağlanacaktır.)

**BİR** rapor...

* birden fazla panoyla ilişkilendirilebilir (söz konusu rapordan sabitlenen kutucuklar birden fazla panoda görünebilir).
* bir veri kümesindeki veriler kullanılarak oluşturulabilir. (Power BI Desktop'ın 1'den fazla veri kümesini tek bir raporda birleştirebilmesi ve bu raporun Power BI'a aktarılabilmesi bu duruma yönelik küçük bir istisna oluşturur)
  
  ![](media/service-basic-concepts/drawing3new.png)

## <a name="dashboards"></a>Panolar
*Pano*, sizin oluşturduğunuz veya bir iş arkadaşınız tarafından oluşturulup sizinle paylaşılan bir öğedir. Bir veya daha fazla kutucuk ve pencere öğesi içeren (veya hiç içermeyen) tek bir tuvaldir. Her bir kutucuk, veri kümesinden oluşturulmuş ve panoya sabitlenmiş tek bir [görselleştirme](power-bi-report-visualizations.md) görüntüler. Panonuza, bu genel bakış konusunda ele alınamayacak kadar fazla sayıda yöntemle kutucuklar ekleyebilirsiniz. Daha fazla bilgi edinmek için bkz. [Power BI'daki pano kutucukları](service-dashboard-tiles.md). 

Gezinti çubuğunda, "size ait" panolar, **Panolar** başlığı altında listelenir. Buradaki "size ait" ifadesi erişiminizin olduğu panolara (yalnızca oluşturduklarınız değil) işaret etmektedir. Her bir pano, temel alınan veri kümelerinin belirli bir alt kümesine ilişkin özelleştirilmiş bir görünümü temsil eder.  Pano size aitse gezinti çubuğunda **Veri Kümeleri** başlığı altında görünen, temel alınan veri kümelerine de erişim sahibi olursunuz.  Pano sizinle paylaşıldıysa yanında bir paylaşım simgesi ![](media/service-basic-concepts/sharing-icon.png) bulunur ve temel alınan veri kümelerinin gezinti çubuğunuzda görünüp görünmeyeceği panonun nasıl paylaşıldığına bağlıdır.

> [!NOTE]
> Sabitleme ve kutucuklar, "Kutucuklar içeren pano" başlığı altında daha ayrıntılı bir şekilde ele alınmıştır.
> 
> 

**BİR** pano...

* birçok farklı veri kümesindeki görselleştirmeleri görüntüleyebilir
* birçok farklı rapordaki görselleştirmeleri görüntüleyebilir
* diğer araçlardan (ör. Excel) sabitlenen görselleştirmeleri görüntüleyebilir
  
  ![](media/service-basic-concepts/drawing1.png)

### <a name="dig-deeper"></a>Derinlemesine:
**Bir pano [sıfırdan oluşturulabilir](service-dashboard-create.md)**: Yeni bir boş pano oluşturun ve ardından veri alın. 

**Bir iş arkadaşınız (veya siz) pano oluşturup [paylaşabilir](service-share-dashboards.md)**: Daveti kabul ettiğinizde, paylaşılan pano (ilişkili tüm raporlar ve veri kümeleri ile birlikte) gezinti çubuğunuza eklenir. Hem pano paylaşmak hem de paylaşılan bir panoyu görüntülemek için Power BI Pro gerekir.

**Bazen panolar veri kümesiyle birlikte içeri aktarılır veya veri kümesine bağlandığınızda oluşturulur**. Örneğin, Salesforce **Veri Al** sihirbazı, bu veri kümesinden bir pano ve/veya rapor oluşturulmasını isteyip istemediğinizi sorar. 

**Panolar neden oluşturulur?**  Nedenlerden bazıları şunlardır:

* karar vermek için gereken tüm bilgileri tek bir bakışta görmek
* iş ile ilgili en önemli bilgileri izlemek
* tüm iş arkadaşlarının aynı doğrultuda ilerlediğinden, aynı bilgileri görüntülediğinden ve kullandığından emin olmak
* bir işletme, ürün, iş birimi veya pazarlama kampanyası vb. için durumu izlemesi yapmak
* geniş bir panonun kişiselleştirilmiş bir görünümünü (sizin için önemli olan tüm ölçümleri içeren) oluşturmak

## <a name="my-workspace"></a>Çalışma Alanım
Power BI panonuza ve çalışma alanınıza geri döndük. Power BI hizmetinin giriş sayfasını oluşturan öğelere daha yakından bakalım.

![](media/service-basic-concepts/completenewer.png)

### <a name="1-navigation-bar-navbar"></a>1. **Gezinti çubuğu**
Power BI'ın şu yapı taşları arasında geçiş yapmak için gezinti çubuğunu kullanın: panolar, raporlar ve veri kümeleri.  

  ![](media/service-basic-concepts/navpane-new.png)

* [Power BI'a veri kümesi, rapor ve pano eklemek için](service-get-data.md) **Veri Al**'ı seçin.
* Gezinti çubuğunu ![](media/service-basic-concepts/expand-icon.png) simgesini kullanarak genişletip daraltabilirsiniz.
* Gezinti çubuğunda belirli öğeleri bulmak için **Ara**'yı kullanın.
* Yeni pano oluşturmak veya yeni bir veri kümesi almak için artı simgesini ![](media/service-basic-concepts/pbi_nancy_plus.png) seçin.
* Listelenen **Panoları, Raporları** ve **Veri Kümelerini** kullanabilirsiniz.  Paylaşılan panolar salt okunurdur ve paylaşım simgesini ![](media/service-basic-concepts/sharing-icon.png) gösterir.
* Pano, rapor ve veri kümesi adları genellikle temel alınan veri kümesi dosyasıyla eşleşir ancak [bunları yeniden adlandırabilirsiniz](service-rename.md).
* Bir panoya, rapora veya veri kümesine sağ tıklayarak içeriğe duyarlı menüyü görüntüleyebilirsiniz. 
  
  ![](media/service-basic-concepts/menu.png)

Tek tıklama ile

* bir başlığı daraltıp genişletebilir,
* bir panoyu görüntüleyebilir,
* raporu Okuma Görünümü'nde açabilir ve
* bir veri kümesini araştırabilirsiniz

### <a name="2-dashboard-with-tiles"></a>2. **Kutucuklar içeren pano**
Panolar [kutucuklardan](service-dashboard-tiles.md) oluşur.  Kutucuklar Düzenleme Görünümü'nde, Soru-Cevap'ta ve başka panolarda oluşturulur; ayrıca Excel'den, SSRS'den ve daha fazlasından sabitlenebilir. Doğrudan panoya eklenen özel kutucuk türüne [pencere öğesi](service-dashboard-add-widget.md) adı verilir. Bir panoda görünen kutucuklar buraya rapor oluşturucusu/sahibi tarafından özel olarak yerleştirilmiştir.  Bir panoya kutucuk ekleme eylemi *sabitleme* olarak adlandırılır.

![](media/service-basic-concepts/canvas.png)

Daha fazla bilgi için bkz. **Panolar** (yukarıda).

### <a name="3-qa-question-box"></a>3. **Soru-Cevap soru kutusu**
Verilerinizi araştırmanın bir yolu da soru sormak ve Power BI'dan görselleştirme biçiminde bir cevap almaktır. Soru-Cevap, bir rapora içerik eklemek için kullanılamaz; yalnızca panolara kutucuk biçiminde içerik eklemek için kullanılabilir.

Soru-Cevap, panoya bağlı veri kümelerinde sorunuza cevap arar.  Söz konusu panoya sabitlenmiş en az bir kutucuğu bulunan veri kümelerine, bağlı veri kümeleri denir.

![](media/service-basic-concepts/qna.png)

Siz sorunuzu yazmaya başlar başlamaz Soru-Cevap sizi Soru-Cevap sayfasına götürür. Yazdığınız sırada Soru-Cevap, başka bir şekilde ifade etme, otomatik doldurma, öneriler ve daha fazlasıyla doğru soruyu sormanıza ve en iyi cevabı almanıza yardımcı olur. Memnun olduğunuz bir görselleştirme (cevap) bulunduğunda bunu panonuza sabitleyin. Daha fazla bilgi için bkz. [Power BI'daki Soru-Cevap](service-q-and-a.md).

### <a name="4-full-screen-notifications-settings-downloads-help-and-feedback"></a>4. **Tam ekran, Bildirimler, Ayarlar, İndir, Yardım ve geri bildirim**
Sağ üst köşedeki simgeler; ayarlar, bildirimler, indirmeler, yardım alma ve Power BI ekibine geri bildirim sağlamaya yönelik kaynaklarınızdır. Panoyu **Tam ekran** modunda açmak için çift oku seçin.  

![](media/service-basic-concepts/help-new.png)

### <a name="5-dashboard-title-aka-what-dashboard-is-active"></a>5. **Pano başlığı** (Diğer bir deyişle, hangi pano etkindir?)
Hangi panonun etkin olduğunun ayrımına varabilmek her zamana kolay değildir.  Pano başlığı; pano görünümü sayfasında, Soru-Cevap sayfasında, rapor Düzenleme Görünümü ile rapor Okuma Görünümü'nde ve bir veri kümesini açtığınızda görünür.   

![](media/service-basic-concepts/dash-title-new.png)

### <a name="6-office-365-app-launcher"></a>6. **Office 365 uygulama başlatıcısı**
Uygulama başlatıcısı, Office 365 uygulamalarınıza ulaşmanıza yardımcı olması için tasarlandı.

![](media/service-basic-concepts/basicconcepts2-newer.png)

### <a name="7-power-bi-home"></a>7. **Power BI giriş**
Bu seçeneği belirlediğinizde en son görüntülediğiniz panoya gidersiniz.

   ![](media/service-basic-concepts/version-new.png)

### <a name="8-options"></a>8. **Seçenekler**
Çalışma alanının bu bölümü panoyla etkileşime yönelik simgeler içerir.  **Kutucuk ekle**, **Sık kullanılanlara ekle** ve **Paylaş** seçeneklerinin yanı sıra, üç noktanın seçilmesi halinde panoyu yineleme, yazdırma ve yenileme gibi seçeneklerle de karşılaşılır.

   ![](media/service-basic-concepts/options.png)

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile çalışmaya başlama](service-get-started.md)  
[Power BI videoları](videos.md)  
[Power BI Premium nedir?](service-premium.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

