---
title: Power BI görsellerinin yetenekleri ve özellikleri
description: Bu makalede Power BI görsellerinin yetenekleri ve özellikleri açıklanır.
author: asander
ms.author: asander
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 206f1aec7c76b00b6f725d8469eb3e483a01c653
ms.sourcegitcommit: f7b28ecbad3e51f410eff7ee4051de3652e360e8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74061788"
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
