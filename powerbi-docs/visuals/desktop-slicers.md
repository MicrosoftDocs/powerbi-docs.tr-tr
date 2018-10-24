---
title: Power BI Desktop'ta dilimleyicileri kullanma
description: Power BI Desktop'ta dilimleyicileri kullanarak raporları filtreleyebilir, vurgulayabilir ve özelleştirebilirsiniz
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 07/27/2018
ms.author: mihart
LocalizationGroup: Create reports
ms.openlocfilehash: df4afe91de955eabfba6eeea9022cc5f9475cc33
ms.sourcegitcommit: b8461c1876bfe47bf71c87c7820266993f82c0d3
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2018
ms.locfileid: "49336864"
---
# <a name="using-slicers-power-bi-desktop"></a>Power BI Desktop'ta dilimleyicileri kullanma

**Power BI Desktop**’ta bir **dilimleyiciyi** kullanarak rapor sayfanızdaki görsellerin sonuçlarını filtreleyebilirsiniz. Ayrıca, dilimleyicilerin kendisiyle etkileşim kurarak uygulanan filtreyi kolayca ayarlayabilirsiniz. Üstelik, dilimleyicinizin nasıl görüneceği ve bununla nasıl etkileşim kuracağınıza ilişkin seçenekleri belirtebilirsiniz. Aşağıdaki resimde, *tür* açılan menüsü görünen bir dilimleyici gösterilmiştir. 

![Masaüstündeki dilimleyiciler](./media/desktop-slicers/desktop-slicers_01.png)

Çeşitli türlerden birine sahip bir dilimleyici gösterilebilir:

* Liste
* Açılan menü
* Arasında
* Küçük veya eşittir
* Büyük veya eşittir

**Görselleştirmeler** bölmesindeki **dilimleyici** görseline tıklayarak bir rapora dilimleyici ekleyebilirsiniz.

![dilimleyici görsel türü](./media/desktop-slicers/desktop-slicers_02.png)

Dilimleyiciler **Power BI Desktop**’ta ve **Power BI hizmetinde** benzer şekilde çalışır. Dilimleyicileri kullanma hakkında bir makale için bkz. [Power BI hizmetindeki dilimleyiciler](power-bi-visualization-slicers.md).

## <a name="synchronize-slicers-across-report-pages"></a>Rapor sayfaları arasında dilimleyicileri eşitleme

**Power BI Desktop**’ta, dilimleyicileri birden çok rapor sayfasında eşitleyebilirsiniz. Dilimleyicileri eşitlemek için şeritteki **Görünüm** bölmesinde **Dilimleyicileri eşitle**’yi seçin. Dilimleyicileri eşitlediğiniz sırada, aşağıdaki resimde gösterildiği gibi **Dilimleyicileri Eşitleme** bölmesi görünür.

![dilimleyicileri eşitle bölmesini gösterme](./media/desktop-slicers/desktop-slicers_03.png)

**Dilimleyicileri Eşitleme** bölmesinde, dilimleyicinin rapor sayfalarında nasıl eşitlenmesi gerektiğini belirtin. Tüm dilimleyicilerin her bir rapor sayfasına **uygulanıp uygulanmayacağını** veya dilimleyicinin her bir rapor sayfasında **görünür** olup olmayacağını belirtebilirsiniz.

Örneğin, aşağıdaki resimde gösterildiği gibi raporunuzda **Sayfa 2**’ye bir dilimleyici ekleyebilirsiniz. Daha sonra bu dilimleyicinin seçili sayfaların her birine *uygulanıp uygulanmayacağını* veya rapordaki her bir seçili sayfada *görünür* olup olmayacağını belirleyebilirsiniz. Her dilimleyici için bunların herhangi bir birleşimini uygulayabilirsiniz. 

![dilimleyicileri eşitleme](./media/desktop-slicers/desktop-slicers_04.png)

Bölmedeki **Tümüne ekle** bağlantısının kullanılması durumunda seçili dilimleyici rapordaki tüm sayfalara uygulanır.


**Dilimleyicileri Eşitleme** bölmesinde gösterilen seçimlerin yalnızca *seçili dilimleyici* için geçerli olduğunu unutmayın. Çeşitli sayfalara birden çok dilimleyici uygulayabilir ve bölmeyi kullanarak her bir dilimleyicinin raporunuzdaki çeşitli sayfalara tek tek nasıl uygulanacağını tanımlayabilirsiniz. 

Dilimleyici seçiminiz eşitlenebilir, ancak stil, düzenleme ve silme gibi diğer seçimler *eşitlenmez*. 

## <a name="advanced-options-for-slicers"></a>Dilimleyiciler için gelişmiş seçenekler

**Dilimleyicileri eşitle** bölmesinin **Gelişmiş seçenekler** bölümünde bir dilimleyici koleksiyonuna **grup adı** da uygulayabilir ve aynı grubu paylaşan dilimleyicilerin sayfalar arasında eşitlenmesini sağlayabilirsiniz. 

![dilimleyiciler için grup adı](./media/desktop-slicers/desktop-slicers_05.png)

Bu özellik, eşitlenmiş şekilde tutmak için özel bir grup oluşturmanızı sağlar. Varsayılan bir ad sağlanır, ancak tercih ettiğiniz bir ad kullanabilirsiniz. 

Grup adı, dilimleyicilerle ilgili ek esneklik sağlar. Aynı alanı kullanan dilimleyicileri eşitlemek için ayrı gruplar oluşturabilir veya farklı alanları kullanan dilimleyicileri aynı gruba koyabilirsiniz. 

## <a name="how-filtering-affects-selection-in-slicers"></a>Filtrelemenin dilimleyici seçimi üzerindeki etkisi

Dilimleyicide bir seçim yapıp ardından normalde seçilen öğeyi kaldıracak bir filtre uygularsanız ilgili öğe dilimleyicideki öğe listesinin en altında kalır. Filtre kaldırıldığında seçim dilimleyicide kalır. Dilimleyicide seçimini kaldırdığınızda öğenin listeden silindiğini görürsünüz.

![dilimleyicilerde korunan seçim](./media/desktop-slicers/retained-selection-in-slicers.gif)


## <a name="next-steps"></a>Sonraki adımlar

Aşağıdaki makaleler de ilginizi çekebilir:

* [Power BI hizmetindeki dilimleyiciler](power-bi-visualization-slicers.md)
* [Power BI Desktop uygulamasındaki sayısal aralık dilimleyiciyi kullanma](../desktop-slicer-numeric-range.md)
* [Power BI Desktop'ta göreli tarih dilimleyici ve filtre kullanma](desktop-slicer-filter-date-range.md)

