---
title: 'İnsan Kaynakları örneği: Tura katılın'
description: 'Power BI için İnsan Kaynakları örneği: Tura katılın'
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/22/2018
ms.author: mihart
LocalizationGroup: Samples
ms.openlocfilehash: 770e200b0aa6916ac6d2de144902a04e9660e552
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34482027"
---
# <a name="human-resources-sample-for-power-bi-take-a-tour"></a>Power BI için İnsan Kaynakları örneği: Tura katılın

## <a name="overview-of-the-human-resources-sample"></a>İnsan Kaynakları örneğine genel bakış
İK departmanları, bulundukları şirketler sektöre veya boyuta göre farklılık gösterse de aynı raporlama modeline sahiptir. Bu örnek, yeni işe alımlara, etkin çalışanlara ve işten ayrılan çalışanlara odaklanarak işe alım stratejisindeki eğilimleri ortaya çıkarmaya çalışır. Ana hedeflerimiz aşağıdaki noktaları kavramaktır:

* İşe aldığımız kişiler
* İşe alım stratejimizdeki eğilimler
* Gönüllü ayrılma konusundaki eğilimler

![](media/sample-human-resources/hr1.png)

Bu örnek, Power BI'ı işle ilgili veriler, raporlar ve panolarla birlikte nasıl kullanabileceğinizi gösteren serinin bir parçasıdır. Bunlar, obviEnce'tan ([www.obvience.com](http://www.obvience.com/)) alınan anonimleştirilmiş gerçek verilerdir. Veriler çeşitli biçimlerde sunulur: içerik paketi/uygulama, Excel çalışma kitabı veya .pbix Power BI Desktop dosyası. Daha fazla bilgi için bkz. [Örnek veri kümeleri](sample-datasets.md).

## <a name="prerequisites"></a>Önkoşullar

 Örneği kullanabilmeniz için öncelikle bunu bir [içerik paketi](https://docs.microsoft.com/power-bi/sample-human-resources#get-the-content-pack-for-this-sample), [pbix dosyası](http://download.microsoft.com/download/6/9/5/69503155-05A5-483E-829A-F7B5F3DD5D27/Human-Resources-Sample-PBIX.pbix) veya [Excel çalışma kitabı](http://go.microsoft.com/fwlink/?LinkId=529780) olarak indirmeniz gerekir.

### <a name="get-the-content-pack-for-this-sample"></a>Bu örneğe ilişkin içerik paketini edinme

1. Power BI hizmeti (app.powerbi.com) sayfasına gidin ve oturum açın.
2. Sol alt köşedeki **Veri Al** seçeneğini belirleyin.
   
    ![](media/sample-datasets/power-bi-get-data.png)
3. Görüntülenen Veri Al sayfasında **Örnekler** simgesini seçin.
   
   ![](media/sample-datasets/power-bi-samples-icon.png)
4. **İnsan Kaynakları Örneği**'ni ve ardından **Bağlan**'ı seçin.  
   
   ![Veri Al](media/sample-human-resources/pbi_hr_sample_connect.png)
5. Power BI, içerik paketini içeri aktarır ve geçerli çalışma alanınıza yeni bir pano, rapor ve veri kümesi ekler. Yeni içerik sarı yıldızla işaretlenir. 
   
   ![Yıldız işareti](media/sample-human-resources/human-resources-sample-asterisk.png)
  
### <a name="get-the-pbix-file-for-this-sample"></a>Bu örneğe ilişkin .pbix dosyasını edinme

Alternatif olarak, örneği bir .pbix dosyası olarak indirebilirsiniz. Bu dosya biçimi, Power BI Desktop ile kullanım için tasarlanmıştır. 

 * [İnsan Kaynakları Örneği](http://download.microsoft.com/download/6/9/5/69503155-05A5-483E-829A-F7B5F3DD5D27/Human Resources Sample PBIX.pbix)

### <a name="get-the-excel-workbook-for-this-sample"></a>Bu örneğe ilişkin Excel çalışma kitabını edinme
Ayrıca bu örnek için [ yalnızca veri kümesini de (Excel çalışma kitabı) indirebilirsiniz](http://go.microsoft.com/fwlink/?LinkId=529780). Çalışma kitabı, görüntüleyebileceğiniz ve değiştirebileceğiniz Power View sayfaları içerir. Ham verileri görmek için **Power Pivot > Yönet** seçeneğini belirleyin.

## <a name="new-hires"></a>Yeni işe alımlar
Önce yeni işe alımları inceleyelim.

1. Çalışma alanınızda **Panolar** sekmesini seçin ve İnsan Kaynakları panosunu açın.
2. Panoda **New Hire Count, Hire Count, New Hires Same Period Last Year, Actives YoY % Change** **By Month** seçeneğini belirleyin.  
   ![](media/sample-human-resources/hr2.png)  

   İnsan Kaynakları Örneği raporu **New Hires** sayfası ile açılır.  

   ![](media/sample-human-resources/hr3.png)

Aşağıdakilere dikkat edin:

* **Month tarafından düzenlenen New Hire Count, New Hires SPLY ve Actives YoY % Change** birleşik haritası, geçen yılla karşılaştırıldığında her ay daha fazla çalışan (bazı aylarda çok daha fazla sayıda çalışan) işe aldığımızı gösteriyor.
* **Region ve Ethnicity tarafından düzenlenen New Hire Count ve Active Employee Count** birleşik haritasında, **East** bölgesinde daha az sayıda çalışan işe aldığımızı görebilirsiniz.
* **Age Group tarafından düzenlenen New Hires YoY Var** şelale grafiği çoğunlukla genç çalışanları işe aldığımızı gösteriyor. Neden olarak, işlerin genel olarak yarı zamanlı olması gösterilebilir.
* **Gender tarafından düzenlenen New Hire Count** pasta grafiğinde oldukça eşit bir dağılım gözlemleniyor.

Cinsiyet dağılımının ayrımının eşit olmadığı bir bölge gibi daha fazla öngörüye ulaşabilir misiniz? Yaş, cinsiyet, bölge ve etnik köken arasındaki ilişkileri araştırmak için grafiklerdeki farklı yaş gruplarını ve cinsiyetleri seçin.

Panoya geri dönmek için üst gezinti çubuğundan panonun adını seçin.

![](media/sample-human-resources/power-bi-breadcrumbs.png)

## <a name="compare-current-active-and-former-employees"></a>Geçerli etkin ve eski çalışanları karşılaştırma
Geçerli etkin çalışanlara ve artık şirket için çalışmayan kişilere ilişkin verileri araştıralım.

Panoda, **Age Group tarafından düzenlenen Active Employee** kutucuğunu seçin.  
![](media/sample-human-resources/pbi_hr_sample_activepie.png)

İnsan Kaynakları Örneği raporu **Actives and Separations** sayfasıyla açılır.  
![](media/sample-human-resources/hr5.png)

**Dikkat çekilmesi gereken öğeler**:

* Sol taraftaki birleşik haritalarda, etkin çalışan ve ayrılan sayılarında yıldan yıla gözlemlenen değişiklik gösterilir. Bu yıl yüksek bir işe alım oranıyla birlikte daha fazla etkin çalışana sahibiz ancak ayrılan sayısında da geçen yıla göre bir artış gözlemliyoruz.
* Ağustos'ta diğer aylara kıyasla daha fazla ayrılma gerçekleşmiş. Herhangi bir aykırı değer bulup bulamayacağınızı öğrenmek için farklı yaş gruplarını, cinsiyetleri veya bölgeleri seçin.
* Pasta grafiklerine baktığımızda cinsiyet ve yaş gruplarına göre etkin çalışanlarımızda oldukça eşit bir dağılım görüyoruz. Yaşa göre cinsiyet dağılımı farklılıklarını görüntülemek için farklı yaş gruplarını seçin. Her yaş grubunda eşit bir cinsiyet dağılımına mı sahibiz?

## <a name="reasons-for-separation"></a>Ayrılma nedenleri
Rapora, Düzenleme Görünümü'nde göz atalım. Sol üst köşedeki **Raporu düzenle** seçeneğini belirleyin.

Pasta grafiklerini Etkin çalışanlar yerine Ayrılan verilerini gösterecek şekilde değiştirin.

1. **Age Group tarafından düzenlenen Active Employee Count** pasta grafiğini seçin.
2. **Alanlar**'da Employees tablosunu genişletmek için **Employees**'in yanındaki oku seçin. **Active Employee Count**'un yanındaki onay kutusunu temizleyerek söz konusu alanı kaldırın.
3. Employees tablosundaki **Separation Count**'un yanındaki onay kutusunu seçerek bu alanı, alan kutusundaki **Values** kutusuna ekleyin.
4. Rapor tuvaline geri döndüğünüzde, **Separation Reason tarafından düzenlenen Separation Count** çubuk grafiğindeki **Voluntary** çubuğunu seçin. Bu, rapordaki diğer görsellerde, gönüllü olarak ayrılan kişileri vurgular.
5. Age Group tarafından düzenlenen Separation Count pasta grafiğinin 50+ adlı dilimine tıklayın.

   Sağ alt köşedeki Separations by Reason çizgi grafiğine bakın. Bu grafik, gönüllü ayrılmaları gösterecek şekilde filtrelenmiştir.  
   ![](media/sample-human-resources/pbi_hr_sample_sepsover50.png)

   50 ve üzeri yaş grubundaki eğilimi fark ettiniz mi? Yılın ikinci yarısında 50 yaşın üstünde daha fazla çalışan gönüllü olarak ayrılıyor. Bu, daha fazla veriyle daha ayrıntılı bir şekilde incelenebilecek bir alan.
6. **Gender tarafından düzenlenen Active Employee Count** pasta grafiği için de aynı adımları izleyebilir ve grafiği, etkin çalışanlar yerine ayrılanları gösterecek şekilde değiştirebilirsiniz. Başka herhangi bir öngörü bulup bulamayacağınızı öğrenmek için cinsiyete göre gönüllü ayrılma verilerini gözden geçirin.
7. Panoya geri dönmek için üst gezinti çubuğunda **Power BI**'a tıklayın. Raporda yapmış olduğunuz değişiklikleri kaydedip kaydetmemek size kalmıştır.

## <a name="bad-hires"></a>Hatalı işe alımlar
Araştırılacak son alan hatalı işe alımlardır. Hatalı işe alımlar, en fazla 60 gün çalışan kişiler olarak tanımlanır. Yüksek oranda işe alım gerçekleştiriyoruz. İyi adayları mı işe alıyoruz?

1. **Age Group tarafından düzenlenen Bad Hires as % of Actives** pano kutucuğunu seçin. Bu kutucuk, raporun "Bad Hires" başlıklı 3. sayfasını açar.

   ![](media/sample-human-resources/hr7.png)  
2. Sol taraftaki Bölge dilimleyicisinde **Northwest** onay kutusunu ve Gender tarafından düzenlenen Bad Hire Count halka grafiğindeki **male** dilimini seçin.  "Bad Hires" sayfasındaki diğer grafiklere bakın. Kadınlara göre daha fazla erkeğin hatalı olarak işe alındığını ve Group A'da çok sayıda hatalı işe alımın bulunduğunu görüyoruz.
   ![](media/sample-human-resources/pbi_hr_sample_badhirespage.png)  
3. **Gender tarafından düzenlenen Bad Hires** halka grafiğine baktığımızda ve **Region** dilimleyicisine tıkladığımızda Doğu'nun erkeklere göre daha çok kadının hatalı olarak işe alındığı tek bölge olduğunu görüyoruz.  
4. Panoya geri dönmek için üst gezinti çubuğundan panonun adını seçin.

## <a name="asking-a-question-in-the-qa-box"></a>Soru-Cevap kutusunda soru sorma
[Soru-Cevap soru kutusu](power-bi-tutorial-q-and-a.md), doğal dil kullanarak soru yazdığınız yerdir. Soru-Cevap, yazdığınız kelimeleri tanıyarak cevabı veri kümesinin neresinde bulabileceğini belirler.

1. Soru-Cevap soru kutusuna tıklayın. Yazmaya başlamadan önce bile Soru-Cevap kutusunun öneriler içerdiğini göreceksiniz:

   ![](media/sample-human-resources/pbi_hr_sample_qabox.png)
2. Bu önerilerden birini seçebilir veya şunu yazabilirsiniz: **show age group, gender and bad hires SPLY where region is east** (Doğu bölgesinde geçen yıl aynı dönem yaş grubunu, cinsiyeti ve hatalı işe alımları göster.)  

   ![](media/sample-human-resources/pbi_hr_sample_qa_answer.png)

   Hatalı olarak işe alınan kadınların birçoğunun 30 yaşın altında olduğuna dikkat edin.

Bu ortamda istediğiniz değişikliği gerçekleştirebilirsiniz. Değişikliklerinizi kaydetmemeyi seçme konusunda her zaman özgürsünüz. Değişiklikleri kaydederseniz istediğiniz zaman **Veri Al** bölümüne giderek bu örneğin yeni bir kopyasını edinebilirsiniz.

## <a name="next-steps-connect-to-your-data"></a>Sonraki adımlar: Verilerinize bağlanma
Bu turda Power BI panolarının, Soru-Cevap özelliğinin ve raporların insan kaynakları verileriyle ilgili olarak nasıl öngörüler sağlayabileceğini kavradığınızı umuyoruz. Şimdi kendi verilerinize bağlanma sırası sizde. Power BI ile çok çeşitli veri kaynaklarına bağlanabilirsiniz. [Power BI ile çalışmaya başlama](service-get-started.md) hakkında daha fazla bilgi edinin.  
