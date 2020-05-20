---
title: Ana Performans Göstergesi (KPI) görselleri
description: Power BI’da Ana Performans Göstergesi (KPI) görselleri oluşturma
author: mihart
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: tutorial
ms.date: 01/30/2020
ms.author: rien
LocalizationGroup: Visualizations
ms.openlocfilehash: c125f1cdd30a717ae7f4cdb93cbf8ea5ed858e79
ms.sourcegitcommit: a72567f26c1653c25f7730fab6210cd011343707
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83564735"
---
# <a name="create-key-performance-indicator-kpi-visualizations"></a>Ana performans göstergesi (KPI) görselleştirmeleri oluşturma

[!INCLUDE[consumer-appliesto-nyyn](../includes/consumer-appliesto-nyyn.md)]

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

Ana Performans Göstergesi (KPI), ölçülebilen bir hedefe yönelik ilerlemeyi gösteren bir görsel ipucudur. KPI’ler hakkında daha fazla bilgi için bkz. [PowerPivot’da Ana Performans Göstergeleri (KPI’ler)](https://support.office.com/en-us/article/Key-Performance-Indicators-KPIs-in-Power-Pivot-E653EDEF-8A21-40E4-9ECE-83A6C8C306AA).


## <a name="when-to-use-a-kpi"></a>KPI'ler ne zaman kullanılır?

KPI'ler şunlar için harika seçimdir:

* İlerleme durumunu ölçme. “Hangi konularda ilerideyim veya hangilerinde gerideyim?” sorusunu yanıtlama.

* Hedefe olan uzaklığı ölçme. “Ne kadar ileride veya gerideyim?” sorusunu yanıtlama.

## <a name="kpi-requirements"></a>KPI gereksinimleri

Tasarımcı, KPI görselini belirli bir ölçüyü temel alarak oluşturur. KPI’nin amacı bir ölçümün geçerli değer ve durumunu tanımlanmış bir hedefe karşı değerlendirmenize yardımcı olmaktır. KPI görselleri, değer döndüren bir *temel* ölçü, bir *hedef* ölçü veya değer ve bir *eşik* ya da *hedef* gerektirir.

KPI veri kümelerinin bir KPI için hedef değerleri içermesi gerekir. Veri kümenizde hedef değerleri bulunmuyorsa veri modelinize veya PBIX dosyanıza hedefleri içeren bir Excel sayfası ekleyerek oluşturabilirsiniz.

## <a name="prerequisites"></a>Önkoşullar

Bu öğreticide [Perakende Analizi örneği .PBIX dosyası](https://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix) kullanılmıştır.

1. Menü çubuğunun sol üst köşesinden **Dosya** > **Aç**’ı seçin

1. **Perakende Analizi örneği PBIX dosyasının** kopyasını bulun

1. Rapor görünümünde **Perakende Analizi örneği PBIX dosyasını** açın. ![Rapor görünümü simgesinin ekran görüntüsü.](media/power-bi-visualization-kpi/power-bi-report-view.png)

1. Yeni sayfa eklemek için **+** simgesini seçin. ![Sarı sekmenin ekran görüntüsü.](media/power-bi-visualization-kpi/power-bi-yellow-tab.png)

> [!NOTE]
> Raporunuzu bir Power BI iş arkadaşınızla paylaşmak için her ikinizin de bireysel Power BI Pro lisanslarınızın olması veya raporun Premium kapasitede depolanması gerekir.    

## <a name="how-to-create-a-kpi"></a>KPI'ler nasıl oluşturulur?

Bu örnekte bir satış hedefine göre kaydettiğiniz ilerlemeyi ölçen bir KPI oluşturacaksınız.

1. **Alanlar** bölmesinden **Sales > Total Units This Year** alanını seçin.  Bu değer gösterge olacaktır.

1. **Zaman > FiscalMonth** ekleyin  Bu değer eğilimi temsil eder.

1. Görselin sağ üst köşesindeki üç nokta simgesini seçin ve Power BI’ın sütunları **FiscalMonth** ile artan düzende sıralayıp sıralamadığını kontrol edin.

    > [!IMPORTANT]
    > Görselleştirmeyi KPI'ye çevirdikten sonra sıralama **yapamazsınız**. Bu aşamada doğru sıralamanız gerekir.

    ![Artan düzende sıralama ve FiscalMonth seçeneklerinin belirlendiği genişletilmiş üç nokta menüsünün ekran görüntüsü.](media/power-bi-visualization-kpi/power-bi-ascending-by-fiscal-month.png)

    Doğru sıralandıktan sonra görseliniz şöyle görünür:

    ![Görselin doğru sıralandığı ekran görüntüsü.](media/power-bi-visualization-kpi/power-bi-chart.png)

1. **Görselleştirme** bölmesindeki **KPI** simgesini seçerek görseli bir KPI'ye dönüştürün.

    ![KPI simgesinin öne çıkarıldığı Görselleştirmeler bölmesinin ekran görüntüsü.](media/power-bi-visualization-kpi/power-bi-kpi-template.png)

1. Hedef eklemek için **Total Units Last Year** alanını **Target goals** alanına ekleyin.

    ![Değerlerin belirtildiği, tamamlanmış KPI görseli ve Alanlar bölmesinin ekran görüntüsü.](media/power-bi-visualization-kpi/power-bi-kpi-done.png)

1. İsteğe bağlı olarak, Biçimlendirme bölmesini açmak üzere boya rulosu simgesini seçerek KPI'yi biçimlendirebilirsiniz.

    * **Gösterge**: göstergenin görüntü birimlerini ve ondalık basamakları denetler.

    * **Eğilim ekseni**: **Açık** olarak ayarlandığında, eğilim eksenini KPI görselinin arka planı olarak gösterilir.  

    * **Hedefler**: **Açık** olarak belirlendiğinde, görsel, hedefi ve yüzde olarak hedefe olan mesafeyi gösterir.

    * **Renk kodlaması > Yön**: Bazı KPI'ler *yüksek* değerler için daha uygun görülürken bazılarının ise *düşük* değerler için daha uygun olduğu düşünülür. Örneğin kazanç ile bekleme süresi karşılaştırması. Genellikle, kazanç değerinin daha yüksek olması bekleme süresinin daha yüksek olmasından iyidir. **Yüksek iyidir**'i seçin ve isterseniz renk ayarlarını değiştirin.

KPI’leri Power BI hizmetinde ve mobil cihazlarınızda kullanabilirsiniz. İşletmenizin can damarına her zaman bağlı olma seçeneği getirir.

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme

KPI'niz yukarıdaki gibi görünmüyorsa **FiscalMonth**’a göre sıralama yapmamış olabilirsiniz. KPI’lerin sıralama seçeneği yoktur. Yeniden başlayarak görselleştirmenizi KPI’ye dönüştürmeden *önce* **FiscalMonth**’a göre sıralamanız gerekir.

## <a name="next-steps"></a>Sonraki adımlar

* [Power BI Harita görselleştirmeleri için ipuçları ve püf noktaları](power-bi-map-tips-and-tricks.md)

* [Power BI'daki görselleştirme türleri](power-bi-visualization-types-for-reports-and-q-and-a.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)
