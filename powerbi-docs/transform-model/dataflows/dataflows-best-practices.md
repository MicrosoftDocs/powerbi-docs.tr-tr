---
title: Veri akışları için en iyi yöntemler
description: Veri akışlarına yönelik en iyi deneyim bağlantıları ve kılavuz koleksiyonu
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
ms.date: 11/13/2020
ms.author: davidi
LocalizationGroup: Data from files
ms.openlocfilehash: 5adfcc3d4ff7d78335f250b92b856bcd14d64c0a
ms.sourcegitcommit: bd133cb1fcbf4f6f89066165ce065b8df2b47664
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/17/2020
ms.locfileid: "94674763"
---
# <a name="dataflows-best-practices"></a>Veri akışları için en iyi yöntemler

Power BI **veri akışları** tüketim, yeniden kullanım ve tümleştirmeye hazır bir veri ekosistemini etkinleştiren, kurumsal odaklı veri hazırlık çözümüdür. Bu makalede, veri akışlarını anlamanıza ve bunlardan en iyi şekilde yararlanmanıza yardımcı olacak makalelere ve diğer bilgilere yönelik bağlantıların yanı sıra, en iyi deneyimlerin yer aldığı bir liste sağlanmaktadır.


## <a name="dataflows-best-practices-table-and-links"></a>Veri akışları için en iyi yöntemler tablosu ve bağlantıları

Aşağıdaki tabloda, veri akışlarını oluştururken veya bunlarla çalışırken uygulanabilecek en iyi deneyimleri açıklayan makalelere yönelik bağlantıların yer aldığı bir koleksiyon sağlanmaktadır. Bağlantılar iş mantığı geliştirme, karmaşık veri akışları geliştirme, veri akışlarını yeniden kullanma ve veri akışlarınızla kurumsal ölçek elde etme hakkında bilgiler içerir.


|**Konu**  |**Rehber alanı**  |**Makale veya içerik bağlantısı**  |
|---------|---------|---------|
|Power Query     | Veri hazırlama deneyiminizden en iyi şekilde yararlanmanıza yönelik ipuçları ve püf noktaları        |[Power Query en iyi deneyimleri](https://docs.microsoft.com/power-query/best-practices)        |
|Hesaplanan Varlıklardan Yararlanma     |Hesaplanan varlıkların veri akışlarında kullanılmasının performans bakımından avantajları vardır         |[İşlem Varlıkları Senaryoları](https://docs.microsoft.com/power-query/dataflows/computed-entities-scenarios)         |
|Karmaşık veri akışları geliştirme     |Büyük ölçekli, performanslı veri akışları geliştirme desenleri         |[Karmaşık veri akışları](https://docs.microsoft.com/power-query/dataflows/best-practices-developing-complex-dataflows)         |
|Veri akışlarını yeniden kullanma     |Desenler, kılavuz ve kullanım örnekleri         |[Veri akışlarını yeniden kullanma](https://docs.microsoft.com/power-query/dataflows/best-practices-reusing-dataflows)         |
|Büyük ölçekli uygulamalar     |Kurumsal mimariyi tamamlayan büyük ölçekli kullanım ve kılavuz         |[Veri akışlarının kullanıldığı veri ambarı](https://docs.microsoft.com/power-query/dataflows/best-practices-for-data-warehouse-using-dataflows)         |
|Geliştirilmiş İşlemden Yararlanma     |Veri akışı performansını 25 kata kadar artırabilir         |[Geliştirilmiş İşlem Altyapısı](dataflows-premium-workload-configuration.md#using-the-compute-engine-to-improve-performance)         |
|İş yükü ayarlarınızı iyileştirme     |Performansı artırmak amacıyla kullanabileceğiniz kaldıraçları anlayarak veri akışları altyapınızdan en iyi şekilde yararlanın         |[Veri akışları iş yükü yapılandırması](dataflows-premium-workload-configuration.md)         |
|Tabloları birleştirme ve genişletme     |Performanslı birleşimler oluşturma         |[Genişleyen tablo işlemlerini iyileştirme](https://docs.microsoft.com/power-query/optimize-expanding-table-columns)         |
|Sorguyu kaynağa döndürme kılavuzu     |Kaynak sistemi kullanarak dönüşümleri hızlandırma         |[Sorguyu kaynağa döndürme](https://docs.microsoft.com/power-query/power-query-folding)         |
|Veri profili oluşturmayı kullanma     |Sütun kalitesini, dağıtımını ve profilini anlama         |[Veri profili oluşturma araçları](https://docs.microsoft.com/power-query/data-profiling-tools)         |
|Hata işlemeyi uygulama     |Hataları yenilemeye dayanıklı, öneriler içeren güçlü veri akışları geliştirme         |[Yaygın hatalara yönelik desenler](https://docs.microsoft.com/power-query/dealing-with-errors)  </br> [Karmaşık hatası işleme](https://docs.microsoft.com/power-query/error-handling)      |
|Şema görünümünü kullanma      |Geniş bir tablo ile çalışırken ve şema düzeyinde işlemler gerçekleştirirken yazma deneyimini iyileştirme         |[Şema görünümü](https://docs.microsoft.com/power-query/schema-view)         |
|||


        
## <a name="next-steps"></a>Sonraki adımlar

Aşağıdaki makaleler veri akışları ve Power BI hakkında daha fazla bilgi sunmaktadır:

* [Veri akışlarına giriş ve self servis veri hazırlığı](dataflows-introduction-self-service.md)
* [Veri akışı oluşturma](dataflows-create.md)
* [Veri akışı yapılandırma ve kullanma](dataflows-configure-consume.md)
* [Veri akışlarının Premium özellikleri](dataflows-premium-features.md)
* [Veri akışı depolama alanını Azure Data Lake 2. Nesil kullanacak şekilde yapılandırma](dataflows-azure-data-lake-storage-integration.md)
* [Veri akışları ve yapay zeka](dataflows-machine-learning-integration.md)
* [Veri akışı sınırlamaları ve önemli noktalar](dataflows-features-limitations.md)