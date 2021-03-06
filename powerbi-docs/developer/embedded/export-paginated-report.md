---
title: Daha iyi iş zekası içgörüleri için, Power BI ekli analiz sayfalandırılmış raporları API’sini dışarı aktarın
description: Eklenmiş bir Power BI sayfalandırılmış raporunu dışarı aktarmayı öğrenin.
author: KesemSharabi
ms.author: kesharab
ms.topic: how-to
ms.service: powerbi
ms.subservice: powerbi-developer
ms.date: 02/09/2021
ms.openlocfilehash: 9757b19e4faf4537cf4ff3c1e6f06dc9d499bc8c
ms.sourcegitcommit: de3b45cad5ae21c77692ce4490e21de01d21e6f3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/10/2021
ms.locfileid: "100013602"
---
# <a name="export-paginated-report-to-file"></a>Sayfalandırılmış raporu dosyaya aktarma

`exportToFile` API’si, REST çağrısı kullanarak Power BI sayfalandırılmış raporunu dışarı aktarmaya olanak tanır. Şu dosya biçimleri desteklenir:
* **.pptx** (PowerPoint)
* **.pdf**
* **.xlsx** (Excel)
* **.dox** (Word)
* **.csv**
* **.xml**
* **.mhtml**
* **Görüntü**
    * Bir resme aktarırken `OutputFormat` biçim ayarıyla resim biçimini ayarlayın
    * Desteklenen OutputFormat değerleri: .bmp, .emf, .gif, .jpeg, .png veya .tiff (varsayılan)

## <a name="usage-examples"></a>Kullanım örnekleri

Dışarı aktarma özelliği çeşitli yollarla kullanabilirsiniz. Aşağıda birkaç örnek verilmiştir:

* **Yazdırmaya gönder düğmesi** - Uygulamanızda tıklandığında dışarı aktarma işi başlatan bir düğme oluşturun. İş görüntülenen raporu .pdf veya .pptx olarak dışarı aktarabilir ve tamamlandığında kullanıcı dosyayı bir indirme olarak alabilir. Rapor parametrelerini ve biçim ayarlarını kullanarak raporu belirli bir durumda, örneğin filtrelenmiş veriler, özel sayfa boyutları ve biçime özgü diğer ayarlarla dışarı aktarabilirsiniz. API zaman uyumsuz olduğundan dosyanın kullanılabilir duruma gelmesi biraz zaman alabilir.

* **E-posta eki** - Önceden ayarlanmış aralıklarla .pdf raporunun eklendiği otomatik bir e-posta gönderin. Yöneticilere haftalık rapor gönderme işlemini otomatikleştirmek isterseniz bu senaryo yararlı olabilir.

## <a name="using-the-api"></a>API'yi kullanma

API zaman uyumsuzdur. [exportToFile](/rest/api/power-bi/reports/exporttofile) API’si çağrıldığında bir dışarı aktarma işini tetikler. Dışarı aktarma işi tetiklendikten sonra, işi tamamlanana kadar izlemek için [yoklama](/rest/api/power-bi/reports/getexporttofilestatus) özelliğini kullanın.

Dışarı aktarma tamamlandığında yoklama API çağrısı dosyayı almak için bir [Power BI URL](/rest/api/power-bi/reports/getfileofexporttofile)’si döndürür. URL 24 saat süreyle kullanılabilir.

## <a name="supported-features"></a>Desteklenen özellikler

### <a name="format-settings"></a>Biçim ayarları

Her dosya biçimi için çeşitli biçim ayarları belirtin. Sayfalandırılmış rapor URL’si parametreleri için desteklenen özellikler ve değerler [Cihaz Bilgileri parametrelerine](../../paginated-reports/report-builder-url-parameters.md#report-commands-rdl) eşdeğerdir.

Burada biri rapor sayfası boyutunu kullanarak raporun ilk dört sayfasını .pptx dosyasına aktarmayı ve diğeri raporun üçüncü sayfasını .jpeg dosyasına aktarmayı gösteren iki örnek verilmiştir.

**İlk dört sayfayı .pptx dosyasına aktarma**

```json
{
      "format": "PPTX",
      "paginatedReportConfiguration":{
            "formatSettings":{
                  "UseReportPageSize": "true",
                  "StartPage": "1",
                  "EndPage": "4"
            }
      }
}
```

**Üçüncü sayfayı .jpeg dosyasına aktarma**

```json
{
      "format": "IMAGE",
      "paginatedReportConfiguration":{
            "formatSettings":{
                  "OutputFormat": "JPEG",
                  "StartPage": "3",
                  "EndPage": "3"
            }
      }
}
```

### <a name="report-parameters"></a>Rapor parametreleri

Raporu bir dizi rapor parametresiyle programı olarak dışarı aktarmak için `exportToFile` API’sini kullanabilirsiniz. Bu işlem [rapor parametresi](../../paginated-reports/paginated-reports-parameters.md) özellikleri kullanılarak gerçekleştirilir.

Burada rapor parametresi değerlerini ayarlamayı gösteren bir örnek verilmiştir.

```json
{
      "format": "PDF",
      "paginatedReportConfiguration":{
            "parameterValues":[
                  {"name": "State", "value": "WA"},
                  {"name": "City", "value": "Seattle"},
                  {"name": "City", "value": "Bellevue"},
                  {"name": "City", "value": "Redmond"}
            ]
      }
}
```

### <a name="authentication"></a>Kimlik Doğrulaması

Bir kullanıcı (veya ana kullanıcı) ya da [hizmet sorumlusunu](embed-service-principal.md) kullanarak kimlik doğrulaması yapabilirsiniz.

### <a name="row-level-security-rls"></a>Satır Düzeyi Güvenlik (RLS)

Veri kaynağı olarak Satır Düzeyi Güvenlik (RLS) ayarlanmış bir Power BI veri kümesi kullanıldığında, verilerin yalnızca belirli kişilere gösterildiği bir raporu dışarı aktarabilirsiniz. Örneğin bölgesel rollerle tanımlanmış bir satış raporunu dışarı aktarıyorsanız, raporu programlama yoluyla filtreleyerek yalnızca belili bir bölgenin görüntülenmesini sağlayabilirsiniz.

RLS kullanarak dışarı aktarmak için, raporun veri kaynağı olarak kullandığı Power BI veri kümesi üzerinde okuma izniniz olmalıdır.

Burada RLS için etkin bir kullanıcı adı sağlama işleminin gösterildiği bir örnek verilmiştir.

```json
{
      "format": "PDF",
      "paginatedReportConfiguration":{
            "identities": [
                  {"username": "john@contoso.com"}
            ]
      }
}
```

### <a name="single-sign-on-sql-and-dataverse-sso"></a>Çoklu oturum açma SQL ve veri deposu (SSO)

Power BI ' de, OAuth 'u SSO ile ayarlama seçeneğiniz vardır. Bunu yaptığınızda, raporu görüntüleyen kullanıcının kimlik bilgileri verileri almak için kullanılır. Talep Rest üstbilgisindeki erişim belirteci verilere erişmek için kullanılmaz, belirtecin ileti gövdesinde etkin kimlikle geçirilmesi gerekir.

Erişim belirteçlerini kafa karıştırıcı yapabilir, erişmek istediğiniz kaynak için doğru erişim belirtecini elde edebilir.

- Azure SQL için kaynak `https://database.windows.net` .
- Datadize için kaynak, `https://` ortamınızın adresidir. Örneğin, `https://contoso.crm.dynamics.com`.

[AuthenticationContext. AcquireTokenAsync](https://docs.microsoft.com/dotnet/api/microsoft.identitymodel.clients.activedirectory.authenticationcontext.acquiretokenasync) metodunu kullanarak belirteç API 'sine erişin.

Bir erişim belirteciyle etkin bir Kullanıcı adı sağlamaya yönelik bir örnek aşağıda verilmiştir.

```json
{
       "format":"PDF",
       "paginatedReportConfiguration":{
          "formatSettings":{
             "AccessiblePDF":"true",
             "PageHeight":"11in",
             "PageWidth":"8.5in",
             "MarginBottom":"2in"
          },
          "identities":[
             {
                "username":"john@contoso.com",
                "identityBlob": {
                "value": "eyJ0eX....full access token"
         }
        }
     ]
   }
}
```

## <a name="ppu-concurrent-requests"></a>PPU eş zamanlı istekleri
[Kullanıcı Başına Premium (PPU)](../../admin/service-premium-per-user-faq.md) kullanılırken `exportToFile` API’si, beş dakikada bir isteğe olanak verir. Beş dakika içinde birden fazla istek, *Çok Fazla İstek* (429) hatasına neden olur.

## <a name="code-examples"></a>Kod örnekleri

Kod örneklerinde kullanılan Power BI API SDK’sı [buradan](https://www.nuget.org/packages/Microsoft.PowerBI.Api) indirilebilir.

Dışarı aktarma işi oluştururken izlenmesi gereken üç adım vardır:

1. Dışarı aktarma isteği gönderme.
2. Yoklama.
3. Dosyayı alma.

Bu bölümde her adım için örnekler sağlanır.

### <a name="step-1---sending-an-export-request"></a>1\. Adım - dışarı aktarma isteği gönderme

İlk adım dışarı aktarma isteği göndermektir. Bu örnekte belirli bir sayfa aralığı, boyutu ve rapor parametresi değerleri için dışarı aktarma isteği gönderilir.

```csharp
private async Task<string> PostExportRequest(
    Guid reportId,
    Guid groupId)
{
    // For documentation purposes the export configuration is created in this method
    // Ordinarily, it would be created outside and passed in
    var paginatedReportExportConfiguration = new PaginatedReportExportConfiguration()
    {
        FormatSettings = new Dictionary<string, string>()
        {
            {"PageHeight", "14in"},
            {"PageWidth", "8.5in" },
            {"StartPage", "1"},
            {"EndPage", "4"},
        },
        ParameterValues = new List<ParameterValue>()
        {
            { new ParameterValue() {Name = "State", Value = "WA"} },
            { new ParameterValue() {Name = "City", Value = "Redmond"} },
        },
    };

    var exportRequest = new ExportReportRequest
    {
        Format = FileFormat.PDF,
        PaginatedReportExportConfiguration = paginatedReportExportConfiguration,
    };

    var export = await Client.Reports.ExportToFileInGroupAsync(groupId, reportId, exportRequest);

    // Save the export ID, you'll need it for polling and getting the exported file
    return export.Id;
}
```

### <a name="step-2---polling"></a>2\. Adım - yoklama

Dışarı aktarma isteğini gönderdikten sonra, beklediğiniz dışarı aktarma dosyasının ne zaman hazır olduğunu belirlemek için yoklamayı kullanın.

```csharp
private async Task<Export> PollExportRequest(
    Guid reportId,
    Guid groupId,
    string exportId /* Get from the ExportToAsync response */,
    int timeOutInMinutes,
    CancellationToken token)
{
    Export exportStatus = null;
    DateTime startTime = DateTime.UtcNow;
    const int secToMillisec = 1000;
    do
    {
        if (DateTime.UtcNow.Subtract(startTime).TotalMinutes > timeOutInMinutes || token.IsCancellationRequested)
        {
            // Error handling for timeout and cancellations
            return null;
        }

        var httpMessage = 
            await Client.Reports.GetExportToFileStatusInGroupWithHttpMessagesAsync(groupId, reportId, exportId);
            
        exportStatus = httpMessage.Body;
        if (exportStatus.Status == ExportState.Running || exportStatus.Status == ExportState.NotStarted)
        {
            // The recommended waiting time between polling requests can be found in the RetryAfter header
            // Note that this header is only populated when the status is either Running or NotStarted
            var retryAfter = httpMessage.Response.Headers.RetryAfter;
            var retryAfterInSec = retryAfter.Delta.Value.Seconds;

            await Task.Delay(retryAfterInSec * secToMillisec);
        }
    }
    // While not in a terminal state, keep polling
    while (exportStatus.Status != ExportState.Succeeded && exportStatus.Status != ExportState.Failed);

    return exportStatus;
}
```

### <a name="step-3---getting-the-file"></a>3\. Adım - dosyayı alma

Yoklama bir URL döndürdüğünde, bu örneği kullanarak dosyayı alın.

```csharp
private async Task<ExportedFile> GetExportedFile(
    Guid reportId,
    Guid groupId,
    Export export /* Get from the GetExportStatusAsync response */)
{
    if (export.Status == ExportState.Succeeded)
    {
        var httpMessage = 
            await Client.Reports.GetFileOfExportToFileInGroupWithHttpMessagesAsync(groupId, reportId, export.Id);

        return new ExportedFile
        {
            FileStream = httpMessage.Body,
            ReportName = export.ReportName,
            FileExtension = export.ResourceFileExtension,
        };
    }

    return null;
}

public class ExportedFile
{
    public Stream FileStream;
    public string ReportName;
    public string FileExtension;
}
```

### <a name="end-to-end-example"></a>Uçtan uca örnek

Bu, raporu dışarı aktarma işleminin uçtan uca bir örneğidir. Bu örnek şu aşamaları içerir:
1. [Dışarı aktarma isteği gönderme](#step-1---sending-an-export-request).
2. [Yoklama](#step-2---polling).
3. [Dosyayı alma](#step-3---getting-the-file).

```csharp
private async Task<ExportedFile> ExportPaginatedReport(
    Guid reportId,
    Guid groupId,
    int pollingtimeOutInMinutes,
    CancellationToken token)
{
    try
    {
        var exportId = await PostExportRequest(reportId, groupId);

        var export = await PollExportRequest(reportId, groupId, exportId, pollingtimeOutInMinutes, token);
        if (export == null || export.Status != ExportState.Succeeded)
        {
           // Error, failure in exporting the report
            return null;
        }

        return await GetExportedFile(reportId, groupId, export);
    }
    catch
    {
        // Error handling
        throw;
    }
}
```

## <a name="limitations"></a>Sınırlamalar

Hizmet sorumluları için, veri kaynağı olarak bir Power BI veri kümesi içeren sayfalandırılmış raporların dışarı aktarılması desteklenmez.

## <a name="next-steps"></a>Sonraki adımlar

Müşterileriniz ve kuruluşunuz için nasıl içerik ekleyeceğinizi gözden geçirin:

> [!div class="nextstepaction"]
>[Raporu dosyaya aktarma](export-to.md)

> [!div class="nextstepaction"]
>[Müşterileriniz için ekleme](embed-sample-for-customers.md)

> [!div class="nextstepaction"]
>[Kuruluşunuz için ekleme](embed-sample-for-your-organization.md)
