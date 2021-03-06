---
title: Power BI Rapor Sunucusu için Power BI Desktop yüklemesi
description: Power BI Rapor Sunucusu için Power BI Desktop yüklemeyi öğrenin
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-report-server
ms.topic: how-to
ms.date: 10/16/2020
ms.openlocfilehash: 068d4a025bda878899e2d54f93bc56eaea336f3e
ms.sourcegitcommit: 7ed995eed0fd6e718748accf87bae384211cd95d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2021
ms.locfileid: "99044092"
---
# <a name="install-power-bi-desktop-for-power-bi-report-server"></a>Power BI Rapor Sunucusu için Power BI Desktop yüklemesi

Power BI Rapor Sunucusu için Power BI raporları oluşturmak istiyorsanız Power BI Rapor Sunucusu için en iyi duruma getirilmiş Power BI Desktop sürümünü indirip yüklemeniz gerekir. Bu, Power BI hizmetiyle kullanılan Power BI Desktop'tan farklı bir sürümdür. Örneğin Power BI hizmeti için Power BI Desktop sürümü önizleme özelliklerini içerir. Bu özellikler genel kullanıma sunulana kadar Power BI Rapor Sunucusu sürümünde sağlanmaz. Bu sürümün kullanılması, rapor sunucusunun; raporların ve modelin bilinen bir sürümüyle etkileşim kurabilmesini sağlar. 

Endişelenmenize gerek yok. Power BI Rapor Sunucusu için Power BI Desktop ve Power BI Desktop aynı bilgisayarda yan yana yükleyebilirsiniz.

## <a name="download-and-install-power-bi-desktop"></a>Power BI Desktop uygulamasını indirme ve yükleme

Power BI Rapor Sunucusu için Power BI Desktop en güncel sürümüne sahip olduğunuzdan emin olmanın en kolay yolu, rapor sunucunuzun Web portalından başlamadır.

1. Rapor sunucusu web portalında, **İndir** okunu ve ardından **Power BI Desktop**'ı seçin.

    ![Web portalından Power BI Desktop'ı indirme](media/install-powerbi-desktop/report-server-download-web-portal.png)

    Veya [Power BI Rapor Sunucusu](https://powerbi.microsoft.com/report-server/) giriş sayfasına giderek **Gelişmiş indirme seçenekleri**’ni belirleyin.

2. İndirme Merkezi sayfasında bir dil seçin, ardından **İndir** seçeneğini belirtin.

3. Bilgisayarınıza bağlı olarak, şu seçeneklerden birini belirleyin: 

    - **PBIDesktopRS.msi** (32 bit sürümü) veya
    - **PBIDesktopRS_x64.msi** (64 bit sürümü).

1. Yükleyiciyi indirdikten sonra, Power BI Desktop Kurulum Sihirbazını çalıştırın.

2. Yüklemenin sonunda **Power BI Desktop’ı Başlat**’ı seçin.

    Uygulama otomatik olarak başlatılır ve kullanımınıza hazır hale gelir.

## <a name="verify-youre-using-the-correct-version"></a>Doğru sürümü kullandığınızdan emin olma
Doğru Power BI Desktop'ı kullandığınızdan kolayca emin olabilirsiniz: Power BI Desktop'taki başlatma ekranına veya başlık çubuğuna bakın. Başlık çubuğunda **Power BI Desktop (ocak 2021)** veya üzeri olduğundan doğru sürüme sahip olduğunu söyleyebilirsiniz. Ayrıca Power BI logo renkleri de ters çevrilmiştir; artık sarı üstüne siyah değil siyah üstüne sarıdır.

![Power BI Desktop Ocak 2021](media/install-powerbi-desktop/power-bi-report-server-desktop.png)

Başlık çubuğunda Power BI hizmeti için Power BI Desktop sürümüne ilişkin ay ve yıl bilgisi görüntülenmez.

## <a name="file-extension-association"></a>Dosya uzantısı ilişkilendirme
Aynı makinede Power BI Rapor Sunucusu için hem Power BI Desktop hem de Power BI Desktop yükletiğinizi varsayalım. En son Power BI Desktop yüklemenizde .pbix dosyalarıyla dosya ilişkilendirmesi bulunur. Dolayısıyla, .pbix dosyasına çift tıkladığınızda en son yüklediğiniz Power BI Desktop'ı başlatır.

Power BI Desktop sahipseniz ve Power BI Rapor Sunucusu için Power BI Desktop yüklerseniz, tüm. pbix dosyaları varsayılan olarak Power BI Rapor Sunucusu için Power BI Desktop açılır. Power BI Desktop uygulamasının .pbix dosyaları için varsayılan seçenek olmasını istiyorsanız, [Power BI Desktop'ı Microsoft Store'dan](https://aka.ms/pbidesktopstore) yeniden yükleyin.

Öncelikli olarak kullanmak istediğiniz Power BI Desktop sürümünü kendiniz açabilirsiniz. Ardından dosyayı Power BI Desktop'tan açabilirsiniz.

Her zaman Power BI Desktop'ın doğru sürümünü açmanın en güvenli yolu aşağıda gösterilmiştir. Power BI Rapor Sunucusu'nun içinden Power BI raporunu düzenlemeye başlayın veya Power BI hizmetinden yeni bir Power BI raporu oluşturun.

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

Power BI mobil uygulamalarında ve Power BI hizmetinde yer alan Power BI Rapor Sunucusu’ndaki Power BI raporları (`https://app.powerbi.com`), birkaç farklı özellik dışında hemen hemen aynı görevi görür.

### <a name="selecting-a-language"></a>Dil seçme

Power BI Rapor Sunucusu için Power BI Desktop için, uygulamayı yüklediğinizde dili seçersiniz. Bunu daha sonra değiştiremezsiniz ama başka dildeki bir sürümü yükleyebilirsiniz.

### <a name="report-visuals-in-a-browser"></a>Tarayıcıda rapor görselleri

Power BI Rapor Sunucusu raporları, Power BI görselleri de dahil olmak üzere neredeyse tüm görselleştirmeleri destekler. Power BI Rapor Sunucusu raporları aşağıdakileri desteklemez:

* R görselleri
* İçerik haritaları
* Power BI Desktop önizleme özellikleri

### <a name="reports-in-the-power-bi-mobile-apps"></a>Power BI mobil uygulamalarında raporlar

Power BI Rapor Sunucusu raporları, [Power BI mobil uygulamalarında](../consumer/mobile/mobile-apps-for-mobile-devices.md) aşağıdakiler de dahil olmak üzere tüm temel işlevleri destekler:

* [Telefon raporu düzeni](../create-reports/desktop-create-phone-report.md): Bir raporu Power BI mobil uygulamaları için en iyi duruma getirebilirsiniz. En iyi duruma getirilmiş raporlar cep telefonunuzda özel bir simge (![Telefon rapor düzeni simgesi](media/install-powerbi-desktop/power-bi-rs-mobile-optimized-icon.png)) ve düzenle gösterilir.
  
    ![Telefonlar için en iyi duruma getirilmiş rapor](media/install-powerbi-desktop/power-bi-rs-mobile-optimized-report.png)

Power BI Rapor Sunucusu, Power BI mobil uygulamalarında şu özellikleri desteklemez:

* R görselleri
* Power BI görselleri
* İçerik haritaları
* Coğrafi filtreleme veya barkodlar

### <a name="custom-security"></a>Özel Güvenlik

Power BI Rapor Sunucusu için Power BI Desktop özel güvenliği desteklemez. Power BI Rapor Sunucunuzun özel güvenlik uzantısıyla yapılandırılmış olması halinde Power BI Desktop'tan (Power BI Rapor Sunucusu için iyileştirilmiş) Power BI Rapor Sunucusu örneğine Power BI raporu kaydedemezsiniz. Rapor dosyasını Power BI Desktop'tan .pbix biçiminde kaydetmeniz ve Power BI Rapor Sunucusu portalına yüklemeniz gerekir.

### <a name="saving-reports-to-a-power-bi-report-server-in-a-different-domain"></a>Raporları farklı bir etki alanındaki Power BI Rapor Sunucusu’na kaydetme

Power BI raporunu Power BI Rapor Sunucusu’na kaydederken Windows kimlik bilgileriniz kullanılır. Windows kimlik bilgilerinizle doğrudan farklı bir etki alanındaki rapor sunucusuna kaydetme işlemi desteklenmez. Bunun yerine web tarayıcısı kullanarak rapor sunucusunu görüntüleyebilir ve dosyayı makinenizden el ile karşıya yükleyebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

Power BI Desktop uygulamasını yüklediğinizde göre Power BI raporu oluşturmaya başlayabilirsiniz.

[Power BI Rapor Sunucusu için Power BI raporu oluşturma](quickstart-create-powerbi-report.md)  
[Power BI Rapor Sunucusu nedir?](get-started.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)

