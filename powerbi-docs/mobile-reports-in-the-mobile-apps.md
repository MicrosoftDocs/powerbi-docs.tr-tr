---
title: "Power BI mobil uygulamalarında raporları araştırma"
description: "Telefonunuzdaki veya tabletinizdeki Power BI mobil uygulamalarında bulunan raporları görüntüleme ve bu raporlarla etkileşim kurma hakkında bilgi edinin. Power BI hizmetinde veya Power BI Desktop'ta oluşturduğunuz raporlarla daha sonra mobil uygulamalarda etkileşim kurabilirsiniz. "
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
ms.date: 10/13/2017
ms.author: maggies
ms.openlocfilehash: 3515a57f88db1c8a7b12706680c0aade8b2cdbfa
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="explore-reports-in-the-power-bi-mobile-apps"></a>Power BI mobil uygulamalarında raporları araştırma
Aşağıdakiler için geçerlidir:

| ![iPhone](media/mobile-reports-in-the-mobile-apps/ios-logo-40-px.png) | ![iPad](media/mobile-reports-in-the-mobile-apps/ios-logo-40-px.png) | ![Android telefon](media/mobile-reports-in-the-mobile-apps/android-logo-40-px.png) | ![Android tablet](media/mobile-reports-in-the-mobile-apps/android-logo-40-px.png) | ![Windows 10 cihazları](media/mobile-reports-in-the-mobile-apps/win-10-logo-40-px.png) |
|:--- |:--- |:--- |:--- |:--- |
| iPhone'lar |iPad'ler |Android telefonlar |Android tabletler |Windows 10 cihazları |

Power BI raporu, verilerinizin etkileşimli bir görünümüdür ve verilerinize dayalı farklı bulguları ve öngörüleri temsil eden görseller içerir. Power BI mobil uygulamalarında raporları görüntülemek, üç adımlı bir işlemin üçüncü adımıdır.

1. [Power BI Desktop'ta rapor oluşturun](desktop-report-view.md). Power BI Desktop'ta [bir raporu telefonlar için en iyi duruma getirebilirsiniz](mobile-apps-view-phone-report.md). 
2. Oluşturduğunuz raporları Power BI hizmetinde [(https://powerbi.com)](https://powerbi.com) veya [Power BI Rapor Sunucusu](report-server/get-started.md)'nda yayımlayın.  
3. Ardından Power BI mobil uygulamalarını kullanarak bu raporlarla etkileşim kurun.

## <a name="open-a-power-bi-report-in-the-mobile-app"></a>Bir Power BI raporunu mobil uygulamada açma
Power BI raporlarını aldığınız yere bağlı olarak bu raporlar mobil uygulamanın farklı konumlarında depolanır. Raporlar; Uygulamalar, Benimle Paylaşılan veya Çalışma Alanı (Çalışma Alanım dahil) bölümlerinde ya da bir rapor sunucusunda olabilir. Raporlar bazı durumlarda listelenir, bazı durumlarda da bir raporu almak için ilişkili panoya göz atmanız gerekebilir.

* Panoda bir kutucuğun sağ üst köşesindeki üç nokta (...) simgesine ve **Rapor Aç** seçeneğine dokunun.
  
  ![Rapor Aç](media/mobile-reports-in-the-mobile-apps/power-bi-android-open-report-tile.png)
  
  Rapor aç seçeneği, kutucukların hepsinde bulunmaz. Örneğin, Soru-Cevap kutusunda soru sorarak oluşturulan kutucuklara dokunulduğunda rapor açılmaz. 
  
  Rapor, [telefonda görüntüleme için en iyi duruma getirilmediyse](mobile-reports-in-the-mobile-apps.md#view-reports-optimized-for-phones) yatay modda açılır.
  
  ![Telefonda yatay modda rapor görünümü](media/mobile-reports-in-the-mobile-apps/power-bi-iphone-report-landscape.png)

## <a name="view-reports-optimized-for-phones"></a>Telefonlar için en iyi duruma getirilmiş raporlar görüntüleme
Power BI rapor yazarları, özellikle telefonlar için en iyi duruma getirilmiş bir rapor düzeni oluşturabilir. İyileştirilmiş raporlar, rapor listesinde özel bir simge ile belirtilir ![Telefon raporu simgesi](media/mobile-reports-in-the-mobile-apps/power-bi-phone-report-icon.png):

![Telefon raporunu açma](media/mobile-reports-in-the-mobile-apps/power-bi-android-phone-report.png)

Bu raporu bir telefonda görüntülediğinizde dikey görünümde açılır.

![Dikey görünümlü rapor](media/mobile-reports-in-the-mobile-apps/07-power-bi-phone-report-portrait.png)

Bir rapor, telefon için en iyi duruma getirilmiş ve getirilmemiş karışık sayfalar içerebilir. Bu durumda görünüm, rapor sayfalarına göz gezdirirken her sayfa için dikeyden yataya dönüşür.

[Telefon görünümü için en iyi duruma getirilmiş raporlar](mobile-apps-view-phone-report.md) hakkında daha fazla bilgi edinin.

## <a name="use-slicers-to-filter-a-report-page"></a>Bir rapor sayfasını filtrelemek için dilimleyicileri kullanma
Power BI hizmetinde [(https://powerbi.com)](https://powerbi.com) bir rapor tasarlarken Filtreler bölmesini telefonda göremeyeceğinizi ancak [rapor sayfasında dilimleyicileri görebileceğinizi](power-bi-visualization-slicers.md) göz önünde bulundurun. Bir rapora dilimleyiciler eklediğinizde hem siz hem de iş arkadaşlarınız, bu dilimleyicileri kullanarak raporu telefonda da filtreleyebilirsiniz.

* Rapor sayfasındaki bir dilimleyicide değer seçtiğinizde sayfadaki diğer görseller filtrelenir.
  
  ![Rapor dilimleyici](media/mobile-reports-in-the-mobile-apps/power-bi-android-tablet-report-slicer.png)
  
  Bu çizimde dilimleyici, sütun grafiği yalnızca July (Temmuz) değerlerini gösterecek şekilde filtrelemektedir.

## <a name="cross-filter-and-highlight-a-power-bi-report-page"></a>Bir Power BI rapor sayfasına çapraz filtre ve vurgu uygulama
Görseldeki bir değeri seçtiğinizde diğer görseller filtrelenmez. Diğer görsellerdeki ilgili değerler vurgulanır.

* Görsel içindeki bir değere dokunun.
  
  ![Bir sayfaya çapraz filtre uygulama](media/mobile-reports-in-the-mobile-apps/power-bi-android-tablet-report-highlight.png)
  
  Bir görseldeki Large sütununa dokunduğunuzda diğer görsellerdeki ilgili değerler vurgulanır. 

## <a name="sort-a-visual-on-an-ipad-or-a-tablet"></a>iPad'de veya tablette bir görseli sıralama
* Önce grafiğe, sonra üç nokta (**...**) simgesine ve ardından alan adına dokunun.
  
   ![Bir görseli sıralama](media/mobile-reports-in-the-mobile-apps/power-bi-android-tablet-report-sort.png)
* Sıralama düzenini ters çevirmek için üç nokta (**...**) simgesine tekrar dokunun ve aynı alan adını yeniden seçin.

## <a name="drill-down-and-up-in-a-visual-on-an-ipad-or-a-tablet"></a>iPad'de veya tablette bir görselin detayına gitme ve detayından çıkma
Rapor yazarı görsele bu özelliği eklemişse iPad'de veya tablette, görselin bir parçasını oluşturan değerleri görmek için detaya gidebilirsiniz. Power BI Desktop'ta veya Power BI hizmetinde [bir görsele detaya gitme özelliği ekleyin](power-bi-visualization-drill-down.md). 

> [!NOTE]
> iPad'de veya tablette detaya gitme özelliği şu anda haritalar üzerinde çalışmamaktadır.
> 
> 

* Bir görsele dokunun. Üst köşesinde yukarı ve aşağı oklar bulunuyorsa ![Detaydan çıkma ve detaya gitme simgeleri](media/mobile-reports-in-the-mobile-apps/power-bi-mobile-drill-up-down.png)detaya gidebilirsiniz. Bir değerde detaya gitmek için sağ üst köşedeki oka ve ardından görseldeki bir değere dokunun (bu örnekte, koyu mavi FD-04 kabarcığı).
  
  ![Bir görselde detaya gitme](media/mobile-reports-in-the-mobile-apps/power-bi-mobile-drill-down-one.png)
* Detaydan çıkmak için sol üst köşedeki yukarı oka dokunun.
  
  ![Detaydan çıkma](media/mobile-reports-in-the-mobile-apps/power-bi-mobile-drill-up.png)

## <a name="go-back-to-my-workspace"></a>Çalışma Alanım bölümüne geri dönme
* Rapor adının yanındaki oka ve ardından **Çalışma Alanım** seçeneğine dokunun.
  
  ![Üst menüye geri dönme](media/mobile-reports-in-the-mobile-apps/power-bi-iphone-report-back.png)

## <a name="next-steps"></a>Sonraki adımlar
* [Telefonunuz için en iyi duruma getirilmiş Power BI raporlarını görüntüleme ve raporlarla etkileşim kurma](mobile-apps-view-phone-report.md)
* [Telefonlar için en iyi duruma getirilmiş bir rapor sürümü oluşturma](desktop-create-phone-report.md)
* Sorularınız mı var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

