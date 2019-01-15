---
title: Rapora filtre ekleme
description: Tüketiciler için Power BI hizmetindeki bir rapora filtre ekleme
author: mihart
manager: kvivek
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 12/06/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 1f1d3c410a74f7a015472deef79072fcefaf5e2e
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2019
ms.locfileid: "54281885"
---
# <a name="take-a-tour-of-the-report-filters-pane"></a>Power BI Filtreler bölmesine ilişkin tura katılın
Bu makale Power BI hizmetindeki Rapor Filtreleri bölmesine bir bakış sunmaktadır.

Power BI'da verileri filtrelemenin birçok yolu vardır ancak öncelikle [Filtreler ve vurgulama hakkında](../power-bi-reports-filters-and-highlighting.md) başlıklı makaleyi okumanızı öneririz.

![tarayıcıda rapor](media/end-user-report-filter/power-bi-browser.png)

## <a name="working-with-the-report-filters-pane"></a>Raporun Filtreler bölmesiyle çalışma
Bir iş arkadaşı sizinle bir rapor paylaştığında **Filtreler** bölmesine bakmayı unutmayın. Bölme bazen raporun sağ kenarı boyunca katlanır. Genişletmek için raporu seçin.   

![tarayıcıda rapor](media/end-user-report-filter/power-bi-expanded.png)

Filtreler bölmesi, rapor *tasarımcısı* tarafından eklenen filtreler içerir. Sizin gibi *tüketiciler* filtrelerle etkileşebilir ve değişikliklerini kaydedebilir, ancak rapora yeni filtre ekleyemez. Örneğin yukarıdaki ekran görüntüsünde tasarımcı iki sayfa düzeyi filtre eklemiştir: Segment ve Year. Bu filtrelerle etkileşim kurabilir ve bunları değiştirebilirsiniz ancak üçüncü bir sayfa düzeyi filtre ekleyemezsiniz.

Power BI hizmetinde raporlar, Filtreler bölmesinde yaptığınız tüm değişiklikleri korur ve bu değişiklikler, raporun mobil sürümüne taşınır. Filtre bölmesini tasarımcının varsayılanlarına geri döndürmek için en üstteki menü çubuğundan **Varsayılana sıfırla**'yı seçin.     

## <a name="open-the-filters-pane"></a>Filtreler bölmesini açma
Bir rapor açıldığında, rapor tuvalinin sağ tarafında Filtreler bölmesi görüntülenir. Bölmeyi görmüyorsanız genişletmek için sağ üst köşedeki oku seçin.  

Bu örnekte, 6 filtresi bulunan bir görsel seçtik. Rapor sayfasında da filtreler bulunur ve bunlar **Sayfa düzeyi filtreleri** başlığı altında yer alır. Bir [Detaylandırma filtresinin](../power-bi-report-add-filter.md) yanı sıra raporun tamamına uygulanmış bir filtre daha bulunur:  **FiscalYear** 2013 veya 2014 değeridir.

![filtre listesi](media/end-user-report-filter/power-bi-filter-list.png)

Bazı filtrelerin yanında **Tümü** ifadesi bulunur ve bu, tüm değerlerin söz konusu filtreye dahil edildiği anlamına gelir.  Örneğin, yukarıdaki ekran görüntüsünde **Chain(All)**, bize bu rapor sayfasının tüm mağaza zincirleriyle ilgili verileri içerdiğini gösterir.  Diğer yandan, **FiscalYear 2013 veya 2014 değeridir** rapor düzeyi filtresi, bize raporun yalnızca 2013 ve 2014 mali yıllarına ilişkin verileri içerdiğini gösterir.

Bu raporu görüntüleyen tüm kullanıcılar filtrelerle etkileşime geçebilir.

- İstediğiniz değeri bulmak ve seçmek için sayfa, görsel, rapor ve detaylandırma filtrelerinde arama yapın. 

    ![Filtrede arama yapma](media/end-user-report-filter/power-bi-filter-search.png)

- Filtrenin üzerine gelip yanındaki oku seçerek ayrıntılarını görüntüleyebilir.
  
   ![seçilen Lindsey'leri gösterir](media/end-user-report-filter/power-bi-expan-filter.png)
* Filtreyi değiştirebilir (örneğin, **Lindseys** filtresini **Fashions Direct** ile değiştirme).
  
     ![seçilen Fashions Direct'i gösterir](media/end-user-report-filter/power-bi-filter-chain.png)

* Üstteki menü çubuğundan **Varsayılana sıfırla**’yı seçerek filtreleri özgün durumuna geri döndürebilir.    
    ![varsayılana sıfırla](media/end-user-report-filter/power-bi-reset-to-default.png)
    
* Filtre adının yanındaki **x** işaretini seçerek filtreyi silebilir.
  
    ![vurgulanmış halde x](media/end-user-report-filter/power-bi-delete-filter.png)

  Bir filtre silindiğinde listeden kaldırılır ancak rapordan silinmez.  Örneğin, **FiscalYear 2013 veya 2014 değeridir** filtresini silerseniz mali yıl verileri raporda kalmaya devam eder ancak artık yalnızca 2013 ve 2014 yıllarını gösterecek şekilde filtrelenmek yerine verilerin kapsadığı tüm mali yılları gösterir.  Ancak sildiğiniz filtreler listeden kaldırılacağından bu filtreleri artık değiştiremezsiniz. Silgi simgesini ![ silgi simgesi ](media/end-user-report-filter/power-bi-eraser-icon.png) seçerek filtreyi temizlemek daha kullanışlı bir seçenektir.
  
  



## <a name="clear-a-filter"></a>Bir filtreyi temizleme
 Gelişmiş veya temel filtreleme modunda silgi simgesini seçerek  ![silgi simgesi](media/end-user-report-filter/pbi_erasericon.jpg) filtreyi temizleyin. 


## <a name="types-of-filters-text-field-filters"></a>Filtre türleri: metin alanı filtreleri
### <a name="list-mode"></a>Liste modu
Bir onay kutusunun işaretlenmesi ilgili değerin seçilmesini veya seçiminin kaldırılmasını sağlar. Tüm onay kutularının durumunu açık veya kapalı olarak değiştirmek için **Tümü** onay kutusu kullanılabilir. Onay kutuları, söz konusu alan için kullanılabilen tüm değerleri temsil eder.  Siz filtreyi ayarlarken, ifade, seçimlerinizi yansıtacak şekilde güncelleştirilir. 

![liste modu filtresi](media/end-user-report-filter/power-bi-restatement-new.png)

İfadenin artık "Mar, Apr veya May değeridir" olarak göründüğüne dikkat edin.

### <a name="advanced-mode"></a>Gelişmiş mod
Gelişmiş moda geçmek için **Gelişmiş Filtreleme** seçeneğini belirleyin. Hangi alanların dahil edileceğini belirlemek için açılan menü denetimlerini ve metin kutularını kullanın. **Ve** ile **Veya** arasında seçim yaparak karmaşık filtre ifadeleri oluşturabilirsiniz. İstediğiniz değerleri belirledikten sonra **Filtre Uygula** düğmesini seçin.  

![gelişmiş mod](media/end-user-report-filter/power-bi-advanced.png)

## <a name="types-of-filters-numeric-field-filters"></a>Filtre türleri: sayısal alan filtreleri
### <a name="list-mode"></a>Liste modu
Değerler sınırlıysa, alanı seçtiğinizde bir liste görüntülenir.  Onay kutuları kullanma ile ilgili yardım için yukarıdaki **Metin alanı filtreleri** &gt; **Liste modu** başlığına bakın.   

### <a name="advanced-mode"></a>Gelişmiş mod
Değerler sınırsızsa veya bir aralığı temsil ediyorsa alanı seçtiğinizde gelişmiş filtreleme modu açılır. Görmek istediğiniz değer aralığını belirtmek için, açılan menüyü ve metin kutularını kullanın. 

![gelişmiş filtre](media/end-user-report-filter/power-bi-dropdown-and-text.png)

**Ve** ile **Veya** arasında seçim yaparak karmaşık filtre ifadeleri oluşturabilirsiniz. İstediğiniz değerleri belirledikten sonra **Filtre Uygula** düğmesini seçin.

## <a name="types-of-filters-date-and-time"></a>Filtre türleri: tarih ve saat
### <a name="list-mode"></a>Liste modu
Değerler sınırlıysa, alanı seçtiğinizde bir liste görüntülenir.  Onay kutuları kullanma ile ilgili yardım için yukarıdaki **Metin alanı filtreleri** &gt; **Liste modu** başlığına bakın.   

### <a name="advanced-mode"></a>Gelişmiş mod
Alan değerleri tarih veya saat temsil ediyorsa Tarih/Saat filtrelerini kullanırken başlangıç/bitiş zamanı belirtebilirsiniz.  

![tarih saat filtresi](media/end-user-report-filter/pbi_date-time-filters.png)


## <a name="next-steps"></a>Sonraki adımlar
[Görsellerin bir rapor sayfasında nasıl birbirlerini karşılıklı olarak filtrelediğini ve vurguladığını öğrenin](end-user-interactions.md)