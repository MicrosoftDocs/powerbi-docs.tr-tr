---
title: İçerik onayını etkinleştirme
description: Veri kümeleri, veri akışları, raporlar ve uygulamalar için onayı nasıl etkinleştireceğinizi öğrenin.
author: paulinbar
ms.author: painbar
ms.service: powerbi
ms.subservice: powerbi-eim
ms.topic: how-to
ms.date: 10/26/2020
LocalizationGroup: Share your work
ms.openlocfilehash: 17fc02131f13fe7fe7d8fb17af4380f6a013b9e7
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96413530"
---
# <a name="enable-content-certification"></a>İçerik onayını etkinleştirme

Kuruluşunuz, kritik bilgiler için seçilen içeriği yetkili kaynak olarak onaylayabilir. Şu an için aşağıdaki içerik türleri onaylanabilir:
* Veri kümeleri
* Veri akışları (önizleme)
* Raporlar (önizleme)
* Uygulamalar (önizleme)

Power BI yöneticisi olarak kuruluşunuzda onaylama işlemini etkinleştirmek ve ayarlamak sizin sorumluluğunuzdadır. Diğer bir deyişle:
* Kiracınızda onaylamayı etkinleştirirsiniz.
* Üyeleri içerik onaylama yetkisine sahip olacak güvenlik gruplarının listesini tanımlarsınız.
* Kuruluşun içerik onaylama süreciyle ilgili belgelere giden (bu tür belgeler varsa) bir URL sağlarsınız.

Bu işlev, Power BI'ın *onay* özelliğinin bir parçasıdır. Daha fazla bilgi için bkz. [Onay: Power BI içeriklerini yükseltme ve onaylama](../collaborate-share/service-endorsement-overview.md).

## <a name="set-up-certification"></a>Onaylamayı ayarlama

1. Yönetim portalında Kiracı ayarlarına gidin.
1. Dışarı aktarma ve paylaşım ayarları bölümünde Onaylama bölümünü genişletin.

   ![Veri kümesi ve veri akışı sertifikası ayarlama](media/service-admin-setup-certification/service-admin-certification-setup-dialog.png)

1. İki durumlu düğmeyi **Etkinleştirildi** olarak ayarlayın.
1. Kuruluşunuz onaylama ilkesi yayımladıysa burada ilkenin URL’sini sağlayın. Bu URL [onay ayarları iletişim kutusunun](../collaborate-share/service-endorse-content.md#request-content-certification) onaylama bölümünde **Daha fazla bilgi edinin** bağlantısına dönüşür. Burada bir bağlantı sağlamazsanız içeriklerinin onaylanmasını isteyen kullanıcılara Power BI yöneticileriyle iletişime geçmeleri önerilir.
1. Üyeleri içerik onaylama yetkisine sahip olacak bir veya daha fazla güvenlik grubu belirtin. Bu yetkili onaylayıcılar [onay ayarları iletişim kutusunun](../collaborate-share/service-endorse-content.md#certify-content) onaylama bölümündeki Onaylama düğmesini kullanabilir.
    
    Bir güvenlik grubunun altında onay yetkisi vermek istemediğiniz güvenlik grupları varsa **Belirli güvenlik grupları hariç** kutusunu işaretleyip açılan kutuya ilgili grupların adını girebilirsiniz.
1. **Uygula**'ya tıklayın.

## <a name="next-steps"></a>Sonraki adımlar
* [İçerikleri yükseltme veya onaylama](../collaborate-share/service-endorse-content.md)
* [Power BI onay hakkında bilgi edinin](../collaborate-share/service-endorsement-overview.md)
* Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
