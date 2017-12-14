---
title: "Soru-Cevap'tan kutucukları Power BI panolarına sabitleme"
description: "Soru-Cevap soru kutusundan kutucukları Power BI panolarına sabitlemeye ilişkin belge"
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
ms.date: 09/09/2017
ms.author: mihart
ms.openlocfilehash: f37c0f9e433f1ac8c6bb8f7f3fa4b513fb4b4652
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2017
---
# <a name="pin-a-tile-to-a-dashboard-from-qa"></a>Soru-Cevap'tan kutucukları panolara sabitleme
## <a name="how-to-pin-a-tile-from-qa"></a>Soru-Cevap'tan kutucuk sabitleme
Soru-Cevap, Power BI'daki özel raporlama aracıdır. Belirli bir öngörüyü bulmanız mı gerekiyor? Verileriniz hakkında soru sorun ve görselleştirme şeklinde yanıt alın.

> **NOT**: Örneği takip etmek için [Perakende Analizi örneğini](sample-retail-analysis.md) açın.
> 
> 

1. Raporlardan sabitlenmiş en az bir kutucuk içeren bir [panoyu](service-dashboards.md) açın. Soru sorduğunuzda Power BI, ilgili panoya sabitlenmiş kutucuğa sahip olan veri kümelerinde yanıt arar.  Daha fazla bilgi edinmek için bkz. [Veri alma](service-get-data.md).
2. Panonuzun en üstündeki soru kutusuna verilerinizle ilgili olarak öğrenmek istediklerinizi yazmaya başlayın.  
   ![](media/service-dashboard-pin-tile-from-q-and-a/power-bi-question-box.png)
3. Örneğin, "last year sales by month and territory" (aya ve bölgeye göre geçen yılın satışları)...  
   ![](media/service-dashboard-pin-tile-from-q-and-a/power-bi-type-q-and-a.png)
   
   yazdığınızda soru kutusunda öneriler görüntülenir.
4. Grafiği panonuza kutucuk olarak eklemek için tuvalin sağ üst kısmında bulunan raptiye ![](media/service-dashboard-pin-tile-from-q-and-a/pbi_pintile.png) simgesini seçin.
5. Kutucuğu, var olan bir panoya veya yeni bir panoya sabitleyin. 
   
   * Var olan pano: Açılan listeden panonun adını seçin. Seçimleriniz, geçerli çalışma alanındaki panolarla sınırlı olacaktır.
   * Yeni pano: Yeni panonun adını yazarak geçerli çalışma alanınıza eklenmesini sağlayabilirsiniz.
6. **Sabitle**'yi seçin.
   
   Sağ üst köşeye yakın bir noktada çıkan bir başarı iletisi, görselleştirmenin bir kutucuk olarak panonuza eklendiğini bildirir.  
   
   ![](media/service-dashboard-pin-tile-from-q-and-a/power-bi-pin.png)
7. Yeni kutucuğu görmek için **Panoya git**'i seçin. Buradan panonuzda [kutucukla ilgili yeniden adlandırma, yeniden boyutlandırma, köprü ekleme, yeniden konumlandırma ve diğer işlemleri](service-dashboard-edit-tile.md) gerçekleştirebilirsiniz. 
   
   ![](media/service-dashboard-pin-tile-from-q-and-a/power-bi-pinned.png)

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme
* Soru yazmaya başladığınızda Soru-Cevap özelliği, geçerli panoyla ilişkilendirilmiş olan tüm veri kümelerinden en iyi yanıtı bulmak üzere arama yapmaya başlar.  "Geçerli pano", üst gezinti çubuğunda görünen panodur. Örneğin, bu soru, **mihart** uygulama çalışma alanının bir parçası olan **Retail Analysis Sample** panosunda sorulmaktadır.
  
  ![](media/service-dashboard-pin-tile-from-q-and-a/power-bi-navbar.png)
* **Soru-Cevap hangi veri kümelerinin kullanılacağına nasıl karar veriyor**?  Soru-Cevap özelliği, ilgili panoya sabitlenmiş görselleştirmelere sahip olan tüm veri kümelerine erişim sahibidir.

## <a name="next-steps"></a>Sonraki adımlar
[Kutucukla ilgili yeniden adlandırma, yeniden boyutlandırma, köprü ekleme, yeniden konumlandırma ve diğer işlemleri gerçekleştirme](service-dashboard-edit-tile.md)    
[Pano kutucuğunuzu Odak modunda görüntüleme](service-focus-mode.md)     
[Power BI'daki Soru-Cevap özelliği](service-q-and-a.md)  
Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

