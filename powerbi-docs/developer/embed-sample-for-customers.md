---
title: "Müşterileriniz için Power BI içeriğini bir uygulamaya ekleme"
description: "Müşterileriniz için Power BI API'leri kullanarak bir panoyu, kutucuğu veya raporu web uygulamasıyla tümleştirmeyi veya web uygulamasına eklemeyi öğrenin."
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
ms.openlocfilehash: 8c703b93e87ad32ab3f730979292b85a86fd53c0
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2017
---
# <a name="embed-a-power-bi-dashboard-tile-or-report-into-your-application"></a>Bir Power BI panosunu, kutucuğunu veya raporunu uygulamanıza ekleme
Müşterileriniz için Power BI .NET SDK'sını ve Power BI JavaScript API'sini kullanarak ekleme yaparken bir panoyu, kutucuğu veya raporu web uygulamasıyla tümleştirmeyi veya web uygulamasına eklemeyi öğrenin. Bu tipik bir ISV senaryosudur.

![Katıştırılmış pano](media/embed-sample-for-customers/powerbi-embed-dashboard.png)

Bu adım adım kılavuza başlamak için **Power BI Pro** hesabınız olması gerekir. Hesabınız yoksa [ücretsiz bir Power BI hesabı açabilir](../service-self-service-signup-for-power-bi.md) ve ardından [Power BI Pro deneme sürümüne](../service-self-service-signup-for-power-bi.md#in-service-power-bi-pro-60-day-trial) kaydolabilirsiniz. Dilerseniz test süreçlerinde kullanmak üzere kendi [Azure Active Directory kiracınızı](create-an-azure-active-directory-tenant.md) oluşturabilirsiniz.

> [!NOTE]
> Bunun yerine kuruluşunuz için bir pano eklemek mi istiyorsunuz? Bkz. [Kuruluşunuz için bir panoyu uygulamayla tümleştirme](integrate-dashboard.md).
> 
> 

Bir panoyu web uygulamasıyla tümleştirmek için **Power BI** API'sini ve Azure Active Directory (AD) yetkilendirme **erişim belirtecini** kullanarak panoya ulaşmanız gerekir. Ardından panoyu ekleme belirteciyle yükleyebilirsiniz. **Power BI** API'si belirli **Power BI** kaynaklarına programlı erişim sağlar. Daha fazla bilgi için bkz. [Overview of Power BI REST API (Power BI REST API'sine Genel Bakış)](https://msdn.microsoft.com/library/dn877544.aspx), [Power BI .NET SDK'sı](https://github.com/Microsoft/PowerBI-CSharp) ve [Power BI JavaScript API'si](https://github.com/Microsoft/PowerBI-JavaScript).

## <a name="download-the-sample"></a>Örneği indirme
Bu makalede GitHub'daki [Kuruluşunuz için ekleme örneğinde](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data) kullanılan kod gösterilmektedir. Bu adım adım kılavuzla birlikte ilerlemek için örneği indirebilirsiniz.

## <a name="step-1---register-an-app-in-azure-ad"></a>1. Adım: Uygulamayı Azure AD'ye kaydetme
REST API çağrıları gerçekleştirmek için uygulamanızı Azure AD'ye kaydetmeniz gerekir. Daha fazla bilgi için bkz. [Bir Azure AD uygulamasını Power BI içeriği eklemek üzere kaydetme](register-app.md).

[Kuruluşunuz için ekleme örneğini](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data) indirdiyseniz kayıt sonrasında aldığınız **İstemci kimliğini** kullanarak örneğin Azure AD kimlik doğrulamasından geçmesini sağlayabilirsiniz. Örneği yapılandırmak için *web.config* dosyasındaki **clientId** değerini değiştirin.

## <a name="step-2---get-an-access-token-from-azure-ad"></a>2. Adım: Azure AD'den erişim belirteci alma
Uygulamanızın içinden Power BI REST API'si çağrısı yapabilmek için önce Azure AD'den bir **erişim belirteci** almanız gerekir. Daha fazla bilgi için bkz. [Power BI uygulamanız için kullanıcıların kimliğini doğrulama ve Azure AD erişim belirteci alma](get-azuread-access-token.md).

**Controllers\HomeController.cs** içindeki her bir içerik öğesi görevinde ilgili örnekleri bulabilirsiniz.

## <a name="step-3---get-a-content-item"></a>3. Adım: İçerik öğesi alma
Power BI içeriğinizi doğru şekilde eklemek için yapmanız gereken birkaç şey vardır. Bu adımların tümü doğrudan REST API ile gerçekleştirilebilir ancak örnek uygulama ve buradaki örnekler için .NET SDK kullanılmıştır.

### <a name="create-the-power-bi-client-with-your-access-token"></a>Power BI İstemcisini erişim belirtecinizle oluşturma
Erişim belirtecinizi kullanarak Power BI API'lerle etkileşim kurmanızı sağlayacak Power BI istemci nesnenizi oluşturmanız gerekir. Bunun için erişim belirtecini *Microsoft.Rest.TokenCredentials* nesnesine sarmanız gerekir.

```
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.Rest;
using Microsoft.PowerBI.Api.V2;

var tokenCredentials = new TokenCredentials(authenticationResult.AccessToken, "Bearer");

// Create a Power BI Client object. It will be used to call Power BI APIs.
using (var client = new PowerBIClient(new Uri(ApiUrl), tokenCredentials))
{
    // Your code to embed items.
}
```

### <a name="get-the-content-item-you-want-to-embed"></a>Eklemek istediğiniz içerik öğesini alma
Eklemek istediğiniz öğeye ilişkin bir başvuru almak için Power BI istemci nesnesini kullanın. Panoları, kutucukları veya raporları ekleyebilirsiniz. Bu örnekte belirli bir çalışma alanının ilk panosunu, kutucuğunu veya raporunu nasıl alacağınız gösterilmiştir.

Bu örnek [App Owns Data örneğinin](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data) **Controllers\HomeController.cs** dosyasında mevcuttur.

**Panolar**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// You will need to provide the GroupID where the dashboard resides.
ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(GroupId);

// Get the first report in the group.
Dashboard dashboard = dashboards.Value.FirstOrDefault();
```

**Kutucuk**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// To retrieve the tile, you first need to retrieve the dashboard.

// You will need to provide the GroupID where the dashboard resides.
ODataResponseListDashboard dashboards = client.Dashboards.GetDashboardsInGroup(GroupId);

// Get the first report in the group.
Dashboard dashboard = dashboards.Value.FirstOrDefault();

// Get a list of tiles from a specific dashboard
ODataResponseListTile tiles = client.Dashboards.GetTilesInGroup(GroupId, dashboard.Id);

// Get the first tile in the group.
Tile tile = tiles.Value.FirstOrDefault();
```

**Rapor**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// You will need to provide the GroupID where the dashboard resides.
ODataResponseListReport reports = client.Reports.GetReportsInGroupAsync(GroupId);

// Get the first report in the group.
Report report = reports.Value.FirstOrDefault();
```

### <a name="create-the-embed-token"></a>Ekleme belirtecini oluşturma
JavaScript API'sinden kullanılabilecek bir ekleme belirtecinin oluşturulması gerekir. Ekleme belirteci, eklediğiniz öğeye özeldir. Bu da eklediğiniz her Power BI içeriği için yeni bir ekleme belirteci oluşturmanız gerektiği anlamına gelir. Kullanılacak **accessLevel** dahil olmak üzere daha fazla bilgi için bkz. [GenerateToken API](https://msdn.microsoft.com/library/mt784614.aspx).

Bu örnek [Kuruluşunuz için ekleme örneğinin](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data) **Controllers\HomeController.cs** dosyasında mevcuttur.

Bu örnekte **EmbedConfig** ve **TileEmbedConfig** için bir sınıf oluşturulduğu kabul edilmektedir. Bu örnek **Models\EmbedConfig.cs** ve **Models\TileEmbedConfig.cs** içinde mevcuttur.

**Pano**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// Generate Embed Token.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");
EmbedToken tokenResponse = client.Dashboards.GenerateTokenInGroup(GroupId, dashboard.Id, generateTokenRequestParameters);

// Generate Embed Configuration.
var embedConfig = new EmbedConfig()
{
    EmbedToken = tokenResponse,
    EmbedUrl = dashboard.EmbedUrl,
    Id = dashboard.Id
};
```

**Kutucuk**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// Generate Embed Token for a tile.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");
EmbedToken tokenResponse = client.Tiles.GenerateTokenInGroup(GroupId, dashboard.Id, tile.Id, generateTokenRequestParameters);

// Generate Embed Configuration.
var embedConfig = new TileEmbedConfig()
{
    EmbedToken = tokenResponse,
    EmbedUrl = tile.EmbedUrl,
    Id = tile.Id,
    dashboardId = dashboard.Id
};
```

**Rapor**

```
using Microsoft.PowerBI.Api.V2;
using Microsoft.PowerBI.Api.V2.Models;

// Generate Embed Token.
var generateTokenRequestParameters = new GenerateTokenRequest(accessLevel: "view");
EmbedToken tokenResponse = client.Reports.GenerateTokenInGroup(GroupId, report.Id, generateTokenRequestParameters);

// Generate Embed Configuration.
var embedConfig = new EmbedConfig()
{
    EmbedToken = tokenResponse,
    EmbedUrl = report.EmbedUrl,
    Id = report.Id
};
```

## <a name="step-4---load-an-item-using-javascript"></a>4. Adım: JavaScript kullanarak öğe yükleme
JavaScript kullanarak web sayfanızdaki bir div öğesine pano yükleyebilirsiniz. Bu örnekte EmbedConfig/TileEmbedConfig modelinin yanı sıra pano, kutucuk veya rapor görünümleri kullanılmaktadır. JavaScript API kullanan tam bir örnek için [Microsoft Power BI Embedded Örneği](https://microsoft.github.io/PowerBI-JavaScript/demo)'ni kullanabilirsiniz.

Bu uygulama örneği [Kuruluşunuz için ekleme örneği](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data) içinde mevcuttur.

**Views\Home\EmbedDashboard.cshtml**

```
<script src="~/scripts/powerbi.js"></script>
<div id="dashboardContainer"></div>
<script>
    // Read embed application token from Model
    var accessToken = "@Model.EmbedToken.Token";

    // Read embed URL from Model
    var embedUrl = "@Html.Raw(Model.EmbedUrl)";

    // Read dashboard Id from Model
    var embedDashboardId = "@Model.Id";

    // Get models. models contains enums that can be used.
    var models = window['powerbi-client'].models;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // This also includes settings and options such as filters.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'dashboard',
        tokenType: models.TokenType.Embed,
        accessToken: accessToken,
        embedUrl: embedUrl,
        id: embedDashboardId
    };

    // Get a reference to the embedded dashboard HTML element
    var dashboardContainer = $('#dashboardContainer')[0];

    // Embed the dashboard and display it within the div container.
    var dashboard = powerbi.embed(dashboardContainer, config);
</script>
```

**Views\Home\EmbedTile.cshtml**

```
<script src="~/scripts/powerbi.js"></script>
<div id="tileContainer"></div>
<script>
    // Read embed application token from Model
    var accessToken = "@Model.EmbedToken.Token";

    // Read embed URL from Model
    var embedUrl = "@Html.Raw(Model.EmbedUrl)";

    // Read tile Id from Model
    var embedTileId = "@Model.Id";

    // Read dashboard Id from Model
    var embedDashboardeId = "@Model.dashboardId";

    // Get models. models contains enums that can be used.
    var models = window['powerbi-client'].models;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // This also includes settings and options such as filters.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'tile',
        tokenType: models.TokenType.Embed,
        accessToken: accessToken,
        embedUrl: embedUrl,
        id: embedTileId,
        dashboardId: embedDashboardeId
    };

    // Get a reference to the embedded tile HTML element
    var tileContainer = $('#tileContainer')[0];

    // Embed the tile and display it within the div container.
    var tile = powerbi.embed(tileContainer, config);
</script>
```

**Views\Home\EmbedReport.cshtml**

```
<script src="~/scripts/powerbi.js"></script>
<div id="reportContainer"></div>
<script>
    // Read embed application token from Model
    var accessToken = "@Model.EmbedToken.Token";

    // Read embed URL from Model
    var embedUrl = "@Html.Raw(Model.EmbedUrl)";

    // Read report Id from Model
    var embedReportId = "@Model.Id";

    // Get models. models contains enums that can be used.
    var models = window['powerbi-client'].models;

    // Embed configuration used to describe the what and how to embed.
    // This object is used when calling powerbi.embed.
    // This also includes settings and options such as filters.
    // You can find more information at https://github.com/Microsoft/PowerBI-JavaScript/wiki/Embed-Configuration-Details.
    var config = {
        type: 'report',
        tokenType: models.TokenType.Embed,
        accessToken: accessToken,
        embedUrl: embedUrl,
        id: embedReportId,
        permissions: models.Permissions.All,
        settings: {
            filterPaneEnabled: true,
            navContentPaneEnabled: true
        }
    };

    // Get a reference to the embedded report HTML element
    var reportContainer = $('#reportContainer')[0];

    // Embed the report and display it within the div container.
    var report = powerbi.embed(reportContainer, config);
</script>
```

## <a name="next-steps"></a>Sonraki adımlar
GitHub üzerindeki örnek uygulamayı gözden geçirebilirsiniz. Yukarıdaki örnekler de bu örneği temel almaktadır. Daha fazla bilgi için bkz. [Kuruluşunuz için ekleme örneği](https://github.com/Microsoft/PowerBI-Developer-Samples/tree/master/App%20Owns%20Data).

JavaScript API hakkında daha fazla bilgi için bkz. [Power BI JavaScript API'si](https://github.com/Microsoft/PowerBI-JavaScript).

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

