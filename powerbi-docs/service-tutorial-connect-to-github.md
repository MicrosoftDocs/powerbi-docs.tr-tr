---
title: 'Öğretici: Power BI ile bir GitHub örneğine bağlanma'
description: Bu öğreticide, Power BI ile GitHub hizmetindeki gerçek verilere bağlanırsınız ve Power BI otomatik olarak panolar ve raporlar oluşturur.
author: maggiesMSFT
manager: kfile
ms.reviewer: SarinaJoan
ms.service: powerbi
ms.subservice: powerbi-service
ms.custom: connect-to-services
ms.topic: tutorial
ms.date: 05/17/2018
ms.author: maggies
LocalizationGroup: Connect to services
ms.openlocfilehash: 8f44356f79b8a77ef06fe464671dbbaaaa4187e9
ms.sourcegitcommit: 5e83fa6c93a0bc6599f76cc070fb0e5c1fce0082
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/13/2019
ms.locfileid: "56215600"
---
# <a name="tutorial-connect-to-a-github-sample-with-power-bi"></a>Öğretici: Power BI ile bir GitHub örneğine bağlanma
Bu öğreticide, Power BI ile GitHub hizmetindeki gerçek verilere bağlanırsınız ve Power BI otomatik olarak panolar ve raporlar oluşturur. Power BI içerik genel deposuna (*depo* olarak da bilinir) bağlanır ve şu bilgileri görürsünüz: Power BI genel içeriğine kaç kişi katkıda bulunuyor? En çok kim katkıda bulunuyor? En çok haftanın hangi gününde katkıda bulunuluyor? Ve diğer soruların yanıtları. 

![Power BI’daki GitHub raporu](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-punch-card.png)

Bu öğreticide aşağıdaki adımları tamamlarsınız:

> [!div class="checklist"]
> * Bir GitHub hesabınız yoksa, GitHub hesabına kaydolma 
> * Power BI hesabınızda oturum açma veya Power BI hesabınız yoksa, Power BI hesabına kaydolma
> * Power BI hizmetini açma
> * GitHub uygulamasını bulma
> * Power BI genel GitHub deposu için bilgileri girme
> * GitHub verileriyle panoyu ve raporu görüntüleme
> * Uygulamayı silerek kaynakları temizleme

Power BI’ya kaydolmadıysanız başlamadan önce [ücretsiz deneme için kaydolun](https://app.powerbi.com/signupredirect?pbi_source=web).

## <a name="prerequisites"></a>Önkoşullar

Bu öğreticiyi tamamlamak için, bir GitHub hesabınız yoksa GitHub hesabınız olması gerekir. 

- [GitHub hesabına](https://docs.microsoft.com/contribute/get-started-setup-github) kaydolun


## <a name="how-to-connect"></a>Bağlanma
1. Power BI hizmetinde (http://powerbi.com)) oturum açın. 
2. Sol gezinti bölmesinde **Uygulamalar**’ı ve sonra **Uygulamaları al**’ı seçin.
   
   ![Power BI Get uygulamaları](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial.png) 

3. **Uygulamalar**’ı seçin, arama kutusuna **github** yazın > **Hemen edinin**’e tıklayın.
   
   ![Power BI Get GitHub](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-get-it-now.png) 

4. Depo adını ve sahibini girin. Bu depodaki URL https://github.com/MicrosoftDocs/powerbi-docs olduğundan, **Depo Sahibi** **MicrosoftDocs** ve **Depo** da **powerbi-docs**’tur. 
   
    ![Power BI GitHub depo adı](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-repo-name.png)

5. Oluşturduğunuz GitHub kimlik bilgilerini girin. Önceden tarayıcınızda GitHub’da oturum açtıysanız Power BI bu adımı atlayabilir. 

6. **Kimlik doğrulama yöntemi** için **OAuth2** \> **Oturum aç** seçeneklerini belirleyin.

7. GitHub kimlik doğrulaması ekranlarındaki yönergeleri uygulayın. Power BI’a GitHub verileri için izin verin.
   
   Şimdi Power BI, GitHub ile bağlantı kurup verilere bağlanabilir.  Veriler, günde bir kez yenilenir.

8. Power BI, verileri içeri aktardıktan sonra yeni GitHub kutucuğunu görürsünüz. 
 
   ![Power BI GitHub kutucuğu](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-tile.png) 

8. Daha fazla alan kazanmak için genel gezinti simgesini seçerek sol gezinti bölmesini simge durumuna küçültün.

    ![Genel gezinti simgesi](media/service-tutorial-connect-to-github/power-bi-global-navigation-icon.png)

10. 8. adımdan GitHub kutucuğunu seçin. 
    
    GitHub panosu açılır. Bunlar canlı verilerdir; bu nedenle gördüğünüz değerler farklı olabilir.

    ![Power BI’da GitHub panosu](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-dashboard.png)

    

## <a name="ask-a-question"></a>Soru sorun

11. İmlecinizi **Verileriniz hakkında soru sorun** bölümüne yerleştirip **çekme istekleri** seçeneğini belirleyin. 

    ![Power BI Verileriniz hakkında soru sorun](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-ask-question.png)

12. **Aya göre** yazın.
 
    ![Aya göre çekme istekleri](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-ask-question-by-month.png)

     Power BI, aylık çekme isteği sayısını gösteren bir çubuk grafik oluşturur.

13. **Soru-Cevaptan Çık** seçeneğini belirleyin.

## <a name="view-the-github-report"></a>GitHub raporunu görüntüleme 

1. GitHub panosunda, **Aya Göre Çekme İstekleri** adlı birleşik sütun ve çizgi grafiğini seçerek ilgili raporu açın.

    ![Aya göre çekme istekleri birleşik grafiği](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-pull-requests-combo-chart.png)

2. **Kullanıcı tarafından toplam çekme istekleri** grafiğinde bir kullanıcı adı seçin ve bu örnekte olduğu gibi ortalama saatin, Mart ayına ait toplam ortalamanın üzerinde olduğunu görün.

    ![Power BI GitHub raporu vurgulama](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-report-highlight.png)

3. **Delikli Kart** sekmesini seçerek raporda sonraki sayfayı görüntüleyin. 
 
    ![Power BI GitHub raporu Delikli Kart](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-tues-3pm.png)

    Görünüşe göre Salı günleri saat 15:00, insanların işlerine giriş yaptığı haftanın en yoğun *yürütme* günü ve saatidir.

## <a name="clean-up-resources"></a>Kaynakları temizleme

Öğreticiyi bitirdiğinize göre şimdi GitHub uygulamasını silebilirsiniz. 

1. Sol gezinti çubuğundan **Uygulamalar**’ı seçin.
2. İmleci GitHub kutucuğunun üzerine getirin ve **Sil** çöp kutusunu seçin.

    ![GitHub uygulamasını silme](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-delete.png)

## <a name="next-steps"></a>Sonraki adımlar

Bu öğreticide, bir GitHub genel deposuna bağlandınız ve Power BI’ın biçimlendirdiği verileri bir panoda ve raporda aldınız. Pano ve raporu keşfederek veriler hakkında bazı soruları yanıtladınız. Şimdi Salesforce, Microsoft Dynamics ve Google Analytics gibi diğer hizmetlere bağlanma hakkında daha fazla bilgi edinebilirsiniz. 
 
> [!div class="nextstepaction"]
> [Kullandığınız çevrimiçi hizmetlere bağlanma](service-connect-to-services.md)


