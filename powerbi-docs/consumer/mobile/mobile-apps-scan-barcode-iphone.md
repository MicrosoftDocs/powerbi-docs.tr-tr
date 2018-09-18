---
title: Bir iPhone ile Power BI mobil uygulamasında barkod tarama
description: Gerçek dünyada barkodlar tarayarak Power BI mobil uygulamasında filtrelenmiş BI bilgilerine doğrudan ulaşın.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-mobile
ms.topic: conceptual
ms.date: 10/13/2017
ms.author: maggies
ms.openlocfilehash: 42ba9b042209dfd717c58042834e8d7966f97ecf
ms.sourcegitcommit: 67336b077668ab332e04fa670b0e9afd0a0c6489
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44744746"
---
# <a name="scan-a-barcode-with-your-iphone-from-the-power-bi-mobile-app"></a>iPhone'unuzla Power BI mobil uygulamasında barkod tarama
Gerçek dünyada barkodlar tarayarak Power BI mobil uygulamasında filtrelenmiş BI bilgilerine doğrudan ulaşın.

![](media/mobile-apps-scan-barcode-iphone/power-bi-barcode-scanner.png)

Diyelim ki bir iş arkadaşınız [Power BI Desktop raporunda bir barkod alanı etiketledi](../../desktop-mobile-barcodes.md) ve raporu sizinle paylaştı. 

iPhone'unuzdaki Power BI uygulamasında bulunan tarayıcı ile bir ürün barkodunu taradığınızda söz konusu barkodu içeren raporu (veya rapor listesini) görürsünüz. Bu barkodla filtrelenmiş raporu iPhone'unuzda açabilirsiniz.

## <a name="scan-a-barcode-with-the-power-bi-scanner"></a>Power BI tarayıcısı ile barkod tarama
1. Power BI mobil uygulamasının sol üst tarafında bulunan ana gezinti menüsünü ![](media/mobile-apps-scan-barcode-iphone/pbi_iph_navmenu.png) açın. 
2. **Tarayıcı**'ya gidin ve bu seçeneği belirleyin. 
   
    ![](media/mobile-apps-scan-barcode-iphone/power-bi-scanner.png)
3. Kameranız etkin değilse Power BI uygulamasının kameranızı kullanmasına onay vermeniz gerekir. Bu onay bir kereliktir. 
4. Tarayıcıyı bir üründeki barkoda doğru tutun. 
   
    Bu barkodla ilişkili bir rapor listesini görürsünüz.
5. Rapor adına dokunarak söz konusu barkodla otomatik olarak filtrelenmiş raporu iPhone'unuzda açın.

## <a name="filter-by-other-barcodes-while-in-a-report"></a>Bir rapordayken başka barkodlara göre filtreleme yapma
iPhone'unuzda barkoda göre filtrelenmiş bir raporu incelerken, aynı raporu başka bir barkodla filtrelemek isteyebilirsiniz.

* Barkod simgesinde bir filtre ![](media/mobile-apps-scan-barcode-iphone/power-bi-barcode-filtered-icon-black.png) bulunuyorsa bu filtre etkindir ve rapor zaten bir barkodla filtrelenmiştir. 
* Simgede bir filtre ![](media/mobile-apps-scan-barcode-iphone/power-bi-barcode-unfiltered-icon.png) bulunmuyorsa filtre etkin değildir ve rapor bir barkodla filtrelenmemiştir. 

Her iki durumda da simgeye dokunarak, kayan bir tarayıcı içeren küçük menüyü açın.

* Raporun filtresini başka bir barkod değeri olarak değiştirmek için tarayıcıyı yeni öğeye odaklayın. 
* Filtrelenmemiş rapora geri dönmek için **Barkod filtresini temizleme**'yi seçin.
* Rapor filtresini geçerli oturumda taradığınız barkodlardan biri olarak değiştirmek için **Son kullanılan barkodlara göre filtrele** seçeneğini belirleyin.

## <a name="issues-with-scanning-a-barcode"></a>Barkod taramada karşılaşılan sorunlar
Bir üründeki barkodu tararken aşağıdaki gibi iletilerle karşılaşabilirsiniz:

### <a name="couldnt-filter-report"></a>"Rapor filtrelenemedi..."
Filtrelemeyi seçtiğiniz rapor, bu barkod değerini içermeyen bir veri modelini temel alıyor. Örneğin, "maden suyu" ürünü raporda yer almıyor.  

### <a name="allsome-of-the-visuals-in-the-report-dont-contain-any-value"></a>Rapordaki görselleştirmelerden hiçbiri/bazıları değer içermiyor
Taradığınız barkod değeri modelinizde bulunuyor ancak raporunuzdaki görselleştirmelerden hiçbiri/bazıları bu değeri içermiyor ve bu nedenle, filtreleme işlemi boş bir durum döndürüyor. Başka rapor sayfalarına göz atmayı deneyin veya Power BI Desktop'ta raporlarınızı bu değeri içerecek şekilde düzenleyin 

### <a name="looks-like-you-dont-have-any-reports-that-can-be-filtered-by-barcodes"></a>"Barkodlarla filtrelenebilecek herhangi bir raporunuzun olmadığı görülüyor."
Bu, etkin barkodu bulunan herhangi bir raporunuz olmadığı anlamına gelir. Barkod tarayıcısıyla yalnızca **Barkod** olarak işaretlenmiş bir sütuna sahip olan raporlar filtrelenebilir.  

Rapor sahibinin (veya sizin) Power BI Desktop'ta bir sütunu **Barkod** olarak etiketlediğinden emin olun. [Power BI Desktop'ta bir barkod alanı etiketleme](../../desktop-mobile-barcodes.md) hakkında daha fazla bilgi edinin

### <a name="couldnt-filter-report---looks-like-this-barcode-doesnt-exist-in-the-report-data"></a>"Rapor filtrelenemedi - Bu barkodun, rapor verilerinde mevcut olmadığı görülüyor."
Filtrelemeyi seçtiğiniz rapor bu barkod değerini içermeyen bir veri modelini temel alıyor. Örneğin, "maden suyu" ürünü raporda yer almıyor. Farklı bir ürünü tarayabilir, farklı bir rapor seçebilir (birden fazla rapor mevcutsa) veya raporu filtrelenmemiş olarak görüntüleyebilirsiniz. 

## <a name="next-steps"></a>Sonraki adımlar
* [Power BI Desktop'ta bir barkod alanı etiketleme](../../desktop-mobile-barcodes.md)
* [Power BI'daki pano kutucukları](../../service-dashboard-tiles.md)
* [Power BI'daki panolar](../../service-dashboards.md)

