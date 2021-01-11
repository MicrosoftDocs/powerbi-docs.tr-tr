---
title: Daha iyi tümleşik BI içgörüleri için, Power BI tümleşik analizlerinde Power BI API'si ile neler yapabilirim?
description: Power BI API'si ile neler yapabilirim? Power BI tümleşik analiz kullanarak daha iyi tümleşik BI içgörüleri elde edin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: overview
ms.date: 03/25/2019
ms.openlocfilehash: 122028b2ac838763318ab5a0c4e6208138d93188
ms.sourcegitcommit: eeaf607e7c1d89ef7312421731e1729ddce5a5cc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2021
ms.locfileid: "97887627"
---
# <a name="what-can-developers-do-with-the-power-bi-api"></a>Geliştiriciler Power BI API ile neler yapabilir?

Power BI REST API kullanarak, Power BI raporlarıyla, panolarla ve kutucuklarla tümleşen uygulamalar oluşturabilirsiniz.

Power BI REST API ile raporlar, veri kümeleri ve çalışma alanları gibi Power BI nesneleri üzerinde yönetim görevleri gerçekleştirebilirsiniz.

Power BI API'lerle yapabileceğiniz bazı işlemler aşağıda verilmiştir.

| **Daha fazla bilgi almak için** | **Bu bilgilere başvurun** |
|----------------------------------------------------------------------------------|------------------------------------------------------------------------------------|
| Power BI kullanıcıları ve Power BI kullanıcısı olmayan kullanıcılar için raporlar, panolar ve kutucuklar ekleyin. | [Power BI panolarınızı, raporlarınızı ve kutucuklarınızı ekleme](../embedded/embed-sample-for-customers.md) |
| Power BI nesneleri üzerinde yönetim görevleri gerçekleştirin. | [Power BI Rest API başvurusu](/rest/api/power-bi/) |
| Power BI panosuna anahtar veri göndermek için mevcut iş akışını genişletme. | [Bir panoya veri gönderme](walkthrough-push-data.md) |
| Power BI'da kimlik doğrulaması yapma. | [Power BI'da kimlik doğrulaması yapma](../embedded/get-azuread-access-token.md) |

> [!NOTE]
> Power BI API'lerde çalışma alanları hâlâ gruplar olarak adlandırılmaktadır. Gruplara yapılan başvurular, çalışma alanlarıyla çalıştığınızı gösterir.

## <a name="api-developer-tools"></a>API Geliştirici araçları

| Araçlar | Açıklama |
|---------|-------------|
| [Deneme alanı aracı](https://microsoft.github.io/PowerBI-JavaScript/demo) | Power BI JavaScript API’lerini kullanmanın tam örneğini deneyin. Bu araç, farklı türde Power BI Embedded örnekleri ile yürütmenin de hızlı bir yoludur. |
| [Power BI JavaScript wiki](https://github.com/Microsoft/powerbi-javascript/wiki) | Power BI JavaScript API'leri hakkında daha fazla bilgi edinmek için. |
| [Postman](https://www.getpostman.com/) | İstekler çalıştırın, test edin, hata ayıklayın, izleyin, otomatik testler çalıştırın ve daha fazlasını yapın. |

## <a name="push-data-into-power-bi"></a>Power BI'a veri gönderme

[Veri kümesine veri göndermek için](walkthrough-push-data.md) Power BI API'yi kullanabilirsiniz. Bu özellik, bir veri kümesi içinde bulunan tabloya satır eklemenizi sağlar. Ardından, eklediğiniz yeni veriler panonuzdaki kutucuklara ve raporunuzdaki görsellere yansıtılır.

![Veri örneği gönderme](media/overview-of-power-bi-rest-api/powerbi-push-data.png)

## <a name="github-repositories"></a>GitHub depoları

* [Power BI Geliştirici örnekleri](https://github.com/Microsoft/PowerBI-Developer-Samples)
* [.NET SDK](https://github.com/Microsoft/PowerBI-CSharp)
* [JavaScript API’si](https://github.com/Microsoft/PowerBI-JavaScript)

## <a name="next-steps"></a>Sonraki Adımlar

* [Bir veri kümesine veri gönderme](walkthrough-push-data.md)
* [Power BI daire kartı görseli geliştirme](../visuals/develop-circle-card.md)
* [Power BI Rest API Başvurusu](rest-api-reference.md)
* [Power BI REST API'leri](/rest/api/power-bi/)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)