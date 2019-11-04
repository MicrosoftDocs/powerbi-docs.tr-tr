---
title: Windows 10 için Power BI mobil uygulamasında SSRS mobil raporlarını ve KPI'lerini görüntüleme
description: Windows 10 için Power BI mobil uygulaması, önemli şirket içi iş bilgilerinize gerçek zamanlı ve dokunmatik kullanıma uygun mobil erişim olanağı sağlar.
author: mshenhav
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-mobile
ms.topic: conceptual
ms.date: 06/28/2018
ms.author: mshenhav
ms.openlocfilehash: 114cf65e8abb072ab3f0254cbd4041a43a31d1dc
ms.sourcegitcommit: d441d350504f8c6d9e100d229757add6237f0bef
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73059642"
---
# <a name="view-reporting-services-ssrs-mobile-reports-and-kpis-in-the-windows-10-power-bi-mobile-app"></a>Windows 10 Power BI mobil uygulamasında Reporting Services (SSRS) mobil raporlarını ve KPI'lerini görüntüleme
Windows 10 için Power BI mobil uygulaması, SQL Server 2016 Reporting Services'deki önemli şirket içi iş bilgilerinize gerçek zamanlı ve dokunmatik kullanıma uygun mobil erişim olanağı sağlar. 

![Reporting Services mobil raporları](././media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report.png)

## <a name="first-things-first"></a>İlk yapılacaklar
SQL Server 2016 Enterprise Edition Mobil Rapor Yayımcısı ile [Reporting Services mobil raporları oluşturun](https://msdn.microsoft.com/library/mt652547.aspx) ve bu raporları [Reporting Services web portalında](https://msdn.microsoft.com/library/mt637133.aspx) yayımlayın. Doğrudan web portalında KPI'ler oluşturun. İstediğinizde kolayca bulabilmek için bunları klasörler halinde düzenleyin ve sık kullandıklarınızı işaretleyin. 

Ardından, klasörler halinde düzenlenmiş veya sık kullanılanlar olarak bir araya getirilmiş mobil raporları ve KPI'leri Windows 10 için Power BI mobil uygulamasında görüntüleyin. 

> [!NOTE]
> Cihazınızın Windows 10'u çalıştırması gerekir. Uygulama, en az 1 GB RAM'e ve 8 GB iç depolama alanına sahip olan cihazlarda en iyi şekilde çalışır.
> 
> 

## <a name="explore-samples-without-a-sql-server-2016-reporting-services-server"></a>Bir SQL Server 2016 Reporting Services sunucusu olmadan örnekleri keşfetme
Reporting Services web portalına erişiminiz olmasa bile Reporting Services mobil raporlarının özelliklerini inceleyebilirsiniz.

1. Windows 10 cihazınızda Power BI uygulamasını açın.
2. Sol üst köşede bulunan genel gezinti düğmesine ![Genel gezinti düğmesi](././media/mobile-app-windows-10-ssrs-kpis-mobile-reports/powerbi_windows10_options_icon.png) dokunun.
3. **Ayarlar** simgesine ![Ayarlar simgesi](./././media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-settings-icon.png) dokunun, **Sunucuya bağlan** seçeneğine sağ tıklayın veya bu seçeneği basılı tutun, ardından **Örnekleri görüntüle**'ye dokunun.
   
   ![SSRS örneklerini görüntüleme](./media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-win10-connect-ssrs-samples.png)
4. Retail Reports veya Sales Reports klasörünü açarak ilgili KPI'leri ve mobil raporları keşfedin.
   
   ![Örnek KPI'ler ve mobil raporlar](./media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-win10-ssrs-sample-kpis.png)

KPI'ler ve mobil raporlarla etkileşim kurmak için örneklere göz atın.

## <a name="connect-to-a-reporting-services-report-server"></a>Bir Reporting Services rapor sunucusuna bağlanma
1. Sol gezinti çubuğunun alt kısmında bulunan **Ayarlar** simgesine ![Ayarlar simgesi](./././media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-settings-icon.png) dokunun
2. **Sunucuya bağlan**'a dokunun.
3. Sunucu adresinin yanı sıra kullanıcı adınızı ve parolanızı girin. Sunucu adresi için şu biçimi kullanın:
   
     `http://<servername>/reports` VEYA   `https://<servername>/reports`
   
   > [!NOTE]
   > Bağlantı dizesinin başına **http** veya **https** ifadesini ekleyin.
   > 
   > 
   
    Sunucuya istediğiniz adı vermek için **Gelişmiş seçenek**'e dokunun.
4. Bağlanmak için onay işaretine dokunun. 
   
   Artık sunucuyu sol gezinti çubuğunda görebilirsiniz.
   
   ![Sol gezinti çubuğundaki sunucu](./media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report-server.png)
   
   >[!TIP]
   >İstediğiniz zaman genel gezinti düğmesine ![Genel gezinti düğmesi](././media/mobile-app-windows-10-ssrs-kpis-mobile-reports/powerbi_windows10_options_icon.png) dokunarak Reporting Services mobil raporları ve Power BI hizmetindeki panolarınız arasında gezinebilirsiniz. 
   > 

## <a name="view-reporting-services-kpis-and-mobile-reports-in-the-power-bi-app"></a>Reporting Services KPI'lerini ve mobil raporlarını Power BI uygulamasında görüntüleme
Reporting Services KPI'leri ve mobil raporları, Reporting Services web portalındaki klasör düzeninde görüntülenir.

![Rapor klasörleri](./media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report-folders.png)

* Odak modunda görmek için bir KPI'ye dokunun.
  
    ![Odak modundaki KPI](./media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report-kpis.png)
* Power BI uygulamasında açmak ve etkileşim kurmak için bir mobil rapora dokunun.
  
    ![Reporting Services mobil raporu](././media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report.png)

## <a name="view-your-favorite-kpis-and-reports"></a>Sık kullandığınız KPI'leri ve raporları görüntüleme
Reporting Services web portalınızda sık kullanılan olarak işaretlediğiniz KPI'leri ve mobil raporları, Windows 10 cihazınızda kolayca ulaşabileceğiniz tek bir klasörde, sık kullanılan Power BI panolarınız ve raporlarınızla birlikte görüntüleyebilirsiniz.

* **Sık Kullanılanlar**'a dokunun.
  
   ![Sık Kullanılanlar simgesi](./media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-ssrs-mobile-report-favorite-menu.png)
  
   Web portalında sık kullanılan olarak işaretlediğiniz öğelerin tümü bu sayfada bulunur.
  
   ![Sık Kullanılanlar sayfası](./media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-windows-10-ssrs-favorites.png)

[Power BI mobil uygulamalarındaki sık kullanılanlar](mobile-apps-favorites.md) hakkında daha fazla bilgi edinin.

## <a name="remove-a-connection-to-a-report-server"></a>Rapor sunucusu bağlantısını kesme
Power BI mobil uygulamanızdan tek seferde yalnızca bir rapor sunucusuna bağlanabilirsiniz. Farklı bir sunucuya bağlanmak isterseniz geçerli sunucu bağlantısını kesmeniz gerekir.

1. Sol gezinti çubuğunun alt kısmında bulunan **Ayarlar** simgesine ![Ayarlar simgesi](./././media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-settings-icon.png) dokunun.
2. Bağlantısını kesmek istediğiniz sunucunun adını basılı tutun.
3. **Sunucuyu kaldır**'a dokunun.
   
    ![Sunucuyu kaldır](./media/mobile-app-windows-10-ssrs-kpis-mobile-reports/power-bi-windows-10-ssrs-remove-server-menu.png)

## <a name="create-reporting-services-mobile-reports-and-kpis"></a>Reporting Services mobil raporları ve KPI'leri oluşturma
Reporting Services KPI'leri ve mobil raporları Power BI mobil uygulamasında oluşturulmaz. Bunlar, SQL Server Mobil Rapor Yayımcısı ve bir SQL Server 2016 Reporting Services web portalında oluşturulur.

* [Kendi Reporting Services mobil raporlarınızı oluşturun](https://msdn.microsoft.com/library/mt652547.aspx) ve bu raporları bir Reporting Services web portalında yayımlayın.
* [Bir Reporting Services web portalında KPI](https://msdn.microsoft.com/library/mt683632.aspx) oluşturma

## <a name="next-steps"></a>Sonraki adımlar
* [Windows 10 için Power BI mobil uygulamasını kullanmaya başlama](mobile-windows-10-phone-app-get-started.md)  
* [Power BI nedir?](../../fundamentals/power-bi-overview.md)  
* Sorularınız mı var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

