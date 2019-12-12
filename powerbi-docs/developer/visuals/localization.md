---
title: Power BI görsellerinde veri görünümü eşlemesini anlama
description: Bu makalede Power BI’ın verileri görsellere geçirmeden önce nasıl dönüştürdüğü açıklanır.
author: asander
ms.author: asander
manager: rkarlin
ms.reviewer: sranins
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: conceptual
ms.date: 06/18/2019
ms.openlocfilehash: 85cfa292055f7db96dcb714ec8c4dd78fe75ee67
ms.sourcegitcommit: f77b24a8a588605f005c9bb1fdad864955885718
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2019
ms.locfileid: "74700306"
---
# <a name="add-the-locale-in-power-bi-for-custom-visuals"></a>Power BI'da özel görseller için yerel ayar ekleme

Görseller, içeriklerini uygun dilde yerelleştirmek için Power BI yerel ayarını alabilir.

[Power BI için desteklenen diller ve ülkeler/bölgeler](./../../supported-languages-countries-regions.md) hakkında daha fazla bilgi edinin

Örnek olarak Örnek Çubuk Grafik görselinde yerel ayarı alma gösterilebilir.

![Örnek Çubuk Grafik görselinde yerelleştirme](media/locale-in-samplebarchart.png)

Bu çubuk grafiklerin her biri farklı bir yerel ayarla (İngilizce, Baskça ve Hintçe) oluşturulmuştur.

> [!NOTE]
> Görselin kodundaki yerelleştirme yöneticisi API 1.10.0 ve üstünde desteklenir.

## <a name="get-the-locale"></a>Yerel ayarı alma

Görselin başlatılması sırasında `locale` bir dize olarak geçirilir. Power BI'da yerel ayar değiştirilirse görsel yeni yerel ayarla yeniden oluşturulur. Locale içeren SampleBarChart'ta tam örnek kodu bulabilirsiniz

BarChart oluşturucusunun artık konak yerel ayar örneğiyle birlikte oluşturucuda örneği oluşturulan bir yere ayar üyesi vardır.

```typescript
private locale: string;
...
this.locale = options.host.locale;
```

Desteklenen yerel ayarlar:

Yerel ayar dizesi | Dil
--------------|----------------------
ar-SA | العربية (Arapça)
bg-BG | български (Bulgarca)
ca-ES | català (Katalanca)
cs-CZ | čeština (Çekçe)
da-DK | dansk (Danca)
de-DE | Deutsche (Almanca)
el-GR | ελληνικά (Yunanca)
en-US | English (İngilizce)
es-ES | español (İspanyolca)
et-EE | eesti (Estonca)
eU-ES | Euskal (Baskça)
fi-FI | suomi (Fince)
fr-FR | français (Fransızca)
gl-ES | galego (Galiçyaca)
he-IL | עברית (İbranice)
hi-IN | हिन्दी (Hintçe)
hr-HR | hrvatski (Hırvatça)
hu-HU | magyar (Macarca)
id-ID | Bahasa Indonesia (Endonezce)
it-IT | italiano (İtalyanca)
ja-JP | 日本の (Japonca)
kk-KZ | Қазақ (Kazakça)
ko-KR | 한국의 (Korece)
lt-LT | Lietuvos (Litvanca)
lv-LV | Latvijas (Letonca)
ms-MY | Bahasa Melayu (Malayca)
nb-NO | norsk (Norveççe)
nl-NL | Nederlands (Felemenkçe)
pl-PL | polski (Lehçe)
pt-BR | português (Portekizce)
pt-PT | português (Portekizce)
ro-RO | românesc (Rumence)
ru-RU | русский (Rusça)
sk-SK | slovenský (Slovakça)
sl-SI | slovenski (Slovence)
sr-Cyrl-RS | српски (Sırpça)
sr-Latn-RS | srpski (Sırpça)
sv-SE | svenska (İsveççe)
th-TH | ไทย (Tayca)
tr-TR | Türkçe
uk-UA | український (Ukraynaca)
vi-VN | tiếng Việt (Vietnamca)
zh-CN | 中国 (Çince-Basitleştirilmiş)
zh-TW | 中國 (Çince-Geleneksel)

> [!NOTE]
> PowerBI Desktop'ta yerel ayar özelliği PowerBI Desktop'ın yüklendiği dili içerir.

## <a name="localizing-the-property-pane-for-custom-visuals"></a>Özel görseller için özellik bölmesini yerelleştirme

Özellik bölmesindeki alanlar daha tümleşik ve tutarlı bir deneyim sağlamak için yerelleştirilebilir. Özel görselinizin diğer tüm Power BI temel görselleri gibi davranması sağlanır.

Örneğin `pbiviz new` komutu kullanılarak oluşturulmuş ve yerelleştirilmemiş bir özel görsel, özellik bölmesinde aşağıdaki alanları gösterir:

![Özellik bölmesinde yerelleştirme](media/property-pane.png)

Hem Category Data hem de Measure Data öğeleri capabilities.json dosyasında `displayName` olarak tanımlanır.

## <a name="how-to-localize-capabilities"></a>Özellikleri yerelleştirme

İlk olarak özelliklerinizde yerelleştirmek istediğiniz her görünen ada bir görünen ad anahtarı ekleyin. Bu örnekte:

```json
{
    "dataRoles": [
        {
            "displayName": "Category Data",
            "displayNameKey": "VisualCategoryDataNameKey1",
            "name": "category",
            "kind": "Grouping"
        },
        {
            "displayName": "Measure Data",
            "displayNameKey": "VisualMeasureDataNameKey2",
            "name": "measure",
            "kind": "Measure"
        }
    ]
}
```

Sonra stringResources adlı bir dizin ekleyin. Dizin, görselinizin desteklemesini istediğiniz yerel ayarlar temelinde tüm farklı dize kaynağı dosyalarınızı içerir. Bu dizinin altında, desteklemek istediğiniz her yerel ayar için bir JSON dosyası eklemelisiniz. Söz konusu dosyalar değiştirmek istediğiniz her displayNameKey için yerel ayar bilgisini ve yerelleştirilmiş dize değerlerini içerir.

Bizim örneğimizde Arapça ve İbranice'yi desteklemek istediğimizi varsayalım. Aşağıdaki şekilde iki JSON dosyası eklememiz gerekir:

![Dize kaynakları klasöründe yerelleştirme dizeleri](media/stringresources-files.png)

Her JSON dosyası, istenen görünen ad anahtarları için dize değerleriyle tek bir yerel ayarı tanımlar (bu dosya yukarıdaki desteklenen listede yer alan yerel ayarlardan biri olmalıdır). Bizim örneğimizde İbranice dize kaynağı dosyası aşağıdaki gibi görünecektir:

```json
{
    "locale": "he-IL",
    "values": {
        "VisualCategoryDataNameKey1": "קטגוריה",
        "VisualMeasureDataNameKey2": "יחידות מידה"
    }
}
```

Yerelleştirme yöneticisini kullanmak için gereken tüm adımlar aşağıda açıklanmıştır.

> [!NOTE]
> Şu anda geliştirme görselinde hata ayıklama işlemi için yerelleştirme desteklenmez

## <a name="setup-environment"></a>Kurulum ortamı

### <a name="desktop"></a>Masaüstü

Masaüstü kullanımı için  Power BI Desktop'ın yerelleştirilmiş sürümünü https://powerbi.microsoft.com adresinden indirin.

### <a name="web-service"></a>Web hizmeti

Hizmette web istemcisini (tarayıcı) kullanıyorsanız, ayarlarda dilinizi değiştirin:

![Web hizmetinde yerelleştirme](media/webservice-settings.png)

## <a name="resource-file"></a>Kaynak dosyası

stringResources klasörünün içinde, kullanacağınız yerel ayarın adını taşıyan klasöre bir resources.resjson dosyası ekleyin. Bizim örneğimizde bu en-US ve ru-RU klasörleridir.

![Yeni resjson dosyası](media/new-resjson.png)

Bundan sonra, kullanacağınız tüm yerelleştirme dizelerini önceki adımda eklediğiniz resources.resjson dosyasına ekleyin.

```json
{
    ...
    "Role_Legend": "Обозначения",
    "Role_task": "Задача",
    "Role_StartDate": "Дата начала",
    "Role_Duration": "Длительность"
    ...
}
```

Bu örnek resources.resjson dosyasının en-US sürümüdür:

```json
{
    ...
    "Role_Legend": "Legend",
    "Role_task": "Task",
    "Role_StartDate": "Start date",
    "Role_Duration": "Duration"
    ...
}
```

Yeni localizationManager örneği. Görselinizin kodunda aşağıda gösterildiği gibi bir localizationManager örneği oluşturun

```typescript
private localizationManager: ILocalizationManager;

constructor(options: VisualConstructorOptions) {
    this.localizationManager = options.host.createLocalizationManager();
}
```

## <a name="localizationmanager-usage-sample"></a>localizationManager kullanım örneği

Artık kodunuzun içinde herhangi bir yere gerekli dizeyi almak için, resources.resjson dosyasında tanımladığınız dize anahtarı bağımsız değişkeniyle yerelleştirme yöneticisinin getDisplayName işlevini çağırabilirsiniz:

```typescript
let legend: string = this.localization.getDisplayName("Role_Legend");
```

en-US için "Legend" ve ru-RU için "Обозначения" değerlerini döndürür

## <a name="next-steps"></a>Sonraki adımlar

* [Yerelleştirilmiş biçimler sağlamak için biçimlendirme yardımcı programlarını kullanma konusunu okuyun](utils-formatting.md)
