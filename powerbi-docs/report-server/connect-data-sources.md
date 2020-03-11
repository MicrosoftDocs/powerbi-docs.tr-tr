---
title: Power BI Rapor Sunucusu'nda sayfalandırılmış rapor veri kaynakları
description: Sayfalandırılmış raporların (.rdl) Power BI Rapor Sunucusu’nda bağlanabileceği veri kaynakları hakkında bilgi edinin.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 05/17/2018
ms.author: maggies
ms.openlocfilehash: 7cb5772e6ccdc1e4036d70f65a3a28210a4f6df1
ms.sourcegitcommit: d55d3089fcb3e78930326975957c9940becf2e76
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2020
ms.locfileid: "78260727"
---
# <a name="paginated-report-data-sources--in-power-bi-report-server"></a>Power BI Rapor Sunucusu'nda sayfalandırılmış rapor veri kaynakları
Power BI Rapor Sunucusu’ndaki Reporting Services sayfalandırılmış raporları, SQL Server Reporting Services’tekilerle aynı veri kaynaklarını destekler. [Reporting Services tarafından desteklenen veri kaynakları](https://docs.microsoft.com/sql/reporting-services/report-data/data-sources-supported-by-reporting-services-ssrs) listesine bakın.

## <a name="connect-to-oracle-data-sources-with-useinstalleduiculture"></a>UseInstalledUICulture ile Oracle veri kaynaklarına bağlanma

Oracle veri kaynaklarına bağlanmak için Power BI Rapor Sunucusu NLS’den bağımsız olan .NET için Oracle Veri Sağlayıcısı’nı (ODP.NET) kullanır.

Varsayılan olarak rapor sunucusu ODP.NET’i yüklerken ilk istemcinin UI kültürünü kullanır.  Sonuç olarak, hizmet yeniden başlatılana kadar rapor sunucusundan Oracle’a yapılan sonraki tüm bağlantılar bu ilk UI kültüründe olacaktır.  Bu yaklaşım, UI kültürü biçimlendirmesindeki uyuşmazlıklardan dolayı rapor işlenirken sorunlara neden olabilir.

Power BI Rapor Sunucusu’nda daha iyi bir deneyim sağlamak için UseInstalledUICulture adlı bir yapılandırma ayarını kullanıma sunduk. UseInstalledUICulture True olarak ayarlandığında, rapor sunucusu ODP.NET’i ilk istemcinin kültürü yerine her zaman sunucunu UI Kültüründe yükler.
Bu ayar Şubat Hizmet Sürümünden başlayarak Power BI Rapor Sunucusu’nda kullanıma sunulmuştur

Özelliği etkinleştirmek için ORACLE uzantı girdisi rsreportserver.config dosyasını aşağıda gösterildiği gibi değiştirin.
```xml
<Extension Name="ORACLE" Type="Microsoft.ReportingServices.DataExtensions.OracleClientConnectionWrapper,Microsoft.ReportingServices.DataExtensions">
    <Configuration>
        <UseInstalledUICulture>true</UseInstalledUICulture>
    </Configuration>
</Extension>
```

## <a name="next-steps"></a>Sonraki adımlar
Veri kaynağınıza bağlandığınıza göre artık [sayfalandırılmış rapor oluşturabilirsiniz](quickstart-create-paginated-report.md).  


Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
