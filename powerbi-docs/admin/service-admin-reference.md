---
title: Yöneticiler için PowerShell cmdlet'leri, REST API'ler ve .NET Client kitaplıkları
description: Power BI'ı betikler ve programlama API'leri aracılığıyla yönetmenin yolları hakkında bilgi edinin.
author: kfollis
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 09/09/2019
ms.author: kfollis
LocalizationGroup: Administration
ms.openlocfilehash: e1c95c330687131a29753359f5223e096bddab1d
ms.sourcegitcommit: e9cd61eaa66eda01cc159251d7936a455c55bd84
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2020
ms.locfileid: "86952628"
---
# <a name="powershell-cmdlets-rest-apis-and-net-client-library-for-power-bi-administration"></a>Power BI yöneticisi için PowerShell cmdlet'leri, REST API'ler ve .NET Client kitaplığı
Power BI, yöneticilerin PowerShell cmdlet'leriyle yaygın görevler için betik oluşturmasına olanak tanır. Ayrıca yönetim çözümleri gelişmek için REST API'leri de gösterir ve bir .NET istemci kitaplığı sağlar. Bu konu başlığı altında, cmdlet'lerin listesiyle bunlara karşılık gelen API'ler ve REST API uç noktası gösterilir. Daha fazla bilgi için bkz.

- PowerShell [indirmesi](https://www.powershellgallery.com/packages/MicrosoftPowerBIMgmt/) ve [belgeleri](https://docs.microsoft.com/powershell/power-bi/overview?view=powerbi-ps)
- REST API [belgeleri](https://docs.microsoft.com/rest/api/power-bi/admin)
- .NET İstemci kitaplığını [indirme](https://www.nuget.org/packages/Microsoft.PowerBI.Api/)

> Yönetim için kiracıda çalışmak üzere `-Scope Organization` ile aşağıdaki cmdlet’ler çağrılmalıdır.

| **Cmdlet adı** | **Diğer adlar** | **API** | **REST API uç noktası** | **Açıklama** |
| --- | --- | --- | --- | --- |
| `Get-PowerBIDatasource` | Yok | `Datasets_GetDataSourcesAsAdmin` | /v1.0/myorg/admin/datasets/{datasetkey}/datasources | Belirli bir veri kümesi için veri kaynaklarını alır. |
| `Get-PowerBIDataset` | Yok | `Datasets_GetDatasetsAsAdmin` | /v1.0/myorg/admin/datasets | Power BI kiracısındaki veri kümelerinin tam listesini alır. |
| `Get-PowerBIWorkspace` | `Get-PowerBIGroup` | `Groups_GetGroupsAsAdmin` | /v1.0/myorg/admin/groups | Power BI kiracısındaki çalışma alanlarının tam listesini alır. |
| `Add-PowerBIWorkspaceUser` | `Add-PowerBIGroupUser` | `Groups_AddUserAsAdmin` | /v1.0/myorg/admin/groups/{groupId}/users | Kullanıcıyı belirli bir çalışma alanına üye olarak ekler. |
| `Remove-PowerBIWorkspaceUser` | `Remove-PowerBIGroupUser` | `Groups_DeleteUserAsAdmin` | /v1.0/myorg/admin/groups/{groupId}/users/{user} | Kullanıcıyı belirli bir çalışma alanının üyelik listesinden kaldırır. |
| `Restore-PowerBIWorkspace` |`Restore-PowerBIGroup` | `Groups_RestoreDeletedGroupAsAdmin` | /v1.0/myorg/admin/groups/{groupId}/restore | Silinen çalışma alanına geri yükler. |
| `Set-PowerBIWorkspace` |`Set-PowerBIGroup` | `Groups_UpdateGroupAsAdmin` | /v1.0/myorg/admin/groups/{groupId} | Belirli bir çalışma alanının özelliklerini güncelleştirir. |
| `Get-PowerBIDataset -WorkspaceId` | Yok | `Groups_GetDatasetsAsAdmin` | /v1.0/myorg/admin/groups/{group\_id}/datasets | Belirli bir çalışma alanı içindeki veri kümelerini alır. |
| `Get-PowerBIReport` | Yok | `Reports_GetReportsAsAdmin` | /v1.0/myorg/admin/reports | Power BI kiracısındaki raporların tam listesini alır. |
| `Get-PowerBIDashboard` | Yok | `Dashboards_GetDashboardsAsAdmin` | /v1.0/myorg/admin/dashboards | Power BI kiracısındaki panoların tam listesini alır. |
| `Get-PowerBIDashboard -WorkspaceId` | Yok | `Groups_GetDashboardsAsAdmin` | /v1.0/myorg/admin/groups/{group\_id}/dashboards | Belirli bir çalışma alanı içindeki panoları alır. |
| `Get-PowerBITile` | `Get-PowerBIDashboardTile` | `Dashboards_GetTilesAsAdmin` | /v1.0/myorg/admin/dashboards/{dashboard\_id}/tiles | Belirli bir panonun kutucuklarını alır. |
| `Get-PowerBIReport` | Yok | `Groups_GetReportsAsAdmin` | /v1.0/myorg/admin/groups/{group\_id}/reports | Belirli bir çalışma alanı içindeki raporları alır. |
| `Get-PowerBIImport` | Yok | `Imports_GetImportsAsAdmin` | /v1.0/myorg/admin/imports | Power BI kiracısındaki içeri aktarma işlemlerinin tam listesini alır. |
| `Connect-PowerBIServiceAccount` | `Login-PowerBI` &  `Login-PowerBIServiceAccount` | Yok | Yok | Power BI'da oturum açın ve oturum başlatın. |
| `Disconnect-PowerBIServiceAccount` | `Logout-PowerBI` & `Logout-PowerBIServiceAccount` | Yok | Yok | Power BI oturumunu kapatın ve mevcut oturumu kapatın. |
| `Invoke-PowerBIRestMethod`| Yok | Yok | Yok | Power BI'a rastgele REST API çağrıları gönderin. |
| `Get-PowerBIAccessToken`| Yok | Yok | Yok | Oturumda Power BI erişim belirtecini alın. |
| `Resolve-PowerBIError`| Yok | Yok | Yok | Başarısız cmdlet çağrıları için ayrıntılı hata bilgilerini alın. |
