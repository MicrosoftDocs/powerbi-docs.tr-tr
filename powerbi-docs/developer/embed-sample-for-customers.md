---
title: Müşterileriniz için Power BI içeriğini bir uygulamaya ekleme
description: Müşterileriniz için Power BI API'leri kullanarak bir raporu, panoyu veya kutucuğu web uygulamasıyla tümleştirmeyi veya web uygulamasına eklemeyi öğrenin.
author: markingmyname
ms.author: maghan
ms.date: 05/25/2018
ms.topic: tutorial
ms.service: powerbi
ms.component: powerbi-developer
ms.custom: mvc
manager: kfile
ms.openlocfilehash: ae683dfbeb7b3848575ab766c33b695eb823d497
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34721053"
---
# <a name="tutorial-embed-a-power-bi-report-dashboard-or-tile-into-an-application-for-your-customers"></a>Öğretici: Müşterileriniz için bir Power BI raporunu, panosunu veya kutucuğunu bir uygulamaya ekleme
**Azure’da Power BI Embedded** ile raporları, panoları veya kutucukları **verilerin sahibi uygulamadır** örneğini kullanarak bir uygulamaya ekleyebilirsiniz. **Verilerin sahibi uygulamadır** örneği, eklenmiş analiz platformu olarak Power BI’ı kullanan bir uygulamanız olması durumunda kullanılır. Bu genellikle bir **ISV geliştiricisi** senaryosudur. Bir **ISV geliştiricisi** olarak, tamamen tümleşik ve etkileşimli bir uygulamada raporlar, panolar veya kutucuklar görüntüleyen Power BI içeriği oluşturabilirsiniz. Üstelik uygulama kullanıcılarının Power BI lisansı olması veya Power BI’dan faydalandıklarını bilmeleri bile gerekmez. Bu öğretici, **verilerin sahibi uygulamadır** yapısını kullanan müşterileriniz için **Azure’da Power BI Embedded** kullanırken **Power BI** JavaScript API’si ile birlikte **Power BI** .NET SDK’sı kullanarak bir raporu bir uygulama ile tümleştirme işlemini göstermektedir.

Bu öğreticide aşağıdakilerin nasıl yapılacağını öğreneceksiniz:
>[!div class="checklist"]
>* Azure’da bir uygulama kaydetme.
>* Bir uygulamaya Power BI raporu ekleme.

## <a name="prerequisites"></a>Önkoşullar
Başlamak için, **ana hesabınız** olacak bir **Power BI Pro** hesabı ve **Microsoft Azure** aboneliği gerekir.

* **Power BI Pro**’ya kaydolmadıysanız başlamadan önce [ücretsiz deneme için kaydolun](https://powerbi.microsoft.com/en-us/pricing/).
* Azure aboneliğiniz yoksa başlamadan önce [ücretsiz bir hesap](https://azure.microsoft.com/free/?WT.mc_id=A261C142F) oluşturun.
* [Azure Active Directory kiracınız](create-an-azure-active-directory-tenant.md) ayarlanmış olmalıdır.
* [Visual Studio](https://www.visualstudio.com/) yüklü olmalıdır (sürüm 2013 veya üzeri).

## <a name="setup-your-embedded-analytics-development-environment"></a>Eklediğiniz analiz geliştirme ortamını ayarlama

Raporları, panoları veya kutucukları uygulamanıza eklemeye başlamadan önce ortamınızın ekleme işlevlerine izin verecek şekilde ayarlanmış olduğundan emin olmanız gerekir. Kurulumun bir parçası olarak aşağıdaki işlemleri yapmanız gerekir.

Hızlıca kullanmaya başlamak ve bir ortam oluşturma ve rapor ekleme adımlarını gösteren örnek bir uygulama indirmek için [Katılım deneyimi aracını](https://aka.ms/embedsetup/AppOwnsData) inceleyebilirsiniz.

Ancak, ortamı el ile ayarlamayı seçerseniz aşağıdaki adımlara devam edebilirsiniz.
### <a name="register-an-application-in-azure-active-directory-azure-ad"></a>Azure Active Directory'de (Azure AD) bir uygulamayı kaydetme

Power BI REST API'lerine erişmesini sağlamak için uygulamanızı Azure Active Directory'ye kaydetmeniz gerekir. Kayıt işlemi sayesinde uygulamanız için bir kimlik oluşturabilir ve Power BI REST kaynaklarıyla ilgili izinleri belirleyebilirsiniz.

1. [Microsoft Power BI API Koşulları](https://powerbi.microsoft.com/api-terms)'nı kabul edin.

2. [Azure portalında](https://portal.azure.com) oturum açın.
 
    ![Azure Portalı Ana Sayfası](media/embed-sample-for-customers/embed-sample-for-customers-002.png)

3. Sol taraftaki gezinti bölmesinde **Tüm Hizmetler**'i, **Uygulama Kayıtları**'nı ve sonra **Yeni uygulama kaydı**'nı seçin.
   
    ![Uygulama kaydı araması](media/embed-sample-for-customers/embed-sample-for-customers-003.png)</br>
    ![Yeni Uygulama kaydı](media/embed-sample-for-customers/embed-sample-for-customers-004.png)

4. Talimatları izleyerek yeni bir uygulama oluşturun. Verilerin sahibi uygulamadır yapısı için **Yerel** uygulama türünü kullanmanız gerekir. Ayrıca, **Azure AD**'nin belirteç yanıtlarını döndürmek için kullanacağı bir **Yeniden Yönlendirme URI'si** belirtmeniz gerekir. Uygulamanıza özgü bir değer girin (örneğin: http://localhost:13526/redirect).

    ![Uygulama Oluşturma](media/embed-sample-for-customers/embed-sample-for-customers-005.png)

### <a name="apply-permissions-to-your-application-within-azure-active-directory"></a>Azure Active Directory'de uygulamanıza izinler uygulama

Uygulamanız için uygulama kayıt sayfasında belirtilenlere ek izinler etkinleştirmeniz gerekir. Ekleme için kullanılan ve bir genel yönetici hesabı olması gereken *ana* hesapla oturum açmanız gerekir.

### <a name="use-the-azure-active-directory-portal"></a>Azure Active Directory portalını kullanma

1. Azure portalındaki [Uygulama kayıtları](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ApplicationsListBlade) sayfasına gidip ekleme için kullandığınız uygulamayı seçin.
   
    ![Uygulama Seçme](media/embed-sample-for-customers/embed-sample-for-customers-006.png)

2. **Ayarlar**’ı ve sonra **API Erişimi** altında **Gerekli izinler**'i seçin.
   
    ![Gerekli İzinler](media/embed-sample-for-customers/embed-sample-for-customers-008.png)

3. **Windows Azure Active Directory**'yi seçin ve **Oturum açmış kullanıcı olarak dizine erişin** seçeneğinin belirlenmiş olduğundan emin olun. **Kaydet**'i seçin.
   
    ![Windows Azure AD İzinleri](media/embed-sample-for-customers/embed-sample-for-customers-011.png)

4. **Ekle**'yi seçin.

    ![İzin Ekleme](media/embed-sample-for-customers/embed-sample-for-customers-012.png)

5. **Bir API seçin** öğesini seçin.

    ![API Erişimi Ekleme](media/embed-sample-for-customers/embed-sample-for-customers-013.png)

6. **Power BI Hizmeti**’ni, ardından **Seç**’i seçin.

    ![PBI Hizmetleri Seçme](media/embed-sample-for-customers/embed-sample-for-customers-014.png)

7. **Temsilci İzinleri** bölümündeki tüm izinleri seçin. Seçimlerin kaydedilmesi için teker teker seçmeniz gerekir. Tümünü seçtikten sonra **Kaydet**'i seçin.
   
    ![Temsilci izinleri seçme](media/embed-sample-for-customers/embed-sample-for-customers-015.png)

8. **Gerekli izinler** bölümünde **İzin Ver**'i seçin.
   
    **İzin Ver** eylemi *ana hesaptan* Azure AD tarafından onay istenmesini önlemek için gereklidir. Bu eylemi gerçekleştiren hesap Genel Yöneticiyse kuruluşunuzdaki tüm kullanıcılara bu uygulama için izin vermiş olursunuz. Bu eylemi gerçekleştiren hesap *ana hesap* ise ve Genel Yönetici değilse bu uygulama için yalnızca *ana hesaba* izin vermiş olursunuz.
   
    ![Gerekli izinler iletişim kutusundaki izin ver seçeneği](media/embed-sample-for-customers/embed-sample-for-customers-016.png)

## <a name="setup-your-power-bi-environment"></a>Power BI ortamınızı ayarlama

### <a name="create-an-app-workspace"></a>Uygulama çalışma alanı oluştur

Müşterileriniz için rapor, pano veya kutucuklar ekliyorsanız, içeriğinizi bir uygulama çalışma alanına yerleştirmeniz gerekir. *Ana* hesabın, ilgili uygulama çalışma alanının yöneticisi olması gerekir.

1. İşe çalışma alanını oluşturarak başlayın. **Çalışma alanları** > **Uygulama çalışma alanı oluşturma**'yı seçin. Burası, uygulamanızın erişmesi gereken içeriklerin yerleştirileceği yerdir.

    ![Çalışma Alanı Oluşturma](media/embed-sample-for-customers/embed-sample-for-customers-020.png)

2. Çalışma alanına bir ad verin. Karşılık gelen **Çalışma Alanı Kimliği** kullanılamıyorsa düzenleyerek benzersiz bir kimlik belirleyin. Bu kimlik uygulamanın da adı olacaktır.

    ![Çalışma Alanını Adlandırma](media/embed-sample-for-customers/embed-sample-for-customers-021.png)

3. Değiştirebileceğiniz birkaç ayar vardır. **Ortak** seçeneğini belirlerseniz çalışma alanınızdakileri kuruluşunuzdaki herkes görebilir. **Özel**'i seçerseniz çalışma alanının içeriğini yalnızca üyeler görebilir.

    ![Özel/Genel](media/embed-sample-for-customers/embed-sample-for-customers-022.png)

    Grubu oluşturduktan sonra Ortak/Özel ayarını değiştiremezsiniz.

4. Üyelere **düzenleme** veya **yalnızca görüntüleme** erişimi verebilirsiniz.

    ![Üye Ekleme](media/embed-sample-for-customers/embed-sample-for-customers-023.png)

5. Çalışma alanı erişimi vermek istediğiniz kişilerin e-posta adreslerini girip **Ekle**'yi seçin. Grup takma adlarını ekleyemezsiniz, yalnızca kişilere izin verilir.

6. Eklediğiniz kişilerin üye mi yoksa yönetici mi olacağına karar verin. Yöneticiler çalışma alanını düzenleyebilir, başka üyeler ekleyebilir. Yalnızca görüntüleme erişimine sahip olanlar hariç üyeler çalışma alanındaki içeriği düzenleyebilir. Hem yöneticiler hem de üyeler uygulamayı yayımlayabilir.

Artık yeni çalışma alanını görüntüleyebilirsiniz. Power BI çalışma alanını oluşturur ve açar. Üyesi olduğunuz çalışma alanlarının listesinde görünür. Yönetici olduğunuz için üç nokta (…) simgesini seçerek geri gidebilir, değişiklik yapabilir, yeni üye ekleyebilir veya üye izinlerini değiştirebilirsiniz.

   ![Yeni çalışma alanı](media/embed-sample-for-customers/embed-sample-for-customers-025.png)

### <a name="create-and-publish-your-reports"></a>Raporlarınızı oluşturma ve yayımlama

Power BI Desktop'ı kullanarak raporlarınızı ve veri kümelerinizi oluşturabilir, ardından bu raporları uygulama çalışma alanında yayımlayabilirsiniz. Raporları yayımlayan son kullanıcının uygulama çalışma alanında yayımlama yapabilmesi için bir Power BI Pro lisansına sahip olması gerekir.

1. GitHub'dan örnek [Blog Tanıtımı](https://github.com/Microsoft/powerbi-desktop-samples)’nı indirin.

    ![rapor örneği](media/embed-sample-for-customers/embed-sample-for-customers-026-1.png)

2. **Power BI Desktop**’ta örnek PBIX raporunu açın

   ![PBI desktop raporu](media/embed-sample-for-customers/embed-sample-for-customers-027.png)

3. **Uygulama çalışma alanında** yayımlayın

   ![PBI desktop raporu](media/embed-sample-for-customers/embed-sample-for-customers-028.png)

    Artık raporunuzu Power BI hizmetinde çevrimiçi görüntüleyebilirsiniz

   ![PBI desktop raporu](media/embed-sample-for-customers/embed-sample-for-customers-029.png)

## <a name="embed-your-content"></a>İçeriğinizi ekleme

Uygulamanıza müşterileriniz için içerik ekleme işlemi, **Azure AD**’den ana hesabınız için bir **erişim belirteci** alınmasını gerektirir. Power BI API’sine çağrı yapmadan önce, verilerin sahibi uygulamadır örneği kullanılarak Power BI uygulamanız için [Azure AD erişim belirteci alınması](get-azuread-access-token.md#access-token-for-non-power-bi-users-app-owns-data) gerekir.

Örnek bir uygulamayı kullanarak içeriğinizi eklemeye başlamak için bu adımları izleyin.

1. Başlamak için GitHub’dan [Verilerin Sahibi Uygulamadır örneğini](https://github.com/Microsoft/PowerBI-Developer-Samples) indirin.

    ![Verilerin Sahibi Uygulamadır uygulama örneği](media/embed-sample-for-customers/embed-sample-for-customers-026.png)

2. Örnek uygulamada Web.config dosyasını açın. Uygulamayı başarıyla çalıştırmak için doldurmanız gereken 5 alan vardır. **clientID**, **groupId**, **reportId**, **pbiUsername** ve **pbiPassword**.

      ![Web Config dosyası](media/embed-sample-for-customers/embed-sample-for-customers-030.png)

    * **clientId** bilgilerini **Azure**’daki **Uygulama Kimliği** ile doldurun. **clientId**, izin istediğiniz kullanıcılara kendini tanıtmak için uygulama tarafından kullanılır. **clientId** değerini almak için aşağıdaki adımları izleyin:

    1. [Azure portalında](https://portal.azure.com) oturum açın.

        ![Azure Portalı Ana Sayfası](media/embed-sample-for-customers/embed-sample-for-customers-002.png)

    2. Sol gezinti bölmesinde **Tüm Hizmetler**'i ve **Uygulama Kayıtları**'nı seçin.

        ![Uygulama kaydı araması](media/embed-sample-for-customers/embed-sample-for-customers-003.png)
    3. **clientId** değerini almak istediğiniz uygulamayı seçin.

        ![Uygulama Seçme](media/embed-sample-for-customers/embed-sample-for-customers-006.png)

    4. GUID olarak listelenen bir **Uygulama Kimliği** görmeniz gerekir. Bu **Uygulama Kimliği**’ni uygulamanın **clientId** değeri olarak kullanın.

        ![clientId](media/embed-sample-for-customers/embed-sample-for-customers-007.png)     

    * **groupId** bilgilerini Power BI’daki **uygulama çalışma alanı GUID’si** ile doldurun.

        ![groupId](media/embed-sample-for-customers/embed-sample-for-customers-031.png)

    * **reportId** bilgilerini Power BI’daki **rapor GUID’si** ile doldurun.

        ![reportId](media/embed-sample-for-customers/embed-sample-for-customers-032.png)    

    * **pbiUsername** bilgisini ana kullanıcı Power BI hesabıyla doldurun.
    * **pbiPassword** bilgisini ana kullanıcı Power BI hesabının parolası ile doldurun.

3. Uygulamayı çalıştırın!

    İlk olarak **Visual Studio**’da **Çalıştır**’ı seçin.

    ![Uygulamayı çalıştırma](media/embed-sample-for-customers/embed-sample-for-customers-033.png)

    Ardından **Rapor Ekle**’yi seçin. Test etmeyi seçtiğiniz içeriğe (raporlar, panolar veya kutucuklar) bağlı olarak uygulamada bu seçeneği belirleyin.

    ![İçerik seçme](media/embed-sample-for-customers/embed-sample-for-customers-034.png)
 
    Artık raporu örnek uygulamada görüntüleyebilirsiniz.

    ![Uygulamayı görüntüleme](media/embed-sample-for-customers/embed-sample-for-customers-035.png)

## <a name="move-to-production"></a>Üretime geçme

Uygulamanızın geliştirme aşamasını tamamladığınıza göre şimdi adanmış kapasite ile uygulamanızın çalışma alanını destekleme işlemine geçmelisiniz. Üretime geçmek için adanmış kapasite gerekir.

### <a name="create-a-dedicated-capacity"></a>Adanmış kapasite oluşturma
Adanmış kapasite oluşturduğunuzda, müşteriniz için özel olarak ayrılmış bir kaynaktan yararlanabilirsiniz. Adanmış kapasiteye atanmamış çalışma alanları, paylaşılan kapasitede bulunur. Azure’daki [Power BI Embedded adanmış kapasite](https://docs.microsoft.com/azure/power-bi-embedded/create-capacity) çözümünü kullanarak adanmış kapasite oluşturabilirsiniz.

>[!Note]
>PRO lisansına sahip ekleme belirteçleri, geliştirmeye testlerine yöneliktir. Bu nedenle, bir Power BI ana hesabının oluşturabileceği ekleme belirteçlerinin sayısı sınırlıdır. Bir üretim ortamında ekleme yapmak için adanmış kapasite satın almanız gerekir. Adanmış kapasiteyle oluşturabileceğiniz ekleme belirteçlerinin sayısıyla ilgili bir sınır yoktur. Geçerli eklenmiş kullanımı yüzde cinsinden gösteren kullanım değerini denetlemek için [Kullanılabilir Özellikleri Al](https://msdn.microsoft.com/library/mt846473.aspx) bölümüne gidin.
>

### <a name="assign-app-workspace-to-dedicated-capacity"></a>Adanmış kapasiteye uygulama çalışma alanı atama

Adanmış kapasite oluşturulduktan sonra, uygulama çalışma alanını adanmış kapasiteye atayın. Bunu yapmak için aşağıdaki adımları uygulayın.

1. **Power BI hizmetinde**, çalışma alanlarını genişletin ve içeriğinizi eklediğiniz çalışma alanına yönelik olan üç noktayı seçin. Ardından **Çalışma alanlarını düzenle**’yi seçin.

    ![Çalışma Alanını Düzenleme](media/embed-sample-for-customers/embed-sample-for-customers-036.png)

2. **Gelişmiş**’i genişletin, ardından **Adanmış kapasite**’yi etkinleştirin, sonra da oluşturduğunuz adanmış kapasiteyi seçin. Sonra **Kaydet**'i seçin.

    ![Adanmış kapasite atama](media/embed-sample-for-customers/embed-sample-for-customers-024.png)

JavaScript API kullanan tam bir örnek için [Playground aracı](https://microsoft.github.io/PowerBI-JavaScript/demo)'nı kullanabilirsiniz. Bunu yapmak, farklı türde Power BI Embedded örnekleri ile yürütmenin hızlı bir yoludur. Ayrıca [PowerBI-JavaScript wiki](https://github.com/Microsoft/powerbi-javascript/wiki) sayfasını ziyaret ederek JavaScript API’si hakkında daha fazla bilgi alabilirsiniz.

Power BI Embedded hakkında daha fazla soru için lütfen [SSS](embedded-faq.md) sayfasını ziyaret edin.  Uygulamanızda Power Bi Embedded ile ilgili sorun yaşıyorsanız, lütfen [sorun giderme](embedded-troubleshoot.md) sayfasını ziyaret edin.

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)