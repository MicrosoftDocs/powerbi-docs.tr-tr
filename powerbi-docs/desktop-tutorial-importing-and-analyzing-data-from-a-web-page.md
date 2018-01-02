---
title: "Eğitim: Power BI Desktop'ı kullanarak bir Web Sayfasından veri içeri aktarma ve bu verileri çözümleme"
description: "Eğitim: Power BI Desktop'ı kullanarak bir Web Sayfasından veri içeri aktarma ve bu verileri çözümleme"
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
ms.openlocfilehash: c5139c6f9f7b2098b51a608fb7719f371173c291
ms.sourcegitcommit: d91436de68a0e833ecff18d976de9d9431bc4121
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/06/2017
---
# <a name="analyzing-web-page-data-using-power-bi-desktop-tutorial"></a>Power BI Desktop'ı kullanarak Web sayfası verilerini çözümleme (eğitim)
Bu eğitimde bir Web sayfasındaki veri tablosunu içeri aktarmayı ve bu verileri görselleştirmek için rapor oluşturmayı öğreneceksiniz. Bu işlemin bir parçası olarak bir Web sayfasındaki tablolarda gezinecek ve tabloya yeni bir şekil vermek için veri dönüştürme adımları uygulayacaksınız.

 Bu makalede:

* **1. Görev:** Web veri kaynağına bağlanma
* **2. Görev:** Verileri Sorgu görünümünde şekillendirme
  * 1. Adım: Yalnızca ilgili sütunları görüntülemek için Diğer Sütunları kaldırma
  * 2. Adım: Belirli bir sütundaki değerleri temizlemek için Değerleri değiştirme
  * 3. Adım: Bir sütunda bulunan değerleri filtreleme
  * 4. Adım: Bir sütunu yeniden adlandırma
  * 5. Adım: Bir sütundaki boş değerleri filtreleme
  * 6. Adım: Bir sorguyu yeniden adlandırma
  * Sorgu Adımları oluşturuldu
* **3. Görev:** Rapor görünümünü kullanarak görselleştirme oluşturma
  * 1. Adım: Sorguyu raporunuza yükleme
  * 2. Adım: Harita görselleştirmesi oluşturma

## <a name="task-1-connect-to-a-web-data-source"></a>1. Görev: Web veri kaynağına bağlanma
 1. görevde şu konumdaki UEFA Avrupa Futbol Şampiyonası Wikipedia sayfasında bulunan Turnuva Özeti tablosunu içeri aktaracaksınız: http://en.wikipedia.org/wiki/UEFA\_European\_Football\_Championship

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage1.png)

### <a name="add-a-wikipedia-page-data-source"></a>Wikipedia sayfası veri kaynağı ekleme
1. **Başlarken iletişim kutusunda** veya **Giriş** şerit sekmesinde **Veri Al**'ı seçin.
2. Açılan **Veri Al** iletişim kutusunda Power BI Desktop'a aktarabileceğiniz farklı veri kaynakları arasından seçim yapabilirsiniz. **Tümü** veya **Diğer** grubunda bulunan **Web**'i seçeceğiz.
3. **Web İçeriği** iletişim kutusundaki **URL** metin kutusuna Wikipedia URL'sini yapıştırın: (http://en.wikipedia.org/wiki/UEFA\_European\_Football\_Championship).
4. **Tamam**'a tıklayın.

Web sayfasıyla bağlantı kurduktan sonra **Gezgin** iletişim kutusunda bu Wikipedia sayfasında bulunan tabloların listesini göreceksiniz. Verileri önizlemek için bu tablolara bir kez tıklayabilirsiniz.

**Gezgin** iletişim kutusunda soldaki bölmede Tournament Summary sonuçları tablosunun **Results[edit]** tablosunu seçin veya **Results[edit]** tablosunu seçip **Düzenle**'yi seçin. Bu sayede bu tabloyu Rapora yüklemeden önce düzenleyebilir, verileri çözümleme için gerekli biçime dönüştürebiliriz.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/tutorialimanaly_navigator.png)

Bu işlemin ardından tablo özeti Sorgu görünümünde açılacak ve verileri temizlemek için bir dizi dönüştürme adımı uygulayabileceksiniz.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage3.png)

## <a name="task-2-shape-data-in-the-subject-table"></a>2. Görev: Verileri konu tablosunda şekillendirme
Veri sorgunuza ait konu tablosunu seçtiniz, şimdi farklı veri şekillendirme ve temizleme adımlarını gerçekleştirmeyi öğreneceksiniz.

**1. Adım:** Yalnızca ilgili sütunları görüntülemek için Diğer Sütunları kaldırma

Bu adımda **Year** ve **Final Winners** haricindeki tüm sütunları kaldıracaksınız.

1. **Sorgu Önizlemesi** kılavuzunda **Year** ve **Final Winners** sütunlarını seçin (**CTRL** + **Tıklama** birleşimini kullanın).
2. **Sorgu Önizlemesi** kılavuzunda sütun başlıklarından birine sağ tıklayıp **Diğer Sütunları Kaldır**'a tıklayarak seçili olmayan sütunları kaldırın. Bu işlem **Giriş** şerit sekmesinin **Sütunları Yönet** grubunda da mevcuttur.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage4.png)

**2. Adım:** Belirli bir sütundaki değerleri temizlemek için Değerleri değiştirme

Bu adımda **Year** sütunundaki Details son ekini değiştireceksiniz. Bu son ek yeni satırda olduğu için tablo önizlemesinde görünmediğine dikkat edin. Ancak Year sütunundaki sayısal değer içeren hücrelerden birine tıkladığınızda tam değeri ayrıntılı görünümde görebilirsiniz.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage5.png)

1. **Year** sütununu seçin.
2. **Sorgu görünümü** şeridinin **Giriş** sekmesinde **Değerleri Değiştir**'e tıklayın veya **Year** sütununa sağ tıklayıp **Değerleri Değiştir**'e tıklayarak Details son ekini boş metinle değiştirin.
3. **Değerleri Değiştir** iletişim kutusunda **Bulunacak Değer** metin kutusuna Details yazın ve **Şununla Değiştir** metin kutusunu boş bırakın.
4. **Tamam**'a tıklayın.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage6.png)

 **3. Adım:** Bir sütunda bulunan değerleri filtreleme

Bu adımda **Year** sütununu "Year" içermeyen satırları görüntüleyecek şekilde filtreleyeceksiniz.

1. **Year** sütunundaki filtre açılan menü okuna tıklayın.
2. **Filtre** açılan menüsündeki **Year** seçeneğini silin.
3. **Tamam**'a tıklayın.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage7.png)

**4. Adım:** Bir sütunu yeniden adlandırma

**Year** sütunundaki verileri temizledik, şimdi **Final Winner** sütunu üzerinde çalışacağız.

Yalnızca kazananların listesine baktığımız için bu sütunun adını **Country** olarak değiştirebiliriz.

1. Sorgu önizlemesinde **Final Winner** sütununu seçin.
2. **Sorgu görünümü** şeridinin **Dönüştür** sekmesinin ve **Herhangi Bir Sütun** grubunun altında **Yeniden Adlandır** seçeneğini göreceksiniz.
3. Buna tıkladığınızda sütun adı düzenlenebilir hale gelir. Bu sütunun adını **Country** olarak değiştireceğiz.

**5. Adım:** Bir sütundaki boş değerleri filtreleme

**Country** sütunundaki boş değerleri de filtrelememiz gerekiyor. Bunu yapmak için 3. adımdaki filtre menüsünü kullanabilir veya alternatif olarak şu işlemi gerçekleştirebiliriz:

1. **Country** sütunundaki boş değer içeren hücrelerden birine sağ tıklayın.
2. Bağlam menüsündeki **Metin Filtreleri -\> Eşit değildir** seçeneğini belirleyin.
3. **Country** sütunundaki boş değerlere sahip satırları kaldırmak üzere yeni bir filtre adımı oluşturulur.

**6. Adım:** Sorguyu adlandırma

Bu adımda son sorgunuzu **Euro Cup Winners** olarak adlandıracaksınız.

1. **Sorgu Ayarları** bölmesindeki **Ad** metin kutusuna **Euro Cup Winners** yazın.
   
   ![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage8.png)

## <a name="task-3-create-visualizations-using-the-report-view"></a>3. Görev: Rapor görünümünü kullanarak görselleştirme oluşturma
Verileri çözümleme için istediğimiz şekle dönüştürdüğümüze göre sonuçta ortaya çıkan tabloyu Raporumuza yükleyip birkaç görselleştirme oluşturabiliriz.

**1. Adım:** Sorguyu raporunuza yükleme

Sorgu sonuçlarını Power BI Desktop'a yükleyip rapor oluşturmak için **Giriş** şeridinden **Kapat ve Yükle**'yi seçin.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage9.png)

Bunu yaptığınızda sorgu değerlendirmesi tetiklenir ve tablo çıktısı Rapora yüklenir. Power BI Desktop'ta **Rapor** simgesini seçerek Power BI Desktop uygulamasını Rapor görünümüne geçirin.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage10.png)

Sonuç tablosunun alanlarını **Rapor görünümünün** **Alanlar bölmesinde** görebilirsiniz.

![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage11.png)

**2. Adım:** Harita görselleştirmesi oluşturma

Görselleştirme oluşturmak için **Alan listesindeki** alanları sürükleyerek **Rapor tuvaline** bırakabiliriz.

1. **Country** alanını sürükleyip **Rapor tuvaline** bırakın. **Rapor tuvalinde** yeni bir görselleştirme oluşturulur. Bu durumda elimizde ülke listesi olduğu için bir **Harita görselleştirmesi** oluşturulur.
   
   ![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage12.png)
2. **Görsel Öğeler** bölmesinde farklı bir simgeye tıklayarak görselleştirme türünü kolayca değiştirebiliriz.
   
   ![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage13.png)
3. Bu örnekte **Harita** görselleştirme türünü koruyacağız. Görselleştirmenin köşelerini sürükleyerek boyutunu da değiştirebiliriz.
   
   ![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage14.png)
4. Haritadaki tüm noktaların aynı boyutta olduğuna dikkat edin. Bunu değiştirerek daha fazla Avrupa Kupası kazanmış ülkelerin haritada daha büyük noktayla gösterilmesini istiyoruz. Bunu yapmak için **Alanlar listesindeki** **Year** alanını **Alanlar bölmesinin** alt yarısındaki **Değerler** kutusuna sürükleyebilirsiniz.
   
   ![](media/desktop-tutorial-importing-and-analyzing-data-from-a-web-page/webpage15.png)

Gördüğünüz gibi verileri istediğiniz şekilde sunmak için raporunuzdaki görselleştirmeleri kolayca özelleştirebilirsiniz. Power BI Desktop, birçok farklı veri kaynağından veri almanın ve çözümleme ihtiyaçlarınızı karşılayacak şekilde biçimlendirmeye ek olarak bu verileri zengin ve etkileşimli bir şekilde görselleştirmeye kadar sorunsuz ve uçtan uca bir deneyim sunar. Rapor hazır hale geldikten sonra [Power BI'a yükleyip](desktop-upload-desktop-files.md) bunu kullanan panolar oluşturabilir ve diğer Power BI kullanıcılarıyla paylaşabilirsiniz.

**Web'den Veri Aktarma** eğitiminin sonuna geldiniz. Tamamlanmış Power BI Desktop dosyasını [buradan](http://download.microsoft.com/download/1/4/E/14EDED28-6C58-4055-A65C-23B4DA81C4DE/Analyzing_Data_From_The_Web.pbix) indirebilirsiniz.

## <a name="where-else-can-i-get-more-information"></a>Daha fazla bilgiye nereden ulaşabilirim?
* [Diğer Power BI Desktop eğitimlerini okuyun](http://go.microsoft.com/fwlink/?LinkID=521937)
* [Power BI Desktop videolarını izleyin](http://go.microsoft.com/fwlink/?LinkID=519322)
* [Power BI Forumu'nu ziyaret edin](http://go.microsoft.com/fwlink/?LinkID=519326)
* [Power BI Blogu'nu okuyun](http://go.microsoft.com/fwlink/?LinkID=519327)

