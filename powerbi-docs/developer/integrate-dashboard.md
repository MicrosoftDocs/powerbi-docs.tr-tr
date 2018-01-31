---
title: "Kuruluşunuz için bir panoyu uygulamayla tümleştirme"
description: "Power BI API'leri kullanarak bir panoyu web uygulamasıyla tümleştirmeyi veya web uygulamasına eklemeyi öğrenin."
services: powerbi
documentationcenter: 
author: markingmyname
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
ms.author: maghan
ms.openlocfilehash: 36b19588d76c99cb712dc481752ebdee0c867f0d
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2018
---
# <a name="integrate-a-dashboard-into-an-app-for-your-organization"></a>Kuruluşunuz için bir panoyu uygulamayla tümleştirme
Kuruluşunuz için REST API çağrılarını ve Power BI JavaScript API'sini kullanarak ekleme yaparken bir panoyu web uygulamasıyla tümleştirmeyi veya web uygulamasına eklemeyi öğrenin.

![Ekli pano](media/integrate-dashboard/powerbi-embed-dashboard.png)

Bu adım adım kılavuza başlamak için **Power BI** hesabınız olması gerekir. Hesabınız yoksa [ücretsiz olarak Power BI'a kaydolabilir](../service-self-service-signup-for-power-bi.md) veya test süreçlerinde kullanmak üzere kendi [Azure Active Directory kiracınızı](create-an-azure-active-directory-tenant.md) oluşturabilirsiniz.

> [!NOTE]
> Bunun yerine ekleme belirteci kullanarak panoyu müşterileriniz için eklemek mi istiyorsunuz? Bkz. [Müşterileriniz için uygulamanıza bir pano, kutucuk veya rapor tümleştirme](embed-sample-for-customers.md).
> 
> 

Bir panoyu web uygulamasıyla tümleştirmek için **Power BI** REST API'sini veya Power BI C# SDK'sini ve Azure Active Directory (AD) yetkilendirme **erişim belirtecini** kullanarak panoya ulaşmanız gerekir. Ardından panoyu aynı erişim belirteciyle yükleyebilirsiniz. **Power BI** API'si belirli **Power BI** kaynaklarına programlı erişim sağlar. Daha fazla bilgi için bkz. [Overview of Power BI REST API (Power BI REST API'sine Genel Bakış)](https://msdn.microsoft.com/library/dn877544.aspx), [Power BI JavaScript API'si](https://github.com/Microsoft/PowerBI-JavaScript).

## <a name="download-the-sample"></a>Örneği indirin
Bu makalede GitHub üzerindeki [integrate-dashboard-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app) uygulamasında kullanılan kodlar gösterilmiştir. Bu adım adım kılavuzla birlikte ilerlemek için örneği indirebilirsiniz.

## <a name="step-1---register-an-app-in-azure-ad"></a>1. Adım: Bir uygulamayı Azure AD'ye kaydetme
REST API çağrıları gerçekleştirmek için uygulamanızı Azure AD'ye kaydetmeniz gerekir. Daha fazla bilgi için bkz. [Bir Azure AD uygulamasını Power BI içeriği eklemek üzere kaydetme](register-app.md).

[Pano tümleştirme örneğini](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app) indirdiyseniz kayıt sonrasında aldığınız **İstemci Kimliğini** ve **Gizli Anahtar**'ı kullanarak örneğin Azure AD kimlik doğrulamasından geçmesini sağlayabilirsiniz. Örneği yapılandırmak için *cloud.config* dosyasındaki **İstemci Kimliğini** ve **Gizli Anahtarı** değiştirin.

![](media/integrate-dashboard/powerbi-embed-dashboard-register-app4.png)

## <a name="step-2---get-an-access-token-from-azure-ad"></a>2. Adım: Azure AD'den erişim belirteci alma
Uygulamanızın içinden Power BI REST API'si çağrısı yapabilmek için önce Azure AD'den bir **erişim belirteci** almanız gerekir. Daha fazla bilgi için bkz. [Power BI uygulamanız için kullanıcıların kimliğini doğrulama ve Azure AD erişim belirteci alma](get-azuread-access-token.md).

## <a name="step-3---get-a-dashboard"></a>3. Adım: Pano alma
Bir **Power BI** panosu almak için **Power BI** panolarının listesini alan [Get Dashboards](https://msdn.microsoft.com/library/mt465739.aspx) işlemini kullanabilirsiniz. Pano listesinden panoların kimliğini öğrenebilirsiniz.

![](media/integrate-dashboard/powerbi-embed-dashboard-get-dashboards.png)

### <a name="get-dashboards-using-an-access-token"></a>Erişim belirteci kullanarak pano alma
[2. Adım](#step-2-get-an-access-token-from-azure-ad)'da aldığınız **erişim belirteci** ile [Get Dashboards](https://msdn.microsoft.com/library/mt465739.aspx) işlemi çağrısını yapabilirsiniz. [Get Dashboards](https://msdn.microsoft.com/library/mt465739.aspx) işlemi pano listesini döndürür. Pano listesinden tek bir pano alabilirsiniz. Aşağıda pano almak için kullanabileceğiniz ayrıntılı bir C# yöntemi verilmiştir. 

REST API çağrısını yapmak için *Taşıyıcı {erişim belirteci}* biçiminde *Yetkilendirme* üst bilgisi dahil etmeniz gerekir.

#### <a name="get-dashboards-with-the-rest-api"></a>REST API'si ile pano alma
**Default.aspx.cs**

```
protected void getDashboardsButton_Click(object sender, EventArgs e)
{
    string responseContent = string.Empty;

    //Configure dashboards request
    System.Net.WebRequest request = System.Net.WebRequest.Create(String.Format("{0}dashboards", baseUri)) as System.Net.HttpWebRequest;
    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", authResult.AccessToken));

    //Get dashboards response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            responseContent = reader.ReadToEnd();

            //Deserialize JSON string
            PBIDashboards PBIDashboards = JsonConvert.DeserializeObject<PBIDashboards>(responseContent);

            if (PBIDashboards != null)
            {
                var gridViewDashboards = PBIDashboards.value.Select(dashboard => new {
                    Id = dashboard.id,
                    DisplayName = dashboard.displayName,
                    EmbedUrl = dashboard.embedUrl
                });

                this.GridView1.DataSource = gridViewDashboards;
                this.GridView1.DataBind();
            }
        }
    }
}

//Power BI Dashboards used to deserialize the Get Dashboards response.
public class PBIDashboards
{
    public PBIDashboard[] value { get; set; }
}
public class PBIDashboard
{
    public string id { get; set; }
    public string displayName { get; set; }
    public string embedUrl { get; set; }
    public bool isReadOnly { get; set; }
}
```

#### <a name="get-dashboards-using-the-net-sdk"></a>.NET SDK kullanarak pano alma
REST API'sini doğrudan çağırmak yerine .NET SDK kullanarak pano listesi alabilirsiniz.

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

var tokenCredentials = new TokenCredentials(<ACCESS TOKEN>, "Bearer");

// Create a Power BI Client object. It will be used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Get a list of dashboards your "My Workspace"
    ODataResponseListDashboard dashboards = client.Dashboards.GetDashboards();

    // Get a list of dashboards from a group (app workspace)
    ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(groupId);

    Dashboard dashboard = dashboards.Value.FirstOrDefault();

    var embedUrl = dashboard.EmbedUrl
}
```

## <a name="step-4---load-a-dashboard-using-javascript"></a>4. Adım: JavaScript kullanarak pano yükleme
JavaScript kullanarak web sayfanızdaki bir div öğesine pano yükleyebilirsiniz.

**Default.aspx**

```
<!-- Embed Dashboard-->
<div> 
    <asp:Panel ID="PanelEmbed" runat="server" Visible="true">
        <div>
            <div><b class="step">Step 3</b>: Embed a dashboard</div>

            <div>Enter an embed url for a dashboard from Step 2 (starts with https://):</div>
            <input type="text" id="tb_EmbedURL" style="width: 1024px;" />
            <br />
            <input type="button" id="bEmbedDashboardAction" value="Embed Dashboard" />
        </div>

        <div id="dashboardContainer"></div>
    </asp:Panel>
</div>
```

**Site.master**

```
window.onload = function () {
    // client side click to embed a selected dashboard.
    var el = document.getElementById("bEmbedDashboardAction");
    if (el.addEventListener) {
        el.addEventListener("click", updateEmbedDashboard, false);
    } else {
        el.attachEvent('onclick', updateEmbedDashboard);
    }

    // handle server side post backs, optimize for reload scenarios
    // show embedded dashboard if all fields were filled in.
    var accessTokenElement = document.getElementById('MainContent_accessTokenTextbox');
    if (accessTokenElement !== null) {
        var accessToken = accessTokenElement.value;
        if (accessToken !== "")
            updateEmbedDashboard();
    }
};

// update embed dashboard
function updateEmbedDashboard() {

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
        type: 'dashboard',
        accessToken: accessToken,
        embedUrl: embedUrl
    };

    // Grab the reference to the div HTML element that will host the dashboard.
    var dashboardContainer = document.getElementById('dashboardContainer');

    // Embed the dashboard and display it within the div container.
    var dashboard = powerbi.embed(dashboardContainer, config);

    // dashboard.on will add an event handler which prints to Log window.
    dashboard.on("tileClicked", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Tile Clicked<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });

    // dashboard.on will add an event handler which prints to Log window.
    dashboard.on("error", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Error<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });
}
```

[Pano tümleştirme örneğini](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app) indirip çalıştırdıysanız sonuç aşağıdakine benzer olacaktır.

![](media/integrate-dashboard/powerbi-embed-dashboard.png)

## <a name="tile-clicked-events"></a>Kutucuk tıklama olayları
Yukarıdaki örnekte panodaki bir kutucuğun tıklanma olaylarını işleyebileceğinizi fark etmiş olabilirsiniz. Olaylar hakkında daha fazla bilgi için bkz. [JavaScript API'sinde Olayları İşleme](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Handling-Events).

```
// dashboard.on will add an event handler which prints to Log window.
dashboard.on("tileClicked", function (event) {
    var logView = document.getElementById('logView');
    logView.innerHTML = logView.innerHTML + "Tile Clicked<br/>";
    logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
    logView.innerHTML = logView.innerHTML + "---------<br/>";
});

// dashboard.on will add an event handler which prints to Log window.
dashboard.on("error", function (event) {
    var logView = document.getElementById('logView');
    logView.innerHTML = logView.innerHTML + "Error<br/>";
    logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
    logView.innerHTML = logView.innerHTML + "---------<br/>";
});
```

[Pano tümleştirme örneğini](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/PowerBI.com%20Integrate/integrate-dashboard-web-app) indirip çalıştırdıysanız, kutucuklardan birine tıkladığınızda panonun altında bir metin görünür. Metin aşağıdakine benzer olmalıdır. Bu sayede bir kutucuk tıklandığında günlüğe kaydedebilir ve kullanıcıyı ilgili konuma yönlendirebilirsiniz.

```
Tile Clicked
{ "event": "TileClick", "reportEmbedUrl": "", "navigationUrl": "https://app.powerbi.com/dashboards/fcff76f9-15ff-4a8e-8242-275ac9c25b90/qna?q=count%20of%20new%20hires%20from%20July%202014%20to%20December%202014", "tileId": "0e99b45c-9b53-4920-b239-cee7d37d2369" }
---------
Tile Clicked
{ "event": "TileClick", "reportEmbedUrl": "https://app.powerbi.com/reportEmbed?reportId=ab199308-80b1-4626-9823-43a84623bd9c", "navigationUrl": "https://app.powerbi.com/reports/ab199308-80b1-4626-9823-43a84623bd9c/ReportSection1", "tileId": "ffc30447-674a-4511-944f-79e182d719de", "pageName": "ReportSection1" }
---------
```

## <a name="working-with-groups-app-workspaces"></a>Gruplarla (uygulama çalışma alanlarıyla) çalışma
Bir gruptaki (uygulama çalışma alanındaki) panoyu eklemek için aşağıdaki REST API çağrısını kullanarak grup içindeki kullanılabilir tüm panoların listesini almanız gerekir. Bu REST API çağrısı hakkında daha fazla bilgi için bkz. [Get Dashboards](https://msdn.microsoft.com/library/mt465739.aspx). İsteğin sonuç döndürmesi için grupta gerekli izinlere sahip olmanız gerekir.

```
https://api.powerbi.com/v1.0/myorg/groups/{groupId}/dashboards
```

Yukarıdaki API, kullanılabilir durumdaki panoların listesini döndürür. Her panoda grubun eklenmesini desteklemek üzere oluşturulmuş olan bir EmbedUrl özelliği mevcuttur.

```
https://app.powerbi.com/dashboardEmbed?dashboardId={dashboardId}&groupId={groupId}
```

## <a name="limitations"></a>Sınırlamalar
* Ekli panolara erişmek isteyen son kullanıcıların Power BI hesabına ve panoya erişim iznine sahip olması gerekir. Bu kullanıcılar panonun sahibi olabilir veya pano kendileriyle paylaşılmış olabilir.
* Şu an için ekli panolarda Soru-Cevap özelliği desteği yoktur.
* Geçici bir sınırlama olarak panoların güvenlik gruplarıyla paylaşılması durumunda kullanıcının ekli panoyu görebilmesi için panoya öncelikle PowerBI.com'dan erişmesi gerekir.

## <a name="next-steps"></a>Sonraki adımlar
GitHub üzerindeki örnek uygulamayı gözden geçirebilirsiniz. Yukarıdaki örnekler de bu örneği temel almaktadır. Daha fazla bilgi için bkz. [integrate-dashboard-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-dashboard-web-app).

JavaScript API hakkında daha fazla bilgi için bkz. [Power BI JavaScript API'si](https://github.com/Microsoft/PowerBI-JavaScript).

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

