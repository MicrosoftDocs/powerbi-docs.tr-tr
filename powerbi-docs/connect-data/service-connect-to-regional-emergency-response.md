---
title: Bölgesel Acil Durum Müdahale Panosu’na bağlanma
description: Bölgesel acil durumlara müdahaleye yönelik şablon uygulaması için COVID-19 Karar Desteği Panosu’nu edinme ve yükleme, verilere bağlanma
author: paulinbar
ms.author: painbar
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: how-to
ms.date: 04/24/2020
LocalizationGroup: Connect to services
ms.openlocfilehash: b8cb2be15d084bba3fc2a70152165ce3b2909dab
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96410563"
---
# <a name="connect-to-the-regional-emergency-response-dashboard"></a>Bölgesel Acil Durum Müdahale Panosu’na bağlanma
Bölgesel Acil Durum Müdahale Panosu, [Microsoft Power Platform Bölgesel Acil Durum Müdahale Panosu çözümünün](/powerapps/sample-apps/regional-emergency-response/overview) raporlama bileşenidir. Bölgesel kuruluş yöneticileri, etkili kararlar almalarına yardımcı olan önemli verileri ve ölçümleri hızla görüntülemelerini sağlayan Power BI kiracılarındaki panoyu görüntüleyebilir.

![Bölgesel Acil Durum Müdahale Panosu uygulama raporu](media/service-connect-to-regional-emergency-response/service-regional-emergency-response-app-report.png)

Bu makalede, Bölgesel Acil Durum Müdahale Panosu şablon uygulamasını kullanarak Bölgesel Acil Durum Müdahalesi uygulamasını yükleme ve veri kaynaklarına bağlanma açıklanır.

Panoda sunulanlar hakkında ayrıntılı bilgi için bkz. [İçgörüler edinme](/powerapps/sample-apps/regional-emergency-response/portals-admin-reporting#get-insights).

Şablon uygulamasını yükleyip veri kaynaklarına bağlandıktan sonra, raporu ihtiyaçlarınıza göre özelleştirebilirsiniz. Daha sonra bunu, kuruluşunuzdaki iş arkadaşlarınıza bir uygulama olarak dağıtabilirsiniz.

## <a name="prerequisites"></a>Önkoşullar

Bu şablon uygulamasını yüklemeden önce [Bölgesel Acil Durum Müdahale çözümünü](/powerapps/sample-apps/regional-emergency-response/deploy) yükleyip ayarlamanız gerekir. Bu çözüm yüklendiğinde, uygulamayı verilerle doldurmak için gereken veri kaynağı başvuruları oluşturulur.

Bölgesel Acil Durum Müdahale çözümünü yüklerken [Common Data Service ortam örneğinizin URL’sini](/powerapps/sample-apps/regional-emergency-response/deploy#step-5-configure-and-publish-power-bi-dashboard) not edin. Şablon uygulamasını verilere bağlamak için bu URL’ye ihtiyacınız olacak.

## <a name="install-the-app"></a>Uygulamayı yükleme

1. Uygulamaya ulaşmak için aşağıdaki bağlantıya tıklayın: [Bölgesel Acil Durum Müdahale Panosu şablon uygulaması](https://appsource.microsoft.com/product/power-bi/powerapps_cxo.regional_response)

1. Uygulamanın AppSource sayfasında [**ŞİMDİ EDİNİN**](https://appsource.microsoft.com/product/power-bi/powerapps_cxo.regional_response)’i seçin.

    [![AppSource’ta Bölgesel Acil Durum Müdahale Panosu uygulaması](media/service-connect-to-regional-emergency-response/service-regional-emergency-response-app-appsource-get-it-now.png)](https://appsource.microsoft.com/product/power-bi/powerapps_cxo.regional_response)

1. **Yükle**'yi seçin. 

    ![Bölgesel Acil Durum Müdahale Panosu uygulamasını yükleme](media/service-connect-to-regional-emergency-response/service-regional-emergency-response-select-install.png)

    Uygulamayı yükledikten sonra Uygulamalarınız sayfasında görebilirsiniz.

   ![Uygulama sayfasındaki Bölgesel Acil Durum Müdahale Panosu uygulaması](media/service-connect-to-regional-emergency-response/service-regional-emergency-response-app-apps-page-icon.png)

## <a name="connect-to-data-sources"></a>Veri kaynaklarına bağlanma

1. Uygulamanızı açmak için Uygulamalar sayfanızdaki simgeyi seçin.

1. Karşılama ekranında **Keşfet**’i seçin.

   ![Şablon uygulaması karşılama ekranı](media/service-connect-to-regional-emergency-response/service-regional-emergency-response-app-splash-screen.png)

   Uygulama, örnek verileri göstererek açılır.

1. Sayfanın üst kısmındaki başlıkta yer alan **Verilerinize bağlanın** seçeneğini belirleyin.

   ![Bölgesel Acil Durum Müdahale Panosu uygulaması, verilerinize bağlanma bağlantısı](media/service-connect-to-regional-emergency-response/service-regional-emergency-response-app-connect-data.png)

1. Görüntülenen iletişim kutusuna [Common Data Service ortam örneğinizin URL’sini](/powerapps/sample-apps/emergency-response/deploy-configure#publish-the-power-bi-dashboard) yazın. Örneğin: https://[myenv].crm.dynamics.com. İşiniz bittiğinde **İleri**’ye tıklayın.

   ![Bölgesel Acil Durum Müdahale Panosu uygulaması, URL iletişim kutusu](media/service-connect-to-regional-emergency-response/service-regional-emergency-response-app-url-dialog.png)

1. Karşınıza çıkan sonraki iletişim kutusunda, kimlik doğrulaması yöntemini **OAuth2** olarak belirleyin. Gizlilik düzeyi ayarlarında bir şey yapmanız gerekmez.

   **Oturum aç**'ı seçin.

   ![Bölgesel Acil Durum Müdahale Panosu uygulaması, kimlik doğrulaması iletişim kutusu](media/service-connect-to-regional-emergency-response/service-regional-emergency-response-app-authentication-dialog.png)

1. Microsoft oturum açma ekranında, Power BI’da oturum açın.

   ![Microsoft oturum açma ekranı](media/service-connect-to-regional-emergency-response/service-regional-emergency-response-app-microsoft-login.png)

   Oturum açtıktan sonra rapor veri kaynaklarına bağlanıp güncel verilerle doldurulur. Bu sırada, etkinlik izleyicisi açılır.

   ![Bölgesel Acil Durum Müdahale Panosu uygulaması, yenileme sürüyor](media/service-connect-to-regional-emergency-response/service-regional-emergency-response-app-refresh-monitor.png)

## <a name="schedule-report-refresh"></a>Rapor yenilemeyi zamanlama

Veri yenileme tamamlandığında, raporu güncel tutmak için [yenileme zamanlaması belirleyin](../connect-data/refresh-scheduled-refresh.md).

1. Üst başlık çubuğunda **Power BI**’ı seçin.

   ![Power BI içerik haritası](media/service-connect-to-regional-emergency-response/service-regional-emergency-response-app-powerbi-breadcrumb.png)

1. Sol gezinti bölmesinde, **Çalışma Alanları** bölümünde Bölgesel Acil Durum Müdahale Panosu çalışma alanını bulup [Zamanlanan yenileme yapılandırma](../connect-data/refresh-scheduled-refresh.md) makalesinde açıklanan yönergeleri izleyin.

## <a name="customize-and-share"></a>Özelleştirin ve paylaşın

Ayrıntılar için bkz. [Uygulamayı özelleştirme ve paylaşma](../connect-data/service-template-apps-install-distribute.md#customize-and-share-the-app). Uygulamayı yayımlamadan veya dağıtmadan önce [rapor sorumluluk reddini](/powerapps/sample-apps/regional-emergency-response/overview#disclaimer) gözden geçirdiğinizden emin olun.

## <a name="next-steps"></a>Sonraki adımlar
* [Bölgesel Acil Durum Müdahale Panosu’nu anlama](/powerapps/sample-apps/regional-emergency-response/portals-admin-reporting#get-insights)
* [Power Apps’teki Kriz İletişimi örnek şablonunu ayarlama ve bunun hakkında bilgi edinme](/powerapps/maker/canvas-apps/sample-crisis-communication-app)
* Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
* [Power BI şablon uygulamaları nedir?](../connect-data/service-template-apps-overview.md)
* [Kuruluşunuzda şablon uygulamalarını yükleme ve dağıtma](../connect-data/service-template-apps-install-distribute.md)