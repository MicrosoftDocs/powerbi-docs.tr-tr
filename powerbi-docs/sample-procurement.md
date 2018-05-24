---
title: 'Procurement Analysis Sample: Tura katılın'
description: 'Power BI için Procurement Analysis Sample: Tura katılın'
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/20/2018
ms.author: mihart
LocalizationGroup: Samples
ms.openlocfilehash: 0fee8ea43224f6b2b1d36886c7b8075716f89633
ms.sourcegitcommit: 2b9ef93bbff5c741ba55ea0502f642632683d593
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/24/2018
---
# <a name="procurement-analysis-sample-for-power-bi-take-a-tour"></a>Power BI için Procurement Analysis Sample: Tura katılın

## <a name="overview-of-the-procurement-analysis-sample"></a>Tedarik Analizi örneğine genel bakış
Bu sektör örneği panosunda ve bağlantılı raporda, bir üretim şirketinin kategori ve konuma göre satıcılar için yaptığı harcamalar çözümlenmiştir. Bu örnekte şu alanları araştıracağız:

* En iyi satıcılar
* En çok harcama yaptığımız kategoriler
* Bize en yüksek indirimi sunan satıcılar ve bu indirimlerin ne zaman yapıldığı

Bu örnek, iş odaklı veriler, raporlar ve panolar ile Power BI'ı nasıl kullanabileceğinizi gösteren serinin bir parçasıdır. Bunlar, obviEnce'tan ([www.obvience.com](http://www.obvience.com/)) alınan anonimleştirilmiş gerçek verilerdir.

![](media/sample-procurement/procurement1.png)

## <a name="prerequisites"></a>Önkoşullar

 Örneği kullanabilmeniz için bir [içerik paketi](https://docs.microsoft.com/en-us/power-bi/sample-procurement#get-the-content-pack-for-this-sample), [.pbix dosyası](http://download.microsoft.com/download/D/5/3/D5390069-F723-413B-8D27-5888500516EB/Procurement-Analysis-Sample-PBIX.pbix) veya [Excel çalışma kitabı](http://go.microsoft.com/fwlink/?LinkId=529784) olarak indirmeniz gerekir.

### <a name="get-the-content-pack-for-this-sample"></a>Bu örneğe ilişkin içerik paketini edinme

1. Power BI hizmeti (app.powerbi.com) sayfasına gidin ve oturum açın.
2. Sol alt köşedeki **Veri Al** seçeneğini belirleyin.
   
    ![](media/sample-datasets/power-bi-get-data.png)
3. Görüntülenen Veri Al sayfasında **Örnekler** simgesini seçin.
   
   ![](media/sample-datasets/power-bi-samples-icon.png)
4. **Tedarik Analizi Örneği**'ni ve ardından **Bağlan**'ı seçin.  
  
   ![Veri Al](media/sample-procurement/procurement1a.png)
   
5. Power BI, içerik paketini içeri aktarır ve geçerli çalışma alanınıza yeni bir pano, rapor ve veri kümesi ekler. Yeni içerik sarı yıldızla işaretlenir. 
   
   ![Yıldız işareti](media/sample-procurement/procurement1b.png)
  
### <a name="get-the-pbix-file-for-this-sample"></a>Bu örneğe ilişkin .pbix dosyasını edinme

Alternatif olarak, örneği bir .pbix dosyası olarak indirebilirsiniz. Bu dosya biçimi, Power BI Desktop ile kullanım için tasarlanmıştır. 

 * [Tedarik Analizi Örneği](http://download.microsoft.com/download/D/5/3/D5390069-F723-413B-8D27-5888500516EB/Procurement%20Analysis%20Sample%20PBIX.pbix)

### <a name="get-the-excel-workbook-for-this-sample"></a>Bu örneğe ilişkin Excel çalışma kitabını edinme
Ayrıca bu örnek için [ yalnızca veri kümesini de (Excel çalışma kitabı) indirebilirsiniz](http://go.microsoft.com/fwlink/?LinkId=529784). Çalışma kitabı, görüntüleyebileceğiniz ve değiştirebileceğiniz Power View sayfaları içerir. Ham verileri görmek için **Power Pivot > Yönet** seçeneğini belirleyin.


## <a name="spending-trends"></a>Harcama eğilimleri
İlk olarak kategoriye ve konuma göre harcama eğilimlerine göz atalım.  

1. Çalışma alanınızda **Panolar** sekmesini açın ve Procurement Analysis panosunu seçin.
2. **Total Invoice by Country/Region** adlı pano kutucuğunu seçin. Bu işlemin ardından "Procurement Analysis Sample" adlı raporun "Spend Overview" sayfası açılır.

    ![](media/sample-procurement/procurement2.png)

Aşağıdaki birkaç noktaya dikkat edin:

* **Month ve Category tarafından düzenlenen Total Invoice** adlı çizgi grafiğinde: **Direct** kategorisinde oldukça tutarlı bir harcama söz konusuyken **Logistics** kategorisinde maksimum harcamanın Aralık ayında yapıldığını ve **Other** kategorisi için Şubat ayında ani bir artış yaşandığını görüyoruz.
* **Country/Region tarafından düzenlenen Total Invoice** adlı haritada: Harcamalarımızın çoğunu ABD'de yaptığımızı görüyoruz.
* **Sub Category tarafından düzenlenen Total Invoice** adlı sütun grafiğinde: **Hardware** ve **Indirect Goods & Services** kategorilerinin, en fazla harcama yapılan kategoriler olduğu görülüyor.
* Tier tarafından düzenlenen Total Invoice adlı çubuk grafiğinde: Büyük çoğunlukla, Katman 1'de (ilk 10) yer alan satıcılarımızla çalıştığımızı görüyoruz. Bu, satıcı ilişkilerinin daha iyi yönetilmesine yardımcı olur.

## <a name="spending-in-mexico"></a>Meksika'da yapılan harcamalar
Şimdi de Meksika'daki harcama alanlarını araştıralım.

1. Pasta grafiğinde haritadaki **Meksika** balonunu seçin. "Sub Category tarafından düzenlenen Total Invoice" adlı sütun grafiğinde, en fazla harcamanın **Indirect Goods & Services** alt kategorisinde yapıldığını görüyoruz.

   ![](media/sample-procurement/pbi_procsample_spendmexico.png)
2. **Indirect Goods & Services** sütununda detaya gidin:

   * Grafiğin sağ üst köşesinde bulunan, detaya git okunu ![](media/sample-procurement/pbi_drilldown_icon.png) seçin.
   * **Indirect Goods & Services** sütununu seçin.

      Bu kategoride şu ana kadar en fazla harcamanın Sales & Marketing alanında yapıldığını görüyoruz.
   * Haritada tekrar **Meksika**'yı seçin.

      Meksika'da bu kategorideki en fazla harcamanın Maintenance & Repair için yapıldığı görülüyor.

      ![](media/sample-procurement/pbi_procsample_drill_mexico.png)
3. Detaydan çıkmak için grafiğin sol üst köşesindeki yukarı oku seçin.
4. Oku tekrar seçerek detaya gitme özelliğini devre dışı bırakın.  
5. Çalışma alanınıza dönmek için üst kısımdaki gezinti çubuğunda **Power BI**'ı seçin.

## <a name="evaluate-different-cities"></a>Farklı şehirleri değerlendirme
Farklı şehirleri değerlendirmek için vurgulama özelliğini kullanabiliriz.

1. **Month tarafından düzenlenen Total Invoice ve Discount %** adlı pano kutucuğunu seçin. Bu işlemin ardından raporun "Discount Analysis" sayfası açılır.
2. **City tarafından düzenlenen Total Invoice** adlı ağaç haritasında farklı şehirleri seçerek karşılaştırma yapabilirsiniz. Miami'nin neredeyse tüm faturalarının Katman 1'deki satıcılara ait olduğu görülüyor.

   ![](media/sample-procurement/pbi_procsample_miamitreemap2.png)

## <a name="vendor-discounts"></a>Satıcı indirimleri
Şimdi de satıcıların sunduğu indirimleri ve en fazla indirimi aldığımız zaman aralıklarını inceleyelim.

![](media/sample-procurement/procurement4.png)

Özellikle aşağıdaki sorulara cevap arayacağız:

* İndirimler aydan aya değişiklik gösteriyor mu yoksa her ay aynı mı?
* Bazı şehirler diğerlerine göre daha fazla indirim alıyor mu?

### <a name="discount-by-month"></a>Aylara göre indirim
**Month tarafından düzenlenen Total Invoice ve Discount %** adlı birleşik haritada **Şubat** ayının en yoğun geçen ay olduğunu ve bunu **Eylül** ayının izlediğini görüyoruz. Şimdi bu aylardaki indirim yüzdelerine göz atalım.
Hacim arttıkça indirimin azaldığını ve hacim düştükçe indirimin arttığına dikkat edin. Ne kadar indirim talep edersek o kadar düşük hacimlerle çalıştığımızı görüyoruz.

![](media/sample-procurement/procurement5.png)

### <a name="discount-by-city"></a>Şehirlere göre indirim
Araştırılacak başka bir alan ise şehirlere göre yapılan indirimlerdir. Ağaç haritasında her bir şehri seçerek diğer grafiklerin nasıl değiştiğine göz atın.

* St. Louis, MO şehrinin toplam fatura açısından bakıldığında Şubat ayında büyük bir artış yakaladığını, indirim tasarrufu alanında ise Nisan ayında büyük bir düşüş yaşadığını görüyoruz.
* Mexico City, Mexico en yüksek indirim yüzdesine (%11,05) sahipken Atlanta, GA en düşük yüzdeye (%0,08) sahip.

![](media/sample-procurement/procurement6.png)

### <a name="edit-the-report"></a>Raporu düzenleme
Sol üst köşedeki **Raporu düzenle** seçeneğine tıklayıp Düzenleme Görünümü'nde araştırma yapın.

* Sayfaların nasıl oluşturulduğuna bakın
* Aynı verileri temel alarak sayfalar ve grafikler ekleyin
* Bir grafik için görselleştirme türünü değiştirin (örneğin, ağaç haritasını halka grafik olarak değiştirin)
* Bu görselleştirmeleri panonuza sabitleyin

Bu ortamda istediğiniz değişikliği gerçekleştirebilirsiniz. Değişikliklerinizi kaydetmemeyi seçme konusunda her zaman özgürsünüz. Değişiklikleri kaydederseniz istediğiniz zaman **Veri Al** bölümüne giderek bu örneğin yeni bir kopyasını edinebilirsiniz.

## <a name="next-steps-connect-to-your-data"></a>Sonraki adımlar: Verilerinize bağlanma
Bu turda Power BI panolarının, perakende verilerine yönelik olarak nasıl öngörüler sağlayabileceğini kavradığınızı umuyoruz. Şimdi sıra sizde, kendi verilerinize bağlanın. Power BI ile çok çeşitli veri kaynaklarına bağlanabilirsiniz. [Power BI ile çalışmaya başlama](service-get-started.md) hakkında daha fazla bilgi edinin.
