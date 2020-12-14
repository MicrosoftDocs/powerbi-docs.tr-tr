---
title: Power BI Embedded uygulamanızı üretim ortamına taşıma
description: Power BI uygulamanızı üretim ortamına taşımak için izlemeniz gereken adımları öğrenin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
ms.topic: tutorial
ms.service: powerbi
ms.subservice: powerbi-developer
ms.custom: seodec18
ms.date: 06/02/2020
ms.openlocfilehash: 6132066f9b724cf5658d3e66ccb835bb23b93d39
ms.sourcegitcommit: 30d0668434283c633bda9ae03bc2aca75401ab94
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/09/2020
ms.locfileid: "96907748"
---
# <a name="move-your-embedded-app-to-production"></a>Embedded uygulamanızı üretim ortamına taşıma

Uygulamanızın geliştirme aşamasını tamamladıktan sonra üretim ortamına taşımak için çalışma alanınızı bir kapasite ile desteklemeniz gerekir.

> [!Important]
> Tüm çalışma alanları (raporları veya panoları içeren çalışma alanı ile veri kümesini içeren çalışma alanı) bir kapasiteye atanmalıdır.

## <a name="create-a-capacity"></a>Kapasite oluşturma

Kapasite oluşturduğunuzda, müşterilerinize yönelik bir kaynaktan yararlanabilirsiniz. İki tür kapasiteden birini seçebilirsiniz:

* **Power BI Premium** - *EM* ve *P* şeklinde iki SKU ailesinde kullanılabilen kiracı düzeyindeki bir Microsoft 356 aboneliği. Power BI içeriği eklerken bu çözüm *Power BI ekleme* olarak adlandırılır. Bu abonelikle ilgili daha fazla bilgi için bkz. [Power BI Premium nedir?](../../admin/service-premium-what-is.md)

* **Azure Power BI Embedded**: [Microsoft Azure portalından](https://portal.azure.com) kapasite satın alabilirsiniz. Bu abonelik *A* SKU’ları kullanır. Power BI Embedded kapasitesi oluşturma hakkında ayrıntılı bilgi için bkz. [Azure portalında Power BI Embedded kapasitesi oluşturma](azure-pbie-create-capacity.md).

    > [!NOTE]
    > A SKU’larla, ÜCRETSİZ Power BI lisansını kullanarak Power BI içeriğine erişemezsiniz.

### <a name="capacity-specifications"></a>Kapasite özellikleri

Aşağıdaki tabloda her SKU'nun kaynakları ve limitleri açıklanmaktadır. İhtiyaçlarınıza en uygun kapasiteyi öğrenmek için [Senaryom için hangi SKU’yu satın almalıyım?](./embedded-faq.md#which-solution-should-i-choose) tablosuna bakın.

| Kapasite Düğümleri | Toplam sanal çekirdek sayısı | Arka uç sanal çekirdek sayısı | RAM (GB) | Ön uç sanal çekirdek sayısı | DirectQuery/Canlı Bağlantı (saniyede) | Model Yenileme Paralelliği |
| --- | --- | --- | --- | --- | --- | --- |
| EM1/A1 | 1 | 0,5 | 2.5 | 0,5 | 3,75 | 1 |
| EM2/A2 | 2 | 1 | 5 | 1 | 7,5 | 2 |
| EM3/A3 | 4 | 2 | 10 | 2 | 15 | 3 |
| P1/A4 | 8 | 4 | 25 | 4 | 30 | 6 |
| P2/A5 | 16 | 8 | 50 | 8 | 60 | 12 |
| P3/A6 | 32 | 16 | 100 | 16 | 120 | 24 |
| | | | | | | |

## <a name="development-testing"></a>Geliştirme testi

Geliştirme testi için Pro lisansıyla ekleme deneme belirteçlerini kullanabilirsiniz. Üretim ortamında ekleme yapmak için bir kapasite kullanın.

Bir Power BI *hizmet sorumlusunun* veya *ana kullanıcısının* (ana hesap) oluşturabileceği ekleme deneme belirteci sayısı sınırlıdır. Geçerli ekleme kullanım yüzdenizi kontrol etmek için [Kullanılabilir Özellikler](/rest/api/power-bi/availablefeatures/getavailablefeatures) API'sini kullanın. Hizmet sorumlusu veya ana hesap başına kullanım miktarı görüntülenir.

Test sırasında ekleme belirteçleriniz tükenirse Power BI Embedded veya Premium [kapasitesi](embedded-capacity.md) satın almanız gerekir. Kapasiteyle oluşturabileceğiniz ekleme belirteçlerinin sayısıyla ilgili bir sınır yoktur.

## <a name="assign-a-workspace-to-a-capacity"></a>Bir kapasiteye çalışma alanı atama

Kapasite oluşturduktan sonra, çalışma alanınızı bu kapasiteye atayabilirsiniz.

Eklenen içerikle (veri kümeleri, raporlar ve panolar dahil) ilgili Power BI kaynaklarını içeren tüm çalışma alanları kapasitelere atanmalıdır. Örneğin eklenen rapor ve ona bağlı olan veri kümesi farklı çalışma alanlarında bulunuyorsa, her iki çalışma alanı da kapasitelere atanmalıdır.

### <a name="assign-a-workspace-to-a-capacity-using-a-service-principal"></a>Hizmet sorumlusu kullanarak kapasiteye çalışma alanı atama

[Hizmet sorumlusu](embed-service-principal.md) kullanarak çalışma alanına kapasite atamak için [Power BI REST API'sini](/rest/api/power-bi/capacities/groups_assigntocapacity) kullanın. Power BI REST API'lerini kullanırken [hizmet sorumlusu nesne kimliğini](embed-service-principal.md) kullandığınızdan emin olun.

### <a name="assign-a-workspace-to-a-capacity-using-a-master-user"></a>Ana kullanıcı kullanarak kapasiteye çalışma alanı atama

**Ana kullanıcı** kullanarak çalışma alanına kapasite atamak için aşağıdaki adımları izleyin.

1. Çalışma alanını **Power BI hizmetinde** açın. 

1. **Power BI hizmetinde**, çalışma alanlarını genişletin ve içeriğinizi eklemek için kullandığınız çalışma alanına yönelik olan üç noktayı seçin. Ardından **Çalışma alanlarını düzenle**’yi seçin.

    >[!div class="mx-imgBorder"]
    >:::image type="content" source="media/move-to-production/workspace-settings.png" alt-text="Power BI hizmeti portalındaki çalışma alanı ayarları menüsünü gösteren ekran görüntüsü.":::

2. **Premium** sekmesini seçin ve şunları yapın:

    * **Kapasite**'yi etkinleştirin.

    * Oluşturduğunuz kapasiteyi seçin.

    * **Kaydet**’i seçin.

    >[!div class="mx-imgBorder"]
    >:::image type="content" source="media/move-to-production/premium-tab.png" alt-text="Power BI hizmeti portalındaki çalışma alanı premium ayarlar menüsünü gösteren ekran görüntüsü.":::

    Kapasiteye atadığınız çalışma alanının yanında bir elmas simgesi görünür 

    >[!div class="mx-imgBorder"]
    >:::image type="content" source="media/move-to-production/premium-workspace.png" alt-text="Power BI hizmeti portalında premium kapasiteye atanmış olan çalışma alanının yanındaki elmas simgesini gösteren ekran görüntüsü.":::

## <a name="next-steps"></a>Sonraki adımlar

>[!div class="nextstepaction"]
>[Power BI tümleşik analizinde kapasite ve SKU’lar](embedded-capacity.md)

>[!div class="nextstepaction"]
>[Power BI tümleşik analizinde kapasite planlaması](embedded-capacity-planning.md)

>[!div class="nextstepaction"]
>[Ekleme belirteci oluştururken dikkate alınması gerekenler](generate-embed-token.md)