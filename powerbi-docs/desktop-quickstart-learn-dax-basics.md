---
title: Power BI Desktop'ta DAX kullanımıyla ilgili temel bilgiler
description: Power BI Desktop'ta DAX kullanımıyla ilgili temel bilgiler
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Model your data
ms.openlocfilehash: 474cca86151925ee4991d477a6127536180808a8
ms.sourcegitcommit: c80fbf5b12754ce217cb47a17cb5400b1036a8f2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/06/2018
---
# <a name="dax-basics-in-power-bi-desktop"></a>Power BI Desktop'ta DAX kullanımıyla ilgili temel bilgiler
Bu makale, Power BI Desktop'ı kullanmaya yeni başlayan kullanıcılara yöneliktir. Bir dizi temel hesaplama ve veri çözümleme sorununu çözmek için Veri Çözümleme İfadeleri'ni (DAX) nasıl kullanabileceğinize ilişkin hızlı ve anlaşılır bir açıklama sunmak için hazırlanmıştır. Bazı kavramsal bilgileri, gerçekleştirebileceğiniz bir dizi görevi ve öğrendiklerinizi sınamaya yönelik birkaç testi inceleyeceğiz. Bu makaleyi tamamladıktan sonra DAX'taki en temel kavramları iyi bir şekilde anlamış olacaksınız.

## <a name="what-is-dax"></a>DAX nedir?
DAX, hesaplama yapmak ve bir veya daha fazla değer döndürmek için bir formülde veya ifadede kullanılabilen işlevlerden, işleçlerden ve sabitlerden oluşan bir koleksiyondur. Daha basit bir şekilde ifade etmek gerekirse DAX, modelinizde zaten bulunan verilerden yeni bilgiler oluşturmanıza yardımcı olur.

## <a name="why-is-dax-so-important"></a>DAX neden bu kadar önemlidir?
Yeni bir Power BI Desktop dosyası oluşturup bu dosyaya veri aktarmak oldukça kolaydır. Hatta hiçbir DAX formülü kullanmadan değerli öngörüler sunan raporlar da oluşturabilirsiniz. Peki ya ürün kategorilerinde farklı tarih aralıklarında gözlemlenen büyüme yüzdesini çözümlemeniz gerekseydi? Yıldan yıla büyümeyi pazar eğilimleriyle karşılaştırarak hesaplamanız gerekse ne yapardınız? DAX formülleri, bu tür görevleri gerçekleştirmeye yarayan becerilerin yanı sıra başka pek çok önemli işlev de sunar. Etkili DAX formülleri oluşturmayı öğrenmek, verilerinizden en iyi şekilde yararlanmanıza yardımcı olur. İhtiyaç duyduğunuz bilgileri elde ettiğinizde, nihai kâr-zarar dengenizi etkileyen gerçek iş sorunlarını çözmeye başlayabilirsiniz. Power BI bu gücü barındırır, DAX ise onu kullanmanıza yardımcı olur.

## <a name="prerequisites"></a>Önkoşullar
Microsoft Excel'de formül oluşturma konusuna zaten aşina olabilirsiniz. DAX'ı anlama konusunda bu bilgilerden yararlanabilirsiniz ancak Excel formülleri konusunda hiç deneyiminiz olmasa bile burada açıklanan kavramlar, DAX formülleri oluşturmaya ve gerçek dünyadaki BI sorunlarını hemen çözmeye başlamanıza yardımcı olacaktır.

Hesaplamalarda, özellikle de ölçülerde ve hesaplanmış sütunlarda kullanılan DAX formüllerini anlamaya odaklanacağız. Power BI Desktop, veri içeri aktarma ve bir rapora alan ekleme konularının yanı sıra [Ölçüler](desktop-measures.md) ve [Hesaplanmış sütunlar](desktop-calculated-columns.md) ile ilgili temel kavramlar hakkında da bilgi sahibi olmanız gerekir.

**Örnek Çalışma Kitabı**

DAX'ı öğrenmenin en iyi yolu, bazı temel formüller oluşturmanız, bunları gerçek verilerle kullanmanız ve sonuçları kendiniz görmenizdir. Buradaki örneklerde ve görevlerde Power BI Desktop için Contoso Sales örneği Önizleme dosyası kullanılmaktadır. Bu örnek dosya, [Öğretici: Power BI Desktop'ta kendi ölçülerinizi oluşturma](desktop-tutorial-create-measures.md) başlıklı makalede de kullanılmıştır. [Örnek dosyayı](http://download.microsoft.com/download/4/6/A/46AB5E74-50F6-4761-8EDB-5AE077FD603C/Contoso%20Sales%20for%20Power%20BI%20Designer.zip) buradan indirebilirsiniz.

## <a name="lets-begin"></a>Haydi başlayalım!
DAX'a ilişkin kavrayışımızı *Söz dizimi*, *İşlevler* ve *Bağlam* olmak üzere üç temel kavram etrafında şekillendireceğiz. Elbette, DAX'ta başka önemli kavramlar da bulunmaktadır ancak bu üç kavramı anlamak, DAX becerilerinizi oluşturmak için en iyi temeli sağlayacaktır.

### <a name="syntax"></a>Söz dizimi
Kendi formüllerinizi oluşturmadan önce DAX formül söz dizimine bir göz atalım. Söz dizimi, bir formülü oluşturan veya daha basit bir şekilde açıklamak gerekirse, formülün nasıl yazıldığına ilişkin çeşitli öğeleri içerir. Örneğin, bir ölçüye yönelik basit bir DAX formülüne bakalım.

![](media/desktop-quickstart-learn-dax-basics/qsdax_1_syntax.png)

Bu formül, aşağıdaki söz dizimi öğelerini içerir:

**A.** Ölçü adı: **Total Sales**.

**B.** Eşittir işareti işleci (**=**), formülün başını gösterir. Hesaplama gerçekleştirildiğinde bir sonuç döndürür.

**C.** DAX işlevi **SUM**, **Sales[SalesAmount]** sütunundaki tüm sayıları toplar. İlerleyen bölümlerde işlevler hakkında daha fazla bilgi edineceksiniz.

**D.** Ayraçlar **()**, bir veya daha fazla bağımsız değişken içeren bir ifadeyi çevreler. Tüm işlevler için en az bir bağımsız değişken gereklidir. Bağımsız değişken, bir işleve değer geçirir.

**E.** Başvurulan tablo: **Sales**.

**F.** Sales tablosunda başvurulan sütun: **[SalesAmount]**. Bu bağımsız değişken ile SUM işlevi, bir SUM oluşturmak için hangi sütunların toplanacağını belirtir.

Bir DAX formülünü anlamaya çalışırken, her bir öğeyi, günlük hayatınızda düşünmek ve konuşmak için kullandığınız dile çevirmek genellikle yararlı olur. Örneğin, bu formülü şöyle okuyabilirsiniz:

> *Total Sales adlı ölçüyle ilgili olarak, Sales tablosundaki [SalesAmount ] sütununda bulunan değerler için SUM (Toplama) işlevi ile elde edilen sonucu hesapla (=).*
> 
> 

Bu ölçü, bir rapora eklendiğinde, dahil ettiğimiz diğer alanların her biri (ör. ABD'deki Cep Telefonları) için satış miktarlarını toplayarak değerleri hesaplayıp döndürür.

Kendinize "Bu ölçü, raporuma yalnızca SalesAmount alanını ekleyerek gerçekleştirdiğim işlemle aynı sonucu vermiyor mu?" sorusunu soruyor olabilirsiniz. Bu doğru olabilir. Ancak, SalesAmount alanındaki değerleri toplayan kendi ölçünüzü oluşturmak için geçerli bir nedeniniz var: Bunu diğer formüllerde bağımsız değişken olarak kullanabiliriz. Bunlar şu anda biraz kafa karıştırıcı görünebilir ancak DAX formül becerileriniz arttıkça bu bilgi, formüllerinizin ve modelinizin daha verimli olmasını sağlayacak. Aslında, daha sonra Total Sales ölçüsünün başka formüllerde bir bağımsız değişken olarak karşımıza çıkacağını göreceksiniz.

Bu formüle ilişkin birkaç noktanın daha üzerinde duralım. Özellikle belirtmek gerekirse, [SUM](https://msdn.microsoft.com/library/ee634387.aspx) işlevini tanıttık. İşlevler; sayılar, tarihler, saatler, metinler ve daha fazlasıyla karmaşık hesaplamalar ve işlemeler gerçekleştirmeyi kolaylaştıran, önceden yazılmış formüllerdir. İlerleyen bölümlerde işlevler hakkında daha fazla bilgi edineceksiniz.

Ayrıca sütun adı olan [SalesAmount] ifadesinin, sütunun ait olduğu tablonun adı olan Sales ifadesinden sonra geldiğine de dikkat edin. Sütun adının tablo adını izlediği bu gösterim tam sütun adı olarak bilinir. Aynı tabloda başvurulan sütunlar için tablo adının formüle eklenmesi gerekmez. Bu, birçok sütuna başvuran uzun formülleri daha kısa ve okunması kolay hale getirir. Ancak, aynı tabloda olsalar bile ölçü formüllerinize tablo adını eklemek iyi bir uygulamadır.

> [!NOTE]
> Tablo adında boşluklar, ayrılmış anahtar sözcükler veya izin verilmeyen karakterler varsa tablo adını tek tırnak işaretleri arasında yazmanız gerekir. Ayrıca, yerel dilinizin karakter kümesini destekleyip desteklemediğine bakılmaksızın, adın ANSI alfasayısal karakter aralığı dışında herhangi bir karakter içermesi durumunda da tablo adını tırnak işareti içinde yazmanız gerekir.
> 
> 

Formüllerinizde kullanılan söz diziminin doğru olması önemlidir. Çoğu durumda, söz dizimi doğru değilse bir söz dizimi hatası döndürülür. Bazı durumlarda ise söz dizimi doğru olmasına rağmen beklediğiniz sonuçlar döndürülmeyebilir. Power BI Desktop'taki DAX düzenleyicisi, doğru öğeleri seçmenize yardım ederek söz dizimsel olarak doğru formüller oluşturmanızı sağlamak için kullanılan öneriler özelliğini içerir.

Basit bir formül oluşturalım. Bu görev, formül söz dizimini ve formül çubuğundaki öneriler özelliğinin size nasıl yardımcı olabileceğini daha iyi anlamanıza yardımcı olacak.

### <a name="task-create-a-measure-formula"></a>Görev: Ölçü formülü oluşturma
Bu görevi tamamlamak için Power BI Desktop Contoso Sales örnek dosyasını açmanız gerekir.
    
1.  Rapor görünümündeki alan listesinde, **Sales** tablosuna sağ tıklayın ve ardından **Yeni Ölçü**'ye tıklayın.
    
2.  Formül çubuğundaki **Ölçü**'yü, yeni bir ölçü adı (**Previous Quarter Sales**) yazarak değiştirin.
    
3.  Eşittir işaretinden sonra **SUM** yazın ve hemen ardına bir sol ayraç ekleyin.
    
    Hemen toplamak için bir sütun adı yazmak yerine başka bir işlev girerek, toplamak istediğimiz verileri *filtreleyeceğiz*.
    
4.  Ayraçlar arasına **CALCULATE** yazın ve hemen ardına bir sol ayraç ekleyin.
    
    CALCULATE işlevine geçirdiğimiz bir bağımsız değişkenle toplamak istediğimiz tutarları filtrelemek için CALCULATE işlevini kullanırsınız. Bunlar, iç içe geçen işlevler olarak adlandırılır. CALCULATE işlevinin en az iki bağımsız değişkeni vardır. Bunlardan ilki değerlendirilecek ifade, ikincisi ise bir filtredir.
   
5.  **CALCULATE** işlevine ilişkin ayraçların **()** arasına **Sales[SalesAmount]** yazın. Bu, CALCULATE işlevimizin ilk ifade bağımsız değişkenidir.
    
6.  Birinci filtreyi belirtmek için bir virgülden (**,**) sonra **PREVIOUSQUARTER** yazın ve hemen ardına bir sol ayraç ekleyin.
    
    SUM sonuçlarımızı önceki üç aylık döneme göre filtrelemek için PREVIOUSQUARTER akıllı zaman gösterimi işlevini kullanırsınız.
    
7.  PREVIOUSQUARTER işlevine ilişkin ayraçların **()** arasına **Calendar[DateKey]** yazın.
    
    PREVIOUSQUARTER işlevi, bitişik tarih aralığı içeren bir sütun olan tek bir bağımsız değişkene sahiptir.
    
8.  Biri PREVIOUSQUARTER işlevine, diğeri ise CALCULATE işlevine geçirilen her iki bağımsız değişkenin de hemen ardına iki sağ ayraç **))** eklediğinizden emin olun.
    
   Formülünüzün aşağıdaki gibi görünmesi gerekir:
    
    **Previous Quarter Sales = CALCULATE(SUM(Sales[SalesAmount]), PREVIOUSQUARTER(Calendar[DateKey]))**
    
9. Formülü doğrulayıp modele eklemek için formül çubuğundaki onay işaretine ![](media/desktop-quickstart-learn-dax-basics/qsdax_syntax_taskcheckmark.png) tıklayın veya Enter tuşuna basın.

Başardınız! DAX kullanarak bir ölçü oluşturdunuz ve bu hiç de azımsanacak bir şey değil. Bu formül, bir rapora uygulanan filtrelere bağlı olarak önceki üç aylık döneme ait toplam satışı hesaplamak için kullanılabilir. Örneğin, bir grafiğe SalesAmount ile yeni Previous Quarter Sales ölçümüzü ekleyip Dilimleyiciler olarak Year ve QuarterOfYear seçeneklerini eklersek aşağıdaki gibi bir görüntü elde ederiz:

![](media/desktop-quickstart-learn-dax-basics/qsdax_3_chart.png)

DAX formüllerinin yalnızca birkaç önemli yönüyle tanıştınız. Birincisi, bu formül iki işlev içeriyordu. Akıllı zaman gösterimi işlevi olan [PREVIOUSQUARTER](https://msdn.microsoft.com/library/ee634385.aspx) işlevinin, bir filtre işlevi olan [CALCULATE](https://msdn.microsoft.com/library/ee634825.aspx) işlevine geçirilen bir bağımsız değişken olarak iç içe geçirildiğine dikkat edin. DAX formülleri, iç içe geçmiş en fazla 64 işlev içerebilir. Bir formülün bu kadar çok iç içe geçmiş işlev içermesi pek olası değildir. Aslında böyle bir formülün oluşturulup ayıklanması oldukça zor olurdu ve formül büyük olasılıkla pek hızlı da çalışmazdı.

Bu formülde filtreleri de kullandınız. Filtreler, hesaplamanın kapsamını daraltır. Bu örnekte bağımsız değişken olarak bir filtre seçtiniz; bu da aslında başka bir işlev ile elde edilir. İlerleyen bölümlerde filtreler hakkında daha fazla bilgi edineceksiniz.

Son olarak, CALCULATE işlevini kullandınız. Bu, DAX'taki en güçlü işlevlerden biridir. Büyük olasılıkla, modeller yazıp daha karmaşık formüller oluşturdukça bu işlevi birçok kez kullanacaksınız. CALCULATE işlevinin ele alınması bu makalenin amaçları arasında yer almamaktadır ancak DAX ile ilgili bilgi birikiminiz genişledikçe dikkatinizi özel olarak bu işleve vermenizi öneririz.

### <a name="syntax-quickquiz"></a>Söz dizimine ilişkin Hızlı Test
1. Formül çubuğundaki bu düğme ne işe yarar?
   
   > ![](media/desktop-quickstart-learn-dax-basics/qsdax_2_syntaxquiz.png)
   > 
   > 
2. Bir DAX formülündeki bir sütun adını her zaman ne çevreler?

Yanıtlara bu makalenin sonunda ulaşabilirsiniz.

### <a name="functions"></a>İşlevler
İşlevler, bağımsız değişken olarak adlandırılan belirli değerleri özel bir sırada veya yapıda kullanarak hesaplamalar gerçekleştiren, önceden tanımlanmış formüllerdir. Diğer işlevler, farklı bir formül, ifade, sütun başvurular, sayılar, metinler, TRUE veya FALSE gibi mantıksal değerler ya da sabitler birer bağımsız değişken olabilir.

DAX, şu işlev kategorilerini içerir: [Tarih ve Saat](https://msdn.microsoft.com/library/ee634786.aspx), [Akıllı Zaman Gösterimi](https://msdn.microsoft.com/library/ee634763.aspx),[Bilgi](https://msdn.microsoft.com/library/ee634552.aspx), [Mantıksal](https://msdn.microsoft.com/library/ee634365.aspx),[Matematiksel](https://msdn.microsoft.com/library/ee634241.aspx), [İstatistiksel](https://msdn.microsoft.com/library/ee634822.aspx), [Metin](https://msdn.microsoft.com/library/ee634938.aspx), [Üst/Alt Öğe](https://msdn.microsoft.com/library/mt150102.aspx) ve [Diğer](https://msdn.microsoft.com/library/mt150101.aspx) işlevler. Excel formüllerindeki işlevlere aşinaysanız DAX'taki işlevlerin çoğu tanıdık gelecektir ancak DAX işlevleri, aşağıdaki yönlerden benzersizdir:

* Bir DAX işlevi, her zaman sütunun veya tablonun tamamına başvurur. Bir tablo veya sütundaki belirli değerleri kullanmak istiyorsanız formüle filtre ekleyebilirsiniz.
* Hesaplamaları satır bazında özelleştirmeniz gerekiyorsa DAX, bağlama göre değişiklik gösteren hesaplamalar gerçekleştirmek için geçerli satır değerini veya ilgili bir değeri bağımsız değişken türü olarak kullanmanıza olanak sağlayan işlevler sunar. İlerleyen bölümlerde bağlam hakkında daha fazla bilgi edineceksiniz.
* DAX, bir değerden çok bir tablo döndüren pek çok işlev içerir. Tablo görüntülenmez ancak diğer işlevlere giriş sağlamak için kullanılır. Örneğin, bir tabloyu alıp ardından bu tablodaki benzersiz değerleri sayabilir veya filtrelenmiş tablolarda veya sütunlarda dinamik toplamlar hesaplayabilirsiniz.
* DAX, pek çok akıllı zaman gösterimi işlevi içerir. Bu işlevler, tarih aralıklarını tanımlamanıza veya seçmenize ve bunlara bağlı olarak dinamik hesaplamalar gerçekleştirmenize olanak sağlar. Örneğin, paralel dönemler için toplamları karşılaştırabilirsiniz.
* Excel, oldukça popüler bir işlev olan DÜŞEYARA işlevini içerir. DAX işlevleri, Excel'deki DÜŞEYARA işlevinde olduğu gibi başvuru olarak bir hücreyi veya hücre aralığını almaz. DAX işlevleri, başvuru olarak bir sütunu veya tabloyu alır. Power BI Desktop'ta ilişkisel bir veri modeli ile çalıştığınızı unutmayın. Başka bir tablodaki değerlere bakmak gerçekten de oldukça kolaydır ve çoğu durumda formül oluşturmanız bile gerekmez.
  
  Gördüğünüz gibi DAX'taki işlevler, oldukça etkili formüller oluşturmanıza yardımcı olabilir. Aslında yalnızca işlevler ile ilgili temel bilgilere değindik. DAX becerileriniz geliştikçe çok çeşitli işlevleri kullanarak formüller oluşturabileceksiniz. DAX işlevlerinin her biri hakkında daha fazla bilgi edinmek için kullanabileceğiniz en iyi yerlerden biri de [DAX İşlev Başvurusu](https://msdn.microsoft.com/library/ee634396.aspx)'dur.

### <a name="functions-quickquiz"></a>İşlevlere ilişkin Hızlı Test
1. Bir işlev her zaman neye başvurur?
2. Bir formül birden fazla işlev içerebilir mi?
3. İki metin dizesini bir dizede birleştirmek için hangi işlev kategorilerini kullanırsınız?

Yanıtlara bu makalenin sonunda ulaşabilirsiniz.

### <a name="context"></a>Bağlam
Bağlam, öğrenilmesi gereken en önemli DAX kavramlarından biridir. DAX'ta satır bağlamı ve filtre bağlamı olmak üzere iki bağlam türü vardır. Öncelikle satır bağlamını inceleyeceğiz.

**Satır bağlamı**

Satır bağlamı, en basit ifadeyle geçerli satır olarak düşünülebilir. Formüllerin bir tablodaki tek bir satırı tanımlamak için filtreler uygulayan bir işleve sahip olduğu her durumda uygulanabilir. İşlev, filtreleme yaptığı tablonun her bir satırı için yapısal olarak bir satır bağlamı uygular. Bu türden bir satır bağlamı, daha çok ölçülere uygulanır.

**Filtre bağlamı**

Filtre bağlamını anlamak, satır bağlamını anlamaktan biraz daha zordur. En basit ifadeyle filtre bağlamını, bir sonucu veya değeri belirleyen hesaplamalarda uygulanan bir veya daha fazla filtre olarak düşünebilirsiniz.

Filtre bağlamı, satır bağlamının yerine değil, satır bağlamına ek olarak uygulanır. Örneğin, bir hesaplamaya dahil edilecek değerlerin kapsamını daha fazla daraltmak için, yalnızca satır bağlamını değil, bu satır bağlamındaki belirli bir değeri (filtre) de belirten bir filtre bağlamı uygulayabilirsiniz.

Filtre bağlamını raporlarınızda kolayca görebilirsiniz. Örneğin, bir görselleştirmeye TotalCost'u ve ardından Year ile Region'ı eklediğinizde, belirli bir yıla ve bölgeye göre verilerin bir alt kümesini seçen bir filtre bağlamı tanımlamış olursunuz.

Filtre bağlamı DAX'ta neden bu kadar önemlidir? Çünkü filtre bağlamı en kolay bir görselleştirmeye alanlar ekleyerek uygulanırken, filtre bağlamı da bir DAX formülüne, ilişkilere ve diğer ölçü ve sütunlara göre TÜMÜ, İLGİLİ, FİLTRELE, HESAPLA gibi işlevler kullanılarak bir filtre tanımlayarak uygulanabilir. Örneğin, Store Sales adlı bir ölçüde bulunan aşağıdaki formüle göz atalım:

![](media/desktop-quickstart-learn-dax-basics/qsdax_4_context.png)

Bu formülü daha iyi anlamak için tıpkı diğerlerinde olduğu gibi bu formülü de parçalara ayırarak inceleyebiliriz.

Bu formül, aşağıdaki söz dizimi öğelerini içerir:

**A.** Ölçü adı: **Store Sales**.

**B.** Eşittir işareti işleci (**=**), formülün başını gösterir.

**C.** **CALCULATE** işlevi, belirtilen filtrelere göre değiştirilen bir bağlamda, bir ifadeyi bağımsız değişken olarak değerlendirir.

**D.** Ayraçlar **()**, bir veya daha fazla bağımsız değişken içeren bir ifadeyi çevreler.

**E.** Aynı tabloda bir ifade olarak bulunan **[Total Sales]**. Total Sales ölçüsün şu formüle sahiptir: =SUM(Sales[SalesAmount]).

**F.** Virgül (**,**), ilk ifade bağımsız değişkenini filtre bağımsız değişkeninden ayırır.

**G.** Başvurulan sütunun tam adı: **Channel[ChannelName]**. Bu, bizim satır bağlamımızdır. Bu sütundaki her bir satır; Mağaza, Çevrimiçi gibi bir kanalı belirtir.

**H.** Filtre olarak kullanılan belirli değer: **Store**. Bu, bizim filtre bağlamımızdır.

Bu formül, filtre olarak Channel[ChannelName] sütunundaki yalnızca "Store" değerini içeren satırlar için yalnızca Total Sales ölçüsüyle tanımlanan satışların hesaplanmasını sağlar.

Hayal edebileceğiniz gibi, bir formülde filtre bağlamını tanımlayarak çok geniş kapsamlı ve etkili özelliklerden yararlanabilirsiniz. İlgili bir tabloda yalnızca belirli bir değere başvurabilmek, bu tür örneklerden yalnızca bir tanesidir. Bağlamı hemen tamamen anlamazsanız endişelenmeyin. Kendi formüllerinizi oluştururken bağlamı ve bağlamın DAX'ta neden bu kadar önemli olduğunu daha iyi anlayacaksınız.

### <a name="context-quickquiz"></a>Bağlama ilişkin Hızlı Test
1. Bağlamın iki farklı türü hangileridir?
2. Filtre bağlamı nedir?
3. Satır bağlamı nedir?

Yanıtlara bu makalenin sonunda ulaşabilirsiniz.

## <a name="summary"></a>Özet
DAX'taki en önemli kavramları temel düzeyde öğrendiğinize göre kendi kendinize ölçüler için DAX formülleri oluşturmaya başlayabilirsiniz. DAX'ı öğrenmek gerçekten de biraz karmaşık olabilir ancak kullanabileceğiniz pek çok kaynak mevcuttur. Bu makaleyi okuyup kendi formüllerinizin birkaçıyla deneme yaptıktan sonra işinizle ilgili sorunları çözmenize yardımcı olabilecek diğer DAX kavram ve formülleri hakkında daha fazla bilgi edinebilirsiniz. Yararlanabileceğiniz birçok DAX kaynağından en önemlisi, [Veri Çözümleme İfadeleri (DAX) Başvurusu](https://msdn.microsoft.com/library/gg413422.aspx)'dur.

DAX, Power Pivot ve Analysis Services Tablolu modelleri gibi diğer Microsoft BI araçlarında yıllardır kullanılmaktadır ve bu, ulaşabileceğiniz pek çok harika bilginin bulunduğu anlamına gelir. Hem Microsoft hem de önde gelen BI uzmanları tarafından sunulan kitaplarda, teknik incelemelerde ve bloglarda daha fazla bilgiye ulaşabilirsiniz. [TechNet'teki DAX Resource Center Wiki](http://social.technet.microsoft.com/wiki/contents/articles/dax-resource-center.aspx) de başlangıç için harika bir kaynaktır.

### <a name="quickquiz-answers"></a>Hızlı Test yanıtları
Söz dizimi:

1. Ölçüyü doğrulayıp modele girer.
2. Köşeli ayraçlar [].

İşlevler:

1. Bir tablo ve sütun.
2. Evet. Bir formül, en fazla 64 iç içe geçmiş işlev içerebilir.
3. [Metin işlevleri](https://msdn.microsoft.com/library/ee634938.aspx).

Bağlam:

1. Satır bağlamı ve filtre bağlamı.
2. Bir hesaplamada tek bir değeri belirleyen bir veya daha fazla filtre.
3. Geçerli satır.

