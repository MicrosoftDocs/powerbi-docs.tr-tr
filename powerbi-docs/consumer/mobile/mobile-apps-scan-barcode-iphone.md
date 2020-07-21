---
title: Power BI mobil uygulamasında barkod tarama
description: Gerçek dünyada barkodlar tarayarak Power BI mobil uygulamasında filtrelenmiş BI bilgilerine doğrudan ulaşın.
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: how-to
ms.date: 12/02/2019
ms.author: painbar
ms.openlocfilehash: 9265cc94aceb53b1b088f2393ca607c83f94b978
ms.sourcegitcommit: e8ed3d120699911b0f2e508dc20bd6a9b5f00580
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2020
ms.locfileid: "86264794"
---
# <a name="scan-a-barcode-with-your-device-from-the-power-bi-mobile-app"></a>Cihazınızla Power BI mobil uygulamasında barkod tarama
Gerçek dünyada barkodlar tarayarak Power BI mobil uygulamasında filtrelenmiş BI bilgilerine doğrudan ulaşın.


Aşağıdakiler cihazlar için geçerlidir:

| ![iPhone](./media/mobile-apps-qr-code/ios-logo-40-px.png) | ![iPad'ler](./media/mobile-apps-qr-code/ios-logo-40-px.png) | ![Android telefon](././media/mobile-apps-qr-code/android-logo-40-px.png) | ![Android tablet](././media/mobile-apps-qr-code/android-logo-40-px.png) |
|:--- |:--- |:--- |:--- |
|iPhone'lar |iPad'ler |Android telefonlar |Android tabletler |

Diyelim ki bir iş arkadaşınız [Power BI Desktop raporunda bir barkod alanı etiketledi](../../transform-model/desktop-mobile-barcodes.md) ve raporu sizinle paylaştı. 

![Renkli bir içeceğin barkodu üzerindeki tarayıcıyı gösteren bir ürün barkod taramasının ekran görüntüsü.](media/mobile-apps-scan-barcode-iphone/power-bi-barcode-scanner.png)

Cihazınızdaki Power BI uygulamasında bulunan tarayıcı ile bir ürün barkodunu taradığınızda söz konusu barkodu içeren raporu (veya rapor listesini) görürsünüz. Bu barkodla filtrelenmiş raporu açabilirsiniz.

## <a name="scan-a-barcode-with-the-power-bi-scanner"></a>Power BI tarayıcısı ile barkod tarama
1. Gezinti çubuğunda **Diğer seçenekler**'e (...) ve sonra da **Tarayıcı**'ya dokunun.

    ![Tarayıcı seçimini gösteren, Gezinti bölmesindeki Diğer seçeneklerin ekran görüntüsü.](media/mobile-apps-scan-barcode-iphone/power-bi-scanner.png)

2. Kameranız etkin değilse Power BI uygulamasının kameranızı kullanmasına onay vermeniz gerekir. Bu onay bir kereliktir. 
4. Tarayıcıyı bir üründeki barkoda doğru tutun. Bu barkodla ilişkili bir rapor listesini görürsünüz.
5. Rapor adına dokunarak söz konusu barkoda göre otomatik olarak filtrelenmiş raporu cihazınızda açın.

## <a name="filter-by-other-barcodes-while-in-a-report"></a>Bir rapordayken başka barkodlara göre filtreleme yapma
Cihazınızda barkoda göre filtrelenmiş bir raporu incelerken, aynı raporu başka bir barkodla filtrelemek isteyebilirsiniz.

* Barkod simgesinde bir filtre bulunuyorsa ![Filtrelenmiş simgesi](media/mobile-apps-scan-barcode-iphone/power-bi-barcode-filtered-icon-black.png)bu filtre etkindir ve rapor zaten bir barkodla filtrelenmiştir. 
* Simgede bir filtre bulunmuyorsa ![Filtrelenmemiş simgesi](media/mobile-apps-scan-barcode-iphone/power-bi-barcode-unfiltered-icon.png)etkin değildir ve rapor bir barkodla filtrelenmemiştir. 

Her iki durumda da simgeye dokunarak, kayan bir tarayıcı içeren küçük menüyü açın.

* Raporun filtresini başka bir barkod değeri olarak değiştirmek için tarayıcıyı yeni öğeye odaklayın. 
* Filtrelenmemiş rapora geri dönmek için **Barkod filtresini temizleme**'yi seçin.
* Rapor filtresini geçerli oturumda taradığınız barkodlardan biri olarak değiştirmek için **Son kullanılan barkodlara göre filtrele** seçeneğini belirleyin.

## <a name="issues-with-scanning-a-barcode"></a>Barkod taramada karşılaşılan sorunlar
Bir üründeki barkodu tararken aşağıdaki gibi iletilerle karşılaşabilirsiniz:

### <a name="couldnt-filter-report"></a>“Rapor filtrelenemedi...”
Filtrelemeyi seçtiğiniz rapor, bu barkod değerini içermeyen bir veri modelini temel alıyor. Örneğin, "maden suyu" ürünü raporda yer almıyor.  

### <a name="allsome-of-the-visuals-in-the-report-dont-contain-any-value"></a>Rapordaki görselleştirmelerden hiçbiri/bazıları değer içermiyor
Taradığınız barkod değeri modelinizde bulunuyor ancak raporunuzdaki görselleştirmelerden hiçbiri/bazıları bu değeri içermiyor ve bu nedenle, filtreleme işlemi boş bir durum döndürüyor. Başka rapor sayfalarına göz atmayı deneyin veya Power BI Desktop'ta raporlarınızı bu değeri içerecek şekilde düzenleyin 

### <a name="looks-like-you-dont-have-any-reports-that-can-be-filtered-by-barcodes"></a>“Barkodlarla filtrelenebilecek herhangi bir raporunuzun olmadığı görülüyor.”
Bu, etkin barkodu bulunan herhangi bir raporunuz olmadığı anlamına gelir. Barkod tarayıcısıyla yalnızca **Barkod** olarak işaretlenmiş bir sütuna sahip olan raporlar filtrelenebilir.  

Rapor sahibinin (veya sizin) Power BI Desktop'ta bir sütunu **Barkod** olarak etiketlediğinden emin olun. [Power BI Desktop'ta bir barkod alanı etiketleme](../../transform-model/desktop-mobile-barcodes.md) hakkında daha fazla bilgi edinin

### <a name="couldnt-filter-report---looks-like-this-barcode-doesnt-exist-in-the-report-data"></a>“Rapor filtrelenemedi - Bu barkodun, rapor verilerinde mevcut olmadığı görülüyor.”
Filtrelemeyi seçtiğiniz rapor bu barkod değerini içermeyen bir veri modelini temel alıyor. Örneğin, "maden suyu" ürünü raporda yer almıyor. Farklı bir ürünü tarayabilir, farklı bir rapor seçebilir (birden fazla rapor mevcutsa) veya raporu filtrelenmemiş olarak görüntüleyebilirsiniz. 

## <a name="next-steps"></a>Sonraki adımlar
* [Power BI Desktop'ta bir barkod alanı etiketleme](../../transform-model/desktop-mobile-barcodes.md)
* [Power BI'daki pano kutucukları](../end-user-tiles.md)
* [Power BI'daki panolar](../end-user-dashboards.md)
