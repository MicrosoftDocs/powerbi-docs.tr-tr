---
title: Yüksek Karşıtlıklı mod desteği
description: Power BI Görsellerine Yüksek Karşıtlıklı mod desteği ekleme
author: sranins
ms.author: rasala
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: cb77ea012fdfdbd5be62c58c6f9b94a0355db1a9
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2019
ms.locfileid: "68424942"
---
# <a name="high-contrast-mode-support"></a>Yüksek Karşıtlıklı mod desteği

Windows *Yüksek Karşıtlıklı* ayarı daha belirgin renkleri kullanarak metin ve uygulamaları daha kolay görünür hale getirir.
[Power BI’da yüksek karşıtlıklı desteği](https://powerbi.microsoft.com/blog/power-bi-desktop-june-2018-feature-summary/#highContrast) hakkında daha fazla bilgi edinin.

Görselinize yüksek karşıtlıklı desteği eklemek için şunlar gerekir:

1. Başlatırken: Power BI’ın yüksek karşıtlıklı modda olup olmadığını algılayın ve yüksek karşıtlıklı moddaysa, geçerli yüksek karşıtlık renklerini alın.
2. Her güncelleştirmede: Daha kolay görmeyi kolaylaştırmak için görselin nasıl işlediğini değiştirin.

PowerBI-visuals-sampleBarChart görselinde yüksek karşıtlıklı desteği uygulanmıştır.

Daha fazla bilgi için bkz. [PowerBI-visuals-sampleBarChart görsel deposu](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/61011c82b66ca0d3321868f1d089c65101ca42e6)

## <a name="on-init"></a>Başlatırken

`options.host` colorPalette üyesinin, yüksek karşıtlık modu için birkaç özelliği vardır. Yüksek karşıtlık modunun etkin olup olmadığını ve etkinse hangi renklerin kullanılacağını belirlemek için bu özellikleri kullanın.

### <a name="detect-that-power-bi-is-in-high-contrast-mode"></a>Power BI’ın yüksek karşıtlıklı modda olduğunu algılama

`host.colorPalette.isHighContrast` `true` ise, yüksek karşıtlık modu etkindir ve görselin kendisini buna uygun şekilde çizmesi gerekir.

### <a name="get-high-contrast-colors"></a>Yüksek karşıtlıklı renkler alın

Yüksek karşıtlık modunda, görseliniz kendisini aşağıdaki renklerle sınırlandırmalıdır:

* **Ön plan** rengi, tüm çizgileri, simgeleri, metinleri ve şekillerin ana hatları veya dolgusunu çizmek için kullanılır.
* **Arka plan** rengi, arka plan ve ana hatları belirlenmiş şekillerin dolgu rengi olarak kullanılır.
* **Ön plan - seçili** rengi seçili veya etkin bir öğeyi göstermek için kullanılır.
* **Köprü** rengi yalnızca köprü metni için kullanılır.

> [!NOTE]
> İkincil bir renk gerekliyse, ön plan rengi biraz opak olarak kullanılabilir (Power BI yerel görselleri % 40 opaklık kullanır). Görsel ayrıntıların kolayca görülmesini sağlamak için bunu seyrek bir şekilde kullanın.

Bu değerleri başlatma sırasında depolayabilirsiniz:

```typescript
private isHighContrast: boolean;

private foregroundColor: string;
private backgroundColor: string;
private foregroundSelectedColor: string;
private hyperlinkColor: string;
//...

constructor(options: VisualConstructorOptions) {
    this.host = options.host;
    let colorPalette: ISandboxExtendedColorPalette = host.colorPalette;
    //...
    this.isHighContrast = colorPalette.isHighContrast;
    if (this.isHighContrast) {
        this.foregroundColor = colorPalette.foreground.value;
        this.backgroundColor = colorPalette.background.value;
        this.foregroundSelectedColor = colorPalette.foregroundSelected.value;
        this.hyperlinkColor = colorPalette.hyperlink.value;
    }
```

Ya da, başlatma sırasında `host` nesnesini depolayabilir ve güncelleştirme sırasında ilgili `colorPalette` özelliklerine erişebilirsiniz.

## <a name="on-update"></a>Güncelleştirme sırasında

Yüksek karşıtlık desteğinin belirli uygulamaları görselden görsele farklılık gösterir ve grafik tasarımının ayrıntılarına bağlıdır. Genellikle, önemli ayrıntıların sınırlı renklerle ayırt edilmesini kolaylaştırmak için, yüksek karşıtlık modu varsayılandan biraz farklı bir tasarım gerektirir.

Power BI yerel görselleri tarafından izlenen bazı yönergeler aşağıda verilmiştir:

* Tüm veri noktaları aynı rengi (ön plan) kullanır.
* Bunlara tüm metinler, eksenler, oklar, çizgiler ve benzeri öğeler dahildir. ön plan rengini kullanır.
* Kalın şekiller, kalın çizgiler (en az iki piksel) ve arka plan rengi dolgusu ile ana hatlar olarak çizilir.
* İlgili olduğunda, veri noktaları farklı işaret şekilleriyle ayırt edilir, veri satırları farklı satır oluşturma ile ayırt edilir.
* Bir veri öğesi vurgulandığında, diğer tüm öğelerin opaklığı %40 olarak değiştirilir.
* Dilimleyiciler için etkin filtre öğeleri ön plan seçili rengini kullanır.

Örneğin, Örnek Çubuk Grafiğinde, tüm çubuklar iki piksel kalın ön plan ana hattı ve arka plan dolgusu ile çizilir. Varsayılan renklerle ve birkaç yüksek karşıtlık teması ile görünme şeklini karşılaştırın:

![Standart renkleri kullanan Örnek Çubuk Grafiği](./media/hc-samplebarchart-standard.png)
![*Koyu #2* renk temasını kullanan Örnek Çubuk Grafiği](./media/hc-samplebarchart-dark2.png)
![*Beyaz* renk temasını kullanan Örnek Çubuk Grafiği](./media/hc-samplebarchart-white.png)

İşte `visualTransform` işlevinde yüksek karşıtlığı destekleyecek şekilde değiştirilen bir bölüm. Bu, `update` sırasında işlemenin bir parçası olarak çağrılır:

### <a name="before"></a>Önce

```typescript
for (let i = 0, len = Math.max(category.values.length, dataValue.values.length); i < len; i++) {
    let defaultColor: Fill = {
        solid: {
            color: colorPalette.getColor(category.values[i] + '').value
        }
    };

    barChartDataPoints.push({
        category: category.values[i] + '',
        value: dataValue.values[i],
        color: getCategoricalObjectValue<Fill>(category, i, 'colorSelector', 'fill', defaultColor).solid.color,
        selectionId: host.createSelectionIdBuilder()
            .withCategory(category, i)
            .createSelectionId()
    });
}
```

### <a name="after"></a>Sonra

```typescript
for (let i = 0, len = Math.max(category.values.length, dataValue.values.length); i < len; i++) {
    const color: string = getColumnColorByIndex(category, i, colorPalette);

    const selectionId: ISelectionId = host.createSelectionIdBuilder()
        .withCategory(category, i)
        .createSelectionId();

    barChartDataPoints.push({
        color,
        strokeColor,
        strokeWidth,
        selectionId,
        value: dataValue.values[i],
        category: `${category.values[i]}`,
    });
}

//...

function getColumnColorByIndex(
    category: DataViewCategoryColumn,
    index: number,
    colorPalette: ISandboxExtendedColorPalette,
): string {
    if (colorPalette.isHighContrast) {
        return colorPalette.background.value;
    }

    const defaultColor: Fill = {
        solid: {
            color: colorPalette.getColor(`${category.values[index]}`).value,
        }
    };

    return getCategoricalObjectValue<Fill>(category, index, 'colorSelector', 'fill', defaultColor).solid.color;
}
```
