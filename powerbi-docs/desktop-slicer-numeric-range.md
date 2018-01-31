---
title: "Power BI Desktop uygulamasındaki sayısal aralık dilimleyiciyi kullanma"
description: "Power BI Desktop uygulamasında sayısal aralıkları kısıtlamak için dilimleyici kullanmayı öğrenin"
services: powerbi
documentationcenter: 
author: davidiseminger
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 01/24/2018
ms.author: davidi
ms.openlocfilehash: cee6cd859507105b7fc0c7e7075478d3a876f7bb
ms.sourcegitcommit: 7249ff35c73adc2d25f2e12bc0147afa1f31c232
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="use-the-numeric-range-slicer-in-power-bi-desktop"></a>Power BI Desktop uygulamasındaki sayısal aralık dilimleyiciyi kullanma
**Sayısal aralık dilimleyici** ile veri modelinizdeki sayısal sütunlara her türlü filtreyi uygulayabilirsiniz. Belirli sayılar **arasında**, belirli bir sayıdan **küçük veya ona eşit**, ya da belirli bir sayıdan **büyük veya ona eşit** filtrelerini kullanabilirsiniz. Bu işlemler kulağa basit gelse de verilerinizi filtrelemek için kullanabileceğiniz önemli yöntemlerdir.

![](media/desktop-slicer-numeric-range/slicer-numeric-range_2.png)

## <a name="using-the-numeric-range-slicer"></a>Sayısal aralık dilimleyiciyi kullanma
Sayısal aralık dilimleyiciyi diğer dilimleyiciler gibi kullanabilirsiniz. Tek yapmanız gereken raporunuz için bir **dilimleyici** görseli oluşturup **Alan** değeri olarak bir sayısal değer seçmektir. Aşağıdaki görüntüde *UnitPrice* alanı seçilmiştir.

![](media/desktop-slicer-numeric-range/slicer-numeric-range_3.png)

**Sayısal aralık dilimleyicinin** sağ üst köşesindeki simgeyi seçtiğinizde bir menü açılır.

![](media/desktop-slicer-numeric-range/slicer-numeric-range_4.png)

Sayısal aralık için aşağıdaki üç seçimi yapabilirsiniz:

* Arasında
* Küçük veya eşittir
* Büyük veya eşittir

Menüden **Arasında**'yı seçtiğinizde bir kaydırıcı görüntülenir ve iki sayı arasında kalan sayısal değerleri filtreleyebilirsiniz. Kaydırma çubuğunu kullanmaya ek olarak kutulardan birine tıklayıp değer girebilirsiniz. Bu işlev özellikle belirli tam sayılar girmek istediğiniz ancak kaydırıcı çubuğu ile tam olarak istediğiniz sayıya gelemediğiniz durumlar için faydalıdır.

Aşağıdaki resimde rapor sayfası 500 ile 1500 arasındaki *UnitPrice* değerlerini gösterecek şekilde filtrelenmiştir.

![](media/desktop-slicer-numeric-range/slicer-numeric-range_5.png)

**Küçük veya eşittir**'i seçtiğinizde kaydırıcı çubuğun sol tarafındaki tutamaç (düşük değer) kaybolur ve kaydırıcı çubuğun yalnızca üst sınırı ayarlanabilir. Aşağıdaki görüntüde kaydırıcı çubuğu 497.17 değerine ayarladık.

![](media/desktop-slicer-numeric-range/slicer-numeric-range_6.png)

Son olarak **Büyük veya eşittir**'iş seçtiğinizde aşağıdaki görüntüde görebileceğiniz gibi kaydırıcı çubuğun sağ tarafındaki tutamaç (yüksek değer) kaybolur ve yalnızca düşük değer ayarlanabilir. Bu durumda yalnızca *UnitPrice* değeri 750.56 değerine eşit veya ondan büyük olan öğeler rapor sayfasındaki görsellerde görüntülenir.

![](media/desktop-slicer-numeric-range/slicer-numeric-range_7.png)

## <a name="limitations-and-considerations"></a>Sınırlamalar ve önemli noktalar
**Sayısal aralık dilimleyici** için geçerli sınırlamalar ve önemli noktalar aşağıda belirtilmiştir.

* **Sayısal aralık dilimleyici** şu an için verilerdeki temel alınan satırları filtreler, toplanmış değerlere filtre uygulamaz. Örneğin, *Sales Amount* alanı kullanıldığında *Sales Amount* tabanlı işlemlere filtre uygulanır, görseldeki her veri noktasına ait olan *Sales Amount* toplamı filtrelenmez.
* Bu özellik şu an için Ölçülerle birlikte çalışmamaktadır
* **Sayısal aralık dilimleyici** şimdilik yalnızca **Power BI Desktop** uygulamasında kullanılabilir. **Sayısal aralık dilimleyici** kullanan bir rapor **Power BI hizmetinde** yayımlandığında filtre uygulanmaya devam eder ancak liste dilimleyici olarak görünür.

