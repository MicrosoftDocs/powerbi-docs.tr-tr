---
title: Power BI uygulaması katıştırmak için gereken izin belirteçlerini anlayın
description: Power BI uygulamanızın Azure ve Power BI hizmeti kimlik doğrulaması yapması gereken belirteçleri öğrenin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: amshuste
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 02/17/2021
ms.openlocfilehash: 6a7847b0e89086094220a51a4893ffffd59d5642
ms.sourcegitcommit: fb408dfd39943dbec990a16bcf204671beb4f0aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/18/2021
ms.locfileid: "100656620"
---
# <a name="embedded-analytics-application-tokens"></a>Katıştırılmış analiz uygulama belirteçleri

Power BI içeriği kullanmak için bir erişim belirtecine ihtiyacınız vardır. Çözümünüze bağlı olarak, bu belirteç bir [Azure AD belirteci](#azure-ad-token) ya da bir [ekleme belirteci](#embed-token)olabilir.

*Müşterileriniz için ekleme* çözümünüz kullanıyorsanız, Web uygulaması kullanıcılarınız, uygulamanız tarafından oluşturulan *ekleme belirtecine* göre Power BI içeriğe (raporlar, panolar ve kutucuklar gibi) erişim izni verilir.

>[!NOTE]
>*Müşteriler için embed* çözümünü kullanırken, Web uygulamanıza erişime izin vermek için herhangi bir kimlik doğrulama yöntemi kullanabilirsiniz.

*Kuruluş çözümünüz için ekleme* işlemini kullanıyorsanız, Web uygulaması kullanıcılarınızın kendi kimlik bilgilerini kullanarak Azure AD 'de kimlik doğrulaması yapılır. Uygulama kullanıcılarınızın Power BI hizmeti erişebileceği Power BI içeriğine erişimi olur.

## <a name="azure-ad-token"></a>Azure AD belirteci

*Müşterileriniz için hem ekleme* hem de *kuruluş çözümlerinizi katıştırma* için bir [Azure AD belirtecine](#azure-ad-token)ihtiyacınız vardır. Bu belirteç tüm [REST API](/rest/api/power-bi/) işlemleri için gereklidir ve bir saatten sonra süresi dolar.

* *Müşterilerinize ekleme*' de, *ekleme belirtecini* oluşturmak için Azure AD belirteci kullanılır.

* *Kuruluşunuzun ekleme* bölümünde, Power BI erişmek IÇIN Azure AD belirteci kullanılır.

## <a name="embed-token"></a>Ekleme belirteci

*Müşteriler için ekleme* çözümünüz kullanıyorsanız, Web uygulamanızın kullanıcının erişebileceği Power BI içeriğini bilmesi gerekir. Aşağıdakileri belirten bir *ekleme belirteci* oluşturmak için [ekleme belirteci](/rest/api/power-bi/embedtoken) REST API 'lerini kullanın:

* Web uygulaması kullanıcılarınızın erişebileceği içerik.

* Web uygulaması kullanıcısının erişim düzeyi (görünüm, oluşturma veya düzenleme).

Daha fazla bilgi için bkz. [ekleme belirteci oluşturma konuları](generate-embed-token.md).

## <a name="authentication-flows"></a>Kimlik doğrulama akışları

Bu bölümde, *müşterileriniz için* eklemeye yönelik kimlik doğrulama akışları açıklanmakta ve kuruluşunuzun ekleme çözümlerini *eklemek için ekleme* yapılır.

### <a name="embed-for-your-customers"></a>Müşterileriniz için ekleme

*Müşterileriniz Için ekleme* çözümünüz etkileşimli olmayan bir kimlik doğrulama akışı kullanır. Kullanıcıların Power BI erişmek için Azure AD 'de oturum açması gerekmez. Bunun yerine, Web uygulamanız Azure AD kimlik doğrulaması için adanmış bir Azure AD kimliği kullanır ve *ekleme belirtecini* oluşturur. Adanmış kimlik aşağıdakilerden biri olabilir:

* **[Hizmet sorumlusu](embed-service-principal.md)**

    Web uygulamanız Azure AD 'ye göre kimlik doğrulaması yapmak ve *yalnızca uygulama Azure AD belirtecini* almak IÇIN Azure AD [hizmet sorumlusu nesnesini](/azure/active-directory/develop/app-objects-and-service-principals#service-principal-object) kullanır. Bu, Azure AD tarafından önerilen *yalnızca uygulama* kimlik doğrulama yöntemidir.

    *Hizmet sorumlusu* kullanırken, Power BI hizmeti *yönetici* ayarlarında [Power BI API 'leri erişimi etkinleştirmeniz](embed-sample-for-customers.md#step-6---service-principal-api-access) gerekir. Bu, Web uygulamanızın Power BI REST API 'Lerine erişmesini sağlar. Bir çalışma alanında API işlemlerini kullanmak için, *hizmet sorumlusunun* çalışma alanının *üyesi* veya *Yöneticisi* olması gerekir.

* **Ana kullanıcı**

    Web uygulamanız Azure AD kimlik doğrulaması için bir kullanıcı hesabı kullanır ve *Azure AD belirtecini* alır. *Ana kullanıcının* bir [Power BI Pro](/power-bi/admin/service-admin-purchasing-power-bi-pro) veya [Kullanıcı başına Premium (PPU)](/power-bi/admin/service-premium-per-user-faq) lisansı olması gerekir.

    *Ana Kullanıcı* kullanırken, uygulamanızın [temsilci izinleri](/azure/active-directory/develop/v2-permissions-and-consent) (kapsamlar olarak da bilinir) tanımlamanız gerekir. *Ana Kullanıcı* veya *kiracı YÖNETICISI* , Power BI REST API 'lerini kullanarak bu izinlerin kullanılmasına izin vermek için gereklidir.

Azure AD 'de başarılı kimlik doğrulamasından sonra, Web uygulamanız, kullanıcılarının belirli Power BI içeriğine erişmesine izin vermek için bir [ekleme belirteci](/rest/api/power-bi/embedtoken) oluşturacaktır.

>[!NOTE]
>* *Müşteriler çözümünüz için ekleme* kullanarak eklemek Istiyorsanız, bir a, Em veya P SKU 'su ile bir kapasiteye sahip olmanız gerekir.
>* [Üretime gitmek](move-to-production.md) için bir kapasiteye ihtiyacınız vardır.

Aşağıdaki diyagramda, *müşteriler çözümünüz için ekleme* için kimlik doğrulama akışı gösterilmektedir.

>[!div class="mx-imgBorder"]
>:::image type="content" source="media\embed-tokens\paas-authentiction.png" alt-text="Müşterilerinizin Power B Embedded Analytics çözümü için bir embed 'te kimlik doğrulama akışının diyagramı.":::

1. Web uygulaması kullanıcısı Web uygulamanıza göre kimlik doğrulaması yapar (kimlik doğrulama yönteminiz ile).

2. Web uygulamanız Azure AD kimlik doğrulaması için bir *hizmet sorumlusu* veya bir *ana Kullanıcı* kullanır.

3. Web uygulamanız Azure AD 'den bir *Azure AD belirteci* alır ve Power BI REST API 'lerine erişmek için onu kullanır. Power BI REST API 'Lerine erişim, *hizmet sorumlusu* veya *ana Kullanıcı* olan kimlik doğrulama yöntemine göre verilir.

4. Web uygulamanız, *ekleme belirteci isteyen* bir [ekleme belirteci](/rest/api/power-bi/embedtoken) REST API işlemini çağırır. *Ekleme belirteci* , hangi Power BI içeriğin katıştırılabileceği belirtir.

5. REST API, Web uygulamanıza *ekleme belirtecini* döndürür.

6. Web uygulaması ekleme belirtecini kullanıcının Web tarayıcısına geçirir.

7. Web uygulaması kullanıcısı Power BI erişmek için ekleme belirtecini kullanır.

### <a name="embed-for-your-organization"></a>Kuruluşunuz için ekleme

*Kuruluş çözümünüz Için ekleme* , etkileşimli bir kimlik doğrulama akışı kullanır. Kullanıcılarınız Power BI kimlik bilgilerini kullanarak Azure AD 'nin kimliğini doğrular. Kullanıcıların, uygulamayı Azure AD 'ye kaydederken ayarlanmış API izinlerine izin vermesi gerekir. İzin, Microsoft *izinleri istendi* iletişim kutusu açılır penceresinde verilir. İzin verildikten sonra, Web uygulaması kullanıcısının erişimi olan raporlar ve panolar gibi Power BI içerikler eklenebilir.

>[!div class="mx-imgBorder"]
>:::image type="content" source="media/embed-tokens/requested-premissions.png" alt-text="Müşterilerin Power B 'ye erişim izinleri vermesini isteyen Microsoft izinleri istenen açılır pencereyi gösteren ekran görüntüsü.":::

>[!NOTE]
>* *Kuruluş çözümünüz için ekleme* , SKU 'ları desteklemez.
>* [Üretime gitmek](move-to-production.md) için aşağıdaki yapılandırmalardan birine ihtiyacınız olacaktır:
>    * Pro lisanslarına sahip tüm kullanıcılar.
>    * PPU lisanslarına sahip tüm kullanıcılar.
>    * [Kapasite](embedded-capacity.md). Bu yapılandırma, tüm kullanıcıların ücretsiz lisansa sahip olmasını sağlar.

Bu diyagramda, *kuruluş çözümünüz için ekleme* için kimlik doğrulama akışına bir örnek gösterilir.

>[!div class="mx-imgBorder"]
>:::image type="content" source="media/embed-tokens/saas-authentiction.png" alt-text="Kuruluşunuzun Power B Embedded Analytics çözümü için bir embed 'te kimlik doğrulaması akışının diyagramı.":::

1. Web uygulaması kullanıcısı Web uygulamasına erişir.

2. Web uygulaması, Web uygulaması kullanıcısını Azure AD 'ye yönlendirir.

3. Web uygulaması kullanıcısı, Power BI kimlik bilgilerini kullanarak Azure AD 'nin kimliğini doğrular.

4. Azure AD, Web uygulaması kullanıcısını Azure AD belirteci ile Web uygulamasına yeniden yönlendirir (örtük verme senaryosunda, erişim belirteci kullanıcının tarayıcısına döndürülür).

5. Web uygulaması, Azure AD belirtecini kullanıcının Web tarayıcısına geçirir.

6. Power BI Web uygulamanız, Web uygulaması kullanıcısının erişim hakkına sahip olduğu raporlar ve panolar gibi Power BI içerikleri eklemek için Azure AD belirtecini kullanır.

## <a name="next-steps"></a>Sonraki adımlar

>[!div class="nextstepaction"]
>[Ekleme belirteci oluştururken dikkate alınması gerekenler](generate-embed-token.md)

>[!div class="nextstepaction"]
>[Power BI tümleşik analizinde kapasite ve SKU’lar](embedded-capacity.md)

>[!div class="nextstepaction"]
>[Başka bir sorunuz mu var? Power BI Topluluğu'na sormayı deneyin](https://community.powerbi.com/)