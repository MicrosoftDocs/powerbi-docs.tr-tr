---
title: Görselleştirmede detaya gitme ve detaydan çıkma
description: Bu makalede, Microsoft Power BI hizmetinde ve Power BI Desktop'ta bir görselleştirmenin detayına nasıl gidileceği gösterilir.
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: MNAaHw4PxzE
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 6/17/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 29823a2f1ca7f1448df54282e0ce081310974eb3
ms.sourcegitcommit: 52aa112ac9194f4bb62b0910c4a1be80e1bf1276
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2019
ms.locfileid: "67265273"
---
# <a name="drill-mode-in-a-visualization-in-power-bi"></a>Power BI’daki görselleştirmelerde ayrıntı modu

Bu makalede, Microsoft Power BI hizmetinde ve Power BI Desktop'ta bir görselleştirmenin detayına nasıl gidileceği gösterilir. Power BI raporlarında verilerinizden en fazla içgörüyü elde edebilmeniz için birden çok veri hiyerarşisi kullanılabilir. Veri noktalarınızda detaya gitmeyi ve detaydan çıkmayı kullanarak verilerinizi çok ayrıntılı keşfedebilirsiniz. Hatta mobil cihazlarınızın küçük form faktöründe bile bundan yararlanabilirsiniz.

## <a name="drill-requires-a-hierarchy"></a>Detay bir hiyerarşi gerektirir

Bir görselleştirmede hiyerarşi varsa ek ayrıntıları açığa çıkarmak için detaya gidebilirsiniz. Örneğin, Olimpiyat madalyası sayısına spor, disiplin ve etkinlik açısından bakan bir görselleştirmeniz olabilir. Görselleştirme varsayılan olarak madalya sayısını sporlara göre (jimnastik, kayak, su sporları vb.) gösterir. Ama bir hiyerarşisi olduğundan, görselleştirme öğelerinden (çubuk, çizgi veya kabarcık gibi) biri seçildiğinde giderek daha ayrıntılı hale gelen bir resim görüntülenir. Yüzme, atlama ve su topu ile ilgili verileri görmek için **su sporları** öğesini seçin.  Tramplen, kule ve senkronize atlama etkinlikleri ile ilgili ayrıntıları görmek için **atlama** öğesini seçin.

Size ait raporlara hiyerarşiler ekleyebilirsiniz ancak sizinle paylaşılan raporlara ekleyemezsiniz.
Hangi Power BI görselleştirmelerinin hiyerarşi içerdiğinden emin değil misiniz? Görselleştirmenin üzerine gelin. Üst köşelerde bu detay denetimlerini görüyorsanız görselleştirmenizde hiyerarşi bulunuyor demektir.

![Tek düzey detaya gitme simgesinin ekran görüntüsü.](./media/end-user-drill/power-bi-drill-icon4.png)  ![Detaya gitmeyi açma ve kapatma simgesinin ekran görüntüsü.](./media/end-user-drill/power-bi-drill-icon2.png)  ![Bir kerede tüm alanlarda detaya gitme simgesinin ekran görüntüsü.](./media/end-user-drill/power-bi-drill-icon3.png)
![detaydan çıkma simgesi](./media/end-user-drill/power-bi-drill-icon5.png) ![Aşağıda doğru genişletme simgesinin ekran görüntüsü.](./media/end-user-drill/power-bi-drill-icon6.png)  

Tarih, benzersiz bir hiyerarşi türüdür. Görselleştirmeye bir tarih alanı eklediğinizde Power BI otomatik olarak yıl, üç ay, ay ve gün içeren bir zaman hiyerarşisi ekler. Daha fazla bilgi için [görselleştirme hiyerarşileri ve detaya gitme davranışı](../guided-learning/visualizations.yml?tutorial-step=18) makalesine bakın veya aşağıdaki videoyu izleyin.

<iframe width="560" height="315" src="https://www.youtube.com/embed/MNAaHw4PxzE?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

> [!NOTE]
> Power BI Desktop'ı kullanarak hiyerarşi oluşturmayı öğrenmek için [Hiyerarşi oluşturma ve ekleme](https://youtu.be/q8WDUAiTGeU) videosunu izleyin.

## <a name="prerequisites"></a>Önkoşullar

1. Power BI hizmetinde veya Desktop’ta detay için hiyerarşisi olan bir görselleştirme gerekir.

1. Örneği takip etmek için [Perakende Analizi örneğini](../sample-datasets.md) açın. Şunlara bakan bir **Ağaç haritası** görselleştirmesi oluşturun:

    | Kutu | Alan |
    | ---- | ----- |
    | Değer |Satışlar<br>\|\_ Total Units This Year |
    | Grup | Mağaza<br>\|\_ Territory<br>\|\_ City<br>\|\_ Postal Code<br>\|\_ Name

    Ağaç haritasında bölge, şehir, posta kodu ve şehir adından oluşan bir hiyerarşi bulunur. Her bölgede bir veya daha fazla şehir, her şehirde bir veya daha fazla posta kodu bulunur ve bu şekilde devam eder. Varsayılan olarak, listede ilk sırada *Territory* göründüğü için görselleştirme yalnızca bölge verilerini gösterir.

    ![Territory alanının öne çıkarıldığı Görselleştirmeler bölmesinin ekran görüntüsü.](media/end-user-drill/power-bi-hierarcy-list.png)

1. Farklı detay simgelerinin birlikte nasıl çalıştığını öğrenmek kafa karıştırıcı olabilir. Şimdi ağaç haritasını yalnızca küçük bölgelerin ikisini gösterecek şekilde filtreleyelim: **KY** ve **TN**. Ağaç haritasını seçin ve **Görsel düzeyi filtreleri** altında **Bölge**’yi genişletip **KY** ve **TN**’yi seçin.

    ![KY ve TN için filtrelenen Görselleştirmeler bölmesinin ekran görüntüsü.](./media/end-user-drill/power-bi-filter.png)

    Şimdi harita ağacında yalnızca iki bölge gösterilir.

    ![KY ve TN'nin öne çıkarıldığı görselin ekran görüntüsü.](./media/end-user-drill/power-bi-territories.png)

## <a name="three-ways-to-use-the-drill-features"></a>Detay özelliklerini kullanmanın üç yolu

Hiyerarşisi olan görselleştirmeler için detaya gitme, detaydan çıkma ve genişletme özelliklerine erişmeye yönelik birkaç seçeneğiniz vardır. Bu makalede aşağıdaki birinci seçeneğin nasıl kullanılacağı gösterilmiştir. Detaya gitme ve genişletmenin temellerini öğrendikten sonra tüm ağacı nasıl kullanacağınızı anlarsınız. Bunların tümü aynı şeyi yapar. Hepsini deneyin ve en hoşunuza gideni seçin.

- Simgeleri görmek ve kullanmak için bir görselleştirmenin üzerine gelin.  

    ![Üzerine gelme örneğinin ekran görüntüsü.](./media/end-user-drill/power-bi-hover.png)

- Menüyü ortaya çıkarmak ve kullanmak için bir görselleştirmeye sağ tıklayın.

    ![Sağ tıklama örneğinin ekran görüntüsü.](./media/end-user-drill/power-bi-drill-menu.png)

- Power BI menü çubuğundan **Araştır** düğmesini seçin.

   ![Detay simgeleri ve seçeneklerinin gösterildiği Keşfet seçiminin ekran görüntüsü.](media/end-user-drill/power-bi-explore.png)

## <a name="drill-pathways"></a>Detay yolları

### <a name="drill-down"></a>Detaya gitme

Görselleştirmenizi detaylandırmanın birkaç yolu vardır. **Detaya git** sizi hiyerarşide bir sonraki düzeye götürür. Bu nedenle, **Territory** düzeyine bakıyorsanız şehir düzeyine, sonra posta kodu ve son olarak ad düzeyine gidebilirsiniz. Yoldaki her bir adım size yeni bilgiler gösterir.

![Detay yolunu gösteren diyagram](./media/end-user-drill/power-bi-drill-path.png)

### <a name="expand"></a>Genişlet

**Genişletme**, geçerli görünüme ilave bir hiyerarşi düzeyi ekler. Bu nedenle, **Territory** düzeyine bakıyorsanız ağaç haritanızı genişletip şehir, posta kodu ve ad ayrıntısını ekleyebilirsiniz. Yoldaki her adım size aynı bilgileri gösterir ve bir düzey yeni bilgi ekler.

![Genişletme yolunu gösteren diyagram](./media/end-user-drill/power-bi-expand-path.png)

Ayrıca bir kerede bir alanda veya aynı anda tüm alanlarda detaya gitmeyi ya da genişletmeyi seçebilirsiniz.

## <a name="drill-down-all-fields-at-once"></a>Aynı anda tüm alanlarda detaya gitme

1. Ağaç haritasının KY ve TN verilerini gösteren en üst düzeyinden başlayın. Tanıtıcılardan birini seçip sağa sürükleyerek ağaç haritanızı genişletin.

    ![KY ve TN'yi gösteren ağaç haritası görselinin ekran görüntüsü](./media/end-user-drill/power-bi-drill-down.png)

1. *Tüm alanlarda aynı anda* detaya gitmek için görselleştirmenin sol üst köşesindeki çift oku ![çift detaya gitme simgesi](./media/end-user-drill/power-bi-drill-icon3.png) seçin. Ağaç haritanızda şimdi Kentucky ve Tennessee şehir verileri gösterilir.

    ![Şehirlerde detaya gitmeyi gösteren ağaç haritası görselinin ekran görüntüsü.](./media/end-user-drill/power-bi-drill-down1.png)

1. Hiyerarşinin posta kodu düzeyine ulaşmak için bir kez daha detaya gidin.

    ![Posta kodunda detaya gitmeyi gösteren ağaç haritası görselinin ekran görüntüsü.](./media/end-user-drill/power-bi-drill-down2.png)

1. Yeniden detaydan çıkmak için görselleştirmenin sol üst köşesindeki yukarı oku seçin ![Tek düzey detaydan çıkma simgesinin ekran görüntüsü.](./media/end-user-drill/power-bi-drill-icon5.png)geçin.

## <a name="drill-down-one-field-at-a-time"></a>Aynı anda tek bir alanda detaya gitme

Bu yöntemde görselleştirmenin sağ üst köşesinde görünen detaya gitme simgesi kullanılır.

1. Detaya gitme simgesini seçerek açın ![Açılmış detaya gitme açık/kapalı simgesinin ekran görüntüsü.](./media/end-user-drill/power-bi-drill-icon2.png)geçin.

    Şimdi **aynı anda tek alanda** detaya gitme seçeneği sunulur.

    ![Açılmış detaya gitme açık/kapalı simgesine işaret eden bir okla görselin ekran görüntüsü.](media/end-user-drill/power-bi-drill-icon-new.png)

    Detaya gitmeyi açmazsanız, görselleştirme öğesinin (çubuk, kabarcık veya yaprak gibi) seçilmesi detaya gidilmesini sağlamaz. Bunun yerine, rapor sayfasındaki diğer grafiklerde çapraz filtreleme yapar.

1. **TN**'nin yaprağını seçin. Ağaç haritanızda şimdi Tennessee’de mağazası olan tüm şehirler gösterilir.

    ![Yalnızca TN için verilerin gösterildiği ağaç haritasının ekran görüntüsü.](media/end-user-drill/power-bi-drill-down-one1.png)

1. Bu noktada yapabilecekleriniz:

    1. Tennessee için detaya gitmeye devam edebilirsiniz.

    1. Tennessee'deki belirli bir şehir için detaya gidebilirsiniz.

    1. Bunun yerine genişletebilirsiniz (aşağıdaki **Aynı anda tüm alanları genişletme** bölümüne bakın).

    Aynı anda tek bir alanda detaya gitme konusuna devam edelim.  **Knoxville, TN** öğesini seçin. Ağaç haritanız şimdi Knoxville’deki mağazanızın posta kodunu gösterir.

    ![37919 posta kodunun gösterildiği ağaç haritasının ekran görüntüsü.](media/end-user-drill/power-bi-drill-down-one2.png)

    Detaya gittiğinizde ve detaydan çıktığınızda başlığın değiştiğine dikkat edin.

## <a name="expand-all-and-expand-one-field-at-a-time"></a>Aynı anda tüm alanları ve tek bir alanı genişletme

Yalnızca posta kodu gösteren bir ağaç haritası pek bilgi vermez.  Bu nedenle hiyerarşide bir düzey aşağıya genişletelim.  

1. Ağaç haritası etkinken *aşağıya genişlet* simgesini ![Aşağıya genişlet simgesinin ekran görüntüsü](./media/end-user-drill/power-bi-drill-icon6.png) seçin. Ağaç haritanız şimdi hiyerarşimizin iki düzeyini gösterir: posta kodu ve mağaza adı.

    ![Posta kodunun ve mağaza adının gösterildiği ağaç haritasının ekran görüntüsü](./media/end-user-drill/power-bi-expand1.png)

1. Tennessee’nin dört hiyerarşi düzeyinin tamamını görmek için ikinci düzeye ulaşana kadar ağaç haritanızın detaydan çıkma okunu seçin (**Bölge ve şehre göre bu yılki toplam birim sayısı**).

    ![TN'nin tüm verilerinin gösterildiği ağaç haritasının ekran görüntüsü.](media/end-user-drill/power-bi-drill-down-one1.png)

1. Detaya gitme düğmesinin hala açık olduğundan emin olun ![Açılmış detaya gitme açık/kapalı simgesinin ekran görüntüsü.](./media/end-user-drill/power-bi-drill-icon2.png) ve *aşağıya genişlet* simgesini ![Aşağıya genişlet simgesinin ekran görüntüsü](./media/end-user-drill/power-bi-drill-icon6.png) seçin. Şimdi ağaç haritanız bazı ek ayrıntılar gösterir. Yalnızca şehir ve eyalet yerine posta kodu da gösterilir.

    ![Şehir, il ve posta kodunun gösterildiği görselin ekran görüntüsü.](./media/end-user-drill/power-bi-expand-one3.png)

1. Ağaç haritanızda Tennessee’nin dört hiyerarşi düzeyinin tamamını görüntülemek için *aşağıya genişletme* simgesini bir kez daha seçin. Daha fazla ayrıntı görmek için bir yaprağın üzerine gelin.

    ![Yaprağa özgü verilerle bir araç ipucunun gösterildiği ağaç haritasının ekran görüntüsü.](./media/end-user-drill/power-bi-expand-all.png)

## <a name="drilling-filters-other-visuals"></a>Diğer görsel delme filtreleri

Detay modunda çalışırken detaya gitme ve genişletme özelliklerinin sayfadaki diğer görselleştirmeleri nasıl etkilediğine karar verirsiniz.

Varsayılan olarak, detaylandırma özelliği bir rapordaki diğer görselleri filtrelemez. Ama bu özelliği Power BI Desktop'ta ve Power BI hizmetinde etkinleştirebilirsiniz.

1. Desktop’ta **Biçim** sekmesini ve **Diğer görsel delme filtreleri** onay kutusunu seçin.

    ![Power BI Desktop'ta Diğer görsel delme filtreleri ayarının gösterildiği ekran görüntüsü](./media/end-user-drill/power-bi-drill-filters-desktop.png)

1. Şimdi hiyerarşideki bir görselde detaya gittiğinizde, detaydan çıktığınızda veya genişlettiğinizde, bu eylem sayfadaki diğer görselleri filtreler.

    ![Desktop'taki sonucun ekran görüntüsü.](./media/end-user-drill/power-bi-drill-filters.png)

    ![Desktop'taki bir diğer sonucun ekran görüntüsü.](./media/end-user-drill/power-bi-drill-filters2.png)

> [!NOTE]
> Power BI hizmetinde bu özelliği etkinleştirmek için, üst menü çubuğundan **Görsel etkileşimler** > **Diğer görsel delme filtreleri**’ni seçin.
>
> ![Power BI hizmetinde Diğer görsel delme filtreleri ayarının ekran görüntüsü](./media/end-user-drill/power-bi-drill-filters-service.png)

## <a name="learn-about-the-hierarchy-axis-and-hierarchy-group"></a>Hiyerarşi eksenini ve hiyerarşi grubunu öğrenin

Hiyerarşi eksenini ve hiyerarşi grubunu, görüntülemek istediğiniz verilerin ayrıntı düzeyini artırmak ve azaltmak için kullanabileceğiniz mekanizmalar olarak düşünebilirsiniz. Tarihler ve saatler de dahil olmak üzere kategoriler ve alt kategoriler halinde düzenleyebileceğiniz tüm veriler bir hiyerarşiye sahip olmaya uygundur.

**Eksen** kutusuna veya **Grup** kutusuna eklenecek bir ya da daha fazla veri alanını seçerek hiyerarşi elde etmek için Power BI’da bir görselleştirme oluşturabilirsiniz. Ardından incelemek istediğiniz verilerin **Değerler** kutusuna veri alanı olarak ekleyin. Görselleştirmenizin sol üst ve sağ üst köşelerinde *Ayrıntı modu* simgelerinin görünmesi, verilerinizin hiyerarşik olduğu anlamına gelir.

Hiyerarşik verilerin temel olarak iki türü olduğu söylenebilir:

- Tarih ve saat verileri - Bir DateTime veri türünün bulunduğu bir veri alanınız varsa bu, hiyerarşik verilere zaten sahip olduğunuz anlamına gelir. Power BI her veri alanı için otomatik olarak hiyerarşi oluşturur. Değerleri [Tarih Saat](https://msdn.microsoft.com/library/system.datetime.aspx) yapısında ayrıştırabilirsiniz. **Eksen** veya **Grup** kutusuna yalnızca bir DateTime alanı eklemeniz gerekir.

- Kategorik veriler - Power BI verilerinizi alt koleksiyonlar içeren veya ortak değerlerin bulunduğu veri satırlarına sahip koleksiyonlardan türetiyorsa, bu hiyerarşik verilere sahip olduğunuz anlamına gelir.

Power BI bir alt ağa veya tüm alt ağlara kadar genişletmenize olanak tanır. Her düzeyde tek bir alt kümeyi veya her düzeyde aynı anda tüm alt kümeleri görebileceğiniz şekilde verilerinizde detaya gidebilirsiniz. Örneğin, belirli bir yılın ayrıntısına gidebilir veya hiyerarşinin ayrıntılarına indikçe her bir yılın tüm sonuçlarını görebilirsiniz.

Ayrıca aynı şekilde detaydan da çıkabilirsiniz.

Aşağıdaki bölümlerde en yüksek görünümden, orta görünümden ve en düşük görünümden detaya gitme açıklanmaktadır.

### <a name="hierarchical-data-and-time-data"></a>Hiyerarşik veriler ve zaman verileri

Bu örnekte:

1. [Perakende Analizi örneğini](../sample-datasets.md) izleyin ve şunlara bakan bir yığılmış sütun grafik görselleştirmesi oluşturun:

    | Kutu | Alan |
    | ---- | ----- |
    | Eksen | Saat<br>\|\_ Ay |
    | Değerler | Satışlar<br>\|\_ TotalSales |

    Eksen veri alanı **Ay** olsa da **Eksen** kutusunda yine de bir **Yıl** kategorisi oluşturur. Bunun nedeni Power BI’ın, okuduğu tüm değerler için tam Tarih Saat yapısını sağlamasıdır. Hiyerarşinin üst tarafında yıla ait veriler gösterilir.

    ![Yıla göre gruplandırılmış verilerin gösterildiği tek çubuğun ekran görüntüsü](media/end-user-drill/power-bi-hierarchical-axis-datetime-1.png)

1. Detaya gitme modu açık olduğunda, hiyerarşide bir düzey kadar detaya gitmek için grafikteki çubuğu seçin. Üç aylık dönemlere ait kullanılabilir verilere ilişkin üç çubuk görürsünüz.

1. Daha sonra sol üst taraftaki simgelerden **Tümünü hiyerarşide bir düzey aşağı genişletin** seçeneğini belirleyin.

1. Hiyerarşide her ayın sonuçlarını gösteren en düşük düzeye inmek için bu işlemi bir kez daha tekrarlayın.

    ![Aya göre çubuğu gösteren çubuk grafiğin ekran görüntüsü](media/end-user-drill/power-bi-hierarchical-axis-datetime-2.png)

Görselleştirmenin dışında, hiyerarşinin her rapor için oluşturulan verilere yansıdığını görebiliriz. Sağ üst köşede üç noktayı ve sonra da **Verileri Göster**'i seçin. Aşağıdaki tablo, tek bir ayın veya tüm ayların detayına gitmenin sonuçlarını gösterir:

|Genişletme modu|Yıl|Çeyrek|Ay|Gün|
| --- |:---:|:---:|:---:|---|
|Tek|![tek yıl](./media/end-user-drill/power-bi-hierarchical-year.png)|![tek çeyrek](media/end-user-drill/power-bi-hierarchical-quarter.png)|![tek ay](./media/end-user-drill/power-bi-hierarchical-one-month.png)|![tek gün](media/end-user-drill/power-bi-hierarchical-one-day.png)|
|Tümü|![tüm yıllar](./media/end-user-drill/power-bi-hierarchical-year.png)|![tüm çeyrekler](media/end-user-drill/power-bi-hierarchical-quarter.png)|![tüm aylar](./media/end-user-drill/power-bi-hierarchical-all-month.png)|![tüm günler](media/end-user-drill/power-bi-hierarchical-all-day.png)|

Verilerin **Çeyrek** ve **Yıl** raporlarında aynı olduğuna dikkat edin. **Değerler** için belirtilen detay düzeyine gitmenizin ardından tek bir raporun daha ayrıntılı hale geldiğini ve "tüm aylar" raporunda daha fazla veri bulunduğunu görebilirsiniz.

### <a name="hierarchical-category-data"></a>Hiyerarşik kategori verileri

Koleksiyonlardan ve alt koleksiyonlardan modeli oluşturulan veriler hiyerarşiktir.

Konum verileri bunun iyi bir örneğidir. Bir veri kaynağında sütunları Ülke, Bölge, Şehir ve Posta Kutusu olan bir tablo düşünün. Aynı Ülkenin, Bölgenin ve Şehrin bulunduğu veriler hiyerarşiktir.

Bu örnekte:

1. [Perakende Analizi örneğini](../sample-datasets.md) izleyin. Şunlara bakan bir yığılmış sütun grafik oluşturun:

    | Kutu | Alan |
    | ---- | ----- |
    | Değer |Satışlar<br>\|\_ Total Units This Year |
    | Eksen | Mağaza<br>\|\_ Territory<br>\|\_ City - City değerini **Gösterge** kutusundan **Eksen** kutusuna sürüklemeniz gerekebilir.<br>\|\_ Postal Code<br>\|\_ Name |

    ![Bölgeye göre bu yıla ait birimlerin toplamını gösteren çubuk grafiğin ekran görüntüsü.](media/end-user-drill/power-bi-hierarchical-axis-category-1.png)

1. Detaya gitme modu açıkken, sol üst taraftaki simgelerden **Tümünü hiyerarşide bir düzey aşağı genişletin** seçeneğini üç kez belirleyin.

    Hiyerarşinin Bölge, Şehir ve Posta Kodu sonuçlarını gösteren en düşük düzeyinde olacaksınız.

    ![En düşük hiyerarşi düzeyini, en fazla ayrıntıyı gösteren çubuk grafiğin ekran görüntüsü.](media/end-user-drill/power-bi-hierarchical-axis-category-2.png)

Görselleştirmenin dışında, hiyerarşinin her rapor için oluşturulan verilere yansıdığını görebiliriz. Sağ üst köşede üç noktayı ve sonra da **Verileri Göster**'i seçin. Aşağıdaki tablo, tek bölge veya tüm bölgeler için detaya gitmenin sonuçlarını gösterir.

| Genişletme modu|Bölge|Şehir|Posta Kodu|Ad|
| ---|:---:|:---:|:---:|---|
|Tek|![tek bölge](./media/end-user-drill/power-bi-hierarchical-territory.png)|![tek şehir](media/end-user-drill/power-bi-hierarchical-one-territory-city.png)|![tek posta kodu](./media/end-user-drill/power-bi-hierarchical-one-territory-city-postal.png)|![tek ad](media/end-user-drill/power-bi-hierarchical-one-territory-city-postal-name.png)|
|Tümü|![tüm bölgeler](./media/end-user-drill/power-bi-hierarchical-territory.png)|![tüm şehirler](media/end-user-drill/power-bi-hierarchical-all-territory-city.png)|![tüm posta kodları](./media/end-user-drill/power-bi-hierarchical-all-territory-city-postal.png)|![tüm adlar](media/end-user-drill/power-bi-hierarchical-all-territory-city-postal-name.png)|

 Detaya gittikçe, **Tek** bir raporun daha belirgin hale geldiğini ve **Tüm** bölgeler raporunun daha fazla veri içerdiğini görebilirsiniz.

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

Bir görselleştirmeye tarih alanı eklenmesi hiyerarşi oluşturmuyorsa tarih alanı aslında bir tarih olarak kaydedilmemiş olabilir. Veri kümesi size aitse:

1. Veri kümesini Power BI Desktop'ta *Veri* görünümünde açın.

1. Tarihin bulunduğu sütunu seçin.

1. **Modelleme** sekmesinde **Veri Türü**'nü **Tarih** veya **Tarih/Saat** olarak değiştirin.

![Veri görünümü seçiminin ekran görüntüsü; sağ üst köşede Veri Türü'nü görebilirsiniz.](media/end-user-drill/power-bi-change-data-type2.png)

Rapor sizinle paylaşıldıysa değişikliği yapmasını istemek için raporun sahibi ile iletişime geçin.

## <a name="next-steps"></a>Sonraki adımlar

[Power BI raporlarındaki görselleştirmeler](../visuals/power-bi-report-visualizations.md)

[Power BI raporları](end-user-reports.md)

[Power BI - Temel Kavramlar](end-user-basic-concepts.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)
