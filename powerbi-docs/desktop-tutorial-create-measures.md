---
title: "Eğitim: Power BI Desktop'ta kendi ölçülerinizi oluşturma"
description: "Eğitim: Power BI Desktop'ta kendi ölçülerinizi oluşturma"
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Learn more
ms.openlocfilehash: 96295ced577ddb18b8c56031278bf9a81cddf981
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/24/2018
---
# <a name="tutorial-create-your-own-measures-in-power-bi-desktop"></a>Eğitim: Power BI Desktop'ta kendi ölçülerinizi oluşturma
Power BI Desktop'taki en etkili veri çözümleme çözümlerinin bazıları ölçüler kullanılarak oluşturulabilir. Ölçüler, raporlarımızla etkileşim kurarken hesaplamalar gerçekleştirmemize yardımcı olur. Bu eğitim, Power BI Desktop'taki temel ölçüleri anlama ve kendi ölçülerinizin bazılarını oluşturma konusunda size yol gösterir.

Bu makale, Power BI Desktop'ı daha gelişmiş modeller oluşturmak için kullanmaya alışmış Power BI kullanıcılarına yöneliktir. Verileri içeri aktarmak, birden çok ilişkili tabloyla çalışmak ve Rapor Tuvali'ne alan eklemek için Veri Al ve Sorgu Düzenleyicisi özelliklerini kullanmaya alışmış olmanız gerekir. Power BI Desktop'ı kullanmaya yeni başladıysanız, [Power BI Desktop ile çalışmaya başlama](desktop-getting-started.md) başlıklı makaleye mutlaka göz atın.

Bu eğitimdeki adımları tamamlamak için, [Contoso Sales Sample for Power BI Desktop](http://download.microsoft.com/download/4/6/A/46AB5E74-50F6-4761-8EDB-5AE077FD603C/Contoso%20Sales%20Sample%20for%20Power%20BI%20Desktop.zip) dosyasını indirmeniz gerekir. Contoso, Inc. adlı kurgusal şirketin çevrimiçi satış verileri zaten girilmiş durumdadır. Dosyadaki veriler bir veritabanından içeri aktarıldığı için veri kaynağına bağlanamaz veya bunu Sorgu Düzenleyicisi'nde görüntüleyemezsiniz. Bilgisayarınıza indirdiğiniz dosyayı Power BI Desktop'ta açın.

## <a name="what-are-these-measures-all-about"></a>Ölçüler ne işe yarar?
Ölçüler çoğu durumda bizim için otomatik olarak oluşturulur. Örneğin, alan listesindeki **Sales** tablosunda bulunan **SalesAmount** alanının yanındaki onay kutusunu seçtiğimizde veya **SalesAmount** alanını Rapor tuvaline sürüklediğimizde...

![](media/desktop-tutorial-create-measures/measurestut_salesamountinfieldlist.png)

Aşağıdakine benzer yeni bir grafik görselleştirmesi görünür:

![](media/desktop-tutorial-create-measures/meastut_salesamountchart.png)

SalesAmount alanındaki toplam satış tutarı değerlerinin toplamını gösteren bir Sütun grafiği elde ederiz.  SalesAmount alanımız aslında içeri aktarmış olduğumuz Sales tablosundaki SalesAmount adlı bir sütundur.

SalesAmount sütunu iki milyonun üzerinde satış değeri satırı içerir. Neden tüm bu değerlere ilişkin satırları içeren bir tablo görmediğinizi merak ediyor olabilirsiniz. Power BI Desktop SalesAmount sütunundaki tüm değerlerin sayısal veri türünde olduğunu ve büyük olasılıkla bu değerleri bir şekilde (toplama, ortalama, sayma vb.) toplamak isteyeceğinizi algılar.

Alanlar listesindeki bir alanın yanında bulunan sigma simgesi ![](media/desktop-tutorial-create-measures/meastut_sigma.png), bu alanın sayısal olduğu ve içerdiği değerlerin toplanabildiği anlamına gelir. Bu örnekte SalesAmount alanını seçtiğimizde, Power BI Desktop kendi ölçüsünü oluşturur ve tüm satış tutarlarının toplamı hesaplanarak grafiğimizde görüntülenir.

Toplam, sayısal veri türüne sahip bir alan seçildiğinde belirlenen varsayılan toplama işlemidir ancak bunu oldukça kolay bir şekilde farklı bir toplama türüyle değiştirebiliriz.

**Değer** alanında, **SalesAmount** alanının yanındaki aşağı oka tıklamamız halinde **Ortalama** seçeneğini belirleyebiliriz.

![](media/desktop-tutorial-create-measures/meastut_salesamountaverage.png)

Görselleştirmemiz, SalesAmount alanındaki tüm satış değerlerinin ortalamasını gösterecek şekilde değişir.

![](media/desktop-tutorial-create-measures/meastut_salesamountaveragechart.png)

Toplama türünü, elde etmek istediğimiz sonuca bağlı olarak değiştirebiliriz ancak tüm toplama türleri her sayısal veri türü için geçerli değildir. Örneğin, SalesAmount alanımız için Toplam ve Ortalama kullanılabilir. Minimum ve Maksimum da kullanılabilir işlemler olarak yer alır. Ancak SalesAmount alanımızın değerleri sayısal olmasına rağmen satış tutarları ifade ettiğinden Sayı işlemi bu alan için pek bir anlam ifade etmez.

Her ölçü bir tür toplama işlemi gerçekleştirdiğinden, toplama işlemlerini anlamak ölçüleri anlamaktan geçer. Biraz sonra kendi ölçülerinizden bazılarını oluştururken, toplama işlemi türlerinden Toplam'ı kullanmaya ilişkin daha fazla örneği inceleyeceğiz.

Ölçülerden hesaplanan değerler, raporla etkileşimlerimize bağlı olarak her zaman değişiklik gösterir. Örneğin, **Geography** tablosundaki **RegionCountryName** alanını grafiğimize sürüklersek her bir ülke için satış tutarları ortalanarak görüntülenir.

![](media/desktop-tutorial-create-measures/meastut_salesamountavchartbyrcn.png)

Raporla etkileşimimiz sonucunda bir ölçünün sonucu değiştiğinde, ölçümüzün *bağlamını* etkilemiş oluruz. Aslında, raporunuzla her etkileşime geçtiğinizde, bir ölçünün hesaplama yaptığı ve bu hesaplamanın sonuçlarını görüntülediği bağlamı değiştirmiş olursunuz.

Çoğu durumda Power BI, üzerine düşeni yaparak, eklediğimiz alanlara ve seçtiğimiz toplama türlerine göre hesaplama yapar ve değerler döndürür. Ancak geri kalan durumlarda, daha karmaşık, benzersiz hesaplamalar gerçekleştirmek için kendi ölçülerinizi oluşturmanız gerekebilir.

Power BI Desktop ile kendi ölçülerinizi oluştururken Veri Çözümleme İfadeleri (DAX) formül dilini kullanırsınız. DAX formülleri Excel formülleriyle oldukça benzerdir. Aslında DAX, Excel formüllerinde de bulunan birçok işlevi, işleci ve söz dizimini kullanır. Ancak DAX işlevleri, ilişkisel verilerle çalışacak ve raporlarımızla etkileşime geçtiğimiz sırada daha dinamik hesaplamalar gerçekleştirecek şekilde tasarlanmıştır.

Toplam ve Ortalama gibi basit toplama işlemlerinden daha karmaşık istatistik ve filtreleme işlevlerine kadar her şeyi yapan 200'ün üzerinde DAX işlevi vardır. Bu makalede DAX diliyle ilgili çok fazla ayrıntıya girmeyecek olsak da daha fazla bilgi edinmenize yardımcı olacak birçok kaynağa ulaşabilirsiniz. Bu eğitimi tamamladıktan sonra [Power BI Desktop'ta DAX kullanımıyla ilgili temel bilgiler](desktop-quickstart-learn-dax-basics.md) makalesine göz atmayı unutmayın.

Kendi oluşturduğumuz ölçüler, tercih ettiğimiz tabloya ilişkin Alanlar listesine eklenir. Bunlar *model* ölçüsü olarak bilinir ve tablomuzda bir alan olarak yer alır. Model ölçülerinin harika avantajlarından biri de bunları istediğimiz gibi adlandırarak daha tanımlanabilir hale getirebilmemizdir. Ayrıca bu ölçüleri diğer DAX ifadelerinde bağımsız değişken olarak kullanabilir ve daha karmaşık hesaplamaları hızla gerçekleştiren ölçüler oluşturabiliriz.

## <a name="lets-create-our-own-measure"></a>Artık kendi ölçümüzü oluşturmamıza ne dersiniz?
Net satışlarımızı çözümlemek istediğimizi varsayalım. Alan listesindeki Sales tablomuza baktığımızda, NetSales adlı bir alanın bulunmadığını görürüz. Ancak net satışları hesaplamak üzere kendi ölçümüzü oluşturmak için gereken yapı taşlarına sahibiz.

Satış tutarlarından indirimleri ve iadeleri çıkarmak için bir ölçüye ihtiyacımız var. Ölçümüzün görselleştirmemizde bulunan bağlama ilişkin bir sonucu hesaplamasını istediğimizden, DiscountAmount ve ReturnAmount toplamını SalesAmount toplamından çıkarmamız gerekir. Bu şu anda biraz kafa karıştırıcı gelebilir ancak endişelenmenize gerek yok, kısa bir süre sonra daha iyi anlamaya başlayacaksınız.

### <a name="net-sales"></a>Net satışlar
1.  Alan listesindeki **Sales** tablosuna sağ tıklayın veya bu bölümdeki aşağı oka tıklayın ve ardından **Yeni Ölçü** seçeneğine tıklayın. Böylece yeni ölçümüz, onu daha kolay bir şekilde bulabileceğimiz Sales tablosuna kaydedilir.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure.png)
    
    > [!TIP]
    > Power BI Desktop'ın Giriş sekmesindeki Yeni Ölçü düğmesine tıklayarak da yeni bir ölçü oluşturabilirsiniz.
    > 
    > ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasureribbon.png)
    > 
    > Şeritten bir ölçü oluşturduğunuzda söz konusu ölçü tablolardan herhangi birinde oluşturulabilir. Ölçülerin belirli bir tabloya ait olması gerekmez ancak ölçüleri sizin için en mantıklı gelen tabloda oluşturmanız halinde bunları bulmanız daha kolay olur. Ölçünün belirli bir tabloda bulunmasını istiyorsanız öncelikle tabloya tıklayarak tabloyu etkin hale getirin. Ardından,Yeni Ölçü'ye tıklayın. Bu örnekte, ilk ölçümüzü Sales tablosunda oluşturacağız.
    > 
    > 
    
    Formül çubuğu, Rapor Tuvali'nin en üst kısmında görünür. Burada ölçümüzü yeniden adlandırabilir ve bir DAX formülü girebiliriz.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formulabar.png)
    
    Yeni ölçümüze bir ad verelim. Yeni ölçülere varsayılan olarak Ölçü adı verilir. Oluşturduğumuz ölçüyü yeniden adlandırmadan başka ölçüler oluşturursak bunlar Ölçü 2, Ölçü 3 vb. şekilde adlandırılır. Ölçülerimizin daha tanımlanabilir olmasını istediğimizden yeni ölçümüzü Net Sales olarak adlandıralım.
    
2. Formül çubuğunda **Ölçü**'yü vurgulayın ve ardından **Net Sales** yazın.
    
    Artık formülümüzü girmeye başlayabiliriz.
    
3.  Eşittir işaretinden sonra **S** yazın. S harfi ile başlayan bütün DAX işlevlerini içeren bir açılan öneri listesi görürsünüz. Yazdığımız her bir harfle, öneri listesi, ihtiyacımız olan işleve yaklaşarak küçülür. Aşağı kaydırıp **SUM** seçeneğini belirleyin ve ardından Enter tuşuna basın.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_s.png)
    
    Enter tuşuna basmamızın ardından bir açma ayracı ve SUM işlevine geçirebileceğimiz tüm kullanılabilir sütunların bulunduğu başka bir öneri listesi görünür.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_sum.png)
    
    İfadeler her zaman bir açma ayracı ve kapatma ayracı arasında yer alır. Bu örnekteki ifademiz, SUM işlevine geçirilecek tek bir ifade (toplanacak bir sütun) içerecek. İstediğimiz sütunun ilk harflerini yazarak sütun listemizi daraltabiliriz. Bu örnekte SalesAmount sütununu istediğimizden salesam yazmaya başladığımızda listemiz küçülür ve seçebileceğimiz iki öğe sunulur. Bunlar aslında aynı sütuna yöneliktir. Ölçümüzü SalesAmount sütununun bulunduğu tabloda oluşturduğumuzdan öğelerden biri yalnızca [SalesAmount] ifadesini gösterir. Diğeri ise sütun adının önünde bulunan tablo adıdır.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_salesam.png)
    
    Genel olarak, sütunların tam adlarını girmekte yarar vardır. Bu sayede, formülleriniz daha kolay okunabilir.
    
4. **Sales[SalesAmount]** seçeneğini belirleyin ve bir kapatma ayracı girin.
    
    > [!TIP]
    > Söz dizimi hataları genellikle, eksik veya yanlış yerleştirilmiş bir kapatma ayracından kaynaklanır.
    > 
    > 
    
    Şimdi de diğer iki sütunumuzu çıkaralım.
    
5.  İlk ifademizdeki kapatma ayracından sonra bir boşluk girin ve ardından başka bir boşluk karakterinin izlediği bir eksi işleci (**-**) girin. Ardından, bağımsız değişken olarak **Sales[DiscountAmount]** sütununun yer aldığı başka bir SUM işlevi girin.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_discamount.png)
    
    Formülümüz için sahip olduğumuz alan azalmaya başladı. Hiç sorun değil.
    
6.  Formül çubuğunun sağındaki aşağı yönde köşeli çift ayraca tıklayın.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_chevron.png)
    
    Artık daha fazla alana sahibiz. Alt-Enter tuşlarına basarak formülümüzün yeni kısımlarını yeni bir satıra girebiliriz. Ayrıca Tab tuşunu kullanarak formül parçalarını yana da kaydırabiliriz.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_formula_expanded.png)
    
    Şimdi formülümüzün son kısmını ekleyebiliriz.
    
7.  Bağımsız değişken olarak **Sales[ReturnAmount]** sütununun bulunduğu başka bir SUM işlevi tarafından izlenen bir eksi işleci daha ekleyin.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_newmeasure_complete.png)
    
    Formülümüz artık hazır gibi görünüyor.

8.  İşlemi tamamlamak için Enter tuşuna basın veya formül çubuğundaki onay işaretine tıklayın. Formül doğrulanır ve Sales tablosundaki alan listesine eklenir.

### <a name="lets-add-our-new-measure-to-a-report"></a>Yeni ölçümüzü bir rapora ekleyelim
Artık Net Sales ölçümüzü rapor tuvaline ekleyebiliriz. Böylece, net satışlar, rapora eklediğimiz diğer tüm alanlar için de hesaplanır. Şimdi de ülkelere göre net satışlara bakalım.

1.  **Sales** tablosundaki **Net Sales** ölçüsünü Rapor tuvaline sürükleyin.
    
2. Şimdi ise **Geography** tablosundaki **RegionCountryName** alanını grafiğe sürükleyin.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_byrcn.png)
    
    Biraz daha veri ekleyelim.
    
3.  Net satışlar ve satış tutarı arasındaki farkı görmek için **SalesAmount** alanını grafiğe sürükleyin.
    
    Artık gerçekten de grafiğimizde iki ölçü var. Otomatik olarak toplanmış olan SalesAmount ölçüsü ve kendi oluşturduğumuz Net Sales ölçüsü. Her iki durumda da sonuçlar, grafiğimizde bulunan başka bir alan bağlamında (RegionCountryName sütunundaki ülkeler) hesaplanmıştır.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_byrcnandsalesamount.png)
    
    Net satışlarımızın ve satış tutarlarımızın takvim yılına göre dağılımını görebilmek için bir Dilimleyici ekleyelim.
    
4.  Grafiğin yanındaki boş bir alana ve ardından, **Görsel Öğeler** bölmesindeki Tablo görselleştirmesine tıklayın.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_blanktablevisbutton.png)
    
    Bu işlemden sonra Rapor tuvalinde boş bir tablo görselleştirmesi oluşturulur.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_blanktable.png)
    
5.  **Calendar** tablosundaki **Year** alanını yeni boş tabloya sürükleyin.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_yearaggtable.png)
    
    Year sayısal bir alan olduğundan, Power BI Desktop bu alanın değerlerini toplamış ve bize bir grafik sunmuştur. Ancak bu, bir Dilimleyici kadar işlevsel değildir.
    
6. **Değerler** bölümünde, **Year** alanının yanındaki aşağı oka ve ardından **Özetleme**'ye tıklayın.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_year_donotsummarize.png)
    
    Artık tablo görselleştirmemizdeki Year alanını bir Dilimleyici olarak değiştirebiliriz.

    7.  **Görsel Öğeler** bölmesinde, **Dilimleyici** görselleştirmesine tıklayın.

    ![](media/desktop-tutorial-create-measures/meastut_netsales_year_changetoslicer.png)
    
    Artık Year Dilimleyicisi'ne sahibiz. Herhangi bir yılı veya bir grup yılı seçerek raporumuzun görselleştirmelerinin uygun şekilde dilimlenmesini sağlayabiliriz.
    
8. **2013**'e tıklayın. Grafiğin değiştiğini görürsünüz. Net Sales ve SalesAmount ölçülerimiz, yalnızca 2013 için yeni sonuçları gösterecek şekilde yeniden hesaplanır. Böylece, ölçülerimizin hesaplandığı ve sonuçları görüntülediği bağlamı tekrar değiştirmiş olduk.
    
    ![](media/desktop-tutorial-create-measures/meastut_netsales_chartslicedbyyear.png)

## <a name="lets-create-another-measure"></a>Başka bir ölçü oluşturalım
Kendi ölçülerinizi oluşturmayı öğrendiğinize göre, bir tane daha oluşturalım.

### <a name="net-sales-per-unit"></a>Birim başına net satışlar
Peki ya birim başına en çok satışın hangi ürünlerde yapıldığını bulmak istesek?

Bunun için başka bir ölçü daha oluşturabiliriz. Bu durumda, net satışları satılan birim miktarına bölmemiz gerekir. Aslında yapmak istediğimiz, Net Sales ölçümüzün sonucunu Sales[SalesQuantity] toplamına bölmektir.

1.  Sales veya Products tablosunda **Net Sales per Unit** adlı yeni bir ölçü oluşturun.
    
    Bu ölçüde, daha önce oluşturduğumuz Net Sales ölçüsünü kullanacağız. DAX formül dilini kullanarak formülümüzde diğer ölçülere başvurabiliriz.
    
2.  **Net Sales** yazmaya başlayın. Öneri listesi ne ekleyebileceğimizi gösterir. **[Net Sales]** seçeneğini belirleyin.
    
    ![](media/desktop-tutorial-create-measures/meastut_nspu_formulastep2a.png)
    
    Ayrıca, yalnızca bir açma ayracı (**[**) yazarak da başka bir ölçüye başvurabiliriz. Öneri listesi, yalnızca formülümüze ekleyebileceğimiz ölçüleri gösterir.
    
    ![](media/desktop-tutorial-create-measures/meastut_nspu_formulastep2b.png)
    
3.  **[Net Sales]** ifadesinden hemen sonra sırasıyla bir boşluk, bölme işleci (**/**) ve SUM işlevi girip **Quantity** yazın. Öneri listesi, adında Quantity bulunan tüm sütunları gösterir. **Sales[SalesQuantity]** seçeneğini belirleyin. Formülün aşağıdaki gibi görünmesi gerekir:
    
    > **Net Sales per Unit = [Net Sales] / SUM(Sales[SalesQuantity])**
    > 
    > 
    
    Çok iyi görünüyor, değil mi? DAX Editor'ın arama ve öneri işlevleri kullanıldığında, DAX formüllerini girmek oldukça kolay hale gelir. Şimdi yeni Net Sales per Unit ölçümüzle neler elde ettiğimize bakalım.
    
4. **Net Sales per Unit** ölçüsünü rapor tuvalindeki boş bir alana sürükleyin.
    
    ![](media/desktop-tutorial-create-measures/meastut_nspu_chart.png)
    
    Pek bir işe yaramadı gibi görünüyor olabilir. Endişelenmeyin.
    
5.  Grafik görselleştirmesi türünü **Ağaç Haritası** olarak değiştirin.
    
    ![](media/desktop-tutorial-create-measures/meastut_nspu_changetotreemap.png)
    
6. Şimdi de **ProductCategory** tablosundaki **ProductCategory** alanını aşağıdaki **Group** alanına sürükleyin.
    
    ![](media/desktop-tutorial-create-measures/meastut_nspu_byproductcat.png)
    
    Bu işe yarar bir bilgi. Peki ya ürüne göre net satışları görmek istersek?
    
7. **ProductCategory** alanını kaldırın ve ardından bunun yerine **Product** tablosundaki **ProductName** alanını **Group** alanına sürükleyin. 
    
    ![](media/desktop-tutorial-create-measures/meastut_nspu_byproductname.png)
    
    Şu anda dilediğimiz gibi deneme yapıyor olabiliriz ancak kabul etmeniz gerekir ki bu oldukça havalı. Elbette bu ağaç haritasını birçok şekilde filtreleyebiliriz ancak bu konu eğitimimizin kapsamında yer almıyor.

## <a name="what-weve-learned"></a>Öğrendiklerimiz
Ölçüler, verilerimizden istediğimiz öngörüleri elde etmede büyük ölçüde etkili. Formül çubuğunu kullanarak ölçü oluşturmayı öğrendik. Ölçüleri, bizim için en çok işe yarayacak şekilde adlandırabiliriz. Böylece öneri listesi, formüllerimize eklenecek doğru öğenin bulunmasını ve seçilmesini kolay hale getirir. Ayrıca, ölçülerdeki hesaplamaların sonuçlarının diğer alanlara veya ölçü formülünüzdeki başka ifadelere göre değiştiği bağlam kavramıyla da tanışmış olduk.

## <a name="next-steps"></a>Sonraki adımlar
DAX formüllerini daha ayrıntılı bir şekilde incelemek ve daha gelişmiş ölçüler oluşturmak istiyorsanız [Power BI Desktop'ta DAX kullanımıyla ilgili temel bilgiler](desktop-quickstart-learn-dax-basics.md) başlıklı makaleye bakabilirsiniz. Bu makale, DAX'ta bulunan söz dizimi ve işlevler gibi temel kavramlara ve bağlamın daha kapsamlı bir şekilde anlaşılmasına odaklanmıştır.

Sık kullanılanlar listenize [Veri Çözümleme İfadeleri (DAX) Başvurusu](https://msdn.microsoft.com/library/gg413422.aspx)'nu eklediğinizden emin olun. Burada DAX söz dizimi, işleçleri ve 200'ü aşkın DAX işleviyle ilgili ayrıntılı bilgi bulabilirsiniz.

