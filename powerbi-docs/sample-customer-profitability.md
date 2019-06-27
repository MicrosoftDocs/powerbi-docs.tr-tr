---
title: 'Power BI için Müşteri Kârlılığı Örneği: Tura katılın'
description: 'Power BI için Müşteri Kârlılığı Örneği: Tura katılın'
author: maggiesMSFT
manager: kfile
ms.reviewer: amac
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/11/2019
ms.author: maggies
LocalizationGroup: Samples
ms.openlocfilehash: 2b89125cd2ad45bdad18bd198385e1117b5e3f16
ms.sourcegitcommit: 69a0e340b1bff5cbe42293eed5daaccfff16d40a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/13/2019
ms.locfileid: "67039469"
---
# <a name="customer-profitability-sample-for-power-bi-take-a-tour"></a>Power BI için Müşteri Kârlılığı Örneği: Tura katılın

## <a name="overview-of-the-customer-profitability-sample"></a>Müşteri Karlılığı örneğine genel bakış
Müşteri Kârlılığı Örneği içerik paketinde, pazarlama malzemeleri üreten bir şirkete ilişkin pano, rapor ve veri kümesi bulunmaktadır. Bu pano, mali işlerden sorumlu bir genel müdür (CFO) tarafından, beş departman yöneticisi (idareciler), ürünler, müşteriler ve brüt kâr ile ilgili ana ölçümleri görme amacıyla oluşturulmuştur. CFO, kârlılığı etkileyen faktörleri bir bakışta görebiliyor.

![Power BI panosu](media/sample-customer-profitability/power-bi-dash.png)

Bu örnek, Power BI'ı işle ilgili veriler, raporlar ve panolarla birlikte nasıl kullanabileceğinizi gösteren serinin bir parçasıdır. Bu örnek obviEnce'ten ([www.obvience.com](http://www.obvience.com/)) alınan, anonimleştirilmiş gerçek verilerle oluşturulmuştur. Veriler çeşitli biçimlerde sunulur: içerik paketi/uygulama, Excel çalışma kitabı veya .pbix Power BI Desktop dosyası. Bkz. [Power BI Örnekleri](sample-datasets.md).

## <a name="prerequisites"></a>Önkoşullar
Birlikte ilerlemek ister misiniz? Bu öğreticide, Power BI hizmeti ve Müşteri Karlılığı Örneği içerik paketi kullanılır. Rapor deneyimleri son derece benzer olduğundan, Power BI Desktop ve örnek .pbix dosyasını kullanarak da örneği takip edebilirsiniz. İçerik paketine ve .pbix dosyasına bağlanma yönergeleri aşağıdaki bölümde açıklanmıştır.

### <a name="get-the-content-pack-for-this-sample"></a>Bu örneğe ilişkin içerik paketini edinme

1. Power BI hizmetini açın (app.powerbi.com), oturum açın ve örneği kaydetmek istediğiniz çalışma alanını açın.

2. Sol alt köşedeki **Veri Al**'ı seçin.

    ![Veri al](media/sample-datasets/power-bi-get-data.png)
3. Görüntülenen **Veri Al** sayfasında **Örnekler**'i seçin.

4. **Müşteri Kârlılığı Örneği**'ni ve ardından **Bağlan**'ı seçin.  

   ![Veri al](media/sample-customer-profitability/get-supplier-sample.png)
5. Power BI, içerik paketini içeri aktarır ve ardından geçerli çalışma alanınıza yeni bir pano, rapor ve veri kümesi ekler.

   ![Müşteri Kârlılığı Örneği girdisi](media/sample-customer-profitability/customer-profitability-sample-entry.png)

### <a name="get-the-pbix-file-for-this-sample"></a>Bu örneğe ilişkin .pbix dosyasını edinme

Alternatif olarak, [Müşteri Kârlılığı Örneğini](http://download.microsoft.com/download/6/A/9/6A93FD6E-CBA5-40BD-B42E-4DCAE8CDD059/Customer%20Profitability%20Sample%20PBIX.pbix) bir .pbix dosyası olarak indirebilirsiniz. Bu dosya biçimi, Power BI Desktop ile kullanım için tasarlanmıştır.


### <a name="get-the-excel-workbook-for-this-sample"></a>Bu örneğe ilişkin Excel çalışma kitabını edinme

Bu örnekte kullanılan veri kaynağını görüntülemek isterseniz, [Excel çalışma kitabı](http://go.microsoft.com/fwlink/?LinkId=529781) olarak da bulabilirsiniz. Çalışma kitabı, görüntüleyebileceğiniz ve değiştirebileceğiniz Power View sayfaları içerir. Ham verileri görmek için Veri Çözümlemesi eklentilerini etkinleştirin, sonra da **Power Pivot > Yönet**'e seçin. Power View ve Power Pivot eklentilerini etkinleştirme ayrıntıları için bkz. [Excel'in içinden Excel örneklerini gözden geçirme](sample-datasets.md#optional-take-a-look-at-the-excel-samples-from-inside-excel-itself).



## <a name="what-is-our-dashboard-telling-us"></a>Panomuz bize ne anlatıyor?

Örneği kaydettiğiniz çalışma alanında Müşteri Kârlılığı panosunu bulun ve seçin:

![Müşteri Kârlılığı örneğine ilişkin pano](media/sample-customer-profitability/power-bi-dash.png)

### <a name="company-wide-dashboard-tiles"></a>Genel şirket durumu ile ilgili pano kutucukları
1. Power BI hizmetinde panoyu açın. Bu pano kutucukları CFO'muza, önem verdiği üst düzey şirket ölçümlerine yönelik bir bakış sağlar. İlginç bir bulguyla karşılaştığında bir kutucuğu seçip söz konusu verileri ayrıntılı olarak inceleyebilir.

2. Panonun sol tarafındaki kutucukları gözden geçirin.

    ![Yöneticiler için kutucuklar](media/sample-customer-profitability/power-bi-manager.png)

- Şirketin brüt kârı %42,5.
- 80 müşterisi var.
- Beş farklı ürün satıyor.
- Bütçesindeki gelir varyansının (yüzde cinsinden) en düşük olduğu ayın Şubat, en yüksek olduğu ayın ise Mart olduğu görülüyor.
- Gelirimizin çoğunu doğu ve kuzey bölgelerden elde ediyoruz. Brüt kâr bütçeyi hiçbir zaman aşmıyor ve ER-0 ile MA-0 iş birimleri için biraz daha inceleme yapılması gerekiyor.
- Yıl için toplam gelir bütçeye yakın.


### <a name="manager-specific-dashboard-tiles"></a>Yöneticiye özgü pano kutucukları
Panonun sağ tarafındaki kutucuklar ise bir ekip puan kartı sağlar. CFO'nun, yöneticilerini takip etmesi gerekiyor ve bu kutucuklar, brüt kâr yüzdesini kullanarak ona kâr ile ilgili üst düzey bir genel bakış sağlıyor. Herhangi bir yönetici için brüt kâr yüzdesi eğilimi beklentinin altındaysa CFO, söz konusu durumu daha ayrıntılı olarak inceleyebiliyor.

![yöneticiler için GM%](media/sample-customer-profitability/power-bi-manager2.png)

Yöneticiye özgü pano kutucuklarını analiz ederek aşağıdaki gözlemleri yapabiliriz:

- Carlos dışındaki tüm yöneticiler, satış hedeflerini zaten aştı. Öte yandan en fazla gerçek satışı Carlos yapmıştır.
- Brüt kâr yüzdesi en düşük yönetici Annelie ancak onun da Mart ayından bu yana istikrarlı bir artış yakaladığını görüyoruz.
- Diğer taraftan, Valery'nin brüt kâr yüzdesinde önemli ölçüde bir düşüş görülüyor.
- Andrew istikrarsız bir yıl geçirmiş.

## <a name="explore-the-dashboards-underlying-data"></a>Panodaki temel alınan verileri keşfedin
Bu panoda bir raporun ve bir Excel çalışma kitabının bağlantısını içeren kutucuklara sahiptir.

### <a name="open-the-excel-online-data-source"></a>Excel Online veri kaynağını açma
Bu panodaki **Hedef ve Gerçek** ile **Yıllara Göre Gelir Büyümesi** adlı iki kutucuk bir Excel çalışma kitabından sabitlenmiştir. Bu kutucuklardan birini seçtiğinizde Power BI veri kaynağını (bu durumda, Excel Online) açar.

![Excel online](media/sample-customer-profitability/power-bi-excel-online.png)

1. Excel'den sabitlenmiş kutucuklardan birini seçin. Excel Online, Power BI hizmetinde açılır.
2. Çalışma kitabında üç sekme değerinde veri olduğuna dikkat edin. **Gelir** bölümünü açın.
3. Carlos’un neden henüz hedefine ulaşamadığına bakalım:  
    a. **Yönetici** kaydırıcısından **Carlos Grilo**’yu seçin.   
    b. Birinci PivotTable, Carlos’un en popüler ürünü Primus için gelir artışının geçen yıla göre %152 gerilediğini göstermektedir. Yıllara göre Gelir Varyansı grafiği ise ayların birçoğunda bütçe altında kaldığını göstermektedir.  

    ![PivotTable](media/sample-customer-profitability/power-bi-pivotchart.png)

    ![Carlos için sonuçlar](media/sample-customer-profitability/power-bi-carlos.png)

4. Keşfetmeye devam edin. İlgi çekici bir şeyler bulursanız sağ üst köşeden **Sabitle** ![sabitle simgesi](media/sample-customer-profitability/power-bi-excel-pin.png) öğesini seçerek [panoya sabitleyin](service-dashboard-pin-tile-from-excel.md).

5. Panoya geri dönmek için tarayıcınızın geri okunu kullanın.

### <a name="open-the-underlying-power-bi-report"></a>Temel alınan Power BI raporunu açın
Müşteri Kârlılığı örnek panosundaki kutucuklarının birçoğu, temel alınan Müşteri Kârlılığı örnek raporundan sabitlenmiştir.

1. Raporu Okuma görünümünde açmak için bu kutucuklardan birini seçin.

   Kutucuk Soru-Cevap içinde oluşturulduysa, kutucuğun seçilmesi Soru-Cevap penceresini açar. Panoya dönmek için **Soru-Cevap'tan Çık**'ı seçin ve farklı bir kutucuk deneyin.

2. Raporun üç sayfası vardır. Raporun en altındaki her sekme farklı bir sayfaya karşılık gelir.

    ![Alt kısımdaki üç sekme](media/sample-customer-profitability/power-bi-report-tabs.png)

    * **Team Scorecard** sayfasında 5 yöneticinin performansına ve müşterilerine odaklanılmaktadır.
    * **Industry Margin Analysis** sayfasında kârlılık durumunu, sektörün tamamı ile karşılaştırmalı bir şekilde çözümlememizi sağlayacak bir yöntem sunulur.
    * **Executive Scorecard** sayfasında ise her yöneticiye ilişkin bir bakış sağlanır. Bunlar Cortana'da görüntülenmek üzere biçimlendirilmiştir.

### <a name="team-scorecard-page"></a>Team Scorecard sayfası
![Team scorecard rapor sayfası](media/sample-customer-profitability/customer2.png)

Ekip üyelerinden ikisine ayrıntılı olarak göz atıp ne gibi öngörüler elde edebileceğimize bakalım. Rapor sayfasını yalnızca Andrew ile ilgili veriler görüntülenecek şekilde filtrelemek için soldaki **Executive** kutusunda Andrew'un adını seçin.

* Hızlı bir KPI için Andrew’un **Revenue Status (Total Year)** değerine bakın; yeşil renkte olması iyi performans gösterdiği anlamına geliyor.
* **Revenue % Variance to Budget by Month and Executive** grafiğinde, Şubat'ta yaşanan düşüş dışında Andrew'un genelde iyi performans sergilediği gösteriliyor. Baskın olduğu bölge doğu bölgesi, 49 müşterisi var ve toplam 7 üründen 5 tanesi ile ilgileniyor. Brüt kâr yüzdesi en yüksek veya en düşük yüzde değil.
* **RevenueTY and Revenue % Var to Budget by Month** grafiği kararlı düzgün bir kâr gösteriyor. Öte yandan, bölge ağaç haritasında **Central** karesini seçip filtrelerseniz Andrew'un yalnızca Mart ayında ve Indiana'da gelir elde ettiğini fark edeceksiniz. Amaçlanan bu muydu yoksa bu incelenmesi gereken bir durum mu?

Şimdi Valery'ye geçelim. Rapor sayfasını yalnızca Valery ile ilgili veriler görüntülenecek şekilde filtrelemek için **Yönetici** kutusunda Valery'nin adını seçin. 

![Valery'nin verileri](media/sample-customer-profitability/customer3.png)

* **Revenue Status (Total Year)** KPI'sinin kırmızı olduğuna dikkat edin. Bu öğenin kesinlikle biraz daha incelenmesi gerekiyor.
* Gelir varyansına baktığımızda da endişe verici bir tabloyla karşılaşıyoruz. Valery gelir marjlarını karşılamıyor.
* Valery'nin yalnızca dokuz müşterisi var, iki ürünle ilgileniyor ve neredeyse yalnızca kuzey bölgesindeki müşterilerle çalışıyor. Ölçümlerinde görülen büyük dalgalanmalar tek bir bölgeyle çalışıyor olması ile açıklanabilir.
* Ağaç haritasında **North** karesini seçerseniz Valery'nin kuzey bölgesindeki brüt kârının toplam marjıyla tutarlı olduğu görülüyor.
* Diğer **Total Revenue by Region** karelerinin seçilmesi ilginç bir durum ortaya koyuyor: Brüt Kâr oranı %23 ile %79 arasında değişiyor. Kuzey bölgesi dışındaki tüm bölgelerde gelir rakamları son derece mevsimsel.

Valery'nin düşük performansının altında yatan nedenleri bulmak için araştırmaya devam edin. Bölgelere, diğer departmanlara ve rapordaki bir sonraki sayfaya bakın: **Sektör Marjı Analizi**.

### <a name="industry-margin-analysis"></a>Sektör Marjı Analizi
Bu rapor sayfasında verilerin farklı bir dilimi sunulur. Burada sektörün tamamına ilişkin brüt kârı, segmentlere göre ayrılmış şekilde görüyoruz. CFO, eğilimler ve kârlılık ile ilgili çıkarımlar yapmasına yardımcı olması için şirket ve departman ölçümlerini sektör ölçümleriyle karşılaştırmak üzere bu sayfayı kullanır. **Gross Margin % by Month and Executive** grafiği ekibe özgü bir grafik olduğundan bu sayfada neden bulunduğunu merak etmiş olabilirsiniz. Bu grafik ile sayfayı departman yöneticisine göre filtreleyebiliyoruz.  

![Sektör marjı analizi rapor sayfası](media/sample-customer-profitability/customer6.png)

Kârlılık, sektörden sektöre nasıl bir değişiklik gösteriyor? Sektörlere göre ürün ve müşteri dağılımı nasıl gerçekleşiyor? Bu soruları yanıtlamak için sol üst kısımdan bir veya birden çok sektör seçin (CPG sektörüyle başlayın). Filtreyi temizlemek için silgi simgesini seçin.

Kabarcık grafiğinde (**Revenue Var % to Budget, GM%, and RevenueTY by Industry**) CFO en büyük kabarcıklara bakıyor çünkü gelir üzerinde en büyük etkiye sahip olanlar bunlar. Sektör segmentine göre her yöneticinin etkisini kolayca görmek için alan grafiğinde her yöneticinin adına tıklayarak sayfayı filtreleyin.

* Andrew'un etki alanının birçok farklı sektör segmentine yayıldığını ve brüt kâr yüzdesi (çoğunlukla olumlu anlamda) ile varyans yüzdesinin geniş çapta değişiklik gösterdiğini görüyoruz.
* Federal segmentine ve Gladius ürününe daha fazla odaklanmış olup az sayıda sektör segmentine yönelmiş olması dışında Annelie'nin grafiğinde de benzer bir durumla karşılaşıyoruz.
* Carlos'un Services segmentine net bir şekilde yöneldiğini ve iyi bir kâr yüzdesi yakaladığını görüyoruz. High Tech segmenti için varyans yüzdesini büyük oranda iyileştirmiş ve henüz acemisi olduğu Industrial segmentinde bütçeye kıyasla olağanüstü bir başarı göstermiş.
* Tina az sayıda segment ile çalışıyor ve en yüksek brüt kâr yüzdesine sahip ancak balonlarının genel olarak küçük boyutta olması, şirketin nihai kâr-zarar dengesi üzerindeki etkisinin minimum düzeyde olduğunu gösteriyor.
* Tek bir üründen sorumlu olan Valery, yalnızca beş sektör segmentinde çalışıyor. Sektör etkisi mevsimsel ancak balon boyutu her zaman büyük ve bu da şirketin nihai kâr-zarar dengesi üzerinde çok büyük bir etkiye sahip olduğunu gösteriyor. Sektör segmentleri onun bu olumsuz performansını nasıl etkiliyor?

### <a name="executive-scorecard"></a>Yönetim Puan Kartı
Bu sayfa Cortana için bir Cortana yanıt sayfası olarak biçimlendirilmiştir. Daha fazla bilgi edinmek için bkz. [Cortana için özel yanıt sayfası oluşturma](service-cortana-answer-cards.md).

## <a name="dig-into-the-data-by-asking-questions-with-qa"></a>Soru-Cevap ile sorular sorarak verilerle ilgili ayrıntılara ulaşma
Bizim analizimiz için bu özellik, Valery'nin en çok hangi sektörden gelir elde ettiğini belirlememize yardımcı olabilir. Soru-Cevap'ı kullanalım.

1. **Raporu düzenle**'yi seçerek raporu Düzenleme görünümünde açın. Düzenleme görünümü ancak raporun sahibi olduğunuzda kullanılabilir. Bu görünüm bazen **oluşturucu** modu olarak da adlandırılır. Bunun yerine bu rapor yalnızca sizinle paylaşılmışsa, raporu Düzenleme görünümünde açamazsınız.

2.  Üst menü çubuğundan **Soru sorun**’u seçerek Soru-Cevap soru kutusunu açın.

    ![Verileriniz hakkında soru sorun](media/sample-customer-profitability/power-bi-ask-question.png)

3. *Valery Ushakov için sektörlere göre toplam gelir* yazın. Siz sorunuzu yazdıkça görselleştirmenin nasıl güncelleştirildiğine dikkat edin.

    ![soru kutusuna soru yazın](media/sample-customer-profitability/power-bi-qna.png)

   Gördüğünüz gibi, Valery'nin en yüksek gelir alanı Distribution sektörüdür.

### <a name="dig-deeper-by-adding-filters"></a>Filtreler ekleyerek daha fazla ayrıntıya ulaşma
Şimdi Distribution sektörünü yakından inceleyelim.  

1. **Sektör Marjı Analizi** rapor sayfasını açın.
2. Rapor sayfasında herhangi bir görselleştirmeyi seçmeden sağdaki filtre bölmesini genişletin (henüz genişletilmemişse). **Filtreler** bölmesinde yalnızca **Sayfa düzeyi filtreleri** görüntülenmelidir.  

   ![Sayfa düzeyi filtreleri](media/sample-customer-profitability/power-bi-filters.png)
3. **Industry** filtresini bulun ve listeyi genişletmek için oku seçin. Şimdi Distribution sektörü için bir sayfa filtresi ekleyelim. Öncelikle **Tümünü Seç** onay kutusunu temizleyerek tüm seçimleri kaldırın. Ardından yalnızca **Dağıtım**'ı seçin.  

   ![Dağıtım için filtre](media/sample-customer-profitability/customer7.png)
4. **Gross Margin % by Month and Executive** grafiğinde, yalnızca Valery ve Tina'nın bu sektörden müşterilerinin olduğunu ve Valery'nin bu sektör ile yalnızca Haziran ayından Kasım ayına kadar çalıştığını görüyoruz.   
5. **Gross Margin by Month and Executive** grafiğinin göstergesinde **Tina**'yı ve ardından **Valery**'yi seçin. Tina'nın **Total Revenue by Product** grafiğindeki yüzdesinin Valery'ye kıyasla gerçekten çok düşük olduğuna dikkat edin.
6. Gerçek geliri görmek için Soru-Cevap seçeneğini kullanarak *yöneticiye ve senaryoya göre dağıtım sektörü için toplam gelir* girin.  

     ![çubuk grafiği görmek için soru kutusuna soru yazın](media/sample-customer-profitability/power-bi-qna2.png)

    Valery'nin performansını etkileyen unsurları anlamak için benzer şekilde diğer sektörleri de inceleyebilir ve hatta müşterileri de görsellerimize ekleyebiliriz.

Burası istediğiniz değişikliği yapabileceğiniz bir ortamdır. Değişikliklerinizi kaydetmemeyi seçme konusunda her zaman özgürsünüz. Değişikliklerinizi kaydetseniz bile, dilediğiniz zaman **Veri Al**'ı seçip bu örneğin yeni bir kopyasını oluşturabilirsiniz.

Ayrıca [sadece bu örneğe ilişkin veri kümesini (Excel çalışma kitabı) de indirebilirsiniz](http://go.microsoft.com/fwlink/?LinkId=529781).

## <a name="next-steps-connect-to-your-data"></a>Sonraki adımlar: Verilerinize bağlanma
Bu turda Power BI panolarının, Soru-Cevap özelliğinin ve raporların müşteri verileriyle ilgili olarak nasıl öngörüler sağlayabileceğini kavradığınızı umuyoruz. Artık siz de kendi verilerinize bağlanarak çalışmaya başlayabilirsiniz. Power BI ile çok çeşitli veri kaynaklarına bağlanabilirsiniz. [Power BI ile çalışmaya başlama](service-get-started.md) hakkında daha fazla bilgi edinin.

[Power BI örnekleri](sample-datasets.md)  
