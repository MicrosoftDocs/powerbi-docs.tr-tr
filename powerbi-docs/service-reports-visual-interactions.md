---
title: Bir rapordaki görsellerin etkileşim kurma biçimini değiştirme
description: Microsoft Power BI hizmeti raporunda ve bir Power BI Desktop raporunda Görsel etkileşimler oluşturmaya ilişkin belgeler.
author: mihart
ms.reviewer: ''
featuredvideoid: N_xYsCbyHPw
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 11/11/2019
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 2485d9120b10b41d193189de383a1a92b15378d5
ms.sourcegitcommit: 0d7ad791a2d2bef45d5d60e38e0af4c9fc22187b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74010967"
---
# <a name="change-how-visuals-interact-in-a-power-bi-report"></a>Power BI raporunda görsellerin etkileşim kurma biçimini değiştirme
Bir rapor için düzenleme izinleriniz varsa, bir rapor sayfasındaki görsellerin birbirlerini nasıl etkileyeceğini değiştirmek için **Görsel etkileşimleri** kullanabilirsiniz. 

## <a name="introduction-to-visual-interactions"></a>Görsel etkileşimlere giriş
Varsayılan olarak, bir rapor sayfasındaki görselleştirmeleri kullanıp sayfadaki diğer görselleştirmeler için çapraz filtreleme ve çapraz vurgulama işlemleri gerçekleştirebilirsiniz.
Örneğin, bir harita görselleştirmesinde bir eyaleti seçtiğinizde görselleştirme, yalnızca söz konusu eyaletle ilgili verilerin görüntülenmesi için çizgi grafiği filtreler ve sütun grafiğini vurgular.
Bkz. [Filtreleme ve vurgulama hakkında](power-bi-reports-filters-and-highlighting.md). Ayrıca, [ayrıntılara gitmeyi](consumer/end-user-drill.md) destekleyen bir görselleştirmeniz varsa, bir görselleştirmenin ayrıntısına inmek rapor sayfasındaki diğer görselleştirmeleri varsayılan olarak etkilemez. Ancak bu varsayılan davranışların her ikisi de geçersiz kılınabilir ve etkileşimler, görselleştirme temelinde ayarlanabilir.

Bu makalede, Power BI Desktop'ta **görsel etkileşimlerin** nasıl kullanılacağı gösterilir. İşlem, Power BI hizmeti [Düzenleme görünümüyle](service-interact-with-a-report-in-editing-view.md) aynıdır. Yalnızca Okuma görünüm erişiminiz varsa veya rapor sizinle paylaşıldıysa, görsel etkileşimler ayarlarını değiştiremezsiniz.

Görselleştirmeleri *filtrelemek* ve *vurgulamak* için **Filtreler** bölmesini kullandığınızda gerçekleşen davranış ile burada açıklanan davranış arasındaki farkı belirtmek için *çapraz filtreleme* ve *çapraz vurgulama* terimleri kullanılmıştır.  

> [!NOTE]
> Bu videoda Power BI Desktop'ın ve Power BI hizmetinin eski sürümleri kullanılır. 
>
>

<iframe width="560" height="315" src="https://www.youtube.com/embed/N_xYsCbyHPw?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>


## <a name="enable-the-visual-interaction-controls"></a>Görsel etkileşim denetimlerini etkinleştirme
Rapor üzerinde düzenleme izinleriniz varsa görsel etkileşim denetimlerini açabilir ve rapor sayfanızda görselleştirmelerin birbirlerini nasıl filtrelediğini ve vurguladığını özelleştirebilirsiniz. 

1. Etkin duruma getirmek için bir görselleştirmeyi seçin.  
2. **Görsel Etkileşimler** seçeneklerini görüntüleyin.
    

    - Masaüstü'nde **Biçim > Etkileşimler**’i seçin.

        ![Biçim’i ve sonra Etkileşimler’i seçme](media/service-reports-visual-interactions/power-bi-interaction.png)

    - Power BI hizmetinde, raporu Düzenleme görünümünde açın ve rapor menü çubuğunda açılan listeyi seçin.

        ![Görsel etkileşimler açılan menüsü](media/service-reports-visual-interactions/power-bi-service.png)

3. Görselleştirme etkileşimi denetimlerini görüntülemek için **Etkileşimleri düzenle**’yi seçin. Power BI, rapor sayfasındaki diğer tüm görselleştirmelere filtreleme ve vurgulama simgeleri ekler. Şimdi seçilen görselleştirmenin rapor sayfasındaki diğer görselleştirmelerle etkileşim kurma biçimini değiştirebilirsiniz.
   
    ![Görsel etkileşimlerin açık olduğu rapor](media/service-reports-visual-interactions/power-bi-turn-on.png)


## <a name="change-the-interaction-behavior"></a>Etkileşim davranışını değiştirme
Rapor sayfanızda her görselleştirmeyi teker teker seçerek görselleştirmelerinizin etkileşim kurma biçimini öğrenin.  Bir veri noktasını, çubuğu veya şekli seçin ve bunun diğer görselleştirmeler üzerindeki etkisini izleyin. Tercih ettiğiniz davranışı görmüyorsanız, etkileşimleri değiştirebilirsiniz. Bu değişiklikler raporla birlikte kaydedilir, dolayısıyla hem siz hem de rapor tüketicileriniz aynı görsel etkileşim deneyimini elde eder.


**Seçili görselleştirmenin**, diğer görselleştirmeler üzerinde nasıl bir etkisi olması gerektiğini belirleyin.  Ayrıca, isteğe bağlı olarak, bu işlemi rapor sayfasındaki tüm görselleştirmeler için yineleyebilirsiniz.
   
   * Görselleştirmeyi çapraz filtrelemesi gerekiyorsa **filtre** simgesini ![filtre simgesi](media/service-reports-visual-interactions/power-bi-filter-icon.png) seçin.
   * Görselleştirmeyi çapraz vurgulaması gerekiyorsa **vurgu** simgesini ![vurgu simgesi](media/service-reports-visual-interactions/power-bi-highlight-icon.png) seçin.
   * Herhangi bir etkisinin olmaması gerekiyorsa **etkisi yok** simgesini ![etkisi yok simgesi](media/service-reports-visual-interactions/power-bi-no-impact.png) seçin.

## <a name="change-the-interactions-of-drillable-visualizations"></a>Detaylandırılabilir görselleştirmelerin etkileşimlerini değiştirme
[Bazı Power BI görselleştirmeleri detaylandırılabilir](consumer/end-user-drill.md). Varsayılan olarak bir görselleştirmeyi detaylandırdığınızda, bu işlem rapor sayfasındaki diğer görselleştirmeleri etkilemez. Ama bu davranış değiştirilebilir. 

1. Detaylandırılabilir görseli seçip etkin duruma getirin. 

> [!TIP]
> [İnsan Kaynakları örnek PBIX dosyasını](https://download.microsoft.com/download/6/9/5/69503155-05A5-483E-829A-F7B5F3DD5D27/Human%20Resources%20Sample%20PBIX.pbix) kullanarak bunu kendiniz deneyin. **New hires** sekmesinde detaya gitme özelliği olan bir sütun grafik vardır.
>


2. Menü çubuğunda **Biçim** > **Diğer görselleri detaylandırma filtreleri**'ni seçin.  Bundan sonra bir görselleştirmede ayrıntıya indiğinizde (ve çıktığınızda), rapor sayfasındaki diğer görselleştirmeler geçerli ayrıntıya gitme seçiminizi yansıtacak şekilde değişir. 

    ![Diğer görselleri detaylandırma filtreleri](media/service-reports-visual-interactions/power-bi-drill.png)geçin.
    
## <a name="next-steps"></a>Sonraki adımlar
[Power BI raporlarındaki filtreleme ve vurgulama](power-bi-reports-filters-and-highlighting.md)