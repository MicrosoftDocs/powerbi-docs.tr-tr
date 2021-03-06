---
title: Power BI’da duyarlılık etiketlerini etkinleştirme
description: Power BI'da duyarlılık etiketlerini etkinleştirme hakkında bilgi edinin
author: paulinbar
ms.author: painbar
ms.service: powerbi
ms.subservice: powerbi-eim
ms.topic: how-to
ms.date: 12/09/2020
LocalizationGroup: Data from files
ms.openlocfilehash: 1732c1b6b8b748c4f3a820b31c4e4fe050a66fcd
ms.sourcegitcommit: b472236df99b490db30f0168bd7284ae6e6095fb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/16/2020
ms.locfileid: "97600335"
---
# <a name="enable-sensitivity-labels-in-power-bi"></a>Power BI’da duyarlılık etiketlerini etkinleştirme

[Microsoft Information Protection duyarlılık etiketlerinin](/microsoft-365/compliance/sensitivity-labels) Power BI’da kullanılabilmesi için kiracıda etkinleştirilmeleri gerekir. Bu makalede, Power BI yöneticilerinin bunu nasıl yapacağı gösterilmektedir. Power BI’daki duyarlılık etiketleri hakkında genel bakış için bkz. [Power BI'daki duyarlılık etiketleri](service-security-sensitivity-label-overview.md). Power BI’da duyarlılık etiketlerini uygulama hakkında bilgi için bkz. [Duyarlılık etiketleri uygulama](./service-security-apply-data-sensitivity-labels.md) 

Duyarlılık etiketleri etkinleştirildiğinde:

* Kuruluştaki belirli kullanıcılar ve güvenlik grupları Power BI içeriğine [duyarlılık etiketleri uygulayabilir](./service-security-apply-data-sensitivity-labels.md) ve bu etiketleri sınıflandırabilir. Power BI hizmetinde bu, raporları, panoları, veri kümeleri ve veri akışları anlamına gelir. Power BI Desktop'ta .pbix dosyaları anlamına gelir.
* Hizmette, kuruluşun tüm üyeleri söz konusu etiketleri görebilir. Desktop'ta, kuruluşun yalnızca etiketlerin yayımlandığı üyeleri bu etiketleri görebilir.

Duyarlılık etiketlerinin etkinleştirilmesi için Azure Information Protection lisansı gerekir. Ayrıntılar için bkz. [Lisanslama ve gereksinimler](#licensing-and-requirements).

>[!NOTE]
>Kullanıcılar Bilgi Koruması önizleme özelliğini kabul ettikten sonraki ilk 48 saat boyunca **duyarlılık etiketlerinin uygulandığı .pbix dosyalarında sorunlarla karşılaşabilir (örneğin .pbix dosyasını hizmete yayımlarken, hizmetten .pbix dosyasını indirirken)** . Bunlar beklenen sorunlardır ve 48 saat içinde otomatik olarak çözülür.

## <a name="licensing-and-requirements"></a>Lisanslama ve gereksinimler

* Power BI’da Microsoft Information Protection duyarlılık etiketlerini uygulamak veya görüntülemek için bir Azure Information Protection Premium P1 veya Premium P2 lisansı gerekir. Azure Information Protection tek başına ya da Microsoft lisanslama paketlerinden biri aracılığıyla satın alınabilir. Ayrıntılı bilgi için [Azure Information Protection fiyatlandırmasına](https://azure.microsoft.com/pricing/details/information-protection/) bakın.

    >[!NOTE]
    > Kuruluşunuz Azure Information Protection duyarlılık etiketlerini kullanıyorsa bunların Power BI’da kullanılabilmesi için Microsoft Information Protection Birleşik Etiketleme platformuna geçirilmesi gerekir. [Duyarlılık etiketlerini geçirme hakkında daha fazla bilgi edinin](/azure/information-protection/configure-policy-migrate-labels).

* Kullanıcının, Power BI içeriğine ve dosyalarına etiket uygulayabilmek için yukarıda bahsedilen Azure Information Protection lisanslarından birine ek olarak Power BI Pro lisansına sahip olması gerekir.

* Office uygulamalarının [duyarlılık etiketlerini görüntülemeye ve uygulamaya yönelik kendi lisanslama gereksinimleri]( https://docs.microsoft.com/microsoft-365/compliance/get-started-with-sensitivity-labels#subscription-and-licensing-requirements-for-sensitivity-labels ) vardır.

* Kiracınızda duyarlılık etiketlerini etkinleştirmeden önce, ilgili kullanıcılar ve gruplar için duyarlılık etiketlerinin tanımlandığından ve yayımlandığından emin olun. Ayrıntılar için bkz. [Duyarlılık etiketlerini ve ilkelerini oluşturma ve yapılandırma](/microsoft-365/compliance/create-sensitivity-labels).

* Desktop'ta duyarlılık etiketlerini kullanabilmek için Desktop Aralık 2020 ve sonraki sürümleri gerekir.

    >[!NOTE]
    > Korumalı bir .pbix dosyasını Aralık 2020'den önceki bir Desktop sürümüyle açmayı denerseniz, işlem başarısız olur ve Desktop sürümünüzü yükseltmeniz istenir.

## <a name="enable-sensitivity-labels"></a>Duyarlılık etiketlerini etkinleştirme

Duyarlılık etiketlerinin hem hizmette hem de Desktop'ta kullanılabilmesi için önce kiracıda etkinleştirilmesi gerekir. Bu bölümde etiketlerin kiracı ayarlarında nasıl etkinleştirileceği açıklanır. Desktop ile ilgili diğer önemli noktalar için aşağıdaki [Duyarlılık etiketlerini kuruluşunuz genelinde Desktop'ta devre dışı bırakma](#disable-sensitivity-labels-in-desktop-across-your-org) bölümüne bakın. 

Kiracıda duyarlılık etiketlerini etkinleştirmek için Power BI **Yönetici portalına** gidin, **Kiracı ayarları** bölmesini açın ve **Bilgi koruma** bölümünü bulun.

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

## <a name="disable-sensitivity-labels-in-desktop-across-your-org"></a>Duyarlılık etiketlerini kuruluşunuz genelinde Desktop'ta devre dışı bırakma

.Pbix dosyalarının duyarlılık etiketleriyle **çalışmadığından** emin olmak istiyorsanız, Power BI yöneticisi tarafından Power BI'ın kullanıcıların .pbix dosyalarını sınıflandırmasını ve korumasını veya zaten koruma uygulanmış olan dosyaları açmasını engellemesine neden olacak bir grup ilkesi oluşturulabilir. Böyle bir ilke oluşturmak için:

1. [Kayıt Defteri Düzenleyicisi](https://support.microsoft.com/windows/how-to-open-registry-editor-in-windows-10-deab38e6-91d6-e0aa-4b7c-8878d9e07b11)'ni açın.

1. **HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Microsoft Power BI Desktop** anahtarını bulun.

1. valueName **EnableInformationProtection** öğesini bulun ve **false** olarak ayarlayın.

Power BI Desktop'ta duyarlılık etiketlerini kullanmayla ilgili diğer sınırlamalar ve önemli noktalar için bkz. [Duyarlılık etiketine genel bakış](./service-security-sensitivity-label-overview.md#limitations).

## <a name="troubleshooting"></a>Sorun giderme

Power BI, Microsoft Information Protection duyarlılık etiketlerini kullanır. Bu nedenle, duyarlılık etiketlerini etkinleştirmeye çalışırken bir hata iletisiyle karşılaşırsanız bunun nedeni aşağıdakilerden biri olabilir:

* Azure Information Protection [lisansınız](#licensing-and-requirements) yoktur.
* Duyarlılık etiketleri, Power BI tarafından desteklenen Microsoft Information Protection sürümüne [geçirilmemiştir](#enable-sensitivity-labels).
* Kuruluşta Microsoft Information Protection [duyarlılık etiketi tanımlanmamıştır](#enable-sensitivity-labels).

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

Power BI'daki duyarlılık etiketi sınırlamaları için bkz. [Power BI'daki duyarlılık etiketleri](service-security-sensitivity-label-overview.md#limitations).

## <a name="next-steps"></a>Sonraki adımlar

Bu makalede, Power BI'da duyarlılık etiketlerini etkinleştirme işlemi açıklanmıştır. Aşağıdaki makalelerde Power BI’da veri koruma hakkında daha fazla bilgi verilmektedir. 

* [Power BI'daki duyarlılık etiketlerine genel bakış](service-security-sensitivity-label-overview.md)
* [Power BI'da duyarlılık etiketlerini uygulama](./service-security-apply-data-sensitivity-labels.md)
* [Power BI’da Microsoft Cloud App Security denetimlerini kullanma](service-security-using-microsoft-cloud-app-security-controls.md)
* [Koruma ölçümleri raporu](service-security-data-protection-metrics-report.md)