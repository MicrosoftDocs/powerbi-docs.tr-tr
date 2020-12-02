---
title: Hiyerarşi dilimleyicisine birden çok alan ekleme
description: Hiyerarşide birden çok alan içeren bir hiyerarşi dilimleyicisi oluşturmayı öğrenin.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: pbi-reports-dashboards
ms.topic: how-to
ms.date: 07/06/2020
LocalizationGroup: Create reports
ms.openlocfilehash: cadb8d45af40c91e7008e771f2a52ef2ea508341
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96393474"
---
# <a name="add-multiple-fields-to-a-hierarchy-slicer"></a>Hiyerarşi dilimleyicisine birden çok alan ekleme

[!INCLUDE [applies-to](../includes/applies-to.md)] [!INCLUDE [yes-desktop](../includes/yes-desktop.md)] [!INCLUDE [yes-service](../includes/yes-service.md)]

Tek dilimleyicide birden çok ilgili alana göre filtre uygulamak istiyorsanız *hiyerarşi* dilimleyicisi olarak adlandırılan bir dilimleyici oluşturabilirsiniz. Bu dilimleyicileri hem Power BI Desktop’ta hem de Power BI hizmetinde oluşturabilirsiniz.

:::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-hierarchy.png" alt-text="Power BI'daki Hiyerarşi dilimleyicisinin ekran görüntüsü.":::

Dilimleyiciye birden çok alan eklediğinizde, sonraki düzeyde yer alan öğeleri göstermek üzere genişletilebilecek öğelerin yanında varsayılan olarak bir ok veya *köşeli çift ayraç* görüntülenir.

:::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-hierarchy-arrow.png" alt-text="Power BI'daki Hiyerarşi dilimleyicisi açılan menüsünün ekran görüntüsü.":::
 
 
Bir öğe için bir veya daha çok alt öğe seçtiğinizde, üst düzey öğeye yönelik yarı seçili bir daire görürsünüz.
 
:::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-hierarchy-semi-selected.png" alt-text="Power BI’da Tek seçimli hiyerarşi dilimleyicisinin ekran görüntüsü.":::

## <a name="format-the-slicer"></a>Dilimleyiciyi biçimlendirme

Dilimleyicinin davranışı değişmemiştir. Ayrıca, dilimleyicinin stilini istediğiniz gibi belirleyebilirsiniz. Örneğin, tek seçim moduna ayarlayabilirsiniz. Alternatif olarak, bir liste ve açılan menüyü değiştirebilirsiniz. 

:::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-hierarchy-dropdown.png" alt-text="Açılan menü dilimleyicisi olarak biçimlendirilmiş hiyerarşi dilimleyicisinin ekran görüntüsü.":::

Ayrıca aşağıdaki biçimlendirme değişikliklerini de yapabilirsiniz.

### <a name="change-the-title"></a>Başlığı değiştirme

Tüm dilimleyicilerin başlığını düzenleyebilirsiniz ancak bu işlev özellikle hiyerarşi dilimleyicileri için yararlıdır. Varsayılan olarak bir hiyerarşi dilimleyicisinin adı, hiyerarşideki alan adlarının listesidir.

Bu örnekte dilimleyicinin başlığında hiyerarşideki üç alan listelenmiştir: Tür, Platform ve Ad.

:::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-title.png" alt-text="Tür, Platform ve Ad alanlarını içeren hiyerarşi dilimleyicisinin ekran görüntüsü.":::

Adı değiştirmek için dilimleyiciyi ve ardından **Biçim** bölmesini seçin. **Dilimleyici üst bilgisi** altındaki **Başlık metni** kutusunda dilimleyicinin geçerli adını görürsünüz.

:::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-edit-title.png" alt-text="Geçerli başlığın gösterildiği Biçim bölmesinin ekran görüntüsü.":::

Metni seçin ve yeni bir ad ekleyin.

:::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-new-title.png" alt-text="Hiyerarşi dilimleyicisinin yeni adını gösteren ekran görüntüsü.":::


### <a name="change-the-expandcollapse-icon"></a>Genişlet/daralt simgesini değiştirme

Hiyerarşi dilimleyicilerinde başka biçimlendirme seçenekleri vardır. Genişlet/daralt simgesini varsayılan oktan artı/eksi işaretiyle veya şapka işaretiyle değiştirebilirsiniz.

1. Dilimleyiciyi ve sonra **Biçim**’i seçin.
1. **Öğeler**’i genişletin ve **Genişlet/daralt simgesini** seçin.
1. **Köşeli Çift Ayraç**, **Artı/eksi** veya **Şapka**’yı seçin.
 
    :::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-hierarchy-caret.png" alt-text="Hiyerarşi diliminiz için bir Genişlet/Daralt simgesi seçme işleminin ekran görüntüsü.":::
 
### <a name="change-the-indentation"></a>Girintiyi değiştirme

Raporunuzda az alan varsa alt öğeleri girintilemek istediğiniz miktarı azaltmanız faydalı olabilir. Girintileme varsayılan olarak 15 pikseldir, ancak bunu artırıp azaltabilirsiniz. 

1. Dilimleyiciyi ve sonra **Biçim**’i seçin.
1. **Öğeler**’i genişletin ve sonra **Basamaklı düzen girintisini** daha küçük veya daha büyük olacak şekilde sürükleyin. Dilerseniz kutuya yalnızca bir sayı da yazabilirsiniz.

    :::image type="content" source="media/power-bi-slicer-hierarchy-multiple-fields/power-bi-slicer-indentation.png" alt-text="Hiyerarşi dilimleyici girintisini ayarlama işleminin ekran görüntüsü.":::

## <a name="next-steps"></a>Sonraki adımlar

- [Power BI'da dilimleyiciler](../visuals/power-bi-visualization-slicers.md)
- Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)