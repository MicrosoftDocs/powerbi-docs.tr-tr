---
title: Keşfetmek ve görsel oluşturmak için Power BI soru- cevap'ı kullanın
description: Panolarda ve raporlarda yeni görselleştirmeler oluşturmak için Power BI soru- cevap'ı kullanma
author: maggiesMSFT
manager: kfile
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/13/2019
ms.author: maggies
LocalizationGroup: Ask questions of your data
ms.openlocfilehash: c6fd8967a49515af4d0614653b3d7550c335052f
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65625379"
---
# <a name="use-power-bi-qa-to-explore-your-data-and-create-visuals"></a>Verilerinizi keşfetme ve görseller oluşturmak için Power BI soru- cevap'ı kullanın

Bazen verilerinize ilişkin cevaplar edinmenin en hızlı yolu doğal dil kullanarak bir soru sormaktır. Power bı'daki soru- cevap özelliği, kendi kelimelerinizle oluşturarak verilerinizi araştırmanıza olanak sağlar.  Bu makalenin ilk bölümünü, soru- cevap Power BI hizmetinde panolarda kullanma gösterilmektedir. İkinci bölümü, soru- cevap ile Power BI hizmetinde veya Power BI Desktop raporları oluştururken, neler yapabileceğinizi gösterir. Daha fazla arka plan bilgileri için bkz [Tüketiciler için soru- cevap](consumer/end-user-q-and-a.md) makalesi. 

[Soru- cevap Power BI mobil uygulamalarında](consumer/mobile/mobile-apps-ios-qna.md) ve [Power BI Embedded ile soru- cevap](developer/qanda.md) ayrı makalelerde ele alınmıştır. 

Soru- cevap, etkileşimli ve eğlenceli. Genellikle, görselleştirmeler ele Geçiren ilginç yolları ortaya gibi bir soru başkalarına geliyor. Görselleştirme oluşturmak, görselleri ayrıntılı olarak incelemek ve bunları panolara sabitlemek için Soru-Cevap özelliğinin nasıl kullanılacağını gösteren Amanda'yı izleyin.

<iframe width="560" height="315" src="https://www.youtube.com/embed/qMf7OLJfCz8?list=PL1N57mwBHtN0JFoKSR0n-tBkUJHeMP2cP" frameborder="0" allowfullscreen></iframe>

## <a name="part-1-use-qa-on-a-dashboard-in-the-power-bi-service"></a>1. Bölüm: Power BI hizmetinde Panoda soru- cevap'ı kullanın

Power BI hizmetinde (app.powerbi.com) bir Pano herhangi biri, tüm bu veri kümelerinde bulunan veriler hakkında sorular sorabilirsiniz bir veya daha fazla veri kümesinden sabitlenmiş kutucuklar içerir. Hangi raporların ve veri kümeleri panoyu oluşturmak için kullanılan görmek için seçin **ilişkilileri görüntüle** menü çubuğundan.

![İlişkili raporlar ve veri kümelerini görüntüleme](media/power-bi-tutorial-q-and-a/power-bi-view-related.png)

Soru- cevap soru kutusu, doğal dil kullanarak sorunuzu yazdığınız yerdir, panonuzun sol üst köşede bulunur. Cevap kutusunu göremiyor musunuz? Bkz: [önemli noktalar ve sorun giderme](consumer/end-user-q-and-a.md#considerations-and-troubleshooting) içinde **Tüketiciler için soru- cevap** makalesi.  Soru- cevap sözcükleri yazın ve yanıt bulmak için nerede (hangi kümesindeki) kullanıma rakamları tanır. Soru-Cevap ayrıca sorunuzu otomatik tamamlama ve farklı şekilde ifade etme özelliklerinin yanı sıra diğer metin ve görsel desteklerle biçimlendirmenize yardımcı olur.

![Soru- cevap soru kutusu](media/power-bi-tutorial-q-and-a/powerbi-qna.png)

Sorunuzun cevabı etkileşimli görselleştirme olarak görüntülenir ve soruyu değiştirdiğinizde güncelleştirilir.

1. Bir pano açın ve imlecinizi soru kutusuna yerleştirin. Sağ üst köşedeki seçin **yeni cevap deneyiminde**.

    ![Power BI yeni soru- cevap bir deneyim](media/power-bi-tutorial-q-and-a/power-bi-qna-new-experience.png)

1. Soru-Cevap özelliği, yazmaya başlamadan önce sorunuzu oluşturmanıza yardımcı olacak önerilerin bulunduğu yeni bir ekran görüntüler. İfadeler ve temel alınan veri kümelerinden tablolarında adını içeren tam sorular bakın ve veri kümesi sahibi oluşturmuş olması halinde tam sorular bile görebilirsiniz [öne çıkan sorular](service-q-and-a-create-featured-questions.md),

   ![Soru- cevap soruları önerilen](media/power-bi-tutorial-q-and-a/power-bi-qna-suggested-questions.png)

   Bu sorulardan birini başlangıç noktası olarak seçin ve belirli bir yanıt bulmak için soru iyileştirmeye devam edin. Veya yeni soru oluşturmanıza yardımcı olması için tablo adı kullanın.

2. Soruları listesinden seçin veya kendi sorunuzu yazmaya başlayın ve açılan listedeki önerilerden seçin.

   ![Listeden bir soru seçin](media/power-bi-tutorial-q-and-a/power-bi-qna-select-a-question-how-many-stores.png)

3. Bir soru yazarken soru- cevap, yanıtınızı görüntülemek üzere en iyi görselleştirmeyi seçer.

   ![Soru- cevap kaç durumuna göre depolar](media/power-bi-tutorial-q-and-a/power-bi-qna-how-many-stores-by-state.png)

4. Dinamik olarak görselleştirme değişiklikleri ve soruyu değiştirdiğinizde.

   ![Soru- cevap çubuk grafik olarak duruma göre kaç depolar](media/power-bi-tutorial-q-and-a/power-bi-qna-stores-by-state-bar-chart.png)

1. Bir soru yazdığınızda Power BI, ilgili panoda kutucuğu bulunan tüm veri kümelerinde en iyi cevabı arar.  Tüm kutucukların kaynağı *datasetA* ise cevabınız *datasetA* kaynağından gelir.  Kutucukları varsa *datasetA* ve *datasetB*, soru- cevap arar sonra bu 2 veri kümesinden en iyi yanıtı.

   > [!TIP]
   > Bu nedenle dikkatli olmanızda fayda vardır, *datasetA* kaynağından tek bir kutucuğunuz varsa ve bunu panonuzdan kaldırırsanız Soru-Cevap artık *datasetA* erişimine sahip olmaz.
   >

5. Sonuç, bir panoya sağ üst köşedeki Raptiye simgesini seçerek görselleştirmeyi sabitleme memnun olduğunuzda. Sizinle paylaşılmış veya bir uygulamanın parçası olan panoları sabitleyemezsiniz.

   ![Soru- cevap görseli Sabitle](media/power-bi-tutorial-q-and-a/power-bi-qna-pin-visual.png)

## <a name="part-2-use-qa-in-a-report-in-power-bi-service-or-power-bi-desktop"></a>2. Bölüm: Power BI hizmetindeki veya Power BI Desktop'taki bir raporda Soru-Cevap özelliğini kullanma

Soru-Cevap özelliğini kullanarak veri kümenizi keşfetmenin yanı sıra rapor ve panolara görselleştirmeler ekleyebilirsiniz. Bir rapor için tek bir veri kümesi temel alınır. Raporlar tamamen boş olabileceği gibi görselleştirmelerle dolu sayfalar da içerebilir. Bir raporun boş olması, araştırabileceğiniz veri olmadığı anlamına gelmez. Veri kümesi, raporla bağlantılıdır ve bu veri kümesini araştırıp görselleştirmeler oluşturabilirsiniz.  Bir raporun oluşturulması için hangi veri kümesinin kullanıldığını görmek üzere raporu Power BI hizmetinde Okuma görünümü'nde açıp menü çubuğundan **İlişkilileri görüntüle**'yi seçin.

![İlgili veri kümelerini görüntüleme](media/power-bi-tutorial-q-and-a/power-bi-view-related.png)

Soru- cevap raporlarda kullanmak için rapor ve temel alınan veri kümesi için düzenleme izinleri olmalıdır. İçinde [Tüketiciler için soru- cevap](consumer/end-user-q-and-a.md) makalenin diyoruz bu bir *Oluşturucu* senaryo. Bunun yerine, değilseniz *tüketen* sizinle birlikte, soru- cevap paylaşılan bir raporu kullanılamaz.

1. Bir raporu düzenleme görünümü (Power BI hizmeti) veya rapor görünümünde (Power BI Desktop) açın ve seçin **soru** menü çubuğundan.

    **Power BI Desktop**    
    ![Select Power BI Desktop'ta soru sorun](media/power-bi-tutorial-q-and-a/power-bi-desktop-question.png)

    **Hizmet**    
    ![Power BI hizmetinde bir soru seçin](media/power-bi-tutorial-q-and-a/power-bi-service.png)

2. Rapor tuvalinizde bir Soru-Cevap soru kutusu görüntülenir. Aşağıdaki örnekte soru kutusu, başka bir görselleştirmenin üst kısmında görüntülenmektedir. Bunda bir sakınca yoktur ancak soru sormadan önce rapora boş bir sayfa eklemek daha iyi bir seçenek olabilir.

    ![Soru- cevap soru kutusu](media/power-bi-tutorial-q-and-a/power-bi-ask-question.png)

3. İmlecinizi soru kutusuna yerleştirin. Siz sorunuzu yazdıkça Soru-Cevap, sorunuzu oluşturmaya yardımcı olmak üzere bazı öneriler görüntüler.

   ![Soru- cevap soru kutusu içinde yazın](media/power-bi-tutorial-q-and-a/power-bi-q-and-a-suggestions.png)

4. Siz bir soru yazarken Soru-Cevap özelliği, cevabınızı görüntülemek için en iyi [görselleştirmeyi](visuals/power-bi-visualization-types-for-reports-and-q-and-a.md) seçer. Siz soruyu değiştirdikçe görselleştirmeler de dinamik olarak değiştirilir.

   ![Soru- cevap, bir görselleştirme oluşturur](media/power-bi-tutorial-q-and-a/power-bi-q-and-a-visual.png)

5. İstediğiniz görselleştirmeye sahip olduğunuzda ENTER'a basın. Görselleştirmeyi rapora kaydetmek için **Dosya > Kaydet**'i seçin.

6. Yeni görselleştirme ile etkileşim kurun. Görselleştirmeyi nasıl oluşturduğunuz fark etmeksizin aynı etkileşim, biçimlendirme ve özellikleri kullanabilirsiniz.

   ![Görselleştirme ile etkileşim](media/power-bi-tutorial-q-and-a/power-bi-q-and-a-ellipses.png)

   Görselleştirmeyi Power BI hizmetinde oluşturduysanız [bir panoya da sabitleyebilirsiniz](service-dashboard-pin-tile-from-q-and-a.md).

## <a name="tell-qa-which-visualization-to-use"></a>Soru-Cevap özelliğinin hangi görselleştirmeleri kullanacağını belirtme
Soru-Cevap ile verileriniz hakkında bilgi edinmekle kalmaz Power BI'ın cevabı nasıl görüntüleyeceğini de belirtebilirsiniz. Sorunuzun yanına "as a <visualization type>" eklemeniz yeterlidir.  Örneğin "show inventory volume by plant as a map" ve "show total inventory as a card".  Kendiniz deneyin.

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme
- Bir veri kümesine canlı bağlantı veya ağ geçidi ile bağlandıysanız Soru-Cevap özelliğinin [söz konusu veri kümesi için etkinleştirilmesi gerekir](service-q-and-a-direct-query.md).

- Bir raporu açtınız ve Soru-Cevap seçeneğini görmüyorsunuz. Power BI hizmetini kullanıyorsanız raporun Düzenleme görünümü'nde açıldığından emin olun. Bu rapor için düzenleme izinlerine sahip değilseniz ve soru- cevap belirli bir rapor ile kullanabileceğiniz anlamına gelir düzenleme Görünümü'nü açamıyorsanız için.

## <a name="next-steps"></a>Sonraki adımlar

- [Tüketiciler için soru- cevap](consumer/end-user-q-and-a.md)   
- [Soru-Cevap'ta soru sormaya yönelik ipuçları](consumer/end-user-q-and-a-tips.md)   
- [Bir çalışma kitabını Soru-Cevap için hazırlama](service-prepare-data-for-q-and-a.md)  
- [Bir şirket içi veri kümesi için soru- cevap için hazırlama](service-q-and-a-direct-query.md)   
- [Pin a tile to the dashboard from Q&A (Soru-Cevap kutucuklarını panolara sabitleme)](service-dashboard-pin-tile-from-q-and-a.md)
