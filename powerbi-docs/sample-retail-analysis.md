---
title: "Power BI için Perakende Analizi örneği: Tura katılın"
description: "Power BI için Perakende Analizi örneği: Tura katılın"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: no
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 12/04/2017
ms.author: mihart
ms.openlocfilehash: 09e245e625c9e0859f93837e56b564218e327926
ms.sourcegitcommit: 54da95f184dd0f7bb59bb0bc8775a1d93129b195
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/08/2017
---
# <a name="retail-analysis-sample-for-power-bi-take-a-tour"></a>Power BI için Perakende Analizi örneği: Tura katılın

Sektörden alınan örneklerin yer aldığı pano ve bağlantılı raporda, birden fazla mağazada ve bölgede satışı yapılan mallara ilişkin perakende satış verileri çözümlenmektedir. Ölçümler şu alanlarda bu yılın performansını geçen yılın rakamlarıyla karşılaştırmaktadır: satış, birim sayısı, brüt kâr, varyans ve yeni mağaza analizi. Anonim hale getirilmiş bu gerçek veriler, obviEnce'tan ([www.obvience.com](http://www.obvience.com)) alınmıştır.

[!Note] Ayrıca [sadece bu örneğe ilişkin veri kümesini (Excel çalışma kitabı) de indirebilirsiniz](http://go.microsoft.com/fwlink/?LinkId=529778). Çalışma kitabı, görüntüleyebileceğiniz ve değiştirebileceğiniz Power View sayfaları içerir.  Ham verileri görmek için **Power Pivot > Yönet** seçeneğini belirleyin. 

![](media/sample-retail-analysis/retail1.png)

## <a name="start-on-the-dashboard-and-open-the-report"></a>Panodan başlayın ve raporu açın
1. Panoda, "Total Stores" kutucuğunu seçin:
   
   ![](media/sample-retail-analysis/retail-analysis-7.png)  
   
   Rapordaki "Store Sales Overview" sayfası açılır. Toplamda 104 tane mağaza olduğunu ve bunların 10 tanesinin yeni olduğunu görüyoruz. Fashions Direct ve Lindseys olmak üzere iki zincirimiz var. Fashions Direct mağazaları ortalamaya göre daha büyük.
2. Pasta grafiğinde, **Fashions Direct**'i seçin.
   
   ![](media/sample-retail-analysis/retail3.png)  
   
   Kabarcık grafiğindeki sonuca dikkat edin:
   
   ![](media/sample-retail-analysis/pbi_sample_retanlbubbles.png)  
   
   FD-01 bölgesi en yüksek Average Sales per Square Foot değerine sahipken FD-02, geçen yılla karşılaştırıldığında en düşük Variance in Sales değerine sahip; FD-03 ve FD-04 ise tüm bölgeler arasında en düşük performansa sahip olanlar.
3. Seçimlerinizin etkisini ortaya çıkaran çapraz vurgulamayı görmek için kabarcıkları veya diğer grafikleri seçin.
4. Panoya dönmek için, üst gezinti çubuğunda (içerik haritaları) panonun adını seçin. 
   
   ![](media/sample-retail-analysis/power-bi-breadcrumbs.png)
5. Panoda, "This Year's Sales" kutucuğunu seçin.
   
   ![](media/sample-retail-analysis/pbi_sample_retanlthisyrsales.png)
   
   Bu, soru kutusuna "This year sales" yazmakla eşdeğerdir.
   
   Şu ekranı görürsünüz:
   
   ![](media/sample-retail-analysis/retail7.png)

## <a name="review-a-tile-created-with-power-bi-qa"></a>Power BI Soru-Cevap ile oluşturulmuş olan bir kutucuğu gözden geçirme
Biraz daha ayrıntıya inelim.

1. Soruya "this year sales **by district**" yazın. Sonucu inceleyin: Yanıtı otomatik olarak bir çubuk grafiğe yerleştirir ve başka ifadeler önerir:
   
   ![](media/sample-retail-analysis/retail8.png)
2. Şimdi soruyu "this year sales **by zip and chain**" olarak değiştirelim.
   
   Siz yazdığınız sırada, sorunuzu uygun grafiklerle nasıl yanıtladığına dikkat edin.
3. Başka sorularla deneme yapın ve elde ettiğiniz sonuçları inceleyin.
4. Hazır olduğunuzda panoya geri dönün.

## <a name="dive-deeper-into-the-data"></a>Verileri ayrıntılı bir şekilde inceleme
Şimdi bölgelerin performanslarına bakarak verileri daha ayrıntılı bir şekilde araştıralım.

1. Panoda, bu yılın satışlarını geçen yılınkilerle karşılaştıran kutucuğu seçin.
   
   ![](media/sample-retail-analysis/pbi_sample_retanlareacht.png)
   
   Geçen yıla göre Variance % değerinde çok fazla dalgalanma olduğuna; Ocak, Nisan ve Temmuz aylarının özellikle kötü geçtiğine dikkat edin.
   
   ![](media/sample-retail-analysis/pbi_sample_retanlsalesvarcol.png)
   
   Şimdi bu sorunların kaynağına inip inemeyeceğimize bir bakalım.
2. Kabarcık grafiğini ve ardından **020-Mens** kabarcığını seçin.
   
   ![](media/sample-retail-analysis/retail11.png)  
   
   Nisan ayında erkek kategorisinin işletmenin geneli kadar ciddi etkilenmediğini ancak Ocak ve Temmuz aylarında sorun yaşandığına dikkat edin.
3. Şimdi **010-Womens** kabarcığını seçin.
   
   ![](media/sample-retail-analysis/retail12.png)
   
   Kadınlar kategorisinin tüm aylarda işletmenin genelinden çok daha kötü performans gösterdiğine ve önceki yılla karşılaştırıldığında neredeyse tüm aylarda daha kötü bir performans sergilediğine dikkat edin.
4. Kabarcığı tekrar seçerek filtreyi temizleyin.

## <a name="try-out-the-slicer"></a>Dilimleyiciyi deneyin
Şimdi belirli bölgelerin performanslarına göz atalım.

1. Sol üstteki dilimleyiciden Allan Guinot'ı seçin.
   
   ![](media/sample-retail-analysis/retail13.png)
   
   Allan'ın bölgesinin Mart ve Haziran ayları için geçen yıldan daha iyi bir performans gösterdiğine dikkat edin.
2. Allan seçili durumdayken Women's kabarcığını seçin.
   
   ![](media/sample-retail-analysis/power-bi-allan.png)
   
   Women's kategorisi için Allan'ın bölgesi, önceki yılın satış hacmini hiç yakalayamamış.
3. Diğer bölge yöneticilerini ve kategorileri inceleyin. Başka hangi öngörülere ulaşabiliyorsunuz?
4. Hazır olduğunuzda panoya geri dönün.

## <a name="what-is-our-data-telling-us-about-sales-growth-this-year"></a>Verilerimiz bu yılki satış artışı hakkında neler söylüyor?
İncelemek istediğimiz son nokta büyüme verileri, yani bu yıl açılan mağazalar.

1. "Stores Opened This Year" kutucuğunu seçin.
   
   ![](media/sample-retail-analysis/retail15.png)
   
   Kutucuktan kolayca anlaşıldığı üzere bu yıl açılan Fashions Direct mağazalarının sayısı Lindseys mağazalarından fazla.
2. "Sales Per Sq Ft by Name" grafiğini inceleyin:
   
   ![](media/sample-retail-analysis/retail14.png)
   
    Yeni mağazaların Average Sales per SQF değerleri arasında oldukça fark var.
3. Sağ üst grafikteki Fashions Direct açıklama öğesine tıklayın. Aynı zincirde bile en iyi mağazanın (Winchester Fashions Direct), $21,22 değerine karşı $12,86 ile, en kötü mağazadan (Cincinnati 2 Fashions Direct) çok daha iyi olduğuna dikkat edin.
   
   ![](media/sample-retail-analysis/power-bi-lindseys.png)
4. Dilimleyicideki Winchester Fashions Direct öğesine tıklayın ve çizgi grafiği inceleyin. İlk satış rakamları Şubat ayında bildirilmiş.
5. Dilimleyicideki Cincinnati 2 Fashions Direct öğesine tıkladığınızda, çizgi grafikte, Haziran ayında açıldığını ve en kötü performansa sahip mağaza olduğunu göreceksiniz.
6. Önceki örneklerde olduğu gibi, grafiklerdeki diğer çubuklara, çizgilere ve kabarcıklara tıklayarak araştırma yapın ve öngörüler keşfedin.

Bu ortamda dilediğiniz işlemi gerçekleştirebilirsiniz. Değişikliklerinizi kaydetmemeyi seçme konusunda her zaman özgürsünüz. Değişikliklerinizi kaydetseniz bile Veri Al sayfasına giderek bu örneğin yeni bir kopyasını oluşturabilirsiniz.

## <a name="connect-to-your-data"></a>Verilerinize bağlanma
Power BI panolarının, Soru-Cevap özelliğinin ve raporların perakende verileri için nasıl öngörüler sağlayacağını gösterme konusunda etkili bir tur deneyimi edindiğinizi umuyoruz. Artık siz de kendi verilerinize bağlanarak çalışmaya başlayabilirsiniz. Power BI ile çok çeşitli veri kaynaklarına bağlanabilirsiniz. [Power BI ile çalışmaya başlama](service-get-started.md) hakkında daha fazla bilgi edinin.

## <a name="next-steps"></a>Sonraki adımlar
* [Perakende Analizi örnek içerik paketini indirme](sample-tutorial-connect-to-the-samples.md)    
* [Bu Power BI örneğine ilişkin Excel çalışma kitabını indirme](http://go.microsoft.com/fwlink/?LinkId=529778)    
* [Power BI için veri alma](service-get-data.md)    
* [Power BI - Temel Kavramlar](service-basic-concepts.md)    
* Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)
