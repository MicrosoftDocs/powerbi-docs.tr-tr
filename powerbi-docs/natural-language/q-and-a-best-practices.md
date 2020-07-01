---
title: Soru-Cevap’ı iyileştirmek için en iyi yöntemler
description: Power BI Soru-Cevap’ı iyileştirme ve daha iyi çalışmasını sağlama
author: mohaali
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: how-to
ms.date: 10/23/2019
ms.author: mohaali
ms.openlocfilehash: a94f4bda1f7ebc4a612da65623f539e820c8c333
ms.sourcegitcommit: eef4eee24695570ae3186b4d8d99660df16bf54c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85240426"
---
# <a name="best-practices-to-optimize-qa-in-power-bi"></a>Power BI’da Soru-Cevap’ı iyileştirmek için en iyi yöntemler
Yaygın ifadeler ve doğal dil kullanarak verilerinize soru sorabilmek çok değerli bir olanaktır. Daha da değerlisi, verilerinizin yanıt vermesi. İşte Power BI’daki Soru-Cevap bunu yapar.

Yanıtlayabileceği büyük soru koleksiyonunu başarıyla yorumlayabileceği şekilde etkinleştirilmesi için Soru-Cevap özelliğinin modelle ilgili varsayımlar yapması gerekir. Modelinizin yapısı bu varsayımlardan birini veya daha fazlasını karşılamıyorsa modelinizi ayarlamanız gerekir. Bu Soru-Cevap ayarları, özelliği kullanıp kullanmadığınızdan bağımsız olarak Power BI’daki herhangi bir model için en iyi yöntem iyileştirmeleridir.

Aşağıdaki bölümlerde, modelinizi nasıl Power BI’daki Soru-Cevap ile iyi çalışacak şekilde ayarlayabileceğiniz açıklanmıştır.

## <a name="automatic-adjustments-that-qa-makes"></a>Soru-Cevap tarafından otomatik olarak yapılan ayarlamalar

### <a name="measure-tables"></a>Ölçü tabloları

Soru-Cevap’ın önceki sürümlerinde ölçü tabloları, temel alınan tablonun bağlantısı kesildiğinde Soru-Cevap’ta karışıklığa neden oluyordu. Soru-Cevap şu anda ölçü tablolarıyla sorunsuz bir şekilde çalışmaktadır.

### <a name="table-names-conflicting-with-column-names"></a>Sütun adlarıyla çakışan tablo adları

Soru-Cevap’ın önceki sürümlerinde bir tablo ve sütun aynı ada sahipse tablo öncelik kazanıyordu. Bu sorun giderildi ve artık modellerinizde bu sorunu düzeltmeniz gerekmiyor.

## <a name="manual-steps-to-improve-qa"></a>Soru-Cevap’ı iyileştirmeye yönelik el ile adımlar

### <a name="use-the-new-qa-tooling-to-fix-your-questions"></a>Sorularınızı düzeltmek için yeni Soru-Cevap aracını kullanın

Soru-Cevap aracıyla Soru-Cevap’a temel iş terimlerinizi öğretebilir ve son kullanıcılarınızın sorduğu soruları düzeltebilirsiniz. Bazı durumlarda, veriler hatalı şekillendirildiğinden veya veriler eksik olduğundan bazı sorular düzeltilememektedir. Bu durumda, iyileştirmenize yardımcı olması için aşağıdaki diğer bölümleri okuyun. [Soru-Cevap araçları](q-and-a-tooling-intro.md) hakkında daha fazla bilgi edinin.

## <a name="add-missing-relationships"></a>Eksik ilişkileri ekleme

Modelinizde tablolar arası ilişkiler eksikse ne Power BI rapor oluşturur ne de Soru-Cevap bu tabloların nasıl birleştirileceğini yorumlayabilir. İlişkiler, iyi bir modelin köşetaşlarından biridir. Örneğin, *siparişler* tablosu ile *müşteriler* tablosu arasındaki ilişki eksikse “Seattle müşterileri için toplam satış miktarını” soramazsınız. Aşağıdaki resimlerde, üzerinde çalışılması gereken bir model ve Soru-Cevap için hazır olan bir model gösterilmektedir. 

**Üzerinde çalışılması gerekiyor**

İlk görüntüde Customers, Sales ve Products tabloları arasında bir ilişki yoktur.

![Soru-Cevap için üzerinde çalışılması gereken ilişkiler](media/q-and-a-best-practices/desktop-qna-01.png)

**Soru-Cevap için Hazır**

İlk görüntüde, tablolar arasında ilişkiler tanımlanmıştır.

![Soru-Cevap için kullanıma hazır olan ilişkiler](media/q-and-a-best-practices/desktop-qna-02.png)


## <a name="rename-tables-and-columns"></a>Tabloları ve sütunları yeniden adlandırma

Soru-Cevap için tablo ve sütun seçimi önemlidir. Örneğin, müşterilerinizin listesini içeren, *Müşteri Özeti* adlı bir tablonuz olduğunu varsayalım. “Chicago’daki müşterileri listele” yerine “Chicago’daki müşteri özetlerini listele” gibi sorular sormanız gerekir. 

Soru-Cevap, bazı temel sözcük bölme ve çoğul algılama işlemlerini gerçekleştirebilse de tablo ve sütun adlarınızın içeriği doğru bir şekilde yansıttığını varsayar.

Başka bir örnek verelim. Çalışanların adlarını ve soyadlarını ve çalışan numaralarını içeren *Çalışan Sayısı* adlı bir tablonuz olduğunu varsayın. Çalışan numaralarını, iş numaralarını ve başlangıç tarihlerini içeren *Çalışanlar* adlı başka bir tablonuz vardır. Modeli bilen kişiler bu yapıyı anlayabilir. “Çalışanların sayısını” soran birisi, “Çalışanlar” tablosundaki satır sayısını alacaktır. Bu sonuç, her bir çalışanın çalıştığı her bir işin sayısı olduğundan tam aklındaki şey olmayabilir. Bu tabloların içeriği doğru yansıtacak şekilde yeniden adlandırılması çok daha iyi olur.

**Üzerinde çalışılması gerekiyor**

*StoreInfo* ve *Product List* gibi tablo adlarının üzerinde çalışılması gerekir.

![Soru-Cevap için üzerinde çalışılması gereken tablo adları](media/q-and-a-best-practices/desktop-qna-03.png)

**Soru-Cevap için Hazır**

*Store* ve *Products* adlı tablolar daha çok işe yarar.

![Soru-Cevap için kullanıma hazır olan tablo adları](media/q-and-a-best-practices/desktop-qna-04.png)

## <a name="fix-incorrect-data-types"></a>Hatalı veri türlerini düzeltin

İçeri aktarılan veriler hatalı veri türleri içerebilir. Özellikle de *dize* olarak içeri aktarılan *tarih* and *sayı* sütunları, Soru-Cevap tarafından tarih ve sayı olarak yorumlanmaz. Power BI modelinizde doğru veri türünü seçtiğinizden emin olun.

![Soru-Cevap’ta kullanılabildiğinden emin olmak için doğru veri türünü seçin](media/q-and-a-best-practices/desktop-qna-05.png)

## <a name="mark-year-and-identifier-columns-as-dont-summarize"></a>Yıl ve tanımlayıcı sütunlarını Özetleme olarak işaretleyin

Power BI, varsayılan olarak sayısal sütunları agresif bir şekilde topladığından, “yıla göre toplam satış” gibi sorular bazen genel satış toplamının yanı sıra genel yıl toplamı gibi sonuçlara yol açabilir. Bu Power BI davranışını önlemek istediğiniz belirli sütunlarınız varsa bunlardaki **Varsayılan Özetleme** özelliğini **Özetleme** olarak ayarlayın. En sık sorun yaşatan sütunlar **yıl**, **ay**, **gün** ve **kimlik** sütunları olduğundan, bunlara özen gösterin. Toplanması mantıklı olmayan *yaş* gibi diğer sütunlar için de **Varsayılan Özetleme** özelliğinin **Özetleme** veya **Ortalama** olarak ayarlanması yararlı olabilir. Bu ayarı **Modelleme** sekmesinde bulabilirsiniz.

![Soru-Cevap için yıl, ay, tarih gibi sütunları Özetlemeyin](media/q-and-a-best-practices/desktop-qna-06.png)

## <a name="choose-a-data-category-for-each-date-and-geography-column"></a>Her tarih ve coğrafya sütunu için bir Veri Kategorisi seçin

**Veri Kategorisi**, bir sütunun içeriğiyle ilgili olarak veri türünün ötesinde ek anlamsal bilgi sağlar. Örneğin, bir tamsayı sütununu posta kodu olarak, bir dize sütununu Şehir, Ülke/Bölge vb. olarak işaretleyebilirsiniz. Soru-Cevap bu bilgileri iki önemli şekilde kullanır: Görselleştirme seçimi ve dil sapmaları için.

İlk olarak, Soru-Cevap ne tür görsel öğeler kullanılacağına karar verilmesine yardımcı olmak için **Veri Kategorisi** bilgilerini kullanır. Örneğin, tarih veya saat **Veri Kategorilerine** sahip olan sütunları genellikle bir çizgi grafiğin yatay ekseni ya da bir kabarcık grafiğinin oynatma ekseni için iyi bir tercih olarak tanır. Coğrafi **Veri Kategorilerine** sahip sütunları içeren sonuçlarınsa bir haritada iyi görünebileceğini varsayar.

İkinci olarak, Soru-Cevap belirli soru türlerinin anlaşılmasını kolaylaştırmak için kullanıcıların tarih ve coğrafya sütunları hakkında nasıl konuşabileceğine dair bilgiye dayalı bazı tahminler yapar. Örneğin, “A kişisi ne zaman işe alındı? sorusundaki “ne zaman” ifadesinin bir tarih sütunuyla eşlenmesi neredeyse kesindir ve “Ağrıdaki müşterileri say” sorusundaki “Ağrı” sözcüğünün bir hastalıktan ziyade bir şehri ifade etmesi daha olasıdır.

![Soru-Cevap için Veri Kategorilerini doğru şekilde seçin](media/q-and-a-best-practices/desktop-qna-07.png)

## <a name="choose-a-sort-by-column-for-relevant-columns"></a>İlgili sütunlar için bir Sütuna Göre Sıralama seçin

**Sütuna Göre Sırala** özelliği, bir sütundaki sıralamanın otomatik olarak bunun yerine başka bir sütuna göre uygulanmasına imkan tanır. Örneğin, “müşterileri gömlek bedenine göre sırala” komutunu verirseniz muhtemelen Gömlek Bedeni sütununuzun alfabetik sıralama (L, M, S, XL, XS) yerine temel beden numarasına göre (XS, S, M, L, XL) sıralanmasını istersiniz.

![Soru-Cevap için Sütuna Göre Sırala seçimini doğru yapın](media/q-and-a-best-practices/desktop-qna-08.png)

## <a name="normalize-your-model"></a>Modelinizi normalleştirin

Tabii ki modelinizi tamamen yeniden şekillendirmeniz gerektiğini söylemiyoruz. Ancak belirli yapılar çok zor olduğundan Soru-Cevap tarafından düzgün işlenmez. Modelinizin yapısında bazı temel normalleştirme işlemleri gerçekleştirirseniz, hem Power BI raporlarının kullanılabilirliği hem de Soru-Cevap sonuçlarının doğruluğu önemli ölçüde artar.

Bu genel kuralı izleyin: Kullanıcının bahsettiği her benzersiz “şey”, tam olarak bir model nesnesiyle (tablo veya sütun) temsil edilmelidir. Kullanıcılarınız müşterilerden bahsediyorsa bir *müşteri* nesnesi olmalıdır. Kullanıcılarınız satıştan bahsediyorsa bir *satış* nesnesi olmalıdır. Kulağa basit geliyor, değil mi? Başlangıçta sahip olduğunuz verilerin durumuna bağlı olarak basit olabilir. Gerekirse **Sorgu Düzenleyicisi**’ndeki zengin veri biçimlendirme özelliklerinden yararlanabilirsiniz, ancak daha basit olan çoğu işlem yalnızca Power BI modelindeki hesaplamalar kullanılarak gerçekleştirilebilir.

Aşağıdaki bölümler, gerçekleştirmeniz gerekebilecek bazı yaygın dönüşümleri içermektedir.

### <a name="create-new-tables-for-multi-column-entities"></a>Çok sütunlu varlıklar için yeni tablolar oluşturun

Daha büyük bir tablo içinde tek başına ayrı bir birim görevi gören birden çok sütununuz varsa, bu sütunlar bir tablo olarak ayrılmalıdır. Örneğin, *Şirketler* tablonuzda bir Kişi Adı, Kişi Unvanı ve Kişi Telefonu sütununuz olduğunu varsayın. Ad, Unvan, Telefon ve *Şirketler* tablosunun geri bağlantısını içerecek ayrı bir *Kişiler* tablosu olması daha iyi bir tasarımdır. Bu, hangi şirkette çalıştıkları fark etmeksizin ilgili kişiler hakkında şirketlerden bağımsız olarak sorular sormayı kolaylaştırır ve görüntüleme esnekliğini geliştirir.

**Üzerinde çalışılması gerekiyor**

![Soru-Cevap için birden çok tablo kullanma](media/q-and-a-best-practices/desktop-qna-09.png)

**Soru-Cevap için Hazır**

![Soru-Cevap için birden çok tablo kullanma](media/q-and-a-best-practices/desktop-qna-10.png)

### <a name="pivot-to-eliminate-property-bags"></a>Özellik paketlerini ortadan kaldırmak için özetleme

Modelinizde *özellik paketleri* varsa bunlar özellik başına tek bir sütun içerecek şekilde yeniden yapılandırılmalıdır. Özellik paketleri çok sayıda özelliğin yönetilmesi için kullanışlı olsa da ne Power BI tarafından raporlanan ne de Soru-Cevap’ın çözüm bulabileceği bir dizi doğal sınırlamaya sahiptir.

Örneğin, Müşteri Kimliği, Özellik ve Değer sütunlarına sahip olan ve her satırın aynı müşteri için farklı bir özelliği (örneğin, yaş, medeni durum, şehir vb.) temsil ettiği bir *CustomerDemographics* tablosunu göz önünde bulundurun. Özellik sütununun içeriğine bağlı olarak Değer sütununa ek anlamlar yüklenmesi, Soru-Cevap’ın buna başvuran çoğu sorguyu yorumlamasını imkansız hale getirir. “Her müşterinin yaşını göster” gibi basit bir komut, “özelliğin yaş olduğu yerlerde müşterileri ve müşterilerin demografik bilgilerini göster” olarak yorumlanabileceğinden işe yarayabilir. Bununla birlikte, modelin yapısı biraz daha karmaşık olan “Chicago’daki müşterilerin ortalama yaşı” gibi soruları desteklemez. Power BI raporlarını doğrudan yazan kullanıcılar bazen istedikleri verilere ulaşmanın akıllıca yollarını bulabilse de Soru-Cevap yalnızca her sütunun tek bir anlamı olduğunda çalışır.

**Üzerinde çalışılması gerekiyor**

![Soru-Cevap modellerinde özellik paketleri kullanmayın](media/q-and-a-best-practices/desktop-qna-11.png)

**Soru-Cevap için Hazır**

![Soru-Cevap için birden çok tablo kullanma](media/q-and-a-best-practices/desktop-qna-12.png)

### <a name="union-to-eliminate-partitioning"></a>Bölümlemeyi ortadan kaldırmak için birleştirme

Verilerinizi birden çok tabloya böldüyseniz veya birden çok sütundaki değerleri özetlediyseniz, kullanıcılarınızın belirli yaygın işlemleri gerçekleştirmesi zor veya imkansız olabilir. İlk olarak tipik bir tablo bölümlemeyi göz önünde bulundurun: bir *Satış2000-2010* tablosu ile bir *Satış2011-2020* tablosu. Tüm önemli raporlarınız belirli bir on yıllık dönemle sınırlanmışsa Power BI raporları için değişiklik yapmanız gerekmeyebilir. Ne var ki, Soru-Cevap’ın esnekliği sayesinde kullanıcılarınız “yıla göre toplam satış” gibi soruların cevaplarını bekler. Bu sorgunun çalışması için verileri tek bir Power BI model tablosunda birleştirmeniz gerekir.

Benzer şekilde, normal bir özetlenmiş değer sütununu ele alalım: Yazar, Kitap, Şehir1, Şehir2 ve Şehir3 sütunlarını içeren *KitapTuru* tablosu. Böyle bir yapıda, "şehre göre kitap sayısı" gibi basit sorular bile doğru yorumlanamaz. Bu sorgunun işe yaraması için şehir değerlerini tek bir sütunda birleştiren ayrı bir *Kitap Turu Şehirleri* tablosu oluşturun.

**Üzerinde çalışılması gerekiyor**

![Soru-Cevap modellerinde özetlenmiş değer sütunları kullanmayın](media/q-and-a-best-practices/desktop-qna-13.png)

**Soru-Cevap için Hazır**

![Soru-Cevap için birden çok tablo kullanma](media/q-and-a-best-practices/desktop-qna-14.png)

### <a name="split-formatted-columns"></a>Biçimlendirilmiş sütunları bölme

Verilerinizi içeri aktardığınız kaynak biçimlendirilmiş sütunlar içeriyorsa Power BI raporları (ve Soru-Cevap) sütunun içine ulaşarak içeriği ayıklamaz. Bu nedenle, örneğin, adres, şehir ve ülkeyi içeren bir **Tam Adres** sütununuz varsa, kullanıcılarınızın her birini tek tek sorgulayabilmesi için bunu Adres, Şehir ve Ülke sütunlarına bölmeniz gerekir.

**Üzerinde çalışılması gerekiyor**

![Soru-Cevap için birden çok veri öğesine yönelik tek bir sütun kullanmayın](media/q-and-a-best-practices/desktop-qna-15.png)

**Soru-Cevap için Hazır**

![Soru-Cevap için birden çok tablo kullanma](media/q-and-a-best-practices/desktop-qna-16.png)

Benzer şekilde, bir kişi için tam ad sütunlarınız varsa, kısmi ad kullanılarak soru sorulmak istenmesi ihtimaline karşı **Ad** ve **Soyadı** sütunlarını ekleyin. 


### <a name="create-new-tables-for-multi-value-columns"></a>Çok değerli sütunlar için yeni tablolar oluşturun

Yine benzer şekilde, verilerinizi içeri aktardığınız kaynak çok değerli sütunlar içeriyorsa Power BI raporları (ve Soru-Cevap) sütunun içine ulaşarak içeriği ayıklayamaz. Örneğin, bir şarkı için birden çok bestecinin adını içeren bir Besteci sütununuz varsa bunu ayrı bir *Besteciler* tablosunda birden çok satıra bölmeniz gerekir.

**Üzerinde çalışılması gerekiyor**

![Soru-Cevap için çok değerli sütunlar kullanmayın](media/q-and-a-best-practices/desktop-qna-17.png)

**Soru-Cevap için Hazır**

![Soru-Cevap için birden çok tablo kullanma](media/q-and-a-best-practices/desktop-qna-18.png)

### <a name="denormalize-to-eliminate-inactive-relationships"></a>Etkin olmayan ilişkileri ortadan kaldırmak için normalleştirmeyi geri alın

“Normalleştirme daha iyidir” kuralının tek istisnası, bir tablodan diğerine ulaşmak için birden çok yol olduğunda görülür. Örneğin, her biri *Şehirler* tablosuyla ilişkili olacak şekilde hem Kaynak Şehir Kimliği hem de Hedef Şehir Kimliği sütununu içeren bir *Uçuşlar* tablonuz olduğunu varsayın. Bu ilişkilerden birinin etkin değil olarak işaretlenmesi gerekir. Soru-Cevap yalnızca etkin ilişkileri kullanabildiğinden, hangisini seçtiğinize bağlı olarak kaynak veya hedef hakkında soru soramazsınız. Bunun yerine, *Uçuşlar* tablosunda şehir adı sütunlarının normalleştirmesini kaldırırsanız şöyle sorular sorabilirsiniz: “yarınki kaynak şehri Seattle, hedef şehri San Francisco olan uçuşları listele.”

**Üzerinde çalışılması gerekiyor**

![Soru-Cevap için tablo başına yalnızca bir yol](media/q-and-a-best-practices/desktop-qna-19.png)

**Soru-Cevap için Hazır**

![Soru-Cevap için birden çok tablo kullanın](media/q-and-a-best-practices/desktop-qna-20.png)

### <a name="add-synonyms-to-tables-and-columns"></a>Tablo ve sütunlara eş anlamlılar ekleme

Bu adım, genel olarak Power BI raporları için değil özel olarak Soru-Cevap için geçerlidir. Kullanıcılar genellikle aynı şeyden bahsederken çeşitli terimler (toplam satış, net satış, toplam net satış gibi) kullanır. Bu eş anlamlıları Power BI modelindeki tablolara ve sütunlara ekleyebilirsiniz. 

Bu adım önemli olabilir. Tablo ve sütun adları kolay olsa bile Soru-Cevap kullanıcıları akıllarına ilk gelen sözcükleri kullanarak soru sorar. Önceden tanımlanmış bir sütun listesinden seçim yapmaz. Ne kadar çok mantıklı eş anlamlı eklerseniz kullanıcılarınızın raporla ilgili deneyimi o kadar iyi olur. Power BI Desktop’ta eş anlamlılar eklemek için Model görünümüne gidin, Modelleme sekmesini seçin ve bir alan ya da tablo belirleyin. Özellikler bölmesinde, eş anlamlılar ekleyebileceğiniz **Eş anlamlılar** kutusu gösterilir.

![Soru-Cevap Özellikler bölmesi eş anlamlılar](media/q-and-a-best-practices/qna-modelling-pane-synonyms.png)

 Eş anlamlı sözcükler eklerken dikkatli olun. Aynı eş anlamlıyı birden fazla sütuna veya tabloya eklemek belirsizliğe neden olur. Soru-Cevap, belirsiz eş anlamlılar arasından seçim yapmak için mümkün olduğunda bağlamı kullanır, ancak ehr soru için yeterli bağlam yoktur. Örneğin, kullanıcınız “müşterileri say” komutunu verdiğinde, modelinizde “müşteri” eş anlamlısını içeren üç öğe varsa kullanıcılar aradıkları yanıtı alamayabilir. Böyle durumlarda, farklı ifadeler için birincil eş anlamlı kullanılacağından bunun benzersiz olduğundan emin olun. Bu, belirsizlik konusunda kullanıcıyı uyarıp (örneğin, “arşivlenen müşteri kaydı sayısını göster” sorusunun farklı ifade edilmesi) sorunun farklı bir şekilde sorulması gerektiğine dair ipucu verebilir.

## <a name="next-steps"></a>Sonraki adımlar

[Power BI Soru-Cevap’a giriş](q-and-a-intro.md)
