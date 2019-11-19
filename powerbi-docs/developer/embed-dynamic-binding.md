---
title: Dinamik bağlama
description: Dinamik bağlama kullanarak rapor eklemeyi öğrenin.
author: KesemSharabi
ms.author: kesharab
manager: rkarlin
ms.topic: conceptual
ms.service: powerbi
ms.subservice: powerbi-developer
ms.date: 09/25/2019
ms.openlocfilehash: 8b42b397f726e492eda80a99eb730c215eb17ccb
ms.sourcegitcommit: 23ad768020a9daf129f69a462a2d46d59d2349d2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72776249"
---
# <a name="dynamic-binding"></a>Dinamik bağlama

Dinamik bağlama, bir raporu eklerken veri kümesini dinamik olarak seçmeye olanak sağlar. Raporun ve veri kümesinin aynı çalışma alanında bulunması gerekmez. Son kullanıcılar seçili veri kümesine bağlı olarak farklı sonuçlar görür.

Her iki çalışma alanı da (raporu içeren çalışma alanı ve veri kümesini içeren çalışma alanı) bir kapasiteye atanmalıdır.

Dinamik bağlama kullanarak bir raporun eklenmesi iki aşamayı içerir:
1. Belirteç oluşturma
2. Yapılandırma nesnesini ayarlama

## <a name="generating-a-token"></a>Belirteç oluşturma
Belirteç oluşturmak için, [birden çok öğe için ekleme belirteci oluşturmaya yönelik API](embed-sample-for-customers.md#multiEmbedToken)’yi kullanın.

Dinamik bağlama, her iki ekleme senaryosu için de desteklenir: *Kuruluşunuz için içerik ekleme* ve *Müşterileriniz için içerik ekleme*.

| Çözüm                   | Belirteç                               | Gereksinimler                                                                                                                                                  |
|---------------------------------|-------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
| *Kuruluşunuz için içerik ekleme* | Power BI kullanıcıları için erişim belirteci     | Azure AD belirteci kullanılan kullanıcının tüm yapıtlar için uygun izinlere sahip olması gerekir.                                                                    |
| *Müşterileriniz için içerik ekleme*    | Power BI kullanıcısı olmayan kişiler için erişim belirteci | Hem rapora hem de dinamik olarak bağlı veri kümesine yönelik izinleri içermelidir. Birden çok yapıtı destekleyen bir ekleme belirteci oluşturmak için yeni API'yi kullanın. |

## <a name="adjusting-the-config-object"></a>Yapılandırma nesnesini ayarlama
Yapılandırma nesnesine `datasetBinding` ekleyin. Sayfanın alt kısmındaki örneği başvuru olarak kullanın.

Power BI’da ekleme konusuna yeni başladıysanız, Power BI içeriğinizi nasıl ekleyeceğinizi öğrenmek için şu öğreticileri inceleyin:
* [Müşterileriniz için Power BI içeriğini bir uygulamaya ekleme](embed-sample-for-customers.md)
* [Öğretici: Kuruluşunuz için Power BI içeriğini bir uygulamaya ekleme](embed-sample-for-your-organization.md)

 ### <a name="example"></a>Örnek
```javascript
var config = {
    type: 'report',
    tokenType: models.TokenType.Embed,
    accessToken: accessToken,
    embedUrl: embedUrl,
    id: "reportId", // The wanted report id
    permissions: permissions,

    /////////////////////////////////////////////
    // Adjustment required for dynamic binding //
    datasetBinding: {
        datasetId: "notOriginalDatasetId",  // </The wanted dataset id
    }
    // End of dynamic binding adjustment            //
    /////////////////////////////////////////////
};

// Get a reference to the embedded report HTML element
var embedContainer = $('#embedContainer')[0];

// Embed the report and display it within the div container
var report = powerbi.embed(embedContainer, config);
```