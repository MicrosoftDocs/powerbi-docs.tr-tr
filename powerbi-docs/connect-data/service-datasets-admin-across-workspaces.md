---
title: Çalışma alanları genelinde veri kümeleri kullanımını denetleme - Power BI
description: Power BI kiracısında bilgi akışını kısıtlamayı öğrenin.
author: maggiesMSFT
ms.reviewer: kayu
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
ms.date: 04/30/2020
ms.author: maggies
LocalizationGroup: Share your work
ms.openlocfilehash: 6cc602b96207b1662f0738c0936ca816bbfd0a03
ms.sourcegitcommit: 4e347efd132b48aaef6c21236c3a21e5fce285cc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92681055"
---
# <a name="control-the-use-of-datasets-across-workspaces"></a>Çalışma alanları genelinde veri kümeleri kullanımını denetleme

Çalışma alanları genelinde veri kümeleri kullanma, bir kuruluştaki veri kültürü ve veri demokratikleştirmesini teşvik etmenin güçlü bir yoludur. Yine de, bir Power BI yöneticisiyseniz bazen bilgi akışını Power BI kiracınızda kısıtlamak istersiniz. **Çalışma alanları genelinde veri kümeleri kullanma** kiracı ayarıyla, veri kümesini yeniden kullanılmasını güvenlik grubu başına tamamen veya kısmen kısıtlayabilirsiniz.

![Power BI yöneticisi çalışma alanı ayarları](media/service-datasets-admin-across-workspaces/power-bi-admin-workspace-settings.png)

Bu ayarı kapatırsanız, rapor oluşturucularda şöyle etkileri olur:

- Çalışma alanları genelindeki raporları kopyalama düğmesi kullanılamaz. 
- Paylaşılan veri kümesini temel alan bir raporda, **Raporu düzenle** düğmesi kullanılamaz.
- Power BI hizmetinde, bulma deneyimini yalnızca geçerli çalışma alanındaki veri kümelerini gösterir.
- Power BI Desktop'ta, bulma deneyimi yalnızca üyesi olduğunuz çalışma alanlarındaki veri kümelerini gösterir.
- Power BI Desktop’ta, kullanıcılar üyesi oldukları herhangi bir çalışma alanının dışındaki veri kümesine canlı bağlantıyla bir .pibx dosyası açarsa, farklı bir veri kümesine bağlanmalarını isteyen bir hata iletisi görürler.

## <a name="provide-a-link-for-the-certification-process"></a>Onaylama süreci için bağlantı sağlama

Power BI yöneticisi olarak **Onay** ayarı sayfasındaki **Daha fazla bilgi edinin** bağlantısı için bir URL sağlayabilirsiniz.  Ayrıntılar için bkz. [İçerik onayını etkinleştirme](../admin/service-admin-setup-certification.md). Bu bağlantı onaylama süreciniz hakkındaki belgelere gidebilir. **Daha fazla bilgi edinin** bağlantısı için bir hedef sağlamazsanız, bağlantı varsayılan olarak [İçeriğinizi onaylama](../collaborate-share/service-endorse-content.md) makalesini açar.

![Veri kümesi onayı - Daha fazla bilgi edinin](media/service-datasets-admin-across-workspaces/service-admin-certification-setup-dialog.png)

## <a name="next-steps"></a>Sonraki adımlar

- [Veri kümelerini çalışma alanları arasında kullanma](service-datasets-across-workspaces.md)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
