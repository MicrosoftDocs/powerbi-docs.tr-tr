---
title: 'Öğretici: Power BI hizmetinde içerik oluşturmaya başlama'
description: Power BI çevrimiçi hizmeti (app.powerbi.com) ile çalışmaya başlama
author: maggiesMSFT
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: tutorial
ms.date: 07/02/2020
ms.author: maggies
LocalizationGroup: Get started
ms.openlocfilehash: ee3919be08cfb2af2ad0e82e9f0f35b5d13147c6
ms.sourcegitcommit: 20cfd157af587b3910a2b6deec9518dca4105d71
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/03/2020
ms.locfileid: "85943197"
---
# <a name="tutorial-get-started-creating-in-the-power-bi-service"></a>Öğretici: Power BI hizmetinde içerik oluşturmaya başlama
Bu öğretici, *Power BI hizmetinin* bazı özelliklerine giriş niteliğindedir. Bu öğreticide, verilere bağlanır, bir rapor ve bir pano oluşturur ve verileriniz hakkında sorular sorarsınız. Power BI hizmetinde çok daha fazlasını yapabilirsiniz. Bu öğretici yalnızca başlangıç niteliğindedir. Power BI hizmetinin, diğer Power BI teklifleriyle nasıl bir uyum içinde çalıştığını anlamanız için [Power BI nedir?](power-bi-overview.md) makalesini okumanızı öneririz.

Rapor oluşturucu değil *okuyucu* musunuz? [Power BI hizmetinde dolaşma](../consumer/end-user-experience.md) sayfası sizin için iyi bir başlangıç noktasıdır.

:::image type="content" source="media/service-get-started/power-bi-service-rearranged-dashboard.png" alt-text="Finansal Örnek panosunun ekran görüntüsü.":::

Bu öğreticide aşağıdaki adımları tamamlarsınız:

> [!div class="checklist"]
> * Power BI çevrimiçi hesabınızda oturum açın veya Power BI hesabınız yoksa Power BI hesabına kaydolun.
> * Power BI hizmetini açın.
> * Bazı verileri alın ve rapor görünümünde açın.
> * Bu verileri kullanarak görselleştirmeler oluşturun ve rapor olarak kaydedin.
> * Rapordan kutucukları sabitleyerek bir pano oluşturun.
> * Soru-Cevap doğal dil aracını kullanarak panonuza başka görselleştirmeler ekleyin.
> * Panodaki kutucukları yeniden boyutlandırın, yeniden düzenleyin ve bunların ayrıntılarını düzenleyin.
> * Veri kümesini, raporu ve panoyu silerek kaynakları temizleyin.

## <a name="sign-up-for-the-power-bi-service"></a>Power BI hizmetine kaydolma
Power BI'da içerik oluşturmak için Power BI Pro lisansı gerekir. Bir Power BI hesabınız yoksa, başlamadan önce [ücretsiz Power BI Pro deneme sürümüne kaydolun](https://app.powerbi.com/signupredirect?pbi_source=web).

## <a name="step-1-get-data"></a>1\. Adım: Veri al

Genellikle Power BI bir raporu oluşturmak istediğinizde çalışmaya Power BI Desktop’ta başlarsınız. Power BI Desktop daha fazla özellik sunar. Raporu tasarlamaya başlamadan önce verileri dönüştürebilir, şekillendirebilir ve modelleyebilirsiniz. Ancak bu kez, Power BI hizmetinde bir rapor oluşturmaya sıfırdan başlayacağız.

Bu öğreticide verileri basit bir Microsoft Excel dosyasından alacağız. Birlikte ilerlemek ister misiniz? [Finansal Örnek dosyasını indirin](https://go.microsoft.com/fwlink/?LinkID=521962).

1. Başlamak için Power BI hizmetini (app.powerbi.com) tarayıcınızda açın. 

    Hesabınız yok mu? Endişelenmeyin, [Power BI Pro için ücretsiz denemeye kaydolabilirsiniz](https://app.powerbi.com/signupredirect?pbi_source=web)

1. Gezinti bölmesinde **Çalışma alanım**'ı seçin.

1. **Çalışma alanım**'da **Yeni** > **Karşıya dosya yükle**'yi seçin.

    **Veri Al** sayfası açılır.   

3. **Yeni içerik oluştur** bölümünde **Dosyalar**'ın seçili olduğundan emin olduktan sonra Excel dosyasını kaydettiğiniz konumu seçin.
   
    :::image type="content" source="media/service-get-started/power-bi-service-get-data-local-file.png" alt-text="Yeni içerik oluştur > Dosyalar adımının ekran görüntüsü.":::

5. Bilgisayarınızda dosyanın bulunduğu konuma gidin ve **Aç** düğmesini seçin.

5. Bu öğreticide Excel dosyasını, rapor ve pano oluşturmak için kullanabileceğimiz bir veri kümesi olarak eklemek için **İçeri aktar** seçeneğini belirleyeceğiz. **Karşıya yükle** seçeneğini belirlerseniz Excel çalışma kitabının tamamı Power BI'a yüklenir. Daha sonra çalışma kitabını Excel Online'da açıp düzenleyebilirsiniz.
   
   :::image type="content" source="media/service-get-started/power-bi-import.png" alt-text="İçeri aktar'ı seçme işleminin ekran görüntüsü.":::
6. Veri kümeniz hazır olduğunda Finansal Örnek veri kümenizin yanındaki **Diğer seçenekler (...)** öğesini ve ardından **Rapor oluştur**'u seçin.
1. Rapor düzenleyicisini açın. 

    :::image type="content" source="media/service-get-started/power-bi-service-datasets.png" alt-text="Tüm içerik > Rapor oluştur'u seçme işleminin ekran görüntüsü.":::

    Rapor tuvali boş olur. Sağ tarafta **Filtreler**, **Görsel Öğeler** ve **Alanlar** bölmeleri bulunur.

    :::image type="content" source="media/service-get-started/power-bi-service-blank-report.png" alt-text="Boş rapor tuvalinin ekran görüntüsü.":::

    > [!TIP]
    > Gezinti bölmesini daraltmak için sol üst köşedeki genel gezinti düğmesini seçin. Bu şekilde tuvalinizde daha fazla yer açılır.
    >
    >:::image type="content" source="media/service-get-started/power-bi-global-nav-button.png" alt-text="Genel gezinti düğmesi.":::
    >

7. Şu anda Düzenleme görünümündesiniz. Menü çubuğundaki **Okuma görünümü** seçeneğine dikkat edin. 

    :::image type="content" source="media/service-get-started/power-bi-service-reading-view.png" alt-text="Okuma görünümü seçeneğinin ekran görüntüsü.":::

    Raporun *sahibi* ve *oluşturucusu* olduğunuz için Düzenleme görünümünde raporları değiştirebilirsiniz. Raporunuzu paylaştığınızda iş arkadaşlarınız raporla yalnızca Okuma görünümünde etkileşim kurabilir. Onlar **Çalışma alanım**'daki raporlarınızın *tüketicileri* olur. 

## <a name="step-2-create-a-chart-in-a-report"></a>2\. Adım: Raporda grafik oluşturma
Verilere bağlandığınıza göre keşfetmeye başlayabilirsiniz. İlgi çekici bir şeyler bulduğunuz zaman rapor tuvaline kaydedebilirsiniz. Daha sonra bunu bir panoya sabitleyerek zaman içindeki değişimini izleyebilirsiniz. Ancak bundan önce yapmamız gereken şeyler var.
    
1. Rapor düzenleyicisinde bir görselleştirme oluşturmak için öncelikle sayfanın sağ tarafındaki **Alanlar** bölmesini kullanın. **Brüt Satış** alanını ve ardından **Tarih** alanını seçin.
   
   :::image type="content" source="media/service-get-started/power-bi-service-fields-pane-selected.png" alt-text="Alanlar listesinin ekran görüntüsü.":::

    Power BI, verileri çözümler ve bir sütun grafiği görselleştirmesi oluşturur. 

    > [!NOTE]
    > İlk önce **Brüt Satış** yerine **Tarih** alanını seçtiyseniz bir tablo görürsünüz. Endişelenmeyin! Bir sonraki adımda görselleştirmeyi değiştireceğiz.

    Power BI sayısal değerler içerdiğini algıladığından bazı alanların yanında sigma simgesi bulunur.

    :::image type="content" source="media/service-get-started/power-bi-sigma-fields.png" alt-text="Sigma simgesi bulunan alanlar.":::

2. Şimdi bu verileri farklı bir şekilde görüntüleyelim. Çizgi grafikler, zaman içinde değişen değerleri görüntülemek için iyi görsellerdir. **Görselleştirmeler** bölmesinden **Çizgi grafik** simgesini seçin.
   
   :::image type="content" source="media/service-get-started/power-bi-service-select-line-chart.png" alt-text="Çizgi grafik seçiliyken rapor düzenleyicisinin ekran görüntüsü.":::

3. Bu grafik ilginç görünüyor, bunu bir panoya *sabitleyelim*. Görselleştirmenin üzerine gelin ve raptiye simgesini seçin.
   
   :::image type="content" source="media/service-get-started/power-bi-service-pin-visual.png" alt-text="Raptiye simgesinin ekran görüntüsü.":::

4. Bu rapor yeni olduğundan, görselleştirmeyi panoya sabitleyebilmeniz için öncelikle raporu kaydetmeniz istenir. Raporunuza bir ad verin (örneğin, *Finansal Örnek raporu*) ve **Kaydet**'i seçin. 

    Şimdi raporu, Okuma görünümünde inceliyorsunuz. 

6. **Raptiye** simgesini yeniden seçin.
 
5. **Yeni pano**’yu seçip *Finansal Örnek panosu* gibi bir ad verin. 
   
   :::image type="content" source="media/service-get-started/power-bi-pin.png" alt-text="Panoya ad verme adımının ekran görüntüsü.":::
  
    Sağ üst köşeye yakın bir noktada çıkan Başarılı iletisi, görselleştirmenin bir kutucuk olarak panonuza eklendiğini bildirir.
   
    :::image type="content" source="media/service-get-started/power-bi-pin-success.png" alt-text="Panoya sabitlendi iletişim kutusunun ekran görüntüsü.":::

    Sabitlediğiniz görselleştirme panonuza kaydedilir. Veriler güncel kalır ve bu sayede en son değeri bir bakışta görebilirsiniz. Ancak rapordaki görselleştirme türünü değiştirirseniz panodaki görselleştirme değişmez.

7. **Panoya git**'i seçtiğinizde çizgi grafiğin yeni panonuza kutucuk olarak sabitlendiğini görebilirsiniz. 
   
   :::image type="content" source="media/service-get-started/power-bi-service-dashboard-tile.png" alt-text="Görselleştirmenin sabitlendiği panonun ekran görüntüsü.":::
   
8. Panonuzdaki yeni kutucuğu seçin. Power BI, raporu Okuma görünümü'nde açar.

1. Düzenleme görünümüne geri dönmek için menü çubuğunda **Diğer seçenekler** (...) > **Düzenle**’yi seçin.

    :::image type="content" source="media/service-get-started/power-bi-service-edit-report.png" alt-text="Raporu düzenlemek için Düzenle’yi seçme adımının ekran görüntüsü.":::

    Düzen görünümü'ne döndükten sonra kutucukları keşfetmeye ve sabitlemeye devam edebilirsiniz.

## <a name="step-3-explore-with-qa"></a>3\. Adım: Soru-Cevap ile araştırma

Verilerinizi hızla araştırmak için Soru-Cevap soru kutusunda soru sormayı deneyin. Soru-Cevap, verileriniz hakkında doğal dil sorguları oluşturmanızı sağlar. Bir panoda Soru-Cevap kutusu, menü çubuğunun altında ve en üst kısımdadır (**Verileriniz hakkında soru sorun**). Bir raporda, menü çubuğunda bulunur (**Bir soru sorun**).

1. Panoya geri dönmek için siyah **Power BI** üst bilgi çubuğunda **Çalışma alanım**’ı seçin.

    :::image type="content" source="media/service-get-started/power-bi-service-go-my-workspace.png" alt-text="Çalışma alanım bölümüne geri dönme işleminin ekran görüntüsü.":::

1. **Çalışma alanım**'da panonuzu seçin.

    :::image type="content" source="media/service-get-started/power-bi-service-dashboard-tab.png" alt-text="Panonuzu seçme işleminin ekran görüntüsü.":::

1. **Verilerinizle ilgili bir soru sorun**’u seçin. Soru-Cevap, otomatik olarak bir dizi öneri sunar. 

    :::image type="content" source="media/service-get-started/power-bi-service-new-qanda.png" alt-text="Soru-Cevap tuvalinin ekran görüntüsü.":::

    > [!NOTE]
    > Önerileri görmüyorsanız **Yeni Soru-Cevap deneyimini** açın.

    :::image type="content" source="media/service-get-started/power-bi-new-qna-experience.png" alt-text="Yeni Soru-Cevap deneyimini açma işleminin ekran görüntüsü.":::

1. Bazı öneriler tek bir değer döndürür. Örneğin **ortalama satılan malların maliyeti nedir**'i seçin.

    Soru-Cevap yanıt arar ve *kart* görselleştirmesi biçiminde sunar.

3. **Görseli sabitle**'yi seçip bu görselleştirmeyi Finansal Örnek panosuna sabitleyin.

    :::image type="content" source="media/service-get-started/power-bi-qna-pin-tile.png" alt-text="Görseli sabitleme işleminin ekran görüntüsü.":::

1. Soru-Cevap sayfasına dönüp **Tüm önerileri göster**'i seçin.
1. **Ülkeye göre toplam kar**'ı seçin. 

    :::image type="content" source="media/service-get-started/power-bi-qna-total-profit-country.png" alt-text="Ülkeye göre toplam kar'ın ekran görüntüsü.":::

1. Haritayı da Finansal Örnek panosuna sabitleyin.

1. Panoda az önce sabitlediğiniz haritayı seçin. Yeniden Soru-Cevap açılır. 
1. İmleci Soru-Cevap kutusunda *ülkeye göre* ifadesinin sonuna yerleştirin ve *çubuk olarak* yazın. Power BI sonuçları içeren bir çubuk grafik oluşturur.

    :::image type="content" source="media/service-get-started/power-bi-qna-profit-country-bar.png" alt-text="Çubuk grafik görselleştirmesinin ekran görüntüsü.":::

1. Çubuk grafiği de Finansal Örnek panonuza sabitleyin.

4. Oluşturduğunuz yeni kutucukları göreceğiniz panonuza geri dönmek için **Soru-Cevap'tan çık** seçeneğini belirleyin. 

   :::image type="content" source="media/service-get-started/power-bi-service-dashboard-qna.png" alt-text="Soru-Cevap görselleştirmelerinin sabitlendiği panonun ekran görüntüsü.":::

   Soru-Cevap bölümünde haritayı çubuk grafik olarak değiştirdiğiniz halde, sabitlediğiniz sırada bir harita olduğu için kutucuğun bir harita olarak kaldığını görürsünüz. 

## <a name="step-4-reposition-tiles"></a>4\. Adım: Kutucukları yeniden konumlandırma

Pano alanını daha iyi kullanmak için kutucukları yeniden düzenleyebiliriz.

1. *Gross Sales* çizgi grafik kutucuğunun sağ alt köşesini, Sales kutucuğu ile aynı yüksekliğe gelene kadar yukarı doğru sürükleyip bırakın.

    :::image type="content" source="media/service-get-started/power-bi-service-resize-tile.png" alt-text="Kutucuğu yeniden boyutlandırma işleminin ekran görüntüsü.":::

    Artık iki kutucuk aynı yükseklikte.

1. SMM Ortalaması kutucuğunda **Diğer seçenekler (...)** > **Ayrıntıları düzenle**'yi seçin. 

    :::image type="content" source="media/service-get-started/power-bi-tile-edit-details.png" alt-text="Kutucuğa ait Diğer seçenekler menüsünün ekran görüntüsü.":::

1. **Başlık** kutusuna *Satılan Ürünlerin Ortalama Maliyeti* yazıp **Uygula**'yı seçin.

    :::image type="content" source="media/service-get-started/power-bi-tile-details-dialog.png" alt-text="Ayrıntıları düzenle iletişim kutusunun ekran görüntüsü.":::

1. Diğer görselleri sığacak şekilde yeniden düzenleyin.

    Şimdi daha iyi görünüyor.

    :::image type="content" source="media/service-get-started/power-bi-service-rearranged-dashboard.png" alt-text="Yeniden düzenlenmiş panonun ekran görüntüsü.":::


## <a name="clean-up-resources"></a>Kaynakları temizleme
Öğreticiyi bitirdiğinize göre şimdi veri kümesini, raporu ve panoyu silebilirsiniz. 

1. Siyah **Power BI** üst bilgi çubuğunda **Çalışma alanım**’ı seçin.
2. Finansal Örnek veri kümesinin yanındaki **Diğer seçenekler (...)** > **Sil**'i seçin.

    :::image type="content" source="media/service-get-started/power-bi-service-delete-dataset.png" alt-text="Veri kümesini silme işleminin ekran görüntüsü.":::

    **Bu veri kümesine ilişkin verilerin bulunduğu tüm raporlar ve pano kutucukları da silinir** uyarısını görürsünüz.

4. **Sil**’i seçin.

## <a name="next-steps"></a>Sonraki adımlar

Daha fazla görselleştirme kutucuğu ekleyip [kutucukları yeniden adlandırma, yeniden boyutlandırma, bağlantılı hale getirme ve yeniden konumlandırma](../create-reports/service-dashboard-edit-tile.md) yoluyla panoları iyileştirin.
