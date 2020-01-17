---
title: Power BI Desktop ile satır düzeyi güvenliği (RLS) anlama
description: Power BI Desktop'ta, içeri aktarılan veri kümeleri ve DirectQuery için satır düzeyi güvenliği yapılandırma.
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.custom: ''
ms.date: 12/05/2019
LocalizationGroup: Create reports
ms.openlocfilehash: dc2c1e312592048c90643526a898ebe654907a68
ms.sourcegitcommit: 97597ff7d9ac2c08c364ecf0c729eab5d59850ce
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/09/2020
ms.locfileid: "75760670"
---
# <a name="restrict-data-access-with-row-level-security-rls-for-power-bi-desktop"></a>Power BI Desktop için satır düzeyi güvenlik (RLS) ile veri erişimini kısıtlama

Power BI Desktop ile satır düzeyi güvenliği (RLS), belirli kullanıcıların veri erişimini kısıtlamak için kullanabilirsiniz. Filtreler verileri satır düzeyinde kısıtlar. Rollerde filtre tanımlayabilirsiniz.

Artık Power BI Desktop ile Power BI'a aktarılan veri modelleri için RLS'yi yapılandırabilirsiniz. Ayrıca, [DirectQuery](desktop-use-directquery.md)'yi kullanan SQL Server gibi veri kümelerinde de RLS'yi yapılandırabilirsiniz. Önceden RLS'yi yalnızca Power BI dışındaki şirket içi Analysis Services modellerinde uygulayabiliyordunuz. Analysis Services canlı bağlantıları için Satır düzeyi güvenliği şirket içi model üzerinde yapılandırırsınız. Güvenlik seçeneği, canlı bağlantı veri kümeleri için gösterilmez.

> [!IMPORTANT]
> Power BI hizmetinde tanımladığınız roller ve kurallar varsa bu rolleri Power BI Desktop'ta yeniden oluşturmanız ve raporu hizmette yayımlamanız gerekir.

[Power BI Hizmetinde RLS](service-admin-rls.md) seçenekleri hakkında bilgi edinin.

[!INCLUDE [include-short-name](./includes/rls-desktop-define-roles.md)]

[!INCLUDE [include-short-name](./includes/rls-desktop-view-as-roles.md)]

[!INCLUDE [include-short-name](./includes/rls-limitations.md)]

[!INCLUDE [include-short-name](./includes/rls-faq.md)]

## <a name="next-steps"></a>Sonraki adımlar

[Power BI hizmetinde satır düzeyi güvenlik (RLS)](service-admin-rls.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)