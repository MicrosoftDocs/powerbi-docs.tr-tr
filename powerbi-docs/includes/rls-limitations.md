---
author: davidiseminger
ms.service: powerbi
ms.topic: include
ms.date: 09/13/2019
ms.author: davidi
ms.openlocfilehash: 6d1a239954a64da1c92cc68b56912e6f4ab67228
ms.sourcegitcommit: 9a265d8117cc202f5f700286b5ff42a631aacdb4
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/06/2019
ms.locfileid: "74882777"
---
## <a name="limitations"></a>Sınırlamalar

Bulut modellerindeki satır düzeyi güvenlik hakkındaki geçerli sınırlamalar burada liste halinde verilmiştir.

* Power BI hizmetinde tanımlanmış olduğunuz roller ve kurallar varsa bunları Power BI Desktop'ta tekrar oluşturmanız gerekir.

* RLS özelliğini yalnızca Power BI Desktop ile oluşturulan veri kümelerinde tanımlayabilirsiniz. RLS özelliğini Excel ile oluşturulmuş olan veri kümeleri için etkinleştirmek isterseniz öncelikle dosyalarınızı Power BI Desktop (PBIX) biçimine dönüştürmeniz gerekir. [Daha fazla bilgi](../desktop-import-excel-workbooks.md)

* Yalnızca İçeri Aktarma ve DirectQuery bağlantıları desteklenir. Analysis Services canlı bağlantıları şirket içi modelde işlenir.

## <a name="known-issues"></a>Bilinen sorunlar

Bilinen sorunların biri, önceden yayımlanmış olan bir raporu Power BI Desktop uygulamasından yayımlamaya çalıştığınızda ortaya çıkan hata iletisidir. Senaryo aşağıdaki gibidir.

1. Anna, Power BI hizmetinde yayımlanmış ve RLS yapılandırması yapılmış bir veri kümesine sahiptir.

1. Anna raporu Power BI Desktop uygulamasında güncelleştirip tekrar yayımlar.

1. Anna bir hata alır.

**Geçici çözüm:** Bu sorun giderilene kadar Power BI Desktop dosyasını Power BI hizmetinden yayımlayın. Bu işlemi, **Veri Al** > **Dosyalar** adımlarını izleyerek yapabilirsiniz.
