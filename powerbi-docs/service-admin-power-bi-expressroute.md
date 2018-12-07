---
title: Power BI ve ExpressRoute
description: Power BI ve ExpressRoute
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: conceptual
ms.date: 12/03/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 62289c974e25207f3a991e7f17a0ee965c729b8a
ms.sourcegitcommit: b03912343a5a214c6bb972aaa6aa051c2a5f4332
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2018
ms.locfileid: "52900141"
---
# <a name="power-bi-and-expressroute"></a>Power BI ve ExpressRoute

**ExpressRoute**, Azure veri merkezleri (Power BI'ın bulunduğu) ile şirket içi altyapınız veya Azure veri merkezleri ile ortak konum ortamınız arasında özel bağlantılar oluşturmanıza olanak sağlayan bir Azure hizmetidir.

**Power BI** ve **ExpressRoute** ile gizli Power BI verileriniz ve bağlantılarınız için daha yüksek düzeyde güvenlik sağlamak üzere, İnternet kullanmadan (veya bir ISP ortak konum özelliği kullanarak) kuruluşunuz ile Power BI arasında özel bir ağ bağlantısı oluşturabilirsiniz.

Daha fazla bilgi için bkz. [ExpressRoute'a genel bakış](/azure/expressroute/expressroute-introduction). Power BI, Power BI'ın genel İnternet üzerinden veri aldığı veya gönderdiği bazı özel durumlar hariç olmak üzere ExpressRoute ile uyumludur. Power BI'ın kullandığı URL'lerin listesi için bkz. [Power BI URL'leri](power-bi-whitelist-urls.md).

![ExpressRoute diyagramı](media/service-admin-power-bi-expressroute/pbi_expressroute_1.png)