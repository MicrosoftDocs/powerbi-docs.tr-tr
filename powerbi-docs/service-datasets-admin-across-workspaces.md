---
title: Çalışma alanları genelinde veri kümeleri kullanımını denetleme (Önizleme) - Power BI
description: Power BI kiracısında bilgi akışını kısıtlamayı öğrenin.
author: maggiesMSFT
manager: kfile
ms.reviewer: chbraun
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/31/2019
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 363bf9b107722b3993ed7ac43138c73da03f410a
ms.sourcegitcommit: 7c426a5209d4fdd1360fc3d0442d57991be1984d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/03/2019
ms.locfileid: "66461799"
---
# <a name="control-the-use-of-datasets-across-workspaces-preview"></a>Çalışma alanları genelinde veri kümeleri kullanımını denetleme (Önizleme)

Çalışma alanları genelinde veri kümeleri kullanma, bir kuruluştaki veri kültürü ve veri demokratikleştirmesini teşvik etmenin güçlü bir yoludur. Yine de, bir Power BI yöneticisiyseniz bazen bilgi akışını Power BI kiracınızda kısıtlamak istersiniz. **Çalışma alanları genelinde veri kümeleri kullanma** kiracı ayarıyla, veri kümesini yeniden kullanılmasını güvenlik grubu başına tamamen veya kısmen kısıtlayabilirsiniz.

![Power BI yöneticisi çalışma alanı ayarları](media/service-datasets-admin-across-workspaces/power-bi-admin-workspace-settings.png)

Bu ayarı kapatırsanız, rapor oluşturucularda şöyle etkileri olur:

- Çalışma alanları genelindeki raporları kopyalama düğmesi kullanılamaz. 
- Paylaşılan veri kümesini temel alan bir raporda, **Raporu düzenle** düğmesi kullanılamaz.
- Power BI hizmetinde, bulma deneyimini yalnızca geçerli çalışma alanındaki veri kümelerini gösterir.
- Power BI Desktop'ta, bulma deneyimi yalnızca üyesi olduğunuz çalışma alanlarındaki veri kümelerini gösterir.
- Power BI Desktop’ta, kullanıcılar üyesi oldukları herhangi bir çalışma alanının dışındaki veri kümesine canlı bağlantıyla bir .pibx dosyası açarsa, farklı bir veri kümesine bağlanmalarını isteyen bir hata iletisi görürler.

## <a name="provide-a-link-for-the-certification-process"></a>Onaylama süreci için bağlantı sağlama

Kiracı yöneticisi olarak, **Onay** ayarı sayfasındaki **Daha fazla bilgi edinin** bağlantısı için bir URL sağlayabilirsiniz.  Bu bağlantı onaylama süreciniz hakkındaki belgelere gidebilir. **Daha fazla bilgi edinin** bağlantısı için bir hedef sağlamazsanız, bağlantı varsayılan olarak [veri kümesi onaylama](service-datasets-certify.md) makalesine işaret eder.

![Veri kümesi onayı - Daha fazla bilgi edinin](media/service-datasets-certify-promote/power-bi-dataset-learn-more-certification.png)

## <a name="next-steps"></a>Sonraki adımlar

- [Çalışma alanları genelinde veri kümeleri kullanma (Önizleme)](service-datasets-across-workspaces.md)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)
