---
title: Hizmet sorumlusu sınırlamaları
description: Hizmet sorumlusu sınırlamaları
services: powerbi
author: KesemSharabi
ms.author: kesharab
ms.topic: include
ms.date: 06/06/2020
ms.custom: include file
ms.openlocfilehash: f55cf56edbc26d58dcfb5d67f46a908625ebcf30
ms.sourcegitcommit: 37bd34053557089c4fbf0e05f78e959609966561
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94425215"
---
## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

* Hizmet sorumlusu yalnızca [yeni çalışma alanlarıyla](../collaborate-share/service-create-the-new-workspaces.md) çalışır.
* Hizmet sorumlusu kullanırken **Çalışma Alanım** desteklenmez.
* Üretime geçilirken bir kapasite gerekir.
* Hizmet sorumlusunu kullanarak Power BI portalında oturum açamazsınız.
* Power BI yönetim portalındaki geliştirici ayarlarında hizmet sorumlusunu etkinleştirmek için Power BI yönetici hakları gereklidir.
* [Kuruluşunuz için eklenen](../developer/embedded/embed-sample-for-your-organization.md) uygulamalar hizmet sorumlusunu kullanamaz.
* [Veri akışları](../transform-model/dataflows/dataflows-introduction-self-service.md) yönetimi desteklenmez.
* Hizmet sorumlusu şu anda yönetici API'lerini desteklemiyor.
* [Azure Analysis Services](/azure/analysis-services/analysis-services-overview) veri kaynağıyla hizmet sorumlusu kullanırken, hizmet sorumlusunun kendisinin Azure Analysis Services örneği izinleri olmalıdır. Bu amaçla hizmet sorumlusu içeren bir güvenlik grubu kullanmak işe yaramaz.