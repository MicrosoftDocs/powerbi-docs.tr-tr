---
title: 'Power BI için Fırsat Analizi Örneği: Tura katılın'
description: 'Power BI için Fırsat Analizi Örneği: Tura katılın'
author: mihart
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 05/20/2018
ms.author: mihart
LocalizationGroup: Samples
ms.openlocfilehash: d3a18b2505739d28276fbe9fc269bbf774879fa6
ms.sourcegitcommit: 80d6b45eb84243e801b60b9038b9bff77c30d5c8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34481084"
---
# <a name="opportunity-analysis-sample-for-power-bi-take-a-tour"></a>Power BI için Fırsat Analizi Örneği: Tura katılın

## <a name="overview-of-the-opportunity-analysis-sample"></a>Fırsat Analizi örneğine genel bakış
**Fırsat Analizi Örneği**'nde *doğrudan* ve *iş ortağı* olmak üzere 2 satış kanalına sahip olan bir yazılım şirketiyle ilgili pano (ve ilişkili rapor) yer almaktadır. Satış Yöneticisi, fırsatları ve geliri bölgeye, anlaşma boyutuna ve kanala göre izlemek için bu panoyu oluşturmuştur.

Satış Yöneticisi, gelir için iki ölçü kullanmaktadır:

* **Revenue**: Bu değer bir satıcının, gelirin ne olacağına yönelik tahminidir.
* **Factored Revenue**: Bu değer, Gelir X Olasılık % şeklinde hesaplanır ve genellikle gerçek satış gelirinin daha doğru bir göstergesi olduğu düşünülür. Olasılık, fırsatın geçerli ***Sales Stage*** verilerine göre belirlenir.
  * Lead: %10  
  * Qualify: %20  
  * Solution: %40  
  * Proposal: %60  
  * Finalize: %80

  ![](media/sample-opportunity-analysis/opportunity1.png)

Bu örnek, iş odaklı veriler, raporlar ve panolar ile Power BI' nasıl kullanabileceğinizi gösteren serinin bir parçasıdır. Bunlar, obviEnce'tan ([www.obvience.com](http://www.obvience.com/)) alınan anonimleştirilmiş gerçek verilerdir.

## <a name="prerequisites"></a>Önkoşullar

 Örneği kullanabilmeniz için bir [içerik paketi](https://docs.microsoft.com/power-bi/sample-opportunity-analysis#get-the-content-pack-for-this-sample), [.pbix dosyası](http://download.microsoft.com/download/9/1/5/915ABCFA-7125-4D85-A7BD-05645BD95BD8/Opportunity-Analysis-Sample-PBIX.pbix) veya [Excel çalışma kitabı](http://go.microsoft.com/fwlink/?LinkId=529782) olarak indirmeniz gerekir.

### <a name="get-the-content-pack-for-this-sample"></a>Bu örneğe ilişkin içerik paketini edinme

1. Power BI hizmeti (app.powerbi.com) sayfasına gidin ve oturum açın.
2. Sol alt köşedeki **Veri Al** seçeneğini belirleyin.
   
    ![](media/sample-datasets/power-bi-get-data.png)
3. Görüntülenen Veri Al sayfasında **Örnekler** simgesini seçin.
   
   ![](media/sample-datasets/power-bi-samples-icon.png)
4. **Fırsat Analizi Örneği**'ni ve ardından **Bağlan**'ı seçin.  
  
   ![Veri Al](media/sample-opportunity-analysis/opportunity-connect.png)
   
5. Power BI, içerik paketini içeri aktarır ve geçerli çalışma alanınıza yeni bir pano, rapor ve veri kümesi ekler. Yeni içerik sarı yıldızla işaretlenir. 
   
   ![Yıldız işareti](media/sample-opportunity-analysis/opportunity-asterisk.png)
  
### <a name="get-the-pbix-file-for-this-sample"></a>Bu örneğe ilişkin .pbix dosyasını edinme

Alternatif olarak, örneği bir .pbix dosyası olarak indirebilirsiniz. Bu dosya biçimi, Power BI Desktop ile kullanım için tasarlanmıştır. 

 * [Fırsat Analizi Örneği](http://download.microsoft.com/download/9/1/5/915ABCFA-7125-4D85-A7BD-05645BD95BD8/Opportunity%20Analysis%20Sample%20PBIX.pbix)

### <a name="get-the-excel-workbook-for-this-sample"></a>Bu örneğe ilişkin Excel çalışma kitabını edinme
Ayrıca bu örnek için [ yalnızca veri kümesini de (Excel çalışma kitabı) indirebilirsiniz](http://go.microsoft.com/fwlink/?LinkId=529782). Çalışma kitabı, görüntüleyebileceğiniz ve değiştirebileceğiniz Power View sayfaları içerir. Ham verileri görmek için **Power Pivot > Yönet** seçeneğini belirleyin.


## <a name="what-is-our-dashboard-telling-us"></a>Panomuz bize ne anlatıyor?
Satış Yöneticisi en önemli olduğunu düşündüğü ölçümleri izlemek için bir pano oluşturmuştur. İlginç bir bulguyla karşılaştığında bir kutucuğu seçip söz konusu verileri ayrıntılı olarak inceleyebilir.

1. Şirket geliri 2 milyar ABD doları, faktörlere göre gelir ise 461 milyon ABD doları seviyesindedir.
2. Fırsat sayısı ve gelir, toplam rakamların ilerleyen aşamalarda azaldığı bilindik bir huni desenini takip etmektedir.
3. Fırsatlarımızın çoğu Doğu bölgesindedir.
4. Büyük çaplı fırsatlar orta veya küçük çaplı fırsatlardan daha fazla gelir getirmektedir.
5. Büyük iş ortağı anlaşmaları 6 milyon ABD doları seviyesindeki doğrudan satışlara kıyasla ortalama 8 milyon ABD doları ile daha fazla gelir getirmektedir.

Büyük, orta veya küçük ölçekli anlaşmaları gerçekleştirmek için aynı ölçüde efor sarf edildiğinden şirketimiz verilerin ayrıntılarına inerek büyük fırsatlar hakkında daha fazla bilgi edinmelidir.

Raporun 1. sayfasını açmak için **Partner Driven ve Sales Stage tarafından düzenlenen Opportunity Count** kutucuğunu seçin.  
![](media/sample-opportunity-analysis/opportunity2.png)

## <a name="explore-the-pages-in-the-report"></a>Rapordaki sayfaları inceleme
### <a name="page-1-of-our-report-is-titled-opportunity-count-overview"></a>Raporumuzun 1. sayfası "Opportunity Count Overview" olarak adlandırılmıştır.
![](media/sample-opportunity-analysis/opportunity3.png)

* Fırsat sayısı bakımından en büyük bölge Doğu olmuştur.  
* Pasta grafiğindeki bölgeleri teker teker seçerek sayfayı filtreleyin. Her bölgede iş ortaklarının daha büyük fırsatlar kovaladığını görebiliyoruz.   
* "Partner Driven ve Opportunity Size tarafından düzenlenen Opportunity Count" sütun grafiği, büyük fırsatların çoğunun iş ortakları tarafından yaratıldığını ve küçük veya orta düzey fırsatlarda iş ortaklarının çoğunlukta olmadığını göstermektedir.
* Sol alttaki çubuk grafikte yer alan Sales Stage öğelerini seçerek bölgesel sayıların arasındaki farkı inceleyin ve sayı açısından en büyük bölgemiz Doğu olmasına rağmen 3 bölgenin Solution, Proposal ve Finalize değerlerinin birbirine yakın olduğuna dikkat edin. Bu da Orta ve Batı bölgelerinde fırsat yüzdesinin daha yüksek olduğu anlamına gelmektedir.

### <a name="page-2-of-our-report-is-titled-revenue-overview"></a>Raporumuzun 2. sayfası "Revenue Overview" olarak adlandırılmıştır.
Bu sayfada veriler benzer şekilde incelenmektedir ancak sayı yerine gelir açısından ele alınmaktadır.  
![](media/sample-opportunity-analysis/opportunity4.png)

* Doğu yalnızca fırsat sayısı değil gelir açısından da en büyük bölgedir.  
* Partner driven (sağ üstteki açıklamada **Yes**'i seçin) ölçütüne göre filtreleme yaptığımızda gelirlerin 1,5 milyar ABD doları ve 294 milyon ABD doları seviyesinde olduğu gösterilmektedir. Bu verileri, iş ortaklarıyla çalışılmadığında 644 milyar ABD doları ve 166 milyon ABD doları seviyesinde olan gelir verileriyle karşılaştırın.  
* Büyük müşterilere ilişkin ortalama gelir, iş ortakları tarafından sağlanan fırsatlarda (8 milyon), iş ortağı harici fırsatlara (6 milyon) kıyasla daha fazladır.  
* İş ortakları tarafından sağlanan işlerde büyük fırsatlar için ortalama gelir, orta çaplı fırsatların (4 milyon) neredeyse iki katıdır.  
* Küçük ve orta çaplı işletmelerin ortalama geliri ise hem iş ortakları tarafından sağlanan hem de sağlanmayan işler için karşılaştırılabilir.   

İş ortaklarımızın müşterilere satış yapma konusunda daha iyi bir iş çıkardığını rahatça söyleyebiliriz.  Anlaşmaları iş ortaklarımız aracılığıyla yapmak daha mantıklı olacaktır.

### <a name="page-3-of-our-report-is-titled-region-stage-counts"></a>Raporumuzun 3. sayfası "Region Stage Counts" olarak adlandırılmıştır.
Bu sayfada benzer veriler bölgeye ve aşamaya göre ayrı ayrı ele alınmaktadır.  
![](media/sample-opportunity-analysis/opportunity5.png)

* Doğu ölçütüne göre filtreleme yaptığımızda (pasta grafiğinde **East**'i seçin) bu bölgedeki fırsatların iş ortaklarının dahil olduğu ve olmadığı alanlarda eşit olduğunu görebiliriz.
* Büyük çaplı fırsatlar en çok merkez bölgesinde, küçük çaplı fırsatlar en çok doğu bölgesinde, orta çaplı fırsatlar ise en çok batı bölgesinde yer almaktadır.

### <a name="page-4-of-our-report-is-titled-upcoming-opportunities"></a>Raporumuzun 4. sayfası "Upcoming Opportunities" olarak adlandırılmıştır.
Burada benzer faktörlere bu kez tarih/saat açısından bakıyoruz.  
![](media/sample-opportunity-analysis/opportunity6.png)

CFO'muz bu sayfayı iş yükünü yönetmek için kullanmaktadır. Satış aşamasına ve aya göre gelir fırsatlarına bakarak uygun planları yapabilir.

* En yüksek ortalama gelir Finalize aşamasına aittir. Bu anlaşmaları sonlandırmak en yüksek önceliğe sahiptir.
* CFO, aya göre filtreleme yaparak (soldaki dilimleyicide ay adını seçerek) Ocak ayının 75 milyon ABD doları gelirle Finalize aşamasında en yüksek büyük fırsat oranına sahip olduğunu görebilir. Diğer taraftan Şubat ayı Solution ve Proposal aşamalarında en fazla orta çaplı fırsata sahiptir.
* Genel olarak, faktöre bağlı gelir rakamları; satış aşamasına, fırsat sayısına ve anlaşma boyutuna göre dalgalanmaktadır. Bu öngörüler hakkında daha fazla bilgiye ulaşmak için filtre ekleyebilirsiniz. Filtrelemek için sağ taraftaki filtre bölmesini kullanabilirsiniz.

Burası keşifler yapabileceğiniz güvenli bir ortamdır. Değişikliklerinizi kaydetmemeyi seçme konusunda her zaman özgürsünüz. Ancak, değişiklikleri kaydederseniz dilediğiniz zaman **Veri Al** bölümüne giderek bu örneğin yeni bir kopyasını edinebilirsiniz.

## <a name="next-steps-connect-to-your-data"></a>Sonraki adımlar: Verilerinize bağlanma
Bu turun Power BI panolarının, Soru-Cevap özelliğinin ve raporların fırsat izleme verileri açısından nasıl öngörü sağlayabileceğini göstermiş olduğunu umuyoruz. Artık siz de kendi verilerinize bağlanarak çalışmaya başlayabilirsiniz. Power BI ile çok çeşitli veri kaynaklarına bağlanabilirsiniz. [Power BI ile çalışmaya başlama](service-get-started.md) hakkında daha fazla bilgi edinin.

[Örnekleri indirin](sample-datasets.md)  
