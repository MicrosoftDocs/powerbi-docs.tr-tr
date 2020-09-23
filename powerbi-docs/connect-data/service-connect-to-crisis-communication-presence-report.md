---
title: Kriz İletişimi Durum Raporu’na Bağlanma
description: COVID-19 Kriz İletişimi Durum Raporu şablon uygulamasını edinme ve yükleme, verilere bağlanma
author: paulinbar
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: how-to
ms.date: 04/06/2020
ms.author: painbar
LocalizationGroup: Connect to services
ms.openlocfilehash: 97501fe6e5a3e12e1b6773ce1b3fd67b503bf0f1
ms.sourcegitcommit: 9350f994b7f18b0a52a2e9f8f8f8e472c342ea42
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90860314"
---
# <a name="connect-to-the-crisis-communication-presence-report"></a>Kriz İletişimi Durum Raporu’na Bağlanma

Bu Power BI uygulaması, Kriz İletişimi için Microsoft Power Platform çözümündeki rapor/pano yapıtıdır. Kriz İletişimi uygulaması kullanıcıları için çalışanların konumunu izler. Çözüm Power Apps, Power Automate, Teams, SharePoint ve Power BI’ın özelliklerini bir araya getirir. Web üzerinde, mobilde veya Teams’de kullanılabilir.

![Kriz İletişimi Durum Raporu uygulama raporu](media/service-connect-to-crisis-communication-presence-report/service-crisis-communication-presence-report.png)

Sağlık sistemleri genelindeki verileri toplayan bu pano, acil durum yöneticilerinin zamanında ve doğru kararlar almasına yardımcı olur.

Bu makalede, uygulamayı yükleme ve veri kaynaklarına bağlanma işlemleri açıklanır. Kriz İletişimi uygulaması hakkında daha fazla bilgi için bkz. [Power Apps’te Kriz İletişimi örnek şablonunu ayarlama ve bunun hakkında bilgi edinme](/powerapps/maker/canvas-apps/sample-crisis-communication-app)

Şablon uygulamasını yükleyip veri kaynaklarına bağlandıktan sonra, raporu ihtiyaçlarınıza göre özelleştirebilirsiniz. Daha sonra bunu, kuruluşunuzdaki iş arkadaşlarınıza bir uygulama olarak dağıtabilirsiniz.

## <a name="prerequisites"></a>Önkoşullar

Bu şablon uygulamasını yüklemeden önce, [Kriz İletişimi örneğini](/powerapps/maker/canvas-apps/sample-crisis-communication-app) yükleyip ayarlamanız gerekir. Bu çözüm yüklendiğinde, uygulamayı verilerle doldurmak için gereken veri kaynağı başvuruları oluşturulur.

Kriz İletişimi örneğini yüklerken [“CI_Employee Status” SharePoint listesi klasör yolunu ve liste kimliğini](/powerapps/maker/canvas-apps/sample-crisis-communication-app#monitor-office-absences-with-power-bi) not edin.

## <a name="install-the-app"></a>Uygulamayı yükleme

1. Uygulamaya ulaşmak için aşağıdaki bağlantıya tıklayın: [Kriz İletişimi Durum Raporu şablon uygulaması](https://appsource.microsoft.com/en-us/product/power-bi/pbi-contentpacks.crisiscomms)

1. Uygulamanın AppSource sayfasında [**ŞİMDİ EDİNİN**](https://appsource.microsoft.com/en-us/product/power-bi/pbi-contentpacks.crisiscomms)’i seçin.

    [![AppSource’ta Kriz İletişimi Durum Raporu uygulaması](media/service-connect-to-crisis-communication-presence-report/service-crisis-communication-presence-report-app-appsource-get-it-now.png)](https://appsource.microsoft.com/en-us/product/power-bi/pbi-contentpacks.crisiscomms)

1. **Bir şey daha ...** penceresindeki bilgileri okuyup **Devam et**’i seçin.

    ![Kriz İletişimi Durum Raporu uygulaması, Bir şey daha... penceresi](media/service-connect-to-crisis-communication-presence-report/service-crisis-communication-presence-report-1-more-thing.png)

1. **Yükle**'yi seçin. 

    ![Kriz İletişimi Durum Raporu uygulamasını yükleme](media/service-connect-to-crisis-communication-presence-report/service-crisis-communication-presence-report-select-install.png)

    Uygulamayı yükledikten sonra Uygulamalarınız sayfasında görebilirsiniz.

   ![Uygulama sayfasında Kriz İletişimi Durum Raporu uygulaması](media/service-connect-to-crisis-communication-presence-report/service-crisis-communication-presence-report-app-apps-page-icon.png)

## <a name="connect-to-data-sources"></a>Veri kaynaklarına bağlanma

1. Uygulamanızı açmak için Uygulamalar sayfanızdaki simgeyi seçin.

1. Karşılama ekranında **Keşfet**’i seçin.

   ![Şablon uygulaması karşılama ekranı](media/service-connect-to-crisis-communication-presence-report/service-crisis-communication-presence-report-app-splash-screen.png)

   Uygulama, örnek verileri göstererek açılır.

1. Sayfanın üst kısmındaki başlıkta yer alan **Verilerinize bağlanın** seçeneğini belirleyin.

   ![Kriz İletişimi Durum Raporu uygulaması, verilerinize bağlanın bağlantısı](media/service-connect-to-crisis-communication-presence-report/service-crisis-communication-presence-report-app-connect-data.png)

1. İletişim kutusunda:
   1. SharePoint_Folder alanına [“CI_Employee Status” SharePoint listesi yolunu](/powerapps/maker/canvas-apps/sample-crisis-communication-app#monitor-office-absences-with-power-bi) girin.
   1. List_ID alanına, liste ayarlarından aldığınız liste kimliğinizi girin. İşiniz bittiğinde **İleri**’ye tıklayın.

   ![Kriz İletişimi Durum Raporu uygulaması URL iletişim kutusu](media/service-connect-to-crisis-communication-presence-report/service-crisis-communication-presence-report-app-url-dialog.png)

1. Karşınıza çıkan sonraki iletişim kutusunda, kimlik doğrulaması yöntemini **OAuth2** olarak belirleyin. Gizlilik düzeyi ayarlarında bir şey yapmanız gerekmez.

   **Oturum aç**'ı seçin.

   ![Kriz İletişimi Durum Raporu uygulaması kimlik doğrulaması iletişim kutusu](media/service-connect-to-crisis-communication-presence-report/service-crisis-communication-presence-report-app-authentication-dialog.png)

1. Microsoft oturum açma ekranında, Power BI’da oturum açın.

   ![Microsoft oturum açma ekranı](media/service-connect-to-crisis-communication-presence-report/service-crisis-communication-presence-report-app-microsoft-login.png)

   Oturum açtıktan sonra rapor veri kaynaklarına bağlanıp güncel verilerle doldurulur. Bu sırada, etkinlik izleyicisi açılır.

   ![Kriz İletişimi Durum Raporu uygulaması yenileme sürüyor](media/service-connect-to-crisis-communication-presence-report/service-crisis-communication-presence-report-app-refresh-monitor.png)

## <a name="schedule-report-refresh"></a>Rapor yenilemeyi zamanlama

Veri yenileme tamamlandığında, raporu güncel tutmak için [yenileme zamanlaması belirleyin](../connect-data/refresh-scheduled-refresh.md).

1. Üst başlık çubuğunda **Power BI**’ı seçin.

   ![Power BI içerik haritası](media/service-connect-to-crisis-communication-presence-report/service-crisis-communication-presence-report-app-powerbi-breadcrumb.png)

1. Sol gezinti bölmesinde, **Çalışma Alanları** bölümünde Hastanede Acil Durum Yanıtlamada Karar Desteği Panosu çalışma alanını bulup [Zamanlanan yenileme yapılandırma](../connect-data/refresh-scheduled-refresh.md) makalesinde açıklanan yönergeleri izleyin.

## <a name="customize-and-share"></a>Özelleştirin ve paylaşın

Ayrıntılar için bkz. [Uygulamayı özelleştirme ve paylaşma](../connect-data/service-template-apps-install-distribute.md#customize-and-share-the-app). Uygulamayı yayımlamadan veya dağıtmadan önce [rapor sorumluluk reddini](../create-reports/sample-covid-19-us.md#disclaimers) gözden geçirdiğinizden emin olun.

## <a name="next-steps"></a>Sonraki adımlar
* [Power Apps’teki Kriz İletişimi örnek şablonunu ayarlama ve bunun hakkında bilgi edinme](/powerapps/maker/canvas-apps/sample-crisis-communication-app)
* Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
* [Power BI şablon uygulamaları nedir?](../connect-data/service-template-apps-overview.md)
* [Kuruluşunuzda şablon uygulamalarını yükleme ve dağıtma](../connect-data/service-template-apps-install-distribute.md)