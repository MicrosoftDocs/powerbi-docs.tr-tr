---
title: Hiyerarşi dilimleyicisine birden çok alan ekleme
description: Hiyerarşide birden çok alan içeren bir hiyerarşi dilimleyicisi oluşturmayı öğrenin.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 06/11/2020
ms.author: maggies
LocalizationGroup: Create reports
ms.openlocfilehash: 2b9c4a8f4695f8d701eba535180194d29dd8bdec
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85238190"
---
# <a name="add-multiple-fields-to-a-hierarchy-slicer"></a>Hiyerarşi dilimleyicisine birden çok alan ekleme

[!INCLUDE [applies-to](../includes/applies-to.md)] [!INCLUDE [yes-desktop](../includes/yes-desktop.md)] [!INCLUDE [yes-service](../includes/yes-service.md)]

Tek dilimleyicide birden çok ilgili alana göre filtre uygulamak istiyorsanız *hiyerarşi* dilimleyicisi olarak adlandırılan bir dilimleyici oluşturabilirsiniz. Bu dilimleyicileri hem Power BI Desktop’ta hem de Power BI hizmetinde oluşturabilirsiniz.

:::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-hierarchy.png" alt-text="Power BI’da hiyerarşi dilimleyicisi":::

Dilimleyiciye birden çok alan eklediğinizde, sonraki düzeyde yer alan öğeleri göstermek üzere genişletilebilecek öğelerin yanında varsayılan olarak bir ok veya *köşeli çift ayraç* görüntülenir.

:::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-hierarchy-arrow.png" alt-text="Power BI’da hiyerarşi dilimleyicisi açılan menüsü":::
 
 
Bir öğe için bir veya daha çok alt öğe seçtiğinizde, üst düzey öğeye yönelik yarı seçili bir daire görürsünüz.
 
:::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-hierarchy-semi-selected.png" alt-text="Power BI’da tek seçimli hiyerarşi dilimleyicisi":::

## <a name="format-the-slicer"></a>Dilimleyiciyi biçimlendirme

Dilimleyicinin davranışı değişmemiştir. Ayrıca, dilimleyicinin stilini istediğiniz gibi belirleyebilirsiniz. Örneğin, tek seçim moduna ayarlayabilirsiniz. Alternatif olarak, bir liste ve açılan menüyü değiştirebilirsiniz. 

:::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-hierarchy-dropdown.png" alt-text="Açılan menü dilimleyicisi olarak biçimlendirilmiş hiyerarşi dilimleyicisi":::

### <a name="change-the-expandcollapse-icon"></a>Genişlet/daralt simgesini değiştirme

Hiyerarşi dilimleyicilerinde başka biçimlendirme seçenekleri vardır. Genişlet/daralt simgesini varsayılan oktan artı/eksi işaretiyle veya şapka işaretiyle değiştirebilirsiniz.

1. Dilimleyiciyi ve sonra **Biçim**’i seçin.
1. **Öğeler**’i genişletin ve **Genişlet/daralt simgesini** seçin.
1. **Köşeli Çift Ayraç**, **Artı/eksi**veya **Şapka**’yı seçin.
 
    :::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-hierarchy-caret.png" alt-text="Hiyerarşi diliminiz için bir Genişlet/Daralt simgesi seçme":::
 
### <a name="change-the-indentation"></a>Girintiyi değiştirme

Raporunuzda az alan varsa alt öğeleri girintilemek istediğiniz miktarı azaltmanız faydalı olabilir. Girintileme varsayılan olarak 15 pikseldir, ancak bunu artırıp azaltabilirsiniz. 

1. Dilimleyiciyi ve sonra **Biçim**’i seçin.
1. **Öğeler**’i genişletin ve sonra **Basamaklı düzen girintisini** daha küçük veya daha büyük olacak şekilde sürükleyin. Dilerseniz kutuya yalnızca bir sayı da yazabilirsiniz.

    :::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-indentation.png" alt-text="Hiyerarşi dilimleyici girintisini ayarlama":::

## <a name="next-steps"></a>Sonraki adımlar

- [Power BI'da dilimleyiciler](../visuals/power-bi-visualization-slicers.md)
- Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)