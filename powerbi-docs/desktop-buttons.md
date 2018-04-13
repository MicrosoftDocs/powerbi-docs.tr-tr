---
title: Power BI’da düğmeleri kullanma
description: Power BI Desktop düğmeleri, uygulamalar gibi davranan raporlarla panolar hazırlamanızı ve kullanıcılarla olan etkileşimi güçlendirmenizi sağlar
services: powerbi
documentationcenter: ''
author: davidiseminger
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 04/04/2018
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 7858c76703feb53ebb74bec998ecbebcba3994cc
ms.sourcegitcommit: c80fbf5b12754ce217cb47a17cb5400b1036a8f2
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/06/2018
---
# <a name="using-buttons-in-power-bi"></a>Power BI’da düğmeleri kullanma
Power BI **düğmeleri**, uygulamalar gibi davranan raporlar ve panolar oluşturmanızı, böylece kullanıcıların Power BI içeriklerinin üzerine gelip tıklayıp etkileşime gireceği ilgi çekici bir ortam elde etmenizi sağlar. **Power BI Desktop**’ta rapor düğmeleri ekleyebilir ve kullanıcılar için uygulama gibi davranan panolar oluşturmak amacıyla bu raporları Power BI hizmetinde paylaşabilir veya yayımlayabilirsiniz.

![Power BI düğmeleri](media/desktop-buttons/desktop-buttons_01.png)

**Power BI Desktop**’ta oluşturduğunuz düğmeler, **Power BI hizmetinde** yayımlanan raporlar ve panolarda kullanıma açıktır.

## <a name="creating-buttons-in-reports"></a>Raporlarda düğme oluşturma
Bir **Power BI Desktop** raporunda düğme oluşturmak için, **Giriş** şeridinde bulunan **Düğmeler** seçeneğini belirlediğinizde görünen açılan menüde, aşağıdaki görüntüde gösterildiği gibi seçeneklerden oluşan bir koleksiyondan istediğiniz düğmeyi seçebilirsiniz. 

![Power BI Desktop’ta düğme kontrolü ekleme](media/desktop-buttons/desktop-buttons_02.png)

Bir düğme oluşturup rapor tuvalinde seçtiğinizde **Görselleştirmeler** bölmesi, düğmeyi gereksinimlerinizi karşılayacak şekilde özelleştirmek için birçok yol gösterir. Örneğin, **Görselleştirmeler** bölmesinin o kartında bulunan kaydırıcıyı oynatarak **Düğme Metni**’ni açıp kapatabilirsiniz. Ayrıca diğer özelliklerin yanı sıra düğmenin simgesini, düğme dolgusunu, başlığı ve bir raporda veya panoda kullanıcıların düğmeye tıkladığında gerçekleşen eylemi değiştirebilirsiniz.

![Power BI Desktop’ta düğme biçimlendirme](media/desktop-buttons/desktop-buttons_03.png)

## <a name="set-button-properties-when-idle-hovered-over-or-selected"></a>Boşta olduğunda, üzerine gelindiğinde veya seçildiğinde gerçekleşen düğme özelliklerini ayarlama

Power BI düğmelerinin üç durumu vardır: varsayılan (üzerine gelinmediğinde veya seçilmediğinde görünen şekli), üzerine gelindiğinde veya seçildiğinde (genelde *tıklanma* olarak geçer). **Görselleştirmeler** bölmesindeki kartların birçoğu, bu üç duruma göre teker teker değiştirilebilir, bu da size düğmelerinizi özelleştirmek için bolca esneklik sağlar.

**Görselleştirmeler** bölmesinde bulunan aşağıdaki kartlar, düğmenin biçimlendirmesini veya davranışını, üç durumuna göre ayarlamanızı sağlar:

* Düğme Metni
* Simge
* Ana hat
* Doldur

Düğmenin her durumda nasıl göründüğünü belirlemek için, bu kartlardan birini genişletin ve kartın üstünde görünen açılan listeyi seçin. Aşağıdaki resimde, üç durumu gösteren seçili açılan listeyle birlikte **Ana hat** kartının genişletildiğini görürsünüz:

![Power BI Desktop’ta bir düğmenin üç durumu](media/desktop-buttons/desktop-buttons_04.png)


## <a name="select-the-action-for-a-button"></a>Düğme için eylem belirleyin

Bir kullanıcı Power BI’da bir düğmeyi seçtiğinde gerçekleşecek olan eylemi belirleyebilirsiniz. Düğme eylemleri seçeneklerine, **Görselleştirmeler** bölmesindeki **Eylem** kartından erişebilirsiniz.

![Power BI’daki bir düğmenin eylemi](media/desktop-buttons/desktop-buttons_05.png)

Düğme eylemleri seçenekleri şunlardır:

* Geri
* Yer işareti
* Soru-Cevap

**Geri** seçeneğini belirlemek, kullanıcıyı raporun önceki sayfasına döndürür. Bu, özellikle ayrıntılı sayfalar için kullanışlıdır.

**Yer işareti** seçeneğini belirlemek, geçerli rapor için tanımlı bir yer işaretiyle ilişkili rapor sayfasını sunar. [Power BI’da yer işaretleri hakkında daha fazla bilgi edinebilirsiniz](desktop-bookmarks.md). 

Açılan listeden **Soru-Cevap** seçeneğini belirlemek, bir **Soru-Cevap Gezgini** penceresi sunar. 

Belirli düğmelerin, otomatik olarak seçili varsayılan bir eylemi olur. Örneğin, **Soru- Cevap** düğmesi türü, otomatik olarak varsayılan eylem olacak şekilde **Soru- Cevap**’ı seçer. [Bu blog gönderisine](https://powerbi.microsoft.com/blog/power-bi-desktop-april-2018-feature-summary/#Q&AExplorer) göz atarak **Soru-Cevap Gezgini** hakkında daha fazla bilgi edinebilirsiniz.

Kullanmak istediğiniz düğme üzerinde *CTRL+CLICK* tuşlarını kullanarak raporunuz için oluşturduğunuz düğmeleri deneyebilir veya test edebilirsiniz. 

## <a name="next-steps"></a>Sonraki adımlar
Düğmelere benzeyen veya düğmelerle etkileşim kuran özellikler hakkında daha fazla bilgi için aşağıdaki makalelere göz atın:

* [Power BI Desktop'ta detaylandırma özelliğini kullanma](desktop-drillthrough.md)
* [Bir pano kutucuğunu veya rapor görselini Odak modunda görüntüleme](service-focus-mode.md)
* [Power BI’da içgörü paylaşmak ve hikayeler oluşturmak için yer işaretlerini kullanma](desktop-bookmarks.md)

