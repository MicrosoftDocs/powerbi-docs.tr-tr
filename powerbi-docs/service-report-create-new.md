---
title: "Bir veri kümesinden yeni bir rapor oluşturma "
description: "Bir veri kümesinden yeni bir Power BI raporu oluşturun."
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: monitoring
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 10/28/2017
ms.author: mihart
ms.openlocfilehash: f4afb1eaa1b3012fdbdb0eff35e9eff695cc32e4
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2017
---
# <a name="create-a-new-power-bi-report-by-importing-a-dataset"></a>Veri kümesi içeri aktararak yeni bir Power BI raporu oluşturma
[Power BI'daki raporlar](service-reports.md) başlıklı makaleyi okudunuz ve artık kendi raporlarınızı oluşturmak isteyebilirsiniz. Rapor oluşturmanın birçok farklı yolu vardır. Biz bu makalede bir Excel veri kümesinden çok basit bir rapor oluşturarak başlayacağız. Rapor oluşturma işlemiyle ilgili temel bilgileri kavradığınızda, sayfanın en altında bulunan **Sonraki adımlar** bölümündeki bağlantıları kullanarak raporlarla ilgili daha ileri düzey konulara göz atabilirsiniz.  

> **İPUCU**: Mevcut bir raporu kopyalayarak rapor oluşturmak için bkz. [Bir raporu kopyalama](power-bi-report-copy.md)
> 
> 

## <a name="import-the-dataset"></a>Veri kümesini içeri aktarma
Bu rapor oluşturma yöntemi için bir veri kümesi ve boş bir tuval ile başlayacağız. Birlikte ilerleyebilmemiz için [Retail Analysis Sample adlı Excel veri kümesini indirin](http://go.microsoft.com/fwlink/?LinkId=529778) ve bunu OneDrive İş'e (önerilir) veya yerel bir konuma kaydedin.

1. Raporu bir Power BI hizmeti çalışma alanında oluşturacağımızdan mevcut bir çalışma alanını seçin veya yenisini oluşturun.
   
   ![](media/service-report-create-new/power-bi-workspaces2.png)
2. Sol gezinti bölmesinin alt tarafında yer alan **Veri Al** seçeneğini belirleyin.
   
   ![](media/service-report-create-new/power-bi-get-data3.png)
3. **Dosyalar**'ı seçin ve Retail Analysis Sample dosyasını kaydettiğiniz konuma gidin.
   
    ![](media/service-report-create-new/power-bi-select-files.png)
4. Bu alıştırma için **İçeri aktar** seçeneğini belirleyin.
   
   ![](media/service-report-create-new/power-bi-import.png)
5. Veri kümesi içeri aktarıldıktan sonra **Veri kümesini görüntüle**'yi seçin.
   
   ![](media/service-report-create-new/power-bi-view-dataset.png)
6. Veri kümesi görüntülendiğinde rapor düzenleyicisi açılır.  Boş bir tuval ve rapor düzenleme araçları görürsünüz.
   
   ![](media/service-report-create-new/power-bi-blank-report.png)

> **İPUCU**: Rapor düzenleme tuvalini daha önce hiç kullanmadıysanız veya bilgilerinizi tazelemeniz gerekiyorsa devam etmeden önce [Rapor düzenleyicisi ile ilgili bir tura katılın](service-the-report-editor-take-a-tour.md).
> 
> 

## <a name="add-a-radial-gauge-to-the-report"></a>Rapora Radyal Ölçer ekleme
Veri kümemiz içeri aktarıldığına göre bazı soruları yanıtlamaya başlayalım.  Pazarlama Müdürümüz (CMO) bu yılki satış hedeflerimize ne kadar yaklaştığımızı öğrenmek istiyor. Bu tür bilgilerin görüntülenmesi için Ölçer, [iyi bir görselleştirme seçimi](power-bi-report-visualizations.md) olacaktır.

1. Alanlar bölmesinde **Sales** > **This Year Sales** > **Değer** seçeneğini belirleyin.
   
    ![](media/service-report-create-new/power-bi-report-step1.png)
2. **Görsel Öğeler** bölmesinden Ölçer şablonunu ![](media/service-report-create-new/powerbi-gauge-icon.png) seçerek görseli bir Ölçere dönüştürün.
   
    ![](media/service-report-create-new/power-bi-report-step2.png)
3. **Sales** > **This Year Sales** > **Hedef** alanını **Hedef değer** kutusuna sürükleyin. Hedefimize çok yakın olduğumuzu görüyoruz.
   
    ![](media/service-report-create-new/power-bi-report-step3.png)
4. Şimdi [raporunuzu kaydedebilirsiniz](service-report-save.md).
   
   ![](media/service-report-create-new/powerbi-save.png)

## <a name="add-an-area-chart-and-slicer-to-the-report"></a>Rapora alan grafiği ve dilimleyici ekleme
Pazarlama müdürümüzün birkaç sorusuna daha yanıt bulmamız gerekiyor. Pazarlama müdürümüz, bu yıla ait satış verileriyle bir önceki yıla ait verileri karşılaştırmamızı istiyor. Ayrıca, sonuçları bölge temelinde görmek istiyor.

1. Öncelikle tuvalde biraz yer açalım. Ölçer görselleştirmesini seçin ve sağ üst köşeye taşıyın. Ardından, köşelerden birini tutup sürükleyerek görseli küçültün.
2. Ölçerin seçimini kaldırın. Alanlar bölmesinde **Sales** > **This Year Sales** > **Değer** ve ardından **Sales** > **Last Year Sales** seçeneğini belirleyin.
   
    ![](media/service-report-create-new/power-bi-report-step4.png)
3. **Görsel Öğeler** bölmesinden Alan grafiği şablonunu ![](media/service-report-create-new/power-bi-areachart-icon.png) seçerek görseli bir Alan grafiğine dönüştürün.
4. **Eksen** kutusuna eklemek üzere **Time** > **Period** seçeneğini belirleyin.
   
    ![](media/service-report-create-new/power-bi-report-step5.png)
5. Görselleştirmeyi sıralamak için üç nokta menüsünü seçin ve **Sıralama Ölçütü: Period** seçeneğini belirleyin.
6. Şimdi de dilimleyiciyi ekleyelim. Tuvalde boş bir alanı ve ardından Dilimleyici ![](media/service-report-create-new/power-bi-slicer-icon.png) şablonunu seçin. Bu işlemin ardından, tuvalimize boş bir dilimleyici eklenir.
   
    ![](media/service-report-create-new/power-bi-report-step6.png)    
7. Alanlar bölmesinde **District** > **District** seçeneğini belirleyin. Dilimleyiciyi taşıyın ve yeniden boyutlandırın.
   
    ![](media/service-report-create-new/power-bi-report-step7.png)  
8. Bölgeye göre belirli desenler ve öngörüler bulmak için dilimleyiciyi kullanın.
   
   ![](media/service-report-create-new/power-bi-slicer-video2.gif)  
9. İsteğe bağlı olarak, görselleştirme eklemeye devam edebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar
* [Bir raporun kopyasını oluşturma](power-bi-report-copy.md)
* [Raporu kaydetme](service-report-save.md)    
* [Rapora yeni bir sayfa ekleme](power-bi-report-add-page.md)  
* [Görselleştirmeleri bir panoya sabitlemeyi](service-dashboard-pin-tile-from-report.md) öğrenin    
* Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

