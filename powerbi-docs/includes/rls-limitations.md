---
author: davidiseminger
ms.service: powerbi
ms.topic: include
ms.date: 01/31/2020
ms.author: davidi
ms.openlocfilehash: b67025de5e2a70876a31fd42e22c9572403288fa
ms.sourcegitcommit: cde65bb8b1bed1ee8cf512651afeb829ddc155de
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77464419"
---
## <a name="limitations"></a>Sınırlamalar

Bulut modellerindeki satır düzeyi güvenlik hakkındaki geçerli sınırlamalar şunlardır:

* Power BI hizmetinde tanımlanmış olduğunuz roller ve kurallar varsa bunları Power BI Desktop'ta tekrar oluşturmanız gerekir.

* RLS özelliğini yalnızca Power BI Desktop ile oluşturulan veri kümelerinde tanımlayabilirsiniz. RLS özelliğini Excel ile oluşturulmuş olan veri kümeleri için etkinleştirmek isterseniz öncelikle dosyalarınızı Power BI Desktop (PBIX) biçimine dönüştürmeniz gerekir. [Daha fazla bilgi edinin](../desktop-import-excel-workbooks.md).

* Yalnızca İçeri Aktarma ve DirectQuery bağlantıları desteklenir. Analysis Services canlı bağlantıları şirket içi modelde işlenir.

## <a name="known-issues"></a>Bilinen sorunlar

Bilinen sorunların biri, önceden yayımlanmış olan bir raporu Power BI Desktop uygulamasından yayımlamaya çalıştığınızda ortaya çıkan hata iletisidir. Senaryo aşağıdaki gibidir:

1. Anna, Power BI hizmetinde yayımlanmış ve RLS yapılandırması yapılmış bir veri kümesine sahiptir.

1. Anna raporu Power BI Desktop uygulamasında güncelleştirip tekrar yayımlar.

1. Anna bir hata alır.

**Geçici çözüm:** Bu sorun giderilene kadar Power BI Desktop dosyasını Power BI hizmetinden yayımlayın. Bu işlemi, **Veri Al** > **Dosyalar** adımlarını izleyerek yapabilirsiniz.
