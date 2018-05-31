---
title: "Eğitim: Power BI Desktop'ta Excel’deki ve OData akışındaki verileri birleştirme"
description: 'Eğitim: Excel’deki ve OData akışındaki verileri birleştirme'
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: tutorial
ms.date: 05/21/2018
ms.author: v-thepet
LocalizationGroup: Learn more
ms.openlocfilehash: c6cd75efd44259c2812f98a37875cf716d4843ad
ms.sourcegitcommit: e6db826c2f43a69e4c63d5f4920baa8f66bc41be
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2018
ms.locfileid: "34456215"
---
# <a name="tutorial-combine-sales-data-from-excel-and-an-odata-feed"></a>Eğitim: Excel’deki ve OData akışındaki satış verilerini birleştirme

Veriler yaygın olarak birden çok veri kaynağına yayılmış halde (ürün bilgilerinin bulunduğu bir veritabanı ve satış bilgilerinin bulunduğu diğer bir veritabanı gibi) bulunur. **Power BI Desktop** ile farklı kaynaklardan verileri birleştirerek ilgi çekici, merak uyandıran veri çözümlemeleri ve görselleştirmeler oluşturabilirsiniz. 

Bu öğreticide, iki veri kaynağından verileri birleştirmeyi öğreneceksiniz: ürün bilgilerini içeren bir Excel çalışma kitabı ve sipariş verilerini içeren bir OData akışı. Her bir veri kümesini içeri aktarıp dönüştürme ve toplama adımlarını gerçekleştirdikten sonra, her iki kaynaktan verileri kullanarak etkileşimli görselleştirmelerle bir satış analizi raporu oluşturacaksınız. Bu teknikler SQL Server sorgularına, CSV dosyalarına ve Power BI Desktop’taki diğer veri kaynaklarına da uygulanabilir.

>[!NOTE]
>Power BI Desktop'ta genellikle bir görevi birkaç farklı yolla gerçekleştirebilirsiniz. Örneğin, bir sütun ya da hücre üzerinde sağ tıklama işlemi veya **Diğer seçenekler** menüsü kullanılarak çok sayıda şerit seçimi yapılabilir. Aşağıdaki adımlarda birkaç alternatif yöntem açıklanmaktadır. 

## <a name="import-the-product-data-from-excel"></a>Ürün verilerini Excel'den içeri aktarma

İlk olarak, ürün verilerini Excel Products.xlsx çalışma kitabından Power BI Desktop’a aktarın.

1. [Products.xlsx Excel çalışma kitabını indirin](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Products.xlsx) ve **Products.xlsx** olarak kaydedin.
   
2. Power BI Desktop şeridinin **Giriş** sekmesinde **Verileri Al** öğesinin yanındaki açılır oku ve sonra **En Yaygın** açılır listesinden **Excel**’i seçin. 
   
   ![Veri al](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_1.png)
   
   >[!NOTE]
   >Ayrıca **Verileri Al** öğesini seçebilir ya da Power BI **Kullanmaya başlama** iletişim kutusundan **Verileri Al**’ı seçtikten sonra **Verileri Al** iletişim kutusundaki **Excel** ya da **Dosya** > **Excel**’i ve ardından **Bağlan**’ı seçebilirsiniz.
   
3. **Aç** iletişim kutusunda **Products.xlsx** dosyasına gidip seçin ve sonra **Aç** seçeneğini belirleyin.
   
4. **Gezgin** bölmesinde, **Products** tablosunu ve ardından **Düzenle**'yi seçin.
   
   ![Excel Gezgin bölmesi](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_2.png)
   
**Power Query Editor**’da tablonun önizlemesi açılır. Burada verileri temizlemek için dönüşümler uygulayabilirsiniz. 
   
![Power Query Editor](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_3.png)
   
>[!NOTE]
>**Power Query Editor**’ı, Power BI Desktop’ta **Giriş** şeridinden **Sorguları Düzenle** > **Sorguları Düzenle** öğesini seçerek veya **Rapor Görünümü** içinde herhangi bir sorgunun yanındaki **Diğer seçenekler**’e sağ tıklayıp veya seçip **Sorguyu Düzenle** seçeneğini belirleyerek de açabilirsiniz.

## <a name="clean-up-the-products-columns"></a>Ürünler sütunlarını temizleme

Birleşik raporunuz yalnızca Excel çalışma kitabındaki **ProductID**, **ProductName**, **QuantityPerUnit** ve **UnitsInStock** sütunlarını kullanacağı için diğer sütunları kaldırabilirsiniz. 

1. **Power Query Editor**’da **ProductID**, **ProductName**, **QuantityPerUnit** ve **UnitsInStock** sütunlarını seçin (**Ctrl**+**Tıklama** birleşimini kullanarak birden fazla sütun seçebilir veya **Shift**+**Tıklama** birleşimini kullanarak yan yana sütunları seçin).
   
2. Seçili üst bilgilerden herhangi birine sağ tıklayın ve açılır listeden **Diğer Sütunları Kaldır**’ı seçerek tabloda seçili olan sütunlar dışındaki tüm sütunları kaldırın. 
   Ayrıca, **Giriş** şerit sekmesindeki **Sütunları Yönet** grubundan **Sütunları Kaldır** > **Diğer Sütunları Kaldır**’ı seçebilirsiniz. 
   
   ![Diğer sütunları kaldırma](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/analyzingsalesdata_removeothercolumns.png)

## <a name="import-the-order-data-from-an-odata-feed"></a>Bir OData akışındaki sipariş verilerini içeri aktarma

Ardından, örnek Northwind satış sistemi OData akışından sipariş verilerini içeri aktarın. 

1. **Power Query Editor**’da **Yeni Kaynak**’ı ve sonra **En Yaygın** açılır listesinden **OData akışı**’nı seçin. 
   
   ![OData alma](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/get_odata.png)
   
2. **OData Akışı** iletişim kutusunda, Northwind OData akışına ait URL'yi (`http://services.odata.org/V3/Northwind/Northwind.svc/`) yapıştırın ve **Tamam**’ı seçin.
   
   ![OData akışı iletişim kutusu](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/get_odata2.png)
   
3. **Gezgin** bölmesinde **Siparişler** tablosunu seçin ve sonra **Tamam**’ı seçerek verileri **Power Query Editor**’a yükleyin.
   
   ![OData Gezgin bölmesi](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/analyzingsalesdata_odatafeed.png)
   
   >[!NOTE]
   >**Gezgin**’de, onay kutusunu seçmeden herhangi bir tablo adını seçerek önizleme görüntüleyebilirsiniz.

## <a name="expand-the-order-data"></a>Sipariş verilerini genişletme

İlişkisel veritabanları veya Northwind OData akışı gibi birden fazla tablosu olan veri kaynaklarına bağlandığınızda, sorgularınızı oluşturmak için tablolar arasındaki başvuruları kullanabilirsiniz. **Siparişler** tablosu, birden fazla ilgili tabloya başvurular içerir. **Expand** işlemini kullanarak, ilgili **Order_Details** tablosundan **ProductID**, **UnitPrice** ve **Quantity** sütunlarını konu (**Siparişler**) tablosuna ekleyebilirsiniz. 

1. **Order_Details** sütununu görene kadar **Siparişler** tablosunu sağa kaydırın. Veri yerine başka bir tabloya başvuru içerdiğini unutmayın.
   
   ![Order_Details sütunu](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/7.png)
   
2. **Order_Details** sütun başlığındaki **Genişlet** simgesini (![Genişlet simgesi](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/expand.png)) seçin. 
   
3. **Genişlet** açılan menüsünde:
   
   1. Tüm sütunları temizlemek için **(Tüm Sütunları Seç)** seçeneğini belirleyin.
      
   2. **ProductID**, **UnitPrice** ve **Quantity** sütunlarını seçtikten sonra **Tamam**’ı seçin.
      
      ![Genişlet iletişim kutusu](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/8.png)

**Order_Details** tablosunu genişlettikten sonra **Order_Details** sütunu iç içe tablodaki üç yeni sütunla değiştirilir ve her siparişten eklenen veriler için tabloda yeni satırlar bulunur. 

![Genişletilmiş sütunlar](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/9.png)

## <a name="create-a-custom-calculated-column"></a>Özel bir hesaplanmış sütun oluşturma

Power Query Editor, verilerinizi zenginleştirmeniz için hesaplamalar ve özel alanları oluşturmanızı sağlar. Birim fiyatı öğe miktarıyla çarparak her bir satır öğesinin toplam fiyatını bir sırayla hesaplayan özel bir sütun oluşturacaksınız.

1. Power Query Editor’ın **Sütun Ekle** şerit sekmesinde **Özel Sütun**’u seçin.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/10.png)
   
2. **Özel Sütun** iletişim kutusunda **Yeni sütun adı** alanına **LineTotal** yazın.

3. **=** öğesinden sonra gelen **Özel sütun formülü** alanına **[Order_Details.UnitPrice]** \* **[Order_Details.Quantity]** girin. (Alan adlarını yazmak yerine **Kullanılabilir sütunlar** kaydırma kutusundan seçebilir ve **<< Ekle** seçeneğini kullanabilirsiniz.) 
3. **Tamam**'ı seçin.
   
   ![Özel Sütun iletişim kutusu](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/11.png)

Yeni **LineTotal** alanı, **Siparişler** tablosunun son sütunu olarak görünür.

## <a name="set-the-data-type-for-the-new-field"></a>Yeni alanın veri türünü belirleme

Power Query Editor verilere bağlandığında, her bir alanın en iyi veri türünü belirler ve verileri buna uygun olarak gösterir. Alanlara atanan veri türlerini üst bilgilerdeki simgelere göre veya **Giriş** şerit sekmesinin **Dönüşüm** grubundaki **Veri Türü** altında görüntüleyebilirsiniz. 

Yeni **LineTotal** sütununuzda **Any** veri türü mevcuttur ancak değerleri para birimidir. Bir veri türü atamak için **LineTotal** sütunu üst bilgisine sağ tıklayın, açılır listeden **Veri Türünü Değiştir**’i seçin ve sonra **Sabit ondalık sayı**’yı seçin. 

![Veri türünü değiştirme](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/12.png)

>[!NOTE]
>Ayrıca **LineTotal** sütununu, sonra **Giriş** şerit sekmesinin **Dönüşüm** alanındaki **Veri Türü**’nü ve ardından **Sabit ondalık sayı**’yı seçebilirsiniz.

## <a name="clean-up-the-orders-columns"></a>Sipariş sütunlarını temizleme

Raporlarda modelinizle birlikte çalışmayı kolaylaştırmak için, bazı sütunları silebilir, yeniden adlandırabilir ve yeniden sıralayabilirsiniz.

Raporunuz yalnızca **OrderDate**, **ShipCity**, **ShipCountry**, **Order_Details.ProductID**, **Order_Details.UnitPrice** ve **Order_Details.Quantity** sütunlarını kullanır. Excel verileriyle yaptığınız gibi bu sütunları seçip **Diğer Sütunları Kaldır** seçeneğini kullanabilir veya listedekilerin dışında kalan tüm sütunları seçebilir, seçili sütunlara sağ tıklayabilir ve **Sütunları Kaldır**’ı seçerek tümünü kaldırabilirsiniz. 

**Order_Details.ProductID**, **Order_Details.UnitPrice** ve **Order_Details.Quantity** sütunlarını tanımlamayı kolaylaştırmak için, sütun adlarındaki *Order_Details.* ön eklerini kaldırabilirsiniz. Sütunları sırasıyla **ProductID**, **UnitPrice** ve **Quantity** olarak yeniden adlandırmak için:

1. Her bir sütun üst bilgisine çift tıklayın ya da basılı tutun veya sütun üst bilgisine sağ tıklayıp açılır listeden **Yeniden Adlandır**’ı seçin. 
2. Her bir adın *Order_Details.* ön ekini silin ve sonra **Enter** tuşuna basın.

Son olarak, **LineTotal** sütununa erişimi kolaylaştırmak için sütunu sola sürükleyip **ShipCountry** sütununun hemen sağına bırakın.

![Temizlenmiş tablo](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/14.png)

## <a name="review-the-query-steps"></a>Sorgu adımlarını gözden geçirme

Power Query Editor’daki verileri şekillendirip dönüştürdüğünüzde her bir adım, Power Query Editor’ın sağ tarafındaki **Sorgu Ayarları** bölmesinin **Uygulanan Adımlar** alanına kaydedilmiştir. Yaptığınız değişiklikleri gözden geçirmek için Uygulanan Adımlar boyunca geri gidebilir ve gerekirse bunları düzenleyebilir, silebilir veya yeniden ayarlayabilirsiniz (ancak önceki adımların değiştirilmesi, sonraki adımları bozabileceğinden bu riskli olabilir). 

Power Query Editor’ın sol tarafındaki **Sorgular** listesinden her bir sorguyu seçin ve **Sorgu Ayarları** içindeki **Uygulanan Adımlar**’ı gözden geçirin. Önceki veri dönüşümlerini uyguladıktan sonra, iki sorgunuza ait Uygulanan Adımlar aşağıdaki gibi görünmelidir:

![Ürünler sorgusu Uygulanan Adımlar](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/15.png) &nbsp;&nbsp; ![Siparişler sorgusu Uygulanan Adımlar](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/17.png)

>[!TIP]
>Uygulanan Adımların temelini, **M** dili olarak da bilinen, **Power Query Editor**’da yazılan formüller oluşturur. Formülleri görmek ve düzenlemek için, şeridin Giriş sekmesinin **Sorgu** grubunda **Gelişmiş Düzenleyici**’yi seçin. 

## <a name="import-the-transformed-queries"></a>Dönüştürülmüş sorguları içeri aktarma

Dönüştürülmüş verilerinizden memnun olduğunuzda, Power BI Desktop Rapor Görünümüne verileri aktarmak için **Giriş** şerit sekmesinin **Kapat** grubundaki **Kapat ve Uygula** > **Kapat ve Uygula** öğesini seçin. 

![Kapat ve Uygula](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_4.png)

Veriler yüklendikten sonra sorgular Power BI Desktop Rapor Görünümündeki **Alanlar** listesinde görünür.

![Alanlar listesindeki sorgular](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/18.png)

## <a name="manage-the-relationship-between-the-datasets"></a>Veri kümeleri arasındaki ilişkiyi yönetme

Power BI Desktop, sorgular üzerinde raporlama yapmak için bunları birleştirmenizi gerektirmez. Bununla birlikte, ortak sahip oldukları alanlara göre veri kümeleri arasındaki ilişkileri kullanarak raporlarınızı genişletebilir ve zenginleştirebilirsiniz. İlişkileri Power BI Desktop otomatik olarak algılayabilir veya Power BI Desktop **İlişkileri Yönet** iletişim kutusunda siz oluşturabilirsiniz. Power BI Desktop’ta ilişkiler hakkında daha fazla bilgi için bkz. [İlişki oluşturma ve yönetme](desktop-create-and-manage-relationships.md).

Bu öğreticideki Siparişler ve Ürünler veri kümeleri ortak bir *ProductID* alanına sahiptir, dolayısıyla aralarında bu sütuna göre bir ilişki vardır. 

1. Power BI Desktop Rapor Görünümünde, **Giriş** şerit sekmesinin **İlişkiler** alanındaki **İlişkileri Yönet**’i seçin.
   
   ![İlişkileri Yönet şeridi](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_5.png)
   
2. **İlişkileri Yönet** iletişim kutusunda Power BI Desktop’ın Ürünler ile Siparişler tabloları arasında etkin bir ilişki olduğunu zaten algıladığına ve listelediğine dikkat edin. İlişkiyi görüntülemek için **Düzenle**’yi seçin. 
   
   ![İlişkileri Yönet iletişim kutusu](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_6.png)
   
   İlişkinin ayrıntılarını gösteren **İlişkiyi Düzenle** iletişim kutusu açılır.  
   
   ![İlişkiyi Düzenle iletişim kutusu](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_7.png)
   
3. Power BI Desktop, ilişkiyi doğru bir şekilde otomatik olarak algıladığı için **İptal** ve sonra **Kapat**’ı seçerek ilişki iletişim kutularından çıkış yapabilirsiniz.

Power BI Desktop penceresinin sol tarafındaki **İlişki** görünümünü seçerek, sorgularınız arasındaki ilişkileri görüntüleyip yönetebilirsiniz. İki sorguyu bağlayan satırdaki oka çift tıklayarak **İlişkiyi Düzenle** iletişim kutusunu açın ve ilişkiyi değiştirin. 

![İlişki Görünümü](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_8.png)

İlişkiler Görünümünden Rapor Görünümüne geri dönmek için **Rapor Görünümü** simgesini seçin. 

![Rapor Görünümü simgesi](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_9.png)

## <a name="create-visualizations-using-your-data"></a>Verilerinizi kullanarak görselleştirmeler oluşturma

Power BI Desktop Rapor Görünümünde verilerinizden içgörüler elde etmek için çeşitli görselleştirmeler oluşturabilirsiniz. Birden çok sayfa içeren raporlar oluşturabilir ve her bir sayfada birden çok görsel olmasını sağlayabilirsiniz. Verilerinizi çözümlemenize ve anlamanıza yardımcı olmaları için başkalarıyla birlikte görselleştirmelerinizle etkileşime geçebilirsiniz. Power BI Hizmetinde (siteniz) raporları görüntüleme ve düzenleme hakkında daha fazla bilgi için bkz. [Rapor Düzenleme](service-interact-with-a-report-in-editing-view.md).

Veri kümelerinizin her ikisini ve aralarındaki ilişkiyi kullanarak satış verilerinizin görselleştirilmesine ve analiz edilmesine yardımcı olabilirsiniz. 

İlk olarak, sipariş edilen her bir ürünün miktarını göstermek üzere her iki sorgunun alanlarını kullanan yığılmış bir sütun grafiği oluşturun. 

1. Sağ taraftaki **Alanlar** bölmesinde bulunan **Siparişler** bölümünden **Miktar** alanını seçin veya tuval üzerindeki boş bir alana sürükleyin. Bu işlem, sipariş edilen tüm ürünlerin toplam miktarını gösteren yığılmış bir sütun grafiği oluşturur. 
   
2. Sipariş edilen her bir ürünün miktarını görüntülemek için **Alanlar** bölmesindeki **Ürünler** bölümünden **ProductName** öğesini seçin veya grafiğin üzerine sürükleyin. 
   
3. Ürünleri en fazla sipariş edilenden en az sipariş edilene doğru sıralamak için, görselleştirmenin sağ üst kısmındaki **Diğer seçenekler** üç nokta simgesini (**...**) ve sonra **Miktara Göre Sırala**’yı seçin.
   
4. Grafiği ürün adları görünür olacak şekilde genişletmek için grafiğin köşelerindeki tutamaçları kullanın. 
   
   ![ProductName’e Göre Miktar çubuk grafiği](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/19.png)

Ardından, zaman içinde (**OrderDate**) sipariş tutarını USD cinsinden (**LineTotal**) gösteren bir grafik oluşturun. 

1. Tuvalde seçili bir öğe yokken **Alanlar** bölmesindeki **Siparişler** bölümünden **LineTotal** öğesini seçin veya tuval üzerindeki boş bir alana sürükleyin. Yığılmış sütun grafiği, tüm siparişlerin toplam tutarını USD cinsinden gösterir. 
   
2. Grafik seçiliyken **Siparişler** bölümünden **OrderDate** öğesini seçin veya grafiğin üzerine sürükleyin. Grafik bu durumda her bir sipariş tarihinin satır toplamlarını gösterir. 
   
3. Daha fazla veri görebilmek için köşeleri sürükleyerek görselleştirmeyi yeniden boyutlandırın. 
   
   ![OrderDate’e Göre LineTotals çizgi grafiği](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/20.png)
   
   >[!TIP]
   >Grafikte yalnızca Yılları görüyorsanız (yalnızca üç veri noktası), **Görselleştirmeler** bölmesinin **Eksen** alanındaki **OrderDate** öğesinin yanın bulunan oku açın ve **Tarih Hiyerarşisi** yerine **OrderDate** öğesini seçin. 

Son olarak, her bir ülkenin sipariş tutarlarını gösteren bir harita görselleştirmesi oluşturun. 

1. Tuvalde seçili bir öğe yokken **Alanlar** bölmesindeki **Siparişler** bölümünden **ShipCountry** öğesini seçin veya tuval üzerindeki boş bir alana sürükleyin. Power BI Desktop, verilerin ülke adları olduğunu algılar ve siparişi olan her ülke için bir veri noktası ile birlikte otomatik olarak bir harita görselleştirmesi oluşturur. 
   
2. Veri noktalarının boyutlarını her bir ülkenin sipariş tutarlarını yansıtacak hale getirmek için **LineTotal** alanını haritanın üzerine sürükleyin (veya **Görselleştirmeler** alanının alt yarısında bulunan **Boyut** altındaki **Veri alanlarını buraya sürükleyin** alanına sürükleyin). Harita üzerindeki dairelerin boyutları bu durumda her bir ülkenin sipariş tutarlarını USD cinsinden yansıtır. 
   
   ![ShipCountry’ye Göre LineTotals harita görselleştirmesi](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/21.png)

## <a name="interact-with-your-report-visuals-to-analyze-further"></a>Daha fazla analiz yapmak için rapor görsellerinizle etkileşimde bulunma

Power BI Desktop, birbirlerine çapraz vurgulama ve filtreleme uygulayan görsellerle etkileşimde bulunarak daha fazla eğilimi ortaya çıkarmanızı sağlar. Daha fazla bilgi için bkz. [Raporlarda Filtreleme ve Vurgulama](power-bi-reports-filters-and-highlighting.md). 

Sorgularınız arasındaki ilişki nedeniyle, bir görselleştirmedeki etkileşimler sayfa üzerindeki diğer tüm görselleştirmeleri etkiler. 

Harita görselleştirmesi üzerinde, merkezi **Kanada**’da bulunan daireyi seçin. Diğer iki görselleştirmenin yalnızca Kanada’ya ait satır toplamlarını ve sipariş miktarlarını vurgulamak üzere filtrelendiğine dikkat edin.

![Kanada için filtrelenmiş satış verileri](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/22.png)

**ProductName’e Göre Miktar** grafiğindeki ürünlerden birini seçerseniz, harita ve tarih grafik filtresi o ürünün verilerini yansıtacak şekilde filtrelenir. **OrderDate’e Göre LineTotal** grafiğindeki tarihlerden birini seçerseniz, harita ve ürün grafiği o tarihe ait verileri gösterecek şekilde filtrelenir. 
>[!TIP]
>Bir seçimi kaldırmak için yeniden seçin veya diğer görselleştirmelerden birini seçin. 

## <a name="complete-the-sales-analysis-report"></a>Satış analizi raporunu tamamlama

Products.xlsx Excel dosyasındaki ve Northwind OData akışındaki verileri, farklı ülke, zaman çerçevesi ve ürünler için sipariş bilgilerini analiz etmeye yardımcı olan görseller halinde birleştirmeyi tamamladınız. Raporunuz hazır olduğunda [Power BI hizmetine yükleyerek](desktop-upload-desktop-files.md) diğer Power BI kullanıcılarıyla paylaşabilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar
* [Diğer Power BI Desktop eğitimlerini okuyun](http://go.microsoft.com/fwlink/?LinkID=521937)
* [Power BI Desktop videolarını izleyin](http://go.microsoft.com/fwlink/?LinkID=519322)
* [Power BI Forumu'nu ziyaret edin](http://go.microsoft.com/fwlink/?LinkID=519326)
* [Power BI Blogu'nu okuyun](http://go.microsoft.com/fwlink/?LinkID=519327)