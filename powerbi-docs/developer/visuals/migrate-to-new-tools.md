---
title: powerbi-visuals-tools 3.x sürümüne geçiş
description: powerbi-visuals-tools'un yeni sürümünü kullanmaya başlama
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
manager: rkarlin
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: d9af0ab870732990201ab3478d71fdafa9e13439
ms.sourcegitcommit: 0cc594ebb78a6d0e88784673ed09f8aefd10c7a7
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76818836"
---
# <a name="migrate-to-the-new-powerbi-visuals-tools-version-3x"></a>Yeni powerbi-visuals-tools 3.*x* sürümüne geçiş yapın

Sürüm 3'ten başlayarak Power BI Görsel Araçları (powerbi-visuals-tools veya `pbiviz`), özel görseller oluşturmak için webpack'i kullanır.
Yeni sürüm, geliştiricilere görsel oluşturma aşamasında birçok iyileştirme sunmaktadır:

- Varsayılan olarak TypeScript 3.*x* sürümü kullanılır. TypeScript 1.5'ten başlayarak terminoloji değiştirilmiştir. [TypeScript modülleri hakkında daha fazla bilgi edinin](https://www.typescriptlang.org/docs/handbook/modules.html).

- ECMAScript 6 (ES6) modülleri desteklenir. [externalJS](migrate-to-new-tools.md#configure-loading-of-external-libraries) yerine ES6 içeri aktarma modüllerini kullanın.

- Veri Temelli Belgelerin ([D3v5](https://d3js.org/)) ve ES6 modülü tabanlı diğer kitaplıkların yeni sürümleri desteklenir.

- Azaltılmış paket boyutu. Webpack, kullanılmayan kodu kaldırmak için [ağaç sallama](https://webpack.js.org/guides/tree-shaking/) özelliğini kullanır. Bu özellik JavaScript kodunu azaltır ve görsel yükleme aşamasında daha iyi bir performans sunar.

- Geliştirilmiş API performansı.

- Globalize.js kitaplığı FormattingUtils ile [tümleştirilmiştir](migrate-to-new-tools.md#remove-the- globalizejs-library).

- Power BI Görsel Araçları, görselin kod tabanını görüntülemek için [webpack-bundle-analyzer](https://github.com/webpack-contrib/webpack-bundle-analyzer) kullanır.

Bu makalede Power BI Görsel Araçları'nın yeni sürümü için tüm geçiş adımları açıklanmıştır.

## <a name="backward-compatibility"></a>Geriye dönük uyumluluk

Yeni araçlarda eski görsel kod tabanı için geriye dönük uyumluluk bilgileri korunur ancak dış kitaplıkları yüklemek için bazı ek değişiklikler gerekebilir.

Modül sistemlerini destekleyen kitaplıklar, webpack modülleri olarak içeri aktarılır. Görselle ilgili diğer kitaplıklar ve kaynak kodu, bir modül halinde sarmalanır.

Eski Power BI Görsel Araçları'nda kullanılan JQuery ve Lodash gibi genel değişkenler artık kullanım dışı bırakılmıştır. Görselinizin eski kodu genel değişkenleri kullanıyorsa, görseliniz muhtemelen yeni araçlarla çalışmayacaktır.

Power BI Görsel Araçları'nın önceki sürümünde `powerbi.extensibility.visual` modülü altında bir görsel sınıfı tanımlamak gerekiyordu. Araçların yeni sürümünde bunun yerine ana TypeScript (.ts) dosyasında bir görsel sınıfı tanımlamanız gerekiyor. Bu dosya genellikle `src/visual.ts` olur.

## <a name="install-powerbi-visuals-tools"></a>powerbi-visuals-tools'u yükleme

Yeni araçları yüklemek için şu komutu çalıştırın:

```cmd
npm install -g powerbi-visuals-tools
```

Aşağıdaki kod, görsel projesi yeni araçlarla çalışacak şekilde güncelleştirildikten sonra [sampleBarChart görsel deposundaki](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/blob/471f103fcef9af93cff76cbac9c7fc67564acd4b/package.json#L15) `package.json` dosyasından alınmıştır:

```json
{
    "name": "visual",
    "version": "3.0.0",
    "scripts": {
        "pbiviz": "pbiviz",
        "start": "pbiviz start",
        "package": "pbiviz package",
        "lint": "tslint -r \"node_modules/tslint-microsoft-contrib\"  \"+(src|test)/**/*.ts\"",
        "test": "pbiviz package --resources --no-minify --no-pbiviz"
    },
    "devDependencies": {
        "@types/d3": "5.7.2",
        "d3": "5.12.0",
        "powerbi-visuals-api": "^2.6.1",
        "powerbi-visuals-tools": "^3.1.7",
        "powerbi-visuals-utils-dataviewutils": "^2.2.1",
        "powerbi-visuals-utils-formattingutils": "^4.4.2",
        "powerbi-visuals-utils-interactivityutils": "^5.6.0",
        "powerbi-visuals-utils-tooltiputils": "^2.3.1",
        "tslint": "^5.20.0",
        "tslint-microsoft-contrib": "^6.2.0"
    }
}
```

## <a name="install-the-power-bi-custom-visuals-api"></a>Power BI Özel Görseller API'sini yükleme

Yeni powerbi-visuals-tools sürümü tüm API sürümlerini içermez. Bunun yerine [powerbi-visuals-api](https://www.npmjs.com/package/powerbi-visuals-api) paketinin belirli bir sürümünü yüklemeniz gerekir. Power BI özel görsellerinizin API sürümüyle eşleşen paket sürümünü seçin. Paket, Power BI Özel Görseller API'si için tüm tür tanımlarını sağlar.

Şu komutu çalıştırarak proje bağımlılıklarınıza `powerbi-visuals-api` ekleyin:

```cmd
npm install --save-dev powerbi-visuals-api
```

Ayrıca webpack, `powerbi-visuals-api` içindeki türleri otomatik olarak dahil ettiğinden eski API türü tanımı bağlantılarını kaldırın. [package.json](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/blob/471f103fcef9af93cff76cbac9c7fc67564acd4b/package.json#L14) ve [tsconfig.json](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/blob/471f103fcef9af93cff76cbac9c7fc67564acd4b/tsconfig.json#L14) içinde de değişiklikler yapılmıştır.

## <a name="update-tsconfigjson"></a>tsconfig.json dosyasını güncelleştirme

Dış modülleri kullanmak için `out` seçeneğini `outDir` olarak değiştirin. Örneğin `"out": "./.tmp/build/visual.js",` yerine `"outDir": "./.tmp/build/",` kullanın.

Bu gereklidir çünkü TypeScript dosyaları JavaScript dosyalarına bağımsız olarak derlenir. İşte bu nedenle artık çıkış olarak visual.js dosyasını belirtmeniz gerekmez.

Ayrıca çıkış olarak modern JavaScript kullanmak istiyorsanız `target` seçeneğini de `ES6` olarak değiştirebilirsiniz. Bu değişiklik [isteğe bağlıdır](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/blob/471f103fcef9af93cff76cbac9c7fc67564acd4b/tsconfig.json#L7).

## <a name="update-custom-visuals-utilities"></a>Özel görseller yardımcı programlarını güncelleştirme

[powerbi-visuals-utils](https://www.npmjs.com/search?q=powerbi-visuals-utils) paketlerinden birini kullanıyorsanız onları da son sürüme güncelleştirmeniz gerekir. Bunu yapmak için şu komutu çalıştırın:

```cmd
npm install powerbi-visuals-utils-<UTILNAME> --save
```

Örneğin, TypeScript'in dış modülleriyle yeni sürümü almak için şunu çalıştırın: 

```cmd
npm install powerbi-visuals-utils-dataviewutils --save
```

Tüm `powerbi-visuals-utils` paketlerini kullanan bir örnek için [MekkoChart deposunu](https://github.com/Microsoft/powerbi-visuals-mekkochart) inceleyin.

## <a name="remove-the-globalizejs-library"></a>Globalize.js kitaplığını kaldırma

[powerbi-visuals-utils-formattingutils@4.3](https://www.npmjs.com/package/powerbi-visuals-utils-formattingutils) bileşeninin yeni sürümü Globalize.js ile birlikte gelir. Bu nedenle bu kitaplığı projenize el ile eklemeniz gerekmez. Tüm gerekli yerelleştirmeler son pakete otomatik olarak eklenir.

## <a name="configure-loading-of-external-libraries"></a>Dış kitaplıkların yüklenmesini yapılandırma

Yeni JavaScript dosyalarını `pbiviz.json` öğesinin `externalJS` dizisindeki kitaplıkların arkasına ekleyin. Örnek:

```JSON
"externalJS": [
    ...
    "node_modules/lodash/lodash.min.js",
    "externalJS/init.lodash.js",
    ...
]
```

Kitaplıkları kaynak kodunuza aktarın. Örneğin `lodash-es` için şu deyimi kullanın:

```JS
import * as _ from "lodash-es";
```

Yukarıdaki örnekte `_`, `lodash` kitaplığının genel değişkenidir.

## <a name="make-changes-in-the-sources-of-your-visuals"></a>Görsellerinizin kaynaklarında değişiklik yapma

Yapmanız gereken temel değişiklik, iç modülleri dış modüllere dönüştürmektir. İç modüllerin içinde dış modül kullanamazsınız.

Yapılacak değişikliklerin ayrıntılı açıklaması aşağıda verilmiştir. Değişiklikler, Çubuk Grafik özel görsel kodu örneği bağlamında açıklanmıştır:

1. [Kaynak kodun](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/commit/72ec605ce6a311a6cc004453b07973b6ed5e61f9#diff-433142f7814fee940a0ffc98dc75bfcbL1-L3) tüm dosyalarındaki tüm modül tanımlarını kaldırın:

    ```typescript
    module powerbi.extensibility.visual {
        ...
    }
    ```

2. [Power BI özel görsel API'si tanımlarını içeri aktarın](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/commit/72ec605ce6a311a6cc004453b07973b6ed5e61f9#diff-433142f7814fee940a0ffc98dc75bfcbR4):

    ```typescript
    import powerbi from "powerbi-visuals-api";
    ```

3. `powerbi` iç modülünden gerekli arabirimleri veya sınıfları [içeri aktarın](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/commit/72ec605ce6a311a6cc004453b07973b6ed5e61f9#diff-433142f7814fee940a0ffc98dc75bfcbR12-R35).

    ```typescript
    import PrimitiveValue = powerbi.PrimitiveValue; 
    import VisualUpdateOptions = powerbi.extensibility.visual.VisualUpdateOptions; 
    import VisualConstructorOptions = powerbi.extensibility.visual.VisualConstructorOptions; 
    import IVisualHost = powerbi.extensibility.visual.IVisualHost; 
    import IColorPalette = powerbi.extensibility.IColorPalette; 
    import IVisual = powerbi.extensibility.visual.IVisual; 
    import VisualObjectInstance = powerbi.VisualObjectInstance; 
    import VisualObjectInstanceEnumeration = powerbi.VisualObjectInstanceEnumeration; 
    import EnumerateVisualObjectInstancesOptions = powerbi.EnumerateVisualObjectInstancesOptions; 
    import Fill = powerbi.Fill; 
    import VisualTooltipDataItem = powerbi.extensibility.VisualTooltipDataItem; 
    import ISelectionManager = powerbi.extensibility.ISelectionManager; 
    ```

4. [D3.js kitaplığını içeri aktarın](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/commit/72ec605ce6a311a6cc004453b07973b6ed5e61f9#diff-433142f7814fee940a0ffc98dc75bfcbR2):

    ```typescript
    import * as d3 from "d3";
    ```

    Veya yalnızca gerekli D3 kitaplık modüllerini içeri aktarın:

    ```typescript
    import { max, min } from "d3-array";
    ```

5. [Görsel projesinde tanımlanan yardımcı programları, sınıfları ve arabirimleri](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/commit/72ec605ce6a311a6cc004453b07973b6ed5e61f9#diff-433142f7814fee940a0ffc98dc75bfcbR38-R41) ana kaynak dosyasına aktarın:

    ```typescript
    import { getLocalizedString } from "./localization/localizationHelper";
    import { getValue, getCategoricalObjectValue } from "./objectEnumerationUtility";
    import {
        ITooltipServiceWrapper,
        TooltipEventArgs,
        createTooltipServiceWrapper
    } from "./tooltipServiceWrapper";
    ```

### <a name="import-css-styles"></a>CSS stillerini içeri aktarma

Araçların yeni sürümü `CSS` ve `Less` stillerini doğrudan TypeScript koduna aktarmanızı sağlar. Daha önce kullanılan [stiller bölümü](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/blob/471f103fcef9af93cff76cbac9c7fc67564acd4b/pbiviz.json#L21) artık derleyici tarafından yok sayılır.

Stil sayfanızı kullanmak için ana TypeScript (.ts) dosyasını açın ve şu satırı ekleyin:  

```typescript
import "./../style/visual.less";
```  

`CSS` ve `Less` stilleriniz otomatik olarak derlenir.

### <a name="externaljs-section-in-pbivizjson"></a>pbiviz.json içinde externalJS bölümü

webpack, içeri aktarılan tüm kitaplıkları içerdiğinden araçlar, görsel paketine yüklenecek [`externalJS` kitaplığı listesine ihtiyaç duymaz](https://github.com/microsoft/PowerBI-visuals-sampleBarChart/commit/72ec605ce6a311a6cc004453b07973b6ed5e61f9#diff-a1a7bbee7e7d2f9d449f4b534532bcf2R20).

> [!NOTE]
> `pbiviz.json` içinde `externalJS` bölümünü boş bırakın.

Görsel paketini oluşturmak için tipik `npm run package` komutunu veya geliştirme sunucusunu başlatmak için `npm run start` komutunu kullanın.

## <a name="update-the-d3js-library-to-version-5"></a>D3.js kitaplığını sürüm 5'e güncelleştirme

Yeni görsel araçlarıyla D3.js kitaplığının yeni sürümünü kullanmaya başlayabilirsiniz. Görsel projenizde D3'ü güncelleştirmek için şu komutları çalıştırın:

- Yeni D3.js'yi yüklemek için `npm install --save d3@5`.

- D3.js'de yeni tür tanımlarını yüklemek için `npm install --save-dev @types/d3@5`.

> [!IMPORTANT]
> D3 sürüm 5 birçok yeni özelliğe sahiptir.

Kodunuzu yeni D3.js ile çalışacak şekilde değiştirin:

- `d3.Selection<T>` arabirimi `Selection<GElement extends BaseType, Datum, PElement extends BaseType, PDatum>` olarak [değişmiştir](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/af2ff9fb0fc70bd94ea0c604d75a362411d5abeb#diff-433142f7814fee940a0ffc98dc75bfcbR157).

- Tek bir `attr` yöntemi çağrısı kullanarak birden çok öznitelik uygulayamazsınız. Bunun yerine `attr` [için her özniteliği ayrı bir çağrıda geçirmeniz](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/af2ff9fb0fc70bd94ea0c604d75a362411d5abeb#diff-433142f7814fee940a0ffc98dc75bfcbR278) gerekir. [`style` yöntemine de ayrı çağrılar](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/af2ff9fb0fc70bd94ea0c604d75a362411d5abeb#diff-433142f7814fee940a0ffc98dc75bfcbR247) yapın.

- D3.js sürüm 4, yeni `merge` yöntemini kullanıma sunmuştur. Bu yöntem veri birleştirme işlemi sonrasında `enter` ve `update` seçimlerini birleştirmek için yaygın olarak kullanılır. D3 bileşenini doğru şekilde kullanmak için [`merge` yöntemini çağırın](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/83fe8d52d362dccd0034dd8e32c94080d9376b29#diff-433142f7814fee940a0ffc98dc75bfcbR272).

D3.js kitaplığındaki değişiklikler hakkında [daha fazla bilgi edinin](https://github.com/d3/d3/blob/master/CHANGES.md).

## <a name="install-babel-and-core-js"></a>Babel ve core-js'yi yükleme

Sürüm 3.1'den başlayarak, görsel araçları modern JavaScript kodunu eski ECMAScript 5'e (ES5) derleyerek geniş bir yelpazedeki tarayıcıları desteklemek için Babel kullanır.

Babel seçeneği varsayılan olarak etkinleştirilir ancak [`core-js`](https://www.npmjs.com/package/core-js) paketini el ile içeri aktarmanız gerekir. Paketi yüklemek için şu komutu çalıştırın:

```cmd
npm install --save core-js
```

Ardından paketi görsel kodunun başlangıç noktasında içeri aktarın. Bu genellikle "src/visual.ts" dosyasıdır.

```JS
import "core-js/stable";
```

[Belgelerde](https://babeljs.io/docs/en/) Babel hakkında daha fazla bilgi edinin.
