---
title: Power BI'da ağaç haritaları
description: Power BI'da ağaç haritaları
author: mihart
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/05/2020
ms.author: rien
LocalizationGroup: Visualizations
ms.openlocfilehash: afc18fa33ec1612900cecc0a34eb50851804fb62
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83276709"
---
# <a name="treemaps-in-power-bi"></a>Power BI'da ağaç haritaları

[!INCLUDE[consumer-appliesto-nyyn](../includes/consumer-appliesto-nyyn.md)]

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

Ağaç haritaları, hiyerarşik verileri iç içe geçmiş dikdörtgenler kümesi şeklinde görüntüler. Hiyerarşinin her düzeyi daha küçük dikdörtgenler (yapraklar) içeren renkli bir dikdörtgen (dal) ile gösterilir. Power BI her dikdörtgenin içindeki alanı, ölçülen değeri temel alarak boyutlandırır. Dikdörtgenler, sol üstten (en büyük) sağ alta (en küçük) doğru boyutlarına göre yerleştirilir.

![Count of Product by Category ve Manufacturer ağaç haritasının ekran görüntüsü.](media/power-bi-visualization-treemaps/pbi-nancy-viz-treemap.png)

Örneğin, satışlarınızı analiz ediyorsanız giysi kategorisi için üst düzey dallarınız olabilir: **Urban**, **Rural**, **Youth** ve **Mix**. Power BI, bu kategorideki giysi üreticileri için kategori dikdörtgenlerinizi yapraklara ayırır. Bu yapraklar, satılan sayıya göre boyutlandırılır ve gölgelendirilir.

Yukarıdaki **Urban** dalında çok sayıda **VanArsdel** giysisi satılmış. Daha az **Natura** ve **Fama** satılmış. Yalnızca birkaç tane **Leo** satılmış. Bu nedenle Ağar Haritanızın **Urban** dalı şöyle görünür:

* Sol üst köşede en büyük **VanArsdel** dikdörtgeni.

* Biraz daha küçük **Natura** ve **Fama** dikdörtgenleri.

* Satılan diğer tüm giysileri temsil eden birçok başka dikdörtgen.

* **Leo** için küçük bir dikdörtgen.

Her yaprak düğümünün boyutunu ve gölgelendirmesini karşılaştırarak, diğer giysi kategorilerinde satılan öğe sayısı ile karşılaştırma yapabilirsiniz; dikdörtgenler ne kadar büyük ve koyu olursa değer o kadar yüksek olur.


## <a name="when-to-use-a-treemap"></a>Ağaç haritası ne zaman kullanılır?

Ağaç haritaları aşağıdaki durumlarda kullanım için mükemmel seçimdir:

* Büyük miktarlarda hiyerarşik veri görüntüleme.

* Çubuk grafik, büyük miktarlardaki değerleri etkili bir şekilde işleyemediğinde.

* Her parça ve bütün arasındaki oranları gösterme.

* Hiyerarşideki kategorilerin her düzeyinde ölçü dağılımının desenini gösterme.

* Boyut ve renk kodlaması kullanarak öznitelikleri gösterme.

* Desenleri, aykırı değerleri, en önemli katkıda bulunanları ve istisnaları bulma.

## <a name="prerequisite"></a>Önkoşul

Bu öğreticide [Perakende Analizi örneği .PBIX dosyası](https://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix) kullanılmıştır.

1. Menü çubuğunun sol üst köşesinden **Dosya** > **Aç**’ı seçin
   
2. **Perakende Analizi örneği PBIX dosyasının** kopyasını bulun

1. **Perakende Analizi örneği PBIX dosyasını** rapor görünümünde ![Rapor görünümü simgesinin ekran görüntüsü.](media/power-bi-visualization-kpi/power-bi-report-view.png) açın.

1. Seç ![Sarı sekmenin ekran görüntüsü.](media/power-bi-visualization-kpi/power-bi-yellow-tab.png) yeni bir sayfa ekleyin.

> [!NOTE]
> Raporunuzu bir Power BI iş arkadaşınızla paylaşmak için her ikinizin de bireysel Power BI Pro lisanslarınızın olması veya raporun Premium kapasitede depolanması gerekir.    



**Perakende Analizi Örneği** veri kümesini aldıktan sonra başlayabilirsiniz.

## <a name="create-a-basic-treemap"></a>Basit bir ağaç haritası oluşturma

Bir rapor oluşturacak ve basit bir ağaç haritası ekleyeceksiniz.


1. **Alanlar** bölmesinde **Sales** > **Last Year Sales** ölçüsünü seçin.

   ![Sales > Last Year Sales’in seçilmesinin ve sonuç görselinin ekran görüntüsü.](media/power-bi-visualization-treemaps/treemapfirstvalue-new.png)

1. Ağaç haritası simgesini seçerek ![Ağaç haritası simgesinin ekran görüntüsü](media/power-bi-visualization-treemaps/power-bi-treemap-icon.png) grafiği ağaç haritasına dönüştürün.

   ![Yapılandırılmamış ağaç haritasının ekran görüntüsü.](media/power-bi-visualization-treemaps/treemapconvertto-new.png)

1. **Öğe** > **Kategori**’yi seçerek **Kategori**’yi **Grup** kutusuna ekleyin.

    Power BI, dikdörtgen boyutunun toplam satışı temel aldığı, rengin ise kategoriyi gösterdiği bir ağaç haritası oluşturur. Temelde, toplam satışın kategoriye göre boyutunu görsel olarak açıklayan bir hiyerarşi oluşturdunuz. **Men's** kategorisi en yüksek satışa sahipken **Hosiery** kategorisi en düşük satışlara sahiptir.

    ![Yapılandırılmış ağaç haritasının ekran görüntüsü.](media/power-bi-visualization-treemaps/power-bi-complete.png)

1. Ağaç haritanızı tamamlamak için **Depolama** > **Zincir**’i seçerek **Zincir**’i **Ayrıntılar**’a ekleyin. Artık geçen yılın satışlarını kategori ve zincire göre karşılaştırabilirsiniz.

   ![Ayrıntılar'a Store > Chain’in eklendiği ağaç haritasını ekran görüntüsü.](media/power-bi-visualization-treemaps/power-bi-details.png)

   > [!NOTE]
   > Renk doygunluğu ve Ayrıntılar aynı anda kullanılamaz.

1. **Category**'nin bu kısmı için araç ipucunu göstermek üzere bir **Chain** alanının üzerine gelin.

    Örneğin, imleç **090-Home** dikdörtgeninde **Fashions Direct** üzerine getirildiğinde dikdörtgen, Home kategorisinin Fashions Direct bölümü için araç ipucunu görüntüler.

   ![Görüntülenen Giriş araç ipucunun ekran görüntüsü.](media/power-bi-visualization-treemaps/treemaphoverdetail-new.png)


## <a name="highlighting-and-cross-filtering"></a>Vurgulama ve çapraz filtreleme

Ağaç haritasında bir **Kategori** veya **Ayrıntı** vurgulandığında rapor sayfasındaki diğer görselleştirmeler çapraz filtrelenir. Örneği takip etmek için, bu rapor sayfasına bazı görseller ekleyin veya ağaç haritasını bu rapordaki diğer sayfalardan birine kopyalayın. Aşağıdaki görüntüde ağaç haritası **Genel Bakış** sayfasına kopyalanmıştır. 

1. Ağaç haritasında, **Kategori** veya **Kategori**'nin içinden bir **Zincir** seçin. Bu işlem, sayfadaki diğer görselleştirmeleri çapraz vurgulayacaktır. Örneğin **050-Shoes** kategorisi seçildiğinde geçen yılki ayakkabı satışının **16.352.432 ABD doları** olduğu ve bunun **2.174.185 ABD doları** tutarındaki kısmının **Fashions Direct**’ten geldiği görülür.

   ![Çapraz vurgulamayı gösteren Store Sales Overview raporunun ekran görüntüsü.](media/power-bi-visualization-treemaps/treemaphiliting.png)

1. **Zincire göre Geçen Yılın Satışları** pasta grafiğinde, **Fashions Direct** dilimini seçtiğinizde ağaç haritası filtrelenir.
   ![Çapraz filtreleme özelliğinin GIF biçiminde gösterimi.](media/power-bi-visualization-treemaps/treemapnoowl.gif)

1. Grafiklerin birbirini çapraz vurgulamasını ve çapraz filtrelemesini yönetmek için bkz. [Power BI raporunda görseller arasındaki etkileşimi değiştirme](../create-reports/service-reports-visual-interactions.md).

## <a name="next-steps"></a>Sonraki adımlar

* [Power BI’daki şelale grafikler](power-bi-visualization-waterfall-charts.md)

* [Power BI'daki görselleştirme türleri](power-bi-visualization-types-for-reports-and-q-and-a.md)

