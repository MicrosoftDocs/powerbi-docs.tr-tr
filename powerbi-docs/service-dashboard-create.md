---
title: "Rapordan Power BI panosu oluşturma"
description: "Rapordan Power BI panosu oluşturma"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
featuredvideoid: 
qualityfocus: 
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 05/09/2017
ms.author: mihart
ms.openlocfilehash: dac5628756898a20fe139447bc2d165ba804320c
ms.sourcegitcommit: 284b09d579d601e754a05fba2a4025723724f8eb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="create-a-power-bi-dashboard-from-a-report"></a>Rapordan Power BI panosu oluşturma
[Power BI'daki panolar](service-dashboards.md) başlıklı makaleyi okuduğunuza göre artık kendi panolarınızı oluşturabilirsiniz. Bir pano oluşturmanın birçok farklı yolu vardır. Bir rapordan, sıfırdan, bir veri kümesinden, mevcut bir pano yinelenerek veya başka yollarla oluşturulabilirler.  Bu konu başlığında ve videoda, mevcut bir rapordaki görselleştirmeleri sabitleyerek yeni bir pano oluşturma işlemi anlatılır.

> **NOT:** Panolar Power BI Desktop'ın değil, Power BI hizmetinin sunduğu bir özelliktir. Panoları Power BI mobil uygulamasında oluşturamaz ancak [görüntüleyip paylaşabilirsiniz](mobile-apps-view-dashboard.md).
> 
> 

![](media/service-dashboard-create/power-bi-completed-dashboard-small.png)

## <a name="video-create-a-dashboard-by-pinning-visuals-and-images-from-a-report"></a>Video: Bir rapordaki görselleri ve resimleri sabitleyerek pano oluşturma
Amanda'nın bir rapordaki görselleştirmeleri sabitleyerek yeni bir pano oluşturmasını izleyin. Ardından, Tedarik Analizi örneğini, videonun altında bulunan adımlar doğrultusunda kullanarak kendiniz deneyin.

<iframe width="560" height="315" src="https://www.youtube.com/embed/lJKgWnvl6bQ" frameborder="0" allowfullscreen></iframe>

## <a name="import-a-dataset-with-a-report"></a>Rapor içeren bir veri kümesini içeri aktarma
Power BI örnek veri kümelerinden birini içeri aktarıp yeni panomuzu oluşturmak için kullanacağız. Kullanacağımız örnek, iki PowerView sayfası bulunan bir Excel çalışma kitabıdır. Çalışma kitabın Power BI tarafından içeri aktarıldığında, çalışma alanınıza bir veri kümesi ve bir rapor eklenir.  Rapor otomatik olarak PowerView sayfalarından oluşturulur.

1. Tedarik Analizi örneği Excel dosyasını indirip kaydetmek için [bu bağlantıyı seçin](http://go.microsoft.com/fwlink/?LinkId=529784). Dosyayı OneDrive İş hesabınıza kaydetmenizi öneririz.
2. Tarayıcınızda Power BI hizmetine (app.powerbi.com) gidin ve oturum açın.
3. Mevcut bir çalışma alanını seçin veya yeni bir uygulama çalışma alanı oluşturun.
4. Sol gezinti bölmesinde, **Veri Al**'ı seçin.
   
    ![](media/service-dashboard-create/power-bi-get-data3.png)
5. **Dosyalar**'ı seçin.
   
   ![](media/service-dashboard-create/power-bi-select-files.png)
6. Tedarik Analizi örnek Excel dosyasını kaydettiğiniz konuma gidin. Dosyayı seçin ve **Bağlan** seçeneğini belirleyin.
   
   ![](media/service-dashboard-create/power-bi-connectnew.png)
7. Bu alıştırma için **İçeri aktar** seçeneğini belirleyin.
   
    ![](media/service-dashboard-create/power-bi-import.png)
8. Başarılı iletisi göründüğünde kapatmak için **x** işaretini seçin.
   
   ![](media/service-dashboard-create/power-bi-view-datasetnew.png)

### <a name="open-the-report-and-pin-some-tiles-to-a-dashboard"></a>Raporu açıp panoya bazı kutucuklar sabitleme
1. Aynı çalışma alanında, **Raporlar** sekmesini seçin. Yeni içeri aktarılan rapor sarı yıldız işaretiyle görüntülenir. Rapor adını seçerek raporu açın.
   
    ![](media/service-dashboard-create/power-bi-reports.png)
2. Rapor, [Okuma görünümü](service-interact-with-a-report-in-reading-view.md)'nde açılır. Raporun alt kısmındaki iki sekmeye dikkat edin: Discount Analysis ve Spend Overview. Her sekme raporun bir sayfasını temsil eder.
   
    ![](media/service-dashboard-create/power-bi-reading-view.png)
3. Kullanılabilir seçenekleri görüntülemek için bir görselleştirmenin üzerine gelin. Panoya bir görselleştirme eklemek için, raptiye ![](media/service-dashboard-create/power-bi-pin-icon.png) simgesini seçin.
   
    ![](media/service-dashboard-create/power-bi-hover.png)
4. Yeni bir pano oluşturduğumuzdan, **Yeni pano** seçeneğini belirleyin ve panoya bir ad verin. 
   
   ![](media/service-dashboard-create/power-bi-pin-tile.png)
5. **Sabitle**'yi seçtiğinizde, Power BI geçerli çalışma alanında yeni bir pano oluşturur. **Panoya sabitlendi** iletisi görüntülendiğinde, **Panoya git** seçeneğini belirleyin. Raporu kaydetmeniz istenirse **Kaydet**'i seçin.
   
     ![](media/service-dashboard-create/power-bi-pin-success.png)
6. Power BI yeni panoyu açar ve tek bir kutucuk (biraz önce sabitlediğimiz görselleştirme) görüntülenir. 
   
   ![](media/service-dashboard-create/power-bi-pinned.png)
7. Rapora dönmek için kutucuğu seçin. Yeni panoya birkaç kutucuk daha sabitleyin. **Panoya sabitle** penceresi görüntülendiğinde, bu kez **Var olan pano**'yu seçin.  
   
   ![](media/service-dashboard-create/power-bi-existing-dashboard.png)

Tebrikler, ilk panonuzu oluşturdunuz! Artık bir panonuz olduğuna göre, onunla birçok şey yapabilirsiniz.  Aşağıda önerilen **Sonraki adımlardan** birini deneyin veya kendi başınıza dilediğiniz gibi keşif yapın.   

## <a name="next-steps"></a>Sonraki adımlar
* [Kutucukları yeniden boyutlandırma ve taşıma](service-dashboard-edit-tile.md)
* [Pano kutucukları hakkında tüm bilmeniz gerekenler](service-dashboard-tiles.md)
* [Uygulama oluşturarak panonuzu paylaşma](service-create-distribute-apps.md)
* [Power BI - Temel Kavramlar](service-basic-concepts.md)
* [Power BI'daki panolar](service-dashboards.md)
* [Harika bir pano oluşturmaya yönelik ipuçları](service-dashboards-design-tips.md)

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

