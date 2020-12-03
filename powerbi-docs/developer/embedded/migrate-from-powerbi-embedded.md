---
title: Power BI Çalışma Alanı Koleksiyonu içeriğini Power BI'a geçirme
description: Power BI Çalışma Alanı Koleksiyonu hizmetinden Power BI Embedded hizmetine geçiş yapmayı ve uygulamalara içerik eklemeyle ilgili avantajlardan faydalanmayı öğrenin.
author: KesemSharabi
ms.author: kesharab
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: how-to
ms.date: 06/30/2018
ms.openlocfilehash: afff3023942352a25ff89fbed5f4a855b23d724d
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96416566"
---
# <a name="how-to-migrate-power-bi-workspace-collection-content-to-power-bi-embedded"></a>Power BI Çalışma Alanı Koleksiyonu içeriğini Power BI Embedded’e geçirme

Power BI Çalışma Alanı Koleksiyonu hizmetinden Power BI Embedded hizmetine geçiş yapmayı ve uygulamalara içerik eklemeyle ilgili avantajlardan faydalanmayı öğrenin.

Microsoft kısa süre önce kullanıcılara içerikle ilgili erişme, paylaşma ve dağıtma konularında daha fazla esneklik sunan yeni bir kapasite tabanlı lisanslama modeli olan [Power BI Embedded’i duyurdu](https://powerbi.microsoft.com/blog/power-bi-embedded-capacity-based-skus-coming-to-azure/). Bu teklif ayrıca ek ölçeklenebilirlik ve performansı da beraberinde getirdi.

Power BI Embedded ile tek bir API yüzeyi, içeriğinizi eklerken kullanabileceğiniz tutarlı özellik kümesi ve panolar, ağ geçitleri ve çalışma alanları gibi en yeni Power BI özeliklerine erişim sahibi olacaksınız. Ayrıca Power BI Desktop’ı kullanmaya başlayabilecek ve Power BI Embedded ile dağıtıma geçebileceksiniz.

Geçerli Power BI Çalışma Alanı Koleksiyonu sınırlı bir süre için kullanılabilir olmaya devam edecektir. Kurumsal Anlaşma kapsamındaki müşteriler mevcut sözleşmelerinin süresi dolana kadar erişim sahibi olacak, Power BI Çalışma Alanı Koleksiyonu hizmetini Doğrudan ya da Bulut Çözümü Sağlayıcısı kanallarından satın almış müşteriler ise Power BI Embedded’in Genel Kullanılabilirlik sürümünden bir yıl süreyle erişim sağlamaya devam edebilecektir.  Bu makalede Power BI Çalışma Alanı Koleksiyonu hizmetinden yeni Power BI Embedded deneyimine geçiş ve uygulamanızda oluşabilecek değişiklikler hakkında bilgilere yer verilmiştir.

> [!IMPORTANT]
> Geçiş Power BI Embedded hizmetine bağlı olsa da **ekleme belirteci** kullandığınız zaman uygulamanızın kullanıcıları açısından Power BI bağımlılığı söz konusu değildir. Müşterilerinizin uygulamanıza eklenmiş içeriği görüntülemek için Power BI'a kaydolması gerekmez. Power BI Embedded harici kullanıcılara hizmet sunmak için bu ekleme yaklaşımını kullanabilirsiniz.

![Akış ekleme](media/migrate-from-powerbi-embedded/powerbi-embed-flow.png)

Yeni Power BI Embedded sürümüne geçiş yapmaya başlamadan önce, [Katıştırma kurulum aracı](https://aka.ms/embedsetup)’nı kullanarak yeni Power BI Embedded ortamınızı ayarlamanıza yardımcı olan bir kılavuzu hızlıca inceleyebilirsiniz.

Size uygun olan çözümü seçin:
* **Embed for your customers** - Bir *verilerin sahibi uygulamadır* çözümü ile ilgilendiğinizde. [Embedding for your customers](embedding.md#embedding-for-your-customers) seçeneği, Power BI hesabı olmayan kullanıcılar için panolar ve raporlar eklemenize olanak sağlar. 

* **Embed for your organization** - Bir *verilerin sahibi kullanıcıdır* çözümü ile ilgilendiğinizde. [Embedding for your organization](embedding.md#embedding-for-your-organization) seçeneği, Power BI hizmetinin kapsamını genişletmenize olanak tanır.

## <a name="prepare-for-the-migration"></a>Geçiş için hazırlama

Power BI Çalışma Alanı Koleksiyonu hizmetinden Power BI Embedded hizmetine geçişe hazırlanmak için yapmanız gereken birkaç işlem vardır. Bir kiracıya ve Power BI Pro lisansına sahip bir kullanıcıya ihtiyacınız vardır.

1. Azure Active Directory (Azure AD) kiracısına erişim sahibi olduğunuzdan emin olun.

    Hangi kiracı kurulumunun kullanılacağını belirlemeniz gerekir.

   * Var olan kurumsal Power BI kiracınızı mı kullanacaksınız?
   * Uygulamanız için ayrı bir kiracı mı kullanacaksınız?
   * Her müşteri için ayrı bir kiracı mı kullanacaksınız?

     Uygulamanız veya her müşteri için yeni bir kiracı oluşturmaya karar verirseniz [Azure Active Directory kiracısı oluşturma](create-an-azure-active-directory-tenant.md) veya [Azure Active Directory kiracısı edinme](/azure/active-directory/develop/active-directory-howto-tenant) konularına bakın.
2. Bu yeni kiracıda oluşturduğunuz kullanıcı, uygulamanızın "ana" hesabı olur. Bu hesabın Power BI'a kaydolması ve kendisine atanmış bir Power BI Pro lisansı olması gerekir.

## <a name="accounts-within-azure-ad"></a>Azure AD içindeki hesaplar

Aşağıdaki hesapların kiracınızda bulunması gerekir.

> [!NOTE]
> Bu hesapların çalışma alanlarını kullanabilmesi için Power BI Pro lisansına sahip olması gerekir.

1. Power BI yöneticisi.

    Bu kullanıcının eklemek üzere oluşturulan tüm çalışma alanlarına üye olması önerilir.

2. İçeriği oluşturacak analistlerin hesapları.

    Bu kullanıcıların gerektiğinde çalışma alanlarına atanması gerekir.

3. Uygulama *ana* kullanıcı hesabı veya Embedded hesabı.

    Bu hesabın kimlik bilgileri uygulama arka ucunda depolanır ve Power BI REST API'leri ile kullanılacak Azure AD belirteçlerini almak için kullanılır. Bu hesap uygulamanın ekleme belirtecini oluşturmak için kullanılır. Bu hesabın aynı zamanda ekleme için oluşturulmuş olan çalışma alanlarının da yöneticisi olması gerekir.

> [!NOTE]
> Bu, kuruluşunuzda bulunan normal bir kullanıcı hesabıdır ve ekleme amacıyla kullanılacaktır.

## <a name="app-registration-and-permissions"></a>Uygulama kaydı ve izinler

Uygulamayı Azure AD'ye kaydetmeniz ve belirli izinleri vermeniz gerekir.

### <a name="register-an-application"></a>Uygulamaları kaydetme

REST API çağrılarını gerçekleştirmek için uygulamanızı Azure AD'ye kaydetmeniz gerekir. Buna Power BI kayıt sayfasına ek olarak Azure portalına giderek ek yapılandırma adımları gerçekleştirme dahildir. Daha fazla bilgi için bkz. [Bir Azure AD uygulamasını Power BI içeriği eklemek üzere kaydetme](register-app.md).

Uygulamayı kaydetmek için uygulamanın **ana** hesabını kullanmanız gerekir.

## <a name="create-workspaces-required"></a>Çalışma alanı oluşturma (Gerekli)

Çalışma alanlarından faydalanarak birden fazla müşteriye hizmet veren uygulamalarınız için daha iyi yalıtım sağlayabilirsiniz. Her müşterinin panoları ve raporları diğerlerinden ayrılır. Ardından her çalışma alanında bir Power BI hesabı kullanarak müşterilerinizin uygulama deneyimlerini de birbirinden ayırabilirsiniz.

> [!IMPORTANT]
> Power BI kullanmayan kişiler için ekleme özelliğinden yararlanma amacıyla kişisel çalışma alanlarını kullanamazsınız.

Power BI'da bir çalışma alanı oluşturmak için Pro lisansa sahip bir kullanıcınız olması gerekir. Çalışma alanını oluşturan Power BI kullanıcısı, varsayılan olarak ilgili çalışma alanının yöneticisi olur.

> [!NOTE]
> Uygulama *ana* hesabının çalışma alanının yöneticisi olması gerekir.

## <a name="content-migration"></a>İçerik geçişi

Çalışma alanı koleksiyonlarınızdaki içeriği Power BI Embedded hizmetine mevcut çözümünüzle paralel bir şekilde ve kesinti yaşamadan geçirebilirsiniz.

Power BI Çalışma Alanı Koleksiyonu içeriğinizi Power BI Embedded hizmetine kopyalama konusunda yardımcı olmak için bir **geçiş aracı** tasarlanmıştır. Bu araç özellikle çok fazla içeriğe sahip olan kullanıcılar için yararlıdır. Daha fazla bilgi için bkz. [Power BI Embedded geçiş aracı](migrate-tool.md).

İçerik geçişi temelde iki API kullanır.

1. Download PBIX: Bu API, Ekim 2016'dan sonra Power BI'a yüklenmiş olan PBIX dosyalarını indirebilir.
2. Import PBIX: Bu API, PBIX dosyalarını Power BI'a yükler.

İlgili kod parçacıkları için bkz. [Power BI Çalışma Alanı Koleksiyonu hizmetinden içerik geçişi için kod parçacıkları](migrate-code-snippets.md).

### <a name="report-types"></a>Rapor türleri

Birden fazla rapor türü vardır ve her birinin geçiş akışı diğerlerinden farklıdır.

#### <a name="cached-dataset--report"></a>Önbelleğe alınmış veri kümesi ve rapor

Önbelleğe alınmış veri kümeleri, canlı bağlantı veya DirectQuery bağlantısının aksine içeri aktarılmış verilere sahip PBIX dosyalarıdır.

**Akış**

1. PaaS çalışma alanından Download PBIX API çağrısı yapın.
2. PBIX dosyasını kaydedin.
3. SaaS çalışma alanına Import PBIX çağrısı yapın.

#### <a name="directquery-dataset--report"></a>DirectQuery veri kümesi ve rapor

**Akış**

1. GET `https://api.powerbi.com/v1.0/collections/{collection_id}/workspaces/{wid}/datasets/{dataset_id}/Default.GetBoundGatewayDataSources` çağrısı yapın ve alınan bağlantı dizesini kaydedin.
2. PaaS çalışma alanından Download PBIX API çağrısı yapın.
3. PBIX dosyasını kaydedin.
4. SaaS çalışma alanına Import PBIX çağrısı yapın.
5. \- POST `https://api.powerbi.com/v1.0/myorg/datasets/{dataset_id}/Default.SetAllConnections` çağrısı yaparak bağlantı dizesini güncelleştirin
6. \- GET `https://api.powerbi.com/v1.0/myorg/datasets/{dataset_id}/Default.GetBoundGatewayDataSources` çağrısı yaparak GW ve veri kaynağı tanımlayıcılarını alın
7. \- PATCH `https://api.powerbi.com/v1.0/myorg/gateways/{gateway_id}/datasources/{datasource_id}` çağrısı yaparak kullanıcının kimlik bilgilerini güncelleştirin

#### <a name="old-dataset--reports"></a>Eski veri kümeleri ve raporlar

Bunlar Ekim 2016 öncesinde oluşturulmuş veri kümeleri/raporlardır. Download PBIX, Ekim 2016'dan önce yüklenmiş olan PBIX dosyalarını desteklemez

**Akış**

1. Geliştirme ortamınızdan (iç kaynak denetiminizden) PBIX dosyasını alın.
2. SaaS çalışma alanına Import PBIX çağrısı yapın.

#### <a name="push-dataset--report"></a>Gönderim veri kümesi ve rapor

Download PBIX, *Push API* veri kümelerini desteklemez. Push API veri kümesi PaaS ile SaaS arasında taşınamaz.

**Akış**

1. Json veri kümesi ile "Create dataset" API çağrısı yaparak veri kümesini SaaS çalışma alanında oluşturun.
2. Oluşturulan veri kümesinin raporunu yeniden oluşturun*.

Aşağıdaki geçici çözümleri kullanarak Push API raporunu PaaS’tan SaaS’a geçirebilirsiniz.

1. PaaS çalışma alanına işlevsiz PBIX dosyaları yükleyin.
2. Push API raporunu kopyalayın ve 1. adımda oluşturduğunuz işlevsiz PBIX dosyasına bağlayın.
3. Push API raporunu işlevsiz PBIX ile birlikte indirin.
4. İşlevsiz PBIX dosyasını SaaS çalışma alanınıza yükleyin.
5. Gönderim veri kümesini SaaS çalışma alanınızda oluşturun.
6. Raporu Push API veri kümesine tekrar bağlayın.

## <a name="create-and-upload-new-reports"></a>Yeni rapor oluşturma ve yükleme

Power BI Çalışma Alanı Koleksiyonu hizmetinden geçirdiğiniz içeriğe ek olarak Power BI Desktop uygulamasını kullanarak rapor ve veri kümesi oluşturabilir, ardından bu raporları bir çalışma alanında yayımlayabilirsiniz. Raporları yayımlayan son kullanıcının çalışma alanında yayımlama yapabilmesi için bir Power BI Pro lisansına sahip olması gerekir.

## <a name="rebuild-your-application"></a>Uygulamanızı yeniden oluşturma

1. Uygulamanızı Power BI REST API'lerini ve powerbi.com içindeki rapor konumunu kullanacak şekilde değiştirmeniz gerekir.
2. Uygulamanızın *ana* hesabını kullanarak AuthN/AuthZ kimlik doğrulamanızı yeniden oluşturun. Bu kullanıcının diğer kullanıcıların adına hareket etmesine izin vermek için [ekleme belirteci](/rest/api/power-bi/embedtoken) kullanabilirsiniz.
3. powerbi.com'daki raporlarınızı uygulamanıza ekleyin.

## <a name="map-your-users-to-a-power-bi-user"></a>Kullanıcılarınızı bir Power BI kullanıcısıyla eşleme

Uygulamanızın içinde yönettiğiniz kullanıcıları, uygulamanızın amaçları doğrultusunda bir *ana* Power BI kimlik bilgisiyle eşlemeniz gerekir. Bu Power BI *ana* hesabının kimlik bilgileri uygulamanızda depolanır ve ekleme belirteçleri oluşturmak için kullanılır.

## <a name="what-to-do-when-you-are-ready-for-production"></a>Üretim aşaması için hazır olduğunuzda yapmanız gerekenler

Üretim aşamasına geçmeye hazır olduğunuzda aşağıdaki işlemleri yapmanız gerekir.

* Geliştirme için ayrı bir kiracı kullanıyorsanız çalışma alanlarınızın, panolarınızın ve raporlarınızın üretim ortamınızda kullanılabilir durumda olduğundan emin olmanız gerekir. Ayrıca uygulamayı üretim kiracınızın Azure AD ortamında oluşturduğunuzdan ve 1. Adım ile belirtilen gerekli uygulama izinlerini atadığınızdan da emin olmanız gerekir.
* İhtiyaçlarınıza uygun bir kapasite satın alın. Gereken kapasite miktarını ve türünü daha iyi anlamak için bkz. [Power BI Embedded analiz kapasite planlama teknik incelemesi](./embedded-capacity-planning.md). Azure’da [kapasite satın alabilirsiniz](https://portal.azure.com/#create/Microsoft.PowerBIDedicated).
* Çalışma alanını düzenleyin ve gelişmiş ayarlar bölümünden bir Premium kapasite atayın.

    ![Premium kapasite](media/migrate-from-powerbi-embedded/powerbi-embedded-premium-capacity02.png)

* Güncelleştirilen uygulamanızı üretim ortamında dağıtın ve Power BI Embedded hizmetindeki raporları eklemeye başlayın.

## <a name="after-migration"></a>Geçiş sonrasında

Azure'da biraz temizlik yapmanız gerekir.

* Dağıtılan çözümün tüm çalışma alanlarını Power BI Çalışma Alanı Koleksiyonunun Azure Embedded hizmetinden kaldırın.
* Azure'daki mevcut Çalışma Alanı Koleksiyonlarını silin.

## <a name="next-steps"></a>Sonraki adımlar

[Power BI ile ekleme](embedding.md)  
[Power BI Çalışma Alanı Koleksiyonu geçiş aracı](migrate-tool.md)  
[Power BI Çalışma Alanı Koleksiyonu hizmetinden içerik geçişi için kod parçacıkları](migrate-code-snippets.md)  
[Power BI panolarınızı, raporlarınızı ve kutucuklarınızı ekleme](embed-sample-for-your-organization.md)  
[Power BI Premium nedir?](../../admin/service-premium-what-is.md)  
[JavaScript API'si Git deposu](https://github.com/Microsoft/PowerBI-JavaScript)  
[Power BI C# Git deposu](https://github.com/Microsoft/PowerBI-CSharp)  
[JavaScript ekleme örneği](https://microsoft.github.io/PowerBI-JavaScript/demo/)  
[Çalışma Alanı Koleksiyonu analiz kapasite planlama teknik incelemesi](./embedded-capacity-planning.md)  
[Power BI Premium teknik incelemesi](https://aka.ms/pbipremiumwhitepaper)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)