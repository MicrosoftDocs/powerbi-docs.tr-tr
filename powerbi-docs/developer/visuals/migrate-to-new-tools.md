---
title: powerbi-visuals-tools 3.x'e geçiş
description: powerbi-visuals-tools'un yeni sürümünü kullanmaya başlama
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: cc554bff1cbd248ccd69a80ee47b60af981cdab1
ms.sourcegitcommit: f7b28ecbad3e51f410eff7ee4051de3652e360e8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74061834"
---
# <a name="migrate-to-the-new-powerbi-visuals-tools-3xx"></a>Yeni powerbi-visuals-tools 3.x.x'e geçme

Sürüm 3'ten başlayarak Power BI Görsel Araçları, Özel Görseller oluşturmak için Webpack'i kullanır.
Yeni sürüm geliştiricilere görsel oluşturmaları için birçok yeni fırsat getirir:

* Varsayılan olarak TypeScript v3.x.x. TypeScript 1.5'ten başlayarak terminoloji değiştirilmiştir. [TypeScript modülleri hakkında daha fazla bilgi edinin](https://www.typescriptlang.org/docs/handbook/modules.html).

* ES6 modülleri desteklenir. Artık [externalJS](migrate-to-new-tools.md#fix-loading-external-libraries)'yi kullanmanız gerekmez, onun yerine ES6 içeri aktarmalarını kullanın.

* [D3v5](https://d3js.org/)'in ve ES6 modülü tabanlı diğer kitaplıkların yeni sürümleri desteklenir.

* Azaltılmış paket boyutu. Webpack kullanılmayan kodu kaldırmak için [Ağaç Sallama](https://webpack.js.org/guides/tree-shaking/) özelliğini kullanır. JS'nin kodunu azaltır ve sonuç olarak görseli yüklerken daha iyi bir performans elde edersiniz.

* Geliştirilmiş API performansı.

* Globalize.js kitaplığı formatting-utils içine [tümleştirilmiştir](migrate-to-new-tools.md#remove-globalizejs-library).

* Araçlar görselin kod tabanını görüntülemek için [webpack-bundle-analyzer](https://github.com/webpack-contrib/webpack-bundle-analyzer) kullanır.

Power BI Görsel Araçları'nın yeni sürümü için tüm geçiş adımları aşağıda açıklanmıştır.

## <a name="backward-compatibility"></a>Geriye dönük uyumluluk

Yeni araçlarda eski görsel kod tabanı için geriye dönük uyumluluk korunur ama dış kitaplıkları yüklemek için bazı ek değişiklikler gerekebilir.

Modül sistemlerini destekleyen kitaplıklar Webpack modülleri olarak içeri aktarılır. Diğer tüm kitaplıklar ve görsel kaynak kodu tek modülde sarmalanır.

Önceki pbiviz araçlarında kullanılan JQuery ve Lodash gibi genel değişkenler artık kullanım dışı bırakılmıştır. Diğer bir deyişle eski görsel kodu genel değişkenlere dayanıyorsa, bu durumda görsel bozulabilir.

Power BI Görsel Araçları'nın önceki sürümünde `powerbi.extensibility.visual` modülü altında bir görsel sınıfı tanımlamak gerekiyordu.

## <a name="how-to-install-powerbi-visuals-tools"></a>powerbi-visuals-tools nasıl yüklenir?

Yeni araç kümesi komut yürütülerek yüklenebilir

```cmd
npm install -g powerbi-visuals-tools
```

sampleBarChart görseli örneği ve `package.json` dosyasında ilgili [değişiklikler](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/package.json#L16):

```json
{
    "name": "visual",
    "version": "1.2.3",
    "scripts": {
        "pbiviz": "pbiviz",
        "start": "pbiviz start",
        "lint": "tslint -r \"node_modules/tslint-microsoft-contrib\"  \"+(src|test)/**/*.ts\"",
        "test": "pbiviz package --resources --no-minify --no-pbiviz"
    },
    "devDependencies": {
      "@types/d3": "5.0.0",
      "d3": "5.5.0",
      "powerbi-visuals-tools": "^3.1.0",
      "tslint": "^4.4.2",
      "tslint-microsoft-contrib": "^4.0.0"
    }
}
```

## <a name="how-to-install-power-bi-custom-visuals-api"></a>Power BI Özel Görseller API'sini yükleme

powerbi-visual-tools'un yeni sürümü tüm API sürümlerini içermez. Bunun yerine geliştiricinin [`powerbi-visuals-api`](https://www.npmjs.com/package/powerbi-visuals-api) paketinin belirli bir sürümünü yüklemesi gerekir. Paketin sürümü Power BI Özel Görseller'in API sürümüyle eşleşir ve Power BI Özel Görseller API'sinin tüm tür tanımlarını sağlar.

`npm install --save-dev powerbi-visuals-api` komutunu yürüterek projenin bağımlılıklarına `powerbi-visuals-api` öğesini ekleyin.
Eski API türü tanımlarının bağlantısını da kaldırmanız gerekir. Çünkü `powerbi-visuals-api` türleri Webpack tarafından otomatik olarak eklenir. Buna karşılık gelen değişiklikler `package.json` dosyasının [bu](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/package.json#L14) satırındadır.

## <a name="update-tsconfigjson"></a>`tsconfig.json` dosyasını güncelleştirme

Dış modülleri kullanmak için `out` seçeneğini `outDir` olarak değiştirmelisiniz.
`"out": "./.tmp/build/visual.js",` yerine `"outDir": "./.tmp/build/",`.

Bu gereklidir çünkü TypeScript dosyaları JavaScript dosyalarına bağımsız olarak derlenir. İşte bu nedenle artık çıkış olarak visual.js dosyasını belirtmeniz gerekmez.

Ayrıca çıkış olarak modern JavaScript kullanmak istiyorsanız `target` seçeneğini de `ES6` olarak değiştirebilirsiniz. [Bu isteğe bağlıdır](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/tsconfig.json#L6).

## <a name="update-custom-visuals-utils"></a>Özel Görseller yardımcı programlarını güncelleştirme

[powerbi-visuals-utils](https://www.npmjs.com/search?q=powerbi-visuals-utils) içinden kullandıklarınız varsa onları da en son sürüme güncelleştirmelisiniz.

`npm install powerbi-visuals-utils-<UTILNAME> --save` komutunu yürütün ve (örneğin `npm install powerbi-visuals-utils-dataviewutils --save` ) TypeScript'in dış modülleriyle yeni sürümü alın.

MekkoChart [deposunda](https://github.com/Microsoft/powerbi-visuals-mekkochart) örnek bulabilirsiniz.
Bu görsel tüm yardımcı programları kullanır.

## <a name="remove-globalizejs-library"></a>Globalize.js kitaplığını kaldırma

Yeni [powerbi-visuals-utils-formattingutils@4.3](https://www.npmjs.com/package/powerbi-visuals-utils-formattingutils) sürümü globalize.js ile birlikte gelir.
Projeye bu kitaplığı el ile eklemeniz gerekmez.
Tüm gerekli yerelleştirmeler son pakete otomatik olarak eklenir.

## <a name="fix-loading-external-libraries"></a>Dış kitaplıkların yüklenmesini düzeltme

Bunun yerine `pbiviz.json` dosyasının `externalJS` dizisine kitaplıklardan sonra yeni JS dosyasını ekleyin. Örnek:

```JSON
"externalJS": [
    ...
    "node_modules/lodash/lodash.min.js",
    "externalJS/init.lodash.js",
    ...
]
```

Kaynakta kitaplıkları içeri aktarın. `lodash-es` örneği:

```JS
import * as _ from "lodash-es";
```

burada `_`, `lodash` kitaplığı için genel değişkendir.

## <a name="changes-in-the-visuals-sources"></a>Görsellerin kaynaklarındaki değişiklikler

Ana değişiklik, iç modüllerin içinde dış modülleri kullanamayacağınız için iç modülleri dış modüllere dönüştürmektir.

Söz konusu değişiklikler Örnek Çubuk Grafiğe uygulanan değişiklikleri açıklar

Değişikliklerin ayrıntılı açıklamaları aşağıda verilmiştir:

1. [Kaynak kodun](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/src/barChart.ts#L153) her dosyasından tüm modüllerin tanımlarını kaldırma

    ```typescript
    module powerbi.extensibility.visual {
        ...
    }
    ```

2. [Power BI özel görsel API'si tanımlarını içeri aktarma](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/src/barChart.ts#L2) .

    ```typescript
    import powerbi from "powerbi-visuals-api";
    ```

3. `powerbi` iç modülünden gerekli arabirimleri veya sınıfları [içeri aktarma](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/src/barChart.ts#L12-L23).

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

4. D3.js kitaplığını [içeri aktarma](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/src/barChart.ts#L1)

    ```typescript
    import * as d3 from "d3";
    ```

    Veya yalnızca gereken d3 kitaplık modüllerini içeri aktarma

    ```typescript
    import { max, min } from "d3-array";
    ```

5. Görsel projesinde tanımlanan yardımcı programları, sınıfları, arabirimleri ana kaynak dosyaya [içeri aktarma](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/src/barChart.ts#L4-L10)

    ```typescript
    import { getLocalizedString } from "./localization/localizationHelper";
    import { getValue, getCategoricalObjectValue } from "./objectEnumerationUtility";
    import {
        ITooltipServiceWrapper,
        TooltipEventArgs,
        createTooltipServiceWrapper
    } from "./tooltipServiceWrapper";
    ```

### <a name="import-css-styles"></a>CSS Stillerini içeri aktarma

Araçların yeni sürümü geliştiricilerin CSS, LESS stilini doğrudan TypeScript koduna indirmesine olanak tanır.

Dolayısıyla daha önce kullanılan [stiller bölümü](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/pbiviz.json#L22) artık derleyici tarafından yoksayılır.

Stil sayfanızı kullanmak için ana ts dosyasını açın ve aşağıdaki satırı ekleyin:  

```typescript
import "./../style/visual.less";
```  

CSS, LESS stilleriniz otomatik olarak derlenir.  

### <a name="externaljs-section-in-pbivizjson"></a>pbiviz.json içinde externalJS bölümü

Araçlara görsel paketine yüklemek için bir `externalJS` listesi [gerekmez](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/sample-next/pbiviz.json#L20). Çünkü webpack içeri aktarılan tüm kitaplıkları içerir.

**pbivi.json'daki externalJS bölümü boş olmalıdır.**

Görsel paketini oluşturmak için tipik `npm run package` komutlarını veya geliştirme sunucusunu başlatmak için `npm run start` komutlarını çağırın.

## <a name="updating-d3js-library-to-version-5"></a>D3.js kitaplığını sürüm 5'e güncelleştirme

Yeni araçlarla D3.js kitaplığının yeni sürümünü kullanmaya başlayabilirsiniz.

Görsel projenizde D3'ü güncelleştirmek için komutları çağırma

Yeni D3.js'yi yüklemek için `npm install --save d3@5`.

D3.js'de yeni tür tanımlarını yüklemek için `npm install --save-dev @types/d3@5`.

Bazı hataya neden olan değişiklikler vardır ve yeni D3.js'yi kullanmak için kodunuzda değişiklik yapmanız gerekir.

1. `d3.Selection<T>` arabirimi `Selection<GElement extends BaseType, Datum, PElement extends BaseType, PDatum>` olarak [değişmiştir](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/af2ff9fb0fc70bd94ea0c604d75a362411d5abeb#diff-433142f7814fee940a0ffc98dc75bfcbR157)

2. Tek bir `attr` yöntemi çağrısıyla birkaç öznitelik uygulayamazsınız. Her özniteliği `attr` yönteminin farklı bir çağrısında [geçirmeniz gerekir](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/af2ff9fb0fc70bd94ea0c604d75a362411d5abeb#diff-433142f7814fee940a0ffc98dc75bfcbR278). `style` yöntemi için de [benzer](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/af2ff9fb0fc70bd94ea0c604d75a362411d5abeb#diff-433142f7814fee940a0ffc98dc75bfcbR247) bir durum geçerlidir.

3. D3.js v4'te yeni birleştirme yöntemi tanıtılmıştır. Bu yöntem veri birleştirme sonrasında girme ve güncelleştirme seçimlerini birleştirmek için yaygın olarak kullanılır. d3'ü düzgün kullanmak için [birleştirme yöntemini çağırın](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/commit/83fe8d52d362dccd0034dd8e32c94080d9376b29#diff-433142f7814fee940a0ffc98dc75bfcbR272).

D3.js kitaplığındaki değişiklikler hakkında [daha fazla bilgi edinin](https://github.com/d3/d3/blob/master/CHANGES.md).

## <a name="babel"></a>Babel

Sürüm 3.1'den başlayarak, araçlar yeni modern JS kodunu eski ES5'e derleyerek geniş bir yelpazedeki tarayıcıları desteklemek için Babel kullanır.

Bu seçenek varsayılan olarak etkinleştirilir ama [`@babel/polyfill`](https://babeljs.io/docs/en/babel-polyfill) paketini el ile içeri aktarmanız gerekir.

Paketi yüklemek için şu komutu yürütün

`npm install --save @babel/polyfill`

ve paketi görsel kodunun (genellikle 'src/visual.ts' dosyası) başlangıç noktasında içeri aktarın:

`import "@babel/polyfill";`

[Belgelerde](https://babeljs.io/docs/en/) Babel hakkında daha fazla bilgi edinin.

Son olarak, görselin kod tabanını görüntülemek için [webpack-visualizer](https://github.com/chrisbateman/webpack-visualizer) komutunu çalıştırın.  

![Görsel kodu istatistikleri](./media/webpack-stats.png)
