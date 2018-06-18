---
title: Power BI API ile neler yapabilirim?
description: Power BI API ile neler yapabilirim?
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 05/25/2018
ms.author: maghan
ms.openlocfilehash: 8a688f46a46dbb1015629c7785d96b62d4f8df26
ms.sourcegitcommit: 8ee0ebd4d47a41108387d13a3bc3e7e2770cbeb8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/06/2018
ms.locfileid: "34813262"
---
# <a name="what-can-developers-do-with-the-power-bi-api"></a>Geliştiriciler Power BI API ile neler yapabilir?
Power BI, gerçek zamanlı olarak pek çok farklı veri kaynağından oluşturulabilen ve güncelleştirilebilen etkileşimli panolar görüntüler. REST çağrılarını destekleyen herhangi bir programlama dilini kullanarak, Power BI panosuyla gerçek zamanlı olarak tümleşebilen uygulamalar oluşturabilirsiniz. Ayrıca, Power BI kutucuklarını ve raporlarını da uygulamalara tümleştirebilirsiniz.

Geliştiriciler ayrıca etkileşimli raporlarda ve panolarda kullanılması mümkün kendi veri görselleştirmelerini de oluşturabilirler. 

Power BI API'lerle yapabileceğiniz bazı işlemler aşağıda verilmiştir.

| **Bunu gerçekleştirmek için:** | **Buraya gidin** |
| --- | --- |
| Power BI kullanıcıları ve Power BI kullanıcısı olmayan kullanıcılar için (uygulama veriye sahiptir) panolar, raporlar ve kutucuklar ekleme |[Power BI panolarınızı, raporlarınızı ve kutucuklarınızı ekleme](embedding-content.md) |
| Power BI panosuna anahtar veri göndermek için mevcut iş akışını genişletme. |[Bir panoya veri gönderme](walkthrough-push-data.md) |
| Power BI'da kimlik doğrulaması yapma. |[Power BI'da kimlik doğrulaması yapma](get-azuread-access-token.md) |
| Özel görsel oluşturma. |[Özel görseller oluşturmak için geliştirici araçları kullanma](../service-custom-visuals-getting-started-with-developer-tools.md) |

> [!NOTE]
> Power BI API'lerde uygulama çalışma alanları hâlâ gruplar olarak adlandırılmaktadır. Gruplara yapılan başvurular, uygulama çalışma alanlarıyla çalıştığınızı gösterir.
> 
> 

## <a name="power-bi-developer-samples"></a>Power BI Geliştirici Örnekleri
Power BI Geliştirici örnekleri pano, rapor ve kutucuk eklemek için öğeler içerir.

[Power BI Geliştirici örnekleri](https://github.com/Microsoft/PowerBI-Developer-Samples)

* **App Owns Data** (Uygulama Veriye Sahiptir) özellikli örnekler Power BI kullanıcısı olmayan kullanıcıları eklemek için kullanılır.
* **User Owns Data** (Kullanıcı Veriye Sahiptir) özellikli örnekler Power BI kullanıcısı olan kullanıcıları eklemek için kullanılır.

## <a name="github-repositories"></a>GitHub depoları
* [.NET SDK](https://github.com/Microsoft/PowerBI-CSharp)
* [JavaScript API'si](https://github.com/Microsoft/PowerBI-JavaScript)
* [Özel Görseller](https://github.com/Microsoft/PowerBI-visuals)

## <a name="developer-tools"></a>Geliştirici araçları
Aşağıda Power BI öğeleri geliştirmede yardımcı olacak araçlar verilmiştir.

Hızlıca çalışmaya başlamak ve Power BI içeriği eklemeye ilişkin bir örnek uygulama indirmek için [Ekleme deneyimi aracını](https://aka.ms/embedsetup) inceleyebilirsiniz.

Size uygun olan çözümü seçin:
* [Embedding for your customers](embedding.md#embedding-for-your-customers) seçeneği, Power BI hesabı olmayan kullanıcılar için panolar ve raporlar eklemenize olanak sağlar. [Embed for your customers](https://aka.ms/embedsetup/AppOwnsData) çözümünü çalıştırın.
* [Embedding for your organization](embedding.md#embedding-for-your-organization) seçeneği, Power BI hizmetinin kapsamını genişletmenize olanak tanır. [Embed for your organization](https://aka.ms/embedsetup/UserOwnsData) çözümünü çalıştırın.

JavaScript API kullanan tam bir örnek için [Playground aracı](https://microsoft.github.io/PowerBI-JavaScript/demo)'nı kullanabilirsiniz. Bunu yapmak, farklı türde Power BI Embedded örnekleri ile yürütmenin hızlı bir yoludur. Ayrıca [PowerBI-JavaScript wiki](https://github.com/Microsoft/powerbi-javascript/wiki) sayfasını ziyaret ederek JavaScript API’si hakkında daha fazla bilgi alabilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar
[Bir veri kümesine veri gönderme](walkthrough-push-data.md)  
[Özel görseller geliştirici araçları ile çalışmaya başlama](../service-custom-visuals-getting-started-with-developer-tools.md) 
[Power BI REST API başvurusu](https://docs.microsoft.com/rest/api/power-bi/)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)