---
title: Pano kutucuğunu düzenleme
description: Bu eğitimde kutucuk oluşturup panoya sabitlemenin yanı sıra pano kutucuğunu nasıl düzenleyeceğinizi (yeniden boyutlandırma, taşıma, yeniden adlandırma, sabitleme, silme ve köprü ekleme) öğreneceksiniz.
author: maggiesMSFT
ms.author: maggies
ms.reviewer: ''
featuredvideoid: lJKgWnvl6bQ
ms.service: powerbi
ms.subservice: pbi-reports-dashboards
ms.topic: how-to
ms.date: 03/02/2018
LocalizationGroup: Dashboards
ms.openlocfilehash: 4e217b0e75e8d2fadd2eff927ba3ef3c04e40e27
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96417440"
---
# <a name="edit-or-remove-a-dashboard-tile"></a>Pano kutucuklarını düzenleme veya kaldırma

## <a name="dashboard-owners-versus-dashboard-consumers"></a>Pano *sahipleri* ve pano *kullanıcıları*
Bir pano oluşturduğunuzda veya panonun sahibi olduğunuzda panodaki kutucukların görünümünü ve varsayılan davranışını değiştirmeye ilişkin birçok seçeneğe sahip olursunuz. İş arkadaşlarınız için pano *kullanma* deneyimini tasarlamak üzere aşağıdaki ayarları ve stratejileri kullanın.  Kutucuk seçildiğinde bağlantılı rapor mu, özel bir URL mi yoksa farklı bir pano mu açılacak? [Video veya veri akışı görüntüleyen bir kutucuk eklemek](service-dashboard-add-widget.md) ister misiniz? [Etkileşimli dilimleyicilere sahip bir kutucuk](service-dashboard-pin-live-tile-from-report.md) bile oluşturabilirsiniz. *Oluşturucu* olarak birçok seçeneği kullanabilirsiniz. 

<iframe width="560" height="315" src="https://www.youtube.com/embed/lJKgWnvl6bQ" frameborder="0" allowfullscreen></iframe>

Bu makalede aşağıdaki noktalar ele alınmaktadır.

* [Görselleştirme oluşturma ve bu görselleştirmeyi bir panoya sabitleme](#create)
* [Kutucukları taşıma](#move)
* [Kutucukları yeniden boyutlandırma](#resize)
* [Kutucukları yeniden adlandırma](#rename)
* [Kutucuklara köprü ekleme](#hyperlink)
* [Kutucukları farklı bir panoya sabitleme](#different)
* [Kutucukları silme](#delete)
  
  > [!TIP]
  > Kutucuğun üzerinde gösterilen görselleştirmeyi değiştirmek için kutucuğu silip yeni bir [pano kutucuğu](../consumer/end-user-tiles.md) ekleyin.

  
## <a name="prerequisites"></a>Önkoşullar
Birlikte ilerlemek için Power BI hizmetini (Power BI Desktop'ı değil) açın ve [BT Harcama Analizi örneğini indirin](sample-it-spend.md). "Başarılı" iletisi göründüğünde **Panoya git**'i seçin.

- - -
<a name="create"></a>

## <a name="create-a-new-visualization-and-pin-it-to-the-dashboard"></a>Yeni bir görselleştirme oluşturma ve bu görselleştirmeyi panoya sabitleme
1. IT Spend Analysis Sample panosunda "Amount" kutucuğunu seçerek ilgili raporu açın.

    ![Tutar kutucuğu](media/service-dashboard-edit-tile/power-bi-amount-tile.png)

2. Üstteki menü çubuğundan **Raporu düzenle**'yi seçerek raporu Düzenleme görünümü'nde açın.

3. Raporun alt kısmında bulunan artı işaretini (+) seçerek yeni bir rapor sayfası ekleyin.

    ![artı simgesi](media/service-dashboard-edit-tile/power-bi-add-page.png)

4. ALANLAR bölmesinde **Fact > Amount** ve **Business Area > Business Area** seçeneklerini belirleyin.
 
5. Görselleştirmeyi bir Halka grafiğe dönüştürmek için GÖRSEL ÖĞELER bölmesinde Halka grafik simgesini seçin.

    ![Görselleştirmeler bölmesi](media/service-dashboard-edit-tile/power-bi-donut-chart.png)

5. Raptiye simgesini seçin ve Halka grafiği, IT Spend Analysis Sample panosuna sabitleyin.

   ![kutucuğun üzerine gelme](media/service-dashboard-edit-tile/power-bi-pin.png)

6. "Başarılı" iletisi göründüğünde **Panoya git**'i seçin. Değişikliklerinizi kaydetmeniz istenecek. **Kaydet**’i seçin.

- - -
<a name="move"></a>

## <a name="move-the-tile"></a>Kutucuğu taşıma
Panoda yeni kutucuğu bulun. Pano tuvali üzerindeki farklı bir konuma taşımak için kutucuğu seçin ve basılı tutarak sürükleyin.

- - -
<a name="resize"></a>

## <a name="resize-the-tile"></a>Kutucuğu yeniden boyutlandırma
Kutucuklar için 1x1'den 5x5'e kadar birçok farklı boyut belirleyebilirsiniz. Kutucuğu yeniden boyutlandırmak için tutamacı (sağ alt köşedeki) seçin ve sürükleyin.

![video](media/service-dashboard-edit-tile/pbigif_resizetile4.gif)

- - -
## <a name="more-options--menu"></a>**Diğer seçenekler** (...) menüsü

1. Kutucuğun sağ üst köşesindeki **Diğer seçenekler**’i (...) seçin. 
   
   ![kutucuk üç noktası](media/service-dashboard-edit-tile/power-bi-tile.png)

2. "Account" kutucuğunun üzerine gelin ve seçenekleri görüntülemek için üç nokta simgesini seçin. Kullanabileceğiniz seçenekler kutucuk türüne göre değişir.  Örneğin, canlı bir kutucuk için kullanabileceğiniz seçenekler standart bir görselleştirme kutucuğu için kullanabileceğiniz seçeneklerden farklıdır. Ayrıca, sizinle paylaşılan (sahibi olmadığınız) bir pano üzerinde çalışıyorsanız daha az seçeneğiniz olur.

   ![üç nokta seçenekler menüsü](media/service-dashboard-edit-tile/power-bi-tile-menu-new.png)

3. "Kutucuk ayrıntıları" penceresini açmak için **Ayrıntıları düzenle** seçeneğini belirleyin. 

    Kutucuğun başlığını ve varsayılan davranışını değiştirin.  Örneğin, *kullanıcı* bir kutucuğu seçtiğinde ilgili kutucuğun oluşturulması için kullanılan raporun açılması yerine yeni bir panonun görüntülenmesini sağlayabilirsiniz.  
   


<a name="rename"></a>

### <a name="rename-the-tile"></a>Kutucuğu yeniden adlandırma
"Kutucuk ayrıntıları" penceresinin üst kısmındaki **Başlık** değerini **Amount spent** olarak değiştirin.

![Kutucuk ayrıntıları penceresi](media/service-dashboard-edit-tile/power-bi-tile-title.png)


<a name="hyperlink"></a>

### <a name="change-the-default-hyperlink"></a>Varsayılan köprüyü değiştirme
Varsayılan olarak, bir kutucuğu seçtiğinizde genellikle kutucuğun oluşturulduğu rapor veya Soru-Cevap (kutucuk Soru-Cevap bölümünde oluşturulduysa) açılır. Kutucuğu bir web sayfası, başka bir pano veya rapor (aynı çalışma alanındaki), SSRS raporu ya da farklı bir çevrimiçi içerik ile bağlantılı hale getirmek için özel bir bağlantı ekleyin.

1. İşlev başlığının altında bulunan **Özel bağlantı ayarlayın** seçeneğini belirleyin.

2. **Geçerli çalışma alanındaki bir pano veya rapora bağlantı**'yı seçin ve açılan listeden seçiminizi yapın.  Bu örnekte biz Human Resources Sample panosunu seçtik. Çalışma alanınızda bu örnek yoksa örneği ekleyip bu adımdan devam edebilir veya farklı bir pano seçebilirsiniz. 

    ![İşlev iletişim kutusu](media/service-dashboard-edit-tile/power-bi-custom-link.png)

3. **Uygula**’yı seçin.

4. Kutucukta yeni başlık görüntülenir.  Kutucuğu seçtiğinizde Power BI, Human Resources Sample panosunu açar. 

    ![kutucuk başlığı](media/service-dashboard-edit-tile/power-bi-title.png)

<a name="different"></a>

### <a name="pin-the-tile-to-a-different-dashboard"></a>Kutucuğu farklı bir panoya sabitleme
1. Üç nokta açılan menüsünde **Kutucuğu sabitle** ![raptiye simgesi](media/service-dashboard-edit-tile/pinnooutline.png) seçeneğini belirleyin.
2. Bu kutucuğun bir kopyasını mevcut bir panoya mı yoksa yeni bir panoya mı sabitlemek istediğinize karar verin. 
   
   ![Panoya sabitle iletişim kutusu](media/service-dashboard-edit-tile/pbi_pintoanotherdash.png)
3. **Raptiye** düğmesini seçin.

<a name="delete"></a>

### <a name="delete-the-tile"></a>Kutucuğu silme
1. Bir kutucuğu panodan kalıcı olarak kaldırmak için üç nokta açılan menüsünden **Kutucuğu sil** ![silme simgesi](media/service-dashboard-edit-tile/power-bi-delete-tile-icon.png) seçeneğini belirleyin. 

2. Kutucuğu sildiğinizde bağlantılı görselleştirme silinmez. "Amount" kutucuğunu seçerek bağlantılı raporu açın. Özgün görselleştirmenin rapordan silinmediğini görmek için raporunuzdaki son sayfayı açın. 

- - -
## <a name="next-steps"></a>Sonraki adımlar
[Power BI'daki pano kutucukları](../consumer/end-user-tiles.md)

[Power BI'daki panolar](../consumer/end-user-dashboards.md)

[Power BI hizmetinde tasarımcılar için temel kavramlar](../fundamentals/service-basic-concepts.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)
