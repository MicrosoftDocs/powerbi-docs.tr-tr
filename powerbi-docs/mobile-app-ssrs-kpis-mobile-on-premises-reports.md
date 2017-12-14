---
title: "Power BI mobil uygulamalarında şirket içi raporları ve KPI'leri görüntüleme"
description: "Power BI mobil uygulamaları, SQL Server Reporting Services ve Power BI Rapor Sunucusu'nda bulunan şirket içi iş bilgilerinize yönelik gerçek zamanlı ve dokunmatik kullanıma uygun mobil erişim sağlar."
services: powerbi
documentationcenter: 
author: maggiesMSFT
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/13/2017
ms.author: maggies
ms.openlocfilehash: 99fceab5904deaa510edd213c349dcfb2e38ac28
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2017
---
# <a name="view-on-premises-report-server-reports-and-kpis-in-the-power-bi-mobile-apps"></a>Power BI mobil uygulamalarında şirket içi rapor sunucusu raporlarını ve KPI'lerini görüntüleme
Aşağıdakiler için geçerlidir:

| ![iPhone](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/iphone-logo-50-px.png) | ![iPad](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/ipad-logo-50-px.png) | ![Android telefon](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/android-phone-logo-50-px.png) | ![Android tablet](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/android-tablet-logo-50-px.png) |
|:--- |:--- |:--- |:--- |
| iPhone'lar |iPad'ler |Android telefonlar |Android tabletler |

Power BI mobil uygulamaları, Power BI Rapor Sunucusu ve SQL Server 2016 Reporting Services'de (SSRS) bulunan şirket içi iş bilgilerinize yönelik gerçek zamanlı ve dokunmatik kullanıma uygun mobil erişim sağlar. 

 ![Mobil uygulamalarda Rapor Sunucusu giriş sayfası](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ipad-pbi-report-server-home.png)

## <a name="first-things-first"></a>İlk yapılacaklar
**Mobil uygulamalar, Power BI içeriklerinizi oluşturduğunuz değil, görüntülediğiniz yerdir.**

* Siz ve kuruluşunuzda rapor oluşturan diğer kişiler, [Power BI Desktop'ı kullanarak Power BI raporları oluşturur ve bu raporları Power BI Rapor Sunucusu](report-server/quickstart-create-powerbi-report.md) web portalında yayımlarsınız. 
* [KPI'leri doğrudan web portalında](https://docs.microsoft.com/sql/reporting-services/working-with-kpis-in-reporting-services) oluşturur, klasörler halinde düzenler, sık kullandıklarınızı işaretler ve istediğinizde kolayca bulabilirsiniz. 
* SQL Server 2016 Enterprise Edition Mobil Rapor Yayımcısı ile [Reporting Services mobil raporları oluşturur](https://docs.microsoft.com/sql/reporting-services/mobile-reports/create-mobile-reports-with-sql-server-mobile-report-publisher) ve bu raporları [Reporting Services web portalında](https://docs.microsoft.com/sql/reporting-services/web-portal-ssrs-native-mode) yayımlarsınız.  

Ardından, Power BI mobil uygulamalarında beş adede kadar rapor sunucusuna bağlanarak Power BI raporlarını ve KPI'lerini klasörler halinde düzenlenmiş veya sık kullanılanlar olarak bir araya getirilmiş şekilde görüntüleyebilirsiniz. 

## <a name="explore-samples-in-the-mobile-apps-without-a-server-connection"></a>Sunucu bağlantısı olmadan mobil uygulamalardaki örnekleri inceleme
Reporting Services web portalına erişiminiz olmasa bile Reporting Services mobil raporlarının ve KPI'lerinin özelliklerini inceleyebilirsiniz. 

1. Sol üst köşede bulunan genel gezinti düğmesine ![Genel gezinti düğmesi](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-global-nav-button.png) ve ardından sağ üst köşedeki dişli simgesine ![Dişli simgesi](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ios-settings-icon.png)dokunun.
2. **Reporting Services Örnekleri**'ne dokunup sayfaya göz atarak örnek KPI'ler ve mobil raporlarla etkileşime geçin.
   
   ![Reporting Services örnekleri](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-ssrs-samples.png)

## <a name="connect-to-an-on-premises-server"></a>Şirket içindeki bir sunucuya bağlanma
Power BI mobil uygulamalarında şirket içi Power BI raporlarını, Reporting Services mobil raporlarını ve KPI'leri görüntüleyebilirsiniz. 

1. Mobil cihazınızda Power BI uygulamasını açın.
2. Henüz Power BI'da oturum açmadıysanız **Rapor Sunucusu**'na dokunun.
   
   ![Rapor sunucusunda oturum açma](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-connect-to-rs-login.png)
   
   Power BI uygulamasında oturum açtıysanız genel gezinti düğmesine ![Genel gezinti düğmesi](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-global-nav-button.png)ve ardından, sağ üst köşedeki dişli simgesine ![Dişli simgesi](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ios-settings-icon.png) dokunun.
3. **Sunucuya bağlan**'a dokunun.
   
    ![Sunucuya bağlan](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-android-server-sign-in.png)
4. Sunucu adresinin yanı sıra kullanıcı adınızı ve parolanızı girin. Sunucu adresi için şu biçimi kullanın:
   
     `http://<servername>/reports`
   
     VEYA
   
     `https://<servername>/reports`
   
   > [!NOTE]
   > Bağlantı dizesinin önüne **http** veya **https** ifadesini ekleyin.
   > 
   > 
   
    ![Sunucuya bağlan iletişim kutusu](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ios-connect-to-server-dialog.png)
5. (İsteğe bağlı) Dilerseniz **Advanced options** (Gelişmiş seçenekler) bölümünde sunucunuza kolay bir ad verebilirsiniz.
6. Artık sol gezinti çubuğunda sunucunuzu görebilirsiniz. Bu örnekte sunucuyu "power bi report server" olarak adlandırdık.
   
   ![Sol gezinti bölmesindeki rapor sunucusu](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-left-nav-report-server.png)

## <a name="view-power-bi-reports-and-kpis-in-the-power-bi-app"></a>Power BI uygulamasında Power BI raporlarını ve KPI'lerini görüntüleme
Power BI raporları, Reporting Services mobil raporları ve KPI'ler, Reporting Services web portalındaki klasör düzeninde görüntülenir. 

* Bir Power BI raporuna ![Power BI raporu simgesi](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-rs-mobile-report-icon.png)dokunun. Rapor yatay modda açılır ve Power BI uygulamasında raporla etkileşime geçebilirsiniz.
  
    ![Power BI raporu](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-iphone-report-server-report.png)
* Rapor sahipleri Power BI Desktop'ta, [bir raporu Power BI mobil uygulamaları için en iyi duruma getirebilir](desktop-create-phone-report.md). En iyi duruma getirilmiş raporlar cep telefonunuzda özel bir simge, ![En iyi duruma getirilmiş Power BI raporu simgesi](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-rs-mobile-optimized-icon.png) ve düzenle gösterilir.
  
    ![Mobil uygulamalar için en iyi duruma getirilmiş Power BI raporu](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-rs-mobile-optimized-report.png)
* Odak modunda görmek için bir KPI'ye dokunun.
  
    ![Odak modunda KPI](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/pbi_ipad_ssmrp_tile.png)

## <a name="view-your-favorite-kpis-and-reports"></a>Sık kullandığınız KPI'leri ve raporları görüntüleme
Web portalında KPI'leri ve raporları sık kullanılanlara ekleyip daha sonra bunları mobil cihazınızda tek bir klasörde, sık kullanılan Power BI panolarınızla birlikte görüntüleyebilirsiniz.

* **Sık Kullanılanlar**'a dokunun.
  
   ![Sol gezinti bölmesindeki Sık Kullanılanlar seçeneği](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ipad-faves-pbi-report-server.png)
  
   Web portalında sık kullandığınız KPI ve raporlarınızın tümü, Power BI hizmetindeki Power BI panoları ile birlikte bu sayfada yer alır:
  
   ![Sık Kullanılanlar sayfasındaki Power BI raporları ve panoları](media/mobile-app-ssrs-kpis-mobile-on-premises-reports/power-bi-ipad-favorites.png)

## <a name="remove-a-connection-to-a-report-server"></a>Rapor sunucusu bağlantısını kesme
1. Sol gezinti çubuğunun alt kısmında bulunan **Ayarlar**'a dokunun.
2. Bağlantısını kesmek istediğiniz sunucunun adına dokunun.
3. **Sunucuyu Kaldır**'a dokunun.

## <a name="next-steps"></a>Sonraki adımlar
* [Power BI ile çalışmaya başlama](service-get-started.md)  
* Sorularınız mı var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

