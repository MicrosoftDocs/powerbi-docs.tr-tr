---
title: Yer imleri
description: Power BI Görsel, yer işaretlerini değiştirmeyi işleyebilir
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 90e3fc73cd49a5c84a5c2acc68a8cf5e0e4aa42b
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2019
ms.locfileid: "68425517"
---
# <a name="add-bookmarks-support-for-power-bi-visuals"></a>Power BI Görselleri için yer işaretleri ekleme desteği

Power BI rapor yer işaretleri rapor sayfası, seçim durumu, görselin filtreleme durumunun yapılandırılmış görünümünü yakalamaya olanak sağlar. Ancak, özel görseller tarafında yer işaretini desteklemek ve değişikliklere doğru tepki vermek için ek eylem gerektirir.

[Belgelerde](https://docs.microsoft.com/power-bi/desktop-bookmarks) yer işaretleri hakkında daha fazla bilgi edinin

## <a name="report-bookmarks-support-in-your-visual"></a>Görselinizde rapor yer işaretleri desteği

Görseliniz diğer görsellerle etkileşimde bulunuyorsa, veri noktalarını seçiyorsa veya diğer görselleri filtreliyorsa, durumu özelliklerden geri yüklemeniz gerekir.

## <a name="how-to-add-report-bookmarks-support"></a>Rapor yer işaretlerini ekleme desteği

1. Gerekli yardımcı programı yükleyin (veya güncelleştirin): `powerbi-visuals-utils-interactivityutils`(https://github.com/Microsoft/PowerBI-visuals-utils-interactivityutils/) sürüm 3.0.0 veya üzeri. Durum seçimi veya filtresiyle işlemek için ek sınıflar içerir. Filtre görselleri ve `InteractivityService` kullanan herhangi bir görsel için gereklidir.

2. `SelectionManager` örneği içinde `registerOnSelectCallback` kullanmak üzere görsel API’yi 1.11.0 sürümüne güncelleştirin. `InteractivityService` yerine düz `SelectionManager` kullanan filtre olmayan görseller için gereklidir.

### <a name="how-custom-visuals-interact-with-power-bi-in-the-report-bookmarks-scenario"></a>Özel görsellerin rapor yer işaretleri senaryosunda Power BI ile etkileşimde bulunma şekli

Aşağıdaki örnek üzerinde düşünelim: Bir kullanıcı, her bir yer işareti içinde farklı seçim durumuyla rapor sayfasında çeşitli yer işaretleri oluşturur.

İlk olarak, kullanıcı görselinizdeki bir veri noktasını seçer. Görsel, seçimleri ana bilgisayara geçirerek Power BI ve diğer görsellerle etkileşim kurar. Ardından kullanıcı `Bookmark panel` içinde "Ekle" seçeneğini belirler ve Power BI yeni yer işaretinin geçerli seçimlerini kaydeder.

Kullanıcı seçimi değiştirdikçe ve yeni yer işaretleri ekledikçe bu işlem tekrarlanan şekilde gerçekleşir.
Oluşturulduktan sonra, kullanıcı yer işaretleri arasında geçiş yapabilir.

Kullanıcılar bir yer işareti seçtiğinde, Power BI kaydedilmiş filtreyi veya seçim durumunu geri yükler ve görsellere geçirir. Diğer görseller, yer işaretinde depolanan duruma göre vurgulanır veya filtrelenir. Eylemlerden sorumlu Power BI ana bilgisayarı. Görseliniz yeni seçim durumunu doğru yansıtmaktan sorumludur (örneğin, işlenen veri noktalarının rengini değiştirme).

Yeni seçim durumu, görsel öğesine `update` yöntemi aracılığıyla iletilir. `options` bağımsız değişkeni, özel bir özellik içerir: `options.jsonFilters`. JSONFilter özelliği `Advanced Filter` ve `Tuple Filter` içerebilir.

Görsel, seçili yer işareti için görselin durumunu gösteren filtre değerlerini geri yüklemelidir.

Ya da görsel yalnızca seçimleri kullanıyorsa, ISelectionManager’ın kayıtlı `registerOnSelectCallback` yöntemini çağırın.

### <a name="visuals-with-selections"></a>Seçimler ile görseller

Görselleriniz, [seçimleri](https://github.com/Microsoft/PowerBI-visuals/blob/master/Tutorial/Selection.md) kullanılarak diğer görsellerle etkileşim kuruyorsa. Yer işaretleri eklemenin iki yolu vardır.

* Görselinizde daha önce **[`InteractivityService`](https://github.com/Microsoft/powerbi-visuals-utils-interactivityutils/blob/master/docs/api/interactivityService.md) kullanmadıysanız** `FilterManager.restoreSelectionIds` yöntemini kullanabilirsiniz.

* Görselinizi, seçimleri yönetmek için zaten **[`InteractivityService`](https://github.com/Microsoft/powerbi-visuals-utils-interactivityutils/blob/master/docs/api/interactivityService.md)** kullanıyorsa. `InteractivityService` örneğinde `applySelectionFromFilter` yöntemini kullanmalısınız.

#### <a name="using-iselectionmanagerregisteronselectcallback"></a>`ISelectionManager.registerOnSelectCallback` kullanma

Kullanıcı yer işaretlerine tıkladığında, Power BI ilgili seçimler ile görselin `callback` yöntemini çağırır. 

```typescript
this.selectionManager.registerOnSelectCallback(
    (ids: ISelectionId[]) => {
        //called when a selection was set by Power BI
    });
);
```

Burada, görselinizde [`'visualTransform'`](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/master/src/barChart.ts#L74) yönteminde oluşturulan bir veri noktası olduğunu varsayalım.

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

Veri noktalarını güncelleştirdikten sonra, `filter` nesnesi içinde depolanan geçerli seçim durumunu yansıtır. Veri noktaları işlendiğinde, özel görselin seçim durumu yer işaretinin durumuyla eşleşecektir.

### <a name="using-interactivityservice-for-control-selections-in-the-visual"></a>Görselde denetim seçimleri için `InteractivityService` kullanma

Görseliniz `InteractivityService` kullanıyorsa, görselinizde yer işaretlerini desteklemek için ek eylemlere gerek kalmaz.

Kullanıcı yer işaretlerini seçtiğinde, yardımcı program görselin seçim durumunu işler.

### <a name="visuals-with-filter"></a>Filtre içeren görseller

Görselin tarih aralığına göre bir veri filtresi oluşturduğunu varsayalım. Elimizde aralığın başlangıcı ve bitişi olarak `startDate` ve `endDate` değerleri vardır.
Görsel, verileri ilgili koşullara göre filtrelemek için gelişmiş bir filtre oluşturur ve `applyJsonFilter` ana bilgisayar yöntemini çağırır.
`target`, filtrelemeye yönelik tablodur.

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

Kullanıcı bir yer işaretine her tıkladığında, özel görsel bir `update` çağrısı alır.

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

Bundan sonra, görselin iç durumunun (veri noktaları ve çizgiler, dikdörtgenler vb. görselleştirme nesneleri) geçerli koşulları yansıtacak şekilde değiştirmesi gerekir.

> [!IMPORTANT]
> Rapor yer işaretleri senaryosunda, görselin diğer görselleri filtrelemek için `applyJsonFilter` öğesini çağırması gerekmez; bunlar zaten Power BI tarafından filtrelenecektir.

Zaman Çizelgesi Dilimleyici görseli, veri aralıklarına karşılık gelen aralık seçicisini değiştirir.

Daha fazla bilgi için bkz. [Zaman Çizelgesi Dilimleyici deposu](https://github.com/Microsoft/powerbi-visuals-timeline/commit/606f1152f59f82b5b5a367ff3b117372d129e597?diff=unified#diff-b6ef9a9ac3a3225f8bd0de84bee0a0df).

### <a name="filter-state-to-save-visual-properties-in-bookmarks"></a>Yer işaretlerine görsel özellikleri kaydetmek için durumu filtrele

`filterState` özelliği, filtreleme bölümünün bir özelliğini yapar. Görsel, yer işaretlerinde farklı değerleri saklayabilir.

Özellik değerini filtre durumu olarak kaydetmek için nesne özelliğinin `capabilities.json` içinde `"filterState": true` olarak işaretlenmesi gerekir.

Örnek: `Timeline Slicer` filtre içinde `Granularity` özellik değerlerini depolar. Ayrıca, yer işaretlerinin kullanıcı tarafından değiştirilmesine yönelik geçerli ayrıntı düzeyini değiştirmeye izin verir.

Daha fazla bilgi için bkz. [Zaman Çizelgesi Dilimleyici deposu](https://github.com/microsoft/powerbi-visuals-timeline/commit/8b7d82dd23cd2bd71817f1bc5d1e1732347a185e#diff-290828b604cfa62f1cb310f2e90c52fdR334);
