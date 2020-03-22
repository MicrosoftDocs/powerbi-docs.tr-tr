---
title: Power BI’da düğmeleri kullanma
description: Power BI raporlarına, raporlarınızın uygulamalar gibi davranmasını sağlayan ve kullanıcılarla etkileşimi derinleştiren düğmeler ekleyebilirsiniz.
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 03/12/2020
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 6629165ec031fea0d1c1af443e1d7b311bc743aa
ms.sourcegitcommit: 7e845812874b3347bcf87ca642c66bed298b244a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/13/2020
ms.locfileid: "79201654"
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
- **Detaylandırma (önizleme)** , kullanıcının yer işaretlerini kullanmadan sayfayı seçimine göre filtrelenmiş şekilde detaylandırmasını sağlar. [Raporlardaki detaylandırma düğmeleri](desktop-drill-through-buttons.md) hakkında daha fazla bilgi edinin.
- **Sayfa gezintisi**, kullanıcıyı yine yer işaretlerini kullanmadan rapor içinde farklı bir sayfaya götürür. Ayrıntılar için bu makaledeki [Sayfa gezintisi oluşturma](#create-page-navigation) bölümüne bakın.
- **Soru-Cevap** seçeneği bir **Soru-Cevap Gezgini** penceresi açar. 

Belirli düğmelerin, otomatik olarak seçili varsayılan bir eylemi vardır. Örneğin, **Soru- Cevap** düğmesi türü, otomatik olarak varsayılan eylem olacak şekilde **Soru- Cevap**’ı seçer. [Bu blog gönderisine](https://powerbi.microsoft.com/blog/power-bi-desktop-april-2018-feature-summary/#Q&AExplorer) göz atarak **Soru-Cevap Gezgini** hakkında daha fazla bilgi edinebilirsiniz.

Kullanmak istediğiniz düğme üzerinde *CTRL+CLICK* tuşlarını kullanarak raporunuz için oluşturduğunuz düğmeleri deneyebilir veya test edebilirsiniz. 

### <a name="create-page-navigation"></a>Sayfa gezintisi oluşturma

**Sayfa gezintisi** türünde **Eylem** ile, hiç yer işareti kaydetmek veya yönetmek zorunda kalmadan gezinti deneyiminin tamamını hızlıca oluşturabilirsiniz.

Sayfa gezintisi düğmesi ayarlamak için, eylem türü olarak **Sayfa gezintisi** seçili bir düğme oluşturun ve **Hedef** sayfasını seçin.

![Sayfa gezintisi eylemi](media/desktop-buttons/power-bi-page-navigation.png)

Hızlıca bir özel gezinti bölmesi oluşturabilirsiniz. Gezinti bölmenizde hangi sayfaların gösterileceğini değiştirmek istiyorsanız, yer işaretlerini düzenlemek ve yönetmek zorunda kalmaktan çekinirsiniz.

![Gezinti sayfası oluşturma](media/desktop-buttons/power-bi-build-navigation-pane.png)

Ayrıca, diğer düğme türleri gibi araç ipucunu da koşullu olarak biçimlendirebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar
Düğmelere benzeyen veya düğmelerle etkileşim kuran özellikler hakkında daha fazla bilgi için aşağıdaki makalelere göz atın:

* [Power BI raporlarında detaylandırmayı kullanma](desktop-drillthrough.md)
* [Power BI’da içgörü paylaşmak ve hikayeler oluşturmak için yer işaretlerini kullanma](desktop-bookmarks.md)

