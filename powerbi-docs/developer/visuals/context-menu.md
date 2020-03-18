---
title: Power BI görsellerinin yetenekleri ve özellikleri
description: Bu makalede Power BI görsellerinin yetenekleri ve özellikleri açıklanır.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
manager: rkarlin
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: how-to
ms.date: 06/18/2019
ms.openlocfilehash: 1e2fbe3288e5dbb759a56ad1c299db2e277408b2
ms.sourcegitcommit: 6bbc3d0073ca605c50911c162dc9f58926db7b66
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79380767"
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
