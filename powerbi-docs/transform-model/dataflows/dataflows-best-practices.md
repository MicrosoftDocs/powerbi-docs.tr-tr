---
title: Veri akışları için en iyi yöntemler
description: Veri akışlarına yönelik en iyi deneyim bağlantıları ve kılavuz koleksiyonu
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: pbi-dataflows
ms.topic: how-to
ms.date: 12/10/2020
LocalizationGroup: Data from files
ms.openlocfilehash: fb688b20fd8b5ee1288f670fba9f7f45fc058680
ms.sourcegitcommit: 1cad78595cca1175b82c04458803764ac36e5e37
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/19/2021
ms.locfileid: "98565359"
---
# <a name="dataflows-best-practices"></a>Veri akışları için en iyi yöntemler

Power BI **veri akışları** tüketim, yeniden kullanım ve tümleştirmeye hazır bir veri ekosistemini etkinleştiren, kurumsal odaklı veri hazırlık çözümüdür. Bu makalede, veri akışlarını anlamanıza ve bunlardan en iyi şekilde yararlanmanıza yardımcı olacak makalelere ve diğer bilgilere yönelik bağlantıların yanı sıra, en iyi deneyimlerin yer aldığı bir liste sağlanmaktadır.

## <a name="dataflows-across-the-power-platform"></a>Power Platform genelinde veri akışları

Veri akışları Power Query, Microsoft Dynamics 365 ve diğer Microsoft teklifleri gibi çeşitli Power Platform teknolojilerinde kullanılabilir. Veri akışlarının Power Platform genelinde nasıl çalışabileceği hakkında daha fazla bilgi için bkz. [Microsoft ürünlerinde veri akışlarını kullanma](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365).


## <a name="dataflows-best-practices-table-and-links"></a>Veri akışları için en iyi yöntemler tablosu ve bağlantıları

Aşağıdaki tabloda, veri akışlarını oluştururken veya bunlarla çalışırken uygulanabilecek en iyi deneyimleri açıklayan makalelere yönelik bağlantıların yer aldığı bir koleksiyon sağlanmaktadır. Bağlantılar iş mantığı geliştirme, karmaşık veri akışları geliştirme, veri akışlarını yeniden kullanma ve veri akışlarınızla kurumsal ölçek elde etme hakkında bilgiler içerir.


|**Konu**  |**Rehber alanı**  |**Makale veya içerik bağlantısı**  |
|---------|---------|---------|
|Power Query     | Veri hazırlama deneyiminizden en iyi şekilde yararlanmanıza yönelik ipuçları ve püf noktaları        |[Power Query en iyi deneyimleri](/power-query/best-practices)        |
|Hesaplanan Varlıklardan Yararlanma     |Hesaplanan varlıkların veri akışlarında kullanılmasının performans bakımından avantajları vardır         |[Hesaplanan Varlıklar Senaryoları](/power-query/dataflows/computed-entities-scenarios)         |
|Karmaşık veri akışları geliştirme     |Büyük ölçekli, performanslı veri akışları geliştirme desenleri         |[Karmaşık veri akışları](/power-query/dataflows/best-practices-developing-complex-dataflows)         |
|Veri akışlarını yeniden kullanma     |Desenler, kılavuz ve kullanım örnekleri         |[Veri akışlarını yeniden kullanma](/power-query/dataflows/best-practices-reusing-dataflows)         |
|Büyük ölçekli uygulamalar     |Kurumsal mimariyi tamamlayan büyük ölçekli kullanım ve kılavuz         |[Veri akışlarının kullanıldığı veri ambarı](/power-query/dataflows/best-practices-for-data-warehouse-using-dataflows)         |
|Geliştirilmiş İşlemden Yararlanma     |Veri akışı performansını 25 kata kadar artırabilir         |[Geliştirilmiş İşlem Altyapısı](dataflows-premium-workload-configuration.md#using-the-compute-engine-to-improve-performance)         |
|İş yükü ayarlarınızı iyileştirme     |Performansı artırmak amacıyla kullanabileceğiniz kaldıraçları anlayarak veri akışları altyapınızdan en iyi şekilde yararlanın         |[Veri akışları iş yükü yapılandırması](dataflows-premium-workload-configuration.md)         |
|Tabloları birleştirme ve genişletme     |Performanslı birleşimler oluşturma         |[Genişleyen tablo işlemlerini iyileştirme](/power-query/optimize-expanding-table-columns)         |
|Sorguyu kaynağa döndürme kılavuzu     |Kaynak sistemi kullanarak dönüşümleri hızlandırma         |[Sorguyu kaynağa döndürme](/power-query/power-query-folding)         |
|Veri profili oluşturmayı kullanma     |Sütun kalitesini, dağıtımını ve profilini anlama         |[Veri profili oluşturma araçları](/power-query/data-profiling-tools)         |
|Hata işlemeyi uygulama     |Hataları yenilemeye dayanıklı, öneriler içeren güçlü veri akışları geliştirme         |[Yaygın hatalara yönelik desenler](/power-query/dealing-with-errors)  </br> [Karmaşık hatası işleme](/power-query/error-handling)      |
|Şema görünümünü kullanma      |Geniş bir tablo ile çalışırken ve şema düzeyinde işlemler gerçekleştirirken yazma deneyimini iyileştirme         |[Şema görünümü](/power-query/schema-view)         |
|Bağlantılı varlıklar      |Dönüşümleri yeniden kullanma ve bunlara başvurma         |[Bağlantılı varlıklar](/power-query/dataflows/linked-entities)         |
|Artımlı yenileme      |Tam yeniden yükleme yerine en son veya değiştirilmiş verileri yükleme         |[Artımlı yenileme](/power-query/dataflows/incremental-refresh)         |
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