---
title: Düzenleme görünümünde bir rapora filtre ekleme
description: Power BI'da bir rapora sayfa filtresi, görselleştirme filtresi veya rapor filtresi ekleme
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/22/2019
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: 3666335394222d32bc13ce86d8d0a4ed421b5f73
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66187644"
---
# <a name="add-a-filter-to-a-report-in-editing-view"></a>Düzenleme görünümünde bir rapora filtre ekleme

Bu makalede Power BI'da bir rapora sayfa filtresi, görselleştirme filtresi, rapor filtresi veya detaylandırma filtresi ekleme adımları anlatılmaktadır. Bu makaledeki örneklerde Power BI hizmeti kullanılmıştır. Adımlar Power BI Desktop ile neredeyse aynıdır.

**Biliyor muydunuz?** Power BI, şu an önizleme aşamasında olan yeni bir filtre deneyimine sahiptir. [Power BI raporlarında yeni filtre deneyimi](power-bi-report-filter-preview.md) hakkında daha fazla bilgi edinin.

![Yeni filtre deneyimi](media/power-bi-report-add-filter/power-bi-filter-reading.png)

## <a name="filters-in-editing-view-or-reading-view"></a>Düzenleme görünümündeki ve Okuma görünümündeki filtrelerin karşılaştırması
Raporlarla etkileşimli çalışmak için kullanabileceğiniz iki görünüm vardır: Okuma görünümü ve Düzenleme görünümü. Kullanabileceğiniz filtreleme özellikleri hangi görünümde olduğunuza bağlıdır. Ayrıntılar için bkz. [Power BI raporlarındaki filtreler ve vurgulama hakkında](power-bi-reports-filters-and-highlighting.md).

Bu makalede rapor **Düzenleme görünümünde** nasıl filtre oluşturabileceğiniz açıklanmaktadır.  Okuma görünümündeki filtreler hakkında daha fazla bilgi için [rapor Okuma görünümünde filtrelerle etkileşim kurma](consumer/end-user-report-filter.md) başlıklı makaleye bakın.

## <a name="filter-types-in-the-filters-pane"></a>Filtreler bölmesindeki filtre türleri
Masaüstü veya Power BI hizmeti kullanılırken, rapor tuvalinin sağ kenarında Filtreler bölmesi görüntülenir. Filtreler bölmesini görmüyorsanız bölmeyi genişletmek için sağ üst köşedeki ">" simgesini seçin.

Dört filtre türü vardır: **sayfa filtresi**, **görsel filtresi**, **detaylandırma filtresi** ve **rapor filtresi**.

![Okuma görünümünde filtre bölmesi](media/power-bi-report-add-filter/power-bi-add-filter-reading-view.png)

Filtreler *kalıcı* olduğu için, rapordan çıktığınızda Power BI yaptığınız filtre, dilimleyici ve diğer veri görünümü değişikliklerini tutar. Bu nedenle, rapora geri döndüğünüzde kaldığınız yerden devam edebilirsiniz. Filtre değişikliklerinizin kalıcı olmasını istemiyorsanız üst menü çubuğundan **Varsayılana sıfırla**’yı seçin.

![kalıcı filtre düğmesi](media/power-bi-report-add-filter/power-bi-reset-to-default.png)

## <a name="add-a-filter-to-a-visual"></a>Görsele filtre ekleme
İki farklı şekilde belirli bir görselde bir görsel düzeyi filtresi ekleyebilirsiniz. 

* Görselleştirme tarafından kullanılan bir alanı filtreleyebilirsiniz.
* Görselleştirme tarafından kullanılmayan bir alan belirleyip söz konusu alanı doğrudan **Görsel düzeyi filtreleri** demetine ekleyebilirsiniz.

Bu örnekte Perakende Analizi örneği kullanılmaktadır. Dilerseniz siz de indirip adımları takip edebilirsiniz. [Perakende Analizi örneğini](sample-retail-analysis.md) indirin.

### <a name="filter-the-fields-in-the-visual"></a>Görseldeki alanları filtreleme


1. Seçin **Raporu Düzenle** raporunuzu düzenleme Görünümü'nde açın.
   
   ![Raporu düzenle düğmesi](media/power-bi-report-add-filter/power-bi-edit-view.png)

2. Görsel Öğeler ve Filtreler bölmesini ve Alanlar bölmesini açın (zaten açık değillerse).
   
   ![Görsel öğeler, filtreler ve alanlar bölmeleri](media/power-bi-report-add-filter/power-bi-display-panes.png)
3. Bir görseli seçerek etkin hale getirin. Görsel tarafından kullanılmakta olan tüm alanlar, **Alanlar** bölmesinde yer alır. Bunlar ayrıca **Görsel düzeyi filtreleri** başlığı altındaki **Filtreler** bölmesinde de listelenir.
   
   ![Görsel düzeyi filtrelerini seçin](media/power-bi-report-add-filter/power-bi-default-visual-filter.png)
4. Bu noktada, görselleştirme tarafından zaten kullanılmakta olan bir alana filtre ekleyeceğiz. 
   
    **Görsel düzeyi filtreleri** alanına gidin ve filtrelemek istediğiniz alanı genişletmek için oku seçin. Bu örnekte **StoreNumberName** alanını filtreleyeceğiz.
     
    ![Ok, filtre genişletir.](media/power-bi-report-add-filter/power-bi-visual-level-filter.png) 
    
    **Temel**, **Gelişmiş** veya **Üst N** filtreleme denetimlerinden birini ayarlayın. Bu örnekte Temel filtrelerde **cha** araması yapacak ve listelenen beş mağazayı seçeceğiz.
     
    ![Temel filtreleme arama](media/power-bi-report-add-filter/power-bi-search-filter.png) 
   
    Görsel, yeni filtreyi yansıtacak şekilde değişir. Raporunuzu filtreli olarak kaydederseniz raporu okuyan kişiler görselin filtrelenmiş halini görür ve değerleri seçerek veya temizleyerek Okuma görünümünde filtre ile etkileşim kurabilir.
     
    ![Filtrelenmiş görseli](media/power-bi-report-add-filter/power-bi-search-visual-filter-results.png)

### <a name="filter-with-a-field-thats-not-in-the-visual"></a>Görselde bulunmayan bir alanla filtreleme

Şimdi de görselleştirmemize bir görsel düzeyinde filtre olarak yeni bir alan ekleyelim.
   
1. Alanlar bölmesinden yeni görsel düzeyi filtresi olarak eklemek istediğiniz alanı seçip **Görsel düzeyi filtreleri alanına** sürükleyin.  Bu örnekte, **Görsel düzeyi filtreleri** demetine **District Manager** öğesini sürükleyip **an** araması yapacak ve listelenen üç yöneticiyi seçeceğiz. 
     
    ![Filtreler bölmesi için bir alan ekleme](media/power-bi-report-add-filter/power-bi-search-add-visual-filter.png)

    **District Manager** öğesinin görselleştirmenin kendisine *eklenmediğine* dikkat edin. Görselleştirme hâlâ Eksen olarak **StoreNumberName** ve Değer olarak **This Year Sales** alanlarından oluşmaktadır.  
     
    ![Görselde alan değil](media/power-bi-report-add-filter/power-bi-visualization.png)

    Ayrıca görselleştirmenin kendisi de bu işlemden sonra, belirtilen mağazalar için yalnızca bu yöneticilerin bu yılki satışlarını gösterecek şekilde filtrelenmiştir.
     
    ![Filtrelenmiş görseli](media/power-bi-report-add-filter/power-bi-search-visual-filter-results-2.png)

    Raporunuzu bu filtreyle kaydederseniz raporu okuyan kişiler, değerleri seçerek veya temizleyerek Okuma görünümünde **District Manager** filtresiyle etkileşim kurabilir.

## <a name="add-a-filter-to-an-entire-page"></a>Sayfanın tamamına filtre ekleme

Sayfa düzeyi filtresi bir sayfanın tamamını de ekleyebilirsiniz.

1. Seçin **Raporu Düzenle** raporunuzu düzenleme Görünümü'nde açın.
   
   ![Raporu düzenle düğmesi](media/power-bi-report-add-filter/power-bi-edit-view.png)
2. Görsel Öğeler ve Filtreler bölmesini ve Alanlar bölmesini açın (zaten açık değillerse).
3. Alanlar bölmesinden yeni sayfa düzeyi filtresi olarak eklemek istediğiniz alanı seçip **Sayfa düzeyi filtreleri** alanına sürükleyin.  
4. Filtrelemek istediğiniz değerleri seçip **Temel** veya **Gelişmiş** filtreleme denetimlerini belirleyin.
   
   Sayfadaki tüm görselleştirmelere değişikliği yansıtacak şekilde yeniden düzenlenmiş.
   
   ![Bir filtre ekleyin ve değerleri seçin](media/power-bi-report-add-filter/filterpage.gif)

    Raporunuzu filtreli olarak kaydederseniz raporu okuyan kişiler, değerleri seçerek veya temizleyerek Okuma görünümünde filtre ile etkileşim kurabilir.

## <a name="add-a-drillthrough-filter"></a>Detaylandırma filtresi ekleme
Power BI hizmetinde ve Power BI Desktop'ta tedarikçi, müşteri veya üretici gibi belirli bir varlığa odaklanan *hedef* rapor sayfaları oluşturabilirsiniz. Artık kullanıcılar, diğer rapor sayfalarında söz konusu varlığa ilişkin veri noktasına sağ tıklayarak, odaklanılmış sayfada detaylandırma yapabilirler.

### <a name="create-a-drillthrough-filter"></a>Detaylandırma filtresi oluşturma
Örneği takip etmek için Yükle [müşteri kârlılığı örneği](sample-customer-profitability.md). İdari işletme alanlarına odaklanan bir sayfa istediğinizi düşünelim.

1. **Raporu düzenle**'yi seçerek raporu Düzenleme görünümünde açın.
   
   ![Raporu düzenle düğmesi](media/power-bi-report-add-filter/power-bi-edit-view.png)

1. Rapora yeni bir sayfa ekleyip sayfayı **Team Executive** olarak adlandırın. Bu sayfa, detaylandırmanın *hedef* sayfası olacaktır.
2. İdari ekibin işletme alanlarına yönelik ana ölçümleri takip eden görselleştirmeleri ekleyin.    
3. Detaylandırma filtreleri bölmesine **Executive > Executive Name** seçeneğini ekleyin.    
   
    ![Detaylandırma filtreleri için bir değer ekleyin](media/power-bi-report-add-filter/power-bi-drillthrough-filter.png)
   
    Power BI'ın rapor sayfasına bir geri oku eklediğine dikkat edin.  Geri okunu seçen kullanıcılar, detaylandırma seçeneğini belirlerken bulundukları sayfa olan *kaynak* rapor sayfasına geri dönerler. Geri oku, yalnızca Okuma görünümü'nde çalışır.
   
     ![Geri oku](media/power-bi-report-add-filter/power-bi-back-arrow.png)

### <a name="use-the-drillthrough-filter"></a>Detaylandırma filtresini kullanma
Detaylandırma filtresinin nasıl çalıştığını görelim.

1. **Team Scorecard** rapor sayfasına gidin.    
2. Andrew Ma olduğunuzu ve yalnızca verilerinizi gösterecek şekilde filtrelenen Team Executive rapor sayfasını görmek istediğinizi düşünelim.  Detaylandırma menü seçeneğini açmak için sol üstteki alan grafiğinde bulunan herhangi bir yeşil veri noktasına sağ tıklayın.
   
    ![Detaylandırma eylemi Başlat](media/power-bi-report-add-filter/power-bi-drillthrough.png)
3. **Team Executive** adlı rapor sayfasında detaylandırma yapmak için **Detaylandırma > Team Executive** seçeneğini belirleyin. Sayfa, sağ tıkladığınız veri noktası (bu örnekte, Andrew Ma) hakkındaki bilgileri gösterecek şekilde filtrelenir. Yalnızca Detaylandırma filtreleri kutusundaki alan detaylandırma rapor sayfasına geçirilir.  
   
    ![Detaylandırma eylemi seçin](media/power-bi-report-add-filter/power-bi-drillthrough-executive.png)

## <a name="add-a-report-level-filter-to-filter-an-entire-report"></a>Rapor düzeyi filtresi tüm rapora ekleyin.

1. **Raporu düzenle**'yi seçerek raporu Düzenleme görünümünde açın.
   
   ![Raporu düzenle düğmesi](media/power-bi-report-add-filter/power-bi-edit-view.png)

2. Zaten açık değillerse, görsel öğeler ve filtreler bölmesini ve alanlar bölmesini açın.
3. Alanlar bölmesinden yeni rapor düzeyi filtresi olarak eklemek istediğiniz alanı seçip **Rapor düzeyi filtreleri** alanına sürükleyin.  
4. Filtre uygulamak istediğiniz değerleri seçin.

    Etkin sayfadaki ve raporda bulunan tüm sayfalardaki görseller, yeni filtreyi yansıtacak şekilde değişir. Raporunuzu filtreli olarak kaydederseniz raporu okuyan kişiler, değerleri seçerek veya temizleyerek Okuma görünümünde filtre ile etkileşim kurabilir.

1. Önceki rapor sayfasına geri dönmek için geri okunu seçin.

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme

- Görsel düzeyi ve sayfa düzeyi filtrenizin farklı sonuçlar döndürebileceği durumlar vardır.  Örneğin, bir görsel düzeyi filtresi eklediğinizde Power BI, toplanan sonuçlarda filtre uygular.  Varsayılan toplama, Toplam'dır ancak [toplama türünü değiştirebilirsiniz](service-aggregates.md).  

    Sonra bir görsel düzeyi filtresi eklediğinizde ise Power BI, toplama yapmadan filtre uygular.  Bu toplama yapmaz çünkü bir sayfada her biri farklı toplama türlerini kullanabilen pek çok görsel olabilir.  Bu nedenle filtre, her bir veri satırına uygulanır.

- Alanlar bölmesini görmüyorsanız rapor [Düzenleme görünümü](service-interact-with-a-report-in-editing-view.md)'nde bulunduğunuzdan emin olun.    
- Filtrelerde çok fazla değişiklik yaptıysanız ve rapor yazarı varsayılan ayarlarına geri dönmek istiyorsanız, üst menü çubuğundan **Varsayılana sıfırla**’yı seçin.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI Filtreler bölmesine ilişkin tura katılın](consumer/end-user-report-filter.md)

[Raporlarda filtreleme ve vurgulama](power-bi-reports-filters-and-highlighting.md)

[Okuma görünümünde filtreler ve vurgulama ile etkileşim kurma](consumer/end-user-reading-view.md)

[Rapor görsellerinin birbirini çapraz filtreleme ve çapraz vurgulama şeklini değiştirme](consumer/end-user-interactions.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

