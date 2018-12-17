---
title: KPI görselleri
description: Power BI’da KPI görselleri oluşturma
author: mihart
manager: kvivek
ms.reviewer: ''
featuredvideoid: xmja6EpqaO0
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: tutorial
ms.date: 11/24/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: c726ba8d50f077a640879f666fd441e27b19d3c7
ms.sourcegitcommit: 4f46d71ff6026c1c158f007425aefdcb501f48ee
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/06/2018
ms.locfileid: "52979364"
---
# <a name="kpi-visuals"></a>KPI görselleri
Ana Performans Göstergesi (KPI), ölçülebilen bir hedefe yönelik ilerlemeyi gösteren bir görsel ipucudur. KPI'ler hakkında daha fazla bilgi için bkz. [Microsoft Developer Network](https://msdn.microsoft.com/library/hh272050).

Power BI’ya kaydolmadıysanız başlamadan önce [ücretsiz deneme için kaydolun](https://app.powerbi.com/signupredirect?pbi_source=web).

## <a name="prerequisites"></a>Önkoşullar
* [Power BI Desktop ücretsizdir.](https://powerbi.microsoft.com/en-us/get-started/)
* [Perakende Analizi örneği PBIX dosyası](http://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix)

## <a name="when-to-use-a-kpi"></a>KPI'ler ne zaman kullanılır?
KPI'ler şunlar için harika seçimdir:

* ilerlemeyi ölçme (ne kadar geride ne kadar ilerideyim?)
* bir hedef için kalan mesafeyi ölçme (ne kadar yakın ne kadar uzağım?)   

## <a name="kpi-requirements"></a>KPI gereksinimleri
Ana Performans Göstergeleri, (KPI'ler) belirli bir ölçüyü temel alır ve geçerli değerin yanı sıra tanımlanmış bir hedefle ilgili ölçümün durumunu değerlendirmenize yardımcı olacak şekilde tasarlanmıştır. Bu nedenle, KPI görselleri, değer döndüren bir *temel* ölçü, bir *hedef* ölçü veya değer ve bir *eşik* ya da *hedef* gerektirir.

Geçerli sürümde KPI veri kümelerinin bir KPI için hedef değerleri içermesi gerekir. Veri kümenizde bulunmuyorsa veri modelinize veya PBIX dosyanıza hedefleri içeren bir Excel sayfası ekleyerek hedefler oluşturabilirsiniz.


## <a name="how-to-create-a-kpi"></a>KPI'ler nasıl oluşturulur?
Takip etmek için, Power BI Desktop’ta [Perakende Analizi örneği .PBIX dosyasını](http://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix) açın. Bir satış hedefi için kaydettiğimiz ilerlemeyi ölçen bir KPI oluşturacağız.

Alternatif olarak, Will şu tek ölçümlü görselleri oluştururken ona eşlik edebilirsiniz: ölçerler, kartlar ve KPI'ler.

<iframe width="560" height="315" src="https://www.youtube.com/embed/xmja6EpqaO0?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

1. Rapor görünümü'nde raporu açın ve yeni bir sayfa eklemek için sarı sekmeyi seçin.    
2. Alanlar bölmesinden, **Satışlar > Bu Yılki Toplam Birim**’i seçin  Bu göstergedir.
3. **Zaman > FiscalMonth** ekleyin  Bu, eğilimi gösterir.
4. ÖNEMLİ: Grafiği **FiscalMonth** ölçütüne göre sıralayın. Görselleştirmeyi KPI'ye çevirdikten sonra sıralama yapamazsınız.

    ![](media/power-bi-visualization-kpi/power-bi-chart.png)
5. Görsel Öğeler bölmesindeki KPI simgesini seçerek görseli bir KPI'ye dönüştürün.
   
    ![](media/power-bi-visualization-kpi/power-bi-kpi-template.png)
6. Bir hedef ekleyin. Hedef olarak geçen yılın satışlarını ekleyin. **Total Units Last Year** alanını **Hedefler** alanına ekleyin.
   
    ![](media/power-bi-visualization-kpi/power-bi-kpi-done.png)
7. İsteğe bağlı olarak, Biçimlendirme bölmesini açmak üzere boya rulosu simgesini seçerek KPI'yi biçimlendirebilirsiniz.
   
   * **Gösterge**: göstergenin görüntü birimlerini ve ondalık basamakları denetler.
   * **Eğilim ekseni**: **Açık** olarak ayarlandığında, KPI görselinin arka planı olarak eğilim ekseni görüntülenir.  
   * **Hedefler**: **Açık** olarak belirlendiğinde, görsel, hedefi ve yüzde olarak hedefe olan mesafeyi görüntüler.
   * **Renk kodlaması > Yön**: Bazı KPI'ler yüksek değerler için *daha uygun* görülürken bazılarının ise düşük değerler için *daha uygun* olduğu düşünülür. Örneğin kazanç ile bekleme süresi karşılaştırması. Genellikle, kazanç değerinin daha yüksek olması bekleme süresinin daha yüksek olmasından iyidir. **Yüksek daha iyidir**'i seçin ve isterseniz renk ayarlarını değiştirin.


KPI'leri Power BI hizmetinden ve mobil cihazlarınızda da kullanabilir, işinizin durumundan her zaman haberdar olabilirsiniz.

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme
* KPI'niz yukarıdaki gibi görünmüyorsa mali aya göre sıralama yapmamış olabilirsiniz. KPI'lerde sıralama seçeneği bulunmadığından görselleştirmenizi bir KPI'ye dönüştürmeden *önce* mali aya göre sıralama yapmanız gerekir.

## <a name="next-steps"></a>Sonraki adımlar

[Power BI’daki temel haritalar](power-bi-map-tips-and-tricks.md)

[Power BI'daki görselleştirme türleri](power-bi-visualization-types-for-reports-and-q-and-a.md)