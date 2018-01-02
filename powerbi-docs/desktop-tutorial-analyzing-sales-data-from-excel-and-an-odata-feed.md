---
title: "Eğitim: Power BI Desktop'ta bir Excel dosyasındaki ve OData akışındaki satış verilerini çözümleme"
description: "Eğitim: Bir Excel dosyasındaki ve OData akışındaki satış verilerini çözümleme"
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
ms.date: 10/12/2017
ms.author: davidi
ms.openlocfilehash: 03c5afae78e1688cadfdef9c0a96ca9f24247e12
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="tutorial-analyzing-sales-data-from-excel-and-an-odata-feed"></a>Eğitim: Bir Excel dosyasındaki ve OData akışındaki satış verilerini çözümleme
**Power BI Desktop**'ı kullanarak her türden farklı veri kaynağına bağlanabilir ve ardından, bunları ilgi çekici veri çözümlemeleri ve görselleştirmeler oluşturmayı kolay hale getiren yöntemlerle birleştirebilir ve şekillendirebilirsiniz. Bu eğitimde, iki veri kaynağından elde edilen verileri birleştirmeyi öğreneceksiniz. 

Veriler yaygın olarak birden çok veri kaynağına yayılmış halde (ürün bilgilerinin bulunduğu bir veritabanı ve satış bilgilerinin bulunduğu diğer bir veritabanı gibi) bulunur. Bu belgede öğreneceğiniz teknikler bir Excel çalışma kitabı ve OData akışına yönelik olsa da SQL Server sorguları, CSV dosyaları veya Power BI Desktop'taki başka bir veri kaynağı gibi diğer veri kaynakları için de uygulanabilir.

Bu eğitimde, Excel'deki (ürün bilgileri içerir) ve bir OData akışındaki (sipariş verileri içerir) verileri içeri aktaracaksınız. Dönüştürme ve birleştirme adımları uygulayacak, ayrıca etkileşimli görselleştirmeler içeren bir **Total Sales per Product and Year** raporu oluşturmak için her iki veri kaynağındaki verileri birleştireceksiniz. 

Raporun son hali aşağıdaki gibi görünecek:

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/18.png)

Bu eğitimdeki adımları uygulayabilmek için, şu şekilde indirebileceğiniz bir Products çalışma kitabına ihtiyacınız vardır**:**[ Buraya](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Products.xlsx)[tıklayarak](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Products.xlsx)[ ](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Products.xlsx)**[Products.xlsx](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Products.xlsx)**[ dosyasını indirin. ](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Products.xlsx)

**Farklı Kaydet** iletişim kutusunda, dosyayı **Products.xlsx** olarak adlandırın.

## <a name="task-1-get-product-data-from-an-excel-workbook"></a>1. Görev: Bir Excel çalışma kitabından ürün verileri alma
Bu görevde, Products.xlsx dosyasındaki ürünleri Power BI Desktop'a aktaracaksınız.

### <a name="step-1-connect-to-an-excel-workbook"></a>1. Adım: Bir Excel çalışma kitabına bağlanma
1. Power BI Desktop'ı başlatın.
2. Giriş şeridinde, **Veri Al**'ı seçin. Excel **En Yaygın** veri bağlantılarından biri olduğundan, doğrudan seçebilmeniz için **Veri Al** menüsünde yer alır.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_1.png)
3. Veri Al düğmesini doğrudan seçerseniz **Dosya \> Excel**'i seçip **Bağlan** seçeneğini de belirleyebilirsiniz.
4. **Dosya Aç** iletişim kutusunda, **Products.xlsx** dosyasını seçin.
5. **Gezgin** bölmesinde, **Products** tablosunu ve ardından **Düzenle**'yi seçin.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_2.png)

### <a name="step-2-remove-other-columns-to-only-display-columns-of-interest"></a>2. Adım: Yalnızca ilgili sütunları görüntülemek için diğer sütunları kaldırma
Bu adımda, **ProductID**, **ProductName**, **UnitsInStock** ve **QuantityPerUnit** dışındaki tüm sütunları kaldıracaksınız. Power BI Desktop'ta genellikle aynı görevi birkaç farklı yolla gerçekleştirebilirsiniz. Örneğin, şeritteki birçok düğmenin işlevi, bir sütunda veya hücrede sağ tıklama menüsü kullanılarak da gerçekleştirilebilir.

Power BI Desktop, veri bağlantılarınızı şekillendirdiğiniz ve dönüştürdüğünüz Sorgu Düzenleyicisi'ni içerir. Sorgu Düzenleyicisi, **Gezgin**'deki **Düzenle** seçeneğini belirlediğinizde otomatik olarak açılır. Sorgu Düzenleyicisi, Power BI Desktop'taki **Giriş** şeridinde bulunan **Sorguları Düzenle** seçeneği belirlenerek de açılabilir. Aşağıdaki adımlar Sorgu Düzenleyicisi'nde uygulanır.

1. Sorgu Düzenleyicisi'nde, **ProductID**, **ProductName**, **QuantityPerUnit** ve **UnitsInStock** sütunlarını seçin. (**CTRL+Tıklama** yöntemiyle birden fazla sütun seçin veya **SHIFT+Tıklama** yöntemiyle yan yana sütunları seçin.)
2. Şeritteki **Sütunları Kaldır** \> **Diğer Sütunları Kaldır** seçeneğini belirleyin veya bir sütun başlığına sağ tıklayıp **Diğer Sütunları Kaldır** seçeneğine tıklayın.

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/anlayzingsalesdata_removeothercolumns.png)

### <a name="step-3-change-the-data-type-of-the-unitsinstock-column"></a>3. Adım: UnitsInStock sütununun veri türünü değiştirme
Sorgu Düzenleyicisi verilere bağlandığında, en iyi veri türünü belirlemek için her bir alanı inceler. Excel çalışma kitabında, stoktaki ürünler her zaman tam sayı değeri alır. Bu nedenle, geçerli adımda **UnitsInStock** sütununun veri türünün Tam Sayı olduğunu doğrulayacaksınız.

1. **UnitsInStock** sütununu seçin.
2. **Giriş** şeridindeki **Veri Türü** açılan menüsüne ilişkin düğmeyi seçin.
3. Tam Sayı olarak belirlenmiş olmaması halinde, açılan menüden veri türü için **Tam Sayı** seçeneğini belirleyin. (**Veri Türü:** düğmesi geçerli seçimin veri türünü de görüntüler.)
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/anlayzingsalesdata_wholenumber.png)      

### <a name="power-bi-desktop-steps-created"></a>Oluşturulan Power BI Desktop adımları
Siz Sorgu Düzenleyicisi'nde sorgu etkinlikleri gerçekleştirdikçe sorgu adımları oluşturulur ve **Sorgu Ayarları** bölmesindeki **Uygulanan Adımlar** listesinde görüntülenir. Her bir sorgu adımına ilişkin bir formül ("M" dili olarak da bilinir) bulunur. "M" formül dili hakkında daha fazla bilgi için bkz. [Power BI formülleri hakkında bilgi edinin](https://support.office.com/Article/Learn-about-Power-Query-formulas-6bc50988-022b-4799-a709-f8aafdee2b2f).

| Görev | Sorgu adımı | Formül |
| --- | --- | --- |
| Excel çalışma kitabına bağlanma |Kaynak |Source{[Name="Products"]}[Data] |
| İlk satırları tablo sütun başlığı düzeyine yükseltme |FirstRowAsHeader |[Table.PromoteHeaders](https://support.office.com/Article/TablePromoteHeaders-b8eaeb95-042a-42e1-9164-6d3c646acadc "Table.PromoteHeaders") <br /> (Products) |
| Yalnızca ilgili sütunları görüntülemek için diğer sütunları kaldırma |Kaldırılan Diğer Sütunlar |[Table.SelectColumns](https://support.office.com/Article/TableSelectColumns-20bb9e28-9fd3-4cd2-a21b-97972c82ec22 "Table.SelectColumns")  <br />(FirstRowAsHeader,{"ProductID", "ProductName", "QuantityPerUnit", "UnitsInStock"}) |
| Veri türünü değiştirme |Değiştirilen Tür |Table.TransformColumnTypes(\#"Removed Other Columns",{{"UnitsInStock", Int64.Type}}) |

## <a name="task-2-import-order-data-from-an-odata-feed"></a>2. Görev: Bir OData akışındaki sipariş verilerini içeri aktarma
Bu görevde, sipariş verilerini içeri aktaracaksınız. Bu adım, bir satış sistemine bağlanmayı temsil eder. Aşağıdaki URL'de bulunan örnek Northwind OData akışındaki verileri Power BI Desktop'a aktaracaksınız. Bu URL'yi aşağıda bulunan adımlar için kopyalayıp yapıştırabilirsiniz: <http://services.odata.org/V3/Northwind/Northwind.svc/> 

### <a name="step-1-connect-to-an-odata-feed"></a>1. Adım: Bir OData akışına bağlanma
1. Sorgu Düzenleyicisi'ndeki **Giriş** şeridinde, **Veri Al** seçeneğini belirleyin.
2. **OData Akışı** veri kaynağına gidin.
3. **OData Akışı** iletişim kutusunda, Northwind OData akışına yönelik **URL**'yi yapıştırın.
4. **Tamam**'ı seçin.
5. **Gezgin** bölmesinde, **Orders** tablosunu ve ardından **Düzenle**'yi seçin.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/anlayzingsalesdata_odatafeed.png)

>[!NOTE]
>Bir tablo adına tıklayarak (onay kutusunu seçmeden) önizleme görüntüleyebilirsiniz.

### <a name="step-2-expand-the-orderdetails-table"></a>2. Adım: Order\_Details tablosunu genişletme
**Orders** tablosunda, her bir Siparişe dahil edilen belirli ürünleri içeren **Details** tablosuna yönelik bir başvuru bulunur. Birden çok tablo içeren veri kaynaklarına (ilişkisel veritabanı gibi) bağlanırken sorgunuzu oluşturmak için bu başvurulardan yararlanabilirsiniz. 

Bu adımda, **Order\_Details** tablosundaki **ProductID**, **UnitPrice** ve **Quantity** sütunlarını **Orders** tablosunda birleştirmek için **Orders** tablosuyla ilişkili **Order\_Details** tablosunu genişletirsiniz. Bu tablolardaki verilerin bir gösterimi aşağıda verilmiştir:

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/orderdetails.png)

**Genişletme** işlemi, ilişkili bir tablodaki sütunları bir konu tablosunda birleştirir. Sorgu çalıştırıldığında, ilişkili tablodaki (**Order\_Details**) satırlar, konu tablosundaki (**Orders**) satırlarda birleştirilir.

**Order\_Details** tablosunu genişletmenizin ardından, **Orders** tablosuna, iç içe geçmiş veya ilişkili tablodaki her bir satır için bir tane olmak üzere üç yeni sütun ve ek satırlar eklenir.

1. **Sorgu Görünümü**'nde, **Order\_Details** sütununa gidin.
2. **Order\_Details** sütununda, genişletme simgesini (![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/expand.png)) seçin.
3. **Genişlet** açılan menüsünde:
   1. Tüm sütunları temizlemek için **(Tüm Sütunları Seç)** seçeneğini belirleyin.
   2. **ProductID**, **UnitPrice** ve **Quantity** sütunlarını seçin.
   3. **Tamam**'a tıklayın.
      ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/7.png)

### <a name="step-3-remove-other-columns-to-only-display-columns-of-interest"></a>3. Adım: Yalnızca ilgili sütunları görüntülemek için diğer sütunları kaldırma
Bu adımda; **OrderDate, ShipCity**, **ShipCountry**, **Order\_Details.ProductID**, **Order\_Details.UnitPrice** ve **Order\_Details.Quantity** sütunları dışındaki tüm sütunları kaldıracaksınız. Bir önceki görevde **Diğer Sütunları Kaldır** seçeneğini kullanmıştınız. Bu görev için, seçili sütunları kaldıracaksınız.

1. **Sorgu Görünümü**'nde, a. ve b. adımlarını uygulayarak tüm sütunları seçin:
   1. İlk sütuna (**OrderID**) tıklayın.
   2. Son sütunu (**Shipper**) SHIFT tuşunu basılı tutarak tıklayın.
   3. Tüm sütunlar seçildiğine göre, CTRL tuşuna basıp tıklayarak şu sütunların seçimini kaldırın: **OrderDate**, **ShipCity**, **ShipCountry**, **Order\_Details.ProductID**, **Order\_Details.UnitPrice** ve **Order\_Details.Quantity**.
2. Yalnızca kaldırmak istediğimiz sütunlar seçili olduğuna göre, seçili herhangi bir sütunun başlığına sağ tıklayıp **Sütunları Kaldır** seçeneğine tıklayın.

### <a name="step-4-calculate-the-line-total-for-each-orderdetails-row"></a>4. Adım: Her bir Order\_Details satırı için satır toplamını hesaplama
Power BI Desktop, içeri aktardığınız sütunları temel alan hesaplamalar oluşturmanıza olanak sağlar. Böylece, bağlandığınız verileri zenginleştirebilirsiniz. Bu adımda, her bir **Order\_Details** satırı için satır toplamını hesaplamak üzere **Özel Sütun** oluşturacaksınız.

Her bir **Order\_Details** satırı için satır toplamını hesaplama:

1. **Sütun Ekle** şerit sekmesinde, **Ekle** **Özel Sütun** seçeneğine tıklayın.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_4.png)
2. **Özel Sütun Ekle** iletişim kutusundaki **Özel Sütun Formülü** metin kutusuna **[Order\_Details.UnitPrice] \* [Order\_Details.Quantity]** girin.
3. **Yeni sütun adı** metin kutusuna **LineTotal** girin.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/8.png)
4. **Tamam**'a tıklayın.

### <a name="step-5-set-the-datatype-of-the-linetotal-field"></a>5. Adım: LineTotal alanının veri türünü ayarlama
1. **LineTotal** sütununa sağ tıklayın.
2. **Türü Değiştir**'i seçin ve **Ondalık Sayı seçeneğini belirleyin.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/9.png)

### <a name="step-6-rename-and-reorder-columns-in-the-query"></a>6. Adım: Sorgudaki sütunları yeniden adlandırma ve yeniden sıralama
Bu adımda, sondaki sütunları yeniden adlandırarak ve bunların sıralarını değiştirerek, modeli, rapor oluşturma sırasında kolayca çalışılabilir hale getirme konusundaki son adımları uygulayacaksınız.

1. **Sorgu Düzenleyicisi**'nde, **LineTotal** sütununu sol taraftaki **ShipCountry** sütununun arkasına sürükleyin.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/10.png)
2. *Order\_Details* ön ekini **Order\_Details.ProductID**, **Order\_Details.UnitPrice** ve **Order\_Details.Quantity** sütunlarından kaldırın. Bunu gerçekleştirmek için her bir sütun başlığına çift tıklayın ve ardından söz konusu metni sütun adlarından silin.

### <a name="power-bi-desktop-steps-created"></a>Oluşturulan Power BI Desktop adımları
Siz Sorgu Düzenleyicisi'nde sorgu etkinlikleri gerçekleştirdikçe sorgu adımları oluşturulur ve **Sorgu Ayarları** bölmesindeki **Uygulanan Adımlar** listesinde görüntülenir. Her bir sorgu adımına ilişkin bir Power Query formülü ("M" dili olarak da bilinir) bulunur. Bu formül dili hakkında daha fazla bilgi için bkz. [Power BI formülleri hakkında bilgi edinin](https://support.office.com/Article/Learn-about-Power-Query-formulas-6bc50988-022b-4799-a709-f8aafdee2b2f "Learn about Power Query formulas (Power Query formülleri hakkında bilgi edinin)").

| Görev | Sorgu adımı | Formül |
| --- | --- | --- |
| Bir OData akışına bağlanma |Kaynak |Source{[Name="Orders"]}[Data] |
| Order\_Details tablosunu genişletme |Order\_Details Genişletildi |[Table.ExpandTableColumn](https://support.office.com/Article/TableExpandTableColumn-54903f25-75a2-4a44-a9a3-52a9d895ee98 "Table.ExpandTableColumn") <br /> (Orders, "Order\_Details", {"ProductID", "UnitPrice", "Quantity"}, {"Order\_Details.ProductID", "Order\_Details.UnitPrice", "Order\_Details.Quantity"}) |
| Yalnızca ilgili sütunları görüntülemek için diğer sütunları kaldırma |Kaldırılan Sütunlar |[Table.RemoveColumns](https://support.office.com/Article/TableRemoveColumns-6265190e-2f58-4300-85b8-df88fc1a67d3 "Table.RemoveColumns") <br />(\#"Expand Order\_Details",{"OrderID", "CustomerID", "EmployeeID", "RequiredDate", "ShippedDate", "ShipVia", "Freight", "ShipName", "ShipAddress", "ShipCity", "ShipRegion", "ShipPostalCode", "ShipCountry", "Customer", "Employee", "Shipper"}) |
| Her bir Order\_Details satırı için satır toplamını hesaplama |InsertedColumn |[Table.AddColumn](https://support.office.com/Article/TableAddColumn-6c64d0a5-9654-4d15-bfb6-9cc380aaf3c0 "Table.AddColumn") <br /> (RemovedColumns, "Custom", each [Order\_Details.UnitPrice] \* [Order\_Details.Quantity]) |

## <a name="task-3-combine-the-products-and-total-sales-queries"></a>Görev 3: Products ve Total Sales sorgularını birleştirme
Power BI Desktop, sorgular üzerinde raporlama yapmak için bunları birleştirmenizi gerektirmez. Bunun yerine, veri kümeleri arasında **İlişkiler** oluşturabilirsiniz. Bu ilişkiler, veri kümeleriniz için ortak olan herhangi bir sütun üzerinde oluşturulabilir. Daha fazla bilgi için bkz. [İlişki oluşturma ve ilişkileri yönetme](desktop-create-and-manage-relationships.md).

Bu eğitimde, ortak bir 'ProductID' alanına sahip Orders ve Products verilerine sahibiz. Bu nedenle, Power BI Desktop ile kullandığımız modelde bunlar arasında bir ilişkinin bulunduğundan emin olmamız gerekir. Bunun için Power BI Desktop'ta her bir tablodaki sütunların ilişkili olduğunu (aynı değerleri içeren sütunların bulunduğunu) belirtmeniz yeterlidir. Power BI Desktop, ilişki yönünü ve kardinalitesini sizin için belirler. Bazı durumlarda, ilişkileri otomatik olarak bile algılayabilir.

Bu görevde, Power BI Desktop'taki **Products** ve **Total Sales** sorguları arasında bir ilişkinin bulunduğunu doğrulayacaksınız.

### <a name="step-1-confirm-the-relationship-between-products-and-total-sales"></a>1. Adım: Products ve Total Sales arasındaki ilişkiyi doğrulama
1. Öncelikle, Sorgu Düzenleyicisi'nde oluşturduğumuz modeli Power BI Desktop'a yüklememiz gerekir. Sorgu Düzenleyicisi'ndeki **Giriş** şeridinde, **Kapat ve Yükle** seçeneğini belirleyin.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_4.png)
2. Power BI Desktop iki sorgudan elde edilen verileri yükler.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/11.png)      
3. Veriler yüklendikten sonra, **Giriş** şeridindeki **İlişkileri Yönet** seçeneğini belirleyin.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_5.png)
4. **Yeni…** düğmesini seçin
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_6.png)
5. İlişkiyi oluşturmaya çalıştığımızda zaten bir ilişkinin bulunduğunu görüyoruz. **İlişki Oluştur** iletişim kutusunda (gölgeli sütunlar ile) gösterildiği gibi, her bir sorgudaki **ProductsID** alanlarında zaten bir ilişki kurulmuş.
   
    ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/12.png)
6. **İptal** seçeneğini belirleyin ve ardından Power BI Desktop'taki **İlişki** görünümünü seçin.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_7.png)
7. Sorgular arasındaki ilişkinin görselleştirildiği aşağıdaki görüntüyle karşılaşırız.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_8.png)
8. Sorguları bağlayan çizgideki oka çift tıkladığınızda, **İlişkiyi Düzenle** iletişim kutusu görüntülenir.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/t_excelodata_9.png)
9. Herhangi bir değişiklik gerekmediğinden, **İptal** seçeneğini belirleyerek, **İlişkiyi Düzenle** iletişim kutusunu kapatabiliriz.

## <a name="task-4-build-visuals-using-your-data"></a>4. Görev: Verilerinizi kullanarak görsel oluşturma
Power BI Desktop, verilerinizden öngörüler elde etmek için çeşitli görselleştirmeler oluşturmanıza olanak sağlar. Birden çok sayfa içeren raporlar oluşturabilir ve her bir sayfada birden çok görsel olmasını sağlayabilirsiniz. Verilerinizi çözümlemenize ve anlamanıza yardımcı olmaları için görselleştirmelerinizle etkileşime geçebilirsiniz. Raporları düzenleme hakkında daha fazla bilgi için bkz. [Bir raporu düzenleme](service-interact-with-a-report-in-editing-view.md).

Bu görevde, daha önce yüklenen verileri temel alan bir rapor oluşturacaksınız. Görselleştirmeleri oluşturmak üzere kullanacağınız sütunları seçmek için Alanlar bölmesini kullanırsınız.

### <a name="step-1-create-charts-showing-units-in-stock-by-product-and-total-sales-by-year"></a>1. Adım: Product tarafından düzenlenen Units in Stock ve Year tarafından düzenlenen Total Sales'ı gösteren grafikler oluşturma
Alanlar bölmesindeki (Alanlar bölmesi ekranın sağ tarafında yer alır) **UnitsInStock** alanını tuvaldeki boş bir alana sürükleyin. Bir Tablo görselleştirmesi oluşturulur. Ardından, ProductName alanını, Görsel Öğeler bölmesinin orta kısmının altında bulunan Eksen kutusuna sürükleyin. Ardından, görselleştirmenin sağ üst köşesindeki üç nokta simgesini kullanarak **Sıralama Ölçütü: \> UnitsInStock** seçeneğini belirleriz.

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/14.png)

**OrderDate**'i tuvaldeki ilk grafiğin altına, LineTotal'ı (Alanlar bölmesinden) ise görselin üzerine sürükleyin ve ardından Çizgi Grafik seçeneğini belirleyin. Aşağıdaki görselleştirme oluşturulur.

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/15.png)

 Ardından, **ShipCountry** alanını tuvalin sağ üst tarafındaki bir alana sürükleyin. Coğrafi bir alan seçtiğiniz için otomatik olarak bir harita oluşturulur. Şimdi de **LineTotal**'ı **Değerler** alanına sürükleyin; her bir ülkeye yönelik olarak haritada bulunan daireler artık söz konusu ülkeye gönderilen siparişlere ilişkin **LineTotal**'a göre boyutlandırılır.

![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/17.png)

### <a name="step-2-interact-with-your-report-visuals-to-analyze-further"></a>2. Adım: Daha fazla çözümleme yapmak için rapor görsellerinizle etkileşime geçme
Power BI Desktop, daha fazla eğilimi ortaya çıkarmak için birbirlerine çapraz vurgulama ve filtreleme uygulayan görsellerle etkileşime geçmenize olanak sağlar. Daha fazla ayrıntı için bkz. [Raporlarda Filtreleme ve Vurgulama](power-bi-reports-filters-and-highlighting.md)

1. **Canad****a**'nın ortasında bulunan açık mavi daireye tıklayın. Diğer görsellerin yalnızca Kanada için Stoku (**ShipCountry**) ve Toplam Siparişleri (**LineTotal**) gösterecek şekilde nasıl filtrelendiğine dikkat edin.
   
   ![](media/desktop-tutorial-analyzing-sales-data-from-excel-and-an-odata-feed/18.png)

## <a name="complete-sales-analysis-report"></a>Tamamlanmış Satış Analizi Raporu
Bu adımların tümünü uyguladıktan sonra, Products.xlsx dosyasındaki ve Northwind OData akışındaki verileri birleştiren bir Satış Raporu elde edersiniz. Rapor, farklı ülkelerden elde edilen satış bilgilerinin çözümlenmesine yardımcı olan görseller görüntüler. Bu eğitime yönelik tamamlanmış bir Power BI Desktop dosyasını [buradan](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Analyzing_Sales_Data.pbix) indirebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar
* [Diğer Power BI Desktop eğitimlerini okuyun](http://go.microsoft.com/fwlink/?LinkID=521937)
* [Power BI Desktop videolarını izleyin](http://go.microsoft.com/fwlink/?LinkID=519322)
* [Power BI Forumu'nu ziyaret edin](http://go.microsoft.com/fwlink/?LinkID=519326)
* [Power BI Blogu'nu okuyun](http://go.microsoft.com/fwlink/?LinkID=519327)



