---
title: "Kart görselleştirmeleri (diğer adıyla büyük sayı kutucukları)"
description: "Power BI'da Kart görselleştirmesi oluşturma"
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
ms.date: 12/24/2017
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: f38f3bb19be268cba4745c88aa98d09c080c773e
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/24/2018
---
# <a name="card-visualizations"></a>Kart görselleştirmeleri
Bazen Power BI panonuzda veya raporunuzda izlemek istediğiniz en önemli şey (örneğin, toplam satış, yıldan yıla pazar payı veya toplam fırsat) tek bir sayı olabilir. Bu görselleştirme türüne *Kart* adı verilir. Diğer tüm yerel Power BI görselleştirmelerinde olduğu gibi Kartlar da rapor düzenleyicisi veya Soru-Cevap kullanılarak oluşturulabilir.

![kart görselleştirmesi](media/power-bi-visualization-card/pbi_opptuntiescard.png)

## <a name="create-a-card-using-the-report-editor"></a>Rapor düzenleyicisini kullanarak kart oluşturma
Bu yönergelerde Perakende Analizi Örneği kullanılmaktadır. Yönergeleri takip etmek için Power BI hizmeti (app.powerbi.com) veya Power BI Desktop [örneğini indirin](sample-datasets.md).   

1. [Boş rapor sayfasıyla](power-bi-report-add-page.md) başlayın ve **Store** \> **Open store count** alanını seçin. Power BI hizmetini kullanıyorsanız raporu [Düzenleme Görünümü](service-interact-with-a-report-in-editing-view.md)'nde açmanız gerekir.

    Power BI, tek sayı içeren bir sütun grafiği oluşturur.

   ![](media/power-bi-visualization-card/pbi_rptnumbertilechart.png)
2. Görsel Öğeler bölmesinde Kart simgesini seçin.

   ![](media/power-bi-visualization-card/pbi_changechartcard.png)
6. Kartın üzerine gelin ve görselleştirmeyi panoya eklemek için raptiye simgesini ![](media/power-bi-visualization-card/pbi_pintile.png) seçin.

   ![](media/power-bi-visualization-card/power-bi-pin-icon.png)
7. Kutucuğu, mevcut bir panoya veya yeni bir panoya sabitleyin.

   * Var olan pano: Açılan listeden panonun adını seçin.
   * Yeni pano: Yeni panonun adını yazın.
8. **Sabitle**'yi seçin.

   Sağ üst köşeye yakın bir noktada çıkan Başarılı iletisi, görselleştirmenin bir kutucuk olarak panonuza eklendiğini bildirir.

   ![](media/power-bi-visualization-card/power-bi-pin-success-message.png)
9. **Panoya git**'i seçin. Burada, sabitlenmiş görselleştirmeyi [düzenleyebilir ve taşıyabilirsiniz](service-dashboard-edit-tile.md).


## <a name="create-a-card-from-the-qa-question-box"></a>Soru-Cevap soru kutusundan kart oluşturma
Soru-Cevap soru kutusu, Kart oluşturmanın en kolay yoludur. Soru-Cevap soru kutusuna Power BI hizmetinde (app.powerbi.com) bir panodan veya rapordan erişebilirsiniz. Aşağıdaki adımlar Power BI hizmeti panosundan Kart oluşturmayı anlatmaktadır. Power BI Desktop'taki Soru-Cevap özelliğini kullanarak kart oluşturmak isterseniz Desktop raporları için Soru-Cevap önizlemesi [yönergelerini izleyin](https://powerbi.microsoft.com/en-us/blog/power-bi-desktop-december-feature-summary/#QandA).

1. Bir [pano](service-dashboards.md) oluşturun ve [veri alın](service-get-data.md). Bu örnekte [Fırsat Analizi Örneği](sample-opportunity-analysis.md) kullanılmaktadır.

1. Panonuzun en üstündeki soru kutusuna verilerinizle ilgili olarak öğrenmek istediklerinizi yazmaya başlayın. 

   ![](media/power-bi-visualization-card/power-bi-q-and-a-box.png)

>**İPUCU**: Power BI hizmeti raporunun [Düzenleme görünümü](service-reading-view-and-editing-view.md)'nde üstteki menü çubuğundan **Bir soru sorun**'u seçin. Power BI Desktop raporunda boş alan bulun ve çift tıklayarak soru kutusu açın.

3. Örneğin soru kutusuna "number of opportunities" yazın.

   ![](media/power-bi-visualization-card/power-bi-q-and-a.png)

   Soru kutusu öneri ve ifade önerilerinde bulunduktan sonra toplam sayıyı görüntüler.  
4. Kartı panoya eklemek için sağ üst köşedeki raptiye simgesini ![](media/power-bi-visualization-card/pbi_pintile.png) seçin.

   ![](media/power-bi-visualization-card/power-bi-pin.png)
5. Kartı mevcut bir panoya veya yeni bir panoya kutucuk olarak sabitleyin.

   * Var olan pano: Açılan listeden panonun adını seçin. Seçimleriniz, geçerli çalışma alanındaki panolarla sınırlı olacaktır.
   * Yeni pano: Yeni panonun adını yazarak geçerli çalışma alanınıza eklenmesini sağlayabilirsiniz.
6. **Sabitle**'yi seçin.

   Sağ üst köşeye yakın bir noktada çıkan Başarılı iletisi, görselleştirmenin bir kutucuk olarak panonuza eklendiğini bildirir.  

   ![](media/power-bi-visualization-card/power-bi-success.png)
7. Yeni kutucuğu görmek için **Panoya git**'i seçin. Buradan panonuzda [kutucukla ilgili yeniden adlandırma, yeniden boyutlandırma, köprü ekleme, yeniden konumlandırma ve diğer işlemleri](service-dashboard-edit-tile.md) gerçekleştirebilirsiniz.

   ![](media/power-bi-visualization-card/power-bi-pinned.png)

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme
- Soru kutusu görmüyorsanız sistem veya kiracı yöneticinizle iletişime geçin.    
- Desktop uygulamasını kullanıyorsanız ve rapordaki boş alana çift tıkladığınızda Soru-Cevap açılmıyorsa bu özelliği etkinleştirmeniz gerekebilir.  **Dosya > Seçenekler ve Ayarlar > Seçenekler > Önizleme özellikleri > Soru-Cevap** yolunu izleyip Desktop uygulamasını yeniden başlatın.


## <a name="next-steps"></a>Sonraki adımlar
[Power BI'daki pano kutucukları](service-dashboard-tiles.md)

[Power BI'daki panolar](service-dashboards.md)

[Power BI - Temel Kavramlar](service-basic-concepts.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)
