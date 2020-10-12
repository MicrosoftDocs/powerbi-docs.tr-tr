---
title: Çoka çok ilişkiler kılavuzu
description: Çoka çok modelinde ilişkiler geliştirmeye yönelik kılavuz.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 03/02/2020
ms.author: v-pemyer
ms.openlocfilehash: 3c94c25f5f1ba717f68a0c2a5ec661be10f70135
ms.sourcegitcommit: 7e99e8af9caf9340958c4607a94728d43e8c3811
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2020
ms.locfileid: "91668540"
---
# <a name="many-to-many-relationship-guidance"></a>Çoka çok ilişkiler kılavuzu

Bu makale, Power BI Desktop'la çalışan veri modelleyicilerine yöneliktir. Üç farklı çoka çok modelleme senaryosu açıklanır. Ayrıca modellerinizde bunların tasarımının nasıl yapılacağına ilişkin yönergeler sağlanır.

[!INCLUDE [relationships-prerequisite-reading](includes/relationships-prerequisite-reading.md)]

Aslında üç çoka çok senaryosu vardır. Şunlara ihtiyacınız olduğunda bu senaryolar gerçekleşir:

- [Boyut türünde iki tabloyu ilişkilendirme](#relate-many-to-many-dimensions)
- [Olgu türünde iki tabloyu ilişkilendirme](#relate-many-to-many-facts)
- [Daha yüksek dilimli olgu türünde tabloları ilişkilendirme](#relate-higher-grain-facts); olgu türündeki tablo boyut türündeki tablodan daha yüksek dilimli satırlar depoladığında

## <a name="relate-many-to-many-dimensions"></a>Çoka çok boyutları ilişkilendirme

Şimdi ilk çoka çok senaryo türünü bir örnekle gözden geçirelim. Klasik senaryo iki varlıkla ilişkilidir: banka müşterileri ve banka hesapları. Müşterilerin birden çok hesabı olabildiğini ve hesapların birden çok müşterisi olabildiğini düşünün. Hesabın birden çok müşterisi olduğunda bunlar yaygın olarak _ortak hesap sahipleri_ olarak adlandırılır.

Bu varlıkların modellenmesi basit bir işlemdir. Boyut türündeki bir tabloda hesaplar, boyut türündeki diğer bir tabloda da müşteriler depolanır. Boyut türündeki tabloların bir özelliği olarak, her tabloda bir Kimlik sütunu bulunur. İki tablo arasındaki ilişkiyi modellemek için üçüncü bir tablo gereklidir. Bu tablo yaygın olarak _köprü oluşturma tablosu_ olarak adlandırılır. Bu örnekte söz konusu tablonun amacı her müşteri-hesap ilişkisi için bir satır depolamasıdır. İlginç olan bu tablonun yalnızca Kimlik sütunları içerdiğinde [_olgusuz olgu tablosu_](star-schema.md#factless-fact-tables) olarak adlandırılmasıdır.

Burada üç tablonun basitleştirilmiş bir model diyagramı verilmiştir.

![Üç tablo içeren bir modeli gösteren diyagram. Tasarım aşağıdaki paragrafta açıklanmıştır.](media/relationships-many-to-many/bank-account-customer-model-example.png)

İlk tablo **Account** adlı tablodur ve iki sütun içerir: **AccountID** ve **Account**. İkinci tablo **AccountCustomer** adlı tablodur ve iki sütun içerir: **AccountID** ve **CustomerID**. Üçüncü tablo **Customer** adlı tablodur ve iki sütun içerir: **CustomerID** ve **Customer**. Tablolardan hiçbiri arasında ilişki yoktur.

Tabloları ilişkilendirmek için iki tane bire çok ilişkisi eklenir. Burada ilişkili tabloların güncelleştirilmiş bir model diyagramı bulunur. **Transaction** adlı olgu türündeki tablo eklenmiştir. Hesap işlemlerini kaydeder. Köprü oluşturma tablosu ve tüm kimlik sütunları gizlenmiştir.

![Modelin dört tablo içerdiğini gösteren diyagram. Tüm tabloları ilişkilendirmek için bire çok ilişkileri eklenmiştir.](media/relationships-many-to-many/bank-account-customer-model-related-tables-1.png)

İlişki filtresi yayma işleminin çalışmasını açıklamaya yardımcı olmak için, model diyagramı tablo satırlarını ortaya koymak için değiştirilmiştir.

> [!NOTE]
> Power BI Desktop model diyagramında tablo satırlarını görüntülemek mümkün değildir. Bu makalede açıklamayı net örneklerle desteklemek için yapılmıştır.

![Modelin tablo satırlarını ortaya çıkardığını gösteren diyagram. Dört tablonun satır ayrıntıları aşağıdaki paragrafta açıklanmıştır.](media/relationships-many-to-many/bank-account-customer-model-related-tables-2.png)

Dört tablonun satır ayrıntıları aşağıdaki madde işaretli listede açıklanır:

- **Account** tablosunun iki satırı vardır:
  - **AccountID** 1, Account-01 içindir
  - **AccountID** 2, Account-02 içindir
- **Customer** tablosunun iki satırı vardır:
  - **CustomerID** 91, Customer-91 içindir
  - **CustomerID** 92, Customer-92 içindir
- **AccountCustomer** tablosunun üç satırı vardır:
  - **AccountID** 1, **CustomerID** 91 ile ilişkilendirilmiştir
  - **AccountID** 1, **CustomerID** 92 ile ilişkilendirilmiştir
  - **AccountID** 2, **CustomerID** 92 ile ilişkilidir
- **Transaction** tablosunun üç satırı vardır:
  - **Date** 1 Ocak 2019, **AccountID** 1, **Amount** 100
  - **Date** 2 Şubat 2019, **AccountID** 2, **Amount** 200
  - **Date** 3 Mart 2019, **AccountID** 1, **Amount** -25

Model sorgulandığında neler olduğuna bakalım.

Aşağıda **Transaction** tablosundaki **Amount** sütununu özetleyen iki görsel vardır. İlk görsel hesaba göre gruplandırır ve **Amount** sütunlarının toplamı _hesap bakiyesini_ temsil eder. İkinci görsel müşteriye göre gruplandırır ve **Amount** sütunlarının toplamı _müşteri bakiyesini_ temsil eder.

![Yan yana duran iki rapor görselini gösteren diyagram. Görseller aşağıdaki paragrafta açıklanmıştır.](media/relationships-many-to-many/bank-account-customer-model-queried-1.png)

İlk görsel **Account Balance** başlığına sahiptir ve iki sütunu vardır: **Account** ve **Amount**. Aşağıdaki sonucu görüntüler:

- Account-01 bakiye tutarı 75'tir
- Account-02 bakiye tutarı 200'dür
- Toplam 275'tir

İkinci görsel **Customer Balance** başlığına sahiptir ve iki sütunu vardır: **Customer** ve **Amount**. Aşağıdaki sonucu görüntüler:

- Customer-91 bakiye tutarı 275'tir
- Customer-92 bakiye tutarı 275'tir
- Toplam 275'tir

Tablo satırlarına **Account Balance** görseline hızlı bir bakış her hesap ve toplam tutar için sonucun doğru olduğunu ortaya koyar. Bunun nedeni her hesap gruplandırmasının, bu hesap için **Transaction** tablosuna filtre yayılması sonucu vermesidir.

Öte yandan **Customer Balance** görselinde doğru görünmeyen bir şey vardır. **Customer Balance** görselindeki her müşterinin bakiyesi toplam bakiyeyle aynıdır. Bu sonuç ancak her müşteri her hesabın ortak hesap sahibi olması durumunda doğru olabilir. Bu örnekte durum böyle değildir. Sorun filtre yayılmasıyla ilgilidir. Filtre **Transaction** tablosuna kadar akıtılmaz.

İlişki filtresi yönlerini **Customer** tablosundan **Transaction** tablosuna kadar izleyin. **Account** ile **AccountCustomer** tablosu arasındaki ilişkinin yanlış yönde yayıldığı açıkça anlaşılabilir. Bu ilişkinin filtre yönü **Her İkisi** olarak ayarlanmalıdır.

![Modelin güncelleştirildiğini gösteren diyagram. Artık her iki yönde de filtre uygular.](media/relationships-many-to-many/bank-account-customer-model-related-tables-3.png)

![Aynı iki rapor görselini yan yana gösteren diyagram. İlk görsel değişmemiş, ancak ikincisi değişmiştir.](media/relationships-many-to-many/bank-account-customer-model-queried-2.png)

Beklendiği gibi **Account Balance** görselinde hiçbir değişiklik yoktur.

Öte yandan **Customer Balance** görselinde artık aşağıdaki sonuç görüntülenir:

- Customer-91 bakiye tutarı 75'tir
- Customer-92 bakiye tutarı 275'tir
- Toplam 275'tir

**Customer Balance** görseli artık doğru sonucu görüntüler. Filtre yönlerini kendiniz izleyin ve müşteri bakiyelerinin nasıl hesaplandığına bakın. Ayrıca görsel toplamının _tüm müşteriler_ anlamına geldiğini de anlamalısınız.

Model ilişkilerini tanımayan biri sonucun yanlış olduğunu düşünebilir. Şu soruyu sorabilir: _**Customer-91** ve **Customer-92** için toplam bakiye neden 350'ye (75 + 275) eşit değil?_

Bu sorunun yanıtı çoka çok ilişkisini anlamayı gerektirir. Her müşteri bakiyesi birden çok hesap bakiyesinin toplamını temsil ettiğinden, müşteri bakiyeleri _toplanabilir değildir_.

### <a name="relate-many-to-many-dimensions-guidance"></a>Çoka çok boyutları ilişkilendirme yönergeleri

Boyut türündeki tablolarınız arasında çoka çok ilişkisi varsa aşağıdaki yönergeleri sağlarız:

- Çoka çok ilişkili her varlığı bir model tablosu olarak ekleyin ve benzersiz tanımlayıcı sütunu içerdiğinden emin olun
- İlişkili varlıkları depolamak üzere bir köprü oluşturma tablosu ekleyin
- Üç tablo arasında bire çok ilişkileri oluşturun
- Filtre yayılmasının olgu türündeki tablolara doğru devam etmesini sağlamak için **tek bir** çift yönlü ilişki yapılandırın
- Eksik kimlik değerleri olmasının uygun olmadığı durumlarda kimlik sütunlarının **Null atanabilir** özelliğini FALSE olarak ayarlayın; kaynakta eksik değerler olduğunda veri yenileme başarısız olacaktır
- Köprü oluşturma tablosunu gizleyin (raporlama için gereken ek sütunlar veya ölçümler içermiyorsa)
- Raporlamaya uygun olmayan tüm kimlik sütunlarını gizleyin (örneğin, kimlikler vekil anahtarlar olduğunda)
- Kimlik sütununu görünür durumda bırakmak anlamlıysa, bunun ilişkinin "bir" tarafında olmasına dikkat edin; "çok" tarafı sütunu her zaman gizleyin. Bu yöntem en iyi filtre performansını sağlar.
- Karışıklıktan veya yanlış yorumlamaktan kaçınmak için, rapor kullanıcılarınıza açıklamaları iletin; açıklamaları metin kutularıyla veya [görsel üst bilgisi araç ipuçlarıyla](report-page-tooltips.md) ekleyebilirsiniz

Çoka çok boyut türündeki tabloları doğrudan ilişkilendirmenizi önermiyoruz. Bu tasarım yaklaşımı ilişkiyi çoka çok kardinalitesiyle yapılandırmayı gerektirir. Kavramsal olarak bu mümkündür ama ilişkili sütunların yinelenen değerler içereceğine işaret eder. Öte yandan boyut türündeki tabloların bir kimlik sütunu olması yaygın olarak kabul edilen bir tasarım uygulamasıdır. Boyut türündeki tablolar kimlik sütununu her zaman ilişkinin "bir" tarafı olarak kullanmalıdır.

## <a name="relate-many-to-many-facts"></a>Çoka çok olguları ilişkilendirme

İkinci çoka çok senaryo türü iki olgu türünde tablo içerir. İki olgu türünde tablo doğrudan ilişkilendirilebilir. Bu tasarım tekniği hızlı ve basit veri araştırmalarında kullanışlı olabilir. Öte yandan, açıkça belirtmek gerekirse bu tasarım yaklaşımını önermiyoruz. Nedenini bu bölümün devamında açıklayacağız.

Şimdi iki olgu türünde tablo içeren bir örneği gözden geçirelim: **Order** ve **Fulfillment**. **Order** tablosu sipariş satırı başına bir satır içerir ve **Fulfillment** tablosu da sipariş satırı başına sıfır veya daha fazla satır içerebilir. **Order** tablosundaki satırlar satış siparişlerini temsil eder. **Fulfillment** tablosundaki satırlar gönderilen sipariş öğelerini temsil eder. Çoka çok ilişki iki **OrderID** sütununu ilişkilendirir; filtre yayılması yalnızca **Order** tablosundan gerçekleşir (**Order** tablosu **Fulfillment** tablosunu filtreler).

![İki tablo içeren bir modeli gösteren diyagram: Order ve Fulfillment.](media/relationships-many-to-many/order-fulfillment-model-example.png)

Her iki tabloda da yinelenen **OrderID** değerlerinin depolanmasını desteklemek için ilişki kardinalitesi çoka çok olarak ayarlanır. **Order** tablosunda yinelenen **OrderID** değerleri bulunabilir çünkü bir siparişin birden çok satırı olabilir. **Fulfillment** tablosunda yinelenen **OrderID** değerleri bulunabilir çünkü siparişlerin birden çok satırı olabilir ve sipariş satırları birçok gönderimle karşılanabilir.

Şimdi tablo satırlarını gözden geçirelim. **Fulfillment** tablosunda sipariş satırlarının birden çok gönderimle karşılanabileceğine dikkat edin. (Bir sipariş satırının eksik olması, siparişin henüz karşılanmadığını gösterir.)

![Modelin tablo satırlarını ortaya çıkardığını gösteren diyagram. İki tablonun satır ayrıntıları aşağıdaki paragrafta açıklanmıştır.](media/relationships-many-to-many/order-fulfillment-model-related-tables.png)

İki tablonun satır ayrıntıları aşağıdaki madde işaretli listede açıklanır:

- **Order** tablosunun beş satırı vardır:
  - **OrderDate** 1 Ocak 2019, **OrderID** 1, **OrderLine** 1, **ProductID** Prod-A, **OrderQuantity** 5, **Sales** 50
  - **OrderDate** 1 Ocak 2019, **OrderID** 1, **OrderLine** 2, **ProductID** Prod-B, **OrderQuantity** 10, **Sales** 80
  - **OrderDate** 2 Şubat 2019, **OrderID** 2, **OrderLine** 1, **ProductID** Prod-B, **OrderQuantity** 5, **Sales** 40
  - **OrderDate** 2 Şubat 2019, **OrderID** 2, **OrderLine** 2, **ProductID** Prod-C, **OrderQuantity** 1, **Sales** 20
  - **OrderDate** 3 Mart 2019, **OrderID** 3, **OrderLine** 1, **ProductID** Prod-C, **OrderQuantity** 5, **Sales** 100
- **Fulfillment** tablosunun dört satırı vardır:
  - **FulfillmentDate** 1 Ocak 2019, **FulfillmentID** 50, **OrderID** 1, **OrderLine** 1, **FulfillmentQuantity** 2
  - **FulfillmentDate** 2 Şubat 2019, **FulfillmentID** 51, **OrderID** 2, **OrderLine** 1, **FulfillmentQuantity** 5
  - **FulfillmentDate** 2 Şubat 2019, **FulfillmentID** 52, **OrderID** 1, **OrderLine** 1, **FulfillmentQuantity** 3
  - **FulfillmentDate** 1 Ocak 2019, **FulfillmentID** 53, **OrderID** 1, **OrderLine** 2, **FulfillmentQuantity** 10

Model sorgulandığında neler olduğuna bakalım. Burada **Order** tablosunun **OrderID** sütununa göre sipariş ve karşılama miktarlarının karşılaştırıldığı bir tablo görseli verilmiştir.

![Üç sütunlu bir tablo görselini gösteren diyagram: OrderID, OrderQuantity ve FulfillmentQuantity.](media/relationships-many-to-many/order-fulfillment-model-queried.png)

Görsel doğru bir sonuç göstermektedir. Öte yandan modelin kullanışlılığı sınırlıdır çünkü yalnızca **Order** tablosunun **OrderID** sütununa göre filtreleyebilir veya gruplandırabilirsiniz.

### <a name="relate-many-to-many-facts-guidance"></a>Çoka çok olguları ilişkilendirme yönergeleri

Genel olarak çoka çok kardinalitesi kullanılarak iki olgu türünde tablonun doğrudan ilişkilendirilmesi önerilmez. Bunun ana nedeni modelin rapor görsellerini filtreleme veya gruplandırma yolları konusunda esneklik sağlamamasıdır. Örnekte görselleri yalnızca **Order** tablosunun **OrderID** sütununa göre filtrelemek veya gruplandırmak mümkündür. Bir diğer nedeni de verilerinizin kalitesiyle ilgilidir. Verilerinizde bütünlük sorunları varsa, _sınırlı ilişkinin_  doğasına bağlı olarak sorgulama sırasında bazı satırlar atlanabilir. Daha fazla bilgi için bkz. [Power BI Desktop’ta model ilişkileri (İlişki değerlendirmesi)](../transform-model/desktop-relationships-understand.md#relationship-evaluation).

Olgu türündeki tabloları doğrudan ilişkilendirmek yerine [Yıldız Şeması](star-schema.md) tasarım ilkelerini benimsemenizi öneririz. Bunu, boyut türünde tablolar ekleyerek yaparsınız. Sonra boyut türündeki tablolar bire çok ilişkileri kullanılarak olgu türündeki tablolarla ilişkilendirilir. Bu tasarım yaklaşımı esnek raporlama seçenekleri getirdiğinden güçlü bir yaklaşımdır. Boyut türündeki sütunlardan herhangi birini kullanarak filtrelemenize veya gruplandırmanıza ve ilişkili olgu türündeki tabloları özetlemenize olanak tanır.

Şimdi daha iyi bir çözüm düşünelim.

![Bir modelin altı tablo içerdiğini gösteren diyagram: OrderLine, OrderDate, Order, Fulfillment, Product ve FulfillmentDate.](media/relationships-many-to-many/order-fulfillment-model-improved.png)

Aşağıdaki tasarım değişikliklerine dikkat edin:

- Modelin şimdi dört tablosu daha vardır: **OrderLine**, **OrderDate**, **Product** ve **FulfillmentDate**
- Dört ek tablonun hepsi boyut türündeki tablolardır ve bu tablolarla olgu türündeki tablolar arasında bire çok ilişkileri vardır
- **OrderLine** tablosunda, 100 ile çarpılan **OrderID** değerini, artı **OrderLine** değerini (her sipariş satırı için benzersiz tanımlayıcı) temsil eden bir **OrderLineID** sütunu bulunur
- **Order** ve **Fulfillment** tabloları şimdi bir **OrderLineID** sütunu içerir ve bu tablolar artık **OrderID** ve **OrderLine** sütunlarını içermez
- **Fulfillment** tablosu şimdi **OrderDate** ve **ProductID** sütunlarını içerir
- **FulfillmentDate** tablosu yalnızca **Fulfillment** tablosuyla ilişkilidir
- Tüm benzersiz tanımlayıcı sütunları gizlenir

Zaman ayırıp yıldız şeması tasarım ilkelerinin uygulanması aşağıdaki avantajları sağlar:

- Rapor görselleriniz boyut türündeki tabloların tüm görünür sütunlarına göre _filtrelenebilir veya gruplandırılabilir_
- Rapor görselleriniz olgu türündeki tabloların tüm görünür sütunlarına göre _özetlenebilir_
- **OrderLine**, **OrderDate** veya **Product** tablolarına uygulanan filtreler olgu türündeki her iki tabloya da yayılır
- İlişkilerin tümü bire çok ilişkisidir ve her ilişki _normal ilişkidir_. Veri bütünlüğü sorunları maskelenmez. Daha fazla bilgi için bkz. [Power BI Desktop’ta model ilişkileri (İlişki değerlendirmesi)](../transform-model/desktop-relationships-understand.md#relationship-evaluation).

## <a name="relate-higher-grain-facts"></a>Daha yüksek dilimli olguları ilişkilendirme

Bu çoka çok senaryosu, bu makalede daha önce açıklanan diğer iki senaryodan çok farklıdır.

Şimdi dört tablo içeren bir örneği gözden geçirelim: **Date**, **Sales**, **Product** ve **Target**. **Date** ve **Product** boyut türünde tablolardır; bunlardan her biri bire çok ilişkisi kullanılarak olgu türündeki **Sales** tablosuyla ilişkilendirilir. Şimdi kadar iyi bir yıldız şeması tasarımını temsil eder. Öte yandan **Target** tablosu henüz diğer tablolarla ilişkilendirilmemiştir.

![Bir modelin dört tablo içerdiğini gösteren diyagram: Date, Sales, Product ve Target.](media/relationships-many-to-many/sales-targets-model-example.png)

**Target** tablosu üç sütun içerir: **Category**, **TargetQuantity** ve **TargetYear**. Tablo satırları yıl ve ürün kategorisinin ayrıntılarını ortaya koyar. Diğer bir deyişle hedefler (satış performansını ölçmek için kullanılır) her yıl her ürün kategorisi için ayarlanır.

![Target tablosunun üç sütunu olduğunu gösteren diyagram: TargetYear, Category ve TargetQuantity.](media/relationships-many-to-many/sales-targets-model-target-rows.png)

**Target** tablosunda veriler, boyut türündeki tablolardan daha üst düzeyde depolandığından, bire çok ilişkisi oluşturulamaz. Bu, ilişkilerden yalnızca biri için geçerlidir. Şimdi **Target** tablosunun boyut türündeki tablolarla nasıl ilişkilendirilebileceğini gözden geçirelim.

### <a name="relate-higher-grain-time-periods"></a>Daha yüksek dilimli dönemleri ilişkilendirme

**Date** ile **Target** tabloları arasındaki ilişki bire çok ilişkisi olmalıdır. Bunun nedeni **TargetYear** sütunundaki değerlerin tarih değerleri olmasıdır. Bu örnekte her **TargetYear** sütunu değeri, hedef yılın ilk tarihidir.

> [!TIP]
> Olguları bir günden daha yüksek bir zaman aralığı diliminde depolarken sütun veri türünü **Tarih** (veya tarih anahtarları kullanıyorsanız **Tamsayı**) olarak ayarlayın. Sütunda zaman aralığının ilk gününü temsil eden değeri depolayın. Örneğin yıl zaman aralığı yılın 1 Ocak günü olarak ve ay zaman aralığı da söz konusu ayın ilk günü olarak kaydedilir.

Öte yandan ay veya tarih düzeyi filtrelerinin anlamlı bir sonuç verdiğinden emin olmak için özen gösterilmelidir. Özel bir hesaplama mantığı olmadan, rapor görselleri hedef tarihleri her yılın ilk günü olarak raporlayabilir. Diğer tüm günler (ve Ocak dışındaki tüm aylar) hedef miktarı BOŞLUK olarak özetler.

Aşağıdaki matris görselinde, rapor kullanıcısı yıldan o yılın aylarına detaya gittiğinde neler olduğu gösterilir. Görsel **TargetQuantity** sütunu özetlemektedir. (Matris satırları için [Veri içermeyen öğeleri göster](../create-reports/desktop-show-items-no-data.md) seçeneği etkinleştirilmiştir.)

![2020 yılının hedef miktarının 270 olduğunu ortaya çıkaran matris görselini gösteren diyagram.](media/relationships-many-to-many/sales-targets-model-matrix-blank-months-bad.png)

Bu davranışı önlemek için ölçüleri kullanarak olgu verilerinizin özetlemesini denetlemenizi öneririz. Özetlemeyi denetlemenin yollarından biri düşük düzeyli zaman aralıkları sorgulandığında BOŞLUK döndürmektir. Gelişmiş DAX ile tanımlanan bir diğer yol da düşük düzeyli zaman aralıkları arasında değerleri paylaştırmaktır.

[ISFILTERED](/dax/isfiltered-function-dax) DAX işlevinin kullanıldığı aşağıdaki ölçü tanımını düşünün. Yalnızca **Date** veya **Month** sütunları filtrelenmediğinde değer döndürür.

```dax
Target Quantity =
IF(
    NOT ISFILTERED('Date'[Date])
        && NOT ISFILTERED('Date'[Month]),
    SUM(Target[TargetQuantity])
)
```

Aşağıdaki matris görseli şimdi **Target Quantity** ölçüsünü kullanır. Tüm aylık hedef miktarlarının BOŞ olduğunu gösterir.

![2020 yılının hedef miktarının 270 olduğunu boş aylık değerlerle birlikte ortaya çıkaran matris görselini gösteren diyagram.](media/relationships-many-to-many/sales-targets-model-matrix-blank-months-good.png)

### <a name="relate-higher-grain-non-date"></a>Daha yüksek dilimi ilişkilendirme (tarih dışı)

Boyut türündeki tablonun tarih dışı bir sütununu olgu türündeki tabloyla (ayrıca boyut türündeki tablodan daha yüksek dilimde) ilişkilendirirken farklı bir tasarım yaklaşımı gereklidir.

**Category** sütunları (hem **Product** hem de **Target** tablosundan) yinelenen değerler içerir. Dolayısıyla bire çok ilişkisinin "bir" tarafı yoktur. Bu örnekte bir çoka çok ilişkisi oluşturmanız gerekir. İlişki filtreleri tek yönde, boyut türündeki tablodan olgu türündeki tabloya yaymalıdır.

![Target ve Ürün tablolarının modelini gösteren diyagram. Çoka çok ilişkisi iki tabloyu ilişkilendirir.](media/relationships-many-to-many/sales-targets-model-relate-non-date.png)

Şimdi tablo satırlarını gözden geçirelim.

![İki tablo içeren bir modeli gösteren diyagram: Target ve Product. Çoka çok ilişkisi iki Category sütununu ilişkilendirir.](media/relationships-many-to-many/sales-targets-model-relate-non-date-tables.png)

**Target** tablosunda dört satır vardır: her hedef yıl (2019 ve 2020) için iki satır ve iki kategori (Clothing ve Accessories). **Product** tablosunda üç ürün vardır. Ürünlerden ikisi giysi (Clothing) kategorisine ve biri de aksesuar (Accessories) kategorisine aittir. Giysilerden birinin rengi yeşil diğer ikisinin mavidir.

**Product** tablosundaki **Category** sütununa göre yapılan bir tablo görsel gruplandırması aşağıdaki sonucu verir.

![İki sütunlu bir tablo görselini gösteren diyagram: Category ve TargetQuantity. Accessories 60, Clothing 40 ve toplam da 100'dür.](media/relationships-many-to-many/sales-targets-model-visual-category-targets.png)

Bu görsel doğru sonucu üretir. Şimdi hedef miktarı gruplandırmak için **Product** tablosunun **Color** sütunu kullanıldığında ne olduğuna bakalım.

![İki sütunlu bir tablo görselini gösteren diyagram: Color ve TargetQuantity. Blue 100, Green 40 ve toplam da 100'dür.](media/relationships-many-to-many/sales-targets-model-visual-color-targets-bad.png)

Görsel verilerin hatalı bir gösterimini üretir. Orada neler oluyor?

**Product** tablosunun **Color** sütununa uygulanan bir filtrenin sonucunda iki satır elde edilir. Satırlardan biri Clothing kategorisi ve diğeri de Accessories kategorisi içindir. Bu iki kategori değeri filtre olarak **Target** tablosuna yayılır. Diğer bir deyişle iki kategorideki ürünler mavi (Blue) rengi kullandığından, hedefleri filtrelemek için _bu kategoriler_ kullanılır.

Bu davranışı önlemek için, daha önce açıklandığı gibi ölçüleri kullanarak olgu verilerinizin özetlemesini denetlemenizi öneririz.

Aşağıdaki ölçü tanımını göz önünde bulundurun. Kategori düzeyinin altındaki tüm **Product** tablosu sütunlarının filtreler için test edildiğine dikkat edin.

```dax
Target Quantity =
IF(
    NOT ISFILTERED('Product'[ProductID])
        && NOT ISFILTERED('Product'[Product])
        && NOT ISFILTERED('Product'[Color]),
    SUM(Target[TargetQuantity])
)
```

Aşağıdaki tablo görseli şimdi **Target Quantity** ölçüsünü kullanır. Tüm renk hedefi miktarlarının BOŞ olduğunu gösterir.

![İki sütunlu bir tablo görselini gösteren diyagram: Color ve TargetQuantity. Blue BOŞ, Green BOŞ ve toplam da 100'dür.](media/relationships-many-to-many/sales-targets-model-visual-color-targets-good.png)

Son model tasarımı aşağıdakine benzer.

![Aralarında bire çok ilişkisi bulunan Date ve Target tablolarına sahip bir modeli gösteren diyagram.](media/relationships-many-to-many/sales-targets-model-example-final.png)

### <a name="relate-higher-grain-facts-guidance"></a>Daha yüksek dilimli olgular kılavuzu

Boyut türünde bir tabloyu olgu türünde bir tabloyla ilişkilendirmeniz gerektiğinde ve olgu türündeki tablo boyut türündeki tablonun satırlarından daha yüksek dilimde satırlar depoladığında, aşağıdaki yönergeleri sağlarız:

- Daha yüksek dilimli olgu tarihleri için:
  - Olgu türündeki tabloda zaman aralığının ilk tarihini depolayın
  - Tarih tablosuyla olgu türündeki tablo arasında bire çok ilişkisi oluşturun
- Diğer daha yüksek dilimli olgular için:
  - Boyut türündeki tabloyla olgu türündeki tablo arasında çoka çok ilişkisi oluşturun
- Her iki tür için de:
  - Ölçü mantığıyla özetlemeyi denetleyin; filtrelemek veya gruplandırmak için düşük düzeyli boyut türündeki sütunlar kullanıldığında BOŞLUK döndürün
  - Özetlenebilir olgu türündeki tablo sütunlarını gizleyin; bu şekilde olgu türündeki tabloyu özetlemek için yalnızca ölçüler kullanılabilir

## <a name="next-steps"></a>Sonraki adımlar

Bu makaleyle ilgili daha fazla bilgi için aşağıdaki kaynaklara bakın:

- [Power BI Desktop’ta model ilişkileri](../transform-model/desktop-relationships-understand.md)
- [Yıldız şemasını ve Power BI açısından önemini anlama](star-schema.md)
- [İlişki sorunlarını giderme kılavuzu](relationships-troubleshoot.md)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
- Önerileriniz mi var? [Power BI'ı geliştirmek için fikirlerinizi paylaşın](https://ideas.powerbi.com/)
