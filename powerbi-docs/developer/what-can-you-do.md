---
title: Geliştiriciler Power BI ile neler yapabilir?
description: Power BI, geliştiriciler için çok çeşitli seçenekler sunar. Ekleme, özel görseller ve akış veri kümeleri bu seçenekler arasında yer almaktadır.
services: powerbi
author: markingmyname
ms.author: maghan
ms.date: 05/03/2018
ms.topic: overview
ms.service: powerbi
ms.custom: mvc
manager: kfile
ms.openlocfilehash: 473052ee652c1fd6e68294efdbd7334cbb2df714
ms.sourcegitcommit: 493f160d04ed411ff4741c599adc63ba1f65230f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33810978"
---
# <a name="what-can-developers-do-with-power-bi"></a>Geliştiriciler Power BI ile neler yapabilir?

Geliştiriciler, Power BI içeriğini uygulamalara eklemek için farklı seçenekler deneyebilir. Bu seçeneklere **Power BI ile ekleme**, **özel görseller** ve **Power BI’ya veri gönderme** dahildir.

## <a name="embedding"></a>Ekleme
Power BI hizmetinde (SaaS) ve Azure’daki Power BI Embedded hizmetinde (PaaS), panolarınızı ve raporlarınızı eklemeye yönelik API’ler bulunur. Başka bir deyişle içeriğinizi eklerken kullanabileceğiniz bir özellik kümesi ve panolar, ağ geçitleri ve uygulama çalışma alanları gibi en yeni Power BI özeliklerine erişim sahibi olacaksınız.

![PBIE örneği](media/what-can-you-do/what-can-you-do-01.png)

## <a name="develop-custom-visuals"></a>Özel görseller geliştirme
Özel görseller, Power BI raporlarında kullanmak üzere kendi görsellerinizi oluşturmanızı sağlar. Özel görseller bir JavaScript üst kümesi olan TypeScript dilinde yazılır. TypeScript, bazı gelişmiş özellikleri ve ES6/ES7 işlevine erken erişimi destekler. Görsel stili, basamaklı biçim tabloları (css) kullanılarak işlenir. Size kolaylık sağlamak adına, iç içe geçme, değişkenler, koşullar ve döngüler gibi bazı gelişmiş özellikleri destekleyen LESS ön derleyicisini kullanıyoruz. Bu özelliklerden hiçbirini kullanmak istemiyorsanız less dosyasında yalın css yazmayı da tercih edebilirsiniz.

![CV örneği](media/what-can-you-do/powerbi-custom-visual-store.png)

## <a name="push-data-into-power-bi"></a>Power BI'a veri gönderme
Veri kümesine veri göndermek için Power BI API'yi kullanabilirsiniz. Bu sayede bir veri kümesi içinde bulunan tabloya satır ekleyebilirsiniz. Eklediğiniz yeni veriler panonuzdaki kutucuklara ve raporunuzdaki görsellere yansıtılır.

![Veri örneği gönderme](media/what-can-you-do/powerbi-push-data.png)

## <a name="next-steps"></a>Sonraki adımlar
[Power BI ile ekleme](embedding.md)  
[Özel görselleri Office Mağazası'nda yayımlama](office-store.md)  
[Bir panoya veri gönderme](walkthrough-push-data.md)
