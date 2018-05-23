---
title: Ekli Power BI içerikleriyle özel düzenler
description: Power BI içeriğini uygulamanıza eklerken kullanabileceğiniz özel düzenler hakkında bilgi edinin.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 12/19/2017
ms.author: maghan
ms.openlocfilehash: fc684ebdf6b1ccb53bdd7794b19c1120ece635a3
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="custom-layouts"></a>Özel düzenler


Özel düzenleri kullanarak raporları özgün rapordan farklı bir düzende ekleyebilirsiniz. Yeni bir düzen tanımlama sırasında tek bir sayfa boyutunu tanımlama, görsel boyutlarını veya konumunu ve görünürlüğünü denetleme işlemleri gerçekleştirilebilir.

Özel bir düzen tanımlamak için özel düzen nesnesi tanımlayın ve ekleme yapılandırmasında ayarlar nesnesine iletin. Ek olarak LayoutType parametresini Custom ölerek ayarlayın. Daha fazla bilgi edinmek için bkz. [Ekleme Yapılandırması Ayrıntıları](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details).

```javascript
var embedConfig = {
    ...
    settings: {
            layoutType: models.LayoutType.Custom
    customLayout: {...}
    }
};
```

## <a name="object-definition"></a>Nesne Tanımı

```javascript
interface ICustomLayout {
  pageSize?: IPageSize;
  displayOption?: DisplayOption;
  pagesLayout?: PagesLayout;
}

enum PageSizeType {
  Widescreen,
  Standard,
  Cortana,
  Letter,
  Custom
}
interface IPageSize {
  type: PageSizeType;
}
interface ICustomPageSize extends IPageSize {
  width?: number;
  height?: number;
}

enum DisplayOption {
  FitToPage,
  FitToWidth,
  ActualSize
}
```

- `pageSize`: Tuval alanı boyutunu (rapordaki beyaz alanı) denetlemek için sayfa boyutunu kullanın.
- `displayOptions`: Şu değerleri kullanabilirsiniz: FitToWidth, FitToPage veya ActualSize. Tuvalin iframe içine sığması için nasıl ölçeklendirileceğini denetler.
- `pagesLayout`: Her bir görselin düzenini denetler. Daha fazla ayrıntı için bkz. PagesLayout.

## <a name="pages-layout"></a>Sayfa düzeni

Sayfa düzeni nesnesi tanımlamak için her sayfa için bir düzen tanımlamanız ve her sayfadaki görseller için düzen tanımlamanız gerekir.
PageLayout isteğe bağlıdır. Sayfa düzeni tanımlamazsanız varsayılan düzen (rapora kaydedilir) uygulanır.

pagesLayout, sayfa adı ile PageLayout nesnesi arasında eşleme sağlar. Tanım:

```javascript
type PagesLayout = { [key: string]: IPageLayout; };
```

PageLayout, görsel adlarını görsel düzen nesnelerine eşleyen bir görsel düzen haritası içerir:

```javascript
interface IPageLayout {
  visualsLayout: { [key: string]: IVisualLayout; };
}
```

## <a name="visual-layout"></a>Görsel düzeni

Görsel düzeni tanımlamak için yeni konum, boyut ve yeni görünürlük durumu iletin.

```javascript
interface IVisualLayout {
  x?: number;
  y?: number;
  z?: number;
  width?: number;
  height?: number;
  displayState?: IVisualContainerDisplayState;
}

interface IVisualContainerDisplayState {
  mode: VisualContainerDisplayMode;
}

enum VisualContainerDisplayMode {
  Visible,
  Hidden
}
```

- `x,y,z`: Görselin yeni konumunu tanımlar.
- `width`, yükseklik: Görselin yeni boyutunu tanımlar.
- `displayState`: Görselin görünürlüğünü tanımlar.


## <a name="update-layout"></a>Düzeni güncelleştirme

updateSettings yöntemini kullanarak rapor düzenini rapor yüklendikten sonra herhangi bir zamanda güncelleştirebilirsiniz. Bkz. [Ayarları Güncelleştirme](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Update-Settings).

## <a name="code-example"></a>Kod örneği

```javascript
// Get models. models contains enums that can be used.
var models = window['powerbi-client'].models;
    
var embedConfiguration = {
    type: 'report',
    id: '5dac7a4a-4452-46b3-99f6-a25915e0fe55',
    embedUrl: 'https://app.powerbi.com/reportEmbed',
    tokenType: models.TokenType.Embed,
    accessToken: 'H4...rf',
    settings: {
            layoutType: models.LayoutType.Custom
        customLayout: {
            pageSize: {
                type: models.PageSizeType.Custom,
                width: 1600,
                height: 1200
            },
            displayOption: models.DisplayOption.ActualSize,
            pagesLayout: {
                "ReportSection1" : {
                    visualsLayout: {
                        "VisualContainer1": {
                            x: 1,
                            y: 1,
                            z: 1,
                            width: 400,
                            height: 300,
                            displayState: {
                                mode: models.VisualContainerDisplayMode.Visible
                            }
                        },
                        "VisualContainer2": {
                            displayState: {
                                mode: models.VisualContainerDisplayMode.Hidden
                            }
                        },
                    }
                }
            }
        }
    }
};
     
// Get a reference to the embedded report HTML element
var embedContainer = document.getElementById('embedContainer');
 
// Embed the report and display it within the div container.
var report = powerbi.embed(embedContainer, embedConfiguration);

```


## <a name="see-also"></a>Ayrıca bkz.

[Power BI panolarınızı, raporlarınızı ve kutucuklarınızı ekleme](embedding-content.md)   
[Power BI Topluluğu'na sorun](https://community.powerbi.com/)

