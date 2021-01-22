---
title: Power BI ve Azure çıkışı
description: Kiracı konumuna ve Power BI Premium aboneliğine göre Azure çıkışı ücretlerini ve Power BI'ı anlama
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: pbi-data-sources
ms.topic: how-to
ms.date: 01/19/2021
LocalizationGroup: Data from databases
ms.openlocfilehash: ec47968294e0fd905d1733bdb30ae1840069aed7
ms.sourcegitcommit: 96080432af4c8e3fe46c23274478ccffa0970efb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/20/2021
ms.locfileid: "98597470"
---
# <a name="power-bi-and-azure-egress"></a>Power BI ve Azure çıkışı

Azure veri merkezlerinden dışarı giden (çıkan) veriler için bant genişliği ücreti alınabilir. Power BI'ı Azure veri kaynaklarıyla birlikte kullanırken Power BI kiracınızın Azure veri kaynaklarınızla aynı bölgede olduğundan emin olarak Azure çıkışı ücretlerinden kaçınabilirsiniz.

Power BI kiracınız, veri kaynaklarınızı dağıttığınız Azure bölgesine dağıtıldığında zamanlanmış yenileme ve DirectQuery etkileşimleri için çıkış ücreti ödemezsiniz. 

## <a name="determining-where-your-power-bi-tenant-is-located"></a>Power BI kiracınızın bulunduğu yeri belirleme

Power BI kiracınızın bulunduğu yeri belirlemek için [Power BI kiracım nerede bulunur?](../admin/service-admin-where-is-my-tenant-located.md) makalesine bakın.

Power BI Premium Multi-Geo müşterileri için, Power BI kiracınızın Azure tabanlı veri kaynaklarınızın bazıları için en uygun konumda olmaması durumunda Power BI Premium Multi-Geo hizmetini istediğiniz Azure bölgesine dağıtarak Power BI kiracınızla Azure veri kaynaklarınızın aynı Azure bölgesinde olmasını sağlayabilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

Power BI Premium veya Multi-Geo hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

* [Azure bant genişliği fiyatlandırma ayrıntıları](https://azure.microsoft.com/pricing/details/bandwidth/)
* [Microsoft Power BI Premium nedir?](../admin/service-premium-what-is.md)
* [Power BI Premium'u satın alma](../admin/service-admin-premium-purchase.md)
* [Power BI Premium için Multi-Geo desteği (Önizleme)](../admin/service-admin-premium-multi-geo.md)
* [Power BI kiracım nerede bulunur?](../admin/service-admin-where-is-my-tenant-located.md)
* [Power BI Premium hakkında SSS](../admin/service-premium-faq.md)
