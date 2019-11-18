---
title: Cortana'yı kullanarak raporları ve panoları görüntüleme - Power BI
description: Verilerinizle ilgili sorularınıza cevap almak için Power BI ile Cortana'yı kullanın. Şu anda raporlar ve panolarla birlikte çalışmaktadır.
author: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/29/2019
ms.author: maggies
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: b0109798336797eee93f738f15af71c00f818bf8
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73853674"
---
# <a name="find-and-view-your-power-bi-data-with-cortana-for-power-bi"></a>Power BI için Cortana ile Power BI verilerinizi bulma ve görüntüleme
Windows 10 cihazlarınızda Cortana'yı kullanarak işletmenizle ilgili önemli sorulara anında cevap alabilirsiniz. Cortana, Power BI ile tümleştirildiğinde Power BI panolarındaki ve raporlarındaki önemli bilgilere doğrudan ulaşabilir. İhtiyacınız olanlar Windows 10 Kasım 2015 veya sonrası sürümü, Cortana, Power BI ve en az bir veri kümesine erişimdir.

> [!IMPORTANT]
> Cortana tümleştirmesi Power BI’da kullanım dışı bırakılıyor. Cortana, 11 Haziran'dan itibaren artık pano ve raporlar için çalışmayacak.

![Cortana arama alanı](media/service-cortana-intro/power-bi-cortana-searchbox.png)

## <a name="preview-the-new-cortana-dashboard-search-experience-for-windows-10"></a>Windows 10'daki yeni Cortana *pano* arama deneyimini önizleme
Bir süredir [Cortana'yı kullanarak belirli türdeki rapor sayfalarını alma](service-cortana-answer-cards.md) özelliğini kullanıyordunuz. Eklediğimiz **yeni deneyim** sayesinde artık panoları da alma olanağı sunuyoruz. Bu yeni özelliği deneyin ve [bize Power BI Fikirleri'ne geri bildirim gönderin](https://ideas.powerbi.com/forums/265200-power-bi). İlerleyen zamanlarda *yeni deneyim* genişletilerek raporların da Cortana aramasına dahil edilmesi sağlanacak.  Yeni deneyimin başlıca avantajlarından biri, ayarlamak için herhangi bir işlem yapmanıza gerek olmamasıdır. Cortana’yı etkinleştirmenize veya Windows 10’u yapılandırmanıza gerek yoktur. Müdahale gerektirmeden çalışır.

> [!NOTE]
> Çalışmazsa yardım almak için [Sorun giderme makalesini](service-cortana-troubleshoot.md) inceleyebilirsiniz.
> 
> 

[Microsoft Azure Search Hizmeti](https://docs.microsoft.com/azure/search/) teknolojisi temel alınır. Bu arama hizmeti akıllı sıralama, hata düzeltme ve otomatik tamamlama gibi ek özellikler sunar.

İki Cortana deneyimi de birlikte kullanılabilir.

## <a name="cortana-for-power-bi-documentation"></a>Power BI için Cortana belgeleri
Power BI için Cortana’yı ayarlama ve kullanma konularında size rehberlik edecek olan dört belge.

**1. Makale** (bu makale): Cortana ve Power BI'ın birlikte nasıl çalıştığını anlama

**2. Makale**: [Power BI raporlarını arama: Cortana - Power BI - Windows tümleştirmesini etkinleştirme](service-cortana-enable.md)

**3. Makale**: [Power BI raporlarında arama yapma: özel *Cortana yanıt kartları* oluşturma](service-cortana-answer-cards.md)

**4. Makale**: [Sorun giderme](service-cortana-troubleshoot.md)

## <a name="how-cortana-and-power-bi-work-together"></a>Cortana ve Power BI birlikte nasıl çalışır?
Cortana'ya bir soru sorduğunuzda cevap aradığı yerlerden biri Power BI olabilir. Cortana, Power BI'da raporlardan (*Cortana yanıt kartı* olarak adlandırılan özel rapor türüne sahip olanlardan) ve panolardan gelen zengin veri kaynaklı cevaplar bulabilir.

Cortana bir eşleşme bulduğunda panonun veya rapor sayfasının adını doğrudan Cortana ekranınızda görüntüler. Pano veya rapor sayfasını Power BI'da açabilirsiniz. Ayrıca, rapor sayfaları etkileşimli olduğu için bunları doğrudan Cortana'da inceleyebilirsiniz.

![Cortana'da etkileşimli rapor sayfası görüntüleme](media/service-cortana-intro/power-bi-report-cortana-s.png)

### <a name="cortana-and-dashboards-the-new-experience"></a>Cortana ve Panolar (*yeni deneyim*)
Cortana, size ait olan ve sizinle paylaşılmış olan panolarda cevap bulabilir. Cortana'ya soru sorarken başlıkları, anahtar sözcükleri, içerik sahibi adlarını, çalışma alanı adlarını, uygulama adlarını ve çok daha fazlasını kullanabilirsiniz.

Cortana’nın cevap bulabilmesi için sorunuzda en az iki sözcük olması gerekir. Bu nedenle, adı tek sözcükten (Marketing) oluşan bir panoda arama yapmak için sorunuza "show", "Power BI" veya pano sahibi adını ekleyerek "show Marketing" ya da "michele hart sample" gibi bir ifadeye dönüştürün. 

Panonuzun başlığı birden fazla sözcükten oluşuyorsa Cortana ilgili panoyu yalnızca en az iki sözcüğüyle veya sözcüklerden birine ek olarak sahibinin adıyla eşleştiğinde döndürür. "Customer Profitability Sample" adlı bir pano için: 

* "show me customer" ifadesi bir Power BI panosu sonucu *döndürmez*.   
* "show me customer profitability", "customer p", "customer s", "profitability sample", "michele hart sample", "show customer profitability sample" ve "show me customer p" gibi ifadeler bir Power BI sonucu *döndürür*.
* "powerbi" sözcüğünü eklediğinizde bu, gerekli iki sözcükten biri olarak sayılır ve bu nedenle "powerbi sample" ifadesi bir Power BI sonucu *döndürür*. 
  
    ![En az 2 sözcükle Cortana araması](media/service-cortana-intro/power-bi-cortana-2-words.png)

### <a name="cortana-and-reports"></a>Cortana ve Raporlar
 Cortana, [Cortana tarafından görüntülenmek üzere tasarlanmış özel sayfalara](service-cortana-answer-cards.md) sahip olan raporlarda cevap bulabilir. Bu özel rapor sayfalarının başlığını veya içinde geçen anahtar sözcükleri kullanarak soru sorabilirsiniz.  

Raporlar için kullanılan teknoloji, [Power BI Soru-Cevap](power-bi-tutorial-q-and-a.md) hizmetinden faydalanır.

Cortana'ya bir soru sorduğunuzda Power BI, Cortana için özel olarak hazırlanmış olan rapor sayfalarını kullanarak cevap verir. Olası cevaplar Cortana tarafından Power BI'da önceden oluşturulmuş olan Cortana *yanıt kartları* kullanılarak belirlenir.  Bir cevap hakkında daha fazla bilgi edinmek için sonucu Power BI’da açın.

> [!NOTE]
> Cortana'nın soruların cevabını Power BI raporlarında arayabilmesi için [Power BI hizmetini kullanarak bu özelliği etkinleştirmeniz ve Windows'u Power BI ile iletişim kuracak şekilde ayarlamanız](service-cortana-enable.md) gerekir.  
> 
> 

## <a name="using-cortana-to-get-answers-from-power-bi"></a>Cortana'yı kullanarak Power BI'dan cevap alma
1. Cortana'dan başlayın. Cortana'yı *açmak* için kullanabileceğiniz birçok farklı yöntem vardır. Görev çubuğundaki Cortana simgesini (aşağıda gösterilmiştir) seçin, sesli komutları kullanın veya Windows mobil cihazınızdaki arama simgesine dokunun.
   
     ![](media/service-cortana-intro/power-bi-cortana-searchbox.png)
2. Cortana hazır duruma geldikten sonra sorunuzu Cortana arama çubuğuna yazın veya söyleyin. Cortana kullanılabilir sonuçları görüntüler. Soruyla eşleşen bir Power BI panosu varsa **En iyi eşleşme** veya **Power BI** bölümünde gösterilir.
   
     ![Cortana araması, Power BI panosunu bulur](media/service-cortana-intro/power-bi-cortana-search-hr.png "Cortana bir Power BI panosunu buluyor")
   
   > [!NOTE]
   > Şu anda yalnızca İngilizce dili desteklenmektedir.
   > 
   > 
3. Cortana'da açmak istediğiniz panoyu seçin.

    ![Power BI panosunu seçin](media/service-cortana-intro/power-bi-cortana-dashboard.png "Power BI panosunu seçin")

    Düzeni değiştirmek için [panonun *telefon görünümünü* düzenleyebilirsiniz](service-create-dashboard-mobile-phone-view.md). 

1. Cortana’da ayrıca panoyu Power BI hizmetinde veya Power BI mobil uygulamasında açma seçenekleri de mevcuttur. Panoyu Power BI hizmetinde açmak için **Web'de aç**'ı seçin. 
   
   ![Pano'yu Cortana'dan açma](media/service-cortana-intro/power-bi-dashboard-opens.png "Pano'yu Cortana'dan açın")   
4. Şimdi Cortana'yı kullanarak bir rapor arayalım. [Raporda Cortana yanıt kartı içeren bir sayfa olduğundan](service-cortana-answer-cards.md) emin olmamız gerekir. Bu örnekte "cortana stores" adlı bir yanıt kartı sayfasına sahip olan "Cortana-New-Stores" adlı bir raporu kullanıyoruz.  
   
     Sorunuzu Cortana arama çubuğuna yazın veya söyleyin. Cortana kullanılabilir sonuçları görüntüler. Soruyla eşleşen bir Power BI rapor sayfası varsa **En iyi eşleşme** veya **Power BI** bölümünde gösterilir. Bu örnekte yanıt kartını oluşturmak için kullanılan .pbix dosyası (ve yedeği) **Belgeler** bölümünde gösterilmektedir.
   
     ![Rapor arama](media/service-cortana-intro/power-bi-cortana-search3-m.png "rapor arama") 
5. **Cortana stores** rapor sayfasını seçerek Cortana penceresinde açılmasını sağlayabilirsiniz.
   
    ![Rapor sayfası Cortana'da açılır](media/service-cortana-intro/power-bi-report-cortana-opens.png "Rapor sayfası Cortana'da açılır")   
   
    *Yanıt kartının* bir veri kümesi sahibi tarafından oluşturulmuş olan özel bir Power BI rapor sayfası türü olduğunu unutmayın.  Daha fazla bilgi için bkz. [Cortana yanıt kartı oluşturma](service-cortana-answer-cards.md).
6. Özellikler bu kadarla sınırlı değil. Yanıt kartlarındaki görselleştirmelerle Power BI'da yaptığınız gibi etkileşim kurabilirsiniz.
   
   * Örneğin görselleştirmedeki öğelerden birini seçerek çapraz filtre uygulayabilir, yanıt kartındaki diğer görselleştirmeleri vurgulayabilirsiniz.
     
     ![](media/service-cortana-intro/power-bi-cortana-filtered-new.png)
   * İsterseniz sonuçları filtrelemek için doğal dil de kullanabilirsiniz.  Örneğin "Cortana stores for Lindseys" sorusunu yönelttiğinizde kart yalnızca Lindseys mağaza zincirine ait verileri gösterecek şekilde filtrelenir.
     
     ![Cortana'da çapraz filtreleme](media/service-cortana-intro/power-bi-cortana-filtered-2.png "Cortana'da çapraz filtreleme")
7. Keşfetmeye devam edin. Cortana penceresinin alt kısmına gidin ve **Power BI'da aç**'ı seçin.
   
     ![](media/service-cortana-intro/power-bi-cortana-open-new.png)
8. Rapor sayfası Power BI'da açılır.    
     ![Raporu Cortana'dan açma](media/service-cortana-intro/power-bi-cortana-open2.png "CoCortana yanıt kartı Cortana aramasında açılır

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme
* Cortana, [Power BI için etkinleştirilmiş](service-cortana-enable.md) olmayan Cortana kartlarına erişemez.
* Hâlâ Cortana'yı Power BI ile birlikte çalıştıramıyor musunuz?  [Cortana ile ilgili sorunları giderme](service-cortana-troubleshoot.md) makalesine bakın.
* Power BI için Cortana şu anda yalnızca İngilizce dilinde kullanılabilir.
* Power BI için Cortana yalnızca Windows mobil cihazlarında kullanılabilir.

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/).
Geri bildirimde bulunmak ister misiniz? [Power BI Fikirleri'ne geri bildirim gönderin](https://ideas.powerbi.com/forums/265200-power-bi).

## <a name="next-steps"></a>Sonraki adımlar
[Raporlar için Cortana - Power BI - Windows tümleştirmesini etkinleştirme](service-cortana-enable.md)

