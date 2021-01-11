---
title: Daha iyi tümleşik BI içgörüleri için, Power BI tümleşik analizlerinde Power BI görsellerine dış kitaplıklar ekleme
description: Bu makalede Power BI görsellerinde dış kitaplıkların nasıl kullanılacağı açıklanır. Power BI tümleşik analiz kullanarak daha iyi tümleşik BI içgörüleri elde edin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 02/24/2020
ms.openlocfilehash: b9a443040384e4d38bd7440eae0a5582cc422836
ms.sourcegitcommit: eeaf607e7c1d89ef7312421731e1729ddce5a5cc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2021
ms.locfileid: "97889191"
---
# <a name="adding-external-libraries"></a>Dış kitaplıklar ekleme

Bu makalede Power BI görsellerinde dış kitaplıkların nasıl kullanılacağı açıklanır. Dış kitaplıkları yükleme, içeri aktarma ve Power BI görselinin kodunda bunları çağırma hakkında bilgi verilir.

## <a name="javascript-libraries"></a>JavaScript kitaplıkları

1. Dış JavaScript kitaplığını yüklemek için *npm* veya *yarn* gibi herhangi bir paket yöneticisini kullanın.
2. Dış kitaplığı kullanan kaynak dosyalara gerekli modülleri aktarın.

>[!NOTE]
>JavaScript kitaplığınıza yazım eklemek, IntelliSense ile derleme zamanı güvenliği almak isterseniz, uygun paketi yüklediğinizden emin olun.

### <a name="installing-the-d3-library"></a>d3 kitaplığını yükleme

Bu, [npm](https://www.npmjs.com/) kullanarak [d3 kitaplığını](https://www.npmjs.com/package/d3) ve [@types/d3](https://www.npmjs.com/package/@types/d3) paketini yükleme örneğidir.

Örneğin tamamı için [Power BI görselleştirmeleri](https://github.com/microsoft/powerbi-visuals-gantt/blob/master/src/gantt.ts#L29) koduna bakın.

1. *d3* paketini ve *d3 types* paketini yükleyin.

    ```powershell
    npm install d3@5 --save
    npm install @types/d3@5 --save
    ```

2. *d3* kitaplığını, bunu kullanan `visual.ts` gibi dosyalara aktarın.

    ```typescript
    import * as d3 from "d3";
    ```

## <a name="css-framework"></a>CSS çerçevesi

1. Dış CSS çerçevesini yüklemek için *npm* veya *yarn* gibi herhangi bir paket yöneticisini kullanın.
2. Görselin `.less` dosyasına `import` deyimini ekleyin.

### <a name="installing-bootstrap"></a>bootstrap yükleme

Bu, [npm](https://www.npmjs.com/) kullanarak [bootstrap ](https://www.npmjs.com/package/bootstrap) yükleme örneğidir.

Örneğin tamamı için [Power BI görselleştirmeleri](https://github.com/Microsoft/powerbi-visuals-sankey/blob/c8200da56913cd8b253be949a35fad0f4472b6de/style/visual.less#L32) koduna bakın.

1. *bootstrap* paketini yükleyin.

    ```powershell
    npm install bootstrap --save
    ```

2. `visual.less` dosyasına `import` deyimini ekleyin.

    ```less
    @import (less) "node_modules/bootstrap/dist/css/bootstrap.css";
    ```
