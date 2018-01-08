---
title: "Power BI'daki Okuma Görünümü'nde bir raporla etkileşim kurma"
description: "Power BI'daki Okuma Görünümü'nde bir raporla etkileşim kurma"
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
ms.date: 12/21/2017
ms.author: mihart
ms.openlocfilehash: 1dc6ecab1b3504b658cd41a378a4c0f5e3c65187
ms.sourcegitcommit: 6ea8291cbfcb7847a8d7bc4e2b6abce7eddcd0ea
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="interact-with-a-report-in-reading-view-in-power-bi"></a>Power BI'daki Okuma Görünümü'nde bir raporla etkileşim kurma
## <a name="reading-view"></a>Okuma görünümü
Okuma görünümü, [Düzenleme görünümü](service-interact-with-a-report-in-editing-view.md) kadar etkileşimli olmasa da verilerinizi keşfetmenizi sağlayacak birçok seçenek sunmaktadır. Bu görünüm özellikle [sizinle paylaşılmış olan](service-share-dashboards.md) ve yalnızca Okuma Görünümü'nde açılabilen raporları görüntülemek için idealdir.

Okuma görünümü, verilerinizle oynayıp bilgi sahibi olmanın eğlenceli ve güvenli bir yoludur. Okuma Görünümü'nde sayfadaki görsellere çapraz vurgulama ve çapraz filtreleme uygulayabilirsiniz.  Görsellerin birindeki değerlerin birini vurguladığınızda veya seçtiğinizde diğer görseller üzerindeki etkisini de anında görebilirsiniz. Rapor sayfasına filtre eklemek, var olan filtreleri değiştirmek ve görselleştirme içindeki değerlerin sıralamasını değiştirmek için Filtre bölmesini kullanabilirsiniz. Yaptığınız filtreleme ve vurgulama işlemleri raporunuza kaydedilmez.

## <a name="cross-highlight-the-related-visualizations-on-a-page"></a>Sayfadaki ilgili görselleştirmeleri çapraz vurgulama
Tek bir rapor sayfasındaki görselleştirmeler birbirine "bağlıdır".  Başka bir deyişle, görselleştirmenizdeki değerlerin birini veya daha fazlasını seçtiğinizde aynı verileri kullanan diğer görselleştirmeler de yaptığınız seçime göre değişir.

![çapraz vurgulama](media/service-interact-with-a-report-in-reading-view/pagefilter3b.gif)

> [!NOTE]
> Bir görselleştirmede yer alan birden fazla öğeyi seçmek için CTRL tuşunu basılı tutun.
> 
> 

## <a name="hover-over-visual-elements-to-see-the-details"></a>Ayrıntıları görmek için görsel öğelerin üzerine gelme
![ayrıntıları görmek için öğelerin üzerine gelin](media/service-interact-with-a-report-in-reading-view/amarillachart.png)

## <a name="sort-the-data-in-a-visualization"></a>Görselleştirme içindeki verileri sıralama
Üç nokta (...) simgesini seçerek **Sıralama ölçütü**'nü açın. Sıralama ölçütü olarak kullanılacak alanı seçmek için açılan oku seçin veya AZ simgesini seçerek artan/azalan düzenler arasında geçiş yapın. 

![bir grafiği sıralama](media/service-interact-with-a-report-in-reading-view/pbi_changechartsort.gif) 

## <a name="interact-with-filters"></a>Filtrelerle etkileşim kurma
Rapor yazarının rapor sayfalarından birine filtre eklemesi durumunda Okuma Görünümü'nde bu filtrelerle etkileşim kurabilirsiniz. Yaptığınız değişiklikler raporla birlikte kaydedilmez.

1. Sağ üst köşedeki Filtre simgesini seçin.
   
   ![filtreler simgesini seçme](media/service-interact-with-a-report-in-reading-view/filters.png)  
2. Seçtiğiniz görsele (Görsel düzeyi filtreleri), rapor sayfasının tamamına (Sayfa düzeyi filtreleri) ve raporun tamamına (Rapor düzeyi filtreleri) uygulanmış olan tüm filtreleri görürsünüz.
   
   ![rapor filtresi türleri](media/service-interact-with-a-report-in-reading-view/power-bi-reading-filters.png)
3. Filtrelerden birinin üzerine gelip aşağı oku seçerek genişletin.
   
   ![filtreyi genişletme](media/service-interact-with-a-report-in-reading-view/power-bi-expan-filter.png)
4. Filtrelerde değişiklik yaparak görsellerin nasıl etkilendiğini inceleyin.  
   
   * Bu örnekte **Chain** için Sayfa düzeyi filtresi verilmiştir. Onay işaretlerini kullanarak **Lindseys**'i **Fashions Direct** olarak değiştirin.
     
     ![sayfa düzeyi filtresini değiştirme](media/service-interact-with-a-report-in-reading-view/power-bi-filter-chain.png)
   * İsterseniz silgi simgesini ![](media/service-interact-with-a-report-in-reading-view/power-bi-eraser-icon.png) veya iki mağaza zincirini birlikte seçerek **Chain** filtresini tamamen kaldırabilirsiniz.
   * **District** sayfa düzeyi filtresini seçip **Gelişmiş filtreleme** moduna geçin. Yalnızca **FD** ile başlayan ve 4 rakamını içermeyen bölgeleri göstermek için filtreleyin.
     
     ![gelişmiş filtreleme](media/service-interact-with-a-report-in-reading-view/power-bi-advanced-filter.png)

Daha fazla bilgi için bkz. [Raporlara filtre ekleme](power-bi-report-add-filter.md) ve [About filters and highlighting in reports (Rapordaki filtreler ve vurgulama özellikleri hakkında)](power-bi-reports-filters-and-highlighting.md).

## <a name="zoom-in-on-individual-visuals"></a>Görselleri yakınlaştırma
Görselin üzerine gelip **Odak modu** simgesini ![](media/service-interact-with-a-report-in-reading-view/pbi_popouticon.jpg) seçin. Bir görselleştirmeyi Odak modunda görüntülediğinizde aşağıda gösterildiği gibi rapor tuvalinin tamamını dolduracak şekilde genişletilir.

![odak modu](media/service-interact-with-a-report-in-reading-view/powerbi-focus-mode.png)

Aynı görselleştirmeyi menü çubukları, filtre bölmesi ve diğer görselleştirmeler olmadan görüntülemek için üst menü çubuğundaki **Tam Ekran** simgesini ![](media/service-interact-with-a-report-in-reading-view/power-bi-focus-icon.png) seçin.

![tam ekran modu](media/service-interact-with-a-report-in-reading-view/power-bi-full-screen.png)

Daha fazla bilgi için bkz. [Raporlar için odak modu](service-focus-mode.md) ve [Raporlar için Tam Ekran modu](service-fullscreen-mode.md)

## <a name="adjust-the-display-dimensions"></a>Görüntüleme boyutlarını ayarlama
Raporlar çok farklı cihazlarda görüntülenir ve bu cihazların ekran boyutlarıyla en/boy oranları birbirinden farklıdır.  Rapor, varsayılan oluşturma işlemi sonucunda cihazda görüntülemek istediğinizden farklı olabilir.  Ayarlamak için **Görünüm**'ü ve ardından şu öğeleri seçin:

* Sayfaya Sığdır: İçeriği, sayfaya en iyi sığacak şekilde ölçeklendirir
* Genişliğe Uydur: İçeriği, sayfa genişliğine göre ölçeklendirir
* Gerçek Boyut: İçeriği tam boyutuyla görüntüler  

    ![rapor Görünüm menüsü](media/service-interact-with-a-report-in-reading-view/power-bi-view.png)

  Okuma Görünümü'nde seçtiğiniz görüntüleme seçenekleri geçicidir, raporu kapattığınızda kaydedilmez.

  Daha fazla bilgi için bkz. [Eğitim: Rapordaki görünüm ayarlarını değiştirme](power-bi-change-report-display-settings.md).

##  <a name="open-the-selection-pane"></a>**Seçim** bölmesini açın
Rapor sayfasındaki görselleştirmeler arasında kolayca gezinebilirsiniz. Seçim bölmesini açmak için **Görünüm > Seçim bölmesi > Açık** yolunu izleyin.

![rapor Seçim bölmesi](media/service-interact-with-a-report-in-reading-view/power-bi-selection-pane.png)

Daha fazla bilgi için Rapor Seçim bölmesine bakın.

##    <a name="miscellaneous-other-interactions"></a>Çeşitli diğer etkileşimler
Okuma görünümü'nde raporla etkileşim kurmak için kullanabileceğiniz birçok yöntem vardır. Daha fazla bilgi edinmek için aşağıdaki bağlantıları kullanın.

- [Rapor kullanım ölçümlerini görüntüleme](service-usage-metrics.md)
- [İlgili panoları, raporları ve veri kümelerini görüntüleme](service-related-content.md)
- [Bir rapor sayfasına abone olma](service-report-subscribe.md)
- [Excel'de Çözümle](service-analyze-in-excel.md)
- [QR kodu oluşturma](service-create-qr-code-for-report.md)
- [Canlı sayfayı panoya sabitleme](service-dashboard-pin-live-tile-from-report.md)
- [Bildirim merkezindeki iletileri görüntüleme](service-notification-center.md)
- [Görselleştirmeleri bir panoya sabitleme](service-dashboard-pin-tile-from-report.md)

## <a name="next-steps"></a>Sonraki adımlar
[Power BI hizmetinde Okuma görünümü ve Düzenleme görünümü](service-reading-view-and-editing-view.md) sayfasına dönün

[Düzenleme görünümü'nü açma](service-reading-view-and-editing-view.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

