---
title: Power BI Desktop’ta Bileşik Modelleri (Önizleme) Kullanma
description: Power BI Desktop'ta birden çok veri bağlantısı ve çoka çok ilişkileriyle veri modelleri oluşturun
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.component: powerbi-desktop
ms.topic: conceptual
ms.date: 07/23/2018
ms.author: davidi
LocalizationGroup: Transform and shape data
ms.openlocfilehash: 4f882865271411d04a99c9213a68df24d000677d
ms.sourcegitcommit: 6faeb642721ee5abb41c04a8b729880c01c4d40e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2018
ms.locfileid: "39211793"
---
# <a name="composite-models-in-power-bi-desktop-preview"></a>Power BI Desktop’ta bileşik modeller (Önizleme)

Daha önce **Power BI Desktop**'ta raporda bir DirectQuery kullandığınızda, bu rapor için ister DirectQuery ister Import olsun başka hiçbir veri bağlantısına izin verilmiyordu. **Karma modellerle** bu kısıtlama kalktı. Bir rapor birden çok DirectQuery veya içeri aktarma veri bağlantısından ya da sizin seçtiğiniz herhangi bir bileşimde veri bağlantıları içerebilir.

![Power BI Desktop’ta bileşik modeller](media/desktop-composite-models/composite-models_01.png)

**Power BI Desktop**'taki **bileşik modeller** özelliği birbiriyle ilgili üç özellikten oluştur:

* **Bileşik modeller** - raporda DirectQuery bağlantıları ve içeri aktarma da dahil olmak üzere herhangi bir birleşimde birden çok veri bağlantısına izin verir.
* **Çoka çok ilişkiler** - **bileşik modellerle** tablolar arasında **çoka çok ilişkiler** kurabilir, tablolarda benzersiz değer gereksinimlerini kaldırabilir ve yalnızca ilişkileri kurmak için yeni tablolar ekleme gibi önceden yapılacak geçici düzeltmelerden kurtulabilirsiniz. 
* **Depolama modu** - DirectQuery temelinde olsa bile arka uç veri kaynaklarını sorgulama gerektiren ve gerektirmeyen hangi görsellerin içeri aktarılacağını belirtebilir, böylelikle performansı geliştirir ve arka uç yükünü azaltırsınız. Daha önce, sorguları başlatan dilimleyiciler gibi basit görseller bile arka uç kaynaklara gönderiliyordu. 

**Bileşik modeller** için birbiriyle ilgili bu özellik koleksiyonundaki üç özelliğin her biri ayrı makalelerde ele alınıyor:

* **Bileşik modeller**, bu makalede ayrıntılı olarak açıklanıyor.
* **Çoka çok ilişkiler** kendi makalesinde ([Power BI Desktop'ta çoka çok ilişkiler (Önizleme)](desktop-many-to-many-relationships.md)) açıklanıyor.
* **Depolama modu** kendi makalesinde ([Power BI Desktop'ta depolama modu (Önizleme)](desktop-storage-mode.md)) açıklanıyor.

## <a name="enabling-the-composite-models-preview-feature"></a>Bileşik modeller önizleme özelliğini etkinleştirme

**Bileşik modeller** özelliği Önizleme aşamasındadır ve **Power BI Desktop**'ta etkinleştirilmesi gerekir. **Bileşik modeller** özelliğini etkinleştirmek için, **Dosya > Seçenekler ve Ayarlar > Seçenekler > Önizleme Özellikleri**’ni seçin ve ardından **bileşik modeller** onay kutusunu işaretleyin. 

![önizleme özelliklerini etkinleştirme](media/desktop-composite-models/composite-models_02.png)

Özelliğin etkinleştirilmesi için **Power BI Desktop**'ı yeniden başlatmanız gerekir.

![değişikliklerin geçerlilik kazanması için yeniden başlatma gerekiyor](media/desktop-composite-models/composite-models_03.png)


## <a name="using-composite-models"></a>Bileşik modelleri kullanma

**Bileşik modellerle** **Power BI Desktop**'ı veya **Power BI hizmetini** kullanırken her türde farklı veri kaynağına bağlanabilir ve bu veri bağlantılarını farklı şekillerde gerçekleştirebilirsiniz. En çok kullanılan veri alma yöntemi olan içeri aktarma seçeneğini kullanarak Power BI'a veri aktarabilir veya DirectQuery'yi kullanarak verilerin bulunduğu özgün kaynak deposuna doğrudan bağlanabilirsiniz. DirectQuery'yle ilgili ayrıntılar hakkında daha fazla bilgiyi [Power BI'da DirectQuery kullanma](desktop-directquery-about.md) makalesinde bulabilirsiniz.

DirectQuery **bileşik modellerle** kullanıldığında, aşağıdakileri gerçekleştiren bir Power BI modeli (tek bir .pbix Power BI Desktop dosyası gibi) oluşturmak mümkündür:

* bir veya birden çok DirectQuery kaynağından verileri birleştirme ve/veya
* DirectQuery kaynaklarından verileri birleştirme ve verileri içeri aktarma

Örneğin, **bileşik modellerle** bir kurumsal veri ambarındaki satış verilerini departman SQL Server veritabanındaki satış hedefi verileriyle birleştiren, ayrıca bir elektronik tablodan bazı verileri içeri aktaran bir model oluşturmak mümkün olur. Birden çok DirectQuery kaynağından verileri birleştiren veya DirectQuery'yi içeri aktarılan verilerle birleştiren modeller, *bileşik model* olarak adlandırılır.

> [!NOTE]
> Bileşik modeller Önizleme aşamasındayken, bileşik modelleri Power BI hizmetine yayımlamak mümkün değildir. 

Tablolar farklı kaynaklardan geliyor olsa bile, her zaman yaptığınız gibi tablolar arasında ilişkiler oluşturabilirsiniz; ama şu kısıtlamalar söz konusudur: kaynaklar arası kurulan tüm ilişkiler, gerçek kardinalitesi ne olursa olsun **Çoka Çok** kardinalitesi olacak şekilde tanımlanır. Bu tür ilişkilerin davranışı da [Power BI Desktop'ta çoka çok ilişkileri (Önizleme)](desktop-many-to-many-relationships.md) makalesinde açıklandığı gibi normal **Çoka Çok**  ilişkileriyle aynıdır. Bileşik modeller bağlamında, gerçekte içeri aktarıldıkları temel veri kaynağından bağımsız olarak tüm içeri aktarılan tabloların aslında tek bir kaynak olduğunu unutmayın.   

## <a name="example-of-using-composite-models"></a>Bileşik modelleri kullanma örnekleri

**Bileşik model** örneği olarak, DirectQuery kullanarak bir şirket veri ambarına (SQL Server'da) bağlanan bir rapor düşünün ve veri ambarı da aşağıdaki resimde gösterildiği gibi *Sales by Country*, *Quarter* ve *Bike (Product)* verilerini içeriyor olsun.

![bileşik modeller için ilişki görünümü](media/desktop-composite-models/composite-models_04.png)

Bu noktada, bu kaynaktan alanları kullanarak basit görseller oluşturabilirsiniz. Örneğin, aşağıdaki görselde seçili üç aylık dönemde *ProductName* alanına göre toplam satış tutarı gösterilir. 

![verilere dayanan görsel](media/desktop-composite-models/composite-models_05.png)

Ama, her ürüne atanmış olan Ürün Yöneticisi (Product Manager) ile pazarlama önceliği hakkında ve bu verilerin Excel elektronik tablosunun neresinde tutulduğu hakkında bilginiz olsa nasıl olurdu? Ürün Yöneticisi'ne (*Product Manager*) göre Satış Tutarı'nı (*Sales Amount*) görmek isteyebilirsiniz, ancak bu yerel verilerin şirket veri ambarına eklenmesi mümkün olmayabilir veya en iyi olasılıkla aylar sürebilir. Bu satış verilerinin veri ambarından içeri aktarılması (DirectQuery kullanmak yerine) mümkün olabilir; bu noktada bu veriler elektronik tabloda içeri aktarılan verilerle birleştirilebilir. Bu yaklaşım, temel kaynakta zorunlu tutulan güvenlik kurallarının herhangi bir bileşimi, en son verileri görebilme gereği ve verilerin çok büyük ölçekli olması gibi en başta DirectQuery'nin kullanılmasına yol açan nedenlerden dolayı mantıklı değildir. 

İşte bu noktada **bileşik modeller** devreye girer. Bileşik modeller size DirectQuery kullanarak veri ambarına bağlanma ve ardından ek kaynaklar için GetData kullanma seçeneği getirir. Bu durumda, şirket veri ambarına DirectQuery bağlantısı kurarız, ardından GetData kullanıp Excel'i seçeriz, yerel verilerimizi içeren elektronik tabloya gideriz ve *ProductNames*, atanan *SalesManager* ve *Priority* verilerini içeren sayfayı içeri aktarabiliriz.  

![Gezgin penceresi](media/desktop-composite-models/composite-models_06.png)

Şimdi, **Alanlar** listesinde özgün *Bike* tablosunu (SQL Server'dan) ve yeni *Product Managers* tablosunu (Excel'den içeri aktarılmış verilerle) görürüz. 

![Tabloların Alanlar görünümü](media/desktop-composite-models/composite-models_07.png)

Benzer biçimde, **Power BI Desktop**'ta **İlişki Görünümü**'ne baktığımızda artık *Product Managers* adlı ek tabloyu görürüz. 

![tabloların ilişki görünümü](media/desktop-composite-models/composite-models_08.png)

Şimdi bunları modeldeki diğer tablolarla ilişkilendirmemiz gerekir ve bu işlemi her zaman yaptığımız gibi, *Bike* tablosuyla (SQL Server'da) *Product Managers* tablosu (içeri aktarılan) arasında ilişki oluşturarak (*Bike[ProductName]* ile *ProductManagers[ProductName]* arasında olduğu gibi) yaparız. Bu makalenin başlarında açıklandığı gibi, kaynaktan geçen tüm ilişkilerin kardinalitesi **Çoka Çok** olmalıdır ve bu seçilen varsayılan kardinalitedir. 

![ilişki oluşturma iletişim kutusu](media/desktop-composite-models/composite-models_09.png)

Bu ilişki oluşturulduktan sonra, tahmin edebileceğimiz gibi ilişki **Power BI Desktop**'ta **İlişki Görünümü**'nde gösterilir.

![yeni ilişki görünümü](media/desktop-composite-models/composite-models_10.png)

Bu tablo ilişkileri kurulunca, artık **Alanlar** listesindeki alanlardan herhangi birini kullanarak görseller oluşturabilir, birden çok kaynaktan gelen verileri sorun yaşamadan karıştırabiliriz. Örneğin, aşağıdaki görselde her *Product Manager* için *Sales Amount* değerleri gösterilir. 

![Alanlar bölmesinin gösterildiği görsel](media/desktop-composite-models/composite-models_11.png)

Bu örnekte bir *boyut* tablosunun (*Product* veya *Customer* gibi) başka bir yerden içeri aktarılmış bazı ek verilerle genişletildiği yaygın bir durum gösterilir ve tabloların farklı kaynaklara bağlantıyla DirectQuery kullanması da mümkündür. Dolayısıyla, örneğimizi genişletmek için *Country* (Ülke) ve *Period* (Dönem) başına *SalesTargets* (Satış Hedefleri) değerlerinin ayrı bir departman veritabanında depolandığını düşünelim. Aşağıdaki görüntüde de gösterildiği şekilde, her zaman yapabileceğiniz gibi bu verilere bağlanmak için **GetData** kullanabilirsiniz. 

![Gezgin iletişim kutusu](media/desktop-composite-models/composite-models_12.png)

Ardından, bu örnekte daha önce yaptığımıza benzer şekilde, yeni tabloyla modeldeki diğer tablolar arasında ilişkiler oluşturabilir ve bunların verilerini birleştiren görseller oluşturabiliriz. Şimdi genişletilmiş örnek senaryomuzda yeni ilişkiler kurduğumuz **İlişkiler Görünümü**'ne yeniden bakalım.

![birçok tablosu olan ilişki görünümü](media/desktop-composite-models/composite-models_13.png)

Yeni verilere ve az önce oluşturduğumuz ilişkilere dayanan aşağıdaki görüntüde gösterildiği gibi, sol alt köşedeki görselde *Target* (Hedef) değerine göre *Sales Amount* (Satış Tutarı) gösterilir, farkı gösteren varyans hesaplaması vardır ve buradaki *Sales Amount* ile *Target* iki farklı SQL Server veritabanlarından gelir. 

![daha fazla veri gösteren görsel](media/desktop-composite-models/composite-models_14.png)

## <a name="setting-storage-mode"></a>Depolama modunu ayarlama

**Bileşik modeldeki** her tablo, tablonun DirectQuery'ye veya içeri aktarmaya dayanıp dayanmadığını gösteren bir **depolama moduna** sahiptir. **Depolama modu**, **Özellik** bölmesinde görüntülenebilir ve değiştirilebilir. Oraya ulaşmak için, **Alanlar** listesinin sağ tıklama bağlam menüsünden **Özellikler**'i seçin. Aşağıdaki görüntüde **depolama modu** gösterilir (bölmenin genişliğinden dolayı görüntüde **Storage ...** olarak kısaltılmıştır).

![Depolama modu ayarı](media/desktop-composite-models/composite-models_15.png)

**Depolama modu** her tablonun araç ipucunda da görülebilir.

![depolama modunun bulunduğu araç ipucu](media/desktop-composite-models/composite-models_16.png)

DirectQuery'den bazı dosyalar ve bazı içeri aktarma tabloları içeren herhangi bir **Power BI Desktop** dosyası (.pbix dosyası) için, durum çubuğunda **depolama modu** olarak **Karma** terimi gösterilir. Durum çubuğunda bu terime tıklayabilir ve tüm tabloları kolayca içeri aktarmaya geçirebilirsiniz.

**Depolama modu** hakkındaki ayrıntılar, [Power BI Desktop'ta depolama modu (Önizleme)](desktop-storage-mode.md) makalesinde tümüyle açıklanmıştır.  

## <a name="calculated-tables"></a>Hesaplanan tablolar

Hesaplanan tablolar DirectQuery kullanan bir modele eklenebilir ve hesaplanan tabloyu tanımlayan DAX içeri aktarılan veya DirectQuery tablolarına veya her ikisinin bir bileşimine başvurabilir. 

Hesaplanan tablolar her zaman içeri aktarılır ve söz konusu tablolardaki veriler tablo yenilendiğinde yenilenir. Bu nedenle, hesaplanan tablolar bir DirectQuery tablosuna başvurursa, DirectQuery tablosuna başvuran görseller her zaman temel tablodaki en son değerleri gösterir, ama hesaplanan tabloya başvuran görseller hesaplanan tablonun son yenilenme zamanındaki verileri gösterir.

## <a name="security-implications"></a>Güvenlik Üzerindeki Etkileri 

Bileşik modellerin güvenlik üzerinde bazı etkileri vardır. Bir veri kaynağına gönderilen sorgu başka bir kaynaktan alınmış olan veri değerlerini içerebilir. Bu makalede daha önce açıklanan örnek için, *Product Manager*'a göre *Sales Amount* değerini gösteren görsel **Sales** ilişkisel veritabanına bir SQL sorgusunun gönderilmesine neden olur ve bu SQL sorgusu *Product Managers* adlarını ve bunlarla ilişkilendirilmiş *Products* değerlerini içerebilir. 

![güvenlik etkilerini gösteren betik](media/desktop-composite-models/composite-models_17.png)

Bu nedenle, elektronik tabloda depolanan bilgiler şimdi ilişkisel veritabanına gönderilen sorguya eklenir. Bu bilgiler gizliyse, bunun güvenlik üzerindeki etkileri dikkate alınmalıdır. Özellikle aşağıdaki etkileri dikkate almanız gerekir:

* Veritabanının izleme veya denetim günlüklerini görebilen yöneticiler, özgün kaynağındaki veriler üzerinde izinlere (bu örnekte Excel dosyası izinleri) sahip olmasalar bile bu bilgileri de görebilir.

* Bir kaynaktan bilgileri şifreli bağlantıyla alma ama sonra yanlışlıkla bu bilgileri şifrelenmemiş bağlantı kullanarak başka bir kaynağa gönderilen sorguya ekleme gibi bir durumdan kaçınmak için her kaynağın şifreleme ayarları dikkate alınmalıdır. 

Tüm güvenlik etkilerinin dikkate alınmasını sağlamak için, bileşik model oluşturmaya yönelik bir eylem gerçekleştirildiğinde **Power BI Desktop** uyarı iletisi görüntüler.  

Benzer nedenlerle, güvenilmeyen bir kaynaktan gönderilen **Power BI Desktop** dosyaları açılırken de dikkat edilmelidir. Söz konusu dosya bileşik modeller içeriyorsa, bu bir kaynaktan alınan bilgilerin (dosyayı açan kullanıcının kimlik bilgileri kullanılarak) sorgunun parçası olarak başka bir veri kaynağına gönderilebileceği (burada Power BI Desktop dosyasının kötü amaçlı yazarı tarafından görülebilir) anlamına gelir. Bu nedenle, Power BI Desktop dosyasını ilk kez açarken, dosya birden çok kaynak içeriyorsa uyarı görüntülenir. Bu uyarı, yerel SQL sorguları içeren bir dosya açılırken görüntülenen uyarıya benzer.  

## <a name="performance-implications"></a>Performans Üzerindeki Etkileri  

DirectQuery kullanılırken, öncelikle arka uç kaynağının kullanıcılara iyi bir deneyim sağlamaya yetecek kaynakları olduğundan emin olmak için performans konusu dikkate alınmalıdır. İyi bir deneyim görsellerin 5 saniyede veya daha hızlı yenilenebilmesi anlamına gelir. Ayrıca, [Power BI'da DirectQuery kullanma](desktop-directquery-about.md) makalesindeki performans önerisine de uymalısınız. Bileşik modellerin kullanımı performansla ilgili olarak dikkate alınması gereken ek noktalar getirir, çünkü çoğunlukla bir sorgunun sonuçlarını ikinci bir kaynağa geçirme yoluyla tek bir görsel birden çok kaynağa sorgu gönderilmesi sonucunu verebilir. Bu durum sonucunda aşağıdaki olası yürütme biçimleri söz konusu olabilir:

* **Çok fazla sayıda hazır değer içeren bir SQL sorgusu** - örneğin, bir dizi seçili *Product Managers* için (elektronik tablodan içeri aktarılmış olan ilişkili tablodan) toplam *Sales Amount* (SQL veritabanından) değerini isteyen bir görselin, *WHERE* yan tümcesinde tüm ürün kimliklerini içeren bir SQL sorgusu göndermeden önce söz konusu Ürün Yöneticileri (Product Managers) tarafından yönetilmiş *Products* (Ürünler) değerlerini bulması gerekebilir.

* **Daha düşük bir ayrıntı düzeyinde, o sırada yerel olarak toplanmış verilerle sorgulayan bir SQL sorgusu** - bu listenin önceki madde işaretli öğesiyle aynı örnek kullanıldığında, *Product Manager* filtresine uyan *Products* sayısının çok fazla artmasıyla, belirli bir noktada bunların tümünü *WHERE* yan tümcesine eklemek verimsiz veya imkansız hale gelir. Bunun yerine, ilişkisel kaynağı daha düşük bir *Product* düzeyinde sorgulamak ve ardından sonuçları yerel olarak toplamak gerekir. *Products*'ın kardinalitesi 1 milyon sınırını aşarsa, sorgu başarısız olacaktır.

* **Değere göre grup başına bir sorgu olmak üzere birden çok SQL sorgusu** - toplamada başka bir kaynaktan bir sütuna göre gruplandırılmış **DistinctCount** (Ayrı Sayım) kullanıldığında, dış kaynak gruplandırmayı tanımlayan birçok hazır değerin verimli bir şekilde geçirilmesini desteklemiyorsa, değere göre grup başına bir SQL sorgusu göndermek gerekebilir. Örneğin, *Product Manager*'a (elektronik tablodan içeri aktarılmış ilişkili tabloda) göre *CustomerAccountNumber* (SQL Server tablosundan) ayrı sayımını isteyen bir görselin, SQL Server'a gönderilen sorgudaki *Product Managers* tablosundan ayrıntıları geçirmesi gerekebilir. Diğer kaynaklar, örneğin Redshift üzerinde bu mümkün değildir ve bunun yerine *Sales Manager* başına bir SQL sorgusu olabilir (belirli bir uygulama sınırına kadar; bu sınırdan sonra sorgu başarısız olacaktır). 

Bu durumlardan her birinin performans üzerinde kendi etkileri vardır ve tam ayrıntılar her veri kaynağında değişiklik gösterir. İki kaynağı birleştiren ilişkide kullanılan sütunların kardinalitesinin düşük kalması (birkaç bin) iyi bir kuraldır çünkü böylelikle performans üzerinde önemli bir etkisi olmaz. Kardinalite arttıkça, sonuçta elde edilecek performans üzerindeki etkinin daha fazla dikkate alınması gerekir. 

Bunlara ek olarak, **çoka çok** ilişkilerinin kullanılması ayrıntılı değerleri yerel olarak toplamak yerine her toplam/alt toplam düzeyi için temel kaynağa ayrı sorguların gönderilmesi gerektiği anlamına gelir. Bu nedenle, toplamları olan basit bir tablo görseli bir yerine iki SQL sorgusu gönderir. 

## <a name="limitations-and-considerations"></a>Sınırlamalar ve önemli noktalar

**Bileşik modellerin** bu sürümünde birkaç sınırlama vardır.

Aşağıdaki çok boyutlu kaynaklar **bileşik modellerle** kullanılamaz:

* SAP HANA
* SAP Business Warehouse
* SQL Server Analysis Services
* Power BI veri kümeleri

Söz konusu çok boyutlu kaynaklara DirectQuery kullanarak bağlandığınızda, başka bir DirectQuery kaynağına bağlanamaz veya içeri aktarılan verilerle birleştiremezsiniz.

DirectQuery kullanımının mevcut sınırlamaları **bileşik modelleri** kullanırken de geçerlidir. Bu sınırlamaların birçoğu şimdi tablonun **depolama moduna** bağlı olarak tablo başına uygulanır. Örneğin, içeri aktarılan tablodaki hesaplanan sütun başka tablolara başvurabilir ama DirectQuery tablosundaki hesaplanan sütunun başvurabileceği sütunlar yine aynı tablodaki sütunlarla sınırlıdır. Model içindeki tablolardan herhangi biri DirectQuery ise, diğer sınırlamalar modelin tamamına uygulanır. Örneğin, modelin içindeki tablolardan herhangi birinin **depolama modu** DirectQuery olduğunda, modelde **QuickInsights** ve **Soru ve Yanıt** özellikleri kullanılamaz. 

## <a name="next-steps"></a>Sonraki adımlar

Aşağıdaki makalelerde bileşik modellerle ilgili daha fazla açıklama ve DirectQuery'nin ayrıntılı açıklaması bulunabilir.

* [Power BI Desktop’ta çoka çok ilişkiler (Önizleme)](desktop-many-to-many-relationships.md)
* [Power BI Desktop’ta depolama Modu (Önizleme)](desktop-storage-mode.md)

DirectQuery makaleleri:

* [Power BI'da DirectQuery kullanma](desktop-directquery-about.md)
* [Power BI'da DirectQuery tarafından desteklenen veri kaynakları](desktop-directquery-data-sources.md)

