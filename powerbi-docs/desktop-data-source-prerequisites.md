---
title: Power BI veri kaynağı önkoşulları
description: Power BI veri kaynağı önkoşulları
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/29/2020
ms.author: davidi
LocalizationGroup: Connect to data
ms.openlocfilehash: c3ccbe6ad87a813185943845431fa1a859b09a76
ms.sourcegitcommit: 8b300151b5c59bc66bfef1ca2ad08593d4d05d6a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2020
ms.locfileid: "76888443"
---
# <a name="power-bi-data-source-prerequisites"></a>Power BI veri kaynağı önkoşulları
Power BI, nesneler için her veri sağlayıcısının belirli bir sürümünü destekler. Power BI ile kullanılabilen veri kaynakları hakkında daha fazla bilgi için bkz. [Veri kaynakları](desktop-data-sources.md). Aşağıdaki tabloda bu gereksinimlere yer verilmiştir.

| Veri kaynağı | Sağlayıcı | Minimum sağlayıcı sürümü | Minimum veri kaynağı sürümü | Desteklenen veri kaynağı nesneleri | İndirme bağlantısı |
| --- | --- | --- | --- | --- | --- |
| SQL Server |ADO.net (.Net Framework'e yerleşik) |.NET Framework 3.5 (yalnızca) |SQL Server 2005 |Tablolar/Görünümler, Skaler işlevler, Tablo işlevleri |.NET Framework 3.5 veya sonraki sürümlerle birlikte gelir |
| Erişim |Microsoft Access Veritabanı Altyapısı (ACE) |ACE 2010 SP1 |Kısıtlama yok |Tablolar/Görünümler |[İndirme bağlantısı](https://go.microsoft.com/fwlink/?linkid=285987&clcid=0x409) |
| Excel (yalnızca .xls dosyaları) (bkz. 1. Not) |Microsoft Access Veritabanı Altyapısı (ACE) |ACE 2010 SP1 |Kısıtlama yok |Tablolar, Sayfalar |[İndirme bağlantısı](https://go.microsoft.com/fwlink/?linkid=285987&clcid=0x409) |
| Oracle (bkz. 2. Not) |ODP.NET |ODAC 11.2 Sürüm 5 (11.2.0.3.20) |9.x |Tablolar/Görünümler |[İndirme bağlantısı](https://go.microsoft.com/fwlink/?linkid=272376&clcid=0x409) |
| | System.Data.OracleClient (.NET Framework’te yerleşik) |.NET Framework 3.5 |9.x |Tablolar/Görünümler |.NET Framework 3.5 veya sonraki sürümlerle birlikte gelir |
| IBM DB2 |IBM ADO.Net istemcisi (IBM veri sunucusu sürücü paketine dahil) |10.1 |9.1+ |Tablolar/Görünümler |[İndirme bağlantısı](https://go.microsoft.com/fwlink/?linkid=274911&clcid=0x409) |
| MySQL |Connector/Net |6.6.5 |5.1 |Tablolar/Görünümler, Skaler işlevler |[İndirme bağlantısı](https://go.microsoft.com/fwlink/?linkid=278885&clcid=0x409) |
| PostgreSQL |NPGSQL ADO.NET sağlayıcısı |2.0.12 |9.4 |Tablolar/Görünümler |[İndirme bağlantısı](https://go.microsoft.com/fwlink/?linkid=282716&clcid=0x409) |
| Teradata |Teradata için .NET Veri Sağlayıcısı |14 |12 |Tablolar/Görünümler |[İndirme bağlantısı](https://go.microsoft.com/fwlink/?linkid=278886&clcid=0x409) |
| SAP Sybase SQL Anywhere |.NET 3.5 için iAnywhere.Data.SQLAnywhere |16 |16 |Tablolar/Görünümler |[İndirme bağlantısı](https://go.microsoft.com/fwlink/?linkid=324846) |

>[!NOTE]
>.xlsx uzantılı Excel dosyaları için ayrı bir sağlayıcı yüklenmesi gerekmez.

>[!NOTE]
>Oracle sağlayıcıları için Oracle istemci yazılımı (8.1.7 veya sonraki sürümler) da gereklidir.
> 
> 

