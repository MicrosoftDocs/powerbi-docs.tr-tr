---
title: "Telefonunuz için en iyi duruma getirilmiş Power BI raporlarını görüntüleme"
description: "Power BI telefon uygulamalarında görüntülemek için en iyi duruma getirilmiş rapor sayfalarıyla etkileşim kurma hakkında bilgi edinin."
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
ms.openlocfilehash: 54a1b81cc4281db7a622668ba205c1c57d5e396d
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2017
---
# <a name="view-power-bi-reports-optimized-for-your-phone"></a>Telefonunuz için en iyi duruma getirilmiş Power BI raporlarını görüntüleme
Power BI Desktop'ta bir Power BI raporu oluşturduğunuzda [raporun telefondaki bir Power BI uygulamasında görüntülenmek üzere en iyi duruma getirilmiş](desktop-create-phone-report.md) sürümünü de oluşturabilirsiniz.

Daha sonra telefonda bir Power BI raporunu açtığınızda Power BI raporun telefonlar için en iyi duruma getirilmiş olup olmadığını algılar ve otomatik olarak en iyi duruma getirilmiş raporu dikey görünümde açar.

![Dikey modda rapor](media/mobile-apps-view-phone-report/07-power-bi-phone-report-portrait.png)

Telefon için en iyi duruma getirilmiş rapor yoksa rapor en iyi duruma getirilmemiş, yatay görünümde açılır. Telefon için en iyi duruma getirilmiş raporlarda bile telefonunuzu yan çevirdiğinizde rapor özgün rapor düzeniyle, en iyi duruma getirilmemiş görünümde açılır. Sayfaların yalnızca bazıları en iyi duruma getirildiyse dikey görünümde raporun yatay görünümde kullanılabileceğini belirten bir ileti görürsünüz.

![En iyi duruma getirilmemiş rapor sayfası](media/mobile-apps-view-phone-report/06-power-bi-phone-report-page-not-optimized.png)

Telefon için en iyi duruma getirilmiş raporlarda diğer tüm Power BI rapor özellikleri çalışmaya devam eder. Aşağıdakilerle yapabilecekleriniz hakkında daha fazla bilgi edinin:

* [iPhone'larda raporlar](mobile-reports-in-the-mobile-apps.md). 
* [Android telefonlarda raporlar](mobile-reports-in-the-mobile-apps.md).

## <a name="filter-the-report-page-on-an-iphone"></a>iPhone'da rapor sayfasını filtreleme
Telefon için en iyi duruma getirilmiş raporda tanımlı filtreler varsa, raporu iPhone'da görüntülerken bu filtreleri kullanabilirsiniz. 

1. Sayfanın en altında bulunan filtre simgesine ![Telefon filtre simgesi](media/mobile-apps-view-phone-report/power-bi-phone-filter-icon.png) dokunun. 
2. İlgilendiğiniz sonuçları görmek için temel veya gelişmiş filtreleme kullanın.
   
    ![Phone BI telefon raporunda gelişmiş filtreleme](media/mobile-apps-view-phone-report/power-bi-iphone-advanced-filter-toronto.gif)

## <a name="cross-highlight-visuals"></a>Görsellerde çapraz vurgulama
Telefon raporlarında görsellerde çapraz vurgulama, Power BI hizmetinde ve yatay görünümde telefonlardaki raporlarda olduğu şekilde çalışmaya devam eder. Bir görselde veri seçtiğinizde, o sayfada bulunan diğer görsellerdeki ilgili verileri vurgular.

[Power BI'da filtreleme ve vurgulama](power-bi-reports-filters-and-highlighting.md) hakkında daha fazla bilgi edinin.

## <a name="select-visuals"></a>Görsel seçme
Telefon raporlarında bir görsel seçtiğinizde ilgili görsele telefon raporunda vurgulama ve odaklama uygulanır, tuval hareketleri engellenir.

Görseli seçtiğinizde kaydırma gibi işlemler gerçekleştirebilirsiniz. Bir görselin seçimini kaldırmak için görsel alanı dışındaki bir yere dokunmanız yeterlidir.

## <a name="open-visuals-in-focus-mode"></a>Görselleri odak modunda açma
Telefon raporları da tek bir görseli daha büyük görüntüleyip görseli ve raporu keşfetmenizi sağlayan odak moduna sahiptir.

* Telefon raporunda görselin sağ üst köşesindeki üç nokta (**...**) simgesine dokunduktan sonra **Odak moduna genişlet**'i seçin.
  
    ![Odak moduna genişlet](media/mobile-apps-view-phone-report/power-bi-phone-report-focus-mode.png)

Odak modunda yaptığınız değişiklikler rapor tuvaline, rapor tuvalinde yaptıklarınız da odak moduna uygulanarak sorunsuz bir keşfetme deneyimi yaşamanız sağlanır. Örneğin görseldeki bir değeri vurgulayıp raporun tamamına gönderseniz raporun tamamı, görselde vurguladığınız değere göre filtrelenmiş halde görüntülenir.

Bazı eylemler ekran boyutu kısıtlamaları nedeniyle yalnızca odak modunda gerçekleştirilebilir:

* Görselde görüntülenen bilgilerin **detayına gitme**. Telefon raporunda [detaya gitme](mobile-apps-view-phone-report.md#drill-down-in-a-visual) hakkında daha fazla bilgi için aşağıdaki bölümü inceleyin.
* Görseldeki değerleri **sıralama**.
* **Geri döndürme**: Görselde gerçekleştirdiğiniz keşfetme adımlarını silme ve tanım kümesini raporun oluşturulduğu zamandaki duruma döndürme.
  
    Bir görseldeki tüm araştırma düzeyini silmek için üç nokta simgesine (**...**) dokunup **Geri döndür**'ü seçin.
  
    ![Geri döndür](media/mobile-apps-view-phone-report/power-bi-phone-report-revert-levels.png)
  
    Geri döndürme işlemi tüm görsellerdeki araştırma düzeylerini silmek için rapor düzeyinde veya seçili görseldeki keşif düzeyini silmek için belirli bir görselde kullanılabilir.   

## <a name="drill-down-in-a-visual"></a>Bir görselde detaya gitme
Hiyerarşi düzeyleri tanımlanmış olan görsellerde bilgilerin detayına gidebilir, ardından normal görünüme dönebilirsiniz. [Görselde detaya gitme özelliğini](power-bi-visualization-drill-down.md) Power BI hizmetinde veya Power BI Desktop uygulamasında kullanabilirsiniz. Detaya gitme özelliği yalnızca telefon için en iyi duruma getirilmiş Power BI raporlarını telefonda görüntülediğinizde kullanılabilir. 

1. Telefondaki raporda sağ üst köşedeki üç nokta (**...**) simgesine dokunduktan sonra **Odak moduna genişlet**'i seçin.
   
    ![Odak moduna genişlet](media/mobile-apps-view-phone-report/power-bi-phone-report-focus-mode.png)
   
    Bu örnekte çubuklar, eyalet değerlerini göstermektedir.
2. Sol alt köşedeki araştır simgesine ![Araştır simgesi](media/mobile-apps-view-phone-report/power-bi-phone-report-explore-icon.png) dokunun.
   
    ![Araştırma modu](media/mobile-apps-view-phone-report/power-bi-phone-report-explore-mode.png)
3. **Sonraki düzeyi göster** veya **Bir sonraki düzeye genişlet**'e dokunun.
   
    ![Bir sonraki düzeye genişlet](media/mobile-apps-view-phone-report/power-bi-phone-report-expand-levels.png)
   
    Şimdi çubuklarda şehirlere ait değerler gösterilir.
   
    ![Genişletilmiş düzeyler](media/mobile-apps-view-phone-report/power-bi-phone-report-expanded-levels.png)
4. Sol üst köşedeki ok simgesine dokunursanız telefon raporuna dönersiniz ve değerler alt düzeye genişletilmiş şekilde kalır.
   
    ![Alt düzeye genişletilmiş durumda](media/mobile-apps-view-phone-report/power-bi-back-to-phone-report-expanded-levels.png)
5. Özgün düzeye dönmek için üç nokta simgesine (**...**) tekrar dokunup **Geri döndür**'ü seçin.
   
    ![Geri döndür](media/mobile-apps-view-phone-report/power-bi-phone-report-revert-levels.png)

## <a name="next-steps"></a>Sonraki adımlar
* [Power BI telefon uygulamaları için en iyi duruma getirilmiş raporlar oluşturma](desktop-create-phone-report.md)
* [Power BI'da bir panonun telefon görünümünü oluşturma](service-create-dashboard-mobile-phone-view.md)
* [Tüm boyutlar için en iyi duruma getirilmiş esnek görseller oluşturma](desktop-create-responsive-visuals.md)
* Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

