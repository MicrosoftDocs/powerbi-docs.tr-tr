---
title: Geliştiriciler Power BI ile neler yapabilir?
description: Power BI, geliştiriciler için çok çeşitli seçenekler sunar. Ekleme, özel görseller ve akış veri kümeleri bu seçenekler arasında yer almaktadır.
author: markingmyname
ms.author: maghan
ms.date: 05/25/2018
ms.topic: overview
ms.service: powerbi
ms.component: powerbi-developer
ms.custom: mvc
manager: kfile
ms.openlocfilehash: 07fb8d365a6fe4a874b057a71a90a99fc8a9e5fa
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34564708"
---
# <a name="what-can-developers-do-with-power-bi"></a>Geliştiriciler Power BI ile neler yapabilir?

Geliştiriciler, Power BI içeriğini uygulamalara eklemek için farklı seçenekler deneyebilir. Bu seçeneklere **Power BI ile ekleme**, **özel görseller** ve **Power BI’ya veri gönderme** dahildir.

## <a name="embedding"></a>Ekleme
Power BI hizmetinde (SaaS) ve Azure’daki Power BI Embedded hizmetinde (PaaS), panolarınızı ve raporlarınızı eklemeye yönelik API’ler bulunur. Başka bir deyişle içeriğinizi eklerken kullanabileceğiniz bir özellik kümesi ve panolar, ağ geçitleri ve uygulama çalışma alanları gibi en yeni Power BI özeliklerine erişim sahibi olacaksınız.

Hızlıca çalışmaya başlamak ve bir örnek uygulama indirmek için [Ekleme deneyimi aracını](https://aka.ms/embedsetup) inceleyebilirsiniz.

Size uygun olan çözümü seçin:
* [Embedding for your customers](embedding.md#embedding-for-your-customers) seçeneği, Power BI hesabı olmayan kullanıcılar için panolar ve raporlar eklemenize olanak sağlar. [Embed for your customers](https://aka.ms/embedsetup/AppOwnsData) çözümünü çalıştırın.
* [Embedding for your organization](embedding.md#embedding-for-your-organization) seçeneği, Power BI hizmetinin kapsamını genişletmenize olanak tanır. [Embed for your organization](https://aka.ms/embedsetup/UserOwnsData) çözümünü çalıştırın.

![PBIE örneği](media/what-can-you-do/what-can-you-do-02.png)

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
