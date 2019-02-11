---
title: Yönetim portalını kullanarak Power BI Premium kapasitelerini izleme
description: Premium kapasitelerinizi izlemek için Power BI yönetim portalını kullanın.
author: minewiskan
ms.author: owend
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 02/05/2019
LocalizationGroup: Premium
ms.openlocfilehash: 59097c07719e4bb8db188e8a86db377076aea7a9
ms.sourcegitcommit: 54d44deb6e03e518ad6378656c769b06f2a0b6dc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/07/2019
ms.locfileid: "55794114"
---
# <a name="monitor-capacities-in-the-admin-portal"></a>Yönetim portalında kapasiteleri izleme

Bu makalede Yönetim portalındaki Kapasite ayarları alanını kullanarak kapasitenizin performansına nasıl hızlı bir bakış atabileceğiniz açıklanır.  Kapasitenizle ilgili en ayrıntılı ölçümleri elde etmek için en iyi yöntem [Power BI Premium Kapasite Ölçümleri](service-admin-premium-monitor-capacity.md) uygulamasını kullanmaktır.

## <a name="capacity-metrics"></a>Kapasite ölçümleri

Yönetici portalının **Kapasite ayarları** bölümünde kapasitenize tarafından kullanılan kaynakların son yedi gün içindeki yükünü gösteren dört gösterge bulunur. Bu dört kutucuk saat ortalamasını baz alır ve son yedi günde ilgili ölçümün %80'in üzerinde olduğu saat sayısını gösterir. Bu ölçüm, son kullanıcı deneyimindeki olası düşüşleri ifade eder.

![Son 7 gün içindeki kullanım](media/service-admin-premium-monitor-capacity/usage-in-days.png)

| **Ölçüm** | **Açıklama** |
| --- | --- |
| CPU |CPU’nun %80 kullanımı aşma sayısı. |
| Bellek Temizleme |Arka uç çekirdeklerinizdeki bellek baskısını gösterir. Bu, özellikle birden çok veri kümesinin kullanılmasından kaynaklanan bellek baskısı nedeniyle veri kümelerinin bellekten ne sıklıkta çıkarıldığına ilişkin bir ölçümdür. |
| Memory Usage |Gigabayt (GB) olarak temsil edilen ortalama bellek kullanımı. |
| DQ/s | Direct Query ve Canlı Bağlantı sayısının, sınırın %80’ini aşma sayısı. <br>  Saniye başına toplam DirectQuery ve canlı bağlantı sorgusu sayısı sınırlıdır. Sınırlar şu şekildedir: P1 için 30/s, P2 için 60/s ve P3 için 120/s.  Direct Query ve canlı bağlantı sorguları sayısı yukarıdaki kısıtlamaya yönelik olarak birlikte hesaplanır. Örneğin, saniyede 15 DirectQuery bağlantısı ve 15 canlı bağlantıya sahipseniz kısıtlama noktanıza varmış olursunuz<br> Bu, hem şirket içi hem de bulut bağlantıları için aynı ölçüde geçerlidir. |
|  |  |

Ölçümler, geçen hafta içindeki kullanımı yansıtır.  Ölçümlerin daha ayrıntılı bir görünümünü görmek istiyorsanız, özet kutucuklarının herhangi birine tıklayarak bunu yapabilirsiniz.  Böylece, premium kapasitenize yönelik her bir ölçüm için ayrıntılı grafiklere gidersiniz. Aşağıdaki grafikte CPU ölçümünün ayrıntıları gösterilmektedir.

![CPU için ayrıntılı kullanım grafiği](media/service-admin-premium-monitor-capacity/premium-usage-detailed-chart-cpu.png)

Bu grafikler, geçen hafta için saatlik olarak özetlenir ve premium kapasitenizde performansla ilgili belirli olaylar olduğunda sorunu ayrıştırmanıza yardımcı olabilir.

Herhangi bir ölçüme yönelik temel verileri bir csv dosyasına da dışarı aktarabilirsiniz.  Bu dışarı aktarma, geçen haftanın her günü için üçer dakikalık aralıklarla size ayrıntılı bilgi sunar.

## <a name="next-steps"></a>Sonraki adımlar

Power BI Premium kapasitelerini izlemeyi anladığınıza göre kapasiteleri iyileştirme konusunda daha fazla bilgi edinebilirsiniz.

> [!div class="nextstepaction"]
> [Power BI Premium kapasite kaynak yönetimi ve en iyi duruma getirme](service-premium-understand-how-it-works.md)
