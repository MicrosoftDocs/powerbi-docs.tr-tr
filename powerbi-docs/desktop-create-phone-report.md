---
title: Power BI mobil uygulamaları için raporları iyileştirme
description: Raporun telefon ve tabletlere özgü bir dikey sürümünü oluşturarak, Power BI mobil uygulamalarının rapor sayfalarını nasıl iyileştireceğinizi öğrenin.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/18/2019
ms.author: maggies
LocalizationGroup: Create reports
ms.openlocfilehash: 16af5a6c8b5341067c458329c68da0a1a0fe14a5
ms.sourcegitcommit: 7f27b9eb0e001034e672050735ab659b834c54a3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74311480"
---
# <a name="optimize-reports-for-the-power-bi-mobile-apps"></a>Power BI mobil uygulamaları için raporları iyileştirme
Dikey düzen oluşturarak mobil uygulamalarda rapor görüntüleme deneyimini geliştirebilirsiniz. Power BI Desktop ve Power BI hizmetinde, dikey modda en iyi deneyim için rapor görsellerini yeniden düzenleyebilir ve yeniden boyutlandırabilirsiniz.  

Bunun yerine bir mobil cihazda rapor görüntüleme hakkında bilgi mi arıyorsunuz? Şu hızlı başlangıcı deneyin: [Power BI mobil uygulamalarında pano ve raporları keşfetme](consumer/mobile/mobile-apps-quickstart-view-dashboard-report.md).

![Telefonda en iyi duruma getirilmiş rapor](media/desktop-create-phone-report/desktop-create-phone-report-1.png)

Bununla birlikte, her yerde uygun şekilde yeniden boyutlandırılan [esnek görseller](#optimize-a-visual-for-any-size) ve [esnek dilimleyiciler](#enhance-slicers-to-work-well-in-phone-reports) oluşturabilirsiniz. Raporunuza filtre eklediyseniz en iyi duruma getirilmiş raporda otomatik olarak görüntülenir.

## <a name="lay-out-a-portrait-version-of-a-report-page"></a>Rapor sayfasının dikey sürümünü düzenleme

Bir rapor oluşturduktan sonra, telefonlar ve tabletler için bunu iyileştirebilirsiniz.

1. Power BI Desktop’ın **Rapor** görünümünde, **Görünüm** sekmesinde **Telefon Düzeni**’ni seçin.  
   
    ![Telefon Düzeni simgesi](media/desktop-create-phone-report/desktop-create-phone-report-3.png)
   
    Power BI hizmetinde, **Raporu düzenle** > **Mobil Düzen**’i seçin.

    Şekli telefona benzeyen boş bir tuval görürsünüz. Özgün rapor sayfanızdaki tüm görseller sağ taraftaki **Görsel Öğeler** bölmesinde listelenir.

1. Telefon düzenine eklemek istediğiniz görselleri **Görsel Öğeler** bölmesinden telefon tuvaline sürükleyin.
   
    Telefon raporları kılavuz düzeni kullanır. Mobil tuvale sürüklediğiniz görseller bu kılavuza yapışır.
   
    ![Görseli sürükleyip bırakma](media/desktop-create-phone-report/desktop-create-phone-report-4.gif)
   
    Ana rapor sayfasındaki görsellerin bazılarını veya tümünü telefon rapor sayfasına ekleyebilirsiniz. Her görseli bir kez ekleyebilirsiniz, tüm görselleri eklemek zorunda değilsiniz.

1. Kılavuz üzerindeki görselleri panolardaki ve mobil panolardaki kutucuklar gibi yeniden boyutlandırabilirsiniz.
   
   Telefon raporu kılavuzu farklı boyutlardaki telefonlara göre değişir. Bu sayede raporunuz hem küçük hem de büyük ekranlı telefonlarda güzel görünür.
   
   ![Görsel boyutunu değiştirme](media/desktop-create-phone-report/desktop-create-phone-report-5.gif)

## <a name="optimize-a-visual-for-any-size"></a>Görseli tüm boyutlar için en iyi duruma getirme
Panonuzdaki veya raporunuzdaki görselleri *değişken* olacak şekilde ayarlayabilirsiniz. Görseller, ekran boyutu ne olursa olsun maksimum sayıda veri ve içgörü görüntüleyecek şekilde dinamik olarak değişirler. 

Power BI, veri görüntüleme önceliğini görsel boyutuna göre değiştirir. Örneğin görselin küçülse dahi bilgilendirici olması için otomatik olarak boşluğu kaldırabilir ve açıklamayı görselin üst tarafına taşıyabilir.

![Yanıt veren görsel yeniden boyutlandırma](media/desktop-create-phone-report/desktop-create-phone-report-6.gif)

Her bir görsel için esneklik seçeneğini açıp kapatabilirsiniz. [Görselleri en iyi duruma getirme](visuals/desktop-create-responsive-visuals.md) hakkında daha fazla bilgi edinin.

## <a name="considerations-when-creating-phone-report-layouts"></a>Telefon rapor düzenlerini oluştururken dikkat edilecek noktalar
* Çok sayfalı raporlarda tüm sayfaları veya yalnızca birkaç tanesini en iyi duruma getirebilirsiniz. 
* Belirli bir rapor sayfası için arka plan rengi tanımladıysanız telefon raporunda da aynı arka plan rengi kullanılır.
* Biçimlendirme ayarlarını yalnızca telefon düzeni için değiştiremezsiniz. Ana ve mobil düzenlerin biçimlendirme özellikleri ortaktır. Örneğin yazı tipi boyutu aynı olacaktır.
* Bir görselin biçimini, veri kümesini, filtrelerini veya diğer özniteliklerini değiştirmek için normal rapor oluşturma moduna geçin.
* Power BI, mobil uygulamada telefon raporları için varsayılan başlıkları ve sayfa adlarını kullanır. Raporunuzdaki başlıklar ve sayfa adları için metin görselleri oluşturduysanız bunları telefon raporlarına eklemeniz önerilmez.     

## <a name="remove-a-visual-from-the-phone-layout"></a>Telefon düzenindeki görselleri kaldırma
* Telefon tuvali üzerinde kaldırmak istediğiniz görselin sağ üst köşesindeki **X** simgesini seçin veya görseli seçip **Sil**’e basın.
  
   Bu işlem görseli yalnızca telefon düzeni tuvalinden kaldırır. Görsel ve özgün rapor etkilenmez.
  
   ![Görselleri kaldırma](media/desktop-create-phone-report/desktop-create-phone-report-7.gif)

## <a name="enhance-slicers-to-work-well-in-phone-reports"></a>Dilimleyicileri telefon raporlarında iyi çalışacak şekilde geliştirme
Dilimleyiciler, rapor verilerinizin tuval üzerinde filtrelenmesini sağlar. Dilimleyicileri normal rapor oluşturma modunda tasarlarken telefon raporlarında daha kullanışlı hale getirmek için bazı dilimleyici ayarlarını değiştirebilirsiniz:

* Raporu okuyanların bir veya daha fazla öğeyi seçip seçemeyeceğine karar verin.
* Dilimleyicinin etrafına bir kutu yerleştirerek raporu taramayı kolaylaştırın.
* Dilimleyiciyi dikey, yatay veya *esnek* hale getirin. 

Dilimleyiciyi esnek hale getirirseniz boyutunu veya şeklini değiştirdiğinizde daha fazla ya da daha az seçenek görüntülenir. Dilimleyici uzun, kısa, geniş veya dar olabilir. Yeterince küçültürseniz rapor sayfasında bir filtre simgesine dönüşür. 

![Power BI'da esnek dilimleyici](media/desktop-create-phone-report/desktop-create-phone-report-8.png)

[Esnek dilimleyiciler oluşturma](power-bi-slicer-filter-responsive.md) hakkında daha fazla bilgi edinin.

## <a name="publish-a-phone-report"></a>Telefon raporu yayımlama
Raporunuzun telefon sürümünü yayımlamak için [ana raporu Power BI Desktop'tan Power BI hizmetine yayımlamanız](desktop-upload-desktop-files.md) yeterlidir, telefon sürümü de aynı anda yayımlanır.
  
[Power BI'da paylaşım ve izinler](service-how-to-collaborate-distribute-dashboards-reports.md) hakkında daha fazla bilgi edinin.

## <a name="view-optimized-and-unoptimized-reports-on-a-phone-or-tablet"></a>En iyi duruma getirilmiş ve getirilmemiş raporları telefonda veya tablette görüntüleme
Telefonlardaki mobil uygulamalarda Power BI en iyi duruma getirilmiş ve getirilmemiş telefon raporlarını otomatik olarak algılar. Telefon için en iyi duruma getirilmiş rapor varsa Power BI telefon uygulaması ilgili raporu otomatik olarak telefon raporu modunda açar.

Telefon için en iyi duruma getirilmiş rapor yoksa rapor en iyi duruma getirilmemiş, yatay görünümde açılır.  

Telefon raporu açıkken telefonun yatay hale getirilmesi durumunda raporun en iyi duruma getirilmiş olma durumundan bağımsız olarak rapor, özgün rapor düzeniyle ve en iyi duruma getirilmemiş görünümde açılır.

Sayfaların yalnızca bazılarını en iyi duruma getirdiyseniz okuyucular dikey görünümde raporun yalnızca yatay görünümde kullanılacağına dair bir ileti görür.

![Telefon sayfası en iyi duruma getirilmemiş](media/desktop-create-phone-report/desktop-create-phone-report-9.png)

Raporu okuyanlar sayfayı yatay modda görmek için telefonlarını veya tabletlerini döndürebilir. [Dikey mod için en iyi duruma getirilmiş Power BI raporlarıyla etkileşimli çalışma](consumer/mobile/mobile-apps-view-phone-report.md) hakkında daha fazla bilgi edinin.

## <a name="next-steps"></a>Sonraki adımlar
* [Power BI'da bir panonun telefon görünümünü oluşturma](service-create-dashboard-mobile-phone-view.md).
* [View Power BI reports optimized for your phone (Telefonunuz için en iyi duruma getirilmiş Power BI raporlarını görüntüleme)](consumer/mobile/mobile-apps-view-phone-report.md).
* [Tüm boyutlar için en iyi duruma getirilmiş esnek görseller oluşturma](visuals/desktop-create-responsive-visuals.md).
* Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/).

