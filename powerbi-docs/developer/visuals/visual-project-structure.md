---
title: Power BI görseli proje yapısı
description: Bu makalede Power BI görseli projesinin klasör ve dosya yapısı açıklanır
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.topic: conceptual
ms.subservice: powerbi-custom-visuals
ms.date: 01/12/2020
ms.openlocfilehash: 18267f06bd43166cb1958d3aff73913a31189953
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "80550754"
---
# <a name="power-bi-visual-project-structure"></a>Power BI görseli proje yapısı

Yeni bir Power BI görseli oluşturmaya başlamanın en iyi yolu Power BI görselleri [pbiviz](https://www.npmjs.com/package/powerbi-visuals-tools) aracını kullanmaktır.

Yeni görsel oluşturmak için, Power BI görselinin yerleştirilmesini istediğiniz dizine gidin ve şu komutu çalıştırın:

`pbiviz new <visual project name>`

Bu komut çalıştırıldığında aşağıdaki dosyaları içeren bir Power BI görseli klasörü oluşturulur:

```markdown
project
├───.vscode
│   ├───launch.json
│   └───settings.json
├───assets
│   └───icon.png
├───node_modules
├───src
│   ├───settings.ts
│   └───visual.ts
├───style
│   └───visual.less
├───capabilities.json
├───package-lock.json
├───package.json
├───pbiviz.json
├───tsconfig.json
└───tslint.json
```

## <a name="folder-and-file-description"></a>Klasör ve dosya açıklaması

Bu bölümde, Power BI görselleri **pbiviz** aracının oluşturduğu dizindeki klasör ve dosyaların her biri hakkında bilgi sağlanır.  

### <a name="vscode"></a>.vscode

Bu klasör VS kodu proje ayarlarını içerir.

Çalışma alanınızı yapılandırmak için `.vscode/settings.json` dosyasını düzenleyin.

Daha fazla bilgi için bkz. [Kullanıcı ve Çalışma Alanı Ayarları](https://code.visualstudio.com/docs/getstarted/settings)

### <a name="assets"></a>varlıklar

Bu klasör `icon.png` dosyasını içerir.

Power BI görselleri aracı bu dosyayı Power BI görselleştirme bölmesinde yeni Power BI görselinin simgesi olarak kullanır.

### <a name="src"></a>src

Bu klasör görselin kaynak kodunu içerir.

Bu klasörde Power BI görselleri aracı şu dosyaları oluşturur:
* `visual.ts` - Görselin ana kaynak kodu.
* `settings.ts` - Görselin ayarlarının kodu. Dosyadaki sınıflar [görselinizin özelliklerini](./objects-properties.md#properties) tanımlamaya yönelik bir arabirim sağlar.

### <a name="style"></a>stil

Bu klasör, içinde görselin stillerinin bulunduğu `visual.less` dosyasını içerir.

### <a name="capabilitiesjson"></a>capabilities.json

Bu dosya görselin ana özelliklerini ve ayarlarını (veya [becerilerini](./capabilities.md)) içerir. Görselin desteklenen özellikleri, nesneleri ve [veri görünümü eşlemesini](./dataview-mappings.md) bildirmesine olanak tanır.

### <a name="package-lockjson"></a>package-lock.json

Bu dosya *npm*’nin `node_modules` ağacını veya `package.json` dosyasını değiştirdiği tüm işlemler için otomatik olarak oluşturulur.

Bu dosya hakkında daha fazla bilgi için resmi [npm-package-lock.json](https://docs.npmjs.com/files/package-lock.json) belgelerine bakın.

### <a name="packagejson"></a>package.json

Bu dosya proje paketini açıklar. Proje hakkındaki bilgileri, örneğin yazarlarını, açıklamasını ve proje bağımlılıklarını içerir.

Bu dosya hakkında daha fazla bilgi için resmi [npm-package.json](https://docs.npmjs.com/files/package.json.html) belgelerine bakın.

### <a name="pbivizjson"></a>pbiviz.json

Bu dosya görsel meta verilerini içerir.

Meta veri girdilerinin anlatıldığı açıklamalarla örnek bir `pbiviz.json` dosyası görmek için [meta veri girdileri](#metadata-entries) bölümüne bakın.

### <a name="tsconfigjson"></a>tsconfig.json

[TypeScript](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html) için yapılandırma dosyası.

Bu dosya, **dosyasındaki \* özelliğinde belirtildiği gibi görselin ana sınıfının yer aldığı**`visualClassName`.ts`pbiviz.json` dosyasının yolunu içermelidir.

### <a name="tslintjson"></a>tslint.json

Bu dosya [TSLint yapılandırmasını](https://palantir.github.io/tslint/usage/configuration/) içerir.

## <a name="metadata-entries"></a>Meta veri girdileri

`pbiviz.json` dosyasından alınan aşağıdaki kod parçasındaki açıklamalar, meta veri girdilerini anlatır.

> [!NOTE]
> * **pbiviz** aracının 3.x.x sürümünden `externalJS` desteklenmez.
> * Yerelleştirme desteği için [Power BI yerel ayarını görselinize ekleyin](./localization.md).

```json
{
  "visual": {
     // The visual's internal name.
    "name": "<visual project name>",

    // The visual's display name.
    "displayName": "<visual project name>",

    // The visual's unique ID.
    "guid": "<visual project name>23D8B823CF134D3AA7CC0A5D63B20B7F",

    // The name of the visual's main class. Power BI creates the instance of this class to start using the visual in a Power BI report.
    "visualClassName": "Visual",

    // The visual's version number.
    "version": "1.0.0",
    
    // The visual's description (optional)
    "description": "",

    // A URL linking to the visual's support page (optional).
    "supportUrl": "",

    // A link to the source code available from GitHub (optional).
    "gitHubUrl": ""
  },
  // The version of the Power BI API the visual is using.
  "apiVersion": "2.6.0",

  // The name of the visual's author and email.
  "author": { "name": "", "email": "" },

  // 'icon' holds the path to the icon file in the assets folder; the visual's display icon.
  "assets": { "icon": "assets/icon.png" },

  // Contains the paths for JS libraries used in the visual.
  // Note: externalJS' isn't used in the Power BI visuals tool version 3.x.x or higher.
  "externalJS": null,

  // The path to the 'visual.less' style file.
  "style": "style/visual.less",

  // The path to the `capabilities.json` file.
  "capabilities": "capabilities.json",

  // The path to the `dependencies.json` file which contains information about R packages used in R based visuals.
  "dependencies": null,

  // An array of paths to files with localizations.
  "stringResources": []
}
```

## <a name="next-steps"></a>Sonraki adımlar

* Görsel, kullanıcı ve Power BI arasındaki etkileşimleri anlamak için bkz. [Power BI görseli kavramı](./power-bi-visuals-concept.md).

* [Adım adım kılavuzu](./custom-visual-develop-tutorial.md) kullanarak sıfırdan kendi Power BI görsellerinizi geliştirmeye başlayın.
