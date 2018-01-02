---
title: "Power BI'daki pano kutucukları"
description: "Power BI'daki pano kutucukları hakkında tüm bilmeniz gerekenler. SQL Server Reporting Services (SSRS) ile oluşturulan kutucuklar da ele alınmaktadır."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: 
qualitydate: 03/15/2016
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/28/2017
ms.author: mihart
ms.openlocfilehash: d1960ea42bee8b00cc6dd095e94ebf6f6303bce8
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2017
---
# <a name="dashboard-tiles-in-power-bi"></a>Power BI'daki pano kutucukları
Panolar ve pano kutucukları Power BI Desktop'ın değil, Power BI hizmetinin sunduğu özelliklerdir. Pano kutucuklarını Power BI Mobil'de oluşturamaz veya sabitleyemezsiniz ancak [görüntüleyip paylaşabilirsiniz](mobile-tiles-in-the-mobile-apps.md). Ayrıca Power BI Mobil'de, [iPhone uygulamanızı kullanarak panonuza resim ekleyebilirsiniz](mobile-iphone-app-get-started.md).

## <a name="dashboard-tiles"></a>Pano kutucukları
![](media/service-dashboard-tiles/power-bi-dashboard.png)

Kutucuklar, verilerinizin panoya sabitlenmiş anlık görüntüleridir. Bir rapor, veri kümesi ve panonun yanı sıra Soru-Cevap kutusu, Excel, SQL Server Reporting Services (SSRS) ve diğer hizmetlerden kutucuk oluşturabilirsiniz.  Bu ekran görüntüsünde, bir panoya sabitlenmiş birçok farklı kutucuk gösterilmektedir.

Sabitlemenin yanı sıra, [Kutucuk ekle](service-dashboard-add-widget.md) seçeneğini kullanarak doğrudan pano üzerinde ayrı kutucuklar oluşturabilirsiniz. Ayrı kutucuklar arasında metin kutuları, resimler, videolar, akış verileri ve web içeriği bulunur.

Power BI'ın yapı taşlarını anlamak için yardıma mı ihtiyacınız var?  Bkz. [Power BI - Temel Kavramlar](service-basic-concepts.md).

> [!NOTE]
> Kutucuğu oluşturmak için kullanılan özgün görselleştirmenin değişmesi halinde kutucuk değişmez.  Örneğin, bir rapordan çizgi grafik sabitler ve ardından çizgi grafiği çubuk grafik olarak değiştirirseniz pano kutucuğunda bir çizgi grafik gösterilmeye devam eder. Veriler yenilenir ancak görselleştirme türü yenilenmez.
> 
> 

## <a name="pin-a-tile-from"></a>Kutucukların sabitlenebileceği yerler
Bir panoya kutucuk eklemenin (sabitlemenin) birçok farklı yolu vardır. Kutucukların sabitlenebileceği yerler:

* [Power BI Soru-Cevap](service-dashboard-pin-tile-from-q-and-a.md)
* [bir rapor](service-dashboard-pin-tile-from-report.md)
* [başka bir pano](service-pin-tile-to-another-dashboard.md)
* [OneDrive İş'teki Excel çalışma kitabı](service-dashboard-pin-tile-from-excel.md)
* [Excel için Power BI Publisher](publisher-for-excel.md)
* [Hızlı Öngörüler](service-insights.md)
* [SSRS](https://msdn.microsoft.com/library/mt604784.aspx)

Ayrıca, [Kutucuk ekle](service-dashboard-add-widget.md) seçeneği kullanılarak doğrudan pano üzerinde resimler, metin kutuları, videolar, akış verileri ve web içeriği için ayrı kutucuklar oluşturulabilir.

  ![](media/service-dashboard-tiles/add_widgetnew.png)

## <a name="interacting-with-tiles-on-a-dashboard"></a>Bir panodaki kutucuklarla ile etkileşim kurma
### <a name="move-and-resize-a-tile"></a>Bir kutucuğu taşıma ve yeniden boyutlandırma
Bir kutucuğu alın ve [panonun farklı yerlerinde taşıyın](service-dashboard-edit-tile.md). Kutucuğu yeniden boyutlandırmak için tutamacın ![](media/service-dashboard-tiles/resize-handle.jpg) üzerine gelin ve tutamacı seçin.

### <a name="hover-over-a-tile-to-change-the-appearance-and-behavior"></a>Görünümünü ve davranışını değiştirmek için bir kutucuğun üzerine gelme
1. Üç noktanın görüntülenmesi için kutucuğun üzerine gelin.
   
    ![](media/service-dashboard-tiles/ellipses_new.png)
2. Kutucuk eylem menüsünü açmak için üç nokta simgesini seçin.
   
    ![](media/service-dashboard-tiles/power-bi-tile-menu.png)
   
    Burada yapabilecekleriniz:
   
   * [Bu kutucuğu oluşturmak için kullanılan raporu açma ](service-reports.md) ![](media/service-dashboard-tiles/chart-icon.jpg)  
   
   * [Bu kutucuğu oluşturmak için kullanılan çalışma sayfasını açma ](service-reports.md) ![](media/service-dashboard-tiles/power-bi-open-worksheet.png)  
     
     * [Odak modunda görüntüleme ](service-focus-mode.md) ![](media/service-dashboard-tiles/fullscreen-icon.jpg)  
     * [Kutucukta kullanılan verileri dışarı aktarma ](power-bi-visualization-export-data.md) ![](media/service-dashboard-tiles/export-icon.png)
     * [Başlığı ve alt başlığı düzenleme, köprü ekleme, son yenileme zamanını görüntüleme ](service-dashboard-edit-tile.md) ![](media/service-dashboard-tiles/pencil-icon.jpg)
     * [Öngörüler elde etme ](service-insights.md) ![](media/service-dashboard-tiles/power-bi-insights.png)
     * [Kutucuğu başka bir panoya sabitleme ](service-pin-tile-to-another-dashboard.md)
       ![](media/service-dashboard-tiles/pin-icon.jpg)
   * [Kutucuğu kaldırma ](service-dashboard-edit-tile.md)
     ![](media/service-dashboard-tiles/trash-icon.png)
3. Eylem menüsü kapatmak için tuvalde boş bir alan seçin.

### <a name="select-click-a-tile"></a>Bir kutucuğu seçme veya bir kutucuğa tıklama
Bir kutucuğu seçtiğinizde sonraki adım, kutucuğun nasıl oluşturulduğuna ve [özel bağlantı](service-dashboard-edit-tile.md) içerip içermediğine göre değişir. Kutucuk özel bir bağlantı içeriyorsa kutucuğu seçtiğinizde söz konusu bağlantıya yönlendirilirsiniz. Aksi halde, kutucuğu seçtiğinizde, kutucuğu oluşturmak için kullanılan rapora, Excel Online çalışma kitabına, şirket içi SSRS raporuna veya Soru-Cevap sorusuna yönlendirilirsiniz.

> [!NOTE]
> Bu, **Kutucuk ekle** seçeneği kullanılarak doğrudan pano üzerinde oluşturulan video kutucukları için geçerli değildir. Bu şekilde oluşturulmuş bir video kutucuğunun seçilmesi, videonun doğrudan panoda oynatılmasına neden olur.   
> 
> 

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme
* Görselleştirmeyi oluşturmak için kullanılan rapor kaydedilmemişse kutucuk seçildiğinde herhangi bir işlem gerçekleşmez.
* Kutucuk Excel Online'daki bir çalışma kitabından oluşturulduysa ve bu çalışma kitabı için en azından Okuma izinlerine sahip değilseniz kutucuğu seçtiğinizde çalışma kitabı Excel Online'da açılmaz.
* **Kutucuk ekle** seçeneği kullanılarak doğrudan pano üzerinde oluşturulan kutucuklar için özel bir köprü oluşturulduysa başlığı, alt başlığı ve/veya kutucuğu seçtiğinizde söz konusu URL açılır.  Aksi halde, bir resim, web kodu veya metin kutusu için doğrudan panoda oluşturulan bu kutucukları seçtiğinizde varsayılan olarak herhangi bir işlem geçekleşmez.
* SSRS'deki rapor için izniniz yoksa SSRS'den oluşturulmuş bir kutucuğu seçtiğinizde erişiminizin olmadığını belirten bir sayfa (rsAccessDenied) görüntülenir.
* SSRS sunucusunun bulunduğu ağa erişiminiz yoksa SSRS'den oluşturulmuş bir kutucuğu seçtiğinizde sunucunun bulunamadığını belirten bir sayfa (HTTP 404) görüntülenir. Raporu görüntülemek için cihazınızın, rapor sunucusuna ilişkin ağ erişimine sahip olması gerekir.
* Kutucuğu oluşturmak için kullanılan özgün görselleştirmenin değişmesi halinde kutucuk değişmez.  Örneğin, bir rapordan çizgi grafik sabitler ve ardından çizgi grafiği çubuk grafik olarak değiştirirseniz pano kutucuğunda bir çizgi grafik gösterilmeye devam eder. Veriler yenilenir ancak görselleştirme türü yenilenmez.

## <a name="next-steps"></a>Sonraki adımlar
[Bir rapordan büyük bir sayı kutucuğu oluşturma](power-bi-visualization-big-number-report.md)

[Soru-Cevap ile büyük bir sayı kutucuğu oluşturma](power-bi-visualization-big-number.md)

[Power BI'daki panolar](service-dashboards.md)  

[Veri yenileme](refresh-data.md)

[Power BI - Temel Kavramlar](service-basic-concepts.md)

[Bir kutucuğu PowerPoint'e aktarma](http://blogs.msdn.com/b/powerbidev/archive/2015/09/28/integrating-power-bi-tiles-into-office-documents.aspx)

[Reporting Services öğelerini Power BI panolarına sabitleme](https://msdn.microsoft.com/library/mt604784.aspx)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)
