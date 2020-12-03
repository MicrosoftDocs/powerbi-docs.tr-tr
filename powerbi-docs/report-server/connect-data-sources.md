---
title: Power BI Rapor Sunucusu'nda sayfalandırılmış rapor veri kaynakları
description: Sayfalandırılmış raporların (.rdl) Power BI Rapor Sunucusu’nda bağlanabileceği veri kaynakları hakkında bilgi edinin.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 06/26/2020
ms.openlocfilehash: 4559995baa7d3e0b5796ca6076687c26c4a0854d
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96415393"
---
# <a name="paginated-report-data-sources--in-power-bi-report-server"></a>Power BI Rapor Sunucusu'nda sayfalandırılmış rapor veri kaynakları
Power BI Rapor Sunucusu’ndaki Reporting Services sayfalandırılmış raporları, SQL Server Reporting Services’tekilerle aynı veri kaynaklarını destekler. [Reporting Services tarafından desteklenen veri kaynakları](/sql/reporting-services/report-data/data-sources-supported-by-reporting-services-ssrs) listesine bakın.

## <a name="connect-to-oracle-data-sources-with-useinstalleduiculture"></a>UseInstalledUICulture ile Oracle veri kaynaklarına bağlanma

Oracle veri kaynaklarına bağlanmak için Power BI Rapor Sunucusu NLS’den bağımsız olan .NET için Oracle Veri Sağlayıcısı’nı (ODP.NET) kullanır.

Varsayılan olarak rapor sunucusu ODP.NET’i yüklerken ilk istemcinin UI kültürünü kullanır.  Sonuç olarak, hizmet yeniden başlatılana kadar rapor sunucusundan Oracle’a yapılan sonraki tüm bağlantılar bu ilk UI kültüründe olacaktır.  Bu yaklaşım, UI kültürü biçimlendirmesindeki uyuşmazlıklardan dolayı rapor işlenirken sorunlara neden olabilir.

Power BI Rapor Sunucusu’nda daha iyi bir deneyim sağlamak için UseInstalledUICulture adlı bir yapılandırma ayarını kullanıma sunduk. UseInstalledUICulture True olarak ayarlandığında, rapor sunucusu ODP.NET’i ilk istemcinin kültürü yerine her zaman sunucunu UI Kültüründe yükler.
Bu ayar Mart 2020 Hizmet Sürümünden başlayarak Power BI Rapor Sunucusu’nda kullanıma sunulmuştur.

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