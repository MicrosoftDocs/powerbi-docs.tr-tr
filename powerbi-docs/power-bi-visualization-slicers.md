---
title: "Power BI'daki dilimleyiciler (Eğitim)"
description: "Eğitim: Power BI'daki dilimleyiciler"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: zIZPA0UrJyA
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 05/30/2017
ms.author: mihart
ms.openlocfilehash: b6ce0c396f4a189489b97fe5cd86ab5cd8dbcc35
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="slicers-in-power-bi-service-tutorial"></a>Power BI hizmetindeki dilimleyiciler (Eğitim)
Satıştan sorumlu Genel Müdür Yardımcınız, tüm bölümle ilgili olarak ve her bir District Manager için bazı ölçümlere göz atabilmek istiyor. Bu amaçla her yönetici için ayrı bir rapor sayfası oluşturabilir veya bir dilimleyici kullanabilir. Dilimleyici, sayfadaki diğer görselleştirmelerde gösterilen veri kümesi bölümünü daraltır.  Dilimleyiciler, filtrelemenin alternatif bir yoludur.

![](media/power-bi-visualization-slicers/slicer2.gif)

## <a name="when-to-use-a-slicer"></a>Dilimleyici ne zaman kullanılır?
Dilimleyiciler, aşağıdaki durumlarda harika bir seçim olacaktır.

* Daha kolay erişim sağlamak amacıyla, sık kullanılan veya önemli filtreleri rapor tuvalinde görüntülemek istiyorsanız.
* Filtreleme ayrıntılarını bulmak için bir açılan liste açmaya gerek kalmadan geçerli filtreli durumu daha kolay bir şekilde görmek istiyorsanız.
* Sütunları gizlemek istediğinizde ihtiyaç duymazsınız ancak yine de filtrelemek için bunları kullanarak daha daraltılmış ve net tablolar elde edersiniz.
* Daha odaklanmış raporlar oluşturmak için kullanabilirsiniz. Dilimleyiciler kayan nesneler olduğu için bunları raporun, kullanıcıların odaklanmasını istediğiniz bölümünün yanına yerleştirebilirsiniz.

## <a name="create-a-slicer"></a>Dilimleyici oluşturma
<iframe width="560" height="315" src="https://www.youtube.com/embed/zIZPA0UrJyA" frameborder="0" allowfullscreen></iframe>


1. [Retail Analysis Sample](sample-retail-analysis.md)'ı [Düzenleme Görünümü](service-interact-with-a-report-in-editing-view.md)'nde açın ve [yeni bir rapor sayfası ekleyin](power-bi-report-add-page.md).
2. Alanlar bölmesinden **District > District Manager** seçeneğini belirleyin.
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_chartfirst.png)
3. Görselleştirmeyi bir dilimleyiciye dönüştürün. Görsel Öğeler bölmesinde dilimleyici simgesini seçin.
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_select.png)

## <a name="format-the-slicer"></a>Dilimleyiciyi biçimlendirme
1. Görsel Öğeler bölmesinde, dilimleyici seçiliyken Biçim seçeneklerini görüntülemek için boya rulosu simgesini ![](media/power-bi-visualization-slicers/power-bi-paintroller.png) seçin.
2. **Genel > Ana hat rengi** açılan listesinde koyu mavi rengini seçtikten sonra **Ağırlık** değerini **6** olarak belirleyin.
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_outline2.png)
3. **Seçim Denetimleri** bölümünde varsayılan olarak **Tümünü Seç** **Kapalı** ve **Tek Seçim** **Açık** durumdadır. Bu, aynı anda birden fazla ad seçmek için CTRL tuşunu kullanmamız gerekeceği anlamına gelir. **Tümünü Seç**'i **Açık**, **Tek Seçim**'i ise **Kapalı** duruma getirin.
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_selectioncontrols2.png)
   
   * Dilimleyicide listenin en üstünde bir **Tümünü Seç** seçeneği belirir. **Tümünü Seç**'i işaretleyerek adların tümünü seçebilir veya tümünün seçimini kaldırabilirsiniz.
   * Bunun yanı sıra artık CTRL tuşunu kullanmak zorunda kalmadan birden çok ad seçebilirsiniz.
4. **Öğeler** bölümünde metin boyutunu 14 olarak artırın.  İş arkadaşlarınızın bu dilimleyiciyi kolayca fark edebilmesini istiyoruz.
5. Son olarak, **Yazı tipi rengi** değerini koyu kırmızı olarak ayarlayın.  Böylece dilimleyicimizdeki seçili adlar, seçili olmayan adlardan ayırt edilir.
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_font2.png)
6. Dilimleyicilere ilişkin diğer seçenekleri inceleyin.

## <a name="use-the-slicer-in-a-report"></a>Raporlarda dilimleyiciyi kullanma
1. Rapor sayfasına birkaç görselleştirme daha ekleyin veya [Retail Analysis Sample raporunu](sample-retail-analysis.md) açıp **District Monthly Sales** sekmesini seçin.
   
    ![](media/power-bi-visualization-slicers/power-bi-retail-sample.png)
2. Rapor sayfasını Carlos için dilimleyin. Diğer görselleştirmelerin bu seçimleri yansıtacak şekilde güncelleştirildiğini göreceksiniz.
   
    ![](media/power-bi-visualization-slicers/slicer2.gif)
3. Dilimleyiciyi District Manager soyadına göre alfabetik olarak sıralayın.  Dilimleyicinin sağ üst köşesindeki üç nokta simgesini (...) seçin ve **District Manager** seçeneğini belirleyin.
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_sort2.png)
   
    ![](media/power-bi-visualization-slicers/pbi_slicer_sorted.png)

## <a name="control-what-effect-the-slicer-has-on-other-visuals-on-the-page"></a>Dilimleyicinin sayfadaki diğer görseller üzerindeki etkisini denetleme
Dilimleyicinin rapor sayfasındaki görsellerden yalnızca bazılarını mı filtrelemesini istiyorsunuz?  Bunu ayarlamak için **Görsel etkileşimler** denetimini kullanın.

**NOT**: **Görsel Etkileşimler** denetimini görmüyorsanız ![](media/power-bi-visualization-slicers/power-bi-slicer-visual-interactions.png) simgesini arayın. İkisini de görmüyorsanız rapor [Düzenleme görünümü](service-reading-view-and-editing-view.md)'nün açık olduğundan emin olun.

1. Dilimleyiciyi etkin hale getirmek için seçin ve menü çubuğunda **Görsel etkileşimler** seçeneğini belirleyin.
   
    ![](media/power-bi-visualization-slicers/pbi-slicer-interactions.png)
2. Sayfadaki diğer tüm görsellerin üzerinde filtre denetimleri görünür. Dilimleyicinin bir görseli filtrelemesi gerekiyorsa **Filtre** simgesini seçin.  Dilimleyicinin görsel üzerinde herhangi bir etkisi olmaması gerekiyorsa **Hiçbiri** simgesini seçin.
   
    ![](media/power-bi-visualization-slicers/filter-controls.png)

Daha fazla bilgi için bkz. [Power BI raporlarındaki görsel etkileşimler](service-reports-visual-interactions.md).

## <a name="considerations-and-troubleshooting-slicers-in-power-bi"></a>Power BI'daki dilimleyiciler ile ilgili önemli noktalar ve sorun giderme
Power BI'daki dilimleyicileri kullanmaya ilişkin birkaç sınırlama vardır ve bu sınırlamalar aşağıda verilmiştir:

1. Dilimleyiciler giriş alanlarını desteklemez.
2. Tek bir dilimleyici bir raporun tamamında kullanılamaz. Bir dilimleyici yalnızca geçerli sayfayı etkiler.
3. Dilimleyiciler panolara sabitlenemez.
4. Detaya gitme özelliği, dilimleyiciler için desteklenmez.    
5. Dilimleyiciler, Görsel düzeyi filtrelerini desteklemez.

Power BI'ı iyileştirmeye yönelik fikirleriniz mi var? [Fikir sunun](https://ideas.powerbi.com/forums/265200-power-bi-ideas).

## <a name="next-steps"></a>Sonraki adımlar
 [Bir rapora görselleştirme ekleme](power-bi-report-add-visualizations-i.md)

 [Power BI'daki görselleştirme türleri](power-bi-visualization-types-for-reports-and-q-and-a.md)

 [Power BI - Temel Kavramlar](service-basic-concepts.md)

[Ücretsiz deneyin!](https://powerbi.com/)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

