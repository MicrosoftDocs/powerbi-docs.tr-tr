---
title: Gelişmiş Düzenleme Modu
description: Gelişmiş kullanıcı arabirimi denetimleriyle Power BI Görselleri
author: shaym83
ms.author: shaym
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 625105aed773bce5cf70932f092faf60ea001c2c
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425563"
---
# <a name="advanced-edit-mode"></a>Gelişmiş düzenleme modu

Gelişmiş kullanıcı arabirimi denetimleri gerektiren görseller, Gelişmiş Düzenleme Modu’na yönelik destek bildirebilir.
Destekleniyorsa, rapor düzenleme modundayken görselin menüsünde bir `Edit` düğmesi görüntülenir.
`Edit` düğmesine basıldığında EditMode `Advanced` olarak ayarlanır.
Görsel, bu kullanıcı arabirimi denetimlerinin görüntülenip görüntülenmeyeceğini belirlemek için EditMode bayrağını kullanabilir.

Varsayılan olarak, görsel Gelişmiş Düzenleme Modu’nu desteklemez.
Farklı bir davranış gerekirse, `advancedEditModeSupport` özelliği ayarlanarak görselin `capabilities.json` dosyasında bu açıkça belirtilmelidir.

Olası değerler şunlardır:

- 0 - NotSupported

- 1 - SupportedNoAction

- 2 - SupportedInFocus

## <a name="entering-advanced-edit-mode"></a>Gelişmiş Düzenleme Modu’na girme

`Edit` düğmesi şu durumlarda görünür:

 1- capabilities.json dosyasında `advancedEditModeSupport` özelliği `SupportedNoAction` veya `SupportedInFocus` olarak ayarlandıysa.

 2- Görsel rapor düzenleme modunda görüntüleniyorsa.

capabilities.json dosyasında `advancedEditModeSupport` özelliği eksikse veya bu `NotSupported` olarak ayarlandıysa, ‘Düzenleme’ düğmesi kaybolur.

![Düzenleme moduna girme](./media/edit-mode.png)

Kullanıcı `Edit` öğesine tıkladığında, görsel EditMode’un `Advanced` olarak ayarlı olduğu bir update() çağrısı alır.
Özelliklerde ayarlanan değere göre aşağıdaki eylemler gerçekleşir:

* `SupportedNoAction` - Ana bilgisayar tarafından başka eylem gerçekleştirilmez.
* `SupportedInFocus` - Ana bilgisayar, görseli odak modunda yeni pencerede açar.

## <a name="exiting-advanced-edit-mode"></a>Gelişmiş Düzenleme Modu’ndan Çıkma

`Back to report` düğmesi şu durumlarda görünür:

1- capabilities.json dosyasındaki `advancedEditModeSupport` özelliği `SupportedInFocus` olarak ayarlandıysa.
