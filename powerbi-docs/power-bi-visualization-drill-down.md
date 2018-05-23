---
title: Power BI'daki görselleştirmelerde detaya gitme
description: Bu belgede, Microsoft Power BI hizmetinde ve Power BI Desktop'ta bir görselleştirmenin detayına nasıl gidileceği gösterilmektedir.
author: mihart
manager: kfile
ms.reviewer: ''
featuredvideoid: MNAaHw4PxzE
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 02/26/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: d622e6b461668d1972a78f6844bd269fb6596061
ms.sourcegitcommit: dcde910817720c05880ffe24755034f916c9b890
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/19/2018
---
# <a name="drill-down-in-a-visualization-in-power-bi"></a>Power BI'daki görselleştirmelerde detaya gitme
## <a name="drill-down-requires-a-hierarchy"></a>Detaya gitme bir hiyerarşi gerektirir
Bir görselde hiyerarşi varsa ek ayrıntıları açığa çıkarmak için detaya gidebilirsiniz. Örneğin, Olimpiyat madalyası sayısına spor, disiplin ve etkinlik açısından bakan bir görselleştirmeniz olabilir. Görselleştirme varsayılan olarak madalya sayısını sporlara göre (jimnastik, kayak, su sporları vb.) gösterir. Ancak bir hiyerarşiye sahip olduğundan, görsel öğelerden (bir çubuk, çizgi veya kabarcık) biri seçildiğinde giderek daha ayrıntılı hale gelen bir resim görüntülenir. Yüzme, atlama ve su topu ile ilgili verileri görmek için **su sporları** öğesini seçin.  Tramplen, kule ve senkronize atlama etkinlikleri ile ilgili ayrıntıları görmek için **atlama** öğesini seçin.

Size ait raporlara hiyerarşiler ekleyebilirsiniz ancak sizinle paylaşılan raporlara ekleyemezsiniz.
Hangi Power BI görselleştirmelerinin bir hiyerarşi içerdiğinden emin değil misiniz?  Bir görselleştirmenin üzerine geldiğinizde üst köşelerde bu detay denetimlerini görüyorsanız görselleştirmenizde hiyerarşi bulunuyor demektir.

![](media/power-bi-visualization-drill-down/power-bi-drill-icon4.png)  ![](media/power-bi-visualization-drill-down/power-bi-drill-icon2.png)  ![](media/power-bi-visualization-drill-down/power-bi-drill-icon3.png)
![](media/power-bi-visualization-drill-down/power-bi-drill-icon5.png) ![](media/power-bi-visualization-drill-down/power-bi-drill-icon6.png)  

Tarih, benzersiz bir hiyerarşi türüdür. Görselleştirmeye bir tarih alanı eklediğinizde Power BI otomatik olarak yıl, üç ay, ay ve gün içeren bir zaman hiyerarşisi ekler. Daha fazla bilgi için [Görsel hiyerarşiler ve detaya gitme davranışı](guided-learning/visualizations.yml?tutorial-step=18) makalesine bakın veya aşağıdaki videoyu izleyin.


  <iframe width="560" height="315" src="https://www.youtube.com/embed/MNAaHw4PxzE?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

> [!NOTE]
> Power BI Desktop'ı kullanarak hiyerarşi oluşturmayı öğrenmek için [How to create and add hierarchies (Hiyerarşi oluşturma ve ekleme)](https://youtu.be/q8WDUAiTGeU) videosunu seyredin
> 
> 

## <a name="two-methods-to-drill-down"></a>Detaya gitmek için iki yöntem
Görselleştirmenizde detaya gitmek (ve detaydan çıkmak) için izleyebileceğiniz iki yol vardır.  Bu makalede her iki yol da açıklanmaktadır. Her iki yöntem de aynı görevi gerçekleştirir, bu nedenle tercih ettiğiniz yöntemi kullanın.

> [!NOTE]
> Birlikte ilerlemek için Power BI hizmetinde [Retail Analysis sample'ı açın](sample-datasets.md) ve **Total Units This Year** (Değerler) özelliğine **Territory**, **City**, **PostalCode** ve **Name** (Grup) açısından bakan bir ağaç haritası oluşturun.  
> 
> 

## <a name="method-one-for-drill-down"></a>Detaya gitmek için birinci yöntem
Bu yöntemde görselleştirmenin üst köşelerinde görünen detay simgeleri kullanılır.

1. Power BI'da bir raporu [Okuma görünümü veya Düzenleme görünümü](service-reading-view-and-editing-view.md)'nde açın. Detay için hiyerarşiye sahip bir görselleştirme gerekir. 
   
   Aşağıdaki animasyonda bir hiyerarşi gösterilmektedir.  Görselleştirmede bölge, şehir, posta kodu ve şehir adından oluşan bir hiyerarşi bulunur. Her bölgede bir veya daha fazla şehir, her şehirde bir veya daha fazla posta kodu bulunur ve bu şekilde devam eder. Varsayılan olarak, listede ilk sırada *Territory* göründüğü için görselleştirme yalnızca bölge verilerini görüntüler.
   
   ![](media/power-bi-visualization-drill-down/power-bi-hierarcy-list.png)
2. Detaya gitmeyi etkinleştirmek için görselleştirmenin sağ üst köşesindeki ok simgesini seçin. Simge koyu olduğunda detay etkindir. Detayı açmazsanız bir görsel öğe (çubuk veya kabarcık gibi) seçildiğinde rapor sayfasındaki diğer grafiklere çapraz filtreleme uygulanır.    
   
   ![](media/power-bi-visualization-drill-down/power-bi-drill-icon.png)
3. **Tek seferde bir alan** kadar detaya gitmek için görselleştirmenizdeki öğelerden birini seçin. Çubuk grafikte bunu, çubuklardan birine tıklayarak yapabilirsiniz. Ağaç haritasında ise **yapraklardan** birine tıklamanız gerekir. Detaya gittiğinizde ve detaydan çıktığınızda başlığın değiştiğine dikkat edin. Bu animasyonda "Territory tarafından düzenlenen Total Units This Year" başlığı "Territory ve City tarafından düzenlenen Total Units This Year", "Territory, City ve PostalCode tarafından düzenlenen Total Units This Year", "Territory, City, PostalCode ve Name tarafından düzenlenen Total Units This Year" olarak değişir. Yeniden detaydan çıkmak için aşağıda gösterildiği gibi görselleştirmenin sol üst köşesindeki **Detaydan Çık** simgesini ![](media/power-bi-visualization-drill-down/power-bi-drill-icon5.png) seçin.
   
   ![](media/power-bi-visualization-drill-down/drill.gif)
4. ***Tüm alanlarda aynı anda*** detaya gitmek için görselleştirmenin sol üst köşesindeki çift oku seçin.
   
   ![](media/power-bi-visualization-drill-down/pbi_drillall.png)
5. Yeniden detaydan çıkmak için görselleştirmenin sol üst köşesindeki yukarı oku seçin.
   
   ![](media/power-bi-visualization-drill-down/pbi_drillup2.png)

## <a name="method-two-for-drill-down"></a>Detaya gitmek için ikinci yöntem
Bu yöntemde üst kısımdaki Power BI menü çubuğundaki **Araştır** açılan menüsü kullanılır.

1. Power BI'da bir raporu [Okuma görünümü veya Düzenleme görünümü](service-reading-view-and-editing-view.md)'nde açın. Detay için hiyerarşiye sahip bir görselleştirme gerekir. 
   
   Aşağıdaki görüntüde bir hiyerarşi gösterilmektedir.  Görselleştirmede bölge, şehir, posta kodu ve şehir adından oluşan bir hiyerarşi bulunur. Her bölgede bir veya daha fazla şehir, her şehirde bir veya daha fazla posta kodu bulunur ve bu şekilde devam eder. Varsayılan olarak, listede ilk sırada *Territory* göründüğü için görselleştirme yalnızca bölge verilerini görüntüler.
   
   ![](media/power-bi-visualization-drill-down/power-bi-hierarcy-list.png)
2. Detaya gitmeyi etkinleştirmek için bir görselleştirmeyi seçerek etkin hale getirin ve Power BI üst menü çubuğunda **Araştır** > **Detaya Git**'i seçin. Görselleştirmenin sağ üst köşesindeki detaya git simgesi siyah bir arka plan olarak değişir. ![](media/power-bi-visualization-drill-down/power-bi-drill-icon2.png)  
   
   ![](media/power-bi-visualization-drill-down/power-bi-explore2.png)
3. Etkinleştirildikten sonra, bir seferde bir alanda detaya gitmek için ağaç haritası yapraklarından birini seçin. Bu örnekte, bu yıl Kuzey Carolina'da satılan toplam birimlerin şehre göre görüntülenmesi için **NC** adlı bölge seçilmektedir.
   
   ![](media/power-bi-visualization-drill-down/power-bi-drilldown-1.png)
4. Tüm alanlarda aynı anda detaya gitmek için **Araştır** > **Sonraki Düzeyi Göster**'i seçin.
   
   ![](media/power-bi-visualization-drill-down/power-bi-show-next-level.png)
5. Yeniden detaydan çıkmak için **Araştır** > **Detaydan Çık**'ı seçin.
   
   ![](media/power-bi-visualization-drill-down/power-bi-drill-up2.png)

6. Görseli oluşturmada kullanılan verileri görmek için **Verileri görüntüle**'yi seçin. Veriler, görselin altındaki bölmede görüntülenir. Siz görseli ayrıntılandırırken bu bölme sabit kalır. Daha fazla bilgi için bkz. [Görseli oluşturmak için kullanılan verileri gösterme](service-reports-show-data.md).

## <a name="understanding-the-hierarchy-axis-and-hierarchy-group"></a>Hiyerarşi eksenini ve hiyerarşi grubunu anlama
Hiyerarşi eksenini ve hiyerarşi grubunu, görüntülemek istediğiniz verilerin ayrıntı düzeyini artırmak ve azaltmak için kullanabileceğiniz mekanizmalar olarak düşünebilirsiniz. Kategoriler ve alt kategoriler halinde düzenlenebilen tüm veriler bir hiyerarşiye sahip olmaya uygundur. Doğal olarak, buna tarihler ve saatler de dahildir.

**Değerler** kutusunda veri alanları olarak araştırmak istediğiniz verilerin yanı sıra **Eksen** kutusuna veya **Grup** kutusuna eklenecek bir ya da daha fazla veri alanını seçerek hiyerarşi elde etmek için Power BI’da bir görselleştirme oluşturabilirsiniz. Görselleştirmenizin sol üst ve sağ köşelerinde Ayrıntı Modu simgelerinin görünmesi, verilerinizin hiyerarşik olduğu anlamına gelir. 

Hiyerarşik verilerin temel olarak iki türü olduğu söylenebilir:
- Tarih ve saat verileri - Bir DateTime veri türünün bulunduğu bir veri alanınız varsa bu, hiyerarşik verilere zaten sahip olduğunuz anlamına gelir. Power BI, değerleri bir [DateTime](https://msdn.microsoft.com/library/system.datetime.aspx) yapısına ayrıştırılabilen herhangi bir veri alanı için otomatik olarak hiyerarşi oluşturur. **Eksen** veya **Grup** kutusuna yalnızca bir DateTime alanı eklemeniz gerekir.
- Kategorik veriler - Verileriniz, alt koleksiyonlar içeren veya ortak değerlerin bulunduğu veri satırlarına sahip koleksiyonlardan türetilmişse bu, hiyerarşik verilere sahip olduğunuz anlamına gelir.

Power BI bir alt ağ veya tüm alt ağlara kadar genişletmenize olanak tanır. Her düzeyde tek bir alt kümeyi veya her düzeyde aynı anda tüm alt kümeleri görebileceğiniz şekilde verilerinizde detaya gidebilirsiniz. Örneğin, belirli bir yılın ayrıntısına gidebilir veya hiyerarşinin ayrıntılarına indikçe her bir yılın tüm sonuçlarını görebilirsiniz. Diğer taraftan, aynı şekilde detaydan çıkabilirsiniz.

Aşağıdaki bölümlerde en yüksek görünümden, orta görünümden ve en düşük görünümden detaya gitme açıklanmaktadır.

### <a name="hierarchical-data-and-time-data"></a>Hiyerarşik veriler ve zaman verileri
Bu örnekte, [Perakende Analizi örneğiyle](sample-datasets.md) birlikte ilerleyin ve **Ay**’ı (Eksen) **Toplam Satış**’a (Değerler) göre gösteren yığılmış bir grafik görselleştirmesi oluşturun.  

Eksen veri alanı **Ay** olsa da **Eksen** kutusunda yine de bir **Yıl** kategorisi oluşturur. Bunun nedeni Power BI’ın, okuduğu tüm değerler için tam DateTime yapısını sağlamasıdır. Hiyerarşinin üst tarafında yıla ait veriler gösterilir.

![](media\power-bi-visualization-drill-down/power-bi-hierarchical-axis-datetime-1.png)

Detaya Gitme modu açık olduğunda, hiyerarşide bir düzey kadar detaya gitmek için grafikteki çubuğa tıklayın. Üç aylık dönemlere ait kullanılabilir verilere ilişkin üç çubuk görürsünüz. Daha sonra sol üst taraftaki simgelerden **Expand all down one level of the hierarchy** (Tümünde hiyerarşinin bir düzeyi kadar detaya git) seçeneğini belirleyin. Daha sonra hiyerarşinin, her ayın sonuçlarını gösteren en düşük düzeyine inmek için bu işlemi tekrarlayın.

![](media\power-bi-visualization-drill-down/power-bi-hierarchical-axis-datetime-2.png)

Görselleştirmenin dışında, hiyerarşinin her rapor için oluşturulan verilere yansıdığını görebiliriz. Aşağıdaki tablo, tek bir ayın veya tüm ayların detayına giden bir raporda **Verileri Göster** seçeneğinin sonuçlarını gösterir. 

Verilerin üç aylık ve yıllık raporlar için aynı olduğunu, ancak **Değerler** için belirtilen detay düzeyine gitmenizin ardından tek bir raporun daha ayrıntılı hale geldiğini ve "tüm aylar" raporunda daha fazla veri bulunduğunu görebilirsiniz.


|Genişletme modu|Yıl|Çeyrek|Ay|Gün|
| ---|:---:|:---:|:---:|---|
|Tek|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-year.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-quarter.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-one-month.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-one-day.png)|
|Tümü|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-year.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-quarter.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-all-month.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-all-day.png)|


### <a name="hierarchical-category-data"></a>Hiyerarşik kategori verileri
Koleksiyonlardan ve alt koleksiyonlardan modeli oluşturulan veriler hiyerarşiktir. Konum verileri bunun iyi bir örneğidir. Bir veri kaynağında sütunları Ülke, Bölge, Şehir ve Posta Kutusu olan bir tablo düşünün. Aynı Ülkenin, Bölgenin ve Şehrin bulunduğu veriler hiyerarşiktir.

Bu örnekte, [Perakende Analizi örneğiyle](sample-datasets.md) birlikte ilerleyin. **Total Units This Year** (Bu Yıla Ait Birimlerin Toplamı) (Değerler) özelliğini **Bölge**, **Şehir**, **Posta Kodu** ve **Ad**’a (Grup) göre gösteren yığılmış bir sütun grafik görselleştirmesi oluşturun.  

![](media\power-bi-visualization-drill-down/power-bi-hierarchical-axis-category-1.png)

Detaya Gitme modu açıkken, sol üst taraftaki simgelerden **Expand all down one level of the hierarchy** (Tümünde hiyerarşinin bir düzeyi kadar detaya git) seçeneğini üç kez belirleyin.
Hiyerarşinin Bölge, Şehir ve Posta Kodu sonuçlarını gösteren en düşük düzeyinde olmanız gerekir.

![](media\power-bi-visualization-drill-down/power-bi-hierarchical-axis-category-2.png)

Görselleştirmenin dışında, hiyerarşinin her rapor için oluşturulan verilere yansıdığını görebiliriz. Aşağıdaki tablo, tek bölge veya tüm bölgeler için detaya giden bir raporda **Verileri Göster** seçeneğinin sonuçlarını gösterir. Detaya gittikçe, tek bir raporun daha ayrıntılı hale geldiğini ve "tüm bölgeler" raporunun daha fazla veri içerdiğini görebilirsiniz.


| Genişletme modu|Bölge|Şehir|Posta Kodu|Ad|
| ---|:---:|:---:|:---:|---|
|Tek|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-territory.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-one-territory-city.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-one-territory-city-postal.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-one-territory-city-postal-name.png)|
|Tümü|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-territory.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-all-territory-city.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-all-territory-city-postal.png)|![](media\power-bi-visualization-drill-down/power-bi-hierarchical-all-territory-city-postal-name.png)|


## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar
* Bir görselleştirmeye tarih alanı eklenmesi bir hiyerarşi oluşturmuyorsa "tarih" alanı aslında bir tarih olarak kaydedilmemiş olabilir. Veri kümesi size aitse bunu Power BI Desktop'ta *Veri* görünümünde açın, tarihi içeren sütunu seçin ve Modelleme sekmesinde **Veri Türü**'nü **Tarih** veya **Tarih/Saat** olarak değiştirin. Rapor sizinle paylaşıldıysa değişikliği yapmasını istemek için raporun sahibi ile iletişime geçin.  
  
  ![](media/power-bi-visualization-drill-down/power-bi-change-data-type2.png)

## <a name="next-steps"></a>Sonraki adımlar
[Power BI raporlarındaki görselleştirmeler](power-bi-report-visualizations.md)

[Power BI raporları](service-reports.md)

[Power BI - Temel Kavramlar](service-basic-concepts.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

