---
title: Power BI’da düğmeleri kullanma
description: Power BI raporlarına, raporlarınızın uygulamalar gibi davranmasını sağlayan ve kullanıcılarla etkileşimi derinleştiren düğmeler ekleyebilirsiniz.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: pbi-reports-dashboards
ms.topic: how-to
ms.date: 05/21/2020
LocalizationGroup: Create reports
ms.openlocfilehash: 77f16bedb45b0730a7007da19a427b1832bc9969
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96414473"
---
# <a name="use-buttons-in-power-bi"></a>Power BI’da düğmeleri kullanma
Power BI’daki **düğmeler**, uygulamalar gibi davranan raporlar oluşturmanızı, böylece kullanıcıların Power BI içeriklerinin üzerine gelip tıklayıp etkileşime gireceği ilgi çekici bir ortam elde etmenizi sağlar. **Power BI Desktop**’ta ve **Power BI hizmetinde** raporlara düğmeler ekleyebilirsiniz. Power BI hizmetinde raporlarınızı paylaştığınızda, bu raporlar kullanıcılarınız için uygulamaya benzer bir deneyim sağlar.

![Power BI düğmeleri](media/desktop-buttons/power-bi-buttons.png)

## <a name="create-buttons-in-reports"></a>Raporlarda düğme oluşturma

### <a name="create-a-button-in-power-bi-desktop"></a>Power BI Desktop’ta düğme oluşturma

**Power BI Desktop**’ta düğme oluşturmak için, **Ekle** şeridinde bulunan **Düğmeler** seçeneğini belirlediğinizde görünen açılan menüde, aşağıdaki görüntüde gösterildiği gibi seçeneklerden oluşan bir koleksiyondan istediğiniz düğmeyi seçebilirsiniz. 

![Power BI Desktop’ta düğme kontrolü ekleme](media/desktop-buttons/power-bi-button-dropdown.png)

### <a name="create-a-button-in-the-power-bi-service"></a>Power BI hizmetinde düğme oluşturma

**Power BI hizmetinde** düğme oluşturmak için, raporu Düzenleme görünümünde açın. Üstteki menü çubuğunda **Düğmeler** seçeneğini belirlediğinizde görünen açılan menüde, aşağıdaki görüntüde gösterildiği gibi seçeneklerden oluşan bir koleksiyondan istediğiniz düğmeyi seçebilirsiniz. 

![Power BI hizmetine düğme denetimi ekleme](media/desktop-buttons/power-bi-button-service-dropdown.png)

## <a name="customize-a-button"></a>Düğmeyi özelleştirme

Düğmeyi ister Power BI Desktop’ta isterse Power BI hizmetinde oluşturuyor olun, işlemin geri kalanı aynıdır. Rapor tuvalinde düğmeyi seçtiğinizde **Görselleştirmeler** bölmesi, düğmeyi gereksinimlerinizi karşılayacak şekilde özelleştirmek için birçok yol gösterir. Örneğin, **Görselleştirmeler** bölmesinin o kartında bulunan kaydırıcıyı oynatarak **Düğme Metni**’ni açıp kapatabilirsiniz. Ayrıca diğer özelliklerin yanı sıra düğmenin simgesini, düğme dolgusunu, başlığı ve kullanıcılar bir raporda düğmeyi seçtiğinde gerçekleşen eylemi de değiştirebilirsiniz.

![Power BI raporunda düğmeyi biçimlendirme](media/desktop-buttons/power-bi-button-properties.png)

## <a name="set-button-properties-when-idle-hovered-over-or-selected"></a>Boşta olduğunda, üzerine gelindiğinde veya seçildiğinde gerçekleşen düğme özelliklerini ayarlama

Power BI düğmelerinin üç durumu vardır: varsayılan (üzerine gelinmediğinde veya seçilmediğinde görünen şekli), üzerine gelindiğinde veya seçildiğinde (genelde *tıklanma* olarak geçer). **Görselleştirmeler** bölmesindeki kartların birçoğu, bu üç duruma göre teker teker değiştirilebilir, bu da size düğmelerinizi özelleştirmek için bolca esneklik sağlar.

**Görselleştirmeler** bölmesinde bulunan aşağıdaki kartlar, düğmenin biçimlendirmesini veya davranışını, üç durumuna göre ayarlamanızı sağlar:

* Düğme Metni
* Simge
* Ana hat
* Doldur

Düğmenin her durumda nasıl göründüğünü belirlemek için, bu kartlardan birini genişletin ve kartın üstünde görünen açılan listeyi seçin. Aşağıdaki resimde, üç durumu gösteren seçili açılan listeyle birlikte **Simge** kartının genişletildiğini görürsünüz.

![Power BI raporundaki bir düğmenin üç durumu](media/desktop-buttons/power-bi-button-format.png)

## <a name="select-the-action-for-a-button"></a>Düğme için eylem belirleyin

Bir kullanıcı Power BI’da bir düğmeyi seçtiğinde gerçekleşecek olan eylemi belirleyebilirsiniz. Düğme eylemleri seçeneklerine, **Görselleştirmeler** bölmesindeki **Eylem** kartından erişebilirsiniz.

![Power BI’daki bir düğmenin eylemi](media/desktop-buttons/power-bi-button-action.png)

Düğme eylemleri seçenekleri şunlardır:

- **Geri** seçeneği, kullanıcıyı raporun önceki sayfasına döndürür. Bu, detaylandırma sayfaları için kullanışlıdır.
- **Yer işareti** seçeneğini, geçerli rapor için tanımlı bir yer işaretiyle ilişkili rapor sayfasını sunar. [Power BI’da yer işaretleri](desktop-bookmarks.md) hakkında daha fazla bilgi edinin. 
- **Detaylandırma**, kullanıcının yer işaretlerini kullanmadan sayfayı seçimine göre filtrelenmiş şekilde detaylandırmasını sağlar. [Raporlardaki detaylandırma düğmeleri](desktop-drill-through-buttons.md) hakkında daha fazla bilgi edinin.
- **Sayfa gezintisi**, kullanıcıyı yine yer işaretlerini kullanmadan rapor içinde farklı bir sayfaya götürür. Ayrıntılar için bu makaledeki [Sayfa gezintisi oluşturma](#create-page-navigation) bölümüne bakın.
- **Soru-Cevap** seçeneği bir **Soru-Cevap Gezgini** penceresi açar. 

Belirli düğmelerin, otomatik olarak seçili varsayılan bir eylemi vardır. Örneğin, **Soru- Cevap** düğmesi türü, otomatik olarak varsayılan eylem olacak şekilde **Soru- Cevap**’ı seçer. [Bu blog gönderisine](https://powerbi.microsoft.com/blog/power-bi-desktop-april-2018-feature-summary/#Q&AExplorer) göz atarak **Soru-Cevap Gezgini** hakkında daha fazla bilgi edinebilirsiniz.

Kullanmak istediğiniz düğme üzerinde *CTRL+CLICK* tuşlarını kullanarak raporunuz için oluşturduğunuz düğmeleri deneyebilir veya test edebilirsiniz. 

## <a name="create-page-navigation"></a>Sayfa gezintisi oluşturma

**Sayfa gezintisi** türünde **Eylem** ile, hiç yer işareti kaydetmek veya yönetmek zorunda kalmadan gezinti deneyiminin tamamını oluşturabilirsiniz.

Sayfa gezintisi düğmesi ayarlamak için, eylem türü olarak **Sayfa gezintisi** seçili bir düğme oluşturun ve **Hedef** sayfasını seçin.

![Sayfa gezintisi eylemi](media/desktop-buttons/power-bi-page-navigation.png)

Özel bir gezinti bölmesi oluşturabilir ve gezinti düğmelerini buraya ekleyebilirsiniz. Gezinti bölmenizde hangi sayfaların gösterileceğini değiştirmek istiyorsanız, yer işaretlerini düzenlemek ve yönetmek zorunda kalmaktan çekinirsiniz.

![Gezinti sayfası oluşturma](media/desktop-buttons/power-bi-build-navigation-pane.png)

Ayrıca, diğer düğme türleri gibi araç ipucunu da koşullu olarak biçimlendirebilirsiniz.

## <a name="set-the-navigation-destination-conditionally"></a>Gezinti hedefini koşullu olarak ayarlama

Gezinti hedefini seçimin çıkışına göre ayarlamak için koşullu biçimlendirmeyi kullanabilirsiniz. Örneğin kullanıcının seçimine göre farklı sayfalara gitmek için tek bir düğme bulundurarak rapor tuvalinizde yer kazanmak isteyebilirsiniz.

:::image type="content" source="media/desktop-buttons/button-navigate-go.png" alt-text="Git düğmesiyle gezinme":::
 
Yukarıda gösterilen örneği oluşturmak için, başlangıç olarak gezinti hedeflerinin adlarını içeren tek sütunlu bir tablo oluşturun:

:::image type="content" source="media/desktop-buttons/button-create-table.png" alt-text="Tablo oluşturma":::

Power BI, detaylandırma hedefini ayarlamak için tam dize eşleşmesi kullandığından girilen değerlerin detaylandırma sayfa adlarıyla tam olarak uyumlu olduğunu iki kez kontrol edin.

Tabloyu oluşturduktan sonra tek seçimlik dilimleyici olarak sayfaya ekleyin:

:::image type="content" source="media/desktop-buttons/button-navigate-slicer.png" alt-text="Gezinti dilimleyici":::

Sonra sayfa gezintisi düğmesini oluşturun ve hedef için koşullu biçimlendirme seçeneğini belirtin:

:::image type="content" source="media/desktop-buttons/button-set-page-nav-destination.png" alt-text="Sayfa gezintisi düğmesi":::
 
Oluşturduğunuz sütunun adını seçin. Şimdiki örnekte bu, **Bir hedef seçin** sütunudur:

:::image type="content" source="media/desktop-buttons/button-select-destination.png" alt-text="Bir hedef seçin":::

Artık düğme, kullanıcının seçimine bağlı olarak farklı sayfalara gidilmesini sağlayabilir.

:::image type="content" source="media/desktop-buttons/button-navigate-go.png" alt-text="Git düğmesiyle gezinme":::
 
### <a name="shapes-and-images-for-navigation"></a>Gezinti için şekiller ve resimler

Sayfa gezintisi eylemi yalnızca düğmeler değil şekiller ve resimler için de desteklenir. Burada yerleşik şekillerden birinin kullanıldığı bir örnek verilmiştir:

:::image type="content" source="media/desktop-buttons/button-navigation-arrow.png" alt-text="Gezinti için ok kullanma":::
 
Burada resim kullanma örneği verilmiştir:

:::image type="content" source="media/desktop-buttons/button-navigation-image.png" alt-text="Gezinti için resim kullanma":::
 
## <a name="buttons-support-fill-images"></a>Düğmeler dolgu resimlerini destekler

Düğmeler dolgu resimlerini destekler. Düğmenizin genel görünümünü şu yerleşik düğme durumlarıyla birleştirilen dolgu resimleriyle özelleştirebilirsiniz: varsayılan, üzerine gelindiğinde, basıldığında ve devre dışı (detaylandırma için).

:::image type="content" source="media/desktop-drill-through-buttons/drill-through-fill-images.png" alt-text="Detaylandırma düğmesi dolgu resimleri":::

**Dolgu** öğesini **Açık** olarak ayarlayın ve ardından farklı durumların resimlerini oluşturun.

:::image type="content" source="media/desktop-drill-through-buttons/drill-through-fill-state-settings.png" alt-text="Dolgu resmi ayarları":::


## <a name="next-steps"></a>Sonraki adımlar
Düğmelere benzeyen veya düğmelerle etkileşim kuran özellikler hakkında daha fazla bilgi için aşağıdaki makalelere göz atın:

* [Power BI raporlarında detaylandırmayı kullanma](desktop-drillthrough.md)
* [Power BI’da içgörü paylaşmak ve hikayeler oluşturmak için yer işaretlerini kullanma](desktop-bookmarks.md)
* [Detaylandırma düğmesi oluşturma](desktop-drill-through-buttons.md)

