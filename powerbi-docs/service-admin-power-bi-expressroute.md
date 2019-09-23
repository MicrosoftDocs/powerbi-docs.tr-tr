---
title: Power BI ve ExpressRoute
description: Power BI ve ExpressRoute
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 09/09/2019
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: c7d12bf6a1a2a02c988f8351a1844be1080ad2b8
ms.sourcegitcommit: a97c0c34f888e44abf4c9aa657ec9463a32be06f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2019
ms.locfileid: "71074791"
---
# <a name="power-bi-and-expressroute"></a>Power BI ve ExpressRoute

**ExpressRoute**, Azure veri merkezleri (Power BI'ın bulunduğu) ile şirket içi altyapınız veya Azure veri merkezleri ile ortak konum ortamınız arasında özel bağlantılar oluşturmanıza olanak sağlayan bir Azure hizmetidir.

**Power BI** ve **ExpressRoute** ile gizli Power BI verileriniz ve bağlantılarınız için daha yüksek düzeyde güvenlik sağlamak üzere, İnternet kullanmadan (veya bir ISP ortak konum özelliği kullanarak) kuruluşunuz ile Power BI arasında özel bir ağ bağlantısı oluşturabilirsiniz.

Daha fazla bilgi için bkz. [ExpressRoute'a genel bakış](/azure/expressroute/expressroute-introduction). Power BI, Power BI'ın genel İnternet üzerinden veri aldığı veya gönderdiği bazı özel durumlar hariç olmak üzere ExpressRoute ile uyumludur. Power BI'ın kullandığı URL'lerin listesi için bkz. [Power BI URL'leri](power-bi-whitelist-urls.md).

![ExpressRoute diyagramı](media/service-admin-power-bi-expressroute/pbi_expressroute_1.png)