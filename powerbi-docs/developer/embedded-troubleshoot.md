---
title: Katıştırılmış uygulamanızla ilgili sorunları giderme
description: Bu makalede, Power BI'dan içerik katıştırma sırasında karşılaşabileceğiniz bazı yaygın sorunlar açıklanmaktadır.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 07/03/2018
ms.author: maghan
ms.openlocfilehash: b3c9599ea3ce01094bb75d9b036fb25b1ca7109a
ms.sourcegitcommit: 627918a704da793a45fed00cc57feced4a760395
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37926571"
---
# <a name="troubleshooting-your-embedded-application"></a>Katıştırılmış uygulamanızla ilgili sorunları giderme

Bu makalede, Power BI'dan içerik katıştırma sırasında karşılaşabileceğiniz bazı yaygın sorunlar açıklanmaktadır.

## <a name="tools-for-troubleshooting"></a>Sorun giderme araçları

### <a name="fiddler-trace"></a>Fiddler ile İzleme

[Fiddler](http://www.telerik.com/fiddler), Telerik tarafından kullanıma sunulup HTTP trafiğini izleyen ücretsiz bir araçtır.  İstemci makinesinden Power BI API'lerindeki gelen ve giden trafiği görebilirsiniz. Bu sayede hataları ve diğer ilgili bilgileri görüntüleyebilirsiniz.

![Fiddler ile İzleme](../includes/media/gateway-onprem-tshoot-tools-include/fiddler.png)

### <a name="f12-in-browser-for-front-end-debugging"></a>Ön uç hata ayıklama için Tarayıcıda F12

F12 tarayıcınızda geliştirici penceresini açar. Bu, ağ trafiğini ve diğer bilgileri görüntüleme olanağı sağlar.

![F12 Tarayıcı hata ayıklama](media/embedded-troubleshoot/browser-f12.png)

### <a name="extracting-error-details-from-power-bi-response"></a>Power BI yanıtından hata ayrıntılarını ayıklama

Bu kod parçacığı, HTTP özel durumundan hata ayrıntılarını ayıklama işleminin nasıl yapılacağını göstermektedir:

```
public static string GetExceptionText(this HttpOperationException exc)
{
    var errorText = string.Format("Request: {0}\r\nStatus: {1} ({2})\r\nResponse: {3}",
    exc.Request.Content, exc.Response.StatusCode, (int)exc.Response.StatusCode, exc.Response.Content);
    if (exc.Response.Headers.ContainsKey("RequestId"))
    {
        var requestId = exc.Response.Headers["RequestId"].FirstOrDefault();
        errorText += string.Format("\r\nRequestId: {0}", requestId);
    }

    return errorText;
}
```
Sorun giderme işlemi için istek kimliklerinin ve hata ayrıntılarının günlüğe kaydedilmesini öneriyoruz.
Lütfen Microsoft destek bölümüyle iletişime geçerken istek kimliğini belirtin.

## <a name="app-registration"></a>Uygulama kaydı

**Uygulama kaydı hatası**

Azure portalı veya Power BI uygulaması kayıt sayfasındaki hata iletileri, yetersiz ayrıcalıktan bahsedecektir. Bir uygulama kaydı için Azure AD kiracısında yönetici olmanız ya da yönetici olmayan kullanıcılar için uygulama kayıtlarının etkinleştirilmiş olması gerekir.

**Power BI Hizmeti yeni bir Uygulama kaydı sırasında Azure portalında görünmüyor**

En az bir kullanıcının Power BI'a kaydolmuş olması gerekir. API listesinde **Power BI Hizmetini** görmüyorsanız hiçbir kullanıcı Power BI'a kaydolmamış demektir.

## <a name="rest-api"></a>REST API

**401 kodunu döndüren API çağrısı**

Daha fazla araştırmak için Fiddler ile yakalama gerekebilir. Azure AD'de kayıtlı uygulama için gerekli izin kapsamı eksik olabilir. Azure portalındaki Azure AD için uygulama kaydında gerekli kapsamın mevcut olduğunu doğrulayın.

**403 kodunu döndüren API çağrısı**

Daha fazla araştırmak için Fiddler ile yakalama gerekebilir. Bir 403 hatasının birkaç nedeni olabilir.

* Kullanıcı, paylaşılan bir kapasitede oluşturulabilecek ekleme belirteci miktarını aştı. Ekleme belirteçleri oluşturmak için Azure kapasitesi satın almanız ve çalışma alanını bu kapasiteye atamanız gerekir. Bkz. [Azure portalında Power BI Embedded kapasitesi oluşturma](https://docs.microsoft.com/azure/power-bi-embedded/create-capacity).
* Azure AD kimlik doğrulama belirtecinin kullanım süresi dolmuştur.
* Kimliği doğrulanmış kullanıcı, grubun (uygulama çalışma alanı) bir üyesi değildir.
* Kimliği doğrulanmış kullanıcı, grubun (uygulama çalışma alanı) bir yöneticisi değildir.
* Yetkilendirme üst bilgisi doğru listelenmemiş olabilir. Yazım hatası olmadığından emin olun.

GenerateToken çağrılmadan önce uygulamanın arka ucunun kimlik doğrulaması belirtecini yenilemesi gerekebilir.

```
    GET https://wabi-us-north-central-redirect.analysis.windows.net/metadata/cluster HTTP/1.1
    Host: wabi-us-north-central-redirect.analysis.windows.net
    ...
    Authorization: Bearer eyJ0eXAiOi...
    ...
 
    HTTP/1.1 403 Forbidden
    ...
     
    {"error":{"code":"TokenExpired","message":"Access token has expired, resubmit with a new access token"}}
```

## <a name="authentication"></a>Kimlik Doğrulama

### <a name="authentication-failed-with-aadsts70002-or-aadsts50053"></a>AADSTS70002 veya AADSTS50053 ile kimlik doğrulaması başarısız oldu

**(AADSTS70002: Kimlik bilgilerini doğrulama hatası. AADSTS50053: Hatalı bir kullanıcı kimliği ve parolayla çok fazla sayıda oturum açma denemesi yaptınız)**

Power BI Embedded'i ve Azure AD Doğrudan Kimlik Doğrulaması'nı kullanıyorsanız ve oturum açarken ***error:unauthorized_client,error_description:AADSTS70002: Kimlik bilgilerini doğrulama hatası. AADSTS50053: Hatalı bir kullanıcı kimliği ve parolayla çok fazla sayıda oturum açma denemesi yaptınız*** iletilerini alıyorsanız, bunun nedeni doğrudan kimlik doğrulamasının 14/6/2018 tarihinden itibaren kapatılmış olmasıdır.

Eski kimlik doğrulamasını engellemek için [Azure AD Koşullu Erişim](https://cloudblogs.microsoft.com/enterprisemobility/2018/06/07/azure-ad-conditional-access-support-for-blocking-legacy-auth-is-in-public-preview/) desteğinin kullanılmasını veya [Azure AD Dizin Doğrudan Kimlik Doğrulama](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication) kullanılmasını öneririz.

Öte yandan, kapsam olarak kuruluşun veya bir [hizmet sorumlusunun](https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-application-objects#service-principal-object) belirlenebileceği bir [Azure AD İlkesi](https://docs.microsoft.com/en-us/azure/active-directory/manage-apps/configure-authentication-for-federated-users-portal#enable-direct-authentication-for-legacy-applications) kullanarak bunu geri geçirmenin bir yolu vardır.

**_Bunu yalnızca uygulama başına veya geçici bir çözüm olarak gerekli olduğunda etkinleştirmenizi öneririz._**

Bu ilkeyi oluşturmak için, ilkeyi oluşturduğunuz ve atadığınız dizinin **Genel Yöneticisi** olmanız gerekir. Burada, bu uygulama için ilkeyi oluşturmaya ve SP'ye atamaya yönelik örnek bir betik verilmiştir:

1. [Azure AD Preview PowerShell Modülü](https://docs.microsoft.com/en-us/powershell/azure/active-directory/install-adv2?view=azureadps-2.0)'nü yükleyin.

2. Aşağıdaki Powershell komutlarını satır satır çalıştırın ($sp değişkeninin sonucunda 1'den çok uygulama olmadığından emin olun).

```powershell
Connect-AzureAD
```

```powershell
$sp = Get-AzureADServicePrincipal -SearchString "Name_Of_Application"
```

```powershell
$policy = New-AzureADPolicy -Definition @("{`"HomeRealmDiscoveryPolicy`":{`"AllowCloudPasswordValidation`":true}}") -DisplayName EnableDirectAuth -Type HomeRealmDiscoveryPolicy -IsOrganizationDefault $false
```

```powershell
Add-AzureADServicePrincipalPolicy -Id $sp.ObjectId -RefObjectId $policy.Id 
```

İlkeyi atadıktan sonra, test etmeden önce yayılması için lütfen 15-20 saniye kadar bekleyin.

**Etkin kimlik sağlanırken belirteç oluşturulamıyor**

GenerateToken, etkin kimlik sağlandığında birkaç nedenden dolayı başarısız olabilir.

* Veri kümesi etkin kimliği desteklemiyor
* Kullanıcı adı sağlanmadı
* Rol sağlanmadı
* DatasetId sağlanmadı
* Kullanıcı doğru izinlere sahip değil

Hangisi olduğunu doğrulamak için aşağıdakileri deneyin.

* [Veri kümesi al](https://docs.microsoft.com/rest/api/power-bi/datasets) komutunu yürütün. IsEffectiveIdentityRequired özelliği doğru mu?
* Kullanıcı adı her EffectiveIdentity için zorunludur.
* IsEffectiveIdentityRolesRequired doğruysa Rol gereklidir.
* DatasetId her EffectiveIdentity için zorunludur.
* Analysis Services için ana kullanıcı bir ağ geçidi yöneticisi olmak zorundadır.

### <a name="aadsts90094-the-grant-requires-admin-permission"></a>AADSTS90094: Verme işlemi için yönetici izni gerekiyor

**_Belirtiler:_**</br>
Yönetici olmayan bir kullanıcı uygulamada ilk kez oturum açmayı ve izin vermeyi denediğinde şu hatayı alır:
* Onay Testi'nin, kuruluşunuzdaki kaynaklara erişim için yalnızca yöneticinin verebileceği izne ihtiyacı vardır. Kullanabilmek için önce lütfen yöneticiden bu uygulamaya izin vermesini isteyin.
* AADSTS90094: Verme işlemi için yönetici izni gerekiyor.

    ![Onay Testi](media/embedded-troubleshoot/consent-test-01.png)

Bir yönetici oturum açabilir ve başarılı bir şekilde onay verebilir.

**_Kök nedeni:_**</br>
Kiracı için kullanıcı onayı devre dışı bırakıldı.

**_Çeşitli düzeltmeler yapılabilir:_**

*Kiracının tamamı için kullanıcı onayını etkinleştir (tüm kullanıcılar, tüm uygulamalar)*
1. Azure Portalı'nda "Azure Active Directory" => "Kullanıcılar ve gruplar" => "Kullanıcı ayarları" bölümüne gidin
2. "Kullanıcılar, uygulamalara kendileri adına şirket verilerine erişme izni verebilir" ayarını etkinleştirin ve değişiklikleri kaydedin

    ![Onay Testi Düzeltmesi](media/embedded-troubleshoot/consent-test-02.png)

*Yönetici tarafından izin verme* Kiracının tamamı için veya belirli bir kullanıcı için bir yönetici tarafından uygulamaya izin verme.

## <a name="data-sources"></a>Veri kaynakları

**ISV aynı veri kaynağı için farklı kimlik bilgilerine sahip olmak istiyor**

Bir veri kaynağında, bir ana kullanıcı için tek kimlik bilgisi kümesi olabilir. Farklı kimlik bilgileri kullanmanız gerekiyorsa ek ana kullanıcılar oluşturun. Ardından, her ana kullanıcı bağlamında farklı kimlik bilgileri atayın ve kullanıcının Azure AD belirtecini kullanarak ekleyin.

## <a name="content-rendering"></a>İçerik işleme

**Katıştırılmış içeriği işleme veya kullanma girişimi başarısız oldu veya zaman aşımına uğradı**

Ekleme belirtecinin son kullanma tarihinin geçmediğinden emin olun. Ekleme belirtecinin son kullanma tarihini kontrol ettiğinizden ve yenilediğinizden emin olun. Daha fazla bilgi için bkz. [JavaScript SDK kullanarak belirteci yenileme](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Refresh-token-using-JavaScript-SDK-example).

**Rapor veya pano yüklenmiyor**

Kullanıcı raporu veya panoyu göremiyorsa rapor ya da panonun powerbi.com'a doğru şekilde yüklendiğinden emin olun. Rapor veya pano, powerbi.com'a yüklenmezse uygulamanızda çalışmaz.

**Rapor veya Pano yavaş çalışıyor**

Power BI Desktop'tan veya powerbi.com'da dosyayı açın ve uygulamanızla veya API'leri eklemeyle ilgili sorunları elemek için performansın kabul edilebilir olduğunu doğrulayın.

## <a name="onboarding-experience-tool-for-embedding"></a>Ekleme için katılım deneyimi aracı

Bir örnek uygulamayı hızlıca indirmek için [Katılım deneyimi aracını](https://aka.ms/embedsetup) inceleyebilirsiniz. Daha sonra uygulamanızı örnekle karşılaştırabilirsiniz.

### <a name="prerequisites"></a>Önkoşullar

Katılım deneyimi aracını kullanmadan önce tüm uygun önkoşulları yerine getirdiğinizi doğrulayın. Bir **Power BI Pro** hesabı ve bir **Microsoft Azure** aboneliği gerekir.

* **Power BI Pro**’ya kaydolmadıysanız başlamadan önce [ücretsiz deneme için kaydolun](https://powerbi.microsoft.com/en-us/pricing/).
* Azure aboneliğiniz yoksa başlamadan önce [ücretsiz bir hesap](https://azure.microsoft.com/free/?WT.mc_id=A261C142F) oluşturun.
* [Azure Active Directory kiracınız](create-an-azure-active-directory-tenant.md) ayarlanmış olmalıdır.
* [Visual Studio](https://www.visualstudio.com/) yüklü olmalıdır (sürüm 2013 veya üzeri).

### <a name="common-issues"></a>Sık Karşılaşılan Sorunlar

Katılım deneyimi aracı ile test etme sırasında karşılaşabileceğiniz bazı yaygın sorunlar şunlardır:

#### <a name="using-the-embed-for-your-customers-sample-application"></a>Embed for your customers örnek uygulamasını kullanma

**Embed for your customers** deneyimi ile çalışıyorsanız *PowerBI-Developer-Samples.zip* dosyasını kaydedin ve sıkıştırmasını açın. Ardından *PowerBI-Developer-Samples-master\App Owns Data* klasörünü açın ve *PowerBIEmbedded_AppOwnsData.sln* dosyasını çalıştırın.

**İzin ver**’i seçtiğinizde (İzin verme adımı) aşağıdaki hatayı alırsınız:

    AADSTS70001: Application with identifier <client ID> was not found in the directory <directory ID>

Bunun çözümü, açılır pencereyi kapatmak ve birkaç saniye bekleyip tekrar denemektir. Bu eylemi birkaç kez yinelemeniz gerekebilir. Uygulama kayıt işlemini tamamlama ile dış API’lerin kullanımına sunulması arasındaki zaman aralığı bu soruna neden olur.

Örnek uygulama çalıştırılırken aşağıdaki hata iletisi görüntülenir:

    Password is empty. Please fill password of Power BI username in web.config.

Örnek uygulamaya eklenmeyen tek değer kullanıcı parolanız olduğundan bu hata oluşur. Çözümde Web.config dosyasını açın ve pbiPassword alanını kullanıcınızın parolasıyla doldurun.

#### <a name="using-the-embed-for-your-organization-sample-application"></a>Embed for your organization örnek uygulamasını kullanma

**Embed for your organization** deneyimi ile çalışıyorsanız *PowerBI-Developer-Samples.zip* dosyasını kaydedin ve sıkıştırmasını açın. Ardından *PowerBI-Developer-Samples-master\User Owns Data\integrate-report-web-app* klasörünü açın ve *pbi-saas-embed-report.sln* dosyasını çalıştırın.

**Embed for your organization** örnek uygulamasını çalıştırdığınızda aşağıdaki hatayı alırsınız:

    AADSTS50011: The reply URL specified in the request does not match the reply URLs configured for the application: <client ID>

Bunun nedeni, web sunucusu uygulaması için belirtilen yeniden yönlendirme URL’sinin örneğe ait URL’den farklı olmasıdır. Örnek uygulamayı kaydetmek istiyorsanız yeniden yönlendirme URL’si olarak `http://localhost:13526/` kullanın.

Kayıtlı uygulamayı düzenlemek istiyorsanız, uygulamanın web API’lerine erişim sağlayabilmesi için [AAD kayıtlı uygulamasını](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications#updating-an-application) düzenleme hakkında bilgi edinin.

Power BI kullanıcı profilinizi veya verilerinizi düzenlemek istiyorsanız, [Power BI verilerinizi](https://docs.microsoft.com/en-us/power-bi/service-basic-concepts) düzenleme hakkında bilgi edinin.

Daha fazla bilgi için lütfen bkz. [Power BI Embedded SSS](embedded-faq.md).

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)