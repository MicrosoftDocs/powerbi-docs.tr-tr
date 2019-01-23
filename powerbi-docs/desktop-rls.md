---
title: Power BI Desktop ile satır düzeyi güvenliği (RLS) anlama
description: Power BI Desktop'ta, içeri aktarılan veri kümeleri ve DirectQuery için satır düzeyi güvenliği yapılandırma.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/03/2018
LocalizationGroup: Create reports
ms.openlocfilehash: a5f594f241fb4964775055a022b2f7c943dd05a1
ms.sourcegitcommit: 2c49a7cee9c77f46830ddfa59fdedbf30186d389
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54488788"
---
# <a name="row-level-security-rls-with-power-bi-desktop"></a>Power BI Desktop ile satır düzeyi güvenlik (RLS)

Power BI Desktop ile satır düzeyi güvenlik (RLS), belirli kullanıcıların veri erişimini kısıtlar. Filtreler verileri satır düzeyinde kısıtlar. Rollerde filtre tanımlayabilirsiniz.

Artık Power BI Desktop ile Power BI'a aktarılan veri modelleri için RLS'yi yapılandırabilirsiniz. Ayrıca, DirectQuery'yi kullanan SQL Server gibi veri kümelerinde de RLS'yi yapılandırabilirsiniz. Önceden RLS'yi yalnızca Power BI dışındaki şirket içi Analysis Services modellerinde uygulayabiliyordunuz. Analysis Services canlı bağlantıları için Satır düzeyi güvenliği şirket içi model üzerinde yapılandırırsınız. Güvenlik seçeneği, canlı bağlantı veri kümeleri için gösterilmez.

> [!IMPORTANT]
> Power BI hizmetinde tanımladığınız roller ve kurallar varsa bu rolleri Power BI Desktop'ta yeniden oluşturmanız ve raporu hizmette yayımlamanız gerekir.

[Power BI Hizmetinde RLS](service-admin-rls.md) seçenekleri hakkında bilgi edinin.

[!INCLUDE [include-short-name](./includes/rls-desktop-define-roles.md)]

[!INCLUDE [include-short-name](./includes/rls-desktop-view-as-roles.md)]

[!INCLUDE [include-short-name](./includes/rls-limitations.md)]

[!INCLUDE [include-short-name](./includes/rls-faq.md)]

## <a name="next-steps"></a>Sonraki adımlar

[Power BI hizmetinde satır düzeyi güvenlik (RLS)](service-admin-rls.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)