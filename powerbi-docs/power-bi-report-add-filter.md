---
title: Bir rapora görselleştirme, sayfa, detaylandırma veya rapor filtresi ekleme
description: Power BI'da bir rapora sayfa filtresi, görselleştirme filtresi veya rapor filtresi ekleme
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 05/26/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: c8f99cf9c4d0645638b2ef300606f89a2d28aa0d
ms.sourcegitcommit: 0ff358f1ff87e88daf837443ecd1398ca949d2b6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/21/2018
ms.locfileid: "46545980"
---
# <a name="add-a-filter-to-a-power-bi-service-report-in-editing-view"></a>Bir Power BI hizmet raporuna filtre ekleme (Düzenleme görünümünde)
> [!TIP]
> Öncelikle [Power BI raporlarındaki filtreler ve vurgulama hakkında](power-bi-reports-filters-and-highlighting.md) başlıklı makaleyi okumanızı öneririz.

Bu makaledeki örneklerde, Power BI hizmeti gösterilmektedir. Ancak adımlar, Power BI Desktop ile neredeyse aynıdır.
> 
> 

## <a name="what-is-the-difference-between-report-filters-in-editing-view-versus-reading-view"></a>Düzenleme Görünümü'ndeki ve Okuma Görünümü'ndeki rapor filtreleri arasındaki fark nedir?
Raporlarla etkileşim kurmak için kullanabileceğiniz iki mod vardır: [Okuma Görünümü](consumer/end-user-reading-view.md) ve [Düzenleme Görünümü](service-interact-with-a-report-in-editing-view.md).  Kullanabileceğiniz filtreleme özellikleri hangi modda olduğunuza bağlıdır.

* Düzenleme Görünümü'nde rapor ve sayfa filtrelerinin yanı sıra görsel filtreler ekleyebilirsiniz. Raporu kaydettiğinizde filtreler de birlikte kaydedilir. Okuma Görünümü'nde rapora göz atan kişiler eklediğiniz filtrelerle etkileşim kurabilir.
* Okuma Görünümü'nde, önceden raporda bulunan tüm rapor, detaylandırma, sayfa ve görsel filtreler ile etkileşim kurabilirsiniz ancak yeni filtreler ekleyemezsiniz. Ancak, raporu mobil uygulamada görüntüleseniz ve rapordan çıkıp daha sonra geri dönseniz bile, Filtreler bölmesinde yaptığınız değişiklikler rapora kaydedilir.  

> [!NOTE]
> Bu makalede rapor **Düzenleme Görünümü**'nde nasıl filtre oluşturabileceğiniz açıklanmaktadır.  Okuma Görünümü'ndeki filtreler hakkında daha fazla bilgi için [rapor Okuma Görünümü'nde filtrelerle etkileşim kurma](consumer/end-user-reading-view.md) başlıklı makaleye bakın.


## <a name="filters-available-in-the-power-bi-filters-pane"></a>Power BI'ın *Filtreler* bölmesinde filtreler mevcuttur
Masaüstü veya Power BI hizmeti kullanılırken, rapor tuvalinin sağ kenarında Filtreler bölmesi görüntülenir. Filtreler bölmesini görmüyorsanız bölmeyi genişletmek için sağ üst köşedeki ">" simgesini seçin.

Dört tür filtre vardır.

- **Sayfa filtresi**, rapor sayfasındaki tüm görsellere uygulanır     
- **Görsel filtresi**, bir rapor sayfasındaki tek bir görsele uygulanır    
- **Detaylandırma filtresi**, bir rapordaki tek bir varlığa uygulanır    
- **Rapor filtresi**, rapordaki tüm sayfalara uygulanır    

    ![Okuma görünümünde filtre bölmesi](media/power-bi-report-add-filter/power-bi-add-filter-reading-view.png)

Filtreler *kalıcı* olduğu için, rapordan çıktığınızda Power BI yaptığınız filtre, dilimleyici ve diğer veri görünümü değişikliklerini tutar. Bu nedenle, rapora geri döndüğünüzde kaldığınız yerden devam edebilirsiniz. Filtre değişikliklerinizin kalıcı olmasını istemiyorsanız üst menü çubuğundan **Varsayılana sıfırla**’yı seçin.

![kalıcı filtre düğmesi](media/power-bi-report-add-filter/power-bi-reset-to-default.png)

## <a name="add-a-filter-to-a-specific-visualization-aka-visual-filter"></a>Belirli bir görselleştirmeye filtre ekleme (başka bir deyişle, görsel filtresi)
Bunu yapmanın 2 yolu vardır: 

* görselleştirme tarafından kullanılmakta olan bir alanı filtreleme
* görselleştirme tarafından kullanılmayan bir alan belirleyip söz konusu alanı doğrudan **Görsel düzeyi filtreleri** demetine ekleme.

### <a name="by-filtering-the-fields-already-in-the-visualization"></a>Görselleştirmede bulunan alanları filtreleme
1. [Raporunuzu Düzenleme Görünümü'nde](consumer/end-user-reading-view.md) açın.
   
   ![](media/power-bi-report-add-filter/power-bi-edit-view.png)
2. Görsel Öğeler ve Filtreler bölmesini ve Alanlar bölmesini açın (zaten açık değillerse).
   
   ![](media/power-bi-report-add-filter/power-bi-display-panes.png)
3. Bir görseli seçerek etkin hale getirin. Görsel tarafından kullanılmakta olan tüm alanlar, **Alanlar** bölmesinde tanımlanır. Bunlar ayrıca **Görsel düzeyi filtreleri** başlığı altındaki **Filtreler** bölmesinde de listelenir.
   
   ![](media/power-bi-report-add-filter/power-bi-default-visual-filter.png)
4. Bu noktada, görselleştirme tarafından kullanılmakta olan bir alana filtre ekleyeceğiz. 
   
   * **Görsel düzeyi filtreleri** alanına gidin ve filtrelemek istediğiniz alanı genişletmek için oku seçin. Bu örnekte, **StoreNumberName** alanını filtreleyeceğiz
     
      ![](media/power-bi-report-add-filter/power-bi-visual-level-filter.png) 
   * **Temel**, **Gelişmiş** veya **Üst N** filtreleme denetimlerinden birini ayarlayın (bkz. [Rapor filtrelerini kullanma](consumer/end-user-report-filter.md)). Bu örnekte, Temel filtrelemeyi seçip 10, 11, 15 ve 18 sayılarının yanına onay işaretleri koyacağız.
     
      ![](media/power-bi-report-add-filter/power-bi-basic-filters.png) 
   * Görsel, yeni filtreyi yansıtacak şekilde değişir. Raporunuzu filtreli olarak kaydederseniz raporu okuyan kişiler, değerleri seçerek veya temizleyerek Okuma Görünümü'nde filtre ile etkileşim kurabilir.
     
      ![](media/power-bi-report-add-filter/power-bi-filter-effect.png)
5. Şimdi de görselleştirmemize bir Görsel düzeyi filtresi olarak yepyeni bir alan ekleyelim.
   
   * Alanlar bölmesinden yeni görsel düzeyi filtresi olarak eklemek istediğiniz alanı seçip **Görsel düzeyi filtreleri alanına** sürükleyin.  Bu örnekte, **Görsel düzeyi filtreleri** demetine **District Manager** öğesini sürükleyip yalnızca Andrew Ma seçeneğini belirleyeceğiz. 
     
      ![](media/power-bi-report-add-filter/power-bi-andrew.png)
   * Görselleştirmenin kendisine **District Manager** öğesinin *eklenmediğine* dikkat edin. Görselleştirme hâlâ Eksen olarak **StoreNumberName** ve Değer olarak **This Year Sales** alanlarından oluşmaktadır.  
     
      ![](media/power-bi-report-add-filter/power-bi-visualization.png)
   * Ayrıca görselleştirmenin kendisi de bu işlemden sonra, belirtilen mağazalar için yalnızca Andrew'un bu yılki satışlarını gösterecek şekilde filtrelenmiştir.
     
     ![](media/power-bi-report-add-filter/power-bi-filtered-andrew.png)

## <a name="add-a-filter-to-an-entire-page-aka-page-view-filter"></a>Tüm sayfaya filtre ekleme (başka bir deyişle, sayfa görünümü filtresi)
1. [Raporunuzu Düzenleme Görünümü'nde](consumer/end-user-reading-view.md) açın.
2. Görsel Öğeler ve Filtreler bölmesini ve Alanlar bölmesini açın (zaten açık değillerse).
3. Alanlar bölmesinden yeni sayfa düzeyi filtresi olarak eklemek istediğiniz alanı seçip **Sayfa düzeyi filtreleri** alanına sürükleyin.  
4. Filtrelemek istediğiniz değerleri seçip **Temel** veya **Gelişmiş** filtreleme denetimlerini belirleyin (bkz. [Rapor filtrelerini kullanma](consumer/end-user-report-filter.md)).
   
   Sayfada bu filtreden etkilenen tüm görselleştirmeler, yapılan değişikliği yansıtacak şekilde yeniden çizilir. 
   
   ![](media/power-bi-report-add-filter/filterpage.gif)

Raporunuzu filtreli olarak kaydederseniz raporu okuyan kişiler, değerleri seçerek veya temizleyerek Okuma Görünümü'nde filtre ile etkileşim kurabilir.

## <a name="add-a-drillthrough-filter"></a>Detaylandırma filtresi ekleme
Power BI hizmetinde ve Power BI Desktop'ta tedarikçi, müşteri veya üretici gibi belirli bir varlığa odaklanan *hedef* rapor sayfaları oluşturabilirsiniz. Artık kullanıcılar, diğer rapor sayfalarında söz konusu varlığa ilişkin veri noktasına sağ tıklayarak, odaklanılmış sayfada detaylandırma yapabilirler.

### <a name="create-a-drillthrough-filter"></a>Detaylandırma filtresi oluşturma
Birlikte ilerlemek için, Müşteri Kârlılığı örneğini Düzenleme görünümü'nde açın. İdari işletme alanlarına odaklanan bir sayfa istediğinizi düşünelim.   

1. Rapora yeni bir sayfa ekleyip sayfayı **Team Executive** olarak adlandırın. Bu, detaylandırmanın *hedef* sayfası olacaktır.
2. İdari ekibin işletme alanlarına yönelik ana ölçümleri takip eden görselleştirmeleri ekleyin.    
3. Detaylandırma filtreleri bölmesine **Executive > Executive Name** seçeneğini ekleyin.    
   
    ![](media/power-bi-report-add-filter/power-bi-drillthrough-filter.png)
   
    Power BI'ın rapor sayfasına bir geri oku eklediğine dikkat edin.  Geri okunu seçen kullanıcılar, detaylandırma seçeneğini belirlerken bulundukları sayfa olan *kaynak* rapor sayfasına geri dönerler. Geri oku, yalnızca Okuma görünümü'nde çalışır.
   
     ![](media/power-bi-report-add-filter/power-bi-back-arrow.png)

### <a name="use-the-drillthrough-filter"></a>Detaylandırma filtresini kullanma
Detaylandırma filtresinin nasıl çalıştığını görelim.

1. **Team Scorecard** rapor sayfasına gidin.    
2. Andrew Ma olduğunuzu ve yalnızca verilerinizi gösterecek şekilde filtrelenen Team Executive rapor sayfasını görmek istediğinizi düşünelim.  Detaylandırma menü seçeneğini açmak için sol üstteki alan grafiğinde bulunan herhangi bir yeşil veri noktasına sağ tıklayın.
   
    ![](media/power-bi-report-add-filter/power-bi-drillthrough.png)
3. **Team Executive** adlı rapor sayfasında detaylandırma yapmak için **Detaylandırma > Team Executive** seçeneğini belirleyin. Sayfa, sağ tıkladığınız veri noktası (bu örnekte, Andrew Ma) hakkındaki bilgileri gösterecek şekilde filtrelenir. Yalnızca Detaylandırma filtreleri kutusundaki alan detaylandırma rapor sayfasına geçirilir.  
   
    ![](media/power-bi-report-add-filter/power-bi-drillthrough-executive.png)

## <a name="add-a-filter-to-an-entire-report-aka-report-filter"></a>Tüm rapora filtre ekleme (başka bir deyişle, Rapor filtresi)
1. [Raporunuzu Düzenleme Görünümü'nde](consumer/end-user-reading-view.md) açın.
2. Görsel Öğeler ve Filtreler bölmesini ve Alanlar bölmesini açın (zaten açık değillerse).
3. Alanlar bölmesinden yeni rapor düzeyi filtresi olarak eklemek istediğiniz alanı seçip **Rapor düzeyi filtreleri** alanına sürükleyin.  
4. Filtrelemek istediğiniz değerleri seçin (bkz. [Rapor filtrelerini kullanma](consumer/end-user-report-filter.md)).

    Etkin sayfadaki ve raporda bulunan tüm sayfalardaki görseller, yeni filtreyi yansıtacak şekilde değişir. Raporunuzu filtreli olarak kaydederseniz raporu okuyan kişiler, değerleri seçerek veya temizleyerek Okuma Görünümü'nde filtre ile etkileşim kurabilir.

1. Önceki rapor sayfasına geri dönmek için geri okunu seçin.

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme

- Görsel düzeyi ve sayfa düzeyi filtrenizin farklı sonuçlar döndürebileceği durumlar vardır.  Örneğin, bir görsel düzeyi filtresi eklediğinizde Power BI, toplanan sonuçlarda filtre uygular.  Varsayılan toplama, Toplam'dır ancak [toplama türünü değiştirebilirsiniz](service-aggregates.md).  

    Sonra bir görsel düzeyi filtresi eklediğinizde ise Power BI, toplama yapmadan filtre uygular.  Bir sayfada her biri farklı toplama türlerini kullanabilen pek çok görsel olduğu için bunu yapar.  Bu nedenle filtre, her bir veri satırına uygulanır.

- Alanlar bölmesini görmüyorsanız rapor [Düzenleme görünümü](service-interact-with-a-report-in-editing-view.md)'nde bulunduğunuzdan emin olun.    
- Filtrelerde çok fazla değişiklik yaptıysanız ve rapor yazarı varsayılan ayarlarına geri dönmek istiyorsanız, üst menü çubuğundan **Varsayılana sıfırla**’yı seçin.

## <a name="next-steps"></a>Sonraki adımlar
 [Rapor filtrelerini kullanma](consumer/end-user-report-filter.md)

  [Raporlarda filtreleme ve vurgulama](power-bi-reports-filters-and-highlighting.md)

[Okuma Görünümü'nde filtreler ve vurgulama ile etkileşim kurma](consumer/end-user-reading-view.md)

[Rapor görsellerinin birbirini çapraz filtreleme ve çapraz vurgulama şeklini değiştirme](consumer/end-user-interactions.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

