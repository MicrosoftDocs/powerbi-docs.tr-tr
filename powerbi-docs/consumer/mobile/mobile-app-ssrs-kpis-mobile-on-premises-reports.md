---
title: Power BI mobil uygulamalarında şirket içi raporları ve KPI'leri görüntüleme
description: Power BI mobil uygulamaları, SQL Server Reporting Services ve Power BI Rapor Sunucusu'nda bulunan şirket içi iş bilgilerinize yönelik gerçek zamanlı ve dokunmatik kullanıma uygun mobil erişim sağlar.
author: paulinbar
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: how-to
ms.date: 12/05/2019
ms.author: painbar
ms.openlocfilehash: e9f3b41e9c8435008f732d215ae022d6a023574d
ms.sourcegitcommit: 7e99e8af9caf9340958c4607a94728d43e8c3811
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2020
ms.locfileid: "91668586"
---
# <a name="view-on-premises-report-server-reports-and-kpis-in-the-power-bi-mobile-apps"></a>Power BI mobil uygulamalarında şirket içi rapor sunucusu raporlarını ve KPI'lerini görüntüleme

Power BI mobil uygulamaları, Power BI Rapor Sunucusu ve SQL Server 2016 Reporting Services'de (SSRS) bulunan şirket içi iş bilgilerinize yönelik gerçek zamanlı ve dokunmatik kullanıma uygun mobil erişim sağlar.

Aşağıdakiler için geçerlidir:

| ![iPhone](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/iphone-logo-50-px.png) | ![iPad](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/ipad-logo-50-px.png) | ![Android telefon](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/android-phone-logo-50-px.png) | ![Android tablet](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/android-tablet-logo-50-px.png) |
|:--- |:--- |:--- |:--- |
| iPhone'lar |iPad'ler |Android telefonlar |Android tabletler |


![Mobil uygulamalarda Rapor Sunucusu giriş sayfası](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ipad-pbi-report-server-home.png)

## <a name="first-things-first"></a>İlk yapılacaklar
**Mobil uygulamalar, Power BI içeriklerinizi oluşturduğunuz değil, görüntülediğiniz yerdir.**

* Siz ve kuruluşunuzda rapor oluşturan diğer kişiler, [Power BI Desktop'ı kullanarak Power BI raporları oluşturur ve bu raporları Power BI Rapor Sunucusu](../../report-server/quickstart-create-powerbi-report.md) web portalında yayımlarsınız. 
* [KPI'leri doğrudan web portalında](/sql/reporting-services/working-with-kpis-in-reporting-services) oluşturur, klasörler halinde düzenler, sık kullandıklarınızı işaretler ve istediğinizde kolayca bulabilirsiniz. 
* SQL Server 2016 Enterprise Edition Mobil Rapor Yayımcısı ile [Reporting Services mobil raporları oluşturur](/sql/reporting-services/mobile-reports/create-mobile-reports-with-sql-server-mobile-report-publisher) ve bu raporları [Reporting Services web portalında](/sql/reporting-services/web-portal-ssrs-native-mode) yayımlarsınız.  

Ardından, Power BI mobil uygulamalarında beş adede kadar rapor sunucusuna bağlanarak Power BI raporlarını ve KPI'lerini klasörler halinde düzenlenmiş veya sık kullanılanlar olarak bir araya getirilmiş şekilde görüntüleyebilirsiniz. 

## <a name="explore-samples-in-the-mobile-apps-without-a-server-connection"></a>Sunucu bağlantısı olmadan mobil uygulamalardaki örnekleri inceleme
Reporting Services web portalına erişiminiz olmasa bile Reporting Services mobil raporlarının ve KPI'lerinin özelliklerini inceleyebilirsiniz. 

1. Sol üst köşedeki profil resminize dokunun ve sonra da beliren hesaplar panelinde **Ayarlar**'a dokunun.

2. Açılan ayarlar sayfasında **Reporting Services Örnekleri**'ne dokunup sayfaya göz atarak örnek KPI'ler ve mobil raporlarla etkileşime geçin.
   
   ![Reporting Services örnekleri](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-ssrs-samples.png)

## <a name="connect-to-an-on-premises-report-server"></a>Şirket içi rapor sunucusuna bağlanma
Power BI mobil uygulamalarında şirket içi Power BI raporlarını, Reporting Services mobil raporlarını ve KPI'leri görüntüleyebilirsiniz. 

1. Mobil cihazınızda Power BI uygulamasını açın.
2. Henüz Power BI'da oturum açmadıysanız **Rapor Sunucusu**'na dokunun.
   
   ![Rapor sunucusunda oturum açma](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-connect-to-rs-login.png)
   
   Power BI uygulamasında zaten oturum açmış durumdaysanız, sol üst köşedeki profil resminize dokunun ve sonra da beliren hesaplar panelinde **Ayarlar**'a dokunun.
3. Açılan ayarlar sayfasında **Sunucuya bağlan**'a dokunun.
   
    ![Sunucuya bağlan](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-android-server-sign-in.png)

    Mobil uygulamanın sunucuya bir şekilde erişmesi gerekir. Bunu yapmanın birkaç yolu vardır:
     * Aynı ağda olmak/VPN kullanmak en kolay yöntemdir.
     * Kuruluş dışından bağlantı kurmak için Web Uygulaması Ara Sunucusu kullanabilirsiniz. Ayrıntılar için bkz. [OAuth kullanarak Reporting Services'e bağlanma](mobile-oauth-ssrs.md).
     * Güvenlik duvarında bir bağlantı (bağlantı noktası) açma.

4. Sunucu adresini girin ve isterseniz sunucuya kolay bir ad verin. Sunucu adresi için şu biçimi kullanın:
   
     `https://<servername>/reports`
   
     VEYA
   
     `https://<servername>/reports`
   
   Bağlantı dizesinin önüne **http** veya **https** ifadesini ekleyin.
   
    ![Sunucuya bağlan iletişim kutusu](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ios-connect-to-server-dialog.png)
5. Sunucu adresini ve isteğe bağlı olarak kolay adı yazdıktan sonra **Bağlan**'a dokunun ve istendiğinde kullanıcı adınızı ve parolanızı girin.
6. Artık Hesaplar bölmesinde sunucunuzu görürsünüz. Bu örnekte sunucu "Work server" olarak adlandırılmıştır.
   
   ![Gezinti bölmesindeki rapor sunucusu](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-left-nav-report-server.png)

## <a name="connect-to-an-on-premises-report-server-in-ios-or-android"></a>iOS veya Android'de şirket içi rapor sunucusuna bağlanma

Power BI’yı iOS veya Android mobil uygulamasında görüntülüyorsanız BT yöneticiniz bir uygulama yapılandırma ilkesi tanımlamış olabilir. Tanımlamışsa, rapor sunucusuna bağlanma deneyiminiz daha kolay olur ve bir rapor sunucusuna bağlandığınızda sağladığınız kadar fazla bilgi vermeniz gerekmez. 

1. Mobil uygulamanızın bir rapor sunucusu ile yapılandırıldığına dair bir ileti görürsünüz. **Oturum aç**’a dokunun.

    ![Rapor sunucusunda oturum açma](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-config-server-sign-in.png)

2.  **Sunucuya bağlan** sayfasında rapor sunucusu ayrıntıları zaten doldurulmuştur. **Bağlan**’a dokunun.

    ![Doldurulmuş rapor sunucusu ayrıntıları](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ios-remote-configure-connect-server.png)

3. Kimlik doğrulaması için bir parola girip **Oturum aç**’a dokunun. 

    ![Oturum aç düğmesini ve parola girişini gösteren ekran görüntüsü.](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-config-server-address.png)

Artık KPI’leri ve rapor sunucusunda depolanmış Power BI raporlarını görüntüleyebilir ve etkileşimde bulunabilirsiniz.

## <a name="view-power-bi-reports-and-kpis-in-the-power-bi-app"></a>Power BI uygulamasında Power BI raporlarını ve KPI'lerini görüntüleme
Power BI raporları, Reporting Services mobil raporları ve KPI'ler, Reporting Services web portalındaki klasör düzeninde görüntülenir. 

* Bir Power BI raporuna ![Power BI raporu simgesi](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-rs-mobile-report-icon.png)dokunun. Rapor yatay modda açılır ve Power BI uygulamasında raporla etkileşime geçebilirsiniz.

    > [!NOTE]
  > Power BI Rapor Sunucusu'nda Power BI raporlarında şu anda detaya gitme ve detaydan çıkma etkin değildir.
  
    ![Power BI raporu](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-report-server-report.png)
* Rapor sahipleri Power BI Desktop'ta, [bir raporu Power BI mobil uygulamaları için en iyi duruma getirebilir](../../create-reports/desktop-create-phone-report.md). En iyi duruma getirilmiş raporlar cep telefonunuzda özel bir simge, ![En iyi duruma getirilmiş Power BI raporu simgesi](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-rs-mobile-optimized-icon.png) ve düzenle gösterilir.
  
    ![Mobil uygulamalar için en iyi duruma getirilmiş Power BI raporu](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-rs-mobile-optimized-report.png)
* Odak modunda görmek için bir KPI'ye dokunun.
  
    ![Odak modundaki KPI](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/pbi_ipad_ssmrp_tile.png)

## <a name="view-your-favorite-kpis-and-reports"></a>Sık kullandığınız KPI'leri ve raporları görüntüleme
Web portalında KPI'leri ve raporları sık kullanılanlara ekleyip daha sonra bunları mobil cihazınızda tek bir klasörde, sık kullanılan Power BI panolarınızla birlikte görüntüleyebilirsiniz.

* Gezinti çubuğunda **Sık Kullanılanlar**'a dokunun.
  
   ![Gezinti bölmesinde Sık Kullanılanlar](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ipad-faves-pbi-report-server-update.png)
  
   Web portalında sık kullandığınız KPI ve raporlarınızın tümü, Power BI hizmetindeki Power BI panoları ile birlikte bu sayfada yer alır:
  
   ![Sık Kullanılanlar sayfasındaki Power BI raporları ve panoları](./media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ipad-favorites.png)

## <a name="remove-a-connection-to-a-report-server"></a>Rapor sunucusu bağlantısını kesme
1. Hesaplar bölmesini açın ve **Ayarlar**'a dokunun.
2. Bağlantısını kesmek istediğiniz sunucunun adına dokunun.
3. **Sunucuyu Kaldır**'a dokunun.

## <a name="next-steps"></a>Sonraki adımlar
* [Power BI nedir?](../../fundamentals/power-bi-overview.md)  
* Sorular? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)