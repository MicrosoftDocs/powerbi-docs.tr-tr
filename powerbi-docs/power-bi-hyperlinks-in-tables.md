---
title: Tabloya köprü ekleme
description: Köprü oluşturmak için Power BI Desktop’ı kullanın. Daha sonra bu köprüleri rapor tablolarınıza ve matrislerinize eklemek için Desktop’ı veya Power BI hizmetini kullanabilirsiniz.
author: mihart
manager: kvivek
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 12/06/2018
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 92224e00da95714125a8e15c27432e8d305ae0f7
ms.sourcegitcommit: f25464d5cae46691130eb7b02c33f42404011357
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53180565"
---
# <a name="add-hyperlinks-to-a-table"></a>Tabloya köprü ekleme
Bu konu başlığı altında, Power BI Desktop'ın köprü oluşturmak için nasıl kullanılacağı açıklanmaktadır. Daha sonra bu köprüleri rapor tablolarınıza ve matrislerinize eklemek için Desktop’ı veya Power BI hizmetini kullanabilirsiniz. 

![Köprüler içeren tablo](media/power-bi-hyperlinks-in-tables/hyperlinkedtable.png)

> [!NOTE]
> [Panolardaki kutucuklar](service-dashboard-edit-tile.md) ve [panolardaki metin kutuları](service-dashboard-add-widget.md) içinde bulunan köprüler, çalışma sırasında Power BI hizmeti kullanılarak oluşturulabilir. [Raporlardaki metin kutuları](service-add-hyperlink-to-text-box.md) içinde bulunan köprüler, çalışma sırasında Power BI hizmeti ve Power BI Desktop kullanılarak oluşturulabilir.
> 
> 

## <a name="to-create-a-hyperlink-in-a-table-or-matrix-using-power-bi-desktop"></a>Power BI Desktop ile bir tablo veya matris içinde köprü oluşturmak için
Tablolardaki ve matrislerdeki köprüler Power BI Hizmeti ile değil, Power BI Desktop ile oluşturulabilir. Köprüler ayrıca, çalışma kitabı Power BI'a aktarılmadan önce Excel Power Pivot'ta da oluşturulabilir. Her iki yöntem de aşağıda açıklanmıştır.

## <a name="create-a-table-or-matrix-hyperlink-in-power-bi-desktop"></a>Power BI Desktop'ta bir tablo veya matris köprüsü oluşturma
Köprü ekleme yordamı, verileri içeri aktararak mı yoksa DirectQuery bağlantısı kullanarak mı aldığınıza göre değişir. Her iki senaryo da aşağıda açıklanmıştır.

### <a name="for-data-imported-into-power-bi"></a>Power BI'a aktarılan veriler için
1. Köprü, veri kümenizde bir alan olarak mevcut değilse Desktop'ı kullanın ve köprüyü bir [özel sütun](desktop-common-query-tasks.md) olarak ekleyin.
2. Veri görünümündeyken sütunu seçin ve **Modelleme** sekmesinde **Veri Kategorisi** açılan listesini açın.
   
    ![Veri kategorisi açılan listesi](media/power-bi-hyperlinks-in-tables/pbi_data_category.png)
3. **Web URL'si** seçeneğini belirleyin.
4. Rapor görünümüne geçin ve Web URL'si olarak kategorilendirilen alanı kullanarak bir tablo veya matris oluşturun. Köprüler mavi renkte ve altı çizili olarak görünür.

    ![Mavi ve altı çizili bağlantılar](media/power-bi-hyperlinks-in-tables/power-bi-table-with-hyperlinks2.png)

    > [!NOTE]
    > URL’ler **http:// , https://** veya **www** başlamalıdır.
    >
   
1. Tabloda uzun bir URL'nin görünmesini istemiyorsanız, bunun yerine köprü simgesini  ![Köprü simgesi](media/power-bi-hyperlinks-in-tables/power-bi-hyperlink-icon.png) gösterebilirsiniz. Matrislerde simge gösteremezsiniz.
   
   * Grafiği seçip etkin duruma getirin.
   * Boya rulosu simgesini ![Boya rulosu simgesi](media/power-bi-hyperlinks-in-tables/power-bi-paintroller.png) seçerek Biçimlendirme sekmesini açın.
   * **Değerler** bölümünü genişletin, **URL simgesini** bulun ve **Açık** olarak değiştirin.
6. (İsteğe bağlı) [Desktop'taki raporu Power BI hizmetinde yayımlayın](guided-learning/publishingandsharing.yml?tutorial-step=2) ve raporu Power BI hizmetinde açın. Köprüler burada da çalışır durumda olacaktır.

### <a name="for-data-connected-with-directquery"></a>DirectQuery ile bağlanılan veriler için
DirectQuery modunda yeni bir sütun oluşturamazsınız.  Ancak, verileriniz zaten URL içeriyorsa bunları köprülere dönüştürebilirsiniz.

1. Rapor görünümündeyken, URL içeren bir alan kullanarak tablo oluşturun.
2. Sütunu seçin ve **Modelleme** sekmesinde **Veri Kategorisi** açılan listesini açın.
3. **Web URL'si** seçeneğini belirleyin. Köprüler mavi renkte ve altı çizili olarak görünür.
4. (İsteğe bağlı) [Desktop'taki raporu Power BI hizmetinde yayımlayın](guided-learning/publishingandsharing.yml?tutorial-step=2) ve raporu Power BI hizmetinde açın. Köprüler burada da çalışır durumda olacaktır.

## <a name="create-a-table-or-matrix-hyperlink-in-excel-power-pivot"></a>Excel Power Pivot'ta bir tablo veya matris köprüsü oluşturma
Power BI tablolarınıza ve matrislerinize köprü eklemenin diğer bir yolu da ilgili veri kümesini Power BI'dan aktarmadan veya ilgili veri kümesine Power BI'dan bağlanmadan önce köprüleri bu veri kümesinde oluşturmaktır. Bu örnekte bir Excel çalışma kitabı kullanılmıştır.

1. Çalışma kitabını Excel'de açın.
2. **PowerPivot** sekmesini seçin ve ardından **Yönet** seçeneğini belirleyin.
   
   ![Excel’de PowerPivot’u açma](media/power-bi-hyperlinks-in-tables/createhyperlinkinpowerpivot2.png)
1. PowerPivot açıldığında **Gelişmiş** sekmesini seçin.
   
   ![PowerPivot Gelişmiş sekmesi](media/power-bi-hyperlinks-in-tables/createhyperlinkinpowerpivot3.png)
4. İmlecinizi, Power BI tablolarında köprüye dönüştürmek istediğiniz URL'leri içeren sütuna yerleştirin.
   
   > [!NOTE]
   > URL’ler **http:// , https://** veya **www** başlamalıdır.
   > 
5. **Raporlama Özellikleri** grubundaki **Veri Kategorisi** açılan listesinden **Web URL'si** seçeneğini belirleyin. 
   
   ![Excel’de veri kategorisi açılan listesi](media/power-bi-hyperlinks-in-tables/createhyperlinksnew.png)

6. Power BI hizmetinden veya Power BI Desktop'tan bu çalışma kitabına bağlanın veya çalışma kitabını içeri aktarın.
7. URL alanını içeren bir tablo görselleştirmesi oluşturun.
   
   ![URL alanı ile Power BI’da bir tablo oluşturma](media/power-bi-hyperlinks-in-tables/hyperlinksintables.gif)

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme
S: Bir tablo veya matriste köprü bağlantısını özel URL olarak kullanabilir miyim?    
C: Hayır. Bir bağlantı simgesi kullanabilirsiniz. Köprü bağlantılarınız için özel metin gerekirse ve URL listeniz kısaysa, bunun yerine bir metin kutusu kullanmayı düşünün.


## <a name="next-steps"></a>Sonraki adımlar
[Power BI raporlarındaki görselleştirmeler](visuals/power-bi-report-visualizations.md)

[Power BI - Temel Kavramlar](consumer/end-user-basic-concepts.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

