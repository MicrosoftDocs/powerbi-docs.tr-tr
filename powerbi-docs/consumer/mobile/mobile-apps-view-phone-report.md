---
title: Telefonunuz için en iyi duruma getirilmiş Power BI raporlarını görüntüleme
description: Power BI telefon uygulamalarında görüntülemek için en iyi duruma getirilmiş rapor sayfalarıyla etkileşim kurma hakkında bilgi edinin.
author: mshenhav
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 04/22/2019
ms.author: mshenhav
ms.openlocfilehash: 79ca47f83bb39ab9d6df141b5a26dcb54e00c72c
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65100971"
---
# <a name="view-power-bi-reports-optimized-for-your-phone"></a>Telefonunuz için en iyi duruma getirilmiş Power BI raporlarını görüntüleme

Aşağıdakiler cihazlar için geçerlidir:

| ![iPhone](./media/mobile-apps-view-phone-report/ios-logo-40-px.png) | ![Android telefon](./media/mobile-apps-view-phone-report/android-logo-40-px.png) |
|:--- |:--- |
| iPhone'lar |Android telefonlar |

Telefonunuzdan bir Power BI raporu görüntülediğinizde, Power BI raporun telefonlar için optimize edilmiştir olmadığını denetler. Varsa, Power BI en iyi duruma getirilmiş raporu dikey görünümde otomatik olarak açılır.

![Dikey modda rapor](./media/mobile-apps-view-phone-report/07-power-bi-phone-report-portrait.png)

Telefon için en iyi duruma getirilmiş rapor yoksa rapor en iyi duruma getirilmemiş, yatay görünümde açılır. Telefon için en iyi duruma getirilmiş raporlarda bile telefonunuzu yan çevirdiğinizde rapor özgün rapor düzeniyle, en iyi duruma getirilmemiş görünümde açılır. Sayfaların yalnızca bazıları en iyi duruma getirildiyse dikey görünümde raporun yatay görünümde kullanılabileceğini belirten bir ileti görürsünüz.

![En iyi duruma getirilmemiş rapor sayfası](./media/mobile-apps-view-phone-report/06-power-bi-phone-report-page-not-optimized.png)

Telefon için en iyi duruma getirilmiş raporlarda diğer tüm Power BI rapor özellikleri çalışmaya devam eder. Aşağıdakilerle yapabilecekleriniz hakkında daha fazla bilgi edinin:

* [iPhone'larda raporlar](mobile-reports-in-the-mobile-apps.md). 
* [Android telefonlarda raporlar](mobile-reports-in-the-mobile-apps.md).

## <a name="filter-the-report-page-on-a-phone"></a>Telefonda rapor sayfasını filtreleme
Telefon için en iyi duruma getirilmiş bir raporda tanımlı filtreler varsa, söz konusu raporu bir telefonda görüntülerken bu filtreleri kullanabilirsiniz. Web üzerindeki raporda filtrelenen değerlerle filtrelenmiş telefonunuzda rapor açılır. Sayfada etkin filtreler olduğunu belirten bir ileti görürsünüz. Telefonunuzdaki filtreleri değiştirebilirsiniz.

1. Sayfanın en altında bulunan filtre simgesine ![Telefon filtre simgesi](./media/mobile-apps-view-phone-report/power-bi-phone-filter-icon.png) dokunun. 
2. İlgilendiğiniz sonuçları görmek için temel veya gelişmiş filtreleme kullanın.
   
    ![Phone BI telefon raporunda gelişmiş filtreleme](./media/mobile-apps-view-phone-report/power-bi-iphone-advanced-filter-toronto.gif)

## <a name="cross-highlight-visuals"></a>Görsellerde çapraz vurgulama
Dikey görsellerde çapraz vurgulama görünümü, olduğu gibi Power BI hizmetinde ve yatay görünümde telefonlardaki çalışır: Bir görseldeki verileri seçtiğinizde, aynı sayfada yer alan diğer görsellerin ilgili verilerini vurgular.

[Power BI'da filtreleme ve vurgulama](../../power-bi-reports-filters-and-highlighting.md) hakkında daha fazla bilgi edinin.

## <a name="select-visuals"></a>Görsel seçme
Telefon raporlarında bir görsel seçtiğinizde ilgili görsele telefon raporunda vurgulama ve odaklama uygulanır, tuval hareketleri engellenir.

Görseli seçtiğinizde kaydırma gibi işlemler gerçekleştirebilirsiniz. Bir görselin seçimini kaldırmak için görsel alanı dışındaki bir yere dokunmanız yeterlidir.

## <a name="open-visuals-in-focus-mode"></a>Görselleri odak modunda açma
Telefon raporları da odak modu sunar: Tek bir büyük bir görünümünü visual alırken ve daha bir kolayca keşfedin.

* Telefon raporunda görselin sağ üst köşesindeki üç nokta ( **...** ) simgesine dokunduktan sonra **Odak moduna genişlet**'i seçin.
  
    ![Odak moduna genişlet](././media/mobile-apps-view-phone-report/power-bi-phone-report-focus-mode.png)

Odak modunda neler rapor tuvaline ve yaşamanız sağlanır. Örneğin, bir görseldeki bir değeri vurgulayın, ardından raporun tamamına dönüş seçerseniz rapor görselde vurguladığınız değere filtrelenir.

Bazı eylemler ekran boyutu kısıtlamaları nedeniyle yalnızca odak modunda gerçekleştirilebilir:

* Görselde görüntülenen bilgilerin **detayına gitme**. Telefon raporunda [detaya gitme](mobile-apps-view-phone-report.md#drill-down-in-a-visual) hakkında daha fazla bilgi için aşağıdaki bölümü inceleyin.
* Görseldeki değerleri **sıralama**.
* **Geri döndürme**: Görselde gerçekleştirdiğiniz keşfetme adımlarını silme ve tanım kümesini raporun oluşturulduğu zamandaki duruma döndürme.
  
    Bir görseldeki tüm araştırma düzeyini silmek için üç nokta simgesine ( **...** ) dokunup **Geri döndür**'ü seçin.
  
    ![Geri döndür](././media/mobile-apps-view-phone-report/power-bi-phone-report-revert-levels.png)
  
    Geri döndürme tüm görsellerdeki araştırma temizleyerek rapor düzeyinde veya seçili görseldeki keşif temizleme görsel düzeyinde kullanılabilir.   

## <a name="drill-down-in-a-visual"></a>Bir görselde detaya gitme
Hiyerarşi düzeyleri tanımlanmış olan görsellerde bilgilerin detayına gidebilir, ardından normal görünüme dönebilirsiniz. [Görselde detaya gitme özelliğini](../end-user-drill.md) Power BI hizmetinde veya Power BI Desktop uygulamasında kullanabilirsiniz.

Detaya gitme birkaç türü vardır:

### <a name="drill-down-on-a-value"></a>Bir değeri detaya gitme
1. Uzun bir görselde bir veri noktasına (dokunun ve basılı) dokunun.
2. Araç ipucu görünür ve ardından hiyerarşi tanımlanmazsa, araç ipucu altbilgi ayrıntıya aşağı ve yukarı ok gösterilir.
3. Detaya gitme için aşağı oka dokunun

    ![Dokunun detaya gitme](././media/mobile-apps-view-phone-report/report-drill-down.png)
    
4. Detaydan çıkma yukarı okuna dokunun.

### <a name="drill-to-next-level"></a>Bir sonraki düzeye detaya gidin
1. Telefondaki raporda sağ üst köşedeki üç nokta ( **...** ) simgesine dokunduktan sonra **Odak moduna genişlet**'i seçin.
   
    ![Odak moduna genişlet](././media/mobile-apps-view-phone-report/power-bi-phone-report-focus-mode.png)
   
    Bu örnekte çubuklar, eyalet değerlerini göstermektedir.
2. Sol alt köşedeki araştır simgesine ![Araştır simgesi](./media/mobile-apps-view-phone-report/power-bi-phone-report-explore-icon.png) alt sol.
   
    ![Araştırma modu](./media/mobile-apps-view-phone-report/power-bi-phone-report-explore-mode.png)
3. **Sonraki düzeyi göster** veya **Bir sonraki düzeye genişlet**'e dokunun.
   
    ![Bir sonraki düzeye genişlet](./media/mobile-apps-view-phone-report/power-bi-phone-report-expand-levels.png)
   
    Şimdi çubuklarda şehirlere ait değerler gösterilir.
   
    ![Genişletilmiş düzeyler](./media/mobile-apps-view-phone-report/power-bi-phone-report-expanded-levels.png)
4. Sol üst köşedeki ok simgesine dokunursanız telefon raporuna dönersiniz ve değerler alt düzeye genişletilmiş şekilde kalır.
   
    ![Alt düzeye genişletilmiş durumda](./media/mobile-apps-view-phone-report/power-bi-back-to-phone-report-expanded-levels.png)
5. Özgün düzeye dönmek için üç nokta simgesine ( **...** ) tekrar dokunup **Geri döndür**'ü seçin.
   
    ![Geri döndür](././media/mobile-apps-view-phone-report/power-bi-phone-report-revert-levels.png)

## <a name="drill-through-from-a-value"></a>Detaylandırma arasında bir değer
Detaylandırma değerleri bir rapor sayfasındaki diğer rapor sayfalarıyla bağlanır. Bir veri noktası için başka bir rapor sayfasında detaylandırma veri noktası değerleri ayrıntılı sayfası aracılığıyla filtrelemek için kullanılan veya seçilen verileri bağlamında olacaktır.
Rapor yazarları için [detayına gitme tanımlamak](https://docs.microsoft.com/power-bi/desktop-drillthrough) rapor oluşturduğunuzda bunlar.

1. Uzun bir görselde bir veri noktasına (dokunun ve basılı) dokunun.
2. Araç ipucu görünür ve ardından detayına gitme tanımlanmazsa, araç ipucu altbilgi ok araştırdığı gösterilir.
3. Detaylandırma okuna dokunun

    ![Dokunun detayına gitme](././media/mobile-apps-view-phone-report/report-drill-through1.png)

4. Hangi rapor sayfasında detaylandırma seçin

    ![Rapor sayfası seçin](././media/mobile-apps-view-phone-report/report-drill-through2.png)

5. Uygulama Başlığı sizin başlattığınız sayfasına geri dönmek için geri düğmesini kullanın.


## <a name="next-steps"></a>Sonraki adımlar
* [Power BI telefon uygulamaları için en iyi duruma getirilmiş raporlar oluşturma](../../desktop-create-phone-report.md)
* [Power BI'da bir panonun telefon görünümünü oluşturma](../../service-create-dashboard-mobile-phone-view.md)
* [Tüm boyutlar için en iyi duruma getirilmiş esnek görseller oluşturma](../../visuals/desktop-create-responsive-visuals.md)
* Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

