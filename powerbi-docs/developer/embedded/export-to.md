---
title: Power BI ekli analizi raporlarını dışarı aktarma API'si
description: Katıştırılmış Power BI raporunu dışarı aktarmayı öğrenin.
author: KesemSharabi
ms.author: kesharab
ms.topic: how-to
ms.service: powerbi
ms.subservice: powerbi-developer
ms.date: 02/09/2021
ms.openlocfilehash: 68d4802ebb150827982a348bc67f6f46f60812be
ms.sourcegitcommit: de3b45cad5ae21c77692ce4490e21de01d21e6f3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/10/2021
ms.locfileid: "100013579"
---
# <a name="export-power-bi-report-to-file-preview"></a>Power BI raporunu dosyaya aktarma (önizleme)

`exportToFile` API’si, REST çağrısı kullanarak Power BI raporunu dışarı aktarmaya olanak tanır. Şu dosya biçimleri desteklenir:
* **.pptx** (PowerPoint)
* **.pdf**
* **.png**
    * .png dosyasına aktarırken, birden çok sayfalı bir rapor zip dosyasında sıkıştırılır
    * .zip dosyası içindeki her dosya bir rapor sayfasını temsil eder
    * Sayfa adları, [Sayfaları Alma](/rest/api/power-bi/reports/getpages) veya [Gruptaki Sayfaları Alma](/rest/api/power-bi/reports/getpagesingroup) API’lerinin dönüş değerleriyle aynı olur

## <a name="usage-examples"></a>Kullanım örnekleri

Dışarı aktarma özelliği çeşitli yollarla kullanabilirsiniz. Aşağıda birkaç örnek verilmiştir:

* **Yazdırmaya gönder düğmesi** - Uygulamanızda tıklandığında dışarı aktarma işi başlatan bir düğme oluşturun. İş görüntülenen raporu .pdf veya .pptx olarak dışarı aktarabilir ve tamamlandığında kullanıcı dosyayı bir indirme olarak alabilir. Yer işaretlerini kullanarak, yapılandırılmış filtreler, dilimleyiciler ve ek ayarlar da dahil olmak üzere raporu belirli bir durumda dışarı aktarabilirsiniz. API zaman uyumsuz olduğundan dosyanın kullanılabilir duruma gelmesi biraz zaman alabilir.

* **E-posta eki** - Önceden ayarlanmış aralıklarla .pdf raporunun eklendiği otomatik bir e-posta gönderin. Yöneticilere haftalık rapor gönderme işlemini otomatikleştirmek isterseniz bu senaryo yararlı olabilir. Daha fazla bilgi için bkz. [Power Automate ile bir Power BI raporunu dışarı aktarma ve e-posta ile gönderme](../../collaborate-share/service-automate-power-bi-report-export.md)

## <a name="using-the-api"></a>API'yi kullanma

API’yi kullanmadan önce aşağıdaki [yönetici kiracı ayarlarının](../../admin/service-admin-portal.md#tenant-settings) etkinleştirildiğini doğrulayın:
* **Raporları PowerPoint sunuları veya PDF belgeleri olarak dışarı aktarma** - Varsayılan olarak etkindir.
* **Raporları resim dosyaları olarak dışarı aktarma** - Yalnızca *.png* için gereklidir ve varsayılan olarak devre dışı bırakılır.

API zaman uyumsuzdur. [exportToFile](/rest/api/power-bi/reports/exporttofile) API’si çağrıldığında bir dışarı aktarma işini tetikler. Dışarı aktarma işi tetiklendikten sonra, işi tamamlanana kadar izlemek için [yoklama](/rest/api/power-bi/reports/getexporttofilestatus) özelliğini kullanın.

Yoklama sırasında API tamamlanan çalışma miktarını temsil eden bir sayı döndürür. Her bir dışarı aktarma işindeki iş, işteki dışarı aktarmalar toplamı temel alınarak hesaplanır. Dışarı aktarma, tek bir görseli veya yer işaretlerini içeren veya içermeyen bir sayfanın dışarı aktarılmasını içerir. Tüm dışarı aktarmalar aynı ağırlığa sahiptir. Örneğin dışa aktarma işiniz, 10 sayfalı bir raporu dışarı aktarmayı içeriyorsa ve yoklama 70 değerini döndürürse, API 'nin dışarı aktarma işindeki 10 sayfadan yedi bir işlendiği anlamına gelir.

Dışarı aktarma tamamlandığında yoklama API çağrısı dosyayı almak için bir [Power BI URL](/rest/api/power-bi/reports/getfileofexporttofile)’si döndürür. URL 24 saat süreyle kullanılabilir.

## <a name="supported-features"></a>Desteklenen özellikler

Bu bölümde, aşağıdaki desteklenen özelliklerin işlemi açıklanmaktadır:

* [Yazdırılacak sayfaları seçme](#selecting-which-pages-to-print)
* [Bir sayfayı veya tek görseli dışarı aktarma](#exporting-a-page-or-a-single-visual)
* [Bookmarks](#bookmarks)
* [Filtreler](#filters)
* [Kimlik Doğrulaması](#authentication)
* [Satır Düzeyi Güvenlik (RLS)](#row-level-security-rls)
* [Veri koruma](#data-protection)
* [Yerelleştirme](#localization)

### <a name="selecting-which-pages-to-print"></a>Yazdırılacak sayfaları seçme

[Sayfaları Alma](/rest/api/power-bi/reports/getpages) veya [Gruptaki Sayfaları Alma](/rest/api/power-bi/reports/getpagesingroup) dönüş değerine göre yazdırmak istediğiniz sayfaları belirtin. Ayrıca dışarı aktardığınız sayfaların sırasını da belirtebilirsiniz.

### <a name="exporting-a-page-or-a-single-visual"></a>Bir sayfayı veya tek görseli dışarı aktarma

Dışarı aktarmak için bir sayfa veya tek bir görsel belirleyebilirsiniz. Sayfalar, yer işaretleri ile veya olmadan aktarılabilir.

Dışarı aktarma türüne bağlı olarak, [Exportreportpage](/rest/api/power-bi/reports/exporttofile#exportreportpage) nesnesine farklı öznitelikler geçirmeniz gerekir. Aşağıdaki tabloda, her bir dışarı aktarma işi için hangi özniteliklerin gerektiği belirtilir.  

>[!NOTE]
>Tek bir görseli dışarı aktarmak, bir sayfayı dışa aktarma ile aynı ağırlığa sahiptir (yer işaretleri içeren veya içermeyen). Bu, sistem hesaplamaları açısından her iki işlemin de aynı değeri üstolmayacağı anlamına gelir.

|Öznitelik   |Sayfa     |Tek görsel  |Yorumlar|
|------------|---------|---------|---|
|`bookmark`  |İsteğe Bağlı |![Geçerli değildir.](../../media/no.png)|Belirli bir durumdaki bir sayfayı dışarı aktarmak için kullanın|
|`pageName`  |![Şunun için geçerlidir:](../../media/yes.png)|![Şunun için geçerlidir:](../../media/yes.png)|[GetPages](/rest/api/power-bi/reports/getpage) REST API veya `getPages` istemci API 'sini kullanın. Daha fazla bilgi için bkz. [sayfaları ve görselleri edinme](/javascript/api/overview/powerbi/get-visuals).   |
|`visualName`|![Geçerli değildir.](../../media/no.png)|![Şunun için geçerlidir:](../../media/yes.png)|Görselin adını almanın iki yolu vardır:<li>`getVisuals`ISTEMCI API 'sini kullanın. Daha fazla bilgi için bkz. [sayfaları ve görselleri edinme](/javascript/api/overview/powerbi/get-visuals).</li><li>Görselin seçildiği zaman tetiklenen *Visualclicked* olayını dinleyin ve günlüğe kaydedin. Daha fazla bilgi için bkz. [olayları işleme](/javascript/api/overview/powerbi/handle-events)</li>. |

### <a name="bookmarks"></a>Yer imleri

[Yer işaretleri](../../consumer/end-user-bookmarks.md) uygulanan filtreler ve rapordaki görsellerin durumu dahil olmak üzere belirli bir rapor yapılandırmasını kaydetmek için kullanılabilir. [exportToFile](/rest/api/power-bi/reports/exporttofile) API'sini kullanarak bir raporun yer işaretini program aracılığıyla ve iki farklı şekilde dışarı aktarabilirsiniz:

* **Var olan bir yer işaretini dışarı aktarma**

    Var olan bir [rapor yer işaretini](../../consumer/end-user-bookmarks.md#report-bookmarks) dışarı aktarmak için `name` özelliğini ve [yer işaretleri JavaScript API'sini](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Bookmarks) kullanarak alabileceğiniz benzersiz (büyük/küçük harfe duyarlı) kimliği kullanın.

* **Raporun durumunu dışarı aktarma**

    Raporun geçerli durumunu dışarı aktarmak için `state` özelliğini kullanın. Örneğin yer işaretinin `bookmarksManager.capture` yöntemini kullanarak belirli bir kullanıcının raporda yaptığı değişiklikleri yakalayabilir ve ardından `capturedBookmark.state` kullanarak bunu geçerli durumunda dışarı aktarabilirsiniz.

>[!NOTE]
>[Kişisel yer işaretleri](../../consumer/end-user-bookmarks.md#personal-bookmarks) ve [kalıcı filtreler](https://powerbi.microsoft.com/blog/announcing-persistent-filters-in-the-service/) desteklenmez.

### <a name="filters"></a>Filtreler

[PowerBIReportExportConfiguration](/rest/api/power-bi/reports/exporttofile#powerbireportexportconfiguration)'da `reportLevelFilters` kullanarak raporu filtrelenmiş durumda dışarı aktarabilirsiniz.

Filtrelenmiş raporu dışarı aktarmak için, filtre olarak kullanmak istediğiniz [URL sorgu dizesi parametrelerini](../../collaborate-share/service-url-filters.md) [ExportFilter](/rest/api/power-bi/reports/exporttofile#exportfilter) öğesine ekleyin. Dizeyi girerken URL sorgu parametresinin `?filter=` bölümünü kaldırmalısınız.

Aşağıdaki tabloda `ExportFilter` öğesine geçirebileceğiniz dizeler için birkaç söz dizimi örneği yer alır.

|Filtre    |Syntax    |Örnek    |
|---|----|----|----|
|Alanda bir değer    |Table/Field eq 'değer'    |Store/Territory eq 'NC'    |
|Alanda birden fazla değer    |Table/Field in ('değer1', 'değer2')     |Store/Territory in ('NC', 'TN')    |
|Bir alanda benzersiz bir değer ve başka bir alanda farklı bir benzersiz değer    |Table/Field1 eq 'değer1' and Table/Field2 eq 'değer2'    |Store/Territory eq 'NC' and Store/Chain eq 'Fashions Direct'    |

>[!NOTE]
>`ReportLevelFilters` tek bir [ExportFilter](/rest/api/power-bi/reports/exporttofile#exportfilter) içerebilir.

### <a name="authentication"></a>Kimlik Doğrulaması

Bir kullanıcı (veya ana kullanıcı) ya da [hizmet sorumlusunu](embed-service-principal.md) kullanarak kimlik doğrulaması yapabilirsiniz.

### <a name="row-level-security-rls"></a>Satır Düzeyi Güvenlik (RLS)

[Satır Düzeyi Güvenlik (RLS)](embedded-row-level-security.md) ile yalnızca belirli kullanıcıların görebileceği verilerin gösterildiği raporları dışarı aktarabilirsiniz. Örneğin bölgesel rollerle tanımlanmış bir satış raporunu dışarı aktarıyorsanız, raporu programlama yoluyla filtreleyerek yalnızca belili bir bölgenin görüntülenmesini sağlayabilirsiniz.

RLS kullanarak dışarı aktarmak için aşağıdaki izinlere sahip olmalısınız:
* Raporun bağlandığı veri kümesi için yazma ve yeniden paylaşma izinleri
* Rapor bir v1 çalışma alanında yer alıyorsa, çalışma alanı yöneticisi olmalısınız
* Rapor bir v2 çalışma alanında yer alıyorsa, çalışma alanı üyesi veya yöneticisi olmanız gerekir

### <a name="data-protection"></a>Veri koruma

.pdf ve .pptx biçimleri [duyarlılık etiketlerini](../../admin/service-security-sensitivity-label-overview.md) destekler. Duyarlılık etiketi olan bir raporu .pdf veya .pptx biçimine aktarıyorsanız, dışarı aktarılan dosya raporu duyarlılık etiketiyle görüntüler.

Duyarlılık etiketine sahip olan raporlar [hizmet sorumlusu](embed-service-principal.md) kullanılarak .pdf veya .pptx dosyasına aktarılamaz.

### <a name="localization"></a>Localization (Yerelleştirme)

`exportToFile` API’sini kullanırken istediğiniz yerel ayarı geçirebilirsiniz. Yerelleştirme ayarları raporun görüntülenme şeklini etkiler; örneğin biçimlendirmeyi seçili yerel ayara göre değiştirir.

## <a name="concurrent-requests"></a>Eş zamanlı istekler

`exportToFile` eş zamanlı dışarı aktarma işi isteklerini destekler. Aşağıdaki tabloda raporunuzun bulunduğu SKU’ya bağlı olarak aynı anda çalıştırabileceğiniz işlerin sayısı gösterilir. Eş zamanlı istekler rapor sayfalarına karşılık gelir. Örneğin A6 SKU’sundaki bir rapor isteğinin 20 sayfası eş zamanlı olarak işlenir. Bu işlem her biri tek sayfa içeren 20 dışarı aktarma isteği göndermekle yaklaşık aynı zamanı alır.

Eş zamanlı istek sayısını aşan işler sonlandırılmaz. Örneğin A1 SKU’sunda üç sayfalık bir raporu dışarı aktarıyorsanız, ilk iş çalıştırılır ve ardından diğer iki iş sonraki iki yürütme döngüsünü bekler.

>[!NOTE]
>`exporToFile` API’sini kullanarak Power BI raporunu bir dosyaya aktarmak [Kullanıcı Başına Premium (PPU)](../../admin/service-premium-per-user-faq.md) için desteklenmez. 

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
* Genel önizleme için, saat başına Power BI dışarı aktarma sayısı, kapasiteye göre 50 ile sınırlıdır. Dışarı aktarma, tek bir görseli veya bir rapor sayfasını, yer işaretleri içeren veya olmayan bir şekilde dışa aktarmayı ifade eder ve sayfalandırılmış raporların dışarı aktarılmasını içermez.
* Dışarı aktarılan raporların dosya boyutu 250 MB’ı aşamaz.
* .png’ye aktarırken duyarlılık etiketleri desteklenmez.
* Dışarı aktarılan bir rapora dahil edilebilir dışarı aktarmalar (tek görseller veya rapor sayfaları) sayısı 50 ' dir (Bu, sayfalandırılmış raporların dışarı aktarılmasını içermez). İstek daha fazla dışarı aktarma içeriyorsa, API bir hata döndürür ve dışarı aktarma işi iptal edilir.
* [Kişisel yer işaretleri](../../consumer/end-user-bookmarks.md#personal-bookmarks) ve [kalıcı filtreler](https://powerbi.microsoft.com/blog/announcing-persistent-filters-in-the-service/) desteklenmez.
* Aşağıdaki Power BI görselleri desteklenmez. Bu görselleri içeren bir rapor dışarı aktarıldığında, raporda bu görsellerin bulunduğu bölümler işlenmez ve bir hata simgesi görüntülenir.
    * Sertifikasız Power BI görselleri
    * R görselleri
    * PowerApps
    * Python görselleri
    * Visio

## <a name="code-examples"></a>Kod örnekleri

Dışarı aktarma işi oluştururken izlenmesi gereken üç adım vardır:

1. [Dışarı aktarma isteği gönderme](#step-1---sending-an-export-request).
2. [Yoklama](#step-2---polling).
3. [Dosyayı alma](#step-3---getting-the-file).
4. [Dosya akışını kullanma](#step-4---using-the-file-stream).

Bu bölümde her adım için örnekler sağlanır.

### <a name="step-1---sending-an-export-request"></a>1\. Adım - dışarı aktarma isteği gönderme

İlk adım dışarı aktarma isteği göndermektir. Bu örnekte belirli bir sayfa için dışarı aktarma isteği gönderilir.

```csharp
private async Task<string> PostExportRequest(
    Guid reportId,
    Guid groupId,
    FileFormat format,
    IList<string> pageNames = null, /* Get the page names from the GetPages REST API */
    string urlFilter = null)
{
    var powerBIReportExportConfiguration = new PowerBIReportExportConfiguration
    {
        Settings = new ExportReportSettings
        {
            Locale = "en-us",
        },
        // Note that page names differ from the page display names
        // To get the page names use the GetPages REST API
        Pages = pageNames?.Select(pn => new ExportReportPage(Name = pn)).ToList(),
        // ReportLevelFilters collection needs to be instantiated explicitly
        ReportLevelFilters = !string.IsNullOrEmpty(urlFilter) ? new List<ExportFilter>() { new ExportFilter(urlFilter) } : null,

    };

    var exportRequest = new ExportReportRequest
    {
        Format = format,
        PowerBIReportConfiguration = powerBIReportExportConfiguration,
    };

    // The 'Client' object is an instance of the Power BI .NET SDK
    var export = await Client.Reports.ExportToFileInGroupAsync(groupId, reportId, exportRequest);

    // Save the export ID, you'll need it for polling and getting the exported file
    return export.Id;
}
```

### <a name="step-2---polling"></a>2\. Adım - yoklama

Dışarı aktarma isteğini gönderdikten sonra, beklediğiniz dışarı aktarma dosyasının ne zaman hazır olduğunu belirlemek için yoklamayı kullanın.

```csharp
private async Task<HttpOperationResponse<Export>> PollExportRequest(
    Guid reportId,
    Guid groupId,
    string exportId /* Get from the PostExportRequest response */,
    int timeOutInMinutes,
    CancellationToken token)
{
    HttpOperationResponse<Export> httpMessage = null;
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

        // The 'Client' object is an instance of the Power BI .NET SDK
        httpMessage = await Client.Reports.GetExportToFileStatusInGroupWithHttpMessagesAsync(groupId, reportId, exportId);
        exportStatus = httpMessage.Body;

        // You can track the export progress using the PercentComplete that's part of the response
        SomeTextBox.Text = string.Format("{0} (Percent Complete : {1}%)", exportStatus.Status.ToString(), exportStatus.PercentComplete);
        if (exportStatus.Status == ExportState.Running || exportStatus.Status == ExportState.NotStarted)
        {
            // The recommended waiting time between polling requests can be found in the RetryAfter header
            // Note that this header is not always populated
            var retryAfter = httpMessage.Response.Headers.RetryAfter;
            var retryAfterInSec = retryAfter.Delta.Value.Seconds;
            await Task.Delay(retryAfterInSec * c_secToMillisec);
        }
    }
    // While not in a terminal state, keep polling
    while (exportStatus.Status != ExportState.Succeeded && exportStatus.Status != ExportState.Failed);

    return httpMessage;
}
```

### <a name="step-3---getting-the-file"></a>3\. Adım - dosyayı alma

Yoklama bir URL döndürdüğünde, bu örneği kullanarak dosyayı alın.

```csharp
private async Task<ExportedFile> GetExportedFile(
    Guid reportId,
    Guid groupId,
    Export export /* Get from the PollExportRequest response */)
{
    if (export.Status == ExportState.Succeeded)
    {
        // The 'Client' object is an instance of the Power BI .NET SDK
        var fileStream = await Client.Reports.GetFileOfExportToFileAsync(groupId, reportId, export.Id);
        return new ExportedFile
        {
            FileStream = fileStream,
            FileSuffix = export.ResourceFileExtension,
        };
    }
    return null;
}

public class ExportedFile
{
    public Stream FileStream;
    public string FileSuffix;
}
```

### <a name="step-4---using-the-file-stream"></a>4\. Adım - Dosya akışını kullanma

Dosya akışını kullanıyorsanız gereksinimlerinize göre düzenleyebilirsiniz. Örneğin bunu e-posta ile gönderebilir veya dışarı aktarılan raporları indirmek için kullanabilirsiniz.

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
    IList<string> pageNames = null,  /* Get the page names from the GetPages REST API */
    string urlFilter = null)
{
    const int c_maxNumberOfRetries = 3; /* Can be set to any desired number */
    const int c_secToMillisec = 1000;
    try
    {
        Export export = null;
        int retryAttempt = 1;
        do
        {
            var exportId = await PostExportRequest(reportId, groupId, format, pageNames, urlFilter);
            var httpMessage = await PollExportRequest(reportId, groupId, exportId, pollingtimeOutInMinutes, token);
            export = httpMessage.Body;
            if (export == null)
            {
                // Error, failure in exporting the report
                return null;
            }
            if (export.Status == ExportState.Failed)
            {
                // Some failure cases indicate that the system is currently busy. The entire export operation can be retried after a certain delay
                // In such cases the recommended waiting time before retrying the entire export operation can be found in the RetryAfter header
                var retryAfter = httpMessage.Response.Headers.RetryAfter;
                if(retryAfter == null)
                {
                    // Failed state with no RetryAfter header indicates that the export failed permanently
                    return null;
                }

                var retryAfterInSec = retryAfter.Delta.Value.Seconds;
                await Task.Delay(retryAfterInSec * c_secToMillisec);
            }
        }
        while (export.Status != ExportState.Succeeded && retryAttempt++ < c_maxNumberOfRetries);

        if (export.Status != ExportState.Succeeded)
        {
            // Error, failure in exporting the report
            return null;
        }

        var exportedFile = await GetExportedFile(reportId, groupId, export);

        // Now you have the exported file stream ready to be used according to your specific needs
        // For example, saving the file can be done as follows:
        /*
            var pathOnDisk = @"C:\temp\" + export.ReportName + exportedFile.FileSuffix;

            using (var fileStream = File.Create(pathOnDisk))
            {
                exportedFile.FileStream.CopyTo(fileStream);
            }
        */

        return exportedFile;
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
>[Sayfalandırılmış raporu dosyaya aktarma](export-paginated-report.md)

> [!div class="nextstepaction"]
>[Müşterileriniz için ekleme](embed-sample-for-customers.md)

> [!div class="nextstepaction"]
>[Kuruluşunuz için ekleme](embed-sample-for-your-organization.md)

> [!div class="nextstepaction"]
>[Power Automate ile Power BI raporunu dışarı aktarma ve e-posta ile gönderme](../../collaborate-share/service-automate-power-bi-report-export.md)
