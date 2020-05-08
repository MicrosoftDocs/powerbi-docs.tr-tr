---
title: 'İnsan Kaynakları örneği: Tura katılın'
description: 'Power BI için İnsan Kaynakları örneği: Tura katılın'
author: maggiesMSFT
ms.reviewer: amac
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 07/05/2019
ms.author: maggies
LocalizationGroup: Samples
ms.openlocfilehash: 8124a80f471e33ebbd140a30d6a49e2a762206ee
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "80404098"
---
# <a name="human-resources-sample-for-power-bi-take-a-tour"></a>Power BI için İnsan Kaynakları örneği: Tura katılın

İnsan Kaynakları örneği içerik paketinde, insan kaynakları departmanına yönelik pano, rapor ve veri kümesi bulunur. Bu örnekte, insan kaynakları departmanının bulundukları şirketler sektöre veya boyuta göre farklılık gösterse de aynı raporlama modeline sahiptir. Bu örnek, yeni işe alımlar, etkin çalışanlar ve ayrılan çalışanlara yöneliktir. İşe alma stratejisindeki tüm eğilimleri ortaya çıkarmaya çalışır. Ana hedeflerimiz aşağıdaki noktaları kavramaktır:

* İşe aldığımız kişiler
* İşe alım stratejimizdeki eğilimler
* Gönüllü ayrılma konusundaki eğilimler

![İnsan Kaynakları örneğine yönelik pano](media/sample-human-resources/hr1.png)

Bu örnek, Power BI'ı işle ilgili veriler, raporlar ve panolarla birlikte nasıl kullanabileceğinizi gösteren serinin bir parçasıdır. Örnek, [obviEnce](http://www.obvience.com/) öğesinden alınan, anonimleştirilmiş gerçek verilerle oluşturulmuştur. Veriler çeşitli biçimlerde sunulur: içerik paketi, .pbix Power BI Desktop dosyası veya Excel çalışma kitabı. Bkz. [Power BI Örnekleri](sample-datasets.md). 

Bu öğreticide, Power BI hizmetinde İnsan Kaynakları örneği içerik paketi incelenir. Power BI Desktop ile hizmette rapor deneyimleri benzer olduğundan, Power BI Desktop'ta örnek .pbix dosyasını kullanarak da örneği takip edebilirsiniz. 

Power BI Desktop'ta örnekleri incelemek için Power BI lisansına ihtiyacınız yoktur. Power BI Pro lisansınız yoksa örneği Power BI hizmetinde Çalışma Alanım alanınıza kaydedebilirsiniz. 

## <a name="get-the-sample"></a>Örneği alma

Örneği kullanabilmeniz için bir [içerik paketi](#get-the-content-pack-for-this-sample), [.pbix dosyası](#get-the-pbix-file-for-this-sample) veya [Excel çalışma kitabı](#get-the-excel-workbook-for-this-sample) olarak indirmeniz gerekir.

### <a name="get-the-content-pack-for-this-sample"></a>Bu örneğe ilişkin içerik paketini edinme

1. Power BI hizmetini açın (app.powerbi.com), oturum açın ve örneği kaydetmek istediğiniz çalışma alanını açın.

   Power BI Pro lisansınız yoksa örneği Çalışma Alanım alanınıza kaydedebilirsiniz.

2. Sol alt köşedeki **Veri Al**'ı seçin.
   
   ![Veri Al’ı seçme](media/sample-datasets/power-bi-get-data.png)
3. Görüntülenen **Veri Al** sayfasında **Örnekler**'i seçin.
   
4. **İnsan Kaynakları Örneği**'ni ve ardından **Bağlan**'ı seçin.  
   
   ![Örneğe bağlanma](media/sample-human-resources/pbi_hr_sample_connect.png)

5. Power BI, içerik paketini içeri aktarır ve ardından geçerli çalışma alanınıza yeni bir pano, rapor ve veri kümesi ekler.
   
   ![İnsan Kaynakları Örneği girişi](media/sample-human-resources/hr-sample-entry.png)
  
### <a name="get-the-pbix-file-for-this-sample"></a>Bu örneğe ilişkin .pbix dosyasını edinme

Alternatif olarak, İnsan Kaynakları örneğini bir [.pbix dosyası](https://download.microsoft.com/download/6/9/5/69503155-05A5-483E-829A-F7B5F3DD5D27/Human%20Resources%20Sample%20PBIX.pbix) olarak indirebilirsiniz. Bu dosya biçimi, Power BI Desktop ile kullanım için tasarlanmıştır.

### <a name="get-the-excel-workbook-for-this-sample"></a>Bu örneğe ilişkin Excel çalışma kitabını edinme

Bu örnekte kullanılan veri kaynağını görüntülemek isterseniz, [Excel çalışma kitabı](https://go.microsoft.com/fwlink/?LinkId=529780) olarak da bulabilirsiniz. Çalışma kitabı, görüntüleyebileceğiniz ve değiştirebileceğiniz Power View sayfaları içerir. Ham verileri görmek için Veri Çözümlemesi eklentilerini etkinleştirip **Power Pivot > Yönet**'i seçin. Power View ve Power Pivot eklentilerini etkinleştirmek için bkz. [Excel’de Excel örneklerini bulma](sample-datasets.md#explore-excel-samples-inside-excel).

## <a name="new-hires"></a>Yeni işe alımlar
Önce yeni işe alımları inceleyelim.

1. Çalışma alanınızda **Panolar** sekmesini seçin ve **İnsan Kaynakları Örneği** panosunu açın.
2. Panoda **New Hire Count, Hire Count, New Hires Same Period Last Year, Actives YoY % Change By Month** seçeneğini belirleyin.  

   ![Yeni İşe Alım Sayısı kutucuğu](media/sample-human-resources/hr2.png)  

   İnsan Kaynakları Örneği raporu **New Hires** sayfası ile açılır.  

   ![Yeni İşe Alımlar sayfası](media/sample-human-resources/hr3.png)

3. İlgilendiğiniz bu öğelere gözatın:

    * **Month’a göre New Hire Count, New Hires SPLY ve Actives YoY % Change** birleşik haritası, geçen yılla karşılaştırıldığında her ay daha fazla çalışan işe aldığımızı gösteriyor. Bazı aylarda insan sayısı önemli ölçüde artıyor.
    * **Region ve Ethnicity tarafından düzenlenen New Hire Count ve Active Employee Count** birleşik haritasında, **East** bölgesinde daha az sayıda çalışan işe aldığımızı görebilirsiniz.
    * **Age Group tarafından düzenlenen New Hires YoY Var** şelale grafiği çoğunlukla genç çalışanları işe aldığımızı gösteriyor. Bu eğilimin nedeni olarak, işlerin çoğunlukla yarı zamanlı olması gösterilebilir.
    * **Gender’a göre New Hire Count** pasta grafiğinde yaklaşık olarak eşit bir dağılım gözlemleniyor.

    Daha fazla içgörüye ulaşabilir misiniz? Örneğin, cinsiyet dağılımının ayrımının eşit olmadığı bir bölge. 

4. Yaş, cinsiyet, bölge ve etnik köken arasındaki ilişkileri araştırmak için grafiklerdeki farklı yaş gruplarını ve cinsiyetleri seçin.

5. Panoya geri dönmek için üst gezinti bölmesinden **İnsan Kaynakları Örneği** seçeneğini belirleyin.

   ![Panoya geri dönme](media/sample-human-resources/power-bi-breadcrumbs.png)

## <a name="compare-currently-active-and-former-employees"></a>Geçerli etkin ve eski çalışanları karşılaştırma
Geçerli etkin çalışanlara ve artık şirket için çalışmayan kişilere ilişkin verileri araştıralım.

1. Panoda, **Age Group tarafından düzenlenen Active Employee** kutucuğunu seçin.

   ![Yaş Grubuna göre Etkin Çalışan Sayısı kutucuğu](media/sample-human-resources/pbi_hr_sample_activepie.png)

   İnsan Kaynakları Örneği raporu **Actives and Separations** sayfasıyla açılır.  

   ![Etkin Çalışanlar - Separations sayfası](media/sample-human-resources/hr5.png)

 2. İlgilendiğiniz bu öğelere gözatın:

    * Sol taraftaki iki birleşik haritada, geçerli çalışan ve ayrılan çalışan sayılarında yıldan yıla gözlemlenen değişiklik gösterilir. Bu yıl yüksek bir işe alım oranıyla birlikte daha fazla sayıda çalışana sahibiz ancak ayrılan sayısında da geçen yıla göre bir artış gözlemliyoruz.
    * Ağustos'ta diğer aylara kıyasla daha fazla ayrılma gerçekleşmiş. Herhangi bir aykırı değer bulup bulamayacağınızı öğrenmek için farklı yaş gruplarını, cinsiyetleri veya bölgeleri seçin.
    * Pasta grafiklerine baktığımızda cinsiyet ve yaş gruplarına göre etkin çalışanlarımızda eşit bir dağılım görüyoruz. Yaşa göre cinsiyet dağılımı farklılıklarını görüntülemek için farklı yaş gruplarını seçin. Her yaş grubunda eşit bir cinsiyet dağılımına mı sahibiz?

## <a name="reasons-for-separation"></a>Ayrılma nedenleri
Rapora, Düzenleme Görünümü’nde göz atalım. Geçerli çalışan verileri yerine ayrılan çalışan verilerini göstermek için pasta grafiklerini değiştirebilirsiniz.

1. Sol üst köşedeki **Raporu düzenle** seçeneğini belirleyin.

2. **Age Group tarafından düzenlenen Active Employee Count** pasta grafiğini seçin.

3. **Alanlar**'da **Employees** tablosunu genişletmek için **Employees**'i seçin. **Active Employee Count**'u temizleyerek söz konusu alanı kaldırın.

4. **Employees** tablosundaki **Separation Count**'u seçerek bu alanı, **Alan** kutusundaki **Values** kutusuna ekleyin.

5. Rapor tuvalinde, **Separation Reason’a göre Separation Count** çubuk grafiğindeki **Voluntary** çubuğunu seçin. 

   Bu, rapordaki diğer görsellerde, gönüllü olarak ayrılan çalışanları vurgular.

6. **Age Group’a göre Separation Count** pasta grafiğinin 50+ adlı dilimine tıklayın.

7. Sağ alt köşedeki çizgi grafiğine bakın. Bu grafik, gönüllü ayrılmaları gösterecek şekilde filtrelenmiştir.  

   ![50 yaş ve üzeri ayrılan çalışanlar](media/sample-human-resources/pbi_hr_sample_sepsover50.png)

   50 ve üzeri yaş grubundaki eğilime dikkat edin. Yılın ikinci yarısında 50 yaşın üstünde daha fazla çalışan gönüllü olarak ayrılmış. Bu eğilim, daha fazla veriyle daha ayrıntılı bir şekilde incelenebilecek bir alan.

8. **Gender’a göre Active Employee Count** pasta grafiği için de aynı adımları izleyebilir ve grafiği, etkin çalışanlar yerine ayrılanları gösterecek şekilde değiştirebilirsiniz. Başka herhangi bir öngörü bulup bulamayacağınızı öğrenmek için cinsiyete göre gönüllü ayrılma verilerini gözden geçirin.

9. Panoya geri dönmek için üst gezinti bölmesinden **İnsan Kaynakları Örneği** seçeneğini belirleyin. Raporda yapmış olduğunuz değişiklikleri kaydedip kaydetmemek size kalmıştır.

## <a name="bad-hires"></a>Hatalı işe alımlar
Araştırılacak son alan hatalı işe alımlardır. Hatalı işe alımlar, en fazla 60 gün çalışan kişiler olarak tanımlanır. İşe alım sürecimizi hızla tamamlayabiliyoruz, ancak iyi adayları işe alıyor muyuz?

1. **Age Group tarafından düzenlenen Bad Hires as % of Actives** pano kutucuğunu seçin. Rapor üçüncü sekme olan **Bad Hires**’ta açılır.

   ![Age Group’a göre Bad Hires as % of Actives kutucuğu](media/sample-human-resources/hr7.png)  
2. Sol taraftaki **Region** dilimleyicisinde **Northwest**’i ve **Gender’a göre Bad Hire Count** halka grafiğindeki **Male** dilimini seçin. **Bad Hires** sayfasındaki diğer grafiklere bakın. Kadınlara göre daha fazla erkeğin hatalı olarak işe alındığına ve Group A'da çok sayıda hatalı işe alımlar olduğuna dikkat edin.

   ![Northwest hatalı işe alımlar](media/sample-human-resources/pbi_hr_sample_badhirespage.png)  

3. **Gender’a göre Bad Hire Count** halka grafiğine bakıp **Region** dilimleyicisinde farklı bölgeler seçerseniz hatalı kadın işe alımlarının, hatalı erkek işe alımlarından daha fazla olduğu tek bölgenin East bölgesi olduğunu fark edersiniz.  

4. Panoya geri dönmek için üst gezinti bölmesinden panonun adını seçin.

## <a name="ask-a-question-in-the-dashboard-qa-box"></a>Panodaki Soru-Cevap kutusunda soru sorma
Panodaki [Soru-Cevap soru kutusunda](power-bi-tutorial-q-and-a.md) doğal dil kullanarak verileriniz hakkında soru sorabilirsiniz. Soru-Cevap, yazdığınız kelimeleri tanıyarak cevabı veri kümesinin neresinde bulabileceğini belirler.

1. Soru-Cevap soru kutusunu seçin. Soru-Cevap özelliği, yazmaya başlamadan önce sorunuzu oluşturmanıza yardımcı olacak öneriler görüntüler.

   ![Soru-Cevap kutusunun önerileri](media/sample-human-resources/pbi_hr_sample_qabox.png)

2. Bu önerilerden birini seçebilir veya şunu girebilirsiniz: *show age group, gender and bad hires SPLY where region is east* (Doğu bölgesinde geçen yıl aynı dönem yaş grubunu, cinsiyeti ve hatalı işe alımları göster.)  

   ![Soru-Cevap kutusunun yanıtları](media/sample-human-resources/pbi_hr_sample_qa_answer.png)

   Hatalı olarak işe alınan kadınların birçoğunun 30 yaşın altında olduğuna dikkat edin.

## <a name="next-steps-connect-to-your-data"></a>Sonraki adımlar: Verilerinize bağlanma
Değişikliklerinizi kaydetmek zorunda olmadığınızdan, bu ortamda güvenle farklı şeyler deneyebilirsiniz. Değişikliklerinizi kaydetseniz bile, dilediğiniz zaman **Veri Al**'ı seçip bu örneğin yeni bir kopyasını oluşturabilirsiniz.

Power BI panolarının, Soru-Cevap özelliğinin ve raporların örnek veriler için nasıl içgörüler sağlayacağını gösterme konusunda etkili bir tur deneyimi yaşadığınızı umuyoruz. Artık siz de kendi verilerinize bağlanarak çalışmaya başlayabilirsiniz. Power BI ile çok çeşitli veri kaynaklarına bağlanabilirsiniz. Daha fazla bilgi edinmek için bkz. [Power BI hizmeti ile çalışmaya başlama](service-get-started.md).
