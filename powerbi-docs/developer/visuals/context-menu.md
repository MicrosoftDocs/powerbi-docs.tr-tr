---
title: Daha iyi tümleşik BI içgörüleri için, Power BI tümleşik analizlerinde Power BI Görseline bağlam menüsü ekleme
description: Power BI görseline bağlam menüsü eklemeyi öğrenin. Power BI tümleşik analiz kullanarak daha iyi tümleşik BI içgörüleri elde edin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
manager: rkarlin
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: how-to
ms.date: 06/18/2019
ms.openlocfilehash: 1c19ba94588628e002cdb9e65f59bd4182020e1c
ms.sourcegitcommit: eeaf607e7c1d89ef7312421731e1729ddce5a5cc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2021
ms.locfileid: "97888708"
---
# <a name="add-context-menu-to-power-bi-visual"></a>Power BI Görseline bağlam menüsü ekleme

Power BI'ın görselinizde bir bağlam menüsü görüntülemesini sağlamak için `selectionId` parametreleri ve bir konumla (`{x:, y:}` nesnesi olarak) `selectionManager.showContextMenu()` kullanabilirsiniz.

> [!IMPORTANT]
> `selectionManager.showContextMenu()`, Görseller API 2.2.0’da tanıtılmıştır.

Normalde bir sağ tıklama (veya dokunmatik cihazlarda uzun dokunma) olayı olarak eklenmiştir Başvuru için örnek BarChart'a Context-Menu eklenmiştir:

```typescript
    public update(options: VisualUpdateOptions) {
        //...
        //handle context menu
        this.svg.on('contextmenu', () => {
            const mouseEvent: MouseEvent = d3.event as MouseEvent;
            const eventTarget: EventTarget = mouseEvent.target;
            let dataPoint = d3.select(eventTarget).datum();
            this.selectionManager.showContextMenu(dataPoint? dataPoint.selectionId : {}, {
                x: mouseEvent.clientX,
                y: mouseEvent.clientY
            });
            mouseEvent.preventDefault();
        });
```
