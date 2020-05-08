---
title: Power BI’da göreli tarih dilimleyicisi veya filtre kullanma
description: Power BI’da göreli tarih aralıklarını kısıtlama amacıyla dilimleyicileri veya filtreleri kullanmayı öğrenin
author: mihart
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 04/06/2020
ms.author: mihart
LocalizationGroup: Create reports
ms.openlocfilehash: 9ce36bfa61b16bd30e59bc8491af80efdfdc8a35
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "81006807"
---
# <a name="use-a-relative-date-slicer-and-filter-in-power-bi"></a>Power BI’da göreli tarih dilimleyicisi ve filtre kullanma

[!INCLUDE [applies-to](../includes/applies-to.md)] [!INCLUDE [yes-desktop](../includes/yes-desktop.md)] [!INCLUDE [yes-service](../includes/yes-service.md)]

**Göreli tarih dilimleyici** veya **göreli tarih filtresi** ile veri modelinizdeki tarih sütunlarına zamana bağlı filtre uygulayabilirsiniz. Örneğin, **göreli tarih dilimleyiciyi** kullanarak yalnızca son 30 gün içinde (veya ay, takvim ayları ve benzeri) gerçekleşen satışlara ait verileri gösterebilirsiniz. Verileri yenilediğinizde de göreli zaman dönemi otomatik olarak ilgili göreli tarih kısıtlamasını uygular.

![Göreli tarih dilimleyicisini işaret eden okun bulunduğu bir raporun ekran görüntüsü.](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-01.png)

## <a name="use-the-relative-date-range-slicer"></a>Göreli tarih aralığı dilimleyicisini kullanma

Göreli tarih dilimleyiciyi diğer dilimleyiciler gibi kullanabilirsiniz. Raporunuz için bir **dilimleyici** görseli oluşturup **Alan** değeri olarak bir tarih değeri seçin. Aşağıdaki görüntüde *OrderDate* alanını seçtik.

![Okların dilimleyici görselini ve Alan bölmesini işaret ettiği Görselleştirmeler bölmesinin ekran görüntüsü.](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-02.png)

Tuvalinizin üzerinde dilimleyiciyi ve sonra dilimleyici görselinin sağ üst köşesinde bulunan karatı seçin. Görselin tarih verileri varsa menüde **Göreli** seçeneği gösterilir.

![Karatın çevresinde bir açıklama balonu ve Göreli ifadesini işaret eden bir okla birlikte dilimleyici görselinin ekran görüntüsü.](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-03.png)

Göreli tarih dilimleyici için *Göreli*'yi seçin.

Ardından ayarları seçebilirsiniz.

*Göreli tarih dilimleyicisindeki* ilk ayar için aşağıdaki seçimleri yapabilirsiniz:

![İlk ayar açıklama balonu içine alınarak Göreli yapılandırma seçeneklerinin ekran görüntüsü.](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-04.png)

* Last

* Sonraki

* Bu

*Göreli tarih dilimleyicisinde* ikinci (ortadaki) ayar, göreli tarih aralığını tanımlamak üzere bir sayı girmenizi sağlar.

![İkinci ayar açıklama balonu içine alınarak Göreli yapılandırma seçeneklerinin ekran görüntüsü.](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-04a.png)

Üçüncü ayar, tarih ölçümünü seçmenize olanak tanır. Aşağıdaki seçimleri yapabilirsiniz:

![Üçüncü ayar açıklama balonu içine alınarak Göreli yapılandırma seçeneklerinin ekran görüntüsü.](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-05.png)

* Gün

* Hafta

* Hafta (Takvim)

* Ay

* Ay (Takvim)

* Yıl

* Yıl (Takvim)

Listeden **Ay**'ı seçip ortadaki ayara *2* değerini girerseniz şu olur:

* bugün 20 Temmuz ise

* dilimleyici tarafından kısıtlanan görsellere eklenen veriler, önceki iki ayın verilerini gösterir

* 21 Mayıs’ta başlayıp 20 Temmuz’a (bugünün tarihi) kadar devam eden

Buna karşılık *Ay (Takvim)* seçeneğini belirlerseniz kısıtlanan görseller 1 Mayıs-30 Haziran arasındaki (son iki tam takvim ayı) verileri gösterir.

## <a name="using-the-relative-date-range-filter"></a>Göreli tarih aralığı filtresini kullanma

Raporunuzun bir sayfası veya tamamı için göreli tarih aralığı filtresi de oluşturabilirsiniz. Bunun için **Alan** bölmesindeki **Sayfa düzeyi filtreleri** veya **Rapor düzeyi filtreleri** bölmesine bir tarih alanı sürükleyin:

![Sayfa düzeyi filtreleri bölmesine sürüklenen OrderDate alanının ekran görüntüsü.](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-06.png)

Bu noktadan sonra göreli tarih aralığını değiştirebilirsiniz. Bu işlem, **göreli tarih dilimleyiciyi** özelleştirme işlemiyle benzerdir. **Filtre Türü** açılan menüsünden **Göreli tarih filtresi**'ni seçin.

![Filtre Türü açılır listesi ve Göreli Tarih filtrelemesi üzerindeki fare işaretçisini gösteren ekran görüntüsü.](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-07.png)

**Göreli tarih filtresi**'ni seçtikten sonra dilimleyicide olduğu gibi değiştirebileceğiniz ve ortada bir sayısal kutusu bulunan üç bölüm görünür.

![Değer seçenekleri ile birlikte Öğeleri göster seçeneğini işaret eden oklarla Rapor düzeyi filtrelerinin ekran görüntüsü.](media/desktop-slicer-filter-date-range/relative-date-range-slicer-filter-08.png)

## <a name="limitations-and-considerations"></a>Sınırlamalar ve önemli noktalar

**Göreli tarih aralığı dilimleyici** ve filtresi için geçerli sınırlamalar ve önemli noktalar aşağıda belirtilmiştir.

* **Power BI**'daki veri modellerinde saat dilimi bilgisi yoktur. Modeller saat bilgisi depolayabilir ancak bulundukları saat dilimiyle ilgili bir belirtim mevcut değildir.

* Dilimleyici ve filtre her zaman UTC cinsinden saati temel alır. Bir raporda filtre oluşturup farklı bir saat dilimindeki iş arkadaşınıza gönderirseniz, her ikiniz de aynı verileri görürsünüz. UTC saat diliminde değilseniz, hem sizin hem de iş arkadaşınızın aradaki saat farkını dikkate alması gerekir.

* **Sorgu Düzenleyicisi**'ni kullanarak bir yerel saat diliminde yakalanan verileri UTC'ye dönüştürebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

[Power BI Desktop’ta gruplandırma ve gruplama özelliklerini kullanma](../desktop-grouping-and-binning.md) hakkında bilgi edinin.
