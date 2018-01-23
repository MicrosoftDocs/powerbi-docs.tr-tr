---
title: "Geliştiriciler Power BI ile neler yapabilir?"
description: "Power BI, geliştiriciler için çok çeşitli seçenekler sunar. Ekleme, özel görseller ve akış veri kümeleri bu seçenekler arasında yer almaktadır."
services: powerbi
documentationcenter: 
author: guyinacube
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 07/20/2017
ms.author: asaxton
ms.openlocfilehash: c5dfbbf5150dbf8ddb4388ac64f6c313eedd578e
ms.sourcegitcommit: 7517c068db806f12bb0b953e9a1bd4249ca12da5
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2018
---
# <a name="what-can-developers-do-with-power-bi"></a>Geliştiriciler Power BI ile neler yapabilir?
Power BI, geliştiriciler için çok çeşitli seçenekler sunar. Ekleme, özel görseller ve akış veri kümeleri bu seçenekler arasında yer almaktadır.

## <a name="embedding"></a>Ekleme
Power BI hizmeti ve Azure'daki Power BI Embedded uygulaması, panolarınızı ve raporlarınızı eklemek için tek bir API sunmak üzere bir araya geliyor. Başka bir deyişle tek bir API yüzeyi, içeriğinizi eklerken kullanabileceğiniz tutarlı özellik kümesi ve panolar, ağ geçitleri ve uygulama çalışma alanları gibi en yeni Power BI özeliklerine erişim sahibi olacaksınız. Daha fazla bilgi için bkz. [Power BI ile ekleme](embedding.md).

![](media/what-can-you-do/powerbi-embed-sample.png)

## <a name="custom-visuals"></a>Özel görseller
Özel görseller, Power BI raporlarında kullanmak üzere kendi görsellerinizi oluşturmanızı sağlar. Özel görseller bazı gelişmiş özellikleri ve ES6/ES7 işlevlerine erken erişimi destekleyen TypeScript (JavaScript'in bir üst kümesi) dilinde yazılır. Görsel stili, basamaklı biçim tabloları (css) kullanılarak işlenir. Size kolaylık sağlamak adına, iç içe geçme, değişkenler, mixin'ler, koşullar ve döngüler gibi bazı gelişmiş özellikleri destekleyen LESS ön derleyicisini kullanıyoruz. Bu özelliklerden hiçbirini kullanmak istemiyorsanız less dosyasında yalın css yazmayı da tercih edebilirsiniz.

Özel görsel geliştirme ve yayımlama hakkında daha fazla bilgi için bkz. [Özel görselleri Office Mağazası'nda yayımlama](office-store.md).

![](media/what-can-you-do/powerbi-custom-visual-store.png)

## <a name="push-data-into-power-bi"></a>Power BI'a veri gönderme
Veri kümesine veri göndermek için Power BI API'yi kullanabilirsiniz. Bu sayede bir veri kümesi içinde bulunan tabloya satır ekleyebilirsiniz. Eklediğiniz yeni veriler panonuzdaki kutucuklara ve raporunuzdaki görsellere yansıtılır.

Daha fazla bilgi için bkz. [Bir panoya veri gönderme](walkthrough-push-data.md)

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile ekleme](embedding.md)  
[Power BI Embedded çalışma alanı koleksiyon içeriğini Power BI'a geçirme](migrate-from-powerbi-embedded.md)  
[JavaScript API'si Git deposu](https://github.com/Microsoft/PowerBI-JavaScript)  
[Power BI C# Git deposu](https://github.com/Microsoft/PowerBI-CSharp)  
[Özel görselleri Office Mağazası'nda yayımlama](office-store.md)  
[Power BI Görselleri Git deposu](https://github.com/Microsoft/PowerBI-visuals)  
[JavaScript ekleme örneği](https://microsoft.github.io/PowerBI-JavaScript/demo/)  
[Power BI Premium teknik incelemesi](https://aka.ms/pbipremiumwhitepaper)  
Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

