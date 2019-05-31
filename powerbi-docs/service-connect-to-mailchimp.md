---
title: Power BI ile MailChimp'e bağlanma
description: Power BI için MailChimp
author: maggiesMSFT
manager: kfile
ms.reviewer: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 04/26/2019
ms.author: maggies
LocalizationGroup: Connect to services
ms.openlocfilehash: 8599c22246183d28d13eb80f05250baa8dc27f5d
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "64579037"
---
# <a name="connect-to-mailchimp-with-power-bi"></a>Power BI ile MailChimp'e bağlanma
Bu makalede, Power BI şablon uygulama ile MailChimp hesabınızdan veri çekme gösterilmektedir. Şablon uygulaması ile bir pano, raporlar kümesi ve bir veri kümesi oluşturarak MailChimp verilerinizi araştırmanıza olanak tanımak için bir çalışma alanı oluşturur. Analiz verileri çekerek [MailChimp panoları](https://powerbi.microsoft.com/integrations/mailchimp) oluşturun ve kampanyalarınızda, raporlarınızda ve bireysel abonelerinizde görülen eğilimleri hızla tanımlayın. İzlemekte verilerin güncel olduğunu verileri günlük olarak yeniler.

Şablon uygulamayı yükledikten sonra panoyu ve raporu değiştirebilirsiniz. Ardından, bu iş arkadaşlarınıza bir uygulama olarak, kuruluşunuzda dağıtabilirsiniz.

Bağlanma [MailChimp şablon uygulaması](https://app.powerbi.com/getdata/services/mailchimp) Power BI için.

## <a name="how-to-connect"></a>Bağlanma

[!INCLUDE [powerbi-service-apps-get-more-apps](./includes/powerbi-service-apps-get-more-apps.md)]

3. Seçin **MailChimp** \> **şimdi edinin**.
4. İçinde **bu Power BI uygulaması yükleme?** seçin **yükleme**.
4. İçinde **uygulamaları** bölmesinde **MailChimp** Döşe.

    ![Power BI MailChimp uygulama kutucuğu](media/service-connect-to-mailchimp/power-bi-connect-mailchimp.png)

6. İçinde **yeni uygulamanızı ile çalışmaya başlama**seçin **verilere**.

    ![Yeni uygulamanızı kullanmaya başlayın](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-connect-data.png)

1. Kimlik Doğrulama Yöntemi için **OAuth2** \> **Oturum aç** seçeneğini belirleyin.
   
    İstendiğinde, MailChimp kimlik bilgilerinizi girin ve kimlik doğrulaması işlemini gerçekleştirin.
   
    İlk kez bağlandığınızda Power BI, hesabınıza salt okunur erişime izin vermenizi ister. İçeri aktarma işlemini başlatmak için **Allow** (İzin ver) seçeneğini belirleyin. Bu işlem hesabınızdaki verilerin hacmine bağlı olarak birkaç dakika sürebilir.
   
    ![MailChimp için Power BI Bağlayıcısı](media/service-connect-to-mailchimp/allow.png)

5. Veriler Power BI tarafından içeri aktarıldıktan sonra MailChimp panosu açılır.
   
    ![Power BI MailChimp Panosu](media/service-connect-to-mailchimp/power-bi-mailchimp-dashboard.png)

## <a name="modify-and-distribute-your-app"></a>Değiştirme ve uygulamanızı dağıtın

MailChimp şablon uygulaması yüklediniz. MailChimp uygulama çalışma alanı da oluşturmuş olduğunuz anlamına gelir. Çalışma alanında, rapor ve Pano değiştirebilir ve ardından olarak dağıtmak bir *uygulama* kuruluşunuzdaki iş arkadaşlarınıza. 

1. Sol gezinti çubuğunda yeni MailChimp çalışma alanınızda, tüm içeriğini görüntülemek için seçin **çalışma alanları** > **MailChimp**. 

    ![Sol gezinti bölmesinde MailChimp çalışma](media/service-connect-to-mailchimp/power-bi-mailchimp-left-nav.png)

    Bu görünüm çalışma alanı için içerik listesidir. Sağ üst köşedeki gördüğünüz **uygulamayı Güncelleştir**. İş arkadaşlarınız için uygulamanızı dağıtmaya hazır olduğunuzda nereden başlayacaksınız olmasıdır.

    ![MailChimp içerik listesi](media/service-connect-to-mailchimp/power-bi-mailchimp-content-list.png)

2. Seçin **raporları** ve **veri kümeleri** çalışma alanındaki diğer öğeleri görmek için. 

    Hakkında bilgi edinin [uygulama dağıtmaya](service-create-distribute-apps.md) iş arkadaşlarınıza önerilmesini sağlayın.

## <a name="next-steps"></a>Sonraki adımlar

* [Power BI'da yeni çalışma alanları oluşturma](service-create-the-new-workspaces.md)
* [Power BI'da uygulamaları yükleme ve kullanma](consumer/end-user-apps.md)
* [Dış hizmetler için Power BI uygulamaları](service-connect-to-services.md)
* Sorularınız mı var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

