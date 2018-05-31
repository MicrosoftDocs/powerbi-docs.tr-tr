---
title: Müşterileriniz için Power BI içeriğini bir uygulamaya ekleme
description: Müşterileriniz için Power BI API'leri kullanarak bir raporu, panoyu veya kutucuğu web uygulamasıyla tümleştirmeyi veya web uygulamasına eklemeyi öğrenin.
services: powerbi
author: markingmyname
ms.author: maghan
ms.date: 05/07/2018
ms.topic: tutorial
ms.service: powerbi
ms.custom: mvc
manager: kfile
ms.openlocfilehash: 2d4fdee8d3e4cca60294acd0a9167da1f048afa5
ms.sourcegitcommit: 9fa954608e78dcdb8d8a503c3c9b01c43ca728ab
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/11/2018
ms.locfileid: "34051945"
---
# <a name="tutorial-embed-a-power-bi-report-dashboard-or-tile-into-an-application-for-your-customers"></a>Öğretici: Müşterileriniz için bir Power BI raporunu, panosunu veya kutucuğunu bir uygulamaya ekleme
**Azure’da Power BI Embedded** ile raporları, panoları veya kutucukları müşterilerinizin verileri paylaşabilmesi için bir uygulamaya ekleyebilirsiniz. Bu genellikle **verilerin sahibi uygulamadır** yapısını kullanan bir **ISV geliştiricisi** senaryosudur. **Verilerin sahibi uygulamadır**, kendi müşterileriniz için Power BI içeriğini eklemek anlamına gelir. Örneğin, Power BI içeriğinin kullanıcısı **Power BI**’da oturum açmaya gerek duymadan raporları, panoları veya kutucukları görüntüleyebilir. Bu öğretici, **verilerin sahibi uygulamadır** yapısını kullanan müşterileriniz için **Azure’da Power BI Embedded** kullanırken **Power BI** JavaScript API’si ile birlikte **Power BI** .NET SDK’sı kullanarak bir raporu bir uygulama ile tümleştirme veya uygulamaya ekleme işlemini göstermektedir.

Bu öğreticide aşağıdakilerin nasıl yapılacağını öğreneceksiniz:
>[!div class="checklist"]
>* Azure’da bir uygulama kaydetme.
>* Azure’da Power BI Embedded kullanarak rapor, pano veya kutucuğu bir uygulamaya ekleme.

## <a name="prerequisites"></a>Önkoşullar
Başlamak için bir **Power BI Pro** hesabı ve **Microsoft Azure** hesabı gerekir.

* **Power BI Pro**’ya kaydolmadıysanız başlamadan önce [ücretsiz deneme için kaydolun](https://powerbi.microsoft.com/en-us/pricing/).
* Azure aboneliğiniz yoksa başlamadan önce [ücretsiz bir hesap](https://azure.microsoft.com/free/?WT.mc_id=A261C142F) oluşturun.
* [Azure Active Directory kiracınız](create-an-azure-active-directory-tenant.md) ayarlanmış olmalıdır.
* [Visual Studio](https://www.visualstudio.com/) yüklü olmalıdır (sürüm 2013 veya üzeri).

## <a name="setup-your-embedded-analytics-development-environment"></a>Eklediğiniz analiz geliştirme ortamını ayarlama

Raporları, panoları veya kutucukları uygulamanıza eklemeye başlamadan önce ortamınızın ekleme işlevlerine izin verecek şekilde ayarlanmış olduğundan emin olmanız gerekir. Kurulumun bir parçası olarak aşağıdaki işlemleri yapmanız gerekir.

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

### <a name="create-your-power-bi-embedded-dedicated-capacity-in-azure"></a>Azure’da Power BI Embedded’e ayrılmış kapasitenizi oluşturma

1. [Azure portalında](https://portal.azure.com) oturum açın.

    ![Azure Portalı Ana Sayfası](media/embed-sample-for-customers/embed-sample-for-customers-002.png)

2. Sol gezinti bölmesinde **Tüm Hizmetler** ve **Power BI Embedded**’i seçin.

    ![PBIE araması](media/embed-sample-for-customers/embed-sample-for-customers-017.png)

3. İstemleri izleyin ve yeni bir **Power BI Embedded**’e ayrılmış kapasite oluşturmak için gereken doğru bilgileri doldurduktan sonra **Oluştur**’u seçin. **Fiyatlandırma Katmanı** seçerken, gereksinimlerinize en uygun katmana karar vermek için aşağıdaki tabloyu gözden geçirin. Ardından, **Oluştur**’u seçin ve kaynağın tamamlanmasını bekleyin.

    ![PBIE ayarı](media/embed-sample-for-customers/embed-sample-for-customers-018.png)

| Kapasite Düğümü | Toplam çekirdek<br/>*(Arka uç + ön uç)* | Arka Uç Çekirdekleri | Ön Uç Çekirdekleri | DirectQuery/canlı bağlantı sınırları | Yoğun saatlerde işlenen maksimum sayfa sayısı |
| --- | --- | --- | --- | --- | --- |
| A1 |1 sanal çekirdek |0,5 çekirdek, 3 GB RAM |0,5 çekirdek | saniyede 5 |1-300 |
| A2 |2 sanal çekirdek |1 çekirdek, 5 GB RAM |1 çekirdek | saniyede 10 |301-600 |
| A3 |4 sanal çekirdek |2 çekirdek, 10 GB RAM |2 çekirdek | saniyede 15 |601-1200 |
| A4 |8 sanal çekirdek |4 çekirdek, 25 GB RAM |4 çekirdek |saniyede 30 |1201-2400 |
| A5 |16 sanal çekirdek |8 çekirdek, 50 GB RAM |8 çekirdek |saniyede 60 |2401-4800 |
| A6 |32 sanal çekirdek |16 çekirdek, 100 GB RAM |16 çekirdek |saniyede 120 |4801-9600 |

Artık yeni **Power BI Embedded’e ayrılmış kapasite**’yi görüntüleyebilirsiniz.

   ![PBIE ayrılmış kapasite](media/embed-sample-for-customers/embed-sample-for-customers-019.png)

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

7. **Gelişmiş**’i genişletin, ardından **Ayrılmış kapasite**’yi etkinleştirin, sonra da oluşturduğunuz **Power BI Embedded’e ayrılmış kapasite**’yi seçin. Sonra **Kaydet**'i seçin.

    ![Üye Ekleme](media/embed-sample-for-customers/embed-sample-for-customers-024.png)

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

JavaScript API kullanan tam bir örnek için [Playground aracı](https://microsoft.github.io/PowerBI-JavaScript/demo)'nı kullanabilirsiniz. Bunu yapmak, farklı türde Power BI Embedded örnekleri ile yürütmenin hızlı bir yoludur. Ayrıca [PowerBI-JavaScript wiki](https://github.com/Microsoft/powerbi-javascript/wiki) sayfasını ziyaret ederek JavaScript API’si hakkında daha fazla bilgi alabilirsiniz.

Power BI Embedded hakkında daha fazla soru için lütfen [SSS](embedded-faq.md) sayfasını ziyaret edin.  Uygulamanızda Power Bi Embedded ile ilgili sorun yaşıyorsanız, lütfen [sorun giderme](embedded-troubleshoot.md) sayfasını ziyaret edin.

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/) 