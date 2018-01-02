---
title: "Büyük veri kümelerine yönelik Power BI Premium desteği"
description: "Power BI Premium artık 10 GB’a kadar olan veri kümelerini destekler."
services: powerbi
documentationcenter: 
author: MarkMcGeeAtAquent
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
ms.date: 12/11/2017
ms.author: v-mamcge
ms.openlocfilehash: 82ac4382fe80d83b60705f135b50738718f28876
ms.sourcegitcommit: 7eb15c813a0d14322cb1316bb7aab23cbc13aae6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2017
---
# <a name="power-bi-premium-support-for-large-datasets"></a>Büyük veri kümelerine yönelik Power BI Premium desteği

Power BI Premium, boyutu 10 GB’a kadar olan Power BI Desktop (.pbix) dosyalarının karşıya yüklenmesini destekler. Büyük bir veri kümesini kullanmak için Premium kapasiteye atanmış bir çalışma alanında yayımlayın.
 
## <a name="best-practices"></a>En iyi yöntemler

Bu bölümde, büyük veri kümeleriyle çalışmaya yönelik en iyi yöntemler açıklanmıştır.

Kapasite açısından **büyük modeller yoğun kaynak kullanımı** gerektirebilir; 1 GB’tan büyük tüm modeller için en az P1 SKU önerilir. Aşağıdaki tabloda çeşitli .pbix boyutları için önerilen SKU'lar açıklanmıştır:


   |SKU  |.pbix dosyasının boyutu   |
   |---------|---------|
   |P1    | 3 GB’tan küçük        |
   |P2    | 6 GB’tan küçük        |
   |P3    | 10 GB'a kadar   |



**.pbix dosyalarınız, verileri yüksek oranda sıkıştırılmış bir şekilde temsil eder**. Muhtemelen veriler belleğe yüklenirken birkaç kez genişletilir ve veri yenileme sırasında birkaç kez daha genişletilebilir.

**Büyük veri kümeleri için zamanlanmış yenileme çok uzun sürebilir** ve çok kaynak tüketimi gerektirebilir. Bunu göz önünde bulundurarak çok fazla örtüşen yenileme zamanlamayın. Bu kapasitedeki tüm veri kümeleri için zamanlanmış yenileme işlerinin zaman aşımının da iki kadına çıkarak dört saat olduğuna dikkat edin.

Veritabanı en son uzun bir süre önce kullanılmışsa, model Premium kapasitenizin belleğine yüklendiği için **büyük veri kümelerinin ilk raporunun yüklenmesi uzun zaman alabilir**. Yüklenmesi nispeten uzun süren raporların ilerleme durumunu göstermek için bir yükleme çubuğu görüntülenir.

**Çalışma alanını Premium kapasiteden kaldırırsanız** model ve modelle ilişkili hiçbir rapor ya da pano çalışmaz.

**Premium kapasitede sorgu başına bellek ve süre sınırları çok daha yüksek olsa da** filtre ve dilimleyicileri kullanarak görsel öğeleri yalnızca gerekli öğelerin görüntüleneceği şekilde kısıtlamanız kesinlikle önerilir.

## <a name="next-steps"></a>Sonraki adımlar
[Power BI Premium nedir?](service-premium.md)  
[Power BI Premium sürüm notları](service-premium-release-notes.md)  
[Microsoft Power BI Premium teknik incelemesi](https://aka.ms/pbipremiumwhitepaper)  
[Planning a Power BI Enterprise Deployment (Power BI Kuruluş Dağıtımı Planlama) teknik incelemesi](https://aka.ms/pbienterprisedeploy)  
[Uzatılmış Pro Deneme Sürümünü etkinleştirme](service-extended-pro-trial.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)