---
title: Giriş sayfası
description: Power BI Görselleri’ne giriş sayfası ekleme
author: sranins
ms.author: rasala
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 44cc9314b31803c97d3203d4aab846685d8f88fa
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2019
ms.locfileid: "68424896"
---
# <a name="landing-page"></a>Giriş sayfası

API 2.3.0 ile, görselinize bir giriş sayfası ekleyebilirsiniz. Bunu yapmak için, özelliklere `supportsLandingPage` öğesini ekleyip bunu true olarak ayarlayın. Bu, görselinizin veri eklenmeden başlatılıp güncelleştirilmesini sağlar (artık filigran göstermeyeceği anlamına gelir). Böylelikle, içinde veri olmadıkça görselde gösterebileceğiniz kendi giriş sayfanızı tasarlayabilirsiniz.

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

Örnek

![giriş sayfası ekran görüntüsü](./media/landing-page.png)
