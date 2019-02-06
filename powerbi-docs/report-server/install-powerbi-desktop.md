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
ms.date: 01/24/2019
ms.openlocfilehash: 63550950b21231909c32ac63f5f2930ebf93c0af
ms.sourcegitcommit: 0abcbc7898463adfa6e50b348747256c4b94e360
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/06/2019
ms.locfileid: "55762226"
---
# <a name="install-power-bi-desktop-optimized-for-power-bi-report-server"></a>Power BI Rapor Sunucusu için en iyi duruma getirilmiş Power BI Desktop uygulamasını yükleme

Power BI Rapor Sunucusu için en iyi duruma getirilmiş Power BI Desktop uygulamasını yüklemeyi öğrenin.

Power BI Rapor Sunucusu için Power BI raporları oluşturmak istiyorsanız Power BI Rapor Sunucusu için en iyi duruma getirilmiş Power BI Desktop'ı indirip yüklemeniz gerekir. Bu, Power BI hizmetiyle kullanılan Power BI Desktop'tan farklı bir sürümdür. Örneğin, Power BI hizmetine yönelik Power BI Desktop sürümü, yayımlanana kadar Power BI Rapor Sunucusu sürümünde yer almayan önizleme özellikleri içerir. Bu sürümün kullanılması, rapor sunucusunun; raporların ve modelin bilinen bir sürümüyle etkileşim kurabilmesini sağlar. 

İyi haber şu: Power BI Desktop ile Power BI Rapor Sunucusu için en iyi duruma getirilmiş Power BI Desktop uygulamaları aynı bilgisayarda yan yana yüklü olabilir.

## <a name="download-and-install-power-bi-desktop"></a>Power BI Desktop uygulamasını indirme ve yükleme

Power BI Rapor Sunucusu için en iyi duruma getirilmiş Power BI Desktop'ın en güncel sürümüne sahip olduğunuzdan emin olmanın en kolay yolu rapor sunucunuzun web portalına gitmektir.

1. Rapor sunucusu web portalında, **İndir** okunu ve ardından **Power BI Desktop**'ı seçin.

    ![Web portalından Power BI Desktop'ı indirme](media/install-powerbi-desktop/report-server-download-web-portal.png)

    Alternatif olarak, Microsoft İndirme Merkezi'nde doğrudan [Microsoft Power BI Desktop](https://go.microsoft.com/fwlink/?linkid=2055039) (Power BI Rapor Sunucusu için en iyi duruma getirilmiş - Ocak 2019) sayfasına da gidebilirsiniz.

2. İndirme Merkezi sayfasında, **İndir** seçeneğini belirleyin.

3. Bilgisayarınıza bağlı olarak, şu seçeneklerden birini belirleyin: 

    - **PBIDesktopRS.msi** (32 bit sürümü) veya

    - **PBIDesktopRS_x64.msi** (64 bit sürümü).

1. Yükleyiciyi indirdikten sonra, Power BI Desktop (Ocak 2019) Kurulum Sihirbazını çalıştırın.

2. Yüklemenin sonunda **Start Power BI Desktop now** (Power BI Desktop'ı şimdi başlat) onay kutusunu işaretleyin.

    Uygulama otomatik olarak başlatılır ve kullanımınıza hazır hale gelir.

## <a name="verify-youre-using-the-correct-version"></a>Doğru sürümü kullandığınızdan emin olma
Doğru Power BI Desktop'ı kullandığınızdan kolayca emin olabilirsiniz: Power BI Desktop'taki başlatma ekranına veya başlık çubuğuna bakın. Başlık çubuğunda sürümün ay ve yıl bilgileri gösterilir. Ayrıca Power BI logo renkleri de ters çevrilmiştir; artık sarı üstüne siyah değil siyah üstüne sarıdır.

![Power BI Rapor Sunucusu için en iyi duruma getirilmiş Power BI Desktop için başlık çubuğu](media/install-powerbi-desktop/power-bi-report-server-desktop-jan-2019.png)

Başlık çubuğunda Power BI hizmeti için Power BI Desktop sürümüne ilişkin ay ve yıl bilgisi görüntülenmez.

## <a name="file-extension-association"></a>Dosya uzantısı ilişkilendirme
Aynı makineye hem Power BI Desktop hem de Power BI Rapor Sunucusu için en iyi duruma getirilmiş Power BI Desktop uygulamasını yüklediyseniz, Power BI Desktop'ın en son yüklemesi .pbix dosyalarıyla ilişkilendirilir. Dolayısıyla, .pbix dosyasına çift tıkladığınızda en son yüklediğiniz Power BI Desktop'ı başlatır.

Power BI Desktop uygulaması yüklüyken Power BI Rapor Sunucusu için en iyi duruma getirilmiş Power BI Desktop uygulamasını yüklediyseniz, tüm .pbix dosyaları varsayılan olarak Power BI Rapor Sunucusu için en iyi duruma getirilmiş Power BI Desktop uygulamasıyla açılır. Power BI Desktop uygulamasının .pbix dosyaları için varsayılan seçenek olmasını istiyorsanız, [Power BI Desktop'ı Microsoft Store'dan](http://aka.ms/pbidesktopstore) yeniden yükleyin.

Öncelikli olarak kullanmak istediğiniz Power BI Desktop sürümünü kendiniz açabilirsiniz. Ardından dosyayı Power BI Desktop'tan açabilirsiniz.

Power BI Rapor Sunucusu'nda Power BI raporunu düzenlediğinizde veya web portalında yeni bir Power BI raporu oluşturduğunuzda her zaman doğru Power BI Destop sürümü açılır.

## <a name="considerations-and-limitations"></a>Önemli noktalar ve sınırlamalar

Power BI mobil uygulamalarında ve Power BI hizmetinde yer alan Power BI Rapor Sunucusu Power BI raporları (http://app.powerbi.com), birkaç farklı özellik dışında hemen hemen aynı görevi görür.

### <a name="in-a-browser"></a>Tarayıcıda

Power BI Rapor Sunucusu raporları aşağıdakiler de dahil olmak üzere tüm görselleştirmeleri destekler:

* Özel görseller

Power BI Rapor Sunucusu raporları aşağıdakileri desteklemez:

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
* Coğrafi filtreleme veya barkodlar

## <a name="power-bi-desktop-for-earlier-versions-of-power-bi-report-server"></a>Önceki Power BI Rapor Sunucusu sürümleri için Power BI Desktop

Rapor sunucunuz önceki bir sürümse, ilgili Power BI Desktop sürümü gerekir. İşte önceki sürüm.

- Microsoft Power BI Desktop ([Power BI Rapor Sunucusu için en iyi duruma getirilmiş - Ağustos 2018](https://www.microsoft.com/download/details.aspx?id=57271))

## <a name="next-steps"></a>Sonraki adımlar

Power BI Desktop uygulamasını yüklediğinizde göre Power BI raporu oluşturmaya başlayabilirsiniz.

[Power BI Rapor Sunucusu için Power BI raporu oluşturma](quickstart-create-powerbi-report.md)  
[Power BI Rapor Sunucusu nedir?](get-started.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
