---
title: "Öğretici: Power BI Desktop'ta boyutsal modelden muhteşem raporlar elde etme"
description: Bu öğreticide boyutsal bir modelle başlayacak ve 20 dakikada başından sonuna kadar güzel bir rapor oluşturacaksınız.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: pbi-reports-dashboards
ms.topic: tutorial
ms.date: 01/19/2021
LocalizationGroup: Reports
ms.openlocfilehash: 03eac7aefdebb31eac353c969db2bf8810173395
ms.sourcegitcommit: 77912d4f6ef2a2b1ef8ffccc50691fe5b38ee97a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98687377"
---
# <a name="tutorial-from-dimensional-model-to-stunning-report-in-power-bi-desktop"></a>Öğretici: Power BI Desktop'ta boyutsal modelden muhteşem raporlar elde etme 

Bu öğreticide boyutsal bir modelle başlayacak ve 45 dakikada başından sonuna kadar güzel bir rapor oluşturacaksınız.

AdventureWorks adlı şirkette çalışıyorsunuz ve yöneticiniz en son satış rakamlarınızı içeren bir rapor görmek istiyor. Şu konuları içeren bir yönetici özeti istendi: 

- Şubat 2019'da en çok satış yapılan gün hangisiydi? 
- Şirketin en başarılı olduğu ülke neresi? 
- Şirket hangi ürün kategorisine ve kurumsal bayi işletme türlerine yatırım yapmaya devam etmeli? 

[AdventureWorks Satışları adlı örnek Excel çalışma kitabını](https://github.com/microsoft/powerbi-desktop-samples/blob/main/AdventureWorks%20Sales%20Sample/AdventureWorks%20Sales.xlsx) kullanarak bu raporu kısa süre içinde oluşturabilirsiniz. Raporun son hali aşağıdaki gibi görünecek. 

:::image type="content" source="media/desktop-dimensional-model-report/adventureworks-finished-report.png" alt-text="Tamamlanmış AdventureWorks raporu.":::

Raporun son halini mi görmek istiyorsunuz? İsterseniz [Tamamlanmış Power BI .pbix dosyasını](https://github.com/microsoft/powerbi-desktop-samples/blob/main/AdventureWorks%20Sales%20Sample/AdventureWorks%20Sales.pbix) indirebilirsiniz.

Başlayalım! 

Bu öğreticide aşağıdakilerin nasıl yapılacağını öğreneceksiniz:

> [!div class="checklist"]
> * Birkaç dönüştürmeyle verilerinizi hazırlama
> * Başlığı, üç görseli ve dilimleyicisi olan bir rapor oluşturma
> * Raporunuzu iş arkadaşlarınızla paylaşabilmek için Power BI hizmetinde yayımlama

## <a name="prerequisites"></a>Önkoşullar

- Başlamadan önce [Power BI Desktop'ı indirmelisiniz](../fundamentals/desktop-get-the-desktop.md). 
- Raporunuzu Power BI hizmetinde yayımlamayı planlıyorsanız ve henüz kaydolmadıysanız, [ücretsiz denemeye kaydolun](../fundamentals/service-self-service-signup-for-power-bi.md). 

## <a name="get-data-download-the-sample"></a>Veri al: Örneği indirme 

1. [AdventureWorks Satışları adlı örnek Excel çalışma kitabını indirin](https://github.com/microsoft/powerbi-desktop-samples/blob/main/AdventureWorks%20Sales%20Sample/AdventureWorks%20Sales.xlsx). 

1. Power BI Desktop'ı açın. 

1. **Giriş** sekmesinin **Veri** bölümünde **Excel**'i seçin. 

1. Örnek çalışma kitabını kaydettiğiniz yere gidin ve **Aç**'ı seçin. 

## <a name="prepare-your-data"></a>Verilerinizi hazırlama 

Gezgin bölmesinde verileri *dönüştürme* veya *yükleme* seçeneği sunulur. Gezgin verilerinizin önizlemesini sağladığından doğru veri aralığını aldığınızı doğrulayabilirsiniz. Sayısal veri türleri italik yazılır. Bu öğreticide verileri yüklemeden önce dönüştüreceğiz.

Tüm tabloları ve ardından **Veri Dönüştürme**'yi seçin. Adının sonunda *_data* ifadesi bulunan sayfaları seçmediğinizden emin olun. 

:::image type="content" source="media/desktop-dimensional-model-report/desktop-load-tables.png" alt-text="Gezgin'de tabloları yükleyin.":::

Veri türlerinin ve sütunların aşağıdaki tabloda belirtilenlerle aynı olduğundan emin olun. Power BI veri türlerini algılamaya izin vermek için bir sorgu seçin ve bir veya daha fazla sütun seçin. **Dönüştür** sekmesinde, **veri türünü Algıla**' yı seçin. Algılanan veri türünde herhangi bir değişiklik yapmak için, **giriş** sekmesinde **veri türü**' nü seçin ve ardından tablodan uygun veri türünü seçin.

:::image type="content" source="media/desktop-dimensional-model-report/power-query-change-data-types.png" alt-text="Sütunların veri türünü denetleyin.":::


|Sorgu  |Sütun  |Veri türü  |
|---------|---------|---------|
|Müşteri  |  CustomerKey | Tam Sayı |
|Tarih | DateKey |    Tam Sayı     |
|     | Tarih | Tarih      |
|     | MonthKey  | Tam Sayı |
|Ürün  | ProductKey | Tam Sayı  | 
|     | Standard Cost | Ondalık Sayı  | 
|     | Liste Fiyatı | Ondalık Sayı  | 
|Reseller  | ResellerKey | Tam Sayı  | 
|Sales   | SalesOrderLineKey | Tam Sayı  | 
|     | ResellerKey  | Tam Sayı  | 
|     | CustomerKey | Tam Sayı  | 
|     | ProductKey  | Tam Sayı  | 
|     | OrderDateKey | Tam Sayı  | 
|     | DueDateKey  | Tam Sayı  | 
|     | ShipDateKey | Tam Sayı  | 
|     | SalesTerritoryKey | Tam Sayı  | 
|     | Sipariş Miktarı   | Tam Sayı  | 
|     | Birim Fiyatı  | Ondalık Sayı  | 
|     | Extended Amount  | Ondalık Sayı  | 
|     | Unit Price Discount Pct | Yüzde  | 
|     | Product Standard Cost | Ondalık Sayı  | 
|     | Toplam Ürün Maliyeti | Ondalık Sayı  | 
|     | Satış Tutarı | Ondalık Sayı  | 
| SalesTerritory  | SalesTerritoryKey | Tam Sayı  | 
|  SalesOrder   |  SalesOrderLineKey | Tam Sayı  | 

 **Giriş** sekmesine dönüp **Kapat ve Uygula**'yı seçin. 

:::image type="content" source="media/desktop-dimensional-model-report/power-query-close-and-apply.png" alt-text="Power Query'deki Kapat ve Uygula düğmesi.":::

## <a name="model-your-data"></a>Verilerinizi modelleme 

Yüklediğiniz veriler raporlama için neredeyse hazır. Şimdi veri modelini inceleyip bazı değişiklikler yapalım. 

Sol tarafta **Model Görünümü**'nü seçin. 

:::image type="content" source="media/desktop-dimensional-model-report/desktop-select-model-view.png" alt-text="Power BI Desktop'ta Model görünümünü seçin.":::

Veri modeliniz aşağıdaki görüntüye benzer olmalı ve her tablo bir kutu içinde görünmelidir. 

:::image type="content" source="media/desktop-dimensional-model-report/desktop-data-model-1.png" alt-text="Başlangıçta kullanılacak veri modeli.":::

### <a name="create-relationships"></a>İlişki oluşturma

Bu modeli daha önce veri ambarlarında da görmüş olabileceğiniz klasik *yıldız şemasına* sahiptir: Bir yıldıza benzer. Yıldızın ortasında bir Olgu tablosu bulunur. Onu çevreleyen ve Boyut tablosu adı verilen tablolar, Olgu tablosuna ilişkilerle bağlanmıştır. Olgu tablosunda Sales Amount ve Product Standard Cost gibi satış işlemleriyle ilgili sayısal bilgiler yer alır. Boyutlar bağlam bilgisi sunduğundan şu tür analizler yapabilirsiniz: 

- Satılan ürün... 
- Satın alan Müşteri... 
- Satışı yapan Kurumsal Bayi... 
- Satışın yapıldığı Satış Bölgesi.  

Dikkatli bakacak olursanız Date tablosu dışındaki tüm Boyut tablolarının Olgu tablosuna bir İlişki üzerinden bağlı olduğunu görebilirsiniz. Şimdi Date için birkaç ilişki ekleyelim. Tarih tablosundaki DateKey değerini Sales tablosundaki OrderDateKey değerine sürükleyin. Date ve Sales arasında "bire çok" ilişkisi oluşturdunuz ve bunu çizginin iki ucundaki **1** ve yıldız * (çok) işaretleriyle de görebilirsiniz.  

Belirli bir Date girişi için bir veya daha fazla Sales girişi mevcut olduğundan ilişki, "bire çok" şeklindedir. Her tarihte yalnızca bir Sales girişi olsaydı ilişki "bire bir" şeklinde olacaktı. Çizginin ortasındaki küçük ok, "çapraz filtreleme yönünü" belirtir. Bu ok, Date tablosundaki değerleri kullanarak Sales tablosunu filtreleyebileceğinizi gösterir. Dolayısıyla bu ilişki, bir satış siparişinin oluşturulduğu zamanı analiz etmenizi sağlar.  

:::image type="content" source="media/desktop-dimensional-model-report/desktop-date-sales-relationship.png" alt-text="Sales ve Date tabloları arasındaki ilişki.":::

Sales tablosunda Due Date ve Ship Date gibi satışlarla ilgili tarihler hakkında farklı bilgiler mevcuttur. Şimdi sürükleme yöntemiyle Date tablosuna iki tane daha ilişki ekleyelim: 

- DateKey - DueDateKey 
- DateKey - ShipDateKey 
    
:::image type="content" source="media/desktop-dimensional-model-report/desktop-date-sales-relationships-done.png" alt-text="Sales ve Date tabloları arasındaki üç ilişki.":::

Düz çizgiden göreceğiniz üzere ilk ilişki olan OrderDateKey ilişkisi etkindir. Kesik çizgi, diğer iki ilişkinin devre dışı olduğunu gösterir. Power BI, Sales ve Date arasında ilişki kurmak için varsayılan olarak etkin ilişkiyi kullanır. Bu nedenle SalesAmount toplamı Due Date veya Ship Date ölçütüne göre değil Order Date ölçütüne göre hesaplanır. Bu davranışı değiştirebilirsiniz. Bu öğreticinin [Ek çalışma: DAX dilinde ölçü yazma](#extra-credit-write-a-measure-in-dax) bölümüne bakın.

### <a name="hide-key-columns"></a>Anahtar sütunları gizleme

Klasik yıldız şemasında Olgular ile Boyutlar arasındaki ilişkileri koruyan birkaç anahtar vardır. Bu anahtar sütunları raporlarınızda kullanmak istemezsiniz. Şimdi anahtar sütunları görünümden kaldırarak Alanlar Listesi bölümünde daha az alan gösterilmesini ve böylece veri modelinin daha kolay kullanılmasını sağlayacağız. 

Tüm tabloları gözden geçirin ve adı *Key* ile biten sütunları gizleyin: 

Sütunun yanındaki **Göz** simgesini ve ardından **Rapor görünümünde gizle**'yi seçin.

:::image type="content" source="media/desktop-dimensional-model-report/desktop-column-visible.png" alt-text="Görünür durumdaki sütun ve Göz simgesi.":::

Özellikler bölmesinde sütunun yanında bulunan **Göz** simgesini de seçebilirsiniz.

Gizli alanlar, üzeri çizilmiş göz simgesiyle gösterilir. 

:::image type="content" source="media/desktop-dimensional-model-report/desktop-column-hidden.png" alt-text="Gizli Göz simgesinin bulunduğu alan.":::
 
Bu alanları gizleyin.

|Tablo  |Sütun  |
|---------|---------|
|Müşteri  | CustomerKey |
|Tarih     | DateKey |
|     | MonthKey |
|Ürün     | ProductKey  |
|Reseller   | ResellerKey  |
|Sales     | CustomerKey  |
|     | DueDateKey |
|     | OrderDateKey |
|     | ProductKey |
|     | ResellerKey        |
|     | SalesOrderLineKey        |
|     | SalesTerritoryKey        |
|     | ShipDateKey        |
| SalesOrder    | SalesOrderLineKey |
| SalesTerritory  | SalesTerritoryKey |

Veri modeliniz bu adımda aşağıdaki veri modeli gibi görünüyor olmalıdır. Sales ile diğer tüm tablolar arasındaki ilişkiler belirlenmiş, tüm anahtar alanlar gizlenmiş durumdadır: 

:::image type="content" source="media/desktop-dimensional-model-report/desktop-data-model-2-hidden-columns.png" alt-text="Anahtar sütunları gizlenmiş veri modeli.":::

### <a name="create-hierarchies"></a>Hiyerarşiler oluşturma

Sütunları gizleyerek veri modelimizi daha kolay kullanılır hale getirdiğimize göre birkaç *hiyerarşi* ekleyerek daha fazla kullanıcı dostu hale getirebiliriz. Hiyerarşiler, gruplandırmalar arasındaki gezintiyi kolaylaştırır. Örneğin şehirler, bir Country veya Region içinde bulunan bir State veya Province içinde yer alır. 

Aşağıdaki hiyerarşileri oluşturun. 

1. Hiyerarşide en üst düzeyde olan veya en az ayrıntılı olan alana sağ tıklayıp **Hiyerarşi oluştur**'u seçin. 

1. **Özellikler** bölmesinde hiyerarşiye bir **Ad** verip düzeyleri ayarlayın. 

1. Ardından **Düzey Değişikliklerini Uygula**'yı seçin. 

    :::image type="content" source="media/desktop-dimensional-model-report/desktop-hierarchy-properties.png" alt-text="Hiyerarşi Özellikleri bölmesi.":::

İsterseniz Özellikler bölmesinde bir hiyerarşiye eklediğiniz düzeyleri yeniden adlandırabilirsiniz. Date tablosundaki Fiscal hiyerarşisinin Year ve Quarter düzeylerinin adını değiştirmeniz gerekir. 

Oluşturmanız gereken hiyerarşiler aşağıda verilmiştir.

| Tablo |Hiyerarşi adı |Düzeyler  |
|---------|---------|---------|
|Müşteri     | Coğrafya   | Ülke-Bölge  |
|     | | State-Province  |
|     |         | Şehir |
|Row4     |         | Posta Kodu |
|Row5     |         | Müşteri   |
|Tarih     | Fiscal  | Year (Fiscal Year)  |
|     |         | Quarter (Fiscal Quarter) |
|     |         | Ay |
|     |         | Tarih |
| Product  | Ürünler | Kategori |
|     |         | Alt Kategori |
|     |         | Modelleme |
|     |         | Product |
| Reseller   | Coğrafya | Ülke-Bölge |
|     |         | State-Province |
|     |         | Şehir  |
|     |         | Posta Kodu  |
|     |         | Reseller |
| SalesOrder  | Sales Orders | Sales Order |
|     |         | Sales Order Line (Satış Siparişi Satırı) |
| SalesTerritory    | Sales Territories | Grup |
|     |         | Ülke |
|     |         | Bölge |
 
Bu adımda veri modeliniz aşağıdaki gibi görünüyor olmalıdır. Tablolar aynıdır ancak her boyut tablosunda bir hiyerarşi vardır: 

:::image type="content" source="media/desktop-dimensional-model-report/desktop-data-model-3-added-hierarchies.png" alt-text="Hiyerarşiye sahip boyut tablolarının bulunduğu veri modeli.":::

### <a name="rename-tables"></a>Tabloları yeniden adlandırma

Modellemeyi tamamlamak için Özellikler bölmesinde aşağıdaki tabloların adını değiştirin: 

|Tablonun eski adı  |Tablonun yeni adı  |
|---------|---------|
|SalesTerritory    |  Sales Territory   |
|SalesOrder  |  Sales Order   |

Excel'deki tablo adlarında boşluk kabul edilmediğinden bu adımı gerçekleştirmeniz şarttır.

Veri modeliniz son halini aldı.

:::image type="content" source="media/desktop-dimensional-model-report/desktop-data-model-4-renamed-tables.png" alt-text="Tabloların yeniden adlandırıldığı tamamlanmış veri modeli.":::

## <a name="extra-credit-write-a-measure-in-dax"></a>Ek çalışma: DAX dilinde ölçü yazma 

*DAX* formül dilinde ölçüler yazmak, veri modellemesi açısından son derece güçlü bir araçtır. [Power BI belgelerinde DAX hakkında öğrenebileceğiniz](/dax/) çok fazla bilgi sağlanır. Şimdilik toplam satış miktarını varsayılan sipariş tarihi yerine satış siparişi son tarihine göre hesaplayan basit bir ölçü yazacağız. Bu ölçü [USERELATIONSHIP işlevini](/dax/userelationship-function-dax) kullanarak ölçü bağlamı için Sales ile Date arasında DueDate tabanlı ilişkiyi etkinleştirir. Ardından [CALCULATE](/dax/calculate-function-dax) işlevini kullanarak ilgili bağlamda Sales Amount toplamını verir.

1. Sol tarafta Veri Görünümü'nü seçin. 

    :::image type="content" source="media/desktop-dimensional-model-report/desktop-open-data-view.png" alt-text="Sol tarafta Veri Görünümü'nü seçin.":::

1. Alanlar listesinden Sales tablosunu seçin.

    :::image type="content" source="media/desktop-dimensional-model-report/desktop-select-sales-table.png" alt-text="Alanlar listesinden Sales tablosunu seçin.":::

1.  **Giriş** şeridinde **Yeni Ölçü**'yü seçin. 

1. Toplam satış miktarını varsayılan sipariş tarihi yerine satış siparişi son tarihine göre hesaplamak için bu ölçüyü seçin veya yazın:

    ```dax
    Sales Amount by Due Date = CALCULATE(SUM(Sales[Sales Amount]), USERELATIONSHIP(Sales[DueDateKey],'Date'[DateKey]))
    ```

1. İşlemek için onay işaretini seçin. 

    :::image type="content" source="media/desktop-dimensional-model-report/desktop-adding-a-dax-measure.png" alt-text="DAX ölçüsünü işlemek için onay işaretini seçin.":::

## <a name="build-your-report"></a>Raporunuzu oluşturma 

Artık verilerinizi modellediğinize göre raporunuzu oluşturmanın zamanı geldi. Rapor görünümüne gidin. Sağ taraftaki Alanlar bölmesinde, oluşturduğunuz veri modelindeki alanları görürsünüz.

Şimdi bir kerede bir görsel olmak üzere raporun son halini oluşturalım. 

:::image type="content" source="media/desktop-dimensional-model-report/adventureworks-finished-report-with-numbers.png" alt-text="Görsellerin sayıyla işaretlenmiş olduğu tamamlanmış rapor":::

### <a name="visual-1-add-a-title"></a>Görsel 1: Başlık ekleme 

1. **Ekle** şeridinde **Metin Kutusu**'nu seçin. "Yönetici Özeti - Satış Raporu" yazın. 

1. Yazdığınız metni seçin. Yazı tipi boyutunu **20** ve **Kalın** olarak ayarlayın. 

    :::image type="content" source="media/desktop-dimensional-model-report/executive-summary-text-box.png" alt-text="Yönetici Özeti metnini biçimlendirin.":::

1. Görselleştirmeler bölmesinde **Arka Plan**'ı **Kapalı** olarak ayarlayın. 

1. Kutuyu tek satıra sığdırmak için yeniden boyutlandırın. 

### <a name="visual-2-sales-amount-by-date"></a>Görsel 2: Tarihe Göre Satış Tutarı 

Şimdi en yüksek satış miktarının elde edildiği ayı ve yılı görmek için bir çizgi grafik oluşturacaksınız.

1. Alanlar bölmesinde **Sales** tablosunun altında bulunan **Sales Amount** alanını rapor tuvalindeki boş bir alana sürükleyin. Varsayılan olarak Power BI tek sütunu (Sales Amount) olan bir sütun grafiği görüntüler. 

1. **Date** tablosunda **Fiscal** hiyerarşisinde bulunan **Month** alanını sürükleyip sütun grafiğin üzerine bırakın. 

    :::image type="content" source="media/desktop-dimensional-model-report/report-sales-amount-by-year.png" alt-text="Her yıl için bir sütunun yer aldığı bir sütun grafik oluşturma.":::

1. Görselleştirmeler bölmesinin **Alanlar** bölümünde **Year** ve **Quarter** alanlarını kaldırın: 

    :::image type="content" source="media/desktop-dimensional-model-report/report-sales-amount-by-year-remove-year-and-quarter.png" alt-text="Görselleştirmeler bölmesinin Alanlar bölümünde Year ve Quarter alanlarını kaldırın.":::

1. Görselleştirmeler bölmesinde, görselleştirme türünü **Alan Grafiği** olarak değiştirin. 

    :::image type="content" source="media/desktop-dimensional-model-report/report-sales-amount-by-year-change-to-area.png" alt-text="Sütun grafiği, alan grafiği olarak değiştirin.":::

1. Yukarıdaki ek çalışma bölümünde verilen DAX ölçüsünü eklediyseniz **Değerler** alanına da ekleyin. 
1. Biçim bölmesini açın, Veri renkleri'ni seçin ve **Sales Amount by Due Date** rengini kırmızı gibi yüksek karşıtlıklı bir renk olarak değiştirin.

    :::image type="content" source="media/desktop-dimensional-model-report/report-sales-amount-by-year-add-DAX-measure.png" alt-text="Alan grafiği olarak Sales Amount by Due Date.":::

    Görebileceğiniz gibi Sales Amount by Due Date, Sales Amount miktarının biraz gerisindedir. Bu da Sales ile Date tabloları arasında bulunan ve DueDateKey kullanan ilişkiyi kullandığını kanıtlar. 

 

### <a name="visual-3-order-quantity-by-reseller-country"></a>Görsel 3: Kurumsal Bayi Ülkesine Göre Sipariş Miktarı 

Şimdi Order Quantity Amount tutarı en yüksek olan kurumsal bayilerin hangi ülkede olduğunu görmek için bir harita oluşturacağız.

1. Alanlar bölmesinde **Reseller** tablosunda bulunan **Country-Region** alanını rapor tuvalinizin boş bir noktasına sürükleyin. Power BI bir harita oluşturur. 

1. **Sales** tablosundaki **Order Quantity** alanını sürükleyip haritanın üzerine bırakın. **Country-Region** alanının **Konum** kutusunda, **Order Quantity** alanının ise **Size** kutusunda olduğundan emin olun. 

    :::image type="content" source="media/desktop-dimensional-model-report/report-sales-order-quantity-by-reseller-country.png" alt-text="Ülkeye/bölgey göre sipariş miktarı haritası.":::

### <a name="visual-4-sales-amount-by-product-category-and-reseller-business-type"></a>Görsel 4: Ürün Kategorisi ve Kurumsal Bayi İş Türüne Göre Satış Miktarı 

Şimdi kurumsal bayi işletme türüne göre satılan ürünleri araştırmak için bir sütun grafik oluşturacağız.

1. Oluşturduğunuz iki grafiği tuvalin üst yarısında yan yana gelecek şekilde sürükleyin. Tuvalin sol tarafında biraz yer ayırın. 

1. Rapor tuvalinizin alt yarısında boş bir alan seçin. 

1. Alanlar bölmesinde **Sales** altından **Sales Amount**, **Product** altından **Product Category** ve **Reseller** altından **Business Type** verilerini seçin.
    :::image type="content" source="media/desktop-dimensional-model-report/report-sales-amount-by-product-category-field-well.png" alt-text="Kategorinin ve Iş türünün satırlarda ve satış tutarının ise değer olarak seçili olduğunu kontrol edin.":::
    
    Power BI otomatik olarak kümelenmiş bir sütun grafik oluşturur. Görselleştirme türünü **Matris** olarak değiştirin: 

    :::image type="content" source="media/desktop-dimensional-model-report/report-sales-amount-by-product-category-change-to-matrix.png" alt-text="Kümelenmiş sütun grafiği matris olarak değiştirin.":::

1. Matris seçili durumdayken Filtreler bölmesinin **Business Type** bölümünde **Tümünü seç**'i belirleyip **[Uygulanamaz]** kutusunun işaretini kaldırın. 

    :::image type="content" source="media/desktop-dimensional-model-report/report-sales-amount-by-product-category-filter-not-applicable.png" alt-text="Uygulanamaz işletme türünü kaldırın.":::

1. Matrisi sürükleyerek, üstteki iki grafiğin altında kalan alanı kaplayacak kadar genişletin. 

    :::image type="content" source="media/desktop-dimensional-model-report/report-sales-amount-by-product-category-increase-width.png" alt-text="Matrisi, raporu dolduracak şekilde genişletin.":::

1. Matrisin Biçimlendirme bölmesinde **Koşullu biçimlendirme** bölümünü ve ardından **Veri çubukları** özelliğini açın. **Gelişmiş denetimler**'i seçip pozitif çubuğu için daha açık bir renk seçin. **Tamam**’ı seçin. 

1. Matrisi sürükleyerek, satış tutarı sütununun genişliğini artırarak tüm alanı ele alır.

    :::image type="content" source="media/desktop-dimensional-model-report/report-sales-amount-by-product-category-add-databars.png" alt-text="Sales Amount için veri çubuklarının yer aldığı matris.":::

Bikes ürününün Sales Amount değeri ortalamadan daha yüksek görünüyor ve en çok satış Value Added Resellers tarafından yapılmış, Warehouses ise onu takip ediyor. Components için Warehouses, Value Added Resellers bayilerinden daha fazla satış yapıyor. 

 

### <a name="visual-5-fiscal-calendar-slicer"></a>Görsel 5: Mali takvim dilimleyicisi 

Dilimleyiciler, rapor sayfasındaki görselleri belirli bir seçime göre filtrelemeye yönelik değerli bir araçtır. Bu örnekte her ayın, çeyreğin veya yılın performansı gösterilecek şekilde görseli daraltan bir dilimleyici oluşturabilirsiniz. 

1. Alanlar bölmesinde **Date** tablosunda bulunan **Fiscal** hiyerarşisini seçin ve tuvalin sol tarafındaki boş alana sürükleyin. 

1. Görselleştirmeler bölmesinde **Dilimleyici**'yi seçin. 

    :::image type="content" source="media/desktop-dimensional-model-report/report-sales-add-fiscal-calendar-slicer.png" alt-text="Rapor satış takvimi dilimleyicisi ekleyin.":::

1. Görselleştirmeler bölmesinin Alanlar bölümünde **Quarter** ve **Date** girişlerini kaldırarak yalnızca **Year** ve **Month** girişlerinin kalmasını sağlayın. 
 
    :::image type="content" source="media/desktop-dimensional-model-report/report-sales-add-fiscal-calendar-slicer-remove-quarter-and-date.png" alt-text="Quarter ve Date girişlerini Fiscal dilimleyicisinden kaldırın.":::

Artık yöneticiniz yalnızca belirli bir aya ait verileri görmek isterse dilimleyiciyi kullanarak yıllar arasında veya her yılın belirli aylarına geçiş yapabilirsiniz. 

## <a name="extra-credit-format-the-report"></a>Ek çalışma: Raporu biçimlendirme 

Bu raporda görünümünü biraz daha geliştirecek basit biçimlendirmeler yapmak istiyorsanız, işte birkaç kolay adım. 

### <a name="theme"></a>Tema 

-  **Görünüm** şeridinde **Temalar**'ı seçip temayı  **Yönetici** olarak değiştirin. 

    :::image type="content" source="media/desktop-dimensional-model-report/formatting-report-change-theme.png" alt-text="Yönetici temasını seçin.":::

### <a name="spruce-up-the-visuals"></a>Görselleri süsleme 

Görselleştirmeler bölmesinin **Biçim** sekmesinde aşağıdaki değişiklikleri yapın. 

:::image type="content" source="media/desktop-dimensional-model-report/formatting-report-formatting-pane.png" alt-text="Görselleştirmeler bölmesindeki Biçim sekmesinin ekran görüntüsü.":::

**Görsel 2, Tarihe Göre Satış Tutarı**

1. Tarihe Göre Satış Tutarı başlıklı 2. görseli seçin. 
1.  **Başlık** bölümünde DAX ölçüsünü eklemediyseniz  **Başlık** metnini "Tarihe Göre Satış Tutarı" olarak değiştirin. 

    DAX ölçüsünü eklediyseniz **Başlık metni** girişini "Sipariş Tarihine/Son Tarihe Göre Satış Tutarı" olarak değiştirin. 

1. **Metin** boyutunu  **16 pt** olarak değiştirin. 
1.  **Gölge** ayarını **Açık** olarak değiştirin. 

**Görsel 3, Kurumsal Bayi Ülkesine Göre Sipariş Miktarı**

1. Kurumsal Bayi Ülkesine Göre Sipariş Miktarı adlı 3. görseli seçin. 
1.  **Harita stilleri** bölümünde **Tema** ayarını **Gri tonlama** olarak değiştirin. 
1.  **Başlık** bölümünde **Başlık metni** yerine "Kurumsal Bayi Ülkesine Göre Sipariş Miktarı" yazın.
1. **Metin boyutu** ayarını  **16 pt** olarak değiştirin. 
1.  **Gölge** ayarını **Açık** olarak değiştirin.  

**Görsel 4, Ürün Kategorisi ve Kurumsal Bayi İş Türüne Göre Satış Miktarı**

1. Ürün Kategorisi ve Kurumsal Bayi İş Türüne Göre Satış Miktarı adlı 4. görseli seçin. 
1.  **Başlık** bölümünde **Başlık metni** yerine "Ürün Kategorisi ve Kurumsal Bayi İş Türüne Göre Satış Miktarı" yazın.
1. **Metin boyutu** ayarını  **16 pt** olarak değiştirin. 
1.  **Gölge** ayarını **Açık** olarak değiştirin. 

**Görsel 5, Mali takvim dilimleyicisi**

1. Mali takvim dilimleyicisi adlı 5. görseli seçin.
1.  **Seçim denetimleri** bölümünde **"Tümünü seç"** özelliğini **Açık** duruma getirin. 
1.  **Dilimleyici üst bilgisi** bölümünde **Metin boyutu** ayarını  **16 pt** olarak değiştirin. 

### <a name="add-a-background-shape-for-the-title"></a>Başlık için bir arka plan şekli ekleme 

1.  **Ekle** şeridinde  **Şekiller** > **Dikdörtgen**'i seçin. 
1. Bunu sayfanın en üstüne yerleştirin, sonra sayfanın genişliğine ve başlığın yüksekliğine uyacak şekilde genişletin. 
1.  **Şekli biçimlendir** bölmesindeki **Çizgi** alanında **Saydamlık** ayarını **%100** olarak değiştirin. 
1.  **Dolgu** bölümünde **Dolgu rengi** ayarını **Tema rengi 5 #6B91C9 (mavi)** olarak değiştirin. 
1.  **Biçim** sekmesinde **Arkaya gönder** > **En arkaya gönder**'i seçin. 
1. Görsel 1'deki başlık metnini seçin ve **Yazı tipi rengi** ayarını  **Beyaz** olarak değiştirin. 

## <a name="finished-report"></a>Tamamlanmış rapor 

Dilimleyicide **FY2019** girişini seçin.

:::image type="content" source="media/desktop-dimensional-model-report/adventureworks-finished-report.png" alt-text="Raporunuzun son hali.":::

Özette, bu rapor yöneticinizin en önemleri sorularını yanıtlar: 

- Şubat 2019'da en çok satış yapılan gün hangisiydi? 
    25 Şubat tarihinde satış tutarı $253.915,47 olmuştur. 

- Şirketin en başarılı olduğu ülke neresi? 
    Satış miktarı 132.748 olan United States olmuştur. 

- Şirket hangi ürün kategorisine ve kurumsal bayi işletme türlerine yatırım yapmaya devam etmeli? 
    Şirket, Bikes kategorisi ile Value Added Reseller ve Warehouse kurumsal bayi işletmelerine yatırım yapmaya devam etmelidir. 

## <a name="save-your-report"></a>Raporunuzu kaydedin 

-  **Dosya** menüsünde **Kaydet**'i seçin. 


## <a name="publish-to-the-power-bi-service-to-share"></a>Paylaşmak için Power BI hizmetinde yayımlama 

Raporunuzu yöneticinizle ve iş arkadaşlarınızla paylaşmak için Power BI hizmetinde yayımlayın. Power BI hesabı olan iş arkadaşlarınızla paylaştığınızda, onlar raporunuzla etkileşimli çalışabilir ama değişiklikleri kaydedemez.

1. Power BI Desktop'ta **Giriş** şeridinde **Yayımla**'yı seçin. 
1. Power BI hizmetinde oturum açmanız gerekebilir. Henüz bir hesabınız yoksa [ücretsiz denemeye kaydolun](https://app.powerbi.com/signupredirect?pbi_source=web). 

1. Power BI hizmetinde Çalışma alanım gibi bir hedef seçtikten sonra  **Seç**'i belirleyin. 

1.  **"dosya-adınız" öğesini Power BI'da aç**'ı seçin. Tamamlanmış raporunuz tarayıcıda açılır. 

1. Raporunuzu başkalarıyla paylaşmak için raporun en üstündeki **Paylaş** öğesini seçin.

## <a name="next-steps"></a>Sonraki adımlar 

- [Tamamlanmış Power BI .pbix dosyasını](https://github.com/microsoft/powerbi-desktop-samples/blob/main/AdventureWorks%20Sales%20Sample/AdventureWorks%20Sales.pbix) indirin
- [Power BI Desktop'ta DAX ve veri modelleme](/learn/modules/dax-power-bi-models/) hakkında daha fazla bilgi edinin

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)
