---
title: Veri kümesi ve veri akışı onaylamasını ayarlama (önizleme)
description: Kuruluşunuzda veri kümesi ve veri akışı onaylama işlemini ayarlamayı öğrenin.
author: paulinbar
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 03/22/2020
ms.author: painbar
LocalizationGroup: Share your work
ms.openlocfilehash: 1fc33b48613335f4fba97921e3d528175eb2a47f
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "81267857"
---
# <a name="set-up-dataset-and-dataflow-certification-preview"></a>Veri kümesi ve veri akışı onaylamasını ayarlama (önizleme)

Kuruluşunuz, kritik bilgiler için yetkili kaynaklar olan veri kümelerini ve veri akışlarını onaylayabilir.

Power BI kiracı yöneticisi olarak kuruluşunuzda onaylama işlemini ayarlamak sizin sorumluluğunuzdadır. Diğer bir deyişle:
* Kiracınızda onaylamayı etkinleştirirsiniz.
* Veri kümelerini ve veri akışlarını onaylama yetkisi olacak grupların ve kullanıcıların listesini tanımlarsınız.
* Veri kümeleri için, kuruluşun veri kümesi onaylama ilkesinin (varsa) URL’sini sağlarsınız.

Veri kümesi ve veri akışı onaylama işlemi, veri kümesi ve veri akışı *onay* sürecinin bir parçasıdır. Daha fazla bilgi için [veri kümesi onayı](../service-datasets-promote.md) ve [veri akışı onayı](../transform-model/service-dataflows-promote-certify.md) konularına bakın.


## <a name="set-up-certification"></a>Onaylamayı ayarlama

1. Yönetim portalında Kiracı ayarlarına gidin.
1. Dışarı aktarma ve paylaşım ayarları bölümünde Onaylama bölümünü genişletin.

   ![Veri kümesi ve veri akışı sertifikası ayarlama](media/service-admin-setup-certification/service-admin-certification-setup-dialog.png)

1. İki durumlu düğmeyi **Etkinleştirildi** olarak ayarlayın.
1. Veri kümesi onaylama işlemi için, kuruluşunuz onaylama ilkesi yayımladıysa burada ilkenin URL’sini sağlayabilirsiniz. Bu URL **veri akışı onay ayarları iletişim kutusunun** onaylama bölümünde [Daha fazla bilgi edinin](../service-datasets-promote.md#request-dataset-certification) bağlantısına dönüşür. 
1. Veri kümelerini ve veri akışlarını onaylama yetkisi olacak kullanıcıları ve grupları belirtin. Bu yetkili onaylayıcılar [veri kümesi](../service-datasets-promote.md#request-dataset-certification) veya [veri akışı](../transform-model/service-dataflows-promote-certify.md#certify-a-dataflow) onay ayarları iletişim kutusunun onaylama bölümündeki Onaylama düğmesini kullanabilir.
1. **Uygula**'ya tıklayın.

## <a name="next-steps"></a>Sonraki adımlar
* [Veri kümelerini tanıtma](../service-datasets-promote.md)
* [Veri kümelerini onaylama](../service-datasets-certify.md)
* [Veri akışlarını yükseltme](../transform-model/service-dataflows-promote-certify.md#promote-a-dataflow)
* [Veri akışlarını onaylama](../transform-model/service-dataflows-promote-certify.md#certify-a-dataflow)
* Sorular? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
