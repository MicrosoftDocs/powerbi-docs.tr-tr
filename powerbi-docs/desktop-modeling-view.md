---
title: Power BI Desktop’ta Modelleme görünümünü kullanma (önizleme)
description: Power BI Desktop'ta karmaşık veri kümelerini görsel bir biçimde görmek için Modelleme görünümünü kullanma
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/13/2018
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 84e2bc663a4e3912608279c7315bc494b3c9844a
ms.sourcegitcommit: c8c126c1b2ab4527a16a4fb8f5208e0f7fa5ff5a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2019
ms.locfileid: "54296536"
---
# <a name="modeling-view-in-power-bi-desktop-preview"></a>Power BI Desktop'ta Modelleme görünümü (önizleme)

**Power BI Desktop**'taki **Modelleme görünümü** ile, birçok tablo içeren karmaşık veri kümelerini görüntüleyebilir ve bunlarla çalışabilirsiniz. Modelleme görünümüyle aşağıdakileri yapabilirsiniz:


## <a name="enabling-the-modeling-view-preview-feature"></a>Modelleme görünümü önizleme özelliğini etkinleştirme

Modelleme görünümü özelliği önizleme aşamasındadır ve **Power BI Desktop**'ta etkinleştirilmesi gerekir. Modelleme görünümünü etkinleştirmek için, **Dosya > Seçenekler ve Ayarlar > Seçenekler > Önizleme Özellikleri**'ni seçin ve ardından aşağıdaki resimde gösterildiği gibi **Modelleme görünümü** onay kutusunu seçin.

![Power BI Desktop'ta Modelleme görünümü önizleme özelliğini etkinleştirme](media/desktop-modeling-view/modeling-view_01.png)

Önizleme özelliğinin etkinleştirilmesi için **Power BI Desktop**'ı yeniden başlatmanız gerektiği bildirilir. 

![Önizleme özelliklerini etkinleştirmek için Power BI Desktop'ı yeniden başlatma](media/desktop-modeling-view/modeling-view_01b.png)

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
* [Power BI Desktop’ta bileşik modeller (Önizleme)](desktop-composite-models.md)
* [Power BI Desktop’ta depolama Modu (Önizleme)](desktop-storage-mode.md)
* [Power BI Desktop’ta çoka çok ilişkiler (Önizleme)](desktop-many-to-many-relationships.md)


DirectQuery makaleleri:

* [Power BI'da DirectQuery kullanma](desktop-directquery-about.md)
* [Power BI'da DirectQuery tarafından desteklenen veri kaynakları](desktop-directquery-data-sources.md)
