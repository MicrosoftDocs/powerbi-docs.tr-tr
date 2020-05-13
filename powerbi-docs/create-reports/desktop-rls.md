---
title: Power BI Desktop için satır düzeyi güvenlik (RLS) ile veri erişimini kısıtlama
description: Power BI Desktop'ta, içeri aktarılan veri kümeleri ve DirectQuery için satır düzeyi güvenliği yapılandırma.
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.custom: ''
ms.date: 01/31/2020
LocalizationGroup: Create reports
ms.openlocfilehash: 89c33de2ef7319c6dcbeace0df79786128e16cd9
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83334327"
---
# <a name="restrict-data-access-with-row-level-security-rls-for-power-bi-desktop"></a>Power BI Desktop için satır düzeyi güvenlik (RLS) ile veri erişimini kısıtlama

Power BI Desktop ile satır düzeyi güvenliği (RLS), belirli kullanıcıların veri erişimini kısıtlamak için kullanabilirsiniz. Filtreler verileri satır düzeyinde kısıtlar. Rollerde filtre tanımlayabilirsiniz.

Artık Power BI Desktop ile Power BI'a aktarılan veri modelleri için RLS'yi yapılandırabilirsiniz. Ayrıca, [DirectQuery](../connect-data/desktop-use-directquery.md)'yi kullanan SQL Server gibi veri kümelerinde de RLS'yi yapılandırabilirsiniz. Önceden RLS'yi yalnızca Power BI dışındaki şirket içi Analysis Services modellerinde uygulayabiliyordunuz. Analysis Services canlı bağlantıları için Satır düzeyi güvenliği şirket içi model üzerinde yapılandırırsınız. Güvenlik seçeneği, canlı bağlantı veri kümeleri için gösterilmez.

> [!IMPORTANT]
> Power BI hizmetinde tanımladığınız roller ve kurallar varsa bu rolleri Power BI Desktop'ta yeniden oluşturmanız ve raporu hizmette yayımlamanız gerekir. [Power BI hizmetinde RLS](../admin/service-admin-rls.md) seçenekleri hakkında bilgi edinin.

[!INCLUDE [include-short-name](../includes/rls-desktop-define-roles.md)]

[!INCLUDE [include-short-name](../includes/rls-desktop-view-as-roles.md)]

[!INCLUDE [include-short-name](../includes/rls-limitations.md)]

[!INCLUDE [include-short-name](../includes/rls-faq.md)]

## <a name="next-steps"></a>Sonraki adımlar

[Power BI hizmetinde satır düzeyi güvenlik (RLS)](../admin/service-admin-rls.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/).