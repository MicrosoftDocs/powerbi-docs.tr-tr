---
title: Daha iyi tümleşik BI içgörüleri için, Power BI tümleşik analizlerinde görsel API
description: Bu makalede Power BI görselleri için IVisual API'nin kullanılması anlatılmaktadır. Power BI tümleşik analiz kullanarak daha iyi tümleşik BI içgörüleri elde edin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 03/19/2020
ms.openlocfilehash: 7b81ecfa1b97b202b6c1ff306cf858f2ea00acde
ms.sourcegitcommit: eeaf607e7c1d89ef7312421731e1729ddce5a5cc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2021
ms.locfileid: "97888547"
---
# <a name="visual-api"></a>Görsel API
Tüm görseller `IVisual` arabirimini uygulayan sınıfla başlar. `IVisual` arabirimini uygulayan bir sınıf olduğu sürece, sınıfı dilediğiniz şekilde adlandırabilirsiniz.

> [!NOTE]
> Görsel sınıfı adının *pbiviz.json* dosyasında tanımlananla eşleşmesi gerekir.

Uygulanması gereken aşağıdaki yöntemleri içeren örnek görsel sınıfına göz atın:

* `constructor`, görselin durumunu başlatmaya yönelik standart bir oluşturucu
* `update`, görselin verilerini güncelleştirmek için
* `enumerateObjectInstances`, nesneleri gerektiği şekilde düzenleyebileceğiniz özellik bölmesine (biçimlendirme seçenekleri), bu bölmeyi doldurmak amacıyla geri döndürmek için
* `destroy`, temizleme için standart yıkıcı

```typescript
class MyVisual implements IVisual {
    
    constructor(options: VisualConstructorOptions) {
        //one time setup code goes here (called once)
    }
    
    public update(options: VisualUpdateOptions): void {
        //code to update your visual goes here (called on all view or data changes)
    }

    public enumerateObjectInstances(options: EnumerateVisualObjectInstancesOptions): VisualObjectInstanceEnumeration {
        //returns objects to populate the property pane (called for each object defined in capabilities)
    }
    
    public destroy(): void {
        //one time cleanup code goes here (called once)
    }
}
```

## <a name="constructor"></a>oluşturucu

Görsel sınıfının oluşturucusu, görsel somut hale geldiğinde çağrılır. Görselin gereksinim duyduğu herhangi bir kurulum işlemi için kullanılabilir.

```typescript
constructor(options: VisualConstructorOptions)
```

**VisualConstructorOptions**

* `element: HTMLElement`, görselinizi içerecek DOM öğesine bir başvuru
* `host: IVisualHost`, görsel ana bilgisayarıyla (Power BI) etkileşim kurmak için kullanılabilen özelliklerden ve hizmetlerden oluşan bir koleksiyon

   `IVisualHost`, şu hizmetleri içerir:

   ```typescript
   export interface IVisualHost extends extensibility.IVisualHost {
       createSelectionIdBuilder: () => visuals.ISelectionIdBuilder;
       : () => ISelectionManager;
       colorPalette: ISandboxExtendedColorPalette;
       persistProperties: (changes: VisualObjectInstancesToPersist) => void;
       applyJsonFilter: (filter: IFilter[] | IFilter, objectName: string, propertyName: string, action: FilterAction) => void;
       tooltipService: ITooltipService;
       telemetry: ITelemetryService;
       authenticationService: IAuthenticationService;
       locale: string;
       allowInteractions: boolean;
       launchUrl: (url: string) => void;
       fetchMoreData: () => boolean;
       instanceId: string;
       refreshHostData: () => void;
       createLocalizationManager: () => ILocalizationManager;
       storageService: ILocalVisualStorageService;
       eventService: IVisualEventService;
       switchFocusModeState: (on: boolean) => void;
   }
   ```
   * `createSelectionIdBuilder`, görselinizdeki seçilebilir öğelerin meta verilerini oluşturup depolar
   * `createSelectionManager`, seçim durumunda yapılan değişiklikleri görselin ana bilgisayarına bildirmek için kullanılan iletişim köprüsünü oluşturur, bkz. [Seçim API](./selection-api.md)’si.
   * `createLocalizationManager`, [Yerelleştirme](./localization.md) konusunda yardımcı olması için bir yönetici oluşturur
   * `allowInteractions: boolean`, görselin etkileşimli olup olmaması gerektiğine yönelik ipucu veren boole bayrağı
   * `applyJsonFilter`, belirli filtre türlerini uygular, bkz. [Filtre API](./filter-api.md)’si
   * `persistProperties`, kullanıcıların özellikleri kalıcı hale getirmesini ve görsel tanımıyla birlikte kaydetmesini sağlar, böylece sonraki yeniden yüklemede kullanılabilir hale getirir
   * `eventService`, **İşleme** olaylarını desteklemek için bir [olay hizmeti](./event-service.md) döndürür
   * `storageService`, görselde [yerel depolama](./local-storage.md) kullanmaya yardımcı olması için bir hizmet döndürür
   * `authenticationService`, kullanıcı kimlik doğrulaması konusunda yardımcı olması için bir hizmet oluşturur
   * `tooltipService`, görselde araç ipuçlarını kullanmaya yardımcı olması için bir [araç ipucu hizmeti](./add-tooltips.md) döndürür
   * `launchUrl`, sonraki sekmede [URL’yi başlatmaya](./launch-url.md) yardımcı olur
   * `locale`, bir yerel ayar dizesi döndürür, bkz. [Yerelleştirme](./localization.md)
   * `instanceId`, geçerli görsel örneğini tanımlamak için bir dize döndürür
   * `colorPalette`, verilerinize renk uygulamak için gereken colorPalette değerini döndürür
   * `fetchMoreData`, standart sınırdan (1.000 satır) daha fazla veri kullanmayı destekler
   * `switchFocusModeState`, odak modu durumunu değiştirmeye yardımcı olur

## <a name="update"></a>update

Tüm görsellerin verilerde veya ana bilgisayar ortamında bir değişiklik olduğunda çağrılan bir genel güncelleştirme yöntemi uygulaması gerekir.

```typescript
public update(options: VisualUpdateOptions): void
```

**VisualUpdateOptions**

* `viewport: IViewport`, görselin içinde işlenmesi gereken görünüm penceresinin boyutları
* `dataViews: DataView[]`, görselinizi işlemek için gereken tüm verileri içeren bir görünüm penceresi nesnesi (görseliniz genellikle DataView bölümündeki kategorik özelliği kullanır)
* `type: VisualUpdateType`, bu güncelleştirmenin türlerini belirten bayraklar (**Data** | **Resize** | **ViewMode** | **Style** | **ResizeEnd**)
* `viewMode: ViewMode`, görselin görünüm modunu belirten bayraklar (**View** | **Edit** | **InFocusEdit**)
* `editMode: EditMode`, görselin düzenleme modunu belirten bayrak (**Default** | **Advanced**) (görsel **AdvancedEditMode**’u destekliyorsa **editMode** **Advanced** olarak ayarlandığında gelişmiş kullanıcı arabirimi denetimlerini işlemesi gerekir, bkz. [AdvancedEditMode](./advanced-edit-mode.md))
* `operationKind?: VisualDataChangeOperationKind`, veri değişikliğinin türünü belirten bayrak (**Create** | **Append**)
* `jsonFilters?: IFilter[]`, uygulanan JSON filtreleri koleksiyonu
* `isInFocus?: boolean`, görselin odak modunda olup olmadığını belirten bayrak
    
## <a name="enumerateobjectinstances-optional"></a>enumerateObjectInstances `optional`

Bu yöntem, özelliklerde listelenen her nesne için çağrılır. Seçenekleri (şu anda sadece ad) kullanarak, bu özelliğin nasıl görüntüleneceği hakkında bilgi içeren bir `VisualObjectInstanceEnumeration` döndürürsünüz.

```typescript
enumerateObjectInstances(options:EnumerateVisualObjectInstancesOptions):VisualObjectInstanceEnumeration
```

**EnumerateVisualObjectInstancesOptions**

* `objectName: string`, nesnenin adı

## <a name="destroy-optional"></a>`optional` öğesini yok etme

Yok etme işlevi, görselinizin yükü kaldırıldığında çağrılır ve olay dinleyicilerini kaldırma gibi temizleme görevlerinde kullanılabilir.

``` typescript
public destroy(): void
```

> [!Note]
> Görseli içeren IFrame’i tamamen kaldırmak daha hızlı olduğundan, Power BI genellikle `destroy` öğesini çağırmaz.
