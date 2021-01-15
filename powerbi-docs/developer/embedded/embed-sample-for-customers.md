---
title: Müşterilerinize daha iyi tümleşik BI içgörüleri sağlamak üzere Power BI tümleşik analiz uygulamanıza içerik ekleme
description: Power BI tümleşik analiz örneğine rapor, pano veya kutucuk eklemeyi öğrenin. Power BI tümleşik analiz kullanarak daha iyi tümleşik BI içgörüleri elde edin.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
ms.topic: tutorial
ms.service: powerbi
ms.subservice: powerbi-developer
ms.custom: seodec18
ms.date: 12/22/2020
ms.openlocfilehash: de954c5950f550c3ed2f3c340714851f5233d3e8
ms.sourcegitcommit: a5e98bc86915f7bea6a0ab5df282683840e63d2c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97969777"
---
# <a name="tutorial-embed-power-bi-content-using-a-sample-embed-for-your-customers-application"></a>Öğretici: Örnek *müşterileriniz için ekleme* uygulamasını kullanarak Power BI içeriği ekleme

**Tümleşik analiz** ve **Power BI Embedded** (Azure teklifi) raporlar, panolar ve kutucuklar gibi Power BI içeriklerini uygulamanıza eklemenizi sağlar.

Bu öğreticide aşağıdakilerin nasıl yapılacağını öğreneceksiniz:
>[!div class="checklist"]
>* Tümleşik analiz ortamınızı ayarlama.
>* Örnek *müşterileriniz için ekleme* (*veriler uygulamaya aittir*) uygulamasını yapılandırma.

Kullanıcıların uygulamanızı kullanabilmek için Power BI'da oturum açmaları veya Power BI lisansına sahip olmaları gerekmez.

*Müşterileriniz için ekleme* yöntemi, üçüncü taraflar için oluşturdukları uygulamalara Power BI içeriği eklemek isteyen bağımsız yazılım satıcıları (ISV) veya geliştiriciler için önerilir.

## <a name="code-sample-specifications"></a>Kod örneği belirtimleri

Bu öğreticide örnek *müşterileriniz için ekleme* uygulamasını aşağıdaki dillerde yapılandırmaya yönelik yönergeler bulunmaktadır:

* .NET Framework
* .NET Core
* Java
* Node JS
* Python

Kod örneği aşağıdaki tarayıcıları destekler:

* Google Chrome

* Microsoft Edge

* Mozilla Firefox

## <a name="prerequisites"></a>Önkoşullar

Bu öğreticiye başlamadan önce hem Power BI'a hem de aşağıda listelenen kod bağımlılıklarına sahip olduğunuzdan emin olun:

* **Power BI bağımlılıkları**

    * Kendi [Azure Active Directory kiracınız](create-an-azure-active-directory-tenant.md).

    * Uygulamanızın Power BI kimlik doğrulamasından geçebilmesi için aşağıdakilerden birini kullanmanız gerekir:

        * [Hizmet sorumlusu](embed-service-principal.md): Azure AD'nin uygulamanızın kimlik doğrulamasından geçmesini sağlayan bir Azure Active Directory (Azure AD) [hizmet sorumlusu nesnesi](/azure/active-directory/develop/app-objects-and-service-principals#service-principal-object).

        * [Power BI Pro](../../admin/service-admin-purchasing-power-bi-pro.md) lisansı: Bu, **ana kullanıcınız** olur ve uygulamanız Power BI kimlik doğrulamasından geçmek için bunu kullanır.

        * Power BI [Kullanıcı Başına Premium (PPU)](../../admin/service-premium-per-user-faq.md) lisansı: Bu, **ana kullanıcınız** olur ve uygulamanız Power BI kimlik doğrulamasından geçmek için bunu kullanır.

    >[!NOTE]
    >[Üretim ortamına geçmek](move-to-production.md) için bir [kapasiteye](embedded-capacity.md) ihtiyacınız olacaktır.

* **Kod bağımlılıkları**

    # <a name="net-framework"></a>[.NET Framework](#tab/net-framework)
    
    * [ .NET Framework 4.8](https://dotnet.microsoft.com/download/dotnet-framework/)
    
    * [Visual Studio](https://visualstudio.microsoft.com/)
    
    
    # <a name="net-core"></a>[.NET Core](#tab/net-core)
    
    * [.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet-core) (veya üzeri)
    
    * Bir tümleşik geliştirme ortamı (IDE). Aşağıdakilerden birini kullanmanız önerilir:
    
        * [Visual Studio](https://visualstudio.microsoft.com/)
    
        * [Visual Studio Code](https://code.visualstudio.com/)

    # <a name="java"></a>[Java](#tab/java)
    
    * [JDK (veya JRE)](https://www.oracle.com/java/technologies/)
    
    * [Eclipse IDE](https://www.eclipse.org/downloads/packages/): *Eclipse for Java EE Developers* (Enterprise Edition) paketine sahip olduğunuzdan emin olun
    
    * [Apache Tomcat İkili Dağıtımları](https://tomcat.apache.org/)
    
    # <a name="node-js"></a>[Node JS](#tab/node-js)
    
    * [ .NET Framework 4.8](https://dotnet.microsoft.com/download/dotnet-framework/)
    
    * Bir tümleşik geliştirme ortamı (IDE). Aşağıdakilerden birini kullanmanız önerilir:
    
        * [Visual Studio](https://visualstudio.microsoft.com/)
    
        * [Visual Studio Code](https://code.visualstudio.com/)
    
    # <a name="python"></a>[Python](#tab/python)
    
    * [Python 3](https://www.python.org/downloads/) (veya üzeri)
    
        >[!NOTE]
        >* *Python*'ı ilk kez yüklüyorsanız yüklemeyi `PATH` değişkenine eklemek için **Add Python to PATH** (Python'ı PATH değişkenine ekle) seçeneğini işaretleyin.
        >* *Python* sisteminizde yüklüyse, yükleme yolunun `PATH` değişkenine eklenmiş olduğunu doğrulayın. Daha fazla bilgi için Python belgelerinin [Excursus: Setting environment variables](https://docs.python.org/3/using/windows.html#excursus-setting-environment-variables) (Ek Açıklama: Ortam değişkenlerini ayarlama) bölümüne bakın (bu bağlantı Python 3'e aittir).
    
    * Bir tümleşik geliştirme ortamı (IDE). Aşağıdakilerden birini kullanmanız önerilir:
    
        * [Visual Studio](https://visualstudio.microsoft.com/)
    
        * [Visual Studio Code](https://code.visualstudio.com/)
    
    ---

## <a name="method"></a>Yöntem

Örnek bir *müşterileriniz için ekleme* uygulaması oluşturmak için aşağıdaki adımları izleyin:

1. [Kullanacağınız kimlik doğrulama yöntemini seçin](#step-1---select-your-authentication-method).

2. [Bir Azure AD uygulaması kaydedin](#step-2---register-an-azure-ad-application).

3. [Power BI çalışma alanı oluşturun](#step-3---create-a-power-bi-workspace).

4. [Power BI raporu oluşturup yayımlayın](#step-4---create-and-publish-a-power-bi-report).

5. [Ekleme parametrelerinin değerlerini alın](#step-5---get-the-embedding-parameter-values).

6. [Hizmet sorumlusu API erişimi](#step-6---service-principal-api-access)
 
7. [Çalışma alanı erişimini etkinleştirin](#step-7---enable-workspace-access).

8. [İçeriğinizi ekleyin](#step-8---embed-your-content).

## <a name="step-1---select-your-authentication-method"></a>1\. Adım: Kullanacağınız kimlik doğrulama yöntemini seçin

Tümleşik analiz çözümünüz, seçtiğiniz kimlik doğrulama yöntemine göre farklılık gösterecektir. Bu nedenle kimlik doğrulama yöntemleri arasındaki farkları anlamak ve çözümünüze en uygun olanı belirlemek önemlidir.

Aşağıdaki tabloda [hizmet sorumlusu](embed-service-principal.md) ile **ana kullanıcı** kimlik doğrulama yöntemleri arasındaki temel farklar listelenmiştir.

|Değerlendirme  |Hizmet sorumlusu  |Ana kullanıcı  |
|---------|---------|---------|
|Mechanism     |Azure AD uygulamanızın [hizmet sorumlusu nesnesi](/azure/active-directory/develop/app-objects-and-service-principals#service-principal-object), Azure AD'nin tümleşik analiz çözümünüzü Power BI kimlik doğrulamasından geçirmesini sağlar.        |Azure AD uygulamanız, Power BI'da kimlik doğrulamasından geçmek için bir Power BI kullanıcısının kimlik bilgilerini (kullanıcı adı ve parola) kullanır.         |
|Güvenlik     |*Hizmet sorumlusu*, Azure AD tarafından önerilen yetkilendirme yöntemidir. Hizmet sorumlusu kullanıyorsanız *uygulama gizli dizisi* veya *sertifika* kullanarak kimlik doğrulamasından geçebilirsiniz.</br></br>Bu öğreticide yalnızca *hizmet sorumlusu* ile *uygulama gizli dizisi* kullanımı gösterilmektedir. *Hizmet sorumlusu* ve *sertifika* kullanarak eklemek için [hizmet sorumlusu ve sertifika](embed-service-principal-certificate.md) makalesine bakın.         |Bu kimlik doğrulama yöntemi, *hizmet sorumlusu* kullanmak kadar güvenli kabul edilmez. Bunun nedeni, *ana kullanıcı* kimlik bilgilerini (kullanıcı adı ve parola) korumak zorunda olmanızdır. Örneğin bu bilgileri tümleşik analiz uygulamanızda göstermemeniz ve parolayı sık sık değiştirmeniz gerekir.         |
|Azure AD temsilci izinleri |Gerekli değildir. |*Ana kullanıcınızın* veya bir yöneticinin, uygulamanızın Power BI REST API [izinlerine](/azure/active-directory/develop/v2-permissions-and-consent) (kapsamlar olarak da bilinir) erişmesine onay vermesi gerekir. Örneğin, *Report.ReadWrite.All*. |
|Power BI hizmeti erişimi |*Hizmet sorumlusu* ile Power BI hizmetine erişemezsiniz.|Power BI hizmetine erişmek için *ana kullanıcı* kimlik bilgilerinizi kullanmanız gerekir.|
|Lisans     |Pro lisansı gerektirmez. Üye veya yönetici olduğunuz tüm çalışma alanlarında bulunan içerikleri kullanabilirsiniz.         |[Power BI Pro](../../admin/service-admin-purchasing-power-bi-pro.md) lisansı gereklidir.         |

## <a name="step-2---register-an-azure-ad-application"></a>2\. Adım: Bir Azure AD uygulaması kaydedin

Uygulamanızı Azure AD'ye kaydederek şunları yapabilirsiniz:
> [!div class="checklist"]
>* Uygulamanız için bir kimlik oluşturma
>* Uygulamanızın [Power BI REST API'lerine](/rest/api/power-bi/) erişmesine izin verme
>* *Ana kullanıcı* kullanıyorsanız: Uygulamanızın [Power BI REST izinlerini](/azure/active-directory/develop/v2-permissions-and-consent) belirtme

Uygulamanızı Azure AD'ye kaydetmek için [Uygulamanızı kaydetme](register-app.md) bölümündeki yönergeleri izleyin.

>[!NOTE]
>Uygulamanızı kaydetmeden önce kullanacağınız kimlik doğrulama yöntemini (*hizmet sorumlusu* veya *ana kullanıcı*) belirlemeniz gerekir.

## <a name="step-3---create-a-power-bi-workspace"></a>3\. Adım: Power BI çalışma alanı oluşturun

Power BI'da raporlarınız, panolarınız ve kutucuklarınız bir çalışma alanında saklanır. Bu öğeleri eklemek için onları oluşturup bir çalışma alanına yüklemeniz gerekir.

>[!TIP]
>Çalışma alanınız varsa bu adımı atlayabilirsiniz.

Çalışma alanı oluşturmak için aşağıdakileri yapın:

1. Power BI'da oturum açın.

2. **Çalışma alanları**'nı seçin.

3. **Çalışma alanı oluştur**'u seçin.

4. Çalışma alanınıza bir ad verin ve **Kaydet**'i seçin.

## <a name="step-4---create-and-publish-a-power-bi-report"></a>4\. Adım: Power BI raporu oluşturup yayımlayın

Bir sonraki adım bir rapor oluşturup çalışma alanınıza yüklemektir. Power BI Desktop'ı kullanarak [kendi raporunuzu oluşturabilir](/power-bi/fundamentals/desktop-getting-started#build-reports) ve ardından çalışma alanınızda [yayımlayabilirsiniz](/powerbi-docs/fundamentals/desktop-getting-started#share-your-work). Alternatif olarak çalışma alanınıza örnek raporlardan birini yükleyebilirsiniz.

>[!Tip]
>İçinde rapor bulunan bir çalışma alanınız varsa bu adımı atlayabilirsiniz.

Örnek raporu indirip çalışma alanınızda yayımlamak için şu adımları izleyin:

1. GitHub'daki [Power BI Desktop samples](https://github.com/Microsoft/PowerBI-Desktop-Samples) klasörünü açın.

2. **Kod**'u ve ardından **ZIP'i indir**'i seçin.

    :::image type="content" source="media/embed-sample-for-customers/download-sample-report.png" alt-text="Power BI Desktop Samples GitHub klasöründeki ZIP'i indir seçeneğini gösteren ekran görüntüsü":::

3. İndirdiğiniz ZIP arşivini ayıklayıp **Samples Reports** klasörüne gidin.

4. Eklemek istediğiniz raporu seçip çalışma alanınızda [yayımlayın](/powerbi-docs/fundamentals/desktop-getting-started#share-your-work).

## <a name="step-5---get-the-embedding-parameter-values"></a>5\. Adım: Ekleme parametrelerinin değerlerini alın

İçeriğinizi eklemek için belirli parametre değerlerini almanız gerekir. Aşağıdaki tabloda gerekli değerler verilmiş ve *hizmet sorumlusu* kimlik doğrulama yöntemi, *ana kullanıcı* kimlik doğrulama yöntemi veya her ikisi için uyumlu olup olmadıkları gösterilmiştir.

İçeriğinizi eklemeden önce aşağıda listelenen tüm değerlere sahip olduğunuzdan emin olun. Bazı değerler kullandığınız kimlik doğrulama yöntemine göre farklılık gösterecektir.

|Parametre   |Hizmet sorumlusu   |Ana kullanıcı  |
|-------------------|---|---|
|[İstemci Kimliği](#client-id) |![Şunun için geçerlidir:](../../media/yes.png) |![Şunun için geçerlidir:](../../media/yes.png) |
|[Çalışma Alanı Kimliği](#workspace-id)     |![Şunun için geçerlidir:](../../media/yes.png) |![Şunun için geçerlidir:](../../media/yes.png) |
|[Rapor Kimliği](#report-id)           |![Şunun için geçerlidir:](../../media/yes.png) |![Şunun için geçerlidir:](../../media/yes.png) |
|[Gizli anahtar](#client-secret) |![Şunun için geçerlidir:](../../media/yes.png) |![Geçerli değildir.](../../media/no.png) |
|[Kiracı Kimliği](#tenant-id)                 |![Şunun için geçerlidir:](../../media/yes.png) |![Geçerli değildir.](../../media/no.png) |
|[Power BI kullanıcı adı](#power-bi-username-and-password)   |![Geçerli değildir.](../../media/no.png) |![Şunun için geçerlidir:](../../media/yes.png) |
|[Power BI parolası](#power-bi-username-and-password)   |![Geçerli değildir.](../../media/no.png) |![Şunun için geçerlidir:](../../media/yes.png) |

### <a name="client-id"></a>İstemci Kimliği

>[!TIP]
>**Uygulama hedefi:** ![Şunun için geçerlidir:](../../media/yes.png)Hizmet sorumlusu ![Şunun için geçerlidir:](../../media/yes.png)Ana kullanıcı

İstemci kimliği GUID değerini (*uygulama kimliği* olarak da bilinir) almak için şu adımları izleyin:

1. [Microsoft Azure](https://ms.portal.azure.com/#allservices)’da oturum açın.

2. **Uygulama kayıtlarını** arayın ve **Uygulama kayıtları** bağlantısını seçin.

3. Power BI içeriğinizi eklemek için kullandığınız Azure AD uygulamasını seçin.

4. **Genel bakış** bölümünde **Uygulama (istemci) kimliği** GUID değerini kopyalayın.

### <a name="workspace-id"></a>Çalışma Alanı Kimliği

>[!TIP]
>**Uygulama hedefi:** ![Şunun için geçerlidir:](../../media/yes.png)Hizmet sorumlusu ![Şunun için geçerlidir:](../../media/yes.png)Ana kullanıcı

Çalışma alanı kimliği GUID değerini almak için şu adımları izleyin:

1. Power BI hizmetinde oturum açın.

2. Eklemek istediğiniz raporu açın.

3. URL'deki GUID değerini kopyalayın. GUID değeri, **/groups/** ile **/reports/** arasındaki sayıdır.

    :::image type="content" source="media/embed-sample-for-customers/workspace-id.png" alt-text="Power BI hizmeti URL'sindeki çalışma alanı kimliği GUID değerini gösteren ekran görüntüsü":::

### <a name="report-id"></a>Rapor Kimliği

>[!TIP]
>**Uygulama hedefi:** ![Şunun için geçerlidir:](../../media/yes.png)Hizmet sorumlusu ![Şunun için geçerlidir:](../../media/yes.png)Ana kullanıcı

1. Power BI hizmetinde oturum açın.

2. Eklemek istediğiniz raporu açın.

3. URL'deki GUID değerini kopyalayın. GUID değeri, **/reports/** ile **/ReportSection/** arasındaki sayıdır.

    :::image type="content" source="media/embed-sample-for-customers/report-id.png" alt-text="Power BI hizmeti URL'sindeki rapor kimliği GUID değerini gösteren ekran görüntüsü":::

### <a name="client-secret"></a>Gizli anahtar

>[!TIP]
>**Uygulama hedefi:** ![Şunun için geçerlidir:](../../media/yes.png)Hizmet sorumlusu ![Şunun için geçerli değildir:](../../media/no.png)Ana kullanıcı

İstemci gizli dizisini almak için şu adımları izleyin:

1. [Microsoft Azure](https://ms.portal.azure.com/#allservices)’da oturum açın.

2. **Uygulama kayıtlarını** arayın ve **Uygulama kayıtları** bağlantısını seçin.

3. Power BI içeriğinizi eklemek için kullandığınız Azure AD uygulamasını seçin.

4. **Yönet**’in altında **Sertifikalar ve gizli diziler**’i seçin.

5. **İstemci gizli dizileri** bölümünde **Yeni istemci gizli dizisi**'ni seçin.

6. Açılan **İstemci gizli dizisi ekle** penceresinde uygulama gizli dizisi için bir açıklama girin, uygulama gizli dizisinin süre sonunu belirtin ve **Ekle**'yi seçin.

7. **İstemci gizli dizileri** bölümünde yeni oluşturulan uygulama gizli dizisinin **Değer** sütunundaki dizeyi kopyalayın. İstemci gizli dizisi değeri, *istemci kimliğidir*.

### <a name="tenant-id"></a>Kiracı Kimliği

>[!TIP]
>**Uygulama hedefi:** ![Şunun için geçerlidir:](../../media/yes.png)Hizmet sorumlusu ![Şunun için geçerli değildir:](../../media/no.png)Ana kullanıcı

Kiracı kimliği GUID değerini almak için şu adımları izleyin:

1. [Microsoft Azure](https://ms.portal.azure.com/#allservices)’da oturum açın.

2. **Uygulama kayıtlarını** arayın ve **Uygulama kayıtları** bağlantısını seçin.

3. Power BI içeriğinizi eklemek için kullandığınız Azure AD uygulamasını seçin.

4. **Genel bakış** bölümünde **Dizin (kiracı) kimliği** GUID değerini kopyalayın.

### <a name="power-bi-username-and-password"></a>Power BI kullanıcı adı ve parolası

>[!TIP]
>**Uygulama hedefi:** ![Şunun için geçerli değildir:](../../media/no.png)Hizmet sorumlusu ![Şunun için geçerlidir:](../../media/yes.png)Ana kullanıcı

**Ana kullanıcı** olarak seçtiğiniz Power BI kullanıcısının *kullanıcı adı* ve *parola* değerlerini alın. Bu, Power BI hizmetinde çalışma alanı oluşturmak ve rapor yüklemek için kullandığınız kullanıcı hesabıdır.

## <a name="step-6---service-principal-api-access"></a>6\. Adım: Hizmet sorumlusu API erişimi

>[!TIP]
>**Uygulama hedefi:** ![Şunun için geçerlidir:](../../media/yes.png)Hizmet sorumlusu ![Şunun için geçerli değildir:](../../media/no.png)Ana kullanıcı
>
>Bu adım yalnızca *hizmet sorumlusu* kimlik doğrulama yöntemini kullanıyorsanız geçerlidir. *Ana kullanıcı* yöntemini kullanıyorsanız bu adımı atlayıp [7. Adım: Çalışma alanı erişimini etkinleştirin](#step-7---enable-workspace-access) ile devam edin.

Bir Azure AD uygulamasının Power BI içeriğine ve API’lerine erişebilmesi için, bir Power BI yöneticisinin Power BI yönetici portalında hizmet sorumlusu erişimini etkinleştirmesi gerekir. Kiracınızın yöneticisi siz değilseniz yöneticiden *Kiracı ayarlarını* sizin için etkinleştirmesini isteyin.
        
1. *Power BI hizmetinde* **Ayarlar** > **Ayarlar** > **Yönetici portalı**'nı seçin.
        
    :::image type="content" source="media/embed-sample-for-customers/admin-settings.png" alt-text="Power BI hizmetinin Ayarlar menüsündeki Yönetici ayarları menü seçeneğini gösteren ekran görüntüsü":::
        
2. **Kiracı ayarları**'nı seçtikten sonra açılan sayfada **Geliştirici ayarları** bölümüne inin.
        
3. **Hizmet sorumlularının Power BI API'leri kullanmasına izin ver** seçeneğini genişletip etkinleştirin.
        
    :::image type="content" source="media/embed-sample-for-customers/developer-settings.png" alt-text="Power BI hizmetinde Kiracı ayarları menü seçeneğinin altındaki Geliştirici ayarları seçeneğini etkinleştirmeyi gösteren ekran görüntüsü":::
        
>[!NOTE]
>*Hizmet sorumlusu* kullanıyorsanız bir *güvenlik grubu* kullanarak erişimini kiracı ayarlarıyla sınırlandırmanız önerilir. Bu özellik hakkında daha fazla bilgi edinmek için [hizmet sorumlusu](embed-service-principal.md) makalesinin şu bölümlerine bakın:
> * [Azure AD güvenlik grubu oluşturma](embed-service-principal.md#step-2---create-an-azure-ad-security-group)
>* [Power BI hizmeti yönetici ayarlarını etkinleştirme](embed-service-principal.md#step-3---enable-the-power-bi-service-admin-settings)

## <a name="step-7---enable-workspace-access"></a>7\. Adım: Çalışma alanı erişimini etkinleştirin

Power BI hizmetindeki raporlar, panolar ve veri kümeleri gibi Azure AD uygulama erişim yapıtlarınızı etkinleştirmek için *hizmet sorumlusunu* veya *ana kullanıcıyı* çalışma alanınıza *üye* veya *yönetici* olarak ekleyin.

1. Power BI hizmetinde oturum açın.

2. Erişimini etkinleştirmek istediğiniz çalışma alanına gidin ve **Daha fazla** menüsünden **Çalışma alanı erişimini** seçin.

    :::image type="content" source="media/embed-service-principal/workspace-access.png" alt-text="Power BI çalışma alanının Daha fazla menüsündeki Çalışma alanı erişimi düğmesini gösteren ekran görüntüsü.":::

3. **Erişim** bölmesinde kullandığınız kimlik doğrulama yöntemine göre *hizmet sorumlusunu* veya *ana kullanıcıyı* **E-posta adresini girin** metin kutusuna yapıştırın.

    >[!NOTE]
    >*Hizmet sorumlusu* kullanıyorsanız Azure AD uygulamanıza verdiğiniz adı belirtmeniz gerekir.

5. **Ekle**’yi seçin.

## <a name="step-8---embed-your-content"></a>8\. Adım: İçeriğinizi ekleyin

Power BI Embedded örnek uygulaması, *müşterileriniz için ekleme* yöntemiyle bir Power BI uygulaması oluşturmanızı sağlar.

Örnek *Müşterileriniz için ekleme* uygulamasını değiştirerek Power BI raporunuzu eklemek için aşağıdaki adımları izleyin.  

1. [Power BI developer samples](https://github.com/microsoft/PowerBI-Developer-Samples) klasörünü açın.

2. **Kod**'u ve ardından **ZIP'i indir**'i seçin.

    :::image type="content" source="media/embed-sample-for-customers/developer-samples.png" alt-text="Power BI Developer Samples GitHub klasöründeki ZIP'i indir seçeneğini gösteren ekran görüntüsü":::

3. İndirdiğiniz ZIP dosyasını ayıklayıp **PowerBI-Developer-Samples-master** klasörüne gidin.

4. Uygulamanızda kullanmak istediğiniz dile bağlı olarak şu klasörlerden birini açın:

* .NET Core
* .NET Framework
* Java
* Node JS
* Python
    >[!NOTE]
    >Örnek *müşterileriniz için ekleme* uygulamaları yalnızca yukarıdaki dilleri destekler. *React TS* örnek uygulaması yalnızca *[kuruluşunuz için ekleme](embed-sample-for-your-organization.md)* çözümünü destekler.

5. **Embed for your customers** klasörünü açın.

# <a name="net-core"></a>[.NET Core](#tab/net-core)

6. Aşağıdaki yöntemlerden birini kullanarak *örnek müşterileriniz için ekleme uygulamasını* açın:

    * [Visual Studio](https://visualstudio.microsoft.com/) kullanıyorsanız **AppOwnsData.sln** dosyasını açın.

    * [Visual Studio Code](https://code.visualstudio.com/) kullanıyorsanız **App Owns Data** klasörünü açın.

7. **appsettings.json** dosyasını açın.

8. Seçtiğiniz kimlik doğrulama yönteminize göre aşağıdaki parametre değerlerini girin:

    |Parametre            |Hizmet sorumlusu  |Ana kullanıcı  |
    |---------------------|---------|---------|
    |`AuthenticationMode` |ServicePrincipal         |MasterUser         |
    |`ClientId`           |Azure AD uygulamanızın [istemci kimliği](#client-id)         |Azure AD uygulamanızın [istemci kimliği](#client-id)         |
    |`TenantId`           |Azure AD [kiracı kimliğiniz](#tenant-id)         |Yok         |
    |`PbiUsername`        |Yok         |*Ana kullanıcının* kullanıcı adı; bkz. [Power BI kullanıcı adı ve parolası](#power-bi-username-and-password)         |
    |`PbiPassword`        |Yok         |*Ana kullanıcının* parolası; bkz. [Power BI kullanıcı adı ve parolası](#power-bi-username-and-password)         |
    |`ClientSecret`       |Azure AD [istemci gizli diziniz](#client-secret)         |Yok         |
    |`WorkspaceId`        |Eklenmiş raporunuzun bulunduğu çalışma alanının kimliği; bkz. [Çalışma alanı kimliği](#workspace-id)          |Eklenmiş raporunuzun bulunduğu çalışma alanının kimliği; bkz. [Çalışma alanı kimliği](#workspace-id)         |
    |`ReportId`           |Eklediğiniz raporun kimliği; bkz. [Rapor kimliği](#report-id)            |Eklediğiniz raporun kimliği; bkz. [Rapor kimliği](#report-id)         |

9. Uygun seçeneği belirleyerek projeyi çalıştırın:

    * **Visual Studio** kullanıyorsanız **IIS Express** (yürüt) öğesini seçin.

    * **Visual Studio Code** kullanıyorsanız **Çalıştır > Hata Ayıklamayı Başlat**'ı seçin.

# <a name="net-framework"></a>[.NET Framework](#tab/net-framework)

6. [Visual Studio](https://visualstudio.microsoft.com/)'yu kullanarak **AppOwnsData.sln** dosyasını açın.

7. **Web.config** dosyasını açın.

8. Seçtiğiniz kimlik doğrulama yönteminize göre aşağıdaki parametre değerlerini girin:

    |Parametre            |Hizmet sorumlusu  |Ana kullanıcı  |
    |---------------------|---------|---------|
    |`authenticationType` |ServicePrincipal         |MasterUser         |
    |`applicationId`           |Azure AD uygulamanızın [istemci kimliği](#client-id)         |Azure AD uygulamanızın [istemci kimliği](#client-id)         |
    |`workspaceId`        |Eklenmiş raporunuzun bulunduğu çalışma alanının kimliği; bkz. [Çalışma alanı kimliği](#workspace-id)          |Eklenmiş raporunuzun bulunduğu çalışma alanının kimliği; bkz. [Çalışma alanı kimliği](#workspace-id)         |
    |`reportId`           |Eklediğiniz raporun kimliği; bkz. [Rapor kimliği](#report-id)            |Eklediğiniz raporun kimliği; bkz. [Rapor kimliği](#report-id)         |
    |`pbiUsername`        |Yok         |*Ana kullanıcının* kullanıcı adı; bkz. [Power BI kullanıcı adı ve parolası](#power-bi-username-and-password)         |
    |`pbiPassword`        |Yok         |*Ana kullanıcının* parolası; bkz. [Power BI kullanıcı adı ve parolası](#power-bi-username-and-password)         |
    |`applicationSecret`       |Azure AD [istemci gizli diziniz](#client-secret)         |Yok         |
    |`tenant`           |Azure AD [kiracı kimliğiniz](#tenant-id)         |Yok         |

9. **IIS Express** (yürüt) öğesini seçerek projeyi çalıştırın.

>[!NOTE]
>Örnek uygulamayı çalıştırdığınızda eklenen raporu görmüyorsanız aşağıdaki adımları izleyerek Power BI paketlerini yenileyin:
>1. Proje adına (AppOwnesData) sağ tıklayıp **NuGet paketlerini yönet**'i seçin.
>2. **Power BI JavaScript** paketini arayıp bulun ve yeniden yükleyin.
>
>Daha fazla bilgi için bkz. [Paketleri yeniden yükleme ve güncelleştirme](/nuget/consume-packages/reinstalling-and-updating-packages).

# <a name="java"></a>[Java](#tab/java)

6. **Eclipse**'i açıp aşağıdaki yönergeleri izleyin.

    >[!NOTE]
    >Java *örnek müşterileriniz için ekleme uygulaması* yönergeleri, [Eclipse IDE for Java EE Developers](https://www.eclipse.org/downloads/packages/) (Enterprise Edition) sürümüne aittir. Farklı bir uygulama kullanıyorsanız kendi kendinize ayarlamanız gerekir.

7. Eclipse'e Tomcat sunucusunu ekleme:

    a. **Pencere** > **Görünümü Göster** > **Sunucular**'ı seçin.

    b. Sunucular sekmesinde **Kullanılabilir sunucu yok. Yeni sunucu oluşturmak için bu bağlantıya tıklayın**'ı seçin.

    c. **Yeni sunucu tanımla** penceresinde **Apache**'yi genişletip makinenizde çalıştırdığınız Tomcat sunucusunu seçin. Örneğin, *Tomcat v9.0 Sunucusu*.

    d. **İleri**’yi seçin.

    e. **Tomcat Sunucusu** penceresinde **Göz at**'ı seçip Tomcat sunucusunun bulunduğu klasöre gidin.

    f. **Tomcat Sunucusu** penceresinde **Yüklü JRE'ler** öğesini seçin.

    örneğin: **Yüklü JRE'ler** penceresinde kullanılabilir durumdaki *jre* girişini ve ardından **Uygula ve Kapat**'ı seçin.

    h. **Tomcat Sunucusu** penceresinde **Son**'u seçin. *Sunucular* sekmesinde Tomcat sunucusunu görebiliyor olacaksınız.

8. Projeyi Eclipse ile açın:

    >[!IMPORTANT]
    >Yolunuz çok uzun olursa Eclipse sorunlarla karşılaşabilir. Bu sorundan kaçınmak için örnek uygulama klasörünün makinenizin klasör yapısının çok derinlerinde olmadığından emin olun.

    a. **Dosya**'yı ve ardından **Dosya Sisteminden Proje Aç**'ı seçin.

    b. **Dosya Sisteminden veya Arşivden Proje Aktar** penceresinde **Dizin**'i seçip **AppOwnsData** klasörünü açın.

    c. **Son**'u seçin.

9. Eclipse'e projeyi ekleme:

    a. **Paket Gezgini** bölmesinde **AppOwnsData**'ya sağ tıklayıp **Özellikler**'i seçin.

    b. **AppOwnesData Özellikleri** penceresinde **Hedeflenen Çalışma Zamanları**'nı ve ardından **Apache Tomcat**'i seçin. Bu seçim, kullanmakta olduğunuz *Apache Tomcat* sürümünü içerecektir; örneğin, *Apache Tomact v9.0*.

    c. **Uygula ve Kapat**'ı seçin.

10. Gereken parametreleri doldurma

    a. **Paket Gezgini**'nde **AppOwnsData** projesini genişletin.

    b. **Java Kaynakları**'nı genişletin.

    c. **src** öğesini genişletin.

    d. **com.embedsample.appoensdata.config** öğesini genişletin.

    e. **Config.java** dosyasını açın.

    f. Seçtiğiniz kimlik doğrulama yönteminize göre aşağıdaki parametre değerlerini girin:

    |Parametre            |Hizmet sorumlusu  |Ana kullanıcı  |
    |---------------------|---------|---------|
    |`authenticationType` |ServicePrincipal         |MasterUser         |
    |`workspaceId`        |Eklenmiş raporunuzun bulunduğu çalışma alanının kimliği; bkz. [Çalışma alanı kimliği](#workspace-id)          |Eklenmiş raporunuzun bulunduğu çalışma alanının kimliği; bkz. [Çalışma alanı kimliği](#workspace-id)         |
    |`reportId`           |Eklediğiniz raporun kimliği; bkz. [Rapor kimliği](#report-id)            |Eklediğiniz raporun kimliği; bkz. [Rapor kimliği](#report-id)         | 
    |`clientId`           |Azure AD uygulamanızın [istemci kimliği](#client-id)         |Azure AD uygulamanızın [istemci kimliği](#client-id)         |
    |`pbiUsername`        |Yok         |*Ana kullanıcının* kullanıcı adı; bkz. [Power BI kullanıcı adı ve parolası](#power-bi-username-and-password)         |
    |`pbiPassword`        |Yok         |*Ana kullanıcının* parolası; bkz. [Power BI kullanıcı adı ve parolası](#power-bi-username-and-password)         |
    |`tenantId`           |Azure AD [kiracı kimliğiniz](#tenant-id)         |Yok         |
    |`appSecret`       |Azure AD [istemci gizli diziniz](#client-secret)         |Yok         |

11. Projeyi çalıştırma

    a. **Paket Gezgini**'nde **AppOwnesData** girişine sağ tıklayın.

    b. **Farklı Çalıştır**  > **Sunucuda Çalıştır**'ı seçin.

    c. **Sunucuda Çalıştır** penceresinde **Var olan bir sunucuyu seç**'i ve ardından *Tomcat* sunucusunu seçin.

    d. **Son**'u seçin.

# <a name="node-js"></a>[Node JS](#tab/node-js)

6. Tercih ettiğiniz IDE ortamını kullanarak **App Owns Data** klasörünü açın. Aşağıdakilerden birini kullanmanız önerilir:

    * [Visual Studio](https://visualstudio.microsoft.com/)

    * [Visual Studio Code](https://code.visualstudio.com/)

7. Bir terminal açın ve şu komutu yürüterek gerekli bağımlılıkları yükleyin: `npm install`.

8. **Config** klasörünü genişletip **config.json** dosyasını açın.

9. Seçtiğiniz kimlik doğrulama yönteminize göre aşağıdaki parametre değerlerini girin:

    |Parametre            |Hizmet sorumlusu  |Ana kullanıcı  |
    |---------------------|---------|---------|
    |`authenticationMode` |ServicePrincipal         |MasterUser         |
    |`clientId`           |Azure AD uygulamanızın [istemci kimliği](#client-id)         |Azure AD uygulamanızın [istemci kimliği](#client-id)         |
    |`workspaceId`        |Eklenmiş raporunuzun bulunduğu çalışma alanının kimliği; bkz. [Çalışma alanı kimliği](#workspace-id)          |Eklenmiş raporunuzun bulunduğu çalışma alanının kimliği; bkz. [Çalışma alanı kimliği](#workspace-id)         |
    |`reportId`           |Eklediğiniz raporun kimliği; bkz. [Rapor kimliği](#report-id)            |Eklediğiniz raporun kimliği; bkz. [Rapor kimliği](#report-id)         |
    |`pbiUsername`        |Yok         |*Ana kullanıcının* kullanıcı adı; bkz. [Power BI kullanıcı adı ve parolası](#power-bi-username-and-password)         |
    |`pbiPassword`        |Yok         |*Ana kullanıcının* parolası; bkz. [Power BI kullanıcı adı ve parolası](#power-bi-username-and-password)         |
    |`clientSecret`       |Azure AD [istemci gizli diziniz](#client-secret)         |Yok         |
    |`tenantId`           |Azure AD [kiracı kimliğiniz](#tenant-id)         |Yok         |

10. Aşağıdaki adımları izleyerek projeyi çalıştırın:

    a. IDE terminalinde `npm start` komutunu yürütün.

    b. Tarayıcınızda yeni bir sekme açıp `http://localhost:5300` adresine gidin.

# <a name="python"></a>[Python](#tab/python)

6. **PowerShell**'i veya **komut istemini** açın.

7. **Python** > **Embed for your customers** klasöründe olduğunuzdan ve **requirements.txt** dosyasının klasörün içinde olduğundan emin olduktan sonra `pip3 install -r requirements.txt` komutunu çalıştırın.

8. Tercih ettiğiniz IDE ortamını kullanarak **App Owns Data** klasörünü açın. Aşağıdakilerden birini kullanmanız önerilir:

    * [Visual Studio](https://visualstudio.microsoft.com/)

    * [Visual Studio Code](https://code.visualstudio.com/)

9. **config.py** dosyasını açın.

10. Seçtiğiniz kimlik doğrulama yönteminize göre aşağıdaki parametre değerlerini girin:

    |Parametre            |Hizmet sorumlusu  |Ana kullanıcı  |
    |---------------------|---------|---------|
    |`AUTHENTICATION_MODE` |ServicePrincipal         |MasterUser         |
    |`WORKSPACE_ID`        |Eklenmiş raporunuzun bulunduğu çalışma alanının kimliği; bkz. [Çalışma alanı kimliği](#workspace-id)          |Eklenmiş raporunuzun bulunduğu çalışma alanının kimliği; bkz. [Çalışma alanı kimliği](#workspace-id)         |
    |`REPORT_ID`           |Eklediğiniz raporun kimliği; bkz. [Rapor kimliği](#report-id)            |Eklediğiniz raporun kimliği; bkz. [Rapor kimliği](#report-id)         |
    |`TENANT_ID`           |Azure AD [kiracı kimliğiniz](#tenant-id)         |Yok         |
    |`CLIENT_ID`           |Azure AD uygulamanızın [istemci kimliği](#client-id)         |Azure AD uygulamanızın [istemci kimliği](#client-id)         |
    |`CLIENT_SECRET`       |Azure AD [istemci gizli diziniz](#client-secret)         |Yok         |
    |`POWER_BI_USER`        |Yok         |*Ana kullanıcının* kullanıcı adı; bkz. [Power BI kullanıcı adı ve parolası](#power-bi-username-and-password)         |
    |`POWER_BI_PASS`        |Yok         |*Ana kullanıcının* parolası; bkz. [Power BI kullanıcı adı ve parolası](#power-bi-username-and-password)         |

11. Dosyayı kaydedin.

12. Aşağıdaki adımları izleyerek projeyi çalıştırın:

    a. **PowerShell** veya **komut istemi** ile **Python** > **Embed for your customers** > **AppOwnesData** klasörüne gidip `flask run` komutunu yürütün.

    b. Tarayıcınızda yeni bir sekme açıp `http://localhost:5300` adresine gidin.

---

## <a name="developing-your-application"></a>Uygulamanızı geliştirme

Örnek *müşterileriniz için ekleme* uygulamasını yapılandırdıktan sonra kendi uygulamanızı geliştirmeye başlayabilirsiniz.

Hazır olduğunuzda [üretime taşıma](move-to-production.md) gereksinimlerini gözden geçirin. Ayrıca bir [kapasiteye](embedded-capacity.md) ihtiyacınız olacağından gereksinimlerinize en uygun SKU'yu belirleme amacıyla [kapasite planlaması](embedded-capacity-planning.md) makalesini de incelemeniz gerekir.


## <a name="next-steps"></a>Sonraki adımlar

> [!div class="nextstepaction"]
>[Üretime taşıma](move-to-production.md)

>[!div class="nextstepaction"]
>[Kuruluşunuz için ekleme](embed-sample-for-your-organization.md)

> [!div class="nextstepaction"]
>[Müşterileriniz için sayfalandırılmış raporlar ekleme](embed-paginated-reports-customers.md)

> [!div class="nextstepaction"]
>[Kuruluşunuz için sayfalandırılmış raporlar ekleme](embed-paginated-reports-organization.md)

>[!div class="nextstepaction"]
>[Power BI Topluluğu'na sorun](https://community.powerbi.com/)
