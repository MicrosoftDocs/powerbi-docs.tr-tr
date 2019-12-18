---
title: Power BI Soru-Cevap görselini kullanma
description: Power BI Soru-Cevap görselini ayarlama
author: mihart
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 11/19/2019
ms.author: mohaali
ms.openlocfilehash: 9805b98df7f606e61412ca9dee7dc0467a1649a3
ms.sourcegitcommit: 90bd747b7c460d17b74cd386d3f5714234b1f6c9
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74791802"
---
# <a name="introduction-to-power-bi-qa-visual"></a>Power BI Soru-Cevap görseline giriş

[!INCLUDE [power-bi-service-new-look-include](../includes/power-bi-service-new-look-include.md)]

## <a name="what-is-the-qa-visual"></a>Soru-Cevap Görseli nedir?

Soru-Cevap görseli, kullanıcıların doğal dil soruları sormasına ve görsel biçiminde yanıtlar almasına olanak tanır. 

![Soru-Cevap görseli kılavuzu](../natural-language/media/qna-visual-walkthrough.gif)

[!INCLUDE [power-bi-visuals-desktop-banner](../includes/power-bi-visuals-desktop-banner.md)]

Soru-Cevap görseli hem *tüketicilerin* verilerine hızlıca yanıt almasını hem de *tasarımcıların* bir raporda herhangi bir yere çift tıklayıp çalışmaya başlamak için doğal dili kullanarak görseller oluşturmasını sağlayan bir araç olarak kullanılabilir. Soru-Cevap görseli de diğer tüm görseller gibi davrandığı için çapraz filtre/çapraz vurgu uygulanabilir ve aynı zamanda yer işaretlerini destekler. Soru-Cevap görseli aynı zamanda Power BI’da kullanılan temaları ve diğer varsayılan biçimlendirme seçeneklerini destekler.

Soru-Cevap görseli dört temel bileşenden oluşur;

- Soru kutusu. Burada kullanıcılar sorularını yazar ve soruları tamamlamaya yardımcı öneriler gösterilir.
- Önerilen soruların önceden doldurulmuş bir listesi.
- Soru-Cevap görselini standart bir görsele dönüştürme simgesi. 
- Tasarımcıların temel alınan doğal dil altyapısını yapılandırmasına olanak tanıyan Soru-Cevap aracını açma simgesi.

## <a name="prerequisites"></a>Önkoşullar

1. Bu eğitimde [Satış ve Pazarlama örneği PBIX dosyası](https://download.microsoft.com/download/9/7/6/9767913A-29DB-40CF-8944-9AC2BC940C53/Sales%20and%20Marketing%20Sample%20PBIX.pbix) kullanılmaktadır. 

1. Power BI Desktop menü çubuğunun sol üst kısmından **Dosya** > **Aç**’ı seçin
   
2. **Satış ve Pazarlama örneği PBIX dosyası** kopyanızı bulun

1. Dosyayı rapor görünümünde açma ![Rapor görünümü simgesinin ekran görüntüsü.](media/power-bi-visualization-kpi/power-bi-report-view.png)geçin.

1. Seç ![Sarı sekmenin ekran görüntüsü.](media/power-bi-visualization-kpi/power-bi-yellow-tab.png) yeni bir sayfa ekleyin.


Soru-Cevap görseli oluştururken bir hata görürseniz, veri kaynağı yapılandırmasının desteklenip desteklenmediğini öğrenmek için [sınırlamalar](../natural-language/q-and-a-limitations.md) bölümüne göz atın.

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

Ne tür sorular soracağınızdan veya hangi terminolojiyi kullanacağınızdan emin değilseniz **Tüm önerileri göster**’i genişletin veya tuvalin sağ tarafında bulunabilecek Alanlar bölmesine bakın. Bunu yaparak Satış ve Pazarlama veri kümesinin terim ve içeriklerini yakından tanıyabilirsiniz.

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
Renk körlerine uygun sütun grafik görselimizi biraz biçimlendirdik: bir başlık ve kenarlık ekledik. Şimdi, raporumuzda standart bir görsele dönüştürmeye ve ayrıca bir panoya sabitlemeye hazırız.

**Bu Soru-Cevap sonucunu standart bir görsele dönüştürmek** için simgeyi ![dişli simgesi](media/power-bi-visualization-q-and-a/power-bi-convert-icon.png) seçin.

![Standart görsel simgesini işaret eden okla Soru-Cevap görseli](media/power-bi-visualization-q-and-a/power-bi-visual-convert.png)

Bu görsel artık bir Soru-Cevap görseli değil, standart sütun grafiğidir. Bir panoya sabitlenebilir. Raporda, bu görsel diğer standart görsellerle aynı şekilde davranır. Görselleştirmeler bölmesinde Soru-Cevap görseli simgesinin yerine bir Sütun grafiği simgesinin gösterildiğine dikkat edin.

***Power BI Hizmeti***’ni kullanıyorsanız, raptiye simgesini seçerek görseli bir panoya sabitleyebilirsiniz. 


![Raptiye simgesi vurgulanmış Power BI hizmeti](media/power-bi-visualization-q-and-a/power-bi-pin.png)


## <a name="advanced-features-of-the-qa-visual"></a>Soru-Cevap görselinin gelişmiş özellikleri
Dişli simgesi seçildiğinde Soru-Cevap görseli Araçlar bölmesi açılır. 

![Araçlar simgesi seçilmiş Soru-Cevap görseli](media/power-bi-visualization-q-and-a/power-bi-q-and-a-tooling.png)

Soru-Cevap’a tanımadığı terimleri öğretmek, bu terimleri yönetmek ve bu veri kümesi ile rapor için önerilen soruları yönetmek üzere Araçlar bölmesini kullanın. Araç bölmesinde bu Soru-Cevap görseli kullanılarak sorulan soruları inceleyebilir ve kullanıcılar tarafından işaretlenen soruları görebilirsiniz. Daha fazla bilgi için bkz. [Soru-Cevap Araçları](../natural-language/q-and-a-tooling-intro.md).

![Soru-Cevap Araçlar bölmesi](media/power-bi-visualization-q-and-a/power-bi-q-and-a-tooling-pane.png)

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme
Soru-Cevap görseli, veri kümenizin alanlarındaki tanınmayan yaygın sözcükleri eşleştirmek için Office ve Bing ile tümleşiktir.  

## <a name="next-steps"></a>Sonraki adımlar

Doğal dili tümleştirebilmeniz için kullanabileceğiniz çeşitli yollar vardır. Daha fazla bilgi için aşağıdaki makaleleri inceleyin:

* [Soru-Cevap Araçları](../natural-language/q-and-a-tooling-intro.md)
* [Soru-Cevap En İyi Yöntemler](../natural-language/q-and-a-best-practices.md)