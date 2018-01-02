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
ms.date: 11/20/2017
ms.author: mihart
ms.openlocfilehash: 3d51475b300fadc55f33960b03c3adc0031a39b8
ms.sourcegitcommit: 12236d08c27c7ee3fabb7ef9d767e9dee693f8aa
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="getting-a-custom-visual-certified"></a>Özel görselleri *sertifikalatma*
## <a name="what-is-meant-by-certified"></a>*Sertifikalı* ile belirtilmek istenen nedir?
*Sertifikalı özel görsel*, bir dizi kod gereksinimini karşılaşmış ve katı güvenlik testlerini geçmiş görsel demektir.  Bir özel görsel sertifikalandığında, [PowerPoint'e aktarılabilir](service-publish-to-powerpoint.md) ve kullanıcı [Rapor sayfalarına abone olduğunda](service-report-subscribe.md) alınan e-postalarda görüntülenir.

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
| [Aster plot](https://appsource.microsoft.com/product/power-bi-visuals/WA104380759?src=office&tab=Overview) | |
| [Bowtie chart by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380838?src=office&tab=Overview) |[Video](https://youtu.be/So5xKMSpVJI) |
| [BciCalendar (Beyondsoft Calendar)](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381096?src=office&tab=Overview)  | |
| [Box and Whisker](https://appsource.microsoft.com/product/power-bi-visuals/WA104380831?src=office&tab=Overview) | |
| [Bullet Chart](https://store.office.com/app.aspx?assetid=WA104380755) |[Video1](https://youtu.be/AOlsFYkfkcw)   [Video2](https://youtu.be/AQvd2FhRyCI) |
| [Bullet Chart by OKViz](https://store.office.com/bullet-chart-by-okviz-WA104380953.aspx) |[Video](https://youtu.be/mtvUNl9bMjA) |
| [Calendar by Tallan](https://appsource.microsoft.com/product/power-bi-visuals/WA104381146?src=office&tab=Overview) | |
| [Chiclet slicer](https://store.office.com/chiclet-slicer-WA104380756.aspx) |[Video](https://youtu.be/iYOkJ1APueY) |
| [Chord Chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380761?src=office&tab=Overview) |[Video](https://youtu.be/AQvd2FhRyCI) |
| [Circular gauge by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380837?tab=Overview) | |
| [Cylindrical gauge](https://appsource.microsoft.com/product/power-bi-visuals/WA104380874) | |
| [Dial gauge](https://appsource.microsoft.com/product/power-bi-visuals/WA104381184) |[Video](https://youtu.be/AOlsFYkfkcw) |
| [Donut chart (Ring chart) by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380824?tab=Overview) |[Video](https://youtu.be/pDToHDFHnq8) |
| [Dot Plot by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104381101?src=office&tab=Overview) |[Video](https://youtu.be/4lskRgcpFJY) |
| [Drill down donut chart by ZoomCharts](https://appsource.microsoft.com/product/power-bi-visuals/WA104380858) | |
| [Dual KPI](https://store.office.com/dual-kpi-WA104380774.aspx) |[Video](https://youtu.be/821o0-eVBXo?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x) |
| [Enlighten Aquarium](https://appsource.microsoft.com/product/power-bi-visuals/WA104381112?src=office&tab=Overview) | |
| Enlighten World Flags - yakında | |
| Enlighten Stack Shuffle - yakında | |
| [Gantt](https://store.office.com/gantt-WA104380765.aspx) |[Video](https://youtu.be/qJ7s_KrGiUU) |
| [Histogram](https://store.office.com/histogram-chart-WA104380776.aspx) | |
| [Horizotal Funnel](https://appsource.microsoft.com/product/power-bi-visuals/WA104380846) |[Video](https://youtu.be/SudZei68PPo) |
| [KPI Indicator](https://store.office.com/kpi-indicator-WA104380832.aspx) | |
| [Linear gauge by MAQ Software](https://appsource.microsoft.com/product/power-bi-visuals/WA104380821?src=office&tab=Overview) |[Video](https://youtu.be/AOlsFYkfkcw) |
| [Mekko chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104380785?src=office&tab=Overview)  | [Video](https://youtu.be/90FLCKpgicA)|
| [Play Axis (Dynamic Slicer)](https://store.office.com/play-axis-dynamic-slicer-WA104380981.aspx) | |
| [Power KPI](https://appsource.microsoft.com/product/power-bi-visuals/WA104381083) |[Video](https://youtu.be/IvfIP3E6-1Q) |
| [Radar chart](https://store.office.com/radar-chart-WA104380771.aspx) | |
| [Ring chart (Donut chart) by MAQSoftware](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380824?src=office&tab=Overview) | [Video](https://youtu.be/pDToHDFHnq8)|
| [Sankey chart](https://store.office.com/app.aspx?assetid=WA104380777.aspx) |[Video](https://youtu.be/WWP9wVUHGaA) |
| [Scroller](https://store.office.com/scroller-WA104381018.aspx) |[Video](https://youtu.be/uhRFQF2cGSY) |
| [Smart Filter by SQLBI](https://store.office.com/smart-filter-by-okviz-WA104380859.aspx) |[Video](https://youtu.be/gcJsDDRQq28) |
| [Sparkline by OKViz](https://appsource.microsoft.com/product/power-bi-visuals/WA104380910?src=office&tab=Overview) |[Video](https://youtu.be/0m3Vnvso9tY) |
| [Güneş ışığı](https://appsource.microsoft.com/product/power-bi-visuals/WA104380767?src=office&tab=Overview) | |
| [Tachometer](https://store.office.com/tachometer-WA104380937.aspx?) |[Video](https://www.youtube.com/watch?v=C3OXdETbS9o) |
| [Termometre](https://appsource.microsoft.com/product/power-bi-visuals/WA104380847?src=office&tab=Overview) | [Video](https://youtu.be/SPX9mgrAdBc)|
| [Time series decomposition](https://appsource.microsoft.com/product/power-bi-visuals/WA104380897) | |
| [Table Heatmap](https://store.office.com/table-heatmap-WA104380818.aspx) | |
| [Text wrapper](https://appsource.microsoft.com/product/power-bi-visuals/WA104380826) | |
| [Timeline slicer](https://store.office.com/timeline-slicer-WA104380786.aspx) |[Video](https://youtu.be/ozMtZ4_NZ10) |
| [Tornado chart](https://store.office.com/tornado-chart-WA104380768.aspx) |[Video](https://youtu.be/AQvd2FhRyCI) |
| [Waffle chart](https://appsource.microsoft.com/product/power-bi-visuals/WA104381049?src=office&tab=Overview) |[Video](https://youtu.be/1vRqYUsm3Vk) |
| [Word Cloud](https://store.office.com/word-cloud-WA104380752.aspx?) |[Video](https://www.youtube.com/watch?v=AblTenl9fqo) |

## <a name="next-steps"></a>Sonraki adımlar
[Özel görseller geliştirici araçları ile çalışmaya başlama (Önizleme)](service-custom-visuals-getting-started-with-developer-tools.md)      
[Microsoft'un YouTube'daki özel görsel oynatma listesi](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)  
[Power BI'daki görselleştirmeler](power-bi-report-visualizations.md)  
[Power BI'daki Özel Görselleştirmeler](power-bi-custom-visuals.md)  
[Microsoft AppSource'ta özel görseller yayımlama](developer/office-store.md)  
Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

