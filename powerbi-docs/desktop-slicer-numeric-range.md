---
title: Power BI Desktop uygulamasındaki sayısal aralık dilimleyiciyi kullanma
description: Power BI Desktop uygulamasında sayısal aralıkları kısıtlamak için dilimleyici kullanmayı öğrenin
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/02/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 68467894850248d6acb841dc2ed651f595f19b95
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "61364098"
---
# <a name="use-the-numeric-range-slicer-in-power-bi-desktop"></a>Power BI Desktop uygulamasındaki sayısal aralık dilimleyiciyi kullanma
**Sayısal aralık dilimleyici** ile veri modelinizdeki sayısal sütunlara her türlü filtreyi uygulayabilirsiniz. Belirli sayılar **arasında**, belirli bir sayıdan **küçük veya ona eşit** ya da belirli bir sayıdan **büyük veya ona eşit** filtrelerini kullanabilirsiniz. Bu işlemler kulağa basit gelse de verilerinizi filtrelemek için kullanabileceğiniz önemli yöntemlerdir.

![Sayısal aralık dilimleyiciyi ile görüntü](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-0.png)

## <a name="using-the-numeric-range-slicer"></a>Sayısal aralık dilimleyiciyi kullanma
Sayısal aralık dilimleyiciyi diğer dilimleyiciler gibi kullanabilirsiniz. Tek yapmanız gereken raporunuz için bir **dilimleyici** görseli oluşturup **Alan** değeri olarak bir sayısal değer seçmektir. Aşağıdaki görüntüde *LineTotal* alanı seçilmiştir.

![Bir sayısal aralık dilimleyici oluşturun](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-1-create.png)

**Sayısal aralık dilimleyicinin** sağ üst köşesindeki aşağı ok bağlantısını seçtiğinizde bir menü açılır.

![Sayısal aralık dilimleyici menüsü](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-2-between.png)

Sayısal aralık için aşağıdaki üç seçimi yapabilirsiniz:

* Arasında
* Küçük veya eşittir
* Büyük veya eşittir

Menüden **Arasında**'yı seçtiğinizde bir kaydırıcı görüntülenir ve iki sayı arasında kalan sayısal değerleri filtreleyebilirsiniz. Kaydırma çubuğunu kullanmaya ek olarak kutulardan birine tıklayıp değer girebilirsiniz. Bu işlev, özellikle belirli sayılar girmek istediğiniz ancak kaydırıcı çubuğu ile tam olarak istediğiniz sayıya gelemediğiniz durumlar için faydalıdır.

Aşağıdaki resimde rapor sayfası 2500,00 ile 6000,00 arasındaki *LineTotal* değerlerini gösterecek şekilde filtrelenmiştir.

![Sayısal aralık dilimleyiciyi ile “Arasında”](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-3-between-range.png)

**Küçük veya eşittir**'i seçtiğinizde kaydırıcı çubuğun sol tarafındaki tutamaç (düşük değer) kaybolur ve kaydırıcı çubuğun yalnızca üst sınırı ayarlanabilir. Aşağıdaki görüntüde kaydırıcı çubuğun en yüksek değerini 5928,19 değerine ayarladık.

![Sayısal aralık dilimleyiciyi ile “Küçüktür”](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-4-less-than.png)

Son olarak **Büyük veya eşittir**'iş seçtiğinizde aşağıdaki görüntüde görebileceğiniz gibi kaydırıcı çubuğun sağ tarafındaki tutamaç (yüksek değer) kaybolur ve yalnızca düşük değer ayarlanabilir. Bu durumda yalnızca *LineTotal* değeri 4902,99 değerine eşit veya ondan büyük olan öğeler rapor sayfasındaki görsellerde görüntülenir.

![Sayısal aralık dilimleyiciyi ile “Büyüktür”](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-5-greater-than.png)

## <a name="snap-to-whole-numbers-with-the-numeric-range-slicer"></a>Sayısal aralık dilimleyicide tam sayılara yaslama

Temel alınan alanın veri türü **Tam Sayı** ise sayısal aralık dilimleyici tam sayılara yaslanır. Bu, dilimleyicinizin tam sayılara düzgün bir şekilde hizalanmasına olanak tanır. **Ondalık Sayı** türündeki alanlar, ondalık değerler girmenizi veya seçmenizi sağlar. Metin kutusunda uygulanan biçimlendirme alanın biçimlendirme kümesiyle eşleşir ancak isterseniz daha hassas sayılar girebilir veya seçebilirsiniz.

## <a name="display-formatting-with-the-date-range-slicer"></a>Tarih aralığı dilimleyicisiyle biçimlendirmeyi görüntüleme

Tarih aralığını görüntülemek veya ayarlamak için dilimleyici kullanıldığında, tarih her zaman kullanıcının tarayıcı veya işletim sistemi yerel ayarı temelinde **Kısa Tarih** biçimi kullanılarak görüntülenir. Temel verilerin veya modelin veri türü ayarları ne olursa olsun, görüntü biçimi budur. 

Örneğin, temel veri türü için uzun tarih biçimi ayarlanmış olabilir (diğer görsellerde veya durumlarda tarihi *14 Mart 2001, Çarşamba* olarak biçimlendirecek *g AAAA yyyy, gggg* biçimi gibi), ama tarih aralığı dilimleyicisinde bu tarih *14/03/2001* olarak görüntülenir.

Dilimleyicide **Kısa Tarih** biçiminin görüntülenmesi, dilimleyicinin içinde dize uzunluğunun tutarlı ve kısa tutulmasını sağlar. 


## <a name="limitations-and-considerations"></a>Sınırlamalar ve önemli noktalar
**Sayısal aralık dilimleyici** için geçerli sınırlamalar ve önemli noktalar aşağıda belirtilmiştir:

* **Sayısal aralık dilimleyici** şu an için verilerdeki temel alınan satırları filtreler, toplanmış değerlere filtre uygulamaz. Örneğin, *Sales Amount* alanı kullanıldığında *Sales Amount* tabanlı işlemlere filtre uygulanır, görseldeki her veri noktasına ait olan *Sales Amount* toplamı filtrelenmez.
* Bu özellik şu an için Ölçülerle birlikte çalışmamaktadır.
* Sayısal dilimleyici üzerindeki metin kutularına temel alınan sütundaki değer aralığının dışında olsa dahi istediğiniz sayı türünü girebilirsiniz. Bu sayede verilerin ileride değişme ihtimali olduğunu biliyorsanız filtreleri buna göre ayarlayabilirsiniz.
