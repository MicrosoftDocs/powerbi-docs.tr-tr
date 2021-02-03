---
title: Power BI tümleşik analiz uygulamanıza içerik ekleyerek kuruluşunuz için daha iyi tümleşik BI içgörüleri sağlama
description: Tümleşik analiz yazılımını, tümleşik analiz araçlarını veya tümleşik iş zekası araçlarını kullanarak Power BI’ı uygulamanızla tümleştirmeyi öğrenin. Power BI tümleşik analiz kullanarak daha iyi tümleşik BI içgörüleri elde edin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: tutorial
ms.custom: seodec18
ms.date: 12/17/2020
ms.openlocfilehash: fbae63597ecf4ff36783ad83785f87c242359f90
ms.sourcegitcommit: 2e81649476d5cb97701f779267be59e393460097
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/02/2021
ms.locfileid: "99494990"
---
# <a name="tutorial-embed-power-bi-content-using-a-sample-embed-for-your-organization-application"></a>Öğretici: *kuruluş uygulamanız için* örnek bir ekleme kullanarak Power BI içerik ekleme

Power BI ekli analiz, raporlar, panolar ve kutucuklar gibi Power BI içerikleri uygulamanıza eklemenize olanak tanır.

Bu öğreticide aşağıdakilerin nasıl yapılacağını öğreneceksiniz:

>[!div class="checklist"]
>* Tümleşik analiz ortamınızı ayarlama.
>* *Kuruluşunuz için bir ekleme* ( *veri sahibi olan Kullanıcı* olarak da bilinir) örnek uygulama yapılandırın.

Uygulamanızı kullanmak için kullanıcılarınızın Power BI oturum açması gerekir.

Kuruluşunuz için ekleme çözümü genellikle kurumsal şirketler ve büyük kuruluşlar tarafından kullanılır ve şirket içi kullanıcılara yöneliktir.

## <a name="code-sample-specifications"></a>Kod örneği belirtimleri

Bu öğreticide, aşağıdaki çerçevelerden birinde kuruluş örnek uygulamanız *için bir ekleme* yapılandırma yönergeleri yer almaktadır:

* .NET Framework
* .NET Core
* Tepki TypeScript

>[!NOTE]
>*.NET Core* ve *.NET Framework* örnekleri, son kullanıcının Power BI hizmeti erişimi olan Power BI Pano, rapor veya kutucuk görüntülemesine olanak tanır. Yanıt verme *TypeScript* örneği, son kullanıcılarınızın Power BI hizmeti üzerinde zaten erişimi olan tek bir rapor eklemenizi sağlar.

Kod örneği aşağıdaki tarayıcıları destekler:

* Microsoft Edge
* Google Chrome
* Mozilla Firefox

## <a name="prerequisites"></a>Önkoşullar

Bu öğreticiye başlamadan önce hem Power BI'a hem de aşağıda listelenen kod bağımlılıklarına sahip olduğunuzdan emin olun:

* **Power BI bağımlılıkları**

    * Kendi [Azure Active Directory kiracınız](create-an-azure-active-directory-tenant.md).

    * Aşağıdaki lisanslardan biri:

        * [Power BI Pro](../../admin/service-admin-purchasing-power-bi-pro.md)

        * [Kullanıcı başına Premium (PPU)](../../admin/service-premium-per-user-faq.md)

    >[!NOTE]
    >[Üretime gitmek](move-to-production.md) için aşağıdaki yapılandırmalardan birine ihtiyacınız olacaktır:
    >* Pro lisanslarına sahip tüm kullanıcılar.
    >* PPU lisanslarına sahip tüm kullanıcılar.
    >* [Kapasite](embedded-capacity.md). Bu yapılandırma, tüm kullanıcıların ücretsiz lisansa sahip olmasını sağlar.

* **Kod bağımlılıkları**

    # <a name="net-core"></a>[.NET Core](#tab/net-core)

    * [.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet-core) (veya üzeri)
    
    * Bir tümleşik geliştirme ortamı (IDE). Aşağıdakilerden birini kullanmanız önerilir:

        * [Visual Studio](https://visualstudio.microsoft.com/)

        * [Visual Studio Code](https://code.visualstudio.com/)

    # <a name="net-framework"></a>[.NET Framework](#tab/net-framework)

    * [ .NET Framework 4.8](https://dotnet.microsoft.com/download/dotnet-framework/)
    
    * [Visual Studio](https://visualstudio.microsoft.com/)

    # <a name="react-typescript"></a>[Tepki TypeScript](#tab/react)

    * Metin Düzenleyicisi

    * Komut satırı terminali (veya PowerShell)

---

## <a name="method"></a>Yöntem

Kuruluşunuzun örnek uygulamasına bir *ekleme* oluşturmak için aşağıdaki adımları izleyin:

1. [Bir Azure AD uygulaması kaydedin](#step-1---register-an-azure-ad-application).

2. [Power BI çalışma alanı oluşturun](#step-2---create-a-power-bi-workspace).

3. [Power BI raporu oluşturup yayımlayın](#step-3---create-and-publish-a-power-bi-report).

4. [Ekleme parametrelerinin değerlerini alın](#step-4---get-the-embedding-parameter-values).

5. [İçeriğinizi ekleyin](#step-5---embed-your-content).

## <a name="step-1---register-an-azure-ad-application"></a>1. adım-bir Azure AD uygulamasını kaydetme

Uygulamanızı Azure AD 'ye kaydetmek, uygulamanız için bir kimlik ayarlamanıza olanak sağlar.

[!INCLUDE[Register Azure AD app](../../includes/embed-tutorial-register-app.md)]

## <a name="step-2---create-a-power-bi-workspace"></a>2. adım-Power BI çalışma alanı oluşturma

[!INCLUDE[Create a Power BI workspace](../../includes/embed-tutorial-create-workspace.md)]

## <a name="step-3---create-and-publish-a-power-bi-report"></a>3. adım-Power BI raporu oluşturma ve yayımlama

[!INCLUDE[Create a Power BI report](../../includes/embed-tutorial-create-report.md)]

## <a name="step-4---get-the-embedding-parameter-values"></a>4. adım-ekleme parametre değerlerini al

İçeriğinizi eklemek için birkaç parametre değeri edinmeniz gerekir. İhtiyacınız olan parametre değerleri, kullanmak istediğiniz örnek uygulamanın diline bağlı olarak değişir. Aşağıdaki tabloda her örnek için hangi parametre değerlerinin gerekli olduğu listelenmektedir.

|Parametre  |.NET Core  |.NET Framework  |Tepki TypeScript |
|---------|---------|---------|---------|
|[İstemci Kimliği](#client-id) |![Şunun için geçerlidir:](../../media/yes.png) |![Şunun için geçerlidir:](../../media/yes.png)         |![Şunun için geçerlidir:](../../media/yes.png) |
|[Gizli anahtar](#workspace-id) |![Şunun için geçerlidir:](../../media/yes.png) |![Şunun için geçerlidir:](../../media/yes.png) |![Geçerli değildir.](../../media/no.png) |
|[Çalışma Alanı Kimliği]() |![Geçerli değildir.](../../media/no.png) |![Geçerli değildir.](../../media/no.png) |![Şunun için geçerlidir:](../../media/yes.png) |
|[Rapor Kimliği]() |![Geçerli değildir.](../../media/no.png) |![Geçerli değildir.](../../media/no.png) |![Şunun için geçerlidir:](../../media/yes.png) |

### <a name="client-id"></a>İstemci Kimliği

>[!TIP]
>**Uygulama hedefi:** ![ Uygulama hedefi. ](../../media/yes.png) . NET Core ![ için geçerlidir. ](../../media/yes.png) .. NET Framework ![ için geçerlidir. ](../../media/yes.png) Tepki TypeScript

[!INCLUDE[Get the client ID](../../includes/embed-tutorial-client-id.md)]

### <a name="client-secret"></a>Gizli anahtar

>[!TIP]
>**Uygulama hedefi:** ![ Uygulama hedefi. ](../../media/yes.png) . NET Core ![ için geçerlidir. ](../../media/yes.png) .. NET Framework ![ için geçerlidir. ](../../media/no.png) Tepki TypeScript

[!INCLUDE[Get the client secret](../../includes/embed-tutorial-client-secret.md)]

### <a name="workspace-id"></a>Çalışma Alanı Kimliği

>[!TIP]
>**Uygulama hedefi:** ![ İçin geçerlidir. ](../../media/no.png) .. NET Core ![ , için geçerlidir. ](../../media/no.png) .. NET Framework ![ için geçerlidir. ](../../media/yes.png) Tepki TypeScript

[!INCLUDE[Get the workspace ID](../../includes/embed-tutorial-workspace-id.md)]

### <a name="report-id"></a>Rapor Kimliği

>[!TIP]
>**Uygulama hedefi:** ![ İçin geçerlidir. ](../../media/no.png) .. NET Core ![ , için geçerlidir. ](../../media/no.png) .. NET Framework ![ için geçerlidir. ](../../media/yes.png) ReactTypeScript

[!INCLUDE[Get the report ID](../../includes/embed-tutorial-report-id.md)]

## <a name="step-5---embed-your-content"></a>5\. Adım: İçeriğinizi ekleme

Power BI Ekli örnek uygulama, kuruluşunuz Power BI uygulamanız için bir *ekleme* oluşturmanıza olanak sağlar.

Power BI raporunuzu eklemek için, kuruluşunuzun örnek uygulamasına *yönelik ekleme* 'yı değiştirmek üzere bu adımları izleyin.

[!INCLUDE[Embedding steps](../../includes/embed-tutorial-embedding-steps.md)]

4. Uygulamanızda kullanmak istediğiniz dile bağlı olarak şu klasörlerden birini açın:

    * .NET Core
    * .NET Framework
    * Tepki verme

    >[!NOTE]
    >*Kuruluşunuz için ekleme* örnek uygulamalar yalnızca yukarıda listelenen çerçeveleri destekler. *Java*, *node js* ve *Python* örnek uygulamaları, yalnızca *[müşterileriniz için embed](embed-sample-for-customers.md)* çözümünü destekler.

# <a name="net-core"></a>[.NET Core](#tab/net-core)

### <a name="configure-your-azure-ad-app"></a>Azure AD uygulamanızı yapılandırma

[!INCLUDE[Configure the Azure AD authentication options](../../includes/embed-tutorial-org-azure-ad-app.md)]

5. *Platform yapılandırmalarında* *Web* platformunuzu açın ve **yeniden yönlendirme URI 'leri** bölümüne ekleyin `https://localhost:5000/signin-oidc` .

    > [!NOTE]
    >**Web** platformunuz yoksa **Platform Ekle** ' yi seçin ve *platformları Yapılandır* penceresinde **Web**' i seçin.

6. Yaptığınız değişiklikleri kaydedin.

:::image type="content" source="media/embed-sample-for-your-organization/azure-ad-net-configurations.png" alt-text=".NET Core uygulama örneği için Web yeniden yönlendirme U R ı dahil olmak üzere Azure AD uygulama kimlik doğrulama yapılandırmalarının gösterildiği ekran görüntüsü.":::

### <a name="configure-the-sample-embedding-app"></a>Örnek ekleme uygulamasını yapılandırma

1. **Kuruluşunuz Için embed** klasörünü açın.

2. Aşağıdaki yöntemlerden birini kullanarak, *Kuruluşunuz için ekleme örnek uygulamanızı* açın:

    * [Visual Studio](https://visualstudio.microsoft.com/)kullanıyorsanız, **Userownsdata. sln** dosyasını açın.

    * [Visual Studio Code](https://code.visualstudio.com/)kullanıyorsanız **Userownsdata** klasörünü açın.

3. **appsettings.js** açın ve aşağıdaki parametre değerlerini girin:

    * `ClientId` - [ISTEMCI kimliği](#client-id) GUID 'sini kullan

    * `ClientSecret`- [İstemci gizliliğini](#client-secret) kullanın

### <a name="run-the-sample-app"></a>Örnek uygulamayı çalıştırma

1. Uygun seçeneği belirleyerek projeyi çalıştırın:

    * **Visual Studio** kullanıyorsanız **IIS Express** (yürüt) öğesini seçin.

    * **Visual Studio Code** kullanıyorsanız **Çalıştır > Hata Ayıklamayı Başlat**'ı seçin.

[!INCLUDE[The embedded application sample app interface](../../includes/embed-tutorial-org-sample-app.md)]

# <a name="net-framework"></a>[.NET Framework](#tab/net-framework)

### <a name="configure-your-azure-ad-app"></a>Azure AD uygulamanızı yapılandırma

[!INCLUDE[Configure the Azure AD authentication options](../../includes/embed-tutorial-org-azure-ad-app.md)]

5. *Platform yapılandırmalarında*, aşağıdakileri yapılandırın:

    1. *Web* platformda, **yeniden yönlendirme URI 'leri** bölümüne ekleyin `https://localhost:44300/` .

        > [!NOTE]
        >**Web** platformunuz yoksa **Platform Ekle** ' yi seçin ve *platformları Yapılandır* penceresinde **Web**' i seçin.
    
    2. *Örtük verme ve karma akışlarda*, **Kimlik belirteçleri** seçeneğini etkinleştirin.
    
6. Yaptığınız değişiklikleri kaydedin.

:::image type="content" source="media/embed-sample-for-your-organization/azure-ad-framework-configurations.png" alt-text="Web yeniden yönlendirme U R ı ve .NET Framework uygulama örneği için seçilen erişim belirteci seçeneği dahil olmak üzere Azure AD uygulama kimlik doğrulama yapılandırmalarının ekran görüntüsü.":::

### <a name="configure-the-sample-embedding-app"></a>Örnek ekleme uygulamasını yapılandırma

1. **Kuruluşunuz Için embed** klasörünü açın.

2. [Visual Studio](https://visualstudio.microsoft.com/)'Yu kullanarak **Userownsdata. sln** dosyasını açın.

3. **Web.config** açın ve aşağıdaki parametre değerlerini girin:

    * `clientId` - [ISTEMCI kimliği](#client-id) GUID 'sini kullan

    * `clientSecret`- [İstemci gizliliğini](#client-secret) kullanın

### <a name="run-the-sample-app"></a>Örnek uygulamayı çalıştırma

1. **IIS Express** (yürüt) öğesini seçerek projeyi çalıştırın.

[!INCLUDE[The embedded application sample app interface](../../includes/embed-tutorial-org-sample-app.md)]

# <a name="react-typescript"></a>[Tepki TypeScript](#tab/react)

### <a name="configure-your-azure-ad-app"></a>Azure AD uygulamanızı yapılandırma

[!INCLUDE[Configure the Azure AD authentication options](../../includes/embed-tutorial-org-azure-ad-app.md)]

5. *Platform yapılandırmalarında*, **Web** platformunuzu aşağıdaki şekilde yapılandırın:

    1. **Yeniden yönlendirme URI 'Lerinde** `https://localhost:3000` **Yapılandır**' ı ekleyin ve seçin.

        > [!NOTE]
        >**Web** platformunuz yoksa **Platform Ekle** ' yi seçin ve *platformları Yapılandır* penceresinde **Web**' i seçin.

    2. *Örtük verme ve karma akışlarda* her iki seçeneği de etkinleştirin:
        * **Erişim belirteçleri**
        * **Kimlik belirteçleri**
    
6. Yaptığınız değişiklikleri kaydedin.

:::image type="content" source="media/embed-sample-for-your-organization/azure-ad-react-configurations.png" alt-text="Localhost 3000 için ayarlanan Web yeniden yönlendirme U R I de dahil olmak üzere Azure AD uygulama kimlik doğrulama yapılandırmalarının gösterildiği ekran görüntüsü.":::

### <a name="configure-the-sample-embedding-app"></a>Örnek ekleme uygulamasını yapılandırma

1. **Kuruluşunuz için ekleme**  >  **userownsdata**  >  **src** klasörünü açın.

2. Bir metin düzenleyicisi kullanarak, **config. TS** dosyasını açın ve aşağıdaki parametre değerlerini girin:

    * `clientId` - [ISTEMCI kimliği](#client-id) GUID 'sini kullan

    * `workspaceId`- [Çalışma alanı kimliğini](#client-secret) kullanın

    * `reportId`- [Rapor kimliğini](#report-id) kullanın

3. Dosyayı kaydedin.

### <a name="run-the-sample-app"></a>Örnek uygulamayı çalıştırma

1. İçinde bir Terminal açın ve **kuruluşunuzun**  >  **userownsdata** için ekleme bölümüne gidin.

2. Aşağıdaki komutu yürüterek gerekli bağımlılıkları yükler:

   `npm install`

3. Aşağıdaki komutu yürüterek uygulamayı çalıştırın:

   `npm run start`

    >[!NOTE]
    >İlk oturum açma sırasında, uygulama için Azure AD izinlerine izin vermeniz istenir.

---

## <a name="developing-your-application"></a>Uygulamanızı geliştirme

Örnek *müşterileriniz için ekleme* uygulamasını yapılandırdıktan sonra kendi uygulamanızı geliştirmeye başlayabilirsiniz.

[!INCLUDE[Move to production](../../includes/embed-tutorial-production.md)]

## <a name="next-steps"></a>Sonraki adımlar

> [!div class="nextstepaction"]
>[Üretime taşıma](move-to-production.md)

>[!div class="nextstepaction"]
>[Müşterileriniz için ekleme](embed-sample-for-customers.md)

> [!div class="nextstepaction"]
>[Müşterileriniz için sayfalandırılmış raporlar ekleme](embed-paginated-reports-customers.md)

> [!div class="nextstepaction"]
>[Kuruluşunuz için sayfalandırılmış raporlar ekleme](embed-paginated-reports-organization.md)

>[!div class="nextstepaction"]
>[Power BI Topluluğu'na sorun](https://community.powerbi.com/)