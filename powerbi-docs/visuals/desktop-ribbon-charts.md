---
title: Power BI'daki şerit grafikleri kullanma
description: Power BI hizmetinde ve Power BI Desktop'ta şerit grafikler oluşturma ve bunları kullanma
author: mihart
manager: kvivek
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 06/10/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 3400071c6b8cee472bb61475e6d3482189680563
ms.sourcegitcommit: 797bb40f691384cb1b23dd08c1634f672b4a82bb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/12/2019
ms.locfileid: "66840091"
---
# <a name="use-ribbon-charts-in-power-bi"></a>Power BI'daki şerit grafikleri kullanma
Verileri görselleştirmek ve hangi veri kategorisinin en yüksek dereceye (en yüksek değer) sahip olduğunu hızla keşfetmek için şerit grafikleri kullanabilirsiniz. Şerit grafikler, sıralama değişimini gösterme konusunda etkili bir araçtır; en yüksek sıra (değer) her bir zaman aralığı için her zaman en üstte görüntülenir. 

![Şerit grafik](media/desktop-ribbon-charts/ribbon-charts_01.png)

## <a name="create-a-ribbon-chart"></a>Bir şerit grafik oluşturma
Örneği takip etmek için [Perakende analizi örnek raporunu](../sample-retail-analysis.md) açın. 

1. Bir şerit grafik oluşturmak için **Görsel Öğeler** bölmesinden **şerit grafik** seçeneğini belirleyin.

    ![görsel öğe şablonları](media/desktop-ribbon-charts/power-bi-template.png)

    Şerit grafikler, şeritler kullanarak görselleştirilen zaman sürekliliği üzerinden bir veri kategorisine bağlanır ve belirli bir kategorinin, grafiğin x ekseni (genellikle zaman çizelgesi) aralığındaki sıralamasını görmenize olanak sağlar.

2. **Eksen**, **Gösterge** ve **Değer** için alanları seçin.  Biz bu örnekte şunları seçtik: **Date**, **Category** ve **This year sales**.  

    ![seçili alanlar](media/desktop-ribbon-charts/power-bi-ribbon-values.png)

    Veri kümesi tek bir yılın verilerini içerdiğinden, **Eksen**'den **Year** alanını da kaldırdık. 

3. Şerit grafiğinde tüm diğer ayların derecelendirmesi gösterilir. Zaman içinde derecelendirmenin nasıl değiştiğine dikkat edin.  Örneğin, Home kategorisi üçüncülükten dördüncülüğe geçmiş ve sonra yeniden üçüncülüğe dönmüştür. Juniors kategorisi Temmuz ayında üçüncülükten beşinciliğe geçmiştir. 

    ![Şerit grafik](media/desktop-ribbon-charts/power-bi-ribbon.png)

## <a name="format-a-ribbon-chart"></a>Bir şerit grafiği biçimlendirme
Bir şerit grafik oluşturduğunuzda **Görsel Öğeler** bölmesinin **Biçim** bölümünde bazı biçimlendirme seçenekleri kullanıma sunulur. Şerit grafiklere yönelik biçimlendirme seçenekleri, yığılmış sütun grafiklere yönelik biçimlendirme seçeneklerine benzese de şeritlere özel ek biçimlendirme seçenekleri içerir.

![Görselleştirme bölmesinde şerit şablonu](media/desktop-ribbon-charts/power-bi-format-ribbon.png)

Şerit grafikleri için bu biçimlendirme seçenekleri ayarlar yapmanızı sağlar.

* **Aralık**, şeritler arasında ne kadar boşluk olacağını ayarlamanıza olanak sağlar. Sütunun maksimum yüksekliğinin yüzde cinsinden değeridir.
* **Seri rengini eşleştir**, şeritlerin rengiyle seri rengini eşleştirmenizi sağlar. **Kapalı** olarak ayarlandığında, şeritler gridir.
* **Saydamlık**, şeritlerin saydamlığını belirler ve varsayılan olarak 30 değerine ayarlanmıştır.
* **Kenarlık**, şeritlerin üst ve alt kısımlarına koyu renkli bir kenarlık yerleştirmenize olanak sağlar. Varsayılan olarak kenarlıklar kapalıdır.

Şerit grafiğinin y ekseninde etiket olmadığından, veri etiketleri eklemek isteyebilirsiniz. Biçimlendirme bölmesinde **Veri etiketleri**'ni seçin. 

![veri etiketleri için biçimlendirme seçenekleri](media/desktop-ribbon-charts/power-bi-labels.png)

Veri etiketleriniz için biçimlendirme seçeneklerini ayarlayın.  Bu örnekte, metin rengini beyaz, ondalık konumları sıfır ve görüntü birimlerini binler olarak ayarladık. 

![Görselleştirme bölmesinde şerit şablonu](media/desktop-ribbon-charts/power-bi-data-labels.png)

## <a name="next-steps"></a>Sonraki adımlar

[Power BI'daki dağılım grafikleri ve kabarcık grafikleri](power-bi-visualization-scatter.md)

[Power BI'daki görselleştirme türleri](power-bi-visualization-types-for-reports-and-q-and-a.md)