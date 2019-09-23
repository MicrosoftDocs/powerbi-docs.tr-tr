---
title: Yöneticiler için PowerShell cmdlet'leri, REST API'leri ve .NET SDK'sı
description: Power BI'ı betikler ve programlama API'leri aracılığıyla yönetmenin yolları hakkında bilgi edinin.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 09/09/2019
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 33845247f289ba41e7ea04ba5194c091a718c5b9
ms.sourcegitcommit: a97c0c34f888e44abf4c9aa657ec9463a32be06f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2019
ms.locfileid: "71074626"
---
# <a name="powershell-cmdlets-rest-apis-and-net-sdk-for-power-bi-administration"></a>Power BI yönetimi için PowerShell cmdlet'leri, REST API'leri ve .NET SDK'sı
Power BI, yöneticilerin PowerShell cmdlet'leriyle yaygın görevler için betik oluşturmasına olanak tanır. Ayrıca yönetim çözümleri gelişmek için REST API'leri de gösterir ve bir .NET SDK'sı sağlar. Bu konu başlığı altında, cmdlet'lerin listesiyle bunlara karşılık gelen SDK yöntemi ve REST API uç noktası gösterilir. Daha fazla bilgi için bkz.

- PowerShell [indirmesi](https://www.powershellgallery.com/packages/MicrosoftPowerBIMgmt/) ve [belgeleri](https://docs.microsoft.com/powershell/power-bi/overview?view=powerbi-ps)
- REST API [belgeleri](https://docs.microsoft.com/rest/api/power-bi/admin)
- .NET SDK [indirmesi](https://www.nuget.org/packages/Microsoft.PowerBI.Api/)

> Yönetim için kiracıda çalışmak üzere `-Scope Organization` ile aşağıdaki cmdlet’ler çağrılmalıdır.

| **Cmdlet adı** | **Diğer adlar** | **SDK yöntemi** | **REST API uç noktası** | **Açıklama** |
| --- | --- | --- | --- | --- |
| `Get-PowerBIDatasource` | YOK | `Datasets_GetDataSourcesAsAdmin` | /v1.0/myorg/admin/datasets/{datasetkey}/datasources | Belirli bir veri kümesi için veri kaynaklarını alır. |
| `Get-PowerBIDataset` | YOK | `Datasets_GetDatasetsAsAdmin` | /v1.0/myorg/admin/datasets | Power BI kiracısındaki veri kümelerinin tam listesini alır. |
| `Get-PowerBIWorkspace` | `Get-PowerBIGroup` | `Groups_GetGroupsAsAdmin` | /v1.0/myorg/admin/groups | Power BI kiracısındaki çalışma alanlarının tam listesini alır. |
| `Add-PowerBIWorkspaceUser` | `Add-PowerBIGroupUser` | `Groups_AddUserAsAdmin` | /v1.0/myorg/admin/groups/{groupId}/users | Kullanıcıyı belirli bir çalışma alanına üye olarak ekler. |
| `Remove-PowerBIWorkspaceUser` | `Remove-PowerBIGroupUser` | `Groups_DeleteUserAsAdmin` | /v1.0/myorg/admin/groups/{groupId}/users/{user} | Kullanıcıyı belirli bir çalışma alanının üyelik listesinden kaldırır. |
| `Restore-PowerBIWorkspace` |`Restore-PowerBIGroup` | `Groups_RestoreDeletedGroupAsAdmin` | /v1.0/myorg/admin/groups/{groupId}/restore | Silinen çalışma alanına geri yükler. |
| `Set-PowerBIWorkspace` |`Set-PowerBIGroup` | `Groups_UpdateGroupAsAdmin` | /v1.0/myorg/admin/groups/{groupId} | Belirli bir çalışma alanının özelliklerini güncelleştirir. |
| `Get-PowerBIDataset -WorkspaceId` | YOK | `Groups_GetDatasetsAsAdmin` | /v1.0/myorg/admin/groups/{group\_id}/datasets | Belirli bir çalışma alanı içindeki veri kümelerini alır. |
| `Get-PowerBIReport` | YOK | `Reports_GetReportsAsAdmin` | /v1.0/myorg/admin/reports | Power BI kiracısındaki raporların tam listesini alır. |
| `Get-PowerBIDashboard` | YOK | `Dashboards_GetDashboardsAsAdmin` | /v1.0/myorg/admin/dashboards | Power BI kiracısındaki panoların tam listesini alır. |
| `Get-PowerBIDashboard -WorkspaceId` | YOK | `Groups_GetDashboardsAsAdmin` | /v1.0/myorg/admin/groups/{group\_id}/dashboards | Belirli bir çalışma alanı içindeki panoları alır. |
| `Get-PowerBITile` | `Get-PowerBIDashboardTile` | `Dashboards_GetTilesAsAdmin` | /v1.0/myorg/admin/dashboards/{dashboard\_id}/tiles | Belirli bir panonun kutucuklarını alır. |
| `Get-PowerBIReport` | YOK | `Groups_GetReportsAsAdmin` | /v1.0/myorg/admin/groups/{group\_id}/reports | Belirli bir çalışma alanı içindeki raporları alır. |
| `Get-PowerBIImport` | YOK | `Imports_GetImportsAsAdmin` | /v1.0/myorg/admin/imports | Power BI kiracısındaki içeri aktarma işlemlerinin tam listesini alır. |
| `Connect-PowerBIServiceAccount` | `Login-PowerBI` &  `Login-PowerBIServiceAccount` | YOK | YOK | Power BI'da oturum açın ve oturum başlatın. |
| `Disconnect-PowerBIServiceAccount` | `Logout-PowerBI` & `Logout-PowerBIServiceAccount` | YOK | YOK | Power BI oturumunu kapatın ve mevcut oturumu kapatın. |
| `Invoke-PowerBIRestMethod`| YOK | YOK | YOK | Power BI'a rastgele REST API çağrıları gönderin. |
| `Get-PowerBIAccessToken`| YOK | YOK | YOK | Oturumda Power BI erişim belirtecini alın. |
| `Resolve-PowerBIError`| YOK | YOK | YOK | Başarısız cmdlet çağrıları için ayrıntılı hata bilgilerini alın. |
