---
title: Daha iyi tümleşik BI içgörüleri için, Power BI tümleşik analizlerinde Power BI görselleri için yer işareti desteği ekleme
description: Power BI görsellerinin işleyebilecekleri. Power BI tümleşik analiz kullanarak daha iyi tümleşik BI içgörüleri elde edin. yer işareti değiştirme
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: how-to
ms.date: 06/18/2019
ms.openlocfilehash: a1bd0f694bbc2bc40fc35aef3c6017e7f4a8196a
ms.sourcegitcommit: a5e98bc86915f7bea6a0ab5df282683840e63d2c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97969708"
---
# <a name="add-bookmark-support-for-power-bi-visuals"></a>Power BI görselleri için yer işareti desteği ekleme

Power BI rapor yer işaretleriyle rapor sayfasının, seçim durumunun ve görselin filtreleme durumunun yapılandırılmış görünümünü yakalayabilirsiniz. Öte yandan Power BI görselleri tarafında yer işaretini desteklemek ve değişikliklere doğru tepki vermek için ek eylem gerekir.

Yer işaretleri hakkında daha fazla bilgi için bkz. [Power BI'da içgörüleri paylaşmak ve hikayeler oluşturmak için yer işaretlerini kullanma](../../create-reports/desktop-bookmarks.md).

## <a name="report-bookmarks-support-in-your-visual"></a>Görselinizde rapor yer işaretleri desteği

Görseliniz diğer görsellerle etkileşimde bulunuyorsa, veri noktalarını seçiyorsa veya diğer görselleri filtreliyorsa, durumu özelliklerden geri yüklemeniz gerekir.

## <a name="add-report-bookmarks-support"></a>Rapor yer işaretlerini ekleme desteği

1. Gereken [powerbi-visuals-utils-interactivityutils](https://github.com/Microsoft/PowerBI-visuals-utils-interactivityutils/) yardımcı programının 3.0.0 veya sonraki bir sürümünü yükleyin veya programı bu sürüme güncelleştirin. Durum seçimi veya filtresiyle işlemek üzere ek sınıflar içerir. Filtre görselleri ve `InteractivityService` kullanan tüm görseller için gereklidir.

2. Bir `SelectionManager` örneğinde `registerOnSelectCallback` kullanmak için görsel API’sini sürüm 1.11.0’a yükseltin. `InteractivityService` yerine düz `SelectionManager` kullanan, filtre olmayan görseller için gereklidir.

### <a name="how-power-bi-visuals-interact-with-power-bi-in-report-bookmarks"></a>Power BI görsellerinin rapor yer işaretlerinde Power BI ile etkileşimde bulunma şekli

Şu senaryoyu ele alalım: Rapor sayfasında her yer işaretinin farklı bir seçim durumunda olduğu çeşitli yer işaretleri oluşturmak istiyorsunuz.

İlk olarak görselinizdeki bir veri noktasını seçersiniz. Görsel, seçimleri ana bilgisayara geçirerek Power BI ve diğer görsellerle etkileşim kurar. Ardından **Yer işareti** bölmesinde **Ekle**’yi seçersiniz ve Power BI geçerli seçimleri yeni yer işareti için kaydeder.

Siz seçimi değiştirdikçe ve yeni yer işaretleri ekledikçe bu işlem tekrarlanır. Yer işaretlerini oluşturduktan sonra aralarında geçiş yapabilirsiniz.

Bir yer işareti seçtiğinizde, Power BI kaydedilmiş filtreyi veya seçim durumunu geri yükler ve görsellere geçirir. Diğer görseller, yer işaretinde depolanan duruma göre vurgulanır veya filtrelenir. Eylemler Power BI konağının sorumluluğundadır. Görseliniz yeni seçim durumunu doğru yansıtmaktan sorumludur (örneğin, işlenen veri noktalarının rengini değiştirmek için).

Yeni seçim durumu, görsel öğesine `update` yöntemi aracılığıyla iletilir. `options` bağımsız değişkeni, özel bir özellik içerir: `options.jsonFilters`. JSONFilter özelliği `Advanced Filter` ve `Tuple Filter` içerebilir.

Görsel, seçili yer işareti için görselin buna karşılık gelen durumunu gösteren filtre değerlerini geri yüklemelidir. Öte yandan görsel yalnızca seçimleri kullanıyorsa ISelectionManager’ın `registerOnSelectCallback` yöntemi olarak kayıtlı olan özel geri arama işlev çağrısını kullanabilirsiniz.

### <a name="visuals-with-selection"></a>Seçim ile Görseller

Görseliniz [Seçim](https://github.com/PowerBi-Projects/PowerBI-visuals/blob/master/Tutorial/Selection.md) kullanarak diğer görsellerle etkileşim kuruyorsa şu iki yoldan biriyle yer işareti ekleyebilirsiniz:

* Görsel henüz [InteractivityService](https://github.com/microsoft/powerbi-visuals-utils-interactivityutils/blob/master/src/interactivityService.ts)’i kullanmadıysa `FilterManager.restoreSelectionIds` yöntemini kullanabilirsiniz.

* Görsel seçimleri yönetmek için zaten [InteractivityService](https://github.com/microsoft/powerbi-visuals-utils-interactivityutils/blob/master/src/interactivityService.ts)’i kullanıyorsa, `InteractivityService` örneğinde `applySelectionFromFilter` yöntemini kullanmalısınız.

#### <a name="use-iselectionmanagerregisteronselectcallback"></a>ISelectionManager.registerOnSelectCallback kullanma

Yer işaretini seçtiğinizde Power BI ilgili seçimler ile görselin `callback` yöntemini çağırır. 

```typescript
this.selectionManager.registerOnSelectCallback(
    (ids: ISelectionId[]) => {
        //called when a selection was set by Power BI
    });
);
```

Görselinizde [visualTransform](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/master/src/barChart.ts#L74) yönteminde oluşturulmuş bir veri noktanızın olduğunu varsayalım.

`datapoints` şuna benzer:

```typescript
visualDataPoints.push({
    category: categorical.categories[0].values[i],
    color: getCategoricalObjectValue<Fill>(categorical.categories[0], i, 'colorSelector', 'fill', defaultColor).solid.color,
    selectionId: host.createSelectionIdBuilder()
        .withCategory(categorical.categories[0], i)
        .createSelectionId(),
    selected: false
});
```

Veri noktalarınız olarak `visualDataPoints` öğesine sahip olur ve `ids` dizisini `callback` işlevine geçirirsiniz.

Bu noktada, görsel `ISelectionId[]` dizisini `visualDataPoints` dizinizdeki seçimlerle karşılaştırmalı ve ilgili veri noktalarını seçili olarak işaretlemelidir.

```typescript
this.selectionManager.registerOnSelectCallback(
    (ids: ISelectionId[]) => {
        visualDataPoints.forEach(dataPoint => {
            ids.forEach(bookmarkSelection => {
                if (bookmarkSelection.equals(dataPoint.selectionId)) {
                    dataPoint.selected = true;
                }
            });
        });
    });
);
```

Siz veri noktalarını güncelleştirdikten sonra, bunlar `filter` nesnesinde depolanan geçerli seçim durumunu yansıtır. Veri noktaları işlendiğinde, özel görselin seçim durumu yer işaretinin durumuyla eşleşecektir.

### <a name="use-interactivityservice-for-control-selections-in-the-visual"></a>Görselde denetim seçimleri için InteractivityService kullanma

Görseliniz `InteractivityService` kullanıyorsa, görselinizde yer işaretlerini desteklemek için ek eylemlere gerek kalmaz.

Yer işaretlerini seçtiğinizde yardımcı program görselin seçim durumunu işler.

### <a name="visuals-with-a-filter"></a>Filtre içeren görseller

Görselin tarih aralığına göre bir veri filtresi oluşturduğunu varsayalım. Aralığın başlangıç ve bitiş tarihleri olarak `startDate` ve `endDate` vardır.

Görsel, verileri ilgili koşullara göre filtrelemek için gelişmiş bir filtre oluşturur ve `applyJsonFilter` konak yöntemini çağırır.

Hedef, filtreleme için kullanılan tablodur.

```typescript
import { AdvancedFilter } from "powerbi-models";

const filter: IAdvancedFilter = new AdvancedFilter(
    target,
    "And",
    {
        operator: "GreaterThanOrEqual",
        value: startDate
            ? startDate.toJSON()
            : null
    },
    {
        operator: "LessThanOrEqual",
        value: endDate
            ? endDate.toJSON()
            : null
    });

this.host.applyJsonFilter(
    filter,
    "general",
    "filter",
    (startDate && endDate)
        ? FilterAction.merge
        : FilterAction.remove
);
```

Bir yer işaretine her tıkladığınızda, özel görsel bir `update` çağrısı alır.

Özel görsel, nesnedeki filtreyi denetlemelidir:

```typescript
const filter: IAdvancedFilter = FilterManager.restoreFilter(
    && options.jsonFilters
    && options.jsonFilters[0] as any
) as IAdvancedFilter;
```

`filter` nesnesi null değilse, görselin filtre koşullarını nesneden geri yüklemesi gerekir:

```typescript
const jsonFilters: AdvancedFilter = this.options.jsonFilters as AdvancedFilter[];

if (jsonFilters
    && jsonFilters[0]
    && jsonFilters[0].conditions
    && jsonFilters[0].conditions[0]
    && jsonFilters[0].conditions[1]
) {
    const startDate: Date = new Date(`${jsonFilters[0].conditions[0].value}`);
    const endDate: Date = new Date(`${jsonFilters[0].conditions[1].value}`);

    // apply restored conditions
} else {
    // apply default settings
}
```

Bundan sonra görsel iç durumunu geçerli koşulları yansıtacak şeklide değiştirmelidir. İç durum veri noktalarını ve görselleştirme nesnelerini (çizgiler, dikdörtgenler vb.) içerir.

> [!IMPORTANT]
> Rapor yer işaretleri senaryosunda, görselin diğer görselleri filtrelemek için `applyJsonFilter` öğesini çağırması gerekmez. Bunlar zaten Power BI tarafından filtrelenecektir.

Zaman Çizelgesi Dilimleyici görseli, veri aralıklarına karşılık gelen aralık seçicisini değiştirir.

Daha fazla bilgi için bkz. [Zaman Çizelgesi Dilimleyici deposu](https://github.com/Microsoft/powerbi-visuals-timeline/commit/606f1152f59f82b5b5a367ff3b117372d129e597?diff=unified#diff-b6ef9a9ac3a3225f8bd0de84bee0a0df).

### <a name="filter-the-state-to-save-visual-properties-in-bookmarks"></a>Yer işaretlerine görsel özelliklerini kaydetmek için durumu filtreleme

`filterState` özelliği, filtreleme bölümünün bir özelliğini yapar. Görsel, yer işaretlerinde çeşitli değerleri depolayabilir.

Özellik değerini filtre durumu olarak kaydetmek için *capabilities.json* dosyasında nesne özelliğini `"filterState": true` olarak işaretleyin.

Örneğin Zaman Çizelgesi Dilimleyici `Granularity` özellik değerlerini bir filtrede depolar. Siz yer işaretlerini değiştirdikçe geçerli ayrıntı düzeyinin değişmesini sağlar.

Daha fazla bilgi için bkz. [Zaman Çizelgesi Dilimleyici deposu](https://github.com/microsoft/powerbi-visuals-timeline/commit/8b7d82dd23cd2bd71817f1bc5d1e1732347a185e#diff-290828b604cfa62f1cb310f2e90c52fdR334).
