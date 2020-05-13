---
title: Power BI’da göreli saat dilimleyicisi veya filtresi kullanma
description: Power BI’da göreli zaman aralıklarını kısıtlama amacıyla dilimleyicileri veya filtreleri kullanmayı öğrenin.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 04/22/2020
ms.author: maggies
LocalizationGroup: Create reports
ms.openlocfilehash: 31563e5bb5b91468b8913c3204e9d27607716c77
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83279216"
---
# <a name="use-a-relative-time-slicer-and-filter-in-power-bi"></a>Power BI’da göreli saat dilimleyicisi ve filtresi kullanma

[!INCLUDE [applies-to](../includes/applies-to.md)] [!INCLUDE [yes-desktop](../includes/yes-desktop.md)] [!INCLUDE [yes-service](../includes/yes-service.md)]

Yeni ortaya çıkan hızlı yenileme senaryolarında, daha kısa bir zaman aralığına filtreleme becerisi yararlı olabilir. Göreli saat dilimleyici veya göreli saat filtresi kullanarak veri modelinizdeki tarih veya saat sütunlarına zamana bağlı filtre uygulayabilirsiniz. Örneğin göreli saat dilimleyicisini kullanarak yalnızca son dakika veya son saat içindeki video görünümlerini gösterebilirsiniz. 

:::image type="content" source="media/slicer-filter-relative-time/power-bi-relative-time.gif" alt-text="Göreli saat örneği":::

Bu özelliği [otomatik sayfa yenileme](../create-reports/desktop-automatic-page-refresh.md) özelliğiyle birlikte kullanmak zorunda değilsiniz. Bununla birlikte birçok göreli saat senaryosu otomatik sayfa yenileme özelliğiyle birlikte iyi sonuç verir.  

> [!NOTE]
> Sayfa veya rapor düzeyinde göreli saat filtresi veya dilimleyicisi uyguladığınızda söz konusu sayfa veya rapordaki tüm görseller paylaşılan *sabit saat noktası* kullanılarak tam olarak aynı zaman aralığına filtrelenir. Görsellerin yürütme zamanları biraz farklı olabileceğinden, bu paylaşılan sabit saat noktası görsellerin sayfanız veya raporunuz genelinde eşitlenmesini sağlar. Bu makalede [sabit zaman](#understanding-anchor-time) hakkında daha fazla bilgi edinebilirsiniz.

## <a name="turn-on-relative-time-preview"></a>Göreli saat önizlemesini açma

Göreli saat filtresi önizleme aşamasındadır, bu nedenle özellik anahtarını açmanız gerekir. **Dosya** > **Seçenekler ve Ayarlar** > **Seçenekler** yolunu izleyin. **Genel ayarlar** > **Önizleme özellikleri**’nin altında **Göreli saat filtresi**’nin seçili olduğundan emin olun.

:::image type="content" source="media/slicer-filter-relative-time/power-bi-relative-time-set-preview.png" alt-text="Göreli saat önizleme seçeneğini ayarlama":::

## <a name="create-a-relative-time-slicer-or-filter"></a>Göreli saat dilimleyicisi veya filtresi oluşturma

Özelliği etkinleştirdikten sonra, tarihi ve saati dilimleyicinin alan kutusuna veya Filtreler bölmesindeki bırakma alanına sürükleyip bırakabilirsiniz. 

### <a name="create-a-slicer"></a>Dilimleyici oluşturma

1. Tarih veya saat alanını tuvale sürükleyin.

2. **Dilimleyici** görselleştirme türünü seçin.

    :::image type="content" source="media/slicer-filter-relative-time/power-bi-relative-time-create-slicer.png" alt-text="Saat dilimleyicisi oluşturma":::

### <a name="create-a-filter"></a>Filtre oluşturma
 
- **Bu görsel**, **bu sayfa** veya **tüm sayfalar** için bir tarih veya saat alanını Filtreler bölmesine sürükleyin.

### <a name="set-relative-time"></a>Göreli saati ayarlama 

Ardından filtre türünü **Göreli Saat** olarak değiştirirsiniz.

:::image type="content" source="media/slicer-filter-relative-time/power-bi-relative-time-set.png" alt-text="Göreli saat olarak değiştirme":::
 
Dilimleyicide şöyle görünür:

:::image type="content" source="media/slicer-filter-relative-time/power-bi-relative-time-slicer.png" alt-text="Dilimleyicide göreli saat":::

Filtre kartında şöyle görünür: 

:::image type="content" source="media/slicer-filter-relative-time/power-bi-relative-time-filter.png" alt-text="Filtrede göreli saat":::
 
Bu yeni filtre türüyle **Son**, **Sonraki** veya **Bu zaman aralığı** temelinde filtreleme seçeneğiniz olur: 

:::image type="content" source="media/slicer-filter-relative-time/power-bi-relative-time-last-next.png" alt-text="Son, Sonraki veya Bu zaman aralığı’nı seçme":::
 
Zaman penceresini bir tam sayı ve bir zaman birimi kullanarak belirtirsiniz: **Dakika** veya **Saat**.
 
:::image type="content" source="media/slicer-filter-relative-time/power-bi-relative-time-minutes-hours.png" alt-text="Dakika veya saat seçme":::

Tuvalde yer kazanmanız gerekirse göreli saat filtresini Filtreler bölmesinde bir filtre kartı olarak da oluşturabilirsiniz.

:::image type="content" source="media/slicer-filter-relative-time/power-bi-relative-time-set-filter.png" alt-text="Göreli saati filtrede ayarlama":::
 
## <a name="understanding-anchor-time"></a>Sabit saat noktasını anlama

Sayfa veya rapor düzeyinde bir filtre uygulandığında söz konusu sayfa veya rapordaki tüm görseller tam olarak aynı zaman aralığına eşitlenir. Bu sorguların tümü *sabit saat noktası* olarak adlandırılan bir zamana göre gönderilir. Sabit saat noktası aşağıdaki koşullarda otomatik olarak yenilenir:

- İlk sayfa yüklemesi.
- El ile yenileme.
- Otomatik olarak veya değişiklik algılama ile sayfa yenileme.
- Modeldeki bir değişiklik.

### <a name="anchor-time-exceptions"></a>Sabit saat noktası özel durumları

- Soru-Cevap görselinin kullanıldığı göreli saat filtrelemesi, siz Soru-Cevap görselini standart görsele dönüştürene kadar bu sabit saat noktasına göre yapılmaz. Öte yandan ana etmenler ve ayrıştırma ağacı gibi diğer yapay zeka görselleri sabit saat noktası ile eşitlenir. 
- Bunun yanı sıra, göreli tarih filtreleri veya dilimleyicileri, göreli saat filtreleri yoksa sabit saat noktasına göre değildir. Göreli tarih filtresiyle göreli saat filtresi aynı sayfada olduğunda, göreli tarih filtresi sabit saat noktasına uyar.

## <a name="limitations-and-considerations"></a>Sınırlamalar ve önemli noktalar

Göreli saat dilimleyicisi ve filtresi için geçerli sınırlamalar ve önemli noktalar aşağıda belirtilmiştir.

- **Saat dilimiyle ilgili önemli noktalar**: Power BI'daki veri modellerinde saat dilimi bilgisi yoktur. Modeller saat bilgisi depolayabilir ancak bulundukları saat dilimiyle ilgili bir belirtim mevcut değildir. Dilimleyici ve filtre her zaman UTC cinsinden saati temel alır. Bir raporda filtre oluşturup farklı bir saat dilimindeki iş arkadaşınıza gönderirseniz, her ikiniz de aynı verileri görürsünüz. Siz veya iş arkadaşınız UTC saat diliminde değilseniz, her ikinizin de aradaki saat farkını dikkate almanız gerekir. Yerel saat diliminde yakalanan verileri UTC’ye dönüştürmek için Sorgu Düzenleyicisi'ni kullanın.
- Bu yeni filtre türü Power BI Desktop’ta, Power BI hizmetinde, Power BI Embedded’de ve Power BI mobil uygulamalarında desteklenir. Öte yandan bilinen birkaç destek sınırlaması vardır:

    - Ekleme API’si aracılığıyla desteklenmez.
    - Web’de yayımlama için desteklenmez.

- **Sorgu önbelleği**: İstemci önbelleğini kullanırız. Bu nedenle "son 1 dakika", sonra "son 5 dakika" ve sonra da yeniden "son 1 dakika" seçeneklerini belirttiğinizi düşünün. Bu noktada, sayfayı yenilemediğiniz veya sayfa otomatik olarak yenilenmediği sürece ilk çalıştırıldığı zamankiyle aynı sonuçları görürsünüz.

## <a name="next-steps"></a>Sonraki adımlar

- [Power BI’da göreli tarih dilimleyicisini ve filtresini kullanma](../visuals/desktop-slicer-filter-date-range.md)
- [Power BI'da dilimleyiciler](../visuals/power-bi-visualization-slicers.md)
