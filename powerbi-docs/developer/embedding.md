---
title: Power BI ile tümleşik analiz
description: Power BI, panolarınıza ve raporlarınıza yönelik tümleşik analizi uygulamalara eklemek için API’ler sunar. Tümleşik analiz yazılımlarını, tümleşik analiz araçlarını veya tümleşik iş zekası araçlarını kullanarak hem PaaS ortamında hem de SaaS ortamında Power BI ile ekleme hakkında daha fazla bilgi edinin.
author: rkarlin
ms.author: rkarlin
manager: kfile
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
ms.openlocfilehash: a212691f2af877e3b86e021a4f48644f4fa6e8e3
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66051054"
---
# <a name="embedded-analytics-with-power-bi"></a>Power BI ile tümleşik analiz

Power BI hizmetinde (SaaS) ve Azure’daki Power BI Embedded hizmetinde (PaaS), panolarınızı ve raporlarınızı eklemeye yönelik API’ler bulunur. İçerik eklerken bu panolar, ağ geçitleri ve uygulama çalışma alanları gibi en son Power BI özelliklerine erişmenizi sağlar.

Bir örnek uygulamayı indirmek ve hızlıca başlamak için [Ekleme kurulum aracını](https://aka.ms/embedsetup) inceleyebilirsiniz.

Size uygun olan çözümü seçin:

* [Embedding for your organization](embedding.md#embedding-for-your-organization) seçeneği, Power BI hizmetinin kapsamını genişletmenize olanak tanır. Bunu yapmak için uygulama [kuruluşunuz için ekleme](https://aka.ms/embedsetup/UserOwnsData) çözüm.
* [Müşterileriniz için içerik ekleme](embedding.md#embedding-for-your-customers) panoları ve raporları Power BI hesabınız yok mu kullanıcılara olanak sağlar. Bunu yapmak için uygulama [müşterileriniz için ekleme](https://aka.ms/embedsetup/AppOwnsData) çözüm.

![PBIE örneği](media/what-can-you-do/what-can-you-do-02.png)

## <a name="use-apis"></a>API'leri kullanma

Power BI içeriği eklemek için iki ana senaryo vardır:
- (Power BI lisansı olan), kuruluşunuzun kullanıcıları için ekleme. 
 
- Power BI lisansı gerekmez müşteriler ve kullanıcılar için ekleme. 

[Power BI REST API'si](https://docs.microsoft.com/rest/api/power-bi/) iki senaryo için.

Power BI lisansı olmayan müşteriler ve kullanıcılar için panoları ve raporları özel uygulamanıza ekleyebilir, aynı API'yi kullanarak kuruluşunuza veya müşterilerinize sunabilirsiniz. Müşterileriniz, uygulama tarafından yönetilen verileri görür. Ayrıca, kuruluşunuzun Power BI kullanıcıları görüntülemek için ek seçeneklere sahip *verilerine* doğrudan Power BI veya katıştırılmış uygulama bağlamı. İçerik eklerken JavaScript ve REST API'lerinin tüm özelliklerini kullanabilirsiniz.

Gömme nasıl çalıştığını anlamak için bkz: [JavaScript ekleme örneği](https://microsoft.github.io/PowerBI-JavaScript/demo/).

## <a name="embedding-for-your-organization"></a>Kuruluşunuz için içerik ekleme

**Embedding for your organization** seçeneği, Power BI hizmetinin kapsamını genişletmenize olanak tanır. Bu ekleme, uygulamanızın kullanıcıları oturum içeriği görüntülemek için Power BI hizmetinde gerektirir. Kuruluşunuzdaki bir kullanıcı oturum açtığında yalnızca sahip olduğu veya Power BI hizmetinde birisinin kendisiyle paylaştığı panolara ve raporlara erişebilir.

Kuruluş ekleme örnekleri iç uygulamaları gibi dahil [SharePoint Online](https://powerbi.microsoft.com/blog/integrate-power-bi-reports-in-sharepoint-online/), [(yönetici hakları olmalıdır) Microsoft Teams tümleştirmesi](https://powerbi.microsoft.com/blog/power-bi-teams-up-with-microsoft-teams/), ve [Microsoft Dynamics](https://docs.microsoft.com/dynamics365/customer-engagement/basics/add-edit-power-bi-visualizations-dashboard).

Kuruluşunuz için ekleme için bkz: [Öğreticisi: Power BI içeriğini bir uygulamaya kuruluşunuz için ekleme](embed-sample-for-your-organization.md).

Düzenleme ve kaydetme gibi self servis özellikleri Power BI kullanıcıları için ekleme yaparken [JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)’si aracılığıyla kullanılabilir.

Git [katıştırma Kurulum aracı](https://aka.ms/embedsetup/UserOwnsData) başlamak ve kuruluşunuz için bir rapor tümleştirme aracılığıyla size bir örnek uygulamayı indirin.

## <a name="embedding-for-your-customers"></a>Müşterileriniz için içerik ekleme

**Müşterileriniz için içerik ekleme** , panoları ve raporları Power BI hesabınız yoksa kullanıcılar için ekleme olanak tanır. Bu ekleme olarak da bilinen olan *Power BI Embedded*.

[Power BI Embedded](azure-pbie-what-is-power-bi-embedded.md) olduğu bir **Microsoft Azure** bağımsız yazılım satıcılarına (ISV) ve geliştiricilerin hızla olanak sağlayan bir uygulamaya görseller, raporlar ve panolar ekleyin. Bu ekleme bir kapasite tabanlı, saatlik tarifeli modeli gerçekleştirilir.

![Müşterileriniz için içerik ekleme akışı](media/embedding/powerbi-embed-flow.png)

Power BI Embedded'in ISV'lere, onların geliştiricilerine ve müşterilerine yönelik avantajları vardır. Örneğin, bir ISV Power BI Desktop ile ücretsiz olarak görseller oluşturmaya başlayabilir. Görsel analitik geliştirme çabalarını en aza tarafından ISV'ler pazara daha hızlı ve farklı veri deneyimleri sayesinde rakiplerinizin uygulamalarından göze çarpın. ISV'ler ayrıca eklenmiş analitiklerle oluşturdukları ek değer için bir premium ücretlendirme seçebilirsiniz.

Power BI Embedded ile müşterilerinizin Power BI ile ilgili bilgi sahibi olmalarına gerek yoktur. Katıştırılmış bir uygulama oluşturmak için iki farklı yöntemleri kullanabilirsiniz:
- Power BI Pro hesabı 
- Hizmet sorumlusu 

Power BI Pro hesabı, uygulamanızın ana hesap (proxy hesabı olarak bunu düşünme) görevi görür. Bu hesap oluşturmanızı sağlar, uygulamanızın Power BI panolarınızı ve raporlarınızı erişmeyi belirteçleri ekleme.

[Hizmet sorumlusu](embed-service-principal.md) bir **yalnızca uygulama** belirteci kullanarak Power BI içeriğini uygulamaya ekleyebilir. Ayrıca oluşturmanıza olanak sağlar, uygulamanızın Power BI panolarınızı ve raporlarınızı erişmeyi belirteçleri ekleme.

Power BI Embedded kullanan geliştiriciler, uygulamanın çekirdek işlevselliğini yerine harcama zaman geliştirme görselleri ve Analitikleri geliştirmeye harcamak. Bunlar hızlı bir şekilde müşteri rapor ve Pano taleplerini karşılamak ve tam olarak belgelenmiş API'leri ve SDK'ları ile kolayca ekleyin. ISV'ler uygulamalarında gezinmesi kolay veri keşfi özellikleri sunarak müşterilerinin her cihazdan bağlam içinde hızlı ve veri odaklı kararlar vermesini sağlar.

> [!IMPORTANT]
> Ekleme Power BI hizmetinde gerekirken, müşterileriniz uygulamanızın katıştırılmış içeriği görüntülemek için bir Power BI hesabınızın olması gerekmez. 

Üretim aşamasına geçmeye hazır olduğunuzda uygulama çalışma alanınızın ayrılmış bir kapasiteye atanması gerekir. Microsoft Azure'daki Power BI Embedded çözümü, uygulamalarınızla kullanılabilecek [ayrılmış kapasiteler](azure-pbie-create-capacity.md) sunar.

Ayrıntılar eklemek için bkz: [Power BI içeriği eklemek üzere nasıl](embed-sample-for-customers.md).

## <a name="next-steps"></a>Sonraki adımlar

Artık Power BI içeriğini uygulamaya eklemeyi veya müşterileriniz için Power BI içeriği eklemeyi deneyebilirsiniz.

> [!div class="nextstepaction"]
> [Kuruluşunuz için ekleme](embed-sample-for-your-organization.md)

> [!div class="nextstepaction"]
> [Power BI Embedded nedir?](azure-pbie-what-is-power-bi-embedded.md)

> [!div class="nextstepaction"]
>[Müşterileriniz için ekleme](embed-sample-for-customers.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)
