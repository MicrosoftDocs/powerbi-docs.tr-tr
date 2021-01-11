---
title: Daha iyi tümleşik BI içgörüleri için, Power BI tümleşik analizlerinde Power BI görselleri için sıralama seçenekleri
description: Bu makalede Power BI görselleri için varsayılan sıralama davranışı açıklanır. Power BI tümleşik analiz kullanarak daha iyi tümleşik BI içgörüleri elde edin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 06/18/2019
ms.openlocfilehash: 0d24719b486608c283ec73f0188092a1ece3155e
ms.sourcegitcommit: eeaf607e7c1d89ef7312421731e1729ddce5a5cc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2021
ms.locfileid: "97889260"
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

![Bağlam menüsündeki sıralama seçenekleri](media/sort-options/sorting.png)

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
