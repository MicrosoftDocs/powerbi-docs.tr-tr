---
title: Power BI görsellerinde gelişmiş düzenleme modu
description: Bu makalede Power BI görsellerine gelişmiş kullanıcı arabirimi denetimleri ayarlama işlemi açıklanır.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 19714db2d1307ac9d7eb8861955870ba9988539e
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73880316"
---
# <a name="advanced-edit-mode-in-power-bi-visuals"></a>Power BI görsellerinde gelişmiş düzenleme modu

Power BI görselinizde gelişmiş kullanıcı arabirimi denetimlerine ihtiyacınız varsa, gelişmiş düzenleme modundan yararlanabilirsiniz. Rapor düzenleme modundayken **Düzenle** düğmesini seçerek düzenleme modunu **Gelişmiş** olarak ayarlayabilirsiniz. Görsel bu kullanıcı arabirimi düğmesini görüntüleyip görüntülemeyeceğini belirlemek için `EditMode` bayrağını kullanabilir.

Varsayılan olarak, görseller gelişmiş düzenleme modunu desteklemez. Farklı bir davranış gerekirse, `advancedEditModeSupport` özelliği ayarlanarak görselin *capabilities.json* dosyasında bunu açıkça belirtmelisiniz.

Olası değerler şunlardır:

- `0` - NotSupported

- `1` - SupportedNoAction

- `2` - SupportedInFocus

## <a name="enter-advanced-edit-mode"></a>Gelişmiş düzenleme moduna girme

Aşağıdaki durumlarda **Düzenle** düğmesi görüntülenir:

* *Capabilities.json* dosyasında `advancedEditModeSupport` özelliği `SupportedNoAction` veya `SupportedInFocus` olarak ayarlanmıştır.

* Görsel rapor düzenlemesi modunda görüntüleniyordur.

*Capabilities.json* dosyasında `advancedEditModeSupport` özelliği yoksa veya `NotSupported` olarak ayarlanmışsa, **Düzenle** düğmesi görüntülenmez.

![Düzenleme moduna girme](./media/edit-mode.png)

**Düzenle**’yi seçtiğinizde görsel EditMode öğesinin `Advanced` olarak ayarlandığı bir update() çağrısı alır. *Capabilities.json* dosyasında ayarlanan değere bağlı olarak aşağıdaki eylemler gerçekleşir:

* `SupportedNoAction` Konak için başka eylem gerekmez.
* `SupportedInFocus` Konak görseli odak moduna geçirir.

## <a name="exit-advanced-edit-mode"></a>Gelişmiş düzenleme modundan çıkma

Aşağıdaki durumlarda **Rapora geri dön** düğmesi görüntülenir:

* *Capabilities.json* dosyasında `advancedEditModeSupport` özelliği `SupportedInFocus` olarak ayarlanmıştır.
