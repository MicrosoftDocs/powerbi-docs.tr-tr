---
title: "Öğretici: Power BI Desktop'ta Excel çalışma kitabından muhteşem raporlar elde etme"
description: Bu öğreticide Excel çalışma kitabından hızla etkileyici bir rapor oluşturma işlemi gösterilir.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: pbi-reports-dashboards
ms.topic: tutorial
ms.date: 10/13/2020
LocalizationGroup: Data from files
ms.openlocfilehash: b984c0f6ebee6cdcc9982956701f3a112be74ab7
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96413208"
---
# <a name="tutorial-from-excel-workbook-to-stunning-report-in-power-bi-desktop"></a>Öğretici: Power BI Desktop'ta Excel çalışma kitabından muhteşem raporlar elde etme

Bu öğreticide 20 dakikada başından sonuna kadar güzel bir rapor oluşturacaksınız! 

:::image type="content" source="media/desktop-excel-stunning-report/power-bi-excel-formatted-report.png" alt-text="Tamamlanmış Power BI raporunun ekran görüntüsü."::: 

Yöneticiniz en son satış rakamlarınızı içeren bir rapor görmek istiyor. Şu konuları içeren bir yönetici özeti istendi: 

- En kârlı ay ve yıl hangisiydi? 
- Şirketin en başarılı olduğu yer neresi (ülkeye göre)? 
- Şirket hangi ürüne ve segmente yatırım yapmaya devam etmeli? 

Örnek finans çalışma kitabımızı kullanarak bu raporu kısa süre içinde oluşturabiliriz. Raporun son hali aşağıdaki gibi görünecek. Başlayalım! 

Bu öğreticide aşağıdakilerin nasıl yapılacağını öğreneceksiniz:

> [!div class="checklist"]
> * Örnek verileri iki farklı şekilde indirme
> * Birkaç dönüştürmeyle verilerinizi hazırlama
> * Başlığı, üç görseli ve dilimleyicisi olan bir rapor oluşturma
> * Raporunuzu iş arkadaşlarınızla paylaşabilmek için Power BI hizmetinde yayımlama

## <a name="prerequisites"></a>Önkoşullar

- Başlamadan önce [Power BI Desktop'ı indirmelisiniz](https://powerbi.microsoft.com/desktop/).
- Raporunuzu Power BI hizmetinde yayımlamayı planlıyorsanız ve henüz kaydolmadıysanız, [ücretsiz denemeye kaydolun](https://app.powerbi.com/signupredirect?pbi_source=web).

## <a name="get-data"></a>Verileri alma 

Bu öğreticide kullanılan verileri almak için iki farklı yöntemden birini seçebilirsiniz.

### <a name="get-data-in-power-bi-desktop"></a>Power BI Desktop’ta veri alma

Power BI Desktop'ı açtıktan sonra boş tuvalde **Örnek veri kümesini deneyin**'i seçin.

:::image type="content" source="media/desktop-excel-stunning-report/power-bi-desktop-canvas-sample-dataset.png" alt-text="Tuval üzerindeki Örnek veri kümesini deneyin seçeneğinin ekran görüntüsü."::: 

Bu öğreticiye Power BI Desktop'tan ulaştıysanız **Verileri yükleyin**'i seçin.

:::image type="content" source="media/desktop-excel-stunning-report/power-bi-two-ways-load-data.png" alt-text="Örnek verileri kullanmaya yönelik iki yöntemi ve Verileri yükleyin seçeneğini gösteren ekran görüntüsü.":::

### <a name="download-the-sample"></a>Örneği indirme

İsterseniz örnek çalışma kitabını doğrudan indirebilirsiniz. 

1. [Financial Sample Excel çalışma kitabını](https://go.microsoft.com/fwlink/?LinkID=521962) indirin.
1. Power BI Desktop'ı açın.
1. **Giriş** sekmesinin **Veri** bölümünde **Excel**'i seçin.
1. Örnek çalışma kitabını kaydettiğiniz yere gidin ve **Aç**'ı seçin.

## <a name="prepare-your-data"></a>Verilerinizi hazırlama 

**Gezgin**'de verileri *dönüştürme* veya *yükleme* seçeneğiniz vardır. Gezgin verilerinizin önizlemesini sağladığından doğru veri aralığını aldığınızı doğrulayabilirsiniz. Sayısal veri türleri italik yazılır. Değişiklik yapmanız gerekirse verilerinizi yüklemeden önce dönüştürün. Görselleştirmelerin daha sonra kolayca okunmasını sağlamak için verileri şimdi dönüştürmek istiyoruz. Yaptığınız her dönüştürmede, bunun **Sorgu Ayarları**'nın altındaki **Uygulanan Adımlar** listesine eklendiğini görürsünüz 

1. **Financials** tablosunu ve **Veri Dönüştürme**'yi seçin. 

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-financial-navigator.png" alt-text="Finansal örnek verileri içeren Power BI Gezgini'nin ekran görüntüsü."::: 

1. **Units Sold** (Satılan Birim Sayısı) sütununu seçin. **Giriş** sekmesinde **Veri Türü**'nü ve sonra da **Tamsayı**'yı seçin. Sütun türünü değiştirmek için **Mevcut olanı değiştir**'i seçin. 

    Kullanıcıların en sık uyguladığı veri temizleme adımı veri türlerini değiştirmektir. Bu örnekte satılan birim sayısı ondalık biçimdedir. Satılan birim sayısının 0,2 veya 0,5 olması sizce de anlamsız değil mi? Bu nedenle bu sayıyı tamsayı olarak değiştirelim. 

    :::image type="content" source="media/desktop-excel-stunning-report/power-query-whole-number.png" alt-text="Ondalık sayıyı tamsayı olarak değiştirme işleminin ekran görüntüsü."::: 

1. **Segment** sütununu seçin. **Dönüştür** sekmesinde **Biçim**'i ve sonra da **BÜYÜK HARF**'i seçin.

    Ayrıca segmentlerin daha sonra grafikte daha kolay görünür olmasını sağlamak istiyoruz. Şimdi Segment sütununu biçimlendirelim. 

     :::image type="content" source="media/desktop-excel-stunning-report/power-query-upper-case.png" alt-text="Küçük harfli başlıkları büyük harfe dönüştürme işleminin ekran görüntüsü.":::

1. Şimdi de **Month Name** (Ay Adı) olan sütun adını **Month** (Ay) olarak kısaltalım. **Month Name** sütununa çift tıklayın ve yalnızca **Month** olarak yeniden adlandırın.  

     :::image type="content" source="media/desktop-excel-stunning-report/power-query-month-name.png" alt-text="Sütun adını kısaltma işleminin ekran görüntüsü.":::

1. **Product** (Ürün) sütununda açılan listeyi seçin ve **Montana**'nın yanındaki kutuyu temizleyin. 

     Montana ürününün geçen ay sonlandırıldığını biliyoruz, dolayısıyla karışıklığı önlemek için bu verilerin raporumuzdan filtrelenmesini istiyoruz. 

     :::image type="content" source="media/desktop-excel-stunning-report/power-query-montana.png" alt-text="Montana değerlerini silme işleminin ekran görüntüsü.":::

1. Her dönüştürmenin **Sorgu Ayarları**'nın altındaki **Uygulanan Adımlar** listesine eklendiğini görürsünüz.

    :::image type="content" source="media/desktop-excel-stunning-report/power-query-applied-steps.png" alt-text="Uygulanan adımlar listesinin ekran görüntüsü.":::

1. **Giriş** sekmesine dönüp **Kapat ve Uygula**'yı seçin. Verilerimiz raporu oluşturmak için neredeyse hazır durumda. 

    Alanlar listesinde Sigma simgesini görüyor musunuz? Power BI bu alanların sayısal olduğunu algıladı. Power BI tarih alanını da takvim simgesiyle gösterir.

     :::image type="content" source="media/desktop-excel-stunning-report/power-bi-fields-list-sigmas-date.png" alt-text="Sayısal alanlar ve tarih alanı içeren Alanlar listesinin ekran görüntüsü.":::

### <a name="extra-credit-write-a-measure-in-dax"></a>Ek çalışma: DAX dilinde ölçü yazma

*DAX* formül dilinde *ölçüler* yazmak, veri modellemesi açısından son derece güçlü bir araçtır. Power BI belgelerinde DAX hakkında öğrenebileceğiniz çok fazla bilgi sağlanır. Şimdilik temel bir ölçü yazalım ve iki tabloyu birleştirelim. 

1. Sol tarafta **Veri Görünümü**'nü seçin. 
 
    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-data-view.png" alt-text="Veri Görünümü simgesinin ekran görüntüsü.":::

1. **Giriş** şeridinde **Yeni Tablo**'yu seçin. 

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-new-table.png" alt-text="Yeni Tablo simgesinin ekran görüntüsü.":::

1. 1 Ocak 2013 ile 31 Aralık 2014 arasındaki tüm verilerin Calendar (Takvim) tablosunu oluşturmak için bu ölçüyü yazın.  

    `Calendar = CALENDAR(DATE(2013,01,01),Date(2014,12,31))` 

2. İşlemek için onay işaretini seçin.

     :::image type="content" source="media/desktop-excel-stunning-report/power-bi-dax-expression.png" alt-text="DAX ifadesinin ekran görüntüsü.":::

1. Şimdi sol tarafta **Model Görünümü**'nü seçin. 

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-model-view.png" alt-text="Model Görünümü simgesinin ekran görüntüsü.":::

1. Tabloları birleştirmek için Financials tablosundan **Date** (Tarih) alanını Calendar tablosundaki **Date** alanına sürükleyin ve iki arasında bir *ilişki* oluşturun.  

     :::image type="content" source="media/desktop-excel-stunning-report/power-bi-date-relationship.png" alt-text="Date alanları arasındaki ilişkinin ekran görüntüsü.":::

## <a name="build-your-report"></a>Raporunuzu oluşturma 

Artık verilerinizi dönüştürdüğünüze ve yüklediğinize göre raporunuzu oluşturmanın zamanı geldi. Sağ taraftaki Alanlar bölmesinde, oluşturduğunuz veri modelindeki alanları görürsünüz. 

Şimdi bir kerede bir görsel olmak üzere raporun son halini oluşturalım. 

:::image type="content" source="media/desktop-excel-stunning-report/power-bi-report-by-numbers.png" alt-text="Rapordaki tüm öğelerin numaralandırılmış ekran görüntüsü.":::

### <a name="visual-1-add-a-title"></a>Görsel 1: Başlık ekleme 

1. **Ekle** şeridinde **Metin Kutusu**'nu seçin. “Yönetici Özeti – Finans Raporu” yazın. 
1. Yazdığınız metni seçin. Yazı tipi boyutunu 20 ve kalın olarak ayarlayın. 

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-title-executive-summary.png" alt-text="Başlığı biçimlendirme işleminin ekran görüntüsü.":::

1. Görselleştirmeler bölmesinde **Arka Plan**'ı **Kapalı** olarak ayarlayın. 
1. Kutuyu tek satıra sığdırmak için yeniden boyutlandırın. 

### <a name="visual-2-profit-by-date"></a>Görsel 2: Tarihe göre kar 

Şimdi en yüksek kârın elde edildiği ayı ve yılı görmek için bir çizgi grafik oluşturacaksınız. 

1. Alanlar bölmesindeki **Profit** (Kâr) alanını rapor tuvalinde boş bir alana sürükleyin. Varsayılan olarak Power BI tek sütunu (Profit) olan bir sütun grafiği görüntüler. 
1. **Date** alanını aynı görsele sürükleyin. Power BI, iki yıla göre kârı gösterecek şekilde sütun grafiğini güncelleştirir.

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-column-year.png" alt-text="Profit sütun grafiğinin ekran görüntüsü.":::

1. Görselleştirmeler bölmesinin **Alanlar** bölümünde, **Eksen** değerinin açılan listesini seçin. **Date Hierarchy** (Tarih Hiyerarşisi) olan **Date** öğesini **Date** olarak değiştirin.

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-date-hierarchy.png" alt-text="Date Hierarchy'yi Date olarak değiştirme işleminin ekran görüntüsü.":::

    Power BI, her ayın kârını gösterecek şekilde sütun grafiğini güncelleştirir.

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-column-month.png" alt-text="Aya göre sütun grafiğinin ekran görüntüsü.":::

1. Görselleştirmeler bölmesinde, görselleştirme türünü **Çizgi grafik** olarak değiştirin. 

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-profit-date-line-chart.png" alt-text="Sütun grafiğini çubuk grafiğe dönüştürme işleminin ekran görüntüsü.":::

    Artık en yüksek kârın Aralık 2014'te elde edildiğini kolayca görebilirsiniz.

### <a name="visual-3-profit-by-country"></a>Görsel 3: Ülkeye göre kar 

En yüksek kârların hangi ülkede elde edildiğini görmek için bir harita oluşturun.

1. Alanlar bölmesinde **Country** (Ülke) alanını rapor tuvalinizdeki boş bir alana sürükleyerek haritayı oluşturun.
1. **Profit** alanını haritaya sürükleyin.

    Power BI her bir konumun göreceli kârını temsil eden balonlar içeren bir harita görseli oluşturur. 

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-map-visual.png" alt-text="Harita grafiği oluşturma işleminin ekran görüntüsü.":::

    Avrupa'da, Kuzey Amerika'dan daha iyi bir performans elde edilmiş gibi görünüyor. 

### <a name="visual-4-sales-by-product-and-segment"></a>Görsel 4: Ürün ve Segment göre satışlar 

Hangi şirketlere ve segmentlere yatırım yapılacağını saptamak için bir çubuk grafik oluşturun.

1. Oluşturduğunuz iki grafiği tuvalin üst yarısında yan yana gelecek şekilde sürükleyin. Tuvalin sol tarafında biraz yer ayırın. 
1. Rapor tuvalinizin alt yarısında boş bir alan seçin. 

1. Alanlar bölmesinde **Sales**, **Product** ve **Segment** alanlarını seçin. 

    Power BI otomatik olarak kümelenmiş bir sütun grafik oluşturur. 

1. Grafiği sürükleyerek, üstteki iki grafiğin altında kalan alanı kaplayacak kadar genişletin.

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-clustered-column-chart.png" alt-text="Kümelenmiş sütun grafiğin ekran görüntüsü.":::

    Şirketin Paseo ürününe yatırım yapmaya devam etmesi ve Small Business (Küçük İşletme) ile Government (Kamu) segmentlerini hedeflemesi gerekiyor gibi görünüyor.  

### <a name="visual-5-year-slicer"></a>Görsel 5: Yıl dilimleyicisi 

Dilimleyiciler, rapor sayfasındaki görselleri belirli bir seçime göre filtrelemeye yönelik değerli bir araçtır. Bu örnekte her ayın veya yılın performansı gösterilecek şekilde görseli daraltan bir dilimleyici oluşturabilirsiniz.  

1. Alanlar bölmesinde **Date** alanını seçin ve tuvalin sol tarafındaki boş alana sürükleyin. 
2. Görselleştirmeler bölmesinde **Dilimleyici**'yi seçin. 
3. Görselleştirmeler bölmesinin Alanlar bölmesinde, **Alanlar**'daki açılan listeyi seçin. Yalnızca Year (Yıl) ve Month (Ay) kalacak şeklide Quarter (Çeyrek) ve Day (Gün) öğelerini kaldırın. 

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-date-hierarchy-trim.png" alt-text="Date Hierarchy'yi değiştirme işleminin ekran görüntüsü.":::

4. Her yılı genişletin ve tüm ayların görünür olması için görseli yeniden boyutlandırın.

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-hierarchy-date-slicer.png" alt-text="Tarih hiyerarşisi dilimleyicisinin ekran görüntüsü.":::

Artık yöneticiniz yalnızca 2013 verilerini görmek isterse dilimleyiciyi kullanarak yıllar arasında veya her yılın belirli aylarına geçiş yapabilirsiniz. 

### <a name="extra-credit-format-the-report"></a>Ek çalışma: Raporu biçimlendirme

Bu raporda görünümünü biraz daha geliştirecek basit biçimlendirmeler yapmak istiyorsanız, işte birkaç kolay adım. 

**Tema**

- **Görünüm** şeridinde temayı **Yönetici** olarak değiştirin.  

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-theme-executive.png" alt-text="Yönetici temasını seçme işleminin ekran görüntüsü."::: 

**Görselleri süsleme** 

Görselleştirmeler bölmesinin **Biçim** sekmesinde aşağıdaki değişiklikleri yapın.

:::image type="content" source="media/desktop-excel-stunning-report/power-bi-format-tab-visualizations.png" alt-text="Görselleştirmeler bölmesindeki Biçim sekmesinin ekran görüntüsü.":::

1. Görsel 2'yi seçin. **Başlık** bölümünde **Başlık metni**'ni “Profit by Month and Year” (Aya ve Yıla Göre Kâr) olarak ve **Metin boyutunu**'da **16 nokta** olarak değiştirin. **Gölge** ayarını **Açık** olarak değiştirin. 

1. Görsel 3'ü seçin. **Harita stilleri** bölümünde **Tema** ayarını **Gri tonlama** olarak değiştirin. **Başlık** bölümünde, başlığın **Metin boyutu**'nu **16 nokta** olarak değiştirin. **Gölge** ayarını **Açık** olarak değiştirin.

1. Görsel 4'ü seçin. **Başlık** bölümünde, başlığın **Metin boyutu**'nu **16 nokta** olarak değiştirin. **Gölge** ayarını **Açık** olarak değiştirin.

1. Görsel 5'i seçin. **Seçim denetimleri** bölümünde **"Tümünü seç" seçeneğini göster** ayarını **Açık** olarak değiştirin. **Dilimleyici üst bilgisi** bölümünde **Metin boyutu** ayarını **16 nokta** olarak artırın. 

**Başlık için bir arka plan şekli ekleme**

1. **Ekle** şeridinde **Şekiller** > **Dikdörtgen**'i seçin. Bunu sayfanın en üstüne yerleştirin, sonra sayfanın genişliğine ve başlığın yüksekliğine uyacak şekilde genişletin. 
1. **Şekli biçimlendir** bölmesinin **Çizgi** bölümünde **Saydamlık** ayarını **%100** olarak değiştirin. 
1. **Dolgu** bölümünde **Dolgu rengi** ayarını **Tema rengi 5 #6B91C9** (mavi) olarak değiştirin. 

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-theme-color-5.png" alt-text="Tema rengi 5'in ekran görüntüsü.":::

1. **Biçim** sekmesinde **Arkaya gönder** > **En arkaya gönder**'i seçin. 
1. Görsel 1'deki başlık metnini seçin ve yazı tipi rengini **Beyaz** olarak değiştirin. 

**Görsel 2 ve 3 için bir arka plan şekli ekleme**

1. **Ekle** sekmesinde **Şekiller** > **Dikdörtgen**'i seçin ve bunu Görsel 2 ve 3'ün genişliğiyle yüksekliğine uyacak şekilde genişletin. 
1. **Şekli biçimlendir** bölmesinin **Çizgi** bölümünde **Saydamlık** ayarını **%100** olarak değiştirin. 
1. **Biçim** sekmesinde **Arkaya gönder** > **En arkaya gönder**'i seçin. 

### <a name="finished-report"></a>Tamamlanmış rapor

Raporun görünümü geliştirilmiş son hali şöyle görünür:  

:::image type="content" source="media/desktop-excel-stunning-report/power-bi-excel-formatted-report.png" alt-text="Son, biçimlendirilmiş raporun ekran görüntüsü.":::

Özette, bu rapor yöneticinizin en önemleri sorularını yanıtlar: 

- En kârlı ay ve yıl hangisiydi? 

    Aralık 2014 

- Şirketin en başarılı olduğu ülke neresi? 

    Avrupa, özellikle de Fransa ve Almanya. 

- Şirket hangi ürüne ve segmente yatırım yapmaya devam etmeli? 

    Şirket Paseo ürününe yatırım yapmaya devam etmeli ve Small Business (Küçük İşletme) ile Government (Kamu) segmentlerini hedeflemelidir. 

## <a name="save-your-report"></a>Raporunuzu kaydedin

- **Dosya** menüsünde **Kaydet**'i seçin.

## <a name="publish-to-the-power-bi-service-to-share"></a>Paylaşmak için Power BI hizmetinde yayımlama 

Raporunuzu yöneticinizle ve iş arkadaşlarınızla paylaşmak için Power BI hizmetinde yayımlayın. Power BI hesabı olan iş arkadaşlarınızla paylaştığınızda, onlar raporunuzla etkileşimli çalışabilir ama değişiklikleri kaydedemez. 

1. Power BI Desktop'ta, **Giriş** şeridindeki **Yayımla**'yı seçin. 

    Power BI hizmetinde oturum açmanız gerekebilir. Henüz bir hesabınız yoksa [ücretsiz denemeye kaydolabilirsiniz](https://app.powerbi.com/signupredirect?pbi_source=web).

1. Power BI hizmetinde **Çalışma alanım** gibi bir hedef seçin, sonra da **Seç** düğmesini seçin.
1. **'dosya-adınız' öğesini Power BI'da aç**'ı seçin.

    :::image type="content" source="media/desktop-excel-stunning-report/open-power-bi.png" alt-text="Raporunuzu Power BI hizmetinde açma işleminin ekran görüntüsü.":::

    Tamamlanmış raporunuz tarayıcıda açılır.

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-excel-report-service.png" alt-text="Power BI hizmetindeki tamamlanmış Power BI raporunuzun ekran görüntüsü."::: 

1. Raporunuzu başkalarıyla paylaşmak için raporun en üstündeki **Paylaş**'ı seçin.

    :::image type="content" source="media/desktop-excel-stunning-report/power-bi-share-report.png" alt-text="Power BI hizmetinden raporunuzu paylaşma işleminin ekran görüntüsü.":::

## <a name="next-steps"></a>Sonraki adımlar

- [Öğretici: Excel’deki ve OData akışındaki satış verilerini analiz etme](../connect-data/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/).
