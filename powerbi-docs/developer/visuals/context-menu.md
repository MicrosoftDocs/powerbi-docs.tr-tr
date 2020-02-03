---
title: Power BI görsellerinin yetenekleri ve özellikleri
description: Bu makalede Power BI görsellerinin yetenekleri ve özellikleri açıklanır.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
manager: rkarlin
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 7d24ea77fd73ca6a83176d1b8560c88fa98a8d6b
ms.sourcegitcommit: 0cc594ebb78a6d0e88784673ed09f8aefd10c7a7
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76819204"
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
