---
title: Daha iyi tümleşik BI içgörüleri için, Power BI tümleşik analizlerinde Soru-Cevap
description: Power BI Embedded, bir uygulamaya Soru-Cevap özelliği eklemenizi ve kullanıcılarınıza doğal dili kullanarak soru sorma olanağı tanımanızı sağlayan bir yöntem sunmaktadır. Power BI tümleşik analiz kullanarak daha iyi tümleşik BI içgörüleri elde edin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: how-to
ms.date: 11/20/2017
ms.openlocfilehash: 43e886e6472c6d95b900ccdb5c2e73b8dca3d4a0
ms.sourcegitcommit: eeaf607e7c1d89ef7312421731e1729ddce5a5cc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2021
ms.locfileid: "97886615"
---
# <a name="qa-in-power-bi-embedded-analytics"></a>Power BI tümleşik analizlerinde Soru-Cevap

Power BI tümleşik analizleri, bir uygulamaya Soru-Cevap özelliği eklemeniz ve kullanıcılarınıza doğal dili kullanarak soru sorma ve çizelge veya grafik gibi görsel biçimlerde anında yanıt alma olanağı tanımanız için bir yöntem sunmaktadır.

![Ekli çerçevede Soru-Cevap ile etkileşimli soru](media/qanda/embedded-qanda.gif)

Soru-Cevap işlevini uygulamanıza eklemek için kullanabileceğiniz iki mod vardır: **etkileşimli** ve **yalnızca sonuç**. **Etkileşimli** mod ile soru yazabilir ve görselde görüntülenmesini sağlayabilirsiniz. Görüntülemek istediğiniz kayıtlı soru veya sorular varsa **yalnızca sonuç** modunu kullanarak soruyu ekleme yapılandırmasına ekleyebilirsiniz.

JavaScript kodu aşağıdaki şekilde görünecektir.

```javascript
// Embed configuration used to describe the what and how to embed.
// This object is used when calling powerbi.embed within the JavaScript API.
// You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
var config= {
    type: 'qna',
    tokenType:   models.TokenType.Embed | models.TokenType.Aad,
    accessToken: access token value,
    embedUrl:    https://app.powerbi.com/qnaEmbed (groupId to be appended as query parameter if required),
    datasetIds:  array of requested data set ids (at the moment we support only one dataset),
    viewMode:    models.QnaMode.Interactive | models.QnaMode.ResultOnly,
    question:    optional parameter for Explore mode (QnaMode.Interactive) and mandatory for Render Result mode (QnaMode.ResultOnly)
};

// Get a reference to the embedded QNA HTML element
var qnaContainer = $('#qnaContainer')[0];

// Embed the QNA and display it within the div container.
var qna = powerbi.embed(qnaContainer, config);
```

## <a name="set-question"></a>Belirlenmiş soru

Belirlenmiş bir soru ile **sonuç modunu** kullandıysanız çerçeveye ek sorular dahil edebilir ve anında yanıtlanmasını sağlayarak önceki sonucu değiştirebilirsiniz. Yeni soruya uygun yeni bir görsel oluşturulur.

Bu yönteme örnek olarak sık sorulan sorular listesi verilebilir. Kullanıcı aynı ekli bölümde bulunan soruları inceleyip yanıtlarını alabilir.

**JS SDK kullanımı için kod parçacıkları:**  

```javascript
// Get a reference to the embedded Q&A HTML element
var qnaContainer = $('#qnaContainer')[0];

// Get a reference to the embedded Q&A.
qna = powerbi.get(qnaContainer);

qna.setQuestion("This year sales")
    .then(function (result) {
        …….
    })
    .catch(function (errors) {
        …….
    });
```

## <a name="visual-rendered-event"></a>visualRendered olayı

**Etkileşimli** modda uygulama, oluşturulan görsel her değiştirildiğinde bir veri değiştirme olayıyla bilgilendirilerek yazılmakta olan güncelleştirilmiş giriş sorgusuna göre sonuç getirmesi sağlanabilir.

*visualRendered* olayını dinleyerek soruları daha sonra kullanılmak üzere kaydedebilirsiniz. 

**JS SDK kullanımı için kod parçacıkları:**  

```javascript
// Get a reference to the embedded Q&A HTML element
var qnaContainer = $('#qnaContainer')[0];

// Get a reference to the embedded Q&A.
qna = powerbi.get(qnaContainer);

// qna.off removes a given event listener if it exists.
qna.off("visualRendered");

// qna.on will add an event listener.
qna.on("visualRendered", function(event) {
     …….
});
```

## <a name="embed-token"></a>Ekleme belirteci

Soru-Cevap bölümü eklemek için bir veri kümesinden ekleme belirteci oluşturmanız gerekir. Daha fazla bilgi için bkz. [Belirteç oluşturma](/rest/api/power-bi/embedtoken).

## <a name="next-steps"></a>Sonraki adımlar

Soru-Cevap işlevini eklemeyi denemek için [JavaScript ekleme örneğini](https://microsoft.github.io/PowerBI-JavaScript/demo/) inceleyin.

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)