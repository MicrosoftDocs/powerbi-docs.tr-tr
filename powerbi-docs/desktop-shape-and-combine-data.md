---
title: Birden fazla kaynaktan verileri şekillendirme ve birleştirme
description: Bu öğreticide, Power BI Desktop’ta verileri şekillendirmeyi ve birleştirmeyi öğreneceksiniz
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: tutorial
ms.date: 05/08/2019
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 2835dd34ce5ba2d7bc6be8659b87eb1f550fdc28
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65514583"
---
# <a name="tutorial-shape-and-combine-data-in-power-bi-desktop"></a>Öğretici: Power BI Desktop'ta verileri şekillendirme ve birleştirme

**Power BI Desktop** ile çok çeşitli veri kaynaklarına bağlanabilir ve ardından verileri ihtiyaçlarınızı karşılayacak şekilde şekillendirebilir, böylece başkalarıyla paylaşabileceğiniz görsel raporlar oluşturabilirsiniz. Verileri *şekillendirme* verileri dönüştürme anlamına gelir. Sütunları veya tabloları yeniden adlandırma, metinleri sayı olarak değiştirme, satırları kaldırma, ilk satırı başlık olarak ayarlama ve benzeri değişiklikler yapma bu işlemlere örnek olarak verilebilir. Verileri *birleştirme*, iki veya daha fazla veri kaynağını bağlama, gerektiği şekilde şekillendirme ve ardından bunları kullanışlı tek bir sorguda birleştirme anlamına gelir.

Bu öğreticide aşağıdakilerin nasıl yapılacağını öğreneceksiniz:

* **Sorgu Düzenleyicisi** kullanarak verileri şekillendirme
* Bir veri kaynağına bağlanma
* Başka bir veri kaynağına bağlanma
* Bu veri kaynaklarını birleştirme ve raporlarda kullanılacak bir veri modeli oluşturma

Bu öğreticide Power BI Desktop’ı kullanarak bir sorgunun nasıl şekillendirileceği gösterilmiş ve sık kullanılan görevlerin bazılarının üzerinde durulmuştur. Burada kullanılan sorgu, sıfırdan nasıl oluşturulacağı da dahil olmak üzere [Power BI Desktop ile çalışmaya başlama](desktop-getting-started.md) başlıklı makalede daha ayrıntılı bir şekilde açıklanmıştır.

Power BI Desktop'taki **Sorgu Düzenleyicisi**'nde, şeridin yanı sıra, sağ tıklama menülerinin de bolca kullanıldığını bilmekte yarar vardır. **Dönüştürme** şeridinde seçebileceklerinizin çoğunu, bir öğeye (sütun gibi) sağ tıklayıp görüntülenen menüden seçim yaparak da kullanabilirsiniz.

## <a name="shape-data"></a>Verileri şekillendirme
Sorgu Düzenleyicisi'nde verileri şekillendirdiğinizde, Sorgu Düzenleyicisi'nin yüklediği ve sunduğu verilerin ayarlanması için adım adım yönergeler (Sorgu Düzenleyicisi'nin sizin için uyguladığı) sağlamış olursunuz. Özgün veri kaynağı etkilenmez. Yalnızca söz konusu belirli veri görünümü ayarlanır veya *şekillendirilir*.

Belirttiğiniz adımlar (bir tabloyu yeniden adlandırma, bir veri türünü dönüştürme veya sütunları silme gibi) Sorgu Düzenleyicisi tarafından kaydedilir ve bu sorgu veri kaynağına her bağlandığında söz konusu adımlar uygulanır. Böylece veriler her zaman sizin belirttiğiniz biçimde şekillendirilir. Bu işlem, Sorgu Düzenleyicisi özelliğini Power BI Desktop'ta her kullanışınızda veya **Power BI** hizmetinde olduğu gibi, paylaşılan sorgunuzu kullanan herkes için gerçekleştirilir. Bu adımlar, **Sorgu Ayarları** bölmesindeki **Uygulanan Adımlar** bölümünde sırasıyla kaydedilir.

Aşağıdaki görüntüde, şekillendirilmiş bir sorgu için **Sorgu Ayarları** bölmesi gösterilmiştir. Sonraki paragraflarda bu adımların her birini inceleyeceğiz.

![](media/desktop-shape-and-combine-data/shapecombine_querysettingsfinished2.png)

[Power BI Desktop ile çalışmaya başlama](desktop-getting-started.md) başlıklı makalede bir Web veri kaynağına bağlanarak edindiğimiz emeklilik verilerini kullanarak, bu verileri ihtiyaçlarımız doğrultusunda şekillendirelim.

Yeni başlayanlar için, tüm verilerin eşit olduğunu dikkate alarak dereceyi hesaplamak için bir özel sütun ekleyelim ve bunu mevcut _Derece_ sütunuyla karşılaştıralım.  Burada, özel sütun eklemenize olanak sağlayan **Özel Sütun** düğmesini işaret eden bir ok ile birlikte **Sütun Ekle** şeridi yer almaktadır.

![](media/desktop-shape-and-combine-data/shapecombine_customcolumn.png)

**Özel Sütun** iletişim kutusunda **Yeni sütun adı** bölümüne _Yeni Derece_ girin ve **Özel sütun formülü** alanına aşağıdakileri girin:

    ([Cost of living] + [Weather] + [Health care quality] + [Crime] + [Tax] + [Culture] + [Senior] + [#"Well-being"]) / 8

Durum iletisinde _'Bir söz dizimi hatası algılanmadı.'_ yazdığından emin olun ve **Tamam** düğmesine tıklayın.

![](media/desktop-shape-and-combine-data/shapecombine_customcolumndialog.png)

Sütun verilerinin tutarlılığını korumak için yeni sütun değerlerini tam sayılara dönüştürelim. Bunları değiştirmek için sütun üst bilgisine sağ tıklayıp **Türü Değiştir \> Tam Sayı** seçeneğini belirlemeniz yeterlidir. 

Birden fazla sütun seçmeniz gerekirse, öncelikle bir sütun seçip **SHIFT** tuşunu basılı tutarak bitişik daha fazla sütun belirleyin ve ardından bir sütun üst bilgisine sağ tıklayarak seçili tüm sütunları değiştirin. Bitişik olmayan sütunları seçmek için **CTRL** tuşunu da kullanabilirsiniz.

![](media/desktop-shape-and-combine-data/shapecombine_changetype2.png)

**Dönüştür** şeridinden de sütun veri türlerini *dönüştürebilirsiniz*. Aşağıda gördüğünüz üzere, **Dönüştür** şeridindeki **Veri Türü** düğmesinde, geçerli veri türünü başka bir türe dönüştürmenize olanak sağlayan bir ok mevcuttur.

![](media/desktop-shape-and-combine-data/queryoverview_transformribbonarrow.png)

**Sorgu Ayarları**'ndaki **Uygulanan Adımlar**'ın, verilere uygulanan tüm şekillendirme adımlarını gösterdiğine dikkat edin. Herhangi bir adımı şekillendirme işleminden kaldırmak istersem bunu adımın solundaki **X**'i seçerek kolayca gerçekleştirebilirim. Aşağıdaki görüntüde, **Uygulanan Adımlar** o ana kadar uygulanmış adımları göstermektedir: web sitesine bağlanma (**Kaynak**) ve tabloyu seçme (**Gezinme**). Ayrıca Sorgu Düzenleyicisi, tabloyu yüklerken metin tabanlı sayı sütunlarının *Metin* olan veri türünü *Tam Sayı* olarak değiştirmiştir (**Değiştirilen Tür**). Son iki adım, **Özel Eklendi** ve **Tür1 Değiştirildi** seçeneği ile önceki eylemlerimizi göstermektedir. 

![](media/desktop-shape-and-combine-data/shapecombine_appliedstepsearly2.png)

Bu sorguyla çalışabilmek için, ilgili verileri istediğimiz hale getirmek üzere birkaç değişiklik yapmamız gerekiyor:

* *Bir sütunu kaldırarak derecelendirmeleri ayarlama*: **Cost of living**’in sonuçlarımızda bir faktör olmadığına karar verdik. Bu sütunu kaldırdıktan sonra, verilerin değişmeden kaldığını belirledik. Ancak Power BI Desktop kullanılarak bu kolayca düzeltilebilir ve bu da, Sorgudaki muhteşem **Uygulanan Adımlar** özelliğini göstermektedir.
* *Birkaç hatayı düzeltme*: Bir sütunu kaldırdığımız için **Yeni Derece** sütunundaki hesaplamalarımızı ayarlamamız gerekiyor. Bu, bir formülün değiştirilmesini kapsar.
* *Verileri sıralama*: **Yeni Derece** ve **Derece** sütunlarına dayanarak verileri sıralayın. 
* *Verileri değiştirme*: Belirli bir değerin nasıl değiştirileceğini ve bir **Uygulanan Adım** ekleme gereksinimini vurgulayacağız.
* *Tablo adını değiştirme*: **Table 0** kullanışlı bir tanımlayıcı değildir ancak bunu değiştirmek kolaydır.

**Cost of living** sütununu kaldırmak için, söz konusu sütunu ve şeritteki **Giriş** sekmesini seçip aşağıdaki şekilde gösterildiği gibi **Sütunları Kaldır** seçeneğini belirlemeniz yeterlidir.

![](media/desktop-shape-and-combine-data/shapecombine_removecolumnscostofliving.png)

_Yeni Derece_ değerlerinin değişmediğine dikkat edin; bu, adımların sıralanmasından kaynaklanır. Adımlar Sorgu Düzenleyicisi tarafından sırasıyla, ancak birbirinden bağımsız olarak kaydedildiğinden her bir **Uygulanan Adım**'ı sıranın yukarısına veya aşağısına taşıyabilirsiniz. Herhangi bir adımda sağ tıklarsanız, Sorgu Düzenleyicisi aşağıdakileri yapmanızı sağlayan bir menü görüntüler: **Yeniden Adlandır**, **Sil**, **Sona Kadar** **Sil** (geçerli adımı ve onu izleyen tüm adımları kaldır), **Yukarı Taşı** veya **Aşağı Taşı**. Devam edin ve _Özel Eklendi_ adımın hemen yukarısındaki son adım olan _Kaldırılan Sütunlar_ adımına geçin.

![](media/desktop-shape-and-combine-data/shapecombine_movestep.png)

Ardından _Özel Eklendi_ adımını seçin. Verilerin şimdi ele almamız gereken _Hata_’yı gösterdiğine dikkat edin. 

![](media/desktop-shape-and-combine-data/shapecombine_error2.png)

Her bir hata ile ilgili daha fazla bilgi edinmek için birkaç farklı yol izlenebilir. Hücreyi seçebilir (**Hata** sözcüğüne tıklamadan) veya doğrudan **Hata** sözcüğüne tıklayabilirsiniz. Doğrudan **Hata** sözcüğüne *tıklamadan* hücreyi seçerseniz Sorgu Düzenleyicisi, hata bilgilerini pencerenin alt kısmında görüntüler.

![](media/desktop-shape-and-combine-data/shapecombine_errorinfo2.png)

Doğrudan *Hata* sözcüğüne tıklarsanız Sorgu Düzenleyicisi, **Sorgu Ayarları** bölmesinde bir **Uygulanan Adım** oluşturur ve hata hakkındaki bilgileri görüntüler. Bu rotayı istemiyoruz, bu nedenle **İptal**’i seçin.

Hataları düzeltmek için, _Yeni Derece_ sütununu seçin, ardından **Görünüm** şeridini açıp **Formül Çubuğu** onay kutusunu seçerek sütunun veri formülünü görüntüleyin. 

![](media/desktop-shape-and-combine-data/shapecombine_formulabar.png)

Şimdi formülü aşağıdaki şekilde değiştirerek _Cost of living_ parametresini kaldırabilir ve böleni azaltabilirsiniz: 

    Table.AddColumn(#"Removed Columns", "New Rank", each ([Weather] + [Health care quality] + [Crime] + [Tax] + [Culture] + [Senior] + [#"Well-being"]) / 7)

Formül kutusunun solundaki yeşil onay işaretini seçin veya **Enter** tuşuna basın. Böylece veriler, düzeltilen değerlerle değiştirilmeli ve **Özel Eklendi** adımı artık *herhangi bir hata olmadan* tamamlanmalıdır.

> [!NOTE]
> Ayrıca hata içeren tüm satırların kaldırılmasını sağlayan **Hataları Kaldır** seçeneğini de belirleyebilirsiniz (şeridi veya sağ tıklama menüsünü kullanarak). Bu durumda, verilerimizden tüm satırları kaldırmış oluruz ancak biz bunu değil, verileri tabloda tutmak istiyoruz.

Şimdi **Yeni Derece** sütununa dayanarak verileri sıralamamız gerekir. İlk olarak, en yeni verilere ulaşmak için son uygulanan adım olan **Tür1 Değiştirildi** adımını seçin. Sonra, **Yeni Derece** sütun üst bilgisinin yanında bulunan açılır listeyi seçin ve **Artan Düzende Sırala** seçeneğini belirleyin.

![](media/desktop-shape-and-combine-data/shapecombine_sort.png)

Verilerin şimdi **Yeni Derece**’ye göre sıralandığına dikkat edin.  Ancak **Derece** sütununa bakarsanız, **Yeni Derece** değerinin bağ olması durumunda verilerin düzgün şekilde sıralanmadığını fark edersiniz. Bunu düzeltmek için, **Yeni Derece** sütununu seçin ve **Formül Çubuğu**’ndaki formülü aşağıdaki şekilde değiştirin:

    = Table.Sort(#"Changed Type1",{{"New Rank", Order.Ascending},{"Rank", Order.Ascending}})

Formül kutusunun solundaki yeşil onay işaretini seçin veya **Enter** tuşuna basın; böylece satırlar, _Yeni Derece_ ve _Derece_’ye göre sıralanmalıdır.

Ek olarak, listenin herhangi bir yerinde bulunan bir **Uygulanan Adım**'ı seçebilir ve verileri, sıradaki ilgili noktada şekillendirmeye devam edebilirsiniz. Sorgu Düzenleyicisi, yeni adımları otomatik olarak, seçili olan **Uygulanan Adım**'ın arkasına yerleştirir. Denemeye ne dersiniz?

İlk olarak, özel sütunu eklemeden önce **Uygulanan Adım**’ı seçin; bu, _Kaldırılan Sütunlar_ adımı olacaktır. Burada, Arizona’daki _Hava Durumu_ derecelendirmesinin değerini değiştireceğiz. Arizona’nın _Hava Durumu_ derecelendirmesini içeren hücreye sağ tıklayın ve görünen menüden *Değerleri Değiştir...* seçeneğini belirleyin. Şu anda hangi **Uygulanan Adım**’ın (_Özel Eklendi_ adımından önceki adım) seçili olduğuna dikkat edin.

![](media/desktop-shape-and-combine-data/shapecombine_replacevalues2.png)

Bir adım eklemeye çalıştığımız için Sorgu Düzenleyicisi bizi bu işlemin taşıdığı risk konusunda uyarır: Birbirini izleyen adımlar sorgunun bozulmasına neden olabilir. Bu işlemi gerçekleştirirken dikkatli ve mantıklı hareket etmemiz gerekir. Bunun bir eğitim olduğunu ve adımları nasıl oluşturacağınızı, sileceğinizi, ekleyeceğinizi ve yeniden sıralayacağınızı göstermek için Sorgu Düzenleyicisi'nin oldukça etkili bir özelliğinin üzerinde durduğumuzu düşündüğümüzde, devam edip **Ekle**'yi seçmememiz için önümüzde hiçbir engel yok.

![](media/desktop-shape-and-combine-data/shapecombine_insertstep.png)

Değeri _51_ olarak değiştirin, böylece Arizona verileri değiştirilir. Yeni bir Uygulanan Adım oluşturduğunuzda, Sorgu Düzenleyicisi bu adımı, gerçekleştirilen eyleme göre (bu örnekte, **Değiştirilen Değer**) adlandırır. Sorgunuzda aynı adlı birden fazla adım olduğunda, Sorgu Düzenleyicisi bunları ayırt etmek için, birbirini izleyen her bir **Uygulanan Adım**'a bir sayı (sırasıyla) ekler.

Şimdi son **Uygulanan Adım**’ı, _Sıralanan Satırlar_’ı seçin ve verilerin Arizona’nın yeni derecelendirmesine göre değiştiğine dikkat edin.  Bu, _Değiştirilen Değer_ adımını, _Özel Eklendi_ adımından önce doğru yere eklememizden kaynaklanır.

Yukarıdakilerin biraz karmaşık olduğunu kabul etmek gerekse de Sorgu Düzenleyicisi'nin ne kadar etkili ve çok yönlü olduğuna yönelik iyi bir örnek olduğunu görmezden gelemeyiz.

Son olarak, söz konusu tablonun adını daha açıklayıcı bir adla değiştirmek istiyoruz. Rapor oluştururken, özellikle de birden çok veri kaynağına bağlandığımızda, açıklayıcı tablo adları kullanmakta yarar vardır. Bu tablo adları **Rapor** görünümünün **Alanlar** bölmesinde yer alır.

Tablo adı kolayca değiştirilebilir: **Sorgu Ayarları** bölmesindeki **Özellikler** bölümünü altında, tablonun yeni adını aşağıdaki görüntüde gösterildiği gibi yazmak ve **Enter** tuşuna basmak yeterlidir. Bu tabloya *RetirementStats* adını verelim.

![](media/desktop-shape-and-combine-data/shapecombine_renametable2.png)

Verileri gerektiği ölçüde şekillendirdik. Şimdi de başka bir veri kaynağına bağlanalım ve verileri birleştirelim.

## <a name="combine-data"></a>Verileri birleştirme
Eyaletlerin çeşitli durumları hakkındaki bu veriler ilgi çekici; ek çözümleme çalışmaları ve sorgular oluşturmak için faydalı olacaktır. Ancak, bu noktada bir sorun var: Gösterilen verilerin çoğunda eyalet kodları için eyaletin tam adı yerine iki harfli kısaltmalar kullanılmıştır. Eyalet adlarını kısaltmalarıyla ilişkilendirmek için bir yönteme ihtiyacımız var.

Şanslı günümüzdeyiz! Tam da bunu yapan başka bir genel veri kaynağı var, ancak emeklilik tablomuza bağlamadan önce bazı şekillendirme işlemleri yapmamız gerekiyor. Aşağıda eyalet kısaltmalarına yönelik web kaynağına ulaşabilirsiniz:

<http://en.wikipedia.org/wiki/List_of_U.S._state_abbreviations>

Sorgu Düzenleyicisi’ndeki **Giriş** şeridinde, **Yeni Kaynak \> Web** seçeneğini belirledikten sonra adresi girip **Bağlan**’ı seçtiğimizde Gezgin, bu Web sayfasında neler bulduğunu gösterir.

 ![](media/desktop-shape-and-combine-data/designer_gsg_usstateabbreviationsnavigator2.png)

İstediğimiz verileri içerdiğinden **Kodlar ve kısaltmalar...** tablosunu seçiyoruz ancak söz konusu tablonun verilerini istediğimiz ölçüde küçültmek için biraz şekillendirme yapmamız gerekir.

> [!TIP]
> Aşağıdaki adımları daha hızlı veya kolay bir şekilde gerçekleştirmenin bir yolu var mı? Evet, iki tablo arasında *ilişki* oluşturabilir ve verileri bu ilişkiye göre şekillendirebiliriz. Aşağıdaki adımlar tablolarla çalışma konusunda öğrenilmesi gereken adımlardır ancak ilişkilerin birden fazla tablodaki verileri hızlı bir şekilde kullanmanıza yardımcı olduğunu bilmenizde yarar vardır.
> 
> 

Bu verileri şekillendirmek için aşağıdaki adımları uygularız:

* Üst satırı kaldırma: Bu, Web sayfasına ilişkin tablonun oluşturulma biçiminin bir sonucudur ve bu satıra ihtiyacımız yok. **Giriş** şeridinde, **Satırları Azalt \> Satırları Kaldır \> Üst Satırları Kaldır** seçeneğini belirleyin.

![](media/desktop-shape-and-combine-data/shapecombine_removetoprows.png)

Kaldırmak istediğiniz sütun sayısını belirtmenizi sağlayan **Üst Satırları Kaldır** penceresi görünür.

>[!NOTE]
>Power BI, tablo üst bilgilerini veri tablonuzdaki bir satır olarak yanlışlıkla içeri aktarırsa, tablonuzu düzeltmek için **Giriş** sekmesinden veya şeritteki **Dönüştür** sekmesinden **İlk Satırı Üst Bilgi Olarak Kullan** seçeneğini belirleyebilirsiniz.

* Alttaki 26 satırı kaldırma: Bölgeleri belirten bu satırlara ihtiyacımız yoktur. **Giriş** şeridinde, **Satırları Azalt \> Satırları Kaldır \> Alt Satırları Kaldır** seçeneğini belirleyin.

![](media/desktop-shape-and-combine-data/shapecombine_removebottomrows.png)

* RetirementStats tablosunda Washington DC için bilgi bulunmadığından bunu listemizde filtrelememiz gerekir. Region Status sütununun yanındaki açılan menü okunu seçin ve ardından **Federal district** seçeneğinin yanındaki onay kutusunu temizleyin.

![](media/desktop-shape-and-combine-data/shapecombine_filterdc.png)

* Gereksiz sütunları kaldırma: Yalnızca eyaletleri iki harfli resmi kısaltmalarıyla eşlememiz gerekiyor, bu nedenle aşağıdaki sütunları kaldırabiliriz: **Sütun1**, **Sütun3**, **Sütun4** ve ardından **Sütun6** ile **Sütun11** arası. İlk olarak **Sütun1**’i seçin ve ardından **CTRL** tuşunu basılı tutarak (bitişik olmayan birden çok sütunu seçmenizi sağlar), kaldırılacak diğer sütunları seçin. Şeritteki Giriş sekmesinde, **Sütunları Kaldır \> Sütunları Kaldır** seçeneğini belirleyin.

![](media/desktop-shape-and-combine-data/shapecombine_removecolumns.png)

>[!NOTE]
>Sorgu Düzenleyicisi'nde uygulanan adımların *sırasının* önemli olduğuna ve verilerin nasıl şekilleneceğini etkileyebildiğine değinmenin zamanı geldi. Bir adımın sonraki bir adımı nasıl etkileyebileceği üzerinde düşünmekte de yarar vardır. Uygulanan Adımlar'daki bir adımı kaldırmanız durumunda, sorgunun adım sıralamasına etkisi nedeniyle sonraki adımlar başta planlandığı gibi davranış göstermeyebilir.

>[!NOTE]
>Sorgu Düzenleyicisi penceresini genişlik azalacak şekilde yeniden boyutlandırdığınızda, bazı şerit öğeleri, görünür alandan en iyi şekilde yararlanılmasını sağlayacak şekilde daraltılır. Sorgu Düzenleyicisi penceresinin genişliğini artırdığınızda ise şerit öğeleri, artırılmış şerit alanından en iyi şekilde yararlanılması için genişletilir.

* Sütunları ve tabloyu daha önce de yaptığımız gibi yeniden adlandırın. Bir sütunu birkaç şekilde yeniden adlandırabilirsiniz: İlk olarak sütunu seçin ve ardından şeritteki **Dönüştür** sekmesinde bulunan **Yeniden Adlandır**'ı seçin veya sütuna sağ tıklayıp **Yeniden Adlandır…** seçeneğini (görünen menüden) belirleyin. Söz konusu iki seçenek aşağıdaki görüntüde oklarla gösterilmiştir; bunlardan birini seçmeniz yeterlidir.

![](media/desktop-shape-and-combine-data/shapecombine_rename.png)

Sütunları *State Name* ve *State Code* olarak yeniden adlandıralım. Tabloyu yeniden adlandırmak için, adı **Sorgu Ayarları** bölmesindeki **Ad** kutusuna yazmanız yeterlidir. Bu tabloya *StateCodes* adını verelim.

StateCodes tablosunu istediğimiz biçimde şekillendirdiğimize göre, bu iki tabloyu veya sorguyu bir tane olacak şekilde birleştirebiliriz. Şu anda sahip olduğumuz tablolar verilere uyguladığımız sorgular sonucunda elde edildiğinden, bunlar genellikle *sorgu* olarak adlandırılır.

Sorguları birleştirmek için izlenebilecek, *birleştirme* ve *ekleme* olmak üzere iki temel yol bulunur.

Bir veya daha fazla sütunu başka bir sorguya eklemek istediğinizde sorguları **birleştirirsiniz**. Var olan bir sorguya eklemek istediğiniz ek veri satırları olduğunda sorguyu **eklersiniz**.

Bu örnekte sorguları birleştirmek istiyoruz. Başlamak için, Sorgu Düzenleyicisi'nin sol bölmesinde, diğer sorguyu *hangi* sorguyla birleştirmek istediğimizi (bu örnekte *RetirementStats*) seçeriz. Ardından, şeritte **Giriş** sekmesinde bulunan **Birleştir \> Sorguları Birleştir** seçeneğini belirleriz.

![](media/desktop-shape-and-combine-data/shapecombine_mergequeries.png)

Verilerin, aktarılmasını istemediğiniz veriler dahil edilmeden veya aktarılmadan birleştirildiğinden emin olmak için gizlilik düzeyleri belirlemeniz istenebilir.

Seçilen tablo ile hangi tabloyu birleştirmek istediğimizi belirleyeceğimiz ve ardından birleştirme için kullanılacak eşleşen sütunları seçeceğimiz **Birleştir** penceresi görüntülenir. *RetirementStats* tablosunda (sorgu) State seçeneğini belirleyin ve ardından *StateCodes* sorgusunu seçin. (Yalnızca iki sorgu bulunduğundan bu örnekte seçim yapmak kolaydır. Birçok veri kaynağına bağlandığınızda arasından seçim yapmanız gereken birçok sorguyla karşılaşırsınız.) Eşleşen doğru sütunları seçtiğimizde (*RetirementStats* tablosundaki **State** sütunu ve *StateCodes* tablosundaki **State Name** sütunu), **Birleştir** penceresi aşağıdaki gibi görünür ve **Tamam** düğmesi etkin hale gelir.

![](media/desktop-shape-and-combine-data/shapecombine_merge2.png)

Sorgunun sonunda, var olan sorguyla birleştirilen tablonun (sorgunun) içeriği olan **NewColumn** oluşturulur. Birleştirilen sorgunun tüm sütunları **NewColumn**'da yer alacak şekilde daraltılır, ancak **Genişlet** seçeneğini belirleyerek tabloyu genişletebilir ve istediğiniz sütunları dahil edebilirsiniz.

![](media/desktop-shape-and-combine-data/shapecombine_mergenewcolumn.png)

Birleştirilen tabloyu Genişletmek ve hangi sütunların ekleneceğini belirlemek için genişlet simgesini (![Genişlet](media/desktop-shape-and-combine-data/icon.png)) seçin. **Genişlet** penceresi görünür.

![](media/desktop-shape-and-combine-data/shapecombine_mergeexpand.png)

Bu örnekte yalnızca **State Code** sütununu istediğimizden, yalnızca bu sütunu seçer ve ardından **Tamam** seçeneğini belirleriz. Ön ek olarak orijinal sütun adını kullan ayarına ihtiyacımız olmadığından veya bunu istemediğimizden ilgili onay kutusunu temizleriz. Bu onay kutusunu seçili bırakırsak, birleştirilen sütun **NewColumn.State Code** (sırasıyla orijinal sütun adı veya **NewColumn**, bir nokta ve sorguya aktarılan sütunun adı) şeklinde adlandırılır.

>[!NOTE]
>Söz konusu **NewColumn** tablosunu elde etme konusunda birkaç deneme yapmak ister misiniz? Biraz deneme yapabilirsiniz ve sonuçları beğenmezseniz **Sorgu Düzenleyicisi** bölmesindeki **Uygulanan Adımlar**'dan bu adımı silmeniz yeterlidir. Sorgunuz, bu **Genişlet** adımı uygulanmadan önceki haline geri döner. Bu işlem, genişletme işlemi istediğiniz gibi görünene dek dilediğiniz kadar tekrarlayabileceğiniz bir serbest tekrarlama gibidir.

Her biri ihtiyaçlarımıza göre şekillendirilmiş iki veri kaynağının birleştirildiği tek bir sorgu (tablo) elde etmiş olduk. Bu sorgu, herhangi bir eyaletteki konut maliyeti istatistikleri, demografik bilgiler veya iş fırsatları gibi ilgi çekici diğer birçok veri bağlantısı için temel oluşturabilir.

Değişiklikleri uygulamak ve Sorgu Düzenleyicisi’ni kapatmak için, şeritteki **Giriş** sekmesinde **Kapat ve Uygula** seçeneğini belirleyin. Dönüştürülmüş veri kümesi, rapor oluşturmak için kullanılmaya hazır bir şekilde Power BI Desktop'ta görüntülenir.

![](media/desktop-shape-and-combine-data/shapecombine_closeandapply.png)

## <a name="next-steps"></a>Sonraki adımlar
Power BI Desktop ile yapabileceğiniz çok şey var. Özellikler hakkında daha fazla bilgi edinmek için aşağıdaki kaynaklara bakın:

* [Power BI Desktop nedir?](desktop-what-is-desktop.md)
* [Power BI Desktop ile Sorgulara Genel Bakış](desktop-query-overview.md)
* [Power BI Desktop'ta Veri Kaynakları](desktop-data-sources.md)
* [Power BI Desktop'taki Verilere Bağlanma](desktop-connect-to-data.md)
* [Power BI Desktop'taki Genel Sorgu Görevleri](desktop-common-query-tasks.md)   

