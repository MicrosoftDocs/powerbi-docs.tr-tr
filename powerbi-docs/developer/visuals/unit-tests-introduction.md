---
title: Birim testi tanıtımı
description: Power BI Görselleri projesi için birim testleri yazma
author: zBritva
ms.author: v-ilgali
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: tutorial
ms.date: 06/18/2019
ms.openlocfilehash: 4b16eaad9b541bf6e5d8df49ffda99d9bbd5bbf2
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2019
ms.locfileid: "68424551"
---
# <a name="tutorial-add-unit-tests-for-power-bi-visual-projects"></a>Öğretici: Power BI Görsel projeleri için birim testleri ekleme

Bu öğreticide, Power BI görselleriniz için birim testleri yazmayla ilgili temel bilgiler açıklanmaktadır.

Bu öğreticide şunları deneyeceğiz:

* Test çalıştırıcısı karma.js ve test çerçevesi - jasmine.js’yi kullanma
* powerbi-visuals-utils-testutils paketini kullanma
* Sahte dosyalar kümesinin Power BI görselleri için birim testini kolaylaştırmaya nasıl yardımcı olduğu.

## <a name="prerequisites"></a>Önkoşullar

* Power BI görselleri projeniz var
* Node.JS ortamı yapılandırıldı

## <a name="install-and-configure-karmajs-and-jasmine"></a>karma.js ve jasmine'yi yükleyip yapılandırın

`devDependencies` bölümünde gerekli kitaplıkları package.json dosyasına ekleyin:

```json
"@babel/polyfill": "^7.2.5",
"@types/d3": "5.5.0",
"@types/jasmine": "2.5.37",
"@types/jasmine-jquery": "1.5.28",
"@types/jquery": "2.0.41",
"@types/karma": "3.0.0",
"@types/lodash-es": "4.17.1",
"coveralls": "3.0.2",
"istanbul-instrumenter-loader": "^3.0.1",
"jasmine": "2.5.2",
"jasmine-core": "2.5.2",
"jasmine-jquery": "2.1.1",
"jquery": "3.1.1",
"karma": "3.1.1",
"karma-chrome-launcher": "2.2.0",
"karma-coverage": "1.1.2",
"karma-coverage-istanbul-reporter": "^2.0.4",
"karma-jasmine": "2.0.1",
"karma-junit-reporter": "^1.2.0",
"karma-sourcemap-loader": "^0.3.7",
"karma-typescript": "^3.0.13",
"karma-typescript-preprocessor": "0.4.0",
"karma-webpack": "3.0.5",
"puppeteer": "1.17.0",
"style-loader": "0.23.1",
"ts-loader": "5.3.0",
"ts-node": "7.0.1",
"tslint": "^5.12.0",
"webpack": "4.26.0"
```

Paket hakkında daha fazla bilgi edinmek için aşağıdaki açıklamaya bakın.

`package.json` dosyasını kaydedin ve şu `package.json` konumundaki komut satırında yürütün:

```cmd
npm install
```

Paket yöneticisi, `package.json` dosyasına eklenen tüm yeni paketleri yükler

Birim testlerini çalıştırmak için test çalıştırıcısını ve `webpack` yapılandırma dosyasını yapılandırmamız gerekir. Burada bulabileceğiniz yapılandırma dosyası örneği

`test.webpack.config.js` örneği:

```typescript
const path = require('path');
const webpack = require("webpack");

module.exports = {
    devtool: 'source-map',
    mode: 'development',
    optimization : {
        concatenateModules: false,
        minimize: false
    },
    module: {
        rules: [
            {
                test: /\.tsx?$/,
                use: 'ts-loader',
                exclude: /node_modules/
            },
            {
                test: /\.json$/,
                loader: 'json-loader'
            },
            {
                test: /\.tsx?$/i,
                enforce: 'post',
                include: /(src)/,
                exclude: /(node_modules|resources\/js\/vendor)/,
                loader: 'istanbul-instrumenter-loader',
                options: { esModules: true }
            },
            {
                test: /\.less$/,
                use: [
                    {
                        loader: 'style-loader'
                    },
                    {
                        loader: 'css-loader'
                    },
                    {
                        loader: 'less-loader',
                        options: {
                            paths: [path.resolve(__dirname, 'node_modules')]
                        }
                    }
                ]
            }
        ]
    },
    externals: {
        "powerbi-visuals-api": '{}'
    },
    resolve: {
        extensions: ['.tsx', '.ts', '.js', '.css']
    },
    output: {
        path: path.resolve(__dirname, ".tmp/test")
    },
    plugins: [
        new webpack.ProvidePlugin({
            'powerbi-visuals-api': null
        })
    ]
};
```

`karma.conf.ts` örneği

```typescript
"use strict";

const webpackConfig = require("./test.webpack.config.js");
const tsconfig = require("./test.tsconfig.json");
const path = require("path");

const testRecursivePath = "test/visualTest.ts";
const srcOriginalRecursivePath = "src/**/*.ts";
const coverageFolder = "coverage";

process.env.CHROME_BIN = require("puppeteer").executablePath();

import { Config, ConfigOptions } from "karma";

module.exports = (config: Config) => {
    config.set(<ConfigOptions>{
        mode: "development",
        browserNoActivityTimeout: 100000,
        browsers: ["ChromeHeadless"], // or Chrome to use locally installed Chrome browser
        colors: true,
        frameworks: ["jasmine"],
        reporters: [
            "progress",
            "junit",
            "coverage-istanbul"
        ],
        junitReporter: {
            outputDir: path.join(__dirname, coverageFolder),
            outputFile: "TESTS-report.xml",
            useBrowserName: false
        },
        singleRun: true,
        plugins: [
            "karma-coverage",
            "karma-typescript",
            "karma-webpack",
            "karma-jasmine",
            "karma-sourcemap-loader",
            "karma-chrome-launcher",
            "karma-junit-reporter",
            "karma-coverage-istanbul-reporter"
        ],
        files: [
            "node_modules/jquery/dist/jquery.min.js",
            "node_modules/jasmine-jquery/lib/jasmine-jquery.js",
            {
                pattern: './capabilities.json',
                watched: false,
                served: true,
                included: false
            },
            testRecursivePath,
            {
                pattern: srcOriginalRecursivePath,
                included: false,
                served: true
            }
        ],
        preprocessors: {
            [testRecursivePath]: ["webpack", "coverage"]
        },
        typescriptPreprocessor: {
            options: tsconfig.compilerOptions
        },
        coverageIstanbulReporter: {
            reports: ["html", "lcovonly", "text-summary", "cobertura"],
            dir: path.join(__dirname, coverageFolder),
            'report-config': {
                html: {
                    subdir: 'html-report'
                }
            },
            combineBrowserReports: true,
            fixWebpackSourcePaths: true,
            verbose: false
        },
        coverageReporter: {
            dir: path.join(__dirname, coverageFolder),
            reporters: [
                // reporters not supporting the `file` property
                { type: 'html', subdir: 'html-report' },
                { type: 'lcov', subdir: 'lcov' },
                // reporters supporting the `file` property, use `subdir` to directly
                // output them in the `dir` directory
                { type: 'cobertura', subdir: '.', file: 'cobertura-coverage.xml' },
                { type: 'lcovonly', subdir: '.', file: 'report-lcovonly.txt' },
                { type: 'text-summary', subdir: '.', file: 'text-summary.txt' },
            ]
        },
        mime: {
            "text/x-typescript": ["ts", "tsx"]
        },
        webpack: webpackConfig,
        webpackMiddleware: {
            stats: "errors-only"
        }
    });
};
```

Gerekirse bu yapılandırmayı değiştirebilirsiniz.

Bazı `karma.conf.js` ayarları:

* `recursivePathToTests` değişkeni, testlerin kod yerini bulur.

* `srcRecursivePath` değişkeni, derleme sonrasında çıktı JS kodunu bulur.

* `srcCssRecursivePath` değişkeni, stillerle daha az dosya derledikten sonra çıktı CSS’yi bulur.

* `srcOriginalRecursivePath` değişkeni, görselinizin kaynak kodunu bulur.

* `coverageFolder` - değişkeni, kapsam raporunun oluşturulacağı bir yeri belirler.

Bazı yapılandırma özellikleri:

* `singleRun: true` - testleri CI sisteminde çalıştırılır. Ayrıca bir kere ayırmak da yeterlidir.
Testlerinizde hata ayıklamak için `false` olarak değiştirebilirsiniz. Karma, tarayıcıyı çalıştırmaya devam eder ve hata ayıklamak için konsolu kullanmanıza olanak sağlar.

* `files: [...]` - Bu dizide, dosyaları tarayıcıya yükleyecek şekilde ayarlayabilirsiniz.
Genellikle kaynak dosyalar, test çalışmaları ve kitaplıklar (jasmine, test yardımcı programları) vardır. Gerekirse diğer dosyaları listelemek için ekleyebilirsiniz.

* `preprocessors` - Yapılandırmanın bu bölümünde, birim testleri yürütülmeden önce yürütülen eylemleri yapılandırırsınız. JS’ye yönelik TypeScript ön derlemesi yapılıyor, kaynak eşleme dosyalarını hazırlanıyor ve kod kapsamı raporu oluşturuluyor. Testlerinizde hata ayıklamak için `coverage` öğesini devre dışı bırakabilirsiniz. Kapsam, test kapsamının denetim kodu için ek kod oluşturduğundan hata ayıklama testlerini karmaşıklaştırır.

**karma.js [belgelerinde](https://karma-runner.github.io/1.0/config/configuration-file.html) bulabileceğiniz tüm yapılandırmaların açıklaması**

Kolay bir şekilde kullanmak için, `scripts` öğesine test komutu ekleyebilirsiniz:

```json
{
    "scripts": {
        "pbiviz": "pbiviz",
        "start": "pbiviz start",
        "typings":"node node_modules/typings/dist/bin.js i",
        "lint": "tslint -r \"node_modules/tslint-microsoft-contrib\"  \"+(src|test)/**/*.ts\"",
        "pretest": "pbiviz package --resources --no-minify --no-pbiviz --no-plugin",
        "test": "karma start"
    }
    ...
}
```

Artık birim testlerinizi yazmaya başlamaya hazırsınız.

## <a name="simple-unit-test-for-check-dom-element-of-the-visual"></a>Görselin DOM öğesini denetlemek için basit birim testi

Görselin test edilmesi için görselin bir örneğini oluşturmamız gerekir.

### <a name="creating-visual-instance-builder"></a>Görsel örnek oluşturucu oluşturma

`visualBuilder.ts` dosyasını sonraki kodla birlikte `test` klasörüne ekleyin:

```typescript
import {
    VisualBuilderBase
} from "powerbi-visuals-utils-testutils";

import {
    BarChart as VisualClass
} from "../src/visual";

import  powerbi from "powerbi-visuals-api";
import VisualConstructorOptions = powerbi.extensibility.visual.VisualConstructorOptions;

export class BarChartBuilder extends VisualBuilderBase<VisualClass> {
    constructor(width: number, height: number) {
        super(width, height);
    }

    protected build(options: VisualConstructorOptions) {
        return new VisualClass(options);
    }

    public get mainElement() {
        return this.element.children("svg.barChart");
    }
}
```

Görselinizin bir örneğini oluşturmak için `build` yöntemi vardır. `mainElement`, görselinizde "kök" DOM öğesinin bir örneğini döndüren bir GET yöntemidir. Alıcı isteğe bağlıdır, ancak birim testini yazmayı daha kolay hale getirir.

Görsel örneği oluşturucumuz var. Test çalışmasını yazalım. Bu test çalışması, görseliniz görüntülendiğinde oluşturulan bu SVG öğelerini denetlemeye yarar.

### <a name="creating-typescript-file-to-write-test-cases"></a>Test çalışmalarını yazmak için TypeScript dosyası oluşturma

Test çalışmaları için bu kodlarla `visualTest.ts` dosyasını ekleyin:

```typescript
import powerbi from "powerbi-visuals-api";

import { BarChartBuilder } from "./VisualBuilder";

import {
    BarChart as VisualClass
} from "../src/visual";

import VisualBuilder = powerbi.extensibility.visual.test.BarChartBuilder;

describe("BarChart", () => {
    let visualBuilder: VisualBuilder;
    let dataView: DataView;

    beforeEach(() => {
        visualBuilder = new VisualBuilder(500, 500);
    });

    it("root DOM element is created", () => {
        expect(visualBuilder.mainElement).toBeInDOM();
    });
});
```

Birkaç yöntem çağrısı vardır.

* [`describe`](https://jasmine.github.io/api/2.6/global.html#describe) yöntemi test çalışmasını açıklar. Jasmine Framework bağlamında genellikle paket veya belirtimler grubu olarak adlandırılır.

* `beforeEach` yöntemi, [`describe`](https://jasmine.github.io/api/2.6/global.html#beforeEach) yönteminde tanımlanan `it` yönteminin her bir çağrısından önce çağrılır.

* `it` tek bir belirtim tanımlar. [`it`](https://jasmine.github.io/api/2.6/global.html#it) yöntemi bir veya daha fazla `expectations` içermelidir.

* [`expect`](https://jasmine.github.io/api/2.6/global.html#expect) - yöntemi bir belirtim için beklenti oluşturur. Tüm beklentiler herhangi bir başarısızlık olmadan geçerse bir belirtim başarılı olur.

* `toBeInDOM` - Bu, eşleştirici yöntemlerinden biridir. Jasmine Framework [belgelerinde](https://jasmine.github.io/api/2.6/matchers.html) mevcut eşleştiriciler hakkında bilgi edinebilirsiniz.

**Resmi [belgelerde](https://jasmine.github.io/) Jasmine Framework hakkında daha fazla bilgi edinin.**

Sonra, komut satırı aracında bir komut yazarak birim testinizi çalıştırabilirsiniz.

Bu test, görsellerin kök SVG öğesinin oluşturulup oluşturulmadığını denetler.

### <a name="launch-unit-tests"></a>Birim testlerini başlatma

Birim testini çalıştırmak için komut satırı aracında bu komutu yazabilirsiniz.

```cmd
npm run test
```

`karma.js`, Chrome tarayıcısını çalıştırır ve test çalışmasını yürütür.

![KarmaJS Chrome'da başlatıldı](./media/karmajs-chrome.png)

> [!NOTE]
> Google Chrome yerel olarak yüklenmelidir.

Komut satırında şu çıktıyı alırsınız:

```cmd
> karma start

23 05 2017 12:24:26.842:WARN [watcher]: Pattern "E:/WORKSPACE/PowerBI/PowerBI-visuals-sampleBarChart/data/*.csv" does not match any file.
23 05 2017 12:24:30.836:WARN [karma]: No captured browser, open http://localhost:9876/
23 05 2017 12:24:30.849:INFO [karma]: Karma v1.3.0 server started at http://localhost:9876/
23 05 2017 12:24:30.850:INFO [launcher]: Launching browser Chrome with unlimited concurrency
23 05 2017 12:24:31.059:INFO [launcher]: Starting browser Chrome
23 05 2017 12:24:33.160:INFO [Chrome 58.0.3029 (Windows 10 0.0.0)]: Connected on socket /#2meR6hjXFmsE_fjiAAAA with id 5875251
Chrome 58.0.3029 (Windows 10 0.0.0): Executed 1 of 1 SUCCESS (0.194 secs / 0.011 secs)

=============================== Coverage summary ===============================
Statements   : 27.43% ( 65/237 )
Branches     : 19.84% ( 25/126 )
Functions    : 43.86% ( 25/57 )
Lines        : 20.85% ( 44/211 )
================================================================================
```

### <a name="how-to-add-static-data-for-unit-tests"></a>Birim testleri için statik veri ekleme

`test` klasöründe `visualData.ts` dosyası oluşturun. Şu kodlarla:

```typescript
import powerbi from "powerbi-visuals-api";
import DataView = powerbi.DataView;

import {
    testDataViewBuilder,
    getRandomNumbers
} from "powerbi-visuals-utils-testutils";

export class SampleBarChartDataBuilder extends TestDataViewBuilder {
    public static CategoryColumn: string = "category";
    public static MeasureColumn: string = "measure";

    public constructor() {
        super();
        ...
    }

    public getDataView(columnNames?: string[]): DataView {
        let dateView: any = this.createCategoricalDataViewBuilder([
            ...
        ],
        [
            ...
        ], columnNames).build();

        // there's client side computed maxValue
        let maxLocal = 0;
        this.valuesMeasure.forEach((item) => {
                if (item > maxLocal) {
                    maxLocal = item;
                }
        });
        (<any>dataView).categorical.values[0].maxLocal = maxLocal;
    }
}
```

`SampleBarChartDataBuilder` sınıfı, `TestDataViewBuilder` öğesini genişletir ve soyut `getDataView` yöntemini uygular.

Verileri veri alanı demetlerine yerleştirdiğinizde, Power BI verilerinize göre kategorik bir `dataview` nesnesi oluşturur.

![Alan demetleri](./media/fields-buckets.png)

Birim testlerinde, bu nesneyi yeniden oluşturmak için Power BI temel işlevleriniz yoktur. Ancak statik verilerinizi kategorik `dataview` ile eşlemeniz gerekir. `TestDataViewBuilder` sınıfı ise bu konuda size yardımcı olur.

[DataViewMapping hakkında daha fazla bilgi edinin](https://github.com/Microsoft/PowerBI-visuals/blob/master/Capabilities/DataViewMappings.md)

`getDataView` yönteminde, yalnızca verilerinizi içeren `createCategoricalDataViewBuilder` yöntemini çağırırsınız.

`sampleBarChart` görseli [capabilities.json](https://github.com/Microsoft/PowerBI-visuals-sampleBarChart/blob/master/capabilities.json#L2) dosyasında, dataRoles ve dataViewMapping nesneleri vardır:

```json
"dataRoles": [
    {
        "displayName": "Category Data",
        "name": "category",
        "kind": "Grouping"
    },
    {
        "displayName": "Measure Data",
        "name": "measure",
        "kind": "Measure"
    }
],
"dataViewMappings": [
    {
        "conditions": [
            {
                "category": {
                    "max": 1
                },
                "measure": {
                    "max": 1
                }
            }
        ],
        "categorical": {
            "categories": {
                "for": {
                    "in": "category"
                }
            },
            "values": {
                "select": [
                    {
                        "bind": {
                            "to": "measure"
                        }
                    }
                ]
            }
        }
    }
],
```

Aynı eşlemeyi oluşturmak için şu parametreleri `createCategoricalDataViewBuilder` yöntemi olarak ayarlamanız gerekir:

```typescript
([
    {
        source: {
            displayName: "Category",
            queryName: SampleBarChartData.ColumnCategory,
            type: ValueType.fromDescriptor({ text: true }),
            roles: {
                Category: true
            },
        },
        values: this.valuesCategory
    }
],
[
    {
        source: {
            displayName: "Measure",
            isMeasure: true,
            queryName: SampleBarChartData.MeasureColumn,
            type: ValueType.fromDescriptor({ numeric: true }),
            roles: {
                Measure: true
            },
        },
        values: this.valuesMeasure
    },
], columnNames)
```

`this.valuesCategory` kategori dizisi.

```ts
public valuesCategory: string[] = ["Monday", "Tuesday", "Wednesday", "Thursday", "Friday", "Saturday", "Sunday"];
```

ve her kategori için `this.valuesMeasure` ölçü dizisi. Örnek:

```ts
public valuesMeasure: number[] = [742731.43, 162066.43, 283085.78, 300263.49, 376074.57, 814724.34, 570921.34];
```

Artık birim testinizde `SampleBarChartDataBuilder` sınıfını kullanabilirsiniz.

`ValueType` sınıfı `powerbi-visuals-utils-testutils` paketinde tanımlıdır. Ayrıca `createCategoricalDataViewBuilder` yöntemi `lodash` kitaplığını gerektirir.

Bu paketleri bağımlılıklara ekleyin.

`devDependencies` bölümündeki `package.json` dosyasında

```json
"lodash-es": "4.17.1",
"powerbi-visuals-utils-testutils": "2.2.0"
```

Çağır

```cmd
npm install
```

`lodash-es` kitaplığını yüklemek için.

Şimdi birim testini yeniden çalıştırabilirsiniz. Bu çıktıyı almalısınız

```cmd
> karma start

23 05 2017 16:19:54.318:WARN [watcher]: Pattern "E:/WORKSPACE/PowerBI/PowerBI-visuals-sampleBarChart/data/*.csv" does not match any file.
23 05 2017 16:19:58.333:WARN [karma]: No captured browser, open http://localhost:9876/
23 05 2017 16:19:58.346:INFO [karma]: Karma v1.3.0 server started at http://localhost:9876/
23 05 2017 16:19:58.346:INFO [launcher]: Launching browser Chrome with unlimited concurrency
23 05 2017 16:19:58.394:INFO [launcher]: Starting browser Chrome
23 05 2017 16:19:59.873:INFO [Chrome 58.0.3029 (Windows 10 0.0.0)]: Connected on socket /#NcNTAGH9hWfGMCuEAAAA with id 3551106
Chrome 58.0.3029 (Windows 10 0.0.0): Executed 1 of 1 SUCCESS (1.266 secs / 1.052 secs)

=============================== Coverage summary ===============================
Statements   : 56.72% ( 135/238 )
Branches     : 32.54% ( 41/126 )
Functions    : 66.67% ( 38/57 )
Lines        : 52.83% ( 112/212 )
================================================================================
```

Ayrıca, görseliniz ile başlatılan Chrome tarayıcısını görmeniz gerekir.

![Chrome'da UT başlatılır](./media/karmajs-chrome-ut-runned.png)

Dikkat kapsamı özetini arttırılmış hale getirin. Geçerli kod kapsamı hakkında daha fazla bilgi edinmek için `coverage\index.html` öğesini açın

![UT kapsamı dizini](./media/code-coverage-index.png)

Veya `src` klasörü kapsamında

![src klasörünün kapsamı](./media/code-coverage-src-folder.png)

Dosya kapsamında kaynak koduna bakabilirsiniz. Birim testlerinin çalıştırılması sırasında bir kod yürütülmezse, `Coverage` yardımcı programları satır arka planını kırmızı olarak işaretler.

![visual.ts dosyasının kod kapsamı](./media/code-coverage-visual-src.png)

> [!IMPORTANT]
> Ancak kod kapsamı, görselin iyi bir işlevsellik kapsamına sahip olduğunuz anlamına gelmez. Tek bir basit birim testi, `src\visual.ts` içinde %96’nın üzerinde kapsam sağladı.

## <a name="next-steps"></a>Sonraki adımlar

Hazır olduğunda görselinizi yayına gönderebilirsiniz.

[AppSource'ta görsel yayımlama hakkında daha fazla bilgi edinin](../office-store.md)
