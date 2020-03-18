---
title: Power BI görsellerinize giriş sayfası ekleme
description: Bu makalede Power BI görsellerine giriş sayfası ekleme işlemi açıklanır.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 06/18/2019
ms.openlocfilehash: 6f1590d5635ed6e55833350027c52379e5d7cf51
ms.sourcegitcommit: 6bbc3d0073ca605c50911c162dc9f58926db7b66
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79379984"
---
# <a name="add-a-landing-page-to-your-power-bi-visuals"></a>Power BI görsellerinize giriş sayfası ekleme

API 2.3.0 ile Power BI görsellerinize giriş sayfası ekleyebilirsiniz. Bunu yapmak için özelliklere `supportsLandingPage` ekleyin ve True olarak ayarlayın. Bu eylem görselinize veri eklemeden önce görseli başlatır ve güncelleştirir. Görsel artık filigran göstermediğinden, veri içermediği sürece görselde görüntülemek üzere kendi giriş sayfanızı tasarlayabilirsiniz.

```typescript
export class BarChart implements IVisual {
    //...
    private element: HTMLElement;
    private isLandingPageOn: boolean;
    private LandingPageRemoved: boolean;
    private LandingPage: d3.Selection<any>;

    constructor(options: VisualConstructorOptions) {
            //...
            this.element = options.element;
            //...
    }

    public update(options: VisualUpdateOptions) {
    //...
        this.HandleLandingPage(options);
    }

    private HandleLandingPage(options: VisualUpdateOptions) {
        if(!options.dataViews || !options.dataViews.length) {
            if(!this.isLandingPageOn) {
                this.isLandingPageOn = true;
                const SampleLandingPage: Element = this.createSampleLandingPage(); //create a landing page
                this.element.appendChild(SampleLandingPage);
                this.LandingPage = d3.select(SampleLandingPage);
            }

        } else {
                if(this.isLandingPageOn && !this.LandingPageRemoved){
                    this.LandingPageRemoved = true;
                    this.LandingPage.remove();
                }
        }
    }
```

Aşağıdaki resimde örnek bir giriş sayfası gösterilir:

![giriş sayfası ekran görüntüsü](media/landing-page/app-landing-page.png)
