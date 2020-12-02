---
title: Power BI Premium Kapasite Ölçümlerine Bağlanma
description: Power BI Premium Kapasite Ölçümleri şablon uygulamasını alıp yükleme ve verilerinize bağlanma
author: paulinbar
ms.author: painbar
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: how-to
ms.date: 05/18/2020
LocalizationGroup: Connect to services
ms.openlocfilehash: f7bb6cdd3279ac15b2952d5e20b9c36a66a0c518
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96410609"
---
# <a name="connect-to-power-bi-premium-capacity-metrics"></a>Power BI Premium Kapasite Ölçümlerine Bağlanma

Premium kapasite kaynaklarını en iyi şekilde kullanma konusunda bilinçli kararlar alabilmek için kapasitelerinizi izlemek temel önem taşır. Power BI Premium Kapasite Ölçümleri uygulaması kapasitenizin performansıyla ilgili en ayrıntılı bilgileri sağlar.

![Power BI Premium Kapasite Ölçümleri uygulaması raporu](media/service-connect-to-pbi-premium-capacity-metrics/service-pbi-premium-capacity-metrics-app-report.png)

Bu makalede uygulamayı yükleme ve veri kaynaklarına bağlanma işlemleri açıklanır. Raporun içeriği ve nasıl kullanılacağı hakkında bilgi için bkz. [Uygulama ile Premium kapasiteleri izleme](../admin/service-admin-premium-monitor-capacity.md) ve [Premium Kapasite Ölçümleri uygulaması blog gönderisi](https://powerbi.microsoft.com/blog/premium-capacity-metrics-app-new-health-center-with-kpis-to-explore-relevant-metrics-and-steps-to-mitigate-issues/).

Uygulamayı yükleyip veri kaynaklarına bağlandıktan sonra, raporu ihtiyaçlarınıza göre özelleştirebilirsiniz. Daha sonra bunu, kuruluşunuzdaki iş arkadaşlarınıza dağıtabilirsiniz.

> [!NOTE]
> Şablon uygulamalarını yüklemek için [izinler](./service-template-apps-install-distribute.md#prerequisites) gerekir. İzinlerinizin yeterli olmadığını fark ederseniz Power BI yöneticinizle iletişime geçin.

## <a name="install-the-app"></a>Uygulamayı yükleme

1. Uygulamaya ulaşmak için aşağıdaki bağlantıya tıklayın: [Power BI Premium Kapasite Ölçümleri şablon uygulaması](https://app.powerbi.com/groups/me/getapps/services/pbi_pcmm.capacity-metrics-dxt)

1. Uygulamanın AppSource sayfasında [**ŞİMDİ EDİNİN**](https://app.powerbi.com/groups/me/getapps/services/pbi_pcmm.capacity-metrics-dxt)’i seçin.

    [![AppSource’da Power BI Premium Kapasite Ölçümleri uygulaması](media/service-connect-to-pbi-premium-capacity-metrics/service-pbi-premium-capacity-metrics-app-appsource-get-it-now.png)](https://app.powerbi.com/groups/me/getapps/services/pbi_pcmm.capacity-metrics-dxt)

1. **Yükle**'yi seçin. 

    ![Power BI Premium Kapasite Ölçümleri uygulamasını yükleme](media/service-connect-to-pbi-premium-capacity-metrics/service-pbi-premium-capacity-metric-select-install.png)

    > [!NOTE]
    > Uygulamayı daha önce yüklediyseniz, [o uygulamanın üzerine yazmak](./service-template-apps-install-distribute.md#update-a-template-app) mı yoksa yeni bir çalışma alanına yüklemek mi istediğiniz sorulur.

    Uygulamayı yükledikten sonra Uygulamalarınız sayfasında görebilirsiniz.

   ![Uygulama sayfasında Power BI Premium Kapasite Ölçümleri uygulaması](media/service-connect-to-pbi-premium-capacity-metrics/service-pbi-premium-capacity-metrics-app-apps-page-icon.png)

## <a name="connect-to-data-sources"></a>Veri kaynaklarına bağlanma

1. Uygulamanızı açmak için Uygulamalar sayfanızdaki simgeyi seçin.

1. Karşılama ekranında **Keşfet**’i seçin.

   ![Şablon uygulaması karşılama ekranı](media/service-connect-to-pbi-premium-capacity-metrics/service-pbi-premium-capacity-metrics-app-splash-screen.png)

   Uygulama, örnek verileri göstererek açılır.

1. Sayfanın üst kısmındaki başlıkta yer alan **Verilerinize bağlanın** seçeneğini belirleyin.

   ![Power BI Premium Kapasite Ölçümleri uygulaması veri bağlantınızı yapma](media/service-connect-to-pbi-premium-capacity-metrics/service-pbi-premium-capacity-metrics-app-connect-data.png)

1. Görüntülenen iletişim kutusunda UTC farkını ayarlayın. UTC farkı, Eşgüdümlü Evrensel Saat ile sizin konumunuzun saati arasındaki saat farkıdır. Ardından **İleri**'ye tıklayın.
  
   ![Power BI Premium Kapasite Ölçümleri uygulaması UTC’yi ayarlama iletişim kutusu](media/service-connect-to-pbi-premium-capacity-metrics/service-pbi-premium-capacity-metrics-app-setutc-dialog.png)
   **Not: Yarım saat biçimi ondalık olmalıdır (örneğin 5,5; 2,5 vb.).**

1. Görüntülenen sonraki iletişim kutusunda hiçbir şey yapmanız gerekmez. **Oturum aç**’ı seçmeniz yeterlidir.

   ![Power BI Premium Kapasite Ölçümleri uygulaması kimlik doğrulaması iletişim kutusu](media/service-connect-to-pbi-premium-capacity-metrics/service-pbi-premium-capacity-metrics-app-authentication-dialog.png)

1. Microsoft oturum açma ekranında, Power BI’da oturum açın.

   ![Microsoft oturum açma ekranı](media/service-connect-to-pbi-premium-capacity-metrics/service-pbi-premium-capacity-metrics-app-microsoft-login.png)

   Oturum açtıktan sonra rapor veri kaynaklarına bağlanıp güncel verilerle doldurulur. Bu sırada, etkinlik izleyicisi açılır.

   ![Power BI Premium Kapasite Ölçümleri uygulaması yenileme devam ediyor](media/service-connect-to-pbi-premium-capacity-metrics/service-pbi-premium-capacity-metrics-app-refresh-monitor.png)

   Oturum açma işlemi sırasında bu ayarı devre dışı bırakmadığınız sürece, rapor verileriniz günde bir kere otomatik olarak yenilenir. Dilerseniz, rapor verilerinizi güncel tutmak için [kendi yenileme zamanlamanızı da ayarlayabilirsiniz](./refresh-scheduled-refresh.md).

## <a name="customize-and-share"></a>Özelleştirin ve paylaşın

Uygulamayı özelleştirmeye başlamak için sağ üst köşedeki kalem simgesine tıklayın.

 ![Düzenle simgesi](media/service-connect-to-pbi-premium-capacity-metrics/service-pbi-premium-capacity-metrics-app-customize.png)

Ayrıntılar için bkz. [Uygulamayı özelleştirme ve paylaşma](./service-template-apps-install-distribute.md#customize-and-share-the-app).

## <a name="next-steps"></a>Sonraki adımlar
* [Uygulama ile Premium kapasiteleri izleme](../admin/service-admin-premium-monitor-capacity.md)
* [Premium Kapasite Ölçümleri uygulaması blog gönderisi](https://powerbi.microsoft.com/blog/premium-capacity-metrics-app-new-health-center-with-kpis-to-explore-relevant-metrics-and-steps-to-mitigate-issues/)
* [Power BI şablon uygulamaları nedir?](./service-template-apps-overview.md)
* [Kuruluşunuzda şablon uygulamalarını yükleme ve dağıtma](./service-template-apps-install-distribute.md)
* Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)