---
title: Tabloya köprü (URL) ekleme
description: Bu konu başlığı altında bir tabloya köprü (URL) ekleme hakkında bilgi alacaksınız. Bir tabloya veya matrise köprü (URL) eklemek için Power BI Desktop kullanırsınız. Daha sonra, Power BI Desktop veya Power BI hizmetinde bu köprüleri rapor tablolarınıza ve matrislerinize ekleyebilirsiniz.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 08/30/2019
ms.author: maggies
LocalizationGroup: Visualizations
ms.openlocfilehash: b158e968d0fd35859cfd293177a7273e8311d5b2
ms.sourcegitcommit: d04b9e1426b8544ce16ef25864269cc43c2d9f7b
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71715308"
---
# <a name="add-hyperlinks-urls-to-a-table"></a>Tabloya köprü (URL) ekleme
Bu konu başlığı altında bir tabloya köprü (URL) ekleme hakkında bilgi alacaksınız. Bir tabloya veya matrise köprü (URL) eklemek için Power BI Desktop kullanırsınız. Daha sonra, Power BI Desktop veya Power BI hizmetinde bu köprüleri rapor tablolarınıza ve matrislerinize ekleyebilirsiniz. 

![Köprüler içeren tablo](media/power-bi-hyperlinks-in-tables/hyperlinkedtable.png)

> [!NOTE]
> Power BI hizmetinde, [panolardaki kutucuklarda](service-dashboard-edit-tile.md) ve [panolardaki metin kutularında](service-dashboard-add-widget.md) çalışma sırasında köprüler oluşturulabilirsiniz. Power BI hizmeti ve Power BI Desktop kullanarak, [raporlardaki metin kutularında](service-add-hyperlink-to-text-box.md) çalışma sırasında köprüler oluşturabilirsiniz.
> 

## <a name="to-create-a-hyperlink-in-a-table-or-matrix-using-power-bi-desktop"></a>Power BI Desktop ile bir tablo veya matris içinde köprü oluşturmak için
Power BI Desktop'ta tablolarda ve matrislerde köprüler oluşturabilirsiniz ancak Power BI hizmetinde oluşturamazsınız. Ayrıca, çalışma kitabını Power BI'ya aktarmadan önce Excel PowerPivot'ta da köprüler oluşturabilirsiniz. Her iki yöntem de aşağıda açıklanmıştır.

## <a name="create-a-table-or-matrix-hyperlink-in-power-bi-desktop"></a>Power BI Desktop'ta bir tablo veya matris köprüsü oluşturma
Köprü ekleme yordamı, verileri içeri aktararak mı yoksa DirectQuery bağlantısı kullanarak mı aldığınıza göre değişir. Her iki senaryo da aşağıda açıklanmıştır.

### <a name="for-data-imported-into-power-bi"></a>Power BI'a aktarılan veriler için
1. Köprü, veri kümenizde bir alan olarak mevcut değilse Power BI Desktop'ı kullanın ve köprüyü bir [özel sütun](desktop-common-query-tasks.md) olarak ekleyin.
2. Veri görünümündeyken sütunu seçin ve **Modelleme** sekmesinde **Veri Kategorisi** açılan listesini açın.
   
    ![Veri kategorisi açılan listesi](media/power-bi-hyperlinks-in-tables/pbi_data_category.png)
3. **Web URL'si** seçeneğini belirleyin.
4. Rapor görünümüne geçin ve Web URL'si olarak kategorilendirilen alanı kullanarak bir tablo veya matris oluşturun. Köprüler mavi renkte ve altı çizili olarak görünür.

    ![Mavi ve altı çizili bağlantılar](media/power-bi-hyperlinks-in-tables/power-bi-table-with-hyperlinks2.png)

    > [!NOTE]
    > URL’ler **http:// , https://** veya **www** başlamalıdır.
    >
   
1. Tabloda uzun bir URL'nin görünmesini istemiyorsanız, bunun yerine köprü simgesini  ![Köprü simgesi](media/power-bi-hyperlinks-in-tables/power-bi-hyperlink-icon.png) gösterebilirsiniz. Matrislerde simge gösteremezsiniz.
   
    Grafiği seçip etkin duruma getirin.

    Biçim simgesini seçin ![Boya rulosu simgesi](media/power-bi-hyperlinks-in-tables/power-bi-paintroller.png) seçerek Biçimlendirme sekmesini açın.

    **Değerler** bölümünü genişletin, **URL simgesini** bulun ve **Açık** olarak değiştirin.

    ![URL simgesini açma](media/power-bi-hyperlinks-in-tables/power-bi-url-icon-on.png)

1. (İsteğe bağlı) [Power BI Desktop'taki raporu Power BI hizmetinde yayımlayın](/learn/modules/publish-share-power-bi/2-publish-reports) ve raporu Power BI hizmetinde açın. Köprüler burada da çalışır durumda olacaktır.

### <a name="for-data-connected-with-directquery"></a>DirectQuery ile bağlanılan veriler için
DirectQuery modunda yeni bir sütun oluşturamazsınız.  Ancak, verileriniz zaten URL içeriyorsa bunları köprülere dönüştürebilirsiniz.

1. Rapor görünümündeyken, URL içeren bir alan kullanarak tablo oluşturun.
2. Sütunu seçin ve **Modelleme** sekmesinde **Veri Kategorisi** açılan listesini açın.
3. **Web URL'si** seçeneğini belirleyin. Köprüler mavi renkte ve altı çizili olarak görünür.
4. (İsteğe bağlı) [Power BI Desktop'taki raporu Power BI hizmetinde yayımlayın](/learn/modules/publish-share-power-bi/2-publish-reports) ve raporu Power BI hizmetinde açın. Köprüler burada da çalışır durumda olacaktır.

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

[Power BI hizmetinde tasarımcılar için temel kavramlar](service-basic-concepts.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

