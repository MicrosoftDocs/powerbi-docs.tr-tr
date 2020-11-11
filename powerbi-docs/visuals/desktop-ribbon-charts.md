---
title: Power BI'daki şerit grafikleri kullanma
description: Power BI Desktop'ta şerit grafikler oluşturma ve bunları kullanma
author: msftrien
ms.reviewer: mihart
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: how-to
ms.date: 05/05/2019
ms.author: rien
LocalizationGroup: Visualizations
ms.openlocfilehash: e89712dea5d9f932669141d8fe4129727166a342
ms.sourcegitcommit: 5ccab484cf3532ae3a16acd5fc954b7947bd543a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/06/2020
ms.locfileid: "93413143"
---
# <a name="create-ribbon-charts-in-power-bi"></a>Power BI'da şerit grafikleri oluşturma

[!INCLUDE[consumer-appliesto-nyyn](../includes/consumer-appliesto-nyyn.md)]    

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

Verileri görselleştirmek ve hangi veri kategorisinin en yüksek dereceye (en yüksek değer) sahip olduğunu hızla keşfetmek için şerit grafikleri oluşturabilirsiniz. Şerit grafikler, sıralama değişimini gösterme konusunda etkili bir araçtır; en yüksek sıra (değer) her bir zaman aralığı için her zaman en üstte görüntülenir. 

![Yıla ve çeyreğe göre görüntülenen Ses, Cep telefonları ve diğer kategorilere ait verilerin yer aldığı şerit grafiği gösteren ekran görüntüsü.](media/desktop-ribbon-charts/ribbon-charts-01.png)

> [!NOTE]
> Raporunuzu bir Power BI iş arkadaşınızla paylaşmak için her ikinizin de bireysel Power BI Pro lisanslarınızın olması veya raporun Premium kapasitede depolanması gerekir. Bkz. [Raporları paylaşma](../collaborate-share/service-share-reports.md).

## <a name="prerequisites"></a>Önkoşullar

Bu öğreticide [Perakende Analizi örneği .PBIX dosyası](https://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix) kullanılmıştır.

1. Menü çubuğunun sol üst köşesinden **Dosya** > **Aç** ’ı seçin
   
2. **Perakende Analizi örneği PBIX dosyasının** kopyasını bulun

1. **Perakende Analizi örneği PBIX dosyasını** rapor görünümünde ![Rapor görünümü simgesinin ekran görüntüsü.](media/power-bi-visualization-kpi/power-bi-report-view.png) açın.

1. Seç ![Sarı sekmenin ekran görüntüsü.](media/power-bi-visualization-kpi/power-bi-yellow-tab.png) yeni bir sayfa ekleyin.

## <a name="create-a-ribbon-chart"></a>Bir şerit grafik oluşturma

1. Bir şerit grafik oluşturmak için **Görsel Öğeler** bölmesinden **şerit grafik** seçeneğini belirleyin.

    ![görsel öğe şablonları](media/desktop-ribbon-charts/power-bi-template.png)

    Şerit grafikler, şeritler kullanarak görselleştirilen zaman sürekliliği üzerinden bir veri kategorisine bağlanır ve belirli bir kategorinin, grafiğin x ekseni (genellikle zaman çizelgesi) aralığındaki sıralamasını görmenize olanak sağlar.

2. **Eksen** , **Gösterge** ve **Değer** için alanları seçin.  Biz bu örnekte şunları seçtik: **Store** > **OpenDate** , **Item** > **Category** ve **Sales** > **This year sales** > **Value**.  

    ![seçili Alanlar](media/desktop-ribbon-charts/power-bi-ribbon-values.png)

    Veri kümesi tek bir yılın verilerini içerdiğinden, **Eksen** 'den **Year** ve **Quarter** alanını da kaldırdık.

3. Şerit grafiğinde tüm ayların derecelendirmesi gösterilir. Zaman içinde derecelendirmenin nasıl değiştiğine dikkat edin. Örneğin Home kategorisi Şubat'tan Mart'ta kadar ikinci sıradan beşinci sıraya geçmiş.

    ![Oluşturduğunuz ve bazı verilerin vurgulanmış olduğu şerit grafiği gösteren ekran görüntüsü.](media/desktop-ribbon-charts/power-bi-ribbon.png)

## <a name="format-a-ribbon-chart"></a>Bir şerit grafiği biçimlendirme
Bir şerit grafik oluşturduğunuzda **Görsel Öğeler** bölmesinin **Biçim** bölümünde bazı biçimlendirme seçenekleri kullanıma sunulur. Şerit grafiklere yönelik biçimlendirme seçenekleri, yığılmış sütun grafiklere yönelik biçimlendirme seçeneklerine benzese de şeritlere özel ek biçimlendirme seçenekleri içerir.

![Biçim simgesinin seçili olduğunu ve Şeritler alanının genişletildiğini gösteren ekran görüntüsü.](media/desktop-ribbon-charts/power-bi-format-ribbon.png)

Şerit grafikleri için bu biçimlendirme seçenekleri ayarlar yapmanızı sağlar.

* **Aralık** , şeritler arasında ne kadar boşluk olacağını ayarlamanıza olanak sağlar. Sütunun maksimum yüksekliğinin yüzde cinsinden değeridir.
* **Seri rengini eşleştir** , şeritlerin rengiyle seri rengini eşleştirmenizi sağlar. **Kapalı** olarak ayarlandığında, şeritler gridir.
* **Saydamlık** , şeritlerin saydamlığını belirler ve varsayılan olarak 30 değerine ayarlanmıştır.
* **Kenarlık** , şeritlerin üst ve alt kısımlarına koyu renkli bir kenarlık yerleştirmenize olanak sağlar. Varsayılan olarak kenarlıklar kapalıdır.

Şerit grafiğinin y ekseninde etiket olmadığından, veri etiketleri eklemek isteyebilirsiniz. Biçimlendirme bölmesinde **Veri etiketleri** 'ni seçin. 

![veri etiketleri için biçimlendirme seçenekleri](media/desktop-ribbon-charts/power-bi-labels.png)

Veri etiketleriniz için biçimlendirme seçeneklerini ayarlayın. Bu örnekte, metin rengini beyaz ve görüntü birimlerini binler olarak ayarladık.

![Şerit grafiğinizin son biçimini gösteren ekran görüntüsü.](media/desktop-ribbon-charts/power-bi-data-labels.png)

## <a name="next-steps"></a>Sonraki adımlar

[Power BI'daki dağılım grafikleri ve kabarcık grafikleri](power-bi-visualization-scatter.md)

[Power BI'daki görselleştirme türleri](power-bi-visualization-types-for-reports-and-q-and-a.md)
