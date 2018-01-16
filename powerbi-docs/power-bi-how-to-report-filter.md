---
title: "Power BI Filtreler bölmesine ilişkin tura katılın"
description: Rapor filtrelerini kullanma
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/29/2017
ms.author: mihart
ms.openlocfilehash: da3d4359fab37d1c5ee5f9d214cc5dba0fa9b680
ms.sourcegitcommit: 804ee18b4c892b7dcbd7d7d5d987b16ef16fc2bb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2018
---
# <a name="take-a-tour-of-the-report-filters-pane"></a>Power BI Filtreler bölmesine ilişkin tura katılın
Bu makalede, raporlardaki Filtreler bölmesine ilişkin ayrıntılı bir bakış sunulmuştur. Söz konusu bölmeyle Power BI raporları için Düzenleme Görünümü ve Okuma Görünümü'nde karşılaşırsınız.

Power BI'da verileri filtrelemenin birçok yolu vardır ancak öncelikle [Filtreler ve vurgulama hakkında](power-bi-reports-filters-and-highlighting.md) başlıklı makaleyi okumanızı öneririz.

## <a name="working-with-filters"></a>Filtrelerle çalışma
Raporlar [Düzenleme görünümü veya Okuma görünümü](service-reading-view-and-editing-view.md)'nde açılabilir. Düzenleme Görünümü'nde, rapor sahipleri [raporlara filtreler ekleyebilir](power-bi-report-add-filter.md) ve eklenen filtreler raporla birlikte kaydedilir. Raporu Okuma görünümü'nde görüntüleyen kullanıcılar filtrelerle etkileşime geçebilir ancak filtre değişikliklerini rapora kaydedemez.

## <a name="filters-in-reading-view"></a>Okuma Görünümü'nde filtreler
Bir rapor Okuma Görünümü'nde açıldığında Filtreler bölümü, rapor tuvalinin sağ tarafında görüntülenir. Bölmeyi görmüyorsanız genişletmek için sağ üst köşedeki oku seçin.

Bu örnekte, 6 filtresi bulunan bir görsel seçtik. Rapor sayfasında da filtreler bulunur ve bunlar **Sayfa düzeyi filtreleri** başlığı altında yer alır. Bir [Detaylandırma filtresinin](power-bi-report-add-filter.md) yanı sıra raporun tamamına uygulanmış bir filtre daha bulunur: **FiscalYear** 2013 veya 2014 değeridir.

![](media/power-bi-how-to-report-filter/power-bi-filter-list.png)

Bazı filtrelerin yanında **Tümü** ifadesi bulunur ve bu, tüm değerlerin söz konusu filtreye dahil edildiği anlamına gelir.  Örneğin, aşağıdaki ekran görüntüsünde **Chain (Tümü)**, bize bu rapor sayfasının tüm mağaza zincirleriyle ilgili verileri içerdiğini gösterir.  Diğer yandan, **FiscalYear 2013 veya 2014 değeridir** rapor düzeyi filtresi, bize raporun yalnızca 2013 ve 2014 mali yıllarına ilişkin verileri içerdiğini gösterir.

Bu raporu görüntüleyen tüm kullanıcılar filtrelerle etkileşime geçebilir.

* Filtrenin üzerine gelip yanındaki oku seçerek ayrıntılarını görüntüleyebilirler.
  
   ![](media/power-bi-how-to-report-filter/power-bi-expan-filter.png)
* Filtreyi değiştirebilirler (örneğin, **Lindseys** filtresini **Fashions Direct** ile değiştirme).
  
     ![](media/power-bi-how-to-report-filter/power-bi-filter-chain.png)
* Filtre adının yanındaki **x** işaretini seçerek filtreyi silebilirler.
  
  Bir filtre silindiğinde listeden kaldırılır ancak rapordan silinmez.  Örneğin, **FiscalYear 2013 veya 2014 değeridir** filtresini silerseniz mali yıl verileri raporda kalmaya devam eder ancak artık yalnızca 2013 ve 2014 yıllarını gösterecek şekilde filtrelenmek yerine verilerin kapsadığı tüm mali yılları gösterir.  Ancak sildiğiniz filtreler listeden kaldırılacağından bu filtreleri artık değiştiremezsiniz. Silgi simgesini ![](media/power-bi-how-to-report-filter/power-bi-eraser-icon.png) seçerek filtreyi temizlemek daha kullanışlı bir seçenektir.
  
  ![](media/power-bi-how-to-report-filter/power-bi-delete-filter.png)

## <a name="filters-in-editing-view"></a>Düzenleme Görünümü'nde filtreler
Bir rapor Düzenleme Görünümü'nde açıldığında Filtreler bölümü, rapor tuvalindeki **Görsel Öğeler bölmesinin** orta kısmının altında görüntülenir. Bölmeyi görmüyorsanız genişletmek için sağ üst köşedeki oku seçin.

![](media/power-bi-how-to-report-filter/power-bi-all-filters.png).  

Tuvalde hiçbir görsel seçilmediyse Filtreler bölmesi, yalnızca rapor sayfasının veya raporun tamamına uygulanan filtreleri ve detaylandırma filtrelerini (ayarlandıysa) görüntüler. Aşağıdaki örnekte, hiçbir görsel seçilmemiştir ve herhangi bir sayfa düzeyi veya detaylandırma filtresi ayarlanmamıştır ancak bir rapor düzeyi filtresi mevcuttur.  

![](media/power-bi-how-to-report-filter/power-bi-no-visual.png)  

Tuvalde bir görsel seçilirse yalnızca bu görsele uygulanmış filtreleri de görürsünüz:   

![](media/power-bi-how-to-report-filter/power-bi-visual-filters.png)

Belirli bir filtreye yönelik seçenekleri görüntülemek için filtre adının yanında bulunan aşağı oku seçin.  Aşağıdaki örnekte, rapor düzeyi filtresi 2013'e ve 2014'e ayarlanmıştır. Bu, bir **temel filtreleme** örneğidir.  Gelişmiş seçenekleri görüntülemek için **Gelişmiş Filtreleme** seçeneğini belirleyin.

![](media/power-bi-how-to-report-filter/pbi_filterlistdropdown.jpg)

## <a name="clear-a-filter"></a>Bir filtreyi temizleme
 Gelişmiş veya temel filtreleme modunda, filtreyi sıfırlamak için silgi simgesini ![](media/power-bi-how-to-report-filter/pbi_erasericon.jpg) seçin. 

## <a name="add-a-filter"></a>Filtre ekleme
* Düzenleme görünümünde bir görsele, sayfaya, detaylandırmaya veya rapora filtre eklemek için Alanlar bölmesindeki bir alanı seçin ve **Veri alanlarını buraya sürükleyin** ifadesiyle gösterilen uygun filtre kutusuna sürükleyin. Bir alan filtre olarak eklendikten sonra, Temel filtreleme ve Gelişmiş filtreleme denetimlerini kullanarak (aşağıda açıklanmıştır) hassas ayarlamalar yapabilirsiniz.

Görsel düzeyi filtresi alanına yeni bir alan sürüklemek söz konusu alanın görsele eklenmesini sağlamaz ancak görseli bu yeni alanla filtrelemenize olanak tanır. Aşağıdaki örnekte, **Chain** alanı görsele yeni bir filtre olarak eklenmiştir. Yalnızca **Chain** alanının bir filtre olarak eklenmesinin, siz Temel veya Gelişmiş filtreleme denetimlerini kullanana kadar görselin değişmesine neden olmadığına dikkat edin.

    ![](media/power-bi-how-to-report-filter/power-bi-visual-filter.gif)

* Görselleştirme oluşturmak için kullanılan tüm alanlar aynı zamanda filtre olarak da kullanılabilir. Öncelikle, bir görseli seçerek etkin hale getirin. Görselde kullanılmakta olan alanlar Görsel Öğeler bölmesinde (Düzenleme görünümündeyseniz) ve Filtreler bölmesindeki **Görsel düzeyi filtreleri** başlığı altında yer alır.
  
   ![](media/power-bi-how-to-report-filter/power-bi-visual-filter.png)  
  
   Temel filtreleme ve Gelişmiş filtreleme denetimlerini kullanarak (aşağıda açıklanmıştır) bu alanlar için hassas ayarlamalar yapabilirsiniz.

## <a name="types-of-filters-text-field-filters"></a>Filtre türleri: metin alanı filtreleri
### <a name="list-mode"></a>Liste modu
Bir onay kutusunun işaretlenmesi ilgili değerin seçilmesini veya seçiminin kaldırılmasını sağlar. Tüm onay kutularının durumunu açık veya kapalı olarak değiştirmek için **Tümü** onay kutusu kullanılabilir. Onay kutuları, söz konusu alan için kullanılabilen tüm değerleri temsil eder.  Siz filtreyi ayarlarken, ifade, seçimlerinizi yansıtacak şekilde güncelleştirilir. 

![](media/power-bi-how-to-report-filter/pbi_restatement.png)

İfadenin artık "Amarilla veya Carretera değeridir" olarak göründüğüne dikkat edin

### <a name="advanced-mode"></a>Gelişmiş mod
Gelişmiş moda geçmek için **Gelişmiş Filtreleme** seçeneğini belirleyin. Hangi alanların dahil edileceğini belirlemek için açılan menü denetimlerini ve metin kutularını kullanın. **Ve** ile **Veya** arasında seçim yaparak karmaşık filtre ifadeleri oluşturabilirsiniz. İstediğiniz değerleri belirledikten sonra **Filtre Uygula** düğmesini seçin.  

![](media/power-bi-how-to-report-filter/aboutfilters.png)

## <a name="types-of-filters-numeric-field-filters"></a>Filtre türleri: sayısal alan filtreleri
### <a name="list-mode"></a>Liste modu
Değerler sınırlıysa, alanı seçtiğinizde bir liste görüntülenir.  Onay kutuları kullanma ile ilgili yardım için yukarıdaki **Metin alanı filtreleri** &gt; **Liste modu** başlığına bakın.   

### <a name="advanced-mode"></a>Gelişmiş mod
Değerler sınırsızsa veya bir aralığı temsil ediyorsa alanı seçtiğinizde gelişmiş filtreleme modu açılır. Görmek istediğiniz değer aralığını belirtmek için, açılan menüyü ve metin kutularını kullanın. 

![](media/power-bi-how-to-report-filter/pbi_dropdown-and-text.png)

**Ve** ile **Veya** arasında seçim yaparak karmaşık filtre ifadeleri oluşturabilirsiniz. İstediğiniz değerleri belirledikten sonra **Filtre Uygula** düğmesini seçin.

## <a name="types-of-filters-date-and-time"></a>Filtre türleri: tarih ve saat
### <a name="list-mode"></a>Liste modu
Değerler sınırlıysa, alanı seçtiğinizde bir liste görüntülenir.  Onay kutuları kullanma ile ilgili yardım için yukarıdaki **Metin alanı filtreleri** &gt; **Liste modu** başlığına bakın.   

### <a name="advanced-mode"></a>Gelişmiş mod
Alan değerleri tarih veya saat temsil ediyorsa Tarih/Saat filtrelerini kullanırken başlangıç/bitiş zamanı belirtebilirsiniz.  

![](media/power-bi-how-to-report-filter/pbi_date-time-filters.png)

## <a name="next-steps"></a>Sonraki adımlar
[Raporlarda filtreleme ve vurgulama](power-bi-reports-filters-and-highlighting.md)  
[Okuma Görünümü'nde filtreler ve vurgulama ile etkileşim kurma](service-reading-view-and-editing-view.md)  
[Rapor Düzenleme Görünümü'nde filtre oluşturma](power-bi-report-add-filter.md)  
[Rapor görsellerinin birbirini çapraz filtreleme ve çapraz vurgulama şeklini değiştirme](service-reports-visual-interactions.md)

[Power BI'daki raporlar](service-reports.md) hakkında daha fazla bilgi edinin  
[Power BI - Temel Kavramlar](service-basic-concepts.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

