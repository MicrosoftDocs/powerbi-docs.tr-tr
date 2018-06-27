---
title: Power BI mobil uygulamalarında raporları araştırma
description: Telefonunuzdaki veya tabletinizdeki Power BI mobil uygulamalarında bulunan raporları görüntüleme ve bu raporlarla etkileşim kurma hakkında bilgi edinin. Power BI hizmetinde veya Power BI Desktop'ta oluşturduğunuz raporlarla daha sonra mobil uygulamalarda etkileşim kurabilirsiniz.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-mobile
ms.topic: conceptual
ms.date: 06/05/2018
ms.author: maggies
ms.openlocfilehash: 5b4d5ea7970dd44cfebadca6935452688515aef5
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "34799430"
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
Power BI rapor yazarları, özellikle telefonlar için en iyi duruma getirilmiş bir rapor düzeni oluşturabilir. Telefonlar için iyileştirilmiş rapor sayfaları ek işlevler içerir: Örneğin, görsellerde detaya gidebilir, sıralama yapabilir ve [rapor yazarının, rapor sayfasına eklediği filtrelere](mobile-apps-view-phone-report.md#filter-the-report-page-on-a-phone) erişebilirsiniz. Rapor telefonunuzda, web üzerindeki raporda filtrelenen değerlerle filtrelenmiş bir şekilde ve sayfada etkin filtreler olduğunu belirten bir iletiyle açılır. Telefonunuzdaki filtreleri değiştirebilirsiniz.

İyileştirilmiş raporlar, rapor listesinde özel bir simge ile belirtilir ![Telefon raporu simgesi](media/mobile-reports-in-the-mobile-apps/power-bi-phone-report-icon.png):

![Telefon raporunu açma](media/mobile-reports-in-the-mobile-apps/power-bi-android-phone-report.png)

Bu raporu bir telefonda görüntülediğinizde dikey görünümde açılır.

![Dikey görünümlü rapor](media/mobile-reports-in-the-mobile-apps/07-power-bi-phone-report-portrait.png)

 Bir rapor, telefon için en iyi duruma getirilmiş ve getirilmemiş karışık sayfalar içerebilir. Bu durumda görünüm, rapor sayfalarına göz gezdirirken her sayfa için dikeyden yataya dönüşür.

[Telefon görünümü için en iyi duruma getirilmiş raporlar](mobile-apps-view-phone-report.md) hakkında daha fazla bilgi edinin.

## <a name="use-slicers-to-filter-a-report"></a>Bir raporu filtrelemek için dilimleyicileri kullanma
Power BI Desktop’ta veya Power BI hizmetinde bir rapor tasarlarken [rapor sayfasına dilimleyiciler eklemeyi](power-bi-visualization-slicers.md) düşünün. İş arkadaşlarınızla birlikte, bir tarayıcıda ve mobil uygulamalarda sayfayı filtrelemek için dilimleyicileri kullanabilirsiniz. Raporu bir telefonda görüntülediğinizde, dilimleyicileri yatay modda ve telefonun dikey modu için iyileştirilmiş bir sayfada görebilir ve etkileşimde bulunabilirsiniz. Tarayıcıdaki bir dilimleyiciden veya filtreden bir değer seçerseniz sayfayı mobil uygulamada görüntülediğinizde de değer seçilir. Sayfada etkin filtreler olduğunu belirten bir ileti görürsünüz.  

* Rapor sayfasındaki bir dilimleyicide değer seçtiğinizde sayfadaki diğer görseller filtrelenir.
  
  ![Rapor dilimleyici](media/mobile-reports-in-the-mobile-apps/power-bi-android-tablet-report-slicer.png)
  
  Bu çizimde dilimleyici, sütun grafiği yalnızca July (Temmuz) değerlerini gösterecek şekilde filtrelemektedir.

## <a name="cross-filter-and-highlight-a-report"></a>Bir rapora çapraz filtre ve vurgu uygulama
Görseldeki bir değeri seçtiğinizde diğer görseller filtrelenmez. Diğer görsellerdeki ilgili değerler vurgulanır.

* Görsel içindeki bir değere dokunun.
  
  ![Bir sayfaya çapraz filtre uygulama](media/mobile-reports-in-the-mobile-apps/power-bi-android-tablet-report-highlight.png)
  
  Bir görseldeki Large sütununa dokunduğunuzda diğer görsellerdeki ilgili değerler vurgulanır. 

## <a name="sort-a-visual-on-an-ipad-or-a-tablet"></a>iPad'de veya tablette bir görseli sıralama
* Önce grafiğe, sonra üç nokta (**...**) simgesine ve ardından alan adına dokunun.
  
   ![Bir görseli sıralama](media/mobile-reports-in-the-mobile-apps/power-bi-android-tablet-report-sort.png)
* Sıralama düzenini ters çevirmek için üç nokta (**...**) simgesine tekrar dokunun ve aynı alan adını yeniden seçin.

## <a name="drill-down-and-up-in-a-visual"></a>Bir görselde detaya gitme ve detaydan çıkma
Rapor yazarı görsele detaya gitme özelliği eklemişse, görselin bir parçasını oluşturan değerleri görmek için detaya gidebilirsiniz. Power BI Desktop'ta veya Power BI hizmetinde [bir görsele detaya gitme özelliği ekleyin](power-bi-visualization-drill-down.md). 

* Görseldeki bir veri noktasına tıklayarak bunun araç ipucunu görüntüleyebilirsiniz. Detaya gitme seçeneği varsa araç ipucunun en altında dokunabileceğiniz oklar olur. 
  
  ![Bir görselde detaya gitme](media/mobile-reports-in-the-mobile-apps/power-bi-mobile-drill-down-tooltip.png)

* Detaydan çıkmak için araç ipucundaki yukarı oka dokunun.
  
  ![Detaydan çıkma](media/mobile-reports-in-the-mobile-apps/power-bi-mobile-drill-up-tooltip.png)

* Ayrıca bir görseldeki tüm veri noktalarının detayına gidebilirsiniz. Odak modunda açın, Araştır simgesine dokunup sonraki düzeyde hepsini gösteri seçin veya geçerli ve bir sonraki düzeyi göstermek için genişletin.

   ![Power BI tümünün detayına gitme](media/mobile-reports-in-the-mobile-apps/power-bi-drill-down-all.png)

## <a name="drill-through-from-one-page-to-another"></a>Bir sayfadan diğerinin detaylarına gitme

*Detaylandırma* sayesinde, bir görselin belirli bir bölümüne dokunduğunuzda Power BI sizi raprodaki farklı, dokunduğunuz değere göre filtrelenmiş bir sayfaya götürür. Raporun yazarı, her biri sizi farklı bir sayfaya götüren bir veya daha fazla detaylandırma seçeneği tanımlayabilir. Bu durumda, hangi sayfayı detaylandırmak istediğinizi seçebilirsiniz. Aşağıdaki örnekte, ölçerdeki değere dokunduğunuzda detaylandırmak üzere ister **iş alanına göre harcama** sayfasını ister **iş alanına göre planlama** sayfasını seçebilirsiniz.

![Power BI mobil raporu detaylandırma](media/mobile-reports-in-the-mobile-apps/power-bi-mobile-drill-through-it-spent-report.png)

Detaylandırma gerçekleştirdiğinizde geri düğmesini kullanarak bir önceki rapor sayfasına dönebilirsiniz.

[Power BI Desktop’ta detaylandırma ekleme](desktop-drillthrough.md) hakkında bilgi edinin.

## <a name="next-steps"></a>Sonraki adımlar
* [Telefonunuz için en iyi duruma getirilmiş Power BI raporlarını görüntüleme ve raporlarla etkileşim kurma](mobile-apps-view-phone-report.md)
* [Telefonlar için en iyi duruma getirilmiş bir rapor sürümü oluşturma](desktop-create-phone-report.md)
* Sorularınız mı var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

