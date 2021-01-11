---
title: Power BI tümleşik analizindeki tümleşik BI Power BI Azure Power BI Embedded nedir?
description: Power BI Embedded, ISV’lerin ve geliştiricilerin uygulamalarına hızlıca etkileyici görseller, raporlar ve panolar eklemelerine yardımcı olarak tümleşik BI Power BI özelliklerini daha kolayca kullanmalarını sağlamayı hedefleyen tümleşik bir analiz aracı olarak tasarlanmıştır. Power BI Embedded kullanarak tümleşik analiz yazılımını, tümleşik analiz araçlarını veya tümleşik iş zekası araçlarını kullanma hakkında bilgi edinin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: nishalit
ms.service: powerbi
ms.subservice: powerbi-developer
ms.devlang: csharp, javascript
ms.topic: overview
ms.custom: seodec18
ms.date: 12/10/2018
ms.openlocfilehash: 1c2227e376879693833af18c5c30acda9f6b16dd
ms.sourcegitcommit: eeaf607e7c1d89ef7312421731e1729ddce5a5cc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2021
ms.locfileid: "97887236"
---
# <a name="what-is-power-bi-embedded-in-azure"></a>Azure’da Power BI Embedded nedir?

Power BI Embedded, ISV’lerin ve geliştiricilerin tümleşik analiz ile Power BI özelliklerini kullanım şeklini kolaylaştırmak için tasarlanmıştır. Power BI Embedded, uygulamalarınıza hızla etkileyici görseller, raporlar ve panolar eklemenize yardımcı olarak Power BI özelliklerini daha basit hale getirir. Bu durum, Microsoft Azure üzerinde oluşturulan uygulamaların Machine Learning ve IoT gibi hizmetleri kullanma şekline benzer. ISV'ler, uygulamalarında gezinmesi kolay veri keşfi özellikleri sunarak müşterilerinin bağlam içinde hızlı ve bilgiye dayalı kararlar vermesini sağlar.

> [!VIDEO https://www.youtube.com/embed/iEHfUuoZseo]

Mayıs 2017'de Power BI ve Power BI Embedded hizmetlerinin yakınsama duyurusunu yaptık. Yakınsama bir API yüzeyi, tutarlı özellik kümesi ve iki hizmette de en son özelliklere erişim imkanı sunuldu. Ayrıca Power BI tüketimini basitleştiren bir kapasite tabanlı fiyatlandırma modelini de kullanıma aldık.

ISV'ler ve geliştiriciler Power BI Embedded ile uygulamalarına Power BI API'lerini kullanarak zeka ekleme konusunda esnekliğe sahip olur. ISV'ler ve geliştiriciler, uygulamalarında Microsoft'un birinci sınıf analiz altyapısını kullanarak piyasaya daha hızlı ulaşmak ve fark yaratmak için minimum düzeyde geliştirme çalışmalarından faydalanabilirler. Geliştiriciler de zamanını görsel analiz özellikleri geliştirmek yerine müşteri isteklerini yerine getirmek için çözümleri üzerinde çalışmaya ayırabilir. Power BI Embedded ayrıca Visual Studio ve Azure gibi kullanmakta olduğunuz geliştirme ortamlarında çalışmanıza imkan tanır.

Power BI Premium kullanan Power BI içeriğinin eklenmiş olduğu bir uygulamanız mı var? Uygulamaları dağıtan bir ISV veya geliştirici ya da bunları kullanan bir kuruluşsanız herhangi bir eylem gerçekleştirmeniz gerekmez. Müşterilerinizle birlikte bu uygulamaları kesinti yaşamadan kullanmaya devam edebilirsiniz. Power BI Çalışma Alanı Koleksiyonları üzerinde derlenmiş bir uygulamanız varsa ve yakınsanmış API yüzeyi ile yeni kapasite tabanlı Azure SKU'larından faydalanmak istiyorsanız geçiş kılavuzu belgelerini inceleyin.

## <a name="comparing-power-bi-embedded-with-power-bi-premium"></a>Power BI Embedded ile Power BI Premium karşılaştırması

**Power BI Embedded**, müşterileri için uygulamalar derleyen bağımsız yazılım satıcıları (ISV) ve geliştiriciler için tasarlanmıştır. Hizmeti oluşturmak yerine uygulama verilerini görselleştirmenizi sağlayan üçüncü taraf iş zekası hizmeti olarak kullanılabilir. Power BI Embedded, geliştiricilerin müşterileri için tasarladığı bir uygulamaya rapor ve pano ekleyebileceği bir hizmet olarak platform (PaaS) analiz çözümüdür. **Power BI Premium** ise kuruluşunuza en kritik iş verilerini tek bir görünümde sunan hizmet olarak yazılım (SaaS) analiz çözümüdür. 

[Power BI Embedded](https://azure.microsoft.com/pricing/details/power-bi-embedded/) kullandıkça öde modeline sahipken [Power BI Premium](https://powerbi.microsoft.com/calculator/) için aylık ücret alınır. Farklar hakkında daha fazla bilgiye bu [videodan](https://www.youtube.com/watch?v=0y2oJikC6Xc&t=0s&list=PLv2BtOtLblH1dQPV49Ni12olDcUoW-GEl&index=3) ulaşabilirsiniz.

## <a name="easy-to-use-tools"></a>Kullanımı kolay araçlar

Power BI Embedded, zamanınızı en iyi yaptığınız şeye yani harika uygulamalar oluşturmaya ayırmanızı sağlar. Sahip olduğunuz araçları ve becerileri kullanarak Power BI Embedded ile yönetim ve geliştirme gerçekleştirebilirsiniz.

* [**Azure portal**](https://portal.azure.com/): Tüm Azure hizmetlerini yönetebileceğiniz web tabanlı platformdur
* [**Visual Studio Code**](https://code.visualstudio.com/docs): Windows, macOS ve Linux için uzantı destekli ücretsiz, indirilebilir, açık kaynak kod düzenleyicisidir
* [**Power BI Desktop**](https://powerbi.microsoft.com/desktop/): Görsel analize sahip zengin ve etkileşimli raporlar oluşturmanızı sağlayan ve ücretsiz olarak indirilebilen araçtır

REST API'sini kullanarak Power BI Embedded'da istediğiniz dilde yazılım geliştirebilirsiniz.

## <a name="engage-with-the-power-bi-engineering-team"></a>Power BI mühendislik ekibiyle iletişime geçin

* [Topluluklar](https://community.powerbi.com/): Power BI ile ilgili sorularınızı yöneltin
* [Power BI Ideas](https://ideas.powerbi.com): Özellik isteğinde bulunun ve istekleri oylayın
* [Reddit](https://www.reddit.com/r/PowerBI/): Power BI hakkındaki tartışmalara katılın

## <a name="next-steps"></a>Sonraki adımlar

Kapasite düğümü ayrıntıları için [fiyatlandırma sayfasına](https://azure.microsoft.com/pricing/details/power-bi-embedded/) bakın.

Power BI Embedded kapasitesi oluşturmak için bkz. [Azure portalında Power BI Embedded kapasitesi oluşturma](azure-pbie-create-capacity.md)

Power BI içeriğinizi eklemeye başlamak için bkz. [Power BI panolarınızı, raporlarınızı ve kutucuklarınızı ekleme](https://powerbi.microsoft.com/documentation/powerbi-developer-embedding-content/).
