---
title: Power BI ile ekleme
description: Power BI, panolarınızı ve raporlarınızı uygulamalara eklemek için kullanabileceğiniz API'ler sunar.
author: markingmyname
ms.author: maghan
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: overview
ms.date: 07/31/2018
ms.openlocfilehash: 7b96e671a6fe9b450fff683ced3caa611ae70bd7
ms.sourcegitcommit: 698b788720282b67d3e22ae5de572b54056f1b6c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45973782"
---
# <a name="embedding-with-power-bi"></a>Power BI ile ekleme

Power BI hizmetinde (SaaS) ve Azure’daki Power BI Embedded hizmetinde (PaaS), panolarınızı ve raporlarınızı eklemeye yönelik API’ler bulunur. Bu özellik, içeriğinizi eklerken kullanabileceğiniz bir özellik kümesi ve panolar, ağ geçitleri ve uygulama çalışma alanları gibi en yeni Power BI özeliklerine erişim sahibi olacağınız anlamına gelir.

Bir örnek uygulamayı indirmek ve hızlıca başlamak için [Katıştırma kurulum aracını](https://aka.ms/embedsetup) inceleyebilirsiniz.

Size uygun olan çözümü seçin:

* [Embedding for your organization](embedding.md#embedding-for-your-organization) seçeneği, Power BI hizmetinin kapsamını genişletmenize olanak tanır. [Embed for your organization](https://aka.ms/embedsetup/UserOwnsData) çözümünü çalıştırın.
* [Embedding for your customers](embedding.md#embedding-for-your-customers) seçeneği, Power BI hesabı olmayan kullanıcılar için panolar ve raporlar eklemenize olanak sağlar. [Embed for your customers](https://aka.ms/embedsetup/AppOwnsData) çözümünü çalıştırın.

![PBIE örneği](media/what-can-you-do/what-can-you-do-02.png)

## <a name="using-apis"></a>API'leri kullanma

Power BI içeriğini eklerken kullanılabilecek iki ana senaryo vardır.  İlk senaryo, kuruluşunuzdaki kullanıcılara (Power BI lisansı olan) yönelik ekleme işlemleri için geçerlidir. İkinci senaryoda ise ekleme işlemini, kullanıcı ve müşterilerinizin Power BI lisanslarının olmasına gerek kalmadan gerçekleştirirsiniz. Power BI REST API'si iki senaryo için de kullanılabilir.

Power BI lisansı olmayan müşteriler ve kullanıcılar için panoları ve raporları özel uygulamanıza ekleyebilir, aynı API'yi kullanarak kuruluşunuza veya müşterilerinize sunabilirsiniz. Müşterileriniz, uygulama tarafından yönetilen verileri görür. Ayrıca, kuruluşunuzdaki Power BI kullanıcıları da *verilerini* doğrudan Power BI'da veya eklenen uygulamanın bağlamında görüntülemeye ilişkin ek seçeneklere sahip olur. İçerik eklerken JavaScript ve REST API'lerinin tüm özelliklerini kullanabilirsiniz.

İçerik eklemenin nasıl gerçekleştirildiğini gösteren bir örnek için bkz. [JavaScript ekleme örneği](https://microsoft.github.io/PowerBI-JavaScript/demo/).

## <a name="embedding-for-your-organization"></a>Kuruluşunuz için içerik ekleme

**Embedding for your organization** seçeneği, Power BI hizmetinin kapsamını genişletmenize olanak tanır. Kuruluşunuza ekleme işlemi için uygulamanızın kullanıcılarının, içeriklerini görüntülemek istediklerinde Power BI hizmetinde oturum açmaları gerekir. Kuruluşunuzdaki bir kullanıcı oturum açtığında yalnızca, sahip olduğu veya Power BI hizmetinde kendisiyle paylaşılmış olan panolara ve raporlara erişebilir.

*Kuruluşunuz için içerik ekleme örnekleri arasında [SharePoint Online](https://powerbi.microsoft.com/blog/integrate-power-bi-reports-in-sharepoint-online/), [Microsoft Teams tümleştirmesi (Yönetici haklarına sahip olmanız gerekir)](https://powerbi.microsoft.com/blog/power-bi-teams-up-with-microsoft-teams/) ve [Microsoft Dynamics](https://docs.microsoft.com/dynamics365/customer-engagement/basics/add-edit-power-bi-visualizations-dashboard) gibi şirket içi uygulamalar bulunur.*

Kuruluşunuz için içerik ekleme konusunda bilgiye aşağıdaki sayfalardan ulaşabilirsiniz:

* [Raporları uygulamalarla tümleştirme](embed-sample-for-your-organization.md)

Düzenleme ve kaydetme gibi self servis özellikleri Power BI kullanıcıları için ekleme yaparken [JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)'si aracılığıyla kullanılabilir.

Hızlı kullanmaya başlamak ve kuruluşunuz için bir raporu tümleştirme adımlarını gösteren örnek bir uygulama indirmek için kuruluşunuzda eklemeye yönelik [katıştırma kurulum aracını](https://aka.ms/embedsetup/UserOwnsData) inceleyebilirsiniz.

## <a name="embedding-for-your-customers"></a>Müşterileriniz için içerik ekleme

**Müşterileriniz için ekleme** seçeneği, Power BI hesabı olmayan kullanıcılar için panolar ve raporlar eklemenize olanak sağlar. Müşterileriniz için ekleme seçeneği **Power BI Embedded** olarak da bilinir.

[Power BI Embedded](azure-pbie-what-is-power-bi-embedded.md) bir **Microsoft Azure** hizmetidir. Bağımsız yazılım satıcılarının (ISV) ve geliştiricilerin kapasite tabanlı, saatlik tarifeli bir model aracılığıyla uygulamaya görseller, raporlar ve panolar eklemesini sağlar.

![Müşterileriniz için içerik ekleme akışı](media/embedding/powerbi-embed-flow.png)

Power BI Embedded'in ISV'lere, onların geliştiricilerine ve müşterilerine yönelik avantajları vardır. Örneğin, bir ISV Power BI Desktop ile ücretsiz olarak görseller oluşturmaya başlayabilir. ISV'ler görsel analiz geliştirme çabalarını en aza indirerek pazara sunma sürecini hızlandırabilir ve fark yaratan veri deneyimleriyle rakipleri arasında öne çıkabilir. Ayrıca ISV'ler eklenen analitik sayesinde oluşturulan ek değer için bir ücret almayı tercih edebilir.

Power BI Embedded ile müşterilerinizin Power BI ile ilgili bilgi sahibi olmalarına gerek yoktur. Ekli uygulama oluşturmak için tek bir Power BI Pro hesabınız olması yeterlidir. Power BI Pro hesabı, uygulamanız için ana hesap olarak kullanılır (bunu ara sunucu hesabı olarak düşünün). Power BI Pro hesabı ile Power BI hizmetindeki, uygulamanıza ait veya uygulamanız tarafından yönetilen pano ve raporlara erişim sağlayan ekleme belirteçleri de oluşturabilirsiniz.

Geliştiriciler Power BI Embedded kullanarak görselleri ve analitiği geliştirmeye zaman harcamak yerine uygulamalarının temel yetkinliğini oluşturmaya zaman ayırabilir. Geliştiriciler müşterilerin rapor ve pano taleplerini hızla karşılayabilir ve tümüyle belgelenmiş API'leri ve SDK'ları kolayca ekleyebilir. ISV'ler uygulamalarında gezinmesi kolay veri keşfi özellikleri sunarak müşterilerinin her cihazdan bağlam içinde hızlı ve veri odaklı kararlar vermesini sağlar.

> [!IMPORTANT]
> Ekleme işlemi Power BI hizmetine bağlı olsa da müşterileriniz için Power BI hizmeti bağımlılığı söz konusu değildir. Kullanıcıların uygulamanıza eklenmiş içeriği görüntülemek için Power BI'a kaydolması gerekmez.

Üretim aşamasına geçmeye hazır olduğunuzda uygulama çalışma alanınızın ayrılmış bir kapasiteye atanması gerekir. Microsoft Azure'daki Power BI Embedded çözümü, uygulamalarınızla kullanılabilecek [ayrılmış kapasiteler](azure-pbie-create-capacity.md) sunar.

Ekleme hakkında ayrıntılı bilgi için bkz. [Power BI panolarınızı, raporlarınızı ve kutucuklarınızı ekleme](embed-sample-for-customers.md).

## <a name="next-steps"></a>Sonraki adımlar

Artık Power BI içeriğini uygulamaya eklemeyi veya müşterileriniz için Power BI içeriği eklemeyi deneyebilirsiniz.

> [!div class="nextstepaction"]
> [Kuruluşunuz için ekleme](embed-sample-for-your-organization.md)

> [!div class="nextstepaction"]
> [Power BI Embedded nedir?](azure-pbie-what-is-power-bi-embedded.md)

> [!div class="nextstepaction"]
>[Müşterileriniz için ekleme](embed-sample-for-customers.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)