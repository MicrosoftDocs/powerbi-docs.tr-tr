---
title: "Öğretici: Power BI Desktop'ta kendi ölçülerinizi oluşturma"
description: "Öğretici: Power BI Desktop'ta kendi ölçülerinizi oluşturma"
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: tutorial
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Learn more
ms.openlocfilehash: 59567b62c44a386b3890f68de49b9f7aed76aa45
ms.sourcegitcommit: 2aa83bd53faad6fb02eb059188ae623e26503b2a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73019339"
---
# <a name="tutorial-create-your-own-measures-in-power-bi-desktop"></a>Öğretici: Power BI Desktop'ta kendi ölçülerinizi oluşturma
Power BI Desktop’taki en güçlü veri analizi çözümlerinin bazılarını ölçüler kullanarak oluşturabilirsiniz. Ölçüler, raporlarınızla etkileşim kurarken verileriniz üzerinde hesaplamalar gerçekleştirerek size yardımcı olur. Bu öğretici, Power BI Desktop’ta temel ölçüleri anlama ve kendi ölçülerinizin bazılarını oluşturma konusunda size yol gösterir.

### <a name="prerequisites"></a>Önkoşullar
- Bu öğretici, Power BI Desktop’ı daha gelişmiş modeller oluşturmak için kullanmaya alışmış Power BI kullanıcılarına yöneliktir. Verileri içeri aktarmak, birden çok ilişkili tabloyla çalışmak ve Rapor Tuvali'ne alan eklemek için Veri Al ve Sorgu Düzenleyicisi özelliklerini kullanmaya alışmış olmanız gerekir. Power BI Desktop'a yeni başladıysanız [Power BI Desktop ile çalışmaya başlama](desktop-getting-started.md) makalesine mutlaka göz atın.
  
- Kurgusal Contoso, Inc. şirketinin çevrimiçi satış verilerini içeren [Contoso Sales Sample for Power BI Desktop](http://download.microsoft.com/download/4/6/A/46AB5E74-50F6-4761-8EDB-5AE077FD603C/Contoso%20Sales%20Sample%20for%20Power%20BI%20Desktop.zip) dosyasını indirin. Bu veriler veritabanından içeri aktarılmıştır; dolayısıyla veri kaynağına bağlanamaz veya bunu Sorgu Düzenleyicisi'nde görüntüleyemezsiniz. Dosyayı bilgisayarınızda ayıklayıp Power BI Desktop’ta açın.

## <a name="understand-measures"></a>Ölçüleri anlama

Ölçüler çoğu zaman sizin için otomatik olarak oluşturulur. Contoso Satış Örneği dosyasında, Alanlar bölümündeki **Satış** tablosunda yer alan **SalesAmount** alanının yanındaki onay kutusunu seçin veya **SalesAmount** değerini rapor tuvaline sürükleyin. Satış tablosunun SalesAmount sütununda yer alan tüm değerlerin toplamını gösteren yeni bir sütun grafiği görselleştirmesi görüntülenir.

![SalesAmount grafiği](media/desktop-tutorial-create-measures/meastut_salesamountchart.png)

Alanlar bölümünde sigma simgesiyle görüntülenen alanlar ![sigma simgesi](media/desktop-tutorial-create-measures/meastut_sigma.png) sayısaldır ve değerleri toplanabilir. Power BI Desktop, iki milyon satır SalesAmount değeri içeren bir tablo göstermek yerine bir sayısal veri türü algıladı ve verileri toplamak için otomatik olarak bir ölçü oluşturup hesapladı. Toplam, bir sayısal veri türü için varsayılan toplamadır, ancak ortalama veya sayım gibi farklı toplamaları kolayca uygulayabilirsiniz. Her ölçü bir tür toplama işlemi gerçekleştirdiğinden, toplama işlemlerini anlamak ölçüleri anlamaktan geçer. 

Grafik toplamasını ortalama olarak değiştirmek için, Görsel Öğeler bölmesinin **Değer** alanında **SalesAmount**’un yanındaki aşağı oka tıklayıp **Ortalama**’yı seçin. Görselleştirme, SalesAmount alanındaki tüm satış değerlerinin ortalamasını gösterecek şekilde değişir.

![SalesAmount ortalama grafiği](media/desktop-tutorial-create-measures/meastut_salesamountaveragechart.png)

Toplama türünü, istediğiniz sonuca bağlı olarak değiştirebilirsiniz, ancak tüm toplama türleri her sayısal veri türü için geçerli değildir. Örneğin, SalesAmount alanı için Toplam ve Ortalama kullanılabilir. Minimum ve Maksimum da kullanılabilir işlemler olarak yer alır. Ancak SalesAmount alanının değerleri sayısal olmasına rağmen satış tutarları ifade ettiğinden Sayım işlemi bu alan için pek bir anlam ifade etmez.

Ölçülerden hesaplanan değerler, raporla etkileşimlerinize bağlı olarak değişiklik gösterir. Örneğin, **Geography** tablosundan **RegionCountryName** alanı grafiğinize sürüklendiğinde, her bir ülke için ortalama satış tutarları gösterilir.

![Ülkeye Göre SaleAmount](media/desktop-tutorial-create-measures/meastut_salesamountavchartbyrcn.png)

Raporunuzla bir etkileşim nedeniyle bir ölçünün sonucu değiştiğinde, ölçünüzün *bağlamını* etkilemiş olursunuz. Rapor görselleştirmelerinizle her etkileşime geçtiğinizde, bir ölçünün hesaplama yaptığı ve bu hesaplamanın sonuçlarını görüntülediği bağlamı değiştirmiş olursunuz.

## <a name="create-and-use-your-own-measures"></a>Kendi ölçülerinizi oluşturma ve kullanma

Çoğu durumda Power BI, seçtiğiniz alan ve toplama türlerine göre otomatik olarak değerleri hesaplar ve döndürür, ancak bazı durumlarda daha karmaşık, benzersiz hesaplamalar gerçekleştirmek için kendi ölçülerinizi oluşturmak isteyebilirsiniz. Power BI Desktop ile kendi ölçülerinizi oluştururken Veri Çözümleme İfadeleri (DAX) formül dilini kullanabilirsiniz. 

DAX formülleri, Excel formüllerinde de bulunan birçok işlevi, işleci ve söz dizimini kullanır. Ancak DAX işlevleri, ilişkisel verilerle çalışacak ve raporlarınızla etkileşime geçtiğimiz sırada daha dinamik hesaplamalar gerçekleştirecek şekilde tasarlanmıştır. Toplam ve Ortalama gibi basit toplama işlemlerinden daha karmaşık istatistik ve filtreleme işlevlerine kadar her şeyi yapan 200’ün üzerinde DAX işlevi vardır. DAX hakkında daha fazla bilgi edinmenize yardımcı olacak birçok kaynak vardır. Bu öğreticiyi tamamladıktan sonra [Power BI Desktop’ta DAX kullanımıyla ilgili temel bilgiler](desktop-quickstart-learn-dax-basics.md) makalesine göz atmayı unutmayın.

Kendi ölçünüzü oluşturduğunuzda bu ölçü, seçtiğiniz tablonun Alanlar listesine eklenir ve *model* ölçüsü olarak adlandırılır. Model ölçülerinin avantajlarından bazıları, bunlara istediğiniz adı vererek daha kolay tanımlanabilmesini sağlayabilmeniz; diğer DAX ifadelerinde bunları bağımsız değişken olarak kullanabilmeniz ve karmaşık hesaplamaları çok hızlı şekilde gerçekleştirmelerini sağlayabilmenizdir.

>[!TIP]
>Power BI Desktop’ın Şubat 2018 sürümünden itibaren birçok genel hesaplama, **hızlı ölçüler** olarak kullanılabilir ve bir iletişim kutusuna girdilerinize dayanarak sizin için DAX formüllerini yazabilir. Bu hızlı ve güçlü hesaplamalar, DAX’ı öğrenmek ve kendi özelleştirilmiş ölçülerinizin çekirdeğini oluşturmak için de mükemmeldir. Hızlı ölçüler oluşturmak veya keşfetmek için, bir tablonun **Diğer seçenekler** listesinden veya şeridin Giriş sekmesindeki **Hesaplamalar** bölümünden **Yeni hızlı ölçü** seçeneğini belirleyin. Hızlı ölçüleri oluşturma ve kullanma hakkında daha fazla bilgi için [Hızlı ölçüleri kullanma](desktop-quick-measures.md) bölümüne bakın.

### <a name="create-a-measure"></a>Ölçü oluşturma

Toplam satış miktarından indirimleri ve iadeleri çıkararak net satışınızı analiz etmek istersiniz. Görselleştirmenizde ne için bağlam olursa olsun, SalesAmount toplamından DiscountAmount ve ReturnAmount toplamını çıkaran bir ölçü gerekir. Alanlar listesinde Net Satış için bir alan yoktur, ancak net satışı hesaplamak için kendi ölçünüzü oluşturmak üzere yapı taşlarınız vardır. 

1.  Alanlar bölümünde **Satış** tablosuna sağ tıklayın veya imleci tablonun üzerine getirip **Diğer seçenekler**’i (...) ve sonra **Yeni Ölçü**’yü seçin. Böylece yeni ölçünüz, daha kolay bir şekilde bulabileceğiniz Satış tablosuna kaydedilir.
    
    ![Yeni ölçü](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure.png)
    
    Power BI Desktop şeridinin Giriş sekmesindeki Hesaplamalar grubunda **Yeni Ölçü**’yü seçerek de yeni bir ölçü oluşturabilirsiniz.
    
    ![Şeritteki yeni ölçü](media/desktop-tutorial-create-measures/meastut_netsales_newmeasureribbon.png)
    
    >[!TIP]
    >Şeritte bir ölçü oluşturduğunuzda bu ölçü herhangi bir tabloda oluşturulabilir; ancak bunu kullanmayı planladığınız yerde oluşturursanız bulmanız da kolaylaşır. Bu durumda, ilk olarak Satış tablosunu seçerek etkinleştirin ve sonra **Yeni Ölçü**’yü seçin. 
    
    Formül çubuğu, Rapor tuvalinin üst kısmında görüntülenir. Burada, ölçünüzü yeniden adlandırabilir ve bir DAX formülü girebilirsiniz.
    
    ![Formül çubuğu](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formulabar.png)
    
2.  Yeni ölçülere varsayılan olarak Ölçü adı verilir. Yeniden adlandırmazsanız, ek yeni ölçüler Ölçü 2, Ölçü 3 olarak adlandırılır ve bu şekilde devam eder. Ölçülerinizin daha kolay tanımlanabilmesini istersiniz. Bu nedenle formül çubuğundaki **Ölçü**’yü vurgulayın ve **Net Satış** yazın.
    
3.  Artık formülünüzü girmeye başlayabilirsiniz. Eşittir işaretinden sonra **Toplam** yazmaya başlayın. Siz yazarken, yazdığınız harflerle başlayan tüm DAX işlevlerini gösteren bir açılan öneri listesi görüntülenir. Gerekirse, sayfayı aşağı kaydırarak listeden **SUM**’ı seçin ve Enter tuşuna basın.
    
    ![SUM seçin](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_s.png)
    
    Bir açma ayracı ve SUM işlevine geçirebileceğimiz tüm kullanılabilir sütunların bulunduğu başka bir açılır öneri listesi görünür.
    
    ![Sütun seçin](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_sum.png)
    
    İfadeler her zaman bir açma ayracı ve kapatma ayracı arasında görüntülenir. İfadeniz, SUM işlevine geçirilecek tek bir bağımsız değişken içerir: SalesAmount sütunu. Listede yalnızca şu değer kalıncaya kadar "SalesAmount" yazmaya başlayın: Sales(SalesAmount). Başında tablo adı bulunan sütun adına, sütunun *tam adı* denir. Tam nitelikli sütun adları, formüllerinizin okunmasını kolaylaştırır. 
    
    ![SalesAmount seçin](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_salesam.png)
    
4. **Sales[SalesAmount]** seçeneğini belirleyin ve bir kapatma ayracı girin.
    
    > [!TIP]
    > Söz dizimi hatalarının sebebi genellikle eksik veya yanlış yerleştirilmiş bir kapanış parantezidir.
    
    
    
5.  Diğer iki sütunu çıkarmak için:
    1. İlk ifadedeki kapatma ayracından sonra bir boşluk girin, ardından eksi işleci ( **-** ) ve başka bir boşluk girin. 
    2. Başka bir SUM işlevi girin ve bağımsız değişken olarak **Sales[DiscountAmount]** sütununu seçebilinceye kadar "DiscountAmount" yazmaya başlayın. Kapatma ayracı ekleyin. 
    3. Bir boşluk, başka bir eksi işleci, boşluk, bağımsız değişken olarak **Sales[ReturnAmount]** içeren başka bir SUM işlevi ve bir kapatma ayracı girin.
    
    ![Formülü tamamlama](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_discamount.png)
    
6.  Formülü tamamlamak ve doğrulamak için Enter tuşuna basın veya formül çubuğundaki onay işaretine tıklayın. Doğrulanmış ölçü artık Satış tablosu için Alan listesinde kullanılmaya hazırdır. 
    
    ![Alan listesindeki ölçü](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_complete.png)
    
Formül girecek alanınız kalmazsa veya formülün ayrı satırlarda olmasını istiyorsanız, daha fazla alan açmak için formül çubuğunun sağ tarafındaki aşağı köşeli çift ayracı seçin.

![Formül köşeli çift ayracı](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_chevron.png)

**Alt-Enter** tuşlarına basarak formülünüzü farklı satırlara bölebilir veya **Tab** tuşunu kullanarak öğeleri taşıyabilirsiniz.

![Genişletilmiş formül](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_expanded.png)

### <a name="use-your-measure-in-the-report"></a>Raporda ölçünüzü kullanma
Artık Net Satış ölçünüzü rapor tuvaline ekleyebilir ve rapora eklediğiniz diğer tüm alanlar için net satışı hesaplayabilirsiniz. Ülkeye göre net satışı görmek için:

1. **Satış** tablosundan **Net Satış** ölçüsünü seçip rapor tuvaline sürükleyin.
    
2. **Coğrafya** tablosundan **RegionCountryName** alanını seçin veya grafiğe sürükleyin.
    
    ![Ülkeye Göre Net Satış](media/desktop-tutorial-create-measures/meastut_netsales_byrcn.png)
    
Ülkeye göre toplam satış ile net satış arasındaki farkı görmek için, **SalesAmount** alanını seçin veya grafiğe sürükleyin. 

![Ülkeye Göre Net Satış ve Satış Miktarı](media/desktop-tutorial-create-measures/meastut_netsales_byrcnandsalesamount.png)

Grafik şimdi iki ölçü kullanır: Otomatik olarak toplanmış olan SalesAmount ölçüsü ve sizin oluşturduğunuz Net Sales ölçüsü. Her ölçü, başka bir alan (RegionCountryName) bağlamında hesaplanmıştır.
    
### <a name="use-your-measure-with-a-slicer"></a>Dilimleyici ile ölçünüzü kullanma

Net satışı ve satış miktarlarını takvim yılına göre filtrelemek için bir dilimleyici ekleyebilirsiniz.
    
1.  Grafiğin yanındaki boş bir alana tıklayın, ardından **Görsel Öğeler** bölmesindeki **Tablo** görselleştirmesini seçin. Bu işlemden sonra rapor tuvalinde boş bir tablo görselleştirmesi oluşturulur.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_blanktable.png)
    
2.  **Takvim** tablosundaki **Yıl** alanını yeni boş tablo görselleştirmesine sürükleyin. Yıl bir sayısal alan olduğundan, Power BI Desktop kendi değerlerini toplar, ancak bir toplama kadar anlam ifade etmez. 
    
    ![Yıl toplama](media/desktop-tutorial-create-measures/meastut_netsales_yearaggtable.png)
    
3.  Görsel Öğeler bölmesindeki **Değerler** alanında, **Yıl**’ın yanındaki aşağı oku seçin ve **Özetleme** seçeneğini belirleyin. Tablo şimdi tek tek yılları listeler.
    
    ![Özetleme](media/desktop-tutorial-create-measures/meastut_netsales_year_donotsummarize.png)
    
4.  Tabloyu dilimleyiciye dönüştürmek için Görsel Öğeler bölmesindeki **Dilimleyici** simgesini seçin.

    ![Dilimleyici olarak değiştirme](media/desktop-tutorial-create-measures/meastut_netsales_year_changetoslicer.png)
    
5.  **Ülkeye Göre Net Satış ve Satış Miktarı** grafiğini uygun şekilde filtrelemek için **Yıl** dilimleyicisinde herhangi bir değer seçin. Net Satış ve SalesAmount ölçüleri, seçilen Yıl alanı bağlamında sonuçları yeniden hesaplar ve görüntüler. 
    
    ![Yıla göre dilimlenmiş grafik](media/desktop-tutorial-create-measures/meastut_netsales_chartslicedbyyear.png)

### <a name="use-your-measure-in-another-measure"></a>Ölçünüzü başka bir ölçüde kullanma

Satılan birim başına en yüksek net satış miktarına sahip olan ürünleri bulmak istediğinizden, net satışı, satılan birim miktarına bölen bir ölçü gerekir. Net Satış ölçünüzün sonucunu, Sales[SalesQuantity] toplamına bölen yeni bir ölçü oluşturabilirsiniz.

1.  Satış tablosunda **Birim Başına Net Satış** adlı yeni bir ölçü oluşturun.
    
2.  Formül çubuğuna **Net Satış** yazmaya başlayın. Öneri listesi, ne ekleyebileceğinizi gösterir. **[Net Sales]** seçeneğini belirleyin.
    
    ![Net Satış kullanan formül](media/desktop-tutorial-create-measures/meastut_nspu_formulastep2a.png)
    
    Ayrıca yalnızca bir açma ayracı ( **[** ) yazarak da ölçülere başvurabilirsiniz. Öneri listesi yalnızca formülünüze eklenecek ölçüleri gösterir.
    
    ![Köşeli ayraç yalnızca ölçüleri gösterir](media/desktop-tutorial-create-measures/meastut_nspu_formulastep2b.png)
    
3.  Bir boşluk, bölme işleci ( **/** ), bir boşluk daha, bir SUM işlevi girin ve sonra **Miktar** yazın. Öneri listesi, adında Miktar olan tüm sütunları gösterir. **Sales[SalesQuantity]** öğesini seçin, kapatma ayracını yazın ve ENTER tuşuna basın veya formülünüzü doğrulamak için onay işaretini seçin. Formülünüz şöyle görünmelidir:
    
    `Net Sales per Unit = [Net Sales] / SUM(Sales[SalesQuantity])`
    
4. Satış tablosundan **Birim Başına Net Satış** ölçüsünü seçin veya rapor tuvalindeki boş bir alana sürükleyin. Grafik, satılan tüm ürünlerin birim başına net satış miktarını gösterir; bu çok bilgilendirici değildir. 
    
    ![Genel birim başına net satış](media/desktop-tutorial-create-measures/meastut_nspu_chart.png)
    
5. Farklı bir görünüm için, grafik görselleştirmesi türünü **Ağaç Haritası** olarak değiştirin.
    
    ![Ağaç haritası olarak değiştirme](media/desktop-tutorial-create-measures/meastut_nspu_changetotreemap.png)
    
6. **Ürün Kategorisi** alanını seçin veya ağaç haritasına ya da Görsel Öğeler bölmesinin Grup alanına sürükleyin. Şimdi harika bilgilere sahipsiniz!
    
    ![Ürün Kategorisine Göre Ağaç Haritası](media/desktop-tutorial-create-measures/meastut_nspu_byproductcat.png)
    
7. Bunun yerine **ProductCategory** alanını kaldırmayı ve **ProductName** alanını grafiğe sürüklemeyi deneyin. 
    
    ![Ürün Adına Göre Ağaç Haritası](media/desktop-tutorial-create-measures/meastut_nspu_byproductname.png)
    
Şu anda dilediğimiz gibi deneme yapıyor olabiliriz ancak kabul etmeniz gerekir ki bu oldukça havalı! Görselleştirmeyi filtrelemenin ve biçimlendirmenin diğer yollarını deneyin.

## <a name="what-youve-learned"></a>Öğrendikleriniz
Ölçüler size verilerinizden istediğiniz öngörüleri elde etme gücü sunar. Formül çubuğunu kullanarak ölçüler oluşturmayı, ölçüleri en mantıklı şekilde adlandırmayı ve DAX öneri listelerini kullanarak doğru formül öğelerini bulup seçmeyi öğrendiniz. Ayrıca, ölçülerdeki hesaplamaların sonuçlarının diğer alanlara veya formülünüzdeki başka ifadelere ya da alanlara göre değiştiği bağlam kavramıyla da tanışmış oldunuz.

## <a name="next-steps"></a>Sonraki adımlar
- Sizin için birçok genel ölçü hesaplamaları sağlayan Power BI Desktop hızlı ölçümleri hakkında daha fazla bilgi edinmek için bkz. [Genel ve güçlü hesaplamaları kolayca gerçekleştirmek için hızlı ölçüleri kullanma](desktop-quick-measures.md).
  
- DAX formüllerini daha ayrıntılı bir şekilde incelemek ve daha gelişmiş ölçüler oluşturmak istiyorsanız [Power BI Desktop’ta DAX kullanımıyla ilgili temel bilgiler](desktop-quickstart-learn-dax-basics.md) başlıklı makaleye bakabilirsiniz. Bu makale söz dizimi ve işlevler gibi DAX temel kavramlarını ele alır ve bağlama ilişkin daha kapsamlı bilgi sunar.
  
- Sık kullanılanlar listenize [Veri Çözümleme İfadeleri (DAX) Başvurusu](https://msdn.microsoft.com/library/gg413422.aspx)'nu eklediğinizden emin olun. Burada DAX söz dizimi, işleçleri ve 200'ü aşkın DAX işleviyle ilgili ayrıntılı bilgi bulabilirsiniz.

