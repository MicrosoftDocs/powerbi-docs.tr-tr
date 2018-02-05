---
title: "Sertifikalı Power BI özel görselleştirmeleri"
description: "Sertifika için özel görsel gönderme işlemi ve gereksinimleri. Önceden sertifikalanan özel görseller listesi."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/24/2018
ms.author: mihart
ms.openlocfilehash: f9824b29515481742c339bc76e766e5e62cf1716
ms.sourcegitcommit: be5223b62e9a5d57c52f8588d4e539d814751dd6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2018
---
# <a name="getting-a-custom-visual-certified"></a>Özel görselleri *sertifikalatma*
## <a name="what-is-meant-by-certified"></a>*Sertifikalı* ile belirtilmek istenen nedir?
*Sertifikalı özel görsel*, bir dizi kod gereksinimini karşılaşmış ve katı güvenlik testlerini geçmiş görsel demektir.  Bir özel görsel sertifikalandığında, [PowerPoint'e aktarılabilir](service-publish-to-powerpoint.md) ve kullanıcı [Rapor sayfalarına abone olduğunda](service-report-subscribe.md) alınan e-postalarda görüntülenir. Elbette, Power BI hizmeti ve Power BI Desktop raporlarına eklenen ve Power BI mobilde görüntülenip eklenen [standart özel görseller](power-bi-custom-visuals.md) gibi de kullanılabilir.

Bir Web geliştiricisi olarak kendi görselleştirmelerinizi oluşturmak ve bunları [Microsoft AppSource](https://appsource.microsoft.com)'a eklemek mi istiyorsunuz? Nasıl yapacağınızı öğrenmek için bkz.[Geliştirici Araçlarıyla çalışmaya başlama](service-custom-visuals-getting-started-with-developer-tools.md).


## <a name="certification-requirements"></a>Sertifikasyon gereksinimleri
* Microsoft AppSource onaylı    
* Özel görsel, API 1.2 veya sonraki bir sürümle yazılmıştır    
* Kod deposu gözden geçirme için kullanılabilir (örneğin, Görsel Kod GitHub aracılığıyla kullanımımıza açıktır)    
* Sadece genel kullanıma açık olarak gözden geçirilebilen OSS bileşenlerini kullanır    
* Dış hizmetlere ya da kaynaklara erişimi yoktur    

> **İPUCU**: Göndermeden önce kodunuzu doğrulamak için varsayılan güvenlik kural setiyle EsLint'i kullanmanızı öneririz.
> 
> 

## <a name="process-for-submitting-a-custom-visual-for-certification"></a>Sertifikasyon için özel görsel gönderme işlemi
Bir özel görseli sertifikasyona göndermek için:

1. Power BI Özel Görseller Destek (pbicvsupport@microsoft.com) birimine bir e-posta gönderin. E-postada aşağıdaki bilgileri verin:    
   
   * Başlık: Görsel Sertifikasyon Talebi    
   * Görsel kaynak kodunun bulunduğu GitHub deposu bağlantısı    
   * Gereksinimlere uygunluk bilgisi (yukarıya bakın)    
   * Kod ve güvenlik incelemesini geçtiği bilgisi    
2. Microsoft Özel Görseller ekibi, özel görseliniz sertifikalandığında ve Sertifikalı listesine (aşağıda) eklendiğinde ya da reddedilmesi durumunda düzeltilmesi gereken sorunların yer aldığı bir raporla sizi bilgilendirir. Microsoft ile açık bir iletişim hattı kurmak ve Sertifikalı görsellerini gerektiği şekilde güncelleştirmek geliştiricinin sorumluluğundadır.

## <a name="removal-of-power-bi-certified-custom-visuals"></a>Power BI Sertifikalı özel görsellerinin kaldırılması
Microsoft, kendi takdirine bağlı olarak, bir görseli Sertifikalı listesinden kaldırabilir.  

## <a name="list-of-custom-visuals-that-have-been-certified"></a>Sertifikalı özel görseller listesi
| AppSource bağlantısı | Video bağlantısı |
| --- | --- |
| [İlişkilendirme kuralları](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380815) | |
| [Aster plot](https://appsource.microsoft.com/product/power-bi-visuals/WA104380759?src=office&tab=Overview) | |
| [BciCalendar (Beyondsoft Calendar)](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381096?src=office&tab=Overview)  | |
| [Bowtie chart by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380838?src=office&tab=Overview) |[Video](https://youtu.be/So5xKMSpVJI) |
| [Box and Whisker](https://appsource.microsoft.com/product/power-bi-visuals/WA104380831?src=office&tab=Overview) | |
| [MAQ Software tuğla grafiği](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380836) | |
| [Akvelon kabarcık grafiği](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381340?src=office) | |
| [Bullet Chart](https://store.office.com/app.aspx?assetid=WA104380755) |[Video1](https://youtu.be/AOlsFYkfkcw)   [Video2](https://youtu.be/AQvd2FhRyCI) |
| [Bullet Chart by OKViz](https://store.office.com/bullet-chart-by-okviz-WA104380953.aspx) |[Video](https://youtu.be/mtvUNl9bMjA) |
| [Calendar by Tallan](https://appsource.microsoft.com/product/power-bi-visuals/WA104381146?src=office&tab=Overview) | |
| [OKViz Candlestick](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380952) | |
| [Chiclet slicer](https://store.office.com/chiclet-slicer-WA104380756.aspx) |[Video](https://youtu.be/iYOkJ1APueY) |
| [Çubuk grafik](https://appsource.microsoft.com/product/power-bi-visuals/WA104380761?src=office&tab=Overview) |[Video](https://youtu.be/AQvd2FhRyCI) |
| [Circular gauge by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380837?tab=Overview) | |
| [Cylindrical gauge](https://appsource.microsoft.com/product/power-bi-visuals/WA104380874) | |
| [Dial gauge](https://appsource.microsoft.com/product/power-bi-visuals/WA104381184) |[Video](https://youtu.be/AOlsFYkfkcw) |
| [Donut chart (Ring chart) by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380824?tab=Overview) |[Video](https://youtu.be/pDToHDFHnq8) |
| [MAQ Software Noktalı Grafik](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381101) | |
| [Dot Plot by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104381101?src=office&tab=Overview) |[Video](https://youtu.be/4lskRgcpFJY) |
| [Microsoft Noktalı Grafik](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380760?src=office) | |
| [Drill down donut chart by ZoomCharts](https://appsource.microsoft.com/product/power-bi-visuals/WA104380858) | |
| [Ayrıntılı Kartogram](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381045?src=office) | |
| [Ayrıntılı Koroplet](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381044?src=office) | |
| [ZoomCharts ayrıntılı sütun grafiği](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380881?src=office) | |
| [Zamana bağlı veriler için ZoomCharts ayrıntılı sütun grafiği](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380881) | |
| [ZoomCharts Ayrıntılı Halka Grafik](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380858) | |
| [Dual KPI](https://store.office.com/dual-kpi-WA104380774.aspx) |[Video](https://youtu.be/821o0-eVBXo?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x) |
| [Gelişmiş dağılım](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380762) | |
| [Enlighten Aquarium](https://appsource.microsoft.com/product/power-bi-visuals/WA104381112?src=office&tab=Overview) | |
| [Enlighten Bubble stack](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380868) | |
| [Enlighten Slicer](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380960?tab=Overview) | |
| [Enlighten Stack Shuffle](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380849) | |
| [Enlighten waffle chart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380850) | |
| [Enlighten World Flags](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380923) | |
| [Zorla Yönlendirilmiş Grafik](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380764) |[Video](https://youtu.be/YsTa7uyJ4sg) |
| [TBATS Tahmini](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381326?src=office) | |
| [Funnel with source]() | || [Gantt](https://store.office.com/gantt-WA104380765.aspx) |[Video](https://youtu.be/qJ7s_KrGiUU) |
| [Akvelon hiyerarşi grafiği](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381333?src=office) | |
| [Histogram](https://store.office.com/histogram-chart-WA104380776.aspx) | |
| [Horizotal Funnel](https://appsource.microsoft.com/product/power-bi-visuals/WA104380846) |[Video](https://youtu.be/SudZei68PPo) |
| [Görüntü Zaman Çizelgesi](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381254) | |
| [Bilgi Grafiği Tasarımcısı](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380898?src=office) | |
| [KPI Indicator](https://store.office.com/kpi-indicator-WA104380832.aspx) | |
| [MAQ Software KPI Bandı](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380946) | |
| [LineDot grafiği](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380766?src=office) | |
| [Linear gauge by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380821?src=office&tab=Overview) |[Video](https://youtu.be/AOlsFYkfkcw) |
| [Mekko chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380785?src=office&tab=Overview)  | [Video](https://youtu.be/90FLCKpgicA)|
| [Play Axis (Dynamic Slicer)](https://store.office.com/play-axis-dynamic-slicer-WA104380981.aspx) | |
| [Power KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104381083) |[Video](https://youtu.be/IvfIP3E6-1Q) |
| [Eğilim grafiği](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381006) | |
| [Radar chart](https://store.office.com/radar-chart-WA104380771.aspx) | |
| [Ring chart (Donut chart) by MAQSoftware](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380824?src=office&tab=Overview) | [Video](https://youtu.be/pDToHDFHnq8)|
| [MAQ Software döner grafik](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381007?src=office) |  |
| [Sankey chart](https://store.office.com/app.aspx?assetid=WA104380777.aspx) |[Video](https://youtu.be/WWP9wVUHGaA) |
| [Scroller](https://store.office.com/scroller-WA104381018.aspx) |[Video](https://youtu.be/uhRFQF2cGSY) |
| [Smart Filter by SQLBI](https://store.office.com/smart-filter-by-okviz-WA104380859.aspx) |[Video](https://youtu.be/gcJsDDRQq28) |
| [Sparkline by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380910?src=office&tab=Overview) |[Video](https://youtu.be/0m3Vnvso9tY) |
| [Akış grafiği](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380772?tab=Overview) |  |
| [Güneş ışığı](https://appsource.microsoft.com/product/power-bi-visuals/WA104380767?src=office&tab=Overview) | |
| [Table Heatmap](https://store.office.com/table-heatmap-WA104380818.aspx) | |
| [Tachometer](https://store.office.com/tachometer-WA104380937.aspx?) |[Video](https://www.youtube.com/watch?v=C3OXdETbS9o) |
| [Text wrapper](https://appsource.microsoft.com/product/power-bi-visuals/WA104380826) | |
| [Termometre](https://appsource.microsoft.com/product/power-bi-visuals/WA104380847?src=office&tab=Overview) | [Video](https://youtu.be/SPX9mgrAdBc)|
| [Time series decomposition](https://appsource.microsoft.com/product/power-bi-visuals/WA104380897) | |
| [Timeline slicer](https://store.office.com/timeline-slicer-WA104380786.aspx) |[Video](https://youtu.be/ozMtZ4_NZ10) |
| [Tornado chart](https://store.office.com/tornado-chart-WA104380768.aspx) |[Video](https://youtu.be/AQvd2FhRyCI) |
| [Klaus Birringer Ultimate Variance grafiği](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381140?src=office) | |
| [Ultimate Waterfall ücretsiz](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380956) | |
| [VitaraCharts - MicroChart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381165) | |
| [Waffle chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104381049?src=office&tab=Overview) |[Video](https://youtu.be/1vRqYUsm3Vk) |
| [Word Cloud](https://store.office.com/word-cloud-WA104380752.aspx?) |[Video](https://www.youtube.com/watch?v=AblTenl9fqo) |

## <a name="next-steps"></a>Sonraki adımlar
[Özel görseller geliştirici araçları ile çalışmaya başlama (Önizleme)](service-custom-visuals-getting-started-with-developer-tools.md)      
[Microsoft'un YouTube'daki özel görsel oynatma listesi](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)  
[Power BI'daki Görselleştirmeler](power-bi-report-visualizations.md)  
[Power BI'daki Özel Görselleştirmeler](power-bi-custom-visuals.md)  
[Microsoft AppSource'ta özel görseller yayımlama](developer/office-store.md)  
Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

