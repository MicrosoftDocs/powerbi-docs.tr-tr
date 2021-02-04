---
title: Power BI mobil uygulamasından barkod tarama
description: Gerçek dünyada barkodlar tarayarak Power BI mobil uygulamasında filtrelenmiş BI bilgilerine doğrudan ulaşın.
author: paulinbar
ms.author: painbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: how-to
ms.date: 12/02/2019
ms.openlocfilehash: 28baefb80037d1f78d2a2fd51b3989aa5d2a1ebb
ms.sourcegitcommit: c33e53e1fab1f29872297524a7b4f5af6c806798
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/04/2021
ms.locfileid: "99533108"
---
# <a name="scan-barcodes-from-the-mobile-app-to-get-filtered-data"></a>Filtrelenmiş verileri almak için mobil uygulamadaki barkodları tarayın 
Power BI mobil uygulamadaki doğrudan filtrelenmiş bı bilgilerine ulaşmak için gerçek dünyada barkodları tarayın.

Aşağıdakiler cihazlar için geçerlidir:

| ![iPhone](./media/mobile-apps-qr-code/ios-logo-40-px.png) | ![iPad'ler](./media/mobile-apps-qr-code/ios-logo-40-px.png) | ![Android telefon](././media/mobile-apps-qr-code/android-logo-40-px.png) | ![Android tablet](././media/mobile-apps-qr-code/android-logo-40-px.png) |
|:--- |:--- |:--- |:--- |
|iPhone'lar |iPad'ler |Android telefonlar |Android tabletler |

Kuruluşunuzun [Power BI Desktop barkod verisi olarak etiketlendirilmiş](../../transform-model/desktop-mobile-barcodes.md)verileri olan raporlar olduğunu varsayalım. Cihazınızdaki Power BI uygulamasındaki tarayıcıyla bir ürün barkodunu taradığınızda, barkod verilerine sahip raporların bir listesini alırsınız. Aradığınız raporu açabilir ve ihtiyacınız olan bilgilere otomatik olarak filtre uygulayabilirsiniz.

![Renkli bir içeceğin barkodu üzerindeki tarayıcıyı gösteren bir ürün barkod taramasının ekran görüntüsü.](media/mobile-apps-scan-barcode-iphone/power-bi-barcode-scanner.png)

Barkod taramanın yararlı olduğu iki senaryo örneği aşağıda verilmiştir:
* Büyük bir süper pazarda envanteri kontrol etdiğinizi ve mağaza depolarından, mağazanın stokta kaç tanesi, maddelerin hangi departmanların stoklanabileceği, vb. gibi belirli ürünler hakkında bilgi almanız gerektiğini düşünün. Mobil cihazınızda Power BI tarayıcıyı açıp bir öğenin barkodunu tarayabilirsiniz. Barkod verileri olan raporların bir listesini alırsınız. İlgili verileri filtreleyerek ilgili raporu seçersiniz ve rapor açılır.
* Bir fabrika katında makineler barkodlara göre tanımlanmakta olduğunu ve bu makinelerden gelen Telemetriyi işleme ve Power BI gönderilme olduğunu varsayalım. Mühendisler, makine durumunu taban halinde denetlerken, makinenin barkodunu kolayca tarayabilir ve performans ve durumu hakkında bir KPI raporuna alabilirler.

## <a name="scan-a-barcode-with-the-power-bi-scanner"></a>Power BI tarayıcısı ile barkod tarama
1. Gezinti çubuğunda **Diğer seçenekler**'e (...) ve sonra da **Tarayıcı**'ya dokunun.

    ![Tarayıcı seçimini gösteren, Gezinti bölmesindeki Diğer seçeneklerin ekran görüntüsü.](media/mobile-apps-scan-barcode-iphone/power-bi-scanner.png)

1. Kameranız etkin değilse Power BI uygulamasının kameranızı kullanmasına onay vermeniz gerekir. Bu onay bir kereliktir. 
1. Tarayıcıya ilgilendiğiniz öğedeki bir barkodun üzerine gelin. Barkod alanları olan raporların bir listesini görürsünüz.
1. Aradığınız raporu bulun ve cihazınızda açmak için, taradığınız barkoda göre otomatik olarak filtrelenmiş ' e dokunun. Rapor barkodu içermiyorsa, "rapor filtrelenemedi" iletisini alırsınız. Bu durumda, listeye dönüp başka bir rapor deneyebilirsiniz.
    
>[!NOTE]
>Yalnızca bir barkod alanı olan bir rapor varsa, raporların bir listesini almazsınız, ancak rapor doğrudan açılır ve taranan barkoda göre filtrelenecektir. Rapor, taranmış barkodu içermiyorsa, "rapor filtrelenemedi" iletisini de alırsınız.

## <a name="filter-by-other-barcodes-while-in-a-report"></a>Bir rapordayken başka barkodlara göre filtreleme yapma
Cihazınızda barkoda göre filtrelenmiş bir raporu incelerken, aynı raporu başka bir barkodla filtrelemek isteyebilirsiniz.

Raporun eylem çubuğunda, **diğer seçenekler (...)** seçeneğine dokunun ve barkod simgesini bulun.

* Barkod simgesi doldurulmuşsa, ![Filtrelenmiş simgesi](media/mobile-apps-scan-barcode-iphone/power-bi-barcode-filtered-icon-black.png)bu filtre etkindir ve rapor zaten bir barkodla filtrelenmiştir. 
* Simge açık ise ![Filtrelenmemiş simgesi](media/mobile-apps-scan-barcode-iphone/power-bi-barcode-unfiltered-icon.png)etkin değildir ve rapor bir barkodla filtrelenmemiştir. 

Her iki durumda da simgeye dokunarak, kayan bir tarayıcı içeren küçük menüyü açın.

* Raporun filtresini başka bir barkod değeri olarak değiştirmek için tarayıcıyı yeni öğeye odaklayın. 
* Filtrelenmemiş rapora geri dönmek için **Barkod filtresini temizleme**'yi seçin.
* Rapor filtresini geçerli oturumda taradığınız barkodlardan biri olarak değiştirmek için **Son kullanılan barkodlara göre filtrele** seçeneğini belirleyin.

## <a name="clear-a-barcode-filter"></a>Barkod filtresini Temizleme
Filtrelenmiş bir raporda barkod filtrelemeyi temizlemek için:
1. Raporun eylem çubuğunda, **diğer seçenekler (...)** seçeneğine dokunun ve bir filtrenin etkin olduğunu belirten doldurulmuş barkod tarayıcı simgesi ![ filtrelenmiş simgesini bulun ](media/mobile-apps-scan-barcode-iphone/power-bi-barcode-filtered-icon-black.png) ve tarayıcıyı açmak için bu simgeye dokunun.
1. Filtrelenmemiş rapora geri dönmek için **Barkod filtresini temizleme**'yi seçin.

## <a name="limitations"></a>Sınırlamalar

* Filtreler bölmesi barkod filtrelemesinin göstergesidir. Bir raporun bir barkod tarafından filtrelenmiş olup olmadığını görmek için barkod tarayıcısı menü öğesindeki simgeye bakın:

    ![Filtrelenmiş simgesi](media/mobile-apps-scan-barcode-iphone/power-bi-barcode-filtered-icon-black.png) Raporun Şu anda bir barkod tarafından filtrelenmiştir olduğunu gösterir.
    
    ![Filtrelenmemiş simgesi](media/mobile-apps-scan-barcode-iphone/power-bi-barcode-unfiltered-icon.png) Raporun Şu anda bir barkod tarafından filtrelenmediğini belirtir. 
* Mobil uygulamalar yalnızca tüm rapor verileri tablolarında yalnızca bir barkod sütunu olan raporlar için barkod filtrelemeyi destekler. Birden fazla barkod sütununa sahip bir rapor için bir barkod tarıyorsanız, filtreleme yapılmaz.

## <a name="issues-with-scanning-a-barcode"></a>Barkod taramada karşılaşılan sorunlar
Bir öğe üzerinde barkod taradığınızda karşılaşabileceğiniz bazı sorunlar aşağıda verilmiştir.

* Bir ileti **filtrelenemedi. Bu barkod rapor verilerinde yok gibi görünüyor**: Bu, taranan barkodun değerinin filtrelemeyi seçtiğiniz raporun DataModel bölümünde görünmeyeceği anlamına gelir. Bu durum örneğin, barkodu taranan ürünün rapora dahil olmaması durumunda olabilir. Farklı bir ürünü tarayabilir, farklı bir rapor seçebilir (birden fazla rapor mevcutsa) veya raporu filtrelenmemiş olarak görüntüleyebilirsiniz.

* **Barkodlara göre filtrelenebilecek bir raporunuz yok gibi** bir ileti alırsınız: Bu, barkod etkin herhangi bir raporunuz olmadığı anlamına gelir. Barkod tarayıcısıyla yalnızca **Barkod** olarak işaretlenmiş bir sütuna sahip olan raporlar filtrelenebilir. Rapor sahibinin (veya sizin) Power BI Desktop'ta bir sütunu **Barkod** olarak etiketlediğinden emin olun. [Power BI Desktop'ta bir barkod alanı etiketleme](../../transform-model/desktop-mobile-barcodes.md) hakkında daha fazla bilgi edinin

* Filtreleme boş bir durum döndürüyor. Bu, taranan barkod değerinin modelinizde varolduğu, ancak raporunuzdaki görsellerin tümünün veya bazılarının bu değeri içermediği anlamına gelebilir. Bu durumda, diğer rapor sayfalarına bakmaya veya bu değeri içerecek şekilde Power BI Desktop raporlarınızı düzenlemeye çalışın 

## <a name="next-steps"></a>Sonraki adımlar
* [Power BI Desktop'ta bir barkod alanı etiketleme](../../transform-model/desktop-mobile-barcodes.md)
* [Power BI'daki pano kutucukları](../end-user-tiles.md)
* [Power BI'daki panolar](../end-user-dashboards.md)