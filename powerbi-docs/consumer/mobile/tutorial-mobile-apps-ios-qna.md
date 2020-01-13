---
title: 'Öğretici: iOS uygulamalarında Soru-Cevap sanal analisti ile soru sorma'
description: Bu öğreticide, iOS cihazınızdaki Power BI mobil uygulamasında yer alan Soru-Cevap sanal analistini kullanarak kendi kelimelerinizle örnek verilerle ilgili sorular soracaksınız.
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: tutorial
ms.date: 11/26/2019
ms.author: painbar
ms.openlocfilehash: f946c3b10f9d4922c227dd92a748af91266c040e
ms.sourcegitcommit: 6272c4a0f267708ca7d38a45774f3bedd680f2d6
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/06/2020
ms.locfileid: "75221821"
---
# <a name="tutorial-ask-questions-about-your-data-with-the-qa-virtual-analyst-in-the-power-bi-ios-apps"></a>Öğretici: Power BI iOS uygulamalarındaki Soru-Cevap sanal analistini kullanarak verileriniz hakkında sorular sorma

Verileriniz hakkında bilgi edinmenin en kolay yolu, bunlarla ilgili soruları kendi kelimelerinizle sormaktır. Bu öğreticide iPad veya iPhone'unuzda Microsoft Power BI mobil uygulamasındaki Soru-Cevap sanal çözümleyicisi ile örnek veriler hakkında sorular soracak ve öne çıkan içgörüleri görüntüleyeceksiniz. 

Aşağıdakiler cihazlar için geçerlidir:

| ![iPhone](./media/tutorial-mobile-apps-ios-qna/iphone-logo-50-px.png) | ![iPad](./media/tutorial-mobile-apps-ios-qna/ipad-logo-50-px.png) |
|:--- |:--- |
| iPhone'lar |iPad'ler |

Soru-Cevap sanal analisti, [Power BI hizmetinde](https://powerbi.com) temel alınan Soru-Cevap verilerine erişen, konuşmaya dayalı bir BI deneyimidir. Veri içgörüleri önerir ve kendi sorularınızı yazarak ya da konuşarak sorabilirsiniz.

![Top sales Soru-Cevap sanal analisti](./media/tutorial-mobile-apps-ios-qna/power-bi-ios-q-n-a-top-sale-intro.png)

Bu öğreticide şunları yapacaksınız:

> [!div class="checklist"]
> * iOS için Power BI mobil uygulamasını yükleme
> * Bir Power BI örnek panosu ve raporu indirme
> * Mobil uygulamanın öne çıkan hangi içgörüleri önerdiğini görme

## <a name="prerequisites"></a>Önkoşullar

* **Power BI'a kaydolma**: Power BI’ya kaydolmadıysanız başlamadan önce [ücretsiz deneme için kaydolun](https://app.powerbi.com/signupredirect?pbi_source=web).
* **iOS için Power BI uygulamasını yükleme**: Apple App Store'dan iPad, iPhone veya iPod Touch'ınıza [iOS uygulamasını indirin](https://apps.apple.com/app/microsoft-power-bi/id929738808). iOS için Power BI uygulamasını şu sürümler destekler:
  * iOS 11 veya sonraki sürümünü çalıştıran iPad.
  * iOS 11 veya sonraki sürümünü çalıştıran iPhone 5 ve üstü. 
  * iOS 11 veya sonraki sürümünü çalıştıran iPod Touch.
* **Örnek verileri indirme**: İlk adım, **Fırsat Analizi Örneği**'ni Power BI hizmetine indirmektir. Bunun nasıl yapılacağını gösteren yönergeler için bkz. [Örnekleri Power BI hizmetinde Çalışma alanım'a indirme](./mobile-apps-download-samples.md).


Önkoşulları tamamladıktan ve örnek verileri indirdikten sonra, örnekleri iOS cihazınızda görüntülemeye hazırsınız.

## <a name="try-featured-insights"></a>Öne çıkan öngörüleri görüntüleme
1. iPhone veya iPad cihazınızda Power BI uygulamasını açın ve tarayıcıdaki Power BI hizmetinde kullandığınız Power BI hesabı kimlik bilgilerinizle oturum açın.

2. Giriş sayfası gezinti çubuğunda **Çalışma Alanları** simgesine dokunun.

    ![Çalışma Alanım'ı açma](./media/tutorial-mobile-apps-ios-qna/power-bi-qna-open-myworkspace.png)

3. Çalışma Alanları sayfası açıldığında **Çalışma Alanlarım**'a dokunun ve ardından **Fırsat Analizi Örneği** panosuna dokunarak panoyu açın.


3. Fırsat Analizi Örneği panosunda, eylem menüsündeki Soru-Cevap sanal analisti simgesine dokunun.

    ![Soru-Cevap sanal analistini açma](./media/tutorial-mobile-apps-ios-qna/power-bi-qna-open-qna.png)

    Soru-Cevap sanal analisti, başlamanız için bazı öneriler sunar.

    ![Soru-Cevap sanal analisti önerileri](./media/tutorial-mobile-apps-ios-qna/power-bi-qna-suggestions.png)

3. **featured insights**'a dokunun.

4. Soru-Cevap sanal analisti bazı öngörüler getirir. Ekranı sağa kaydırın ve **Insight 2**'ye dokunun.

    ![Öne çıkan içgörüler](./media/tutorial-mobile-apps-ios-qna/power-bi-ios-qna-suggest-insight-2.png)

   Soru-Cevap sanal analisti, Insight 2'yi görüntüler.

    ![Öne çıkan içgörüleri görüntüleme](./media/tutorial-mobile-apps-ios-qna/power-bi-ios-qna-show-insight-2.png)

5. Odak modunda açmak için grafiğe dokunun.

    ![Grafiği odak modunda açma](./media/tutorial-mobile-apps-ios-qna/power-bi-ios-qna-open-insight-2.png)

6. Soru-Cevap sanal analisti deneyimine geri dönmek için sol üst köşedeki oka dokunun.

## <a name="clean-up-resources"></a>Kaynakları temizleme

Öğreticiyi tamamladığınızda Fırsat Analizi Örneği pano, rapor ve veri kümesini silebilirsiniz.

1. Power BI hizmetine ([Power BI hizmeti](https://app.powerbi.com)) gidin ve oturum açın.

2. Gezinti bölmesinde **Çalışma Alanım**’ı seçin.

3. Panolar sekmesine tıklayın ve ardından Fırsat Analizi Örneği satırında çöp kutusuna tıklayın.

    ![Sil simgesini seçme](./media/tutorial-mobile-apps-ios-qna/power-bi-tutorial-mobile-apps-ios-qna-delete-opportunity-analysis-sample.png)

    Şimdi raporlar sekmesini seçin ve aynı işlemi yapın.

4. Veri kümeleri sekmesini seçin, **Diğer seçenekler** (...) öğesine tıklayın ve sonra **Sil**'i seçin.

    ![Sil simgesini seçme](./media/tutorial-mobile-apps-ios-qna/power-bi-tutorial-mobile-apps-ios-qna-delete-opportunity-analysis-sample-datasets.png)

## <a name="next-steps"></a>Sonraki adımlar

iOS için Power BI mobil uygulamalarında Soru-Cevap sanal yardımcısını denediniz. Power BI hizmetinde Soru-Cevap hakkında daha fazla bilgi edinin.
> [!div class="nextstepaction"]
> [Q&A in the Power BI service (Power BI hizmetindeki Soru-Cevap özelliği)](../end-user-q-and-a.md)