---
title: Power BI tüketicileri için Soru-Cevap
description: Power BI Soru-Cevap doğal dil sorgularına yönelik belgelere genel bakış konusu.
author: mihart
ms.reviewer: mohammad.ali
ms.service: powerbi
ms.subservice: powerbi-consumer
ms.topic: how-to
ms.date: 07/11/2020
ms.author: mihart
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 496b47e259d4044f00fa6b7e74e9a4eec27942c8
ms.sourcegitcommit: 2131f7b075390c12659c76df94a8108226db084c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/03/2020
ms.locfileid: "87537217"
---
# <a name="qa-for-power-bi-consumers"></a>Power BI tüketicileri için Soru-Cevap

[!INCLUDE[consumer-appliesto-yyny](../includes/consumer-appliesto-yyny.md)]

[!INCLUDE [power-bi-service-new-look-include](../includes/power-bi-service-new-look-include.md)]

## <a name="what-is-qa"></a>Soru-Cevap nedir?
Bazen verilerinize ilişkin cevaplar edinmenin en hızlı yolu doğal dil kullanarak bir soru sormaktır. Örneğin, "What were total sales last year?" (Bu yılki toplam satış rakamları nedir?)

Kullanımı kolay olan doğal dil özelliklerinden yararlanarak verilerinizi araştırmak ve grafikler ile graflar biçiminde cevaplar almak için Soru-Cevap'ı kullanın. Bir arama motorundan farklı olan Soru-Cevap, yalnızca Power BI'daki verilerle ilgili sonuçlar sunar.

## <a name="which-visualization-does-qa-use"></a>Soru-Cevap hangi görselleştirmeleri kullanır?
Soru-Cevap görüntülenen verilere en uygun görselleştirmeyi seçer. Bazen temel alınan veri kümesi belirli bir tür veya kategoride tanımlanmış olur ve bu durum Soru-Cevap özelliğine ilgili verileri görüntüleme konusunda yardımcı olur. Örneğin, verilerin türü tarih olarak tanımlanmışsa çizgi grafik olarak görüntülenme olasılığı yüksektir. Kategorisi şehir olarak belirlenmiş veriler ise genelde harita olarak görüntülenir.

Sorunuza görselin türünü ekleyerek Soru-Cevap özelliğinin o türü kullanmasını sağlayabilirsiniz. Ancak Soru-Cevap özelliğinin, verileri her zaman istediğiniz görsel türünde görüntülemesinin mümkün olmayacağını unutmayın. Soru-Cevap, çalışabileceğiniz görsel türlerini listesini gösterir.

## <a name="where-can-i-use-qa"></a>Soru-Cevap özelliğini nerede kullanabilirim?
Soru-Cevap özelliğini Power BI hizmetindeki panolarda ve Power BI mobilde panonun en altında bulabilirsiniz. Panonun tasarımcısı size düzenleme izinleri vermediyse verileri araştırmak için Soru-Cevap özelliğini kullanabilirsiniz ancak Soru-Cevap ile oluşturulan görselleştirmeleri kaydedemezsiniz.

![soru kutusu](media/end-user-q-and-a/powerbi-qna.png)

Rapor *tasarımcısı* bir [Soru-Cevap görseli](../visuals/power-bi-visualization-q-and-a.md) eklediyse raporlarda Soru-Cevap da bulabilirsiniz.   

![Soru-Cevap görseli](media/end-user-q-and-a/power-bi-q-and-a-default.png)

## <a name="qa-on-dashboards"></a>Panolarda Soru-Cevap

**Power BI Soru-Cevap**, Pro veya Premium lisansla sunulur.  [Power BI mobil uygulamalarında Soru-Cevap](mobile/mobile-apps-ios-qna.md) ve [Power BI Embedded’da Soru-Cevap](../developer/embedded/qanda.md) konuları ayrı makalelerde ele alınmıştır. Şu anda **Power BI Soru-Cevap** yalnızca İngilizce sorulan doğal dil sorgularını destekler ancak Power BI yöneticiniz tarafından etkinleştirilebilecek olan bir İspanyolca önizleme sürümü vardır.


![Soru-Cevap tarafından oluşturulmuş bir ağaç haritası](media/end-user-q-and-a/power-bi-treemap.png)

Soruyu sormak yalnızca bir başlangıçtır.  Sorunuzu daraltarak veya genişleterek, dikkate değer yeni bilgiler keşfederek, ayrıntılara yoğunlaşarak ve daha geniş bir görünüm elde etmek için uzaklaştırarak verilerinizde yaptığınız yolculuğun tadını çıkarın. Elde ettiğiniz içgörülere ve yaptığınız keşiflere inanamayacaksınız.

Bu, gerçekten etkileşimli ve hızlı bir deneyim. Bellek içi bir depolama birimi sayesinde neredeyse anında cevap alırsınız.


## <a name="use-qa-on-a-dashboard-in-the-power-bi-service"></a>Power BI hizmetindeki bir panoda Soru-Cevap özelliğini kullanma
Power BI hizmetinde (app.powerbi.com) panolar, bir veya daha fazla veri kümesinden sabitlenmiş kutucuklar içerir. Bu nedenle, bu veri kümelerinde bulunan tüm verilerle ilgili sorular sorabilirsiniz. Panonun oluşturulması için hangi raporların ve veri kümelerinin kullanıldığını görmek üzere **Diğer eylemler** açılır listesinden **İlişkilileri görüntüle**'yi seçin.

![menü çubuğundaki ilgili görünüm](media/end-user-q-and-a/power-bi-q-and-a-view-related.png)

## <a name="how-do-i-start"></a>Nereden başlayabilirim?
Öncelikle içerikle ilgili bilgi edinin. Panodaki ve rapordaki görselleri gözden geçirin. Kullanabileceğiniz veri türünü ve aralığını inceleyin. 

Örnek:

* Bir görselin eksen etiketlerinde ve değerlerinde "sales", "account", "month" ve "opportunities" yazıyorsa rahatlıkla şöyle sorular sorabilirsiniz: "Which *account* has the highest *opportunity*, or show *sales* by month as a bar chart."

* Google Analytics'te web sitesi performans verileri varsa Soru-Cevap özelliğine web sayfasında geçirilen süreyi, benzersiz sayfa ziyareti sayısını ve kullanıcı etkileşim oranlarını sorabilirsiniz. Demografik verileri sorguluyorsanız yaş ve konuma göre hane geliriyle ilgili sorular sorabilirsiniz.

Verileri tanıdıktan sonra panoya dönün ve imlecinizi soru kutusuna yerleştirin. Soru-Cevap ekranı açılır.

![Soru-Cevap ekranı](media/end-user-q-and-a/power-bi-suggested.png) 

Soru-Cevap özelliği, yazmaya başlamadan önce sorunuzu oluşturmanıza yardımcı olacak önerilerin bulunduğu yeni bir ekran görüntüler. Temel alınan veri kümelerinde adları içeren ifade ve soruları görürsünüz ve veri kümesi sahibi tarafından oluşturulan *öne çıkan* soruları da görüntüleyebilirsiniz.

Bunlardan herhangi birini seçerek soru kutusuna ekleyebilir ve belirli bir yanıtı bulmak için bunlardan faydalanabilirsiniz. 

![Soru-Cevap ekranı](media/end-user-q-and-a/power-bi-result.png) 

Power BI ayrıca istemler, otomatik tamamlama ve görsel ipuçları gibi özelliklerle de soru sormanıza yardımcı olur. Power BI bu yardımı panolarda Soru-Cevap, raporlarda Soru-Cevap için ve Soru-Cevap görseli ile sağlar. Aşağıdaki [Doğal dil sorgusu yazarak bir Soru-Cevap görseli oluşturma](#create-a-qa-visual-by-typing-a-natural-language-query) bölümünde bu özellikleri ayrıntılı olarak açıklıyoruz

<!-- ![video](../visuals/media/end-user-q-and-a/qna4.gif) -->


## <a name="the-qa-visual-in-power-bi-reports"></a>Power BI raporlarında Soru-Cevap görseli

Soru-Cevap görseli, doğal dil soruları sormanıza ve görsel biçiminde yanıtlar almanıza olanak tanır. Soru-Cevap görseli de rapordaki diğer tüm görseller gibi davranır. Çapraz filtre/çapraz vurgu uygulanabilir ve aynı zamanda yer işaretleri ile yorumları destekler. 

Bir Soru-Cevap görselini üst kısımdaki soru kutusundan tanıyabilirsiniz. Buraya doğal dil kullanarak sorular girebilir veya yazabilirsiniz. Soru-Cevap görseli, verileriniz hakkında sorular sormak için tekrar tekrar kullanılabilir. Rapordan ayrıldığınızda Soru-Cevap varsayılan değerine sıfırlanır. 

![Varsayılan Soru-Cevap görselinin ekran görüntüsü](media/end-user-q-and-a/power-bi-q-and-a-default.png)


## <a name="use-qa"></a>Soru-Cevap kullanma 
Panoda Soru-Cevap veya raporda Soru-Cevap görseli kullanmak için, önerilen sorulardan birini seçin veya kendi doğal dil sorunuzu yazın. 

### <a name="create-a-qa-visual-by-using-a-suggested-question"></a>Önerilen bir soruyu kullanarak Soru-Cevap görseli oluşturma

Burada, **toplam birim sayısı en fazla olan coğrafi durumları** seçtik. Power BI kullanılacak görsel türünü en iyi şekilde seçmeye çalışır. Bu örnekte görsel türü bir haritadır.

![Soru-Cevap görseli harita](media/end-user-q-and-a/power-bi-q-and-a-suggested.png)

Ancak, doğal dil sorgunuza ekleyerek hangi görsel türünü kullanacağını Power BI’a söyleyebilirsiniz. Tüm görsel türlerinin verileriniz üzerinde işe yaramayacağını veya mantıklı olmayacağını unutmayın. Örneğin, bu veriler anlamlı bir dağılım grafiği oluşturmaz. Ancak bir kartogram gibi çalışır.

![Kartogram olarak Soru-Cevap görseli](media/end-user-q-and-a/power-bi-filled-map.png)

### <a name="create-a-qa-visual-by-typing-a-natural-language-query"></a>Doğal dil sorgusu yazarak bir Soru-Cevap görseli oluşturma


Ne tür sorular soracağınızdan veya hangi terminolojiyi kullanacağınızdan emin değilseniz **Tüm önerileri göster**’i genişletin veya rapordaki diğer görsellere bakın. Bunu yaparak veri kümesinin terim ve içeriklerini yakından tanıyabilirsiniz.

1. Doğal dil kullanarak Soru-Cevap alanına sorunuzu yazın. Sorunuzu yazarken, Power BI otomatik tamamlama, görsel ipuçları ve geri bildirim ile size yardımcı olur.

    **Otomatik tamamlama** - Sorunuzu yazarken Power BI Soru-Cevap, doğal dil ile hızlıca üretken olmanıza yardımcı olacak ilgili ve bağlamsal önerileri gösterir. Siz yazarken anında geri bildirim ve sonuçlar alırsınız. Deneyim bir arama altyapısına yazmaya benzer.

    Bu örnekte istediğimiz öneri en sondakidir. 

    ![Altı mavi çizili sözcükle Soru-Cevap](media/end-user-q-and-a/power-bi-autocomplete.png)

    **Kırmızı/Mavi alt çizgiler**- Power BI Soru-Cevap, Power BI'ın hangi sözcükleri tanıdığını hangilerini tanımadığını görmenize yardımcı olmak için sözcükleri alt çizgilerle gösterir. Düz mavi alt çizgi Power BI'ın sözcüğü tanıdığına işaret eder. Aşağıdaki örnekte, Soru-Cevap’ın **mağaza** sözcüğünü tanıdığı gösterilmektedir.

    ![Soruyu tamamlamak için açılan öneriler listesiyle Soru-Cevap](media/end-user-q-and-a/power-bi-blue.png)

    Önerilen soruların açılan listesini görüntülemek için altı mavi çizili bir sözcük seçin. 

    ![Ayrıca şunları deneyebilirsiniz önerilerini içeren açılan liste](media/end-user-q-and-a/power-bi-try.png)


    Genellikle Soru-Cevap’a bir sözcük yazdığınızda sözcük kırmızı alt çizgiyle işaretlenir. Kırmızı alt çizgi, iki olası sorundan birini gösterebilir. İlk sorun türü düşük güven kategorisine ayrılmıştır. Şüpheli veya belirsiz bir sözcük yazarsanız alanın altına kırmızı çizgi eklenir. 'Konum' sözcüğü örnek olabilir. Birden fazla alan 'Konum' sözcüğünü içerebilir. Bu nedenle sistem, hedeflediğiniz alanı seçmenizi istemek için kırmızı bir alt çizgi kullanır. Bu örnekte Power BI 'VanArsdel' için kullanmak istediğiniz alanı seçmenizi ister.
    
    ![Soru-Cevap soru kutusundaki kırmızı altı çizili terim](media/end-user-q-and-a/power-bi-q-and-a-red.png)
    
    'Alan' sözcüğünü yazmanıza rağmen eşleştiği sütunun 'bölge' olması başka bir düşük güven örneğidir. Power BI Soru-Cevap, Bing ve Office ile tümleştirme sayesinde aynı anlama gelen sözcükleri tanır. Soru-Cevap, sözcüğe kırmızı alt çizgi ekler, böylece doğrudan eşleşme olmadığını bilirsiniz

    ![Soru-Cevap, eş anlamlıları kullanarak soruyu yeniden yazar](media/end-user-q-and-a/power-bi-red.png)

    Sorunun ikinci türü, Soru-Cevap’ın sözcüğü hiç tanımamasıdır. Verilerin hiçbir yerinde mevcut olmamasına rağmen 'coğrafya' sözcüğünün kullanılması bu durumun örneği olabilir. Sözcük Türkçe sözlükte yer alır ancak Soru-Cevap bu sözcüğe kırmızı alt çizgi ekler. Power BI Soru-Cevap görselleştirme oluşturamaz ve rapor tasarımcısından terimi eklemesini istemenizi önerir.

    ![Tasarımcıdan coğrafya sözcüğünü eklemesini istemeniz önerisiyle Soru-Cevap](media/end-user-q-and-a/power-bi-geography.png)

    **Öneriler** - Harf girmeye devam ettikçe, Power BI soruyu anlamaması durumunda size bildirir ve yardımcı olmaya çalışır. Aşağıdaki örnekte Power BI "Şunu mu demek istediniz..." sorusunu sorar ve veri kümenizdeki terminolojiyi kullanarak sorunuzu farklı bir şekilde sormayı önerir. 

    ![Önerilen düzeltmeler sunan Soru-Cevap görseli](media/end-user-q-and-a/power-bi-q-and-a-did-you-mean.png)

    Power BI’ın düzeltmesini seçtikten sonra sonuçlarınız çizgi grafik olarak görüntülenir. 

    ![Çizgi grafik olarak Soru-Cevap görseli sonuçları](media/end-user-q-and-a/power-bi-q-and-a-line.png)


    Ancak, çizgi grafiği başka bir görsel türü ile değiştirebilirsiniz.  

    ![Soruya "sütun grafik olarak" eklenmiş Soru-Cevap görseli](media/end-user-q-and-a/power-bi-q-and-a-specify-type.png)



## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme

**Soru**: Panoda Soru-Cevap özelliğini göremiyorum.    
**Yanıt 1:** Soru kutusu görmüyorsanız öncelikle ayarlarınızı kontrol edin. Bunun için Power BI araç çubuğunuzun sağ üst köşesindeki dişli simgesini seçin.   
![dişli simgesi](media/end-user-q-and-a/power-bi-settings.png)

Ardından **Ayarlar** > **Panolar**'ı seçin. **Soru-Cevap arama kutusunu bu panoda göster** seçeneğinin yanında onay işareti bulunduğundan emin olun.    
![Pano için Soru-Cevap ayarları](media/end-user-q-and-a/power-bi-turn-on.png)  


**Yanıt 2**: Bazen ayarlara erişemezsiniz. Pano *tasarımcısı* veya yöneticiniz Soru-Cevap özelliğini kapattıysa, tekrar açmanın uygun olup olmadığını sorun.   

**Soru**: Bir soru yazdığımda beklediğim sonuçları alamıyorum.    
**Yanıt**: Rapor veya pano sahibiyle iletişim kurma seçeneğini belirleyin. Bunu doğrudan Soru-Cevap panosu sayfasından veya Soru-Cevap görselinden yapabilirsiniz. Ya da Power BI üst bilgisinden sahibi arayabilirsiniz.  Tasarımcının Soru-Cevap sonuçlarını geliştirmek için gerçekleştirebileceği birçok işlem vardır. Örneğin tasarımcı, veri kümesindeki sütunların adını değiştirerek daha kolay anlaşılır hale getirebilir (`CustFN` yerine `CustomerFirstName`). Tasarımcı veri kümesine hakim olduğundan yararlı sorular oluşturup bunları Soru-Cevap önerilen sorularına ekleyebilir.

![İletişim bilgilerini görüntüleme](media/end-user-q-and-a/power-bi-q-and-a-contact.png)

## <a name="privacy"></a>Gizlilik

Microsoft sorularınızı Power BI'ı geliştirmek için kullanabilir. Daha fazla bilgi edinmek için [Microsoft Gizlilik Bildirimi](https://go.microsoft.com/fwlink/?LinkId=521839)'ni gözden geçirin.

## <a name="next-steps"></a>Sonraki adımlar
Bir Soru-Cevap görselinin rapor *tasarımcısı* tarafından nasıl oluşturulup yönetildiğini öğrenmek için bkz. [Soru-Cevap görsel türü](../visuals/power-bi-visualization-q-and-a.md).
