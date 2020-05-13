---
title: Şirket içi veri ağ geçidi
description: Bu makale, Power BI için şirket içi veri ağ geçidine bir genel bakıştır. DirectQuery veri kaynaklarıyla çalışmak için bu ağ geçidini kullanabilirsiniz. Bulut veri kümelerini şirket içi verilerle yenilemek için de bu ağ geçidini kullanabilirsiniz.
author: arthiriyer
ms.author: arthii
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
LocalizationGroup: Gateways
ms.date: 07/15/2019
ms.openlocfilehash: 1d91792d544854d5a98b1966b2561196249ff7c8
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83302863"
---
# <a name="what-is-an-on-premises-data-gateway"></a>Şirket içi veri ağ geçidi nedir?

[!INCLUDE [gateway-rewrite](../includes/gateway-rewrite.md)]

Şirket içi veri ağ geçidi bir köprü işlevi görerek şirket içi veriler (bulutta olmayan veriler) ile çeşitli Microsoft bulut hizmetleri arasında hızlı ve güvenli veri aktarımı sağlar. Bu bulut hizmetleri Power BI, PowerApps, Power Automate, Azure Analysis Services ve Azure Logic Apps'tir. Bir ağ geçidi kullanarak, kuruluşlar veritabanlarını ve diğer veri kaynaklarını şirket içi ağlarında tutabilir ve diğer yandan da bu şirket içi verileri bulut hizmetlerinde güvenli bir şekilde kullanabilir.

## <a name="how-the-gateway-works"></a>Ağ geçidi nasıl çalışır?

![Ağ geçidine genel bakış](media/service-gateway-onprem/on-premises-data-gateway.png)

Ağ geçidinin nasıl çalıştığı hakkında daha fazla bilgi için bkz. [Şirket içi veri ağ geçidi mimarisi](/data-integration/gateway/service-gateway-onprem-indepth).

## <a name="types-of-gateways"></a>Ağ geçidi türleri

Her biri farklı bir senaryoya yönelik olan iki farklı türde ağ geçidi bulunur:

* **Şirket içi veri ağ geçidi** birden fazla kullanıcının birden fazla şirket içi veri kaynağına bağlanmasını sağlar. Tek bir ağ geçidi yüklemesiyle, şirket içi veri ağ geçidini tüm desteklenen hizmetlerle kullanabilirsiniz. Bu ağ geçidi birden çok kişinin birden çok veri kaynağına eriştiği karmaşık senaryolara çok uygundur.

* **Şirket içi veri ağ geçidi (kişisel mod)** tek kullanıcının kaynaklara bağlantı kurmasını sağlar ve başkalarıyla paylaşılamaz. Şirket içi veri ağ geçidi (kişisel mod) yalnızca Power BI ile kullanılabilir. Bu ağ geçidi, rapor oluşturan tek kişinin siz olduğunuz ve herhangi bir veri kaynağını başkalarıyla paylaşmak zorunda olmadığınız senaryolara çok uygundur.

## <a name="use-a-gateway"></a>Ağ geçidi kullanma

Ağ geçidi kullanmanın dört ana adımı vardır.

1. Bir yerel bilgisayara [Ağ geçidini indirme ve yükleme](/data-integration/gateway/service-gateway-install).
1. Güvenlik duvarınızı ve diğer ağ gereksinimlerini temel alarak ağ geçidini [yapılandırma](/data-integration/gateway/service-gateway-app).
1. Diğer ağ gereksinimlerini de yönetebilen [Ağ geçidi yöneticileri ekleme](/data-integration/gateway/service-gateway-manage).
1. Şirket içi veri kaynağını yenilemek için [ağ geçidini kullanın](service-gateway-sql-tutorial.md).
1. Hata oluştuğunda ağ geçidi [sorunları giderme](service-gateway-onprem-tshoot.md).

## <a name="next-steps"></a>Sonraki adımlar

* [Şirket içi veri ağ geçidini yükleme](/data-integration/gateway/service-gateway-install)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)
