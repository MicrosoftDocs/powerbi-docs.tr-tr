---
title: Şirket içi veri ağ geçidi
description: Bu makale, Power BI için şirket içi veri ağ geçidine bir genel bakıştır. DirectQuery veri kaynaklarıyla çalışmak için bu ağ geçidini kullanabilirsiniz. Bulut veri kümelerini şirket içi verilerle yenilemek için de bu ağ geçidini kullanabilirsiniz.
author: mgblythe
ms.author: mblythe
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
LocalizationGroup: Gateways
ms.date: 07/15/2019
ms.openlocfilehash: b01a3ef5832541822aa9311df14289285f601b2b
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73872452"
---
# <a name="what-is-an-on-premises-data-gateway"></a>Şirket içi veri ağ geçidi nedir?

[!INCLUDE [gateway-rewrite](includes/gateway-rewrite.md)]

Şirket içi veri ağ geçidi bir köprü işlevi görerek şirket içi veriler (bulutta olmayan veriler) ile çeşitli Microsoft bulut hizmetleri arasında hızlı ve güvenli veri aktarımı sağlar. Bu bulut hizmetleri Power BI, PowerApps, Microsoft Flow, Azure Analysis Services ve Azure Logic Apps'tir. Bir ağ geçidi kullanarak, kuruluşlar veritabanlarını ve diğer veri kaynaklarını şirket içi ağlarında tutabilir ve diğer yandan da bu şirket içi verileri bulut hizmetlerinde güvenli bir şekilde kullanabilir.

## <a name="how-the-gateway-works"></a>Ağ geçidi nasıl çalışır?

![Ağ geçidine genel bakış](media/service-gateway-onprem/on-premises-data-gateway.png)

Ağ geçidinin nasıl çalıştığı hakkında daha fazla bilgi için bkz. [Şirket içi veri ağ geçidi mimarisi](/data-integration/gateway/service-gateway-onprem-indepth).

## <a name="types-of-gateways"></a>Ağ geçidi türleri

Her biri farklı bir senaryoya yönelik olan iki farklı türde ağ geçidi bulunur:

* **Şirket içi veri ağ geçidi** birden fazla kullanıcının birden fazla şirket içi veri kaynağına bağlanmasını sağlar. Tek ağ geçidi kurulumuyla, tüm desteklenen hizmetler ile bir şirket içi veri ağ geçidi kullanabilirsiniz. Bu ağ geçidi birden fazla kullanıcının birden fazla veri kaynağına eriştiği karmaşık senaryolara çok uygundur.

* **Şirket içi veri ağ geçidi (kişisel mod)** tek kullanıcının kaynaklara bağlantı kurmasını sağlar ve başkalarıyla paylaşılamaz. Şirket içi veri ağ geçidi (kişisel mod) sadece Power BI ile kullanılabilir. Bu ağ geçidi, rapor oluşturan tek kişinin siz olduğunuz ve herhangi bir veri kaynağını başkalarıyla paylaşmak zorunda olmadığınız senaryolara çok uygundur.

## <a name="use-a-gateway"></a>Ağ geçidi kullan

Ağ geçidi kullanmanın dört ana adımı vardır.

1. Bir yerel bilgisayara [Ağ geçidini indirme ve yükleme](/data-integration/gateway/service-gateway-install).
1. Güvenlik duvarınızı ve diğer ağ gereksinimlerini temel alarak ağ geçidini [Yapılandırma](/data-integration/gateway/service-gateway-app).
1. Diğer ağ gereksinimlerini yönetebilen [Ağ geçidi yöneticileri ekleme](/data-integration/gateway/service-gateway-manage).
1. Şirket içi veri kaynağını yenilemek için [ağ geçidini kullanın](service-gateway-sql-tutorial.md).
1. Hata oluştuğunda [Sorun giderme](service-gateway-onprem-tshoot.md).

## <a name="next-steps"></a>Sonraki adımlar

* [Şirket içi veri ağ geçidini yükleme](/data-integration/gateway/service-gateway-install)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)
