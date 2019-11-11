---
title: Power BI Desktop’ta çoka çok ilişkileri
description: Power BI Desktop’ta çoka çok kardinalitesine sahip ilişkileri kullanın
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 02/13/2019
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 578d5f77753884575111b3247f5aa4d3ae79e179
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73866810"
---
# <a name="relationships-with-a-many-many-cardinality-in-power-bi-desktop"></a>Power BI Desktop’ta çoka çok kardinalitesine sahip ilişkiler

Power BI Desktop'daki *çoka çok kardinalitesine sahip ilişkiler* özelliğiyle *Çoka Çok* kardinalitesini kullanan tabloları birleştirebilirsiniz. Kolayca ve sezgisel bir şekilde iki veya daha fazla veri kaynağı içeren veri modelleri oluşturabilirsiniz. *Çoka çok kardinalitesine sahip ilişkiler* özelliği, Power BI Desktop'taki daha kapsamlı *bileşik modeller* özelliğinin bir parçasıdır.

!["İlişkiyi düzenle" bölmesindeki bir çok-çok ilişkisi](media/desktop-many-to-many-relationships/many-to-many-relationships_01.png)

Power BI Desktop'taki *çoka çok kardinalitesine sahip ilişkiler* özelliği, birbiriyle ilişkili üç özellikten biridir:

* **Bileşik modeller**: Raporda DirectQuery bağlantıları ve içeri aktarma da dahil olmak üzere herhangi bir birleşimde iki veya daha fazla veri bağlantısına izin verir. Daha fazla bilgi için bkz. [Power BI Desktop’ta bileşik modeller](desktop-composite-models.md).

* **Çoka çok kardinalitesine sahip ilişkiler**: *Bileşik modeller* sayesinde tablolar arasında *çoka çok kardinalitesine sahip ilişkiler* kurabilirsiniz. Bu yaklaşım tablolardaki benzersiz değer gereksinimlerini ortadan kaldırır. Ayrıca yalnızca ilişki kurmak için yeni tablo eklenmesi gibi eski geçici çözümleri de devre dışı bırakır. Bu özellik bu makalede ayrıntılı olarak açıklanmaktadır.

* **Depolama modu**: Artık arka uç veri kaynaklarını sorgulaması gereken görselleri belirtebilirsiniz. Sorgu gerektirmeye görseller DirectQuery tabanlı olsa dahi içeri aktarılmaz. Bu özellik, performansı artırmanıza ve arka uç yükünü azaltmanıza yardımcı olur. Daha önce, sorguları başlatan dilimleyiciler gibi basit görseller bile arka uç kaynaklara gönderiliyordu. Daha fazla bilgi için bkz. [Power BI Desktop’ta depolama modu (önizleme)](desktop-storage-mode.md).

## <a name="what-relationships-with-a-many-many-cardinality-solves"></a>*Çoka çok kardinalitesine sahip ilişkiler* neye çözüm getirir?

*Çoka çok kardinalitesine sahip ilişkiler* özelliği kullanıma sunulmadan önce iki tablo arasındaki ilişki Power BI’da tanımlanıyordu. İlişkideki tablo sütunlarından en az birinde benzersiz değerlerin bulunması şarttı. Ancak genellikle benzersiz değer içeren sütun bulunmuyordu. 

Örneğin, iki tabloda da *Ülke* etiketine sahip bir sütun bulunabiliyor ama *Ülke* değerleri iki tabloda da benzersiz olmuyordu. Bu tabloları birleştirmek için geçici bir çözüme ihtiyaç duyuluyordu. Geçici çözümlerin biri, modele gerekli benzersiz değerlerin bulunduğu ek tablolar eklemekti. *Çoka çok kardinalitesine sahip ilişkiler* özelliği sayesinde bu tür tabloları **Çoka Çok** kardinalitesine sahip bir ilişki kullanarak doğrudan birleştirebilirsiniz.  

## <a name="use-relationships-with-a-many-many-cardinality"></a>*Çoka çok kardinalitesine sahip ilişkileri* kullanma

Power BI'da iki tablo arasındaki ilişkiyi tanımlarken, ilişkinin kardinalitesini tanımlamanız gerekir. Örneğin *ProductSales* ve *Product* arasında *ProductSales[ProductCode]* ve *Product[ProductCode]* sütunları kullanılarak kurulan ilişkinin kardinalitesi *Çok-1* olacaktır. Her ürün için birden fazla satış olduğundan ve *Product* tablosundaki *(ProductCode)* sütunu benzersiz olduğundan ilişki bu şekilde tanımlanır. Bir ilişkinin kardinalitesini *Çok-1*, *1-Çok* veya *1-1* olarak tanımladığınızda Power BI doğrulama gerçekleştirerek seçtiğiniz kardinalitenin gerçek verilerle eşleştiğinden emin olmanızı sağlar.

Örneğin, aşağıdaki görüntüde yer alan basit modele göz atalım:

![İlişki görünümü](media/desktop-many-to-many-relationships/many-to-many-relationships_02.png)

Şimdi *Product* tablosunda aşağıdaki gibi yalnızca iki satır görüntülendiğini düşünelim:

![İki satırlı Product tablosu görseli](media/desktop-many-to-many-relationships/many-to-many-relationships_03.png)

Aynı zamanda *Sales* tablosunda C ürünü için bir satırın da bulunduğu yalnızca dört satır olduğunu düşünelim. Bilgi tutarlılığı hatası nedeniyle C ürününün satırı *Product* tablosunda mevcut değildir.

![Dört satır içeren Sales tablosu](media/desktop-many-to-many-relationships/many-to-many-relationships_04.png)

*ProductName* ve *Price* (*Product* tablosundan) ile her ürün için toplam *Qty* değeri (*ProductSales* tablosundan) şu şekilde gösterilecektir: 

![Ürün adını, fiyatını ve miktarını gösteren görsel](media/desktop-many-to-many-relationships/many-to-many-relationships_05.png)

Yukarıdaki görüntüde gördüğünüz gibi C ürünüyle ilişkilendirilmiş boş bir *ProductName* satırı vardır. Bu boş satır aşağıdakileri gösterir:

* *Product* tablosunda karşılık gelen satırları bulunmayan *ProductSales* tablosu satırları. Bu örnekte *C* ürünü için gördüğümüz gibi bir bilgi tutarlılığı sorunu vardır.

* *ProductSales* tablosunda, yabancı anahtar sütunu null olan herhangi bir satır. 

Bu nedenlerden dolayı, her iki durumda da boş satır *ProductName* ve *Price* değerlerinin bilinmediği satışları gösterir.

Bazen tablolar iki sütunla birleştirilebilir ama sütunlardan hiçbiri benzersiz değildir. Örneğin, aşağıdaki iki tabloyu inceleyin:

* *Sales* tablosu *State* temelinde satış verilerini gösterir ve her satır o eyaletin satış türüne ilişkin satış tutarını gösterir. Eyaletler CA, WA ve TX olarak belirlenmiştir. 

    ![Eyalete göre satışları gösteren satış tablosu](media/desktop-many-to-many-relationships/many-to-many-relationships_06.png)

* *CityData* tablosu, şehirlerin nüfus ve eyalet (CA, WA ve New York dahil) verilerini gösterir.

    ![Şehir, eyalet ve nüfus bilgilerini gösteren satış tablosu](media/desktop-many-to-many-relationships/many-to-many-relationships_07.png)

Her iki tabloda da *State* sütunu bulunur ve her Eyaletin toplam nüfusuyla birlikte eyalet temelinde satış toplamını raporlamak isteyebilirsiniz ama bir sorun vardır: *State* sütunu iki tabloda da benzersiz değildir. 

## <a name="the-previous-workaround"></a>Eski geçici çözüm

Temmuz 2018 öncesi Power BI Desktop sürümlerinde kullanıcıların bu tablolar arasında doğrudan ilişki oluşturması mümkün değildi. Yaygın bir geçici çözüm olarak aşağıdakiler yapılırdı:

* Yalnızca benzersiz *State* kimliklerini içeren üçüncü bir tablo oluşturulurdu. Tablo aşağıdakilerden biri veya hepsi olabilir:
  * Hesaplanan tablo (Veri Çözümleme İfadeleri [DAX] kullanılarak tanımlanmış).
  * Tabloların birinden çekilen benzersiz kimlikleri görüntüleyebilecek ve Sorgu Düzenleyicisinde tanımlanan bir sorguyu temel alan bir tablo.
  * Birleştirilmiş tam küme.

* İki özgün tablo, yaygın *Çok-1* ilişkileri kullanılarak yeni tabloyla ilişkilendirilirdi.

Geçici çözüm tablosunu görünür şekilde bırakabilir veya gizleyerek **Alanlar** listesinde görünmemesini sağlayabilirdiniz. Tabloyu gizlediğinizde *Çok-1* ilişkileri genellikle iki yönde de filtreleme yapacak şekilde ayarlanırdı ve iki tablodaki *State* alanını da kullanmanız mümkün olurdu. Sonraki çapraz filtreleme işlemleri diğer tabloya da yayılırdı. Bu yaklaşım aşağıdaki görüntüde gösterilmiştir:

![İlişki görünümü](media/desktop-many-to-many-relationships/many-to-many-relationships_08.png)

*State* (*CityData* tablosundan) ile toplam *Population* ve toplam *Sales* değerlerini gösteren bir görsel aşağıdaki gibi olacaktır:

![Tablo görseli](media/desktop-many-to-many-relationships/many-to-many-relationships_09.png)

> [!NOTE]
> Bu geçici çözümde *CityData* tablosundan eyalet değerinin kullanılmasıyla, yalnızca söz konusu tablodaki eyaletlerin listelendiğine (ve dolayısıyla TX eyaletinin hariç tutulduğuna) dikkat edin. Aynı zamanda, *Çok-1* ilişkilerinden farklı olarak, toplam satırı tüm *Sales* değerlerini (TX eyaletininkiler de dahil) içerirken ayrıntılar bu tür eşleşmeyen satırları kapsayan boş satırı içermez. Benzer biçimde, *State* için null değeri olan bir *Sales* değerini kapsayacak boş bir satır yoktur.

Bu görsele *City* verilerini de eklerseniz *City* başına nüfus değeri biliniyor olsa da *City* için gösterilen *Sales* değeri yalnızca ilgili *State* için gösterilen *Sales* değerini tekrarlar. Bu, aşağıdaki görüntüde gösterildiği gibi bir sütunda gruplandırma, belirli toplu ölçü ile ilgisiz olduğunda karşılaşılan bir durumdur:

![Tablo görseli](media/desktop-many-to-many-relationships/many-to-many-relationships_10.png)

Bu geçici çözümde yeni *Sales* tablosunu tüm *States* değerlerinin birleşimi olarak tanımlarsak ve **Fields** listesinde görünür hale getirirsek aşağıdaki görüntüde olduğu gibi aynı görselde hem *State* (yeni tabloda) hem de toplam *Population* ve toplam *Sales* değerleri gösterilir:

![Tablo görseli](media/desktop-many-to-many-relationships/many-to-many-relationships_11.png)

Gördüğünüz gibi *Sales* verileri bilinen ancak *Population* verileri bilinmeyen *TX* ve *Population* verileri bilinen ancak *Sales* verileri bilinmeyen *New York* dahil edilecektir. Bu geçici çözüm çok uygun bir çözüm değildir ve birçok sorun barındırmaktadır. Çoka çok kardinalitesiyle ilişkiler oluşturulduğunda, aşağıdaki bölümde açıklandığı gibi bu sorunlara çözüm getirilmiştir.

## <a name="use-relationships-with-a-many-many-cardinality-instead-of-the-workaround"></a>Geçici çözüm yerine *çoka çok kardinalitesine sahip ilişkileri* kullanın

Power BI Desktop'ın Temmuz 2018 sürümünden başlayarak yukarıda bahsedilenler gibi tabloları benzer geçici çözümler aramadan doğrudan birbirine bağlayabilirsiniz. Artık ilişki kardinalitesini *Çok-Çok* olarak ayarlamak mümkündür. Bu ayar, iki tabloda da benzersiz değerler olmadığını belirtir. Bu tür ilişkiler için, hangi tablonun diğer tabloyu filtrelediğini denetleyebilir veya her iki tablo da birbirini filtrelediğinde iki yönlü filtreleme olmasını sağlayabilirsiniz.  

*Power BI Desktop*'ta, hiçbir tablonun ilişkideki sütunlar için benzersiz değerler içermediği saptandığında kardinalite varsayılan olarak Çok-Çok olarak ayarlanır. Bu tür durumlarda ilişki ayarının beklediğiniz davranışa uyduğunu, veri sorununa yol açan beklenmedik bir etkisi olmadığını onaylamak için bir uyarı görüntülenir. 

Örneğin *CityData* ile *Sales* arasında filtrelerin *CityData* alanından *Sales* alanına akış gerçekleştireceği bir ilişki oluşturduğunuzda Power BI Desktop'ta görüntülenen **İlişkiyi düzenle** penceresi aşağıdaki gibi olacaktır:

!["İlişkiyi düzenle" penceresi](media/desktop-many-to-many-relationships/many-to-many-relationships_01.png)

Sonuçta elde edilen **İlişki** görünümü, iki tablo arasında doğrudan çok-çok ilişkisini gösterecektir. Tabloların **Alanlar** listesindeki görünümü ve görseller oluşturulduktan sonraki davranışları, geçici çözümün uygulandığı örneğe benzer olacaktır. Geçici çözümde ayrı *State* verilerini gösteren tablo görünür durumda getirilmemişti. Örneğin önceki bölümde anlatıldığı şekilde *State*, *Population* ve *Sales* verilerini içeren bir görsel şu şekilde görüntülenecektir:

![Tablo görseli](media/desktop-many-to-many-relationships/many-to-many-relationships_12.png)

*Çoka çok kardinalite ilişkileri* ile daha tipik olan *Çoka bir* ilişkileri arasındaki en Önemli farklar şunlardır:

* Gösterilen değerlerde diğer tablodaki eşleşmeyen satırları gösteren boş satır bulunmaz. Değerler, ilişkideki diğer tabloda kullanılan sütunlarda null değerler bulunan satırları dikkate almaz.
* Birden fazla satır arasında ilişki bulunabileceğinden `RELATED()` işlevi kullanılamaz.
* Tabloda `ALL()` işlevinin kullanılması çok-çok ilişkisiyle ilgili diğer tablolara uygulanan filtreleri kaldırmaz. Önceki örnekte aşağıdaki betikte gösterildiği gibi tanımlanmış bir ölçü, ilişkili *CityData* tablosundaki sütunlarda bulunan filtreleri kaldırmaz:

    ![Betik örneği](media/desktop-many-to-many-relationships/many-to-many-relationships_13.png)

    *State*, *Sales* ve *Sales total* değerlerini gösteren bir görsel aşağıdaki gibi olacaktır:

    ![Tablo görseli](media/desktop-many-to-many-relationships/many-to-many-relationships_14.png)

Yukarıda anlatılan farklılıkları göz önünde bulundurarak *genel toplamın %* gibi `ALL(\<Table>)` kullanan hesaplamaların istenen sonuçları döndürdüğünden emin olun. 


## <a name="limitations-and-considerations"></a>Sınırlamalar ve önemli noktalar

*Çoka çok kardinaliteye sahip ilişkiler* ile bileşik modellerin bu sürümünde birkaç sınırlama vardır.

Aşağıdaki Live Connect (çok boyutlu) kaynaklar bileşik modellerle kullanılamaz:

* SAP HANA
* SAP Business Warehouse
* SQL Server Analysis Services
* Power BI veri kümeleri
* Azure Analysis Services

Söz konusu çok boyutlu kaynaklara DirectQuery kullanarak bağlandığınızda, başka bir DirectQuery kaynağına bağlanamaz veya içeri aktarılan verilerle birleştiremezsiniz.

*Çoka çok kardinalitesine sahip ilişkileri* kullanırken DirectQuery’yi kullanmakla ilgili mevcut sınırlamalar yine geçerlidir. Bu sınırlamaların birçoğu şimdi tablonun depolama moduna bağlı olarak tablo başına uygulanır. Örneğin, içeri aktarılan tablodaki hesaplanan sütun başka tablolara başvurabilir ama DirectQuery tablosundaki hesaplanan sütun yine aynı tablodaki sütunlara başvurabilir. Model içindeki tablolardan herhangi biri DirectQuery ise, diğer sınırlamalar modelin tamamına uygulanır. Örneğin, modelin içindeki tablolardan herhangi birinin depolama modu DirectQuery olduğunda, modelde QuickInsights ve Soru ve Yanıt özellikleri kullanılamaz. 

## <a name="next-steps"></a>Sonraki adımlar

Bileşik modeller ve DirectQuery hakkında daha fazla bilgi için aşağıdaki makalelere bakın:
* [Power BI Desktop’taki bileşik modeller](desktop-composite-models.md)
* [Power BI Desktop’ta depolama modu (önizleme)](desktop-storage-mode.md)
* [Power BI Desktop'ta DirectQuery'yi kullanma](desktop-directquery-about.md)
* [Power BI Desktop'ta da DirectQuery tarafından desteklenen veri kaynakları](desktop-directquery-data-sources.md)
