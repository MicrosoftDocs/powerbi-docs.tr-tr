---
title: Excel’de Power BI öne çıkan tablolarına erişme (önizleme)
description: Excel’de Veri Türleri Galerisinde Power BI veri kümelerindeki öne çıkan tablolardan veri bulabilirsiniz.
author: maggiesMSFT
ms.reviewer: lukaszp
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/20/2020
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: d8ef72f25509fe41c983e7385095fdad5985f5de
ms.sourcegitcommit: 5e5a7e15cdd55f71b0806016ff91256a398704c1
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/22/2020
ms.locfileid: "83793524"
---
# <a name="access-power-bi-featured-tables-in-excel-preview"></a>Excel’de Power BI öne çıkan tablolarına erişme (önizleme)

Excel’de Veri Türleri Galerisinde Power BI veri kümelerindeki öne çıkan tablolardan veri bulabilirsiniz. Öne çıkan tablolar Excel sayfalarınıza kurumsal veriler eklemenizi kolaylaştırır. Power BI’ın onaylı ve tanıtılan veri kümesi özelliklerini kullanarak, kuruluşlar daha fazla kullanıcının ilgili ve yenilenebilir verileri bularak ve kullanarak daha iyi kararlar almasına olanak tanır. Excel belgelerinde [Power BI’dan Excel veri türlerini kullanma](https://support.office.com/article/use-excel-data-types-from-power-bi-preview-cd8938ce-f963-444d-b82a-7140848241e9) hakkında daha fazla bilgi edinebilirsiniz.

Veri Türleri Galerisi yalnızca Power BI veri kümelerinde modelleyicinin seçtiği öne çıkan tabloları gösterir. Ayrıca Power BI’da erişebileceğiniz tüm veri kümelerine Excel’de göz atabilirsiniz. Excel’de **Veri** şeridindeki **Veri Al**’ın altında **Power BI Veri Kümeleri**’ni seçin.

## <a name="access-power-bi-data-through-the-excel-data-types-gallery"></a>Excel Veri Türleri Galerisi’nden Power BI verilerine erişme
Power BI veri kümelerindeki öne çıkan tablolar Veri şeridindeki Excel Veri Türleri galerisinde görüntülenir.

:::image type="content" source="media/service-excel-featured-tables/excel-data-ribbon.png" alt-text="Excel Veri şeridi":::

Galeri genişletildiğinde en çok kullanılan veri kümelerini gösterir.

:::image type="content" source="media/service-excel-featured-tables/excel-data-types-gallery.png" alt-text="Excel Veri Türleri Galerisi":::
 
Power BI öne çıkan tablosundaki verileri aramak için Excel sayfanızda bir hücre veya aralık seçin.

:::image type="content" source="media/service-excel-featured-tables/excel-select-cell.png" alt-text="Hücre seçin":::
 
Erişiminiz olan sertifikalı veri kümelerindeki öne çıkan tablolarda yer alan verileri aramak için galeride **Kuruluş verileri** seçeneğini belirtin.

:::image type="content" source="media/service-excel-featured-tables/excel-organizational-data.png" alt-text="Excel Kuruluş Verileri":::
 
Hangi tür veri aradığınızı biliyorsanız veya Kuruluş verileri seçeneğini kullanarak eşleşen satırları bulamazsanız belirli bir veri türünü seçin.

:::image type="content" source="media/service-excel-featured-tables/excel-select-data-type.png" alt-text="Veri türünü seçin":::
 
Arama yaptığınızda yüksek güvenilirlikle eşleşen bir satır bulunursa, hücre hemen söz konusu satıra bağlanır. Bağlantılı öğe simgesi hücrenin Power BI’daki satıra bağlandığını gösterir.

:::image type="content" source="media/service-excel-featured-tables/excel-linked-item-icon.png" alt-text="Bağlantılı öğe simgesi":::

Hücrenin birden çok olası satır eşleşmesi varsa bir veri seçici bölmesi gösterilir. Hücrede soru işareti gösterilir; bu soru işareti söz konusu satırın veri seçici bölmesini açar. Burada kullanıcının A2:A7 aralığını seçtikten ve Power BI öne çıkan tablosunda arama yaptıktan sonrası gösteren bir örnek vardır.

:::image type="content" source="media/service-excel-featured-tables/excel-multiple-matches.png" alt-text="Birden çok olası satır eşleşmesi":::

**Veri Seçicisi** bölmesinde olası satır eşleşmeleri gösterilir.

:::image type="content" source="media/service-excel-featured-tables/excel-data-selector-pane.png" alt-text="Excel Veri Seçicisi bölmesi":::
 
Kuruluş verileri seçeneği birden çok veri türünde satırlar döndürebilir. Excel, olası satır eşleşmelerini geldikleri veri türüne göre gruplandırır. Excel veri türlerini en güçlü olası satır eşleşmesi temelinde sıralar. Eşleşen satırların veri türlerini daraltmak ve genişletmek için köşeli ayraç oklarını kullanın.

:::image type="content" source="media/service-excel-featured-tables/excel-data-selector-multiple.png" alt-text="Excel Veri Seçicisi bölmesi":::
 
Her satır için satır adını seçerek satırda daha fazla ayrıntı görüntüleyin. Bunlar doğru satırı seçmenize yardımcı olur. Satırı bulduğunuzda **Seç**’e basarak satırı Excel’deki hücreye bağlayın. 

:::image type="content" source="media/service-excel-featured-tables/excel-data-selector-select.png" alt-text="Veri Seçici ayrıntıları":::
 
Satır seçildiğinde hücre satıra bağlanır ve değeri Power BI öne çıkan tablosundaki **Satır Etiketi** alanının değerine bağlanır. 

:::image type="content" source="media/service-excel-featured-tables/excel-linked-item-icon.png" alt-text="Excel bağlantılı öğesi":::
 
**Bağlı Hücre** simgesi seçildiğinde öne çıkan tablodaki tüm alanların ve hesaplanan alanların verilerini içeren bir kart gösterilir. Kartın başlığında öne çıkan tablodaki satır etiketi alanını değeri yer alır.
 
:::image type="content" source="media/service-excel-featured-tables/excel-linked-item-details.png" alt-text="Bağlantılı öğe ayrıntıları":::

Alan değerlerini kılavuza eklemek için **Veri Ekle** simgesini seçin.

:::image type="content" source="media/service-excel-featured-tables/excel-insert-data.png" alt-text="Veri ekleme"::: 

Alanın değerini kılavuza eklemek için alan listesinden bir alan adı seçin.  

:::image type="content" source="media/service-excel-featured-tables/excel-select-field.png" alt-text="Alan adı seçin":::

Alan değeri bitişik hücreye yerleştirilir. Hücre formülü bağlı hücreye ve hücre adına başvurur, bu nedenle verileri Excel işlevlerinde kullanabilirsiniz.

:::image type="content" source="media/service-excel-featured-tables/excel-cell-formula.png" alt-text="Excel hücre formülü":::
 
Verilerinizi Excel tablosu olarak biçimlendirdiğinizde, alanların eklenmesi tabloyu genişletir ve hücre başlığını alan adıyla eşleşecek şekilde ayarlar. Aynı veri türlerine bağlı olan satırlar da bunlara karşılık gelen değerlerle doldurulur.

:::image type="content" source="media/service-excel-featured-tables/excel-field-column-name.png" alt-text="Alan, sütun adıdır"::: 

## <a name="cell-formulas"></a>Hücre formülleri

Excel tablosunu kullanırken bağlı tablo sütununa başvurabilir ve `.` (nokta) başvurusunu kullanarak veri alanları ekleyebilirsiniz.

:::image type="content" source="media/service-excel-featured-tables/excel-dot-reference.png" alt-text="Excel nokta başvurusu":::

Benzer şekilde bir hücreyi kullanırken hücreye başvurabilir ve alanları almak için `.` (nokta) başvurusu kullanabilirsiniz.

:::image type="content" source="media/service-excel-featured-tables/excel-cell-dot-reference.png" alt-text="Hücre nokta başvurusu":::
 
## <a name="data-caching-and-refresh"></a>Verileri önbelleğe alma ve yenileme

Excel bir hücreyi Power BI öne çıkan tablosundaki bir satıra bağladığında, tüm alan değerlerini alır ve Excel dosyasına kaydeder. Dosyayı paylaştığınız herkes Power BI’dan veri istemeden alanlardan herhangi birine başvurabilir.  

Bağlantılı hücrelerdeki verileri yenilemek için **Veri** şeridindeki **Tümünü Yenile** düğmesini kullanın. 

:::image type="content" source="media/service-excel-featured-tables/excel-refresh-all.png" alt-text="Tümünü Yenile":::
 
Ayrıca tek tek hücreleri de yenileyebilirsiniz. Hücreye sağ tıklayın ve **Veri Türleri** > **Yenile**’yi seçin.

## <a name="show-a-card-change-or-convert-to-text"></a>Kart gösterme, değiştirme veya metne dönüştürme

Bağlantılı hücreler sağ tıklatma menü seçeneklerine eklenir. Hücreye sağ tıklayın > **Veri Türü** >’nü seçin  

- **Kartı Göster**
- **Yenile**
- **Değiştir** 
- **Metne Dönüştür**.

:::image type="content" source="media/service-excel-featured-tables/excel-right-click-data-type.png" alt-text="Sağ tıklayın, Metne Dönüştür":::
 
**Metne Dönüştür** seçeneği Power BI öne çıkan tablosundaki satıra yönelik bağlantıyı kaldırır. Burada önemi olan, hücredeki metnin bağlantılı hücrenin satır etiketi değeri olmasıdır. Hücreyi istemediğiniz bir satıra bağladıysanız, ilk hücre değerlerini geri yüklemek için Excel’de **Geri Al**’ı seçin.

## <a name="licensing"></a>Lisanslama
Excel Veri Türleri Galerisi ve Power BI öne çıkan tablolarına bağlantı deneyimleri yalnızca Excel E5 ve G5 müşterilerine yöneliktir. 

## <a name="security"></a>Güvenlik

Yalnızca Power BI’da izniniz olan veri kümelerindeki öne çıkan tabloları görürsünüz. Verileri yenilerken, satırları almak için Power BI’daki veri kümesine erişim izniniz olmalıdır. Veri kümesi üzerinde Oluşturma veya Yazma izni gerekir. Excel, satırın tamamı için döndürülen verileri önbelleğe alır. Excel dosyasını paylaştığınız herkes tüm bağlantılı hücrelerdeki alanların tümünü görebilir.

Power BI veri kümesinin satır düzeyi güvenliği varsa veya veri kümesine Microsoft Bilgi Koruması duyarlılık etiketi uygulandıysa, bu veri kümesindeki öne çıkan tablolar Excel Veri Türleri Galerisi’ne eklenmez. Bu ilk önizlemenin sınırlamalarından biridir.

## <a name="curate-a-featured-table-in-power-bi-desktop"></a>Power BI Desktop’ta bir öne çıkan tablo seçme
Excel Veri Türleri Galerisi, Power BI hizmetine yüklenen veri kümelerindeki öne çıkan tabloları gösterir. Veri modelinde öne çıkan tabloları seçki olarak sunmak için Power BI Desktop’ı kullanın, sonra bunları Power BI hizmetine yükleyin.

### <a name="turn-on-the-featured-table-preview"></a>Öne çıkan tablo önizlemesini açma

1. Power BI Desktop'ta **Dosya** > **Seçenekler ve Ayarlar** > **Seçenekler** > **Önizleme Özellikleri**'ni seçin.
2. **Öne çıkan tablolar** onay kutusunu seçin.

    :::image type="content" source="media/service-excel-featured-tables/power-bi-preview-featured-tables.png" alt-text="Öne çıkan tablolar önizleme seçeneği":::

### <a name="select-a-table"></a>Tablo seçme

1. Power BI Desktop'ta Model görünümüne gidin.

    :::image type="content" source="media/service-excel-featured-tables/power-bi-model-view.png" alt-text="Model görünümü":::
 
2. Tablo seçin ve **Öne çıkan tablo** öğesini **Evet** olarak ayarlayın.

    :::image type="content" source="media/service-excel-featured-tables/power-bi-featured-table-yes.png" alt-text="Öne çıkan tablo seçeneğini Evet olarak ayarlama":::

4. **Bu öne çıkan tabloyu ayarla** bölümünde gerekli alanları sağlayın:

    - **Açıklama**.
    - **Satır etiketi** alanının değeri Excel’de kullanılır ve böylece kullanıcılar satırı kolayca belirleyebilir. **Veri Seçicisi** bölmesinde ve **Bilgi** kartında bağlı hücre için hücre değeri olarak görüntülenir. 
    - **Anahtar sütunu** alanının değeri satır için benzersiz bir kimlik sağlar. Bu değer Excel’in bir hücreyi tablodaki belirli bir satıra bağlamasına olanak tanır.

    :::image type="content" source="media/service-excel-featured-tables/power-bi-set-up-featured-table.png" alt-text="Öne çıkan tabloyu ayarlama":::

Veri kümesini Power BI hizmetine yayımladıktan veya içeri aktardıktan sonra öne çıkan tablo Excel Veri Türleri Galerisi’nde görüntülenir.

- Excel veri türleri listesini önbelleğe aldığından, yeni yayımlanan önce çıkan tabloları görmek için Excel’i yeniden başlatmanız gerekir.
- Bazı veri kümeleri önizlemede desteklenmez; söz konusu veri kümelerinde tanımlanan öne çıkan tablolar Excel’de görüntülenmez. Ayrıntılar için önemli noktalar ve sınırlamalara bakın.

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

- Excel yalnızca yeni Power BI çalışma alanlarında depolanan öne çıkan tabloları görüntüler. Klasik çalışma alanlarında veya Çalışma Alanım’da depolanan öne çıkan tablolar Excel’de veri türleri olarak gösterilmez. Power BI'da [klasik çalışma alanlarını yeni çalışma alanlarına yükseltebilirsiniz](service-upgrade-workspaces.md).

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

- Sorularınız mı var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)

