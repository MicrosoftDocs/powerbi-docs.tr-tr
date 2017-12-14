---
title: "Power BI'daki Soru-Cevap özelliğini kullanma"
description: "Power BI'daki Soru-Cevap özelliğini kullanma"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
editor: 
tags: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/25/2017
ms.author: mihart
ms.openlocfilehash: a6736916a4bb2e94c1f5e1e3c3c3e5339cf990ec
ms.sourcegitcommit: 99cc3b9cb615c2957dde6ca908a51238f129cebb
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2017
---
# <a name="how-to-use-power-bi-qa"></a>Power BI'daki Soru-Cevap özelliğini kullanma
## <a name="ask-questions-of-your-data-using-natural-language"></a>Verilerinizle ilgili soruları doğal dil kullanarak sorun
Bir panodan başlayın. Soru-Cevap soru kutusu, sorunuzu doğal dil kullanarak yazdığınız yerdir. Soru-Cevap, yazdığınız kelimeleri tanıyarak cevabı nerede (hangi veri kümesinde) bulabileceğini belirler. Soru-Cevap ayrıca sorunuzu otomatik tamamlama ve farklı şekilde ifade etme özelliklerinin yanı sıra diğer metin ve görsel desteklerle biçimlendirmenize yardımcı olur.

![](media/service-how-to-q-and-a/powerbi-qna.png)

Sorunuzun cevabı etkileşimli görselleştirme olarak görüntülenir ve soruyu değiştirdiğinizde güncelleştirilir.

Soru-Cevap, etkileşimli ve eğlenceli bir özelliktir. Bir soruyla başlayıp devamını getirerek görselleştirmelerin ilgi çekici dünyasında kısa bir seyahate çıkabilirsiniz. Görsel oluşturmak, bu görsellerin ayrıntılarına inmek ve bu görselleri panolara sabitlemek için Soru-Cevap kullanımını gösteren Amanda'yı izleyin.

> [!NOTE]
> Soru-Cevap aynı zamanda [iPad, iPhone ve iPod touch cihazlarıyla iOS için Microsoft Power BI uygulamasında](mobile-apps-ios-qna.md) da kullanılabilir.
> 
> 

<iframe width="560" height="315" src="https://www.youtube.com/embed/qMf7OLJfCz8?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

## <a name="use-natural-language-to-ask-questions-about-your-data"></a>Verilerinizle ilgili sorular sormak için doğal dil kullanma
1. İmlecinizi soru kutusuna yerleştirin. Soru-Cevap özelliği, yazmaya başlamadan önce sorunuzu oluşturmanıza yardımcı olacak önerilerin bulunduğu yeni bir ekran görüntüler.
   
   ![](media/service-how-to-q-and-a/powerbi-qna-cursor.png)  
   
   Listede şunlar bulunur:  
   a.  Panoya sabitlenmiş olan [kutucukları](service-dashboard-tiles.md) oluşturma aşamasında kullanılan sorular ve  
   b.  [temel alınan veri kümelerindeki](service-get-data.md) tablo adları.  
   
   Bu sorulardan birini başlangıç noktası olarak kullanabilir, soruyu değiştirerek aradığınız sonuca ulaşabilirsiniz. İsterseniz yeni soru oluşturmanıza yardımcı olması için tablo adı yazabilirsiniz.
2. Açılan menüden seçim yapın veya sorunuzu yazmaya başlayın.  
   
   ![](media/service-how-to-q-and-a/powerbi-qna-list.png)
3. Siz soruyu yazarken Power BI Soru-Cevap özelliği, cevabınızı görüntülemek üzere en iyi [görselleştirmeyi](power-bi-visualization-types-for-reports-and-q-and-a.md) seçer. Siz soruyu değiştirdikçe görselleştirmeler de dinamik olarak değiştirilir. Soru-Cevap ayrıca sorunuzu otomatik tamamlama ve farklı şekilde ifade etme özelliklerinin yanı sıra diğer metin ve görsel desteklerle oluşturmanıza yardımcı olur.  
   ![](media/service-how-to-q-and-a/powerbi-qna-viz.png)
4. Bir sorgu yazdığınızda Power BI ilgili panoda kutucuğu bulunan tüm veri kümelerinde cevap arar.  Tüm kutucukların kaynağı *datasetA* ise cevabınız *datasetA* kaynağından gelir.  Hem *datasetA* hem de *datasetB* varsa Soru-Cevap, bu 2 veri kümesinden en iyi cevabı almak için arama yapar.
   
   > [!TIP]
   > Bu nedenle dikkatli olmanızda fayda vardır, *datasetA* kaynağından tek bir kutucuğunuz varsa ve bunu panonuzdan kaldırırsanız Soru-Cevap artık *datasetA* erişimine sahip olmaz.
   > 
   > 
5. Sonuç içinize sindiğinde sağ üst köşedeki raptiye simgesini seçerek [görselleştirmeyi panoya sabitleyebilirsiniz](service-dashboard-pin-tile-from-q-and-a.md). Sizinle paylaşılmış veya bir uygulamanın parçası olan panoları sabitleyemezsiniz.
   
   ![](media/service-how-to-q-and-a/pbi_qna_finish-typing-question.jpg)

### <a name="tell-qa-which-visualization-to-use"></a>Soru-Cevap özelliğine, kullanılacak görselleştirmeleri söyleyin.
Soru-Cevap ile yalnızca verileri değil görüntüleme şeklini de belirleyebilirsiniz. Sorunuzun yanına "as a <visualization type>" eklemeniz yeterlidir.  Örneğin "show inventory volume by plant as a map" ve "show total inventory as a card".  Kendiniz deneyin.

## <a name="how-does-qa-know-how-to-answer-questions"></a>Soru-Cevap, sorularınızı nasıl cevaplıyor?
### <a name="which-datasets-does-qa-use"></a>Soru-Cevap hangi veri kümelerini kullanmaktadır?
Soru-Cevap, verilere özgü soruları nasıl cevaplıyor? Temel alınan veri kümesindeki tabloların, sütunların ve hesaplanmış alanların adlarını kullanır. Bu nedenle öğelerin sizin tarafınızdan (veya veri kümesi sahibi tarafından) adlandırılması önemlidir! 

Örneğin, şu sütunların bulunduğu "Sales" adlı bir Excel tablonuz olduğunu kabul edelim: "Product", "Month", "Units Sold", "Gross Sales" ve "Profit". Bu varlıkların herhangi biriyle ilgili soru sorabilirsiniz.  "show *sales*, "total *profit* by *month*", "sort *products* by *units sold*" ve başka birçok soruyu yönlendirebilirsiniz.

Soru-Cevap özelliğinin sorularınızın cevabını bulması için veri kümenizin düzenli olması gerekir. Bu özellikler Salesforce verileriyle nasıl çalışır? salesforce.com hesabınıza bağlandığınızda Power BI otomatik olarak bir pano oluşturur.  Soru-Cevap özelliğini kullanarak soru sormaya başlamadan önce pano görselleştirmelerinde görüntülenen verilere ve Soru-Cevap açılan menüsünde görüntülenen verilere bakın.

* Görselleştirmenin eksen etiketlerinde ve değerlerinde "sales", "account", "month" ve "opportunities" yazıyorsa rahatlıkla şöyle sorular sorabilirsiniz: "Which *account* has the highest *opportunity*, or show *sales* by month as a bar chart."
* Açılan menüde "salesperson", "state" ve "year" varsa rahatlıkla şöyle sorular sorabilirsiniz: "which *salesperson* had the lowest *sales* in *Florida* in *2013*."

Google Analytics'te web sitesi performans verileri varsa Soru-Cevap özelliğine web sayfasında geçirilen süreyi, benzersiz sayfa ziyareti sayısını ve kullanıcı etkileşim oranlarını sorabilirsiniz. Demografik verileri sorguluyorsanız yaş ve konuma göre hane geliriyle ilgili sorular sorabilirsiniz.

### <a name="which-visualization-does-qa-use"></a>Soru-Cevap hangi görselleştirmeleri kullanır?
Soru-Cevap görüntülenen verilere en uygun görselleştirmeyi seçer. Bazen temel alınan veri kümeleri belirli bir tür veya kategoride tanımlanmış olur ve bu durum Soru-Cevap özelliğine ilgili verileri görüntüleme konusunda yardımcı olur. Örneğin, verilerin türü tarih olarak tanımlanmışsa çizgi grafik olarak görüntülenme olasılığı yüksektir. Kategorisi şehir olarak belirlenmiş veriler ise genelde harita olarak görüntülenir.

Sorunuza görselleştirme türünü ekleyerek Soru-Cevap özelliğinin o türü kullanmasını sağlayabilirsiniz. Ancak Soru-Cevap özelliğinin, verileri her zaman istediğiniz görselleştirme türünde görüntülemesinin mümkün olmayacağını unutmayın.

Soru-Cevap özelliğinin tanıdığı anahtar sözcükler hakkında bilgi için bkz. [Soru sormaya ilişkin ipuçları](service-q-and-a-tips.md).

## <a name="next-steps"></a>Sonraki adımlar
[Power BI'daki Soru-Cevap](service-q-and-a.md) özelliğine geri dön  
[Eğitim: Soru-Cevap özelliğini Perakende Satış örneğiyle kullanma](power-bi-visualization-introduction-to-q-and-a.md)  
[Soru-Cevap'ta soru sormaya yönelik ipuçları](service-q-and-a-tips.md)  
[Bir çalışma kitabını Soru-Cevap için hazırlama](service-prepare-data-for-q-and-a.md)  
[Pin a tile to the dashboard from Q&A (Soru-Cevap kutucuklarını panolara sabitleme)](service-dashboard-pin-tile-from-q-and-a.md)  

