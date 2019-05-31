---
title: Power BI Rapor Sunucusu için en iyi duruma getirilmiş Power BI Desktop uygulamasını yükleme
description: Power BI Rapor Sunucusu için en iyi duruma getirilmiş Power BI Desktop uygulamasını yüklemeyi öğrenin
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: conceptual
ms.date: 05/22/2019
ms.openlocfilehash: 54713c9c978554521d68aeb7b4c25d681ddb3d69
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66187425"
---
# <a name="install-power-bi-desktop-optimized-for-power-bi-report-server"></a>Power BI Rapor Sunucusu için en iyi duruma getirilmiş Power BI Desktop uygulamasını yükleme

Power BI Rapor Sunucusu için Power BI raporları oluşturmak istiyorsanız Power BI Rapor Sunucusu için en iyi duruma getirilmiş Power BI Desktop'ı indirip yüklemeniz gerekir. Bu, Power BI hizmetiyle kullanılan Power BI Desktop'tan farklı bir sürümdür. Örneğin, Power BI hizmetine yönelik Power BI Desktop sürümü, yayımlanana kadar Power BI Rapor Sunucusu sürümünde yer almayan önizleme özellikleri içerir. Bu sürümün kullanılması, rapor sunucusunun; raporların ve modelin bilinen bir sürümüyle etkileşim kurabilmesini sağlar. 

İyi haber şu: Power BI Desktop ile Power BI Rapor Sunucusu için en iyi duruma getirilmiş Power BI Desktop uygulamaları aynı bilgisayarda yan yana yüklü olabilir.

## <a name="download-and-install-power-bi-desktop"></a>Power BI Desktop uygulamasını indirme ve yükleme

Power BI Rapor Sunucusu için en iyi duruma getirilmiş Power BI Desktop'ın en güncel sürümüne sahip olduğunuzdan emin olmanın en kolay yolu rapor sunucunuzun web portalına gitmektir.

1. Rapor sunucusu web portalında, **İndir** okunu ve ardından **Power BI Desktop**'ı seçin.

    ![Web portalından Power BI Desktop'ı indirme](media/install-powerbi-desktop/report-server-download-web-portal.png)

    Veya doğrudan [Microsoft Power BI Desktop](https://www.microsoft.com/download/details.aspx?id=56723) (iyileştirilmiş Power BI rapor sunucusu için - Mayıs 2019) Microsoft Download Center'daki.

2. İndirme Merkezi sayfasında, **İndir** seçeneğini belirleyin.

3. Bilgisayarınıza bağlı olarak, şu seçeneklerden birini belirleyin: 

    - **PBIDesktopRS.msi** (32 bit sürümü) veya

    - **PBIDesktopRS_x64.msi** (64 bit sürümü).

1. Yükleyiciyi indirdikten sonra Power BI Desktop (Mayıs 2019) Kurulum Sihirbazı'nı çalıştırın.

2. Yüklemenin sonunda seçin **Power BI Desktop'ı başlatma**.

    Uygulama otomatik olarak başlatılır ve kullanımınıza hazır hale gelir.

## <a name="verify-youre-using-the-correct-version"></a>Doğru sürümü kullandığınızdan emin olma
Doğru Power BI Desktop'ı kullandığınızdan kolayca emin olabilirsiniz: Power BI Desktop'taki başlatma ekranına veya başlık çubuğuna bakın. Başlık çubuğunda sürümün ay ve yıl bilgileri gösterilir. Ayrıca Power BI logo renkleri de ters çevrilmiştir; artık sarı üstüne siyah değil siyah üstüne sarıdır.

![Power BI Rapor Sunucusu için en iyi duruma getirilmiş Power BI Desktop için başlık çubuğu](media/install-powerbi-desktop/power-bi-report-server-desktop-may-2019.png)

Başlık çubuğunda Power BI hizmeti için Power BI Desktop sürümüne ilişkin ay ve yıl bilgisi görüntülenmez.

## <a name="file-extension-association"></a>Dosya uzantısı ilişkilendirme
Aynı makineye hem Power BI Desktop hem de Power BI Rapor Sunucusu için en iyi duruma getirilmiş Power BI Desktop uygulamasını yüklediyseniz, Power BI Desktop'ın en son yüklemesi .pbix dosyalarıyla ilişkilendirilir. Dolayısıyla, .pbix dosyasına çift tıkladığınızda en son yüklediğiniz Power BI Desktop'ı başlatır.

Power BI Desktop uygulaması yüklüyken Power BI Rapor Sunucusu için en iyi duruma getirilmiş Power BI Desktop uygulamasını yüklediyseniz, tüm .pbix dosyaları varsayılan olarak Power BI Rapor Sunucusu için en iyi duruma getirilmiş Power BI Desktop uygulamasıyla açılır. Power BI Desktop uygulamasının .pbix dosyaları için varsayılan seçenek olmasını istiyorsanız, [Power BI Desktop'ı Microsoft Store'dan](http://aka.ms/pbidesktopstore) yeniden yükleyin.

Öncelikli olarak kullanmak istediğiniz Power BI Desktop sürümünü kendiniz açabilirsiniz. Ardından dosyayı Power BI Desktop'tan açabilirsiniz.

Power BI rapor Sunucusu'ndaki bir Power BI raporu düzenleme veya yeni bir Power BI raporu web Portalı'ndan oluşturarak her zaman Power BI Desktop'ın doğru sürümü açılır.

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

Power BI mobil uygulamalarında ve Power BI hizmetinde yer alan Power BI Rapor Sunucusu Power BI raporları (http://app.powerbi.com), birkaç farklı özellik dışında hemen hemen aynı görevi görür.

### <a name="in-a-browser"></a>Tarayıcıda

Power BI rapor sunucusu raporları, özel görseller de dahil olmak üzere neredeyse tüm görselleştirmeleri destekler. Power BI Rapor Sunucusu raporları aşağıdakileri desteklemez:

* R görselleri
* ArcGIS haritaları
* İçerik haritaları
* Power BI Desktop önizleme özellikleri

### <a name="in-the-power-bi-mobile-apps"></a>Power BI mobil uygulamalarında

Power BI Rapor Sunucusu raporları, [Power BI mobil uygulamalarında](../consumer/mobile/mobile-apps-for-mobile-devices.md) aşağıdakiler de dahil olmak üzere tüm temel işlevleri destekler:

* [Telefon raporu düzeni](../desktop-create-phone-report.md): Bir raporu Power BI mobil uygulamaları için en iyi duruma getirebilirsiniz. En iyi duruma getirilmiş raporlar cep telefonunuzda özel bir simge (![Telefon rapor düzeni simgesi](media/install-powerbi-desktop/power-bi-rs-mobile-optimized-icon.png)) ve düzenle gösterilir.
  
    ![Telefonlar için en iyi duruma getirilmiş rapor](media/install-powerbi-desktop/power-bi-rs-mobile-optimized-report.png)

Power BI Rapor Sunucusu, Power BI mobil uygulamalarında şu özellikleri desteklemez:

* R görselleri
* ArcGIS haritaları
* Özel görseller
* İçerik haritaları
* Coğrafi filtreleme veya çubuğu kodları

## <a name="power-bi-desktop-for-earlier-versions-of-power-bi-report-server"></a>Önceki Power BI Rapor Sunucusu sürümleri için Power BI Desktop

Rapor sunucunuz önceki bir sürümse, ilgili Power BI Desktop sürümü gerekir. Aşağıda, önceki sürümü indirmek için bağlantıya yer verilmiştir.

- Microsoft Power BI Desktop ([iyileştirilmiş Power BI rapor sunucusu - Ocak 2019](https://go.microsoft.com/fwlink/?linkid=2055039))

## <a name="next-steps"></a>Sonraki adımlar

Power BI Desktop uygulamasını yüklediğinizde göre Power BI raporu oluşturmaya başlayabilirsiniz.

[Power BI Rapor Sunucusu için Power BI raporu oluşturma](quickstart-create-powerbi-report.md)  
[Power BI Rapor Sunucusu nedir?](get-started.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
