---
title: Hizmet sorumlusu sınırlamaları
description: Hizmet sorumlusu sınırlamaları
services: powerbi
author: KesemSharabi
ms.author: kesharab
ms.topic: include
ms.date: 06/06/2020
ms.custom: include file
ms.openlocfilehash: 569d7dfe251183962a14de1c42d85ee2e58950af
ms.sourcegitcommit: d8acf2fb0318708a3e8e1e259cb3747b0312b312
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2020
ms.locfileid: "86401672"
---
## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

* Hizmet sorumlusu yalnızca [yeni çalışma alanlarıyla](../collaborate-share/service-create-the-new-workspaces.md) çalışır.
* Hizmet sorumlusu kullanırken **Çalışma Alanım** desteklenmez.
* Üretime geçilirken adanmış kapasite gerekir.
* Hizmet sorumlusunu kullanarak Power BI portalında oturum açamazsınız.
* Power BI yönetim portalındaki geliştirici ayarlarında hizmet sorumlusunu etkinleştirmek için Power BI yönetici hakları gereklidir.
* [Kuruluşunuz için eklenen](../developer/embedded/embed-sample-for-your-organization.md) uygulamalar hizmet sorumlusunu kullanamaz.
* [Veri akışları](../transform-model/service-dataflows-overview.md) yönetimi desteklenmez.
* Hizmet sorumlusu şu anda yönetici API'lerini desteklemiyor.
* [Azure Analysis Services](https://docs.microsoft.com/azure/analysis-services/analysis-services-overview) veri kaynağıyla hizmet sorumlusu kullanırken, hizmet sorumlusunun kendisinin Azure Analysis Services örneği izinleri olmalıdır. Bu amaçla hizmet sorumlusu içeren bir güvenlik grubu kullanmak işe yaramaz.
* Hizmet sorumlusu şu an için ağ geçidindeki veri kaynaklarına erişim sağlayamaz. Başka bir ifadeyle hizmet sorumlusunu ağ geçidindeki veri kaynağı kullanıcılarının arasına ekleyemezsiniz.
