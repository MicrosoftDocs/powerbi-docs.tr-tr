---
title: Excel’de Power BI öne çıkan tablolarına erişme (önizleme)
description: Excel’de Veri Türleri Galerisinde Power BI veri kümelerindeki öne çıkan tablolardan veri bulabilirsiniz.
author: maggiesMSFT
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
ms.date: 07/24/2020
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 00fba391a6ad92f1e3edaf0e2af9691452724f6e
ms.sourcegitcommit: 65025ab7ae57e338bdbd94be795886e5affd45b4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87251760"
---
# <a name="access-power-bi-featured-tables-in-excel-preview"></a>Excel’de Power BI öne çıkan tablolarına erişme (önizleme)

Excel’de Veri Türleri Galerisinde Power BI veri kümelerindeki *öne çıkan tablolardan* veri bulabilirsiniz. Öne çıkan tablolar Excel sayfalarınıza kurumsal veriler eklemenizi kolaylaştırır. Burada Power BI verilerini Excel sayfalarına alma adımları verilmiştir.

- Power BI veri modelleyicisi [Power BI’da veri kümesini yükseltir veya onaylar](../connect-data/service-datasets-promote.md).
- Veri modelleyicisi veri kümesinde [öne çıkan tabloları belirler](service-create-excel-featured-tables.md) ve veri kümesini Power BI hizmetine kaydeder.
- Kuruluşun geri kalanı ilgili ve yenilenebilir veriler için Excel'de bu öne çıkan tablolara bağlanabilir. Excel bu tablolara *veri türleri* olarak başvurur ve bunları Veri Türleri Galerisinde listeler.

> [!NOTE]
> Excel’de, Power BI’dan erişebildiğiniz herhangi bir veri kümesindeki verileri de alabilirsiniz. **Veri** şeridinde **Veri Al** > **Power BI (Microsoft)** öğesini seçin.
> :::image type="content" source="media/service-excel-featured-tables/excel-get-data-power-bi.png" alt-text="Veri şeridinde Power BI’dan Veri Al seçeneğinin ekran görüntüsü.":::

## <a name="the-excel-data-types-gallery"></a>Excel Veri Türleri Galerisi
Power BI veri kümelerinde öne çıkan tablolar Excel'in **Veri** şeridinde *veri türleri* olarak **Veri Türleri** galerisinde görünür.

:::image type="content" source="media/service-excel-featured-tables/excel-data-ribbon.png" alt-text="Excel Veri şeridinde Veri Türleri galerisinin ekran görüntüsü.":::

Genişletildiğinde galeri **Hisse Senetleri** ve **Coğrafya** gibi genel veri türlerini ve sizin tarafınızdan kullanılabilecek ilk 10 **Kuruluş** veri türünü (Power BI veri kümelerinde öne çıkan tablolar) gösterir.

:::image type="content" source="media/service-excel-featured-tables/excel-data-types-gallery.png" alt-text="Excel Veri Türleri Galerisinin ekran görüntüsü.":::

## <a name="format-a-range-of-cells-as-a-table-optional"></a>Hücre aralığını tablo olarak biçimlendirme (isteğe bağlı)

 Başlamadan önce verilerinizi Excel tablosu olarak biçimlendirmeniz önerilir. Böylece bir satırda yaptığınız değişiklikler tablodaki diğer satırlara da uygulanır. 

1. Sütun üst bilgisi ekleyin. 
2. Ardından verilerinizde bir hücre seçin ve Ctrl + T tuşlarına basın. 
3. **Tablom üst bilgi satırı içeriyor** > **Tamam**’ı işaretleyin.

    :::image type="content" source="media/service-excel-featured-tables/excel-format-table.png" alt-text="Aralığı tabloya dönüştürmeyi gösteren ekran görüntüsü.":::

## <a name="search-for-power-bi-data-in-the-excel-data-types-gallery"></a>Excel Veri Türleri Galerisinde Power BI verilerini arama

Power BI öne çıkan tablosunda verileri aramak için, Excel sayfanızda öne çıkan tablodaki bir değerle eşleşen değerin yer aldığı bir hücre veya aralık seçin. **Kuruluş**’u seçin. Excel, erişiminiz olan tüm öne çıkan tablolarda eşleşme arar.

:::image type="content" source="media/service-excel-featured-tables/excel-table-organization.png" alt-text="Hücre veya hücre aralığı seçmenin ekran görüntüsü.":::
 
Aradığınız öne çıkan tabloyu biliyorsanız galeriden **Kuruluşunuzdan (önizleme)** öğesini seçin ve tabloyu belirleyin.

:::image type="content" source="media/service-excel-featured-tables/excel-organizational-data-table.png" alt-text="Excel Kuruluş Verileri, Sağlayıcılar veri türü tablosunun ekran görüntüsü.":::
 
Arama yaptığınızda Excel yüksek güvenilirlikle eşleşen satırları bulduğunda bu hücreler hemen söz konusu satırlara bağlanır. Bağlantılı öğe simgesi hücrelerin Power BI’daki satırlara bağlandığını gösterir.

:::image type="content" source="media/service-excel-featured-tables/excel-linked-card-icon.png" alt-text="Bağlantılı öğe simgesinin ekran görüntüsü.":::

Hücrede eşleşme olasılığı olan birden fazla satır varsa hücre bir soru işareti simgesi gösterir ve **Veri Seçici** bölmesi açılır. Aşağıdaki örnekte kullanıcı B2:B10 aralığını seçti ve bir Power BI öne çıkan tablosu arattı. B5 hücresi “Ma Maison” dışındaki tüm satırlar eşleşiyor. **Veri Seçici** iki olası eşleşmeyi gösteriyor.

:::image type="content" source="media/service-excel-featured-tables/excel-data-selector-pane.png" alt-text="Excel Veri Seçici bölmesinin ekran görüntüsü.":::
 
Kuruluş veri seçeneği birden çok öne çıkan tablodan satırları döndürebilir. Excel, olası satır eşleşmelerini geldikleri veri türüne göre gruplandırır. Excel veri türlerini en güçlü olası satır eşleşmesi temelinde sıralar. Eşleşen satırların veri türlerini daraltmak ve genişletmek için köşeli ayraç oklarını kullanın.

:::image type="content" source="media/service-excel-featured-tables/excel-data-selector-multiple.png" alt-text="Birden çok olasılık içeren Excel Veri Seçici bölmesinin ekran görüntüsü.":::
 
Her satır için satır adını seçerek satırda daha fazla ayrıntı görüntüleyin. Bunlar doğru satırı seçmenize yardımcı olur. Bunu bulduğunuzda, **Seç**’e basarak satırı Excel’deki hücreye bağlayın. 

:::image type="content" source="media/service-excel-featured-tables/excel-data-selector-details.png" alt-text="Veri Seçici ayrıntılarının ekran görüntüsü.":::
 
Hücrede **Kart** simgesi seçildiğinde öne çıkan tablodaki tüm alanların ve hesaplanan alanların verilerini içeren bir kart gösterilir. Kartın başlığında öne çıkan tablodaki satır etiketi alanını değeri yer alır.
 
:::image type="content" source="media/service-excel-featured-tables/excel-linked-item-details.png" alt-text="Bağlı öğe ayrıntılarının ekran görüntüsü.":::

Alanın değerini kılavuza eklemek için **Veri Ekle** simgesini seçin ve alan listesinden bir alan adı seçin.  

:::image type="content" source="media/service-excel-featured-tables/excel-select-field.png" alt-text="Alan adı seç öğesinin ekran görüntüsü.":::

Alan değeri veya değerleri bitişik hücrelere yerleştirilir. Hücre formülü bağlı hücreye ve hücre adına başvurur, bu nedenle verileri Excel işlevlerinde kullanabilirsiniz.

:::image type="content" source="media/service-excel-featured-tables/excel-cell-formula.png" alt-text="Excel hücre formülünün ekran görüntüsü.":::

## <a name="cell-formulas"></a>Hücre formülleri

Excel tablosunu kullanırken bağlı tablo sütununa başvurabilir ve `.` (nokta) başvurusunu kullanarak veri alanları ekleyebilirsiniz.

:::image type="content" source="media/service-excel-featured-tables/excel-dot-reference.png" alt-text="Excel nokta başvurusunun ekran görüntüsü.":::

Benzer şekilde bir hücreyi kullanırken hücreye başvurabilir ve alanları almak için `.` (nokta) başvurusu kullanabilirsiniz.

:::image type="content" source="media/service-excel-featured-tables/excel-cell-dot-reference.png" alt-text="Hücre nokta başvurusunun ekran görüntüsü.":::
 
## <a name="data-caching-and-refresh"></a>Verileri önbelleğe alma ve yenileme

Excel bir hücreyi Power BI öne çıkan tablosundaki bir satıra bağladığında, tüm alan değerlerini alır ve Excel dosyasına kaydeder. Dosyayı paylaştığınız herkes Power BI’dan veri istemeden alanlardan herhangi birine başvurabilir.  

Bağlantılı hücrelerdeki verileri yenilemek için **Veri** şeridindeki **Tümünü Yenile** düğmesini kullanın. 

:::image type="content" source="media/service-excel-featured-tables/excel-refresh-all.png" alt-text="Tümünü Yenile öğesinin ekran görüntüsü.":::
 
Ayrıca tek tek hücreleri de yenileyebilirsiniz. Hücreye sağ tıklayın ve **Veri Türleri** > **Yenile**’yi seçin.

## <a name="show-a-card-change-or-convert-to-text"></a>Kart gösterme, değiştirme veya metne dönüştürme

Bağlantılı hücreler sağ tıklatma menü seçeneklerine eklenir. Bir hücreye sağ tıklayın. Her zamanki seçeneklere ek olarak şunları görürsünüz:

- **Veri Türünü Göster Kartı**.
- **Yenile**.
- **Değiştir**.
- **Metne Dönüştür**.

:::image type="content" source="media/service-excel-featured-tables/excel-right-click-data-type.png" alt-text="Sağ tıklama, Metne Dönüştür ekran görüntüsü.":::
 
**Metne Dönüştür** seçeneği Power BI öne çıkan tablosundaki satıra yönelik bağlantıyı kaldırır. Burada önemi olan, hücredeki metnin bağlantılı hücrenin satır etiketi değeri olmasıdır. Hücreyi istemediğiniz bir satıra bağladıysanız, ilk hücre değerlerini geri yüklemek için Excel’de **Geri Al**’ı seçin.

## <a name="licensing"></a>Lisanslama

Excel Veri Türleri Galerisi ve Power BI öne çıkan tablolarına bağlantı deneyimleri yalnızca Excel E5 ve G5 müşterilerine yöneliktir. 

## <a name="security"></a>Güvenlik

Yalnızca Power BI’da izniniz olan veri kümelerindeki öne çıkan tabloları görürsünüz. Verileri yenilerken, satırları almak için Power BI’daki veri kümesine erişim izniniz olmalıdır. Veri kümesi üzerinde Oluşturma veya Yazma izni gerekir. Excel, satırın tamamı için döndürülen verileri önbelleğe alır. Excel dosyasını paylaştığınız herkes tüm bağlantılı hücrelerdeki alanların tümünü görebilir.

Power BI veri kümesinin satır düzeyi güvenliği varsa veya veri kümesine Microsoft Bilgi Koruması duyarlılık etiketi uygulandıysa, bu veri kümesindeki öne çıkan tablolar Excel Veri Türleri Galerisi’ne eklenmez. Bu ilk önizlemenin sınırlamalarından biridir.

## <a name="administrative-control"></a>Yönetim denetimi

Power BI yöneticileri, Excel Veri Türleri Galerisi’ndeki öne çıkan tabloları kuruluşta kimlerin kullanabileceğini denetleyebilir. Ayrıntılar için Yönetim portalında [Öne çıkan tablo ayarları](../admin/service-admin-portal.md#featured-tables-settings) konusuna bakın. 
 
### <a name="auditing"></a>Denetim

Yönetim denetim günlükleri öne çıkan tablolar için şu olayları gösterir:

- **AnalyzedByExternalApplication**: Yöneticilere, hangi kullanıcıların hangi öne çıkan tablolara eriştiği konusunda görünürlük sağlar.
- **UpdateFeaturedTables**: Yöneticilere, hangi kullanıcıların öne çıkan tabloları yayımladığı ve güncelleştirdiği konusunda görünürlük sağlar.

Denetim günlüğü olaylarının tam listesi için bkz. [Power BI’da kullanıcı etkinliklerini izleme](../admin/service-admin-auditing.md).

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

İlk önizlemenin sınırlamaları şunlardır:

- Tümleştirme Excel Insider Derlemelerinde kullanılabilir.
- Excel Veri Türleri Galerisi, Power BI Desktop ve Power BI hizmetinde uygun lisansa sahip olan kullanıcılara yönelik öne çıkan tabloları içerir. Power BI hizmeti desteği önizlemenin lansmanında sağlanmıyor olabilir ama eklenecektir.
- Aşağıdaki özelliklerin kullanıldığı Power BI veri kümelerindeki öne çıkan tablolar Excel’de gösterilmez: 

    - Satır düzeyi güvenlik veri kümeleri.
    - Microsoft Information Protection’ın etkinleştirildiği veri kümeleri.
    - DirectQuery veri kümeleri.
    - Canlı bağlantısı olan veri kümeleri.

- Excel yalnızca öne çıkan tablonun sütunlarında ve hesaplanan sütunlarında bulunan verileri gösterir. İlk önizlemede aşağıdakiler sağlanmaz:

    - Öne çıkan tabloda tanımlanan ölçüler.
    - İlgili tablolarda tanımlanan ölçüler ve ilişkilerden hesaplanan örtük ölçüler.

- Excel yalnızca yeni Power BI çalışma alanlarında depolanan öne çıkan tabloları (*veri türlerini*) görüntüler. Klasik çalışma alanlarında veya Çalışma Alanım’da depolanan öne çıkan tablolar Excel’de veri türleri olarak gösterilmez. Power BI'da [klasik çalışma alanlarını yeni çalışma alanlarına yükseltebilirsiniz](service-upgrade-workspaces.md).

Excel’deki Veri Türleri deneyimi arama işlevine benzer. Excel sayfası tarafından sağlanan bir hücre değerini alır ve Power BI öne çıkan tablolardaki eşleşen satırlar için arama yapar. Arama deneyiminin şöyle davranışları vardır:

- Arama yapmak için **Kuruluş Verileri** düğmesi kullanıldığında Excel yalnızca Sertifikalı veri kümelerindeki öne çıkan tablolarda arama yapar.
- Satır eşleşmesi öne çıkan tablodaki metin sütunlarına dayanır. Power BI Soru-Cevap özelliğiyle aynı dizini kullanır. Bu dizin İngilizce dilinde yapılan aramalar için iyileştirilmiştir. Başka dillerde yapılan aramaların sonucunda doğru eşleşmeler bulunamayabilir. Eşleşmede sayısal sütunlar dikkate alınmaz.
- Eşleşme tek tek arama terimlerinin Tam ve Ön Ek eşleşmelerine dayanır. Hücrenin değeri boşluklara ve sekme gibi boşluk karakterlerine göre bölünür. Sonra da her sözcük bir arama terimi olarak kabul edilir. Satırın metin alanı değerleri, Tam ve Ön Ek eşleşmeleri için her arama terimiyle karşılaştırılır. Satırın metin alanı arama terimiyle başlıyorsa Ön Ek eşleşmesi döndürülür. Örneğin hücre “Bölgesel Harita” ifadesini içeriyorsa, “Bölgesel” ve “Harita” ayrı arama terimleridir. 

    - Metin sütunlarının değeri “Bölgesel” veya “Harita” ile tam olarak eşleşen satırlar döndürülür. 
    - Metin sütununun değeri “Bölgesel” veya “Harita” ile başlayan satırlar döndürülür. 
    - Burada önemli olan, “Bölgesel” veya “Harita” terimini içeren ama bu terimlerle başlamayan satırlar döndürülmez.

- Power BI her hücre için en çok 100 satır önerisi döndürür.
- Öne çıkan tablonun ayarlanması veya güncelleştirilmesi XMLA uç noktasında desteklenmez
- Öne çıkan tabloları yayımlamak için veri modeli olan Excel dosyaları kullanılabilir. Verileri Power BI Desktop’a yükleyin ve ardından öne çıkan tabloyu yayımlayın.
- Öne çıkan tabloda Tablo Adı, Satır Etiketi veya Anahtar Sütunu’nun değiştirilmesi, tablodaki satırlara bağlı hücreleri olan Excel kullanıcılarını etkileyebilir. 
- Excel verilerin Power BI veri kümesinden ne zaman alındığını gösterir. Bu Power BI’da verilerin yenilendiği zaman veya veri kümesindeki en son veri noktası olmayabilir. Örneğin veri kümesinin Power BI’da bir hafta önce yenilendiğini ama yenileme yapıldığında temel kaynak verilerin bir haftalık olduğunu düşünün. Gerçek veriler 2 haftalık olacaktır ama Excel verilerin alınma zamanı olarak, verilerin Excel’e alındığı tarihi/saati gösterecektir.

## <a name="next-steps"></a>Sonraki adımlar

- [Power BI Desktop'ta öne çıkan tabloları ayarlama](service-create-excel-featured-tables.md)
- Excel belgelerinde [Power BI’dan Excel veri türlerini kullanma](https://support.office.com/article/use-excel-data-types-from-power-bi-preview-cd8938ce-f963-444d-b82a-7140848241e9) hakkında bilgi edinebilirsiniz.
- Sorularınız mı var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)

