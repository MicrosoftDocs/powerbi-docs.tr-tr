---
title: "Bir rapordaki görsellerin etkileşim kurma biçimini değiştirme"
description: "Microsoft Power BI raporlarında Görsel etkileşimler oluşturmaya ilişkin belgeler."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: N_xYsCbyHPw
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/25/2017
ms.author: mihart
ms.openlocfilehash: 126bd40e98a88138a2732155f9792d65666e52c7
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2017
---
# <a name="visualization-interactions-in-a-power-bi-report"></a>Power BI raporlarındaki görselleştirme etkileşimleri
Varsayılan olarak, bir rapor sayfasındaki görselleştirmeleri kullanıp sayfadaki diğer görselleştirmeler için çapraz filtreleme ve çapraz vurgulama işlemleri gerçekleştirebilirsiniz.
Örneğin, bir harita görselleştirmesinde bir eyaleti seçtiğinizde görselleştirme, yalnızca söz konusu eyaletle ilgili verilerin görüntülenmesi için çizgi grafiği filtreler ve sütun grafiğini vurgular.
Bkz. [Filtreleme ve vurgulama hakkında](power-bi-reports-filters-and-highlighting.md).

Bu varsayılan davranışı değiştirmek için **Görsel Etkileşimler** denetimini kullanın. Görsel etkileşimler yalnızca [Düzenleme modunda](service-interact-with-a-report-in-editing-view.md) kullanılabilir. Sizinle bir rapor paylaşıldığında Görsel Etkileşimler'e erişemezsiniz.

> [!NOTE]
> Görselleştirmeleri filtrelemek ve vurgulamak için **Filtreler**  bölmesini kullandığınızda gerçekleşen davranış ile burada açıklanan davranış arasındaki farkı belirtmek için *çapraz filtreleme* ve *çapraz vurgulama* terimleri kullanılmıştır.  
> 
> 

<iframe width="560" height="315" src="https://www.youtube.com/embed/N_xYsCbyHPw?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

1. Etkin duruma getirmek için bir görselleştirmeyi seçin.  
2. Üst kısımda bulunan menü çubuğunda **Görsel Etkileşimler**'i seçerek bu denetimi etkinleştirin. Rapor sayfasındaki diğer görselleştirmelerin üzerine geldiğinizde filtre ve vurgu simgelerinin göründüğünü fark edersiniz.
   
    ![](media/service-reports-visual-interactions/pbi-visual-interaction-icon.png)
3. Seçili görselleştirmenin, diğer görselleştirmeler üzerinde nasıl bir etkisi olması gerektiğini belirleyin.  
   
   * Diğer görselleştirmeyi çapraz filtrelemesi gerekiyorsa **filtre** simgesini ![](media/service-reports-visual-interactions/pbi-filter-icon-outlined.png) seçin.
   * Diğer görselleştirmeyi çapraz vurgulaması gerekiyorsa **vurgu** simgesini ![](media/service-reports-visual-interactions/pbi-highlight-icon-outlined.png) seçin.
   * Herhangi bir etkisi olmamalıysa **etkisi yok** simgesini ![](media/service-reports-visual-interactions/pbi-noimpact-icon-outlined.png) seçin.
4. İsteğe bağlı olarak, bu işlemi rapor sayfasındaki tüm görselleştirmeler için yineleyin.

### <a name="next-steps"></a>Sonraki adımlar
[Rapor filtrelerini kullanma](power-bi-how-to-report-filter.md)

[Raporlarda filtreleme ve vurgulama](power-bi-reports-filters-and-highlighting.md)

[Power BI - Temel Kavramlar](service-basic-concepts.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

