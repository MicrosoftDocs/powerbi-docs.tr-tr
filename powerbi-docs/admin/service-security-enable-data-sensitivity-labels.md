---
title: Power BI’da duyarlılık etiketlerini etkinleştirme
description: Power BI'da duyarlılık etiketlerini etkinleştirme hakkında bilgi edinin
author: paulinbar
ms.service: powerbi
ms.subservice: powerbi-eim
ms.topic: how-to
ms.date: 07/06/2020
ms.author: painbar
LocalizationGroup: Data from files
ms.openlocfilehash: 0fe1b7b1b8175511838005b7b63ca7543bbf939a
ms.sourcegitcommit: 181679a50c9d7f7faebcca3a3fc55461f594d9e7
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/07/2020
ms.locfileid: "86034348"
---
# <a name="enable-sensitivity-labels-in-power-bi"></a>Power BI’da duyarlılık etiketlerini etkinleştirme

[Microsoft Information Protection duyarlılık etiketlerinin](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) Power BI’da kullanılabilmesi için kiracıda etkinleştirilmeleri gerekir. Bu makalede, Power BI kiracı yöneticilerinin bunu nasıl yapılacağı gösterilmektedir. Power BI’daki duyarlılık etiketleri hakkında genel bakış için bkz. [Power BI'daki duyarlılık etiketleri](service-security-sensitivity-label-overview.md). Power BI’da duyarlılık etiketlerini uygulama hakkında bilgi için bkz. [Duyarlılık etiketleri uygulama](./service-security-apply-data-sensitivity-labels.md) 

Duyarlılık etiketleri etkinleştirildiğinde:

* Kuruluştaki belirli kullanıcılar ve güvenlik grupları Power BI rapor, pano, veri kümesi ve veri akışlarına [duyarlılık etiketleri uygulayabilir](./service-security-apply-data-sensitivity-labels.md) ve bu etiketleri sınıflandırabilir.
* Kuruluşun tüm üyeleri bu etiketleri görebilir.

Duyarlılık etiketlerinin etkinleştirilmesi için Azure Information Protection lisansı gerekir. Ayrıntılar için bkz. [Lisanslama](service-security-sensitivity-label-overview.md#licensing).

## <a name="enable-sensitivity-labels"></a>Duyarlılık etiketlerini etkinleştirme

Power BI **Yönetici portalına** gidin, **Kiracı ayarları** bölmesini açın ve **Bilgi koruma** bölümünü bulun.

![Information Protection bölümünü bulma](media/service-security-enable-data-sensitivity-labels/enable-data-sensitivity-labels-01.png)

**Information Protection** bölümünde aşağıdaki adımları uygulayın:
1. **Kullanıcıların Power BI içeriği için duyarlılık etiketleri uygulamasına izin ver**’i açın.
1. Düğmeyi etkinleştirin.
1. Power BI varlıklarında duyarlılık etiketlerini kimlerin uygulayabileceğini ve değiştirebileceğini tanımlayın. Varsayılan olarak, kuruluşunuzdaki herkes duyarlılık etiketlerini uygulayabilecektir. Bununla birlikte, yalnızca belirli kullanıcılar veya güvenlik grupları için duyarlılık etiketlerini etkinleştirmeyi seçebilirsiniz. Tüm kuruluş veya belirli güvenlik grupları seçili olduğunda, belirli kullanıcı alt kümelerini veya güvenlik gruplarını hariç bırakabilirsiniz.
   
   * Kuruluş genelinde duyarlılık etiketleri etkinleştirildiğinde, özel durumlar genellikle güvenlik gruplarıdır.
   * Duyarlılık etiketleri yalnızca belirli kullanıcılar veya güvenlik grupları için etkinleştirildiğinde, özel durumlar genellikle belirli kullanıcılardır.  
    Bu yaklaşım, duyarlılık etiketleri uygulama izinlerine sahip bir gruba ait olsalar bile belirli kullanıcıların Power BI’da duyarlılık etiketi uygulamasını önlemeyi mümkün hale getirir.

1. **Uygula** düğmesine basın.

![Duyarlılık etiketlerini etkinleştirme](media/service-security-enable-data-sensitivity-labels/enable-data-sensitivity-labels-02.png)

> [!IMPORTANT]
> Yalnızca varlık üzerinde *oluştur* ve *düzenle* izinlerine sahip olan ve bu bölümde ayarlanmış ilgili güvenlik grubuna dahil olan Power BI Pro kullanıcıları, duyarlılık etiketlerini ayarlayabilir ve düzenleyebilir. Bu gruba dahil olmayan kullanıcılar etiketleri ayarlayamaz veya düzenleyemez.  

## <a name="troubleshooting"></a>Sorun giderme

Power BI, Microsoft Information Protection duyarlılık etiketlerini kullanır. Bu nedenle, duyarlılık etiketlerini etkinleştirmeye çalışırken bir hata iletisiyle karşılaşırsanız bunun nedeni aşağıdakilerden biri olabilir:

* Azure Information Protection [lisansınız](service-security-sensitivity-label-overview.md#licensing) yoktur.
* Duyarlılık etiketleri, Power BI tarafından desteklenen Microsoft Information Protection sürümüne geçirilmemiştir. [Duyarlılık etiketlerini geçirme](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels) hakkında daha fazla bilgi edinin.
* Kuruluşta hiçbir Microsoft Information Protection duyarlılık etiketi tanımlanmamıştır. Etiketin kullanılabilir olması için etiketin yayımlanmış bir ilkenin parçası olması gerektiğini unutmayın. [Duyarlılık etiketleri hakkında daha fazla bilgi edinin](https://docs.microsoft.com/Office365/SecurityCompliance/sensitivity-labels) veya [Microsoft güvenlik ve uyumluluk merkezini](https://sip.protection.office.com/sensitivity?flight=EnableMIPLabels) ziyaret ederek etiketleri tanımlama ve kuruluşunuz için ilkeler yayımlama hakkında bilgi edinin.

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

Power BI'daki duyarlılık etiketi sınırlamaları için bkz. [Power BI'daki duyarlılık etiketleri](service-security-sensitivity-label-overview.md#limitations).

## <a name="next-steps"></a>Sonraki adımlar

Bu makalede, Power BI'da duyarlılık etiketlerini etkinleştirme işlemi açıklanmıştır. Aşağıdaki makalelerde Power BI’da veri koruma hakkında daha fazla bilgi verilmektedir. 

* [Power BI'daki duyarlılık etiketlerine genel bakış](service-security-sensitivity-label-overview.md)
* [Power BI'da duyarlılık etiketlerini uygulama](../collaborate-share/service-security-apply-data-sensitivity-labels.md)
* [Power BI’da Microsoft Cloud App Security denetimlerini kullanma](service-security-using-microsoft-cloud-app-security-controls.md)
* [Koruma ölçümleri raporu](service-security-data-protection-metrics-report.md)