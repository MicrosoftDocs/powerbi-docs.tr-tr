---
title: "Power BI Desktop ile satır düzeyi güvenliği (RLS) anlama"
description: "Power BI Desktop'ta, içeri aktarılan veri kümeleri ve DirectQuery için satır düzeyi güvenliği yapılandırma."
services: powerbi
documentationcenter: 
author: guyinacube
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: powerbi
ms.date: 10/12/2017
ms.author: asaxton
ms.openlocfilehash: e6b6efb976de8df6064f2eb1156237d1a1250807
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2017
---
# <a name="row-level-security-rls-with-power-bi-desktop"></a>Power BI Desktop ile satır düzeyi güvenlik (RLS)
Power BI Desktop ile satır düzeyi güvenlik (RLS), belirli kullanıcıların veri erişimini kısıtlamak için kullanılabilir. Filtreler verileri satır düzeyinde kısıtlar. Rollerde filtre tanımlayabilirsiniz.

Artık Power BI Desktop ile Power BI'a aktarılan veri modelleri için RLS'yi yapılandırabilirsiniz. Ayrıca, DirectQuery'yi kullanan SQL Server gibi veri kümelerinde de RLS'yi yapılandırabilirsiniz. Önceden RLS'yi yalnızca Power BI dışındaki şirket içi Analysis Services modellerinde uygulayabiliyordunuz. Analysis Services canlı bağlantıları için Satır düzeyi güvenliği şirket içi model üzerinde yapılandırırsınız. Güvenlik seçeneği, canlı bağlantı veri kümeleri için gösterilmez.

> [!IMPORTANT]
> Power BI hizmetinde tanımladığınız roller/kurallar varsa bu rolleri Power BI Desktop'ta yeniden oluşturmanız ve raporu hizmette yayımlamanız gerekir.
> 
> 

[Power BI Hizmetinde RLS](service-admin-rls.md) seçenekleri hakkında bilgi edinin.

[!INCLUDE [include-short-name](./includes/rls-desktop-define-roles.md)]

[!INCLUDE [include-short-name](./includes/rls-desktop-view-as-roles.md)]

[!INCLUDE [include-short-name](./includes/rls-limitations.md)]

[!INCLUDE [include-short-name](./includes/rls-faq.md)]

## <a name="next-steps"></a>Sonraki adımlar
[Power BI hizmetinde satır düzeyi güvenlik (RLS)](service-admin-rls.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

