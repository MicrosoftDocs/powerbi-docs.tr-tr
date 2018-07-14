---
title: Sertifikalı Power BI özel görselleştirmeleri
description: Sertifika için özel görsel gönderme işlemi ve gereksinimleri. Önceden sertifikalanan özel görseller listesi.
author: mihart
manager: kfile
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.component: powerbi-developer
ms.topic: conceptual
ms.date: 02/13/2018
ms.author: mihart
ms.openlocfilehash: efddb15572705d6d1c7cb215250360e94a8546cb
ms.sourcegitcommit: 127df71c357127cca1b3caf5684489b19ff61493
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/03/2018
ms.locfileid: "37600370"
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
| [Aster Plot](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380759) | |
| [Beyondsoft Calendar](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381096) | |
| [MAQ Software Bowtie Chart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380838) | [Video](https://youtu.be/So5xKMSpVJI) |
| [Kutu ve Çizgi grafiği](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380831) | |
| [MAQ Software Box and Whisker Chart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381351) | [Video](https://youtu.be/JoHaFLfhXdo) |
| [MAQ Software Brick Chart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380836) | [Video](https://youtu.be/hA3DOsvn2xY) |
| [Akvelon Bubble Chart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381340) | |
| [Bullet Chart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380755) | [Video](https://youtu.be/AOlsFYkfkcw) |
| [Bullet Chart by OKViz](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380953) | [Video](https://youtu.be/mtvUNl9bMjA) |
| [Calendar by Tallan](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381146) | |
| [OKViz Candlestick](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380952) | [Video](https://youtu.be/nT_18gyRxPo) |
| [OKViz Card with States](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380967) | |
| [Chiclet Slicer](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380756) | |
| [Chord](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380761) | [Video](https://youtu.be/AQvd2FhRyCI) |
| [MAQ Software Circular Gauge](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380837) | [Video](https://youtu.be/9NHXALkBXuY) |
| [Küme Eşleme](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380806) | |
| [MAQ Software Cylindrical Gauge](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380874) | [Video](https://youtu.be/DgdoWi7Gcxo) |
| [Kadranlı Ölçer](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381184) | |
| [Noktalı Çizim](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380760) | |
| [Dot Plot by OKViz](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380949) | [Video](https://youtu.be/By16pX9KT40) |
| [Ayrıntılı Kartogram](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381045) | |
| [Ayrıntılı Koroplet](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381044) | |
| [Ayrıntılı sütun grafiği](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380857) | [Video](https://youtu.be/lBy2gQQ5YsQ) |
| [Zamana bağlı veriler için ayrıntılı sütun grafiği](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380881) | [Video](https://youtu.be/T_mRou18vx0) |
| [Ayrıntılı halka grafik](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380858) | [Video](https://youtu.be/AUVFrSHmPeo) |
| [Dual KPI](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380774) | |
| [MAQ Software Dynamic Tooltip](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380983) | [Video](https://youtu.be/Z-tl97BpEr0) |
| [Gelişmiş Dağılım](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380762) | [Video](https://youtu.be/xCfM0cjM4do) |
| [Enlighten Aquarium](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381112) | |
| [Enlighten Slicer](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380960) | |
| [Enlighten Stack Shuffle](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380849) | |
| [Enlighten Waffle Chart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380850) | |
| [Zorla Yönlendirilmiş Grafik](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380764) | [Video](https://youtu.be/YsTa7uyJ4sg) |
| [MAQ Software Funnel with Source](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381334) | [Video](https://youtu.be/R_EcimsLI8U) |
| [Gantt](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380765) | [Video](https://youtu.be/qJ7s_KrGiUU) |
| [MAQ Software Gantt Chart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381364) | [Video](https://youtu.be/vJLV9JRCpI8) |
| [Yerküre Veri Çubukları](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381344) | |
| [MAQ Software kılavuz](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380825) | [Video](https://youtu.be/VOPoDJgZfOY) |
| [Akvelon Hierarchy Chart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381333) | [Video](https://youtu.be/0ZGzJaq_KT4) |
| [Çubuk Grafiği](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380776) | |
| [MAQ Software Histogram with points](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381032) | [Video](https://youtu.be/-ILF--wExrw) |
| [MAQ Software Horizontal Funnel](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380846) | [Video](https://youtu.be/SudZei68PPo) |
| [CloudScope Image](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381297) | |
| [Görüntü Kılavuzu](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381355) | |
| [Bilgi Grafiği Tasarımcısı](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380898) | |
| [Akvelon KPI Chart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381432) | |
| [MAQ Software KPI Sütunu](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380996) | [Video](https://youtu.be/rU0xoOlIq1U) |
| [MAQ Software KPI Kılavuzu](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380947) | [Video](https://youtu.be/dM4PvZh71V0) |
| [KPI Indicator](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380832) | |
| [MAQ Software KPI Bandı](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380946) | [Video](https://youtu.be/cudG4gsZ2V8) |
| [MAQ Software Linear Gauge](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380821) | [Video](https://youtu.be/7_jFaM30dkc) |
| [LineDot Grafiği](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380766) | |
| [Mekko Grafiği](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380785) | [Video](https://youtu.be/90FLCKpgicA) |
| [CloudScope Genel Bakışı](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381477) | |
| [Play Axis (Dynamic Slicer)](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380981) | |
| [Power KPI](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381083) | [Video](https://youtu.be/IvfIP3E6-1Q) |
| [Power KPI Matrix](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381299) | [Video](https://youtu.be/1enze8pcGzY) |
| [Eğilim Grafiği](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381006) | [Video](https://youtu.be/DQWdcQtjDVw) |
| [MAQ Software Quadrant Chart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381011) | [Video](https://youtu.be/ppBnyhqWNC0) |
| [Radar Grafik](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380771) | |
| [MAQ Software Ring Chart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380824) | [Video](https://youtu.be/pDToHDFHnq8) |
| [MAQ Software Rotating Chart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381007) | [Video](https://youtu.be/d5xBCMmb3hU) |
| [Sankey Grafiği](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380777) | [Video](https://youtu.be/WWP9wVUHGaA) |
| [Scroller](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381018) | |
| [OKViz Smart Filter](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380859) | [Video](https://youtu.be/gcJsDDRQq28) |
| [Sparkline by OKViz](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380910) | [Video](https://youtu.be/0m3Vnvso9tY) |
| [Akış Grafiği](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380772) | |
| [Güneş ışığı](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380767) | |
| [OKViz Genel Bakış Paneli](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380873) | |
| [Table Heatmap](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380818) | |
| [Tachometer](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380937) | [Video](https://youtu.be/C3OXdETbS9o) |
| [Metin Filtresi](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381309) | |
| [MAQ Software Text Wrapper](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380826) | |
| [MAQ Software Termometre](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380847) | [Video](https://youtu.be/SPX9mgrAdBc) |
| [Time Brush Dilimleyici](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380798) | |
| [Zaman Çizelgesi Dilimleyici](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380786) | [Video](https://youtu.be/ozMtZ4_NZ10) |
| [CloudScope Zaman Çizelgesi](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381427) | [Video](https://youtu.be/szNi9YgXFJc) |
| [Tornado chart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380768) | [Video](https://www.youtube.com/watch?v=AQvd2FhRyCI) |
| [MAQ Software Trading Chart](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380823) | [Video](https://youtu.be/xhTR6y6J9Ko) |
| [Ultimate Variance](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381140) | [Video](https://youtu.be/pDYF8iZxERs) |
| [Ultimate Waterfall](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380956) | [Video](https://youtu.be/0BZsVCQdEkc) |
| [CloudScope User List](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381426) | |
| [Waffle Grafiği](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381049) | [Video](https://youtu.be/1vRqYUsm3Vk) |
| [Word Cloud](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380752) | [Video](https://youtu.be/AblTenl9fqo) |

## <a name="next-steps"></a>Sonraki adımlar
[Özel görseller geliştirici araçları ile çalışmaya başlama (Önizleme)](service-custom-visuals-getting-started-with-developer-tools.md)      
[Microsoft'un YouTube'daki özel görsel oynatma listesi](https://www.youtube.com/playlist?list=PL1N57mwBHtN1vIjfvuBIzZllrmKo-Vz6x)  
[Power BI'daki Görselleştirmeler](power-bi-report-visualizations.md)  
[Power BI'daki Özel Görselleştirmeler](power-bi-custom-visuals.md)  
[Microsoft AppSource'ta özel görseller yayımlama](developer/office-store.md)  
Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

