---
title: Kuruluşunuz için Power BI içeriğini bir uygulamaya ekleme
description: Kuruluşunuz için Power BI API'leri kullanarak bir raporu, panoyu veya kutucuğu web uygulamasıyla tümleştirmeyi ya da web uygulamasına eklemeyi öğrenin.
author: markingmyname
ms.author: maghan
ms.date: 07/13/2018
ms.topic: tutorial
ms.service: powerbi
ms.component: powerbi-developer
ms.custom: mvc
manager: kfile
ms.openlocfilehash: cfc450216202f332f518955d28cb71df6aa0b800
ms.sourcegitcommit: f2b106b5eb338a64f903e8ce6793bccb07f9440a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/18/2018
ms.locfileid: "39105281"
---
# <a name="tutorial-embed-a-power-bi-report-dashboard-or-tile-into-an-application-for-your-organization"></a>Öğretici: Kuruluşunuz için bir Power BI raporunu, panosunu veya kutucuğunu bir uygulamaya ekleme
Bu öğretici, **Power BI**'ı kuruluşunuz için bir uygulamaya eklerken **Power BI JavaScript API’si** ile birlikte **Power BI .NET SDK’sı** kullanarak bir raporu bir uygulama ile tümleştirme işlemini göstermektedir. **Power BI** ile raporları, panoları veya kutucukları **verilerin sahibi kullanıcıdır** yapısını kullanarak bir uygulamaya ekleyebilirsiniz. **Verilerin sahibi kullanıcıdır** yapısı, uygulamanızın Power BI hizmetinin kapsamını genişletmesini sağlar.

![Uygulamayı görüntüleme](media/embed-sample-for-your-organization/embed-sample-for-your-organization-035.png)

Bu öğreticide aşağıdakilerin nasıl yapılacağını öğreneceksiniz:
>[!div class="checklist"]
>* Azure’da bir uygulama kaydetme.
>* Bir uygulamaya Power BI raporu ekleme.

## <a name="prerequisites"></a>Önkoşullar
Başlamak için bir **Power BI Pro** hesabı ve **Microsoft Azure** aboneliği gerekir.

* **Power BI Pro**’ya kaydolmadıysanız başlamadan önce [ücretsiz deneme için kaydolun](https://powerbi.microsoft.com/en-us/pricing/).
* Azure aboneliğiniz yoksa başlamadan önce [ücretsiz bir hesap](https://azure.microsoft.com/free/?WT.mc_id=A261C142F) oluşturun.
* [Azure Active Directory kiracınız](create-an-azure-active-directory-tenant.md) ayarlanmış olmalıdır.
* [Visual Studio](https://www.visualstudio.com/) yüklü olmalıdır (sürüm 2013 veya üzeri).

## <a name="setup-your-embedded-analytics-development-environment"></a>Eklediğiniz analiz geliştirme ortamını ayarlama

Raporları, panoları veya kutucukları uygulamanıza eklemeye başlamadan önce ortamınızın ekleme işlevlerine izin verecek şekilde ayarlanmış olduğundan emin olmanız gerekir. Kurulumun bir parçası olarak aşağıdaki işlemleri yapmanız gerekir.

Hızla kullanmaya başlamak ve bir ortam oluşturma ve rapor ekleme adımlarını gösteren örnek bir uygulama indirmek için [Katılım deneyimi aracını](https://aka.ms/embedsetup/UserOwnsData) inceleyebilirsiniz.

Ancak, ortamı el ile ayarlamayı seçerseniz aşağıdaki adımlara devam edebilirsiniz.
### <a name="register-an-application-in-azure-active-directory-azure-ad"></a>Azure Active Directory'de (Azure AD) bir uygulamayı kaydetme

Power BI REST API'lerine erişmesini sağlamak için uygulamanızı Azure Active Directory'ye kaydetmeniz gerekir. Kayıt işlemi sayesinde uygulamanız için bir kimlik oluşturabilir ve Power BI REST kaynaklarıyla ilgili izinleri belirleyebilirsiniz.

1. [Microsoft Power BI API Koşulları](https://powerbi.microsoft.com/api-terms)'nı kabul edin.

2. [Azure portalında](https://portal.azure.com) oturum açın.

    ![Azure Portalı Ana Sayfası](media/embed-sample-for-your-organization/embed-sample-for-your-organization-002.png)

3. Sol taraftaki gezinti bölmesinde **Tüm Hizmetler**'i, **Uygulama Kayıtları**'nı ve sonra **Yeni uygulama kaydı**'nı seçin.

    ![Uygulama kaydı araması](media/embed-sample-for-your-organization/embed-sample-for-your-organization-003.png)</br>
    ![Yeni Uygulama kaydı](media/embed-sample-for-your-organization/embed-sample-for-your-organization-004.png)

4. Talimatları izleyerek yeni bir uygulama oluşturun. **Verilerin sahibi kullanıcıdır** yapısı için **Web uygulaması/API** uygulama türünü kullanmanız gerekir. Ayrıca, **Azure AD**'nin belirteç yanıtlarını döndürmek için kullanacağı bir **Oturum açma URL'si** belirtmeniz gerekir. Uygulamanıza özgü bir değer girin, örneğin: http://localhost:13526/).

    ![Uygulama Oluşturma](media/embed-sample-for-your-organization/embed-sample-for-your-organization-005.png)

### <a name="apply-permissions-to-your-application-within-azure-active-directory"></a>Azure Active Directory'de uygulamanıza izinler uygulama

Uygulamanız için uygulama kayıt sayfasında belirtilenlere ek izinler etkinleştirmeniz gerekir. İzinleri etkinleştirmek için *genel yönetici* hesabıyla oturum açmış olmanız gerekir.

### <a name="use-the-azure-active-directory-portal"></a>Azure Active Directory portalını kullanma

1. Azure portalındaki [Uygulama kayıtları](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ApplicationsListBlade) sayfasına gidip ekleme için kullandığınız uygulamayı seçin.

    ![Uygulama Seçme](media/embed-sample-for-your-organization/embed-sample-for-your-organization-006.png)

2. **Ayarlar**’ı ve sonra **API Erişimi** altında **Gerekli izinler**'i seçin.

    ![Gerekli İzinler](media/embed-sample-for-your-organization/embed-sample-for-your-organization-008.png)

3. **Windows Azure Active Directory**'yi seçin ve **Oturum açmış kullanıcı olarak dizine erişin** seçeneğinin belirlenmiş olduğundan emin olun. **Kaydet**'i seçin.

    ![Windows Azure AD İzinleri](media/embed-sample-for-your-organization/embed-sample-for-your-organization-011.png)

4. **Ekle**'yi seçin.

    ![İzin Ekleme](media/embed-sample-for-your-organization/embed-sample-for-your-organization-012.png)

5. **Bir API seçin** öğesini seçin.

    ![API Erişimi Ekleme](media/embed-sample-for-your-organization/embed-sample-for-your-organization-013.png)

6. **Power BI Hizmeti**’ni, ardından **Seç**’i seçin.

    ![PBI Hizmetleri Seçme](media/embed-sample-for-your-organization/embed-sample-for-your-organization-014.png)

7. **Temsilci İzinleri** bölümündeki tüm izinleri seçin. Seçimlerin kaydedilmesi için teker teker seçmeniz gerekir. Tümünü seçtikten sonra **Kaydet**'i seçin.

    ![Temsilci izinleri seçme](media/embed-sample-for-your-organization/embed-sample-for-your-organization-015.png)

## <a name="setup-your-power-bi-environment"></a>Power BI ortamınızı ayarlama

### <a name="create-an-app-workspace"></a>Uygulama çalışma alanı oluştur

Müşterileriniz için rapor, pano veya kutucuklar ekliyorsanız, içeriğinizi bir uygulama çalışma alanına yerleştirmeniz gerekir.

1. İşe çalışma alanını oluşturarak başlayın. **Çalışma alanları** > **Uygulama çalışma alanı oluşturma**'yı seçin. Burası, uygulamanızın erişmesi gereken içerikleri yerleştirdiğiniz yerdir.

    ![Çalışma Alanı Oluşturma](media/embed-sample-for-your-organization/embed-sample-for-your-organization-020.png)

2. Çalışma alanına bir ad verin. Karşılık gelen **Çalışma Alanı Kimliği** kullanılamıyorsa düzenleyerek benzersiz bir kimlik belirleyin. Bu kimlik uygulamanın da adı olmalıdır.

    ![Çalışma Alanını Adlandırma](media/embed-sample-for-your-organization/embed-sample-for-your-organization-021.png)

3. Değiştirebileceğiniz birkaç ayar vardır. **Ortak** seçeneğini belirlerseniz çalışma alanınızdakileri kuruluşunuzdaki herkes görebilir. **Özel**'i seçerseniz çalışma alanının içeriğini yalnızca üyeler görebilir.

    ![Özel/Genel](media/embed-sample-for-your-organization/embed-sample-for-your-organization-022.png)

    Grubu oluşturduktan sonra Ortak/Özel ayarını değiştiremezsiniz.

4. Üyelere **düzenleme** veya **yalnızca görüntüleme** erişimi verebilirsiniz.

    ![Üye Ekleme](media/embed-sample-for-your-organization/embed-sample-for-your-organization-023.png)

5. Çalışma alanı erişimi vermek istediğiniz kişilerin e-posta adreslerini girip **Ekle**'yi seçin. Grup takma adlarını ekleyemezsiniz, yalnızca kişilere izin verilir.

6. Eklediğiniz kişilerin üye mi yoksa yönetici mi olacağına karar verin. Yöneticiler çalışma alanını düzenleyebilir, başka üyeler ekleyebilir. Yalnızca görüntüleme erişimine sahip olanlar dışındaki üyeler çalışma alanındaki içeriği düzenleyebilir. Hem yöneticiler hem de üyeler uygulamayı yayımlayabilir.

    Artık yeni çalışma alanını görüntüleyebilirsiniz. Power BI çalışma alanını oluşturur ve açar. Üyesi olduğunuz çalışma alanlarının listesinde gösterilir. Yönetici olduğunuz için üç nokta (…) simgesini seçerek geri gidebilir, değişiklik yapabilir, yeni üye ekleyebilir veya üye izinlerini değiştirebilirsiniz.

    ![Çalışma Alanı Oluşturma](media/embed-sample-for-your-organization/embed-sample-for-your-organization-025.png)

### <a name="create-and-publish-your-reports"></a>Raporlarınızı oluşturma ve yayımlama

Power BI Desktop'ı kullanarak raporlarınızı ve veri kümelerinizi oluşturabilir, ardından bu raporları uygulama çalışma alanında yayımlayabilirsiniz. Raporları yayımlayan son kullanıcının uygulama çalışma alanında yayımlama yapabilmesi için bir Power BI Pro lisansına sahip olması gerekir.

1. GitHub'dan örnek [Blog Tanıtımı](https://github.com/Microsoft/powerbi-desktop-samples)’nı indirin.

    ![rapor örneği](media/embed-sample-for-your-organization/embed-sample-for-your-organization-026-1.png)

2. **Power BI Desktop**’ta örnek PBIX raporunu açın

   ![PBI desktop raporu](media/embed-sample-for-your-organization/embed-sample-for-your-organization-027.png)

3. **Uygulama çalışma alanında** yayımlayın

   ![PBI desktop raporu](media/embed-sample-for-your-organization/embed-sample-for-your-organization-028.png)

    Artık raporunuzu Power BI hizmetinde çevrimiçi görüntüleyebilirsiniz.

   ![PBI desktop raporu](media/embed-sample-for-your-organization/embed-sample-for-your-organization-029.png)

## <a name="embed-your-content-using-the-sample-application"></a>Örnek uygulamayı kullanarak içeriği ekleme

Örnek bir uygulamayı kullanarak içeriğinizi eklemeye başlamak için bu adımları izleyin.

1. Başlamak için GitHub’dan [Verilerin Sahibi Kullanıcıdır örneğini](https://github.com/Microsoft/PowerBI-Developer-Samples) indirin.  Biri [raporlar](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app), biri [panolar](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app), biri de [kutucuklar](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app) için olmak üzere 3 farklı örnek uygulama vardır.  Bu makalenin aşağıdaki adımlarında **raporlar** uygulaması referans alınır.

    ![Verilerin Sahibi Kullanıcıdır uygulama örneği](media/embed-sample-for-your-organization/embed-sample-for-your-organization-026.png)

2. Örnek uygulamadaki Cloud.config dosyasını açın. Uygulamayı başarıyla çalıştırmak için doldurmanız gereken birkaç alan vardır. **ClientID** ve **ClientSecret**.

    ![Cloud Config dosyası](media/embed-sample-for-your-organization/embed-sample-for-your-organization-030.png)

    **ClientID** bilgilerini **Azure**’daki **Uygulama Kimliği** ile doldurun. Uygulama, izin istediğiniz kullanıcılara kendini tanıtmak için **ClientID** değerini kullanır.

    **ClientID** değerini almak için aşağıdaki adımları izleyin:

    [Azure portalında](https://portal.azure.com) oturum açın.

    ![Azure Portalı Ana Sayfası](media/embed-sample-for-your-organization/embed-sample-for-your-organization-002.png)

    Sol gezinti bölmesinde **Tüm Hizmetler**'i ve **Uygulama Kayıtları**'nı seçin.

    ![Uygulama kaydı araması](media/embed-sample-for-your-organization/embed-sample-for-your-organization-003.png)

    **ClientID** değerini kullanması gereken uygulamayı seçin.

    ![Uygulama Seçme](media/embed-sample-for-your-organization/embed-sample-for-your-organization-006.png)

    GUID olarak listelenen bir **Uygulama Kimliği** görmeniz gerekir. Bu **Uygulama Kimliği**’ni uygulamanın **ClientID** değeri olarak kullanın.

    ![ClientID](media/embed-sample-for-your-organization/embed-sample-for-your-organization-007.png)

    **ClientSecret** alanına **Azure**'daki **Uygulama kayıtları** bölümünden alacağınız **Anahtarlar** bilgilerini girin.

    **ClientSecret** değerini almak için aşağıdaki adımları izleyin:

    [Azure portalında](https://portal.azure.com) oturum açın.

    ![Azure Portalı Ana Sayfası](media/embed-sample-for-your-organization/embed-sample-for-your-organization-002.png)

    Sol gezinti bölmesinde **Tüm Hizmetler**'i ve **Uygulama Kayıtları**'nı seçin.

    ![Uygulama kaydı araması](media/embed-sample-for-your-organization/embed-sample-for-your-organization-003.png)

    **ClientSecret** değerini kullanması gereken uygulamayı seçin.

    ![Uygulama Seçme](media/embed-sample-for-your-organization/embed-sample-for-your-organization-006.png)

    **Ayarlar** seçeneğini belirleyin.

    ![Ayarlar](media/embed-sample-for-your-organization/embed-sample-for-your-organization-038.png)

    **Anahtarlar**'ı seçin.

    ![Anahtarlar](media/embed-sample-for-your-organization/embed-sample-for-your-organization-039.png)

    **Açıklama** alanına bir ad yazın, **Süre** belirleyin ve ardından **Kaydet**'e tıklayarak uygulamanıza ait **Değer** bilgisini alın. **Anahtar değerini** kaydettikten sonra **Anahtarlar** dikey penceresini kapattığınızda değer alanında yalnızca **_Gizli_** ifadesi görünür ve bu noktada **anahtar değerini** alamazsınız. **Anahtar değerini** kaybederseniz **Azure portaldan** yeni bir tane oluşturmanız gerekir.

    ![Anahtarlar](media/embed-sample-for-your-organization/embed-sample-for-your-organization-031.png)

     **groupId** bilgilerini Power BI’daki **uygulama çalışma alanı GUID’si** ile doldurun.

    ![groupId](media/embed-sample-for-customers/embed-sample-for-customers-031.png)

    **reportId** bilgilerini Power BI’daki **rapor GUID’si** ile doldurun.

    ![reportId](media/embed-sample-for-customers/embed-sample-for-customers-032.png)

3. Uygulamayı çalıştırın!

    İlk olarak **Visual Studio**’da **Çalıştır**’ı seçin.

    ![Uygulamayı çalıştırma](media/embed-sample-for-your-organization/embed-sample-for-your-organization-033.png)

    Ardından **Rapor Al**'ı seçin.

    ![İçerik seçme](media/embed-sample-for-your-organization/embed-sample-for-your-organization-034.png)

    Artık raporu örnek uygulamada görüntüleyebilirsiniz.

    ![Uygulamayı görüntüleme](media/embed-sample-for-your-organization/embed-sample-for-your-organization-035.png)

## <a name="embed-your-content-within-your-application"></a>İçeriğinizi uygulamanın içine ekleme
İçeriğinizi ekleme adımları [Power BI REST API'leri](https://docs.microsoft.com/rest/api/power-bi/) ile yapılabilse de, bu makalede açıklanan örnek kodlar **.NET SDK** ile hazırlanır.

Bir raporu web uygulamasıyla tümleştirmek için **Power BI REST API'sini** veya **Power BI C# SDK'sını** ve Azure Active Directory (AD) yetkilendirme **erişim belirtecini** kullanarak rapora ulaşmanız gerekir. Ardından raporu aynı **erişim belirteciyle** yükleyebilirsiniz. **Power BI Rest API'si** belirli **Power BI** kaynaklarına programlı erişim sağlar. Daha fazla bilgi için bkz. [Power BI REST API](https://docs.microsoft.com/rest/api/power-bi/), [Power BI JavaScript API'si](https://github.com/Microsoft/PowerBI-JavaScript).

### <a name="get-an-access-token-from-azure-ad"></a>Azure AD'den erişim belirteci alma
Uygulamanızın içinden Power BI REST API'si çağrısı yapabilmek için önce Azure AD'den bir **erişim belirteci** almanız gerekir. Daha fazla bilgi için bkz. [Power BI uygulamanız için kullanıcıların kimliğini doğrulama ve Azure AD erişim belirteci alma](get-azuread-access-token.md).

### <a name="get-a-report"></a>Rapor alma
Bir **Power BI** raporu almak için **Power BI** raporlarının listesini alan [Get Reports](https://docs.microsoft.com/rest/api/power-bi/reports/getreports) işlemini kullanabilirsiniz. Rapor listesindeki rapor kimliklerinden birini seçebilirsiniz.

### <a name="get-reports-using-an-access-token"></a>Erişim belirteci kullanarak rapor alma
[Get Reports](https://docs.microsoft.com/rest/api/power-bi/reports/getreports) işlemi rapor listesini döndürür. Rapor listesindeki raporlardan birini alabilirsiniz.

REST API çağrısını yapmak için *Taşıyıcı {erişim belirteci}* biçiminde *Yetkilendirme* üst bilgisi dahil etmeniz gerekir.

#### <a name="get-reports-with-the-rest-api"></a>REST API'si ile rapor alma

**REST API'si** ile rapor almayı gösteren kod örneği aşağıda verilmiştir.

*Eklemek istediğiniz içerik öğesini (rapor, pano veya kutucuk) alma örneği, [örnek uygulama](#embed-your-content-using-the-sample-application) içindeki **_Default.aspx.cs_** dosyasında sağlanır.*

```csharp
using Newtonsoft.Json;

//Get a Report. In this sample, you get the first Report.
protected void GetReport(int index)
{
    //Configure Reports request
    System.Net.WebRequest request = System.Net.WebRequest.Create(
        String.Format("{0}/Reports",
        baseUri)) as System.Net.HttpWebRequest;

    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", accessToken.Value));

    //Get Reports response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            //Deserialize JSON string
            PBIReports Reports = JsonConvert.DeserializeObject<PBIReports>(reader.ReadToEnd());

            //Sample assumes at least one Report.
            //You could write an app that lists all Reports
            if (Reports.value.Length > 0)
            {
                var report = Reports.value[index];

                txtEmbedUrl.Text = report.embedUrl;
                txtReportId.Text = report.id;
                txtReportName.Text = report.name;
            }
        }
    }
}

//Power BI Reports used to deserialize the Get Reports response.
public class PBIReports
{
    public PBIReport[] value { get; set; }
}
public class PBIReport
{
    public string id { get; set; }
    public string name { get; set; }
    public string webUrl { get; set; }
    public string embedUrl { get; set; }
}
```

#### <a name="get-reports-using-the-net-sdk"></a>.NET SDK kullanarak rapor alma
REST API'sini doğrudan çağırmak yerine .NET SDK kullanarak rapor listesi alabilirsiniz. Raporları listelemek için kullanabileceğiniz örnek kod aşağıda verilmiştir.

```csharp
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

var tokenCredentials = new TokenCredentials(<ACCESS TOKEN>, "Bearer");

// Create a Power BI Client object. It is used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Get the first report all reports in that workspace
    ODataResponseListReport reports = client.Reports.GetReports();

    Report report = reports.Value.FirstOrDefault();

    var embedUrl = report.EmbedUrl;
}
```

### <a name="load-a-report-using-javascript"></a>JavaScript kullanarak rapor yükleme
JavaScript kullanarak web sayfanızdaki bir div öğesine rapor yükleyebilirsiniz.

Belirli bir çalışma alanının raporunu nasıl alacağınızı gösteren bir kod örneğini burada bulabilirsiniz.

*Eklemek istediğiniz içerik öğesini (rapor, pano veya kutucuk) yükleme örneği, [örnek uygulama](#embed-your-content-using-the-sample-application) içindeki **_Default.aspx_** dosyasında sağlanır.*

```javascript
<!-- Embed Report-->
<div> 
    <asp:Panel ID="PanelEmbed" runat="server" Visible="true">
        <div>
            <div><b class="step">Step 3</b>: Embed a report</div>

            <div>Enter an embed url for a report from Step 2 (starts with https://):</div>
            <input type="text" id="tb_EmbedURL" style="width: 1024px;" />
            <br />
            <input type="button" id="bEmbedReportAction" value="Embed Report" />
        </div>

        <div id="reportContainer"></div>
    </asp:Panel>
</div>
```

**Site.master**

```javascript
window.onload = function () {
    // client side click to embed a selected report.
    var el = document.getElementById("bEmbedReportAction");
    if (el.addEventListener) {
        el.addEventListener("click", updateEmbedReporte, false);
    } else {
        el.attachEvent('onclick', updateEmbedReport);
    }

    // handle server side post backs, optimize for reload scenarios
    // show embedded report if all fields were filled in.
    var accessTokenElement = document.getElementById('MainContent_accessTokenTextbox');
    if (accessTokenElement !== null) {
        var accessToken = accessTokenElement.value;
        if (accessToken !== "")
            updateEmbedReport();
    }
};

// update embed report
function updateEmbedReport() {

    // check if the embed url was selected
    var embedUrl = document.getElementById('tb_EmbedURL').value;
    if (embedUrl === "")
        return;

    // get the access token.
    accessToken = document.getElementById('MainContent_accessTokenTextbox').value;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'report',
        accessToken: accessToken,
        embedUrl: embedUrl
    };

    // Grab the reference to the div HTML element that will host the report.
    var reportContainer = document.getElementById('reportContainer');

    // Embed the report and display it within the div container.
    var report = powerbi.embed(reportContainer, config);

    // report.on will add an event handler which prints to Log window.
    report.on("error", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Error<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    }
  );
}
```

## <a name="using-a-power-bi-premium-dedicated-capacity"></a>Power BI Premium adanmış kapasitesini kullanma

Uygulamanızın geliştirme aşamasını tamamladığınıza göre şimdi adanmış kapasite ile uygulamanızın çalışma alanını destekleme işlemine geçmelisiniz.

### <a name="create-a-dedicated-capacity"></a>Adanmış kapasite oluşturma
Adanmış kapasite oluşturduğunuzda, uygulama çalışma alanınızdaki içerik için özel olarak ayrılmış bir kaynaktan yararlanabilirsiniz. Adanmış kapasite atanmamış çalışma alanları, paylaşılan kapasite olarak kabul edilir. [Power BI Premium](../service-admin-premium-purchase.md)'u kullanarak adanmış kapasite oluşturabilirsiniz.

### <a name="assign-an-app-workspace-to-a-dedicated-capacity"></a>Adanmış kapasiteye uygulama çalışma alanı atama

Adanmış kapasite oluşturulduktan sonra, uygulama çalışma alanınızı bu adanmış kapasiteye atayabilirsiniz. Bunu yapmak için aşağıdaki adımları uygulayın.

1. **Power BI hizmetinde**, çalışma alanlarını genişletin ve içeriğinizi eklemek için kullandığınız çalışma alanına yönelik olan üç noktayı seçin. Ardından **Çalışma alanlarını düzenle**’yi seçin.

    ![Çalışma Alanını Düzenleme](media/embed-sample-for-your-organization/embed-sample-for-your-organization-036.png)

2. **Gelişmiş**’i genişletin, ardından **Adanmış kapasite**’yi etkinleştirin, sonra da oluşturduğunuz adanmış kapasiteyi seçin. Sonra **Kaydet**'i seçin.

    ![Adanmış kapasite atama](media/embed-sample-for-your-organization/embed-sample-for-your-organization-024.png)

3. **Kaydet**'i seçtikten sonra uygulama çalışma alanının yanında bir **elmas** simgesi görünmelidir.

    ![kapasite atanmış uygulama çalışma alanı](media/embed-sample-for-your-organization/embed-sample-for-your-organization-037.png)

## <a name="next-steps"></a>Sonraki adımlar
Bu öğreticide **Power BI kuruluş hesabınızı** kullanarak bir uygulamaya Power BI içeriği eklemeyi öğrendiniz. Şimdi uygulamaları kullanarak bir uygulamaya Power BI içeriği eklemeyi deneyebilirsiniz.  Üçüncü taraf müşteriler için de Power BI içeriği ekleme denemeleri yapabilirsiniz.

> [!div class="nextstepaction"]
> [Uygulamalardan ekleme](embed-from-apps.md)

> [!div class="nextstepaction"]
>[Üçüncü taraf müşteriler için ekleme](embed-sample-for-customers.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)
