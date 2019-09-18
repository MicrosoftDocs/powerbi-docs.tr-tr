---
title: Tüketiciler için Power BI'daki pano kutucukları
description: Tüketiciler için Power BI'daki pano kutucukları hakkında tüm bilinmesi gerekenler. SQL Server Reporting Services (SSRS) ile oluşturulan kutucuklar da ele alınmaktadır.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: conceptual
ms.date: 12/05/2018
ms.author: mihart
LocalizationGroup: Dashboards
ms.openlocfilehash: 3a341dda238996db4953fa7c68d7053034ca40b8
ms.sourcegitcommit: 52aa112ac9194f4bb62b0910c4a1be80e1bf1276
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2019
ms.locfileid: "61050286"
---
# <a name="dashboard-tiles-in-power-bi"></a>Power BI'daki pano kutucukları
Kutucuklar, verilerinizin bir *tasarımcı* tarafından panoya sabitlenmiş olan anlık görüntüleridir. Bir rapor, veri kümesi ve panonun yanı sıra Soru-Cevap soru kutusu, Excel, SQL Server Reporting Services (SSRS) ve diğer hizmetlerden kutucuk oluşturabilirsiniz.  Bu ekran görüntüsünde, bir panoya sabitlenmiş birçok farklı kutucuk gösterilmektedir.

![Power BI panosu](./media/end-user-tiles/power-bi-dashboard.png)


Raporlardan sabitlenen kutucuklara ek olarak *tasarımcılar*, **Kutucuk ekle** komutuyla doğrudan panoya bağımsız kutucuklar ekleyebilir. Ayrı kutucuklar arasında metin kutuları, resimler, videolar, akış verileri ve web içeriği bulunur.

Power BI'ın yapı taşlarını anlamak için yardıma mı ihtiyacınız var?  Bkz. [Power BI - Temel Kavramlar](end-user-basic-concepts.md).


## <a name="interacting-with-tiles-on-a-dashboard"></a>Bir panodaki kutucuklarla ile etkileşim kurma

1. Üç noktanın görüntülenmesi için kutucuğun üzerine gelin.
   
    ![kutucuk üç noktası](./media/end-user-tiles/ellipses_new.png)
2. Kutucuk eylem menüsünü açmak için üç nokta simgesini seçin. Seçenekler, kutucuğu oluşturmak için kullanılan görsel türüne ve yöntemine göre değişiklik gösterir. Görebileceğiniz birkaç örnek aşağıda verilmiştir.

    - Soru-Cevap kullanılarak oluşturulan kutucuk
   
        ![üç nokta simgesi](./media/end-user-tiles/power-bi-menu1.png)

    - çalışma kitabından oluşturulan kutucuk
   
        ![üç nokta simgesi](./media/end-user-tiles/power-bi-menu2.png)

    - rapordan oluşturulan kutucuk
   
        ![üç nokta simgesi](./media/end-user-tiles/power-bi-menu3.png)
   
    Burada yapabilecekleriniz:
   
   * [Bu kutucuğu oluşturmak için kullanılan raporu açma ](end-user-reports.md) ![rapor simgesi](./media/end-user-tiles/chart-icon.jpg)  
   
   * [Kutucuğu oluşturmak için kullanılan Soru-Cevap sorusunu açma ](end-user-reports.md) ![Soru-Cevap simgesi](./media/end-user-tiles/qna-icon.png)  
   

   * [Bu kutucuğu oluşturmak için kullanılan çalışma kitabını açma ](end-user-reports.md) ![çalışma sayfası simgesi](./media/end-user-tiles/power-bi-open-worksheet.png)  
    * [Kutucuğu odak modunda görüntüleme ](end-user-focus.md) ![odak simgesi](./media/end-user-tiles/fullscreen-icon.jpg)  
     * [Öngörüleri çalıştırma ](end-user-insights.md) ![öngörüler simgesi](./media/end-user-tiles/power-bi-insights.png)
    * [Bir yorum ekleme ve tartışma başlatma](end-user-comment.md) ![yorum simgesi](./media/end-user-tiles/comment-icons.png)

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
* Kutucuğu oluşturmak için kullanılan özgün görselleştirmenin değişmesi halinde kutucuk değişmez.  Örneğin, *tasarımcı* bir rapordan çizgi grafik sabitler ve ardından çizgi grafiği çubuk grafik olarak değiştirirse pano kutucuğunda bir çizgi grafik gösterilmeye devam eder. Veriler yenilenir ancak görselleştirme türü yenilenmez.

## <a name="next-steps"></a>Sonraki adımlar
[Veri yenileme](../refresh-data.md)

[Power BI - Temel Kavramlar](end-user-basic-concepts.md)
