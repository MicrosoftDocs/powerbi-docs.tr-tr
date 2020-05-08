---
title: Power BI’da detaylandırma düğmesi oluşturma
description: Power BI raporlarına, raporlarınızın uygulamalar gibi davranmasını sağlayan ve kullanıcılarla etkileşimi derinleştiren detaylandırma düğmeleri ekleyebilirsiniz.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 03/12/2020
ms.author: maggies
LocalizationGroup: Create reports
ms.openlocfilehash: d3cb3c8093446d4417a59c5f64ab6b85a765e3c8
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "79206459"
---
# <a name="create-a-drill-through-button-in-power-bi-preview"></a>Power BI’da detaylandırma düğmesi oluşturma (önizleme)

Power BI’da bir düğme oluşturduğunuzda, **Detaylandırma (önizleme)** eylemini seçebilirsiniz. Bu eylem türü, belirli bir bağlama filtrelenmiş ayrıntıları almak için odaklanmış bir sayfayı detaylandıran bir düğme oluşturur.

Raporlarınızdaki önemli detaylandırma senaryolarının keşfedilebilirliğini artırmak istiyorsanız detaylandırma düğmesi kullanışlı olabilir.

Bu örnekte, kullanıcı grafikte Word çubuğunu seçtikten sonra **Ayrıntılara bakın** düğmesi etkinleştirilir.

![Ayrıntılara bakın düğmesi](media/desktop-drill-through-buttons/power-bi-drill-through-visual-button.png)

Kullanıcı **Ayrıntılara bakın** düğmesini seçtiğinde, Pazar Sepeti Çözümlemesi sayfası detaylandırılır. Soldaki görselde de görebileceğiniz gibi, detaylandırma sayfası şimdi Word için filtrelenmiştir.

![Filtrelenen görsel](media/desktop-drill-through-buttons/power-bi-drill-through-destination.png)

## <a name="set-up-a-drill-through-button"></a>Detaylandırma düğmesi ayarlama

Detaylandırma düğmesi ayarlamak için önce raporunuzda [geçerli bir detaylandırma sayfası ayarlamanız](desktop-drillthrough.md) gerekir. Daha sonra eylem türü olarak **Detaylandırma** seçeneğini belirleyip bir düğme oluşturmanız ve **Hedef** olarak da detaylandırma sayfasını seçmeniz gerekir.

Detaylandırma düğmesinin iki durumu (detaylandırma etkin ve devre dışı durumu) olduğundan, iki araç ipucu seçeneği olduğunu görürsünüz.

![Detaylandırma düğmesini ayarlama](media/desktop-drill-through-buttons/power-bi-create-drill-through-button.png)

Araç ipucu kutularını boş bırakırsanız Power BI otomatik olarak araç ipuçları oluşturur. Bu araç ipuçları, hedef ve detaylandırma alanlarını temel alır.

Aşağıda, düğme devre dışı olduğunda otomatik olarak oluşturulan bir araç ipucu örneği verilmiştir:

"Pazar Sepeti Çözümlemesi sayfasını (hedef sayfa) detaylandırmak için, Ürün’den (detaylandırma alanı) tek bir veri noktası seçin."

![Devre dışı durumu için otomatik olarak oluşturulan araç ipucu](media/desktop-drill-through-buttons/power-bi-drill-through-tooltip-disabled.png)

Aşağıda, düğme etkin olduğunda otomatik olarak oluşturulan bir araç ipucu örneği verilmiştir:

"Pazar Sepeti Çözümlemesi sayfasını (hedef sayfa) detaylandırmak için tıklayın."

![Etkin durumu için otomatik olarak oluşturulan araç ipucu](media/desktop-drill-through-buttons/power-bi-drill-through-visual-button.png)

Ancak özel araç ipuçları sağlamak isterseniz her zaman bir statik dize girebilirsiniz. Araç ipuçları için koşullu biçimlendirmeyi henüz desteklemiyoruz.

Bir alanın seçilen değerine göre düğme metnini değiştirmek için koşullu biçimlendirmeyi kullanabilirsiniz. Bunu yapmak için, SELECTEDVALUE DAX işlevine göre istediğiniz dizeyi veren bir ölçü oluşturmanız gerekir.

Aşağıda, tek bir Ürün değeri seçili DEĞİLSE "Ürün ayrıntılarına bakın" değerini veren; seçiliyse "[the selected Product] ayrıntılarına bakın" değerini veren bir örnek ölçü verilmiştir:

```
String_for_button = If(SELECTEDVALUE('Product'[Product], 0) == 0), "See product details", "See details for " & SELECTEDVALUE('Product'[Product]))
```

Bu ölçüyü oluşturduktan sonra düğme metni için **Koşullu biçimlendirme** seçeneğini belirlersiniz:

![Koşullu biçimlendirme’yi seçme](media/desktop-drill-through-buttons/power-bi-button-conditional-tooltip.png)

Daha sonra düğme metni için oluşturduğunuz ölçüyü seçersiniz:

![Değer temeli alanı](media/desktop-drill-through-buttons/power-bi-conditional-measure.png)

Tek bir ürün seçildiğinde düğme metninde şöyle yazar:

"Word ayrıntılarına bakın"

![Tek bir değer seçildiğinde](media/desktop-drill-through-buttons/power-bi-conditional-button-text.png)

Herhangi bir ürün seçilmediğinde veya birden fazla ürün seçildiğinde düğme devre dışı bırakılır ve düğme metninde şöyle yazar:

"Ürün ayrıntılarına bakın"

![Birden çok değer seçildiğinde](media/desktop-drill-through-buttons/power-bi-button-conditional-text-2.png)

## <a name="pass-filter-context"></a>Filtre bağlamını geçir

Bu düğme, normal detaylandırma gibi çalışır, detaylandırma alanını içeren görselleri çapraz filtreleyerek ek alanlarda da filtreler geçirebilirsiniz. Örneğin, seçimleriniz detaylandırma alanı olarak Ürün’ü içeren görseli çapraz filtrelediğinden, **Ctrl** + **tıklama** ve çapraz filtreleme yöntemini kullanarak Mağazadaki birden çok filtreyi detaylandırma sayfasına geçirebilirsiniz:

![Filtre bağlamını geçirme](media/desktop-drill-through-buttons/power-bi-cross-filter-drill-through-button.png)

Detaylandırma düğmesini seçtiğinizde, hem Mağaza hem de Ürün üzerindeki filtrelerin hedef sayfaya geçirildiğini görürsünüz:

![Bu sayfadaki filtreler](media/desktop-drill-through-buttons/power-bi-button-filters-passed-through.png)

### <a name="ambiguous-filter-context"></a>Belirsiz filtre bağlamı

Detaylandırma düğmesi tek bir görsele bağlı olmadığından, seçiminiz belirsiz olursa düğme devre dışı bırakılır.

Bu örnekte, iki görsel de Ürün’de tek bir seçim içerdiğinden düğme devre dışı bırakılır. Detaylandırma eyleminin hangi görselden hangi veri noktasına bağlanacağı belirsizdir:

![Belirsiz filtre bağlamı](media/desktop-drill-through-buttons/power-bi-button-disabled-ambiguity.png)

## <a name="limitations"></a>Sınırlamalar

- Bu düğme, tek bir düğme kullanılarak birden çok hedefe gidilmesine izin vermez.
- Bu düğme yalnızca aynı raporda detaylandırmaları destekler; başka bir deyişle, raporlar arası detaylandırmayı desteklemez.
- Düğme için devre dışı durum biçimlendirmesi, rapor temanızdaki renk sınıflarına bağlıdır. [Renk sınıfları](desktop-report-themes.md#setting-structural-colors) hakkında daha fazla bilgi edinin.
- Detaylandırma eylemi, tüm yerleşik görseller için çalışır ve AppSource’tan içeri aktarılan *bazı* görsellerle çalışır. Ancak, AppSource’tan içeri aktarılan *tüm* görsellerle çalışma garantisi verilmez.

## <a name="next-steps"></a>Sonraki adımlar
Düğmelere benzeyen veya düğmelerle etkileşim kuran özellikler hakkında daha fazla bilgi için aşağıdaki makalelere göz atın:

* [Düğme oluşturma](desktop-buttons.md)
* [Power BI raporlarında detaylandırmayı kullanma](desktop-drillthrough.md)
* [Power BI’da içgörü paylaşmak ve hikayeler oluşturmak için yer işaretlerini kullanma](desktop-bookmarks.md)

