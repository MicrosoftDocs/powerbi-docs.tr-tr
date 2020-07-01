---
title: Bir veri kümesinden rapor oluşturma
description: Bir veri kümesinden Power BI raporu oluşturun.
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
ms.date: 04/25/2019
ms.author: maggies
LocalizationGroup: Reports
ms.openlocfilehash: 74a0238d39d778641d1906271fd478463ee4a95a
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85218965"
---
# <a name="create-a-report-in-the-power-bi-service-by-importing-a-dataset"></a>Veri kümesini içeri aktararak Power BI hizmetinde rapor oluşturma
[Power BI'daki raporlar](../consumer/end-user-reports.md) başlıklı makaleyi okudunuz ve artık kendi raporlarınızı oluşturmak isteyebilirsiniz. Rapor oluşturmanın farklı yolları vardır. Bu makalede, Power BI hizmetinde bir Excel veri kümesinden temel bir rapor oluşturarak başlayacağız. Rapor oluşturmanın temeli anladıktan sonra, raporlara yönelik daha gelişmiş konu başlıkları için [sonraki adımlara](#next-steps) göz atın.  

## <a name="prerequisites"></a>Önkoşullar
- [Power BI hizmetine kaydolma](../fundamentals/service-self-service-signup-for-power-bi.md). Power BI Desktop kullanarak raporları oluşturmak için bkz. [Masaüstü rapor görünümü](desktop-report-view.md). 
- [Retail Analysis Sample adlı Excel veri kümesini indirin](https://go.microsoft.com/fwlink/?LinkId=529778) ve bunu OneDrive İş'e veya yerel bir konuma kaydedin.

## <a name="import-the-dataset"></a>Veri kümesini içeri aktarma
Bu rapor oluşturma yöntemi için bir veri kümesi ve boş bir tuval ile başlayacağız. Artık Perakende Analizi Örneği Excel veri kümesine siz de dahil olabilirsiniz.

1. Raporu bir Power BI hizmeti çalışma alanında oluşturacağımızdan mevcut bir çalışma alanını seçin veya bir tane oluşturun.
   
   ![çalışma alanlarının listesi](media/service-report-create-new/power-bi-workspaces2.png)
2. Gezinti bölmesinin alt kısmından **Veri al**'ı seçin.
   
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
> Rapor düzenleme tuvalini daha önce hiç kullanmadıysanız veya bilgilerinizi tazelemeniz gerekiyorsa devam etmeden önce [Rapor düzenleyicisi ile ilgili bir tura katılın](service-the-report-editor-take-a-tour.md).> 
> 

## <a name="add-a-radial-gauge-to-the-report"></a>Rapora Radyal Ölçer ekleme
Veri kümemiz içeri aktarıldığına göre bazı soruları yanıtlamaya başlayalım.  Pazarlama Müdürümüz (CMO) bu yılki satış hedeflerimize ne kadar yaklaştığımızı öğrenmek istiyor. Bu tür bilgilerin görüntülenmesi için Ölçer, [iyi bir görselleştirme seçimi](../visuals/power-bi-report-visualizations.md) olacaktır.

1. Alanlar bölmesinde **Sales** > **This Year Sales** > **Değer** seçeneğini belirleyin.
   
    ![rapor düzenleyicisindeki çubuk grafik](media/service-report-create-new/power-bi-report-step1.png)
2. **Görselleştirmeler** bölmesinden Ölçer şablonunu ![Ölçer simge](media/service-report-create-new/powerbi-gauge-icon.png) seçerek görseli bir Ölçere dönüştürün.
   
    ![rapor düzenleyicisinde ölçer görseli](media/service-report-create-new/power-bi-report-step2.png)
3. **Sales** > **This Year Sales** > **Hedef** alanını **Hedef değer** kutusuna sürükleyin. Hedefimize çok yakın olduğumuzu görüyoruz.
   
    ![Hedef değer olarak Hedefin bulunduğu ölçer görseli](media/service-report-create-new/power-bi-report-step3.png)
4. Şimdi raporunuzu kaydedebilirsiniz.
   
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
6. Şimdi de dilimleyiciyi ekleyelim. Tuvalde boş bir alanı ve sonra Dilimleyici ![Dilimleyici simgesi](media/service-report-create-new/power-bi-slicer-icon.png) şablonunu seçin. Artık tuvalimizde boş bir dilimleyici var.
   
    ![rapor tuvali](media/service-report-create-new/power-bi-report-step6.png)    
7. Alanlar bölmesinde **District** > **District** seçeneğini belirleyin. Dilimleyiciyi taşıyın ve yeniden boyutlandırın.
   
    ![Rapor düzenleyicisi, Bölge ekleme](media/service-report-create-new/power-bi-report-step7.png)  
8. Bölgeye göre belirli desenler ve öngörüler bulmak için dilimleyiciyi kullanın.
   
   ![dilimleyici kullanımının videosu](media/service-report-create-new/power-bi-slicer-video2.gif)  

Verilerinizi keşfetmeye ve görsel öğeleri eklemeye devam edin. Özellikle ilgi çekici bilgiler bulduğunuzda [panoya sabitleyin](service-dashboard-pin-tile-from-report.md).

## <a name="next-steps"></a>Sonraki adımlar

* [Görselleştirmeleri bir panoya sabitlemeyi](service-dashboard-pin-tile-from-report.md) öğrenin   
* Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](https://community.powerbi.com/)
