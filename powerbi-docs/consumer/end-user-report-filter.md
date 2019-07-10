---
title: Rapordaki Filtreler bölmesinde gezinti
description: Tüketiciler için Power BI hizmetindeki bir rapora filtre ekleme
author: mihart
manager: kvivek
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 06/24/2019
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: ef7e4f556832f1323043a80cf219678a16511c9e
ms.sourcegitcommit: e67bacbfc5638ee97e3d2e0e7f5bd2d9aac78f9c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2019
ms.locfileid: "67532830"
---
# <a name="take-a-tour-of-the-report-filters-pane"></a>Power BI Filtreler bölmesine ilişkin tura katılın

Bu makale Power BI hizmetindeki Rapor **Filtreleri** bölmesine bir bakış sunmaktadır. Verilerinizde yeni içgörüler keşfetmek için filtreleri kullanın.

Power BI'da verilere filtre uygulamanın birçok farklı yolu vardır. Filtreler hakkında daha fazla bilgi için bkz. [Power BI raporlarında filtreler ve vurgulama](../power-bi-reports-filters-and-highlighting.md).

![Filtreler seçeneğini işaret eden bir okla birlikte tarayıcıdaki raporun ekran görüntüsü.](media/end-user-report-filter/power-bi-browser-new2.png)

## <a name="working-with-the-report-filters-pane"></a>Raporun Filtreler bölmesiyle çalışma

Bir iş arkadaşı sizinle bir rapor paylaştığında **Filtreler** bölmesine bakmayı unutmayın. Bölme bazen raporun sağ kenarı boyunca katlanır. Genişletmek için raporu seçin.

![Filtreler bölmesi genişletilmiş olarak raporun ekran görüntüsü.](media/end-user-report-filter/power-bi-filter-pane.png)

**Filtreler** bölmesi, rapor *tasarımcısı* tarafından rapora eklenen filtreleri içerir. Sizin gibi *tüketiciler* mevcut filtrelerle etkileşebilir ve değişikliklerini kaydedebilir, ancak rapora yeni filtre ekleyemezsiniz. Örneğin yukarıdaki ekran görüntüsünde tasarımcı iki sayfa düzeyi filtre eklemiştir: **Segment** ve **Yıl**. Bu filtrelerle etkileşim kurabilir ve bunları değiştirebilirsiniz ancak üçüncü bir sayfa düzeyi filtresi ekleyemezsiniz.

Power BI hizmetinde raporlar, **Filtreler** bölümünde yaptığınız tüm değişiklikleri saklar. Hizmet, raporun mobil versiyonu aracılığıyla bu değişiklikleri taşır.

**Filtreler** bölmesini tasarımcının varsayılan ayarlarına sıfırlamak için üstteki menü çubuğundan ![Varsayılana sıfırla seçeneğinin ekran görüntüsü.](media/end-user-report-filter/power-bi-reset.png) öğesini seçin.

## <a name="view-all-the-filters-for-a-report-page"></a>Bir rapor sayfasının tüm filtrelerini görüntüleme

**Filtreler** bölmesinde, tasarımcının rapora eklediği tüm filtreler gösterilir. **Filtreler** bölmesi ayrıca filtreler hakkındaki bilgileri görüntüleyebileceğini ve filtrelerle etkileşimde bulunabileceğiniz alandır. Yaptığınız değişiklikleri kaydedebilir veya **Varsayılana sıfırla**’yı kullanarak özgün filtre ayarlarına dönebilirsiniz.

Kaydetmek istediğiniz değişiklikler varsa, kişisel bir yer işareti de oluşturabilirsiniz.  Daha fazla bilgi için bkz. [Yer işareti nedir?](end-user-bookmarks.md).

**Filtreler** bölmesi birkaç türde rapor filtresi gösterir ve yönetir. Bu filtreler bir görsele, bir rapor sayfasına ve raporun tamamına uygulanabilir.

Bu örnekte, iki filtresi olan bir görsel seçtik. Rapor sayfasında da filtreler bulunur ve bunlar **Bu sayfadaki filtreler** başlığı altında yer alır. Ayrıca, raporun tamamı için bir **Tarih** filtresi mevcuttur.

![Bir görselleştirme içeren ve ilgili filtreleri açıklama balonuna alınmış raporun ekran görüntüsü.](media/end-user-report-filter/power-bi-all-filters2.png)

Bazı filtrelerin yanında **(Tümü)** ifadesi bulunur. **(Tümü)** , filtreye tüm değerlerin dahil edildiği anlamına gelir. Yukarıdaki ekran görüntüsünde **Segment(Tümü)** ifadesi, bu rapor sayfasının tüm ürün segmentleriyle ilgili verileri içerdiğini gösterir. **Bölge Batı** sayfa düzeyi filtresini seçerseniz rapor sayfası yalnızca Batı bölgesine ait verileri içerir.

Bu raporu görüntüleyen tüm kullanıcılar filtrelerle etkileşime geçebilir.

### <a name="view-only-those-filters-applied-to-a-visual"></a>Yalnızca bir görsele uygulanmış filtreleri görüntüleme

Belirli bir görsele uygulanan filtrelere yakından bakmak için fareyle görselin üzerine gelerek filtre simgesini ortaya çıkarın ![Filtre simgesinin ekran görüntüsü.](media/end-user-report-filter/power-bi-filter-icon.png). Bir görseli etkileyen tüm filtreleri, dilimleyicileri, vb. içeren açılan listeyi görüntülemek için bu filtre simgesini seçin. Açılır pencerede filtreler, **Filtreler** bölmesinde gösterilen filtrelerle aynıdır.

![Filtrelerin Filtreler bölmesindeki yerini işaret eden oklarla birlikte filtre listesinin ekran görüntüsü.](media/end-user-report-filter/power-bi-hover-visual-filter.png)

Bu görünümde gösterilebilen filtre türleri şunlardır:

- Temel filtreler

- Dilimleyiciler

- Çapraz vurgulama

- Çapraz filtreleme

- Gelişmiş filtreler

- Üst N filtreler

- Göreli Tarih filtreleri

- Eşitleme dilimleyicileri

- Ekleme/Dışlama filtreleri

- URL aracılığıyla geçirilen filtreler

Aşağıdaki örnekte:

1. Sütun grafiğin çapraz filtreli olduğunu görebiliriz.

1. **Dahil Edilen** seçeneği, çapraz filtrenin **Segment** için olduğu ve üç tane dahil edildiği anlamına gelir.

1. **Çeyrek** için bir dilimleyici uygulanmıştır.

1. **Bölge** bu rapor sayfasına uygulanmış bir filtredir ve

1. **isVanArsdel** ile **Yıl**, bu görsele uygulanmış filtrelerdir.

![Numaraları yukarıdaki numaralı liste ile çakışan filtre listesi ile birlikte rapor ve filtrelerinin ekran görüntüsü.](media/end-user-report-filter/power-bi-visual-pop-up.png)

### <a name="search-in-a-filter"></a>Filtrede arama yapma

Bazen bir filtre uzun bir değer listesine sahip olabilir. İstediğiniz değeri bulup seçmek için arama kutusunu kullanın.

![Bir filtrede arama yapma işleminin ekran görüntüsü.](media/end-user-report-filter/power-bi-fiter-search.png)

### <a name="display-filter-details"></a>Filtre ayrıntılarını görüntüleme

Bir filtreyi anlamak için mevcut değerlere ve sayılara göz atın.  Filtre adının üzerine gelip yanındaki oku seçerek ayrıntılarını görüntüleyin.
  
![Batı bölgesini seçilmiş olarak gösteren bir filtrenin ekran görüntüsü.](media/end-user-report-filter/power-bi-expand-filter.png)

### <a name="change-filter-selections"></a>Filtre seçimlerini değiştirme

Veri içgörüleri aramanın bir yolu, filtrelerle etkileşimde bulunmaktır. Filtre seçimlerini, alan adının yanındaki açılır oku kullanarak değiştirebilirsiniz.  Filtreye ve Power BI’ın filtrelediği verilerin türüne bağlı olarak, listeden basit seçimler ile tarih veya sayı aralığı belirlemeye varan seçenekleriniz mevcut olacaktır. Aşağıdaki gelişmiş filtrede, ağaç haritası üzerindeki **Toplam Birim YTD** filtresini 2.000 ile 3.000 arasında olacak şekilde değiştirdik. Bu değişikliğin ağaç haritasından Prirum’u kaldırdığına dikkat edin.
  
![Fashions Direct’in seçili olduğu bir rapor ve filtrelerinin ekran görüntüsü.](media/end-user-report-filter/power-bi-filter-treemap.png)

> [!TIP]
> Aynı anda birden fazla filtre değeri seçmek için CTRL tuşunu basılı tutun. Çoğu filtre çoklu seçimi destekler.

### <a name="reset-filter-to-default"></a>Filtreyi varsayılana sıfırlama

Filtrelerde yaptığınız tüm değişiklikleri geri almak isterseniz üstteki menü çubuğundan **Varsayılana sıfırla**’yı seçin.  Bu seçim, filtreleri rapor tasarımcısı tarafından ayarlandığı özgün durumuna geri döndürür.

![Varsayılana sıfırla seçeneğinin ekran görüntüsü.](media/end-user-report-filter/power-bi-reset.png)

### <a name="clear-a-filter"></a>Bir filtreyi temizleme

**(Tümü)** olarak ayarlamak istediğiniz yalnızca bir filtre varsa, filtre adının yanındaki silgi simgesini ![Silgi simgesinin ekran görüntüsü.](media/end-user-report-filter/power-bi-eraser-icon.png) seçerek seçimi kaldırın.
  
<!--  too much detail for consumers

## Types of filters: text field filters
### List mode
Ticking a checkbox either selects or deselects the value. The **All** checkbox can be used to toggle the state of all checkboxes on or off. The checkboxes represent all the available values for that field.  As you adjust the filter, the restatement updates to reflect your choices. 

![list mode filter](media/end-user-report-filter/power-bi-restatement-new.png)

Note how the restatement now says "is Mar, Apr or May".

### Advanced mode
Select **Advanced Filtering** to switch to advanced mode. Use the dropdown controls and text boxes to identify which fields to include. By choosing between **And** and **Or**, you can build complex filter expressions. Select the **Apply Filter** button when you've set the values you want.  

![advanced mode](media/end-user-report-filter/power-bi-advanced.png)

## Types of filters: numeric field filters
### List mode
If the values are finite, selecting the field name displays a list.  See **Text field filters** &gt; **List mode** above for help using checkboxes.   

### Advanced mode
If the values are infinite or represent a range, selecting the field name opens the advanced filter mode. Use the dropdown and text boxes to specify a range of values that you want to see. 

![advanced filter](media/end-user-report-filter/power-bi-dropdown-and-text.png)

By choosing between **And** and **Or**, you can build complex filter expressions. Select the **Apply Filter** button when you've set the values you want.

## Types of filters: date and time
### List mode
If the values are finite, selecting the field name displays a list.  See **Text field filters** &gt; **List mode** above for help using checkboxes.   

### Advanced mode
If the field values represent date or time, you can specify a start/end time when using Date/Time filters.  

![datetime filter](media/end-user-report-filter/pbi_date-time-filters.png)

-->

## <a name="next-steps"></a>Sonraki adımlar

[Görsellerin bir rapor sayfasında nasıl birbirlerini karşılıklı olarak filtrelediğini ve vurguladığını](end-user-interactions.md) öğrenin