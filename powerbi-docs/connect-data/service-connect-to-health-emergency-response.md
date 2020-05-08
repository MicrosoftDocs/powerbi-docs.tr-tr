---
title: Hastanede Acil Durum Yanıtlamada Karar Desteği Panosuna Bağlanma
description: Sağlık hizmetlerindeki acil durumlara yönelik şablon uygulaması için COVID-19 Karar Desteği Panosunu edinme ve yükleme, verilere bağlanma
author: paulinbar
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: conceptual
ms.date: 04/06/2020
ms.author: painbar
LocalizationGroup: Connect to services
ms.openlocfilehash: b951e96a5d81603dc91e4fc47a2b412d4140f85d
ms.sourcegitcommit: 7aa0136f93f88516f97ddd8031ccac5d07863b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/05/2020
ms.locfileid: "80752062"
---
# <a name="connect-to-the-hospital-emergency-response-decision-support-dashboard"></a>Hastanede Acil Durum Yanıtlamada Karar Desteği Panosuna Bağlanma
Hastanede Acil Durum Yanıtlamada Karar Desteği Panosu şablon uygulaması, [Sağlık hizmetlerinde acil müdahale için Microsoft Power Platform çözümünün](https://powerapps.microsoft.com/blog/emergency-response-solution-a-microsoft-power-platform-solution-for-healthcare-emergency-response/) raporlama bileşenidir. Sağlık sistemleri genelindeki verileri toplayan bu pano, acil durum yöneticilerinin zamanında ve doğru kararlar almasına yardımcı olur.

![Hastanede Acil Durum Yanıtlamada Karar Desteği Panosu uygulama raporu](media/service-connect-to-health-emergency-response/service-health-emergency-response-app-report.png)

Bu makalede, uygulamayı yükleme ve veri kaynaklarına bağlanma işlemleri açıklanır. Bu uygulamada göreceğiniz raporu kullanmayı öğrenmek için bkz. [Hastanede Acil Durum Yanıtlamada Karar Desteği Panosu belgeleri](https://docs.microsoft.com/powerapps/sample-apps/emergency-response/deploy-configure#view-the-power-bi-dashboard).

Şablon uygulamasını yükleyip veri kaynaklarına bağlandıktan sonra, raporu ihtiyaçlarınıza göre özelleştirebilirsiniz. Daha sonra bunu, kuruluşunuzdaki iş arkadaşlarınıza bir uygulama olarak dağıtabilirsiniz.

## <a name="prerequisites"></a>Önkoşullar

Bu şablon uygulamasını yüklemeden önce [Hastane Acil Durum Yanıtı Power Platform çözümünü](https://docs.microsoft.com/powerapps/sample-apps/emergency-response/deploy-configure) yükleyip ayarlamanız gerekir. Bu çözüm yüklendiğinde, uygulamayı verilerle doldurmak için gereken veri kaynağı başvuruları oluşturulur.

Hastane Acil Durum Yanıtı Power Platform çözümünü yüklerken [Common Data Service ortam örneğinizin URL’sini](https://docs.microsoft.com/powerapps/sample-apps/emergency-response/deploy-configure#publish-the-power-bi-dashboard) not edin. Şablon uygulamasını verilere bağlamak için bu URL’ye ihtiyacınız olacak.

## <a name="install-the-app"></a>Uygulamayı yükleme

1. Uygulamaya ulaşmak için aşağıdaki bağlantıya tıklayın: [Hastanede Acil Durum Yanıtlamada Karar Desteği Panosu şablon uygulaması](https://appsource.microsoft.com/en-us/product/power-bi/pbi-contentpacks.powerapps_healthcare)

1. Uygulamanın AppSource sayfasında [**ŞİMDİ EDİNİN**](https://appsource.microsoft.com/en-us/product/power-bi/pbi-contentpacks.powerapps_healthcare)’i seçin.

    [![AppSource’ta Hastanede Acil Durum Yanıtlamada Karar Desteği Panosu uygulaması](media/service-connect-to-health-emergency-response/service-health-emergency-response-app-appsource-get-it-now.png)](https://appsource.microsoft.com/en-us/product/power-bi/pbi-contentpacks.powerapps_healthcare)

1. **Bir şey daha ...** penceresindeki bilgileri okuyup **Devam et**’i seçin.

    ![Hastanede Acil Durum Yanıtlamada Karar Desteği Panosu uygulama raporu, Bir şey daha... seçeneği](media/service-connect-to-health-emergency-response/service-health-emergency-response-1-more-thing.png)

1. **Yükle**'yi seçin. 

    ![Hastanede Acil Durum Yanıtlamada Karar Desteği Panosu uygulamasını yükleme](media/service-connect-to-health-emergency-response/service-health-emergency-response-select-install.png)

    Uygulamayı yükledikten sonra Uygulamalarınız sayfasında görebilirsiniz.

   ![Hastanede Acil Durum Yanıtlamada Karar Desteği Panosu uygulaması](media/service-connect-to-health-emergency-response/service-health-emergency-response-app-apps-page-icon.png)

## <a name="connect-to-data-sources"></a>Veri kaynaklarına bağlanma

1. Uygulamanızı açmak için Uygulamalar sayfanızdaki simgeyi seçin.

1. Karşılama ekranında **Keşfet**’i seçin.

   ![Şablon uygulaması karşılama ekranı](media/service-connect-to-health-emergency-response/service-health-emergency-response-app-splash-screen.png)

   Uygulama, örnek verileri göstererek açılır.

1. Sayfanın üst kısmındaki başlıkta yer alan **Verilerinize bağlanın** seçeneğini belirleyin.

   ![Hastanede Acil Durum Yanıtlamada Karar Desteği Panosu uygulaması, verilerinize bağlanma bağlantısı](media/service-connect-to-health-emergency-response/service-health-emergency-response-app-connect-data.png)

1. İletişim kutusunda:
   1. Kuruluş adı alanına kuruluşunuzun adını (ör. “Contoso Sağlık Sistemleri”) girin. Bu alan isteğe bağlıdır. Bu ad, panonun sol üst kısmında görünür.
   1. CDS_base_solution alanına [Common Data Service ortam örneğinizin URL’sini](https://docs.microsoft.com/powerapps/sample-apps/emergency-response/deploy-configure#publish-the-power-bi-dashboard) yazın. Örneğin: https://[myenv].crm.dynamics.com. İşiniz bittiğinde **İleri**’ye tıklayın.

   ![Hastanede Acil Durum Yanıtlamada Karar Desteği Panosu uygulaması, URL iletişim kutusu](media/service-connect-to-health-emergency-response/service-health-emergency-response-app-url-dialog.png)

1. Karşınıza çıkan sonraki iletişim kutusunda, kimlik doğrulaması yöntemini **OAuth2** olarak belirleyin. Gizlilik düzeyi ayarlarında bir şey yapmanız gerekmez.

   **Oturum aç**'ı seçin.

   ![Hastanede Acil Durum Yanıtlamada Karar Desteği Panosu uygulaması, kimlik doğrulaması iletişim kutusu](media/service-connect-to-health-emergency-response/service-health-emergency-response-app-authentication-dialog.png)

1. Microsoft oturum açma ekranında, Power BI’da oturum açın.

   ![Microsoft oturum açma ekranı](media/service-connect-to-health-emergency-response/service-health-emergency-response-app-microsoft-login.png)

   Oturum açtıktan sonra rapor veri kaynaklarına bağlanıp güncel verilerle doldurulur. Bu sırada, etkinlik izleyicisi açılır.

   ![Hastanede Acil Durum Yanıtlamada Karar Desteği Panosu uygulaması, yenileme sürüyor](media/service-connect-to-health-emergency-response/service-health-emergency-response-app-refresh-monitor.png)

## <a name="schedule-report-refresh"></a>Rapor yenilemeyi zamanlama

Veri yenileme tamamlandığında, raporu güncel tutmak için [yenileme zamanlaması belirleyin](../refresh-scheduled-refresh.md).

1. Üst başlık çubuğunda **Power BI**’ı seçin.

   ![Power BI içerik haritası](media/service-connect-to-health-emergency-response/service-health-emergency-response-app-powerbi-breadcrumb.png)

1. Sol gezinti bölmesinde, **Çalışma Alanları** bölümünde Hastanede Acil Durum Yanıtlamada Karar Desteği Panosu çalışma alanını bulup [Zamanlanan yenileme yapılandırma](../refresh-scheduled-refresh.md) makalesinde açıklanan yönergeleri izleyin.

## <a name="customize-and-share"></a>Özelleştirin ve paylaşın

Ayrıntılar için bkz. [Uygulamayı özelleştirme ve paylaşma](../service-template-apps-install-distribute.md#customize-and-share-the-app). Uygulamayı yayımlamadan veya dağıtmadan önce [rapor sorumluluk reddini](../create-reports/sample-covid-19-us.md#disclaimers) gözden geçirdiğinizden emin olun.

## <a name="next-steps"></a>Sonraki adımlar
* [Hastane Acil Durum Yanıtı raporunu anlama](https://docs.microsoft.com/powerapps/sample-apps/emergency-response/deploy-configure#view-the-power-bi-dashboard)
* [Power Apps’teki Kriz İletişimi örnek şablonunu ayarlama ve bunun hakkında bilgi edinme](https://docs.microsoft.com/powerapps/maker/canvas-apps/sample-crisis-communication-app)
* Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
* [Power BI şablon uygulamaları nedir?](../service-template-apps-overview.md)
* [Kuruluşunuzda şablon uygulamalarını yükleme ve dağıtma](../service-template-apps-install-distribute.md)
