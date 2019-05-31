---
title: Power BI ile Zendesk'e bağlanma
description: Power BI için Zendesk
author: maggiesMSFT
manager: kfile
ms.reviewer: sarinas
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 04/26/2019
ms.author: maggies
LocalizationGroup: Connect to services
ms.openlocfilehash: 1edc4179b000191dfeff87387417009bc28e0ee5
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "64578803"
---
# <a name="connect-to-zendesk-with-power-bi"></a>Power BI ile Zendesk'e bağlanma

Bu makalede, verilerinizi Power BI şablon uygulama ile Zendesk hesabınızdan çekme gösterilmektedir. Zendesk uygulamasında, bir Power BI panosu ve bilet hacimleriniz ve aracı performansı hakkında Öngörüler sağlayan Power BI rapor kümesi sunar. Veriler günde bir kez otomatik olarak yenilenir. 

Şablon uygulamayı yükledikten sonra en çok önem verdiğiniz bilgileri vurgulamak için rapor ve Pano özelleştirebilirsiniz. Ardından, bu iş arkadaşlarınıza bir uygulama olarak, kuruluşunuzda dağıtabilirsiniz.

[Zendesk içerik paketine](https://app.powerbi.com/getdata/services/zendesk) bağlanın veya Power BI ile [Zendesk tümleştirmesi](https://powerbi.microsoft.com/integrations/zendesk) hakkında daha fazla bilgi edinin.

Şablon uygulamayı yükledikten sonra panoyu ve raporu değiştirebilirsiniz. Ardından, bu iş arkadaşlarınıza bir uygulama olarak, kuruluşunuzda dağıtabilirsiniz.

>[!NOTE]
>Bağlanmak için bir Zendesk yönetici hesabı gerekir. Aşağıda, [gereksinimler](#system-requirements) ile ilgili daha ayrıntılı bilgi verilmiştir.

## <a name="how-to-connect"></a>Bağlanma

[!INCLUDE [powerbi-service-apps-get-more-apps](./includes/powerbi-service-apps-get-more-apps.md)]

3. Seçin **Zendesk** \> **şimdi edinin**.
4. İçinde **bu Power BI uygulaması yükleme?** seçin **yükleme**.
4. İçinde **uygulamaları** bölmesinde **Zendesk** Döşe.

    ![Power BI Zendesk uygulama kutucuğu](media/service-connect-to-zendesk/power-bi-zendesk-tile.png)

6. İçinde **yeni uygulamanızı ile çalışmaya başlama**seçin **verilere**.

    ![Yeni uygulamanızı kullanmaya başlayın](media/service-tutorial-connect-to-github/power-bi-github-app-tutorial-connect-data.png)

4. Hesabınızla ilişkili URL'yi girin. URL formundadır **https://company.zendesk.com** . [Bu parametreleri bulmaya](#finding-parameters) ilişkin ayrıntılı bilgi için aşağıya bakın.
   
   ![Zendesk’e bağlan](media/service-connect-to-zendesk/pbi_zendeskconnect.png)

5. İstendiğinde Zendesk kimlik bilgilerinizi girin.  Kimlik doğrulama yöntemi olarak **OAuth2**'yi seçin ve **Oturum Aç**'a tıklayın. Zendesk kimlik doğrulaması akışını takip edin. (Zaten Zendesk'e tarayıcınızda oturum açmadıysanız, sizin için kimlik bilgilerini istenmeyebilir.)
   
   > [!NOTE]
   > Bu içerik paketi, bir Zendesk yönetici hesabı ile bağlanmanız gerekir. 
   > 
   
   ![OAuth2 bilgilerinizle oturum açın](media/service-connect-to-zendesk/pbi_zendesksignin.png)
6. Power BI'ın, Zendesk verilerinize erişmesine izin vermek için **İzin ver**'e tıklayın.
   
   ![İzin ver](media/service-connect-to-zendesk/zendesk2.jpg)
7. İçeri aktarma işlemini başlatmak için **Connect**'e (Bağlan) tıklayın. 
8. Verileri Power BI tarafından içeri aktarıldıktan sonra Zendesk uygulamanız için içerik listesine bakın: yeni bir pano, rapor ve veri kümesi.
9. Araştırma işlemi başlatmak için panoyu seçin.

    ![Zendesk dashboard](media/service-connect-to-zendesk/power-bi-zendesk-dashboard.png)
   
## <a name="modify-and-distribute-your-app"></a>Değiştirme ve uygulamanızı dağıtın

Zendesk şablon uygulaması yüklediniz. Zendesk uygulama çalışma alanı da oluşturmuş olduğunuz anlamına gelir. Çalışma alanında, rapor ve Pano değiştirebilir ve ardından olarak dağıtmak bir *uygulama* kuruluşunuzdaki iş arkadaşlarınıza. 

1. Sol gezinti çubuğunda yeni Zendesk çalışma alanınızda, tüm içeriğini görüntülemek için seçin **çalışma alanları** > **Zendesk**. 

    ![Sol gezinti bölmesinde Zendesk çalışma](media/service-connect-to-zendesk/power-bi-zendesk-workspace-left-nav.png)

    Bu görünüm çalışma alanı için içerik listesidir. Sağ üst köşedeki gördüğünüz **uygulamayı Güncelleştir**. İş arkadaşlarınız için uygulamanızı dağıtmaya hazır olduğunuzda nereden başlayacaksınız olmasıdır. 

    ![Zendesk içerik listesi](media/service-connect-to-zendesk/power-bi-zendesk-content-list.png)

2. Seçin **raporları** ve **veri kümeleri** çalışma alanındaki diğer öğeleri görmek için.

    Hakkında bilgi edinin [uygulama dağıtmaya](service-create-distribute-apps.md) iş arkadaşlarınıza önerilmesini sağlayın.

## <a name="system-requirements"></a>Sistem Gereksinimleri
Zendesk içerik paketine erişmek için bir Zendesk Yönetici hesabı gereklidir. Bir aracı veya bir son kullanıcıysanız ve Zendesk verilerinizi görüntülemek istiyorsanız, bir öneri ekleyip Zendesk bağlayıcısını gözden geçirin [Power BI Desktop](desktop-connect-to-data.md).

## <a name="finding-parameters"></a>Parametreleri bulma
Zendesk URL'niz, Zendesk hesabınızda oturum açmak için kullandığınız URL ile aynı olacaktır. Zendesk URL'nizin ne olduğundan emin değilseniz Zendesk [oturum açma yardımını](https://www.zendesk.com/login/) kullanabilirsiniz.

## <a name="troubleshooting"></a>Sorun giderme
Bağlanma sorunu yaşıyorsanız, Zendesk URL'nizi kontrol edin ve bir Zendesk yönetici hesabı kullandığınızı onaylayın.

## <a name="next-steps"></a>Sonraki adımlar

* [Power BI'da yeni çalışma alanları oluşturma](service-create-the-new-workspaces.md)
* [Power BI'da uygulamaları yükleme ve kullanma](consumer/end-user-apps.md)
* [Dış hizmetler için Power BI uygulamaları bağlanma](service-connect-to-services.md)
* Sorularınız mı var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

