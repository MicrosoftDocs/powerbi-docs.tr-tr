---
title: Power BI’da müşteri tarafından yönetilen anahtarları kullanma
description: Power BI’da müşteri tarafından yönetilen anahtarları kullanmayı öğrenin.
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: how-to
ms.date: 11/11/2020
LocalizationGroup: Premium
ms.openlocfilehash: 215c84b9af9d3b785c055d633a41b99bbea2bb2f
ms.sourcegitcommit: cc20b476a45bccb870c9de1d0b384e2c39e25d24
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/11/2020
ms.locfileid: "94512597"
---
# <a name="use-customer-managed-keys-in-power-bi"></a>Power BI’da müşteri tarafından yönetilen anahtarları kullanma

Power BI bekleyen ve işlenmekte olan verileri şifreler. Varsayılan olarak Power BI verilerinizi şifrelemek için Microsoft tarafından yönetilen anahtarları kullanır. Kuruluşlar, rapor görüntülerinden Premium kapasitelere içeri aktarılan veri kümelerine, Power BI’daki bekleyen kullanıcı içeriklerini şifrelemek için kendi anahtarlarını kullanmayı tercih edebilir. 

## <a name="why-use-customer-managed-keys"></a>Müşteri tarafından yönetilen anahtarları neden kullanmalıyım?

Power BI müşteri tarafından yönetilen anahtarlar (CMK) sayesinde kuruluşlar bulut sağlayıcısıyla (bu durumda Microsoft) bekleyen veri şifrelemesine yönelik uyumluluk gereksinimlerini karşılayabilir. CMK yalnızca yeni Power BI Premium müşterileri için sunulur ve kuruluşların Power BI kullanıcı içeriklerini kendi sağladıkları ve yönettikleri bir anahtar kullanarak şifrelemesini sağlar. Müşteri tarafından yönetilen anahtarın iptal edilmesi, Power BI’daki kullanıcı içeriğini bir saat içinde Microsoft dahil hiç kimse tarafından okunamaz hale getirir. KAG teklifiyle karşılaştırıldığında CMK ayrıca Premium kapasitelerde barındırılan raporlara ve veri kümelerine aktarılan müşteri verilerine ek olarak hizmet tarafından oluşturulan kullanıcı içeriklerini de kapsar, daha sıkı önbelleğe alma ilkeleri uygular ve tüm verileri şifrelemek için tek bir anahtar kullanabilir.


## <a name="how-to-use-customer-managed-keys"></a>Müşteri tarafından yönetilen anahtarları kullanma
Power BI müşteri tarafından yönetilen anahtarlar özelliğini kullanmak için kuruluşunuzun ilgili Microsoft hesap yöneticisiyle iletişime geçerek CMK özelliğini etkinleştirmek için gerekli şartları karşıladığını doğrulaması gerekir.  


## <a name="next-steps"></a>Sonraki adımlar

Aşağıdaki bağlantılarda, müşteri tarafından yönetilen anahtarlar için yararlı olabilecek bilgiler sağlanır:

* [Power BI için kendi anahtarını getir şifrelemesi](service-encryption-byok.md)
* [Power BI Premium için Multi-Geo desteğini yapılandırma](service-admin-premium-multi-geo.md)
* [Kapasiteler nasıl çalışır?](service-premium-what-is.md#how-capacities-function)
* [Artımlı yenileme](service-premium-incremental-refresh.md).
