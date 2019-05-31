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
ms.date: 05/30/2019
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: dcf62925d8e5eef07fb6295f8d8141413947f8fb
ms.sourcegitcommit: d88cc6a87d4ba82ad2c4d496a3634f927e4ac529
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/30/2019
ms.locfileid: "66413063"
---
# <a name="take-a-tour-of-the-report-filters-pane"></a>Power BI Filtreler bölmesine ilişkin tura katılın
Bu makalede, Power BI hizmetinde rapor filtreleri bölmesine göz alır. Verilerinizde yeni içgörüler keşfetmek için filtreleri kullanın.

Power BI'da verileri filtrelemenin birçok yolu vardır ancak öncelikle [Filtreler ve vurgulama hakkında](../power-bi-reports-filters-and-highlighting.md) başlıklı makaleyi okumanızı öneririz.

![tarayıcıda rapor](media/end-user-report-filter/power-bi-browser-new2.png)

## <a name="working-with-the-report-filters-pane"></a>Raporun Filtreler bölmesiyle çalışma
Bir iş arkadaşı sizinle bir rapor paylaştığında **Filtreler** bölmesine bakmayı unutmayın. Bölme bazen raporun sağ kenarı boyunca katlanır. Genişletmek için raporu seçin.   

![tarayıcıda rapor](media/end-user-report-filter/power-bi-filter-pane.png)

Filtreler bölmesi, rapor *tasarımcısı* tarafından eklenen filtreler içerir. *Tüketiciler* sizin gibi değişikliklerinizi kaydetmek için filtreleri ile etkileşim kurabilir ancak rapora yeni filtreler ekleyemez. Örneğin yukarıdaki ekran görüntüsünde tasarımcı iki sayfa düzeyi filtre eklemiştir: Segmentlere ayırın ve yıl çalışan. Bu filtrelerle etkileşim kurabilir ve bunları değiştirebilirsiniz ancak üçüncü bir sayfa düzeyi filtre ekleyemezsiniz.

Power BI hizmetinde raporları filtreler bölmesinde yaptığınız tüm değişiklikleri korur ve bu değişiklikler raporun mobil sürümüne taşınır. Filtre bölmesini tasarımcının varsayılanlarına geri döndürmek için en üstteki menü çubuğundan **Varsayılana sıfırla**'yı seçin.  

![Varsayılana sıfırla](media/end-user-report-filter/power-bi-reset-to-default.png)   

## <a name="view-all-the-filters-for-a-report-page"></a>Bir rapor sayfasının tüm filtreleri görüntüleyebilir
Rapor tarafından eklenen tüm filtreleri filtreler bölmesi görüntülenir *Tasarımcısı*. Filtreler bölmesi de burada filtreleri hakkındaki bilgileri görüntüleyebilir ve bunlarla etkileşim alandır. Siz olun veya değişiklikleri kaydedip kaydetmemek **Varsayılana Sıfırla** özgün filtre ayarlarına döndürmek için.

Değişiklikleri kaydetmek ister misiniz yoksa kişisel bir yer işareti de oluşturabilirsiniz.  Daha fazla bilgi için [rapor için bir yer işareti ekleme](end-user-bookmarks.md).

Birkaç görüntülenir ve filtreler bölmesinden yönetilen rapor filtresi türleri bu görsel, bir rapor sayfası ve raporun tamamına uygulanan vardır.

Bu örnekte, 2 filtreleri içeren bir görsel seçtik. Rapor sayfasının altında listelenen filtreler de bulunur. **bu sayfada filtreler** başlığı. Ve raporun tamamına filtre tarihi vardır.

![filtre listesi](media/end-user-report-filter/power-bi-all-filters2.png)

Bazı filtrelerin yanında **Tümü** ifadesi bulunur ve bu, tüm değerlerin söz konusu filtreye dahil edildiği anlamına gelir.  Örneğin, **Segment(All)** yukarıdaki ekran görüntüsünde bize Bu rapor sayfasının tüm ürün segmentleri ilgili verileri içerdiğini gösterir.  Öte yandan, sayfa düzeyi filtresi, **bölgedir Batı** bize rapor sayfasını yalnızca Batı bölgesinde verileri içerdiğini gösterir.

Bu raporu görüntüleyen tüm kullanıcılar filtrelerle etkileşime geçebilir.

### <a name="view-only-those-filters-applied-to-a-visual"></a>Yalnızca bu görsele uygulanmış filtreleri görüntüleyin
Belirli bir görselde uygulanan filtrelere yakından almak için filtre simgesini açığa çıkarmak için görselin üzerine gelin ![simgesi](media/end-user-report-filter/power-bi-filter-icon.png). Tüm filtreler, dilimleyiciler ve benzeri, söz konusu görsel etkileyen bir açılır pencere görmek için filtre simgesini seçin. Açılır pencere filtrelere, görüntülenen aynı filtrelerdir **filtreleri** bölmesi. 

![filtre listesi](media/end-user-report-filter/power-bi-hover-visual-filter.png)

 
Bu görünüm filtre türleri şunlardır:
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



Örnekte, aşağıda:
1. Sütun grafiği çapraz filtre olduğunu görebiliriz.
2. **Dahil edilen** bize çapraz filtreleme için olduğunu söyleyen **Segment**, ve üç dahil edilir. 
3. Dilimleyici için uygulanan **Çeyrek**.
4. **Bölge** Bu rapor sayfasına bir filtre ve
5. **isVanArsdel** ve **yıl** uygulanan filtreler bu görsele olan getirin.


![filtre listesi](media/end-user-report-filter/power-bi-visual-pop-up.png)

### <a name="search-in-a-filter"></a>Filtrede arama yapma
Bazen bir filtre uzun bir değerler listesi olabilir. Bulmak ve bulmak istediğiniz değer seçmek için arama kutusunu kullanın. 

![Filtrede arama yapma](media/end-user-report-filter/power-bi-fiter-search.png)

### <a name="display-filter-details"></a>Görüntüleme filtresi ayrıntıları
Bir filtre anlamak için kullanılabilir değerler ve sayıları göz atın.  Filtrenin üzerine gelip filtre adının yanındaki oku seçerek ayrıntılarına bakın. 
  
![seçilen Lindsey'leri gösterir](media/end-user-report-filter/power-bi-expand-filter.png)

### <a name="change-filter-selections"></a>Filtre seçimlerini Değiştir
Veri öngörüleri için aranacak bir filtrelerle etkileşim kurmak için yoludur. Filtre seçimlerini alan adının yanındaki açılır oku kullanarak değiştirebilirsiniz.  Filtre ve filtrelenen veri türüne bağlı olarak, seçenekleri bir listeden basit seçimler tarihlerde veya sayılarda aralıklarını tanımlamak üzere çeşitli. Aşağıdaki Gelişmiş filtre, bu özelliğin filtre değiştirdik **toplam birimler YTD** üzerinde 2.000 ve 3.000 arasında olacak şekilde ağaç haritası. Bu Prirum ağaç Haritası ' kaldırır dikkat edin. 
  
![seçilen Fashions Direct'i gösterir](media/end-user-report-filter/power-bi-filter-treemap.png)

> [!TIP]
> Aynı anda birden fazla filtre değeri seçmek için CTRL tuşunu basılı tutun. Filtrelerin çoğu, çoklu seçim destekler. 

### <a name="reset-filter-to-default"></a>Filtre Varsayılana sıfırla
Dışında tüm değişiklikleri geri istiyorsanız filtreleri, select yaptığınız **Varsayılana Sıfırla** üstteki menü çubuğundan.  Bu rapor tarafından belirlenen filtrelere ilk durumuna döner *Tasarımcısı*. 

![Varsayılana sıfırla](media/end-user-report-filter/power-bi-reset-to-default.png)
    
### <a name="clear-a-filter"></a>Bir filtreyi temizleme
Ayarlamak için istediğiniz yalnızca bir filtre olup olmadığını **(Tümü)** , Silgi simgesini seçerek Temizle ![ Silgi simgesini ](media/end-user-report-filter/power-bi-eraser-icon.png) filtre adının yanındaki.
  
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
[Görsellerin bir rapor sayfasında nasıl birbirlerini karşılıklı olarak filtrelediğini ve vurguladığını öğrenin](end-user-interactions.md)