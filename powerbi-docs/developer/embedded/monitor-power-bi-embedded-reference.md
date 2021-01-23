---
title: Power BI Embedded veri başvurusunu izleme
description: Power BI Embedded izlerken gereken önemli başvuru malzemeleri.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: how-to
ms.date: 01/14/2021
ms.openlocfilehash: fc6b9dd4d50d665211324d1b6c05e62468fc034d
ms.sourcegitcommit: 77912d4f6ef2a2b1ef8ffccc50691fe5b38ee97a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98690811"
---
# <a name="monitoring-power-bi-embedded-data-reference"></a>Power BI Embedded veri başvurusunu izleme

Power BI Embedded izleme verilerini toplama ve çözümleme hakkında ayrıntılar için bkz. [izleyici Power BI Embedded](monitor-power-bi-embedded.md) .

## <a name="metrics"></a>Ölçümler

Bu bölümde, Power BI Embedded için toplanan otomatik olarak toplanan tüm platform ölçümleri listelenmektedir.  

|Ölçüm türü | Kaynak sağlayıcısı/tür ad alanı<br/> ve bireysel ölçümlere bağlantı |
|-------|-----|
| Kapasiteler | [Microsoft. Powerbiadanmış/kapasiteler](/azure/azure-monitor/platform/metrics-supported#microsoftpowerbidedicatedcapacities) |

### <a name="capacities"></a>Kapasiteler

Kaynak sağlayıcısı ve türü: [Microsoft. Powerbiadanmış/kapasiteler](/azure/azure-monitor/platform/metrics-supported#microsoftpowerbidedicatedcapacities)

| Name | Metric | Birim | Açıklama |
|:---|:-------|:-----|:------------|
|Bellek (Gen1) |memory_metric               |Bayt        |Bellek. A1 için 0-3 GB, a2 için 0-5 GB, a3 için 0-10 GB, A4 için 0-25 GB, A6 için GB ve A6 için 0-50 GB. Yalnızca Power BI Embedded nesil 1 kaynakları için desteklenir. |
|Bellek kullanımı (veri kümeleri) (Gen1) |memory_thrashing_metric     |Yüzde      |Ortalama bellek miktarı. Yalnızca Power BI Embedded nesil 1 kaynakları için desteklenir. |
|QPU High kullanımı (Gen1) |qpu_high_utilization_metric |Count        |Son dakikada QPU yüksek kullanımı, yüksek QPU kullanımı Için 1, aksi durumda 0. Yalnızca Power BI Embedded nesil 1 kaynakları için desteklenir. |
|Sorgu süresi (veri kümeleri) (Gen1) |QueryDuration               |Mayacak |Son aralıktaki DAX sorgu süresi. Yalnızca Power BI Embedded nesil 1 kaynakları için desteklenir. |
|Sorgu havuzu Iş kuyruğu uzunluğu (veri kümeleri) (Gen1) |QueryPoolJobQueueLength     |Count        |Sorgu iş parçacığı havuzu kuyruğundaki iş sayısı. Yalnızca Power BI Embedded nesil 1 kaynakları için desteklenir. |

## <a name="metric-dimensions"></a>Ölçüm boyutları

Ölçüm boyutları hakkında daha fazla bilgi için bkz. [çok boyutlu ölçümler](/azure/azure-monitor/platform/data-platform-metrics#multi-dimensional-metrics).

Power BI Embedded, Boyutlar içeren ölçümleri yok.

## <a name="resource-logs"></a>Kaynak günlükleri

Bu bölümde, Power BI Embedded için toplayacağınız kaynak günlüklerinin türleri listelenir.

Başvuru için, [Azure izleyici 'de desteklenen tüm kaynak günlükleri kategorisi türlerinin](/azure/azure-monitor/platform/resource-logs-schema)listesini inceleyin.

Bu bölüm, Power BI Embedded için toplanan tüm kaynak günlüğü kategori türlerini listeler.  

|Kaynak günlük türü | Kaynak sağlayıcısı/tür ad alanı<br/> ve bireysel ölçümlere bağlantı |
|-------|-----|
| Kapasiteler | [Microsoft. Powerbiadanmış/kapasiteler](/azure/azure-monitor/platform/resource-logs-categories#microsoftpowerbidedicatedcapacities) |

## <a name="azure-monitor-logs-tables"></a>Azure Izleyici günlük tabloları

Bu bölüm, Power BI Embedded ilgili tüm Azure Izleyici günlükleri kusto tablolarının yanı sıra Log Analytics tarafından sorgu için kullanılabilir.

|Kaynak Türü | Notlar |
|-------|-----|
| [Power BI Embedded](/azure/azure-monitor/reference/tables/tables-resourcetype#power-bi-embedded) |Aşağıdaki tablo listesini görüntüleyin |

### <a name="power-bi-embedded"></a>Power BI Embedded

| Tablo |  Açıklama |
|:---------|:-------------|------------------|
| [AzureActivity](/azure/azure-monitor/reference/tables/azureactivity) | Azure etkinlik günlüğünden gelen ve Azure 'da oluşan herhangi bir abonelik düzeyi veya yönetim grubu düzeyindeki olay hakkında Öngörüler sağlayan girişler.    |                             |                                                   | 
| [AzureDiagnostics](/azure/azure-monitor/reference/tables/azurediagnostics)   | Azure Tanılama modu kullanan Azure hizmetleri için kaynak günlüklerini depolar. Kaynak günlükleri, Azure kaynaklarının iç işlemini anlatmaktadır. |
| [AzureMetrics](/azure/azure-monitor/reference/tables/azuremetrics)   | Azure hizmetleri tarafından yayılan ölçüm verileri, sistem durumunu ve performansını ölçer. |

Tüm Azure Izleyici günlükleri/Log Analytics tablolarının bir başvurusu için bkz. [Azure Izleyici günlük tablosu başvurusu](/azure/azure-monitor/reference/tables/tables-resourcetype).

## <a name="activity-log"></a>Etkinlik günlüğü

**Altyapı** ve/veya **Tüm Ölçümler** kategorisini seçebilirsiniz.

### <a name="engine"></a>Altyapı

Motor kategorisi, kaynağı aşağıda listelenen olayları günlüğe kaydetmek için yönlendirir. Her olay için özellikler vardır.

|     Olay Adı     |     Olay Açıklaması     |
|----------------------------|----------------------------------------------------------------------------------|
|    Audit Login    |    İzleme başladıktan sonra gerçekleştirilen tüm yeni altyapı bağlantısı olaylarını kaydeder.    |
|    Session Initialize    |    İzleme başladıktan sonra gerçekleştirilen tüm oturum başlatma olaylarını kaydeder.    |
|    Vertipaq Query Begin    |    İzleme başladıktan sonra gerçekleştirilen tüm VertiPaq SE sorgu başlatma olaylarını kaydeder.    |
|    Query Begin    |    İzleme başladıktan sonra gerçekleştirilen tüm sorgu başlatma olaylarını kaydeder.    |
|    Query End    |    İzleme başladıktan sonra gerçekleştirilen tüm sorgu bitiş olaylarını kaydeder.    |
|    Vertipaq Query End    |    İzleme başladıktan sonra gerçekleştirilen tüm VertiPaq SE sorgu bitiş olaylarını kaydeder.    |
|    Audit Logout    |    İzleme başladıktan sonra gerçekleştirilen tüm sonlandırılan altyapı bağlantısı olaylarını kaydeder.    |
|    Hata    |    İzleme başladıktan sonra gerçekleştirilen tüm altyapı hatası olaylarını kaydeder.    |

#### <a name="event-example"></a>Olay örneği

Aşağıdaki tabloda bir olay örneği gösterilmektedir.

| Özellik Adı | Vertipaq Query End Example | Özellik Açıklaması |
|---|---|---|
| EventClass | XM_SEQUERY_END | Olay Sınıfı, olayları kategorilere ayırmak için kullanılır. |
| EventSubclass | 0 | Olay Alt Sınıfı, her olay sınıfıyla ilgili ek bilgi sağlar. (örneğin, 0: VertiPaq Scan) |
| RootActivityId | ff217fd2-611d-43c0-9c12-19e202a94f70 | Kök etkinlik kimliği. |
| CurrentTime | 2018-04-06T18:30:11.9137358Z | Kullanılabilir durumdaysa etkinliğin başlatıldığı saat. |
| StartTime | 2018-04-06T18:30:11.9137358Z | Kullanılabilir durumdaysa etkinliğin başlatıldığı saat. |
| JobID | 0 | İlerlemeye ilişkin iş kimliği. |
| ObjectID | 464 | Nesne kimliği |
| ObjectType | 802012 | ObjectType |
| EndTime | 2018-04-06T18:30:11.9137358Z | Olayın bitiş saati. |
| Süre | 0 | Olayın süresi (milisaniye cinsinden). |
| SessionType | Kullanıcı | Oturum türü (işleme neden olan varlık). |
| ProgressTotal | 0 | İlerleme toplamı. |
| IntegerData | 0 | Tamsayı verileri. |
| Önem | 0 | Bir özel durumun önem derecesi. |
| Başarılı | 1 | 1 = başarılı. 0 = başarısız (örneğin 1 değeri izin denetimi işleminin başarılı olduğunu belirtirken 0, bu denetimin başarısız olduğunu gösterir). |
| Hata | 0 | Belirli bir olayın hata numarası. |
| ConnectionID | 3 | Benzersiz bağlantı kimliği. |
| DatasetID | 5eaa550e-06ac-4adf-aba9-dbf0e8fd1527 | Kullanıcının deyiminin çalıştırıldığı veri kümesinin kimliği. |
| SessionID | 3D063F66-A111-48EE-B960-141DEBDA8951 | Oturum GUID'si. |
| SPID | 180 | Sunucu işlem kimliği. Kullanıcı oturumunu benzersiz bir şekilde tanımlar. Doğrudan XML/A tarafından kullanılan oturum GUID'sine karşılık gelir. |
| ClientProcessID | null | İstemci uygulamasının işlem kimliği. |
| ApplicationName | null | Sunucu bağlantısını oluşturan istemci uygulamasının adı. |
| CapacityName | pbi641fb41260f84aa2b778a85891ae2d97 | Power BI Embedded kapasite kaynağının adı. |

### <a name="allmetrics"></a>Tüm Ölçümler

**Tüm Ölçümler** seçeneğinin işaretlenmesi, tüm ölçümlerin verilerini günlüğe kaydederek bir Power BI Embedded kaynağı ile kullanmanızı sağlar.

Aşağıdaki tabloda, etkinlik günlüğünde oluşturulabilecek Power BI Embedded ilişkili işlemler listelenmiştir.

## <a name="schemas"></a>Şemalar

Power BI Embedded, **Power BI adanmış** şemayı kullanır.

## <a name="next-steps"></a>Sonraki adımlar

>[!div class="nextstepaction"]
>[Azure Power BI Embedded izleme](monitor-power-bi-embedded.md)

>[!div class="nextstepaction"]
>[Azure kaynaklarında tanılama günlüğüne kaydetme](/azure/monitoring-and-diagnostics/monitoring-overview-of-diagnostic-logs)

>[!div class="nextstepaction"]
>[Set-AzureRmDiagnosticSetting](/powershell/module/azurerm.insights/Set-AzureRmDiagnosticSetting)