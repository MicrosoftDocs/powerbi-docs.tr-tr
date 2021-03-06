---
title: Daha iyi tümleşik BI içgörüleri için Power BI tümleşik analizlerinde bir başlatma URL’si oluşturma
description: Bu makalede Power BI Görselleri’ni kullanarak URL’nin yeni sekmede nasıl açılabileceği açıklanır. Power BI tümleşik analiz kullanarak daha iyi tümleşik BI içgörüleri elde edin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 06/18/2019
ms.openlocfilehash: 6fe9908c324705b8cb00519b4743ae8c052c7ad8
ms.sourcegitcommit: eeaf607e7c1d89ef7312421731e1729ddce5a5cc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2021
ms.locfileid: "97888317"
---
# <a name="create-a-launch-url"></a>Başlatma URL’si oluşturma

Başlatma URL’si oluşturduğunuzda asıl çalışmayı yapması için Power BI’ı temsilci olarak atayarak yeni bir tarayıcı sekmesi (veya penceresi) açabilirsiniz.

> [!IMPORTANT]
> `host.launchUrl()`, Görseller API 1.9.0’da tanıtılmıştır.

## <a name="sample"></a>Örnek

`IVisualHost` arabirimini içeri aktarın ve bağlantıyı görselin oluşturucusunun `host` nesnesine kaydedin.

```typescript
import powerbi from "powerbi-visuals-api";
import IVisualHost = powerbi.extensibility.visual.IVisualHost;

export class Visual implements IVisual {
    private host: IVisualHost;
    // ...
    constructor(options: VisualConstructorOptions) {
        // ...
        this.host = options.host;
        // ...
    }

    // ...
}
```

## <a name="usage"></a>Kullanım

`host.launchUrl()` API çağrısını kullanarak hedef URL’nizi bir dize bağımsız değişkeni olarak geçirin:

```typescript
this.host.launchUrl('https://some.link.net');
```

## <a name="restrictions"></a>Kısıtlamalar

* Göreli yolları değil yalnızca mutlak yolları kullanın. Örneğin `https://some.link.net/subfolder/page.html` gibi bir mutlak yol kullanın. `/page.html` göreli yolu açılmaz.

* Şu anda yalnızca *HTTP* ve *HTTPS* protokolleri desteklenir. *FTP* ve *MAILTO* gibi protokolleri kullanmaktan kaçının.

## <a name="best-practices"></a>En iyi uygulamalar

* Çoğunlukla bağlantıyı yalnızca bir kullanıcının açık eylemine yanıt olarak açmak en iyisidir. Kullanıcının, bağlantıya veya düğmeye tıklandığında yeni bir sekme açılacağını anlamasını kolaylaştırın. Kullanıcının eylemi olmadan bir `launchUrl()` çağrısını tetikleme veya farklı bir eylemin yan etkisi olarak kullanıcının kafasını karıştırabilir veya sinir bozucu olabilir.

* Bağlantı, görselin düzgün çalışması için temel önem taşımıyorsa, raporun yazarına bağlantıyı devre dışı bırakmak ve gizlemek için bir yol sağlamanızı öneririz. Bu öneri özellikle üçüncü taraf bir uygulamaya rapor ekleme veya bunu Web’de yayımlama gibi özel Power BI kullanım durumları için geçerlidir.

* Bir döngünün içinden `launchUrl()` çağrısını, görselin `update` işlevini veya sık tekrarlanan diğer tüm kodları tetiklemekten kaçının.

## <a name="a-step-by-step-example"></a>Adım adım örnek

### <a name="add-a-link-launching-element"></a>Bağlantı başlatma öğesi ekleme

Görselin `constructor` işlevine aşağıdaki satırlar eklendi:

```typescript
    this.helpLinkElement = this.createHelpLinkElement();
    options.element.appendChild(this.helpLinkElement);
```

Bağlantı öğesini oluşturan ve ekleyen özel bir işlev eklendi:

```typescript
private createHelpLinkElement(): Element {
    let linkElement = document.createElement("a");
    linkElement.textContent = "?";
    linkElement.setAttribute("title", "Open documentation");
    linkElement.setAttribute("class", "helpLink");
    linkElement.addEventListener("click", () => {
        this.host.launchUrl("https://docs.microsoft.com/power-bi/developer/visuals/custom-visual-develop-tutorial");
    });
    return linkElement;
};
```

Son olarak, *visual.less* dosyasında bulunan bir giriş, bağlantı öğesinin stilini tanımlar:

```less
.helpLink {
    position: absolute;
    top: 0px;
    right: 12px;
    display: block;
    width: 20px;
    height: 20px;
    border: 2px solid #80B0E0;
    border-radius: 20px;
    color: #80B0E0;
    text-align: center;
    font-size: 16px;
    line-height: 20px;
    background-color: #FFFFFF;
    transition: all 900ms ease;

    &:hover {
        background-color: #DDEEFF;
        color: #5080B0;
        border-color: #5080B0;
        transition: all 250ms ease;
    }

    &.hidden {
        display: none;
    }
}
```

### <a name="add-a-toggling-mechanism"></a>Geçiş mekanizması ekleme

Geçiş mekanizması eklemek için, rapor yazarının bağlantı öğesinin görünürlüğünü değiştirebileceği statik bir nesne eklemeniz gerekir. (Varsayılan olarak *gizli* değerine ayarlanır.) Daha fazla bilgi için bkz. [statik nesne öğreticisi](https://microsoft.github.io/PowerBI-visuals/docs/concepts/objects-and-properties).

Aşağıdaki kodda gösterildiği gibi *capabilities.json* dosyasının objects girdisine `showHelpLink` Boole statik nesnesi eklenir:

```typescript
"objects": {
    "generalView": {
            "displayName": "General View",
            "properties":
                "showHelpLink": {
                    "displayName": "Show Help Button",
                    "type": {
                        "bool": true
                    }
                }
            }
        }
    }
```

![URL geçişini başlatma](media/launch-url/launchurl-toggle.png)

Görselin `update` işlevine aşağıdaki satırlar eklendi:

```typescript
if (settings.generalView.showHelpLink) {
    this.helpLinkElement.classList.remove("hidden");
} else {
    this.helpLinkElement.classList.add("hidden");
}
```

Öğenin görüntülenmesini değiştirmek için *visual.less* dosyasında *gizli* sınıfı tanımlanır.