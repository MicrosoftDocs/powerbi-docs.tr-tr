---
title: "KPI görselleri (Eğitim)"
description: "Power BI'da KPI oluşturma"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: xmja6EpqaO0
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 08/09/2017
ms.author: mihart
ms.openlocfilehash: 23b322c9fbc4c203a5b20aa45bb41c2cb6cb7f0f
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2017
---
# <a name="kpi-visuals-tutorial"></a>KPI görselleri (Eğitim)
Ana Performans Göstergesi (KPI), ölçülebilen bir hedefe yönelik ilerlemeyi gösteren bir görsel ipucudur. KPI'ler hakkında daha fazla bilgi için bkz. [Microsoft Developer Network](https://msdn.microsoft.com/library/hh272050).

## <a name="when-to-use-a-kpi"></a>KPI'ler ne zaman kullanılır?
KPI'ler şunlar için harika seçimdir:

* ilerlemeyi ölçme (ne kadar geride ne kadar ilerideyim?)
* bir hedef için kalan mesafeyi ölçme (ne kadar yakın ne kadar uzağım?)   

## <a name="kpi-visual-requirements"></a>KPI görseli gereksinimleri
Ana Performans Göstergeleri, (KPI'ler) belirli bir ölçüyü temel alır ve geçerli değerin yanı sıra tanımlanmış bir hedefle ilgili ölçümün durumunu değerlendirmenize yardımcı olacak şekilde tasarlanmıştır. Bu nedenle, KPI görselleri, değer döndüren bir *temel* ölçü, bir *hedef* ölçü veya değer ve bir eşik ya da hedef gerektirir.

> [!NOTE]
> Geçerli sürümde KPI veri kümelerinin bir KPI için hedef değerleri içermesi gerekir. Veri kümenizde bulunmuyorsa veri modelinize veya PBIX dosyanıza hedefleri içeren bir Excel sayfası ekleyerek hedefler oluşturabilirsiniz.
> 
> 

## <a name="how-to-create-a-kpi"></a>KPI'ler nasıl oluşturulur?
Birlikte ilerleyebilmek için, Power BI'da oturum açın ve **Veri Al > Örnekler > Perakende Analizi Örneği**'ni seçin. Bir satış hedefi için kaydettiğimiz ilerlemeyi ölçen bir KPI oluşturacağız.

Alternatif olarak, Will şu tek ölçümlü görselleri oluştururken ona eşlik edebilirsiniz: ölçekler, kartlar ve KPI'ler.

<iframe width="560" height="315" src="https://www.youtube.com/embed/xmja6EpqaO0?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

1. **Sales > Total Units This Year** seçeneğini belirleyin.  Bu göstergedir.
2. **Time > Month** seçeneğini ekleyin.  Bu, eğilimi gösterir.
3. ÖNEMLİ: Grafiği sıralamak için **Month** ölçütünü kullanın. Görselleştirmeyi KPI'ye çevirdikten sonra sıralama yapamazsınız.
4. Görsel Öğeler bölmesindeki KPI simgesini seçerek görseli bir KPI'ye dönüştürün.
   
    ![](media/power-bi-visualization-kpi/power-bi-kpi-icon.png)
5. Bir hedef ekleyin. Hedef olarak geçen yılın satışlarını ekleyin. **Total Units Last Year** alanını **Hedefler** alanına ekleyin.
   
    ![](media/power-bi-visualization-kpi/power-bi-kpi.png)
6. İsteğe bağlı olarak, Biçimlendirme bölmesini açmak üzere boya rulosu simgesini seçerek KPI'yi biçimlendirebilirsiniz.
   
   * **Gösterge**: göstergenin görüntü birimlerini ve ondalık basamakları denetler.
   * **Eğilim ekseni**: **Açık** olarak ayarlandığında, KPI görselinin arka planı olarak eğilim ekseni görüntülenir.  
   * **Hedefler**: **Açık** olarak belirlendiğinde, görsel, hedefi ve yüzde olarak hedefe olan mesafeyi görüntüler.
   * **Durum**: Bazı KPI'ler yüksek değerler için *daha uygun* görülürken bazılarının ise düşük değerler için *daha uygun* olduğu düşünülür. Örneğin, kazançlar ve bekleme süresi. Genellikle, kazanç değerinin daha yüksek olması bekleme süresinin daha yüksek olmasından iyidir, hatta ikincisinin genellikle daha kötü olduğu düşünülür. Bu geçiş düğmesi, KPI davranışının seçilebilmesini sağlar. Durum seçimi için **daha yüksek daha iyi** varsayılan olarak ayarlanmıştır.
7. KPI'nizi istediğiniz şekilde ayarladıktan sonra [panoya sabitleyin](service-dashboard-pin-tile-from-report.md).

KPI'leri mobil cihazlarınızda da kullanabilir ve işinizin durumundan her zaman haberdar olabilirsiniz

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme
* KPI'niz yukarıdaki gibi görünmüyorsa aya göre sıralama yapmamış olabilirsiniz. KPI'lerde sıralama seçeneği bulunmadığından görselleştirmenizi bir KPI'ye dönüştürmeden *önce* aya göre sıralama yapmanız gerekir.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI'daki raporlar](service-reports.md)

[Power BI raporlarındaki görselleştirmeler](power-bi-report-visualizations.md)

[Power BI - Temel Kavramlar](service-basic-concepts.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

