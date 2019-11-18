---
title: Power BI Soru-Cevap ile görselleri keşfetme ve oluşturma
description: Pano ve raporlarda yeni görselleştirmeler oluşturmak için Power BI Soru-Cevap özelliğinin nasıl kullanılacağını öğrenin.
author: maggiesMSFT
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/13/2019
ms.author: maggies
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: 183ce11457069612f84bb834d7060a047cae1866
ms.sourcegitcommit: 64c860fcbf2969bf089cec358331a1fc1e0d39a8
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2019
ms.locfileid: "73875081"
---
# <a name="use-power-bi-qa-to-explore-your-data-and-create-visuals"></a>Power BI Soru-Cevap ile verilerinizi keşfetme ve görseller oluşturma

Bazen verilerinize ilişkin cevaplar edinmenin en hızlı yolu doğal dil kullanarak bir soru sormaktır. Power BI'ın Soru-Cevap özelliği, verilerinizi kendi sözcüklerinizi kullanarak keşfetmenizi sağlar.  Bu makalenin ilk bölümünde, Soru-Cevap özelliğini Power BI hizmetindeki panolarda nasıl kullanacağınız gösterilmektedir. İkinci bölümde ise Power BI hizmeti veya Power BI Desktop ile rapor oluştururken Soru-Cevap ile yapabilecekleriniz anlatılmaktadır. Daha fazla arka plan bilgisine [Tüketiciler için Soru-Cevap](consumer/end-user-q-and-a.md) makalesinden ulaşabilirsiniz. 

[Power BI mobil uygulamalarında Soru-Cevap](consumer/mobile/mobile-apps-ios-qna.md) ve [Power BI Embedded’da Soru-Cevap](developer/qanda.md) konuları ayrı makalelerde ele alınmıştır. 

Soru-Cevap etkileşimli ve hatta eğlenceli bir özelliktir. Genellikle görselleştirmelerin sürdürülebilecek ilginç yollar açması nedeniyle her soru yeni bir soruyu getirir. Görselleştirme oluşturmak, görselleri ayrıntılı olarak incelemek ve bunları panolara sabitlemek için Soru-Cevap özelliğinin nasıl kullanılacağını gösteren Amanda'yı izleyin.

<iframe width="560" height="315" src="https://www.youtube.com/embed/qMf7OLJfCz8?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

## <a name="part-1-use-qa-on-a-dashboard-in-the-power-bi-service"></a>1\. Bölüm: Power BI hizmetindeki bir panoda Soru-Cevap özelliğini kullanma

Power BI hizmetinde (app.powerbi.com) panolar, bir veya daha fazla veri kümesinden sabitlenmiş kutucuklar içerir. Bu nedenle, bu veri kümelerinde bulunan tüm verilerle ilgili sorular sorabilirsiniz. Panonun oluşturulması için hangi raporların ve veri kümelerinin kullanıldığını görmek üzere menü çubuğundan **İlişkilileri görüntüle**'yi seçin.

![İlgili raporları ve veri kümelerini görüntüleme](media/power-bi-tutorial-q-and-a/power-bi-view-related.png)

Soru-Cevap soru kutusu, panonuzun sol üst köşesinde bulunur. Burası, doğal dil kullanarak sorunuzu yazdığınız yerdir. Soru-Cevap kutusunu görmüyor musunuz? **Tüketiciler için Soru-Cevap** makalesinin [Önemli noktalar ve sorun giderme](consumer/end-user-q-and-a.md#considerations-and-troubleshooting) bölümünü inceleyin.  Soru-Cevap, yazdığınız kelimeleri tanıyarak cevabı nerede (hangi veri kümesinde) bulabileceğini belirler. Soru-Cevap ayrıca sorunuzu otomatik tamamlama ve farklı şekilde ifade etme özelliklerinin yanı sıra diğer metin ve görsel desteklerle biçimlendirmenize yardımcı olur.

![Soru-Cevap soru kutusu](media/power-bi-tutorial-q-and-a/powerbi-qna.png)

Sorunuzun cevabı etkileşimli görselleştirme olarak görüntülenir ve soruyu değiştirdiğinizde güncelleştirilir.

1. Bir pano açın ve imlecinizi soru kutusuna yerleştirin. Sağ üst köşeden **Yeni Soru-Cevap deneyimi**'ni seçin.

    ![Power BI Yeni Soru-Cevap deneyimi](media/power-bi-tutorial-q-and-a/power-bi-qna-new-experience.png)

1. Soru-Cevap özelliği, yazmaya başlamadan önce sorunuzu oluşturmanıza yardımcı olacak önerilerin bulunduğu yeni bir ekran görüntüler. Temel alınan veri kümelerindeki tabloların adlarını içeren ifadelerin ve tamamlanmış soruların yanı sıra veri kümesi sahibinin [öne çıkan sorular](service-q-and-a-create-featured-questions.md) oluşturmuş olması halinde soruların tamamlanmış hallerini bile görebilirsiniz.

   ![Soru-Cevap özelliğindeki önerilen sorular](media/power-bi-tutorial-q-and-a/power-bi-qna-suggested-questions.png)

   Bu sorulardan birini başlangıç noktası olarak kullanabilir, soruyu değiştirerek belirli bir yanıta ulaşabilirsiniz. İsterseniz yeni soru oluşturmanıza yardımcı olması için tablo adı yazabilirsiniz.

2. Soru listesinden seçim yapın veya kendi sorunuzu yazmaya başlayıp açılan listedeki önerilerden birini seçin.

   ![Listeden bir soru seçin](media/power-bi-tutorial-q-and-a/power-bi-qna-select-a-question-how-many-stores.png)

3. Sorunuzu yazmaya başladığınızda, Soru-Cevap özelliği yanıtınızı görüntülemek için en uygun görselleştirmeyi seçer.

   ![Soru-Cevap eyalete göre mağaza sayısı](media/power-bi-tutorial-q-and-a/power-bi-qna-how-many-stores-by-state.png)

4. Soruyu değiştirdiğinizde görselleştirme de dinamik olarak değişir.

   ![Soru-Cevap eyalete göre mağaza sayısı çubuk grafiği](media/power-bi-tutorial-q-and-a/power-bi-qna-stores-by-state-bar-chart.png)

1. Bir soru yazdığınızda Power BI, ilgili panoda kutucuğu bulunan tüm veri kümelerinde en iyi cevabı arar.  Tüm kutucukların kaynağı *datasetA* ise cevabınız *datasetA* kaynağından gelir.  Hem *datasetA* hem de *datasetB* varsa Soru-Cevap, bu 2 veri kümesinden en iyi cevabı almak için arama yapar.

   > [!TIP]
   > Bu nedenle dikkatli olmanızda fayda vardır, *datasetA* kaynağından tek bir kutucuğunuz varsa ve bunu panonuzdan kaldırırsanız Soru-Cevap artık *datasetA* erişimine sahip olmaz.
   >

5. Sonuç içinize sindiğinde sağ üst köşedeki raptiye simgesini seçerek görselleştirmeyi panoya sabitleyebilirsiniz. Sizinle paylaşılmış veya bir uygulamanın parçası olan panoları sabitleyemezsiniz.

   ![Soru-Cevap Görseli sabitleme](media/power-bi-tutorial-q-and-a/power-bi-qna-pin-visual.png)

## <a name="part-2-use-qa-in-a-report-in-power-bi-service-or-power-bi-desktop"></a>2\. Bölüm: Power BI hizmetindeki veya Power BI Desktop'taki bir raporda Soru-Cevap özelliğini kullanma

Soru-Cevap özelliğini kullanarak veri kümenizi keşfetmenin yanı sıra rapor ve panolara görselleştirmeler ekleyebilirsiniz. Bir rapor için tek bir veri kümesi temel alınır. Raporlar tamamen boş olabileceği gibi görselleştirmelerle dolu sayfalar da içerebilir. Bir raporun boş olması, araştırabileceğiniz veri olmadığı anlamına gelmez. Veri kümesi, raporla bağlantılıdır ve bu veri kümesini araştırıp görselleştirmeler oluşturabilirsiniz.  Bir raporun oluşturulması için hangi veri kümesinin kullanıldığını görmek üzere raporu Power BI hizmetinde Okuma görünümü'nde açıp menü çubuğundan **İlişkilileri görüntüle**'yi seçin.

![İlgili veri kümelerini görüntüle](media/power-bi-tutorial-q-and-a/power-bi-view-related.png)

Raporlarda Soru-Cevap özelliğini kullanabilmeniz için söz konusu rapora ve temel alınan veri kümesine ilişkin düzenleme izinlerine sahip olmanız gerekir. [Tüketiciler için Soru-Cevap](consumer/end-user-q-and-a.md) makalesinde bu bir *oluşturan* senaryosu olarak adlandırılmıştır. Bunun yerine sizinle paylaşılan bir raporu *tüketiyorsanız* Soru-Cevap özelliğini kullanamazsınız.

1. Bir raporu Düzenleme görünümü'nde (Power BI hizmeti) veya Rapor görünümü'nde (Power BI Desktop) açın ve menü çubuğundan **Soru sorun**'u seçin.

    **Power BI Desktop**    
    ![Power BI Desktop'ta Soru sorun'u seçin](media/power-bi-tutorial-q-and-a/power-bi-desktop-question.png)

    **Hizmet**    
    ![Power BI hizmetinse Soru sorun'u seçin](media/power-bi-tutorial-q-and-a/power-bi-service.png)

2. Rapor tuvalinizde bir Soru-Cevap soru kutusu görüntülenir. Aşağıdaki örnekte soru kutusu, başka bir görselleştirmenin üst kısmında görüntülenmektedir. Bunda bir sakınca yoktur ancak soru sormadan önce rapora boş bir sayfa eklemek daha iyi bir seçenek olabilir.

    ![Soru-Cevap soru kutusu](media/power-bi-tutorial-q-and-a/power-bi-ask-question.png)

3. İmlecinizi soru kutusuna yerleştirin. Siz sorunuzu yazdıkça Soru-Cevap, sorunuzu oluşturmaya yardımcı olmak üzere bazı öneriler görüntüler.

   ![Soru-Cevap soru kutusuna yazın](media/power-bi-tutorial-q-and-a/power-bi-q-and-a-suggestions.png)

4. Siz bir soru yazarken Soru-Cevap özelliği, cevabınızı görüntülemek için en iyi [görselleştirmeyi](visuals/power-bi-visualization-types-for-reports-and-q-and-a.md) seçer. Siz soruyu değiştirdikçe görselleştirmeler de dinamik olarak değiştirilir.

   ![Soru-Cevap bir görselleştirme oluşturur](media/power-bi-tutorial-q-and-a/power-bi-q-and-a-visual.png)

5. İstediğiniz görselleştirmeye sahip olduğunuzda ENTER'a basın. Görselleştirmeyi rapora kaydetmek için **Dosya > Kaydet**'i seçin.

6. Yeni görselleştirme ile etkileşim kurun. Görselleştirmeyi nasıl oluşturduğunuz fark etmeksizin aynı etkileşim, biçimlendirme ve özellikleri kullanabilirsiniz.

   ![Görselleştirme ile etkileşim kurun](media/power-bi-tutorial-q-and-a/power-bi-q-and-a-ellipses.png)

   Görselleştirmeyi Power BI hizmetinde oluşturduysanız [bir panoya da sabitleyebilirsiniz](service-dashboard-pin-tile-from-q-and-a.md).

## <a name="tell-qa-which-visualization-to-use"></a>Soru-Cevap özelliğinin hangi görselleştirmeleri kullanacağını belirtme
Soru-Cevap ile verileriniz hakkında bilgi edinmekle kalmaz Power BI'ın cevabı nasıl görüntüleyeceğini de belirtebilirsiniz. Sorunuzun yanına "as a <visualization type>" eklemeniz yeterlidir.  Örneğin "show inventory volume by plant as a map" ve "show total inventory as a card".  Kendiniz deneyin.

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme
- Bir veri kümesine canlı bağlantı veya ağ geçidi ile bağlandıysanız Soru-Cevap özelliğinin [söz konusu veri kümesi için etkinleştirilmesi gerekir](service-q-and-a-direct-query.md).

- Bir raporu açtınız ve Soru-Cevap seçeneğini görmüyorsunuz. Power BI hizmetini kullanıyorsanız raporun Düzenleme görünümü'nde açıldığından emin olun. Düzenleme görünümü'nü açamıyorsanız bu, söz konusu rapor için düzenleme izinlerine sahip olmadığınız ve bu raporla Soru-Cevap özelliğini kullanabileceğiniz anlamına gelir.

## <a name="next-steps"></a>Sonraki adımlar

- [Tüketiciler için Soru-Cevap](consumer/end-user-q-and-a.md)   
- [Soru-Cevap'ta soru sormaya yönelik ipuçları](consumer/end-user-q-and-a-tips.md)   
- [Bir çalışma kitabını Soru-Cevap için hazırlama](service-prepare-data-for-q-and-a.md)  
- [Şirket içi veri kümesini Soru-Cevap için hazırlama](service-q-and-a-direct-query.md)   
- [Pin a tile to the dashboard from Q&A (Soru-Cevap kutucuklarını panolara sabitleme)](service-dashboard-pin-tile-from-q-and-a.md)
