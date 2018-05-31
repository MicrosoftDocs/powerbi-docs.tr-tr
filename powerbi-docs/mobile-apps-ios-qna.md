---
title: iOS uygulamalarında Soru-Cevap sanal çözümleyicisi - Power BI
description: iOS cihazınızdaki Power BI mobil uygulamasında yer alan Soru-Cevap sanal çözümleyicisini kullanarak kendi kelimelerinizle örnek verilerle ilgili sorular sorun.
services: powerbi
documentationcenter: ''
author: maggiesMSFT
manager: kfile
backup: ''
editor: ''
tags: ''
qualityfocus: no
qualitydate: ''
ms.service: powerbi
ms.component: powerbi-mobile
ms.devlang: NA
ms.topic: conceptual
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 05/05/2018
ms.author: maggies
ms.openlocfilehash: eaa8960de53b5c3e48c4bd619469beeec384b033
ms.sourcegitcommit: 493f160d04ed411ff4741c599adc63ba1f65230f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33812185"
---
# <a name="qa-virtual-analyst-in-ios-apps---power-bi"></a>iOS uygulamalarında Soru-Cevap sanal çözümleyicisi - Power BI

Verileriniz hakkında bilgi edinmenin en kolay yolu, bunlarla ilgili soruları kendi kelimelerinizle sormaktır. Bu makalede iPad, iPhone ve iPod Touch cihazınızda Microsoft Power BI mobil uygulamasındaki Soru-Cevap sanal çözümleyicisi ile örnek veriler hakkında sorular soracak ve öne çıkan içgörüleri görüntüleyeceksiniz. 

Aşağıdakiler cihazlar için geçerlidir:

| ![iPhone](media/mobile-apps-ios-qna/iphone-logo-50-px.png) | ![iPad](media/mobile-apps-ios-qna/ipad-logo-50-px.png) |
|:--- |:--- |
| iPhone'lar |iPad'ler |

Soru-Cevap sanal çözümleyicisi, Power BI hizmetinde temel alınan Soru-Cevap verilerine erişen, konuşmaya dayalı bir BI deneyimidir [(https://powerbi.com)](https://powerbi.com). Veri içgörüleri önerir ve kendi sorularınızı yazarak ya da konuşarak sorabilirsiniz.

![Top sales Soru-Cevap sanal analisti](media/mobile-apps-ios-qna/power-bi-ios-q-n-a-top-sale-intro.png)

Power BI’ya kaydolmadıysanız başlamadan önce [ücretsiz deneme için kaydolun](https://app.powerbi.com/signupredirect?pbi_source=web).

## <a name="prerequisites"></a>Önkoşullar

### <a name="install-the-power-bi-for-ios-app"></a>iOS için Power BI uygulamasını yükleme
App Store'a giderek iPad, iPhone veya iPod touch'ınıza [iOS uygulamasını indirin](http://go.microsoft.com/fwlink/?LinkId=522062 "iPhone uygulamasını indirin").

iOS için Power BI uygulamasını şu sürümler destekler:
- iOS 10 veya sonraki sürümünü çalıştıran iPad.
- iOS 10 veya sonraki sürümünü çalıştıran iPhone 5 ve üstü. 
- iOS 10 veya sonraki sürümünü çalıştıran iPod Touch.

### <a name="download-samples"></a>Örnekleri indirme
İlk adım, Power BI hizmetindeki Perakende Analizi ve Fırsat Analizi örneklerini indirmektir.

**Perakende Analizi örneğini alın**

1. Power BI hizmeti (app.powerbi.com) sayfasına gidin ve oturum açın.

2. Sol gezinti bölmesinde **Çalışma Alanları**, **Çalışma Alanım**’ı seçin.

3. Sol alt köşedeki **Veri Al** seçeneğini belirleyin.
   
    ![](media/mobile-apps-ios-qna/power-bi-get-data.png)

3. Veri Al sayfasında **Örnekler** simgesini seçin.
   
   ![](media/mobile-apps-ios-qna/power-bi-samples-icon.png)

4. **Perakende Analizi Örneği**’ni seçin.
 
    ![Perakende Analizi Örneği](media/mobile-apps-ios-qna/power-bi-rs.png)
 
8. **Bağlan**'ı seçin.  
  
   ![Perakende Analizi Örneği](media/mobile-apps-ios-qna/retail16.png)
   
5. Power BI, içerik paketini içeri aktarır ve geçerli çalışma alanınıza yeni bir pano, rapor ve veri kümesi ekler.
   
   ![Perakende Analizi Örneği](media/mobile-apps-ios-qna/power-bi-service-retail-sample.png)

**Fırsat Analizi örneğini alın**

- Perakende Analizi örneği için uyguladığınız adımları yineleyin; ancak bu kez 4. Adımda **Fırsat Analizi örneğini** seçin.

    ![Perakende Analizi Örneği](media/mobile-apps-ios-qna/power-bi-oa.png)
  
Örnekleriniz iOS cihazınızda görüntülenmeye hazırdır.

## <a name="try-asking-questions-on-your-iphone-or-ipad"></a>iPhone'unuzda veya iPad'inizde sorular sorma
1. iPhone veya iPad cihazınızda genel gezinti düğmesine ![Genel gezinti düğmesi](media/mobile-ipad-app-get-started/power-bi-iphone-global-nav-button.png) > **Çalışma Alanları** > **Çalışma Alanım**’a dokunun ve Perakende Analizi Örneği panosunu açın.

2. Sayfanın altındaki eylem menüsünde bulunan Soru-Cevap sanal analisti simgesine ![Soru-Cevap sanal analisti simgesi](media/mobile-apps-ios-qna/power-bi-ios-q-n-a-icon.png) dokunun (iPad cihazında sayfanın üstünde).
     Soru-Cevap sanal analisti, başlamanız için bazı öneriler sunar.
3. **show** yazın, açılan öneri listesinden **sales** seçeneğine ve ardından **Gönder** simgesine ![Gönder simgesi](media/mobile-apps-ios-qna/power-bi-ios-qna-send-icon.png) dokunun.

    ![Show sales](media/mobile-apps-ios-qna/power-bi-ios-q-n-a-show-sales.png)
4. Anahtar sözcüklerden **by** sözcüğünü seçin, açılan öneri listesinden **item** seçeneğine ve ardından **Gönder** simgesine ![](media/mobile-apps-ios-qna/power-bi-ios-qna-send-icon.png) dokunun.

    ![Sales by item](media/mobile-apps-ios-qna/power-bi-ios-q-n-a-sale-by-item.png)
5. Anahtar sözcüklerden **as** sözcüğünü seçin, sütun grafik simgesine ![](media/mobile-apps-ios-qna/power-bi-ios-q-n-a-column-chart-icon.png) ve ardından **Gönder** simgesine ![](media/mobile-apps-ios-qna/power-bi-ios-qna-send-icon.png) dokunun.
6. Çıkan grafiğe uzun basın ve **Genişlet** seçeneğini belirleyin.

    ![](media/mobile-apps-ios-qna/power-bi-ios-q-n-a-tap-expand-feedback.png)

    Grafik, uygulamada odak modunda açılır.

    ![](media/mobile-apps-ios-qna/power-bi-ios-q-n-a-expanded-chart.png)
7. Soru-Cevap sanal analisti sohbet penceresine geri dönmek için sol üst köşedeki oka dokunun.
8. Ardından, metni silmek ve baştan başlamak için metin kutusunun sağındaki X işaretine dokunun.
9. Yeni bir soru sorun: Anahtar sözcüklerden **top** sözcüğüne ve ardından **sale by avg $/unit ly** > **Gönder** ![](media/mobile-apps-ios-qna/power-bi-ios-qna-send-icon.png) seçeneğine dokunun.

    ![](media/mobile-apps-ios-qna/power-bi-ios-q-n-a-top-sale-2.png)
10. Anahtar sözcüklerden **by** sözcüğünü seçin, yukarıda çıkan öneri listesindeki **time** seçeneğine ve ardından **Gönder** simgesine ![](media/mobile-apps-ios-qna/power-bi-ios-qna-send-icon.png) dokunun.

     ![](media/mobile-apps-ios-qna/power-bi-ios-q-n-a-top-sale-by-time.png)
11. **as** yazın, öneri listesindeki çizgi grafik simgesini ![](media/mobile-apps-ios-qna/power-bi-ios-q-n-a-line-chart-icon.png) seçin ve **Gönder** simgesine ![](media/mobile-apps-ios-qna/power-bi-ios-qna-send-icon.png) dokunun.

    ![](media/mobile-apps-ios-qna/power-bi-ios-q-n-a-top-sale-as-line.png)

## <a name="try-saying-your-questions"></a>Sorularınızı sesli olarak sorma
Artık Power BI mobil uygulamasında yazmak yerine konuşarak verileriniz hakkında sorular sorabilirsiniz.

1. Sayfanın altındaki eylem menüsünde bulunan Soru-Cevap sanal analisti simgesine ![Soru-Cevap sanal analisti simgesi](media/mobile-apps-ios-qna/power-bi-ios-q-n-a-icon.png) dokunun (iPad cihazında sayfanın üstünde).
2. Mikrofon simgesine ![](media/mobile-apps-ios-qna/power-bi-ios-qna-mic-icon.png) dokunun.

    ![](media/mobile-apps-ios-qna/power-bi-ios-qna-mic-on.png)

1. Mikrofon simgesi etkin olduğunda konuşmaya başlayın. Örneğin, "average unit price by time" dedikten sonra **Gönder** simgesine ![](media/mobile-apps-ios-qna/power-bi-ios-qna-send-icon.png) dokunun.

    ![](media/mobile-apps-ios-qna/power-bi-ios-qna-speech-complete.png)

### <a name="questions-about-privacy-when-using-speech-to-text"></a>Konuşmayı metne dönüştürme özelliği konusunda gizlilik ile ilgili sorularınız mı var?
Apple iOS Geliştirici Kılavuzlarındaki [What's New in iOS (iOS'teki Yenilikler)](https://go.microsoft.com/fwlink/?linkid=845624) başlığı altında bulunan Speech Recognition (Konuşma Tanıma) bölümüne bakın.

## <a name="help-and-feedback"></a>Yardım ve geri bildirim
* Yardıma mı ihtiyacınız var? "Hi" veya "Help" diyerek yeni bir soruya başlama ile ilgili yardım alabilirsiniz.
* Sonuçlar ile ilgili geri bildirim sağlamak mı istiyorsunuz? Bir grafiğe veya başka bir sonuca uzun basarak gülen veya üzgün yüze dokunun.

    ![](media/mobile-apps-ios-qna/power-bi-ios-q-n-a-tap-feedback.png)

    Geri bildiriminiz anonimdir ve sorulara verilen cevapları iyileştirmemize yardımcı olur.

## <a name="enhance-your-qa-virtual-analyst-results"></a>Soru-Cevap sanal analisti sonuçlarını geliştirme
Bir veri kümesi ile ilgili olarak siz ve müşterilerinizin Soru-Cevap sanal analistini kullandığında aldığı cevapları iyileştirmek için daha hedefe yönelik sorular sorabilir veya veri kümesini geliştirebilirsiniz.

### <a name="how-to-ask-questions"></a>Soru sorma
* iOS mobil uygulamanızdaki Soru-Cevap sanal analisti veya Power BI hizmetindeki [Soru-Cevap özelliği ile soru sormaya ilişkin bu ipuçlarını](service-q-and-a-tips.md) uygulayın.

### <a name="how-to-enhance-the-dataset"></a>Veri kümesini geliştirme
* Power BI Desktop veya Power BI hizmetindeki veri kümesini, [verilerinizin Soru-Cevap özelliği ve Soru-Cevap sanal analisti ile düzgün çalışabileceği şekilde](service-prepare-data-for-q-and-a.md) geliştirin.

## <a name="next-steps"></a>Sonraki adımlar
* [Q&A in the Power BI service (Power BI hizmetindeki Soru-Cevap özelliği)](power-bi-q-and-a.md)
* Sorularınız mı var? [Power BI Topluluğu'nun Mobil uygulamalar bölümüne](https://go.microsoft.com/fwlink/?linkid=839277) göz atın
