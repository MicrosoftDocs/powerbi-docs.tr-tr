---
title: Bir veri kümesinden rapor oluşturma
description: Bir veri kümesinden bir Power BI raporu oluşturun.
author: maggiesMSFT
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 04/25/2019
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: 6b69c2b1fa811d395a26403de852c44af33491c7
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "64770238"
---
# <a name="create-a-report-in-the-power-bi-service-by-importing-a-dataset"></a>Bir veri kümesini içeri aktararak Power BI hizmetinde bir rapor oluşturma
[Power BI'daki raporlar](consumer/end-user-reports.md) başlıklı makaleyi okudunuz ve artık kendi raporlarınızı oluşturmak isteyebilirsiniz. Bir rapor oluşturmak için farklı yöntemler vardır. Bu makalede, bir Excel veri kümesinden alınan Power BI hizmetinde temel bir rapor oluşturarak başlayacağız. Rapor oluşturma temel kavramları anladığınızda, kullanıma [sonraki adımlar](#next-steps) daha uçtaki gelişmiş konulara göz atabilirsiniz.  

## <a name="prerequisites"></a>Önkoşullar
- [Power BI hizmetine kaydolma](service-self-service-signup-for-power-bi.md). Power BI Desktop kullanarak raporları oluşturmak için bkz: [Masaüstü rapor görünümü](desktop-report-view.md). 
- [Perakende analizi örnek Excel veri kümesini indirin](http://go.microsoft.com/fwlink/?LinkId=529778) ve OneDrive iş için veya yerel olarak kaydedin.

## <a name="import-the-dataset"></a>Veri kümesini içeri aktarma
Bu rapor oluşturma yöntemi için bir veri kümesi ve boş bir tuval ile başlayacağız. Perakende analizi örnek Excel veri kümesini izleyebilirsiniz.

1. Biz bir Power BI hizmeti çalışma alanında rapor oluşturabilir, böylece mevcut bir çalışma alanını seçin veya bir tane oluşturun.
   
   ![Uygulama çalışma alanlarının listesi](media/service-report-create-new/power-bi-workspaces2.png)
2. Sol gezinti bölmesinin altından seçin **veri alma**.
   
   ![Veri al](media/service-report-create-new/power-bi-get-data3.png)
3. **Dosyalar**'ı seçin ve Retail Analysis Sample dosyasını kaydettiğiniz konuma gidin.
   
    ![Dosyalar’ı seçme](media/service-report-create-new/power-bi-select-files.png)
4. Bu alıştırma için **İçeri aktar** seçeneğini belirleyin.
   
   ![İçeri aktar seçeneğini belirleme](media/service-report-create-new/power-bi-import.png)
5. Veri kümesi içeri aktarıldıktan sonra **Veri kümesini görüntüle**'yi seçin.
   
   ![Veri kümesini görüntüle’yi seçme](media/service-report-create-new/power-bi-view-dataset.png)
6. Veri kümesi görüntülendiğinde rapor düzenleyicisi açılır.  Boş bir tuval ve rapor düzenleme araçları görürsünüz.
   
   ![rapor düzenleyicisi](media/service-report-create-new/power-bi-blank-report.png)

> [!TIP]
> Rapor düzenleme tuvalini bilginiz veya bilgilerinizi tazelemeniz [rapor Düzenleyicisi turuna](service-the-report-editor-take-a-tour.md) devam etmeden önce. > 
> 

## <a name="add-a-radial-gauge-to-the-report"></a>Rapora Radyal Ölçer ekleme
Veri kümemiz içeri aktarıldığına göre bazı soruları yanıtlamaya başlayalım.  Pazarlama Müdürümüz (CMO) bu yılki satış hedeflerimize ne kadar yaklaştığımızı öğrenmek istiyor. Bu tür bilgilerin görüntülenmesi için Ölçer, [iyi bir görselleştirme seçimi](visuals/power-bi-report-visualizations.md) olacaktır.

1. Alanlar bölmesinde **Sales** > **This Year Sales** > **Değer** seçeneğini belirleyin.
   
    ![rapor düzenleyicisindeki çubuk grafik](media/service-report-create-new/power-bi-report-step1.png)
2. **Görselleştirmeler** bölmesinden Ölçer şablonunu ![Ölçer simge](media/service-report-create-new/powerbi-gauge-icon.png) seçerek görseli bir Ölçere dönüştürün.
   
    ![rapor düzenleyicisinde ölçer görseli](media/service-report-create-new/power-bi-report-step2.png)
3. **Sales** > **This Year Sales** > **Hedef** alanını **Hedef değer** kutusuna sürükleyin. Hedefimize çok yakın olduğumuzu görüyoruz.
   
    ![Hedef değer olarak Hedefin bulunduğu ölçer görseli](media/service-report-create-new/power-bi-report-step3.png)
4. Raporunuzu kaydetmek için iyi bir zaman artık olacaktır.
   
   ![Dosya menüsü](media/service-report-create-new/powerbi-save.png)

## <a name="add-an-area-chart-and-slicer-to-the-report"></a>Rapora alan grafiği ve dilimleyici ekleme
Pazarlama müdürümüzün birkaç sorusuna daha yanıt bulmamız gerekiyor. Pazarlama müdürümüz, bu yıla ait satış verileriyle bir önceki yıla ait verileri karşılaştırmamızı istiyor. Ayrıca, sonuçları bölge temelinde görmek istiyor.

1. Öncelikle tuvalde biraz yer açalım. Ölçer görselleştirmesini seçin ve sağ üst köşeye taşıyın. Ardından, köşelerden birini tutup sürükleyerek görseli küçültün.
2. Ölçerin seçimini kaldırın. Alanlar bölmesinde **Sales** > **This Year Sales** > **Değer** ve ardından **Sales** > **Last Year Sales** seçeneğini belirleyin.
   
    ![Ölçerin ve çubuk grafiğin bulunduğu rapor düzenleyicisi](media/service-report-create-new/power-bi-report-step4.png)
3. **Görselleştirmeler** bölmesinden Alan grafiği şablonunu ![grafik simgesi](media/service-report-create-new/power-bi-areachart-icon.png) seçerek görseli bir Alan grafiğine dönüştürün.
4. **Eksen** kutusuna eklemek üzere **Time** > **Period** seçeneğini belirleyin.
   
    ![Alan grafiğinin etkin olduğu rapor düzenleyicisi](media/service-report-create-new/power-bi-report-step5.png)
5. Görselleştirmeyi zaman aralığına göre sıralamak için üç noktayı seçin ve **Döneme Göre Sırala** seçeneğini belirleyin.
6. Şimdi de dilimleyiciyi ekleyelim. Tuvalde boş bir alanı ve sonra Dilimleyici ![Dilimleyici simgesi](media/service-report-create-new/power-bi-slicer-icon.png) şablonunu seçin. Şimdi boş bir Dilimleyici değiştirirsek tuvalimizde sahibiz.
   
    ![rapor tuvali](media/service-report-create-new/power-bi-report-step6.png)    
7. Alanlar bölmesinde **District** > **District** seçeneğini belirleyin. Dilimleyiciyi taşıyın ve yeniden boyutlandırın.
   
    ![Rapor düzenleyicisi, Bölge ekleme](media/service-report-create-new/power-bi-report-step7.png)  
8. Bölgeye göre belirli desenler ve öngörüler bulmak için dilimleyiciyi kullanın.
   
   ![dilimleyici kullanımının videosu](media/service-report-create-new/power-bi-slicer-video2.gif)  

Verilerinizi keşfetmeye ve görsel öğeleri eklemeye devam edin. Özellikle ilgi çekici bilgiler bulduğunuzda [panoya sabitleyin](service-dashboard-pin-tile-from-report.md).

## <a name="next-steps"></a>Sonraki adımlar

* [Görselleştirmeleri bir panoya sabitlemeyi](service-dashboard-pin-tile-from-report.md) öğrenin   
* Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

