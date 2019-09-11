---
title: Power BI görsellerinize giriş sayfası ekleme
description: Bu makalede Power BI görsellerine giriş sayfası ekleme işlemi açıklanır.
author: sranins
ms.author: rasala
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: d15c52134fe3c8638625e50a1374867a4abed3c1
ms.sourcegitcommit: b602cdffa80653bc24123726d1d7f1afbd93d77c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70236701"
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

![giriş sayfası ekran görüntüsü](./media/landing-page.png)
