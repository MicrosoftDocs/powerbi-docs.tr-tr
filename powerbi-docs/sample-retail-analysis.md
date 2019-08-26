---
title: 'Power BI için Perakende Analizi örneği: Tura katılın'
description: 'Power BI için Perakende Analizi örneği: Tura katılın'
author: maggiesMSFT
manager: kfile
ms.reviewer: amac
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 07/02/2019
ms.author: maggies
LocalizationGroup: Samples
ms.openlocfilehash: b3adcf3ba97e83875187a11116fdb7b642e5560b
ms.sourcegitcommit: 0e50ebfa8762e19286566432870ef16d242ac78f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/13/2019
ms.locfileid: "68962230"
---
# <a name="retail-analysis-sample-for-power-bi-take-a-tour"></a>Power BI için Perakende Analizi örneği: Tura katılın

Perakende Analizi örneği içerik paketinde birden çok mağaza ve bölgede satılan öğelerin perakende satış verilerini analiz eden bir pano, rapor ve veri kümesi vardır. Ölçümler bu yılın performansını geçen yılın satış, birim sayısı, brüt kar, varyans ve yeni mağaza analizi rakamlarıyla karşılaştırmaktadır. 

![Perakende Analizi örneği panosu](media/sample-retail-analysis/retail1.png)

Bu örnek, Power BI'ı işle ilgili veriler, raporlar ve panolarla birlikte nasıl kullanabileceğinizi gösteren serinin bir parçasıdır. Örnek, [obviEnce](http://www.obvience.com/) öğesinden alınan, anonimleştirilmiş gerçek verilerle oluşturulmuştur. Veriler çeşitli biçimlerde sunulur: içerik paketi, .pbix Power BI Desktop dosyası veya Excel çalışma kitabı. Bkz. [Power BI Örnekleri](sample-datasets.md). 

Bu öğreticide, Power BI hizmetinde Perakende Analizi örneği içerik paketi incelenir. Power BI Desktop ile hizmette rapor deneyimleri benzer olduğundan, Power BI Desktop'ta örnek .pbix dosyasını kullanarak da örneği takip edebilirsiniz. 

Power BI Desktop'ta örnekleri incelemek için Power BI lisansına ihtiyacınız yoktur. Power BI Pro lisansınız yoksa örneği Power BI hizmetinde Çalışma Alanım alanınıza kaydedebilirsiniz. 

## <a name="get-the-sample"></a>Örneği alma

 Örneği kullanabilmeniz için bir [içerik paketi](#get-the-content-pack-for-this-sample), [.pbix dosyası](#get-the-pbix-file-for-this-sample) veya [Excel çalışma kitabı](#get-the-excel-workbook-for-this-sample) olarak indirmeniz gerekir.

### <a name="get-the-content-pack-for-this-sample"></a>Bu örneğe ilişkin içerik paketini edinme

1. Power BI hizmetini açın (app.powerbi.com), oturum açın ve örneği kaydetmek istediğiniz çalışma alanını açın. 

    Power BI Pro lisansınız yoksa örneği Çalışma Alanım alanınıza kaydedebilirsiniz.

2. Sol alt köşedeki **Veri Al**'ı seçin.

    ![Veri Al’ı seçme](media/sample-datasets/power-bi-get-data.png)
3. Görüntülenen **Veri Al** sayfasında **Örnekler**'i seçin.
   
4. **Perakende Analizi Örneği**'ni ve ardından **Bağlan**'ı seçin.  
  
   ![Örneğe bağlanma](media/sample-retail-analysis/retail16.png)
   
5. Power BI, içerik paketini içeri aktarır ve ardından geçerli çalışma alanınıza yeni bir pano, rapor ve veri kümesi ekler.
   
   ![Perakende Analizi Örneği girdisi](media/sample-retail-analysis/retail-entry.png)
  
### <a name="get-the-pbix-file-for-this-sample"></a>Bu örneğe ilişkin .pbix dosyasını edinme

Alternatif olarak, Perakende Analizi örneğini bir [.pbix dosyası](http://download.microsoft.com/download/9/6/D/96DDC2FF-2568-491D-AAFA-AFDD6F763AE3/Retail%20Analysis%20Sample%20PBIX.pbix) olarak indirebilirsiniz. Bu dosya biçimi Power BI Desktop ile kullanım için tasarlanmıştır. 

### <a name="get-the-excel-workbook-for-this-sample"></a>Bu örneğe ilişkin Excel çalışma kitabını edinme

Bu örnekte kullanılan veri kaynağını görüntülemek isterseniz, [Excel çalışma kitabı](http://go.microsoft.com/fwlink/?LinkId=529778) olarak da bulabilirsiniz. Çalışma kitabı, görüntüleyebileceğiniz ve değiştirebileceğiniz Power View sayfaları içerir. Ham verileri görmek için Veri Çözümlemesi eklentilerini etkinleştirip **Power Pivot > Yönet**'i seçin. Power View ve Power Pivot eklentilerini etkinleştirme ayrıntıları için bkz. [Excel'in içinden Excel örneklerini gözden geçirme](sample-datasets.md#optional-take-a-look-at-the-excel-samples-from-inside-excel-itself).

## <a name="start-on-the-dashboard-and-open-the-report"></a>Panodan başlayın ve raporu açın

1. Örneği kaydettiğiniz çalışma alanında **Panolar** sekmesini açın, sonra **Perakende Analizi Örneği** panosunu bulun ve bu panoyu seçin. 
2. Panoda **Total Stores New & Existing Stores** kutucuğunu seçin. Bu kutucuk Perakende Analizi Örneği raporunun **Store Sales Overview** sayfasını açar. 

   ![Toplam Mağaza Sayısı kutucuğu](media/sample-retail-analysis/retail-analysis-7.png)  

   Bu rapor sayfasında toplam 104 mağazamız olduğunu ve bunlardan 10'unun yeni olduğunu görürsünüz. Fashions Direct ve Lindseys olmak üzere iki zincirimiz var. Fashions Direct mağazaları ortalamaya göre daha büyük.
3. **This Year Sales by Chain** pasta grafiğinde **Fashions Direct**'i seçin.

   ![This Year Sales by Chain grafiği](media/sample-retail-analysis/retail3.png)  

   **Total Sales Variance %** kabarcık grafiğinde sonucu gözden geçirin:

   ![Total Sales Variance % grafiği](media/sample-retail-analysis/pbi_sample_retanlbubbles.png)  

   **FD-01** bölgesi en yüksek ortalama **Sales per Square Foot** değerine sahipken FD-02 geçen yılla karşılaştırıldığında en düşük **Total Sales Variance** değerine sahip. FD-03 ve FD-04 tüm bölgeler arasında en düşük performansa sahip olanlar.
4. Seçimlerinizin etkisini ortaya çıkaran çapraz vurgulamayı görmek için kabarcıkları veya diğer grafikleri seçin.
5. Panoya dönmek için üst gezinti çubuğundan **Perakende Analizi Örneği**'ni seçin.

   ![Gezinti çubuğu](media/sample-retail-analysis/power-bi-breadcrumbs.png)
6. Panoda **This Year's Sales New & Existing Stores** kutucuğunu seçin. Bu seçim, Soru-Cevap soru kutusuna *This year sales* (Bu yılın satışları) yazmakla eşdeğerdir.

   ![This Year's Sales kutucuğu](media/sample-retail-analysis/pbi_sample_retanlthisyrsales.png)

   Soru-Cevap sonuçları gösterilir:

   ![Soru-Cevap'ta bu yılın satışları](media/sample-retail-analysis/retail7.png)

## <a name="review-a-tile-created-with-power-bi-qa"></a>Power BI Soru-Cevap ile oluşturulmuş olan bir kutucuğu gözden geçirme
Biraz daha ayrıntıya inelim.

1. Soruyu _this year sales **by district**_ (bölgeye göre bu yılın satışları) olarak değiştirin. Sonucu inceleyin: Soru-Cevap yanıtı otomatik olarak bir çubuk grafiğe yerleştirir ve başka tümcecikler önerir:

   ![Soru-Cevap'ta bölgeye göre bu yılın satışları](media/sample-retail-analysis/retail8.png)
2. Şimdi de soruyu _this year sales **by zip and chain**_ (posta kodu ve zincire göre bu yılın satışları) olarak değiştirin.

   Siz yazdığınız sırada Power BI'ın nasıl sorunuzu yanıtladığına ve uygun grafikleri görüntülediğine dikkat edin.
3. Başka sorularla deneme yapın ve elde ettiğiniz sonuçları inceleyin.
4. Hazır olduğunuzda panoya geri dönün.

## <a name="dive-deeper-into-the-data"></a>Verileri ayrıntılı bir şekilde inceleme
Şimdi bölgelerin performanslarına bakarak verileri daha ayrıntılı bir şekilde araştıralım.

1. Panoda **This Year's Sales, Last Year's Sales** kutucuğunu seçin. Bu kutucuk raporun **District Monthly Sales** sayfasını açar.

   ![This Year's Sales, Last Year's Sales kutucuğu](media/sample-retail-analysis/pbi_sample_retanlareacht.png)

   **Total Sales Variance % by Fiscal Month** grafiğinde geçen yılla karşılaştırıldığında fark yüzdesindeki büyük değişkenliğine ve Ocak, Nisan ve Temmuz aylarının özellikle kötü geçtiğine dikkat edin.

   ![Total Sales Variance % by Fiscal Month grafiği](media/sample-retail-analysis/pbi_sample_retanlsalesvarcol.png)

   Şimdi bu sorunların kaynağına inip inemeyeceğimize bir bakalım.
2. Kabarcık grafiğinde **020-Mens** kabarcığını seçin.

   ![020-Mens kabarcığını seçin](media/sample-retail-analysis/retail11.png)  

   Nisan ayında erkek kategorisinin işletmenin geneli kadar ciddi etkilenmediğini ancak Ocak ve Temmuz aylarında yine de sorun yaşandığına dikkat edin.
1. **010-Womens** kabarcığını seçin.

   ![010-Womens kabarcığını seçin](media/sample-retail-analysis/retail12.png)

   Kadınlar kategorisinin tüm aylarda işletmenin genelinden çok daha kötü performans gösterdiğine ve önceki yılla karşılaştırıldığında neredeyse tüm aylarda daha kötü bir performans sergilediğine dikkat edin.
1. Kabarcığı tekrar seçerek filtreyi temizleyin.

## <a name="try-out-the-slicer"></a>Dilimleyiciyi deneyin
Şimdi belirli bölgelerin performanslarına göz atalım.

1. Sol üstteki **District Manager** dilimleyicisinden **Allan Guinot**'ı seçin.

   ![Allan Guinot'ı seçin](media/sample-retail-analysis/retail13.png)

   Allan'ın bölgesinin Mart ve Haziran aylarında geçen yıla göre daha iyi bir performans gösterdiğine dikkat edin.
2. **Allan Guinot** seçili durumdayken kabarcık grafiğinde **Womens-10** kabarcığını seçin.

   ![Allan Guinot ve Womens-10 seçili](media/sample-retail-analysis/power-bi-allan.png)

   Womens-10 kategorisinde Allan'ın bölgesinin geçen yılın hacmine ulaşamadığına dikkat edin.
3. Diğer bölge yöneticilerini ve kategorileri inceleyin. Başka hangi içgörülere ulaşabiliyorsunuz?
4. Hazır olduğunuzda panoya geri dönün.

## <a name="what-the-data-says-about-sales-growth-this-year"></a>Veriler bu yılki satış artışı hakkında ne söylüyor?
İncelemek istediğimiz son nokta büyüme verileri, bunu bu yıl açılan mağazaları inceleyerek yapacağız.

1. **Stores Opened This Year by Open Month, Chain** kutucuğunu seçin. Bu kutucuk raporun **New Stores Analysis** sayfasını açar.

   ![New Stores Analysis sayfası](media/sample-retail-analysis/retail15.png)

   Kutucuktan kolayca anlaşıldığı üzere bu yıl açılan Fashions Direct mağazalarının sayısı Lindseys mağazalarından fazla.
2. **Sales Per Sq Ft by Name** grafiğini gözlemleyin:

   ![Sales Per Sq Ft by Name grafiği](media/sample-retail-analysis/retail14.png)

    Yeni mağazaların ortalama satış/metre kare farkına dikkat edin.
3. Sağ üstteki **Open Store Count by Open Month and Chain** grafiğinde göstergedeki **Fashions Direct** öğesini seçin. Aynı zincirde bile en iyi mağazanın (Winchester Fashions Direct), $21,22 değerine karşı $12,86 ile, en kötü mağazadan (Cincinnati 2 Fashions Direct) çok daha iyi olduğuna dikkat edin.

   ![Fashions Direct seçili](media/sample-retail-analysis/power-bi-lindseys.png)
4. **Name** dilimleyicisindeki **Winchester Fashions Direct** öğesini seçin ve çizgi grafiği inceleyin. İlk satış rakamları Şubat ayında bildirilmiş.
5. Dilimleyicideki **Cincinnati 2 Fashions Direct** öğesini seçin; çizgi grafikte Haziran ayında açıldığını ve en kötü performansa sahip mağaza gibi göründüğünü göreceksiniz.
6. Tüm grafiklerde diğer çubukları, çizgileri ve kabarcıkları seçerek inceleyin ve içgörüleri keşfedin.

## <a name="next-steps-connect-to-your-data"></a>Sonraki adımlar: Verilerinize bağlanma
Değişikliklerinizi kaydetmek zorunda olmadığınızdan, bu ortamda güvenle farklı şeyler deneyebilirsiniz. Değişikliklerinizi kaydetseniz bile, dilediğiniz zaman **Veri Al**'ı seçip bu örneğin yeni bir kopyasını oluşturabilirsiniz.

Power BI panolarının, Soru-Cevap özelliğinin ve raporların örnek veriler için nasıl içgörüler sağlayacağını gösterme konusunda etkili bir tur deneyimi yaşadığınızı umuyoruz. Artık siz de kendi verilerinize bağlanarak çalışmaya başlayabilirsiniz. Power BI ile çok çeşitli veri kaynaklarına bağlanabilirsiniz. Daha fazla bilgi edinmek için bkz. [Power BI hizmeti ile çalışmaya başlama](service-get-started.md).
