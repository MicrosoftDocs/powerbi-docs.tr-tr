---
title: "Power BI raporlarında grafiklerin sıralanma biçimini değiştirme"
description: "Power BI raporlarında grafiklerin sıralanma biçimini değiştirme"
services: powerbi
documentationcenter: 
author: mihart
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
ms.date: 09/08/2017
ms.author: mihart
ms.openlocfilehash: 37161fab1e19e6ce00eb0f02c96b6e5cbdd60f18
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="change-how-a-chart-is-sorted-in-a-power-bi-report"></a>Power BI raporlarında grafiklerin sıralanma biçimini değiştirme
Power BI'da grafikleri kategori adlarına göre alfabetik şekilde veya kategorilerin sayısal değerlerine göre sıralayabilirsiniz. Örneğin, bu grafik mağaza adına göre sıralanmıştır.

![](media/power-bi-report-change-sort/pbi_chartsortcategory.png)

Bunun yerine metrekare başına satışa göre en yüksekten en düşüğe doğru sıralama yapmak oldukça kolaydır.

1. Üç nokta (...) simgesini seçin ve ardından **Sıralama ölçütü: Sales Per Sq Ft** seçeneğini belirleyin.
2. Gerekirse sıralama simgesini ![](media/power-bi-report-change-sort/sorticon.png) seçerek **Azalan** düzene geçin.
   
   ![](media/power-bi-report-change-sort/sortby.gif)
   
   **NOT**: Her görsel sıralanamaz.  Örneğin, şu görselleri sıralamak mümkün değildir: Ağaç Haritası, Harita, Doldurulmuş Harita, Dağılım, Ölçek, Kart, Çok Satırlı Kart, Şelale.

## <a name="sorting-using-other-criteria"></a>Diğer ölçütleri kullanarak sıralama
Bazı durumlarda görselinizi farklı bir alana veya ölçüte göre sıralamak isteyebilirsiniz.  Örneğin, aya göre (alfabetik sırada değil) veya tek basamak yerine sayının tamamına göre (ör. 0, 1, 20, 9 değil 0, 1, 9, 20 şeklinde) sıralama yapmak isteyebilirsiniz.  

Bazı durumlarda görseli istediğiniz şekilde (örneğin, aya göre) sıralayabilirsiniz.  Aksi halde, raporun temel aldığı veri kümesinde değişiklik yapmanız gerekebilir. Kullanabileceğiniz çeşitli çözümler aşağıda verilmiştir:

* Power BI Desktop'ta, [Veri Araçları Modelleme sekmesini kullanarak başka bir sütuna göre sıralama yapın](desktop-sort-by-column.md).
* Veri kümesinin sahibi sizseniz Excel'de ay adını ve sayıyı birleştiren yeni bir sütun oluşturun. Ardından veri kümesini yenilediğinizde veya yeniden içeri aktardığınızda yeni sütunu Alanlar listesinde görebilirsiniz.
* Excel'deki sayı içeren sütunlarınızın "metin" değil, "tam sayı" veya "ondalık" olarak etiketlendiğinden emin olun.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI raporlarındaki görselleştirmeler](power-bi-report-visualizations.md) hakkında daha fazla bilgi.

[Power BI - Temel Kavramlar](service-basic-concepts.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

