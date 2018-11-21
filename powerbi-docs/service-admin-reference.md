---
title: Yöneticiler için PowerShell cmdlet'leri, REST API'leri ve .NET SDK'sı
description: Power BI'ı betikler ve programlama API'leri aracılığıyla yönetmenin yolları hakkında bilgi edinin.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-admin
ms.topic: overview
ms.date: 06/25/2018
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 1ed4298e4ed4cddcdf965bd427c654cab6adf1e6
ms.sourcegitcommit: 46f1ba3f972f6e64bce05ad0fd527b27c49aedd6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52157023"
---
# <a name="powershell-cmdlets-rest-apis-and-net-sdk-for-power-bi-administration"></a>Power BI yönetimi için PowerShell cmdlet'leri, REST API'leri ve .NET SDK'sı
Power BI, yöneticilerin PowerShell cmdlet'leriyle yaygın görevler için betik oluşturmasına olanak tanır. Ayrıca yönetim çözümleri gelişmek için REST API'leri de gösterir ve bir .NET SDK'sı sağlar. Bu konu başlığı altında, cmdlet'lerin listesiyle bunlara karşılık gelen SDK yöntemi ve REST API uç noktası gösterilir. Daha fazla bilgi için bkz.

- PowerShell [indirmesi](https://www.powershellgallery.com/packages/MicrosoftPowerBIMgmt/) ve [belgeleri](https://docs.microsoft.com/powershell/power-bi/overview?view=powerbi-ps)
- REST API [belgeleri](https://docs.microsoft.com/rest/api/power-bi/admin)
- .NET SDK [indirmesi](https://www.nuget.org/packages/Microsoft.PowerBI.Api/)

| **Cmdlet adı** | **Diğer adlar** | **SDK yöntemi** | **REST API uç noktası** | **Açıklama** |
| --- | --- | --- | --- | --- |
| **Get-PowerBIDatasource** | YOK | Datasets\_GetDataSourcesAsAdmin | /v1.0/myorg/admin/datasets/{datasetkey}/datasources | Belirli bir veri kümesi için veri kaynaklarını alır. |
| **Get-PowerBIDataset** | YOK | Datasets\_GetDatasetsAsAdmin | /v1.0/myorg/admin/datasets | Power BI kiracısındaki veri kümelerinin tam listesini alır. |
| **Get-PowerBIWorkspace** | **Get-PowerBIGroup** | Groups\_GetGroupsAsAdmin | /v1.0/myorg/admin/groups | Power BI kiracısındaki çalışma alanlarının tam listesini alır. |
| **Add-PowerBIWorkspaceUser** | **Add-PowerBIGroupUser** |Groups\_AddUserAsAdmin | /v1.0/myorg/admin/groups/{groupId}/users | Kullanıcıyı belirli bir çalışma alanına üye olarak ekler. |
| **Remove-PowerBIWorkspaceUser** | **Remove-PowerBIGroupUser** | Groups\_DeleteUserAsAdmin | /v1.0/myorg/admin/groups/{groupId}/users/{user} | Kullanıcıyı belirli bir çalışma alanının üyelik listesinden kaldırır. |
| **Restore-PowerBIWorkspace** |**Restore-PowerBIGroup** | Groups\_RestoreDeletedGroupAsAdmin | /v1.0/myorg/admin/groups/{groupId}/restore | Silinen çalışma alanına geri yükler. |
| **Set-PowerBIWorkspace** |**Set-PowerBIGroup** | Groups\_UpdateGroupAsAdmin | /v1.0/myorg/admin/groups/{groupId} | Belirli bir çalışma alanının özelliklerini güncelleştirir. |
| **Get-PowerBIDataset -WorkspaceId** | YOK | Groups\_GetDatasetsAsAdmin | /v1.0/myorg/admin/groups/{group\_id}/datasets | Belirli bir çalışma alanı içindeki veri kümelerini alır. |
| **Export-PowerBIReport** | YOK | Reports\_ExportReportAsAdmin | YOK | Belirli bir raporu yerel dosyaya aktarır. |
| **Get-PowerBIReport** | YOK | Reports\_GetReportsAsAdmin | /v1.0/myorg/admin/reports | Power BI kiracısındaki raporların tam listesini alır. |
| **Get-PowerBIDashboard** | YOK | Dashboards\_GetDashboardsAsAdmin | /v1.0/myorg/admin/dashboards | Power BI kiracısındaki panoların tam listesini alır. |
| **Get-PowerBIDashboard** | YOK | Groups\_GetDashboardsAsAdmin | /v1.0/myorg/admin/groups/{group\_id}/dashboards | Belirli bir çalışma alanı içindeki panoları alır. |
| **Get-PowerBITile** | **Get-PowerBIDashboardTile** | Dashboards\_GetTilesAsAdmin | /v1.0/myorg/admin/dashboards/{dashboard\_id}/tiles | Belirli bir panonun kutucuklarını alır. |
| **Get-PowerBIReport** | YOK | Groups\_GetReportsAsAdmin | /v1.0/myorg/admin/groups/{group\_id}/reports | Belirli bir çalışma alanı içindeki raporları alır. |
| **Get-PowerBIImport** | YOK | Imports\_GetImportsAsAdmin | /v1.0/myorg/admin/imports | Power BI kiracısındaki içeri aktarma işlemlerinin tam listesini alır. |
| **Connect-PowerBIServiceAccount** | **Login-PowerBI** &  **Login-PowerBIServiceAccount** | YOK | YOK | Power BI'da oturum açın ve oturum başlatın. |
| **Disconnect-PowerBIServiceAccount** | **Logout-PowerBI** & **Logout-PowerBIServiceAccount** | YOK | YOK | Power BI oturumunu kapatın ve mevcut oturumu kapatın. |
| **Invoke-PowerBIRestMethod**| YOK | YOK | YOK | Power BI'a rastgele REST API çağrıları gönderin. |
| **Get-PowerBIAccessToken**| YOK | YOK | YOK | Oturumda Power BI erişim belirtecini alın. |
| **Resolve-PowerBIError**| YOK | YOK | YOK | Başarısız cmdlet çağrıları için ayrıntılı hata bilgilerini alın. |