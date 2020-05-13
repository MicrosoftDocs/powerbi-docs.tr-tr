---
title: 'Öğretici: Power BI ile bir GitHub deposuna bağlanma'
description: Bu öğreticide, Power BI ile GitHub hizmetindeki gerçek verilere bağlanırsınız ve Power BI otomatik olarak panolar ve raporlar oluşturur.
author: maggiesMSFT
ms.reviewer: SarinaJoan
ms.service: powerbi
ms.subservice: powerbi-service
ms.custom: connect-to-services
ms.topic: tutorial
ms.date: 08/07/2019
ms.author: maggies
LocalizationGroup: Connect to services
ms.openlocfilehash: a3c87a700df1c35596b6520cc64d9b580ccb74eb
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83332326"
---
# <a name="tutorial-connect-to-a-github-repo-with-power-bi"></a>Öğretici: Power BI ile bir GitHub deposuna bağlanma
Bu öğreticide, Power BI ile GitHub hizmetindeki gerçek verilere bağlanırsınız ve Power BI otomatik olarak panolar ve raporlar oluşturur. Power BI içerik genel deposuna (*depo* olarak da bilinir) bağlanır ve şunlar gibi soruların cevaplarını görürsünüz: Power BI genel içeriğine kaç kişi katkıda bulunuyor? En çok kim katkıda bulunuyor? En çok haftanın hangi gününde katkıda bulunuluyor? Ve diğer sorular. 

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

- [GitHub hesabına](https://docs.microsoft.com/contribute/get-started-setup-github) kaydolun.


## <a name="how-to-connect"></a>Bağlanma
1. Power BI hizmetinde (`https://app.powerbi.com`) oturum açın. 
2. Gezinti bölmesinde **Uygulamalar** seçeneğini ve ardından **Uygulamaları edinin** seçeneğini belirleyin.
   
   ![Power BI Get uygulamaları](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial.png) 

3. **Uygulamalar**’ı seçin, arama kutusuna **GitHub** yazın > **Hemen edinin**’e tıklayın.
   
   ![Power BI Get GitHub](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-app-source.png) 

4. **Bu Power BI uygulaması yüklensin mi?** iletişim kutusunda **Yükle**’yi seçin.
5. **Yeni uygulamanız hazır** alanında **Uygulamaya gidin** seçeneğini belirleyin.
6. **Yeni uygulamanızı kullanmaya başlayın** alanında **Bağlan** seçeneğini belirleyin.

    ![Yeni uygulamanızı kullanmaya başlayın](media/service-tutorial-connect-to-github/power-bi-new-app-connect-get-started.png)

7. Depo adını ve sahibini girin. Bu depodaki URL https://github.com/MicrosoftDocs/powerbi-docs olduğundan, **Depo Sahibi** **MicrosoftDocs** ve **Depo** da **powerbi-docs**’tur. 
   
    ![Power BI GitHub depo adı](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-connect.png)

5. Oluşturduğunuz GitHub kimlik bilgilerini girin. Önceden tarayıcınızda GitHub’da oturum açtıysanız Power BI bu adımı atlayabilir. 

6. **Kimlik Doğrulama Yöntemi** için **OAuth2** seçimini koruyun ve \>**Oturum Açın**.

7. GitHub kimlik doğrulaması ekranlarındaki yönergeleri uygulayın. Power BI’a GitHub verileri için izin verin.
   
   Şimdi Power BI, GitHub ile bağlantı kurup verilere bağlanabilir.  Veriler, günde bir kez yenilenir.

8. Power BI verileri içeri aktardıktan sonra yeni GitHub çalışma alanınızın içeriklerini görürsünüz. 
9. Gezinti bölmesinde çalışma alanı adının yanındaki oku seçin. Çalışma alanının bir pano ve rapor içerdiğini görürsünüz. 

    ![Gezinti bölmesindeki uygulama](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-left-nav-expanded.png)

10. Pano adının yanındaki **Diğer seçenekler** (...) > **Yeniden adlandır**’ı seçin ve **GitHub panosu** yazın.
 
    ![Power BI GitHub kutucuğu](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-left-nav.png) 

8. Daha fazla alan kazanmak için genel gezinti simgesini seçerek gezinti bölmesini simge durumuna küçültün.

    ![Genel gezinti simgesi](media/service-tutorial-connect-to-github/power-bi-global-navigation-icon.png)

10. GitHub panonuzu seçin.
    
    GitHub panosu canlı veriler içerir. Bu nedenle gördüğünüz değerler farklı olabilir.

    ![Power BI’da GitHub panosu](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-new-dashboard.png)

    

## <a name="ask-a-question"></a>Soru sorun

1. İmlecinizi **Verileriniz hakkında soru sorun** bölümüne yerleştirin. Power BI, **kullanmaya başlamaya yönelik sorular** sunar. 

1. **Kaç kullanıcı bulunduğunu** seçin.
 
    ![Kaç kullanıcı bulunuyor?](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-qna-how-many-users.png)

13. **Kaç** ve **kullanıcı bulunuyor** sorularına benzer biçimde **çekme isteği başına kaç kullanıcı bulunuyor** yazın. 

     Power BI, kişi başına isteği sayısını gösteren bir çubuk grafik oluşturur.

    ![Kullanıcı başına kaç tane çekme isteği bulunuyor?](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-qna-how-many-prs.png)


13. Panonuza sabitlemek için sabitleme iğnesini seçin ve **Soru-Cevap'tan çıkın**.

## <a name="view-the-github-report"></a>GitHub raporunu görüntüleme 

1. GitHub panosunda **Aya Göre Çekme İstekleri** adlı sütun grafiğini seçerek ilgili raporu açın.

    ![Aya göre çekme istekleri sütun grafiği](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-column-chart.png)

2. **Kullanıcılara göre toplam çekme isteği** grafiğinde bir kullanıcı adı seçin. Bu örnekte, çalışma saatlerinin çoğunluğunun Şubat’ta olduğunu görüyoruz.

    ![Power BI GitHub raporu vurgulama](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-cross-filter-total-prs.png)

3. **Delikli Kart** sekmesini seçerek raporda sonraki sayfayı görüntüleyin. 
 
    ![Power BI GitHub raporu Delikli Kart](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-tues-3pm.png)

    Görünüşe göre Salı günleri saat 15:00, insanların işlerine giriş yaptığı haftanın en yoğun *yürütme* günü ve saatidir.

## <a name="clean-up-resources"></a>Kaynakları temizleme

Öğreticiyi bitirdiğinize göre şimdi GitHub uygulamasını silebilirsiniz. 

1. Gezinti bölmesinde **Uygulamalar**’ı seçin.
2. İmleci GitHub kutucuğunun üzerine getirin ve **Sil** çöp kutusunu seçin.

    ![GitHub uygulamasını silme](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-delete.png)

## <a name="next-steps"></a>Sonraki adımlar

Bu öğreticide, bir GitHub genel deposuna bağlandınız ve Power BI’ın biçimlendirdiği verileri bir panoda ve raporda aldınız. Pano ve raporu keşfederek veriler hakkında bazı soruları yanıtladınız. Şimdi Salesforce, Microsoft Dynamics ve Google Analytics gibi diğer hizmetlere bağlanma hakkında daha fazla bilgi edinebilirsiniz. 
 
> [!div class="nextstepaction"]
> [Kullandığınız çevrimiçi hizmetlere bağlanma](service-connect-to-services.md)


