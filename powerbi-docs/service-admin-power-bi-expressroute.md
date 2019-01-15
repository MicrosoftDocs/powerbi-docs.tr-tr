---
title: Power BI ve ExpressRoute
description: Power BI ve ExpressRoute
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 12/03/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 0c4618150094a4eabb0dc9745e9ac93e4f342ff1
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2019
ms.locfileid: "54291108"
---
# <a name="power-bi-and-expressroute"></a>Power BI ve ExpressRoute

**ExpressRoute**, Azure veri merkezleri (Power BI'ın bulunduğu) ile şirket içi altyapınız veya Azure veri merkezleri ile ortak konum ortamınız arasında özel bağlantılar oluşturmanıza olanak sağlayan bir Azure hizmetidir.

**Power BI** ve **ExpressRoute** ile gizli Power BI verileriniz ve bağlantılarınız için daha yüksek düzeyde güvenlik sağlamak üzere, İnternet kullanmadan (veya bir ISP ortak konum özelliği kullanarak) kuruluşunuz ile Power BI arasında özel bir ağ bağlantısı oluşturabilirsiniz.

Daha fazla bilgi için bkz. [ExpressRoute'a genel bakış](/azure/expressroute/expressroute-introduction). Power BI, Power BI'ın genel İnternet üzerinden veri aldığı veya gönderdiği bazı özel durumlar hariç olmak üzere ExpressRoute ile uyumludur. Power BI'ın kullandığı URL'lerin listesi için bkz. [Power BI URL'leri](power-bi-whitelist-urls.md).

![ExpressRoute diyagramı](media/service-admin-power-bi-expressroute/pbi_expressroute_1.png)