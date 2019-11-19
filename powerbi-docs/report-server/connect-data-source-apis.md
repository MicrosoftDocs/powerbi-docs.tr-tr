---
title: PowerShell ile veri kaynağı bağlantı dizelerini değiştirme
description: PowerShell - Power BI Rapor Sunucusu'nda API'leri kullanarak veri kaynağı bağlantı dizelerini değiştirin.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 10/24/2019
ms.author: maggies
ms.openlocfilehash: 77716514ffbb6dc8d3f128ada85276b46bf7af05
ms.sourcegitcommit: 17f45a81b0dcbf9e3f1fb2a551584170baecd320
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2019
ms.locfileid: "72923677"
---
# <a name="change-data-source-connection-strings-in-power-bi-reports-with-powershell---power-bi-report-server"></a>PowerShell - Power BI Rapor Sunucusu ile Power BI raporlarını kullanarak veri kaynağı bağlantı dizelerini değiştirin

PowerShell'de API'leri kullanarak Power BI Rapor Sunucusu’ndaki veri kaynağı bağlantı dizelerini değiştirebilirsiniz. 

1. Power BI Rapor Sunucusu PowerShell komutlarını yükleyin. Komutlar ve yükleme yönergeleri için bkz. [https://github.com/Microsoft/ReportingServicesTools](https://github.com/Microsoft/ReportingServicesTools). 

2. Power BI dosyası için mevcut veri kaynağı bilgilerini PowerShell komutları aracılığıyla getirin:

    ```powershell
    Get-RsRestItemDataSource -RsItem '/MyPbixReport'
    ```

    Power BI raporunda bulunan ilk veri kaynağına ilişkin bilgileri görüntülemek için: 

    ```powershell
    $dataSources[0]
    ```

3. Bağlantı ve kimlik bilgilerini gerektiği şekilde güncelleştirin. Bağlantı dizesi güncelleştiriliyorsa ve veri kaynağı depolanan kimlik bilgilerini kullanıyorsa, hesap parolasını sağlamanız gerekir. 

    Veri kaynağı bağlantı dizesini güncelleştirmek için:

    ```powershell
    $dataSources[0].ConnectionString = 'data source=myCatalogServer;initial catalog=ReportServer;persist security info=False' 
    ```

    Veri kaynağı kimlik bilgisi türünü değiştirmek için:

    ```powershell
    $dataSources[0].DataModelDataSource.AuthType = 'Integrated'
    ```

    Veri kaynağı kullanıcı adını/parolasını değiştirmek için:

    ```powershell
    $dataSources[0].DataModelDataSource.Username = 'domain\user
    ```
    ```powershell
    $dataSources[0].DataModelDataSource.Secret = 'password'
    ```

4. Güncelleştirilmiş kimlik bilgilerini sunucuya geri kaydedin.

    ```powershell
    Set-RsRestItemDataSource -RsItem '/MyPbixReport' -RsItemType 'PowerBIReport' -DataSources $dataSources
    ```

## <a name="next-steps"></a>Sonraki adımlar

[Power BI Rapor Sunucusu'nda sayfalandırılmış rapor veri kaynakları](connect-data-sources.md) 

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)

