---
title: Power BI Embedded'da Soru-Cevap
description: Power BI Embedded, Soru-Cevap özelliğini uygulamaya eklemenizi ve kullanıcılarınıza doğal dil kullanarak soru sorma olanağı vermenizi sağlayan bir yöntem sunar.
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 11/20/2017
ms.openlocfilehash: afe53e7b24328612bd7858abe263e4365f1c891d
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "61268740"
---
# <a name="qa-in-power-bi-embedded"></a>Power BI Embedded'da Soru-Cevap

Power BI Embedded, Soru-Cevap özelliğini uygulamaya eklemenizi ve kullanıcılarınıza doğal dil kullanarak soru sorma ve tablo veya grafik gibi görsellerle anında cevap alma olanağı vermenizi sağlayan bir yöntem sunar.

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
    viewMode:    models.QnAMode.Interactive | models.QnAMode.ResultOnly,
    question:    optional parameter for Explore mode (QnAMode.Interactive) and mandatory for Render Result mode (QnAMode.ResultOnly)
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

Soru-Cevap bölümü eklemek için bir veri kümesinden ekleme belirteci oluşturmanız gerekir. Daha fazla bilgi için bkz. [Belirteç oluşturma](https://docs.microsoft.com/rest/api/power-bi/embedtoken).

## <a name="next-steps"></a>Sonraki adımlar

Soru-Cevap işlevini eklemeyi denemek için [JavaScript ekleme örneğini](https://microsoft.github.io/PowerBI-JavaScript/demo/) inceleyin.

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)
