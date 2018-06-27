---
title: Power BI Rapor Sunucusu'nda zamanlanmış yenileme ile ilgili sorunları giderme
description: Bu makalede, Power BI Rapor Sunucusu'nda zamanlanmış yenileme ile ilgili sorunları gidermek için kullanılabilecek kaynaklara yer verilmiştir.
author: markingmyname
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-report-server
ms.topic: conceptual
ms.date: 11/01/2017
ms.author: maghan
ms.openlocfilehash: a90f22c262a314b50981be94121e2573f9fe525a
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34296377"
---
# <a name="troubleshoot-scheduled-refresh-in-power-bi-report-server"></a>Power BI Rapor Sunucusu'nda zamanlanmış yenileme ile ilgili sorunları giderme
Bu makalede, Power BI Rapor Sunucusu'nda zamanlanmış yenileme ile ilgili sorunları gidermek için kullanılabilecek kaynaklara yer verilmiştir.

Karşılaşılan yeni sorunlar bu makaleye eklenerek, size yardımcı olmaya yönelik bilgilerin güncel kalması sağlanacaktır.

## <a name="common-issues"></a>Sık karşılaşılan sorunlar
Bir rapor için yenileme zamanlama sırasında daha yaygın olarak karşılaşabileceğiniz sorunlar aşağıda verilmiştir. 

### <a name="driver-related-problems"></a>Sürücüyle ilgili sorunlar
Farklı veri kaynaklarıyla başarılı bir şekilde bağlantı kurabilmek için 3. taraf sürücülere ihtiyaç duyabilirsiniz. Bu sürücüleri yalnızca Power BI Desktop uygulamasını kullandığınız bilgisayara değil rapor sunucusuna da yüklemeniz gerekir.

Sürücü hem 32 bit hem de 64 bit biçiminde olabilir. Power BI Rapor Sunucusu 64 bit olduğundan yüklenen sürücünün de 64 bit olması gerekir.

3. taraf sürücülerini yükleme ve yapılandırma hakkında ayrıntılı bilgi için lütfen üreticiye başvurun.

### <a name="memory-pressure"></a>Bellek baskısı
Bellek baskısı, raporların işlenmesi ve oluşturulması için daha fazla belleğe ihtiyaç duyulduğunda ortaya çıkabilir. Raporlarda yenileme zamanlamak için bilgisayarda önemli miktarda belleğe ihtiyaç duyulabilir. Bu durum özellikle büyük raporlar için geçerlidir. Bellek baskısı sonucunda raporlar başarısız olabilir ve rapor sunucusu kilitlenebilir.

Bellek baskısı sorunuyla sürekli karşılaşıyorsanız kaynak yükünü dağıtmak için rapor sunucusunu daha geniş ölçekteki bir dağıtıma taşımayı tercih edebilirsiniz. rsreportserver.config dosyasındaki `IsDataModelRefreshService` ayarı ile de Veri yenileme için kullanılacak belirli bir rapor sunucusu tanımlayabilirsiniz. Bu ayarı kullanarak bir veya daha fazla sunucuyu isteğe bağlı raporları işleyecek ön uç sunucusu haline getirebilir, başka bir sunucu kümesini ise yalnızca zamanlanmış yenileme için kullanılacak şekilde ayarlayabilirsiniz.

Analysis Services örneklerini izleme hakkında bilgi için bkz. [Monitor an Analysis Services Instance (bir Analysis Services örneğini izleme)](https://docs.microsoft.com/sql/analysis-services/instances/monitor-an-analysis-services-instance).

Analysis Services bellek ayarları hakkında bilgi için bkz. [Memory Properties (Bellek Özellikleri)](https://docs.microsoft.com/sql/analysis-services/server-properties/memory-properties).

### <a name="kerberos-configuration"></a>Kerberos yapılandırması
Windows kimlik bilgileriyle bir veri kaynağına başarılı bir bağlantı oluşturmak için Kerberos kısıtlanmış temsil yapılandırması gerekli olabilir. Kerberos kısıtlanmış temsil yapılandırması hakkında daha fazla bilgi için bkz. [Power BI raporlarını kullanmak için Kerberos'u yapılandırma](configure-kerberos-powerbi-reports.md).

## <a name="known-issues"></a>Bilinen sorunlar
Bilinen sorunlar hakkında bilgiler mevcut olduğunda burada listelenecektir.

## <a name="configuration-settings"></a>Yapılandırma ayarları
Zamanlanmış yenilemeyi etkilemek için aşağıdaki ayarlar kullanılabilir. SQL Server Management Studio'da (SSMS) yapılan ayarlar ölçeği genişletilen dağıtımdaki tüm rapor sunucularına uygulanır. rsreportserver.config dosyasında yapılan ayarlar ise yapılandırma gerçekleştirilen sunucuya özgüdür.

**SSMS'deki ayarlar:**

| Ayar | Açıklama |
| --- | --- |
| MaxFileSizeMb |Karşıya yüklenen raporlar için maksimum dosya boyutu. Varsayılan değer: 1.000 MB (1 GB). Maksimum değer: 2.000 MB (2 GB). |
| ModelCleanupCycleMinutes |Modelin bellekten çıkarılmak üzere hangi sıklıkta denetlendiğini tanımlar. Varsayılan değer 15 dakikadır. |
| ModelExpirationMinutes |Son kullanıldığı ve çıkarıldığı zamana göre modelin süresinin kaç dakika sonra dolacağını tanımlar. Varsayılan değer 60 dakikadır. |
| ScheduleRefreshTimeoutMinutes |Bir modda veri yenilemenin ne kadar sürebileceğini tanımlar. Varsayılan değer 120 dakikadır. Üst sınır yoktur. |

**rsreportserver.config dosyasındaki ayarlar:**

```
<Configuration>
    <Service>
        <PollingInterval>10</PollingInterval>
        <IsDataModelRefreshService>false</IsDataModelRefreshService>
        <MaxQueueThreads>0</MaxQueueThreads>
    </Service>
</Configuration>
```

## <a name="tools-for-troubleshooting"></a>Sorun giderme araçları
### <a name="logs-relevant-for-scheduled-refresh-of-power-bi-reports"></a>Power BI raporlarının zamanlanmış yenilemesiyle ilgili günlükler
Zamanlanmış yenileme hakkındaki bilgilerin bulunduğu günlük dosyaları RSPowerBI_ günlükleridir. Bu dosyalar rapor sunucunuzun yükleme konumundaki LogFiles klasöründe bulunur. 

```
C:\Program Files\Microsoft Power BI Report Server\PBIRS\LogFiles\RSPowerBI_*.log
```

**Hata koşulu**

```
2017-10-20 02:00:09.5188|ERROR|744|Error Processing Data Model Refresh: SessionId: e960c25e-ddd4-4763-aa78-0e5dceb53472, Status: Error Model can not be refreshed because not all the data sources are embedded, Exception Microsoft.PowerBI.ReportServer.AsServer.InvalidDataSourceException: Model can not be refreshed because not all the data sources are embedde
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.AnalysisServicesDataRefresh.CanModelRefresh(IEnumerable`1 dataSources)
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.<>c__DisplayClass7.<ExecuteActionWithLogging>b__5()
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.<ExecuteFuncWithLogging>d__1`1.MoveNext()
```

***Başarılı yenileme***

```
2017-10-25 15:23:41.9370|INFO|6|Handling event with data: TimeEntered: 10/25/2017 8:23:41 PM, Type: Event, SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, EventType: DataModelRefresh
2017-10-25 15:23:41.9370|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Data Refresh.
2017-10-25 15:23:41.9370|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Retrieving PBIX AsDatabaseInfo.
2017-10-25 15:23:42.7134|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Verifying all the data sources are embedded.
2017-10-25 15:23:42.7134|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Verifying connection strings are valid.
2017-10-25 15:23:42.7134|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Streaming model to Analysis Server.
2017-10-25 15:23:42.7603|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Refreshing the model.
2017-10-25 15:23:51.5258|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Removing credentials from the model.
2017-10-25 15:23:51.6508|INFO|6|Processing Data Model Refresh: SessionId: 46d398db-0b1f-49d8-b7bd-c5461c07ec7a, Status: Starting Saving model to the catalog.
```

**Yanlış Kimlik Bilgileri**

```
2017-10-20 08:22:01.5595|INFO|302|Processing Data Model Refresh: SessionId: 22cd9ec3-b21a-4eb1-81ae-15fac8d379ea, Status: Starting Refreshing the model.
2017-10-20 08:22:02.3758|ERROR|302|Error Processing Data Model Refresh: SessionId: 22cd9ec3-b21a-4eb1-81ae-15fac8d379ea, Status: Error Failed to refresh the model, Exception Microsoft.AnalysisServices.OperationException: Failed to save modifications to the server. Error returned: 'The credentials provided for the SQL source are invalid. (Source at rosecatalog;reportserver.). The exception was raised by the IDbCommand interface.
'.
   at Microsoft.AnalysisServices.Tabular.Model.SaveChanges(SaveOptions saveOptions)
   at Microsoft.PowerBI.ReportServer.AsServer.TOMWrapper.RefreshModel(Database database)
   at Microsoft.PowerBI.ReportServer.AsServer.AnalysisServicesServer.RefreshDatabase(String databaseName, IEnumerable`1 dataSources)
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.AnalysisServicesDataRefresh.RefreshDatabase(AsDatabaseInfo asDatabaseInfo)
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.<>c__DisplayClass7.<ExecuteActionWithLogging>b__5()
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.<ExecuteFuncWithLogging>d__1`1.MoveNext()
2017-10-20 08:22:02.4588|ERROR|302|Error Processing Data Model Refresh: SessionId: 22cd9ec3-b21a-4eb1-81ae-15fac8d379ea, Status: Error Failed Data Refresh, Exception Microsoft.AnalysisServices.OperationException: Failed to save modifications to the server. Error returned: 'The credentials provided for the SQL source are invalid. (Source at rosecatalog;reportserver.). The exception was raised by the IDbCommand interface.
'.
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.ExecuteActionWithLogging(Action methodToExecute, String description, String localizedDescription, String messageInFailure, RefreshInfo refreshInfo, DataAccessors dataAccessors, ReportEventType operation, Int64 size, Boolean isDataRetrieval, Boolean showInExecutionLog)
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.AnalysisServicesDataRefresh.RefreshData(RefreshInfo refreshInfo)
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.<>c__DisplayClass7.<ExecuteActionWithLogging>b__5()
   at Microsoft.PowerBI.ReportServer.WebHost.EventHandler.DataRefreshScope.<ExecuteFuncWithLogging>d__1`1.MoveNext()
```

#### <a name="enabling-verbose-logging"></a>Ayrıntılı günlük kaydını etkinleştirme
Power BI Rapor Sunucusu'nda ayrıntılı günlük kaydını etkinleştirme adımları SQL Server Reporting Services'dekilerle aynıdır.

1. `<install directory>\PBIRS\ReportServer\bin\ReportingServicesService.exe.config` dosyasını açın.
2. `<system.diagnostics>` bölümünde **DefaultTraceSwitch** değerini **4** olarak değiştirin.
3. `<RStrace>` bölümünde **Components** değerini **all:4** olarak değiştirin. 

### <a name="executionlog"></a>ExecutionLog
Bir Power BI raporu oluşturulduğunda veya zamanlanmış yenileme planı yürütüldüğünde veritabanındaki Yürütme Günlüğüne yeni girişler eklenir. Bu girişlere rapor sunucusu katalog veritabanındaki **ExecutionLog3** görünümünden ulaşabilirsiniz.

Power BI raporlarına ait yürütme günlüğü girişleri, diğer rapor türlerine ait girişlerden farklıdır.

* TimeRendering sütunları her zaman 0 olur. Power BI raporları sunucuda değil tarayıcıda oluşturulur.
* 2 İstek Türü ve bunlara bağlı öğe eylemleri vardır:
  * **Interactive**: Rapor görüntülendiğinde.
    * **ASModelStream**: katalogdaki veri modelinin Analysis Services'e akışı yapıldığında.
    * **ConceptualSchema**: kullanıcı raporu görüntülerken tıklama gerçekleştirdiğinde.
    * **QueryData**: istemciden veri istendiğinde.
  * **Refresh Cache**: yenileme zamanlama planı yürütüldüğünde.
    * **ASModelStream**: katalogdaki veri modelinin Analysis Services'e akışı yapıldığında.
    * **DataRefresh**: Veriler bir veya daha fazla veri kaynağından yenilendiğinde.
    * **SaveToCatalog**: veri modeli kataloğa tekrar kaydedildiğinde.

## <a name="analysis-services"></a>Analysis Services
Sorunları tanılamak veya bellek sınırlarını ayarlamak için Analysis Services üzerinde değişiklik yapmak istediğiniz durumlar olabilir.

> [!IMPORTANT]
> Bu ayarlar rapor sunucusunu yükselttiğinizde sıfırlanır. Gerekirse yeniden uygulamak üzere değişikliklerinizin bir kopyasını saklamayı unutmayın.
> 
> 

### <a name="install-location"></a>Yükleme konumu
Power BI Rapor Sunucusu ve Analysis Services için varsayılan konum aşağıda belirtilmiştir.

`C:\Program Files\Microsoft Power BI Report Server\PBIRS\ASEngine`

### <a name="configuring-analysis-services-settings-msmdsrvini"></a>Analysis Services ayarlarını (msmdsrv.ini) yapılandırma
`<install directory>\PBIRS\ASEngine` dizininde yer alan *msmdsrv.ini* dosyasını kullanarak Analysis Services'deki farklı ayarları denetleyebilirsiniz. msmdsrv.ini dosyasını açtığınızda dosyanın, bulunmasını beklediğiniz tüm ayarları içermediğini fark edeceksiniz. 

Bunun nedeni Power BI Rapor Sunucusu tarafından çalıştırılan gerçek Analysis Services işleminin `<install directory>\PBIRS\ASEngine\workspaces` konumunda başlatılmasıdır. Alışkın olduğunuz *msmdsrv.ini* dosyasını bu klasörde bulabilirsiniz. Analysis Services işlemi her çalıştırıldığında üzerine yazıldığından çalışma alanları klasörü içindeki dosyanın değiştirilmemesine dikkat edilmesi gerekir. Bir ayarı denetlemek isterseniz bunu lütfen `<install directory>\PBIRS\ASEngine` dizinindeki msmdsrv.ini dosyasını değiştirerek yapın.

Aşağıdaki ayarlar Analysis Services işlemi her çalıştırıldığında sıfırlanır. Bu ayarlarda yaptığınız değişiklikler yok sayılır.

* ConfigurationSettings\PrivateProcess
* ConfigurationSettings\DataDir
* ConfigurationSettings\LogDir
* ConfigurationSettings\TempDir
* ConfigurationSettings\BackupDir
* ConfigurationSettings\AllowedBrowsingFolders
* ConfigurationSettings\CrashReportsFolder
* ConfigurationSettings\ExtensionDir
* ConfigurationSettings\Port
* ConfigurationSettings\DeploymentMode
* ConfigurationSettings\ServerLocation
* ConfigurationSettings\TMCompatabilitySKU
* ConfigurationSettings\FlightRecorder\TraceDefinitionFile

### <a name="profiling-the-local-analysis-services-process"></a>Yerel Analysis Services işleminin profilini oluşturma
Tanılama amacıyla yerel Analysis Services işlemi üzerinde bir SQL Profiler izlemesi çalıştırılabilir. Yerel Analysis Services örneğine bağlanmak için aşağıdakileri uygulayın.

SQL Server Profiler İzlemesi, [SQL Server Management Studio (SSMS) indirilebilir dosyası](https://docs.microsoft.com/sql/ssms/download-sql-server-management-studio-ssms) içinde yer almaktadır.

1. **SQL Server Profiler**'ı yönetici olarak çalıştırın.
2. **Yeni İzleme** düğmesini seçin.
3. **Sunucuya bağlan** iletişim kutusunda, **Analysis Services**'i seçin ve sunucu adı olarak **localhost:5132** girin.
4. **İzleme özellikleri** iletişim kutusunda, yakalamak istediğiniz olayları seçin ve ardından **Çalıştır** seçeneğini belirleyin.

## <a name="lock-pages-in-memory-windows-privilege"></a>Sayfaları Bellekte Kilitle adlı Windows ayrıcalığı
Power BI raporu oluşturamadığınızı fark ederseniz Power BI Rapor Sunucusu'nun çalıştırıldığı hesaba **Sayfaları bellekte kilitle** ayrıcalığını atayabilirsiniz. **Sayfaları bellekte kilitle** ayrıcalığını yapılandırma hakkında daha fazla bilgi için bkz. [Windows privileges assigned to the Analysis Services service account (Analysis Services hizmet hesabına atanmış olan Windows ayrıcalıkları)](https://docs.microsoft.com/sql/analysis-services/instances/configure-service-accounts-analysis-services#bkmk_winpriv).

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)

