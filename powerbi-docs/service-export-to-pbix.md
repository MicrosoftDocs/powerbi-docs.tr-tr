---
title: "Bir raporu Power BI hizmetinden Power BI Desktop'a aktarma (Önizleme)"
description: "Power BI hizmetindeki raporları Power BI Desktop dosyalarına indirme"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/20/2018
ms.author: mihart
ms.openlocfilehash: 259007c76b7b53ba0ea55a28fbdd189469383364
ms.sourcegitcommit: 2ae323fbed440c75847dc55fb3e21e9c744cfba0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2018
---
# <a name="export-a-report-from-power-bi-service-to-desktop-preview"></a>Bir raporu Power BI hizmetinden Power BI Desktop'a aktarma (Önizleme)
Power BI Desktop uygulamasında bir raporu kaydedip **Yayımla**'yı seçerek Power BI hizmetine aktarabilirsiniz (*indirme* olarak da adlandırılır). Ayrıca, bu dışarı aktarma işleminin yönünü değiştirip Power BI hizmetinde bulunan bir raporu Desktop uygulamasına indirebilirsiniz. Herhangi bir yönde dışarı aktarılan dosyaların uzantısı *.pbix* olur.

Dikkat etmeniz gereken bazı sınırlamalar ve önemli noktalar bu makalenin sonraki bölümlerinde ele alınmıştır.

![](media/service-export-to-pbix/power-bi-file-export.png)

## <a name="download-the-report-as-a-pbix"></a>Raporu .pbix olarak indirme
.pbix dosyasını indirmek için şu adımları uygulayın:

1. **Power BI hizmetinde** indirmek istediğiniz raporu [Düzenleme görünümü](service-reading-view-and-editing-view.md)'nde açın.
2. Menü çubuğundan **Dosya > Raporu indir**'i seçin.
   
   > [!NOTE]
   > Raporu indirebilmeniz için 23 Kasım 2016 tarihinden sonra [Power BI Desktop kullanılarak oluşturulmuş](guided-learning/publishingandsharing.yml#step-2) veya bu tarihten sonra güncelleştirilmiş olması gerekir. Aksi halde Power BI hizmetindeki *Raporu indir* seçeneği gri renkte görünür.
   > 
   > 
3. .pbix dosyası oluşturulurken bir durum başlığında ilerleme durumu görüntülenir. Hazır olduğunda .pbix dosyasını açmanız veya kaydetmeniz istenir. Dosyanın adı raporun başlığıyla aynı olur.
   
    ![](media/service-export-to-pbix/power-bi-save-pbix.png)
   
    Artık .pbix dosyasını ister Power BI hizmetinde (app.powerbi.com) isterseniz de Power BI Desktop uygulamasında açabilirsiniz.     
4. Raporu Desktop uygulamasında hemen açmak için **Aç**'ı seçin. Dosyayı belirli bir konuma kaydetmek için **Kaydet > Farklı Kaydet**'i seçin. Henüz yüklü değilse [Power BI Desktop uygulamasını yükleyin](desktop-get-the-desktop.md).
   
    Raporu Desktop uygulamasında açtığınızda Power BI hizmeti raporunda bulunan bazı özelliklerin Desktop uygulamasında kullanılamayacağını belirten bir uyarı iletisiyle karşılaşabilirsiniz.
   
    ![](media/service-export-to-pbix/power-bi-export-to-pbix_2.png)

5. Desktop'taki rapor düzenleyicisi ile Power BI hizmetindeki rapor düzenleyicisi neredeyse aynı görünüme sahiptir.  
   
    ![](media/service-export-to-pbix/power-bi-desktop.png)

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme
Power BI hizmetinden *.pbix* dosyası indirirken (dışarı aktarırken) dikkat etmeniz gereken bazı önemli noktalar ve sınırlamalar vardır.

* Dosyayı indirebilmek için raporu düzenleme iznine sahip olmanız gerekir
* Raporun **Power BI Desktop** uygulamasında oluşturulup *yayımlanarak* **Power BI hizmetine** gönderilmiş olması veya .pbix dosyasının hizmete *yüklenmiş* olması gerekir.
* Raporların 23 Kasım 2016'dan sonra yayımlanmış veya güncelleştirilmiş olması gerekir. Bu tarihten önce yayımlanmış olan raporlar indirilemez.
* Bu özelik, içerik paketleri de dahil olmak üzere **Power BI hizmetinde** oluşturulmuş olan raporlarla kullanılamaz.
* İndirilen dosyaları açarken mutlaka **Power BI Desktop** uygulamasının son sürümünü kullanmanız gerekir. İndirilen *.pbix* dosyaları **Power BI Desktop** uygulamasının eski sürümlerinde açılmayabilir.
* Yöneticiniz verileri dışarı aktarma özelliğini devre dışı bıraktıysa bu özellik **Power BI hizmetinde** görüntülenmez.

## <a name="next-steps"></a>Sonraki adımlar
Bu özellik hakkındaki bir dakikalık **Guy in a Cube** videosunu izleyin:

<iframe width="560" height="315" src="https://www.youtube.com/embed/ymWqU5jiUl0" frameborder="0" allowfullscreen></iframe>

**Power BI hizmetini** kullanmayı öğrenmenize yardımcı olabilecek farklı makaleleri de inceleyebilirsiniz:

* [Power BI'daki raporlar](service-reports.md)
* [Power BI - Temel Kavramlar](service-basic-concepts.md)

**Power BI Desktop** uygulamasını yükledikten sonra aşağıdaki makaleler hızlı bir şekilde çalışmaya başlamanızı sağlayabilir:

* [Power BI Desktop ile çalışmaya başlama](desktop-getting-started.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)   

