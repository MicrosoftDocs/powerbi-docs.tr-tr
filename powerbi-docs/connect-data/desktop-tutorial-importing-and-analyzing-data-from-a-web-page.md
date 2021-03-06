---
title: 'Öğretici: Web sayfasından verileri içeri aktarma ve analiz etme'
description: 'Öğretici: Power BI Desktop kullanarak bir web sayfasından verileri içeri aktarma ve çözümleme'
author: davidiseminger
ms.author: davidi
ms.reviewer: ''
ms.custom: seodec18
ms.service: powerbi
ms.subservice: pbi-data-sources
ms.topic: tutorial
ms.date: 01/13/2020
LocalizationGroup: Learn more
ms.openlocfilehash: d407da8e11473180f21e62c94f0ab440050beedc
ms.sourcegitcommit: 653e18d7041d3dd1cf7a38010372366975a98eae
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96404836"
---
# <a name="tutorial-analyze-webpage-data-by-using-power-bi-desktop"></a>Öğretici: Power BI Desktop kullanarak web sayfası verilerini analiz etme

Uzun süreli bir futbol sever olarak, yıllara göre UEFA Avrupa Kupası (Euro Cup) sahipleri ile ilgili rapor oluşturmak istiyorsunuz. Power BI Desktop sayesinde bu verileri bir web sayfasından rapora aktarabilir ve verileri gösteren görselleştirmeler oluşturabilirsiniz. Bu öğreticide, Power BI Desktop kullanarak aşağıdakileri yapmayı öğreneceksiniz:

- Bir web veri kaynağına bağlanma ve tüm kullanılabilir tablolarda gezinme.
- Power Query Düzenleyicisi’nde verileri şekillendirme ve dönüştürme.
- Sorguyu adlandırma ve bir Power BI Desktop raporuna aktarma.
- Bir harita ve pasta grafiği görselleştirmesi oluşturma ve özelleştirme.

## <a name="connect-to-a-web-data-source"></a>Bir web veri kaynağına bağlanma

UEFA kupası sahiplerine ait verileri, https://en.wikipedia.org/wiki/UEFA_European_Football_Championship adresindeki UEFA Avrupa Futbol Şampiyonası Wikipedia sayfasında bulunan Sonuçlar tablosundan alabilirsiniz. 

![Wikipedia Sonuçlar tablosu](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage1.png)

Web bağlantıları yalnızca temel kimlik doğrulaması kullanılarak kurulur. Kimlik doğrulaması gerektiren web siteleri, Web bağlayıcısı ile düzgün çalışmayabilir.

Verileri içeri aktarmak için:

1. Power BI Desktop **Giriş** şerit sekmesinde, **Veri Al** seçeneğinin yanındaki oku açın ve sonra **Web**’i seçin.

   ![Şeritten Veri Al](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web3.png) 

   >[!NOTE]
   >Ayrıca **Veri Al** öğesini seçebilir ya da Power BI Desktop kullanmaya başlama iletişim kutusundan **Veri Al**’ı seçtikten sonra **Veri Al** iletişim kutusundaki **Tümü** veya **Diğer** bölümünden **Web**’i ve sonra **Bağlan**’ı seçebilirsiniz.

1. **Web’den** iletişim kutusunda `https://en.wikipedia.org/wiki/UEFA_European_Football_Championship` URL’sini **URL** metin kutusuna yapıştırın ve sonra **Tamam**’ı seçin.

    ![İletişim kutusundan Veri Al](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web2.png)

   Wikipedia web sayfasına bağlandıktan sonra **Gezgin** iletişim kutusunda sayfadaki kullanılabilir tabloların listesi gösterilir. Verilerin önizlemesini görmek için tablo adlarından herhangi birini seçebilirsiniz. **Sonuçlar[düzenle]** tablosunda istediğiniz veriler bulunur ancak bu veriler tam olarak istediğiniz şekilde değildir. Verileri raporunuza yüklemeden önce yeniden şekillendirir ve temizlersiniz.

   ![Gezgin iletişim kutusu](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/tutorialimanaly_navigator.png)

   >[!NOTE]
   >**Önizleme** bölmesinde seçilen en son tablo gösterilir ama **Veri Dönüştürme**’yi veya **Yükle**’yi seçtiğinizde tüm seçili tablolar Power Query Düzenleyicisi’ne yüklenir.

1. **Gezgin** listesinde **Sonuçlar[düzenle]** tablosunu ve ardından **Veri Dönüştürme**’yi seçin.

   **Power Query Düzenleyicisi**’nde tablonun önizlemesi açılır. Burada verileri temizlemek için dönüşümler uygulayabilirsiniz.

   ![Power Query Düzenleyicisi](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage3.png)

## <a name="shape-data-in-power-query-editor"></a>Power Query Editor’da verileri şekillendirme

Yalnızca yılları ve kazanan ülkeleri görüntüleyerek verilerin taranmasını kolaylaştırmak istiyorsunuz. Bu veri şekillendirme ve temizleme adımlarını gerçekleştirmek için Power Query Düzenleyicisi’ni kullanabilirsiniz.

İlk olarak tablodan ikisi dışında tüm sütunları kaldırın. Daha sonraki işlemler sırasında bu sütunları *Year* (Yıl) ve *Country* (Ülke) olarak adlandırın.

1. **Power Query Düzenleyicisi** kılavuzunda sütunları seçin. Birden fazla öğe seçmek için Ctrl tuşunu kullanın.

1. Tablodan diğer tüm sütunları kaldırmak için, sağ tıklayıp **Diğer Sütunları Kaldır**’ı veya **Giriş** şerit sekmesindeki **Sütunları Yönet** grubundan **Sütunları Kaldır** > **Diğer Sütunları Kaldır**’ı seçin.

   ![Diğer sütunları kaldır açılır menüsü](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web6.png)

   veya

   ![Diğer sütunları kaldır şeridi](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage4.png)

Ardından, ilk sütun hücrelerindeki fazladan *Details* sözcüğünü kaldırın.

1. İlk sütunu seçin.

1. Sağ tıklayın ve **Değerleri Değiştir**’i seçin veya şeritte **Giriş** sekmesinin **Dönüştürme** grubundaki **Değerleri Değiştir**’i seçin. Bu seçenek **Dönüştürme** sekmesinin **Herhangi Bir Sütun** grubunda da bulunabilir.

   ![Değerleri Değiştir açılır menüsü](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web7.png) 

   veya

   ![Değerleri Değiştir şeridi](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web8a.png)

1. **Değerleri Değiştir** iletişim kutusundaki **Bulunacak Değer** metin kutusuna **Details** yazın, **Şununla Değiştir** metin kutusunu boş bırakın ve sonra **Tamam**’ı seçerek bu sütundan *Details* sözcüğünü silin.

   ![Sütundan bir sözcüğü kaldırma](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage6.png)

Bazı hücreler yıl değerleri yerine yalnızca "Year" sözcüğünü içerir. Sütunu yalnızca "Year" sözcüğünü içermeyen satırları gösterecek şekilde filtreleyebilirsiniz.

1. Sütundaki filtre açılır okunu seçin.

1. Açılan menüyü aşağı kaydırın, **Year** seçeneğinin yanındaki onay kutusunu temizleyin ve **Tamam**’ı seçin.

   ![Verileri filtreleme](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage7.png)

Şu anda yalnızca kazananların verilerini görüyor olduğunuz için, ikinci sütunu **Country** olarak yeniden adlandırabilirsiniz. Sütunu yeniden adlandırmak için:

1. İkinci sütun başlığına çift tıklayın veya dokunup basılı tutun ya da
   - Sütun başlığına sağ tıklayın ve **Yeniden Adlandır**’ı seçin ya da
   - *Sütunu seçin ve ardından şeritte **Dönüşüm** sekmesinin **Herhangi Bir Sütun** grubundan **Yeniden Adlandır**’ı seçin.

   ![Yeniden Adlandır açılan menüsü](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage7a.png) 
  
   veya

   ![Yeniden adlandır şeridi](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web8.png)

1. Sütunu yeniden adlandırmak için üst bilgiye **Country** yazın ve **Enter** tuşuna basın.

Ayrıca, **Country** sütununda null değerleri olan "2020" gibi sütunları filtrelemek istiyorsunuz. **Year** değerlerinde yaptığınız gibi filtre menüsünü kullanabilir veya şunları yapabilirsiniz:

1. Değeri *null* olan **2020** satırında **Country** hücresine sağ tıklayın.

1. Bağlam menüsünden **Metin Filtreleri** > **Eşit Değil**’i seçerek hücrenin değerini içeren satırları kaldırın.

   ![Metin filtresi](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web11.png)

## <a name="import-the-query-into-report-view"></a>Sorguyu Rapor Görünümüne aktarma

Verileri istediğiniz gibi şekillendirdikten sonra sorgunuzu "Euro Cup Winners" olarak adlandırıp raporunuza aktarabilirsiniz.

1. **Sorgu Ayarları** bölmesindeki **Ad** metin kutusuna **Euro Cup Winners** yazın.

   ![Sorguyu adlandırma](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage8.png)

1. Şeridin **Giriş** sekmesinden **Kapat ve Uygula** > **Kapat ve Uygula** öğesini seçin.

   ![Kapat ve Uygula](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage9.png)

Sorgu, Power BI Desktop *Rapor* görünümüne yüklenir ve bunu **Alanlar** bölmesinde görebilirsiniz.

   ![Alanlar Bölmesi](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage11.png)

>[!TIP]
>Sorgunuzu düzenlemek ve daraltmak için aşağıdakileri yaparak dilediğiniz zaman Power Query Düzenleyicisi’ne geri dönebilirsiniz:
>- **Alanlar** bölmesindeki **Euro Cup Winners** öğesinin yanında bulunan **Diğer seçenekler** üç nokta simgesini ( **...** ) ve **Sorguyu Düzenle**’yi seçin ya da
>- Rapor görünümünde **Giriş** şerit sekmesinin **Harici veriler** grubundaki **Sorguları Düzenle** > **Sorguları Düzenle** öğesini seçin. 

## <a name="create-a-visualization"></a>Görselleştirme oluşturma

Verilerinizi temel alan bir görselleştirme oluşturmak için:

1. **Alanlar** bölmesinden **Ülke** alanını seçin veya rapor tuvaline sürükleyin. Power BI Desktop, verileri ülke adları olarak tanır ve otomatik olarak bir **Harita** görselleştirmesi oluşturur.

   ![Harita görselleştirmesi](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web14.png)

1. Köşelerdeki tanıtıcıları tüm kazanan ülke adları görünür olacak şekilde sürükleyerek haritayı genişletin.  

   ![Haritayı genişletme](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage14.png)

1. Haritada, bir Avrupa Kupası turnuvasını kazanmış her ülke için türdeş veri noktaları gösterilir. Her bir veri noktasının boyutunu ülkenin ne sıklıkta kazandığını yansıtacak şekilde değiştirmek için, **Yıl** alanını **Görselleştirmeler** bölmesinin alt kısmında bulunan **Boyut** altında **Veri alanlarını buraya sürükleyin** alanına sürükleyin. Alan otomatik olarak **Yıl Sayısı** ölçümüne dönüşür ve harita görselleştirmesinde daha fazla turnuva kazanmış ülkeler için daha büyük veri noktaları gösterilir.

   ![Yıl Sayısı’nı Boyut’a sürükleme](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage15.png)

## <a name="customize-the-visualization"></a>Görselleştirmeyi özelleştirme

Sizin de görebildiğiniz gibi, verilerinizi temel alarak görselleştirmeler oluşturmak son derece kolaydır. Ayrıca, görselleştirmelerinizi, verilerinizi istediğiniz yöntemlerle daha iyi şekilde sunmak üzere özelleştirmek de kolaydır.

### <a name="format-the-map"></a>Haritayı biçimlendirme

Görselleştirmeyi ve ardından **Görselleştirmeler** bölmesindeki **Biçim** (boya fırçası) simgesini seçerek görselleştirmenin görünümünü değiştirebilirsiniz. Örneğin, Batı Almanya iki, Almanya ise bir turnuva kazandığı için ve harita iki noktayı ayırmak veya birbirine eklemek yerine üst üste getirdiğinden, görselleştirmenizdeki "Almanya" veri noktaları yanıltıcı olabilir. Bu olguyu vurgulamak için bu iki noktayı farklı şekillerde renklendirebilirsiniz. Ayrıca, haritaya daha açıklayıcı ve çekici bir başlık verebilirsiniz.

1. Görselleştirme seçiliyken, **Biçim** simgesini ve sonra **Veri renkleri**’ni seçerek veri rengi seçeneklerini genişletin.

   ![Biçim simgesi ve Veri renkleri seçimi](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web15.png)

1. **Tümünü göster** seçeneğini **Açık** duruma getirin ve ardından **Batı Almanya**’nın yanındaki açılır menüyü ve sarı rengi seçin.

   ![Renk değiştirme](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web16.png)

1. Başlık seçeneklerini genişletmek için **Başlık** öğesini seçin ve **Başlık metni** alanında mevcut başlığın yerine **Euro Cup Winners** yazın.

1. **Yazı tipi rengi**’ni kırmızı, **Metin boyutu**’nu **12** ve **Yazı tipi ailesi**’ni **Segoe (Kalın)** olarak değiştirin.

   ![Yazı tipi rengi, boyutu ve ailesi](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web17.png)

Harita görselleştirmeniz şu şekilde görünür:

![Biçimlendirilmiş harita görselleştirmesi](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web18.png)

### <a name="change-the-visualization-type"></a>Görselleştirme türünü değiştirme

Bir görselleştirmeyi ve sonra **Görselleştirmeler** bölmesinin üst kısmından farklı bir simgeyi seçerek görselleştirme türünü değiştirebilirsiniz. Örneğin, Sovyetler Birliği ve Çekoslovakya ülkeleri dünya haritasında artık mevcut olmadığı için harita görselleştirmenizde bu ülkelerin verileri eksik olabilir. Ağaç haritası veya pasta grafiği gibi başka bir görselleştirme türü tüm değerleri gösterdiği için daha doğru olabilir.

Haritayı bir pasta grafiği ile değiştirmek için haritayı ve sonra **Görselleştirmeler** bölmesindeki **Pasta grafiği** öğesini seçin.

![Görselleştirmeyi pasta grafiğine dönüştürme](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/get-data-web19.png)

>[!TIP]
>- "Almanya" ve "Batı Almanya"’yı aynı renk yapmak için **Veri renkleri** biçimlendirme seçeneklerini kullanabilirsiniz. 
>- Pasta grafiğinde en fazla kazanan ülkeleri bir arada gruplandırmak için, görselleştirmenin sağ üst kısmındaki üç noktayı ( **...** ) ve sonra da **Yıl Sayısına Göre Sırala**’yı seçin.

Power BI Desktop, birçok farklı veri kaynağından veri almanın ve çözümleme ihtiyaçlarınızı karşılayacak şekilde biçimlendirmeye ek olarak bu verileri zengin ve etkileşimli bir şekilde görselleştirmeye kadar sorunsuz ve uçtan uca bir deneyim sunar. Rapor hazır hale geldikten sonra [Power BI'a yükleyip](../create-reports/desktop-upload-desktop-files.md) bunu kullanan panolar oluşturabilir ve diğer Power BI kullanıcılarıyla paylaşabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

* [Power BI için Microsoft Learn](/learn/powerplatform/power-bi?WT.mc_id=powerbi_landingpage-docs-link)
* [Power BI Desktop videolarını izleyin](../fundamentals/desktop-videos.md)
* [Power BI Forumu'nu ziyaret edin](https://go.microsoft.com/fwlink/?LinkID=519326)
* [Power BI Blogu'nu okuyun](https://go.microsoft.com/fwlink/?LinkID=519327)