---
title: URL’yi başlatma
description: Power BI Görselleri yeni sekmede URL açabilir
author: Guy-Moses
ms.author: guymos
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 1a7002c3b45f341c0cbc0db683bc4f8a113e21f9
ms.sourcegitcommit: 473d031c2ca1da8935f957d9faea642e3aef9839
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2019
ms.locfileid: "68424873"
---
# <a name="launch-url"></a>URL’yi başlatma

URL’yi başlatma, asıl işi Power BI’a temsilci olarak atayarak yeni bir tarayıcı sekmesinin (veya penceresinin) açılmasına olanak tanır.

## <a name="sample"></a>Örnek

```typescript
   this.host.launchUrl('https://powerbi.microsoft.com');
```

## <a name="usage"></a>Kullanım

`host.launchUrl()` API çağrısını kullanarak hedef URL’nizi bir dize bağımsız değişkeni olarak geçirin:

```typescript
this.host.launchUrl('http://some.link.net');
```

## <a name="restrictions"></a>Kısıtlamalar

* Yalnızca mutlak yolları kullanın. Göreli olanları kullanmayın. `http://some.link.net/subfolder/page.html` uygundur, `/page.html` açılmaz.
* Şu anda yalnızca `http` ve `https` protokolleri desteklenir. `ftp`, `mailto` ve benzerlerini kullanmaktan kaçının.

## <a name="best-practices"></a>En iyi yöntemler

1. Çoğu durumda, bağlantıyı yalnızca bir kullanıcının açık eylemine yanıt olarak açmak en iyisidir. Kullanıcının, bağlantıya veya düğmeye tıklandığında yeni bir sekme açılacağını anlamasını kolaylaştırın. Kullanıcının eylemi olmadan bir `launchUrl()` çağrısını tetikleme veya farklı bir eylemin yan etkisi olarak kullanıcının kafasını karıştırabilir veya sinir bozucu olabilir.
2. Bağlantı, görselin düzgün çalışması için önemli değilse, raporun yazarına bağlantıyı devre dışı bırakmak ve gizlemek için bir yol sağlanılması önerilir. Bu, özellikle üçüncü taraf uygulamaya bir rapor ekleme veya bunu Web’de yayımlama gibi özel Power BI kullanım durumları için geçerlidir.
3. Bir döngünün içinden `launchUrl()` çağrısını, görselin `update` işlevini veya diğer tüm sık tekrarlan kodları tetiklemekten kaçının.

## <a name="step-by-step-example"></a>Adım adım ilerleyen örnek

### <a name="adding-a-link-launching-element"></a>Link başlatma öğesi ekleme

Görselin `constructor` işlevine aşağıdaki satırlar eklendi:

```typescript
    this.helpLinkElement = this.createHelpLinkElement();
    options.element.appendChild(this.helpLinkElement);
```

Ve, bağlayıcı öğeyi oluşturan ve ekleyen özel bir işlev eklendi:

```typescript
private createHelpLinkElement(): Element {
    let linkElement = document.createElement("a");
    linkElement.textContent = "?";
    linkElement.setAttribute("title", "Open documentation");
    linkElement.setAttribute("class", "helpLink");
    linkElement.addEventListener("click", () => {
        this.host.launchUrl("https://docs.microsoft.com/power-bi/developer/custom-visual-develop-tutorial");
    });
    return linkElement;
};
```

Son olarak, visual.less dosyasında bulunan bir giriş, bağlantı öğesinin stilini tanımlar:

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

### <a name="adding-a-toggling-mechanism"></a>Bir değiştirme mekanizması ekleme

Bu, bağlantı öğesi görünürlüğünün (varsayılan olarak gizliye ayarlıdır) rapor yazarı tarafından değiştirebilmesi için statik bir nesne eklemeyi gerektirir (bkz. [statik nesne öğreticisi](https://microsoft.github.io/PowerBI-visuals/docs/concepts/objects-and-properties)).
`capabilities.json` nesnesinin girişine bir `showHelpLink` boole statik nesne eklendi:

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

![URL geçişini başlatma](./media/launchurl-toggle.png)

Görselin `update` işlevine aşağıdaki satırlar eklendi:

```typescript
if (settings.generalView.showHelpLink) {
    this.helpLinkElement.classList.remove("hidden");
} else {
    this.helpLinkElement.classList.add("hidden");
}
```

`hidden` sınıfı, öğenin görüntüsünü denetlemek için visual.less dosyasında tanımlanır.
