---
title: Power BI görselleri için sıralama seçenekleri
description: Bu makalede Power BI görselleri için varsayılan sıralama davranışı açıklanır.
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: cecec80dc9fe8570535cbd1e0c1e7114363472d8
ms.sourcegitcommit: b602cdffa80653bc24123726d1d7f1afbd93d77c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70236673"
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

- `role`: Sıralama için `DataMapping` nesnesini belirler
- `direction`: Sıralama yönünü belirler (1 = Artan, 2 = Azalan)

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
