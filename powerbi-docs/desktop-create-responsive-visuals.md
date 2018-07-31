---
title: Power BI görselini tüm boyutlar için en iyi duruma getirme
description: Power BI Desktop ve Power BI hizmetinde var olan raporlardaki görselleri Power BI telefon uygulamaları için en iyi duruma getirmeyi öğrenin.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 04/13/2018
ms.author: maggies
LocalizationGroup: Create reports
ms.openlocfilehash: a6e683318c00a800f69334f90ce3a71d74489030
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34290534"
---
# <a name="optimize-a-power-bi-visual-for-any-size"></a>Power BI görselini tüm boyutlar için en iyi duruma getirme
Varsayılan olarak, yeni bir rapor oluşturduğunuzda görseller *duyarlıdır*: Ekran boyutu ne olursa olsun, en fazla miktarda veri ve içgörü görüntülemek üzere dinamik olarak değişirler. Eski raporlar için görselleri de dinamik olarak yeniden boyutlandırılacak şekilde ayarlayabilirsiniz.

Power BI, veri görüntüleme önceliğini görsel boyutuna göre değiştirir. Örneğin görselin küçülse dahi bilgilendirici olması için otomatik olarak boşluğu kaldırır ve açıklamayı görselin üst tarafına taşır. Yanıt verme özellikle telefonlarda kullanılan Power BI mobil uygulamalarındaki görseller için faydalıdır.

![Yanıt veren görsel yeniden boyutlandırma](media/desktop-create-responsive-visuals/power-bi-responsive-visual.gif)

X ve Y eksenlerine ve dilimleyicilere sahip herhangi bir görsel, duyarlı bir şekilde yeniden boyutlandırılabilir.

## <a name="turn-on-responsiveness-in-power-bi-desktop"></a>Power BI Desktop'ta yanıt verme özelliğini etkinleştirme
1. Power BI Desktop'taki eski bir raporun **Görünüm** sekmesinden **Masaüstü Düzeni**'nde olduğunuzdan emin olun.
   
    ![Masaüstü Düzeni simgesi](media/desktop-create-responsive-visuals/power-bi-desktop-layout.png)
2. Bir görsel seçtikten sonra **Görsel Öğeler** bölmesinin **Biçim** bölümünü seçin.
3. **Genel** bölümünü genişletip **Yanıt veriyor** ayarını **Açık** olarak belirleyin.
   
    ![Yanıt veriyor ayarı açık](media/desktop-create-responsive-visuals/power-bi-turn-responsive-on.png)
   
     [Telefon için en iyi duruma getirilmiş bir rapor oluşturup](desktop-create-phone-report.md) bu görseli eklediğinizde yanıt veren boyutlandırma gerçekleşecektir.

## <a name="turn-on-responsiveness-in-the-power-bi-service"></a>Power BI hizmetinde yanıt verme özelliğini etkinleştirme
Power BI hizmetindeki eski bir raporda bulunan bir görsel için yanıt verme özelliğini etkinleştirebilirsiniz. Bunun için raporu düzenleme iznine sahip olmanız gerekir.

1. Power BI hizmetinde ([https://powerbi.com](https://powerbi.com)) bulunan bir raporda **Raporu Düzenle**'yi seçin.
2. Bir görsel seçtikten sonra **Görsel Öğeler** bölmesinin **Biçim** bölümünü seçin.
3. **Genel** bölümünü genişletip **Yanıt veriyor** ayarını **Açık** olarak belirleyin.
   
    ![Yanıt veriyor ayarı açık](media/desktop-create-responsive-visuals/power-bi-turn-responsive-on.png)
   
     [Bu raporun telefon görünümünü oluşturup](desktop-create-phone-report.md) bu görseli eklediğinizde esnek boyutlandırma gerçekleşecektir.

## <a name="next-steps"></a>Sonraki adımlar
* [Power BI telefon uygulamaları için en iyi duruma getirilmiş raporlar oluşturma](desktop-create-phone-report.md)
* [View Power BI reports optimized for your phone (Telefonunuz için en iyi duruma getirilmiş Power BI raporlarını görüntüleme)](mobile-apps-view-phone-report.md)
* Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

