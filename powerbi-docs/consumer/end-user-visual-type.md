---
title: Tüketiciler için Power bı'da görsel türleri
description: Power BI hizmetinde görsel türleri
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 05/14/2019
ms.author: mihart
LocalizationGroup: Consumer
ms.openlocfilehash: acee7e78a19986a0f83e13836ba6d77f7c35fdce
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65711546"
---
# <a name="visual-types-in-power-bi"></a>Power bı'da görsel türleri
Görseller, raporlar, panolar, uygulamaları ve soru- cevap özelliğinde bulabilirsiniz Power BI ile görsel bu tür bazı paketlenir ve bazı *özel görseller*. Özel görseller Power BI’ın dışında ve *rapor tasarımcılarının* Power BI raporlarına, panolarına ve uygulamalarına ekleyebilecekleri şekilde oluşturulur. 

Bu makalede, Power BI ile paketlenmiş görsel bir genel bakıştır.  Bu, en sık karşılaşabileceğiniz görseller vardır. 

> [!NOTE]
> Özel görseller hakkında daha fazla bilgi edinmek için bunları [Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps?product=power-bi-visuals)’un **Power BI görselleri** bölümünde arayın. Her görsel için bir açıklama, oluşturucu bilgileri ve ekran görüntüsü veya video bulabilirsiniz. 

## <a name="list-of-visuals-available-in-power-bi"></a>Power BI'da kullanılabilen görseller listesi
Bu görsellerin tümünü bulunabilir Power BI uygulamaları, panoları, raporları ve [soru- cevap içinde belirtilen](end-user-q-and-a.md). Görsellerle etkileşim öğrenmek için bkz. [görsellerde raporlar, panolar ve uygulamalar ile etkileşimde bulunma](end-user-visualizations.md)

### <a name="area-charts-basic-layered-and-stacked"></a>Alan grafikleri: Basit (Katmanlı) ve Yığılmış
![alan grafiği](media/end-user-visual-type/basic-area-map-small.png)

Basit alan grafiği için çizgi grafik temel alınır ve eksen ile çizgi arasındaki alan doldurulur. Alan grafikleri, zaman içindeki değişimin büyüklüğünü vurgular ve bir eğilime ilişkin toplam değere dikkat çekmek için kullanılabilir. Örneğin, zaman içindeki kârı gösteren veriler, bir alan grafiğinde toplam kârı vurgulayacak şekilde gösterilebilir.

### <a name="bar-and-column-charts"></a>Çubuk grafikler ve sütun grafikleri
![sütun grafik](media/end-user-visual-type/pbi-nancy-viz-bar.png)

 ![çubuk grafik](media/end-user-visual-type/pbi-nancy-viz-col.png)

Belirli bir değere farklı kategorilerde bakmak için standart olarak çubuk grafikler kullanılır.

### <a name="cards-single-number"></a>Kartlar: Tek sayı
![tek sayı kartı](media/end-user-visual-type/pbi-nancy-viz-card.png)

Tek sayı kartları tek bir olguyu, tek bir veri noktasını görüntüler. Bazen Power BI panonuzda veya raporunuzda izlemek istediğiniz en önemli şey (örneğin, toplam satış, yıldan yıla pazar payı veya toplam fırsat) tek bir sayı olabilir.  

### <a name="cards-multi-row"></a>Kartlar: Çok satırlı
![çok satırlı kart](media/end-user-visual-type/multi-row-card.png)

Çok satırlı kartlar, satır başına bir tane olmak üzere bir veya birden çok veri noktasını görüntüler.


### <a name="combo-charts"></a>Birleşik haritalar
![birleşik harita](media/end-user-visual-type/combo-small.png)

Birleşik haritada sütun grafikleri ile çizgi grafikler birleştirilir. Bu iki grafiği tek bir görselleştirmede birleştirdiğinizde verileri daha hızlı karşılaştırabilirsiniz. Birleşik haritalarda bir veya iki Y ekseni olabilir; bu nedenle yakından bakın. 

Birleşik haritalar aşağıdaki durumlarda harika bir seçimdir:
- aynı X eksenine sahip bir çizgi grafiğiniz ve sütun grafiğiniz olduğunda.
- farklı değer aralıklarına sahip birden fazla ölçüyü karşılaştırmak istediğinizde
- bir görseldeki iki ölçü arasındaki bağıntıyı göstermek için
- bir ölçünün, başka bir ölçü tarafından tanımlanan hedefi karşılayıp karşılamadığını kontrol etmek istediğinizde.
- tuval alanını tasarruflu kullanmak istediğinizde

### <a name="doughnut-charts"></a>Halka grafikler
![halka grafik](media/end-user-visual-type/donut-small.png)

Halka grafikler, pasta grafiklerine benzer.  Parçaların bütünle ilişkisini gösterir. Tek fark ortasının boş ve bir etiket veya simge yerleştirmeye müsait olmasıdır.

### <a name="funnel-charts"></a>Huni grafikler
![huni grafik](media/end-user-visual-type/pbi-nancy-viz-funnel.png)

Huniler, aşamalardan oluşan bir işlemin görselleştirilmesine yardımcı olur ve öğe akışı bir aşamadan diğerine sıralı olarak yapılır.  Fırsat ile başlayan ve alımın tamamlanmasıyla biten bir satış işlemi buna örnektir.

Örneğin, şu aşamalarda müşterileri izleyen bir satış hunisi: Müşteri Adayı > Nitelikli Müşteri Adayı > Olası Müşteri > Sözleşme > Kapanış. Huninin şekli ilk bakışta takip ettiğiniz sürecin ilerleme durumu hakkında bilgi verir.
Huninin her aşaması, toplamın belirli bir yüzdesini temsil eder. Bu nedenle çoğu durumda huni grafik bir huniye benzer. İlk aşama en büyüktür ve sonraki her aşama da bir öncekinden küçüktür. Armut şeklindeki huni de kullanışlıdır. Süreçte bir sorun olduğunu belirtebilir. Ancak genellikle ilk aşama olan "giriş" aşaması en büyük olandır.

Huni grafikler aşağıdaki durumlarda harika bir seçimdir:
- veriler sıralı olduğunda ve en az 4 aşama boyunca ilerlediğinde.
- ilk aşamadaki "öğelerin" sayısının son aşamadaki sayıdan büyük olması beklendiğinde.
- potansiyeli (gelir/satış/anlaşma vs.) aşamalara göre hesaplamak için.
- dönüşüm ve elde tutma oranlarını hesaplayıp takip etmek için.
- doğrusal bir süreçteki sorunlu noktaları ortaya çıkarmak için.
- alışveriş sepeti iş akışını takip etmek için.
- tıklama ile yapılan reklam/pazarlama kampanyalarının ilerleme ve başarı durumunu takip etmek için.

### <a name="gauge-charts"></a>Ölçek grafikleri
![ölçek grafiği](media/end-user-visual-type/gauge-m.png)

Radyal ölçerler dairesel bir yay içerir ve belirli bir hedefe/KPI'ye yönelik ilerlemeyi ölçen tek bir değer görüntüler. Hedef veya hedef değer çizgi (iğne) ile gösterilir. Hedefe yönelik ilerleme gölgelendirme ile gösterilir. İlerlemeyi gösteren değer ise yayın içinde kalın olarak gösterilir. Olası tüm değerler, minimumdan (en soldaki değer) başlayıp maksimumda (en sağdaki değer) sonlanacak şekilde yay boyunca eşit olarak dağılır.

Yukarıdaki örnekte, Satış ekibimizin aylık ortalama satışlarını izleyen bir araba satıcısı olduğumuzu varsayıyoruz. Hedefimiz olan 140 değeri siyah bir iğneyle gösterilmektedir. Mümkün olan minimum ortalama satışı 0, maksimum ortalama satışı ise 200 olarak belirledik. Mavi gölge, bu ay ortalama yaklaşık 120 satışa ulaştığımızı gösteriyor. Şanslıyız ki hedefimize ulaşmak için bir haftamız daha var.

Radial ölçerler şunlar için harika bir seçimdir:
- bir hedefe yönelik ilerlemeyi göstermek
- KPI gibi bir yüzde değerini göstermek
- tek bir ölçünün durumunu göstermek
- hızla taranabilen ve anlaşılabilen bilgiler görüntülemek

 ### <a name="key-influencers-chart"></a>Ana etmenler grafiği
![ana etmen](media/end-user-visual-type/power-bi-influencer.png)

Ana etmenler grafiği, seçili bir sonuç veya değere en çok katkıda bulunanları gösterir.

Bir ana ölçümü etkileyen faktörleri anlamak için ana etmenlerden faydalanabilirsiniz. Örneğin, *müşterilerin ikinci siparişi vermelerindeki etmenler *veya* satışların geçen Haziran ayında çok yüksek olmasının nedenleri*. 

### <a name="kpis"></a>KPI'ler
![kpi](media/end-user-visual-type/power-bi-kpi.png)

Ana Performans Göstergesi (KPI), ölçülebilen bir hedefe yönelik ilerlemeyi gösteren bir görsel ipucudur. 

KPI'ler şunlar için harika seçimdir:
- ilerlemeyi ölçme (ne kadar geride ne kadar ilerideyim?)
- bir hedef için kalan mesafeyi ölçme (ne kadar yakın ne kadar uzağım?)

### <a name="line-charts"></a>Çizgi grafikler
![çizgi grafik](media/end-user-visual-type/pbi-nancy-viz-line.png)

Çizgi grafikler değerler dizisinin tümünün, genellikle zaman içindeki genel şeklini vurgular.

### <a name="maps-basic-maps"></a>Haritalar: Temel haritalar
![temel harita](media/end-user-visual-type/pbi-nancy-viz-map.png)

Hem kategorik hem de nicel bilgileri uzamsal konumlarla ilişkilendirmek için bir temel harita kullanın.

### <a name="maps-arcgis-maps"></a>Haritalar: ArcGIS haritaları
![ArcGis haritası](media/end-user-visual-type/power-bi-esri-map-theme2.png)

ArcGIS haritaları ile Power BI birlikte kullanıldığında eşleme deneyimi, haritada belirli noktaları göstermenin ötesinde yepyeni bir boyut kazanıyor. Altlık haritalar, konum türleri, temalar, sembol stilleri ve başvuru katmanları için kullanılabilir seçenekleri görsel harika, bilgilendirici harita oluşturur. Uzamsal analiz içeren bir haritadaki yetkili veri katmanlarının (örneğin, görselleştirmenizdeki verilerin) birleşimi görselinizi verileri daha derin bir anlayış oluşturur.

### <a name="maps-filled-maps-choropleth"></a>Haritalar: Kartogramlar (Koroplet)
![kartogram](media/end-user-visual-type/pbi-nancy-viz-filledmap.png)

Bir kartogram, değerlerin bir coğrafya veya bölge üzerinde orantısal olarak nasıl farklılık gösterdiğini görüntülemek için gölgelendirmeyi ya da tonlandırmayı veya desenleri kullanır. Bu göreli farklılıkları açıktan (daha az sık/daha düşük) koyuya (daha fazla sık/daha yüksek) çeşitlilik gösteren gölgelendirme ile hızlıca görüntüleyin.

### <a name="maps-shape-maps"></a>Haritalar: Şekil haritaları
![şekil haritası](media/end-user-visual-type/power-bi-shape-map2.png)

Şekil haritaları haritadaki bölgeleri renk kullanarak karşılaştırır. Harita görselinin aksine, şekil haritaları veri noktalarının kesin coğrafi konumlarını bir haritada gösteremez. Bunun yerine, ana amacı bölgelerin göreli karşılaştırmalarını, farklı şekilde renklendirerek bir haritada göstermektir.

### <a name="matrix"></a>Matris
![matris](media/end-user-visual-type/matrix.png)

Matris görseli basamaklı düzeni destekleyen bir tür tablo görselidir (aşağıdaki "Tablo" bölümüne bakın). Genellikle rapor tasarımcıları rapor ve panolara matrisler ekler ve bu matrisler kullanıcıların rapor sayfasındaki diğer görselleri çapraz vurgulayabilmek için matristeki bir veya birden fazla öğeyi (satır, sütun, hücre) seçebilmesini sağlar.  

### <a name="pie-charts"></a>Pasta grafikleri
![pasta grafiği](media/end-user-visual-type/pbi-nancy-viz-pie.png)

Pasta grafikleri parçaların bütünle ilişkisini gösterir. 

### <a name="ribbon-chart"></a>Şerit grafik
![Şerit grafik](media/end-user-visual-type/power-bi-ribbon.png)

Şerit grafikleri hangi veri kategorisinin en yüksek derecelendirmeye (en büyük değer) sahip olduğunu gösterir. Şerit grafikler, sıralama değişimini gösterme konusunda etkili bir araçtır; en yüksek sıra (değer) her bir zaman aralığı için her zaman en üstte görüntülenir.

### <a name="scatter-bubble-and-dot-plot-charts"></a>Dağılım, Kabarcık ve Noktalı grafikleri


Dağılım grafiğinde her zaman, biri yatay eksende bir sayısal veri kümesi gösteren, diğeri ise dikey eksen üzerinde bir sayısal değer kümesi gösteren iki değer ekseni bulunur. Grafik, X ve Y sayısal değerlerinin kesişim noktalarını görüntüler ve bu değerleri tekli veri noktalarına dönüştürür. Bu veri noktaları, verilere bağlı olarak yatay eksende eşit veya eşit olmayan şekilde dağıtılabilir.

![kabarcık grafiği](media/end-user-visual-type/pbi-nancy-viz-bubble.png)

Kabarcık grafiğinde veri noktaları yerine kabarcıklar kullanılır ve kabarcığın boyutu verilerin farklı bir boyutunu gösterir.

Noktalı grafik, kabarcık grafiğine ve dağılım grafiğine benzer ancak onlardan farklı olarak X ekseninde sayısal veya kategorik veriler çizilmesine imkan tanır.

### <a name="scatter-high-density"></a>Yüksek yoğunluklu dağılım
![yüksek yoğunluklu dağılım](media/end-user-visual-type/density-scatter.png)

Tanımı gereği, makul oranda hızlı ve etkileşime duyarlı görseller oluşturmak için yüksek yoğunluklu veriler örneklenir. Yüksek yoğunluklu örnekleme çakışan noktaları ortadan kaldıran bir algoritma kullanır ve veri kümesindeki tüm noktaların görsele yansıtılmasını sağlar. Verilerin yalnızca temsili bir örneğini çizmez.  

Veri kümesinin tamamındaki önemli noktalar için yanıtlama, temsil ve korumanın en iyi bileşimini sağlamayı güvence altına alır.

### <a name="slicers"></a>Dilimleyiciler
![dilimleyici](media/end-user-visual-type/pbi-slicer.png)

Dilimleyici, sayfadaki diğer görselleri filtrelemek için kullanılabilen tek başına bir grafiktir. Dilimleyiciler birçok farklı biçimde (kategori, aralık, tarih vb.) gelir ve kullanılabilir değerlerin yalnızca birini, birçoğunu veya tümünü seçecek şekilde biçimlendirilebilir. 

Dilimleyiciler aşağıdaki durumlarda harika seçimdir:
- daha kolay erişim sağlamak amacıyla, sık kullanılan veya önemli filtreleri rapor tuvalinde görüntülemek
- açılan bir listeyi açmak zorunda kalmadan, o sırada filtreli olan durumu daha kolay görüntülemek
- veri tablolarında gereksiz ve gizli sütunlara göre filtreleme yapmak
- dilimleyicileri önemli görsellerin yanına koyarak daha iyi odaklanmış raporlar oluşturmak

### <a name="standalone-images"></a>Tek başına resimler
![tek başına resim](media/end-user-visual-type/pbi-nancy-viz-image.png)

Tek başına resim rapora veya panoya eklenmiş bir grafiktir. 


### <a name="tables"></a>Tablolar
![tablo grafiği](media/end-user-visual-type/table-type.png)

Tablo, mantıksal satır ve sütun dizilerinde ilgili verileri içeren bir kılavuzdur. Tabloda başlık ve toplam satırı da bulunabilir. Tablolar, tek bir kategoriye ait birden fazla değeri incelediğiniz nicelik karşılaştırmaları için idealdir. Örneğin bu tabloda Category için beş farklı ölçü gösterilmektedir.

Tablolar şunlar için harika seçimdir:
- ayrıntılı verileri ve tam değerleri görüp karşılaştırmak için (görsel gösterimler yerine)
- verileri tablo biçiminde görüntülemek için
- sayısal verileri kategorilere göre ayrılmış şekilde görüntülemek için

### <a name="treemaps"></a>Ağaç haritaları
![ağaç haritası grafiği](media/end-user-visual-type/pbi-nancy-viz-tree.png)

Ağaç haritaları, renkli dikdörtgenlerden oluşan grafiklerdir ve boyutlar değerleri temsil eder.  Bu grafikler hiyerarşik (ana dikdörtgenlerde iç içe geçmiş dikdörtgenler halinde) olabilir. Her dikdörtgenin içindeki alan, ölçülmekte olan değere bağlıdır. Ayrıca dikdörtgenler, sol üstten (en büyük) sağ alta (en küçük) doğru boyutlarına göre düzenlenir.

Ağaç haritaları aşağıdaki durumlarda kullanım için mükemmel seçimdir:
- büyük miktarlarda hiyerarşik veri görüntüleme
- çubuk grafik, yüksek miktarlardaki değerleri etkili bir şekilde işleyemediğinde
- her bir parça ve bütün arasındaki oranları gösterme
- hiyerarşideki kategorilerin her düzeyinde ölçü dağılımının desenini gösterme
- boyut ve renk kodlaması kullanarak öznitelikleri gösterme
- desenleri, aykırı değerleri, en önemli katkıda bulunanları ve istisnaları bulma

### <a name="waterfall-charts"></a>Şelale grafikler
![Şelale grafiği](media/end-user-visual-type/waterfall-small.png)

Şelale grafikler, değerler eklenirken veya çıkarılırken değişen toplamı gösterir. Bir başlangıç değerinin (örneğin, net gelir) bir dizi pozitif ve negatif değişiklikten nasıl etkilendiğini anlamak için faydalıdır.

Artış ve azalışları hızlıca görebilmeniz için sütunlar renk kodludur. Başlangıç değeri ve son değer sütunları genellikle yatay eksende başlar ve ara değerler de yüzen sütunlar olarak görünür. Bu "görünüm" nedeniyle şelale grafikler köprü grafikleri olarak da adlandırılır.

Şelale grafikler aşağıdaki durumlarda harika bir seçimdir:
- zaman serilerinde veya farklı kategorilerde ölçü değişikliği yaptığınızda
- toplam değere etki eden büyük değişiklikleri denetlemek için
- çeşitli gelir kaynaklarını göstererek şirketinizin yıllık kârının çizimini yapmak ve toplam kâra (veya zarara) ulaşmak için.
- şirketinizin bir yılın başındaki ve sonundaki çalışan sayısını göstermek için
- her ay kazandığınız ve harcadığınız para tutarını ve hesabınızın değişen bakiyesini görselleştirmek için.

## <a name="qna"></a>Soru- cevap bilgi hangi görselin kullanın
Power BI soru- cevap özelliğiyle doğal dil sorguları yazarken sorgunuzda görsel türünü belirtebilirsiniz.  Örnek:


"***sales by state as a treemap***" (ağaç haritası olarak eyalete göre satışlar)

![soru-cevap oturumu](media/end-user-visual-type/qa-treemap.png)

## <a name="next-steps"></a>Sonraki adımlar
[Raporlar, panolar ve uygulamalar görsellerle etkileşim](end-user-visualizations.md)    
[Doğru görsel başvuruları ile ilgili sqlbi.com sayfası](http://www.sqlbi.com/wp-content/uploads/videotrainings/dashboarddesign/visuals-reference-may2017-A3.pdf)
