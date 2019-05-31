---
title: Power BI Desktop'taki modelleme görünümünü kullanın
description: Power BI Desktop'ta karmaşık veri kümelerini görsel bir biçimde görmek için Modelleme görünümünü kullanma
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 1fdb6058a6306f63f53c770812f85ccd9f9113ea
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65941347"
---
# <a name="modeling-view-in-power-bi-desktop"></a>Power BI Desktop'ta model görünümü

**Power BI Desktop**'taki **Modelleme görünümü** ile, birçok tablo içeren karmaşık veri kümelerini görüntüleyebilir ve bunlarla çalışabilirsiniz.


## <a name="using-modeling-view"></a>Modelleme görünümünü kullanma

Modelleme görünümüne erişmek için, aşağıdaki resimde gösterildiği gibi **Power BI Desktop**'ın sol tarafında bulunan Modelleme görünümü simgesini seçin.

![Power BI Desktop’ta modelleme görünümü simgesi](media/desktop-modeling-view/modeling-view_02.png)

## <a name="creating-separate-diagrams"></a>Ayrı diyagramlar oluşturma

Modelleme görünümüyle, modelinizin diyagramlarını oluşturabilir ve bu diyagramların modelinizdeki tabloların yalnızca bir alt kümesini içermesini sağlayabilirsiniz. Bu olanak, üzerinde çalışmak istediğiniz tabloların daha net bir görünümünü sağlamaya yardımcı olabilir ve karmaşık veri kümeleriyle çalışmayı kolaylaştırabilir. Tabloların yalnızca bir alt kümesiyle yeni bir diyagram oluşturmak için, Power BI Desktop penceresinin alt kısmında yer alan **Tüm tablolar** sekmesinin yanındaki **+** işaretine tıklayın.

![Sekmeler bölümündeki + işaretine tıklayarak yeni diyagram oluşturma](media/desktop-modeling-view/modeling-view_03.png)

Bundan sonra tabloyu **Alanlar** listesinden diyagram yüzeyine sürükleyebilirsiniz. Tabloya sağ tıklayın ve görüntülenen menüden **İlgili tabloları ekle**'yi seçin.

![Tabloya sağ tıklayın ve İlgili tabloları ekle'yi seçin](media/desktop-modeling-view/modeling-view_04.png)

Bunu yaptığınızda, özgün tabloyla ilgili tablolar yeni diyagramda görüntülenir. Aşağıdaki resimde, **İlgili tabloları ekle** menü seçeneği belirtildikten sonra ilgili tabloların nasıl görüntülendiği gösterilir.

![İlgili tabloları gösterme](media/desktop-modeling-view/modeling-view_05.png)

## <a name="setting-common-properties"></a>Ortak özellikleri ayarlama

Modelleme görünümünde **CTRL** tuşunu basılı tutup birden çok tabloya tıklayarak aynı anda birden çok nesne seçebilirsiniz. Birden çok tablo seçtiğinizde, bunlar Modelleme görünümünde vurgulu gösterilir. Birden çok tablo vurgulanmış durumdayken, **Özellikler** bölmesinde uygulanan değişiklikler tüm seçili tablolara uygulanır.

Örneğin, diyagramınızdaki birden çok tablonun [depolama modunu](desktop-storage-mode.md) değiştirmek için **CTRL** tuşunu basılı tutarak tabloları seçebilir ve sonra da **Özellikler** bölmesinde depolama modu ayarını değiştirebilirsiniz.

![CTRL tuşunu basılı tutarak birden çok tabloyu seçin ve tüm seçili tablolar için ortak özellikleri ayarlayın](media/desktop-modeling-view/modeling-view_06.png)


## <a name="next-steps"></a>Sonraki adımlar

Aşağıdaki makalelerde, veri modelleriyle ilgili daha fazla açıklama ve DirectQuery'nin ayrıntılı açıklaması bulunabilir.

* [Power BI Desktop'ta Toplamalar (Önizleme)](desktop-aggregations.md)
* [Power BI Desktop’taki bileşik modeller](desktop-composite-models.md)
* [Power BI Desktop’ta depolama Modu (Önizleme)](desktop-storage-mode.md)
* [Power BI Desktop’ta çok-çok ilişkiler](desktop-many-to-many-relationships.md)


DirectQuery makaleleri:

* [Power BI'da DirectQuery kullanma](desktop-directquery-about.md)
* [Power BI'da DirectQuery tarafından desteklenen veri kaynakları](desktop-directquery-data-sources.md)
