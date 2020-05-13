---
author: davidiseminger
ms.service: powerbi
ms.topic: include
ms.date: 01/31/2020
ms.author: davidi
ms.openlocfilehash: 912b0213c328c623e7881f7f30fe7d67f6d889b3
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83274661"
---
## <a name="limitations"></a>Sınırlamalar

Bulut modellerindeki satır düzeyi güvenlik hakkındaki geçerli sınırlamalar şunlardır:

* Power BI hizmetinde tanımlanmış olduğunuz roller ve kurallar varsa bunları Power BI Desktop'ta tekrar oluşturmanız gerekir.

* RLS özelliğini yalnızca Power BI Desktop ile oluşturulan veri kümelerinde tanımlayabilirsiniz. RLS özelliğini Excel ile oluşturulmuş olan veri kümeleri için etkinleştirmek isterseniz öncelikle dosyalarınızı Power BI Desktop (PBIX) biçimine dönüştürmeniz gerekir. [Daha fazla bilgi](../connect-data/desktop-import-excel-workbooks.md).

* Yalnızca İçeri Aktarma ve DirectQuery bağlantıları desteklenir. Analysis Services canlı bağlantıları şirket içi modelde işlenir.

## <a name="known-issues"></a>Bilinen sorunlar

Bilinen sorunların biri, önceden yayımlanmış olan bir raporu Power BI Desktop uygulamasından yayımlamaya çalıştığınızda ortaya çıkan hata iletisidir. Senaryo aşağıdaki gibidir:

1. Anna, Power BI hizmetinde yayımlanmış ve RLS yapılandırması yapılmış bir veri kümesine sahiptir.

1. Anna raporu Power BI Desktop uygulamasında güncelleştirip tekrar yayımlar.

1. Anna bir hata alır.

**Geçici çözüm:** Bu sorun giderilene kadar Power BI Desktop dosyasını Power BI hizmetinden yayımlayın. Bu işlemi, **Veri Al** > **Dosyalar** adımlarını izleyerek yapabilirsiniz.

