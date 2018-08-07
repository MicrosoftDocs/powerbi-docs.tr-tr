---
title: Power BI ile ekleme
description: Power BI, panolarınızı ve raporlarınızı uygulamalara eklemek için kullanabileceğiniz API'ler sunar.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: overview
ms.date: 07/31/2018
ms.author: maghan
ms.openlocfilehash: 8f200450e5359124ffcc3447c68c6bd755c57896
ms.sourcegitcommit: fecea174721d0eb4e1927c1116d2604a822e4090
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/31/2018
ms.locfileid: "39359875"
---
# <a name="embedding-with-power-bi"></a>Power BI ile ekleme
Power BI hizmetinde (SaaS) ve Azure’daki Power BI Embedded hizmetinde (PaaS), panolarınızı ve raporlarınızı eklemeye yönelik API’ler bulunur. Başka bir deyişle içeriğinizi eklerken kullanabileceğiniz bir özellik kümesi ve panolar, ağ geçitleri ve uygulama çalışma alanları gibi en yeni Power BI özeliklerine erişim sahibi olursunuz.

Hızlıca çalışmaya başlamak ve bir örnek uygulama indirmek için [Ekleme deneyimi aracını](https://aka.ms/embedsetup) inceleyebilirsiniz.

Size uygun olan çözümü seçin:

* [Embedding for your organization](embedding.md#embedding-for-your-organization) seçeneği, Power BI hizmetinin kapsamını genişletmenize olanak tanır. [Embed for your organization](https://aka.ms/embedsetup/UserOwnsData) çözümünü çalıştırın.
* [Embedding for your customers](embedding.md#embedding-for-your-customers) seçeneği, Power BI hesabı olmayan kullanıcılar için panolar ve raporlar eklemenize olanak sağlar. [Embed for your customers](https://aka.ms/embedsetup/AppOwnsData) çözümünü çalıştırın.

![PBIE örneği](media/what-can-you-do/what-can-you-do-02.png)

## <a name="using-apis"></a>API'leri kullanma
Power BI içeriğini eklerken kullanılabilecek iki ana senaryo vardır.  İlk senaryo, kuruluşunuzdaki kullanıcılara (Power BI lisansı olan) yönelik ekleme işlemleri için geçerlidir. İkinci senaryoda ise ekleme işlemini, kullanıcı ve müşterilerinizin Power BI lisanslarının olmasına gerek kalmadan gerçekleştirirsiniz. Power BI REST API'si iki senaryo için de kullanılabilir.

Power BI lisansı olmayan müşteriler ve kullanıcılar için panoları ve raporları özel uygulamanıza ekleyebilir, aynı API'yi kullanarak kuruluşunuza veya müşterilerinize sunabilirsiniz. Müşterileriniz, uygulama tarafından yönetilen verileri görür. Ayrıca, kuruluşunuzdaki Power BI kullanıcıları da *verilerini* doğrudan Power BI'da veya eklenen uygulamanın bağlamında görüntülemeye ilişkin ek seçeneklere sahip olur. İçerik eklerken JavaScript ve REST API'lerinin tüm özelliklerini kullanabilirsiniz.

İçerik eklemenin nasıl gerçekleştirildiğini gösteren bir örnek için bkz. [JavaScript ekleme örneği](https://microsoft.github.io/PowerBI-JavaScript/demo/).

## <a name="embedding-for-your-organization"></a>Kuruluşunuz için içerik ekleme
**Embedding for your organization** seçeneği, Power BI hizmetinin kapsamını genişletmenize olanak tanır. Bunun için uygulamanızın kullanıcılarının, içeriklerini görüntülemek istediklerinde Power BI hizmetinde oturum açmaları gerekir. Kuruluşunuzdaki bir kullanıcı oturum açtığında yalnızca, sahip olduğu veya Power BI hizmetinde kendisiyle paylaşılmış olan panolara ve raporlara erişebilir.

*Kuruluşunuz için içerik ekleme örnekleri arasında şirket içi web uygulaması, SharePoint Online web bölümü ve [Microsoft Teams tümleştirmesi bulunur (Yönetici haklarına sahip olmanız gerekir)](https://powerbi.microsoft.com/en-us/blog/power-bi-teams-up-with-microsoft-teams/).*

Kuruluşunuz için içerik ekleme konusunda bilgiye aşağıdaki sayfalardan ulaşabilirsiniz:

* [Raporları uygulamalarla tümleştirme](embed-sample-for-your-organization.md)

Düzenleme ve kaydetme gibi self servis özellikleri Power BI kullanıcıları için ekleme yaparken [JavaScript API](https://github.com/Microsoft/PowerBI-JavaScript)'si aracılığıyla kullanılabilir.

Hızla kullanmaya başlamak ve kuruluşunuz için bir raporu tümleştirme adımlarını gösteren örnek bir uygulama indirmek için kuruluşunuzda eklemeye yönelik [ekleme deneyimi aracını](https://aka.ms/embedsetup/UserOwnsData) inceleyebilirsiniz.

## <a name="embedding-for-your-customers"></a>Müşterileriniz için içerik ekleme

**Embedding for your customers** seçeneği, Power BI hesabı olmayan kullanıcılar için panolar ve raporlar eklemenize olanak sağlar. Müşterilerinizin Power BI'dan haberdar olmalarına gerek yoktur. Katıştırılmış bir uygulama oluşturmak için en az bir Power BI Pro hesabı gereklidir. Power BI Pro hesabı, uygulamanız için ana hesap olarak kullanılır. Bunu bir yetkili hesap olarak düşünün. Power BI Pro hesabı ile Power BI hizmetindeki, uygulamanıza ait veya uygulamanız tarafından yönetilen pano ve raporlara erişim sağlayan ekleme belirteçleri de oluşturabilirsiniz.

[Power BI Embedded](azure-pbie-what-is-power-bi-embedded.md), bağımsız yazılım satıcılarına (ISV) ve geliştiricilere müşteriler için kapasite tabanlı, saat üzerinden tarifeli bir model aracılığıyla büyüleyici görseller, raporlar ve panolar ekleyebilme olanağı sunuyor.

![Müşterileriniz için içerik ekleme akışı](media/embedding/powerbi-embed-flow.png)

Power BI Embedded'in ISV'lere, onların geliştiricilerine ve müşterilerine yönelik avantajları vardır. Örneğin, bir ISV Power BI Desktop ile ücretsiz olarak görseller oluşturmaya başlayabilir. ISV'ler görsel analiz geliştirme çabalarını en aza indirerek pazara sunma sürecini hızlandırabilir ve fark yaratan veri deneyimleriyle rakipleri arasında öne çıkabilir. Ayrıca ISV'ler eklenen analitik sayesinde oluşturulan ek değer için bir ücret almayı tercih edebilir.

Geliştiriciler görselleri ve analitiği geliştirmeye zaman harcamak yerine uygulamalarının temel yetkinliğini oluşturmaya zaman ayırabilir. Geliştiriciler müşterilerin rapor ve pano taleplerini hızla karşılayabilir ve tümüyle belgelenmiş API'leri ve SDK'ları kolayca ekleyebilir. Son olarak, ISV'ler uygulamalarında gezinmesi kolay veri keşfi özellikleri sunarak müşterilerinin her cihazdan güvenle bağlam içinde hızlı ve veri odaklı kararlar vermesini sağlar.

> [!IMPORTANT]
> Ekleme işlemi Power BI hizmetine bağlı olsa da müşterileriniz için Power BI hizmeti bağımlılığı söz konusu değildir. Kullanıcıların uygulamanıza eklenmiş içeriği görüntülemek için Power BI'a kaydolması gerekmez.

Üretim aşamasına geçmeye hazır olduğunuzda uygulama çalışma alanınızın ayrılmış bir kapasiteye atanması gerekir. Microsoft Azure içindeki Power BI Embedded çözümü, uygulamalarınızla kullanılabilecek ayrılmış kapasiteler sunar.

Ekleme hakkında ayrıntılı bilgi için bkz. [Power BI panolarınızı, raporlarınızı ve kutucuklarınızı ekleme](embed-sample-for-customers.md).

Hızla kullanmaya başlamak ve bir raporu uygulamanızla tümleştirme adımlarını gösteren örnek bir uygulama indirmek için [Ekleme deneyimi aracını](https://aka.ms/embedsetup/AppOwnsData) inceleyebilirsiniz.

Azure'daki Power BI Çalışma Alanı Koleksiyonları'nı kullanıyorsanız içeriğinizi taşıma hakkında bilgi almak için bkz. [Power BI Çalışma Alanı Koleksiyonları Azure hizmetindeki içeriği taşıma](migrate-from-powerbi-embedded.md).

## <a name="next-steps"></a>Sonraki adımlar
Artık Power BI içeriğini uygulamaya eklemeyi veya müşterileriniz için Power BI içeriği eklemeyi deneyebilirsiniz.

> [!div class="nextstepaction"]
> [Power BI Embedded nedir?](azure-pbie-what-is-power-bi-embedded.md)

> [!div class="nextstepaction"]
> [Kuruluşunuz için ekleme](embed-sample-for-your-organization.md)

> [!div class="nextstepaction"]
>[Müşterileriniz için ekleme](embed-sample-for-customers.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)