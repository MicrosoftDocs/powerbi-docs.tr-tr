---
title: "Eğitim: Power BI Desktop ile Facebook analizi"
description: "Eğitim: Power BI Desktop ile Facebook analizi"
services: powerbi
documentationcenter: 
author: davidiseminger
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
ms.date: 12/06/2017
ms.author: davidi
LocalizationGroup: Learn more
ms.openlocfilehash: e0bdec7d2774fd5c6641041af14b2170d7223151
ms.sourcegitcommit: 88c8ba8dee4384ea7bff5cedcad67fce784d92b0
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/24/2018
---
# <a name="tutorial-facebook-analytics-using-power-bi-desktop"></a>Eğitim: Power BI Desktop ile Facebook analizi
Bu eğitimde **Facebook** verilerini içeri aktarmayı ve görselleştirmeyi öğreneceksiniz. Eğitim sırasında belirli bir Facebook sayfasına (Power BI sayfası) bağlanmayı, veri dönüştürme adımlarını uygulamayı ve görselleştirme oluşturmayı öğreneceksiniz.

Eğitim şu adımlardan oluşmaktadır:

* **1. Görev:** Bir Facebook Sayfasına bağlanma
* **2. Görev**: Rapor görünümünü kullanarak görselleştirme oluşturma
  
  * **1. Adım**: Ağaç haritası görselleştirmesi oluşturma
* **3. Görev**: Verileri Sorgu görünümünde şekillendirme
  
  * **1. Adım**: Tarih-saat sütununu ikiye ayırma
  * **2. Adım**: İlişkili tablodan toplam değer ekleme
* **4. Görev**: Rapor görünümünü kullanarak ek görselleştirmeler oluşturma
  
  * **1. Adım**: Sorguyu raporunuza yükleme
  * **2. Adım**: Çizgi grafik ve Çubuk grafik oluşturma

## <a name="task-1-connect-to-a-facebook-page"></a>**1. Görev: Bir Facebook sayfasına bağlanma**
Bu görevde [Microsoft Power BI Facebook](https://www.facebook.com/microsoftbi) sitesindeki (URL: *https://www.facebook.com/microsoftbi)* verileri içeri aktaracaksınız.

Herkes bu sayfaya bağlanarak bu adımları uygulayabilir, herhangi bir özel kimlik bilgisi (bu adımda kullanacağınız kendi Facebook hesabınız dışında) gerekli değildir.

![](media/desktop-tutorial-facebook-analytics/1.png)

1. **Başlarken** iletişim kutusunda veya **Giriş şerit sekmesinde** **Veri Al**'ı seçin.
2. Açılan **Veri Al** iletişim kutusunda bulunan veri kaynakları arasından seçim yapabilirsiniz. **Diğer** grubundan **Facebook**'u seçin.
   
   ![](media/desktop-tutorial-facebook-analytics/t_fb_getdataother.png)
   
   **Bağlan**'ı seçtiğinizde üçüncü taraf hizmetleri kullanmanın risklerini belirten bir iletişim kutusu açılır.
   
   ![](media/desktop-tutorial-facebook-analytics/t_fb_connectingtotps.png)
3. Devam'ı seçtiğinizde **Facebook** iletişim kutusu açılır ve sayfa adını (**microsoftbi**) **Kullanıcı adı** metin kutusuna yapıştırabilirsiniz. **Bağlantı** açılan menüsünden **Gönderiler**'i seçin.
   
   ![](media/desktop-tutorial-facebook-analytics/2.png)
4. **Tamam**'a tıklayın.
5. Kimlik bilgileri istendiğinde kendi Facebook hesabınızı kullanarak oturum açın ve Power BI'ın hesabınız üzerinden erişim kurmasına izin verin.
   
   ![](media/desktop-tutorial-facebook-analytics/facebookcredentials.png)

Sayfaya bağlandıktan sonra verilerin modele yüklendiğini göreceksiniz. 

![](media/desktop-tutorial-facebook-analytics/t_fb_1-loadpreview.png)

Ardından veriler **Sorgu Düzenleyicisi**'nde görüntülenir. **Sorgu Düzenleyicisi**, Power BI Desktop'ın bir parçasıdır ancak ayrı bir pencerede yüklenir ve veri bağlantılarınızdaki tüm dönüştürme işlemlerini gerçekleştireceğiniz yer burasıdır.

![](media/desktop-tutorial-facebook-analytics/t_fb_1-intoqueryeditor.png)

Verilerinizi istediğiniz şekle getirdikten sonra Power BI Desktop'a yükleyebilirsiniz. **Giriş** şeridinde **Yükle ve Kapat**'ı seçin.

![](media/desktop-tutorial-facebook-analytics/t_fb_1-loadandclose.png)

Verilerin Power BI Desktop veri modeline yüklenme durumu gösteren bir iletişim kutusu açılır.

![](media/desktop-tutorial-facebook-analytics/t_fb_1-loading.png)

Veriler yüklendikten sonra **Rapor** görünümü açılır ve tablodaki tüm sütunlar sağ taraftaki **Alan** listesine eklenir.

![](media/desktop-tutorial-facebook-analytics/fbdesigner1.png)

## <a name="task-2-create-visualizations-using-the-report-view"></a>**2. Görev: Rapor görünümünü kullanarak görselleştirme oluşturma**
Sayfadaki verileri aldığınıza göre görselleştirmeleri kullanarak hızlıca verilerinizle ilgili öngörülere sahip olabilirsiniz.

**1. Adım:** Ağaç haritası görselleştirmesi oluşturma

Görselleştirme oluşturmak oldukça kolaydır. Tek yapmanız gereken **Alan listesi** bölümündeki alanlardan birini sürükleyip **Rapor tuvaline** bırakmaktır.

**type** alanını **Rapor** tuvaline sürükleyin. Power BI Desktop, **Rapor tuvalinde** yeni bir görselleştirme oluşturur. Ardından **Alanlar** bölümündeki **type** öğesini (az önce **Rapor** tuvaline sürüklediğiniz alan) **Değer** alanına sürükleyerek bir **Çubuk** görselleştirme oluşturun.

![](media/desktop-tutorial-facebook-analytics/fbdesigner2.png)

**Görsel Öğeler** bölmesinden farklı bir simge seçerek görselleştirme türünü kolayca değiştirebilirsiniz. Şimdi **Ağaç haritası** oluşturmak için aşağıdaki görüntüde verilen şekilde **Görsel Öğeler** bölmesinde ilgili simgeyi seçelim.

![](media/desktop-tutorial-facebook-analytics/fbdesigner3.png)

Ardından bir açıklama ekleyip bir veri noktasını rengini değiştirelim. **Görsel Öğeler** bölmesindeki **Biçim** simgesini seçin. **Biçim** simgesi boya fırçasına benzer.

![](media/desktop-tutorial-facebook-analytics/fbdesigner3a.png)

**Açıklama**'nın yanındaki aşağı oku seçtiğinizde bölüm genişletilerek seçtiğiniz görselleştirmenin açıklamasını özelleştirmek için kullanılabilecek seçenekler gösterilir. Bu örnekte aşağıdaki seçimleri yaptık:

* açıklamanın görünmesi için **Açıklama** kaydırıcısını **Açık** konumuna getirdik
* **Açıklama Konumu** açılan menüsünden **Sağ**'ı seçtik
* açıklamaya ilişkin bir başlık görünmesi için **Başlık** kaydırıcısını da **Açık** konumuna getirdik
* açıklamanın başlığına **type** yazdık

Aşağıdaki görüntüde bu ayarlar yapılmış ve görselleştirmeye yansıtılmıştır.

![](media/desktop-tutorial-facebook-analytics/fbdesigner3b.png)

Şimdi veri noktalarından birinin rengini değiştirelim. Genelde köprüler için kullanılan renge yakın olması için bağlantı veri noktasının mavi olması gerekir.

**Veri Renkleri**'nin yanındaki oku seçerek bu bölümü genişletin. Veri noktaları gösterilir ve renklerin yanındaki seçim oklarını kullanarak her veri noktası için ayrı bir renk seçebiliriz.

![](media/desktop-tutorial-facebook-analytics/fbdesigner3c.png)

Herhangi bir veri noktasının yanındaki renk kutusunda bulunan aşağı oka tıkladığınızda açılan renk seçimi iletişim kutusundan kullanmak istediğiniz rengi seçebilirsiniz. Burada açık maviyi seçeceğiz.

![](media/desktop-tutorial-facebook-analytics/fbdesigner3d.png)

Böyle daha iyi. Aşağıdaki görüntüde rengin görselleştirmedeki veri noktasına nasıl uygulandığını ve açıklamanın da otomatik olarak güncelleştirilerek **Veri Renkleri** bölümünde seçilen rengi yansıttığını görebilirsiniz.

![](media/desktop-tutorial-facebook-analytics/fbdesigner3e.png)

## <a name="task-3-shape-data-in-the-table"></a>**3. Görev: Tablodaki verileri şekillendirme**
Tabloyu içeri aktardıktan ve görselleştirmeye başladıktan sonra verilerinizden en yüksek performansı elde etmek için çeşitli veri şekillendirme ve temizleme adımları gerçekleştirmeniz gerekebilir.

**1. Adım:** Tarih-saat sütununu ikiye ayırma

Bu adımda **created\_time** sütununu ikiye bölerek tarih ve saat değerlerini alacaksınız. Power BI Desktop'ta var olan sorguları değiştirmek istediğinizde **Sorgu Düzenleyicisi**'ni açmanız gerekir. Bunu yapmak için **Giriş** sekmesinden **Sorguları Düzenle**'yi seçin.

![](media/desktop-tutorial-facebook-analytics/t_fb_editquery.png)

1. **Sorgu Düzenleyicisi** kılavuzunda **created\_time** sütununu görene kadar sağa doğru kaydırın
2. **Sorgu Önizlemesi** kılavuzunda sütun başlığına sağ tıklayıp **Sütunu Böl \> Sınırlayıcıya göre** yolunu izleyerek sütunları bölün. Sınırlayıcı açılan menüsünde **Özel**'i seçip **"T"** yazın. Bu işlem **Giriş** şerit sekmesinin **Sütunları Yönet** grubunda da mevcuttur.
   
   ![](media/desktop-tutorial-facebook-analytics/9.png)
   
   ![](media/desktop-tutorial-facebook-analytics/10.png)
3. Oluşturulan sütunları sırasıyla **created\_date** ve **created\_time** olarak adlandırın.
4. Yeni **created\_time** sütununu seçtikten sonra **Sorgu görünümü** şeridinde **Sütun Ekle** sekmesine gidip **Tarih ve Saat** grubundan **Zaman\>Saat**'i seçin. Yalnızca zamanın saat bileşenini içeren yeni bir sütun eklenir.
   
   ![](media/desktop-tutorial-facebook-analytics/11.png)
5. Yeni **Saat** sütununun türünü **Tam Sayı** olarak değiştirmek için **Giriş** sekmesine gidip **Veri Türü** açılan menüsünü seçin veya sütuna sağ tıklayıp **Dönüştür\>Tam Sayı**'yı seçin.
   
   ![](media/desktop-tutorial-facebook-analytics/12.png)

**2. Adım:** İlişkili tablodan toplam değer ekleme

Bu adımda görselleştirmelerde kullanmak üzere iç içe geçmiş değerden alınacak paylaşım sayısını ekleyeceksiniz.

1. **shares** sütununu görene kadar sağa doğru kaydırın. İç içe geçmiş değer, gerçek değerlere ulaşmak için başka bir dönüştürme işlemi yapılması gerektiğini belirtir.
2. Sütun başlığının sağ üst köşesindeki ![](media/desktop-tutorial-facebook-analytics/14.png) simgesini seçerek **Genişlet/Toplam** oluşturucusunu açın. **count** öğesini ve ardından **Tamam**'ı seçin. Bunu yaptığınızda tablodaki her satır için paylaşım sayısı eklenir.
   
   ![](media/desktop-tutorial-facebook-analytics/15.png)
   
   Veriler yüklendikten sonra sütun adına çift tıklayarak, sütuna sağ tıklayarak veya **Sorgu görünümü** şeridinde **Dönüştür** sekmesinin **Herhangi Bir Sütun** grubunda **Yeniden Adlandır**'ı seçerek sütunun adını **shares** olarak değiştirin.
3. Son olarak yeni **shares** sütununun değerini **Tam Sayı** olarak değiştirin. Sütun seçiliyken türü değiştirmek için sütuna sağ tıklayıp **Dönüştür\>Tam Sayı** yolunu izleyebilir veya **Giriş** sekmesine gidip **Veri Türü** açılan menüsünü seçebilirsiniz.

### <a name="query-steps-created"></a>Oluşturulan sorgu adımları
Siz Sorgu görünümünde dönüştürme işlemlerini etkinlikleri gerçekleştirdikçe sorgu adımları oluşturulur ve **Sorgu Ayarları** bölmesindeki **UYGULANAN ADIMLAR** listesinde görüntülenir. Her bir sorgu adımına ilişkin bir Sorgu formülü ("M" dili olarak da bilinir) bulunur.

![](media/desktop-tutorial-facebook-analytics/16.png)

| Görev | Sorgu adımı | Formül |
| --- | --- | --- |
| Bir Facebook kaynağına bağlanma |Source |Facebook.Graph (&quot;https://graph.facebook.com/microsoftbi/posts&quot;) |
| İhtiyacınız olan değerlere ulaşmak için **Sütunları Böl** işlemi |Split Column by Delimiter |Table.SplitColumn  (Source,&quot;created_time&quot;,Splitter.SplitTextByDelimiter(&quot;T&quot;),{&quot;created_time.1&quot;, &quot;created_time.2&quot;}) |
| Yeni sütunlar için **Türü Değiştir** işlemi (otomatik adım) |Changed Type |Table.TransformColumnTypes  (#&quot;Split Column by Delimiter&quot;,{{&quot;created_time.1&quot;, type date}, {&quot;created_time.2&quot;, type time}}) |
| ****Bir sütunu** yeniden adlandırma** |Renamed Columns |Table.RenameColumns  (#&quot;Changed Type&quot;,{{&quot;created_time.1&quot;, &quot;created_date&quot;}, {&quot;created_time.2&quot;, &quot;created_time&quot;}}) |
| ****Bir sütun** ekleme** |Inserted Hour |Table.AddColumn  (#&quot;Renamed Columns&quot;, &quot;Hour&quot;, each Time.Hour([created_time]), type number) |
| **Türü Değiştirme ** |Changed Type1 |Table.TransformColumnTypes  (#&quot;Inserted Hour&quot;,{{&quot;Hour&quot;, type text}}) |
| ****İç içe geçmiş tablodaki değerleri** genişletme** |Expand shares |Table.ExpandRecordColumn  (#&quot;Changed Type1&quot;, &quot;shares&quot;, {&quot;count&quot;}, {&quot;shares.count&quot;}) |
| ****Sütunu** yeniden adlandırma** |Renamed Columns1 |Table.RenameColumns  (#&quot; Expand shares&quot;,{{&quot;shares.count&quot;, &quot;shares&quot;}}) |
| **Türü Değiştir** |Changed Type2 |Table.TransformColumnTypes  (#&quot;Renamed Columns1&quot;,{{&quot;shares&quot;, Int64.Type}}) |

## <a name="task-4-create-additional-visualizations-using-the-report-view"></a>**4. Görev: Rapor görünümünü kullanarak ek görselleştirmeler oluşturma**
Verileri çözümlememizin geri kalanı için istediğimiz şekle dönüştürdüğümüze göre sonuç tabloyu Raporumuza yükleyip ek görselleştirmeler oluşturabiliriz.

**1. Adım: Sorguyu raporunuza yükleme**

Sorgu sonuçlarını rapora yüklemek için **Sorgu Düzenleyicisi**'nde **Yükle ve Kapat**'ı seçin. Bunu yaptığınızda değişiklikler Power BI Desktop'a yüklenir ve **Sorgu Düzenleyicisi** kapatılır.

![](media/desktop-tutorial-facebook-analytics/t_fb_1-loadandclose.png)

Power BI Desktop'ta **Rapor** görünümünde olduğunuzdan emin olun. Power BI Desktop'ta sol taraftaki çubuğun en üstünde bulunan simgeyi seçin.

![](media/desktop-tutorial-facebook-analytics/17.png)

**2. Adım:** Çizgi grafik ve Çubuk grafik oluşturma

Görselleştirme oluşturmak için **Alan listesindeki** alanları sürükleyerek **Rapor tuvaline** bırakabiliriz.

1. **shares** alanını **Rapor** tuvaline sürükleyerek bir çubuk grafik oluşturun. Ardından created\_date sütununu grafiğe sürüklediğinizde Power BI Desktop görselleştirmeyi **Çizgi Grafik** olarak değiştirir.
   
   ![](media/desktop-tutorial-facebook-analytics/19.png)
2. Sonraki adımda **shares** alanını sürükleyip **Rapor tuvaline** bırakın. Şimdi **Hour** alanını **Alan Listesi** altındaki **Eksen** bölümüne sürükleyin.
   
   ![](media/desktop-tutorial-facebook-analytics/20.png)
3. **Görsel Öğeler** bölmesinde farklı bir simgeye tıklayarak görselleştirme türünü kolayca değiştirebiliriz. Aşağıdaki resimde **Çubuk Grafik** simgesi okla gösterilmiştir.
   
   ![](media/desktop-tutorial-facebook-analytics/21.png)
4. Görselleştirme türünü **Çubuk Grafik** olarak değiştirin.
5. **Çubuk Grafik** oluşturuldu ancak eksen istediğimiz şekilde değil. Diğer yönde (yüksekten düşüğe) sıralanmasını istiyoruz. **Y Ekseni**'nin yanındaki aşağı oku seçerek o bölümü genişletin. İstediğimiz şekilde sıralayabilmek için bu eksenin türünü **Sürekli** yerine **Kategorik** olarak değiştirmemiz gerekiyor (aşağıdaki görüntüde eksenin seçimi yapmadan önceki hali gösterilmektedir, istediğiniz gibi görünen hali için sonraki görüntüye bakın).

![](media/desktop-tutorial-facebook-analytics/22.png)

Böyle daha iyi. Bu sayfada artık üç farklı görselleştirmemiz olduğuna göre bunları istediğimiz şekilde boyutlandırarak rapor sayfasını doldurabiliriz.

![](media/desktop-tutorial-facebook-analytics/23.png)

Gördüğünüz gibi verileri istediğiniz şekilde sunmak için raporunuzdaki görselleştirmeleri kolayca özelleştirebilirsiniz. Power BI Desktop, birçok farklı veri kaynağından veri almanın ve çözümleme ihtiyaçlarınızı karşılayacak şekilde biçimlendirmeye ek olarak bu verileri zengin ve etkileşimli bir şekilde görselleştirmeye kadar sorunsuz ve uçtan uca bir deneyim sunar. Rapor hazır hale geldikten sonra [Power BI'a yükleyip](desktop-upload-desktop-files.md) bunu kullanan panolar oluşturabilir ve diğer Power BI kullanıcılarıyla paylaşabilirsiniz.

Bu eğitimde kullanılan dosyanın son halini [buradan](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/FacebookAnalytics.pbix) indirebilirsiniz

### <a name="where-else-can-i-get-more-information"></a>Daha fazla bilgiye nereden ulaşabilirim?
* [Diğer Power BI Desktop eğitimlerini okuyun](http://go.microsoft.com/fwlink/?LinkID=521937)
* [Power BI Desktop videolarını izleyin](http://go.microsoft.com/fwlink/?LinkID=519322)
* [Power BI Forumu'nu ziyaret edin](http://go.microsoft.com/fwlink/?LinkID=519326)
* [Power BI Blogu'nu okuyun](http://go.microsoft.com/fwlink/?LinkID=519327)



