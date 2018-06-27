---
title: Power BI’da özel kuruluş görsellerini kullanma
description: Power BI'da özel kuruluş görsellerini kullanma, yönetme ve oluşturma
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 02/06/2018
ms.author: maghan
LocalizationGroup: Visualizations
ms.openlocfilehash: bc4dcc26ac2007e482b396139d572018c8a3acd3
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
ms.locfileid: "34291915"
---
# <a name="using-organization-custom-visuals-in-power-bi"></a>Power BI’da özel kuruluş görsellerini kullanma

Power BI'da özel görselleri kullanarak size veya aktarmaya çalıştığınız veri bilgilerine göre uyarlanmış, benzersiz türde bir görsel oluşturabilirsiniz. Bu özel görseller genellikle geliştiriciler tarafından, Power BI’daki birçok görselin gereksinimlerini tam olarak karşılamadığı durumlarda oluşturulur. 

Bazı kuruluşlarda özel görseller daha da önemlidir ve bunlar kuruluşa özgü verilerin ya da bilgilerin aktarılması için gerekli olabilir, özel veri gereksinimlerine sahip olabilir ya da özel iş yöntemlerini vurgulayabilir. Bu durumdaki kuruluşların özel görseller geliştirmesi, kuruluş genelinde paylaşması ve bakımlarının düzgün yapıldığından emin olması gerekir. Power BI özel görselleri, kuruluşların tam olarak bunu yapmasına olanak sağlar.

Aşağıdaki resimde, Power BI’daki özel kuruluş görsellerinin yöneticiden başlayıp geliştirme ve bakım aşamalarından geçerek veri analistinde sonlanan akış süreci gösterilmektedir.

![](media/power-bi-custom-visuals-organizational/custom-visual-org-01.jpg)

Kuruluş görselleri, Power BI yöneticisi tarafından Yönetim portalından dağıtılır ve yönetilir. Görsel kuruluş deposuna dağıtıldıktan sonra kuruluştaki kullanıcılar bunları doğrudan Power BI Desktop’tan kolayca keşfedebilir ve özel kuruluş görsellerini raporlarında içeri aktarabilir.

## <a name="using-organizational-custom-visuals"></a>Özel kuruluş görsellerini kullanma

Oluşturduğunuz raporlarda özel kuruluş görsellerini kullanma hakkında daha fazla bilgi için şu makaleye bakın: [Kuruluş görsellerini raporlarınızda içeri aktarma hakkında daha fazla bilgi edinin](power-bi-custom-visuals.md).
 
## <a name="administering-organizational-custom-visuals"></a>Özel kuruluş görsellerini yönetme

Kuruluşunuzda özel kuruluş görsellerini yönetme, dağıtma ve yönetme hakkında daha fazla bilgi edinmek için şu makaleye bakın: [Özel kuruluş görsellerinin dağıtımı ve yönetimi hakkında daha fazla bilgi edinin](https://go.microsoft.com/fwlink/?linkid=866790).

> [!WARNING]
> Özel bir görsel, güvenlik veya gizlilik riski taşıyan kod içerebilir. Bir özel görseli kuruluş deposuna dağıtmadan önce görselin yazarına ve kaynağına güvendiğinizden emin olun. 
> 

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar
 
Bilmeniz gereken birçok önemli nokta ve sınırlama vardır.
 
Yönetici:

* Eski özel görseller (sürümü tutulan yeni API'leri temel almayan özel görseller gibi) desteklenmez

* Özel bir görsel depodan silinirse, silinen görseli kullanan tüm mevcut raporlar işlenmeyi durdurur. Depodan silme işlemi geri alınamaz. Özel bir görseli geçici olarak devre dışı bırakmak için "Devre dışı bırak" özelliğini kullanın.
 
Son kullanıcı:

* Kuruluş görselleri için Power BI Çalışma Alanı Koleksiyonu desteklenmez

* AppSource marketten edinilen Visio görseli, PowerApps görseli ve GlobeMap görseli kuruluş deposu aracılığıyla dağıtılırsa gösterilmez
