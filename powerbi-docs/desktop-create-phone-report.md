---
title: "Power BI telefon uygulamaları için en iyi duruma getirilmiş raporlar oluşturma"
description: "Power BI Desktop'ta rapor sayfalarını Power BI telefon uygulamaları için en iyi duruma getirmeyi öğrenin."
services: powerbi
documentationcenter: 
author: maggiesMSFT
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/08/2017
ms.author: maggies
ms.openlocfilehash: 0dd906bc1b165793e9ff91f64324eeb8e1d1266c
ms.sourcegitcommit: b780b7108fd9b52398b8377b52836f0e0fedc96e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/09/2017
---
# <a name="create-reports-optimized-for-the-power-bi-phone-apps"></a>Power BI telefon uygulamaları için en iyi duruma getirilmiş raporlar oluşturma
[Power BI Desktop'ta bir rapor oluşturduğunuzda](desktop-report-view.md) raporun telefona özgü bir sürümünü oluşturarak telefonlardaki mobil uygulamalarda daha iyi bir kullanım deneyimi sunmasını sağlayabilirsiniz. Raporunuzu telefon için uyarlamak üzere görsellerin yerini ve boyutunu değiştirmeniz ve en iyi deneyim için bazılarını hariç tutmanız gerekebilir. Bununla birlikte, telefonda görüntülendiğinde uygun şekilde yeniden boyutlandırılan [*esnek* görseller](#optimize-a-visual-for-any-size) ve [esnek dilimleyiciler](#enhance-slicers-to-to-work-well-in-phone-reports) oluşturabilirsiniz. Ayrıca, raporunuza filtre eklediyseniz bu filtreler telefon raporunda otomatik olarak görüntülenir. Raporunuzu okuyanlar bu filtreleri görebilir ve rapora uygulayabilir.

![Telefonda en iyi duruma getirilmiş rapor](media/desktop-create-phone-report/07-power-bi-phone-report-portrait.png)

## <a name="lay-out-a-report-page-for-the-phone-in-power-bi-desktop"></a>Power BI Desktop'ta bir rapor sayfasını telefona göre düzenleme
[Power BI Desktop'ta bir rapor oluşturduktan sonra](desktop-report-view.md) telefonlar için en iyi duruma getirebilirsiniz.

1. Power BI Desktop'ta sol gezinti çubuğundaki **Rapor Görünümü**'nü seçin.
   
    ![Rapor Görünümü simgesi](media/desktop-create-phone-report/pbi_reportviewinpbidesigner_changeview.png)
2. **Görünüm** sekmesinde **Telefon Düzeni**'ni seçin.  
   
    ![Telefon Düzeni simgesi](media/desktop-create-phone-report/power-bi-phone-layout-icon.png)
   
    Boş bir telefon tuvali göreceksiniz. Özgün rapor sayfanızdaki tüm görseller sağ taraftaki Görsel Öğeler bölmesinde listelenir.
3. Telefon düzenine eklemek istediğiniz görselleri Görsel Öğeler bölmesinden telefon tuvaline sürükleyin.
   
    Telefon raporları kılavuz düzeni kullanır. Mobil tuvale sürüklediğiniz görseller bu kılavuza yapışır.
   
    ![Görseli sürükleyip bırakma](media/desktop-create-phone-report/02_dragging_and_droping_a_vis.gif)
   
    Ana rapor sayfasındaki görsellerin bazılarını veya tümünü telefon rapor sayfasına ekleyebilirsiniz. Her görseli yalnızca bir kez ekleyebilirsiniz.
4. Kılavuz üzerindeki görselleri panolardaki ve mobil panolardaki kutucuklar gibi yeniden boyutlandırabilirsiniz.
   
   > [!NOTE]
   > Telefon raporu kılavuzu farklı boyutlardaki telefonlara göre değişir. Bu sayede raporunuz hem küçük hem de büyük ekranlı telefonlarda güzel görünür.
   > 
   > 
   
   ![Görsel boyutunu değiştirme](media/desktop-create-phone-report/03_resizing_a_viz_to_grid.gif)

## <a name="optimize-a-visual-for-any-size"></a>Görseli tüm boyutlar için en iyi duruma getirme
Pano veya raporunuzdaki görsellerin *esnek* hale gelip ekran boyutu ne olursa olsun maksimum sayıda veri ve öngörü görüntüleyecek şekilde dinamik olarak değişmesini sağlayabilirsiniz. 

Power BI, veri görüntüleme önceliğini görsel boyutuna göre değiştirir. Örneğin görselin küçülse dahi bilgilendirici olması için otomatik olarak boşluğu kaldırır ve açıklamayı görselin üst tarafına taşır.

![Esnek görsel yeniden boyutlandırma](media/desktop-create-phone-report/power-bi-responsive-visual.gif)

Her bir görsel için esneklik seçeneğini açıp kapatabilirsiniz. [Görselleri en iyi duruma getirme](desktop-create-responsive-visuals.md) hakkında daha fazla bilgi edinin.

## <a name="considerations-when-creating-phone-report-layouts"></a>Telefon rapor düzenlerini oluştururken dikkat edilecek noktalar
* Çok sayfalı raporlarda tüm sayfaları veya yalnızca birkaç tanesini en iyi duruma getirebilirsiniz. 
* Belirli bir rapor sayfası için arka plan rengi tanımladıysanız telefon raporunda da aynı arka plan rengi kullanılır.
* Biçimlendirme ayarlarını yalnızca telefon düzeni için değiştiremezsiniz. Ana ve mobil düzenlerin biçimlendirme özellikleri ortaktır. Örneğin yazı tipi boyutu aynı olacaktır.
* Bir görselin biçimini, veri kümesini, filtrelerini veya diğer özniteliklerini değiştirmek için normal rapor oluşturma moduna geçin.
* Power BI, mobil uygulamada telefon raporları için varsayılan başlıkları ve sayfa adlarını kullanır. Raporunuzdaki başlıklar ve sayfa adları için metin görselleri oluşturduysanız bunları telefon raporlarına eklemeniz önerilmez.     

## <a name="remove-a-visual-from-the-phone-layout"></a>Telefon düzenindeki görselleri kaldırma
* Telefon tuvali üzerinde kaldırmak istediğiniz görselin sağ üst köşesindeki X simgesine tıklayın veya görseli seçip **Sil**'e tıklayın.
  
   Bu işlem görseli yalnızca telefon düzeni tuvalinden kaldırır. Görsel ve özgün rapor etkilenmez.
  
   ![Görselleri kaldırma](media/desktop-create-phone-report/05_removing_a_vis.gif)

## <a name="enhance-slicers-to-to-work-well-in-phone-reports"></a>Dilimleyicileri telefon raporlarında iyi çalışacak şekilde geliştirme
Dilimleyiciler, rapor verilerinizin tuval üzerinde filtrelenmesini sağlar. Dilimleyicileri normal rapor oluşturma modunda tasarlarken telefon raporlarında daha kullanışlı hale getirmek için bazı dilimleyici ayarlarını değiştirebilirsiniz:

* Raporu okuyanların bir veya daha fazla öğeyi seçip seçemeyeceğine karar verin.
* Dilimleyicinin etrafına bir kutu yerleştirerek raporu taramayı kolaylaştırın.
* Dilimleyiciyi dikey, yatay veya *esnek* hale getirin. 

Dilimleyiciyi esnek hale getirirseniz boyutunu veya şeklini değiştirdiğinizde daha fazla ya da daha az seçenek görüntülenir. Dilimleyici uzun, kısa, geniş veya dar olabilir. Yeterince küçültürseniz rapor sayfasında bir filtre simgesine dönüşür. 

![Power BI'da esnek dilimleyici](media/desktop-create-phone-report/power-bi-slicer-2-rows.png)

[Esnek dilimleyiciler oluşturma](power-bi-slicer-filter-responsive.md) hakkında daha fazla bilgi edinin.

## <a name="publish-a-phone-report"></a>Telefon raporu yayımlama
* Raporunuzun telefon sürümünü yayımlamak için [ana raporu Power BI Desktop'tan Power BI hizmetine yayımlamanız](desktop-upload-desktop-files.md) yeterlidir, telefon sürümü de aynı anda yayımlanır.
  
    [Power BI'da paylaşım ve izinler](service-how-to-collaborate-distribute-dashboards-reports.md) hakkında daha fazla bilgi edinin.

## <a name="view-optimized-and-unoptimized-reports-on-a-phone"></a>En iyi duruma getirilmiş ve getirilmemiş raporları telefonda görüntüleme
Telefonlardaki mobil uygulamalarda Power BI en iyi duruma getirilmiş ve getirilmemiş telefon raporlarını otomatik olarak algılar. Telefon için en iyi duruma getirilmiş rapor varsa Power BI telefon uygulaması ilgili raporu otomatik olarak telefon raporu modunda açar.

Telefon için en iyi duruma getirilmiş rapor yoksa rapor en iyi duruma getirilmemiş, yatay görünümde açılır.  

Telefon raporu açıkken telefonun yatay hale getirilmesi durumunda raporun en iyi duruma getirilmiş olma durumundan bağımsız olarak rapor, özgün rapor düzeniyle ve en iyi duruma getirilmemiş görünümde açılır.

Yalnızca sayfaların bazılarını en iyi duruma getirdiyseniz okuyucular dikey görünümde raporun yalnızca yatay görünümde kullanılacağına dair bir ileti görür.

![Telefon sayfası en iyi duruma getirilmemiş](media/desktop-create-phone-report/06-power-bi-phone-report-page-not-optimized.png)

Raporu okuyanlar sayfayı yatay modda görmek için telefonlarını döndürebilir. [Telefonunuz için en iyi duruma getirilmiş Power BI raporlarıyla etkileşim kurma](mobile-apps-view-phone-report.md) hakkında daha fazla bilgi edinin.

## <a name="next-steps"></a>Sonraki adımlar
* [Power BI'da bir panonun telefon görünümünü oluşturma](service-create-dashboard-mobile-phone-view.md)
* [Telefonunuz için en iyi duruma getirilmiş Power BI raporlarını görüntüleme](mobile-apps-view-phone-report.md)
* [Tüm boyutlar için en iyi duruma getirilmiş esnek görseller oluşturma](desktop-create-responsive-visuals.md)
* Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

