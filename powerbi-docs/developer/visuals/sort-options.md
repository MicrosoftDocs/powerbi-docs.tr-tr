---
title: Sırala
description: Power BI Görselleri için varsayılan sıralama davranışı.
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: f3d913e2bce34850dfae4c9486b2e43c78521a58
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2019
ms.locfileid: "68424528"
---
# <a name="sorting-options"></a>Sıralama seçenekleri

`Sorting`, görsel için varsayılan sıralama davranışını belirtir.
Özellik, aşağıda açıklanan parametrelerin birini gerektirir:

## <a name="default-sorting"></a>Varsayılan sıralama

`default` seçeneği en basit formdur. ‘DataMappings’ bölümünde sunulan verileri sıralama olanağı tanır.
Bu seçenek, kullanıcının ‘DataMappings’i’ sıralamasına ve sıralama yönünü belirtmesine olanak tanır.

```json
    "sorting": {
        "default": {   }
    }
```

![Bağlam menüsündeki sıralama seçenekleri](./media/sorting.png)

## <a name="implicit-sorting"></a>Örtük sıralama

`implicit`, dizi parametresiyle sıralamadır - `clauses` ise her veri rolü için sıralamayı açıklar.
`implicit`, görselin kullanıcısının sıralama düzenini değiştiremeyeceği anlamına gelir.
Power BI, sıralama seçeneklerini görselin menüsünde göstermez. Ancak Power BI, verileri belirtilen ayarlara göre sıralayacak.

`clauses` parametreleri, iki parametre ile birkaç nesne içerebilir:

- `role`, sıralama için `DataMapping` nesnesini belirler.

- `direction` sıralama yönünü belirler (1 = Artan, 2 = Azalan).

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

`custom`, sıralamanın geliştirici tarafından görselin kodunda yönetildiği anlamına gelir.
