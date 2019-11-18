---
title: 'Öğretici: iOS uygulamalarında Soru-Cevap sanal analisti ile soru sorma'
description: Bu öğreticide, iOS cihazınızdaki Power BI mobil uygulamasında yer alan Soru-Cevap sanal analistini kullanarak kendi kelimelerinizle örnek verilerle ilgili sorular soracaksınız.
author: mshenhav
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: tutorial
ms.date: 11/16/2018
ms.author: mshenhav
ms.openlocfilehash: c7fd216d50f918d96392532ccb82f80d619ce8a3
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73869650"
---
# <a name="tutorial-ask-questions-about-your-data-with-the-qa-virtual-analyst-in-the-power-bi-ios-apps"></a>Öğretici: Power BI iOS uygulamalarındaki Soru-Cevap sanal analistini kullanarak verileriniz hakkında sorular sorma

Verileriniz hakkında bilgi edinmenin en kolay yolu, bunlarla ilgili soruları kendi kelimelerinizle sormaktır. Bu öğreticide iPad, iPhone ve iPod Touch cihazınızda Microsoft Power BI mobil uygulamasındaki Soru-Cevap sanal çözümleyicisi ile örnek veriler hakkında sorular soracak ve öne çıkan içgörüleri görüntüleyeceksiniz. 

Aşağıdakiler cihazlar için geçerlidir:

| ![iPhone](./media/tutorial-mobile-apps-ios-qna/iphone-logo-50-px.png) | ![iPad](./media/tutorial-mobile-apps-ios-qna/ipad-logo-50-px.png) |
|:--- |:--- |
| iPhone'lar |iPad'ler |

Soru-Cevap sanal çözümleyicisi, Power BI hizmetinde temel alınan Soru-Cevap verilerine erişen, konuşmaya dayalı bir BI deneyimidir [(https://powerbi.com)](https://powerbi.com). Veri içgörüleri önerir ve kendi sorularınızı yazarak ya da konuşarak sorabilirsiniz.

![Top sales Soru-Cevap sanal analisti](./media/tutorial-mobile-apps-ios-qna/power-bi-ios-q-n-a-top-sale-intro.png)

Bu öğreticide şunları yapacaksınız:

> [!div class="checklist"]
> * iOS için Power BI mobil uygulamasını yükleme
> * Bir Power BI örnek panosu ve raporu indirme
> * Mobil uygulamanın öne çıkan hangi içgörüleri önerdiğini görme

Power BI’ya kaydolmadıysanız başlamadan önce [ücretsiz deneme için kaydolun](https://app.powerbi.com/signupredirect?pbi_source=web).

## <a name="prerequisites"></a>Önkoşullar

### <a name="install-the-power-bi-for-ios-app"></a>iOS için Power BI uygulamasını yükleme
App Store'a giderek iPad, iPhone veya iPod Touch'ınıza [iOS uygulamasını indirin](https://go.microsoft.com/fwlink/?LinkId=522062 "iPhone uygulamasını indirin").

iOS için Power BI uygulamasını şu sürümler destekler:
- iOS 10 veya sonraki sürümünü çalıştıran iPad.
- iOS 10 veya sonraki sürümünü çalıştıran iPhone 5 ve üstü. 
- iOS 10 veya sonraki sürümünü çalıştıran iPod Touch.

### <a name="download-the-opportunity-analysis-sample"></a>Fırsat Analizi örneğini indirme
Eğitimin ilk adımı, Power BI hizmetindeki Fırsat Analizi örneklerini indirmektir.

1. Tarayıcınızda Power BI hizmetini (app.powerbi.com) açın ve oturum açın.

1. Genel gezinti simgesini seçerek gezinti bölmesini açın.

    ![genel gezinti simgesi](./media/tutorial-mobile-apps-ios-qna/power-bi-android-quickstart-global-nav-icon.png)

2. Gezinti bölmesinde **Çalışma Alanları** > **Çalışma Alanım**'ı seçin.

    ![Çalışma Alanım](./media/tutorial-mobile-apps-ios-qna/power-bi-android-quickstart-my-workspace.png)

3. Sol alt köşedeki **Veri Al** seçeneğini belirleyin.
   
    ![Veri Al](./media/tutorial-mobile-apps-ios-qna/power-bi-get-data.png)

3. Veri Al sayfasında **Örnekler** simgesini seçin.
   
   ![Örnekler simgesi](./media/tutorial-mobile-apps-ios-qna/power-bi-samples-icon.png)

4. **Fırsat Analizi örneğini** seçin.
 
    ![Fırsat Analizi Örneği](./media/tutorial-mobile-apps-ios-qna/power-bi-oa.png)
 
8. **Bağlan**'ı seçin.  
  
   ![Fırsat Analizi Örneği - Bağlan](./media/tutorial-mobile-apps-ios-qna/opportunity-connect.png)
   
5. Power BI, örneği içeri aktarır ve Çalışma Alanınıza yeni bir pano, rapor ve veri kümesi ekler.
   
   ![Opportunity Analysis Sample panosu](./media/tutorial-mobile-apps-ios-qna/power-bi-service-opportunity-sample.png)

Örneğiniz iOS cihazınızda görüntülenmeye hazırdır.

## <a name="try-featured-insights"></a>Öne çıkan öngörüleri görüntüleme
1. iPhone veya iPad cihazınızda Power BI uygulamasını açın ve tarayıcıdaki Power BI hizmetinde kullandığınız Power BI hesabı kimlik bilgilerinizle oturum açın.

1.  Genel gezintü düğmesine ![Genel gezinti düğmesi](./media/tutorial-mobile-apps-ios-qna/power-bi-iphone-global-nav-button.png) > **Çalışma Alanları** > **Çalışma Alanım** öğesine dokunun ve Fırsat Analizi Örneği panosunu açın.

2. Sayfanın altındaki eylem menüsünde bulunan Soru-Cevap sanal analisti simgesine ![Soru-Cevap sanal analisti simgesi](./media/tutorial-mobile-apps-ios-qna/power-bi-ios-q-n-a-icon.png) dokunun (iPad cihazında sayfanın üstünde).

     ![Opportunity Analysis Sample panosu](./media/tutorial-mobile-apps-ios-qna/power-bi-ios-qna-opportunity-analysis.png)

     Power BI Soru-Cevap sanal analisti, başlamanız için bazı öneriler sunar.

     ![featured insights düğmesi](./media/tutorial-mobile-apps-ios-qna/power-bi-ios-qna-suggest-insights.png)
3. **featured insights**'a dokunun.

     Soru-Cevap sanal analisti bazı öngörüler getirir.
4. Ekranı sağa kaydırın ve **Insight 2**'ye dokunun.

    ![Insight 2 düğmesi](./media/tutorial-mobile-apps-ios-qna/power-bi-ios-qna-suggest-insight-2.png)

     Soru-Cevap sanal analisti, Insight 2'yi görüntüler.

    ![Insight 2](./media/tutorial-mobile-apps-ios-qna/power-bi-ios-qna-show-insight-2.png)
5. Odak modunda açmak için grafiğe dokunun.

    ![Odak modundaki Insight 2 grafiği](./media/tutorial-mobile-apps-ios-qna/power-bi-ios-qna-open-insight-2.png)
6. Soru-Cevap sanal analisti deneyimine geri dönmek için sol üst köşedeki oka dokunun.

## <a name="clean-up-resources"></a>Kaynakları temizleme

Öğreticiyi tamamladığınızda Fırsat Analizi Örneği pano, rapor ve veri kümesini silebilirsiniz.

1. Power BI hizmeti (app.powerbi.com) sayfasına gidin ve oturum açın.

2. Gezinti bölmesinde **Çalışma Alanları** > **Çalışma Alanım**'ı seçin.

3. **Panolar** sekmesinde Fırsat Analizi panosunun yanında bulunan çöp kutusu biçimindeki **Sil** simgesini seçin.

    ![Örnek panosunu silme](./media/tutorial-mobile-apps-ios-qna/power-bi-service-delete-opportunity-sample.png)

4. **Raporlar** sekmesini seçin ve aynı işlemi Fırsat Analizi raporu için tekrarlayın.

5. **Veri Kümeleri** sekmesini seçin ve aynı işlemi Fırsat Analizi veri kümesi için tekrarlayın.


## <a name="next-steps"></a>Sonraki adımlar

iOS için Power BI mobil uygulamalarında Soru-Cevap sanal yardımcısını denediniz. Power BI hizmetinde Soru-Cevap hakkında daha fazla bilgi edinin.
> [!div class="nextstepaction"]
> [Q&A in the Power BI service (Power BI hizmetindeki Soru-Cevap özelliği)](../end-user-q-and-a.md)

