---
title: Power BI Desktop uygulamasındaki sayısal aralık dilimleyiciyi kullanma
description: Power BI Desktop uygulamasında sayısal aralıkları kısıtlamak için dilimleyici kullanmayı öğrenin
author: davidiseminger
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/19/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: 535dbe2b1765d788e59d928f7303ce4696aa163b
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73879689"
---
# <a name="use-the-numeric-range-slicer-in-power-bi-desktop"></a>Power BI Desktop uygulamasındaki sayısal aralık dilimleyiciyi kullanma
Sayısal aralık dilimleyici ile veri modelinizdeki sayısal sütunlara her türlü filtreyi uygulayabilirsiniz. Sayısal verilerinizi filtrelemeye yönelik üç seçenek vardır: belirli sayılar arasında, belirli bir sayıdan küçük veya ona eşit ya da belirli bir sayıdan büyük veya ona eşit. Bu kulağa basit geliyor olabilir ama verilerinizi filtrelemenin güçlü bir yoludur.

![Sayısal aralık dilimleyiciyi ile görüntü](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-0.png)

## <a name="use-the-numeric-range-slicer"></a>Sayısal aralık dilimleyiciyi kullanma
Sayısal aralık dilimleyiciyi aynı diğer dilimleyiciler gibi kullanabilirsiniz. Tek yapmanız gereken raporunuz için bir **dilimleyici** görseli oluşturup **Alan** değeri olarak bir sayısal değer seçmektir. Aşağıdaki görüntüde **LineTotal** alanını seçtik.

![Bir sayısal aralık dilimleyici oluşturun](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-1-create.png)

**Sayısal aralık dilimleyicinin** sağ üst köşesindeki aşağı ok bağlantısını seçtiğinizde bir menü açılır.

![Sayısal aralık dilimleyici menüsü](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-2-between.png)

Sayısal aralık için aşağıdaki üç seçeneği kullanabilirsiniz:

* **Arasında**
* **Küçük veya eşittir**
* **Büyük veya eşittir**

Menüden **Arasında** seçeneğini kullandığınızda kaydırıcı görüntülenir. Kaydırıcıyı kullanarak ilgili sayılar arasında kalan sayısal değerleri seçebilirsiniz. Bazı durumlarda kaydırıcı çubuğunun hareket hassaslığı tam olarak istenen sayıya gelmeyi zorlaştırır. Ayrıca kaydırıcıyı kullanabilir ve istediğiniz değerleri yazmak için iki kutudan birini seçebilirsiniz. Belirli sayılara göre dilimlemek istediğiniz bu seçenek kullanışlıdır. 

Aşağıdaki resimde rapor sayfası 2500,00 ile 6000,00 arasındaki **LineTotal** değerlerini gösterecek şekilde filtrelenmiştir.

![Sayısal aralık dilimleyiciyi ile “Arasında”](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-3-between-range.png)

**Küçük veya eşittir**'i seçtiğinizde kaydırıcı çubuğun sol tarafındaki tutamaç (düşük değer) kaybolur ve kaydırıcı çubuğun yalnızca üst sınırını ayarlayabilirsiniz. Aşağıdaki görüntüde kaydırıcı çubuğun en yüksek değerini 5928,19 değerine ayarladık.

![Sayısal aralık dilimleyiciyi ile “Küçüktür”](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-4-less-than.png)

Son olarak, **Büyüktür veya eşittir**'i seçerseniz sağ (yüksek değerli) kaydırıcı çubuğu tutamacı görüntüden kaldırılır. Bundan sonra aşağıdaki resimde görüldüğü gibi en düşük değeri ayarlayabilirsiniz. Bu durumda yalnızca **LineTotal** değeri 4902,99 değerine eşit veya ondan büyük olan öğeler rapor sayfasındaki görsellerde görüntülenir.

![Sayısal aralık dilimleyiciyi ile “Büyüktür”](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-5-greater-than.png)

## <a name="snap-to-whole-numbers-with-the-numeric-range-slicer"></a>Sayısal aralık dilimleyicide tam sayılara yaslama

Temel alınan alanın veri türü **Tam Sayı** ise sayısal aralık dilimleyici tam sayılara yaslanır. Bu özellik dilimleyicinizin tam sayılara düzgün bir şekilde hizalanmasına olanak tanır. **Ondalık Sayı** alanları, ondalık değerler girmenizi veya seçmenizi sağlar. Metin kutusunda ayarlanan biçimlendirme alanın biçimlendirme kümesiyle eşleşir ancak isterseniz daha hassas sayılar girebilir veya seçebilirsiniz.

## <a name="display-formatting-with-the-date-range-slicer"></a>Tarih aralığı dilimleyicisiyle biçimlendirmeyi görüntüleme

Bir veri aralığını görüntülemek veya ayarlamak için dilimleyici kullandığınızda, tarihler **Kısa Tarih** biçiminde görüntülenir. Tarihi biçimi kullanıcının tarayıcı veya işletim sistemi yerel ayarı tarafından belirlenir. Bundan dolayı, temel verilerin veya modelin veri türü ayarları ne olursa olsun görüntü biçimi o olacaktır. 

Örneğin temel veri türünüz uzun veri biçiminde olabilir. Bu durumda *g AAAA yyyy, gggg* gibi bir tarih biçimi diğer görsellerde veya durumlarda tarihi *14 Mart 2001, Çarşamba* olarak biçimlendirebilir. Ama tarihi aralığı dilimleyicisinde bu tarih dilimleyicide *14/03/2001* olarak biçimlendirilir.

Dilimleyicide **Kısa Tarih** biçiminin görüntülenmesi, dilimleyicinin içinde dize uzunluğunun tutarlı ve kısa tutulmasını sağlar. 

## <a name="limitations-and-considerations"></a>Sınırlamalar ve önemli noktalar
**Sayısal aralık dilimleyici** için sınırlamalar ve önemli noktalar aşağıda belirtilmiştir:

* **Sayısal aralık dilimleyici** verilerdeki temel alınan satırları filtreler, toplanmış değerlere filtre uygulamaz. Örneğin bir *Satış Tutarı* alanı kullandığınızı varsayalım. Dilimleyici her işlemi görselin her veri noktası için satış tutarı toplamı temelinde değil satış tutarı temelinde filtreler.
* Bu özellik şu an için ölçülerle birlikte çalışmamaktadır.
* Sayısal dilimleyici üzerindeki metin kutularına temel alınan sütundaki değer aralığının dışında olsa dahi istediğiniz sayı türünü girebilirsiniz. Bu seçenek, verilerin ileride değişme ihtimali olduğunu biliyorsanız filtreleri buna göre ayarlamanızı sağlar.
