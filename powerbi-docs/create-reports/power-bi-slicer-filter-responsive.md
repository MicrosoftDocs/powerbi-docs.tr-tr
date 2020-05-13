---
title: Power BI’da yeniden boyutlandırabileceğiniz, yanıt veren bir dilimleyici oluşturma
description: Raporunuza uygun şekilde yeniden boyutlandırabileceğiniz, hızlı yanıt veren bir dilimleyici oluşturmayı öğrenin
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 04/06/2020
ms.author: maggies
LocalizationGroup: Create reports
ms.openlocfilehash: f4e70bdcd877c29063a73cc24111d4dc04aa39b9
ms.sourcegitcommit: 0e9e211082eca7fd939803e0cd9c6b114af2f90a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/13/2020
ms.locfileid: "83280990"
---
# <a name="create-a-responsive-slicer-you-can-resize-in-power-bi"></a>Power BI’da yeniden boyutlandırabileceğiniz, yanıt veren bir dilimleyici oluşturma

[!INCLUDE [applies-to](../includes/applies-to.md)] [!INCLUDE [yes-desktop](../includes/yes-desktop.md)] [!INCLUDE [yes-service](../includes/yes-service.md)]

Hızlı yanıt veren dilimleyiciler, yeniden boyutlandırılarak raporunuzdaki herhangi bir alana sığdırılabilir. Hızlı yanıt veren dilimleyicileri yatay, kare veya dikey gibi farklı boyut ve şekillerde yeniden boyutlandırabilirsiniz ve siz bunları yaptığınız sırada dilimleyicideki değerler kendi kendine yeniden düzenlenir. Power BI Desktop’ta ve Power BI hizmetinde yatay dilimleyicilerin ve tarih/aralık dilimleyicilerinin hızlı yanıt vermesini sağlayabilirsiniz. Tarih/aralık dilimleyicileri, bunları parmak ucunuzla daha kolay değiştirebilmeniz için geliştirilmiş dokunma alanlarına da sahiptir. Hızlı yanıt veren dilimleyicileri istediğiniz kadar büyük veya küçük bir boyuta getirebilirsiniz. Ayrıca bunlar, hem Power BI hizmetinde hem de Power BI mobil uygulamalarında otomatik olarak raporlara uyacak şekilde yeniden boyutlandırılır. 

![Hızlı yanıt veren dilimleyiciler çeşitli şekillerde olabilir](media/power-bi-slicer-filter-responsive/power-bi-slicer-filter-responsive-0-slicer.gif)

## <a name="create-a-slicer"></a>Dilimleyici oluşturma

Dinamik dilimleyici oluşturmanın ilk adımı basit bir dilimleyici oluşturmaktır. 

1. **Görsel Öğeler** bölmesinde ![Dilimleyici](media/power-bi-slicer-filter-responsive/power-bi-slicer-filter-responsive-0-slicer-icon.png) simgesini **Dilimleyici simgesi** seçin.
2. Filtre uygulamak istediğiniz alanı **Alan** seçeneğine sürükleyin.

    ![Dilimleyiciye alan ekleme](media/power-bi-slicer-filter-responsive/power-bi-slicer-filter-responsive-1-create.png)

## <a name="convert-to-a-horizontal-slicer"></a>Yatay dilimleyiciye dönüştürme

1. **Görsel Öğeler** bölmesinde, dilimleyici seçiliyken **Biçim** sekmesini seçin.
2. **Genel** bölümünü genişletin ve **Yönlendirme** için **Yatay**’ı seçin.

    ![Dilimleyici yatay olarak ayarlama](media/power-bi-slicer-filter-responsive/power-bi-slicer-filter-responsive-2-horizontal.png) 

1.  Muhtemelen daha fazla değer gösterilmesi için daha geniş olmasını istersiniz.

     ![Dilimleyiciyi genişletme](media/power-bi-slicer-filter-responsive/power-bi-slicer-filter-responsive-3-wider.png)

## <a name="make-it-responsive-and-experiment-with-it"></a>Dilimleyiciyi hızlı yanıt verir hale getirme ve denemeler yapma

Bu adım kolaydır. 

1. **Biçim** sekmesinin **Genel** bölümündeki **Yönlendirme**’nin hemen altında bulunan **Yanıt veriyor** seçeneğini **Açık** konumuna getirin.  

    ![Dilimleyici artık hızlı yanıt verir](media/power-bi-slicer-filter-responsive/power-bi-slicer-filter-responsive-4-responsive-on.png)

1. Artık dilimleyiciyle deneme yapabilirsiniz. Köşeleri sürükleyerek kısaltın, uzatın, genişletin ve daraltın. Yeterince küçültürseniz bir filtre simgesine dönüşür.

    ![Çok küçük olduğu için filtre simgesine dönüşmüş hızlı yanıt veren dilimleyici](media/power-bi-slicer-filter-responsive/power-bi-slicer-filter-responsive-5-mini-icon.png)

## <a name="add-it-to-a-phone-report-layout"></a>Bir telefon raporu düzenine ekleyin

Power BI Desktop’ta bir raporun her sayfası için telefon düzeni oluşturabilirsiniz. Bir sayfada telefon düzeni varsa, bir cep telefonunda portre görünümünde görüntülenir. Aksi takdirde, yatay görünümde görüntülenmesi gerekir. 

1. **Görünüm** menüsünde, select **Telefon Düzeni**’ni seçin.

     ![Telefon düzeni simgesi, Görünüm menüsü](media/power-bi-slicer-filter-responsive/power-bi-slicer-filter-responsive-6-phone-layout-button.png)
    
1. Telefonlara yönelik raporda yer almasını istediğiniz tüm görsel öğeleri ızgaraya sürükleyin. Hızlı yanıt veren dilimleyiciyi sürükleyerek istediğiniz boyuta getirebilirsiniz; bu örnekte bir filtre simgesine dönüşmüştür.

    ![Dilimleyiciyi telefon rapor düzenine ekleme](media/power-bi-slicer-filter-responsive/power-bi-slicer-filter-responsive-7-phone-slicer-icon.png)

[Power BI mobil uygulamaları için iyileştirilmiş raporlar](desktop-create-phone-report.md) oluşturma hakkında daha fazla bilgi edinin.

## <a name="make-a-time-or-range-slicer-responsive"></a>Bir zaman veya aralık dilimleyicisinin hızlı yanıt vermesini sağlama

Aynı adımları izleyerek bir kutucuk veya aralık dilimleyicisinin hızlı yanıt vermesini sağlayabilirsiniz. **Yanıt veriyor** seçeneğini **Açık** konuma getirdiğinizde birkaç şeyi fark edersiniz:

- Görsel öğeler, tuvalde izin verilen boyuta bağlı olarak giriş kutularının sıralamasını iyileştirir. 
- Tuvalde izin verilen boyutuna bağlı olarak dilimleyicinin mümkün olduğunca kullanılabilir hale getirilmesi için veri öğelerinin görüntülenmesi iyileştirilir. 
- Kaydırıcılardaki yeni yuvarlak tutamaçlar, dokunarak etkileşim kurmayı iyileştirir. 
- Bir görsel öğe kullanışlılığını kaybedecek kadar küçüldüğünde, bir görsel öğe türünü temsil eden bir simgeye dönüşür. Bununla etkileşim kurmak için öğeye iki kez dokunarak odak modunda açabilirsiniz. Bu, rapor sayfasında işlevsellik kaybı yaşanmadan yer tasarrufu yapılmasını sağlar.

## <a name="next-steps"></a>Sonraki adımlar

- [Power BI hizmetindeki dilimleyiciler](../visuals/power-bi-visualization-slicers.md)
- Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)