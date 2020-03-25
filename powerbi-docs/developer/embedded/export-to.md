---
title: Power BI raporlarını dışarı aktarma API’si
description: Eklenmiş bir Power BI raporunu dışarı aktarmayı öğrenin
author: KesemSharabi
ms.author: kesharab
ms.topic: conceptual
ms.service: powerbi
ms.subservice: powerbi-developer
ms.date: 03/01/2020
ms.openlocfilehash: 1e882f5314b599c97356409626f059b022f640f7
ms.sourcegitcommit: 2c798b97fdb02b4bf4e74cf05442a4b01dc5cbab
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80114555"
---
# <a name="export-report-to-file-preview"></a>Raporu dosyaya aktarma (önizleme)

`exportToFile` API’si, REST çağrısı kullanarak Power BI raporunu dışarı aktarmaya olanak tanır. Şu dosya biçimleri desteklenir:
* **PPTX** (PowerPoint)
* **PDF**
* **PNG**
    * PNG dosyasına aktarırken, birden çok sayfalı bir rapor zip dosyasında sıkıştırılır
    * PNG zip dosyası içindeki her dosya bir rapor sayfasını temsil eder
    * Sayfa adları, [Sayfaları Alma](https://docs.microsoft.com/rest/api/power-bi/reports/getpages) veya [Gruptaki Sayfaları Alma](https://docs.microsoft.com/rest/api/power-bi/reports/getpagesingroup) API’lerinin dönüş değerleriyle aynı olur

## <a name="usage-examples"></a>Kullanım örnekleri

Dışarı aktarma özelliği çeşitli yollarla kullanabilirsiniz. Aşağıda birkaç örnek verilmiştir:

* **Yazdırmaya gönder düğmesi** - Uygulamanızda tıklandığında dışarı aktarma işi başlatan bir düğme oluşturun. İş görüntülenen raporu PDF veya PPTX olarak dışarı aktarabilir ve tamamlandığında kullanıcı dosyayı bir indirme olarak alabilir. Yer işaretlerini kullanarak, yapılandırılmış filtreler, dilimleyiciler ve ek ayarlar da dahil olmak üzere raporu belirli bir durumda dışarı aktarabilirsiniz. API zaman uyumsuz olduğundan dosyanın kullanılabilir duruma gelmesi biraz zaman alabilir.

* **E-posta eki** - Önceden ayarlanmış aralıklarla PDF raporunun eklendiği otomatik bir e-posta gönderin. Yöneticilere haftalık rapor gönderme işlemini otomatikleştirmek isterseniz bu senaryo yararlı olabilir.

## <a name="using-the-api"></a>API'yi kullanma

API’yi kullanmadan önce aşağıdaki [yönetici kiracı ayarlarının](../../service-admin-portal.md#tenant-settings) etkinleştirildiğini doğrulayın:
* **Raporları PowerPoint sunuları veya PDF belgeleri olarak dışarı aktarma** - Varsayılan olarak etkindir.
* **Raporları resim dosyaları olarak dışarı aktarma** - Yalnızca PNG için gereklidir ve varsayılan olarak devre dışı bırakılır.

API zaman uyumsuzdur. [exportToFile](https://docs.microsoft.com/rest/api/power-bi/reports/exporttofile) API’si çağrıldığında bir dışarı aktarma işini tetikler. Dışarı aktarma işi tetiklendikten sonra, işi tamamlanana kadar izlemek için [yoklama](https://docs.microsoft.com/rest/api/power-bi/reports/getexporttofilestatus) özelliğini kullanın.

Yoklama sırasında API tamamlanan çalışma miktarını temsil eden bir sayı döndürür. Her dışarı aktarma işindeki çalışmalar, raporun sayfa sayısı temelinde hesaplanır. Tüm sayfaların ağırlığı aynıdır. Örneğin 10 sayfalık bir raporu dışarı aktarıyorsanız ve yoklamada 70 sayısı döndürülüyorsa, API dışarı aktarma işindeki 10 sayfadan yedisini işlemiştir.

Dışarı aktarma tamamlandığında yoklama API çağrısı dosyayı almak için bir [Power BI URL](https://docs.microsoft.com/rest/api/power-bi/reports/getfileofexporttofile)’si döndürür. URL 24 saat süreyle kullanılabilir.

## <a name="supported-features"></a>Desteklenen özellikler

### <a name="selecting-which-pages-to-print"></a>Yazdırılacak sayfaları seçme

[Sayfaları Alma](https://docs.microsoft.com/rest/api/power-bi/reports/getpages) veya [Gruptaki Sayfaları Alma](https://docs.microsoft.com/rest/api/power-bi/reports/getpagesingroup) dönüş değerine göre yazdırmak istediğiniz sayfaları belirtin. Ayrıca dışarı aktardığınız sayfaların sırasını da belirtebilirsiniz.

### <a name="bookmarks"></a>Yer imleri

 Rapora filtreleri uyguladıktan sonra programlama yoluyla raporu belirli bir durumda dışarı aktarmak için `exportToFile` API’sini kullanabilirsiniz. Bu işlem [Yer İşaretleri](../../consumer/end-user-bookmarks.md) özellikleri kullanılarak yapılır. Raporu yer işaretlerini kullanarak dışarı aktarmak için [yer işaretleri javascript API’sini](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Bookmarks) kullanın.

 Örneğin yer işaretinin `capturedBookmark.state` yöntemini kullanarak belirli bir kullanıcının raporda yaptığı değişiklikleri yakalayabilir ve ardından bunu geçerli durumunda karşıya yükleyebilirsiniz.

[Kişisel yer işaretleri](../../consumer/end-user-bookmarks.md#personal-bookmarks) ve [kalıcı filtreler](https://powerbi.microsoft.com/blog/announcing-persistent-filters-in-the-service/) desteklenmez.

### <a name="authentication"></a>Kimlik Doğrulama

Yalnızca bir kullanıcı (veya ana kullanıcı) kullanarak kimlik doğrulaması yapabilirsiniz. Şu anda [hizmet sorumlusu](embed-service-principal.md) desteklenmemektedir.

### <a name="row-level-security-rls"></a>Satır Düzeyi Güvenlik (RLS)

[Satır Düzeyi Güvenlik (RLS)](embedded-row-level-security.md) ile yalnızca belirli kullanıcıların görebileceği verilerin gösterildiği raporları dışarı aktarabilirsiniz. Örneğin bölgesel rollerle tanımlanmış bir satış raporunu dışarı aktarıyorsanız, raporu programlama yoluyla filtreleyerek yalnızca belili bir bölgenin görüntülenmesini sağlayabilirsiniz.

RLS kullanarak dışarı aktarmak için aşağıdaki izinlere sahip olmalısınız:
* Raporun bağlandığı veri kümesi için yazma ve yeniden paylaşma izinleri
* Rapor bir v1 çalışma alanında yer alıyorsa, çalışma alanı yöneticisi olmalısınız
* Rapor bir v2 çalışma alanında yer alıyorsa, çalışma alanı üyesi veya yöneticisi olmalısınız

### <a name="data-protection"></a>Veri koruma

PDF ve PPTX biçimleri [duyarlılık etiketlerini](../../admin/service-security-data-protection-overview.md#sensitivity-labels-in-power-bi) destekler. Duyarlılık etiketi olan bir raporu PDF veya PPTX biçimine aktarıyorsanız, dışarı aktarılan dosya raporu duyarlılık etiketiyle görüntüler.

### <a name="localization"></a>Localization (Yerelleştirme)

`exportToFile` API’sini kullanırken istediğiniz yerel ayarı geçirebilirsiniz. Yerelleştirme ayarları raporun görüntülenme şeklini etkiler; örneğin biçimlendirmeyi seçili yerel ayara göre değiştirir.

## <a name="concurrent-requests"></a>Eş zamanlı istekler

`exportToFile` eş zamanlı dışarı aktarma işi isteklerini destekler. Aşağıdaki tabloda raporunuzun bulunduğu SKU’ya bağlı olarak aynı anda çalıştırabileceğiniz işlerin sayısı gösterilir. Eş zamanlı istekler rapor sayfalarına karşılık gelir. Örneğin A6 SKU’sundaki bir rapor isteğinin 20 sayfası eş zamanlı olarak işlenir. Bu işlem her biri tek sayfa içeren 20 dışarı aktarma isteği göndermekle yaklaşık aynı zamanı alır.

Eş zamanlı istek sayısını aşan işler sonlandırılmaz. Örneğin A1 SKU’sunda üç sayfalık bir raporu dışarı aktarıyorsanız, ilk iş çalıştırılır ve ardından diğer iki iş sonraki iki yürütme döngüsünü bekler.

|Azure SKU  |Office SKU  |Eş zamanlı rapor sayfası sayısı üst sınırı  |
|-----------|------------|-----------|
|A1         |EM1         |1          |
|A2         |EM2         |2          |
|A3         |EM3         |3          |
|A4         |P1          |6          |
|A5         |P2          |12         |
|A6         |P3          |24         |

## <a name="limitations"></a>Sınırlamalar

* Dışarı aktardığınız raporun Premium veya Embedded kapasitede bulunması gerekir.
* Dışarı aktardığınız raporun veri kümesi Premium veya Embedded kapasitede bulunmalıdır.
* Genel önizleme için bir saatte dışarı aktarılan Power BI rapor sayfalarının sayısı 50 ile sınırlandırılmıştır.
* Dışarı aktarılan raporların dosya boyutu 250 MB’ı aşamaz.
* PNG’ye aktarırken duyarlılık etiketleri desteklenmez.
* [Hizmet sorumlusu](embed-service-principal.md) desteklenmez.
* Dışarı aktara eklenebilecek sayfa sayısı 30’dur. Raporda daha fazla sayfa varsa API hata döndürür ve dışarı aktarma işi iptal edilir.
* [Kişisel yer işaretleri](../../consumer/end-user-bookmarks.md#personal-bookmarks) ve [kalıcı filtreler](https://powerbi.microsoft.com/blog/announcing-persistent-filters-in-the-service/) desteklenmez
* Sayfalandırılmış tablolar şu anda desteklenmez.
* Aşağıdaki Power BI görselleri desteklenmez. Bu görselleri içeren bir rapor dışarı aktarıldığında, raporda bu görsellerin bulunduğu bölümler işlenmez ve bir hata simgesi görüntülenir.
    * Sertifikasız Power BI görselleri
    * R görselleri
    * PowerApps
    * Python görselleri
    * Visio

## <a name="code-examples"></a>Kod örnekleri

Dışarı aktarma işi oluştururken izlenmesi gereken üç adım vardır:

1. Dışarı aktarma isteği gönderme.
2. Yoklama.
3. Dosyayı alma.

Bu bölümde her adım için örnekler sağlanır.

### <a name="step-1---sending-an-export-request"></a>1\. Adım - dışarı aktarma isteği gönderme

İlk adım dışarı aktarma isteği göndermektir. Bu örnekte belirli bir sayfa için dışarı aktarma isteği gönderilir.

```csharp
/////// Export sample ///////
private async Task<string> PostExportRequest(
    Guid reportId,
    Guid groupId,
    FileFormat format,
    IList<string> pageNames = null /* Get the page names from the GetPages API */)
        {
            var powerBIReportExportConfiguration = new PowerBIReportExportConfiguration
            {
                Settings = new ExportReportSettings
                {
                    Locale = "en-us",
                },

                // Note that page names differ from the page display names.
                // To get the page names use the GetPages API.
                Pages = pageNames?.Select(pn => new ExportReportPage(Name = pn)).ToList(),
            };

            var exportRequest = new ExportReportRequest
            {
                Format = format,
                PowerBIReportConfiguration = powerBIReportExportConfiguration,
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
        const int c_secToMillisec = 1000;
        do
        {
            if (DateTime.UtcNow.Subtract(startTime).TotalMinutes > timeOutInMinutes || token.IsCancellationRequested)
            {
                // Error handling for timeout and cancellations
                return null;
            }

            var httpMessage = await Client.Reports.GetExportToFileStatusInGroupWithHttpMessagesAsync(groupId, reportId, exportId);
            exportStatus = httpMessage.Body;

            // You can track the export progress using the PercentComplete that's part of the response
            SomeTextBox.Text = string.Format("{0} (Percent Complete : {1}%)", exportStatus.Status.ToString(), exportStatus.PercentComplete);

            if (exportStatus.Status == ExportState.Running || exportStatus.Status == ExportState.NotStarted)
            {
                // The recommended waiting time between polling requests can be found in the RetryAfter header
                // Note that this header is only populated when the status is either Running or NotStarted
                var retryAfter = httpMessage.Response.Headers.RetryAfter;
                var retryAfterInSec = retryAfter.Delta.Value.Seconds;
                await Task.Delay(retryAfterInSec * c_secToMillisec);
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
private readonly IDictionary<string, string> mediaTypeToSuffix = new Dictionary<string, string>
    {
        { "image/png", "png" },
        { "application/zip", "zip" },
        { "application/pdf", "pdf" },
        { "application/vnd.openxmlformats-officedocument.presentationml.presentation", "pptx" },
    };

private async Task<ExportedFile> GetExportedFile(
    Guid reportId,
    Guid groupId,
    Export export /* Get from the GetExportStatusAsync response */)
    {
        if (export.Status == ExportState.Succeeded)
        {
            var httpMessage = await Client.Reports.GetFileOfExportToFileInGroupWithHttpMessagesAsync(groupId, reportId, export.Id);
            var mediaType = httpMessage.Response.Content.Headers.ContentType.ToString().ToLower();

            if (!mediaTypeToSuffix.TryGetValue(mediaType, out string fileSuffix))
            {
                // Handle unexpected errors
            }
            else
            {
                return new ExportedFile
                {
                    FileStream = httpMessage.Body,
                    FileSuffix = fileSuffix,
                };
            }
        }

        return null;
    }

public class ExportedFile
{
    public Stream FileStream;
    public string FileSuffix;
}
```

### <a name="end-to-end-example"></a>Uçtan uca örnek

Bu, raporu dışarı aktarma işleminin uçtan uca bir örneğidir. Bu örnek şu aşamaları içerir:
1. [Dışarı aktarma isteği gönderme](#step-1---sending-an-export-request).
2. [Yoklama](#step-2---polling).
3. [Dosyayı alma](#step-3---getting-the-file).

```csharp
private async Task<ExportedFile> ExportPowerBIReport(
    Guid reportId,
    Guid groupId,
    FileFormat format,
    int pollingtimeOutInMinutes,
    CancellationToken token,
    IList<string> pageNames = null /* Get the page names from the GetPages API */)
        {
            try
            {
                var exportId = await PostExportRequest(reportId, groupId, format, pageNames);

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

## <a name="next-steps"></a>Sonraki adımlar

Müşterileriniz ve kuruluşunuz için nasıl içerik ekleyeceğinizi gözden geçirin:

> [!div class="nextstepaction"]
>[Müşterileriniz için ekleme](embed-sample-for-customers.md)

> [!div class="nextstepaction"]
>[Kuruluşunuz için ekleme](embed-sample-for-your-organization.md)
