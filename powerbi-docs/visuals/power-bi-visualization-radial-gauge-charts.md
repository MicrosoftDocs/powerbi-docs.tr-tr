---
title: Power BI'da radyal ölçer grafikleri
description: Power BI'da radyal ölçer grafikleri
author: mihart
ms.author: mihart
ms.reviewer: mihart
featuredvideoid: ''
ms.service: powerbi
ms.subservice: pbi-visuals
ms.topic: conceptual
ms.date: 06/17/2020
LocalizationGroup: Visualizations
ms.openlocfilehash: 013e9f3143c485fd63a160f8d124e313b7c2edc6
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96418843"
---
# <a name="radial-gauge-charts-in-power-bi"></a>Power BI'da radyal ölçer grafikleri

[!INCLUDE[consumer-appliesto-nyyn](../includes/consumer-appliesto-nyyn.md)]

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

Radyal ölçerler dairesel bir yay içerir ve belirli bir hedefe veya Ana Performans Göstergesi’ne (KPI) yönelik ilerlemeyi ölçen tek bir değeri gösterir. Satır veya (*iğne*) hedeflenen veya amaçlanan değeri temsil eder. Gölgelendirme, hedefe yönelik ilerlemeyi temsil eder. Yayın içindeki değer ilerleme değerini temsil eder. Power BI, olası tüm değerleri minimumdan (en soldaki değer) başlayıp maksimumda (en sağdaki değer) sonlanacak şekilde yay boyunca eşit olarak dağıtır.

![Radyal ölçer ekran görüntüsü.](media/power-bi-visualization-radial-gauge-charts/gauge-m.png)

Bu örnekte, satış ekibinin aylık ortalama satışlarını izleyen bir araba satıcısı olduğunuzu varsayın. İğne 140 arabalık satış hedefini temsil eder. Mümkün olan minimum ortalama satış 0, maksimum ortalama satış ise 200’dür.  Mavi gölge, ekibin bu ayki ortalama satışının 120 olduğunu gösteriyor. Neyse ki, hedefe ulaşmak için bir hafta daha bulunuyor.

> [!NOTE]
> Raporunuzu bir Power BI iş arkadaşınızla paylaşmak için her ikinizin de bireysel Power BI Pro lisanslarınızın olması veya raporun Premium kapasitede depolanması gerekir.

## <a name="when-to-use-a-radial-gauge"></a>Radyal ölçer ne zaman kullanılır?

Radial ölçerler şunlar için harika bir seçimdir:

* Bir hedefe yönelik ilerlemeyi göstermek.

* KPI gibi bir yüzde değerini göstermek.

* Tek bir ölçünün durumunu göstermek.

* Hızla tarayıp anlayabileceğiniz bilgileri görüntüleyin.

## <a name="prerequisites"></a>Önkoşullar

Bu öğreticide [Financial Sample Excel dosyası](https://go.microsoft.com/fwlink/?LinkID=521962) kullanılır.

1. Menü çubuğunun sol üst kısmından **Veri Al** > **Excel**’i seçin
   
2. **Financial sample Excel dosyası** kopyanızı bulun

1. **Financial sample Excel dosyası**’nı rapor görünümünde ![Rapor görünümü simgesinin ekran görüntüsü.](media/power-bi-visualization-kpi/power-bi-report-view.png) açın.

1. **Mali** ve **Sayfa1**’i seçin

1. **Yükle**’ye tıklayın

1. Seç ![Sarı sekmenin ekran görüntüsü.](media/power-bi-visualization-kpi/power-bi-yellow-tab.png) yeni bir sayfa ekleyin.



## <a name="create-a-basic-radial-gauge"></a>Basit bir radyal ölçer oluşturma

### <a name="step-1-create-a-gauge-to-track-gross-sales"></a>1\. Adım: Gross Sales (Brüt Satış) değerini izlemeye yönelik bir ölçer oluşturma

1. Boş bir rapor sayfasında başlayın

1. **Alanlar** bölmesinden, **Gross Sales** seçeneğini belirleyin.

   ![Brüt Satışlar seçili ve genişletilmiş finansal tablolar](media/power-bi-visualization-radial-gauge-charts/grosssalesvalue-new.png)

1. Toplama işlemini **Ortalama** olarak değiştirin.

   ![Toplam değer işaretlenmiş olarak Gross Sales ve ortalama toplam alanlar bölmesinin ekran görüntüsü.](media/power-bi-visualization-radial-gauge-charts/changetoaverage-new.png)

1. Ölçer simgesini seçin ![Ölçer simgesi ekran görüntüsü.](media/power-bi-visualization-radial-gauge-charts/gaugeicon-new.png) Sütun grafiğini ölçer grafiğe dönüştürmek için.

    ![Ölçer grafiği ekran görüntüsü.](media/power-bi-visualization-radial-gauge-charts/gauge-no-target.png)

    **Financial Sample** dosyasını ne zaman indirdiğinize bağlı olarak, bu sayılarla eşleşmeyen sayılar görebilirsiniz.

    > [!TIP]
    > Varsayılan olarak, Power BI, geçerli değerin (bu örnekte, **Ortalama Gross Sales**) ölçerin ortasındaki değer olduğunun varsayıldığı bir ölçer grafiği oluşturur. **Ortalama Brüt Satış** değeri 182.760 ABD doları olduğundan, başlangıç değeri (Minimum) 0 olarak, bitiş değeri ise (Maksimum) geçerli değerin iki katı olarak ayarlanır.

### <a name="step-3-set-a-target-value"></a>3\. Adım: Hedef değer ayarlama

1. **COGS**’yi **Alanlar** bölmesinden **Hedef değer** kutusuna sürükleyin.

1. Toplama işlemini **Ortalama** olarak değiştirin.

   Power BI **$145.48K** olan hedef değerimizi gösteren bir iğne ekler.

   ![COGS ortalamasının da eklendiği ölçer grafik ekran görüntüsü.](media/power-bi-visualization-radial-gauge-charts/gaugeinprogress-new.png)

    Hedefimize ulaştığımıza dikkat edin.

   > [!NOTE]
   > Elle de bir hedef değer girebilirsiniz. [Minimum, Maksimum ve Hedef değerleri belirlemek için el ile biçimlendirme seçeneklerini kullanma](#use-manual-format-options-to-set-minimum-maximum-and-target-values) bölümüne bakın.

### <a name="step-4-set-a-maximum-value"></a>4\. Adım: Maksimum değer ayarlama

2\. Adımda, Power BI, minimum ve maksimum değerleri otomatik olarak ayarlamak için **Değer** alanını kullanmıştır. Peki ya maksimum değeri kendiniz belirlemek isterseniz? Mümkün olan maksimum değer olarak geçerli değerin iki katı yerine veri kümenizdeki en yüksek Brüt Satış değerini belirlemek istediğinizi varsayalım.

1. **Alanlar** bölmesindeki **Gross Sales** alanını **Maksimum Değer** kutusuna sürükleyin.

1. Toplama işlemini **Maksimum** olarak değiştirin.

   ![Gross Sales ve Maksimum toplam değer işaretlenmiş olarak Alanlar bölmesinin ekran görüntüsü.](media/power-bi-visualization-radial-gauge-charts/setmaximum-new.png)

   Ölçer, yeni bir bitiş değeriyle (Brüt satıştaki 1,21 milyon değeri) yeniden çizilir.

   ![Tamamlanmış ölçer grafiği ekran görüntüsü.](media/power-bi-visualization-radial-gauge-charts/power-bi-final-gauge.png)

### <a name="step-5-save-your-report"></a>5\. Adım: Raporunuzu kaydedin

1. [Raporu kaydedin](../create-reports/service-report-save.md).

## <a name="use-manual-format-options-to-set-minimum-maximum-and-target-values"></a>Minimum, Maksimum ve Hedef değerleri ayarlamak için el ile biçimlendirme seçeneklerini kullanma

1. **Max of Gross Sales** alanını **Maksimum değer** kutusundan kaldırın.

1. **Biçim** bölmesini açmak için boya rulosu simgesini seçin.

   ![Boya rulosu simgesi işaretlenmiş olarak Ölçer grafiği ve Format bölmesi ekran görüntüsü.](media/power-bi-visualization-radial-gauge-charts/power-bi-roller.png)

1. **Ölçer ekseni**'ni genişletin ve **Minimum** ve **Maksimum** değerleri girin.

    ![Ölçer ekseni seçenekleri ekran görüntüsü.](media/power-bi-visualization-radial-gauge-charts/power-bi-gauge-axis.png)

1. Hedef değeri kaldırmak için **Alanlar** bölmesinden **COGS** seçeneğini temizleyin.

    ![Temizlenmiş COGS seçeneği ekran görüntüsü.](media/power-bi-visualization-radial-gauge-charts/pbi-remove-target.png)

1. **Ölçer ekseni**'nin altında **Hedef** alanı göründüğünde, buraya bir değer girin.

     ![Hedef işaretlenmiş olarak Ölçer ekseni seçenekleri ekran görüntüsü.](media/power-bi-visualization-radial-gauge-charts/power-bi-gauge-target.png)

1. İsteğe bağlı olarak, ölçer grafiğinizi biçimlendirmeye devam edebilirsiniz.

Bu adımları tamamladıktan sonra şuna benzeyen bir ölçer grafiğiniz olur:

![Ölçer grafiğinin son hali ekran görüntüsü.](media/power-bi-visualization-radial-gauge-charts/power-bi-final.png)

## <a name="next-step"></a>Sonraki adım

* [Ana Performans Göstergesi (KPI) görselleri](power-bi-visualization-kpi.md)

* [Power BI'daki görselleştirme türleri](power-bi-visualization-types-for-reports-and-q-and-a.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)

