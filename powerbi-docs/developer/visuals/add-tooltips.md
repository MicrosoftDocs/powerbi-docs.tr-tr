---
title: Power BI görsellerinde araç ipuçları
description: Bu makalede Power BI görsellerinde araç ipuçlarını nasıl görüntüleyebileceğiniz açıklanır.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: b850fddeb08428171aa653b97a6fb9e45a3afce7
ms.sourcegitcommit: 2c798b97fdb02b4bf4e74cf05442a4b01dc5cbab
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80114294"
---
# <a name="tooltips-in-power-bi-visuals"></a>Power BI görsellerinde araç ipuçları

Görseller artık Power BI araç ipucu desteğini kullanabilir. Power BI araç ipuçları aşağıdaki etkileşimleri işler:'''

* Araç ipucunu gösterme.'''
* Araç ipucunu gizleme.
* Araç ipucunu taşıma.

Araç ipuçları, bir başlıkla, verili renkte bir değerle ve belirtilen koordinat kümesinde opaklıkla bir metin öğesi görüntüleyebilir. Bu veriler API’ye sağlanır ve Power BI konağı bunu yerel görseller için araç ipuçlarını işlediği şekilde işler.

Aşağıdaki resimde örnek çubuk grafikte bir araç ipucu gösterilir:

![Örnek çubuk grafik araç ipuçları](media/add-tooltips/tooltips-in-samplebarchart.png)

Önceki araç ipucu resminde tek bir çubuk kategorisi ve değeri gösterilir. Tek bir araç ipucunu birden çok değer görüntüleyecek şekilde genişletebilirsiniz.

## <a name="manage-tooltips"></a>Araç ipuçlarını yönetme

Araç ipuçlarını 'ITooltipService' arabirimi aracılığıyla yönetirsiniz. Bu arabirim bir araç ipucunun gösterilmesi, kaldırılması veya taşınması gerektiğini konağa bildirmek için kullanılır.

```typescript
    interface ITooltipService {
        enabled(): boolean;
        show(options: TooltipShowOptions): void;
        move(options: TooltipMoveOptions): void;
        hide(options: TooltipHideOptions): void;
    }
```

Görselinizin, görsel içindeki fare olaylarını dinlemesi ve sonra `Tooltip****Options` nesneleri içinde uygun içerikle doldurulmuş olarak `show()`, `move()` ve `hide()` temsilcilerini çağırması gerekir.
`TooltipShowOptions` ve `TooltipHideOptions`, bu olaylarda nelerin görüntüleneceğini ve nasıl davranılması gerektiğini tanımlar.

Bu yöntemlerin çağrılması fare hareketi veya dokunma olayları gibi kullanıcı olaylarını içerdiğinden, bu olaylar için `TooltipService` üyelerini çağıran dinleyiciler oluşturmak iyi bir yöntemdir.
Örneğimiz bunları `TooltipServiceWrapper` adlı bir sınıfta toplar.

### <a name="the-tooltipservicewrapper-class"></a>TooltipServiceWrapper sınıfı

Bu sınıfın arkasındaki temel düşünce, `TooltipService` öğesinin örneğini tutmak, ilgili öğelerin üzerinde D3 fare olaylarını dinlemek ve sonra öğelerde `show()` ve gerektiğinde `hide()` işlemleri için çağrıları yapmaktır.

Sınıf, bu olaylar için ilgili durumu ve mantığı barındırır ve yönetir; genellikle temel alınan D3 kodu ile arabirim oluşturmak için ayarlanmıştır. D3 arabirimi oluşturma ve dönüştürme işlemleri bu makalenin kapsamı dışındadır.

[SampleBarChart görsel deposunda](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/981b021612d7b333adffe9f723ab27783c76fb14) tam örnek kodu bulabilirsiniz.

### <a name="create-tooltipservicewrapper"></a>TooltipServiceWrapper oluşturma

Çubuk grafik oluşturucusunun artık konağın `tooltipService` örneğiyle birlikte oluşturucuda örneği oluşturulan bir `TooltipServiceWrapper` üyesi vardır.

```typescript
        private tooltipServiceWrapper: ITooltipServiceWrapper;

        this.tooltipServiceWrapper = createTooltipServiceWrapper(this.host.tooltipService, options.element);
```

`TooltipServiceWrapper` sınıfı, `tooltipService` örneğini ve görsel ve dokunma parametrelerinin kök D3 öğesini barındırır.

```typescript
    class TooltipServiceWrapper implements ITooltipServiceWrapper {
        private handleTouchTimeoutId: number;
        private visualHostTooltipService: ITooltipService;
        private rootElement: Element;
        private handleTouchDelay: number;

        constructor(tooltipService: ITooltipService, rootElement: Element, handleTouchDelay: number) {
            this.visualHostTooltipService = tooltipService;
            this.handleTouchDelay = handleTouchDelay;
            this.rootElement = rootElement;
        }
        .
        .
        .
    }
```

Bu sınıfın olay dinleyicilerini kaydetmesi için tek giriş noktası `addTooltip` yöntemidir.

### <a name="the-addtooltip-method"></a>addTooltip yöntemi

```typescript
        public addTooltip<T>(
            selection: d3.Selection<Element>,
            getTooltipInfoDelegate: (args: TooltipEventArgs<T>) => VisualTooltipDataItem[],
            getDataPointIdentity: (args: TooltipEventArgs<T>) => ISelectionId,
            reloadTooltipDataOnMouseMove?: boolean): void {

            if (!selection || !this.visualHostTooltipService.enabled()) {
                return;
            }
        ...
        ...
        }
```

* **selection: d3.Selection<Element>** : Üzerinde araç ipuçlarının işlendiği d3 öğeleri.

* **getTooltipInfoDelegate: (args: TooltipEventArgs<T>) => VisualTooltipDataItem[]** : Bağlam başına araç ipucu içeriğini (görüntülenen öğeler) doldurmak için temsilci.

* **getDataPointIdentity: (args: TooltipEventArgs<T>) => ISelectionId**: Veri noktası kimliğini (bu örnekte kullanılmıyor) almak için temsilci. 

* **reloadTooltipDataOnMouseMove? boolean**: MouseMove olayı sırasında araç ipucu verilerinin yenilenip yenilenmeyeceğini belirten Boole değeri (bu örnekte kullanılmıyor).

Sizin de görebileceğiniz gibi, `tooltipService` devre dışı bırakıldığında veya gerçek bir seçim olmadığında hiçbir eylem yapılmadan `addTooltip` yönteminden çıkılır.

### <a name="call-the-show-method-to-display-a-tooltip"></a>Araç ipucunu görüntülemek için gösterme yöntemini çağırma

Bundan sonra `addTooltip` yöntemi aşağıdaki kodda gösterildiği gibi D3 `mouseover` olayını dinler:

```typescript
        ...
        ...
        selection.on("mouseover.tooltip", () => {
            // Ignore mouseover while handling touch events
            if (!this.canDisplayTooltip(d3.event))
                return;

            let tooltipEventArgs = this.makeTooltipEventArgs<T>(rootNode, true, false);
            if (!tooltipEventArgs)
                return;

            let tooltipInfo = getTooltipInfoDelegate(tooltipEventArgs);
            if (tooltipInfo == null)
                return;

            let selectionId = getDataPointIdentity(tooltipEventArgs);

            this.visualHostTooltipService.show({
                coordinates: tooltipEventArgs.coordinates,
                isTouchEvent: false,
                dataItems: tooltipInfo,
                identities: selectionId ? [selectionId] : [],
            });
        });
```

* **makeTooltipEventArgs**: Seçili D3 öğelerinden bir tooltipEventArgs içine bağlamı ayıklar. Koordinatları da hesaplar.

* **getTooltipInfoDelegate**: Ardından araç ipucu içeriğini tooltipEventArgs’den oluşturur. Bu BarChart sınıfına bir geri aramadır çünkü görselin mantığı budur. Araç ipucunda görüntülenecek olan gerçek metin içeriğidir.

* **getDataPointIdentity**: Bu örnekte kullanılmıyor.

* **this.visualHostTooltipService.show**: Araç ipucunu görüntüleme çağrısı.  

Ek işleme `mouseout` ve `mousemove` olayları için örnekte bulunabilir.

Daha fazla bilgi için bkz. [SampleBarChart görsel deposu](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/981b021612d7b333adffe9f723ab27783c76fb14).

### <a name="populate-the-tooltip-content-by-the-gettooltipdata-method"></a>Araç ipucu içeriğini getTooltipData yöntemiyle doldurma

BarChart sınıfı yalnızca veri noktasının `category`, `value` ve `color` öğelerini VisualTooltipDataItem[] öğesine ayıklayan `getTooltipData` üyesiyle eklenmişti.

```typescript
        private static getTooltipData(value: any): VisualTooltipDataItem[] {
            return [{
                displayName: value.category,
                value: value.value.toString(),
                color: value.color,
                header: 'ToolTip Title'
            }];
        }
```

Önceki uygulamada, `header` üyesi sabittir ancak dinamik değerler gerektiren daha karmaşık uygulamalar için bunu kullanabilirsiniz. `VisualTooltipDataItem[]` öğesini birden fazla öğe ile doldurabilirsiniz; bu, araç ipucuna birden çok satır ekler. Araç ipucunun tek bir veri noktasından fazla veri görüntüleyebildiği yığılmış çubuk grafikleri gibi görsellerde faydalı olabilir.

### <a name="call-the-addtooltip-method"></a>addTooltip yöntemini çağırma

Son adım gerçek veriler değiştiğinde `addTooltip` yöntemini çağırmaktır. Bu çağrı `BarChart.update()` yönteminde gerçekleştirilir. Tüm 'bar' öğelerinin seçimini izlemek için bir çağrı yapılır ve yalnızca daha önce bahsedildiği gibi `BarChart.getTooltipData()` geçirilir.

```typescript
        this.tooltipServiceWrapper.addTooltip(this.barContainer.selectAll('.bar'),
            (tooltipEvent: TooltipEventArgs<number>) => BarChart.getTooltipData(tooltipEvent.data),
            (tooltipEvent: TooltipEventArgs<number>) => null);
```

## <a name="add-report-page-tooltips"></a>Rapor sayfası araç ipuçları ekleme

Rapor sayfası araç ipuçları desteği eklemek için en çok değişikliği *capabilities.json* dosyasında bulursunuz.

Örnek bir şema

```json
{
    "tooltips": {
        "supportedTypes": {
            "default": true,
            "canvas": true
        },
        "roles": [
            "tooltips"
        ]
    }
}
```

Rapor sayfası araç ipuçlarını **Biçim** bölmesinde tanımlayabilirsiniz.

![Rapor sayfası araç ipucu](media/add-tooltips/report-page-tooltips.png)

* `supportedTypes` Görsel tarafından desteklenen ve alanlarda da yansıtılan araç ipucu yapılandırması. 
   * `default` Veri alanı aracılığıyla "otomatik" araç ipuçları bağlamasının desteklenip desteklenmediğini belirtir. 
   * `canvas` Rapor sayfası araç ipuçlarının desteklenip desteklenmediğini belirtir.

* `roles` (İsteğe bağlı) Tanımlandıktan sonra, alanlar kutusunda seçili araç ipucu seçeneğine hangi veri rollerinin bağlı olduğunu bildirir.

Daha fazla bilgi için bkz. [Rapor sayfası araç ipuçları kullanım yönergeleri](https://powerbi.microsoft.com/blog/power-bi-desktop-march-2018-feature-summary/#tooltips).

Rapor sayfası araç ipucunu görüntülemek için, Power BI konağı `ITooltipService.Show(options: TooltipShowOptions)` veya `ITooltipService.Move(options: TooltipMoveOptions)` çağrısı yaptıktan sonra selectionId’yi (önceki `options` bağımsız değişkeninin `identities` özelliği) kullanır. SelectionId’nin araç ipucu tarafından alınması için üzerine geldiğiniz öğenin seçili verilerini (kategori, seri vb.) temsil etmesi gerekir.

Aşağıdaki kodda selectionId’nin araç çubuğu görüntüleme çağrılarına gönderilmesinin bir örneği gösterilir:

```typescript
    this.tooltipServiceWrapper.addTooltip(this.barContainer.selectAll('.bar'),
        (tooltipEvent: TooltipEventArgs<number>) => BarChart.getTooltipData(tooltipEvent.data),
        (tooltipEvent: TooltipEventArgs<number>) => tooltipEvent.data.selectionID);
```
