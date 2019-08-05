---
title: Analiz bölmesi
description: Power BI Görselleri’nde dinamik başvuru çizgileri oluşturma
author: Guy-Moses
ms.author: guymos
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: b3b50f8dbcf40a3923e86422e24f8ed020894445
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425540"
---
# <a name="analytics-pane-in-power-bi-visuals"></a>Power BI Görselleri’nde Analiz bölmesi

**Analiz bölmesi**, Kasım 2018’de [yerel görseller için sunuldu](https://docs.microsoft.com/power-bi/desktop-analytics-pane).
API v2.5.0 sürümüne sahip özel görseller, özelliklerini **Analiz bölmesinde** sunup yönetebilir.

![Analiz Bölmesi](./media/visualization-pane-analytics-tab.png)

Görselin capabilities.json dosyasında bir nesne tanımlayarak, [Biçim bölmesinin yönetim özelliklerine](https://docs.microsoft.com/power-bi/developer/custom-visual-develop-tutorial-format-options) benzer bir şekilde işlenir. 

Farklar şunlardır:

1. `object` öğesinin tanımının altında 2 değerine sahip bir `objectCategory` alanı ekleyin.

    > [!NOTE]
    > `objectCategory` alanı, API 2.5.0’da getirilen bir isteğe bağlı alandır. Nesnenin denetlediği görselin görünüşünü tanımlar (1 = Biçimlendirme, 2 = Analiz). "Biçimlendirme", görünüm, kullanım, renkler, eksenler, etiketler vb. için kullanılır. “Analiz”, tahminler, eğilim çizgileri, başvuru çizgileri, şekiller ve benzerleri için kullanılır.
    >
    > Atlanırsa, `objectCategory` öğesi varsayılan olarak “Biçimlendirmeyi” alır.

2. Nesnenin aşağıdaki iki özelliği olmalıdır:
    1. Varsayılan değeri false olan, bool türünde `show`.
    2. Metin türünde `displayName`. Seçeceğiniz varsayılan değer örneğin ilk görünen adı olur.

```json
{
  "objects": {
    "YourAnalyticsPropertiesCard": {
      "displayName": "Your analytics properties card's name",
      "objectCategory": 2,
      "properties": {
        "show": {
          "type": {
            "bool": true
          }
        },
        "displayName": {
          "type": {
            "text": true
          }
        },
      ... //any other properties for your Analytics card
      }
    }
  ...
  }
}
```

Diğer tüm özellikler, Biçim nesneleri için yapıldığı gibi tanımlanabilir. Nesne numaralandırması, tıpkı **Biçim bölmesinde** olduğu gibi yapılır.

***Bilinen sınırlamalar ve sorunlar***

  1. Henüz çoklu örnek desteği yok. Nesnelerin statik dışında farklı bir [seçicisi](https://microsoft.github.io/PowerBI-visuals/docs/concepts/objects-and-properties/#selector) olamaz (bu da “seçici”: null olur) ve özel görsellerin bir kartın kullanıcı tanımlı birden fazla örneği bulunamaz.
  2. `integer` türünün özellikleri doğru şekilde görüntülenmiyor. Bunun yerine, geçici bir çözüm olarak `numeric` türünü kullanın.

> [!NOTE]
> Analiz bölmesini sadece yeni bilgiler ekleyen veya sunulan bilgilere farklı bir bakış açısı getiren nesneler için kullanın. Örneğin, önemli eğilimleri gösteren dinamik başvuru çizgileri.
> Görselin görünüm ve kullanımını denetleyen tüm seçenekler (biçimlendirme) Biçimlendirme bölmesinde tutulmalıdır.
