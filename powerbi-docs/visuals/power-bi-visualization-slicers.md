---
title: "Öğretici: Power BI'daki dilimleyiciler"
description: Power BI'da dilimleyiciler
author: v-thepet
ms.reviewer: ''
featuredvideoid: zIZPA0UrJyA
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: tutorial
ms.date: 10/22/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 808f27b94e53d5acf351772ef304f9cc69215007
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73880798"
---
# <a name="slicers-in-power-bi"></a>Power BI'da dilimleyiciler

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

Rapor okuyucularınızın genel satış ölçümlerine bakabilmesini ancak aynı zamanda tek Bölge Yöneticileri ve farklı zaman aralıkları için performansı vurgulayabilmesini istiyorsunuz. Ayrı raporlar veya karşılaştırmalı grafikler oluşturabilir ya da dilimleyicileri kullanabilirsiniz. Dilimleyici, rapordaki diğer görselleştirmelerde gösterilen veri kümesi bölümünü daraltan alternatif bir filtreleme yöntemidir. 

Bu öğreticide, liste ve tarih aralığı dilimleyicilerini oluşturma, biçimlendirme ve kullanma işlemlerinde size yol göstermek üzere ücretsiz [Perakende Analizi Örneği](../sample-retail-analysis.md) kullanılır. Dilimleyicileri biçimlendirme ve kullanma yöntemlerini keşfetmekten keyif alacağınızı umuyoruz. 

![dilimleyici](media/power-bi-visualization-slicers/slicer2.gif)

## <a name="when-to-use-a-slicer"></a>Dilimleyici ne zaman kullanılır?
Aşağıdakileri yapmak istediğinizde dilimleyicileri kullanmanız oldukça faydalı olacaktır:

* Daha kolay erişim sağlamak amacıyla, sık kullanılan veya önemli filtreleri rapor tuvalinde görüntülemek.
* Açılan bir listeyi açmak zorunda kalmadan, o sırada filtreli olan durumu daha kolay bir şekilde görüntülemek. 
* Veri tablolarında gereksiz ve gizli sütunlara göre filtreleme yapmak.
* Dilimleyicileri önemli görsellerin yanına koyarak daha odaklı raporlar oluşturmak.

Power BI dilimleyicileri aşağıdaki sınırlamalara sahiptir:

- Dilimleyiciler giriş alanlarını desteklemez.
- Detaya gitme özelliği, dilimleyiciler için desteklenmez.


## <a name="create-slicers"></a>Dilimleyici oluşturma

**Verileri Bölge Yöneticisine göre filtrelemek için yeni bir dilimleyici oluşturma**

Bu öğreticide [Perakende Analizi örneği .PBIX dosyası](https://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix) kullanılmıştır.

1. Menü çubuğunun sol üst köşesinden **Dosya** > **Aç**’ı seçin
   
2. **Perakende Analizi örneği PBIX dosyasının** kopyasını bulun

1. **Perakende Analizi örneği PBIX dosyasını** rapor görünümünde ![Rapor görünümü simgesinin ekran görüntüsü.](media/power-bi-visualization-kpi/power-bi-report-view.png) açın.

1. Seç ![Sarı sekmenin ekran görüntüsü.](media/power-bi-visualization-kpi/power-bi-yellow-tab.png) yeni bir sayfa ekleyin.

2. Genel Bakış sayfasında, tuvalde hiçbir şey seçili değilken **Görselleştirmeler** bölmesindeki **Dilimleyici** simgesini ![dilimleyici simgesi](media/power-bi-visualization-slicers/slicer-icon.png) seçerek yeni bir dilimleyici oluşturun. 
3. Dilimleyiciyi doldurmak için, yeni dilimleyici seçiliyken **Bölge** > **DM** seçeneğini belirleyin. Yeni dilimleyici, adların önünde seçim kutularının bulunduğu bir listedir. 
    
    ![yeni dilimleyici](media/power-bi-visualization-slicers/power-bi-new-slicer.png)
    
4. Dilimleyiciye yer açmak için dilimleyiciyi ve tuvalin üzerindeki diğer öğeleri yeniden boyutlandırıp sürükleyin. Dilimleyiciyi çok küçük boyutlandırırsanız dilimleyici öğelerinin kesileceğini unutmayın. 
5. Dilimleyici üzerindeki adları seçin ve sayfadaki diğer görselleştirmelere etkilerini not edin. Seçimlerini kaldırmak için adları tekrar seçin ve birden fazla ad seçmek için **Ctrl** tuşunu basılı tutun. Tüm adların seçilmesi, hiçbir adın seçilmemesiyle aynı etkiye sahiptir. 

6. Alternatif olarak, dilimleyicinizi biçimlendirmek için boya rulosu simgesini seçin. Çok fazla seçenek olduğu için bunların hepsini burada açıklayamayız. Bu yüzden, farklı şeyler deneyerek size uygun dilimleyiciyi oluşturun. Aşağıdaki örneklerde, ilk dilimleyicide yatay yönlendirme kullanılmış ve öğeler için renkli arka planlar tercih edilmiş. İkinci dilimleyici dikey tutulmuş ve daha standart bir görünüm için metin renklendirilmiş.

   ![yeni dilimleyici](media/power-bi-visualization-slicers/power-bi-filter-examples.png)
>[!TIP]
>Liste dilimleyici öğeleri varsayılan olarak artan düzende sıralanır. Sıralamayı tersine çevirerek öğeleri azalan düzene göre sıralamak için dilimleyicinin sağ üst köşesindeki üç noktayı ( **...** ) seçip **Azalan düzende sırala** seçeneğini belirleyin.

**Verileri tarih aralığına göre filtrelemek için yeni bir dilimleyici oluşturma**

1. Yeni bir görselleştirme oluşturmak için, tuval üzerinde hiçbir seçenek işaretli değilken, Alanlar bölmesindeki **Mağaza** listesini açın ve **Açılış Tarihi** öğesini Görselleştirmeler bölmesindeki **Değerler** kutusuna sürükleyin.
2. Yeni görselleştirme seçiliyken **Dilimleyici** simgesini seçerek yeni görselleştirmeyi bir dilimleyiciye dönüştürün. Bu dilimleyici, tarih aralığı doldurulmuş bir kaydırıcı denetimidir.
    
    ![yeni aralık dilimleyici](media/power-bi-visualization-slicers/power-bi-date-slicer.png)

    
4. Dilimleyiciye yer açmak için dilimleyiciyi ve tuvalin üzerindeki diğer öğeleri yeniden boyutlandırıp sürükleyin. Dilimleyici boyutu ile birlikte kaydırıcının yeniden boyutlandırıldığını ancak dilimleyiciyi çok küçük boyutlandırmanız durumunda kaybolduğunu ve tarihlerin kesildiğini unutmayın. 
4. Kaydırıcı ile farklı tarih aralıkları seçin veya daha kesin bir seçim için bir değer yazın ya da takvimi açın. Sayfadaki diğer görselleştirmelere etkilerini not edin.
    
    >[!NOTE]
    >Sayısal ve/veya tarih/saat veri türleri varsayılan olarak aralık kaydırıcı dilimleyicileri üretir. Şubat 2018 Power BI güncelleştirmesinden itibaren, tamsayı veri türü aralık kaydırıcıları artık ondalık basamakları göstermek yerine tam sayı değerlerine uymaktadır. 


5. Dilimleyici türünü değiştirmek için, dilimleyici seçiliyken fareyi dilimleyicinin sağ üst köşesine getirin, görüntülenen karatı açın ve **Liste** ya da **Önce** gibi diğer seçeneklerden birini belirleyin. Dilimleyici görünümünün ve seçim seçeneklerinin nasıl değiştiğine dikkat edin. 
 
    ![yeni aralık dilimleyici](media/power-bi-visualization-slicers/power-bi-between-slicer.png)


Tarih ve sayısal aralık dilimleyicileri oluşturma hakkında daha fazla bilgi için aşağıdaki videoyu izleyin ve [Power BI Desktop uygulamasındaki sayısal aralık dilimleyiciyi kullanma](../desktop-slicer-numeric-range.md) makalesine bakın.
   > [!NOTE]
   > Bu videoda Power BI Desktop’ın eski bir sürümü kullanılmaktadır.
   > 
   > 
<iframe width="560" height="315" src="https://www.youtube.com/embed/zIZPA0UrJyA" frameborder="0" allowfullscreen></iframe> 

## <a name="control-which-page-visuals-are-affected-by-slicers"></a>Hangi sayfa görsellerinin dilimleyicilerden etkilendiğini denetleme
Varsayılan olarak, rapor sayfalarındaki dilimleyiciler, birbirleri de dahil olmak üzere o sayfadaki diğer tüm görselleştirmeleri etkiler. Yeni oluşturduğunuz liste ve tarih kaydırıcılarından değerleri seçerken diğer görselleştirmelere etkilerini not edin. Filtrelenen veriler her iki dilimleyicide seçilen değerlerin bir kesişimidir. 

Bazı sayfa görselleştirmelerini diğerlerinden etkilenmemesi için hariç tutmak üzere **Görsel etkileşimler**’i kullanabilirsiniz. **Genel Bakış** sayfasındaki "FiscalMonth ve Bölge Yöneticisine Göre Toplam Satış Değişimi" grafiği, her zaman görünür tutmak istediğiniz Aya Göre Bölge Yöneticileri için genel karşılaştırmalı verileri gösterir. Dilimleyici seçimlerinin bu grafikte filtrelenmesini önlemek için **Görsel etkileşimler**’i kullanabilirsiniz. 

1. **Bölgenin Aylık Satışları** sayfasında Bölge Yöneticisi dilimleyicisi seçiliyken:
    - Power BI Desktop’ta **Görsel Araçlar** bölümündeki **Biçim** menüsünü seçin ve **Etkileşimleri düzenle** seçeneğini belirleyin.
   
   Sayfadaki diğer tüm görsellerin üzerinde filtre denetimleri ![filtre denetimleri](media/power-bi-visualization-slicers/filter-controls.png) görünür. Başlangıçta, tüm **Filtre** simgeleri seçilidir.
   
2. Dilimleyicinin filtrelemesini durdurmak için **FiscalMonth ve Bölge Yöneticisine Göre Toplam Satış Değişimi** grafiğinin üzerindeki **Hiçbiri** simgesini seçin. 
3. Bu dilimleyicinin filtrelemesini durdurmak için **Ay** dilimleyicisini seçin ve yine **FiscalMonth ve Bölge Yöneticisine Göre Toplam Satış Değişimi** grafiğinin üzerindeki **Hiçbiri** simgesini seçin. Şimdi dilimleyicilerde ad ve tarih aralıklarını seçtiğinizde, FiscalMonth ve Bölge Yöneticisine Göre Toplam Satış Değişimi grafiği değişmez. 

Etkileşimleri düzenleme hakkında daha fazla bilgi için bkz. [Power BI raporlarındaki görsel etkileşimler](../service-reports-visual-interactions.md).

## <a name="sync-and-use-slicers-on-other-pages"></a>Diğer sayfalardaki dilimleyicileri eşitleme ve kullanma
Şubat 2018 tarihinde yapılan Power BI güncelleştirmesinden itibaren bir dilimleyiciyi eşitleyebilir ve bir rapordaki tüm sayfalarda kullanabilirsiniz. 

Mevcut raporun **Bölgenin Aylık Satışları** sayfasında **Bölge Yöneticisi** dilimleyicisi bulunuyor. Peki bu dilimleyiciyi **Genel Bakış** sayfasına eklemek istersek ne yapabiliriz? **Yeni Mağazalar** sayfasında da dilimleyici bulunur. Ancak, bu dilimleyici yalnızca **Mağaza Adı** bilgisini sağlar. **Eşitleme dilimleyicisi** bölmesiyle herhangi bir sayfada yapılan dilimleyici seçimlerinin üç sayfadaki tüm görselleştirmeleri etkilemesi amacıyla yeni **Bölge Yöneticisi** dilimleyicisini bu sayfalarla eşitleyebiliriz.

1. Power BI Desktop’ta, **Görünüm** menüsünden **Eşitleme Dilimleyicileri**’ni seçin.

    ![dilimleyicileri eşitleme](media/power-bi-visualization-slicers/power-bi-slicer-view-sync.png)

1.  **Filtreler** ve **Görselleştirmeler** bölmesinin arasında **Eşitleme Dilimleyicileri** bölmesi görüntülenir.  

    ![dilimleyicileri eşitleme](media/power-bi-visualization-slicers/power-bi-slicer-sync-pane.png)

1. **Bölgenin Aylık Satışları** sayfasında **Bölge Yöneticisi** dilimleyicisini seçin. 
    
    ![dilimleyicileri eşitleme](media/power-bi-visualization-slicers/9-sync-slicers.png)
    
3. **Bölgenin Aylık Satışları** dilimleyicisini bu sayfalarla eşitlemek için **Eşitle** sütununda **Yeni Mağazalar** sayfasını ve **Genel Bakış** sayfasını seçin. 
    
3. **Görünen** sütununda **Yeni Mağazalar** sayfasını ve **Genel Bakış** sayfasını seçin. **Eşitleme dilimleyicileri** bölmeniz aşağıdaki görüntüye benzer şekilde görünmelidir:

    ![dilimleyicileri eşitleme](media/power-bi-visualization-slicers/power-bi-sync-slicer-finished.png)

1. Dilimleyiciyi eşitlemenin ve diğer sayfalarda görünür yapmanın etkilerini gözlemleyin. **Bölge Aylık Satışları** sayfasında **Bölge Yöneticisi** dilimleyicisi artık **Genel Bakış** sayfasındaki seçimlerin aynısını gösterir. **Yeni Depolar** sayfasında, **Bölge Yöneticisi** dilimleyicisindeki seçimler **Depo Adı** dilimleyicisindeki seçimleri etkiler. 
    
    >[!TIP]
    >Dilimleyici, eşitlenmiş sayfalarda ilk olarak özgün sayfa ile aynı boyut ve konumda görünse de, çeşitli sayfalardaki eşitlenmiş dilimleyicileri birbirinden bağımsız olarak taşıyabilir, yeniden boyutlandırabilir ve biçimlendirebilirsiniz. 

>[!NOTE]
>Bir dilimleyiciyi bir sayfa ile eşitlemenize karşın o sayfada görünür hale getirmezseniz, diğer sayfalarda yapılan dilimleyici seçimleri sayfadaki verileri filtrelemeye devam eder.
 
## <a name="format-slicers"></a>Biçim dilimleyiciler
Dilimleyici türüne bağlı olarak farklı biçimlendirme seçenekleri mevcuttur. **Yatay** yönü, **Duyarlı** düzeni ve **Öğe** renklendirmeyi kullanarak standart liste öğeleri yerine düğme ya da kutucuklar oluşturabilir ve dilimleyici öğelerini farklı ekran boyutları ve düzenlerine göre yeniden boyutlandırabilirsiniz.  

1. Herhangi bir sayfada **Bölge Yöneticisi** dilimleyicisi seçiliyken, **Görselleştirmeler** bölmesinde **Biçim** simgesini ![biçim simgesi](media/power-bi-visualization-slicers/power-bi-paintroller.png) seçerek biçimlendirme denetimlerini görüntüleyin. 
    
    ![biçimlendirme](media/power-bi-visualization-slicers/3-format.png)
    
2. Seçenekleri görüntülemek ve düzenlemek için her kategorinin yanındaki açılan okları seçin. 

### <a name="general-options"></a>Genel seçenekler
1. **Anahat rengi**’nin altında kırmızıyı seçin ve **Anahat ağırlığı**’nı “2” olarak değiştirin. Etkinleştirildiğinde bu, üst bilgi ve öğe ana hatlarının veya alt çizgilerinin rengini ve kalınlığını ayarlar. 
2. **Yön** altında varsayılan ayar **Dikey**’dir. Yatay yönde düzenlenmiş kutucuk veya düğmelerle bir dilimleyici oluşturmak için **Yatay**’ı seçin ve dilimleyiciye sığmayan öğelere erişmek için okları kaydırın.
    
    ![yatay](media/power-bi-visualization-slicers/4-horizontal.png)
    
3. Dilimleyici öğelerinin boyut ve düzenini görünüm ekranına ve dilimleyici boyutuna göre değiştirmek için **Duyarlı** düzeni etkinleştirin. Liste dilimleyicileri için duyarlı düzen yalnızca yatay yönde kullanılabilir ve küçük ekranlarda öğelerin kesilmesini önler. Aralık kaydırıcı dilimleyiciler için duyarlı biçimlendirme, kaydırıcının stilini değiştirir ve daha esnek bir yeniden boyutlandırma sağlar. Her iki dilimleyici türü de çok küçük boyutlarda filtre simgeleri haline gelir. 
    
    ![esnek](media/power-bi-visualization-slicers/5-responsive.png)
    
    >[!NOTE]
    >Esnek düzen değişiklikleri, ayarladığınız üst bilgi ve öğe biçimlendirmesini geçersiz kılabilir. 
    
4. **X Konumu**, **Y Konumu**, **Genişlik** ve **Yükseklik** bölümündeki sayısal duyarlıkla dilimleyici konumunu ve boyutunu ayarlayın dilimleyiciyi doğrudan tuval üzerinde taşıyıp yeniden boyutlandırın. Farklı öğe boyutları ve düzenlemelerle denemeler yapın ve duyarlı biçimlendirmenin uygun şekilde nasıl değiştiğine dikkat edin.  

    ![yatay düğmeler](media/power-bi-visualization-slicers/6-buttons.png)

Yatay yönlendirme ve duyarlı düzen hakkında daha fazla bilgi için bkz. [Power BI’da yeniden boyutlandırabileceğiniz duyarlı bir dilimleyici oluşturma](../power-bi-slicer-filter-responsive.md).

### <a name="selection-controls-options-list-slicers-only"></a>Seçim denetimi seçenekleri (yalnızca liste dilimleyiciler)
1. **Tümünü Seç’i Göster** seçeneği varsayılan olarak **Kapalı**’dır. Dilimleyiciye, açılıp kapatıldığında tüm öğeleri seçen veya tüm öğelerin seçimini kaldıran bir **Tümünü Seç** öğesi eklemek için bu seçeneği **Açık** duruma getirin. Tüm öğeler seçiliyken öğeye tıklandığında veya dokunulduğunda öğenin seçimi kaldırılır ve “is-not” türünde bir filtreye izin verilir. 
    
    ![tümünü seç](media/power-bi-visualization-slicers/7-select-all.png)
    
2. **Tek Seçim** varsayılan olarak **Açık**’tır. Öğeye tıklandığında veya dokunulduğunda bu öğe seçilir, tıklama veya dokunma sırasında **Ctrl** tuşu basılı tutulduğunda ise birden çok öğe seçilir. **Ctrl** tuşu basılı tutulmadan birden çok öğenin seçilmesini sağlamak için **Tek Seçim**’i **Kapalı** duruma getirin. Bir öğeye tıklandığında veya dokunulduğunda bu öğenin seçimi kaldırılır. 

### <a name="title-options"></a>Başlık seçenekleri
**Başlık** varsayılan olarak **Açık**’tır ve dilimleyicinin üst tarafında veri alanı adını gösterir. 
1. **Yazı tipi rengini** kırmızı, **Metin boyutunu** 14 pt ve **Yazı tipi ailesini** Arial Black olarak ayarlamak ve metni **Ortaya Hizalamak** için başlık metnini biçimlendirin. 


### <a name="item-options-list-slicers-only"></a>Öğe seçenekleri (yalnızca liste dilimleyiciler)
1. **Yazı tipi rengini** siyah, **Arka planı** açık kırmızı, **Metin boyutunu** 10 pt, **Yazı tipi ailesini** ise Arial olarak ayarlayacak şekilde öğe metnini ve arka planını biçimlendirin. 
2. **Anahat** altında, her bir öğenin çevresine **Genel** seçeneklerde ayarladığınız boyuta ve renge sahip bir kenarlık çizmek için **Çerçeve** seçeneğini belirleyin. 
    
    ![biçimlendirilmiş](media/power-bi-visualization-slicers/8-formatted.png)
    
    >[!TIP]
    >- **Yön > Yatay** kullanıldığında, seçimi kaldırılan öğeler seçilen metin ve arka plan renklerini gösterirken seçilen öğeler, genellikle beyaz metinli siyah arka plan olan sistem varsayılanını kullanır.
    >- **Yön > Dikey** kullanıldığında, öğeler her zaman ayarlanan renkleri gösterir ve seçim kutuları seçildiğinde her zaman siyah olur. 

### <a name="datenumeric-inputs-and-slider-options-range-slider-slicers-only"></a>Tarih/sayısal girişler ve Kaydırıcı seçenekleri (yalnızca aralık kaydırıcı dilimleri)
- Tarih/sayısal giriş seçenekleri, liste dilimleyicilere yönelik **Öğe** seçenekleriyle aynıdır, ancak burada bir **Anahat** veya alt çizgi yoktur.
- Kaydırıcı seçenekleri, aralık kaydırıcının rengini ayarlamanıza veya kaydırıcıyı **Kapalı** duruma getirerek yalnızca sayısal girişleri bırakmanıza olanak tanır.

### <a name="other-formatting-options"></a>Diğer biçimlendirme seçenekleri
Diğer biçimlendirme seçenekleri varsayılan olarak kapalıdır. **Açık** duruma getirildiğinde: 
- **Arka plan:** Genel dilimleyiciye bir arka plan rengi ekler ve bunun saydamlığını ayarlar.
- **Görünüşü kilitle:** Dilimleyici yeniden boyutlandırıldıysa dilimleyicinin şeklini korur.
- **Kenarlık:** Dilimleyicinin çevresine 1 piksel kenarlık ekler ve bunun rengini ayarlar. (Bu dilimleyici kenarlığı Genel Anahat ayarlarından ayrıdır ve bunlardan etkilenmez.) 

## <a name="next-steps"></a>Sonraki adımlar
[Power BI'daki görselleştirme türleri](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Power BI’da tablolar](power-bi-visualization-tables.md)

