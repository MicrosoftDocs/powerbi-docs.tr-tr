---
title: Power BI görselleri için sıralama seçenekleri
description: Bu makalede Power BI görselleri için varsayılan sıralama davranışı açıklanır.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 546480ae863c63d6517fde7c98e7c9787c022ab6
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73875535"
---
# <a name="sorting-options-for-power-bi-visuals"></a>Power BI görselleri için sıralama seçenekleri

Bu makalede *sıralama* seçeneklerinin Power BI görselleri için sıralama davranışını nasıl belirttiği açıklanır. 

Sıralama özelliği aşağıdaki parametrelerden birini gerektirir.

## <a name="default-sorting"></a>Varsayılan sıralama

`default` seçeneği en basit formdur. ‘DataMappings’ bölümünde sunulan verileri sıralama olanağı tanır. Seçenek veri eşlemelerinin kullanıcı tarafından sıralanmasını etkinleştirir ve sıralama yönünü belirtir.

```json
    "sorting": {
        "default": {   }
    }
```

![Bağlam menüsündeki sıralama seçenekleri](./media/sorting.png)

## <a name="implicit-sorting"></a>Örtük sıralama

Örtük sıralama, her veri rolü için sıralamayı tanımlayan `clauses` dizi parametresiyle sıralama işlemidir. `implicit`, görselin kullanıcısının sıralama düzenini değiştiremeyeceği anlamına gelir. Power BI sıralama seçeneklerini görselin menüsünde göstermez. Öte yandan Power BI verileri belirtilen ayarlara göre sıralar.

`clauses` parametreleri iki parametre ile birkaç nesne içerebilir:

- `role` Sıralama için `DataMapping` nesnesini belirler
- `direction` Sıralama yönünü belirler (1 = Artan, 2 = Azalan)

```json
    "sorting": {
        "implicit": {
            "clauses": [
                {
                    "role": "category",
                    "direction": 1
                },
                {
                    "role": "measure",
                    "direction": 2
                }
            ]
        }
    }
```

## <a name="custom-sorting"></a>Özel sıralama

Özel sıralama, sıralamanın geliştirici tarafından görselin kodunda yönetildiği anlamına gelir.
