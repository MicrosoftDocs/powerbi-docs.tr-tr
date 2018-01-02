---
title: "Eğitim: Power BI Desktop'ta, hesaplanmış sütun oluşturma"
description: "Eğitim: Power BI Desktop'ta, hesaplanmış sütun oluşturma"
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
ms.date: 09/06/2017
ms.author: davidi
ms.openlocfilehash: 7e959054300dafcab5f38bfce121fe0ac91dca06
ms.sourcegitcommit: f2b38777ca74c28f81b25e2f739e4835a0ffa75d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/17/2017
---
# <a name="tutorial-create-calculated-columns-in-power-bi-desktop"></a>Eğitim: Power BI Desktop'ta, hesaplanmış sütun oluşturma
Bazen çözümlediğiniz veriler, istediğiniz sonuçlar için ihtiyaç duyduğunuz bir alanı içermeyebilir. Hesaplanmış sütunlar bunun için vardır. Hesaplanmış sütunlar, bir sütunun değerlerini Veri Çözümleme İfadeleri (DAX) formülleri kullanarak tanımlar. Bu sütun değerleri, modelin başka bir yerindeki birkaç farklı sütundan alınmış metin değerlerini birleştirmekten, diğer değerlerden yola çıkarak bir sayısal değer hesaplamaya kadar her şey olabilir. Örneğin, verilerinizde (Alanlar listesinde alanlar olarak) City ve State sütunları var ancak ikisini birden Miami, FL gibi tek bir Location alanında tek bir değer olarak görmek istiyorsunuz. Bu tam olarak hesaplanmış sütunların işidir.

Hesaplanmış sütunlar, DAX formüllerini temel almaları açısından ölçülere benzer ancak kullanımları birbirinden farklıdır. Ölçüler çoğunlukla, sonuçları bir tablo satırına, veya bir görselleştirmenin Eksen, Açıklama ya da Grup kısmındaki diğer alanlara göre hesaplamak için kullanılır. Buna karşın hesaplanmış sütunlar, sütunun sonucunu tablo satırının kendisinde veya görselleştirmenin Eksen, Açıklama ya da Grup alanında gösterir.

Bu eğitim, hesaplanmış sütunları anlamanız ve Power BI Desktop'ta kendi hesaplanmış sütunlarınızı oluşturmanız konusunda size yol gösterecektir. Eğitim, Power BI Desktop'ı daha gelişmiş modeller oluşturmak için kullanmaya alışmış Power BI kullanıcılarına yöneliktir. Verileri içeri aktarmak için Sorgu kullanmaya, birden çok ilişkili tabloyla çalışmaya ve Rapor Tuvaline alan eklemeye alışkın olmanız gerekir. Power BI Desktop'a yeni başladıysanız [Power BI Desktop ile çalışmaya başlama](desktop-getting-started.md) makalesine mutlaka göz atın.

Bu eğitimdeki adımları tamamlamak için [Contoso Sales Sample for Power BI Desktop](http://download.microsoft.com/download/4/6/A/46AB5E74-50F6-4761-8EDB-5AE077FD603C/Contoso%20Sales%20Sample%20for%20Power%20BI%20Desktop.zip) dosyasını indirmeniz gerekir. Bu örnek dosyanın aynısı, [Power BI Desktop'ta kendi ölçülerinizi oluşturma](desktop-tutorial-create-measures.md) eğitiminde de kullanılmıştır. Bu dosya, Contoso, Inc adlı kurgusal şirketin satış verilerini içerir. Dosyadaki veriler bir veritabanından içeri aktarıldığı için veri kaynağına bağlanamazsınız veya verileri Sorgu Düzenleyicisi'nde görüntüleyemezsiniz. Dosyayı bilgisayarınıza indirip Power BI Desktop'ta açın.

## <a name="lets-create-a-calculated-column"></a>Şimdi bir hesaplanmış sütun oluşturalım
Ürün kategorilerini ürün alt kategorileriyle birlikte satırlarda tek bir değer olarak görmek istediğimizi varsayalım (Cell phones - Accessories, Cell phones - Smart phones & PDAs vb. gibi). Rapor Görünümü veya Veri Görünümünde (burada Rapor Görünümünü kullanıyoruz) Alanlar listesindeki ürün tablolarımıza baktığımızda bize istediğimizi sunan bir alan olmadığını görüyoruz. Ancak, ayrı ayrı tablolarda ProductCategory ve ProductSubcategory alanları bulunuyor.

 ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_nonewcol.png)

Bu iki sütundaki değerleri birleştirerek yeni sütunumuzda yeni değerler üretecek bir hesaplanmış sütun oluşturalım. İlginçtir ki, iki ayrı tablodan veri alıp tek bir sütunda birleştirmemiz gerekiyor. Yeni sütunumuzu oluşturmak için DAX kullanacağımız için, var olan farklı tabloların birbiri arasındaki ilişkiler dahil olmak üzere elimizdeki modelin tam gücünden yararlanabiliriz.

### <a name="to-create-a-productfullcategory-column"></a>Bir ProductFullCategory sütunu oluşturmak için
1.  Alanlar listesindeki **ProductSubcategory** tablosuna sağ tıklayın veya yanındaki aşağı oka tıklayın ve **Yeni Sütun**'u seçin. Böylece yeni sütunumuzun ProductSubcategory tablosuna ekleneceğinden emin olduk.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_newcolumn.png)
    
    Formül çubuğu, Rapor tuvalinin veya Veri kılavuzunun üzerinde görünür. Burada sütunumuzu yeniden adlandırabilir ve bir DAX formülü girebiliriz.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_newcolumnformula.png)
    
    Varsayılan olarak yeni bir hesaplanmış sütunun adı sadece Sütun olur. Bunu yeniden adlandırmadan başka sütunlar oluşturursak bu yeni sütunların adları da Sütun 2, Sütun 3 vs. şeklinde ilerler. Sütunlarımızın birbirine karışmamasını isteriz, bu yüzden yeni sütunumuza yeni bir ad verelim.
    
2.  Formül çubuğunda **Sütun** adı zaten vurgulanmış olduğu için **ProductFullCategory** yazmanız yeterlidir.
    
    Şimdi formülümüzü girmeye başlayabiliriz. Yeni sütunumuzdaki değerlerin ProductCategory tablosundan ProductCategory adıyla başlamasını istiyoruz. Bu sütun farklı ancak ilişkili bir tabloda olduğu için sütuna [RELATED](https://msdn.microsoft.com/library/ee634202.aspx) işlevini kullanarak ulaşacağız.
    
3.  Eşittir işaretinden sonra **R** yazın. R harfi ile başlayan bütün DAX işlevlerini içeren bir açılır öneri listesi göreceksiniz. Yazdığımız her bir harfle, öneri listesi ihtiyacımız olan işleve yaklaşarak küçülür. İşlevin yanında işlevin bir açıklamasını görürsünüz. Aşağıya inip Enter'a basarak **RELATED**'ı seçin.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_1.png)
    
    Bir açma parantezi ve RELATED işlevine geçirilebilecek bütün kullanılabilir sütunların öneri listesi belirir. Bir açıklama ve beklenen parametrelerin ayrıntıları da gösterilir.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_2.png)
    
    Bir ifade her zaman bir açma parantezi ve kapanış parantezi arasında görünür. Bu örnekte, ifademiz RELATED işlevine geçirilmiş tek bir bağımsız değişken içerecektir. Bu, değeri döndürülecek olan ilgili sütundur. Sütun listesi sadece ilgili sütunları gösterecek şekilde otomatik olarak daraltılır. Bu örnekte, ProductCategory tablosundaki ProductCategory sütununu istiyoruz.
    
    **ProductCategory[ProductCategory]**'yi seçin ve ardından bir kapanış parantezi ekleyin.
    
    > [!TIP]
    > Söz dizimi hatalarının sebebi genellikle eksik veya yanlış yerleştirilmiş bir kapanış parantezidir. Ancak, parantezi unutsanız bile Power BI Desktop genellikle ekler.
    > 
    > 
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_3.png)
    
4. Her bir değeri ayırmak için tire simgesi eklemeniz gerekir. Diğer bir deyişle, ilk ifadenin kapanış parantezinden sonra bir boşluk koyun, ve işareti (&) yazın, tırnak işareti yazın, boşluk koyun, tire (-) ekleyin, bir boşluk daha koyun, kapanış tırnağı ile bir ve işareti daha yazın. Formülünüzün şöyle görünmesi gerekir:
    
    **ProductFullCategory = RELATED(ProductCategory[ProductCategory]) & " - " &**
    
    > [!TIP]
    > Formül düzenleyicisini genişletmek için formül çubuğunun sağındaki aşağı köşeli çift ayraca tıklayın. Bir satır aşağı inmek için Alt ve Enter'a, içeriği yana kaydırmak için Tab tuşuna basın.
    > 
    > 
    
5.  Son olarak, formülü tamamlamak için bir sol köşeli ayraç daha açın ve formülü bitirmek için **[ProductSubcategory]** sütununu seçin. Formülünüzün şöyle görünmesi gerekir:
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_5.png)
    
    ProductSubcategory sütununu çağıran ikinci ifadede bir kez daha RELATED işlevini kullanmadığımızı fark edeceksiniz. Bunun sebebi, bu sütunun zaten yeni sütunumuzu oluşturduğumuz tabloda olmasıdır. Tablo adıyla (tam ad) veya tablo adı olmadan (nitelemesiz ad) [ProductCategory]'ye girebiliriz.
    
6.  Enter tuşuna basarak veya formül çubuğundaki onay işaretine tıklayarak formülü tamamlayın. Formül doğrulanır ve **ProductSubcategory** tablosundaki alan listesine eklenir.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_pfc_6.png)
    
    Hesaplanmış sütunların, alan listesinde özel bir simge ile belirtildiğini fark edeceksiniz. Bu simge, söz konusu sütunların formül içerdiğini gösterir. Bunlar yalnızca Power BI Desktop'ta böyle görünür. Power BI hizmetinde (Power BI sitenizde) bir formülü değiştirme olanağı yoktur. Bu nedenle, bir hesaplanmış sütun alanı simge içermez.
    
## <a name="lets-add-our-new-column-to-a-report"></a>Yeni sütunumuzu bir rapora ekleyelim
Şimdi yeni ProductFullCategory sütunumuzu rapor tuvaline ekleyebiliriz. ProductFullCategory'e göre SalesAmount'a bakalım.

**ProductFullCategory** sütununu **ProductSubcategory** tablosundan Rapor tuvaline sürükleyin ve daha sonra **Sales** tablosundaki **SalesAmount** alanını grafiğe sürükleyin.

![](media/desktop-tutorial-create-calculated-columns/calccol_fileds_report_1.png)

## <a name="lets-create-another"></a>Şimdi bir tane daha oluşturalım
Hesaplanmış sütun oluşturmayı öğrendiğinize göre bir tane daha hesaplanmış sütun oluşturabiliriz.

Contoso Sales Sample for Power BI Desktop modeli, hem etkin hem de etkin olmayan mağazaların satış verilerini içerir. Verileri gösterilen mağazalar etkin değilse bunun net bir şekilde anlaşılmasını istiyoruz. Bu nedenle Active StoreName adlı bir alan istiyoruz. Bunu yapmak için başka bir sütun oluşturacağız. Bu örnekte, etkin olmayan mağazanın adının, yeni Active StoreName sütunumuz (alan olarak) tarafından "Inactive" olarak, etkin olan mağazanınsa yine bu sütun tarafından gerçek adıyla gösterilmesini istiyoruz.

Neyse ki Stores tablomuzda, etkin mağazalar için On, etkin olmayan mağazalar içinse Off değerini içeren Status adlı bir sütun var. Yeni sütunumuzda yeni değerler oluşturmak için Status sütunundaki her satır için değerleri sınayabiliriz.

### <a name="to-create-an-active-storename-column"></a>Bir Active StoreName sütunu oluşturmak için
1.  **Stores** tablosunda **Active StoreName** adlı yeni bir hesaplanmış sütun oluşturun.
    
    Bu sütun için DAX formülümüz her mağazanın durumunu denetleyecek. Mağazanın durumu On ise formülümüz mağazanın adını döndürecek. Off ise, "Inactive" adı belirecek. Bunu yapmak için mantıksal [IF](https://msdn.microsoft.com/library/ee634824.aspx) işlevini kullanarak mağazanın durumunu sınayacağız ve sonucun true veya false olma durumuna göre belirli bir değer döndüreceğiz.
    
2.  **IF** yazmaya başlayın. Öneri listesi ne ekleyebileceğimizi gösterir. **IF**'i seçin.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_1.png)
    
    IF için ilk bağımsız değişken bir mantıksal sınamadır. Bir mağazanın durumunun "On" olup olmadığını sınamak istiyoruz.
    
3.  Bir açma köşeli ayracı **[** ekleyin, bu Stores tablosundan sütun seçmemize olanak sağlar. **[Status]**'u seçin.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_2.png)
    
4.  **[Status]** ifadesinden hemen sonra **="On"** yazın ve ikinci bağımsız değişkeni girmek için virgül (**,**) koyun. Araç ipucu, sonucun true olduğu durumlara ilişkin değeri eklememizi öneriyor.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_3.png)
    
5.  Mağaza On ise, mağaza adını göstermek istiyoruz. Bir açma köşeli ayracı **[** yazın ve **[StoreName]** sütununu seçin, daha sonra üçüncü bağımsız değişkeni girmek için bir virgül daha koyun.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_step5.png)
    
6.  Sonucun false olduğu durumlar için bir değer eklememiz gerekiyor. Bu örnekte değerin **"Inactive"** olmasını istiyoruz.
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_step6.png)
    
7.  Enter tuşuna basarak veya formül çubuğundaki onay işaretine tıklayarak formülü tamamlayın. Formül doğrulanır ve Stores tablosundaki alan listesine eklenir.
    
    Diğer herhangi bir alan gibi yeni Active StoreName sütunumuzu da görselleştirmelerde kullanabiliriz. Bu grafikte, durumu On olan mağazalar adlarıyla ayrı ayrı, durumu Off olan mağazalar ise grup halinde ve Inactive olarak gösterilir. 
    
    ![](media/desktop-tutorial-create-calculated-columns/calccol_activestore_viz.png)
    
## <a name="what-weve-learned"></a>Öğrendiklerimiz
Hesaplanmış sütunlar verilerimizi zenginleştirerek daha kolay öngörüler sağlayabilir. Formül çubuğunu kullanarak hesaplanmış sütun oluşturmayı, öneri listesinin kullanımını ve yeni sütunlarımızı adlandırmanın en iyi yollarını öğrendik.

## <a name="next-steps"></a>Sonraki adımlar
DAX formüllerine ilişkin derinlemesine bilgi edinmek ve daha gelişmiş DAX formülleriyle hesaplamış sütunlar oluşturmak istiyorsanız bkz. [Power BI Desktop'ta DAX kullanımıyla ilgili temel bilgiler](desktop-quickstart-learn-dax-basics.md). Bu makale söz dizimi ve işlevler gibi DAX temel kavramlarını ele alır ve bağlama ilişkin daha kapsamlı bilgi sunar.

Sık kullanılanlar listenize [Veri Çözümleme İfadeleri (DAX) Başvurusu](https://msdn.microsoft.com/library/gg413422.aspx)'nu eklediğinizden emin olun. Burada DAX söz dizimi, işleçleri ve 200'ü aşkın DAX işleviyle ilgili ayrıntılı bilgi bulabilirsiniz.

