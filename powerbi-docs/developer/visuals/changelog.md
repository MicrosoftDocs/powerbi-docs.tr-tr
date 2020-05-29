---
title: Power BI görselleri API’si değişiklik günlüğü
description: Bu makalede Power BI görselleri API'sinin farklı sürümleri arasındaki temel farklar açıklanmaktadır.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 03/13/2019
ms.openlocfilehash: fa8759d7edb519240140263bcd01bfdddd9c7d86
ms.sourcegitcommit: bfc2baf862aade6873501566f13c744efdd146f3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83141070"
---
# <a name="power-bi-visuals-api-changelog"></a>Power BI görselleri API’si değişiklik günlüğü
Bu sayfada API sürümleri genel hatlarıyla özetlenmiştir. Burada listelenen sürümlerin kararlı sürümler olduğu kabul edilir ve bu sürümler değişmeyecektir.

## <a name="api-v26"></a>API v2.6
  * Güncelleştirme seçeneğine **isInFocus**, görsel konak için de **switchFocusModeState** yöntemi ekler
  * **subtotals** özelleştirmesini destekler

## <a name="api-v25"></a>API v2.5
  * **[Analiz Bölmesi](./analytics-pane.md)** desteği sunar
  * `SelectionIdBuilder` **withMatrixNode** ve **withTable** yöntemlerini destekler
  * `DataRepetitionSelector` arabirimini desteklemez, yerini `data.CustomVisualOpaqueIdentity` arabirimine bırakmıştır

## <a name="api-v23"></a>API v2.3
  * **[Giriş Sayfası API'si](./landing-page.md)**
  * **[Yerel Depolama API’si](./local-storage.md)**
  * **[Tanımlama grubu filtresi API’si (çok sütunlu filtre)](./filter-api.md#the-tuple-filter-api-multi-column-filter)**
  * **[Olayları İşleme API'si](./event-service.md#render-events-in-power-bi-visuals)**

## <a name="api-v22"></a>API v2.2
  * **[JSON Filtresini DataView’dan geri yükleme](./filter-api.md#restore-the-json-filter-from-the-data-view)** desteği sunar
  * **[ContextMenu API'si](./context-menu.md)**

## <a name="api-v21"></a>API v2.1
  * Performans iyileştirmeleri:
    * Daha kısa yükleme süreleri
    * Daha küçük bellek ayak izi
    * İyileştirilmiş veri ve olay işlemleri  

**Sürüm notları**
* Yeniden düzenlenmiş filtreleme API'leri, API 2.2 sürümünde kullanıma sunulacaktır, API 2.1 sürümünde desteklenmez.
* Görseller yalnızca özelliklerinde belirtilmiş olan dataView türünü alır. Bu güncelleştirmenin sonucunda birden fazla dataView türü kullanmış olan görseller bozulacaktır.
* `DataViewScopeIdentity` arabirimini desteklemez, yerini `data.DataRepetitionSelector` arabirimine bırakmıştır. `DataViewScopeIdentity` arabiriminin anahtar özelliğini kullandıysanız bunu `JSON.stringify(identity)` ile değiştirebilirsiniz.
* `undefined`, dataView içindeki `null` ile değiştirilmiştir. `var item in myArray` kullanarak bir dizide yinelendiğinde `undefined` öğesini atlar ancak `null` öğesini atlamaz. Bu deseni kullanan görseller, bu güncelleştirmeden sonra bozulabilir. Dizilerde `null` olup olmadığını kontrol etmeyi unutmayın:
   ```typescript
   for (var item in myArray) {
     if (!item) {
       continue;
     }
     console.log(item);
   }
   ```
* `proto` özelliği artık dataView içinde gizli meta veriler/veriler depolamaz. Bu güncelleştirme sonucunda özelliklere `proto` aracılığıyla erişen görseller bozulabilir.

## <a name="api-v113"></a>API v1.13
* **[Dilimleyicileri Eşitleme](./enable-sync-slicers.md)** desteği sunar. Bu özelliğin PBI geçerli kod durumu nedeniyle yalnızca tek alanlı dilimleyicileri desteklediğini unutmayın. [Daha fazla bilgi edinin](/power-bi/desktop-slicers).
* Erişilebilirlik: [Yüksek karşıtlık desteği](./high-contrast-support.md) 
* Erişilebilirlik: Klavye Odağı bayrağına izin ver

## <a name="api-v112"></a>API v1.12
* Temaları destekler
* **[fetchMoreData](./fetch-more-data.md)** desteği sunar. **Daha Fazla Veri Getirme API'sinin** 30 bin veri noktası sabit sınırını aşabildiğini unutmayın.
* **[Tuval Araç İpuçları API'si](./add-tooltips.md#add-report-page-tooltips)**

## <a name="api-v111"></a>API v1.11
* **[Filtre Yöneticisi API'si](./filter-api.md)**
* **[Yer işaretlerini](./bookmarks-support.md)** destekler 

## <a name="api-v110"></a>API v1.10
* `ILocalizationManager` ekler
* **Kimlik Doğrulama API'si**

## <a name="api-v19"></a>API v1.9
* **[launchUrl API'si](./launch-url.md)**

## <a name="api-v18"></a>API v1.8
* Özellikler şemasında yeni **fillRule** (gradyan) türünü destekler
* Nesne özellikleri için özellikler şemasında **rule** özelliğini destekler

## <a name="api-v17"></a>API v1.7
* **[RESJSON](./localization.md#resource-file)** desteği sunar

## <a name="api-v162"></a>API v1.6.2
* Görsel içi düzenleme moduna girmek için **[Düzenleme modu](./advanced-edit-mode.md)** desteği sunar
* HTML tabanlı **[Etkileşimli (html) R Power BI görsellerini](https://microsoft.github.io/PowerBI-visuals/tutorials/building-r-powered-custom-visual/creating-r-visuals.md)** destekler

## <a name="api-v150"></a>API v1.5.0
* Görsellerle etkileşim kurmak için **[Etkileşimlere izin ver](./visuals-interactions.md)** işlevini destekler

## <a name="api-v140"></a>API v1.4.0
* **[Yerelleştirme](./localization.md)** desteği sunar

## <a name="api-v130"></a>API v1.3.0
* **[Araç İpuçları](./add-tooltips.md)** desteği sunar

## <a name="api-v120"></a>API v1.2.0
* Görselinizde kullanılan renkleri yönetmek için **colorPalette** ekler.
* **Çoklu seçimi** destekler. selectionManager, `SelectionId` dizisini kabul edebilir.
* R betiklerini kullanarak **[R görsellerini](https://microsoft.github.io/PowerBI-visuals/tutorials/building-r-powered-custom-visual/creating-r-visuals.md)** destekler

## <a name="api-v110"></a>API v1.1.0
* iFrame'de görseller için hata ayıklamayı destekler
* iFrame'in daha hızlı başlatılması için basit bir korumalı alan ekler
* [Capabilities.objects öğesinin "text" türünü desteklememesi](https://github.com/Microsoft/PowerBI-visuals-tools/issues/12) sorununu düzeltir
* Görsel API türü tanımlarını ve şemasını güncelleştirmek için `pbiviz update` desteği sunar
* Görselleri belirli bir API sürümüyle oluşturmak için `pbiviz new` içinde `--api-version` bayrağını destekler
* API v1.2.0 alfa sürümünü destekler

**Görsel Konak**
* Veri seçimi için kullanılan benzersiz tanıtıcılar oluşturmak için **createSelectionIdBuilder** ekler
* Görselin seçim durumunu yönetmek ve değişiklikleri görsel konağa iletmek için **createSelectionManager** ekler
* Görsellerde kullanılacak varsayılan **colors** dizisi ekler

## <a name="api-v100"></a>API v1.0.0
* İlk API sürümü