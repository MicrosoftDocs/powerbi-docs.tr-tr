---
title: Power BI’da sayısal aralık dilimleyiciyi kullanma
description: Power BI’da sayısal aralıkları kısıtlamak için dilimleyici kullanmayı öğrenin.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
featuredvideoid: zIZPA0UrJyA
ms.service: powerbi
ms.subservice: pbi-reports-dashboards
ms.topic: how-to
ms.date: 04/06/2020
LocalizationGroup: Create reports
ms.openlocfilehash: 83ba0234ef4f4e350f413f3c934e2f09f0a9a3f2
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96412794"
---
# <a name="use-the-numeric-range-slicer-in-power-bi"></a>Power BI’da sayısal aralık dilimleyiciyi kullanma

[!INCLUDE [applies-to](../includes/applies-to.md)] [!INCLUDE [yes-desktop](../includes/yes-desktop.md)] [!INCLUDE [yes-service](../includes/yes-service.md)]

Sayısal aralık dilimleyici ile veri modelinizdeki sayısal sütunlara her türlü filtreyi uygulayabilirsiniz. Sayısal verilerinizi filtrelemeye yönelik üç seçenek vardır: belirli sayılar arasında, belirli bir sayıdan küçük veya ona eşit ya da belirli bir sayıdan büyük veya ona eşit. Bu basit teknik verilerinizi filtrelemenin güçlü bir yoludur.

![Sayısal aralık dilimleyiciyi ile görüntü](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-0.png)

## <a name="video"></a>Video

Bu videoda sayısal aralık dilimleyici oluşturma işleminde size yol göstereceğiz.

> [!NOTE]
> Bu videoda Power BI Desktop’ın eski bir sürümü kullanılmaktadır.

<iframe width="560" height="315" src="https://www.youtube.com/embed/zIZPA0UrJyA" frameborder="0" allowfullscreen></iframe> 


## <a name="add-a-numeric-range-slicer"></a>Sayısal aralık dilimleyici ekleme

Sayısal aralık dilimleyiciyi aynı diğer dilimleyiciler gibi kullanabilirsiniz. Tek yapmanız gereken raporunuz için bir **Dilimleyici** görseli oluşturup **Alan** değeri olarak da bir sayısal değer seçmektir. Aşağıdaki görüntüde **LineTotal** alanını seçtik.

![Bir sayısal aralık dilimleyici oluşturun](media/desktop-slicer-numeric-range/desktop-slicer-numeric-range-1-create.png)

Sayısal aralık dilimleyicinin sağ üst köşesindeki aşağı oku seçtiğinizde bir menü açılır.

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

Temel alınan alanın veri türü *Tam Sayı* ise sayısal aralık dilimleyici tam sayılara yaslanır. Bu özellik dilimleyicinizin tam sayılara düzgün bir şekilde hizalanmasına olanak tanır. *Ondalık Sayı* alanları, ondalık değerler girmenizi veya seçmenizi sağlar. Metin kutusunda ayarlanan biçimlendirme alanın biçimlendirme kümesiyle eşleşir, ancak isterseniz daha hassas sayılar girebilir veya seçebilirsiniz.

## <a name="display-formatting-with-the-date-range-slicer"></a>Tarih aralığı dilimleyicisiyle biçimlendirmeyi görüntüleme

Bir veri aralığını görüntülemek veya ayarlamak için dilimleyici kullandığınızda, tarihler *Kısa Tarih* biçiminde görüntülenir. Tarihi biçimi kullanıcının tarayıcı veya işletim sistemi yerel ayarı tarafından belirlenir. Bundan dolayı, temel verilerin veya modelin veri türü ayarları ne olursa olsun görüntü biçimi o olacaktır.

Örneğin temel veri türünüz uzun veri biçiminde olabilir. Bu durumda *g AAAA yyyy, gggg* gibi bir tarih biçimi diğer görsellerde veya durumlarda tarihi *14 Mart 2001, Çarşamba* olarak biçimlendirebilir. Ama tarihi aralığı dilimleyicisinde bu tarih dilimleyicide *14/03/2001* olarak biçimlendirilir.

Dilimleyicide Kısa Tarih biçiminin görüntülenmesi, dilimleyicinin içinde dize uzunluğunun tutarlı ve kısa tutulmasını sağlar.

## <a name="limitations-and-considerations"></a>Sınırlamalar ve önemli noktalar

Sayısal aralık dilimleyici için sınırlamalar ve önemli noktalar aşağıda belirtilmiştir:

* Sayısal aralık dilimleyici verilerdeki temel alınan satırları filtreler, toplanmış değerlere filtre uygulamaz. Örneğin bir *Satış Tutarı* alanı kullandığınızı varsayalım. Dilimleyici her işlemi görselin her veri noktası için satış tutarı toplamı temelinde değil satış tutarı temelinde filtreler.
* Bu özellik şu an için ölçülerle birlikte çalışmamaktadır.
* Sayısal dilimleyiciye, temel alınan sütundaki değer aralığının dışında olsa dahi istediğiniz sayı türünü girebilirsiniz. Bu seçenek, verilerin ileride değişme ihtimali olduğunu biliyorsanız filtreleri buna göre ayarlamanızı sağlar.
