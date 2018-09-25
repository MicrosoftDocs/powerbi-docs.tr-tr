---
title: Power BI'daki pano kutucukları
description: Power BI'daki pano kutucukları hakkında tüm bilmeniz gerekenler. SQL Server Reporting Services (SSRS) ile oluşturulan kutucuklar da ele alınmaktadır.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 08/21/2018
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: f0ff1d9a49e0566119df2c790ad618700c9a9ca3
ms.sourcegitcommit: 70192daf070ede3382ac13f6001e0c8b5fb8d934
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/22/2018
ms.locfileid: "46565464"
---
# <a name="dashboard-tiles-in-power-bi"></a>Power BI'daki pano kutucukları
Panolar ve pano kutucukları Power BI Desktop'ın değil, Power BI hizmetinin sunduğu özelliklerdir. Pano kutucuklarını Power BI Mobil'de oluşturamaz veya sabitleyemezsiniz ancak [görüntüleyip paylaşabilirsiniz](mobile/mobile-tiles-in-the-mobile-apps.md). Ayrıca Power BI Mobil'de, [iPhone uygulamanızı kullanarak panonuza resim ekleyebilirsiniz](mobile/mobile-iphone-app-get-started.md).

## <a name="dashboard-tiles"></a>Pano kutucukları
![Power BI panosu](./media/end-user-tiles/power-bi-dashboard.png)

Kutucuklar, verilerinizin panoya sabitlenmiş anlık görüntüleridir. Bir rapor, veri kümesi ve panonun yanı sıra Soru-Cevap kutusu, Excel, SQL Server Reporting Services (SSRS) ve diğer hizmetlerden kutucuk oluşturabilirsiniz.  Bu ekran görüntüsünde, bir panoya sabitlenmiş birçok farklı kutucuk gösterilmektedir.

Sabitlemenin yanı sıra, [Kutucuk ekle](../service-dashboard-add-widget.md) seçeneğini kullanarak doğrudan pano üzerinde ayrı kutucuklar oluşturabilirsiniz. Ayrı kutucuklar arasında metin kutuları, resimler, videolar, akış verileri ve web içeriği bulunur.

Power BI'ın yapı taşlarını anlamak için yardıma mı ihtiyacınız var?  Bkz. [Power BI - Temel Kavramlar](end-user-basic-concepts.md).

> [!NOTE]
> Kutucuğu oluşturmak için kullanılan özgün görselleştirmenin değişmesi halinde kutucuk değişmez.  Örneğin, bir rapordan çizgi grafik sabitler ve ardından çizgi grafiği çubuk grafik olarak değiştirirseniz pano kutucuğunda bir çizgi grafik gösterilmeye devam eder. Veriler yenilenir ancak görselleştirme türü yenilenmez.
> 
> 

## <a name="pin-a-tile-from"></a>Kutucukların sabitlenebileceği yerler
Bir panoya kutucuk eklemenin (sabitlemenin) birçok farklı yolu vardır. Kutucukların sabitlenebileceği yerler:

* [Power BI Soru-Cevap](../service-dashboard-pin-tile-from-q-and-a.md)
* [bir rapor](../service-dashboard-pin-tile-from-report.md)
* [başka bir pano](../service-pin-tile-to-another-dashboard.md)
* [OneDrive İş'teki Excel çalışma kitabı](../service-dashboard-pin-tile-from-excel.md)
* [Excel için Power BI Publisher](../publisher-for-excel.md)
* [Hızlı Öngörüler](end-user-insights.md)
* [SSRS](https://msdn.microsoft.com/library/mt604784.aspx)

Ayrıca, [Kutucuk ekle](../service-dashboard-add-widget.md) seçeneği kullanılarak doğrudan pano üzerinde resimler, metin kutuları, videolar, akış verileri ve web içeriği için ayrı kutucuklar oluşturulabilir.

  ![Kutucuk ekle simgesi](./media/end-user-tiles/add_widgetnew.png)

## <a name="interacting-with-tiles-on-a-dashboard"></a>Bir panodaki kutucuklarla ile etkileşim kurma
### <a name="move-and-resize-a-tile"></a>Bir kutucuğu taşıma ve yeniden boyutlandırma
Bir kutucuğu alın ve [panonun farklı yerlerinde taşıyın](../service-dashboard-edit-tile.md). Kutucuğu yeniden boyutlandırmak için tutamacın üzerine gelin ve tutamacı ![tutamaç](./media/end-user-tiles/resize-handle.jpg) seçin.

### <a name="hover-over-a-tile-to-change-the-appearance-and-behavior"></a>Görünümünü ve davranışını değiştirmek için bir kutucuğun üzerine gelme
1. Üç noktanın görüntülenmesi için kutucuğun üzerine gelin.
   
    ![kutucuk üç noktası](./media/end-user-tiles/ellipses_new.png)
2. Kutucuk eylem menüsünü açmak için üç nokta simgesini seçin.
   
    ![üç nokta simgesi](./media/end-user-tiles/power-bi-tile-menu.png)
   
    Burada yapabilecekleriniz:
   
   * [Bu kutucuğu oluşturmak için kullanılan raporu açma ](end-user-reports.md) ![rapor simgesi](./media/end-user-tiles/chart-icon.jpg)  
   
   * [Bu kutucuğu oluşturmak için kullanılan çalışma sayfasını açma ](end-user-reports.md) ![çalışma sayfası simgesi](./media/end-user-tiles/power-bi-open-worksheet.png)  
     
    * [Odak modunda görüntüleme ](end-user-focus.md) ![odak simgesi](./media/end-user-tiles/fullscreen-icon.jpg)  
     * [Kutucukta kullanılan verileri dışarı aktarma](end-user-export-data.md) ![verileri dışarı aktarma simgesi](./media/end-user-tiles/export-icon.png)
     * [Başlığı ve alt başlığı düzenleme, köprü ekleme](../service-dashboard-edit-tile.md) ![düzenleme simgesi](./media/end-user-tiles/pencil-icon.jpg)
     * [Öngörüleri çalıştırma ](end-user-insights.md) ![öngörüler simgesi](./media/end-user-tiles/power-bi-insights.png)
     * [Kutucuğu başka bir panoya sabitleme ](../service-pin-tile-to-another-dashboard.md)
       ![raptiye simgesi](./media/end-user-tiles/pin-icon.jpg)
     * [Kutucuğunu kaldırma](../service-dashboard-edit-tile.md)
     ![silme simgesi](./media/end-user-tiles/trash-icon.png)
3. Eylem menüsü kapatmak için tuvalde boş bir alan seçin.

### <a name="select-click-a-tile"></a>Bir kutucuğu seçme veya bir kutucuğa tıklama
Bir kutucuğu seçtiğinizde sonraki adım, kutucuğun nasıl oluşturulduğuna ve [özel bağlantı](../service-dashboard-edit-tile.md) içerip içermediğine göre değişir. Kutucuk özel bir bağlantı içeriyorsa kutucuğu seçtiğinizde söz konusu bağlantıya yönlendirilirsiniz. Aksi halde, kutucuğu seçtiğinizde, kutucuğu oluşturmak için kullanılan rapora, Excel Online çalışma kitabına, şirket içi SSRS raporuna veya Soru-Cevap sorusuna yönlendirilirsiniz.

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
[Panonuz için Kart (büyük sayı kutucuğu) oluşturma](../visuals/power-bi-visualization-card.md)

[Power BI'daki panolar](end-user-dashboards.md)  

[Veri yenileme](../refresh-data.md)

[Power BI - Temel Kavramlar](end-user-basic-concepts.md)

[Bir kutucuğu PowerPoint'e aktarma](http://blogs.msdn.com/b/powerbidev/archive/2015/09/28/integrating-power-bi-tiles-into-office-documents.aspx)

[Reporting Services öğelerini Power BI panolarına sabitleme](https://msdn.microsoft.com/library/mt604784.aspx)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

