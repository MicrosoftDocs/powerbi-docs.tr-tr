---
title: Power BI'da Soru-Cevap görseli oluşturma
description: Power BI Desktop'ta veya Power BI hizmetinde Power BI Soru-Cevap görseli oluşturma ve biçimlendirme adımları.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: rien
ms.service: powerbi
ms.subservice: pbi-visuals
ms.topic: how-to
ms.date: 01/05/2021
ms.openlocfilehash: 1cf80593458c12a1bee07ed40202e3613fdcb5e9
ms.sourcegitcommit: c700e78dfedc34f5a74b23bbefdaef77e2a87f8a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97961374"
---
# <a name="create-a-qa-visual-in-power-bi"></a>Power BI'da Soru-Cevap görseli oluşturma

[!INCLUDE[consumer-appliesto-nyyn](../includes/consumer-appliesto-nyyn.md)]    

Soru-Cevap görseli, kullanıcıların doğal dil soruları sormasına ve görsel biçiminde yanıtlar almasına olanak tanır. *Tüketiciler* bu görseli kullanarak verileriyle ilgili sorularına hızlı yanıtlar alabilir. *Tasarımcılar* ise bu sayede hızlıca görseller oluşturabilir. Rapor tasarımcısıysanız bu makale tam size göre. Başlamak için raporun herhangi bir yerine çift tıklayıp doğal dil kullanabilirsiniz. Bu makalede bir Soru-Cevap görseli oluşturacak, biçimlendirecek ve özelleştireceksiniz. Bu görsel, Power BI’da kullanılan temaları ve diğer varsayılan biçimlendirme seçeneklerini destekler. Oluşturulan görsel diğer görseller gibi kullanılabilir ve çapraz filtreleme, çapraz vurgulama ve yer işaret desteği sunar. 

Power BI'da Soru-Cevap hakkında daha fazla bilgi mi arıyorsunuz? [Soru-Cevap görseline giriş](../natural-language/q-and-a-intro.md) sayfasını inceleyin. 

![Soru-Cevap görseli kılavuzu](../natural-language/media/qna-visual-walkthrough.gif)

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

Soru-Cevap görseli dört temel bileşenden oluşur:

- Soru kutusu. Burada kullanıcılar sorularını yazar ve soruları tamamlamaya yardımcı öneriler gösterilir.
- Önerilen soruların önceden doldurulmuş bir listesi.
- Soru-Cevap görselini standart bir görsele dönüştürme simgesi. 
- Tasarımcıların temel alınan doğal dil altyapısını yapılandırmasına olanak tanıyan Soru-Cevap aracını açma simgesi.

## <a name="prerequisites"></a>Ön koşullar

1. Adımları takip etmek için [Satış ve Pazarlama örneği PBIX dosyasını](https://download.microsoft.com/download/9/7/6/9767913A-29DB-40CF-8944-9AC2BC940C53/Sales%20and%20Marketing%20Sample%20PBIX.pbix) indirin.

1. Power BI Desktop'ın sol üst tarafından **Dosya** > **Aç**’ı seçin.
   
2. **Satış ve Pazarlama örneği PBIX dosyası** kopyanızı bulun.

1. Dosyayı rapor görünümünde açma ![Rapor görünümü simgesinin ekran görüntüsü.](media/power-bi-visualization-kpi/power-bi-report-view.png).

1. Artı işaretini seçerek ![Sarı sekmenin ekran görüntüsü.](media/power-bi-visualization-kpi/power-bi-yellow-tab.png) yeni bir sayfa ekleyin.

Soru-Cevap görseli oluştururken bir hata görürseniz, veri kaynağı yapılandırmasının desteklenip desteklenmediğini öğrenmek için [Soru-Cevap sınırlamaları](../natural-language/q-and-a-limitations.md) makalesine göz atın.    

> [!NOTE]
> Raporunuzu bir Power BI iş arkadaşınızla paylaşmak için her ikinizin de bireysel Power BI Pro lisanslarınızın olması veya raporu Premium kapasite çalışma alanına kaydetmeniz gerekir. Bkz. [Raporları paylaşma](../collaborate-share/service-share-dashboards.md).

## <a name="create-a-qa-visual-using-a-suggested-question"></a>Önerilen bir soruyu kullanarak Soru-Cevap görseli oluşturma
Bu alıştırmada, Soru-Cevap görselimizi oluşturmak için önerilen sorulardan birini seçeceğiz. 

1. Boş bir rapor sayfasında başlayın ve Görselleştirmeler bölmesinden Soru-Cevap görseli simgesini seçin.

    ![Soru-Cevap görseli simgesi çizgi içine alınmış Görselleştirme bölmesi](media/power-bi-visualization-q-and-a/power-bi-icon.png)

2. Görseli yeniden boyutlandırmak için kenarlığı sürükleyin.

    ![Rapor tuvali üzerinde Soru-Cevap görseli](media/power-bi-visualization-q-and-a/power-bi-qna.png)

3. Görseli oluşturmak için, önerilen sorulardan birini seçin veya soru kutusuna yazmaya başlayın. Bu örnekte, **gelir toplamı en yüksek coğrafi bölgeler**’i seçtik. Power BI kullanılacak görsel türünü en iyi şekilde seçmeye çalışır. Bu örnekte görsel türü bir haritadır.

    ![Soru-Cevap görseli harita](media/power-bi-visualization-q-and-a/power-bi-map.png)

    Ancak, doğal dil sorgunuza ekleyerek hangi görsel türünü kullanacağını Power BI’a söyleyebilirsiniz. Tüm görsel türlerinin verileriniz üzerinde işe yaramayacağını veya mantıklı olmayacağını unutmayın. Örneğin, bu veriler anlamlı bir dağılım grafiği oluşturmaz. Ancak bir kartogram gibi çalışır.

    ![Kartogram olarak Soru-Cevap görseli](media/power-bi-visualization-q-and-a/power-bi-specify-map.png)

## <a name="create-a-qa-visual-using-a-natural-language-query"></a>Doğal dil sorgusu kullanarak Soru-Cevap görseli oluşturma
Yukarıdaki örnekte, Soru-Cevap görselimizi oluşturmak için önerilen sorulardan birini seçtik.  Bu alıştırmada kendi sorumuzu yazacağız. Sorumuzu yazarken, Power BI otomatik tamamlama, öneriler ve geri bildirim ile bize yardımcı olur.

Ne tür sorular soracağınızdan veya hangi terminolojiyi kullanacağınızdan emin değilseniz **Tüm önerileri göster**’i genişletin veya tuvalin sağ tarafındaki Alanlar bölmesine bakın. Alanlar bölmesi, Satış ve Pazarlama veri kümesinin terim ve içerikleri hakkında bilgi sahibi olmanızı sağlar.

![Tüm önerileri göster ve Alanlar bölmesi vurgulanmış tuval](media/power-bi-visualization-q-and-a/power-bi-terminology.png)


1. Soru-Cevap alanına bir soru yazın. Power BI tanımadığı sözcüklere kırmızı bir alt çizgi ekler. Mümkün olduğunda, Power BI tanınmayan sözcükleri tanımlamaya yardımcı olur.  Aşağıdaki ilk örnekte, önerilerden birini seçmeniz yeterlidir.  

    ![Soru-Cevap soru kutusuna soru yazma](media/power-bi-visualization-q-and-a/power-bi-red-suggest.png)

2. Harf girmeye devam ettikçe, Power BI soruyu anlamaması durumunda bize bildirir ve yardımcı olmaya çalışır. Aşağıdaki örnekte Power BI "Şunu mu demek istediniz..." sorusunu sorar ve veri kümemizdeki terminolojiyi kullanarak sorumuzu farklı bir şekilde sormayı önerir. 

    ![Soru-Cevap görseli görüntüleme önerileri](media/power-bi-visualization-q-and-a/power-bi-define.png)

5. Power BI’ın yardımı sayesinde tüm tanınabilir terimlerle soru sorabildik. Power BI sonuçları çizgi grafik olarak gösterir. 

    ![Soru-Cevap görsel sonuçları](media/power-bi-visualization-q-and-a/power-bi-type.png)


6. Görseli bir sütun grafik olarak değiştirelim. 

    ![Soruya "sütun grafik olarak" eklenmiş Soru-Cevap görseli](media/power-bi-visualization-q-and-a/power-bi-specify-visual.png)

7.  Rapor sayfasına daha fazla görsel ekleyin ve Soru-Cevap görselinin sayfadaki diğer görsellerle nasıl etkileşim kurduğuna bakın. Bu örnekte Soru-Cevap görseli çizgi grafiği ve haritayı çapraz filtrelemiş ve çubuk grafiği çapraz vurgulamıştır.

    ![Tek çubuğun seçili olduğu Soru-Cevap görseli ve rapor sayfasındaki diğer üç görsel üzerindeki etkisi](media/power-bi-visualization-q-and-a/power-bi-filters.png)

## <a name="format-and-customize-the-qa-visual"></a>Soru-Cevap görselini biçimlendirme ve özelleştirme
Soru-Cevap görseli, biçimlendirme bölmesi kullanılarak ve bir tema uygulanarak özelleştirilebilir. 

### <a name="apply-a-theme"></a>Tema uygulama
Bir tema seçtiğinizde, bu tema tüm rapor sayfasına uygulanır. Aralarından seçim yapabileceğiniz birçok tema vardır; bu yüzden istediğiniz görünümü yapana kadar deneyin. 

1. Menü çubuğundan **Giriş** sekmesini ve **Tema değiştir**’i seçin. 

    ![Tema değiştir seçiliyken masaüstü](media/power-bi-visualization-q-and-a/power-bi-themes.png)

    
    
2. Bu örnekte **Daha fazla tema** > **Renk körlerine uygun**’u seçtik.

    ![Renk körü teması uygulanmış Soru-Cevap görseli](media/power-bi-visualization-q-and-a/power-bi-color-blind.png)

### <a name="format-the-qa-visual"></a>Soru-Cevap görselini biçimlendirme
Soru-Cevap görselini, soru alanını ve önerilerin görüntülenme şeklini biçimlendirin. Bir başlığın arka planından, tanınmayan sözcüklerin üzerine gelme rengine kadar her şeyi değiştirebilirsiniz. Burada soru kutusuna gri bir arka plan ekledik ve alt çizgileri sarı ve yeşil olarak değiştirdik. Başlık ortalandı ve sarı bir arka plan uygulandı. 

![Biçimlendirme sonuçlarımızı gösteren Soru-Cevap görseli](media/power-bi-visualization-q-and-a/power-bi-q-and-a-format.png)

## <a name="convert-your-qa-visual-into-a-standard-visual"></a>Soru-Cevap görselini standart bir görsele dönüştürme
Renk körlerine uygun sütun grafik görselimizi biraz biçimlendirdik: Bir başlık ve kenarlık ekledik. Şimdi, raporumuzda standart bir görsele dönüştürmeye ve ayrıca bir panoya sabitlemeye hazırız.

**Bu Soru-Cevap sonucunu standart bir görsele dönüştürmek** için simgeyi ![dişli simgesi](media/power-bi-visualization-q-and-a/power-bi-convert-icon.png) seçin.

![Standart görsel simgesini işaret eden okla Soru-Cevap görseli](media/power-bi-visualization-q-and-a/power-bi-visual-convert.png)

Bu görsel artık bir Soru-Cevap görseli değil, standart sütun grafiğidir. Bir panoya sabitlenebilir. Raporda, bu görsel diğer standart görsellerle aynı şekilde davranır. Görselleştirmeler bölmesinde Soru-Cevap görseli simgesinin yerine bir Sütun grafiği simgesinin gösterildiğine dikkat edin.

**_Power BI hizmetini_* _ kullanıyorsanız, raptiye simgesini seçerek görseli bir panoya sabitleyebilirsiniz. 


![Raptiye simgesi vurgulanmış Power BI hizmeti](media/power-bi-visualization-q-and-a/power-bi-pin.png)


## <a name="advanced-features-of-the-qa-visual"></a>Soru-Cevap görselinin gelişmiş özellikleri
Dişli simgesi seçildiğinde Soru-Cevap görseli Araçlar bölmesi açılır. 

![Araçlar simgesi seçilmiş Soru-Cevap görseli](media/power-bi-visualization-q-and-a/power-bi-q-and-a-tooling.png)

Soru-Cevap’a tanımadığı terimleri öğretmek, bu terimleri yönetmek ve bu veri kümesi ile rapor için önerilen soruları yönetmek üzere Araçlar bölmesini kullanın. Araç bölmesinde kullanıcıların bu Soru-Cevap görselini kullanarak sorduğu soruları inceleyebilir ve kullanıcılar tarafından işaretlenen soruları görebilirsiniz. Daha fazla bilgi için bkz. [Power BI Soru-Cevap eğitimi için Soru-Cevap araçlarına giriş](../natural-language/q-and-a-tooling-intro.md).

![Soru-Cevap Araçlar bölmesi](media/power-bi-visualization-q-and-a/power-bi-q-and-a-tooling-pane.png)

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme
Soru-Cevap görseli, veri kümenizin alanlarındaki tanınmayan yaygın sözcükleri eşleştirmek için Office ve Bing ile tümleşiktir.  

## <a name="next-steps"></a>Sonraki adımlar

Doğal dili tümleştirmek için kullanabileceğiniz birçok farklı yol vardır. Daha fazla bilgi için aşağıdaki makaleleri inceleyin:

_ [Soru-Cevap Araçları](../natural-language/q-and-a-tooling-intro.md)
* [Soru-Cevap En İyi Yöntemler](../natural-language/q-and-a-best-practices.md)
