---
title: Power BI ve ExpressRoute
description: Power BI ve ExpressRoute
author: mgblythe
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 09/09/2019
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 59ddddcf1b02f07b850294fa314b7508f7f9fcdc
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73856942"
---
# <a name="power-bi-and-expressroute"></a>Power BI ve ExpressRoute

**ExpressRoute**, Azure veri merkezleri (Power BI'ın bulunduğu) ile şirket içi altyapınız veya Azure veri merkezleri ile ortak konum ortamınız arasında özel bağlantılar oluşturmanıza olanak sağlayan bir Azure hizmetidir.

**Power BI** ve **ExpressRoute** ile gizli Power BI verileriniz ve bağlantılarınız için daha yüksek düzeyde güvenlik sağlamak üzere, İnternet kullanmadan (veya bir ISP ortak konum özelliği kullanarak) kuruluşunuz ile Power BI arasında özel bir ağ bağlantısı oluşturabilirsiniz.

Daha fazla bilgi için bkz. [ExpressRoute'a genel bakış](/azure/expressroute/expressroute-introduction). Power BI, Power BI'ın genel İnternet üzerinden veri aldığı veya gönderdiği bazı özel durumlar hariç olmak üzere ExpressRoute ile uyumludur. Power BI'ın kullandığı URL'lerin listesi için bkz. [Power BI URL'leri](power-bi-whitelist-urls.md).

![ExpressRoute diyagramı](media/service-admin-power-bi-expressroute/pbi_expressroute_1.png)