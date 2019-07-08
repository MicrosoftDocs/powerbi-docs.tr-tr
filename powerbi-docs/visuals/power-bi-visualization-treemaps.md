---
title: Power BI'da ağaç haritaları
description: Power BI'da ağaç haritaları
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: IkJda4O7oGs
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/24/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 4c28071917dbe5669e6e35bd416236ef7047eb24
ms.sourcegitcommit: 58c649ec5fd2447a0f9ca4c4d45a0e9fff2f1b6a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2019
ms.locfileid: "67408840"
---
# <a name="treemaps-in-power-bi"></a>Power BI'da ağaç haritaları

Ağaç haritaları, hiyerarşik verileri iç içe geçmiş dikdörtgenler kümesi şeklinde görüntüler. Hiyerarşinin her düzeyi daha küçük dikdörtgenler (yapraklar) içeren renkli bir dikdörtgen (dal) ile gösterilir. Power BI her dikdörtgenin içindeki alanı, ölçülen değeri temel alarak boyutlandırır. Dikdörtgenler, sol üstten (en büyük) sağ alta (en küçük) doğru boyutlarına göre yerleştirilir.

![Count of Product by Category ve Manufacturer ağaç haritasının ekran görüntüsü.](media/power-bi-visualization-treemaps/pbi-nancy-viz-treemap.png)

Örneğin, satışlarınızı analiz ediyorsanız giysi kategorisi için üst düzey dallarınız olabilir: **Urban**, **Rural**, **Youth** ve **Mix**. Power BI, bu kategorideki giysi üreticileri için kategori dikdörtgenlerinizi yapraklara ayırır. Bu yapraklar, satılan sayıya göre boyutlandırılır ve gölgelendirilir.

Yukarıdaki **Urban** dalında çok sayıda **VanArsdel** giysisi satılmış. Daha az **Natura** ve **Fama** satılmış. Yalnızca birkaç tane **Leo** satılmış. Bu nedenle Ağar Haritanızın **Urban** dalı şöyle görünür:

* Sol üst köşede en büyük **VanArsdel** dikdörtgeni.

* Biraz daha küçük **Natura** ve **Fama** dikdörtgenleri.

* Satılan diğer tüm giysileri temsil eden birçok başka dikdörtgen.

* **Leo** için küçük bir dikdörtgen.

Her yaprak düğümünün boyutunu ve gölgelendirmesini karşılaştırarak, diğer giysi kategorilerinde satılan öğe sayısı ile karşılaştırma yapabilirsiniz; dikdörtgenler ne kadar büyük ve koyu olursa değer o kadar yüksek olur.

Önce, ağaç haritası oluşturma işleminin gösterildiği bir videoyu izlemek ister misiniz? Bu videoda 2:10'a atlayarak Amanda'nın ağaç haritası oluşturmasını izleyin.

<iframe width="560" height="315" src="https://www.youtube.com/embed/IkJda4O7oGs" frameborder="0" allowfullscreen></iframe>

## <a name="when-to-use-a-treemap"></a>Ağaç haritası ne zaman kullanılır?

Ağaç haritaları aşağıdaki durumlarda kullanım için mükemmel seçimdir:

* Büyük miktarlarda hiyerarşik veri görüntüleme.

* Çubuk grafik, büyük miktarlardaki değerleri etkili bir şekilde işleyemediğinde.

* Her parça ve bütün arasındaki oranları gösterme.

* Hiyerarşideki kategorilerin her düzeyinde ölçü dağılımının desenini gösterme.

* Boyut ve renk kodlaması kullanarak öznitelikleri gösterme.

* Desenleri, aykırı değerleri, en önemli katkıda bulunanları ve istisnaları bulma.

## <a name="prerequisites"></a>Önkoşullar

* Power BI hizmeti veya Power BI Desktop

* Perakende Analizi Örneği raporu

## <a name="get-the-retail-analysis-sample-report"></a>Perakende Analizi Örneği raporunu alma

Bu yönergelerde Perakende Analizi Örneği kullanılmaktadır. Bir görsel öğe oluşturmak için veri kümesinde ve raporda düzenleme izinlerine sahip olmanız gerekir. Neyse ki, Power BI örneklerinin tümü düzenlenebilir. Biri sizinle bir rapor paylaşırsa, raporda görselleştirmeler oluşturamazsınız. Örneği takip etmek için [Perakende Analizi Örneği raporunu](../sample-datasets.md) alın.

**Perakende Analizi Örneği** veri kümesini aldıktan sonra başlayabilirsiniz.

## <a name="create-a-basic-treemap"></a>Basit bir ağaç haritası oluşturma

Bir rapor oluşturacak ve basit bir ağaç haritası ekleyeceksiniz.

1. **Çalışma Alanım**’dan **Veri kümeleri** > **Rapor oluştur**’u seçin.

    ![Veri kümeleri > Rapor oluştur ekran görüntüsü.](media/power-bi-visualization-treemaps/power-bi-create-a-report.png)

1. **Alanlar** bölmesinde **Sales** > **Last Year Sales** ölçüsünü seçin.

   ![Sales > Last Year Sales’in seçilmesinin ve sonuç görselinin ekran görüntüsü.](media/power-bi-visualization-treemaps/treemapfirstvalue_new.png)

1. Ağaç haritası simgesini seçerek ![Ağaç haritası simgesinin ekran görüntüsü](media/power-bi-visualization-treemaps/power-bi-treemap-icon.png) grafiği ağaç haritasına dönüştürün.

   ![Yapılandırılmamış ağaç haritasının ekran görüntüsü.](media/power-bi-visualization-treemaps/treemapconvertto_new.png)

1. **Grup** kutusuna **Item** > **Category** alanlarını sürükleyin.

    Power BI, dikdörtgen boyutunun toplam satışı temel aldığı, rengin ise kategoriyi gösterdiği bir ağaç haritası oluşturur. Temelde, toplam satışın kategoriye göre boyutunu görsel olarak açıklayan bir hiyerarşi oluşturdunuz. **Men's** kategorisi en yüksek satışa sahipken **Hosiery** kategorisi en düşük satışlara sahiptir.

    ![Yapılandırılmış ağaç haritasının ekran görüntüsü.](media/power-bi-visualization-treemaps/power-bi-complete.png)

1. Ağaç haritanızı tamamlamak için **Ayrıntılar**'a **Store** > **Chain** alanlarını sürükleyin. Artık geçen yılın satışlarını kategori ve zincire göre karşılaştırabilirsiniz.

   ![Ayrıntılar'a Store > Chain’in eklendiği ağaç haritasını ekran görüntüsü.](media/power-bi-visualization-treemaps/power-bi-details.png)

   > [!NOTE]
   > Renk doygunluğu ve Ayrıntılar aynı anda kullanılamaz.

1. **Category**'nin bu kısmı için araç ipucunu göstermek üzere bir **Chain** alanının üzerine gelin.

    Örneğin, imleç **090-Home** dikdörtgeninde **Fashions Direct** üzerine getirildiğinde dikdörtgen, Home kategorisinin Fashions Direct bölümü için araç ipucunu görüntüler.

   ![Görüntülenen Giriş araç ipucunun ekran görüntüsü.](media/power-bi-visualization-treemaps/treemaphoverdetail_new.png)

1. Ağaç haritasını [bir pano kutucuğu (görseli sabitleyin)](../service-dashboard-tiles.md) olarak ekleyin.

1. [Raporu](../service-report-save.md) kaydedin.

## <a name="highlighting-and-cross-filtering"></a>Vurgulama ve çapraz filtreleme

**Filtreler** bölmesini kullanmayla ilgili bilgi için bkz. [Rapora filtre ekleme](../power-bi-report-add-filter.md).

Ağaç haritasında bir **Kategori** veya **Ayrıntı** vurgulandığında rapor sayfasındaki diğer görselleştirmeler çapraz vurgulanır ve çapraz filtrelenir (tersi de geçerlidir). Örneği takip etmek için, bu rapor sayfasına bazı görseller ekleyin veya ağaç haritasını bu rapordaki diğer sayfalardan birine kopyalayın.

1. Ağaç haritasında, **Kategori** veya **Kategori**'nin içinden bir **Zincir** seçin. Bu işlem, sayfadaki diğer görselleştirmeleri çapraz vurgulayacaktır. Örneğin **050-Shoes** kategorisi seçildiğinde geçen yılki ayakkabı satışının **3.640.471 ABD doları** olduğu ve bunun **2.174.185 ABD doları** tutarındaki kısmının **Fashions Direct**'ten geldiği görülür.

   ![Çapraz vurgulamayı gösteren Store Sales Overview raporunun ekran görüntüsü.](media/power-bi-visualization-treemaps/treemaphiliting.png)

1. **Zincire göre Geçen Yılın Satışları** pasta grafiğinde, **Fashions Direct** dilimini seçtiğinizde ağaç haritası filtrelenir.
   ![Çapraz filtreleme özelliğinin GIF biçiminde gösterimi.](media/power-bi-visualization-treemaps/treemapnoowl.gif)

1. Grafiklerin birbirini çapraz vurgulamasını ve çapraz filtrelemesini yönetmek için bkz. [Power BI raporunda görseller arasındaki etkileşimi değiştirme](../service-reports-visual-interactions.md).

## <a name="next-steps"></a>Sonraki adımlar

* [Power BI’daki şelale grafikler](power-bi-visualization-waterfall-charts.md)

* [Power BI'daki görselleştirme türleri](power-bi-visualization-types-for-reports-and-q-and-a.md)
