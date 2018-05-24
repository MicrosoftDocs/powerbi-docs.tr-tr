---
title: 'Power BI için Customer Profitability Sample: Tura katılın'
description: 'Power BI için Customer Profitability Sample: Tura katılın'
author: amandacofsky
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/22/2018
ms.author: mihart
LocalizationGroup: Samples
ms.openlocfilehash: f20fe4595236381106b6cb2a676ffd3d3baa3971
ms.sourcegitcommit: 2b9ef93bbff5c741ba55ea0502f642632683d593
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/24/2018
---
# <a name="customer-profitability-sample-for-power-bi-take-a-tour"></a>Power BI için Customer Profitability Sample: Tura katılın

## <a name="overview-of-the-customer-profitability-sample"></a>Müşteri Karlılığı örneğine genel bakış
"Customer Profitability Sample" içerik paketinde, pazarlama malzemeleri üreten bir şirkete ilişkin pano, rapor ve veri kümesi bulunmaktadır. Bu pano, mali işlerden sorumlu bir genel müdür (CFO) tarafından, 5 departman yöneticisi (diğer adıyla idareciler), ürünler, müşteriler ve brüt kâr ile ilgili ana ölçümleri görme amacıyla oluşturulmuştur. CFO, kârlılığı etkileyen faktörleri bir bakışta görebiliyor.

![power bi panosu](media/sample-customer-profitability/power-bi-dash.png)

Bu örnek, Power BI'ı işle ilgili veriler, raporlar ve panolarla birlikte nasıl kullanabileceğinizi gösteren serinin bir parçasıdır. Anonim hale getirilmiş bu gerçek veriler, obviEnce'tan ([www.obvience.com](http://www.obvience.com/)) alınmıştır. Veriler çeşitli biçimlerde sunulur: içerik paketi/uygulama, Excel çalışma kitabı veya .pbix Power BI Desktop dosyası. Bkz: [Örnek veri kümeleri](sample-datasets.md).

## <a name="prerequisites"></a>Önkoşullar
Birlikte ilerlemek ister misiniz? Bu öğreticide, Power BI hizmeti ve "Müşteri Karlılığı" örnek içerik paketi kullanılır.  Rapor deneyimleri son derece benzer olduğundan, Power BI Desktop ve örnek PBIX dosyasını kullanarak da örneği takip edebilirsiniz. İçerik paketine ve PBIX dosyasına bağlanma yönergeleri aşağıda verilmiştir.

### <a name="get-the-content-pack-for-this-sample"></a>Bu örneğe ilişkin içerik paketini edinme

1. Power BI hizmeti (app.powerbi.com) sayfasına gidin ve oturum açın.
2. Sol alt köşedeki **Veri Al** seçeneğini belirleyin.

    ![veri al](media/sample-datasets/power-bi-get-data.png)
3. Görüntülenen Veri Al sayfasında **Örnekler** simgesini seçin.

   ![örnekler simgesi](media/sample-datasets/power-bi-samples-icon.png)
4. **Müşteri Kârlılığı Örneği**'ni ve ardından **Bağlan**'ı seçin.  

   ![Veri Al](media/sample-customer-profitability/get-supplier-sample.png)
5. Power BI, içerik paketini içeri aktarır ve geçerli çalışma alanınıza yeni bir pano, rapor ve veri kümesi ekler. Yeni içerik sarı yıldızla işaretlenir. Power BI'da test çalıştırması gerçekleştirmek için örnekleri kullanın.  

   ![Yıldız işareti](media/sample-customer-profitability/supplier-sample-asterisk.png)

### <a name="get-the-pbix-file-for-this-sample"></a>Bu örneğe ilişkin .pbix dosyasını edinme

Alternatif olarak, örneği bir .pbix dosyası olarak indirebilirsiniz. Bu dosya biçimi, Power BI Desktop ile kullanım için tasarlanmıştır.
[Müşteri Kârlılığı Örneği](http://download.microsoft.com/download/6/A/9/6A93FD6E-CBA5-40BD-B42E-4DCAE8CDD059/Customer-Profitability-Sample-PBIX.pbix)

### <a name="get-the-excel-workbook-for-this-sample"></a>Bu örneğe ilişkin Excel çalışma kitabını edinme

Bu örnekte kullanılan veri kaynağını detaylı olarak incelemek isterseniz, [(Excel çalışma kitabı)](http://go.microsoft.com/fwlink/?LinkId=529781) olarak da bulabilirsiniz. Çalışma kitabı, görüntüleyebileceğiniz ve değiştirebileceğiniz Power View sayfaları içerir. Ham verileri görmek için **Power Pivot > Yönet** seçeneğini belirleyin.


## <a name="what-is-our-dashboard-telling-us"></a>Panomuz bize ne anlatıyor?

**Çalışma Alanım** bölümünde Customer Profitability örneğine ilişkin panoyu bulun:

![Müşteri Kârlılığı örneğine ilişkin pano](media/sample-customer-profitability/power-bi-dash.png)

### <a name="company-wide-dashboard-tiles"></a>Genel şirket durumu ile ilgili pano kutucukları
1. Power BI hizmetinde panoyu açın. Bu pano kutucukları CFO'muza, önem verdiği üst düzey şirket ölçümlerine yönelik bir bakış sağlar.  İlginç bir bulguyla karşılaştığında bir kutucuğu seçip söz konusu verileri ayrıntılı olarak inceleyebilir.

2. Panonun sol tarafındaki kutucukları gözden geçirin.

    ![yöneticiler için kutucuklar](media/sample-customer-profitability/power-bi-manager.png)

- Şirketimizin brüt kârı %42,5.
- 80 müşterimiz var.
- 5 farklı ürün satıyoruz.
- Bütçemizdeki gelir varyansının (yüzde cinsinden) en düşük olduğu ayın Şubat, en yüksek olduğu ayın ise Mart olduğunu görüyoruz.
- Gelirimizin çoğunu Doğu ve Kuzey bölgelerden elde ediyoruz. Brüt kârın bütçeyi hiçbir zaman aşmadığı ve ER-0 ile MA-0 için biraz daha fazla inceleme yapılması gerektiği görülüyor.
- Yıl için toplam gelir bütçeye yakın.


### <a name="manager-specific-dashboard-tiles"></a>Yöneticiye özgü pano kutucukları
Panonun sağ tarafındaki kutucuklar ise bir ekip puan kartı sağlar. CFO'nun, yöneticilerini takip etmesi gerekiyor ve bu kutucuklar, brüt kâr yüzdesini kullanarak ona kâr ile ilgili üst düzey bir genel bakış sağlıyor. Herhangi bir yönetici için brüt kâr yüzdesi eğilimi beklentinin altındaysa CFO, söz konusu durumu daha ayrıntılı olarak inceleyebiliyor.

![yöneticiler için GM%](media/sample-customer-profitability/power-bi-manager2.png)

- Carlos dışındaki tüm yöneticiler, satış hedeflerini zaten aştı. Ancak en fazla gerçek satışı Carlos yapmıştır.
- Brüt kâr yüzdesi en düşük yönetici Annelie ancak onun da Mart ayından bu yana istikrarlı bir artış yakaladığını görüyoruz.
- Diğer taraftan, Valery'nin brüt kâr yüzdesinde önemli ölçüde bir düşüş görülüyor.
- Andrew ise istikrarsız bir yıl geçirmiş gibi görünüyor.

## <a name="explore-the-dashboards-underlying-data"></a>Panodaki temel alınan verileri keşfedin
Bu panoda bir raporun ve bir Excel çalışma kitabının bağlantısını içeren kutucuklara sahiptir.

### <a name="open-the-excel-online-data-source"></a>Excel Online veri kaynağını açma
Bu panodaki "Hedef ve Gerçek" ile "Yıllara Göre Gelir Büyümesi" adlı iki kutucuk bir Excel çalışma kitabından sabitlenmiştir. Bu nedenle, bu kutucuklardan birini seçtiğinizde Power BI, veri kaynağını (bu durumda, Excel Online) açar.

![Excel online](media/sample-customer-profitability/power-bi-excel-online.png)

1. Excel'den sabitlenmiş kutucuklardan birini seçin. Excel Online, Power BI hizmetinde açılır.
2. Çalışma kitabında 3 sekme değerinde veri olduğuna dikkat edin. "Gelir" bölümünü açın.
3. Carlos’un neden henüz hedefine ulaşamadığına bakalım.  
    a. "Yönetici" kaydırıcısından **Carlos Grilo**’ı seçin.   
    b. Birinci PivotTable, Carlos’un en popüler ürünü Primus için gelirlerinin geçen yıla göre %152 azaldığını göstermektedir. Yıllara göre grafik ise ayların birçoğunda bütçe altında kaldığını göstermektedir.  

    ![PivotTable](media/sample-customer-profitability/power-bi-pivotchart.png)

    ![Carlos için sonuçlar](media/sample-customer-profitability/power-bi-carlos.png)

4. Araştırmaya devam edin ve ilgi çekici bir şeyler bulursanız sağ üst köşeden **Sabitle** ![sabitle simgesi](media/sample-customer-profitability/power-bi-excel-pin.png) öğesini seçerek [panoya sabitleyin](service-dashboard-pin-tile-from-excel.md).

5. Panoya geri dönmek için tarayıcınızın geri okunu kullanın.

### <a name="open-the-underlying-power-bi-report"></a>Temel alınan Power BI raporunu açın
Müşteri Karlılığı örnek panosundaki kutucuklarının büyük bölümü, temel alınan Müşteri Karlılığı örnek raporundan sabitlenmiştir.

1. Raporu Okuma görünümünde açmak için bu kutucuklardan birini seçin.

2. Raporda 3 sayfa vardır. Raporun en alt bölümündeki her sekme bir sayfaya karşılık gelir.

    ![alt kısımdaki 3 sekme](media/sample-customer-profitability/power-bi-report-tabs.png)

    * "Team Scorecard" sayfasında 5 yöneticinin performansına ve "müşterilerine" odaklanılmaktadır.
    * "Industry Margin Analysis" sayfasında kârlılık durumumuzu, bulunduğumuz sektörün tamamı ile karşılaştırmalı bir şekilde çözümlememizi sağlayacak bir yöntem sunulur.
    * "Executive Scorecard" sayfasında ise her yöneticimize ilişkin bir bakış sağlanır. Bunlar Cortana'da görüntülenmek üzere biçimlendirilmiştir.

### <a name="team-scorecard-page"></a>Team Scorecard sayfası
![Team scorecard rapor sayfası](media/sample-customer-profitability/customer2.png)

Ekip üyelerinden ikisine ayrıntılı olarak göz atıp ne gibi öngörüler elde edebileceğimize bakalım. Rapor sayfasını yalnızca Andrew ile ilgili veriler görüntülenecek şekilde filtrelemek için soldaki dilimleyicide Andrew'un adını seçin.

* Hızlı bir KPI edinmek için Andrew'un **Gelir Durumuna** (yeşil) bakın. Performansı iyi durumda.
* "Month ölçütüne göre Revenue % Variance" Alan grafiğine baktığımızda Şubat ayında yaşanan düşüş dışında Andrew'un oldukça iyi bir performans sergilediğini görüyoruz. Baskın olduğu bölge Doğu, 49 müşterisi var ve toplam 7 üründen 5 tanesi ile ilgileniyor. Brüt kâr yüzdesi en yüksek veya en düşük seviyede değil.
* "Month ölçütüne göre RevenueTY ve Revenue % Variance to Budget" grafiğinde kâr durumunun istikrarlı olduğu görülüyor. Ancak, bölge ağaç haritasında **Central**'ı filtrelediğinizde Andrew'un yalnızca Mart ayında ve sadece Indiana bölgesinden elde ettiğini görüyoruz. Amaçlanan bu muydu veya bu incelenmesi gereken bir durum mu?

Şimdi Valery'ye geçelim. Rapor sayfasını yalnızca Valery ile ilgili veriler görüntülenecek şekilde filtrelemek için dilimleyicide Valery'nin adını seçin.  
![Vaery Ushalov için dilim Yöneticisi](media/sample-customer-profitability/customer3.png)

* **RevenueTY Status** KPI'sinin kırmızı olduğuna dikkat edin. Bu durumun kesinlikle biraz daha incelenmesi gerekiyor.
* Gelir varyansına baktığımızda da endişelendirici bir tabloyla karşılaşıyoruz. Valery gelir marjlarını karşılamıyor.
* Valery'nin yalnızca 9 müşterisi var, 2 ürünle ilgileniyor ve neredeyse yalnızca Kuzey bölgesindeki müşterilerle çalışıyor. Ölçümlerinde görülen büyük dalgalanmalar tek bir bölgeyle çalışıyor olması ile açıklanabilir.
* Ağaç haritasında **Kuzey** karesi seçildiğinde Valery'nin Kuzey bölgesindeki brüt kârının toplam marjıyla tutarlı olduğu görülüyor.
* Diğer **Region** kareleri seçildiğinde ilgi çekici bir durumla karşılaşırız: brüt kâr yüzdesi %23 ila %79 arasında değişiyor ve gelir rakamları, Kuzey hariç tüm bölgelerde son derece mevsimsel.

Valery'nin düşük performansının altında yatan nedenleri bulmak için araştırmaya devam edin. Bölgelere, diğer departmanlara ve rapordaki bir sonraki sayfaya ("Industry Margin Analysis") bakın.

### <a name="industry-margin-analysis"></a>Industry Margin Analysis
Bu rapor sayfasında verilerin farklı bir dilimi sunulur. Burada sektörün tamamına ilişkin brüt kârı, segmentlere göre ayrılmış şekilde görüyoruz. CFO, eğilimler ve kârlılık ile ilgili çıkarımlar yapmasına yardımcı olması için şirket ve departman ölçümlerini sektör ölçümleriyle karşılaştırmak üzere bu sayfayı kullanır. "Month ve Executive Name ölçütlerine göre Gross Margin" alan grafiği ekibe özgü bir grafik olduğundan bu sayfada neden bulunduğunu merak etmiş olabilirsiniz. Bu grafik ile sayfayı departman yöneticisine göre filtreleyebiliyoruz.  
![Sektör marjı analizi rapor sayfası](media/sample-customer-profitability/customer6.png)

Kârlılık, sektörden sektöre nasıl bir değişiklik gösteriyor? Sektörlere göre ürün ve müşteri dağılımı nasıl gerçekleşiyor? Sol üst kısımda bir veya birden fazla sektör seçin. CPG sektörü ile başlayın. Filtreyi temizlemek için silgi simgesini seçin.

CFO, kabarcık grafiğindeki en büyük balonları görmeye çalışır. Gelir üzerinde en büyük etkiye sahip olanlar bunlardır. Alan grafiğinde adlarına tıklayarak sayfayı yöneticiye göre filtrelediğinde ise her bir yöneticinin sektör segmentine göre etkisini kolayca görebilir.

* Andrew'un etki alanının birçok farklı sektör segmentine yayıldığını ve brüt kâr yüzdesi (çoğunlukla olumlu anlamda) ile varyans yüzdesinin geniş çapta değişiklik gösterdiğini görüyoruz.
* Federal segmentine ve Gladius ürününe daha fazla odaklanmış olup az sayıda sektör segmentine yönelmiş olması dışında Annelie'nin grafiğinde de benzer bir durumla karşılaşıyoruz.
* Carlos'un Services segmentine net bir şekilde yöneldiğini ve iyi bir kâr yüzdesi yakaladığını görüyoruz. High Tech segmenti için varyans yüzdesini büyük oranda iyileştirmiş ve henüz acemisi olduğu Industrial segmentinde bütçeye kıyasla olağanüstü bir başarı göstermiş.
* Tina az sayıda segment ile çalışıyor ve en yüksek brüt kâr yüzdesine sahip ancak balonlarının genel olarak küçük boyutta olması, şirketin nihai kâr-zarar dengesi üzerindeki etkisinin minimum düzeyde olduğunu gösteriyor.
* Yalnızca tek bir üründen sorumlu olan Valery, yalnızca 5 sektör segmentinde çalışıyor. Sektör etkisi mevsimsel ancak balon boyutu her zaman büyük ve bu da şirketin nihai kâr-zarar dengesi üzerinde çok büyük bir etkiye sahip olduğunu gösteriyor. Sektör onun bu olumsuz performansını nasıl etkiliyor?

### <a name="executive-scorecard"></a>Executive Scorecard
Bu sayfa Cortana için bir Yanıt Kartı olarak biçimlendirilmiştir. Daha fazla bilgi edinmek için bkz. [Cortana için Yanıt Kartları oluşturma](service-cortana-answer-cards.md)

## <a name="dig-into-the-data-by-asking-questions-with-qa"></a>Soru-Cevap ile sorular sorarak verilerle ilgili ayrıntılara ulaşma
Bizim analizimiz için bu özellik, Valery'nin en çok hangi sektörden gelir elde ettiğini belirlememize yardımcı olabilir. Soru-Cevap'ı kullanalım.

1. **Raporu düzenle**'yi seçerek raporu Düzenleme görünümünde açın. Düzenleme görünümü yalnızca raporun "sahibiyseniz" kullanılabilir; bu özellik bazı durumlarda **oluşturucu** modu olarak adlandırılır. Bunun yerine, bu rapor sizinle paylaşılmışsa, raporu Düzenleme görünümünde açamazsınız.

2.  Üst menü çubuğundan **Soru sorun**’u seçerek Soru-Cevap soru kutusunu açın.

    ![Verileriniz hakkında soru sorun](media/sample-customer-profitability/power-bi-ask-question.png)

3. **Total revenue by industry for Valery** (Valery için sektörlere göre toplam gelir) yazın. Siz sorunuzu yazdıkça görselleştirmenin nasıl güncelleştirildiğine dikkat edin.

    ![soru kutusuna soru yazın](media/sample-customer-profitability/power-bi-qna.png)

   Valery'nin en çok geliri Distribution sektöründen elde ettiğini görüyoruz.

### <a name="dig-deeper-by-adding-filters"></a>Filtreler ekleyerek daha fazla ayrıntıya ulaşma
Şimdi, *Distribution* sektörünü yakından inceleyelim.  

1. "Sektör Marjı Analizi" rapor sayfasını açın.
2. Rapor sayfasında herhangi bir görselleştirmeyi seçmeden sağdaki filtre bölmesini genişletin (henüz genişletilmemişse). Filtreler bölmesinde yalnızca Sayfa düzeyi filtreleri görüntülenmelidir.  

   ![Sayfa düzeyi filtreleri](media/sample-customer-profitability/power-bi-filters.png)
3. **Industry** filtresini bulun ve listeyi genişletmek için oku seçin. Şimdi Distribution sektörü için bir sayfa filtresi ekleyelim. Öncelikle **Tümünü Seç** onay kutusunu temizleyerek tüm seçimleri kaldırın. Ardından yalnızca **Dağıtım**'ı seçin.  

   ![Dağıtım için filtre](media/sample-customer-profitability/customer7.png)
4. "Month ve Executive ölçütlerine göre Gross Margin" alan grafiğinde, yalnızca Valery ve Tina'nın bu sektörden müşterilerinin olduğunu ve Valery'nin bu sektör ile yalnızca Haziran ayından Kasım ayına kadar çalıştığını görüyoruz.   
5. "Month ve Executive ölçütüne göre Gross Margin" alan grafiği açıklamasında **Tina**'yı ve ardından **Valery**'yi seçin. Tina'nın "Product ölçütüne göre Total Revenue" yüzdesinin Valery'ye kıyasla gerçekten çok düşük olduğuna dikkat edin.
6. Gerçek geliri görmek için Soru-Cevap seçeneğini kullanarak **yöneticiye ve senaryoya göre dağıtım sektörü için toplam gelir** yazın.  

     ![çubuk grafiği görmek için soru kutusuna soru yazın](media/sample-customer-profitability/power-bi-qna2.png)

    Valery'nin performansını etkileyen unsurları anlamak için benzer şekilde diğer sektörleri de inceleyebilir ve hatta müşterileri de görsellerimize ekleyebiliriz.

Burası keşifler yapabileceğiniz güvenli bir ortamdır. Değişikliklerinizi kaydetmemeyi seçme konusunda her zaman özgürsünüz. Ancak, değişiklikleri kaydederseniz dilediğiniz zaman **Veri Al** bölümüne giderek bu örneğin yeni bir kopyasını edinebilirsiniz.

Ayrıca [sadece bu örneğe ilişkin veri kümesini (Excel çalışma kitabı) de indirebilirsiniz](http://go.microsoft.com/fwlink/?LinkId=529781).

## <a name="next-steps-connect-to-your-data"></a>Sonraki adımlar: Verilerinize bağlanma
Bu turda Power BI panolarının, Soru-Cevap özelliğinin ve raporların müşteri verileriyle ilgili olarak nasıl öngörüler sağlayabileceğini kavradığınızı umuyoruz. Şimdi sıra sizde, kendi verilerinize bağlanın. Power BI ile çok çeşitli veri kaynaklarına bağlanabilirsiniz. [Power BI ile çalışmaya başlama](service-get-started.md) hakkında daha fazla bilgi edinin.

[Power BI'daki Örneklere geri dönün](sample-datasets.md)  
