---
title: "İnsan Kaynakları örneği: Tura katılın"
description: "Power BI için İnsan Kaynakları örneği: Tura katılın"
services: powerbi
documentationcenter: 
author: mihart
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
ms.date: 12/04/2017
ms.author: mihart
ms.openlocfilehash: 0bb540a4c27729999bbb1780a7d5a203d67d3a7c
ms.sourcegitcommit: 54da95f184dd0f7bb59bb0bc8775a1d93129b195
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/08/2017
---
# <a name="human-resources-sample-for-power-bi-take-a-tour"></a>Power BI için İnsan Kaynakları örneği: Tura katılın
İK departmanları, bulundukları şirketler sektöre veya boyuta göre farklılık gösterse de aynı raporlama modeline sahiptir. Bu örnek, yeni işe alımlara, etkin çalışanlara ve işten ayrılan çalışanlara odaklanarak işe alım stratejisindeki eğilimleri ortaya çıkarmaya çalışır. Ana hedeflerimiz aşağıdaki noktaları kavramaktır:

* İşe aldığımız kişiler
* İşe alım stratejimizdeki eğilimler
* Gönüllü ayrılma konusundaki eğilimler

Bu örnek, Power BI'ı işle ilgili veriler, raporlar ve panolarla birlikte nasıl kullanabileceğinizi gösteren serinin bir parçasıdır. Bunlar, obviEnce'tan ([www.obvience.com](http://www.obvience.com/)) alınan anonimleştirilmiş gerçek verilerdir.

![](media/sample-human-resources/hr1.png)

Birlikte ilerlemek ister misiniz? [Power BI hizmetinde](https://powerbi.com) **Veri Al > Örnekler > İnsan Kaynakları Örneği > Bağlan** yolunu izleyerek örneğin bir kopyasını edinin.

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
[Soru-Cevap soru kutusu](service-how-to-q-and-a.md), doğal dil kullanarak soru yazdığınız yerdir. Soru-Cevap, yazdığınız kelimeleri tanıyarak cevabı veri kümesinin neresinde bulabileceğini belirler.

1. Soru-Cevap soru kutusuna tıklayın. Yazmaya başlamadan önce bile Soru-Cevap kutusunun öneriler içerdiğini göreceksiniz:
   
   ![](media/sample-human-resources/pbi_hr_sample_qabox.png)
2. Bu önerilerden birini seçebilir veya şunu yazabilirsiniz: **show age group, gender and bad hires SPLY where region is east** (Doğu bölgesinde geçen yıl aynı dönem yaş grubunu, cinsiyeti ve hatalı işe alımları göster.)  
   
   ![](media/sample-human-resources/pbi_hr_sample_qa_answer.png)
   
   Hatalı olarak işe alınan kadınların birçoğunun 30 yaşın altında olduğuna dikkat edin.

Bu ortamda istediğiniz değişikliği gerçekleştirebilirsiniz. Değişikliklerinizi kaydetmemeyi seçme konusunda her zaman özgürsünüz. Değişiklikleri kaydederseniz istediğiniz zaman **Veri Al** bölümüne giderek bu örneğin yeni bir kopyasını edinebilirsiniz.

## <a name="next-steps-connect-to-your-data"></a>Sonraki adımlar: Verilerinize bağlanma
Bu turda Power BI panolarının, Soru-Cevap özelliğinin ve raporların insan kaynakları verileriyle ilgili olarak nasıl öngörüler sağlayabileceğini kavradığınızı umuyoruz. Şimdi kendi verilerinize bağlanma sırası sizde. Power BI ile çok çeşitli veri kaynaklarına bağlanabilirsiniz. [Power BI ile çalışmaya başlama](service-get-started.md) hakkında daha fazla bilgi edinin.  

