---
title: "Power BI'daki dilimleyiciler (Eğitim)"
description: "Öğretici: Power BI'daki dilimleyiciler"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: zIZPA0UrJyA
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 03/05/2018
ms.author: v-thepet
LocalizationGroup: Visualizations
ms.openlocfilehash: cfa4c0f17c67a036b7d01744da1b5247345c493a
ms.sourcegitcommit: 4217430c3419046c3a90819c34f133ec7905b6e7
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/12/2018
---
# <a name="slicers-in-power-bi-tutorial"></a>Power BI'daki dilimleyiciler (Eğitim)
Satıştan sorumlu Genel Müdür Yardımcısı, tüm bölümle ilgili olarak ve her bir District Manager için bazı ölçümlere göz atabilmek istiyor. Bu amaçla her yönetici için ayrı bir rapor oluşturabilir veya bir dilimleyici kullanabilir. Dilimleyici, rapordaki diğer görselleştirmelerde gösterilen veri kümesi bölümünü daraltır. Dilimleyiciler, filtrelemenin alternatif bir yoludur.

Bu öğreticide, bir dilimleyici oluşturup biçimlendirme ve bu dilimleyiciyi kullanarak bir raporu filtreleme konusunda size yol göstermek için ücretsiz [Perakende Analizi Örneği](sample-retail-analysis.md) kullanılmaktadır. Dilimleyicileri biçimlendirme ve kullanma yöntemlerini keşfetmekten keyif alacağınızı umuyoruz. 

![dilimleyici](media/power-bi-visualization-slicers/slicer2.gif)

## <a name="when-to-use-a-slicer"></a>Dilimleyici ne zaman kullanılır?
Aşağıdakileri yapmak istediğinizde dilimleyicileri kullanmanız oldukça faydalı olacaktır:

* Daha kolay erişim sağlamak amacıyla, sık kullanılan veya önemli filtreleri rapor tuvalinde görüntülemek.
* Açılan bir listeyi açmak zorunda kalmadan, o sırada filtreli olan durumu daha kolay bir şekilde görüntülemek. 
* Veri tablolarında gereksiz ve gizli sütunlara göre filtreleme yapmak.
* Dilimleyicileri önemli görsellerin yanına koyarak daha odaklı raporlar oluşturmak.

Power BI dilimleyicileri aşağıdaki sınırlamalara sahiptir:

- Dilimleyiciler giriş alanlarını desteklemez.
- Dilimleyiciler panolara sabitlenemez.
- Detaya gitme özelliği, dilimleyiciler için desteklenmez.
- Dilimleyiciler, görsel düzeyi filtrelerini desteklemez.

## <a name="create-a-slicer"></a>Dilimleyici oluşturma

Bu öğreticide bir liste dilimleyici kullanılmaktadır. Sayısal ve tarih/saat veri türleri, aralık dilimleyicilere sahip olabilir. Aralık dilimleyiciler oluşturma ve bunları kullanma hakkında daha fazla bilgi için [Power BI Desktop uygulamasındaki sayısal aralık dilimleyiciyi kullanma](desktop-slicer-numeric-range.md) başlıklı makaleye bakın veya aşağıdaki videoyu izleyin.
<iframe width="560" height="315" src="https://www.youtube.com/embed/zIZPA0UrJyA" frameborder="0" allowfullscreen></iframe>

1. Power BI Desktop veya Power BI hizmetinde, [Perakende Analizi Örneği](sample-retail-analysis.md)’ni [Düzeleme Görünümü](service-interact-with-a-report-in-editing-view.md)’nde açın ve [yeni bir rapor sayfası ekleyin](power-bi-report-add-page.md).
2. Alanlar bölmesinden, yeni bir görselleştirme oluşturmak için Bölge bölümünde **Bölge Yöneticisi**’ni seçin.
    
    ![yeni grafik](media/power-bi-visualization-slicers/1-new-vis.png)
    
3. Yeni görselleştirmeyi bir dilimleyiciye dönüştürmek için Görselleştirmeler bölmesindeki **Dilimleyici** simgesini ![dilimleyici simgesi](media/power-bi-visualization-slicers/slicer-icon.png) seçin. 
    
    ![dilimleyiciye dönüştürme](media/power-bi-visualization-slicers/2-slicer.png)

Ayrıca yeni bir dilimleyici oluşturmak için Dilimleyici simgesini seçip, Alan kutusunu doldurmak için bir veri alanını seçebilir veya bu Alan kutusuna sürükleyebilirsiniz.

>[!TIP]
>Liste dilimleyici öğelerini veri değerlerine göre sıralayabilirsiniz. Dilimleyici öğelerini ters alfabetik düzende sıralamak için dilimleyicinin sağ üst köşesindeki üç noktayı (...) seçin ve **Bölge Yöneticisine Göre Sırala** seçeneğini belirleyin. Ayar, varsayılan olarak alfabetik düzende artar ancak artan veya azalan sıra arasında geçiş yapar. 

## <a name="format-the-slicer"></a>Dilimleyiciyi biçimlendirme
Görsel biçimlendirmesini Bölge Yöneticisi dilimleyicisine uygulayın.
1. Biçimlendirme denetimlerini görüntülemek için Görselleştirmeler bölmesinde, Dilimleyici seçiliyken Biçim simgesini ![](media/power-bi-visualization-slicers/power-bi-paintroller.png) seçin. 
    
    ![biçimlendirme](media/power-bi-visualization-slicers/3-format.png)
    
2. Seçenekleri görüntülemek ve düzenlemek için her kategorinin yanındaki açılan oklara tıklayın. 

### <a name="general-options"></a>Genel seçenekler
1. **Anahat rengi**’nin altında kırmızıyı seçin ve **Anahat ağırlığı**’nı “2” olarak değiştirin. Etkinleştirildiğinde bu, üst bilgi ve öğe ana hatlarının veya alt çizgilerinin rengini ve kalınlığını ayarlar. 
2. Yönlendirme bölümünde varsayılan ayar Dikey’dir ve öğelerin önünde seçim kutularının bulunduğu dikey bir liste oluşturur. Yatay olarak düzenlenmiş öğelerle dilimleyici oluşturmak için **Yatay** seçeneğini belirleyin. Yatay yönlendirme, dilimleyicinin boyutuna, şekline ve öğe biçimlendirmesine bağlı olarak çeşitli metin, düğme veya kutucuk düzenlemeleri oluşturabilir. 
    
    ![yatay](media/power-bi-visualization-slicers/4-horizontal.png)
    
3. Yatay dilimleyici öğelerinin boyutunu ve düzenlemesini, dilimleyici boyutu ve şekli ile eşleşecek biçimde değiştiren **Esnek** düzeni açın. Dilimleyici çok küçük boyutta olduğunda bir filtre simgesi haline gelir. 
    
    ![esnek](media/power-bi-visualization-slicers/5-responsive.png)
    
    >[!NOTE]
    >Esnek düzen değişiklikleri, ayarladığınız üst bilgi ve öğe biçimlendirmesini geçersiz kılabilir. 
    
4. **X Konumu**, **Y Konumu**, **Genişlik** ve **Yükseklik** bölümündeki sayısal duyarlıkla dilimleyici konumunu ve boyutunu ayarlayın veya yatay düğme sırası gibi farklı öğe boyutları ve düzenlemeleri oluşturmak için dilimleyiciyi doğrudan tuval üzerinde taşıyıp yeniden boyutlandırın. 

    ![yatay düğmeler](media/power-bi-visualization-slicers/6-buttons.png)

Yatay yönlendirme ve esnek biçimlendirme hakkında daha fazla bilgi için bkz. [Power BI’da yeniden boyutlandırabileceğiniz esnek bir dilimleyici oluşturma](power-bi-slicer-filter-responsive.md).

### <a name="selection-controls-options"></a>Seçim Denetimleri seçenekleri
1. Show Select All (Tümünü Seç’i Göster) varsayılan olarak Kapalı’dır. Dilimleyiciye, açılıp kapatıldığında tüm öğeleri seçen veya tüm öğelerin seçimini kaldıran bir Tümünü seç öğesi eklemek için bu seçeneği **Açık** duruma getirin. Tüm öğeler seçiliyken öğeye tıklandığında öğenin seçimi kaldırılır ve “is-not” türünde bir filtreye izin verilir. 
    
    ![tümünü seç](media/power-bi-visualization-slicers/7-select-all.png)
    
2. Tek Seçim varsayılan olarak Açık’tır. Öğeye tıklandığında bu öğe seçilir, tıklama sırasında CTRL tuşu basılı tutulduğunda ise birden çok öğe seçilir. CTRL tuşu basılı tutulmadan birden çok öğenin seçilmesini sağlamak için Tek Seçim’i **Kapalı** duruma getirin. Bir öğeye tıklandığında bu öğenin seçimi kaldırılır. 

### <a name="header-options"></a>Üst bilgi seçenekleri
Üst bilgi varsayılan olarak Açık’tır ve dilimleyicinin üst tarafında veri alanı adını gösterir. 
1. **Yazı tipi rengini** kırmızı **Metin boyutunu** 14 pt, **Yazı tipi ailesini** ise Arial Black olarak ayarlayacak şekilde üst bilgi metnini biçimlendirin. 
2. Anahat bölümünde Genel seçeneklerde ayarladığınız boyuta ve renge sahip bir alt çizgi oluşturmak için **Yalnızca alt** seçeneğini belirleyin. 

### <a name="item-options"></a>Öğe seçenekleri
1. **Yazı tipi rengini** siyah, **Arka planı** açık kırmızı, **Metin boyutunu** 10 pt, **Yazı tipi ailesini** ise Arial olarak ayarlayacak şekilde öğe metnini ve arka planını biçimlendirin. 
2. Her bir öğenin çevresine Genel seçeneklerde ayarladığınız boyuta ve renge sahip bir kenarlık çizmek için **Çerçeve** seçeneğini belirleyin. 
    
    ![biçimlendirilmiş](media/power-bi-visualization-slicers/8-formatted.png)
    
    >[!TIP]
    >- Yatay Yönlendirme kullanıldığında, seçimi kaldırılan öğeler seçilen metin ve arka plan renklerini gösterirken seçilen öğeler, genellikle beyaz metinli siyah arka plan olan sistem varsayılanını kullanır. 
    >- Dikey Yönlendirme kullanıldığında, öğeler her zaman ayarlanan renkleri gösterir ve seçim kutuları seçildiğinde her zaman siyah olur. 

### <a name="other-formatting-options"></a>Diğer biçimlendirme seçenekleri
Diğer biçimlendirme seçenekleri varsayılan olarak kapalıdır. **Açık** duruma getirildiğinde: 
- **Başlık:** Dilimleyicinin üst tarafına bir başlık ekler ve bu başlığı biçimlendirir (üst bilgiye ek olarak ve üst bilgiden bağımsız olarak). 
- **Arka plan:** Genel dilimleyiciye bir arka plan rengi ekler ve bunun saydamlığını ayarlar.
- **Görünüşü kilitle:** Dilimleyici yeniden boyutlandırıldıysa dilimleyicinin şeklini korur.
- **Kenarlık:** Dilimleyicinin çevresine 1 piksel kenarlık ekler ve bunun rengini ayarlar. (Bu dilimleyici kenarlığı Genel Anahat ayarlarından ayrıdır ve bunlardan etkilenmez.) 

## <a name="sync-and-use-the-slicer-on-other-pages"></a>Diğer sayfalarda dilimleyiciyi eşitleme ve kullanma
Şubat 2018 tarihinde yapılan Power BI güncelleştirmesinden itibaren bir dilimleyiciyi eşitleyebilir ve bir rapordaki tüm sayfalarda kullanabilirsiniz. 
1. Bölge Yöneticisi seçiliyken Power BI Desktop’ta Görünüm menüsünden **Dilimleyicileri eşitle** seçeneğini belirleyin veya Power BI hizmetinde **Dilimleyicileri eşitle bölmesini** açık duruma getirin. Dilimleyicileri Eşitle bölmesi görünür. 
    
    ![dilimleyicileri eşitleme](media/power-bi-visualization-slicers/9-sync-slicers.png)
    
2. İlk sütunda **Genel Bakış**’ı ve dilimleyicinin eşitlenmesini istediğiniz diğer tüm sayfaları seçin veya dilimleyicinin tüm rapor sayfalarıyla eşitlenmesini sağlamak için **Tümüne ekle** seçeneğine tıklayın.  
3. Sonraki sütunda **Genel Bakış**’ı ve dilimleyicinin görünür durumda olmasını istediğiniz diğer tüm sayfaları seçin. 
4. **Genel Bakış** sayfasına geçip dilimleyiciye ve dilimleyicinin diğer sayfa görselleri üzerindeki etkilerine bakın. 
    - Farklı öğe seçimleri yapıp bu seçimleri kaldırın ve sayfadaki diğer görsellerin buna uygun şekilde nasıl değiştiğine dikkat edin. Herhangi bir sayfada yapılan öğe seçimi, eşitlenen tüm sayfalara yansır.
    - Genel Bakış sayfasında dilimleyicinin boyutunu, şeklini, konumunu ve/veya biçimlendirmesini değiştirin. Eşitlenen diğer sayfalardaki dilimleyici biçimlendirmesi değişmez. 

### <a name="control-which-page-visuals-are-affected-by-the-slicer"></a>Hangi sayfa görsellerinin dilimleyici tarafından etkileneceğini denetleme
Varsayılan olarak, rapor sayfasındaki bir dilimleyici söz konusu sayfada bulunan diğer tüm görselleştirmeleri etkiler. Bazı sayfa görselleştirmelerinin etkilenmesini önlemek için **Görsel etkileşimler**’i kullanın.

1. **Genel Bakış** sayfasında, dilimleyici seçiliyken:
    - Power BI Desktop’ta Görsel Araçlar bölümündeki Biçim menüsüne tıklayın ve **Etkileşimleri düzenle** seçeneğini belirleyin.
    - Power BI hizmetinde, menü çubuğundan **Görsel etkileşimler**’i açın ve **Etkileşimleri düzenle** seçeneğini açın. 
    
    Sayfadaki diğer tüm görsellerin üzerinde filtre denetimleri görünür. ![filtre denetimleri](media/power-bi-visualization-slicers/filter-controls.png)
    
2. Dilimleyicinin bir görseli filtrelemesini durdurmak için söz konusu görselin üzerindeki **Hiçbiri** simgesini seçin. Dilimleyicinin görseli tekrar filtrelemeye başlaması için **Filtre** simgesini seçin. 

Etkileşimleri düzenleme hakkında daha fazla bilgi için bkz. [Power BI raporlarındaki görsel etkileşimler](service-reports-visual-interactions.md).

## <a name="next-steps"></a>Sonraki adımlar
[Ücretsiz deneyin!](https://powerbi.com/)

Power BI'ı iyileştirmeye yönelik fikirleriniz mi var? [Fikir sunun](https://ideas.powerbi.com/forums/265200-power-bi-ideas).

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

[Bir rapora görselleştirme ekleme](power-bi-report-add-visualizations-i.md)

[Power BI'daki görselleştirme türleri](power-bi-visualization-types-for-reports-and-q-and-a.md)

[Power BI - Temel Kavramlar](service-basic-concepts.md)

