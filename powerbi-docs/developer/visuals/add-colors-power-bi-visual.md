---
title: Daha iyi tümleşik BI içgörüleri için, Power BI tümleşik analizlerinde Power BI görsellerinize renkler ekleme
description: Bu makalede Power BI görsellerinize renk ekleme ve görselin veri noktalarını renkle işleme yöntemleri anlatılmaktadır. Power BI tümleşik analiz kullanarak daha iyi tümleşik BI içgörüleri elde edin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: how-to
ms.date: 03/27/2020
ms.openlocfilehash: e6b6fb1dbc1397b93ac12692c8610e6f36d0b8bf
ms.sourcegitcommit: eeaf607e7c1d89ef7312421731e1729ddce5a5cc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2021
ms.locfileid: "97887995"
---
# <a name="add-colors-to-your-power-bi-visuals"></a>Power BI görsellerinize renk ekleme

Bu makalede görsellerinize renk ekleme ve görselin veri noktalarını renkle işleme yöntemleri anlatılmaktadır.

`IVisualHost`, hizmetlerinden biri olarak renk gösterir.
Bu makaledeki örnek kod, [SampleBarChart görselini](https://github.com/microsoft/PowerBI-visuals-sampleBarChart) değiştirir.
Kaynak kodu için bkz. [barChart.ts](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/blob/master/src/barChart.ts).

Görsel oluşturmaya başlamak için bkz. [Power BI daire kartı görseli geliştirme](develop-circle-card.md).

## <a name="add-color-to-data-points"></a>Veri noktalarına renk ekleme

Her veri noktası farklı bir renkle gösterilir.
Aşağıdaki örnekte olduğu gibi rengi `BarChartDataPoint` arabirimine ekleyin:

```typescript
/**
 * Interface for BarChart data points.
 *
 * @interface
 * @property {number} value    - Data value for point.
 * @property {string} category - Corresponding category of data value.
 * @property {string} color    - Color corresponding to data point.
 */
interface BarChartDataPoint {
    value: number;
    category: string;
    color: string;
};
```

## <a name="use-the-color-palette-service"></a>Renk paleti hizmetini kullanma

`colorPalette` hizmeti, görselinizde kullanılan renkleri yönetir.
Hizmetin bir örneği `IVisualHost` üzerinde mevcuttur.

Bunu `update` yönteminde tanımlayın.

```typescript
constructor(options: VisualConstructorOptions) {
        this.host = options.host; // host: IVisualHost
        ...
    }

public update(options: VisualUpdateOptions) {

    let colorPalette: IColorPalette = host.colorPalette;
    ...
}
```

## <a name="assigning-color-to-data-points"></a>Veri noktalarına renk atama

Ardından `dataPoints` için bir değer belirtin.
Bu örnekte her bir `dataPoints` içinde değer, kategori ve renk bulunur.
`dataPoints` içinde başka özellikler de bulunabilir.

`SampleBarChart` içinde `visualTransform` yöntemi, `dataPoints` hesaplamasını kapsüller.
Bu yöntem, Çubuk Grafik Bar Chart viewmodel'in bir parçasıdır.
Yöntem, `visualTransform` içindeki `dataPoints` hesaplamasıyla yinelendiğinden aşağıdaki örnekte gösterildiği gibi renk atamak için ideal yerdir:

```typescript

public update(options: VisualUpdateOptions) {
    ....
    let viewModel: BarChartViewModel = visualTransform(options, this.host);
    ....
}

function visualTransform(options: VisualUpdateOptions, host: IVisualHost): BarChartViewModel {
    let colorPalette: IColorPalette = host.colorPalette; // host: IVisualHost
    for (let i = 0, len = Math.max(category.values.length, dataValue.values.length); i < len; i++) {
        barChartDataPoints.push({
            category: category.values[i],
            value: dataValue.values[i],
            color: colorPalette.getColor(category.values[i]).value,
        });
    }
}
```

Ardından `dataPoints` verilerini `update` yöntemi içindeki [d3](https://d3js.org/)-selection `barSelection` üzerine uygulayın:

```typescript
// This code is actual for d3 v5
// in d3 v5 for this case we should use merge() after enter() and apply changes on barSelectionMerged
this.barSelection = this.barContainer
    .selectAll('.bar')
    .data(this.barDataPoints);

const barSelectionMerged = this.barSelection
    .enter()
    .append('rect')
    .merge(<any>this.barSelection);

barSelectionMerged.classed('bar', true);

barSelectionMerged
.attr("width", xScale.bandwidth())
.attr("height", d => height - yScale(<number>d.value))
.attr("y", d => yScale(<number>d.value))
.attr("x", d => xScale(d.category))
.style("fill", (dataPoint: BarChartDataPoint) => dataPoint.color)
.style("stroke", (dataPoint: BarChartDataPoint) => dataPoint.strokeColor)
.style("stroke-width", (dataPoint: BarChartDataPoint) => `${dataPoint.strokeWidth}px`);

this.barSelection
    .exit()
    .remove();
```

## <a name="next-steps"></a>Sonraki adımlar

Power BI görselleri hakkında daha fazla bilgi için bkz. [Power BI görsellerinin becerileri ve özellikleri](capabilities.md).

Power BI görseli geliştirme hakkında daha fazla bilgi için bkz. [Power BI görsellerinde hata ayıklama](visuals-how-to-debug.md) ve [Power BI görselleriyle ilgili sorunları giderme](power-bi-custom-visuals-troubleshoot.md).
