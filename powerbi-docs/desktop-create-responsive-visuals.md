---
title: "Power BI görselini tüm boyutlar için en iyi duruma getirme"
description: "Power BI Desktop ve Power BI hizmetindeki görselleri Power BI telefon uygulamaları için en iyi duruma getirmeyi öğrenin."
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
ms.openlocfilehash: a059c01d6e9e08851434f71a1f36ac096054e291
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2017
---
# <a name="optimize-a-power-bi-visual-for-any-size"></a>Power BI görselini tüm boyutlar için en iyi duruma getirme
Pano veya raporunuzdaki görsellerin *yanıt verir* duruma gelip ekran boyutu ne olursa olsun maksimum sayıda veri ve öngörü görüntüleyecek şekilde dinamik olarak değişmesini sağlayabilirsiniz.

Power BI, veri görünümü önceliğini görsel boyutuna göre değiştirir. Örneğin, görselin küçülse bile bilgilendirici olması için otomatik olarak boşluğu kaldırır ve açıklamayı görselin üst tarafına taşır. Yanıt verme özellikle telefonlarda kullanılan Power BI mobil uygulamalarındaki görseller için faydalıdır.

![Yanıt veren görsel yeniden boyutlandırma](media/desktop-create-responsive-visuals/power-bi-responsive-visual.gif)

Yanıt verme özelliğini X ve Y ekseni ile dilimleyicilere sahip tüm görseller için etkinleştirebilirsiniz.

## <a name="turn-on-responsiveness-in-power-bi-desktop"></a>Power BI Desktop'ta yanıt verme özelliğini etkinleştirme
1. Power BI Desktop'ın **Görünüm** sekmesinden **Masaüstü Düzeni**'nde olduğunuzdan emin olun.
   
    ![Masaüstü Düzeni simgesi](media/desktop-create-responsive-visuals/power-bi-desktop-layout.png)
2. Bir görsel seçtikten sonra **Görsel Öğeler** bölmesinin **Biçim** bölümünü seçin.
3. **Genel** bölümünü genişletip **Yanıt veriyor** ayarını **Açık** olarak belirleyin.
   
    ![Yanıt veriyor ayarı açık](media/desktop-create-responsive-visuals/power-bi-turn-responsive-on.png)
   
     [Telefon için en iyi duruma getirilmiş bir rapor oluşturup](desktop-create-phone-report.md) bu görseli eklediğinizde yanıt veren boyutlandırma gerçekleşecektir.

## <a name="turn-on-responsiveness-in-the-power-bi-service"></a>Power BI hizmetinde yanıt verme özelliğini etkinleştirme
Power BI hizmetindeki bir raporda bulunan bir görsel için yanıt verme özelliğini etkinleştirebilirsiniz. Bunun için raporu düzenleme iznine sahip olmanız gerekir.

1. Power BI hizmetinde ([https://powerbi.com](https://powerbi.com)) bulunan bir raporda **Raporu Düzenle**'yi seçin.
2. Bir görsel seçtikten sonra **Görsel Öğeler** bölmesinin **Biçim** bölümünü seçin.
3. **Genel** bölümünü genişletip **Yanıt veriyor** ayarını **Açık** olarak belirleyin.
   
    ![Yanıt veriyor ayarı açık](media/desktop-create-responsive-visuals/power-bi-turn-responsive-on.png)
   
     [Bir panonun telefon görünümünü oluşturup](service-create-dashboard-mobile-phone-view.md) bu görseli eklediğinizde esnek boyutlandırma gerçekleşecektir.

## <a name="next-steps"></a>Sonraki adımlar
* [Power BI telefon uygulamaları için en iyi duruma getirilmiş raporlar oluşturma](desktop-create-phone-report.md)
* [Power BI'da bir panonun telefon görünümünü oluşturma](service-create-dashboard-mobile-phone-view.md)
* [View Power BI reports optimized for your phone (Telefonunuz için en iyi duruma getirilmiş Power BI raporlarını görüntüleme)](mobile-apps-view-phone-report.md)
* Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

