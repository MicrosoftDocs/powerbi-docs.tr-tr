---
title: "Bir Power BI raporundan büyük bir sayı kutucuğu oluşturma"
description: "Bir Power BI raporundan büyük bir sayı kutucuğu oluşturma"
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
ms.date: 09/26/2017
ms.author: mihart
ms.openlocfilehash: 9f748ed1d3a34c6c6aceb14337bbb780598a15f9
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2017
---
# <a name="create-a-big-number-tile-from-a-power-bi-report"></a>Bir Power BI raporundan büyük bir sayı kutucuğu oluşturma
Bazen Power BI panonuzda izlemek istediğiniz en önemli şey (örneğin, toplam satış, yıldan yıla pazar payı veya toplam fırsat) tek bir sayı olabilir. [Soru-Cevap kutusunda soru sorarak](power-bi-visualization-big-number.md) veya bir Power BI raporunda ilgili işlemleri gerçekleştirerek büyük bir sayı kutucuğu oluşturabilirsiniz. Bu makalede söz konusu işlemi bir raporda nasıl yapacağınız açıklanmaktadır.

1. Bir [pano](service-dashboards.md) oluşturun ve [veri alın](service-get-data.md).
   
   Alıştırma yapmak için veriye ihtiyacınız varsa [Perakende Analizi örneğini indirin](sample-retail-analysis.md). 
2. Raporu [Düzenleme Görünümü](service-reading-view-and-editing-view.md)'nde açın.
3. Raporda boş alana sahip bir sayfa bulun veya [rapora yeni bir sayfa ekleyin](power-bi-report-add-page.md).
4. Alanlar listesinde, görüntülemek istediğiniz sayı alanını seçin.
   
   Bu örnekte **Store** tablosundaki **Open Store count** alanını seçtik. Power BI, tek sayı içeren bir sütun grafiği oluşturur.
   
   ![](media/power-bi-visualization-big-number-report/pbi_rptnumbertilechart.png)
5. Görsel Öğeler bölmesinde Kart simgesini seçin.
   
   ![](media/power-bi-visualization-big-number-report/pbi_changechartcard.png)
6. Kartın üzerine gelin ve kutucuğu panoya eklemek için raptiye simgesini ![](media/power-bi-visualization-big-number-report/pbi_pintile.png) seçin. 
   
   ![](media/power-bi-visualization-big-number-report/power-bi-pin-icon.png)
7. Kutucuğu, var olan bir panoya veya yeni bir panoya sabitleyin. 
   
   * Var olan pano: Açılan listeden panonun adını seçin.
   * Yeni pano: Yeni panonun adını yazın.
8. **Sabitle**'yi seçin.
   
   Sağ üst köşeye yakın bir noktada çıkan Başarılı iletisi, görselleştirmenin bir kutucuk olarak panonuza eklendiğini bildirir.
   
   ![](media/power-bi-visualization-big-number-report/power-bi-pin-success-message.png)
9. **Panoya git**'i seçin. Burada, sabitlenmiş görselleştirmeyi [düzenleyebilir ve taşıyabilirsiniz](service-dashboard-edit-tile.md).

## <a name="next-steps"></a>Sonraki adımlar
[Power BI'daki pano kutucukları](service-dashboard-tiles.md)

[Power BI'daki panolar](service-dashboards.md)

[Power BI - Temel Kavramlar](service-basic-concepts.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

