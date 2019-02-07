---
title: Büyük veri kümelerine yönelik Power BI Premium desteği
description: Power BI Premium artık 10 GB’a kadar olan veri kümelerini destekler.
author: jocaplan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 10/18/2018
ms.author: jocaplan
LocalizationGroup: Premium
ms.openlocfilehash: 941d4bc3d66ce8e636f730d5757b7215c978d582
ms.sourcegitcommit: 54d44deb6e03e518ad6378656c769b06f2a0b6dc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55794828"
---
# <a name="power-bi-premium-support-for-large-datasets"></a>Büyük veri kümelerine yönelik Power BI Premium desteği

Power BI Premium, boyutu 10 GB’a kadar olan Power BI Desktop (.pbix) dosyalarının karşıya yüklenmesini destekler. Bir veri kümesi karşıya yüklendiğinde, boyutu 12 GB’a kadar çıkacak şekilde yenilenebilir. Büyük bir veri kümesini kullanmak için Premium kapasiteye atanmış bir çalışma alanında yayımlayın.
 
## <a name="best-practices"></a>En iyi yöntemler

Bu bölümde, büyük veri kümeleriyle çalışmaya yönelik en iyi yöntemler açıklanmıştır.

**Büyük modeller çok fazla veri kullanarak** kapasitenizi etkileyebilir. 1 GB üzerindeki modeller için en az P1 SKU kullanmanızı öneririz. Büyük modelleri A3 düzeyine kadar olan A SKU'larını kullanan çalışma alanlarında yayımlama işlemi başarılı sonuç verse de bu modelleri yenileme işlemi yapılamaz.

Aşağıdaki tabloda çeşitli .pbix boyutları için önerilen SKU'lar açıklanmıştır:

   |SKU  |.pbix dosyasının boyutu   |
   |---------|---------|
   |P1    | 3 GB’tan küçük        |
   |P2    | 6 GB’tan küçük        |
   |P3, P4, P5    | 10 GB'a kadar   |

Power BI Embedded A4 SKU’su P1 SKU, A5 = P2 ve A6 = P3’e eşittir. A ve EM SKU'larında büyük modellerin yayımlanması durumunda, paylaşılan kapasitedeki model boyutu sınırlamasına özgü olmayan hatalar döndürülebilir. A ve EM SKU'larında büyük modellerin yenilenmesi muhtemelen zaman aşımı hatalarına neden olacaktır. Bu senaryolardaki hata iletilerini geliştirmek için çalışıyoruz.

**.pbix dosyalarınız, verileri yüksek oranda sıkıştırılmış bir şekilde temsil eder**. Muhtemelen veriler belleğe yüklenirken birkaç kez genişletilir ve veri yenileme sırasında birkaç kez daha genişletilebilir.

**Büyük veri kümeleri için zamanlanmış yenileme çok uzun sürebilir** ve çok kaynak tüketimi gerektirebilir. Bunu göz önünde bulundurarak çok fazla örtüşen yenileme zamanlamayın. Bu kapasitedeki tüm veri kümeleri için zamanlanmış yenileme işlerinin zaman aşımının da iki kadına çıkarak dört saat olduğuna dikkat edin. Daha hızlı ve daha güvenilir olmasının yanı sıra daha az kaynak tükettiği için [artımlı yenilemeyi](service-premium-incremental-refresh.md) kullanmanızı öneririz.

Veritabanı en son uzun bir süre önce kullanılmışsa, model Premium kapasitenizin belleğine yüklendiği için **büyük veri kümelerinin ilk raporunun yüklenmesi uzun zaman alabilir**. Yüklenmesi nispeten uzun süren raporların ilerleme durumunu göstermek için bir yükleme çubuğu görüntülenir.

**Çalışma alanını Premium kapasiteden kaldırırsanız** model ve modelle ilişkili hiçbir rapor ya da pano çalışmaz.

**Premium kapasitede sorgu başına bellek ve süre sınırları çok daha yüksek olsa da** filtre ve dilimleyicileri kullanarak görsel öğeleri yalnızca gerekli öğelerin görüntüleneceği şekilde kısıtlamanız kesinlikle önerilir.

**Sonraki adımlar**

[Power BI Premium nedir?](service-premium.md)
[Power BI Premium sürüm notları](service-premium-release-notes.md)
[Microsoft Power BI Premium teknik incelemesi](https://aka.ms/pbipremiumwhitepaper)
[Planning a Power BI Enterprise Deployment (Power BI Kuruluş Dağıtımı Planlama) teknik incelemesi](https://aka.ms/pbienterprisedeploy)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
