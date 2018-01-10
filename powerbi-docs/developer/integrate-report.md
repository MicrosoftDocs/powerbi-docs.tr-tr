---
title: "Kuruluşunuz için bir Power BI raporunu uygulamayla tümleştirme"
description: "Power BI API'leri kullanarak bir raporu web uygulamasıyla tümleştirmeyi veya web uygulamasına eklemeyi öğrenin."
services: powerbi
documentationcenter: 
author: guyinacube
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: get-started-article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/05/2017
ms.author: asaxton
ms.openlocfilehash: 8285cbbc2d8dee653863cad50036da58362c32d1
ms.sourcegitcommit: 7517c068db806f12bb0b953e9a1bd4249ca12da5
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2018
---
# <a name="integrate-a-report-into-an-app-for-your-organization"></a>Kuruluşunuz için bir raporu uygulamayla tümleştirme
Kuruluşunuz için REST API çağrılarını ve Power BI JavaScript API'sini kullanarak ekleme yaparken bir raporu web uygulamasıyla tümleştirmeyi veya web uygulamasına eklemeyi öğrenin.

![Ekli rapor örneği](media/integrate-report/powerbi-embedded-report.png)

Bu adım adım kılavuza başlamak için **Power BI** hesabınız olması gerekir. Hesabınız yoksa [ücretsiz bir Power BI hesabı açabilir](../service-self-service-signup-for-power-bi.md) veya test süreçlerinde kullanmak üzere kendi [Azure Active Directory kiracınızı](create-an-azure-active-directory-tenant.md) oluşturabilirsiniz.

> [!NOTE]
> Bunun yerine ekleme belirteci kullanarak raporu müşterileriniz için eklemek mi istiyorsunuz? Bkz. [Müşterileriniz için uygulamanıza bir pano, kutucuk veya rapor tümleştirme](embed-sample-for-customers.md).
> 
> 

Bir raporu web uygulamasıyla tümleştirmek için **Power BI** REST API'sini veya Power BI C# SDK'sını ve Azure Active Directory (AD) yetkilendirme **erişim belirtecini** kullanarak rapora ulaşmanız gerekir. Ardından raporu aynı erişim belirteciyle yükleyebilirsiniz. **Power BI** API'si belirli **Power BI** kaynaklarına programlı erişim sağlar. Daha fazla bilgi için bkz. [Overview of Power BI REST API (Power BI REST API'sine Genel Bakış)](https://msdn.microsoft.com/library/dn877544.aspx), [Power BI JavaScript API'si](https://github.com/Microsoft/PowerBI-JavaScript).

## <a name="download-the-sample"></a>Örneği indirme
Bu makalede GitHub üzerindeki [integrate-report-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app) uygulamasında kullanılan kodlar gösterilmiştir. Bu adım adım kılavuzla birlikte ilerlemek için örneği indirebilirsiniz.

## <a name="step-1---register-an-app-in-azure-ad"></a>1. Adım: Bir uygulamayı Azure AD'ye kaydetme
REST API çağrıları gerçekleştirmek için uygulamanızı Azure AD'ye kaydetmeniz gerekir. Daha fazla bilgi için bkz. [Bir Azure AD uygulamasını Power BI içeriği eklemek üzere kaydetme](register-app.md).

[integrate-report-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app) örneğini indirdiyseniz kayıt sonrasında aldığınız **İstemci Kimliğini** ve **Gizli Anahtar**'ı kullanarak örneğin Azure AD kimlik doğrulamasından geçmesini sağlayabilirsiniz. Örneği yapılandırmak için *cloud.config* dosyasındaki **İstemci Kimliğini** ve **Gizli Anahtarı** değiştirin.

![](media/integrate-report/powerbi-embed-dashboard-register-app4.png)

## <a name="step-2---get-an-access-token-from-azure-ad"></a>2. Adım: Azure AD'den erişim belirteci alma
Uygulamanızın içinden Power BI REST API'si çağrısı yapabilmek için önce Azure AD'den bir **erişim belirteci** almanız gerekir. Daha fazla bilgi için bkz. [Power BI uygulamanız için kullanıcıların kimliğini doğrulama ve Azure AD erişim belirteci alma](get-azuread-access-token.md).

## <a name="step-3---get-a-report"></a>3. Adım: Rapor alma
Bir **Power BI** raporu almak için **Power BI** raporlarının listesini alan [Get Reports](https://msdn.microsoft.com/library/mt634543.aspx) işlemini kullanabilirsiniz. Rapor listesindeki rapor kimliklerinden birini seçebilirsiniz.

### <a name="get-reports-using-an-access-token"></a>Erişim belirteci kullanarak rapor alma
[2. Adım](#step-2-get-an-access-token-from-azure-ad)'da aldığınız **erişim belirteci** ile [Get Reports](https://msdn.microsoft.com/library/mt634543.aspx) işlemi çağrısını yapabilirsiniz. [Get Reports](https://msdn.microsoft.com/library/mt634543.aspx) işlemi rapor listesini döndürür. Rapor listesindeki raporlardan birini alabilirsiniz. Aşağıda rapor almak için kullanabileceğiniz ayrıntılı bir C# yöntemi verilmiştir. 

REST API çağrısını yapmak için *Taşıyıcı {erişim belirteci}* biçiminde *Yetkilendirme* üst bilgisi dahil etmeniz gerekir.

#### <a name="get-reports-with-the-rest-api"></a>REST API'si ile rapor alma
**Default.aspx.cs**

```
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
REST API'sini doğrudan çağırmak yerine .NET SDK kullanarak rapor listesi alabilirsiniz.

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

var tokenCredentials = new TokenCredentials(<ACCESS TOKEN>, "Bearer");

// Create a Power BI Client object. It will be used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Get the first report all reports in that workspace
    ODataResponseListReport reports = client.Reports.GetReports();

    Report report = reports.Value.FirstOrDefault();

    var embedUrl = report.EmbedUrl;
}
```

## <a name="step-4---load-a-report-using-javascript"></a>4. Adım: JavaScript kullanarak rapor yükleme
JavaScript kullanarak web sayfanızdaki bir div öğesine rapor yükleyebilirsiniz.

**Default.aspx**

```
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

```
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
    });
}
```

[integrate-report-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app) indirdiyseniz sonuç aşağıdakine benzer olacaktır.

![Ekli rapor örneği](media/integrate-report/powerbi-embedded-report.png)

## <a name="working-with-groups-app-workspaces"></a>Gruplarla (uygulama çalışma alanlarıyla) çalışma
Bir gruptaki (uygulama çalışma alanındaki) raporu eklemek için REST API çağrısını kullanarak grup panosu içindeki kullanılabilir tüm raporların listesini almanız gerekir. Bu REST API çağrısı hakkında daha fazla bilgi için bkz. [Get Reports](https://msdn.microsoft.com/library/mt634543.aspx). İsteğin sonuç döndürmesi için grupta gerekli izinlere sahip olmanız gerekir.

```
https://api.powerbi.com/v1.0/myorg/groups/{group_id}/reports
```

Yukarıdaki API, kullanılabilir durumdaki raporların listesini döndürür. Her raporda grubun eklenmesini desteklemek üzere oluşturulmuş olan bir EmbedUrl özelliği mevcuttur.

```
https://app.powerbi.com/reportEmbed?reportId={report_id}&groupId={group_id}
```

## <a name="next-steps"></a>Sonraki adımlar
GitHub üzerindeki örnek uygulamayı gözden geçirebilirsiniz. Daha fazla bilgi için bkz. [integrate-report-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-report-web-app).

JavaScript API hakkında daha fazla bilgi için bkz. [Power BI JavaScript API'si](https://github.com/Microsoft/PowerBI-JavaScript).

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

