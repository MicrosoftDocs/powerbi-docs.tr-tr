---
title: "Power BI için Customer Profitability Sample: Tura katılın"
description: "Power BI için Customer Profitability Sample: Tura katılın"
services: powerbi
documentationcenter: 
author: amandacofsky
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/29/2017
ms.author: mihart
ms.openlocfilehash: 9a100b7d13c11a8bd066b72a570f45d0c2bc08be
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2017
---
# <a name="customer-profitability-sample-for-power-bi-take-a-tour"></a>Power BI için Customer Profitability Sample: Tura katılın
"Customer Profitability Sample" içerik paketinde, pazarlama malzemeleri üreten bir şirkete ilişkin pano, rapor ve veri kümesi bulunmaktadır. Bu pano, mali işlerden sorumlu bir genel müdür (CFO) tarafından, 5 departman yöneticisi (diğer adıyla idareciler), ürünler, müşteriler ve brüt kâr ile ilgili ana ölçümleri görme amacıyla oluşturulmuştur. CFO, kârlılığı etkileyen faktörleri bir bakışta görebiliyor.

Bu örnek, Power BI'ı işle ilgili veriler, raporlar ve panolarla birlikte nasıl kullanabileceğinizi gösteren serinin bir parçasıdır. Bunlar, anonim hale getirilen gerçek veriler olup obviEnce'tan ([www.obvience.com](http://www.obvience.com/)) alınmıştır.

Ayrıca [yalnızca bu örneğe ilişkin veri kümesini de (Excel çalışma kitabı) indirebilirsiniz](http://go.microsoft.com/fwlink/?LinkId=529781).  
![](media/sample-customer-profitability/power-bi-dash.png)

## <a name="what-is-our-dashboard-telling-us"></a>Panomuz bize ne anlatıyor?
### <a name="company-wide-dashboard-tiles"></a>Genel şirket durumu ile ilgili pano kutucukları
Bu kutucuklar, CFO'muza, önem verdiği üst düzey şirket ölçümlerine yönelik bir bakış sağlar.  CFO, ilginç bir bulguyla karşılaştığında bir kutucuğu seçip söz konusu verileri ayrıntılı olarak inceleyebilir.

1. Şirketimizin brüt kârı %42,5.
2. 80 müşterimiz var.
3. 5 farklı ürün satıyoruz.
4. Bütçemizdeki gelir varyansının (yüzde cinsinden) en düşük olduğu ayın Şubat, en yüksek olduğu ayın ise Mart olduğunu görüyoruz.
5. Gelirimizin çoğunu Doğu ve Kuzey bölgelerden elde ediyoruz. Brüt kârın bütçeyi hiçbir zaman aşmadığı ve ER-0 ile MA-0 için biraz daha fazla inceleme yapılması gerektiği görülüyor.
6. Yıl için toplam gelir bütçeye yakın.

### <a name="manager-specific-dashboard-tiles"></a>Yöneticiye özgü pano kutucukları
Bu kutucuklar ile bir ekip karnesi oluşturuluyor. CFO'nun, yöneticilerini takip etmesi gerekiyor ve bu kutucuklar, brüt kâr yüzdesini kullanarak ona kâr ile ilgili üst düzey bir genel bakış sağlıyor. Herhangi bir yönetici için brüt kâr yüzdesi eğilimi beklentinin altındaysa CFO, söz konusu durumu daha ayrıntılı olarak inceleyebiliyor.

Brüt kâr yüzdesi en düşük yönetici Annelie ancak onun da Mart ayından bu yana istikrarlı bir artış yakaladığını görüyoruz. Diğer taraftan, Valery'nin brüt kâr yüzdesinde önemli ölçüde bir düşüş görülüyor. Andrew ise istikrarsız bir yıl geçirmiş gibi görünüyor. Bağlantılı raporu açmak için, yöneticiye özgü kutucuklardan herhangi birine tıklayın. Raporda 3 sayfa bulunur ve ilk olarak "Industry Margin Analysis" sayfası açılır.

## <a name="explore-the-pages-in-the-report"></a>Rapordaki sayfaları inceleme
Raporumuzda 3 sayfa var:

* "Team Scorecard" sayfasında 5 yöneticinin performansına ve "müşterilerine" odaklanılmaktadır.
* "Industry Margin Analysis" sayfasında kârlılık durumumuzu, bulunduğumuz sektörün tamamı ile karşılaştırmalı bir şekilde çözümlememizi sağlayacak bir yöntem sunulur.
* "Executive Scorecard" sayfasında ise her yöneticimize ilişkin bir bakış sağlanır. Bunlar Cortana'da görüntülenmek üzere biçimlendirilmiştir.

### <a name="team-scorecard-page"></a>Team Scorecard sayfası
![](media/sample-customer-profitability/customer2.png)

Ekip üyelerinden ikisine ayrıntılı olarak göz atıp ne gibi öngörüler elde edebileceğimize bakalım. Rapor sayfasını yalnızca Andrew ile ilgili veriler görüntülenecek şekilde filtrelemek için soldaki dilimleyicide Andrew'un adını seçin.

* Hızlı bir KPI edinmek için Andrew'un **Gelir Durumuna** (yeşil) bakın. Performansı iyi durumda.
* "Month ölçütüne göre Revenue % Variance" Alan grafiğine baktığımızda Şubat ayında yaşanan düşüş dışında Andrew'un oldukça iyi bir performans sergilediğini görüyoruz. Baskın olduğu bölge Doğu, 49 müşterisi var ve toplam 7 üründen 5 tanesi ile ilgileniyor. Brüt kâr yüzdesi en yüksek veya en düşük seviyede değil.
* "Month ölçütüne göre RevenueTY ve Revenue % Variance to Budget" grafiğinde kâr durumunun istikrarlı olduğu görülüyor. Ancak, bölge ağaç haritasında **Central**'ı filtrelediğinizde Andrew'un yalnızca Mart ayında ve sadece Indiana bölgesinden elde ettiğini görüyoruz. Amaçlanan bu muydu veya bu incelenmesi gereken bir durum mu?

Şimdi Valery'ye geçelim. Rapor sayfasını yalnızca Valery ile ilgili veriler görüntülenecek şekilde filtrelemek için dilimleyicide Valery'nin adını seçin.  
![](media/sample-customer-profitability/customer3.png)

* **RevenueTY Status** KPI'sinin kırmızı olduğuna dikkat edin. Bu durumun kesinlikle biraz daha incelenmesi gerekiyor.
* Gelir varyansına baktığımızda da endişelendirici bir tabloyla karşılaşıyoruz. Valery gelir marjlarını karşılamıyor.
* Valery'nin yalnızca 9 müşterisi var, 2 ürünle ilgileniyor ve neredeyse yalnızca Kuzey bölgesindeki müşterilerle çalışıyor. Ölçümlerinde görülen büyük dalgalanmalar tek bir bölgeyle çalışıyor olması ile açıklanabilir.
* Ağaç haritasında **Kuzey** karesi seçildiğinde Valery'nin Kuzey bölgesindeki brüt kârının toplam marjıyla tutarlı olduğu görülüyor.
* Diğer **Region** kareleri seçildiğinde ilgi çekici bir durumla karşılaşırız: brüt kâr yüzdesi %23 ila %79 arasında değişiyor ve gelir rakamları, Kuzey hariç tüm bölgelerde son derece mevsimsel.

Valery'nin düşük performansının altında yatan nedenleri bulmak için araştırmaya devam edin. Bölgelere, diğer departmanlara ve rapordaki bir sonraki sayfaya ("Industry Margin Analysis") bakın.

### <a name="industry-margin-analysis"></a>Industry Margin Analysis
Bu rapor sayfasında verilerin farklı bir dilimi sunulur. Burada sektörün tamamına ilişkin brüt kârı, segmentlere göre ayrılmış şekilde görüyoruz. CFO, eğilimler ve kârlılık ile ilgili çıkarımlar yapmasına yardımcı olması için şirket ve departman ölçümlerini sektör ölçümleriyle karşılaştırmak üzere bu sayfayı kullanır. "Month ve Executive Name ölçütlerine göre Gross Margin" alan grafiği ekibe özgü bir grafik olduğundan bu sayfada neden bulunduğunu merak etmiş olabilirsiniz. Bu grafik ile sayfayı departman yöneticisine göre filtreleyebiliyoruz.  
![](media/sample-customer-profitability/customer6.png)

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

1. Panoya dönmek için üst gezinti çubuğunda **Power BI**'ı seçin.
2. Panonun üst tarafındaki Soru-Cevap soru kutusunu seçin.
   
    ![](media/sample-customer-profitability/customer4.png)
3. **Total revenue by industry for Valery** (Valery için sektörlere göre toplam gelir) yazın. Siz sorunuzu yazdıkça görselleştirmenin nasıl güncelleştirildiğine dikkat edin.
   
    ![](media/sample-customer-profitability/customer5.png)
   
   Valery'nin en çok geliri Distribution sektöründen elde ettiğini görüyoruz.

### <a name="dig-deeper-by-adding-filters"></a>Filtreler ekleyerek daha fazla ayrıntıya ulaşma
Şimdi, *Distribution* sektörünü yakından inceleyelim.  

1. Panoya dönün ve Andrew'un Brüt Kâr Eğilimini gösteren alan grafiğini seçin. Bu işlemin ardından raporun "Industry Margin Analysis" sayfası açılır.
2. Rapor sayfasında herhangi bir görselleştirmeyi seçmeden sağdaki filtre bölmesini genişletin. Filtreler bölmesinde yalnızca Sayfa düzeyi filtreleri görüntülenmelidir.  
   
   ![](media/sample-customer-profitability/power-bi-filters.png)
3. **Industry** filtresini bulun ve listeyi genişletmek için oku seçin. Şimdi Distribution sektörü için bir sayfa filtresi ekleyelim. Öncelikle **Tümünü Seç** onay kutusunu temizleyerek tüm seçimleri kaldırın. Ardından, **Distribution**'ı seçin.  
   
   ![](media/sample-customer-profitability/customer7.png)
4. "Month ve Executive ölçütlerine göre Gross Margin" alan grafiğinde, yalnızca Valery ve Tina'nın bu sektörden müşterilerinin olduğunu ve Valery'nin bu sektör ile yalnızca Haziran ayından Kasım ayına kadar çalıştığını görüyoruz.   
5. "Month ve Executive ölçütüne göre Gross Margin" alan grafiği açıklamasında **Tina**'yı ve ardından **Valery**'yi seçin. Tina'nın "Product ölçütüne göre Total Revenue" yüzdesinin Valery'ye kıyasla gerçekten çok düşük olduğuna dikkat edin. 
6. Mevcut geliri görmek için panoya geri dönün ve Soru-Cevap'ı kullanarak **total revenue for distribution by scenario by executive** (yöneticiye ve senaryoya göre dağıtım sektörü için toplam gelir) yazın.  
   
   ![](media/sample-customer-profitability/customer8.png)

Valery'nin performansını etkileyen unsurları anlamak için benzer şekilde diğer sektörleri de inceleyebilir ve hatta müşterileri de görsellerimize ekleyebiliriz.

Burası keşifler yapabileceğiniz güvenli bir ortamdır. Değişiklikleri kaydetmeme seçeneğiniz her zaman mevcuttur. Ancak, değişiklikleri kaydederseniz istediğiniz zaman **Veri Al** bölümüne giderek bu örneğin yeni bir kopyasını edinebilirsiniz.

## <a name="next-steps-connect-to-your-data"></a>Sonraki adımlar: Verilerinize bağlanma
Bu turda Power BI panolarının, Soru-Cevap özelliğinin ve raporların müşteri verileriyle ilgili olarak nasıl öngörüler sağlayabileceğini kavradığınızı umuyoruz. Şimdi sıra sizde, kendi verilerinize bağlanın. Power BI sayesinde çok çeşitli veri kaynaklarına bağlanabilirsiniz. [Power BI ile çalışmaya başlama](service-get-started.md) hakkında daha fazla bilgi edinin.

[Power BI'daki Örneklere geri dönün](sample-datasets.md)  

