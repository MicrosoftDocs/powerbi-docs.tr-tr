---
title: Power BI ile Google Analytics'e bağlanma
description: Power BI için Google Analytics
author: SarinaJoan
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/16/2017
ms.author: sarinas
LocalizationGroup: Connect to services
ms.openlocfilehash: b479c46ffe3e51ad5f15cc9884a2ea02626a4cc5
ms.sourcegitcommit: 2a7bbb1fa24a49d2278a90cb0c4be543d7267bda
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "34244642"
---
# <a name="connect-to-google-analytics-with-power-bi"></a>Power BI ile Google Analytics'e bağlanma
Power BI aracılığıyla Google Analytics'e bağlanmak için ilk olarak Google Analytics hesabınıza bağlanırsınız. Site trafiğiniz ve kullanıcılarınıza ilişkin ölçülerle ilgili öngörüler sağlayan bir Power BI panosu ile bir dizi Power BI raporu edinirsiniz. Pano ve raporlarla etkileşim kurabilir ancak değişiklikleri kaydedemezsiniz. Veriler günde bir kez otomatik olarak yenilenir.

Power BI için [Google Analytics](https://app.powerbi.com/getdata/services/google-analytics)'e bağlanın. Power BI ile [Google Analytics tümleştirmesi](https://powerbi.microsoft.com/integrations/google-analytics) hakkında daha fazla bilgi edinin.

Power BI Desktop'ta [Google Analytics bağlayıcısının](service-google-analytics-connector.md) bulunduğu bölüme giderek, özelleştirilmiş panolar ve raporlar oluşturmaya başlayabilirsiniz. Özel raporlar oluşturmak için Google Analytics hesabınızla bağlanmanız yeterlidir. Daha sonra bu özel raporları Power BI hizmetinde yayımlayabilirsiniz.

## <a name="how-to-connect"></a>Bağlanma
[!INCLUDE [powerbi-service-apps-get-more-apps](./includes/powerbi-service-apps-get-more-apps.md)]

1. **Google Analytics** \> **Al**'ı seçin.
   
   ![](media/service-connect-to-google-analytics/ga.png)
2. İstendiğinde, Google Analytics kimlik bilgilerinizi girin. Kimlik doğrulama yöntemi olarak **OAuth2**'yi seçin ve **Oturum Aç**'a tıklayın. Google kimlik doğrulama akışını takip edin. Daha önce yapılandırmış olmanız halinde bu akışta iki öğeli kimlik doğrulama da uygulanabilir.
   
   ![](media/service-connect-to-google-analytics/creds.png)
3. Power BI'ın, Google Analytics verilerinize erişmesine izin vermek için **Accept**'e (Kabul et) tıklayın.
   
   ![](media/service-connect-to-google-analytics/googleanalytics.png)
4. Power BI belirli bir Google Analytics Görünümüne bağlanır. Bağlanmak istediğiniz hesap adını, özellik adını ve görünüm adını seçin. Bu bilgiler, Google Analytics hesabınızdaki sol üst kısımda veya **Ana Sayfa** sekmesinde bulunabilir. Ayrıntıları aşağıda bulabilirsiniz. 
   
   ![](media/service-connect-to-google-analytics/params2.png)
5. İçeri aktarma işlemini başlatmak için **Connect**'e (Bağlan) tıklayın. 

## <a name="view-the-google-analytics-dashboard-and-reports"></a>Google Analytics panosunu ve raporları görüntüleme
[!INCLUDE [powerbi-service-apps-open-app](./includes/powerbi-service-apps-open-app.md)]

      ![](media/service-connect-to-google-analytics/googleanalytics2.png)

[!INCLUDE [powerbi-service-apps-open-app](./includes/powerbi-service-apps-what-now.md)]

## <a name="system-requirements"></a>Sistem gereksinimleri
Power BI'dan bağlanmak için bir [Google Analytics](https://www.google.com/analytics/) hesabınız olması gerekir. Kendisine bağlı bir Google Analytics hesabı olmayan diğer Google hesapları bir kimlik doğrulama hatası alır.

## <a name="troubleshooting"></a>Sorun giderme
**Kimlik bilgileri** Birden çok Google hesabınız varsa bağlantı sırasında doğru hesabın kullanıldığından emin olmak için lütfen gizli veya özel bir tarayıcı penceresi kullanın.

Kimlik bilgilerinizin geçersiz olduğunu belirten bir hata alıyor ancak Google'da oturum açabiliyorsanız lütfen bir [Google Analytics](https://www.google.com/analytics/) hesabınız olduğunu doğrulayın.

**Parametreler** Şu anda parametreler için benzersiz adlar gereklidir. Seçtiğiniz değerin yinelendiğini belirten bir hata ile karşılaştıysanız lütfen başka bir değer seçin veya Google Analytics'te adları benzersiz olacak şekilde değiştirin. Bu sorunu iyileştirmek için yoğun bir şekilde çalışıyoruz.

>[!NOTE]
>Parametreler büyük/küçük harfe duyarlıdır. Parametreleri, tam olarak Google Analytics hesabınızda göründüğü gibi girin.

![](media/service-connect-to-google-analytics/pbi_googleanalytics1.png)

Sorun hâlâ çözülmedi mi? Power BI ekibine ulaşmak için bir destek bileti açın:

* Power BI uygulamasındayken soru işareti \> **Destek Ekibine Başvur** seçeneğini belirleyin.
* Bu makaleyi okuduğunuz Power BI Destek sitesinde sayfanın sağ tarafında bulunan **Contact Support**'u (Destek Ekibine Başvur) seçin.

## <a name="next-steps"></a>Sonraki adımlar
* [Power BI'da uygulamalar ne anlama gelir?](service-install-use-apps.md)
* [Power BI'da veri alma](service-get-data.md)
* Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

