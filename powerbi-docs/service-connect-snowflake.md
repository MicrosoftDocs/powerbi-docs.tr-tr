---
title: Power BI ile Snowflake'e bağlanma
description: Power BI için SSO ile Snowflake
author: cpopell
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 11/20/2019
ms.author: gepopell
LocalizationGroup: Connect to services
ms.openlocfilehash: 5e5519e30be30d6367791d1b6822196b407a21b1
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "77576853"
---
#  <a name="connecting-to-snowflake-in-power-bi-service"></a>Power BI hizmetinde Snowflake'e bağlanma

## <a name="introduction"></a>Giriş

Power BI hizmetinde Snowflake'e bağlanmanın diğer bağlayıcılardan tek farkı, AAD için sunulan ek özelliktir (SSO seçeneği). Tümleştirmenin farklı bölümlerinde Snowflake, Power BI ve Azure için farklı yönetici rollerine ihtiyaç duyulur. SSO kullanmadan da AAD kimlik doğrulamasını etkinleştirebilirsiniz. Temel kimlik doğrulaması, hizmetteki diğer bağlayıcılara benzer şekilde çalışır.

AAD tümleştirmesini yapılandırmak ve isteğe bağlı SSO özelliğini etkinleştirmek istiyorsanız:
* Snowflake yöneticisiyseniz lütfen Snowflake belgelerindeki [Snowflake için Power BI SSO - Kullanmaya Başlama](https://docs.snowflake.net/manuals/LIMITEDACCESS/oauth-powerbi.html) makalesini okuyun.
* (SSO) Power BI yöneticisiyseniz "Power BI Hizmeti yapılandırması - Yönetim Portalı" bölümünü inceleyin
* (SSO) Power BI veri kümesi oluşturucusuysanız "Power BI Hizmeti yapılandırması - Veri kümesini etkinleştirme" bölümünü inceleyin

## <a name="power-bi-service-configuration"></a>Power BI Hizmeti yapılandırması

### <a name="admin-portal"></a>Yönetim Portalı

SSO özelliğini etkinleştirmek istiyorsanız kiracı yöneticisinin Yönetim Portalına giderek Power BI AAD kimlik bilgilerinin Snowflake'e gönderilmesini onaylaması gerekir.

![Snowflake SSO için kiracı yöneticisi ayarı](media/service-connect-snowflake/snowflakessotenant.png)

"Yönetim Portalınıza" gidin, "Kiracı Ayarları" kenar çubuğu öğesini seçin, sayfanın "Tümleştirme Ayarları" bölümüne kaydırın ve "Snowflake SSO" seçeneğini bulun.

Yukarıda belirtildiği gibi AAD belirtecinizin Snowflake sunucularına gönderilmesini onaylamak için bu özelliği el ile etkinleştirmeniz gerekir. Etkinleştirmek için "Devre dışı" düğmesine tıklayın, Uygula'ya basın ve ayarların geçerli hale gelmesini bekleyin. Hizmetin yapılandırmayı yayması bir saate kadar sürebilir.

Bu işlem tamamlandıktan sonra raporları SSO ile kullanabilirsiniz.

### <a name="configuring-a-dataset-with-aad"></a>AAD ile veri kümesi yapılandırma

Snowflake bağlayıcısını temel alan bir rapor, Power BI web hizmetinde web üzerinde yayımlandıktan sonra, veri kümesi oluşturucusunun uygun çalışma alanına gitmesi, "Veri kümeleri"ni ve ardından "Ayarlar"ı seçmesi gerekir (ilgili veri kümesinin yanında bulunan ve ek eylemlerin yer aldığı "..." menüsünün altında).

Power BI'ın çalışma şekli nedeniyle SSO yalnızca şirket içi veri ağ geçidi aracılığıyla çalıştırılan veri kaynağı olmadığında çalışır.

* Veri modelinizde yalnızca bir Snowflake kaynağı kullanıyorsanız, şirket içi veri ağ geçidini kullanmama şartıyla SSO özelliğini kullanabilirsiniz
* Veri modelinizde başka bir kaynağa ek olarak bir Snowflake kaynağı kullanıyorsanız, bu kaynakların hiçbirinin şirket içi veri ağ geçidini kullanmaması şartıyla SSO özelliğini kullanabilirsiniz
* Şirket içi veri ağ geçidi üzerinden Snowflake kaynağı kullanılan durumlar için şu anda AAD kimlik bilgileri desteklenmez. Bu durum bir sanal ağa Power BI IP aralığının tamamından değil ağ geçidi yüklü olan tek bir IP adresinden erişmeye çalıştığınız durumlarda geçerli olabilir.
* Snowflake kaynağını ağ geçidine ihtiyaç duyan başka bir kaynakla birlikte kullanıyorsanız Snowflake'i de şirket içi veri ağ geçidinden kullanmanız gerekir ve SSO kullanamazsınız.

Şirket içi veri ağ geçidini kullanma hakkında daha fazla bilgi için [Şirket içi veri ağ geçidi nedir?](https://docs.microsoft.com/power-bi/service-gateway-onprem) makalesine bakın.

Ağ geçidi kullanmıyorsanız yapmanız gereken başka işlem yoktur. Şirket içi veri ağ geçidinizde Snowflake kimlik bilgileri yapılandırıldıysa ancak modelinizde yalnızca o veri kaynağını kullanıyorsanız, Veri kümesi ayarları sayfasındaki düğmeye tıklayarak ağ geçidini o veri modeli için kapatabilirsiniz.

![Ağ geçidini kapatmayı sağlayan veri kümesi ayarı](media/service-connect-snowflake/snowflake_gateway_toggle_off.png)

Veri kümesi oluşturucusunun "Veri kaynağı kimlik bilgileri"ni seçerek oturum açması gerekir. Veri kümesinin Snowflake'te oturum açması için Temel kimlik bilgileri veya OAuth2 (AAD) kimlik bilgileri kullanılabilir. AAD'yi kullanmayı seçerseniz veri kümesinde SSO kullanımı etkinleştirilebilir. Bu ilk kullanıcı Snowflake'te veri kümesi için oturum açtığında diğer kullanıcıların verileri almak için kullanılan Oauth2 kimlik bilgilerinin bulunacağı seçeneği belirlemesi gerekir. Bu durumda AAD SSO etkinleştirilir. İlk kullanıcının Temel kimlik doğrulaması veya OAuth2 (AAD) ile oturum açma durumundan bağımsız olarak SSO için AAD kimlik bilgileri gönderilir. 

![Snowflake SSO için veri kümesi ayarı](media/service-connect-snowflake/snowflakessocredui.png)

Bu işlem tamamlandıktan sonra diğer kullanıcıların aynı Snowflake veri kümesindeki verilere bağlanmak için otomatik olarak AAD kimlik doğrulamalarını kullanmaları gerekir.

SSO'yu etkinleştirmezseniz raporu yenileyen kullanıcılar, diğer çoğu Power BI raporunda olduğu gibi oturum açmış olan kullanıcının kimlik bilgilerini kullanır.

### <a name="troubleshooting"></a>Sorun Giderme

Tümleştirme konusunda herhangi bir sorunla karşılaşırsanız lütfen Snowflake [sorun giderme kılavuzunu](https://docs.snowflake.net/manuals/LIMITEDACCESS/oauth-powerbi.html#troubleshooting) inceleyin.

