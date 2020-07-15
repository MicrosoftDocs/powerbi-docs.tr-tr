---
title: Power BI'da duyarlılık etiketlerini uygulama
description: Power BI'da duyarlılık etiketlerini uygulamayı öğrenin
author: paulinbar
ms.service: powerbi
ms.subservice: powerbi-eim
ms.topic: how-to
ms.date: 07/06/2020
ms.author: painbar
LocalizationGroup: Data from files
ms.openlocfilehash: f92d10fdff880049460d24c714201d9a433745d8
ms.sourcegitcommit: 181679a50c9d7f7faebcca3a3fc55461f594d9e7
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/07/2020
ms.locfileid: "86035253"
---
# <a name="how-to-apply-sensitivity-labels-in-power-bi"></a>Power BI'da duyarlılık etiketlerini uygulama

Rapor, pano, veri kümesi ve veri akışlarınıza uygulanan Microsoft Information Protection duyarlılık etiketleri, hassas içeriklerinizi yetkisiz veri erişimi ve sızıntılara karşı koruyabilir. Verilerinize duyarlılık etiketlerinin doğru şekilde uygulanması, verilerinize yalnızca yetkili kişilerin erişebilmesini sağlar. Bu makalede, içeriğinize duyarlılık etiketlerini nasıl uygulayacağınız gösterilmektedir.

Power BI’da duyarlılık etiketleri uygulayabilmek için:
* Bir Power BI Pro lisansına ve etiketlemek istediğiniz içerik üzerinde Düzenleme izinlerine sahip olmanız gerekir.
* [Power BI’da duyarlılık etiketlerini etkinleştirme](./service-security-enable-data-sensitivity-labels.md#enable-sensitivity-labels) makalesinde açıklandığı gibi, duyarlılık etiketlerini uygulama izinleri olan bir güvenlik grubuna dahil olmanız gerekir.
* Tüm [önkoşulların](./service-security-sensitivity-label-overview.md#requirements-for-using-sensitivity-labels-in-power-bi) ve [lisans gereksinimlerinin](./service-security-data-protection-overview.md#licensing) karşılanması gerekir.

Power BI’daki duyarlılık etiketleri hakkında daha fazla bilgi için bkz. [Power BI'daki duyarlılık etiketleri](service-security-sensitivity-label-overview.md).

## <a name="applying-sensitivity-labels"></a>Duyarlılık etiketleri uygulama

Kiracınızda veri koruma etkin olduğunda panolar, raporlar, veri kümeleri ve veri akışlarının liste görünümünün duyarlılık sütununda duyarlılık etiketleri görünür.

![Duyarlılık etiketlerini etkinleştirme](media/service-security-apply-data-sensitivity-labels/apply-data-sensitivity-labels-01.png)

**Rapor veya panodaki bir duyarlılık etiketini uygulama veya değiştirme**
1. **Daha fazla (...)** seçeneğine tıklayın.
1. **Ayarlar**'ı seçin.
1. Ayarlar kenar bölmesinde uygun duyarlılık etiketini seçin.
1. Ayarları kaydedin.

Aşağıdaki görüntüde rapordaki bu adımlar gösterilmektedir

![Duyarlılık etiketlerini ayarlama](media/service-security-apply-data-sensitivity-labels/apply-data-sensitivity-labels-02.png)

**Veri kümesi veya veri akışındaki bir duyarlılık etiketini uygulama veya değiştirme**

1. **Diğer seçenekler (...)** öğesine tıklayın.
1. **Ayarlar**'ı seçin.
1. Ayarlar kenar bölmesinde uygun duyarlılık etiketini seçin.
1. Ayarları uygulayın.

Aşağıdaki iki görüntüde, veri kümesindeki bu adımlar gösterilmektedir.

**Diğer seçenekler (...)** öğesini ve sonra **Ayarlar**’ı seçin.

![Veri kümesi ayarlarını açma](media/service-security-apply-data-sensitivity-labels/apply-data-sensitivity-labels-05.png)

Ayarlar sayfasında duyarlılık etiketi bölümünü açın, istediğiniz duyarlılık etiketini seçin ve **Uygula**'ya tıklayın.

![Duyarlılık etiketi seçme](media/service-security-apply-data-sensitivity-labels/apply-data-sensitivity-labels-06.png)

## <a name="removing-sensitivity-labels"></a>Duyarlılık etiketlerini kaldırma
Rapor, pano, veri kümesi veya veri akışından duyarlılık etiketini kaldırmak için, [etiketleri uygulama işlemiyle aynı yordamı](#applying-sensitivity-labels) izleyin ama verilerin duyarlılığını sınıflandırmanız istendiğinde **(Hiçbiri)** öğesini seçin. 

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

Power BI'daki duyarlılık etiketi sınırlamaları için bkz. [Power BI'daki duyarlılık etiketleri](service-security-sensitivity-label-overview.md#limitations).

## <a name="next-steps"></a>Sonraki adımlar

Bu makalede, Power BI'da duyarlılık etiketlerini uygulama işlemi açıklanmıştır. Aşağıdaki makalelerde Power BI’da veri koruma hakkında daha fazla bilgi verilmektedir. 

* [Power BI'daki duyarlılık etiketlerine genel bakış](./service-security-sensitivity-label-overview.md)
* [Power BI’da duyarlılık etiketlerini etkinleştirme](./service-security-enable-data-sensitivity-labels.md)
* [Power BI’da Microsoft Cloud App Security denetimlerini kullanma](./service-security-using-microsoft-cloud-app-security-controls.md)