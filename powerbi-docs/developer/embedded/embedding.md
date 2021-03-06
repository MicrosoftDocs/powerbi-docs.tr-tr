---
title: Daha iyi tümleşik BI içgörüleri için, Power BI tümleşik analizleriyle tümleşik analizler
description: Power BI, uygulamalara Power BI tümleşik analiz panoları ve raporları eklemek için API'ler sunar. Power BI tümleşik analiz kullanarak daha iyi tümleşik BI içgörüleri elde edin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: overview
helpviewer_keywords:
- embedded analytics
- embedding
- Power BI embedding
- app owns data
- user owns data
- Power BI APIs
ms.custom: seodec18
ms.date: 05/15/2019
ms.openlocfilehash: c7278dee5957e2b63b6821decec0171ba6b628a0
ms.sourcegitcommit: eeaf607e7c1d89ef7312421731e1729ddce5a5cc
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2021
ms.locfileid: "97887144"
---
# <a name="embedded-analytics-with-power-bi"></a>Power BI ile tümleşik analiz

Power BI hizmetinde (SaaS) ve Azure’daki Power BI Embedded hizmetinde (PaaS), panolarınızı ve raporlarınızı eklemeye yönelik API’ler bulunur. Bu özellik, içeriğinizi eklerken panolar, ağ geçitleri ve çalışma alanları gibi en yeni Power BI özeliklerine erişmenize olanak tanır.

Bir örnek uygulamayı indirmek ve hızlıca başlamak için [Ekleme kurulum aracını](https://aka.ms/embedsetup) inceleyebilirsiniz.

Size uygun olan çözümü seçin:

* [Embedding for your organization](embedding.md#embedding-for-your-organization) seçeneği, Power BI hizmetinin kapsamını genişletmenize olanak tanır. Bunu yapmak için [Ekleme kurulum aracı](https://app.powerbi.com/embedsetup) içinde *Kuruluşunuz için ekleme* çözümünü uygulayın.
* [Müşterileriniz için ekleme](embedding.md#embedding-for-your-customers) seçeneği, Power BI hesabı olmayan kullanıcılar için panolar ve raporlar eklemenize olanak sağlar. Bunu yapmak için [Ekleme kurulum aracı](https://app.powerbi.com/embedsetup) içinde *Müşterileriniz için ekleme* çözümünü uygulayın.

![PBIE örneği](media/embedding/what-can-you-do-02.png)

## <a name="use-apis"></a>API'leri kullanma

Power BI içeriğini eklerken kullanılabilecek iki ana senaryo vardır:
- Kuruluşunuzun (Power BI lisansı olan) kullanıcıları için ekleme. 
 
- Power BI lisansı gerektirmeden kullanıcılarınız ve müşterileriniz için ekleme. 

[Power BI REST API](/rest/api/power-bi/)'si iki senaryo için de kullanılabilir.

Power BI lisansı olmayan müşteriler ve kullanıcılar için panoları ve raporları özel uygulamanıza ekleyebilir, aynı API'yi kullanarak kuruluşunuza veya müşterilerinize sunabilirsiniz. Müşterileriniz uygulama tarafından yönetilen verileri görür. Ayrıca, kuruluşunuzdaki Power BI kullanıcıları da *verilerini* doğrudan Power BI'da veya eklenen uygulamanın bağlamında görüntülemeye ilişkin ek seçeneklere sahip olur. İçerik eklerken JavaScript ve REST API'lerinin tüm özelliklerini kullanabilirsiniz.

İçerik eklemenin nasıl çalıştığını anlamak için bkz. [JavaScript ekleme örneği](https://microsoft.github.io/PowerBI-JavaScript/demo/).

## <a name="embedding-for-your-organization"></a>Kuruluşunuz için içerik ekleme

**Embedding for your organization** seçeneği, Power BI hizmetinin kapsamını genişletmenize olanak tanır. Bu tür eklemeler, uygulama kullanıcılarınızın içeriği görüntülemek için Power BI hizmetinde oturum açmasını gerektirir. Kuruluşunuzdaki bir kullanıcı oturum açtığında yalnızca sahip olduğu veya Power BI hizmetinde birisinin kendisiyle paylaştığı panolara ve raporlara erişebilir.

Kuruluşunuz için içerik ekleme örnekleri arasında [SharePoint Online](https://powerbi.microsoft.com/blog/integrate-power-bi-reports-in-sharepoint-online/), [Microsoft Teams tümleştirmesi (Yönetici haklarına sahip olmanız gerekir)](https://powerbi.microsoft.com/blog/power-bi-teams-up-with-microsoft-teams/) ve [Microsoft Dynamics](/dynamics365/customer-engagement/basics/add-edit-power-bi-visualizations-dashboard) gibi şirket içi uygulamalar bulunur.

Kuruluşunuz için eklemek istiyorsanız şu [Öğretici’ye göz atın: Kuruluşunuz için Power BI içeriğini bir uygulamaya ekleme](embed-sample-for-your-organization.md).

Düzenleme ve kaydetme gibi self servis özellikleri Power BI kullanıcıları için ekleme yaparken [JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)’si aracılığıyla kullanılabilir.

Kullanmaya başlamak ve kuruluşunuz için bir raporu tümleştirme adımlarını gösteren örnek bir uygulama indirmek için [Ekleme kurulum aracını](https://app.powerbi.com/embedsetup) inceleyebilirsiniz.

## <a name="embedding-for-your-customers"></a>Müşterileriniz için içerik ekleme

**Müşterileriniz için ekleme** seçeneği, Power BI hesabı olmayan kullanıcılar için panolar ve raporlar eklemenize olanak sağlar. Bu ekleme türü seçeneği *Power BI Embedded* olarak da bilinir.

[Power BI Embedded](azure-pbie-what-is-power-bi-embedded.md), bağımsız yazılım satıcılarının (ISV) ve geliştiricilerin uygulamaya görseller, raporlar ve panolar eklemesini sağlayan bir **Microsoft Azure** hizmetidir. Ekleme, kapasite-tabanlı, saatlik tarifeli bir model aracılığıyla yapılır.

![Müşterileriniz için içerik ekleme akışı](media/embedding/powerbi-embed-flow.png)

Power BI Embedded'in ISV'lere, onların geliştiricilerine ve müşterilerine yönelik avantajları vardır. Örneğin, bir ISV Power BI Desktop ile ücretsiz olarak görseller oluşturmaya başlayabilir. ISV'ler görsel analiz geliştirme çabalarını en aza indirerek pazara sunma sürecini hızlandırabilir ve fark yaratan veri deneyimleriyle rakipleri arasında öne çıkabilir. Ayrıca ISV'ler eklenen analitik sayesinde oluşturulan ek değer için bir ücret almayı tercih edebilir.

Power BI Embedded ile müşterilerinizin Power BI ile ilgili bilgi sahibi olmalarına gerek yoktur. Eklenmiş uygulama oluşturmak için iki farklı yöntem kullanabilirsiniz:
- Power BI Pro hesabı 
- Hizmet sorumlusu 

Power BI Pro hesabı, uygulamanızın ana hesabı olarak kullanılır (bunu ara sunucu hesabı olarak düşünün). Bu hesap ayrıca Power BI hizmetindeki panolara ve raporlara erişim sağlayan ekleme belirteçlerini oluşturmanızı da sağlar.

[Hizmet sorumlusu](embed-service-principal.md) bir **yalnızca uygulama** belirteci kullanarak Power BI içeriğini uygulamaya ekleyebilir. Power BI hizmetindeki panolara ve raporlara erişim sağlayan ekleme belirteçlerini oluşturmanızı da sağlar.

Geliştiriciler, Power BI Embedded kullanarak görselleri ve analitiği geliştirmeye zaman harcamak yerine uygulamalarının temel işlevselliğini oluşturmaya zaman ayırabilir. Müşterilerin rapor ve pano taleplerini hızla karşılayıp tümüyle belgelenmiş API'leri ve SDK'ları kolayca ekleyebilirler. ISV'ler uygulamalarında gezinmesi kolay veri keşfi özellikleri sunarak müşterilerinin her cihazdan bağlam içinde hızlı ve veri odaklı kararlar vermesini sağlar.

> [!IMPORTANT]
> Ekleme Power BI hizmetini gerektirse de uygulamanızın eklenmiş içeriğini görüntülemek için müşterilerinizin bir Power BI hesabı olması gerekmez.

Üretim aşamasına geçmeye hazır olduğunuzda çalışma alanınızın bir kapasiteye atanması gerekir. Uygulamalarınızla birlikte kullanmak üzere Microsoft Azure'da [Power BI Embedded kapasitesi oluşturun](azure-pbie-create-capacity.md).

Ekleme işleminin ayrıntıları için bkz. [Power BI içeriğini ekleme](embed-sample-for-customers.md).

## <a name="next-steps"></a>Sonraki adımlar

Artık Power BI içeriğini uygulamaya eklemeyi veya müşterileriniz için Power BI içeriği eklemeyi deneyebilirsiniz.

> [!div class="nextstepaction"]
> [Kuruluşunuz için ekleme](embed-sample-for-your-organization.md)

> [!div class="nextstepaction"]
> [Power BI Embedded nedir?](azure-pbie-what-is-power-bi-embedded.md)

> [!div class="nextstepaction"]
>[Müşterileriniz için ekleme](embed-sample-for-customers.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)