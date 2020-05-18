---
title: Power BI ile Smartsheet'e bağlanma
description: Power BI için Smartsheet
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 05/04/2020
ms.author: painbar
LocalizationGroup: Connect to services
ms.openlocfilehash: 4498557d1bd38ce457b2e79d637e713af11c945a
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83325058"
---
# <a name="connect-to-smartsheet-with-power-bi"></a>Power BI ile Smartsheet'e bağlanma
Bu makalede, verileri Smartsheet hesabınızdan Power BI şablon uygulamasıyla çekme işlemi adım adım açıklanmaktadır. Smartsheet, işbirliği ve dosya paylaşımı için basit bir platform sunar. Power BI için Smartsheet şablon uygulaması, Smartsheet hesabınıza genel bakış bilgilerini gösteren bir pano, raporlar ve veri kümesi sağlar. Ayrıca, [Power BI Desktop](desktop-connect-to-data.md)'ı kullanarak hesabınızdaki her bir sayfaya doğrudan bağlanabilirsiniz. 

Şablon uygulamasını yükledikten sonra panoyu ve raporu değiştirebilirsiniz. Daha sonra bunu, kuruluşunuzdaki iş arkadaşlarınıza bir uygulama olarak dağıtabilirsiniz.

Power BI için [Smartsheet şablon uygulamasına](https://app.powerbi.com/groups/me/getapps/services/pbi-contentpacks.pbiapps-smartsheet) bağlanın.

>[!NOTE]
>Ek erişim ayrıcalığı olduğundan, Power BI şablon uygulamasına bağlanılması ve içerik paketinin yüklenmesi için Smartsheet yönetici hesabı tercih edilir.

## <a name="how-to-connect"></a>Bağlanma

[!INCLUDE [powerbi-service-apps-get-more-apps](../includes/powerbi-service-apps-get-more-apps.md)]

3. **Smartsheet** \> **Şimdi edinin**'i seçin.
4. **Bu Power BI uygulaması yüklensin mi?** iletişim kutusunda **Yükle**’yi seçin.
4. **Uygulamalar** bölmesinde **Smartsheet** kutucuğunu seçin.

    ![Power BI Smartsheet uygulaması kutucuğu](media/service-connect-to-smartsheet/power-bi-smartsheet-tile.png)

6. **Yeni uygulamanızı kullanmaya başlayın** alanında **Bağlan** seçeneğini belirleyin.

    ![Yeni uygulamanızı kullanmaya başlayın](media/service-connect-to-zendesk/power-bi-new-app-connect-get-started.png)

4. Kimlik Doğrulama Yöntemi için **OAuth2\> Oturum aç** seçeneğini belirleyin.
   
   İstendiğinde Smartsheet kimlik bilgilerinizi girin ve kimlik doğrulaması işlemindeki diğer adımları uygulayın.
   
   ![Smartsheet kimlik bilgileri](media/service-connect-to-smartsheet/creds.png)
   
   ![Smartsheet oturumu açma](media/service-connect-to-smartsheet/creds2.png)

5. Power BI verileri içeri aktardıktan sonra Smartsheet panosu açılır.
   
   ![Smartsheet panosu](media/service-connect-to-smartsheet/power-bi-smartsheet-dashboard.png)

## <a name="modify-and-distribute-your-app"></a>Uygulamanızı değiştirme ve dağıtma

Smartsheet şablon uygulamasını yüklediniz. Yani Smartsheet uygulama çalışma alanını da oluşturmuş oldunuz. Çalışma alanında, raporu ve panoyu değiştirebilir ve sonra kuruluşunuzdaki iş arkadaşlarınıza bir *uygulama* olarak dağıtabilirsiniz. 

1. Yeni Smartsheet çalışma alanınızın tüm içeriğini görüntülemek için gezinti bölmesinde **Çalışma Alanları** > **Smartsheet**'i seçin. 

    ![Gezinti bölmesinde Smartsheet çalışma alanı](media/service-connect-to-smartsheet/power-bi-smartsheet-workspace.png)

    Bu görünüm çalışma alanı için içerik listesidir. Sağ üst köşede, **Uygulamayı güncelleştir** seçeneğini görürsünüz. Uygulamanızı iş arkadaşlarınıza dağıtmaya hazır olduğunuzda, buradan başlayacaksınız. 

    ![Smartsheet içerik listesi](media/service-connect-to-smartsheet/power-bi-smartsheet-workspace-content.png)

2. Çalışma alanındaki diğer öğeleri görmek için **Raporlar**’ı ve **Veri kümeleri**’ni seçin.

    İş arkadaşlarınıza [uygulama dağıtma](../collaborate-share/service-create-distribute-apps.md) hakkında bilgi edinin.

## <a name="whats-included"></a>Neleri kapsar?
Power BI için Smartsheet şablon uygulaması; Smartsheet hesabınıza yönelik olarak, sahip olduğunuz çalışma alanı, rapor ve sayfa sayısı ve bunların ne zaman değiştirildiği gibi bilgileri içeren bir genel bakış sunar. Yönetici kullanıcılar, en çok sayfa oluşturanlar gibi, sistemlerindeki kullanıcılar ile ilgili bazı bilgileri de görür.  

Hesabınızdaki her bir sayfaya doğrudan bağlanmak için [Power BI Desktop](desktop-connect-to-data.md)'taki Smartsheet bağlayıcısını kullanabilirsiniz.  

## <a name="next-steps"></a>Sonraki adımlar

* [Power BI'da yeni çalışma alanları oluşturma](../collaborate-share/service-create-the-new-workspaces.md)
* [Power BI'da uygulamaları yükleme ve kullanma](../consumer/end-user-apps.md)
* [Dış hizmetler için Power BI uygulamalarına bağlanma](service-connect-to-services.md)
* Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)