---
title: PowerShell - Power BI Rapor Sunucusu Ekim 2020 öncesi sürüm ile veri kaynağı bağlantı dizelerini değiştirme
description: Power BI Rapor Sunucusu Ekim 2020 öncesi sürümde API’leri kullanarak veri kaynağı bağlantı dizelerini değiştirme.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: how-to
ms.date: 10/26/2020
ms.openlocfilehash: f0dd30e721d8325fdbfd8b562083fbedef2af9c0
ms.sourcegitcommit: 7ed995eed0fd6e718748accf87bae384211cd95d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2021
ms.locfileid: "99044207"
---
# <a name="change-data-source-connection-strings-in-power-bi-reports-with-powershell---power-bi-report-server-pre-october-2020"></a>PowerShell - Power BI Rapor Sunucusu Ekim 2020 öncesi sürüm ile Power BI raporlarını kullanarak veri kaynağı bağlantı dizelerini değiştirin


PowerShell'i kullanıp gerekli API'lerle etkileşim kurarak Power BI Rapor Sunucusu'nda barındırılan Power BI raporlarının veri kaynağı bağlantı dizelerini değiştirebilirsiniz. 

> [!IMPORTANT]
> En son Power BI Rapor Sunucusu sürümünü kullanıyorsanız, bkz. [PowerShell-Power BI rapor sunucusu ile Power BI raporlardaki veri kaynağı bağlantı dizelerini değiştirme](connect-data-source-apis.md).

> [!NOTE]
> Şu anda bu işlevsellik yalnızca DirectQuery’de çalışır. İçeri aktarma ve veri yenileme desteği yakında sağlanacaktır.

1. Power BI Rapor Sunucusu PowerShell komutlarını yükleyin. Komutlar ve yükleme yönergeleri için bkz. [https://github.com/Microsoft/ReportingServicesTools](https://github.com/Microsoft/ReportingServicesTools). 

    Aşağıdaki komutu kullanarak `ReportingServicesTools` modülünü doğrudan [PowerShell Galerisi](https://www.powershellgallery.com/packages/ReportingServicesTools/)'nden yükleyin.

    ```powershell
    Install-Module ReportingServicesTools
    ```

2. Power BI dosyası için mevcut veri kaynağı bilgilerini PowerShell komutları aracılığıyla getirin:

    ```powershell
    $dataSources = Get-RsRestItemDataSource -RsItem '/MyPbixReport'
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
    $dataSources[0].DataModelDataSource.Username = 'domain\user'
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
