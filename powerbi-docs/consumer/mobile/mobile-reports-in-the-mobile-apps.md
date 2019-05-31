---
title: Power BI mobil uygulamalarında raporları araştırma
description: Telefonunuzdaki veya tabletinizdeki Power BI mobil uygulamalarında bulunan raporları görüntüleme ve bu raporlarla etkileşim kurma hakkında bilgi edinin. Power BI hizmetinde veya Power BI Desktop'ta oluşturduğunuz raporlarla daha sonra mobil uygulamalarda etkileşim kurabilirsiniz.
author: mshenhav
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 04/21/2019
ms.author: mshenhav
ms.openlocfilehash: bee60dd6f3254b049f2445e6e985c625933caf5b
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65565529"
---
# <a name="explore-reports-in-the-power-bi-mobile-apps"></a>Power BI mobil uygulamalarında raporları araştırma
Aşağıdakiler için geçerlidir:

| ![iPhone](././media/mobile-reports-in-the-mobile-apps/ios-logo-40-px.png) | ![iPad](././media/mobile-reports-in-the-mobile-apps/ios-logo-40-px.png) | ![Android telefon](././media/mobile-reports-in-the-mobile-apps/android-logo-40-px.png) | ![Android tablet](././media/mobile-reports-in-the-mobile-apps/android-logo-40-px.png) | ![Windows 10 cihazları](./media/mobile-reports-in-the-mobile-apps/win-10-logo-40-px.png) |
|:--- |:--- |:--- |:--- |:--- |
| iPhone'lar |iPad'ler |Android telefonlar |Android tabletler |Windows 10 cihazları |

Power BI raporu, verilerinizin etkileşimli bir görünümüdür ve verilerinize dayalı farklı bulguları ve öngörüleri temsil eden görseller içerir. Power BI mobil uygulamalarında raporları görüntülemek, üç adımlı bir işlemin üçüncü adımıdır.

1. [Power BI Desktop'ta rapor oluşturun](../../desktop-report-view.md). Power BI Desktop'ta [bir raporu telefonlar için en iyi duruma getirebilirsiniz](mobile-apps-view-phone-report.md). 
2. Oluşturduğunuz raporları Power BI hizmetinde [(https://powerbi.com)](https://powerbi.com) veya [Power BI Rapor Sunucusu](../../report-server/get-started.md)'nda yayımlayın.  
3. Ardından Power BI mobil uygulamalarını kullanarak bu raporlarla etkileşim kurun.

## <a name="open-a-power-bi-report-in-the-mobile-app"></a>Bir Power BI raporunu mobil uygulamada açma
Power BI raporlarını aldığınız yere bağlı olarak bu raporlar mobil uygulamanın farklı konumlarında depolanır. Raporlar; Uygulamalar, Benimle Paylaşılan veya Çalışma Alanı (Çalışma Alanım dahil) bölümlerinde ya da bir rapor sunucusunda olabilir. Raporlar bazı durumlarda listelenir, bazı durumlarda da bir raporu almak için ilişkili panoya göz atmanız gerekebilir.

Listeleri ve menüleri, bu öğe bir rapor olduğunu anlamanıza yardımcı olacak bir rapor adının yanındaki simge bulabilirsiniz. 

![raporları çalışma Alanım içinde](./media/mobile-reports-in-the-mobile-apps/reports-my-workspace.png) 

Power BI mobil uygulamalarında raporlar için iki simge vardır:

* ![rapor simgesi](./media/mobile-reports-in-the-mobile-apps/report-default-icon.png) uygulamasındaki yatay yönde sunulur ve tarayıcıda görünüyor gibi aynı görünür bir rapor gösterir.

* ![Telefon raporu simgesi](./media/mobile-reports-in-the-mobile-apps/report-phone-icon.png) Dikey sunulacak en az bir telefon en iyi duruma getirilmiş rapor sayfasına sahip bir rapor gösterir. 

Not: Telefonunuz, yatay görünümde tutmak, rapor sayfasını telefon düzeni olsa bile yatay düzeni, her zaman alırsınız. 

Bir raporu panodan almak için bir kutucuğun sağ üst köşedeki üç nokta (…) dokunun > **raporunu Aç**.
  
  ![Rapor Aç](./media/mobile-reports-in-the-mobile-apps/power-bi-android-open-report-tile.png)
  
  Rapor aç seçeneği, kutucukların hepsinde bulunmaz. Örneğin, Soru-Cevap kutusunda soru sorarak oluşturulan kutucuklara dokunulduğunda rapor açılmaz. 
  
## <a name="interacting-with-reports"></a>Raporlarla etkileşim kurma
Uygulamada açık olan bir raporu aldıktan sonra Bununla çalışmaya başlayabilirsiniz. Raporunuzu ve verileri ile yapabileceğiniz çok şey vardır. Rapor alt bilgisinde rapor ve dokunma ve ayrıca dilim ve verilerin ayrıntılarına inin raporda gösterilen verileri uzun dokunma gerçekleştirebileceğiniz eylemler bulabilirsiniz.

### <a name="using-tap-and-long-tap"></a>Dokunun ve uzun dokunun kullanma
Dokunun eşit bir fare tıklatın. Bir veri noktasına göre rapor çapraz vurgulama istiyorsanız, bu nedenle, veri noktasında dokunun.
Bir Dilimleyici değeri dokunarak, seçili değeri ve raporun geri kalanını bu değere göre dilimleme yapar. Bir bağlantıya dokunarak, düğme veya yer işareti eylemi yazarı tarafından tanımlanan göre etkinleştirir.

Büyük olasılıkla bir görsele dokunun, bir kenarlık göründüğünü fark. Üzerinde sağ üst köşedeki kenarlığın üç nokta (...) yoktur. Dokunma dayanarak bu görselde yapabileceğiniz eylemleri içeren bir menü getirir.

![Rapor görselini ve menüsü](./media/mobile-reports-in-the-mobile-apps/report-visual-menu.png)

### <a name="tooltip-and-drill-actions"></a>Araç ipucu ve detaylandırma eylemleri

Uzun dokunduğunuzda (dokunun ve basılı) bir veri noktasının araç ipucu bu veri noktasını temsil eden değer sunma yukarı göster. 

![rapor araç ipucu](./media/mobile-reports-in-the-mobile-apps/report-tooltip.png)

Rapor yazarlarının hiyerarşileri veri ve rapor sayfaları arasında ilişkiler tanımlayabilirsiniz. Hiyerarşi yukarı detaya ayrıntıya gitme, sağlar ve bir görsel ve bir değeri başka bir rapor sayfasında detaylandırma. Böylece, uzun araç ipucu yanı sıra bir değere dokunun, ilgili ayrıntılandırma seçeneği altbilgisinde görüntülenir. 

![Rapor detaylandırma eylemleri](./media/mobile-reports-in-the-mobile-apps/report-drill-actions.png)

*Detaylandırma* sayesinde, bir görselin belirli bir bölümüne dokunduğunuzda Power BI sizi raprodaki farklı, dokunduğunuz değere göre filtrelenmiş bir sayfaya götürür.  Raporun yazarı, her biri sizi farklı bir sayfaya götüren bir veya daha fazla detaylandırma seçeneği tanımlayabilir. Bu durumda, hangi sayfayı detaylandırmak istediğinizi seçebilirsiniz. Geri düğmesini önceki rapor sayfasına geri alır.

[Power BI Desktop’ta detaylandırma ekleme](../../desktop-drillthrough.md) hakkında bilgi edinin.
   
   > [!IMPORTANT]
   > Yalnızca bir hücre değerini ve sütun ve satır üst bilgileri tarafından değil, Power BI mobil uygulamasında matris ve tablo görsellerinde detaya etkinleştirilir.
   
   
   
### <a name="using-the-actions-in-the-report-footer"></a>Rapor alt bilgisinde eylemlerini kullanma
Dikdörtgenler, geçerli rapor sayfasını veya raporun tamamına yapabileceğiniz eylem yok. Altbilgi en faydalı Eylemler hızlı erişimi olan ve tüm eylemleri nokta (...) erişimden olabilir.

![dikdörtgenler](./media/mobile-reports-in-the-mobile-apps/report-footer.png)

Alt bilgisinden gerçekleştirebileceğiniz eylemler şunlardır:
1) Rapor Filtresi sıfırlayın ve çapraz vurgulama seçimleri özgün durumuna geri dön.
2) Görüntülemek veya bu rapordaki açıklamaları eklemek için konuşma bölmesini açın.
3) Görüntülemek ve şu anda rapora uygulanan filtreyi değiştirmek için Filtre bölmesini açın.
4) Bu rapordaki tüm sayfalara listeleyin. Sayfa adına dokunarak yükleyin ve o sayfası sunar.
Rapor sayfaları arasında hareket etmek, ekranınızın kenarından merkezine geçirilerek yapılabilir.
5) Tüm rapor eylemleri görüntüleyin.

#### <a name="all-report-actions"></a>Tüm rapor eylemi
Üzerinde dokunun... Rapor alt bilgisinde seçeneği, rapor üzerinde gerçekleştirebileceğiniz tüm eylemler ortaya çıkarır. 

![Tüm Eylemler raporu](./media/mobile-reports-in-the-mobile-apps/report-all-actions.png)

Belirli bir rapor özelliklerine bağımlı olduğundan bazı eylemleri, devre dışı bırakılabilir.
Örnek:
1) **Geçerli konuma göre filtreleme** Raporunuzdaki verileri coğrafi verilerle yazarı tarafından kategoriye ayrılma etkinleştirilir. [Raporunuzdaki coğrafi verileri tanımlama öğrenin](https://docs.microsoft.com/power-bi/desktop-mobile-geofiltering).
2) **Raporu barkodla filtrelemek için tarama** yalnızca veri kümesini raporunuzda barkod etiketlendi etkinleştirilir. [Power BI Desktop'taki barkodları etiketi nasıl](https://docs.microsoft.com/power-bi/desktop-mobile-barcodes). 
3) **Davet** yalnızca bu raporu başkalarıyla paylaşmak için izniniz varsa etkindir. Rapor sahibi olduğunda veya yeniden paylaşma iznine sahibi tarafından verilen iznine sahip olur.
4) **Not ekleme ve paylaşma** varsa devre dışı olabilir bir [Intune koruma ilkesini](https://docs.microsoft.com/intune/app-protection-policies) kuruluşunuzdaki Power BI mobil uygulamasından paylaşımı yasaktır. 

## <a name="next-steps"></a>Sonraki adımlar
* [Telefonunuz için en iyi duruma getirilmiş Power BI raporlarını görüntüleme ve raporlarla etkileşim kurma](mobile-apps-view-phone-report.md)
* [Telefonlar için en iyi duruma getirilmiş bir rapor sürümü oluşturma](../../desktop-create-phone-report.md)
* Sorularınız mı var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

