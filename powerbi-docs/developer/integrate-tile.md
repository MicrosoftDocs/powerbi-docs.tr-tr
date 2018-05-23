---
title: Kuruluşunuz için bir Power BI kutucuğunu uygulamayla tümleştirme
description: Bir kutucuğu uygulamayla tümleştirmek için adım adım kılavuz, örnek kod
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 02/13/2018
ms.author: maghan
ms.openlocfilehash: 6ad2138ab37b20fa16a5455ab167ec9e6b7e159c
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="integrate-a-tile-into-an-app-user-owns-data"></a>Kutucukları uygulamalarla tümleştirme (veriler kullanıcıya aittir)
Kuruluşunuz için REST API çağrılarını ve Power BI JavaScript API'sini kullanarak ekleme yaparken bir kutucuğu web uygulamasıyla tümleştirmeyi veya web uygulamasına eklemeyi öğrenin.

![Web uygulamasına eklenmiş kutucuk](media/integrate-tile/powerbi-embedded-tile.png)

Bu adım adım kılavuza başlamak için **Power BI** hesabınız olması gerekir. Hesabınız yoksa [ücretsiz bir Power BI hesabı açabilir](../service-self-service-signup-for-power-bi.md) veya test süreçlerinde kullanmak üzere kendi [Azure Active Directory kiracınızı](create-an-azure-active-directory-tenant.md) oluşturabilirsiniz.

> [!NOTE]
> Bunun yerine ekleme belirteci kullanarak kutucuğu müşterileriniz için eklemek mi istiyorsunuz? Bkz. [Müşterileriniz için uygulamanıza bir pano, kutucuk veya rapor tümleştirme](embed-sample-for-customers.md).
> 
> 

Bir kutucuğu web uygulamasıyla tümleştirmek için **Power BI** REST API'sini veya Power BI C# SDK'sını ve Azure Active Directory (AD) yetkilendirme **erişim belirtecini** kullanarak kutucuğa ulaşmanız gerekir. Ardından kutucuğu aynı erişim belirteciyle yükleyebilirsiniz. **Power BI** API'si belirli **Power BI** kaynaklarına programlı erişim sağlar. Daha fazla bilgi için bkz. [Overview of Power BI REST API (Power BI REST API'sine Genel Bakış)](https://msdn.microsoft.com/library/dn877544.aspx), [Power BI JavaScript API'si](https://github.com/Microsoft/PowerBI-JavaScript).

## <a name="download-the-sample"></a>Örneği indirme
Bu makalede GitHub üzerindeki [integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app) uygulamasında kullanılan kodlar gösterilmiştir. Bu adım adım kılavuzla birlikte ilerlemek için örneği indirebilirsiniz.

## <a name="step-1---register-an-app-in-azure-ad"></a>1. Adım: Bir uygulamayı Azure AD'ye kaydetme
REST API çağrıları gerçekleştirmek için uygulamanızı Azure AD'ye kaydetmeniz gerekir. Daha fazla bilgi için bkz. [Bir Azure AD uygulamasını Power BI içeriği eklemek üzere kaydetme](register-app.md).

[integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app) örneğini indirdiyseniz kayıt sonrasında aldığınız **İstemci Kimliğini** ve **Gizli Anahtar**'ı kullanarak örneğin Azure AD kimlik doğrulamasından geçmesini sağlayabilirsiniz. Örneği yapılandırmak için *cloud.config* dosyasındaki **İstemci Kimliğini** ve **Gizli Anahtarı** değiştirin.

![](media/integrate-tile/powerbi-embed-dashboard-register-app4.png)

## <a name="step-2---get-an-access-token-from-azure-ad"></a>2. Adım: Azure AD'den erişim belirteci alma
Uygulamanızın içinden Power BI REST API'si çağrısı yapabilmek için önce Azure AD'den bir **erişim belirteci** almanız gerekir. Daha fazla bilgi için bkz. [Power BI uygulamanız için kullanıcıların kimliğini doğrulama ve Azure AD erişim belirteci alma](get-azuread-access-token.md).

## <a name="step-3---get-a-tile"></a>3. Adım: Kutucuk alma
Bir **Power BI** kutucuğu almak için belirli bir panodaki **Power BI** kutucuklarının listesini alan [Get Tiles](https://msdn.microsoft.com/library/mt465741.aspx) işlemini kullanabilirsiniz. Kutucuk listesinde kutucuk kimlikleri ve ekleme URL'si yer alır.

Kutucuğu alabilmek için öncelikle pano kimliğini almanız gerekir. Pano alma hakkında bilgi için bkz. [Panoları uygulamalarla tümleştirme (veriler kullanıcıya aittir)](integrate-dashboard.md).

### <a name="get-tiles-using-an-access-token"></a>Erişim belirteci kullanarak kutucuk alma
[2. Adım](#step-2-get-an-access-token-from-azure-ad)'da aldığınız **erişim belirteci** ile [Get Tiles](https://msdn.microsoft.com/library/mt465741.aspx) işlemi çağrısını yapabilirsiniz. [Get Tiles](https://msdn.microsoft.com/library/mt465741.aspx) işlemi kutucuk listesini döndürür. Kutucuk listesindeki kutucuklardan birini alabilirsiniz. Aşağıda kutucuk almak için kullanabileceğiniz ayrıntılı bir C# yöntemi verilmiştir. 

REST API çağrısını yapmak için *Taşıyıcı {erişim belirteci}* biçiminde *Yetkilendirme* üst bilgisi dahil etmeniz gerekir.

#### <a name="get-tiles-with-the-rest-api"></a>REST API'si ile kutucuk alma
**Default.aspx.cs**

```
using Newtonsoft.Json;

//Get a tile from a dashboard. In this sample, you get the first tile.
protected void GetTile(string dashboardId, int index)
{
    //Configure tiles request
    System.Net.WebRequest request = System.Net.WebRequest.Create(
        String.Format("{0}Dashboards/{1}/Tiles",
        baseUri,
        dashboardId)) as System.Net.HttpWebRequest;

    request.Method = "GET";
    request.ContentLength = 0;
    request.Headers.Add("Authorization", String.Format("Bearer {0}", accessToken.Value));

    //Get tiles response from request.GetResponse()
    using (var response = request.GetResponse() as System.Net.HttpWebResponse)
    {
        //Get reader from response stream
        using (var reader = new System.IO.StreamReader(response.GetResponseStream()))
        {
            //Deserialize JSON string
            PBITiles tiles = JsonConvert.DeserializeObject<PBITiles>(reader.ReadToEnd());

            //Sample assumes at least one Dashboard with one Tile.
            //You could write an app that lists all tiles in a dashboard
            if (tiles.value.Length > 0)
                tileEmbedUrl.Text = tiles.value[index].embedUrl;
        }
    }
}

//Power BI Tiles used to deserialize the Get Tiles response.
public class PBITiles
{
    public PBITile[] value { get; set; }
}
public class PBITile
{
    public string id { get; set; }
    public string title { get; set; }
    public string embedUrl { get; set; }
}
```

#### <a name="get-tiles-using-the-net-sdk"></a>.NET SDK kullanarak kutucuk alma
REST API’sini doğrudan çağırmak yerine .NET SDK kullanarak pano listesi alabilirsiniz.

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

var tokenCredentials = new TokenCredentials(<ACCESS TOKEN>, "Bearer");

// Create a Power BI Client object. It will be used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Get a list of dashboards your "My Workspace"
    ODataResponseListDashboard tiles = client.Dashboards.GetDashboards();

    // Get a list of dashboards from a group (app workspace)
    ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(groupId);

    Dashboard dashboard = dashboards.Value.FirstOrDefault();

    // Get the first tile from the above dashbaord
    ODataResponseListTile tiles = client.Dashboards.GetTiles(dashboard.Id);

    Tile tile = tiles.Value.FirstOrDefault();
}
```

## <a name="step-4---load-a-tile-using-javascript"></a>4. Adım: JavaScript kullanarak kutucuk yükleme
JavaScript kullanarak web sayfanızdaki bir div öğesine kutucuk yükleyebilirsiniz.

**Default.aspx**

```
<!-- Embed Tile-->
<div> 
    <asp:Panel ID="PanelEmbed" runat="server" Visible="true">
        <div>
            <div><b class="step">Step 3</b>: Embed a tile</div>

            <div>Enter an embed url for a tile from Step 2 (starts with https://):</div>
            <input type="text" id="tb_EmbedURL" style="width: 1024px;" />
            <br />
            <input type="button" id="bEmbedTileAction" value="Embed Tile" />
        </div>

        <div id="tileContainer"></div>
    </asp:Panel>
</div>
```

**Site.master**

```
window.onload = function () {
    // client side click to embed a selected tile.
    var el = document.getElementById("bEmbedTileAction");
    if (el.addEventListener) {
        el.addEventListener("click", updateEmbedTile, false);
    } else {
        el.attachEvent('onclick', updateEmbedTile);
    }

    // handle server side post backs, optimize for reload scenarios
    // show embedded tile if all fields were filled in.
    var accessTokenElement = document.getElementById('MainContent_accessTokenTextbox');
    if (accessTokenElement !== null) {
        var accessToken = accessTokenElement.value;
        if (accessToken !== "")
            updateEmbedTile();
    }
};

// update embed tile
function updateEmbedTile() {

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
        type: 'tile',
        accessToken: accessToken,
        embedUrl: embedUrl
    };

    // Grab the reference to the div HTML element that will host the tile.
    var tileContainer = document.getElementById('tileContainer');

    // Embed the tile and display it within the div container.
    var tile = powerbi.embed(tileContainer, config);

    // tile.on will add an event handler which prints to Log window.
    tile.on("error", function (event) {
        var logView = document.getElementById('logView');
        logView.innerHTML = logView.innerHTML + "Error<br/>";
        logView.innerHTML = logView.innerHTML + JSON.stringify(event.detail, null, "  ") + "<br/>";
        logView.innerHTML = logView.innerHTML + "---------<br/>";
    });
}
```

[integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app) indirdiyseniz sonuç aşağıdakine benzer olacaktır.

![Web uygulamasına eklenmiş kutucuk](media/integrate-tile/powerbi-embedded-tile.png)

## <a name="working-with-groups-app-workspaces"></a>Gruplarla (uygulama çalışma alanlarıyla) çalışma
Bir gruptaki (uygulama çalışma alanındaki) kutucuğu eklemek için REST API çağrısını kullanarak grup panosu içindeki kullanılabilir tüm kutucukların listesini almanız gerekir. Bu REST API çağrısı hakkında daha fazla bilgi için bkz. [Get Tiles](https://msdn.microsoft.com/library/mt465741.aspx). İsteğin sonuç döndürmesi için grupta gerekli izinlere sahip olmanız gerekir.

```
https://api.powerbi.com/v1.0/myorg/groups/{groupId}/dashboards/{dashboard_id}/tiles
```

Yukarıdaki API, kullanılabilir durumdaki kutucukların listesini döndürür. Her kutucukta grubun eklenmesini desteklemek üzere oluşturulmuş olan bir EmbedUrl özelliği mevcuttur.

```
https://app.powerbi.com/embed?dashboardId={dashboard_id}&tileId={tile_id}&groupId={group_id}
```

## <a name="next-steps"></a>Sonraki adımlar
Power BI'da [Kutucuk Ekleme](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Tile-Embed) - JavaScript Wiki

[Power BI JavaScript API'si](https://github.com/Microsoft/PowerBI-JavaScript).

GitHub'daki [integrate-tile-web-app](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/User%20Owns%20Data/integrate-tile-web-app) örneği.

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

