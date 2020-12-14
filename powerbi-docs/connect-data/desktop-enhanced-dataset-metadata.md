---
title: Power BI Desktop’ta gelişmiş veri kümesi meta verilerini kullanma
description: Bu makalede, Power BI’da gelişmiş veri kümesi meta verilerinin nasıl kullanılacağı açıklanmaktadır.
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: pbi-data-sources
ms.topic: conceptual
ms.date: 12/08/2020
LocalizationGroup: Connect to data
ms.openlocfilehash: 661e50617094d396e8beb887ac0e4a27c28c2ca7
ms.sourcegitcommit: 30d0668434283c633bda9ae03bc2aca75401ab94
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/09/2020
ms.locfileid: "96906982"
---
# <a name="using-enhanced-dataset-metadata"></a>Gelişmiş veri kümesi meta verilerini kullanma

Power BI Desktop, rapor oluşturduğunda, ilgili PBIX ve PBIT dosyalarında da veri kümesi meta verileri oluşturur. Önceden meta veriler Power BI Desktop’a özgü bir biçimde depolanıyordu. Meta veriler için Base 64 kodlamalı M ifadeleri ve veri kaynakları kullanılıyordu. Power BI, bu meta verilerin depolanma şekline dair varsayımlarda bulunuyordu.

**Gelişmiş veri kümesi meta verileri** özelliğinin yayınlanmasıyla birlikte, bu sınırlamaların çoğu kaldırıldı. PBIX dosyaları, dosyanın açılmasıyla birlikte otomatik olarak gelişmiş meta verilere yükseltilir. **Gelişmiş veri kümesi meta verileri** sayesinde, Power BI Desktop tarafından oluşturulan meta veriler, [Tablosal Nesne Modeli](/analysis-services/tom/introduction-to-the-tabular-object-model-tom-in-analysis-services-amo)’ni temel alarak, Analysis Services tablosal modelleri için kullanılanlara benzer bir biçimi kullanır.


**Gelişmiş veri kümesi meta verileri** özelliği stratejik ve temel niteliktedir. Gelecekteki Power BI işlevleri bunun meta verileri temelinde oluşturulur. Gelişmiş veri kümesi meta verilerinden yararlanan bazı ek özellikler de vardır:

- Power BI veri kümelerinin yönetimi için [XMLA okuma/yazma](/power-platform-release-plan/2019wave2/business-intelligence/xmla-readwrite)
- Yeni nesil özelliklerden yararlanmak için Analysis Services iş yüklerinden Power BI’a geçiş.

## <a name="limitations"></a>Sınırlamalar
Gelişmiş meta veri desteğinden önce Power BI Desktop; SQL Server, Oracle, Teradata ve eski HANA bağlantıları için veri modeline yerel bir sorgu eklenmişti. Bu sorgu, Power BI hizmeti veri modelleri tarafından kullanılıyordu. Gelişmiş meta veri desteği sayesinde Power BI hizmeti veri modeli, yerel sorguyu çalışma zamanında yeniden oluşturur. Power BI Desktop tarafından oluşturulan sorguyu kullanmaz. Bu alma süreci çoğu durumda doğru şekilde çözümlenir ancak bazı dönüşümlerin çalışması için temel alınan verilerin okunması gerekir. Daha önce çalışan raporlarda bazı hatalar görebilirsiniz. Örneğin şuna benzer hatalarla karşılaşabilirsiniz: 

"Dimension City tablosundaki M sorgusu yerel kaynak sorgusuna dönüştürülemiyor. Daha sonra tekrar deneyin veya desteğe başvurun. Desteğe başvurursanız bu ayrıntıları sağlayın." 

Sorgularınızı Power BI Desktop'ta üç farklı noktadan düzeltebilirsiniz:

- Değişiklikleri uyguladığınızda veya yenileme yaptığınızda.
- Power Query Düzenleyicisi'nin ifadenin veri kaynağına katlanamadığını belirttiği uyarı çubuğunda.
    :::image type="content" source="media/desktop-enhanced-dataset-metadata/enhanced-metadata-apply-query-changes.png" alt-text="Sorgu değişikliklerini uygula iletisinin ekran görüntüsü: İfadeyi veri kaynağına katlayamadık.":::
- Raporu açtıktan sonra desteklenmeyen sorgular olup olmadığını denetleme amacıyla değerlendirme çalıştırdığınızda. Bu değerlendirmelerin çalıştırılması performansı etkileyebilir.


## <a name="next-steps"></a>Sonraki adımlar

Power BI Desktop ile her şeyi yapabilirsiniz. Özellikler hakkında daha fazla bilgi edinmek için aşağıdaki kaynaklara bakın:

* [Power BI Desktop nedir?](../fundamentals/desktop-what-is-desktop.md)
* [Power BI Desktop’taki Yenilikler](../fundamentals/desktop-latest-update.md)
* [Power BI Desktop ile sorgulara genel bakış](../transform-model/desktop-query-overview.md)
* [Power BI Desktop'taki veri türleri](desktop-data-types.md)
* [Power BI Desktop'ta verileri şekillendirme ve birleştirme](desktop-shape-and-combine-data.md)
* [Power BI Desktop'taki genel sorgu görevleri](../transform-model/desktop-common-query-tasks.md)
