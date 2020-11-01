---
title: COVID-19 ABD izleme raporuna bağlanma
description: COVID-19 ABD’deki Vakalar şablon uygulamasını edinip yükleme ve verilerinize bağlanma.
author: paulinbar
ms.service: powerbi
ms.subservice: powerbi-template-apps
ms.topic: how-to
ms.date: 04/05/2020
ms.author: painbar
LocalizationGroup: Connect to services
ms.openlocfilehash: 01dab6cad6142b455a0d61a0011e43cea6da23e1
ms.sourcegitcommit: 3ddfd9ffe2ba334a6f9d60f17ac7243059cf945b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/22/2020
ms.locfileid: "92349536"
---
# <a name="connect-to-the-covid-19-us-tracking-report"></a>COVID-19 ABD izleme raporuna bağlanma
Bu makalede COVID-19 izleme raporuna yönelik şablon uygulamasını yükleme ve veri kaynaklarına bağlanma yöntemi açıklanır.

![COVID-19 ABD İzleme Raporu](media/service-connect-to-covid-19-tracking/service-covid-19-us-tracking-report-title-screen.png)

Sorumluluk reddi ve veriler hakkındaki bilgiler de dahil olmak üzere raporun kendisiyle ilgili ayrıntılı bilgiler için bkz. [ABD eyalet ve yerel hükümetlere yönelik COVID-19 izleme örneği](../create-reports/sample-covid-19-us.md).

Şablon uygulamasını yükleyip veri kaynaklarına bağlandıktan sonra, raporu ihtiyaçlarınıza göre özelleştirebilirsiniz. Daha sonra bunu, kuruluşunuzdaki iş arkadaşlarınıza bir uygulama olarak dağıtabilirsiniz.

## <a name="install-the-app"></a>Uygulamayı yükleme

1. Uygulamaya ulaşmak için aşağıdaki bağlantıya tıklayın: [COVID-19 ABD İzleme Raporu şablon uygulaması](https://app.powerbi.com/groups/me/getapps/services/pbi-contentpacks.covid19ms)

1. Uygulamanın AppSource sayfasına ulaştığınızda [**ŞİMDİ EDİNİN**](https://app.powerbi.com/groups/me/getapps/services/pbi-contentpacks.covid19ms)’e tıklayın.

    [![AppSource’ta COVID-19 ABD İzleme Raporu](media/service-connect-to-covid-19-tracking/service-covid-19-us-tracking-report-appsource-icon.png)](https://app.powerbi.com/groups/me/getapps/services/pbi-contentpacks.covid19ms)

1. Sorulduğunda **Yükle** ’ye tıklayın. Uygulamayı yükledikten sonra Uygulamalarınız sayfasında görebilirsiniz.

   ![Uygulama sayfasında COVID-19 ABD İzleme Raporu](media/service-connect-to-covid-19-tracking/service-covid-19-us-tracking-report-apps-page-icon.png)

## <a name="connect-to-data-sources"></a>Veri kaynaklarına bağlanma

1. Uygulamanızı açmak için Uygulamalar sayfanızdaki simgeye tıklayın.

1. Görüntülenen karşılama ekranında **Bağlan** ’ı seçin.

   ![Şablon uygulaması karşılama ekranı](media/service-connect-to-covid-19-tracking/service-covid-19-us-tracking-report-splash-screen.png)

1. Parametreler iletişim kutusu açılır. Gerekli parametre yoktur. **İleri** ’ye tıklayın.

   ![Covid-19 US İzleme Kaydı için parametre iletişim kutusunun ekran görüntüsü.](media/service-connect-to-covid-19-tracking/service-covid-19-us-tracking-report-parameters-dialog.png)

1. Kimlik doğrulama yöntemi iletişim kutusu açılır. Önerilen değerler önceden doldurulmuştur. Diğer değerler hakkında bilginiz yoksa mevcut değerleri değiştirmeyin.

    **İleri** ’ye tıklayın.

   ![Covid-19 US İzleme Kaydı için kimlik doğrulaması iletişim kutusunun ekran görüntüsü.](media/service-connect-to-covid-19-tracking/service-covid-19-us-tracking-report-authentication-dialog.png)

1. **Oturum aç** ’a tıklayın.

   ![Covid-19 US İzleme Kaydı için oturum açma iletişim kutusunun ekran görüntüsü.](media/service-connect-to-covid-19-tracking/service-covid-19-us-tracking-report-signin-dialog.png)
 
   Rapor veri kaynaklarına bağlanıp güncel verilerle doldurulur. Bu süre boyunca örnek verileri ve devam eden bir yenileme işlemi olduğunu görürsünüz.

   ![COVID-19 ABD İzleme Raporu, yenileme sürüyor](media/service-connect-to-covid-19-tracking/service-covid-19-us-tracking-report-refresh-monitor.png)

## <a name="schedule-report-refresh"></a>Rapor yenilemeyi zamanlama

Veri yenileme tamamlandığında uygulamayla ilişkilendirilen çalışma alanında olursunuz. Raporu güncel tutmak için [yenileme zamanlaması belirleyin](../connect-data/refresh-scheduled-refresh.md).

## <a name="customize-and-share"></a>Özelleştirin ve paylaşın

Ayrıntılar için bkz. [Uygulamayı özelleştirme ve paylaşma](../connect-data/service-template-apps-install-distribute.md#customize-and-share-the-app). Uygulamayı yayımlamadan veya dağıtmadan önce [rapor sorumluluk reddini](../create-reports/sample-covid-19-us.md#disclaimers) gözden geçirdiğinizden emin olun.

## <a name="next-steps"></a>Sonraki adımlar
* [ABD eyalet ve yerel hükümetlere yönelik COVID-19 izleme örneği](../create-reports/sample-covid-19-us.md)
* Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
* [Power BI şablon uygulamaları nedir?](../connect-data/service-template-apps-overview.md)
* [Kuruluşunuzda şablon uygulamalarını yükleme ve dağıtma](../connect-data/service-template-apps-install-distribute.md)
