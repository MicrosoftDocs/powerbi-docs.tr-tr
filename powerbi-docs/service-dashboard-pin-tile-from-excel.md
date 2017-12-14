---
title: "Excel'deki kutucukları Power BI panolarına sabitleme"
description: "OneDrive İş'teki bir Excel dosyasında bulunan kutucukları Power BI panolarına sabitleyin. Aralıkları, grafikleri ve tabloları sabitleyin"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: l8JoB7w0zJA
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/26/2017
ms.author: mihart
ms.openlocfilehash: 855ecbe74fa4bf4ab1b1f81f22f2bab278adddb9
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2017
---
# <a name="pin-a-tile-to-a-power-bi-dashboard-from-excel"></a>Excel'deki kutucukları Power BI panolarına sabitleme
Excel çalışma kitabınızdaki bir kutucuğu sabitleyebilmeniz için çalışma kitabı ile Power BI hizmeti (app.powerbi.com) arasında bağlantı kurmanız gerekir. Çalışma kitabı ile hizmet arasında bağlantı kurulduğunda çalışma kitabının bağlantılı, salt okunur bir sürümü Power BI hizmetine aktarılır ve böylece aralıkları panolara sabitleyebilirsiniz. Panolara bir çalışma sayfasının tamamını bile sabitleyebilirsiniz.  
Sizinle bir çalışma kitabı paylaşılırsa, dosyanın sahibi tarafından sabitlenen kutucukları görüntüleyebilirsiniz ancak herhangi bir pano kutucuğu oluşturamazsınız. 

Excel ve Power BI'ın birlikte nasıl çalıştığı hakkında ayrıntılı bilgi için bkz. [Excel çalışma kitabı dosyalarından veri alma](http://go.microsoft.com/fwlink/?LinkID=521962).

Will bize Excel çalışma kitaplarındaki verileri içeri aktarmak ve bu verilere bağlanmak için kullanabileceğimiz birkaç yöntem gösterecek.

<iframe width="560" height="315" src="https://www.youtube.com/embed/l8JoB7w0zJA" frameborder="0" allowfullscreen></iframe>

## <a name="connect-your-excel-workbook-from-onedrive-for-business-to-power-bi"></a>OneDrive İş'teki Excel çalışma kitabınızı Power BI'a bağlama
**Bağlan**'ı seçtiğinizde çalışma kitabınız, Power BI'da tıpkı Excel Online'da göründüğü gibi görünecektir. Ancak, Excel Online'dan farklı olarak çalışma sayfalarınızdaki öğeleri doğrudan panolarınıza sabitlemenize yardımcı olacak harika özelliklere sahip olacaksınız.

Çalışma kitabınızı Power BI'da düzenleyemezsiniz. Ancak bazı değişiklikler yapmanız gerekirse çalışma alanınızın **Çalışma Kitapları** sekmesinden kalem simgesini seçip çalışma kitabınızı Excel Online'da düzenlemeyi veya bilgisayarınızdaki Excel programında açmayı seçebilirsiniz. Yaptığınız tüm değişiklikler OneDrive'daki çalışma kitabına kaydedilir.

1. Çalışma kitabınızı OneDrive İş hesabınıza yükleyin.
2. Power BI'dan [bu çalışma kitabına bağlanın](service-excel-workbook-files.md).
3. Power BI'da söz konusu çalışma kitabı çalışma alanınızın **Çalışma Kitapları** sekmesine eklenir.  ![](media/service-dashboard-pin-tile-from-excel/pbi_workbookicon.png) simgesi bunun bir Excel çalışma kitabı olduğunu, sarı yıldız işareti ise yeni olduğunu gösterir.
   
    Power BI'da çalışma kitabı üzerinde yaptığınız değişiklikler kaydedilmez ve OneDrive İş'teki özgün çalışma kitabı bu değişikliklerden etkilenmez. Power BI'da değerleri sıralar, filtreler veya değiştirirseniz söz konusu değişiklikler kaydedilemez ya da sabitlenemez. Çalışma kitabını güncelleştirmek için kalem simgesini seçin ve çalışma kitabını Excel Online'da açın. Excel Online'da çalışma kitabı üzerinde yapılan değişikliklerin kutucuklarda güncelleştirilmesi birkaç dakika sürebilir.     
   
   ![](media/service-dashboard-pin-tile-from-excel/power-bi-workbooks.png)
4. Adını seçerek çalışma kitabını Power BI'da açın.
   
   ![](media/service-dashboard-pin-tile-from-excel/power-bi-opened.png)

## <a name="pin-a-range-of-cells-to-a-dashboard"></a>Bir hücre aralığını panoya sabitleme
Yeni bir [pano kutucuğu](service-dashboard-tiles.md) eklemenin yollarından biri, bu işlemi Power BI'daki Excel çalışma kitabında gerçekleştirmektir. OneDrive İş hesabınıza veya grup tarafından paylaşılan başka bir belge kitaplığına kaydedilen Excel çalışma kitaplarından aralık sabitleyebilirsiniz. Bu aralıklar veri, grafik, tablo, PivotTable, PivotChart ve Excel'in diğer öğelerini içerebilir.

1. Bir panoya sabitlemek istediğiniz hücreleri vurgulayın.
   
    ![](media/service-dashboard-pin-tile-from-excel/pbi_selectrange.png)
2. Raptiye ![](media/service-dashboard-pin-tile-from-excel/pbi_pintile_small.png) simgesini seçin. 
3. Kutucuğu, var olan bir panoya veya yeni bir panoya sabitleyin. 
   
   * Var olan pano: Açılan listeden panonun adını seçin.
   * Yeni pano: Yeni panonun adını yazın.
   
   ![](media/service-dashboard-pin-tile-from-excel/pbi_dashdialog1.png)
4. **Sabitle**'yi seçin. Sağ üst köşeye yakın bir noktada çıkan Başarılı iletisi, aralığın bir kutucuk olarak panonuza eklendiğini bildirir. 
   
    ![](media/service-dashboard-pin-tile-from-excel/power-bi-go-to-dashboard.png)
5. **Panoya git**'i seçin. Burada, sabitlenmiş görselleştirmeyi [yeniden adlandırabilir, yeniden boyutlandırabilir, bağlantılı hale getirebilir ve taşıyabilirsiniz](service-dashboard-edit-tile.md). Varsayılan olarak, sabitlenen kutucuk seçildiğinde çalışma kitabı Power BI'da açılır.

## <a name="pin-an-entire-table-or-pivot-chart-to-a-dashboard"></a>Bir tablonun veya özet grafiğin tamamını panoya sabitleme
Yukarıdaki adımları uygulayın ancak bu kez, bir hücre aralığı seçmek yerine tablonun veya özet tablonun tamamını seçin.

Bir tabloyu sabitlemek için, tablonun tüm aralığını seçin ve başlıkları da eklediğinizden emin olun.  Bir özet tabloyu sabitlemek için özet tablonun görünür her bir parçasını (kullanıldıysa filtreler de dahil) seçtiğinizden emin olun.

 ![](media/service-dashboard-pin-tile-from-excel/pbi_selecttable.png)

Tablodan veya özet tablodan oluşturulan bir kutucuk tablonun tamamını gösterir.  Özgün çalışma kitabında satır veya sütun ekler, kaldırır veya filtrelerseniz söz konusu satır ve sütunlar kutucukta da eklenir, kaldırılır ya da filtrelenir.

## <a name="view-the-workbook-linked-to-the-tile"></a>Kutucukla bağlantılı çalışma kitabını görüntüleme
Bir çalışma kitabı kutucuğu seçildiğinde bağlantılı çalışma kitabı Power BI'da açılır. Çalışma kitabı dosyası, dosya sahibinin OneDrive İş hesabında bulunduğundan çalışma kitabını görüntüleyebilmeniz için Okuma izinlerinizin olması gerekir. İzne sahip değilseniz bir hata iletisiyle karşılaşırsınız.  

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme
Desteklenmeyen özellikler: Power BI, çalışma kitabı kutucuklarını almak için Excel Hizmetleri'ni kullanır. Bu nedenle, Excel'in bazı özellikleri Excel Hizmetleri REST API'sinde desteklenmediğinden söz konusu özellikler Power BI'daki kutucuklarda görülmez. Örneğin, mini grafikler, simge kümesi koşullu biçimlendirme özelliği ve zaman dilimleyicileri. Desteklenmeyen özelliklerin tam listesi için bkz. [Unsupported Features in Excel Services REST API (Excel Hizmetler REST API'sinde Desteklenmeyen Özellikler)](http://msdn.microsoft.com/library/office/ff394477.aspx)

## <a name="next-steps"></a>Sonraki adımlar
[Excel çalışma kitabıyla bağlantılı bir panoyu paylaşma](service-share-dashboard-that-links-to-excel-onedrive.md)

[Excel çalışma kitaplarından veri alma](service-excel-workbook-files.md)

[Power BI'daki panolar](service-dashboards.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

