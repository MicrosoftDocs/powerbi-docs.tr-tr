---
title: Excel’de Power BI öne çıkan tablolarına erişme
description: Excel’de Kuruluş Veri Türleri Galerisinde Power BI veri kümelerindeki öne çıkan tablolardan veri bulabilirsiniz.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: pbi-collaborate-share
ms.topic: how-to
ms.date: 12/07/2020
LocalizationGroup: Share your work
ms.openlocfilehash: b5f84f67231393dfed78bd9f90142fbd1b4f6c91
ms.sourcegitcommit: 30d0668434283c633bda9ae03bc2aca75401ab94
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/09/2020
ms.locfileid: "96907051"
---
# <a name="access-power-bi-featured-tables-in-excel-organization-data-types"></a>Excel kuruluş veri türlerindeki Power BI öne çıkan tablolarına erişme

*Öne çıkan tablolar*, Excel’deki verilerinizi Power BI’daki verilerle bağlantılandırmanın bir yoludur. Bu, Excel sayfalarınıza kurumsal veriler eklemenizi kolaylaştırır. Excel’de Veri Türleri Galerisinde Power BI veri kümelerindeki öne çıkan tablolardan veri bulabilirsiniz. Bu makalede nasıl olduğu açıklanmaktadır.

Power BI’da veri kümeleri oluşturuyor musunuz? [Power BI Desktop’ta öne çıkan tabloları ayarlama](service-create-excel-featured-tables.md) hakkında bilgi edinin.

> [!NOTE]
> Excel’de, Power BI’dan erişebildiğiniz herhangi bir Power BI veri kümesindeki verileri de analiz edebilirsiniz. Ayrıntılar için “Power BI için Excel’de analiz etme” başlıklı makalede [Excel’den Power BI veri kümelerine erişmenin diğer yolları](service-analyze-in-excel.md#other-ways-to-access-power-bi-datasets-from-excel) bölümüne bakın.
> 

## <a name="the-excel-data-types-gallery"></a>Excel Veri Türleri Galerisi
Power BI veri kümelerinde öne çıkan tablolar Excel'in **Veri** şeridinde *veri türleri* olarak **Veri Türleri** galerisinde görünür.

:::image type="content" source="media/service-excel-featured-tables/excel-data-ribbon.png" alt-text="Excel Veri şeridinde Veri Türleri galerisinin ekran görüntüsü.":::

Genişletildiğinde galeri **Hisse Senetleri** ve **Coğrafya** gibi genel veri türlerini ve sizin tarafınızdan kullanılabilecek ilk 10 **Kuruluş** veri türünü (Power BI veri kümelerinde öne çıkan tablolar) gösterir.

:::image type="content" source="media/service-excel-featured-tables/excel-data-types-gallery.png" alt-text="Excel Veri Türleri Galerisinin ekran görüntüsü.":::

## <a name="search-for-power-bi-data-in-the-data-types-gallery"></a>Veri Türleri Galerisinde Power BI verilerini arama

Power BI öne çıkan tablosunda verileri aramak için, Excel sayfanızda öne çıkan tablodaki bir değerle eşleşen değerin yer aldığı bir hücre veya aralık seçin. Veri türleri galerisinin yanındaki **Diğer** okunu seçin.

:::image type="content" source="media/service-excel-featured-tables/excel-data-types-more.png" alt-text="Excel Veri Türleri Galerisindeki Diğer simgesinin ekran görüntüsü.":::

Aradığınız tabloyu görürseniz seçin. Aksi takdirde, **Kuruluşunuzdaki diğerleri**’ni seçin. Excel, erişim sahibi olduğunuz tüm öne çıkan tabloları bu bölmede görüntüler.

:::image type="content" source="media/service-excel-featured-tables/excel-more-your-organization.png" alt-text="Kuruluşunuzdan (önizleme) seçeneğini belirleme ekran görüntüsü.":::
 
Excel, erişim sahibi olduğunuz tüm öne çıkan tabloları görüntüler. **Veri Seçicisi** bölmesinde **Filtre** kutusuna giriş yaparak seçeneklerinizi daraltın. Kullanmak istediğiniz tabloyu seçin.

:::image type="content" source="media/service-excel-featured-tables/excel-data-selector-store.png" alt-text="Excel Kuruluş Verileri, Sağlayıcılar veri türü tablosunun ekran görüntüsü.":::
 
Excel yüksek güvenilirlikle eşleşen satırları bulduğunda bu hücreler hemen söz konusu satırlara bağlanır. Bağlantılı öğe simgesi hücrelerin Power BI’daki satırlara bağlandığını gösterir.

:::image type="content" source="media/service-excel-featured-tables/excel-linked-card-icon.png" alt-text="Bağlantılı öğe simgesinin ekran görüntüsü.":::

Hücrede eşleşme olasılığı olan birden fazla satır varsa hücre bir soru işareti simgesi gösterir ve **Veri Seçici** bölmesi açılır. Aşağıdaki örnekte, B3:B9 aralığını seçtik ve sonra **Depo** adlı Power BI öne çıkan tablosunu seçtik. B9 hücresi “508 - Pasadena Lindseys” dışındaki tüm satırlar eşleşiyor. **Veri seçicisi**, iki olası eşleşmeyi, iki farklı tabloda aynı değeri gösterir.

:::image type="content" source="media/service-excel-featured-tables/excel-question-mark-featured-table.png" alt-text="Excel Veri Seçici bölmesinin ekran görüntüsü.":::
 
Kuruluş veri seçeneği birden çok öne çıkan tablodan satırları döndürebilir. Excel, olası satır eşleşmelerini geldikleri veri türüne göre gruplandırır. Excel veri türlerini en güçlü olası satır eşleşmesi temelinde sıralar. Eşleşen satırların veri türlerini daraltmak ve genişletmek için köşeli ayraç oklarını kullanın.

:::image type="content" source="media/service-excel-featured-tables/excel-data-selector-multiple.png" alt-text="Birden çok olasılık içeren Excel Veri Seçici bölmesinin ekran görüntüsü.":::
 
Her öneri için, **Veri Seçici** bölmesindeki satır adını seçerek satırda daha fazla ayrıntı görüntüleyin. Bunlar doğru satırı seçmenize yardımcı olur. Bunu bulduğunuzda, **Seç**’e basarak satırı Excel’deki hücreye bağlayın. 

:::image type="content" source="media/service-excel-featured-tables/excel-data-selector-details.png" alt-text="Veri Seçici ayrıntılarının ekran görüntüsü.":::

## <a name="explore-related-data"></a>İlgili verileri keşfetme

Excel sayfanızdaki değerler ile Power BI öne çıkan tablosundaki veriler arasında bağlantı oluşturduğunuza göre bu verileri keşfedebilirsiniz. Excel raporlamanızı geliştirmek için verileri kullanın.

### <a name="view-related-data-in-a-card"></a>İlgili verileri kartta görüntüleme 
 
Hücrede **Kart** simgesini seçerek öne çıkan tablodaki tüm alanların ve hesaplanan alanların verilerini içeren bir kart gösterin. Kartın başlığında öne çıkan tablodaki satır etiketi alanını değeri yer alır.
 
:::image type="content" source="media/service-excel-featured-tables/excel-linked-item-details.png" alt-text="Bağlı öğe ayrıntılarının ekran görüntüsü.":::

### <a name="insert-related-data-from-power-bi"></a>Power BI’dan ilgili verileri ekleme 

Alanın değerini kılavuza eklemek için **Veri Ekle** simgesini seçin ve alan listesinden bir alan adı seçin.  

:::image type="content" source="media/service-excel-featured-tables/excel-select-field.png" alt-text="Alan adı seç öğesinin ekran görüntüsü.":::

Alan değeri veya değerleri bitişik hücrelere yerleştirilir. Hücre formülü bağlı hücreye ve hücre adına başvurur, bu nedenle verileri Excel işlevlerinde kullanabilirsiniz.

:::image type="content" source="media/service-excel-featured-tables/excel-cell-formula.png" alt-text="Excel hücre formülünün ekran görüntüsü.":::

### <a name="use-cell-formulas"></a>Hücre formülleri kullanma

Excel tablosunda, bağlı tablo sütununa başvurabilir ve `.` (nokta) başvurusunu kullanarak veri alanları ekleyebilirsiniz.

:::image type="content" source="media/service-excel-featured-tables/excel-dot-reference.png" alt-text="Excel nokta başvurusunun ekran görüntüsü.":::

Benzer şekilde bir hücrede, hücreye başvurabilir ve alanları almak için `.` (nokta) başvurusunu kullanabilirsiniz.

:::image type="content" source="media/service-excel-featured-tables/excel-cell-dot-reference.png" alt-text="Hücre nokta başvurusunun ekran görüntüsü.":::

### <a name="show-a-card-change-or-convert-to-text"></a>Kart gösterme, değiştirme veya metne dönüştürme

Bağlantılı hücreler sağ tıklatma menü seçeneklerine eklenir. Bir hücreye sağ tıklayın. Her zamanki seçeneklere ek olarak şunları görürsünüz:

- **Veri Türünü Göster Kartı**.
- **Veri Türü** > **Metne Dönüştür**.
- **Veri Türü** > **Değiştir**.
- **Yenile**.

:::image type="content" source="media/service-excel-featured-tables/excel-right-click-data-type.png" alt-text="Sağ tıklama, Metne Dönüştür ekran görüntüsü.":::
 
**Metne Dönüştür** seçeneği Power BI öne çıkan tablosundaki satıra yönelik bağlantıyı kaldırır. Burada önemi olan, hücredeki metnin bağlantılı hücrenin satır etiketi değeri olmasıdır. Hücreyi istemediğiniz bir satıra bağladıysanız, ilk hücre değerlerini geri yüklemek için Excel’de **Geri Al**’ı seçin.
 
## <a name="data-caching-and-refresh"></a>Verileri önbelleğe alma ve yenileme

Excel bir hücreyi Power BI öne çıkan tablosundaki bir satıra bağladığında, tüm alan değerlerini alır ve Excel dosyasına kaydeder. Dosyayı paylaştığınız herkes Power BI’dan veri istemeden alanlardan herhangi birine başvurabilir.  

Bağlantılı hücrelerdeki verileri yenilemek için **Veri** şeridindeki **Tümünü Yenile** düğmesini kullanın. 

:::image type="content" source="media/service-excel-featured-tables/excel-refresh-all.png" alt-text="Tümünü Yenile öğesinin ekran görüntüsü.":::
 
Ayrıca tek tek hücreleri de yenileyebilirsiniz. Hücreye sağ tıklayın ve **Veri Türleri** > **Yenile**’yi seçin.

## <a name="licensing"></a>Lisanslama

Excel Veri Türleri Galerisi ve Power BI öne çıkan tablolarına bağlantı deneyimleri, Power BI Pro hizmet planına sahip Excel aboneleri tarafından kullanılabilir. 

## <a name="security"></a>Güvenlik

Yalnızca Power BI’da izniniz olan veri kümelerindeki öne çıkan tabloları görürsünüz. Verileri yenilerken, satırları almak için Power BI’daki veri kümesine erişim izniniz olmalıdır. Power BI’da [Veri kümesi üzerinde Oluşturma veya Yazma izni](../connect-data/service-datasets-build-permissions.md) gerekir.
 
Excel, satırın tamamı için döndürülen verileri önbelleğe alır. Excel dosyasını paylaştığınız herkes tüm bağlantılı hücrelerdeki alanların tümünü görebilir.

## <a name="administrative-control"></a>Yönetim denetimi

Power BI yöneticileri, Excel Veri Türleri Galerisi’ndeki öne çıkan tabloları kuruluşta kimlerin kullanabileceğini denetleyebilir. Ayrıntılar için Yönetici portalında [öne çıkan tablolar bağlantılarına izin verme](../admin/service-admin-portal.md#allow-connections-to-featured-tables) konusuna bakın. 
 
### <a name="auditing"></a>Denetim

Yönetim denetim günlükleri öne çıkan tablolar için şu olayları gösterir:

- **AnalyzedByExternalApplication**: Yöneticilere, hangi kullanıcıların hangi öne çıkan tablolara eriştiği konusunda görünürlük sağlar.
- **UpdateFeaturedTables**: Yöneticilere, hangi kullanıcıların öne çıkan tabloları yayımladığı ve güncelleştirdiği konusunda görünürlük sağlar.

Denetim günlüğü olaylarının tam listesi için bkz. [Power BI’da kullanıcı etkinliklerini izleme](../admin/service-admin-auditing.md).

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

Geçerli sınırlamalar şunlardır:

- Tümleştirme geçerli kanaldaki Excel ile kullanılabilir.
- Aşağıdaki özelliklerin kullanıldığı Power BI veri kümelerindeki öne çıkan tablolar Excel’de gösterilmez: 

    - DirectQuery veri kümeleri.
    - Canlı bağlantısı olan veri kümeleri.

- Excel yalnızca öne çıkan tablonun sütunlarında, hesaplanan sütunlarında ve tanımlanmış ölçülerde bulunan verileri gösterir. Aşağıdakiler sağlanmaz:
   
    - İlgili tablolarda tanımlanmış ölçüler.
    - İlişkilerden hesaplanan örtülü ölçüler.

- Excel yalnızca yeni Power BI çalışma alanlarında depolanan öne çıkan tabloları (*veri türlerini*) görüntüler. Klasik çalışma alanlarında depolanan öne çıkan tablolar Excel’de veri türleri olarak gösterilmez. Power BI'da [klasik çalışma alanlarını yeni çalışma alanlarına yükseltebilirsiniz](service-upgrade-workspaces.md).

Excel’deki Veri Türleri deneyimi arama işlevine benzer. Excel sayfası tarafından sağlanan bir hücre değerini alır ve Power BI öne çıkan tablolardaki eşleşen satırlar için arama yapar. Arama deneyiminin şöyle davranışları vardır:

- Satır eşleşmesi öne çıkan tablodaki metin sütunlarına dayanır. Power BI Soru-Cevap özelliğiyle aynı dizini kullanır. Bu dizin İngilizce dilinde yapılan aramalar için iyileştirilmiştir. Başka dillerde yapılan aramaların sonucunda doğru eşleşmeler bulunamayabilir. 
- Eşleşmede çoğu sayısal sütun dikkate alınmaz. Satır Etiketi veya Anahtar Sütunu sayısal ise eşleşme için dahil edilir.
- Eşleşme tek tek arama terimlerinin Tam ve Ön Ek eşleşmelerine dayanır. Hücrenin değeri boşluklara ve sekme gibi boşluk karakterlerine göre bölünür. Sonra da her sözcük bir arama terimi olarak kabul edilir. Satırın metin alanı değerleri, Tam ve Ön Ek eşleşmeleri için her arama terimiyle karşılaştırılır. Satırın metin alanı arama terimiyle başlıyorsa Ön Ek eşleşmesi döndürülür. Örneğin hücre “Bölgesel Harita” ifadesini içeriyorsa, “Bölgesel” ve “Harita” ayrı arama terimleridir. 

    - Metin sütunlarının değeri “Bölgesel” veya “Harita” ile tam olarak eşleşen satırlar döndürülür. 
    - Metin sütunlarının değeri “Bölgesel” veya “Harita” ile başlayan satırlar döndürülür. 
    - Burada önemli olan, “Bölgesel” veya “Harita” terimini içeren ama bu terimlerle başlamayan satırlar döndürülmez.

- Power BI her hücre için en çok 100 satır önerisi döndürür.
- Bazı simgeler desteklenmez.
- Öne çıkan tablonun ayarlanması veya güncelleştirilmesi XMLA uç noktasında desteklenmez
- Öne çıkan tabloları yayımlamak için veri modeli olan Excel dosyaları kullanılabilir. Verileri Power BI Desktop’a yükleyin ve ardından öne çıkan tabloyu yayımlayın.
- Öne çıkan tabloda Tablo Adı, Satır Etiketi veya Anahtar Sütunu’nun değiştirilmesi, tablodaki satırlara bağlı hücreleri olan Excel kullanıcılarını etkileyebilir. 
- Excel verilerin Power BI veri kümesinden ne zaman alındığını gösterir. Bu, Power BI’da verilerin yenilendiği zaman veya veri kümesindeki en son veri noktası olmayabilir. Örneğin veri kümesinin Power BI’da bir hafta önce yenilendiğini ama yenileme yapıldığında temel kaynak verilerin bir haftalık olduğunu düşünün. Gerçek veriler iki haftalık olacaktır ama Excel verilerin alınma zamanı olarak, verilerin Excel’e alındığı tarihi/saati gösterecektir. 

## <a name="next-steps"></a>Sonraki adımlar

- [Power BI Desktop'ta öne çıkan tabloları ayarlama](service-create-excel-featured-tables.md)
- Excel belgelerinde [Power BI’dan Excel veri türlerini kullanma](https://support.office.com/article/use-excel-data-types-from-power-bi-preview-cd8938ce-f963-444d-b82a-7140848241e9) hakkında bilgi edinebilirsiniz.
- Sorularınız mı var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)

