---
title: "Öğretici: Power BI Desktop'ta Excel’deki ve OData akışındaki verileri birleştirme"
description: 'Öğretici: Excel’deki ve OData akışındaki verileri birleştirme'
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: pbi-data-sources
ms.topic: tutorial
ms.date: 01/17/2020
LocalizationGroup: Learn more
ms.openlocfilehash: 391c8fef1e95aa39ff6dfcd8aab8088f692504e7
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96404928"
---
# <a name="tutorial-analyze-sales-data-from-excel-and-an-odata-feed"></a>Öğretici: Excel’deki ve OData akışındaki satış verilerini analiz etme

Birden çok veri kaynağından veriler olması yaygın bir durumdur. Örneğin, biri ürün bilgileri ve diğeri de satış bilgileri için iki veritabanınız olabilir. *Power BI Desktop* ile farklı kaynaklardan verileri birleştirerek ilgi çekici, merak uyandıran veri çözümlemeleri ve görselleştirmeler oluşturabilirsiniz.

Bu öğreticide iki veri kaynağından elde edilen verileri birleştireceksiniz:

* Ürün bilgilerini içeren Excel çalışma kitabı
* Sipariş verilerini içeren OData akışı

Her veri kümesini içeri aktaracak, dönüştürme ve toplama işlemleri yapacaksınız. Ardından iki kaynaktaki verileri kullanarak, etkileşimli görselleştirmelerle bir satış analizi raporu oluşturacaksınız. Daha sonra bu teknikleri SQL Server sorgularına, CSV dosyalarına ve Power BI Desktop’taki diğer veri kaynaklarına da uygulayabilirsiniz.

>[!NOTE]
>Power BI Desktop'ta genellikle bir görevi birkaç farklı yolla gerçekleştirebilirsiniz. Örneğin, sütunda veya hücrede sağ tıklayarak veya **Diğer seçenekler** menüsünü kullanarak ek şerit seçimleri görebilirsiniz. Aşağıdaki adımlarda birkaç alternatif yöntem açıklanmaktadır.

## <a name="import-excel-product-data"></a>Excel ürün verilerini içeri aktarma

İlk olarak, ürün verilerini *Products.xlsx* Excel çalışma kitabından Power BI Desktop’a aktarın.

1. [Products.xlsx Excel çalışma kitabını indirin](https://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Products.xlsx) ve *Products.xlsx* olarak kaydedin.

1. Power BI Desktop şeridinin **Giriş** sekmesinde **Verileri Al** öğesinin yanındaki oku ve sonra **En Yaygın** menüsünden **Excel**’i seçin.

   ![Veri al](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_1.png)

   >[!NOTE]
   >Ayrıca **Verileri Al** öğesini seçebilir ya da Power BI **Kullanmaya başlama** iletişim kutusundan **Verileri Al**’ı seçtikten sonra **Verileri Al** iletişim kutusundaki **Excel** ya da **Dosya** > **Excel**’i ve ardından **Bağlan**’ı seçebilirsiniz.

1. **Aç** iletişim kutusunda **Products.xlsx** dosyasına gidip seçin ve sonra **Aç** seçeneğini belirleyin.

1. **Gezgin**'de **Products** tablosunu ve ardından **Veri Dönüştürme**'yi seçin.

   ![Excel Gezgin bölmesi](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_2.png)

Power Query Düzenleyicisi’nde tablo önizlemesi açılır. Burada verileri temizlemek için dönüşümler uygulayabilirsiniz.

![Power Query Düzenleyicisi](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_3.png)

>[!NOTE]
>Power Query Düzenleyicisi'ni, Power BI Desktop’ta **Giriş** şeridinden **Sorguları Düzenle** > **Sorguları Düzenle** öğesini seçerek veya **Rapor** görünümü içinde herhangi bir sorgunun yanındaki **Diğer seçenekler**’e sağ tıklayıp veya bunu seçip **Sorguyu Düzenle** seçeneğini belirterek de açabilirsiniz.

## <a name="clean-up-the-products-columns"></a>Ürünler sütunlarını temizleme

Birleşik raporunuz Excel çalışma kitabındaki **ProductID**, **ProductName**, **QuantityPerUnit** ve **UnitsInStock** sütunlarını kullanacaktır. Diğer sütunları kaldırabilirsiniz.

1. Power Query Düzenleyicisi'nde **ProductID**, **ProductName**, **QuantityPerUnit** ve **UnitsInStock** sütunlarını seçin. Ctrl tuşunu kullanarak birden çok sütunu veya Shift tuşunu kullanarak bitişik sütunları seçebilirsiniz.

1. Seçili üst bilgilerden birine sağ tıklayın. Açılan menüden **Diğer Sütunları Kaldır**'ı seçin.
   Ayrıca, **Giriş** şerit sekmesindeki **Sütunları Yönet** grubundan **Sütunları Kaldır** > **Diğer Sütunları Kaldır**’ı seçebilirsiniz.

   ![Diğer sütunları kaldırma](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/analyzingsalesdata_removeothercolumns.png)

## <a name="import-the-odata-feeds-order-data"></a>OData akışının sipariş verilerini içeri aktarma

Ardından, örnek Northwind satış sistemi OData akışından sipariş verilerini içeri aktarın.

1. Power Query Düzenleyicisi'nde **Yeni Kaynak**'ı seçin ve sonra da **En Yaygın** menüsünden **OData akışı**'nı seçin.

   ![OData alma](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/get_odata.png)

1. **OData akışı** iletişim kutusunda Northwind OData akışının URL'sini (`https://services.odata.org/V3/Northwind/Northwind.svc/`) yapıştırın. **Tamam**’ı seçin.

   ![OData akışı iletişim kutusu](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/get_odata2.png)

1. **Gezgin**'de **Orders** tablosunu ve sonra **Veri Dönüştürme**'yi seçerek verileri Power Query Düzenleyicisi'ne yükleyin.

   ![OData için Gezgin](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/analyzingsalesdata_odatafeed.png)

   >[!NOTE]
   >**Gezgin**’de, onay kutusunu seçmeden herhangi bir tablo adını seçerek önizleme görüntüleyebilirsiniz.

## <a name="expand-the-order-data"></a>Sipariş verilerini genişletme

İlişkisel veritabanları veya Northwind OData akışı gibi birden fazla tablosu olan veri kaynaklarına bağlandığınızda, sorgularınızı oluşturmak için tablo başvurularını kullanabilirsiniz. **Siparişler** tablosu, birden fazla ilgili tabloya başvurular içerir. İlgili **Order_Details** tablosundan **ProductID**, **UnitPrice** ve **Quantity** sütunlarını konu (**Orders**) tablosuna eklemek için genişletme işlemini kullanabilirsiniz.

1. **Order_Details** sütununu görene kadar **Orders** tablosunu sağa kaydırın. Burada veriler değil başka bir tabloya başvurular bulunur.

   ![Order_Details sütunu](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/order-details-column.png)

1. **Order_Details** sütun başlığındaki **Genişlet** simgesini (![Genişlet simgesi](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/expand.png)) seçin.

1. Açılan menüde:

   1. Tüm sütunları temizlemek için **(Tüm Sütunları Seç)** seçeneğini belirleyin.

   1. **ProductID**, **UnitPrice** ve **Quantity** sütunlarını seçtikten sonra **Tamam**’ı seçin.

      ![Genişlet açılan menüsü](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/expand-drop-down-menu.png)

**Order_Details** tablosunu genişlettikten sonra **Order_Details** sütununun yerini iç içe üç yeni tablo sütunu alır. Her siparişe eklenen veriler için tabloda yeni satırlar vardır.

![Genişletilmiş sütunlar](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/expanded-columns.png)

## <a name="create-a-custom-calculated-column"></a>Özel bir hesaplanmış sütun oluşturma

Power Query Editor, verilerinizi zenginleştirmeniz için hesaplamalar ve özel alanları oluşturmanızı sağlar. Her siparişin satır öğesinin toplam fiyatını hesaplamak için birim fiyatıyla öğe miktarını çarpan özel bir sütun oluşturacaksınız.

1. Power Query Editor'ın **Sütun Ekle** şerit sekmesinde **Özel Sütun**'u seçin.

   ![Özel sütun ekleme](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/adding-a-custom-column.png)

1. **Özel Sütun** iletişim kutusunda **Yeni sütun adı** alanına **LineTotal** yazın.

1. **=** öğesinden sonra gelen **Özel sütun formülü** alanına **[Order_Details.UnitPrice]** \* **[Order_Details.Quantity]** parametrelerini girin. Alan adlarını yazmak yerine **Kullanılabilir sütunlar** kaydırma kutusundan seçebilir ve **<< Ekle** seçeneğini kullanabilirsiniz.

1. **Tamam**’ı seçin.

   ![Özel Sütun iletişim kutusu](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/custom-column-dialog-box.png)

   Yeni **LineTotal** alanı, **Siparişler** tablosunun son sütunu olarak görünür.

## <a name="set-the-new-fields-data-type"></a>Yeni alanın veri türünü ayarlama

Power Query Editor verilere bağlandığında, görüntüleme amacıyla her alanın veri türünü tahmin eder. Her alana atanan veri türü bir üst bilgi simgesiyle gösterilir. Ayrıca **Giriş** şerit sekmesinin **Dönüştür** grubundaki **Veri Türü**'nün altına da bakabilirsiniz.

Yeni **LineTotal** sütununuzun veri türü **Herhangi Biri**'dir ama para birimi değerleri içerir. Bir veri türü atamak için **LineTotal** sütunu üst bilgisine sağ tıklayın, açılır menüden **Türü Değiştir**’i seçin ve sonra **Sabit ondalık sayı**’yı seçin.

![Veri türünü sabit ondalık olarak değiştirme](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/change-data-type-to-fixed-decimal.png)

>[!NOTE]
>Ayrıca **LineTotal** sütununu, sonra **Giriş** şerit sekmesinin **Dönüşüm** alanındaki **Veri Türü**’nün yanındaki oku ve ardından **Sabit ondalık sayı**’yı seçebilirsiniz.

## <a name="clean-up-the-orders-columns"></a>Sipariş sütunlarını temizleme

Raporlarda modelinizle birlikte çalışmayı kolaylaştırmak için, bazı sütunları silebilir, yeniden adlandırabilir ve yeniden sıralayabilirsiniz.

Raporunuz şu sütunları kullanacaktır:

* **OrderDate**
* **ShipCity**
* **ShipCountry**
* **Order_Details.ProductID**
* **Order_Details.UnitPrice**
* **Order_Details.Quantity**
* **LineTotal**

Bu sütunları seçin ve Excel verileriyle yaptığınız gibi **Diğer Sütunları Kaldır**'ı kullanın. Öte yandan listelenmeyen sütunları seçmek isterseniz bunlardan birine sağ tıklayabilir ve **Sütunları Kaldır**'ı seçebilirsiniz.

Ön eki "**Order_Details.** " olan sütunları, daha kolay okunmaları için yeniden adlandırabilirsiniz:

1. Her sütun üst bilgisine çift tıklayın ya da basılı tutun veya sütun üst bilgisine sağ tıklayıp açılır menüden **Yeniden Adlandır**’ı seçin.

1. Her bir adın **Order_Details.** ön ekini silin.

Son olarak, **LineTotal** sütununa erişimi kolaylaştırmak için sütunu sola sürükleyip **ShipCountry** sütununun hemen sağına bırakın.

![Temizlenmiş tablo](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/cleaned-up-table.png)

## <a name="review-the-query-steps"></a>Sorgu adımlarını gözden geçirme

Verileri şekillendirmek ve dönüştürmek için kullanılan Power Query Editor eylemleriniz kaydedilir. Her eylem sağda **Sorgu Ayarları** bölmesinde, **Uygulanan Adımlar**'ın altında gösterilir. Adımlarınızı gözden geçirmek ve gerekirse bunları düzenlemek, silmek veya yeniden sıralamak için **Uygulanan Adımlar**'da geri gidebilirsiniz. Bununla birlikte, önceki adımlarda değişiklik yapmak risklidir çünkü sonraki adımlar bozulabilir.

Power Query Editor’ın sol tarafındaki **Sorgular** listesinden her bir sorguyu seçin ve **Sorgu Ayarları** içindeki **Uygulanan Adımlar**’ı gözden geçirin. Önceki veri dönüştürmelerini uyguladıktan sonra, iki sorgunuza ait **Uygulanan Adımlar** şöyle görünmelidir:

![Ürünler sorgusu Uygulanan Adımlar](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/products-query-applied-steps.png) &nbsp;&nbsp; ![Siparişler sorgusu Uygulanan Adımlar](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/orders-query-applied-steps.png)

>[!TIP]
>Uygulanan Adımların temelini [M dili](/powerquery-m/power-query-m-reference) olarak da bilinen *Power Query Dili*'nde yazılan formüller oluşturur. Formülleri görmek ve düzenlemek için, şeridin **Giriş** sekmesinin **Sorgu** grubunda **Gelişmiş Düzenleyici**’yi seçin.

## <a name="import-the-transformed-queries"></a>Dönüştürülmüş sorguları içeri aktarma

Dönüştürülmüş verilerinizden memnun kaldığınızda ve bunları Power BI Desktop **Rapor** görünümünde içeri aktarmaya hazır olduğunuzda, **Giriş** şerit sekmesinin **Kapat** grubundaki **Kapat ve Uygula** > **Kapat ve Uygula**'yı seçin.

![Kapat ve Uygula](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_4.png)

Veriler yüklendikten sonra sorgular Power BI Desktop **Rapor** görünümündeki **Alanlar** listesinde görünür.

![Alanlar listesindeki sorgular](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/queries-in-fields-list.png)

## <a name="manage-the-relationship-between-the-datasets"></a>Veri kümeleri arasındaki ilişkiyi yönetme

Power BI Desktop, sorgular üzerinde raporlama yapmak için bunları birleştirmenizi gerektirmez. Bununla birlikte, ortak alanlarına göre veri kümeleri arasındaki ilişkileri kullanarak raporlarınızı genişletebilir ve zenginleştirebilirsiniz. İlişkileri Power BI Desktop otomatik olarak algılayabilir veya Power BI Desktop **İlişkileri Yönet** iletişim kutusunda siz oluşturabilirsiniz. Daha fazla bilgi için bkz. [Power BI Desktop'ta ilişki oluşturma ve ilişkileri yönetme](../transform-model/desktop-create-and-manage-relationships.md).

Paylaşılan `ProductID` alanı bu öğreticinin `Orders` ile `Products` veri kümeleri arasında ilişki oluşturur.

1. Power BI Desktop **Rapor** görünümünde **Giriş** şerit sekmesinin **İlişkiler** alanındaki **İlişkileri Yönet**’i seçin.

   ![İlişkileri Yönet şeridi](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_5.png)

1. **İlişkileri yönet** iletişim kutusunda Power BI Desktop’ın **Products** ile **Orders** tabloları arasında etkin bir ilişki olduğunu zaten algıladığını ve listelediğini görebilirsiniz. İlişkiyi görüntülemek için **Düzenle**’yi seçin.

   ![İlişkileri Yönet iletişim kutusu](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_6.png)

   İlişkinin ayrıntılarını gösteren **İlişkiyi Düzenle** açılır.  

   ![İlişkiyi Düzenle iletişim kutusu](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_7.png)

1. Power BI Desktop, ilişkiyi doğru bir şekilde otomatik olarak algıladığı için **İptal** ve sonra **Kapat**’ı seçebilirsiniz.

Power BI Desktop'ta sol taraftaki **Model**'i seçerek sorgu ilişkilerini görüntüleyin ve yönetin. İki sorguyu bağlayan satırdaki oka çift tıklayarak **İlişkiyi düzenle** iletişim kutusunu açın ve ilişkiyi görüntüleyin veya değiştirin.

![İlişki Görünümü](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_8.png)

**Model** görünümünden **Rapor** görünümüne dönmek için **Rapor** simgesini seçin.

![Rapor Görünümü simgesi](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_9.png)

## <a name="create-visualizations-using-your-data"></a>Verilerinizi kullanarak görselleştirmeler oluşturma

Veri içgörüleri elde etmek için Power BI Desktop Gözden Geçirme Görünümünde farklı görselleştirmeler oluşturabilirsiniz. Raporların birden çok sayfası olabilir ve her sayfada birden çok görsel bulunabilir. Verileri çözümlemenize ve anlamanıza yardımcı olmaları için başkalarıyla birlikte görselleştirmelerinizle etkileşime geçebilirsiniz. Daha fazla bilgi için bkz. [Power BI hizmetinin Düzenleme görünümünde raporla etkileşim kurma](../create-reports/service-interact-with-a-report-in-editing-view.md).

Veri kümelerinizin her ikisini ve aralarındaki ilişkiyi kullanarak satış verilerinizin görselleştirilmesine ve analiz edilmesine yardımcı olabilirsiniz.

İlk olarak, sipariş edilen her bir ürünün miktarını göstermek üzere her iki sorgunun alanlarını kullanan yığılmış bir sütun grafiği oluşturun.

1. Sağ taraftaki **Alanlar** bölmesinde bulunan **Siparişler** bölümünden **Miktar** alanını seçin veya tuval üzerindeki boş bir alana sürükleyin. Sipariş edilen tüm ürünlerin toplam miktarını gösteren yığılmış bir sütun grafiği oluşturulur.

1. Sipariş edilen her ürünün miktarını görüntülemek için **Alanlar** bölmesindeki **Products** bölümünden **ProductName** öğesini seçin veya grafiğin üzerine sürükleyin.

1. Ürünleri en fazla sipariş edilenden en az sipariş edilene doğru sıralamak için, görselleştirmenin sağ üst kısmındaki **Diğer seçenekler** üç nokta simgesini ( **...** ) ve sonra **Miktara Göre Sırala**’yı seçin.

1. Grafiği ürün adları görünür olacak şekilde genişletmek için grafiğin köşelerindeki tutamaçları kullanın.

   ![ProductName’e Göre Miktar çubuk grafiği](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/quantity-by-productname-bar-chart.png)

Ardından, zaman içinde (**OrderDate**) sipariş tutarını USD cinsinden (**LineTotal**) gösteren bir grafik oluşturun.

1. Tuvalde seçili bir öğe yokken **Alanlar** bölmesindeki **Siparişler** bölümünden **LineTotal** öğesini seçin veya tuval üzerindeki boş bir alana sürükleyin. Yığılmış sütun grafiği, tüm siparişlerin toplam tutarını USD cinsinden gösterir.

1. Yığılmış grafiği seçin, sonra **Orders** bölümünden **OrderDate** öğesini seçin veya grafiğin üzerine sürükleyin. Grafik bu durumda her bir sipariş tarihinin satır toplamlarını gösterir.

1. Görselleştirmeyi yeniden boyutlandırmak ve daha fazla veri görebilmek için köşeleri sürükleyin.

   ![OrderDate’e Göre LineTotals çizgi grafiği](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/linetotals-by-orderdate-line-chart.png)

   >[!TIP]
   >Grafikte yalnızca **Years** ve üç veri noktası görüyorsanız, **Görselleştirmeler** bölmesinin **Eksen** alanındaki **OrderDate** öğesinin yanında bulunan oku seçin ve sonra da **Tarih Hiyerarşisi** yerine **OrderDate** öğesini seçin.

Son olarak, her bir ülkenin sipariş tutarlarını gösteren bir harita görselleştirmesi oluşturun.

1. Tuvalde seçili bir öğe yokken **Alanlar** bölmesindeki **Siparişler** bölümünden **ShipCountry** öğesini seçin veya tuval üzerindeki boş bir alana sürükleyin. Power BI Desktop verilerin ülke adları olduğunu algılar. Ardından otomatik olarak bir harita görselleştirmesi oluşturur; haritada siparişi olan her ülke için bir veri noktası bulunur.

1. Veri noktası boyutlarının her ülkenin sipariş miktarını yansıtmasını sağlamak için **LineTotal** alanını haritaya sürükleyin. Bunu **Görselleştirmeler** bölmesindeki **Boyut**'un altında yer alan **Veri alanlarını buraya sürükleyin** öğesine de sürükleyebilirsiniz. Harita üzerindeki dairelerin boyutları bu durumda her bir ülkenin sipariş tutarlarını USD cinsinden yansıtır.

   ![ShipCountry’ye Göre LineTotals harita görselleştirmesi](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/linetotals-by-shipcountry-map-visualization.png)

## <a name="interact-with-your-report-visuals-to-analyze-further"></a>Daha fazla analiz yapmak için rapor görsellerinizle etkileşimde bulunma

Power BI Desktop'ta, daha fazla eğilimi ortaya çıkarmak için birbirlerine çapraz vurgulama ve filtreleme uygulayan görsellerle etkileşimli çalışabilirsiniz. Daha fazla bilgi için bkz. [Power BI raporlarında filtreleme ve vurgulama](../create-reports/power-bi-reports-filters-and-highlighting.md).

Sorgularınız arasındaki ilişki nedeniyle, bir görselleştirmedeki etkileşimler sayfa üzerindeki diğer tüm görselleştirmeleri etkiler.

Harita görselleştirmesi üzerinde, merkezi **Kanada**’da bulunan daireyi seçin. Diğer iki görselleştirme Kanada’ya ait satır toplamlarını ve sipariş miktarlarını vurgulamak için filtre uygular.

![Kanada için filtrelenmiş satış verileri](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/sales-data-filtered-for-canada.png)

**Quantity by ProductName** grafiğinde, haritayı ve grafiğin ürün verilerini yansıtacak şekilde filtrelediği tarihi görmek için bir ürün seçin. **LineTotal by OrderDate** grafiğinde, haritayı ve grafiğin söz konusu tarihin verilerini gösterecek şekilde filtrelediği ürünü görmek için bir tarih seçin.

>[!TIP]
>Bir seçimi kaldırmak için yeniden seçin veya diğer görselleştirmelerden birini seçin.

## <a name="complete-the-sales-analysis-report"></a>Satış analizi raporunu tamamlama

Tamamlanmış raporunuz *Products.xlsx* Excel dosyasındaki ve Northwind OData akışındaki verileri, farklı ülkelerin sipariş bilgilerini, zaman çerçevelerini ve ürünlerini analiz etmeye yardımcı olan görsellerde birleştirir. Raporunuz hazır olduğunda [Power BI hizmetine yükleyerek](../create-reports/desktop-upload-desktop-files.md) diğer Power BI kullanıcılarıyla paylaşabilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

* [Power BI için Microsoft Learn](/learn/powerplatform/power-bi?WT.mc_id=powerbi_landingpage-docs-link)
* [Power BI Desktop videolarını izleyin](../fundamentals/desktop-videos.md)
* [Power BI Forumu'nu ziyaret edin](https://go.microsoft.com/fwlink/?LinkID=519326)
* [Power BI Blogu'nu okuyun](https://go.microsoft.com/fwlink/?LinkID=519327)