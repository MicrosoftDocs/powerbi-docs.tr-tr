---
title: Power BI Desktop’ta gelişmiş veri kümesi meta verilerini kullanma
description: Bu makalede, Power BI’da gelişmiş veri kümesi meta verilerinin nasıl kullanılacağı açıklanmaktadır.
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 09/22/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: 67141f67be85f5c292118d4e88cfe3c5a949ce4f
ms.sourcegitcommit: ff981839e805f523748b7e71474acccf7bdcb04f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/22/2020
ms.locfileid: "91019872"
---
# <a name="using-enhanced-dataset-metadata"></a>Gelişmiş veri kümesi meta verilerini kullanma

Power BI Desktop, rapor oluşturduğunda, ilgili PBIX ve PBIT dosyalarında da veri kümesi meta verileri oluşturur. Önceden meta veriler Power BI Desktop’a özgü bir biçimde depolanıyordu. Base-64 kodlu M ifadeleri ve veri kaynaklar kullanılıyordu ve meta verilerin nasıl depolanacağına dair varsayımlarda bulunuluyordu.

**Gelişmiş veri kümesi meta verileri** özelliğinin yayınlanmasıyla birlikte, bu sınırlamaların çoğu kaldırıldı. PBIX dosyaları, dosyanın açılmasıyla birlikte otomatik olarak gelişmiş meta verilere yükseltilir. **Gelişmiş veri kümesi meta verileri** sayesinde, Power BI Desktop tarafından oluşturulan meta veriler, [Tablosal Nesne Modeli](/analysis-services/tom/introduction-to-the-tabular-object-model-tom-in-analysis-services-amo)’ni temel alarak, Analysis Services tablosal modelleri için kullanılanlara benzer bir biçimi kullanır.


**Gelişmiş veri kümesi meta verileri** özelliği stratejik ve temel niteliktedir; gelecekteki Power BI işlevleri bunun meta verileri temelinde oluşturulur. Gelişmiş veri kümesi meta verilerinden yararlanan bazı ek özellikler arasında, Power BI veri kümelerinin yönetimi için [XMLA okuma/yazma](/power-platform-release-plan/2019wave2/business-intelligence/xmla-readwrite) ve yeni nesil özelliklerden yararlanmak için Analysis Services iş yüklerinden Power BI’a geçiş yer alır.


## <a name="next-steps"></a>Sonraki adımlar

Power BI Desktop ile her şeyi yapabilirsiniz. Özellikler hakkında daha fazla bilgi edinmek için aşağıdaki kaynaklara bakın:

* [Power BI Desktop nedir?](../fundamentals/desktop-what-is-desktop.md)
* [Power BI Desktop’taki Yenilikler](../fundamentals/desktop-latest-update.md)
* [Power BI Desktop ile sorgulara genel bakış](../transform-model/desktop-query-overview.md)
* [Power BI Desktop'taki veri türleri](desktop-data-types.md)
* [Power BI Desktop'ta verileri şekillendirme ve birleştirme](desktop-shape-and-combine-data.md)
* [Power BI Desktop'taki genel sorgu görevleri](../transform-model/desktop-common-query-tasks.md)