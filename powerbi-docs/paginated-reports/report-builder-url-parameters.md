---
title: Sayfalandırılmış raporlardaki URL parametreleri - Power BI Rapor Oluşturucusu
description: Bu konu başlığında, Power BI Report Builder ’ın rapor parametrelerine, ayarlayabileceğiniz özelliklere ve çok daha fazlasına yönelik yaygın kullanımlar açıklanmaktadır.
ms.service: powerbi
ms.subservice: report-builder
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
ms.reviewer: cfinlan
ms.custom: ''
ms.date: 09/09/2020
ms.openlocfilehash: f81cf6625f02f71b1ccf8bcd2c442ded3329083d
ms.sourcegitcommit: 002c140d0eae3137a137e9a855486af6c55ad957
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2020
ms.locfileid: "89642396"
---
# <a name="url-parameters-in-paginated-reports-in-power-bi"></a>Power BI’da bulunan sayfalandırılmış raporlardaki URL parametreleri

Bir URL’ye parametre ekleyerek, Power BI’daki sayfalandırılmış raporlara komut gönderebilirsiniz. Örneğin, belirli rapor parametresi değerlerini kullanarak raporu görüntülemiş olabilirsiniz. Önceden tanımlanmış URL erişimi parametrelerini kullanarak, URL’de bulunan bu bilgileri kapsülleyebilirsiniz. Power BI’ın raporu işleyiş biçimini daha da özelleştirerek işleme biçimlerine yönelik parametreler ekleyebilir veya rapor araç çubuğunun görünümünü ve kullanımını değiştirebilirsiniz. Ardından, diğer kişilerin rapor deneyiminin tarayıcıdaki gibi olması için bu URL’yi bir e-posta iletisine veya web sayfasına doğrudan yapıştırabilirsiniz. 

URL erişimi parametreleri aracılığıyla gerçekleştirebileceğiniz eylemler şunlardır: 

- Bir rapora rapor parametresi gönderme. 
- Rapor içeriğinin desteklenen bir dosya formatında dışarı aktarılmasını başlatma. 
- Parametreler bölmesini gizleme veya gösterme. 
- DeviceInfo ayarını belirtme. 

URL erişimi aracılığıyla kullanılabilen komut ve ayarların tam listesi için, bu makalenin sonraki kısımlarında bulabileceğiniz  [URL erişimi parametresi başvurusu](#url-access-parameter-reference) bölümüne bakın. 

## <a name="url-access-concepts"></a>URL erişimi kavramları 

Power BI’a gönderilen URL istekleri, hizmet tarafından işlenen parametreleri içerir. Hizmetin URL isteklerini işleme yöntemi, parametrelere, parametrelerin ön eklerine ve URL’nin içerdiği öğelerin türlerine bağlıdır. Sayfalandırılmış rapor URL’si işlevi, standart URL işlemeyi destekleyen çoğu tarayıcı ve uygulamayla uyumludur. 

## <a name="url-access-syntax"></a>URL erişimi söz dizimi 

URL istekleri, herhangi bir sırayla listelenen birden fazla parametreyi içerebilir. Parametreler & işaretiyle ayrılır. Ad ve değer çiftleri eşittir işareti (=) ile ayrılır. Örnek:

```
powerbiserviceurl?rp:parametervalueh&rdl:parameter=value  
```

## <a name="syntax-description"></a>Söz dizimi açıklaması 

### <a name="powerbiserviceurl"></a>powerbiserviceurl 

Power BI kiracınızın Web hizmeti URL’si. Örnek: 

URL erişimi parametrelerinin ad ve değer çiftlerini ayırmak için **&** kullanılır.

**ön ek** Power BI hizmetindeki bir eylemi belirten, URL parametresine yönelik ön ek (örneğin, rp: veya rdl:). 

> [!NOTE]
> Büyük/küçük harfe duyarlı olan rapor parametreleri için bir parametre ön eki gerekir. 

**parameter** Parametrenin adı. 

### <a name="value"></a>değer 

Kullanılan parametrenin değerine karşılık gelen URL Metni. 

Rapor parametrelerini URL’ye geçirme örnekleri için bkz.  [Bir rapor parametresini URL’ye geçirme](report-builder-url-pass-parameters.md).

## <a name="url-access-parameter-reference"></a>URL erişimi parametresi başvurusu

Power BI’daki sayfalandırılmış raporlarınızın görünümünü ve kullanımını yapılandırmak için, aşağıdaki parametreleri URL’nin bir parçası olarak kullanabilirsiniz. En sık kullanılan parametreler bu bölümde listelenir. Parametreler büyük/küçük harfe duyarlı değildir ve çıkış biçimiyle ilişkili olanlar, parametre ön ekiyle `rdl:` başlar.  

### <a name="report-commands-rdl"></a>Rapor komutları (`rdl:`) 

**Dışarı aktarma biçimi** Bir raporun işleneceği ve dışarı aktarılacağı biçimi belirtir.

Örnek: rdl:format=PDF

Kullanılabilir değerler şunlardır:
 
- PPTX (PowerPoint)
- MHTML 
- GÖRÜNTÜ 
- EXCELOPENXML (EXCEL) 
- WORDOPENXML (WORD) 
- CSV 
- PDF 
- ACCESSIBLEPDF (PDF)
- XML 

**Rapor Görünümü**: Raporu görüntülemek için kullanılan görünüm türünü belirtir.

-   rdl:reportView

    - "interactive" (varsayılan): Raporu etkileşimli modda yükler.
    - "pageView": Raporu sayfa görünümü modunda yükler.

**Parametre paneli** Rapor yüklendiğinde parametre panelinin kapanacağını veya açık olacağını ya da tamamen gizleneceğini belirtir.

-   rdl:parameterPanel

    - “daraltılmış”: raporu, parametre paneli kapalı şekilde yükler. Parametre düğmesi, kullanıcıların genişlet düğmesine tıklayabilmesi için etkinleştirilir;
    - “gizli”: raporu, parametre paneli kapalı ve parametre düğmesi devre dışı şekilde yükler;
    - “genişletilmiş” (varsayılan): raporu, parametre paneli açık ve parametre düğmesi etkin şekilde yükler;

**Cihaz Bilgisi** Aşağıdaki dışarı aktarma biçimleri için ek çıkış parametreleri belirtebilirsiniz. 

PDF/ACCESSIBLEPDF:

- rdl:AccessiblePDF=true/false
- rdl:Columns=integer
- rdl:ColumnSpacing=decimal(in)
- rdl:DpiX=integer
- rdl:DpiY=integer
- rdl:EndPage=integer
- rdl:HumanReadablePDF=true/false
- rdl:MarginBottom=decimal(in)
- rdl:MarginLeft=decimal(in)
- rdl:MarginRight=decimal(in)
- rdl:MarginTop=decimal(in)
- rdl:PageHeight=decimal(in)
- rdl:PageWidth=decimal(in)
    - rdl:StartPage=integer
    
CSV:

- rdl:Encoding=string
- rdl:ExcelMode=true/false
- rdl:FieldDelimiter=string
- rdl:NoHeader=true/false
- rdl:Qualifier=string
- rdl:RecordDelimiter=string
- rdl:SuppressLineBreaks=true/false
    - rdl:UseFormattedValues=true/false
    
WORDOPENXML (WORD):

- rdl:AutoFit=string -> True/False/Never/Default
- rdl:ExpandToggles=true/false
- rdl:FixedPageWidth=true/false
- rdl:OmitHyperlinks=true/false
- rdl:OmitDrillthroughs=true/false

EXCELOPENXML (EXCEL):

- rdl:OmitDocumentMap=true/false
- rdl:OmitFormulas=true/false
    - rdl:SimplePageHeaders=true/false
    
PPTX (PowerPoint):
 
- rdl:Columns=integer
- rdl:ColumnSpacing=decimal(in)
- rdl:DpiX=integer
- rdl:DpiY=integer
- rdl:EndPage=integer
- rdl:MarginBottom=decimal(in)
- rdl:MarginLeft=decimal(in)
- rdl:MarginRight=decimal(in)
- rdl:MarginTop=decimal(in)
- rdl:PageHeight=decimal(in)
- rdl:PageWidth=decimal(in)
- rdl:StartPage=integer
    - rdl:UseReportPageSize=true/false

XML:

- rdl:XSLT=string
- rdl:MIMEType=string
- rdl:UseFormattedValues=true/false
- rdl:Indented=true/false
- rdl:OmitNamespace=true/false
- rdl:OmitSchema=true/false
- rdl:Encoding=string
- rdl:Schema=true/false

**Köprüyü aynı tarayıcı penceresine açma** Power BI’ın bu köprüyü aynı tarayıcı penceresinde açmasını sağlamak için raporunuzdaki köprü URL’sine “rdl:targetSameWindow=true” ekleyebilirsiniz. Rapora köprüler ekleme hakkında daha fazla bilgi için SQL Server Reporting Services belgelerindeki [URL’ye köprü ekleme](https://docs.microsoft.com/sql/reporting-services/report-design/add-a-hyperlink-to-a-url-report-builder-and-ssrs) sayfasına bakın.

## <a name="next-steps"></a>Sonraki adımlar

- [Power BI’da, bir sayfalandırılmış rapor için URL’de rapor parametresi geçirme](report-builder-url-pass-parameters.md)
- [Power BI Premium’da sayfalandırılmış raporlar nelerdir?](paginated-reports-report-builder-power-bi.md)
