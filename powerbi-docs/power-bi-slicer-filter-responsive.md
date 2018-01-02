---
title: "Power BI’da yeniden boyutlandırabileceğiniz, yanıt veren bir dilimleyici oluşturma"
description: "Raporunuza uygun şekilde yeniden boyutlandırabileceğiniz, hızlı yanıt veren bir dilimleyici oluşturmayı öğrenin"
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
ms.date: 12/08/2017
ms.author: maggies
ms.openlocfilehash: f95f126cc6a7c95fbe3227b712281a7d3f81e320
ms.sourcegitcommit: b780b7108fd9b52398b8377b52836f0e0fedc96e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/09/2017
---
# <a name="create-a-responsive-slicer-you-can-resize-in-power-bi-preview"></a>Power BI’da yeniden boyutlandırabileceğiniz, hızlı yanıt veren bir dilimleyici oluşturma (Önizleme)

Hızlı yanıt veren dilimleyiciler, yeniden boyutlandırılarak raporunuzdaki herhangi bir alana sığdırılabilir. Hızlı yanıt veren dilimleyicileri yatay, kare veya dikey gibi farklı boyut ve şekillerde yeniden boyutlandırabilirsiniz ve siz bunları yaptığınız sırada dilimleyicideki değerler kendi kendine yeniden düzenlenir. Power BI Desktop’ta ve Power BI hizmetinde yatay dilimleyicilerin ve tarih/aralık dilimleyicilerinin hızlı yanıt vermesini sağlayabilirsiniz. Tarih/aralık dilimleyicileri, bunları parmak ucunuzla daha kolay değiştirebilmeniz için geliştirilmiş dokunma alanlarına da sahiptir. Hızlı yanıt veren dilimleyicileri istediğiniz kadar büyük veya küçük bir boyuta getirebilirsiniz. Ayrıca bunlar, hem Power BI hizmetinde hem de Power BI mobil uygulamalarında otomatik olarak raporlara uyacak şekilde yeniden boyutlandırılır. 

![Hızlı yanıt veren dilimleyiciler çeşitli şekillerde olabilir](media/power-bi-slicer-filter-responsive/responsive-slicer-gif.gif)

## <a name="create-a-slicer"></a>Dilimleyici oluşturma

Dinamik dilimleyici oluşturmanın ilk adımı basit bir dilimleyici oluşturmaktır. 

1. **Görsel Öğeler** bölmesinde **Dilimleyici** simgesini ![Dilimleyici simgesi](media/power-bi-slicer-filter-responsive/power-bi-slicer-icon.png) seçin.
2. Filtre uygulamak istediğiniz alanı **Alan** seçeneğine sürükleyin.

    ![Dilimleyiciye alan ekleme](media/power-bi-slicer-filter-responsive/power-bi-slicer-field.png)

## <a name="convert-to-a-horizontal-slicer"></a>Yatay dilimleyiciye dönüştürme

1. **Görsel Öğeler** bölmesinde, dilimleyici seçiliyken **Biçim** sekmesini seçin.
2. **Genel** bölümünü genişletin ve **Yönlendirme** için **Yatay**’ı seçin.

    ![Dilimleyici yatay olarak ayarlama](media/power-bi-slicer-filter-responsive/power-bi-slicer-horizontal.png) 

1.  Muhtemelen daha fazla değer gösterilmesi için daha geniş olmasını istersiniz.

     ![Dilimleyiciyi genişletme](media/power-bi-slicer-filter-responsive/power-bi-slicer-wide-horizontal.png)

## <a name="make-it-responsive-and-experiment-with-it"></a>Dilimleyiciyi hızlı yanıt verir hale getirme ve denemeler yapma

Bu adım kolaydır. 

1. **Biçim** sekmesinin **Genel** bölümündeki **Yönlendirme**’nin hemen altında bulunan **Yanıt veriyor (Önizleme)	** seçeneğini **Açık** konumuna getirin.  

    ![Dilimleyici artık hızlı yanıt verir](media/power-bi-slicer-filter-responsive/power-bi-slicer-wide-responsive.png)

1. Artık dilimleyiciyle deneme yapabilirsiniz. Köşeleri sürükleyerek kısaltın, uzatın, genişletin ve daraltın. Yeterince küçültürseniz bir filtre simgesine dönüşür.

    ![Çok küçük olduğu için filtre simgesine dönüşmüş hızlı yanıt veren dilimleyici](media/power-bi-slicer-filter-responsive/power-bi-slicer-small-filter-icon.png)

## <a name="add-it-to-a-phone-report-layout"></a>Bir telefon raporu düzenine ekleyin

Power BI Desktop’ta bir raporun her sayfası için telefon düzeni oluşturabilirsiniz. Bir sayfada telefon düzeni varsa, bir cep telefonunda portre görünümünde görüntülenir. Aksi takdirde, yatay görünümde görüntülenmesi gerekir. 

1. **Görünüm** menüsünde, select **Telefon Düzeni**’ni seçin.

     ![Telefon düzeni simgesi, Görünüm menüsü](media/power-bi-slicer-filter-responsive/power-bi-phone-layout-menu.png)
    
1. Telefonlara yönelik raporda yer almasını istediğiniz tüm görsel öğeleri ızgaraya sürükleyin. Hızlı yanıt veren dilimleyiciyi sürükleyerek istediğiniz boyuta getirebilirsiniz; bu örnekte bir filtre simgesine dönüşmüştür.

    ![Dilimleyiciyi telefon rapor düzenine ekleme](media/power-bi-slicer-filter-responsive/power-bi-slicer-phone-layout.png)

[Power BI mobil uygulamaları için iyileştirilmiş raporlar](desktop-create-phone-report.md) oluşturma hakkında daha fazla bilgi edinin.

## <a name="make-a-time-or-range-slicer-responsive"></a>Bir zaman veya aralık dilimleyicisinin hızlı yanıt vermesini sağlama

Aynı adımları izleyerek bir kutucuk veya aralık dilimleyicisinin hızlı yanıt vermesini sağlayabilirsiniz. **Yanıt veriyor** seçeneğini **Açık** konuma getirdiğinizde birkaç şeyi fark edersiniz:

- Görsel öğeler, tuvalde izin verilen boyuta bağlı olarak giriş kutularının sıralamasını iyileştirir. 
- Tuvalde izin verilen boyutuna bağlı olarak dilimleyicinin mümkün olduğunca kullanılabilir hale getirilmesi için veri öğelerinin görüntülenmesi iyileştirilir. 
- Kaydırıcılardaki yeni yuvarlak tutamaçlar, dokunarak etkileşim kurmayı iyileştirir. 
- Bir görsel öğe kullanışlılığını kaybedecek kadar küçüldüğünde, bir görsel öğe türünü temsil eden bir simgeye dönüşür. Bununla etkileşim kurmak için öğeye iki kez dokunarak odak modunda açabilirsiniz. Bu, rapor sayfasında işlevsellik kaybı yaşanmadan yer tasarrufu yapılmasını sağlar.

## <a name="next-steps"></a>Sonraki adımlar

- [Öğretici: Power BI hizmetindeki dilimleyiciler](power-bi-visualization-slicers.md)
- Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)