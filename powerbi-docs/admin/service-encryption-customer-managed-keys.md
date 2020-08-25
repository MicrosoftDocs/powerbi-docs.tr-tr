---
title: Power BI’da müşteri tarafından yönetilen anahtarları kullanma
description: Power BI’da müşteri tarafından yönetilen anahtarları kullanmayı öğrenin.
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: how-to
ms.date: 08/12/2020
LocalizationGroup: Premium
ms.openlocfilehash: 8d13cc7a24486fada7f8d428ba52abeaa49d2518
ms.sourcegitcommit: b60063c49ac39f8b28c448908ecbb44b54326335
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/12/2020
ms.locfileid: "88160952"
---
# <a name="use-customer-managed-keys-in-power-bi"></a>Power BI’da müşteri tarafından yönetilen anahtarları kullanma

Power BI bekleyen ve işlenmekte olan verileri şifreler. Varsayılan olarak Power BI verilerinizi şifrelemek için Microsoft tarafından yönetilen anahtarları kullanır. Kuruluşlar, rapor görüntülerinden Premium kapasitelere içeri aktarılan veri kümelerine, Power BI’daki bekleyen kullanıcı içeriklerini şifrelemek için kendi anahtarlarını kullanmayı tercih edebilir. 

## <a name="why-use-customer-managed-keys"></a>Müşteri tarafından yönetilen anahtarları neden kullanmalıyım?
Power BI müşteri tarafından yönetilen anahtarlar (CMK) sayesinde kuruluşlar bulut sağlayıcısıyla (bu durumda Microsoft) bekleyen veri şifrelemesine yönelik uyumluluk gereksinimlerini karşılayabilir. CMK, kuruluşların Power BI kullanıcı içeriğini kendilerinin sağlayıp yönettikleri bir anahtarla şifrelemesine olanak verir. Müşteri tarafından yönetilen anahtarın iptal edilmesi, Power BI’daki kullanıcı içeriğini bir saat içinde Microsoft dahil hiç kimse tarafından okunamaz hale getirir. KAG teklifiyle karşılaştırıldığında, CMK Power BI Premium kapasitelerinin dışındaki kullanıcı içeriğini de kapsar. Daha sıkı önbelleğe alma ilkelerini zorunlu kılar ve KAG’yi varsayılan olarak tüm kapasitelerde etkinleştirir. 
 
## <a name="how-to-use-customer-managed-keys"></a>Müşteri tarafından yönetilen anahtarları kullanma
Power BI müşteri tarafından yönetilen anahtarı kullanmak için kuruluşunuzun boyut gereksinimlerini karşılaması gerekir. Kuruluşunuzun genel yöneticisinin Microsoft’a bir destek isteği göndermesi gerekir. Alternatif olarak, süreç hakkında daha fazla bilgi edinmek için kuruluşunuzun Microsoft hesap yöneticisine de ulaşabilirler.  


## <a name="next-steps"></a>Sonraki adımlar

Aşağıdaki bağlantılarda, müşteri tarafından yönetilen anahtarlar için yararlı olabilecek bilgiler sağlanır:

* [Power BI için kendi anahtarını getir şifrelemesi](service-encryption-byok.md)
* [Power BI Premium için Multi-Geo desteğini yapılandırma](service-admin-premium-multi-geo.md)
* [Kapasiteler nasıl çalışır?](service-premium-what-is.md#how-capacities-function)
* [Artımlı yenileme](service-premium-incremental-refresh.md).
