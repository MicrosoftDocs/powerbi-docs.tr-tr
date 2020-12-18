---
title: Power BI ekli analizinde dinamik bağlama kullanarak bir raporu veri kümesine bağlama
description: Dinamik bağlama kullanarak rapor eklemeyi öğrenin.
author: KesemSharabi
ms.author: kesharab
ms.topic: how-to
ms.service: powerbi
ms.subservice: powerbi-developer
ms.date: 11/07/2019
ms.openlocfilehash: d8a460f68838faab11cdab6d39f0e757a9789899
ms.sourcegitcommit: bbf7e9341a4e1cc96c969e24318c8605440282a5
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97098387"
---
# <a name="connect-a-report-to-a-dataset-using-dynamic-binding"></a>Dinamik bağlama kullanarak bir raporu veri kümesine bağlama 

Rapor bir veri kümesine bağlı olduğunda dinamik bağlamayı kullanabilirsiniz. Rapor ve veri kümesi arasındaki bağlantı, *bağlama* olarak bilinir. Bağlama, daha önceden belirlenmesinin aksine ekleme sırasında belirlendiğinde, bu işlem dinamik bağlama olarak bilinir.

*Dinamik bağlama* kullanarak bir Power BI raporu eklerken, kullanıcının kimlik bilgilerine bağlı olarak aynı raporu farklı veri kümelerine bağlayabilirsiniz.

Bu, farklı bilgileri göstermek için bağlı olduğu veri kümesine bağlı olarak bir rapor kullanabileceğiniz anlamına gelir. Örneğin, perakende satış değerlerini gösteren bir rapor farklı perakende satıcı veri kümelerine bağlanabilir ve bağlı olduğu perakende satıcının veri kümesine bağlı olarak farklı sonuçlar oluşturabilir.

Raporun ve veri kümesinin aynı çalışma alanında bulunması gerekmez. Her iki çalışma alanı da (raporu içeren çalışma alanı ve veri kümesini içeren çalışma alanı) bir [kapasiteye](azure-pbie-create-capacity.md) atanmalıdır.

Ekleme sürecinin bir parçası olarak, *yeterli izinlere sahip bir belirteç oluşturduğunuzdan* ve *yapılandırma nesnesini ayarladığınızdan* emin olun.

## <a name="generating-a-token-with-sufficient-permissions"></a>Yeterli izinlere sahip bir belirteç oluşturma

Dinamik bağlama, *Kuruluşunuz için ekleme* ve *Müşterileriniz için ekleme* senaryolarının her ikisi için de desteklenir. Aşağıdaki tabloda her senaryoya ilişkin değerlendirmeler açıklanmaktadır.

|Senaryo  |Veri sahipliği  |Belirteç  |Gereksinimler  |
|---------|---------|---------|---------|
|*Kuruluşunuz için içerik ekleme*    |Veriler kullanıcıya aittir         |Power BI kullanıcıları için erişim belirteci         |Azure AD belirteci kullanılan kullanıcının tüm yapıtlar için uygun izinlere sahip olması gerekir.         |
|*Müşterileriniz için içerik ekleme*     |Veriler uygulamaya aittir         |Power BI kullanıcısı olmayan kişiler için erişim belirteci         |Hem rapora hem de dinamik olarak bağlı veri kümesine yönelik izinleri içermelidir. [Birden çok öğe için ekleme belirteci oluşturmayı sağlayan API](/rest/api/power-bi/embedtoken/generatetoken)’yi kullanarak birden çok yapıtı destekleyen bir ekleme belirteci oluşturun.         |

## <a name="adjusting-the-config-object"></a>Yapılandırma nesnesini ayarlama
Yapılandırma nesnesine `datasetBinding` ekleyin. Aşağıdaki örneği başvuru olarak kullanın.

```javascript
var config = {
    type: 'report',
    tokenType: models.TokenType.Embed,
    accessToken: accessToken,
    embedUrl: embedUrl,
    id: "reportId", // The wanted report id
    permissions: permissions,

    // -----  Adjustment required for dynamic binding ---- //
    datasetBinding: {
        datasetId: "notOriginalDatasetId",  // </The wanted dataset id
    }
    // ---- End of dynamic binding adjustment ---- //
};

// Get a reference to the embedded report HTML element
var embedContainer = $('#embedContainer')[0];

// Embed the report and display it within the div container
var report = powerbi.embed(embedContainer, config);
```

## <a name="next-steps"></a>Sonraki adımlar

Power BI’da ekleme konusuna yeni başladıysanız, Power BI içeriğinizi nasıl ekleyeceğinizi öğrenmek için şu öğreticileri inceleyin:
* [Öğretici: Müşterileriniz için Power BI içeriğini bir uygulamaya ekleme](embed-sample-for-customers.md)
* [Öğretici: Kuruluşunuz için Power BI içeriğini bir uygulamaya ekleme](embed-sample-for-your-organization.md)