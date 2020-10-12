---
title: iOS uygulamalarında Soru-Cevap sanal çözümleyicisi - Power BI
description: iOS cihazınızdaki Power BI mobil uygulamasında yer alan Soru-Cevap sanal çözümleyicisini kullanarak kendi kelimelerinizle örnek verilerle ilgili sorular sorun.
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: how-to
ms.date: 03/11/2020
ms.author: painbar
ms.openlocfilehash: 323ea88f3a8843dd663985abac5552be1de71584
ms.sourcegitcommit: be424c5b9659c96fc40bfbfbf04332b739063f9c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/01/2020
ms.locfileid: "91634424"
---
# <a name="qa-virtual-analyst-in-ios-apps---power-bi"></a>iOS uygulamalarında Soru-Cevap sanal çözümleyicisi - Power BI

Verileriniz hakkında bilgi edinmenin en kolay yolu, bunlarla ilgili soruları kendi kelimelerinizle sormaktır. Bu makalede iPad, iPhone ve iPod Touch cihazınızda Microsoft Power BI mobil uygulamasındaki Soru-Cevap sanal çözümleyicisi ile örnek veriler hakkında sorular soracak ve öne çıkan içgörüleri görüntüleyeceksiniz. 

Aşağıdakiler cihazlar için geçerlidir:

| ![iPhone](./media/mobile-apps-ios-qna/iphone-logo-50-px.png) | ![iPad](./media/mobile-apps-ios-qna/ipad-logo-50-px.png) |
|:--- |:--- |
| iPhone'lar |iPad'ler |

Soru-Cevap sanal çözümleyicisi, Power BI hizmetinde temel alınan Soru-Cevap verilerine erişen, konuşmaya dayalı bir BI deneyimidir [(https://powerbi.com)](https://powerbi.com). Veri içgörüleri önerir ve kendi sorularınızı yazarak ya da konuşarak sorabilirsiniz.

![Top sales Soru-Cevap sanal analisti](./media/mobile-apps-ios-qna/power-bi-ios-q-n-a-top-sale-intro.png)

Power BI’ya kaydolmadıysanız başlamadan önce [ücretsiz deneme için kaydolun](https://app.powerbi.com/signupredirect?pbi_source=web).

## <a name="prerequisites"></a>Önkoşullar

* **iOS için Power BI uygulamasını yükleme**: iPhone veya iPad'inize [iOS uygulamasını indirin](https://go.microsoft.com/fwlink/?LinkId=522062).
iOS için Power BI uygulamasını şu sürümler destekler:
    * iOS 11 veya sonraki sürümünü çalıştıran iPad.
    * iOS 11 veya sonraki sürümünü çalıştıran iPhone 5 ve üstü.
* **Perakende Analizi ve Fırsat Analizi Örneklerini indirme**: Bu hızlı başlangıcın ilk adımı, Power BI hizmetinde Perakende Analizi ve Fırsat Analizi örneklerini indirmektir. Çalışmaya başlamak için Power BI hesabınızda [Örneği indirmeyi öğrenin](./mobile-apps-download-samples.md). Perakende Analizi Örneğini ve Fırsat Analizi Örneğini seçtiğinizden emin olun.

Önkoşulları tamamladıktan sonra Soru-Cevap sanal analistini denemeye hazırsınız.

## <a name="try-asking-questions-on-your-iphone-or-ipad"></a>iPhone'unuzda veya iPad'inizde sorular sorma
1. iPhone veya iPad'inizdeki alt gezinti çubuğunda Çalışma Alanları düğmesine ![çalışma alanları düğmesi](./media/mobile-apps-ios-qna/power-bi-iphone-workspaces-button.png)dokunun, Çalışma Alanım'a gidin ve Perakende Analizi Örneği panosunu açın.

2. Sayfanın altındaki eylem menüsünde bulunan Soru-Cevap sanal analisti simgesine ![Soru-Cevap sanal analisti simgesi](././media/mobile-apps-ios-qna/power-bi-ios-q-n-a-icon.png) dokunun (iPad cihazında sayfanın üstünde).
     Soru-Cevap sanal analisti, başlamanız için bazı öneriler sunar.
3. **show** yazın, açılan öneri listesinden **sales** seçeneğine ve ardından **Gönder** simgesine ![Gönder simgesi](./media/mobile-apps-ios-qna/power-bi-ios-qna-send-icon.png) dokunun.

    ![Show sales](./media/mobile-apps-ios-qna/power-bi-ios-q-n-a-show-sales.png)
4. Anahtar sözcüklerden **by** sözcüğünü seçin, açılan öneri listesinden **item** seçeneğine ve ardından **Gönder**’e ![Gönder simgesi](./media/mobile-apps-ios-qna/power-bi-ios-qna-send-icon.png) dokunun.

    ![Sales by item](./media/mobile-apps-ios-qna/power-bi-ios-q-n-a-sale-by-item.png)
5. Anahtar sözcüklerden **as** sözcüğünü seçin, sütun grafik simgesine :::image type="icon" source="./media/mobile-apps-ios-qna/power-bi-ios-q-n-a-column-chart-icon.png" border="false"::: ve ardından **Gönder**’e ![Gönder simgesi](./media/mobile-apps-ios-qna/power-bi-ios-qna-send-icon.png) dokunun.
6. Çıkan grafiğe uzun basın ve **Genişlet** seçeneğini belirleyin.

    ![Genişlet seçeneğine bakan işaretçiyi gösteren sütun grafiğinin ekran görüntüsü.](media/mobile-apps-ios-qna/power-bi-ios-q-n-a-tap-expand-feedback.png)

    Grafik, uygulamada odak modunda açılır.

    ![Grafiğin odak modunu gösteren sütun grafiğinin ekran görüntüsü.](media/mobile-apps-ios-qna/power-bi-ios-q-n-a-expanded-chart.png)
7. Soru-Cevap sanal analisti sohbet penceresine geri dönmek için sol üst köşedeki oka dokunun.
8. Ardından, metni silmek ve baştan başlamak için metin kutusunun sağındaki X işaretine dokunun.
9. Yeni bir soru sorun: Anahtar sözcüklerden **top** sözcüğüne ve ardından **sale by avg $/unit ly** > **Gönder**’e ![Gönder simgesi](./media/mobile-apps-ios-qna/power-bi-ios-qna-send-icon.png) dokunun.

    ![Birim başına ortalama miktara göre en yüksek satışı gösteren bir sorunun ekran görüntüsü.](media/mobile-apps-ios-qna/power-bi-ios-q-n-a-top-sale-2.png)
10. Anahtar sözcüklerden **by** sözcüğünü seçin, yukarıda çıkan öneri listesindeki **time** seçeneğine ve ardından **Gönder**’e ![Gönder simgesi](./media/mobile-apps-ios-qna/power-bi-ios-qna-send-icon.png) dokunun.

     ![Zaman içinde birim başına ortalama miktara göre en yüksek satışı gösteren bir grafiğin ekran görüntüsü.](media/mobile-apps-ios-qna/power-bi-ios-q-n-a-top-sale-by-time.png)
11. **as** yazın, öneri listesindeki çizgi grafik simgesini :::image type="icon" source="./media/mobile-apps-ios-qna/power-bi-ios-q-n-a-line-chart-icon.png" border="false"::: seçin ve **Gönder**'e ![Gönder simgesi](./media/mobile-apps-ios-qna/power-bi-ios-qna-send-icon.png) dokunun.

    ![Sütundan çizgi grafiğine bakan bir işaretçiyi gösteren sütun ve çizgi grafiğinin ekran görüntüsü](media/mobile-apps-ios-qna/power-bi-ios-q-n-a-top-sale-as-line.png)

## <a name="try-saying-your-questions"></a>Sorularınızı sesli olarak sorma
Artık Power BI mobil uygulamasında yazmak yerine konuşarak verileriniz hakkında sorular sorabilirsiniz.

1. Sayfanın altındaki eylem menüsünde bulunan Soru-Cevap sanal analisti simgesine ![Soru-Cevap sanal analisti simgesi](././media/mobile-apps-ios-qna/power-bi-ios-q-n-a-icon.png) dokunun (iPad cihazında sayfanın üstünde).
2. Mikrofon simgesine dokunun ![Mikrofon simgesi](media/mobile-apps-ios-qna/power-bi-ios-qna-mic-icon.png).

    ![Mikrofonun etkin olduğunu gösteren bir sorunun ekran görüntüsü.](media/mobile-apps-ios-qna/power-bi-ios-qna-mic-on.png)

1. Mikrofon simgesi etkin olduğunda konuşmaya başlayın. Örneğin, "average unit price by time" dedikten sonra **Gönder**’e ![Gönder simgesi](./media/mobile-apps-ios-qna/power-bi-ios-qna-send-icon.png) dokunun.

    ![Konuşmanın tamamlandığını gösteren bir sorunun ekran görüntüsü.](media/mobile-apps-ios-qna/power-bi-ios-qna-speech-complete.png)

### <a name="questions-about-privacy-when-using-speech-to-text"></a>Konuşmayı metne dönüştürme özelliği konusunda gizlilik ile ilgili sorularınız mı var?
Apple iOS Geliştirici Kılavuzlarındaki [What's New in iOS (iOS'teki Yenilikler)](https://go.microsoft.com/fwlink/?linkid=845624) başlığı altında bulunan Speech Recognition (Konuşma Tanıma) bölümüne bakın.

## <a name="help-and-feedback"></a>Yardım ve geri bildirim
* Yardıma mı ihtiyacınız var? "Hi" veya "Help" diyerek yeni bir soruya başlama ile ilgili yardım alabilirsiniz.
* Sonuçlar ile ilgili geri bildirim sağlamak mı istiyorsunuz? Bir grafiğe veya başka bir sonuca uzun basarak gülen veya üzgün yüze dokunun.

    ![İşaretçiden gülen yüze geri bildirim gösteren bir sütun grafiğinin ekran görüntüsü.](media/mobile-apps-ios-qna/power-bi-ios-q-n-a-tap-feedback.png)

    Geri bildiriminiz anonimdir ve sorulara verilen cevapları iyileştirmemize yardımcı olur.

## <a name="enhance-your-qa-virtual-analyst-results"></a>Soru-Cevap sanal analisti sonuçlarını geliştirme
Bir veri kümesi ile ilgili olarak siz ve müşterilerinizin Soru-Cevap sanal analistini kullandığında aldığı cevapları iyileştirmek için daha hedefe yönelik sorular sorabilir veya veri kümesini geliştirebilirsiniz.

### <a name="how-to-ask-questions"></a>Soru sorma
* iOS mobil uygulamanızdaki Soru-Cevap sanal analisti veya Power BI hizmetindeki [Soru-Cevap özelliği ile soru sormaya ilişkin bu ipuçlarını](../end-user-q-and-a-tips.md) uygulayın.

### <a name="how-to-enhance-the-dataset"></a>Veri kümesini geliştirme
* Power BI Desktop veya Power BI hizmetindeki veri kümesini, [verilerinizin Soru-Cevap özelliği ve Soru-Cevap sanal analisti ile düzgün çalışabileceği şekilde](../../create-reports/service-prepare-data-for-q-and-a.md) geliştirin.

## <a name="next-steps"></a>Sonraki adımlar
* [Q&A in the Power BI service (Power BI hizmetindeki Soru-Cevap özelliği)](../end-user-q-and-a.md)
* Sorularınız mı var? [Power BI Topluluğu'nun Mobil uygulamalar bölümüne](https://go.microsoft.com/fwlink/?linkid=839277) göz atın
