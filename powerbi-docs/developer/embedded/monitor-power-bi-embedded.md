---
title: İzleyici Power BI Embedded
description: Power BI Embedded nasıl izleneceğini öğrenmek için Buradan başlayın.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: how-to
ms.date: 01/14/2021
ms.openlocfilehash: 1b8ebbd7913bc5763f9f4dd8576fbc4783e8d531
ms.sourcegitcommit: 77912d4f6ef2a2b1ef8ffccc50691fe5b38ee97a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98690797"
---
# <a name="monitor-power-bi-embedded"></a>İzleyici Power BI Embedded

Azure kaynaklarına bağlı kritik Uygulamalarınız ve iş süreçleriniz olduğunda, bu kaynakları kullanılabilirlik, performans ve işlem için izlemek istersiniz. Bu makalede, Power BI Embedded tarafından oluşturulan izleme verileri ve bu verileri çözümlemek ve uyarmak için Azure Izleyici 'nin özelliklerini nasıl kullanabileceğiniz açıklanmaktadır.

## <a name="monitor-overview"></a>İzlemeye genel bakış

Her bir *Power BI Embedded* örneği Için Azure Portal **genel bakış** sayfasında aşağıdaki bilgiler yer alır:

* **Kaynak grubu** -Örneğin ait olduğu [kaynak grubu](/azure/azure-resource-manager/management/overview#resource-groups)
* **Durum** -Power BI Embedded örneğinizin durumu
* **Konum** -Power BI Embedded örneğinizin konumu
* **Kaynak adı** -Power BI Embedded örneğinizin adı
* **SKU** -Power BI Embedded ÖRNEĞINIZIN kullandığı SKU
* **Abonelik adı** -Power BI Embedded örnek abonelik adı
* **ABONELIK kimliği** -Power BI Embedded örnek abonelik kimliği

## <a name="what-is-azure-monitor"></a>Azure İzleyici nedir?

*Power BI Embedded* , Azure 'da, diğer bulutlardaki ve Şirket içindeki kaynaklara ek olarak Azure kaynaklarınızı izlemeye yönelik eksiksiz bir özellik kümesi sunan Azure [izleyici](/azure/azure-monitor/overview)'yi kullanarak izleme verileri oluşturur.

Aşağıdaki kavramları açıklayan Azure [izleyici Ile Azure kaynaklarını izleme](/azure/azure-monitor/insights/monitor-azure-resource)makalesini başlatın:

- Azure İzleyici nedir?
- İzleme ile ilişkili maliyetler
- Azure 'da toplanan verileri izleme
- Veri toplamayı yapılandırma
- İzleme verilerini analiz etmek ve uyarı vermek için Azure 'da standart araçlar

Aşağıdaki bölümlerde, Power BI Embedded için toplanan belirli verileri açıklayarak ve veri toplamayı yapılandırmak ve bu verileri Azure araçlarıyla çözümlemek için örnekler sağlamak üzere bu makalede derleme yapılır.

## <a name="monitoring-data"></a>Verileri izleme

Power BI Embedded, [Azure kaynaklarından gelen verileri izleme](/azure/azure-monitor/insights/monitor-azure-resource#monitoring-data-from-Azure-resources)bölümünde açıklanan diğer Azure kaynaklarıyla aynı türde izleme verilerini toplar.

Power BI Embedded tarafından oluşturulan ölçümler ve günlük ölçümleri hakkında ayrıntılı bilgi için bkz. [izleme *Power BI Embedded* veri başvurusu](monitor-power-bi-embedded-reference.md) .

## <a name="collection-and-routing"></a>Toplama ve yönlendirme

Platform ölçümleri ve etkinlik günlüğü otomatik olarak toplanır ve depolanır, ancak bir tanılama ayarı kullanılarak başka konumlara yönlendirilebilir.  

Kaynak günlükleri, bir tanılama ayarı oluşturup bunları bir veya daha fazla konuma yönlendirene kadar toplanmaz ve depolanmaz.

Azure portal, CLı veya PowerShell kullanarak bir tanılama ayarı oluşturmaya yönelik ayrıntılı süreç için [Azure 'da platform günlüklerini ve ölçümlerini toplamak üzere tanılama ayarı oluşturma](/azure/azure-monitor/platform/diagnostic-settings) konusuna bakın. Bir tanılama ayarı oluşturduğunuzda hangi günlük kategorilerinin toplanacağını belirlersiniz. *Power BI Embedded* kategorileri [Power BI Embedded izleme veri başvurusunda](monitor-power-bi-embedded-reference.md#resource-logs)listelenmiştir.

### <a name="using-powershell-to-enable-diagnostics"></a>Tanılamayı etkinleştirmek için PowerShell'i kullanma

PowerShell kullanarak ölçümleri ve tanılama günlüğünü etkinleştirmek için aşağıda listelenen komutları kullanın. Tanılamayı etkinleştirmek üzere PowerShell kullanma hakkında daha fazla bilgi için bkz. [PowerShell kullanarak Azure izleyici 'de Log Analytics çalışma alanı oluşturma ve yapılandırma](/azure/azure-monitor/platform/powershell-workspace-configuration).

* Tanılama günlüklerinin bir depolama hesabına kaydedilmesini sağlamak için şu komutu kullanın:

    ```powershell
    Set-AzureRmDiagnosticSetting -ResourceId [your resource id] -StorageAccountId [your storage account id] -Enabled $true
    ```
    Depolama hesabı kimliği, günlükleri göndermek istediğiniz depolama hesabının kaynak kimliğidir.

* Tanılama günlüklerinin akışını bir olay hub'ına yapmak için şu komutu kullanın:

    ```powershell
    Set-AzureRmDiagnosticSetting -ResourceId [your resource id] -ServiceBusRuleId [your service bus rule id] -Enabled $true
    ```
* Azure Service Bus kural kimliği, şu biçime sahip bir dizedir:

    ```powershell
    {service bus resource ID}/authorizationrules/{key name}
    ```

* Tanılama günlüklerini Log Analytics çalışma alanına göndermek için şu komutu kullanın:

    ```powershell
        Set-AzureRmDiagnosticSetting -ResourceId [your resource id] -WorkspaceId [resource id of the log analytics workspace] -Enabled $true
    ```

* Log Analytics çalışma alanının kaynak kimliğini almak için aşağıdaki komutu kullanabilirsiniz:

    ```powershell
    (Get-AzureRmOperationalInsightsWorkspace).ResourceId
    ```

Bu parametreleri bir arada kullanarak birden fazla çıkış seçeneği oluşturabilirsiniz.

Toplayacağınız ölçümler ve Günlükler aşağıdaki bölümlerde ele alınmıştır.

## <a name="analyzing-metrics"></a>Ölçümler çözümleniyor

**Azure izleyici** menüsünden **ölçümler** ' i açarak Ölçüm Gezgini 'ni kullanarak diğer Azure hizmetlerinden ölçümlerle *Power BI Embedded* için ölçümleri çözümleyebilirsiniz. Bu aracı kullanma hakkında ayrıntılı bilgi için bkz. [Azure Ölçüm Gezgini](/azure/azure-monitor/platform/metrics-getting-started) kullanmaya başlama.

Power BI Embedded için toplanan platform ölçümlerinin bir listesi için bkz. [ *Power BI Embedded* veri başvurusu ölçümlerini izleme](monitor-power-bi-embedded-reference.md#metrics)  

Başvuru için, [Azure izleyici 'de desteklenen tüm kaynak ölçümlerinin](/azure/azure-monitor/platform/metrics-supported)bir listesini görebilirsiniz.

## <a name="analyzing-logs"></a>Günlükler çözümleniyor

Azure Izleyici günlüklerindeki veriler, her tablonun kendine ait benzersiz özellikler kümesine sahip olduğu tablolarda depolanır.  

Azure Izleyici 'deki tüm kaynak günlüklerine aynı alanlar ve hizmete özgü alanlar gelir. Ortak şema [Azure izleyici kaynak günlüğü şemasında](https://docs.microsoft.com/azure/azure-monitor/platform/diagnostic-logs-schema#top-level-resource-logs-schema) özetlenmiştir Power BI Embedded kaynak günlükleri şeması, [Power BI Embedded veri başvurusunda](monitor-power-bi-embedded-reference.md#schemas)bulunur.

[Etkinlik günlüğü](/azure/azure-monitor/platform/activity-log) , abonelik düzeyindeki olaylara ilişkin Öngörüler sağlayan bir Azure platformu oturum açma işlemi. Bunu bağımsız olarak görüntüleyebilir veya Azure Izleyici günlüklerine yönlendirebilirsiniz, burada Log Analytics kullanarak çok daha karmaşık sorgular yapabilirsiniz.  

Power BI Embedded için toplanan kaynak günlüklerinin türlerinin listesi için bkz. [izleme Power BI Embedded veri başvurusu](monitor-power-bi-embedded-reference.md#resource-logs)  

Azure Izleyici günlükleri tarafından kullanılan tabloların listesi ve Log Analytics tarafından sorgulanabilir, bkz. [izleme Power BI Embedded veri başvurusu](monitor-power-bi-embedded-reference.md#azure-monitor-logs-tables)  

### <a name="sample-kusto-queries"></a>Örnek kusto sorguları

> [!IMPORTANT]
> Power BI Embedded menüsünden **Günlükler** ' i seçtiğinizde, Log Analytics geçerli Power BI Embedded kaynağı için ayarlanan sorgu kapsamıyla açılır. Bu, günlük sorgularının yalnızca bu kaynaktaki verileri dahil olacağı anlamına gelir. Diğer Power BI Embedded kaynağı veya diğer Azure hizmetlerinden veri içeren bir sorgu çalıştırmak istiyorsanız, **Azure izleyici** menüsünden **Günlükler** ' i seçin. Ayrıntılar için bkz. [Azure izleyici 'de günlük sorgusu kapsamı ve zaman aralığı Log Analytics](/azure/azure-monitor/log-query/scope/) .

Aşağıda, izleme Power BI Embedded yönelik sorgu örnekleri verilmiştir.

* Bu, beş dakikadan kısa bir süre içinde tamamlanan bir sorgudur (300.000 milisaniye).

    ```Kusto
        search *
        | where Type == "AzureDiagnostics"
        | where ( OperationName == "QueryEnd" )
        | where toint(Duration_s) < 300000   
    ```
* Kapasite adlarını tanımlayın.

    ```Kusto
        search *
        | where Type == "AzureDiagnostics"
        | where ( OperationName == "QueryEnd" )
        | where toint(Duration_s) < 300000   
    ```

## <a name="alerts"></a>Uyarılar

İzleme verilerinizde önemli koşullar bulunduğunda Azure Izleyici uyarıları size önceden bildirimde bulunur. Bunlar, müşterilerinizin sorunları fark etmeden önce sisteminizdeki sorunları tanımlamanızı ve ele belirlemenizi sağlar. [Ölçümler](/azure/azure-monitor/platform/alerts-metric-overview), [Günlükler](/azure/azure-monitor/platform/alerts-unified-log)ve [etkinlik günlüğü](/azure/azure-monitor/platform/activity-log-alerts)hakkında uyarı ayarlayabilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

Azure kaynaklarında tanılama günlüğüne kaydetme hakkında daha fazla bilgi edinebilirsiniz.

>[!div class="nextstepaction"]
>[Power BI Embedded veri başvurusunu izleme](monitor-power-bi-embedded-reference.md)

>[!div class="nextstepaction"]
>[Azure İzleyici ile Azure kaynaklarını izleme](/azure/azure-monitor/insights/monitor-azure-resource)