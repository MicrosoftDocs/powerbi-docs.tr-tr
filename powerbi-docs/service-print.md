---
title: Power BI hizmetinden yazdırma
description: Power BI'dan bir pano, kutucuk veya rapor sayfasını yazdırma.
author: mihart
manager: kfile
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 03/01/2018
ms.author: mihart
LocalizationGroup: Common tasks
ms.openlocfilehash: d5859c0b59717a4af432c5fb7b526fa62ff03f59
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34242990"
---
# <a name="printing-from-power-bi-service"></a>Power BI hizmetinden yazdırma
Power BI hizmetinden bir panonun tamamını, pano kutucuğunu, rapor sayfasını veya rapor görselini yazdırın. Raporlar yalnızca sayfa sayfa yazdırılabilir; tek seferde raporun tamamını yazdıramazsınız.

> [!NOTE]
> Yazdırma özelliği yalnızca Power BI hizmetinde kullanılabilir ve Power BI Desktop ile kullanılamaz.
> 
> 

Amanda'nın panosundan ve raporundan yazdırma işlemi gerçekleştirmesini izleyin. Ardından kendiniz denemek için videonun altındaki adım adım yönergeleri uygulayın.

<iframe width="560" height="315" src="https://www.youtube.com/embed/jtlLGRKBvXY" frameborder="0" allowfullscreen></iframe>

## <a name="print-a-dashboard"></a>Pano yazdırma
1. Yazdırmak istediğiniz panoyu açın.
2. Sağ üst köşedeki üç nokta (...) simgesini seçin ve **Panoyu yazdır** seçeneğini belirleyin.
   
    ![Panoyu yazdır seçeneği](media/service-print/pbi_print_dash_ellipses.png)
3. Tarayıcınızın Yazdır penceresi açılır. Ayarları ve yazdırma hedefini seçip **Yazdır** seçeneğini belirleyin.
   
   > [!NOTE]
   > Göreceğiniz yazdırma iletişim kutusu, kullandığınız tarayıcıya göre değişir.
   > 
   
    ![yazdır iletişim kutusu](media/service-print/pbi_print_dash_new2.png)

## <a name="print-a-dashboard-tile"></a>Pano kutucuğu yazdırma
1. [Kutucuğu Odak modunda açmak için](service-focus-mode.md) üç noktayı ve Odak simgesini ![Odak simgesi](media/service-print/power-bi-focus-icon.png) seçin.
   
    ![üç nokta menüsü](media/service-print/menu-options.png)
2. Kutucuğu [tam ekran modunda](service-fullscreen-mode.md) açmak için üst taraftaki gezinti çubuğundan tam ekran simgesini ![tam ekran simgesi](media/service-print/power-bi-full-screen-icon.png) seçin.
3. Seçenekler menüsünün gösterilmesi için kutucuğun üzerine gelin.
   
    ![tam ekran seçenekler menüsü](media/service-print/menu-options-new.png)
4. Yazdır simgesini ![yazdır simgesi](media/service-print/print-icon.png) seçin.     
   
   > [!NOTE]
   > Göreceğiniz yazdırma iletişim kutusu, kullandığınız tarayıcıya göre değişir.
   > 
   > 

## <a name="print-a-report-page"></a>Rapor sayfası yazdırma
Tek seferde yalnızca bir rapor sayfası yazdırılabilir.

1. Raporu Okuma Görünümü'nde veya Düzenleme Görünümü'nde açın.
2. Geçerli rapor sayfasını yazdırmak için **Dosya** > **Yazdır** seçeneğini belirleyin.
   
    ![Power BI Dosya menüsü](media/service-print/power-bi-print.png)
3. Tarayıcınızın Yazdır penceresi açılır.
   
   > [!NOTE]
   > Göreceğiniz yazdırma iletişim kutusu, kullandığınız tarayıcıya göre değişir.
   > 
   > 

## <a name="print-a-report-visual"></a>Rapor görseli yazdırma
1. [Görseli Odak modunda açmak](service-focus-mode.md) için kutucuğun üzerine gelin ve sağ üst köşedeki Odak simgesini ![Odak simgesi](media/service-print/power-bi-focus-icon.png) seçin.
2. Yukarıdaki *Rapor sayfası yazdırma* bölümünde bulunan 2. ve 3. adımları uygulayın.

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme
* S: **Yazdır** düğmesini bulamıyorum.    
* C: Power BI Desktop sürümünde yazdırma desteklenmez.  Yazdırma yalnızca Power BI hizmetinde çalışır.
* S: Tüm rapor sayfalarını tek seferde yazdıramıyorum.    
* C: Doğru. Rapor sayfaları yalnızca tek tek yazdırılabilir.
* S: PDF olarak yazdıramıyorum.    
* Y: Bu seçeneği yalnızca tarayıcınızda PDF sürücüsünü yapılandırmış olmanız halinde görürsünüz.    
* S: **Yazdır** seçeneğini belirlediğimde görüntülediğim ekran burada gösterilen ile aynı değil.    
* Y: Yazdır ekranları, tarayıcı ve yazılım sürümüne göre değişiklik gösterir.
* S: Çıktım doğru ölçeklendirilmemiş.  Panom sayfaya sığmıyor. Ölçeklendirme ve yönlendirme ile ilgili diğer sorular.    
* Y: Yazdırılan kopyanın, içeriğin Power BI hizmetinde göründüğü haliyle aynı olacağını garanti edemiyoruz. Ölçeklendirme, kenar boşlukları, görsel ayrıntıları, yönlendirme ve boyut gibi konular Power BI tarafından denetlenmez. Bu gibi sorunlarla ilgili yardım almak için, kullandığınız tarayıcıya yönelik belgelere göz atın.      

## <a name="next-steps"></a>Sonraki adımlar
[İş arkadaşlarınızla ve diğer kişilerle pano ve rapor paylaşma](service-share-dashboards.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

