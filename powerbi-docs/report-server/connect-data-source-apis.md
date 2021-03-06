---
title: PowerShell ile veri kaynağı bağlantı dizelerini değiştirme
description: PowerShell - Power BI Rapor Sunucusu'nda API'leri kullanarak veri kaynağı bağlantı dizelerini değiştirin.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: how-to
ms.date: 10/26/2020
ms.openlocfilehash: b7f431ba6b8f559380916c17689d0eab74a0c9a7
ms.sourcegitcommit: 7ed995eed0fd6e718748accf87bae384211cd95d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2021
ms.locfileid: "99044322"
---
# <a name="change-data-source-connection-strings-in-power-bi-reports-with-powershell---power-bi-report-server"></a>PowerShell - Power BI Rapor Sunucusu ile Power BI raporlarını kullanarak veri kaynağı bağlantı dizelerini değiştirin


Power BI Rapor Sunucusu Ekim 2020 sürümü ile başlayarak, DirectQuery ve yenileme için Power BI raporların bağlantılarını güncelleştirme özelliğini etkinleştirdik.

> [!IMPORTANT]
> Ayrıca bu özellik, önceki sürümlerde özelliği ayarlama yönteminizle ilgili yeni bir değişikliktir. Power BI Rapor Sunucusu’nun Ekim 2020’den önceki bir sürümünü kullanıyorsanız bkz. [PowerShell - Ekim 2020’den önceki bir Power BI Rapor Sunucusu sürümü ile Power BI raporlarını kullanarak veri kaynağı bağlantı dizelerini değiştirme](connect-data-source-apis-pre-oct-2020.md)

## <a name="prerequisites"></a>Önkoşullar:
- Power BI Rapor Sunucusu Ekim 2020 veya sonraki bir sürümünü indirin [Power BI rapor sunucusu için Power BI Desktop](https://powerbi.microsoft.com/report-server/).
- **Gelişmiş veri kümesi meta verileri** etkinken rapor sunucusu için en iyi duruma getirilmiş Power BI Desktop 2020 Ekim veya sonraki sürümü ile kaydedilmiş bir rapor.
- Parametreli hale getirilmiş bağlantıları kullanan bir rapor. Yalnızca parametreli hale getirilmiş bağlantılara ve veritabanlarına sahip raporlar yayımlandıktan sonra güncelleştirilebilir.
- Bu örnekte, Reporting Services PowerShell araçları kullanılmaktadır. Yeni REST API’lerini kullanarak da aynı sonucu elde edebilirsiniz.

## <a name="create-a-report-with-parameterized-connections"></a>Parametreli hale getirilmiş bağlantılara sahip raporlar oluşturma
    
1. Bir sunucuya SQL Server bağlantısı oluşturma. Aşağıdaki örnekte, localhost’u ReportServer adlı bir veritabanına bağlayıp ExecutionLog’dan veri çekiyoruz.

    :::image type="content" source="media/connect-data-source-apis/sql-server-connect-database.png" alt-text="SQL Server veritabanına bağlanma":::

    Bu noktada M sorgusu aşağıdaki gibi görünür:

    ```
    let
        Source = Sql.Database("localhost", "ReportServer"),
        dbo_ExecutionLog3 = Source{[Schema="dbo",Item="ExecutionLog3"]}[Data]
    in
        dbo_ExecutionLog3
    ```

2. Power Query Düzenleyicisi şeridinde **Parametreleri Yönet**’i seçin.

    :::image type="content" source="media/connect-data-source-apis/power-query-manage-parameters.png" alt-text="Parametreleri Yönet’i seçme":::

1.  servername ve databasename için parametreler oluşturun.

    :::image type="content" source="media/connect-data-source-apis/report-server-manage-parameters.png" alt-text="Parametreleri Yönet, servername ve databasename ayarlama.":::


3. Sorguyu ilk bağlantı için düzenleyip databasename ve servername öğelerini eşleyin.

    :::image type="content" source="media/connect-data-source-apis/report-server-map-database-server.png" alt-text="Sunucu ve Veritabanı adını eşleme":::

    Sorgu şimdi şu şekilde görünür:

    ```
    let
        Source = Sql.Database(ServerName, Databasename),
        dbo_ExecutionLog3 = Source{[Schema="dbo",Item="ExecutionLog3"]}[Data]
    in
        dbo_ExecutionLog3
    ```
    
    4. Bu raporu sunucuda yayımlayın. Bu örnekte rapor executionlogparameter olarak adlandırılmıştır. Aşağıdaki resim, bir veri kaynağı yönetim sayfası örneğidir.

    :::image type="content" source="media/connect-data-source-apis/report-server-manage-data-source-credentials.png" alt-text="Veri kaynağı yönetim sayfası.":::

## <a name="update-parameters-using-the-powershell-tools"></a>PowerShell araçlarını kullanarak parametreleri güncelleştirme

1. PowerShell’i açın ve [https://github.com/microsoft/ReportingServicesTools](https://github.com/microsoft/ReportingServicesTools) sayfasındaki yönergeleri izleyerek Reporting Services araçlarının en son sürümünü yükleyin.
    
2.  Raporun parametresini almak için, aşağıdaki PowerShell çağrısını kullanarak yeni REST DataModelParameters API’sini kullanın:

    ```powershell
    Get-RsRestItemDataModelParameters '/executionlogparameter'

        Name         Value
        ----         -----
        ServerName   localhost
        Databasename ReportServer
    ```

3. Bu çağrının sonucunu bir değişkene kaydediyoruz:

    ```powershell
    $parameters = Get-RsRestItemDataModelParameters '/executionlogparameter'
    ```

4. Bu değişken, değiştirmemiz gereken değerlerle güncelleştirilir.
5. Bu çağrının sonucunu bir değişkene kaydediyoruz:

    ```powershell
    $parameters[0].Value = 'myproductionserver'
    $parameters[1].Value = 'myproductiondatabase'
    ```

6. Güncelleştirilmiş değerlerle, sunucudaki değerleri güncelleştirmek için `Set-RsRestItemDataModelParameters` commandlet’ini kullanabiliriz:

    ```powershell
    Set-RsRestItemDataModelParameters -RsItem '/executionlogparameter' -DataModelParameters $parameters
    ```

7. Parametreler güncelleştirildiğinde sunucu, parametrelere bağlı tüm veri kaynaklarını güncelleştirir. **Veri kaynağını düzenle** iletişim kutusuna geri dönerek, güncelleştirilmiş sunucu ve veritabanının kimlik bilgilerini ayarlayabilmeniz gerekir.

    :::image type="content" source="media/connect-data-source-apis/report-server-manage-executionlogparameter-dialog.png" alt-text="Güncelleştirilmiş sunucu ve veritabanı için kimlik bilgilerini ayarlama.":::

## <a name="next-steps"></a>Sonraki adımlar

[Power BI Rapor Sunucusu'nda sayfalandırılmış rapor veri kaynakları](connect-data-sources.md) 

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
