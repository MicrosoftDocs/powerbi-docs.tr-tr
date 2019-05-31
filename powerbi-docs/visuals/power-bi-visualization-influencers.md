---
title: Ana etmenler görselleştirmeleri öğreticisi
description: "Öğretici: Power BI'da bir kilit görselleştirme oluşturma"
author: mihart
manager: kvivek
ms.reviewer: juluczni
ms.service: powerbi
ms.component: powerbi-service
ms.topic: tutorial
ms.date: 05/22/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: 8d2d6755d01a8ea9d5dad9813fcd7f4b4c1f8232
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66051609"
---
# <a name="key-influencers-visualization"></a>Ana etmenler görselleştirmesi
Görsel kilit Etkenler bu sürücüye ilginizi çeken bir ölçüm anlamanıza yardımcı olur. Verilerinizi çözümler, önemli faktörleri derecelendirir ve bunları ana etmenler olarak görüntüler. Örneğin, hangi etkileri olan çalışan devir olarak da bilinen karmaşıklığı şekil istediğinizi varsayalım. Bir faktör İstihdam sözleşme uzunluğu olabilir ve çalışan yaş diğer bir etken olabilir. 
 
## <a name="when-to-use-key-influencers"></a>Kilit kullanıldığı durumlar 
İsterseniz kilit görsel harika bir seçimdir: 
- Analiz edilen ölçüm hangi faktörlerin etkileyen bakın.
- Bu etkenler göreceli önemini karşılaştırın. Örneğin, kısa vadeli sözleşmeler çalışan kaybını uzun vadeli sözleşmelerden daha mı fazla etkiliyor? 

## <a name="key-influencer-requirements"></a>Ana etmen gereksinimleri 
Analiz ölçüm kategorik veya sayısal bir alan olmalıdır (toplamlar ve ölçüler henüz desteklenmez).

## <a name="features-of-the-key-influencers-visual"></a>Görsel kilit özellikleri

![Numaralandırılmış özellikleri](media/power-bi-visualization-influencers/power-bi-ki-numbers-new.png)

1. **Sekmeleri**: Görünümler arasında geçiş yapmak için sekmeyi seçin. **Anahtar öğrenilenler** en çok katkıda bulunanlar için seçilen ölçüm değeri gösterir. **İlk Segment** ölçüm seçili değerine katkıda üst segmentlerini gösterir. *Segment*, bir değer bileşiminden oluşur. Örneğin, bir segment kullanan müşteriler en az 20 yıldır atanmış olması ve Batı bölgesinde Canlı tüketiciler olabilir. 

2. **Açılan kutu**: Araştırma altında ölçüm değeri. Bu örnekte ölçüm Ara **derecelendirme**. Seçilen değer **düşük**.

3. **İfadenin**: Sol bölmede görsel yorumlamaya yardımcı olur.

4. **Sol bölmede**: Sol bölmede bir görsel içerir. Bu durumda, sol bölmede, üstteki kilit listesini gösterir.

5. **İfadenin**: Sağ bölmede görsel yorumlamaya yardımcı olur.

6. **Sağ bölmede**: Sağ bölmede bir görsel bulunur. Bu durumda, sütun grafiği için anahtar etkileyen tüm değerleri görüntüler **tema** sol bölmede seçilmiş. Belirli değerini **kullanılabilirlik** sol bölmeden yeşil renkte gösterilir. Diğer değerler için **tema** siyah olarak gösterilir.

7. **Ortalama çizgisi**: Ortalama tüm diğer olası değerleri için hesaplanır **tema** dışında **kullanılabilirlik**. Bu nedenle hesaplama siyah renkli tüm değerleri içerir. Diğer yüzde söyler **Temalar** , düşük derecelendirme vermiş oldunuz. Diğer bir deyişle, müşteri tarafından bir derecelendirme verilir, bu müşteri neden veya tema derecelendirmesi de açıklanmaktadır. Bazı temaları, kullanılabilirlik, hız ve güvenlik durumdadır. 

   **Kullanılabilirlik temadır** göre görselin sol bölmede, düşük derecelendirme için ikinci en yüksek anahtar yetkili olan. Diğer tüm tema ve kullanıcıların katkısı bir derecelendirme ortalama **düşük**, kırmızı renkte gösterilen sonuç alın. Yalnızca %11.35 verilen tüm diğer temaları, daha yüksek **kullanılabilirlik**.

8. **Onay kutusu**: **Yalnızca öğrenilenler olan değerleri göster**.

## <a name="create-a-key-influencers-visual"></a>Ana etmenler görseli oluşturma 
 
Bir kilit görsel oluşturma hakkında bilgi edinmek için bu videoyu izleyin. Ardından oluşturmak için aşağıdaki adımları izleyin. 

<iframe width="560" height="315" src="https://www.youtube.com/embed/fDb5zZ3xmxU" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Ürün Yöneticisi, müşteri adayı negatif incelemeleri, bulut hizmeti hakkında bırakın müşterilere Etkenler kullanıma tahmin etmek istemektedir. Takip etmek için, Power BI Desktop’ta [Customer Feedback (Müşteri Geri Bildirimi) PBIX dosyasını](https://github.com/Microsoft/powerbi-desktop-samples/blob/master/2019/customerfeedback.pbix) açın. Ayrıca yükleyebilirsiniz [müşteri geri bildirim Excel dosyasını Power BI hizmetinde veya Power BI Desktop için](https://github.com/Microsoft/powerbi-desktop-samples/blob/master/2019/customerfeedback.xlsx). 

> [!NOTE]
> Müşteri geri bildirimi veri çubuğunda [Moro et al., 2014] tabanlı S. Moro, P. Cortez ve P. Rita kümesidir. "Banka telefonla başarısını tahmin etmek için bir veri odaklı bir yaklaşım." *Karar destek sistemleri*, Elsevier, 62:22-31, Haziran 2014'te. 

1. Raporu açıp seçin **anahtar öğrenilenler** simgesi. 

    ![Görselleştirmeler bölmesinde Ana etmenler şablonunu seçin](media/power-bi-visualization-influencers/power-bi-template-new.png)

2. İçine incelemek istediğiniz ölçüyü Taşı **Çözümle** alan. **Çözümle** alanı yalnızca kategorik veya sürekli olmayan, değişken destekler. Bir müşteri yönetendir görmek için hizmeti düşük derecelendirmesini seçin **müşteri tablosu** > **derecelendirme**. 
3. Etkilemek düşündüğünüz taşıma alanları **derecelendirme** içine **tarafından açıklayan** alan. İstediğiniz sayıda alanı taşıyabilirsiniz. Bu durumda, başlangıcı:
    - Ülke-Bölge 
    - Role in Org (Kuruluştaki Rol) 
    - Subscription Type (Abonelik Türü) 
    - Company Size (Şirket Boyutu) 
    - Tema 
1. Negatif derecelendirmelerine odaklanmak için seçin **düşük** içinde **ne olmasını derecelendirme etkiler** açılan kutusu.  

    ![Aşağı açılan kutusundan düşük seçin](media/power-bi-visualization-influencers/power-bi-key-influencers.png)

Analiz analiz ediliyor. alanın tablo düzeyi üzerinde çalışır. Bu durumda sahip **derecelendirme** ölçümü. Bu ölçüm, bir müşteri düzeyinde tanımlanır. Her müşteri, yüksek bir puan ya da düşük puan sağlamıştır. Açıklayıcı tüm faktörlerin yapmak görsel için müşteri düzeyinde tanımlanması gerekir bunları kullanın. 

Önceki örnekte, tüm açıklayıcı Etkenler birebir veya ölçüye sahip bir bire çok ilişkisi vardır. Bu durumda, tam olarak bir tema ile ilişkili her puanı vardır. Bu tema, müşteri gözden geçirme ana temasını oluştu. Benzer şekilde, müşterilere bir ülkeden bir üyelik türü vardır ve bir rol kuruluşlarında gerçekleştirmek gelir. Açıklayıcı zaten bir müşteri özniteliklerini faktörlerdir ve hiçbir dönüştürme gereklidir. Görsel, bunları anında kullanımını yapabilirsiniz. 

Öğreticinin sonraki bölümlerinde, bire çok ilişkilerine sahip daha karmaşık örneklere bakın. Bu gibi durumlarda, analizini çalıştırılmadan önce müşteri düzeye toplanacak sütunları içerir. 

Ölçüler ve toplamlar açıklayıcı faktörleri de tablo düzeyinde değerlendirilir olarak kullanılan **Çözümle** ölçümü. Bu makalenin sonraki bölümlerinde bazı örnekler gösterilmektedir. 

## <a name="interpret-categorical-key-influencers"></a>Kategorik kilit yorumlama 
Kilit düşük değerlendirmelerinde bir göz atalım. 

### <a name="top-single-factor-that-influences-the-likelihood-of-a-low-rating"></a>Düşük derecelendirme olasılığını etkileyen üst tek faktörlü

Kuruluşun Bu örnekte üç rol vardır: tüketici, yönetici ve yayımcı. Bir tüketici olan, düşük derecelendirme için katkıda bulunan üst faktördür. 

![Rol Seç kuruluştaki tüketicisidir.](media/power-bi-visualization-influencers/power-bi-role-consumer.png)


Daha kesin tüketicilerinize hizmetinizi negatif bir puan vermek 2.57 bir kez daha yüksektir. Kilit listeleri grafik **rolüdür kuruluştaki tüketici** soldaki listedeki ilk. Seçerek **rolüdür kuruluştaki tüketici**, Power BI, sağ bölmede ek ayrıntılar gösterir. Düşük derecelendirme olasılığını comparative her rolün etkisini gösterilir.
  
- Tüketici %14.93 düşük puan verin. 
- Ortalama olarak, diğer tüm rolleri %5.78 zaman bir düşük puan verin.
- Tüketiciler için diğer tüm rolleri karşılaştırıldığında düşük bir puan vermek 2.57 bir kez daha yüksektir. Bu, yeşil bir çubuk kırmızı noktalı çizgi bölerek belirleyebilirsiniz. 

### <a name="second-single-factor-that-influences-the-likelihood-of-a-low-rating"></a>Düşük derecelendirme olasılığını etkileyen ikinci tek öğe

Görsel kilit karşılaştırır ve birçok farklı değişkenlerinden Etkenler derecelendirir. İkinci etkileyen ile yapmak için hiçbir şey sahip **kuruluştaki rolünü**. İkinci etkileyen olan listeden seçin **temadır kullanılabilirlik**. 

![Tema seç bir kullanımdır](media/power-bi-visualization-influencers/power-bi-theme.png)

İkinci en önemli faktör, müşterinin incelemesinin tema ilişkilidir. Güvenilirlik, tasarım veya hız gibi diğer temaları açıklama eklenen müşteriler karşılaştırıldığında düşük bir puan vermek 2.55 kat daha büyük olasılıkla müşteriler, ürün kullanılabilirliği hakkında yorum yaptı. 

Görseller arasında kırmızı noktalı çizgiyle gösterilir, ortalama %5.78 %11.34 değiştirildi. Diğer tüm değerlerin ortalamasını üzerinde bağlı olduğu dinamik bir ortalamadır. İlk etkileyen için ortalama müşteri rolü dışlandı. İkinci etkileyen için kullanılabilirlik tema dışlanır. 
 
Seçin **yalnızca öğrenilenler olan değerleri göster** yalnızca etkili değerlerini kullanarak filtrelemek için onay kutusunu işaretleyin. Bu durumda, bunlar düşük puan sürücü rolleri hedeflenmiştir. On iki temaları, Power BI, düşük derecelendirme sürücü Temalar tanımlanan dört için azaltılır. 

![Onay kutusunu işaretleyin](media/power-bi-visualization-influencers/power-bi-only-show.png)

## <a name="interact-with-other-visuals"></a>Diğer görsellerle etkileşim kurma 
 
Dilimleyici, filtre veya tuval üzerinde diğer görseller seçtiğiniz her zaman visual kilit Analizine veri yeni bölümünde yeniden çalıştırır. Örneğin, taşıma **şirket boyutu** rapora ve bir dilimleyici olarak kullanın. Kilit, Kurumsal müşteriler için genel popülasyon farklı olup olmadığını görmek için bunu kullanın. Bir kuruluş şirket boyutu 50.000 çalışanlarla daha büyüktür.
 
Seçme **> 50.000** tekrar bölümlerini analiz, görebilirsiniz öğrenilenler değiştirilmiş olmasıdır. Büyük kurumsal müşteriler, düşük derecelendirme için en çok etkileyen güvenlikle ilgili bir tema sahiptir. Büyük müşterilere mutsuz hakkında belirli güvenlik özellikleri varsa bkz. daha fazla araştırmak isteyebilirsiniz. 

![Slice şirket boyutuna göre](media/power-bi-visualization-influencers/power-bi-filter.png)

## <a name="interpret-continuous-key-influencers"></a>Sürekli kilit yorumlama 
 
Şu ana kadar farklı kategorik alanlar keşfetmek için görsel kullanmayı gördünüz düşük derecelendirme etkiler. Yaş, yükseklik ve fiyat gibi sürekli Etkenler olması mümkündür **tarafından açıklayan** alan. Kurduğunda gerçekleşen işlemlere göz atalım olduğunda **çalışma süresi** müşteri tabloya öğesinden taşındı **tarafından açıklayan**. Çalışma süresi gösterilmektedir ne kadar bir müşterinin hizmet kullandı. 
 
Çalışma süresi arttıkça, daha düşük bir derecelendirme alma olasılığını da artırır. Bu eğilim, daha uzun vadeli müşteriler negatif bir puan vermek daha olası olduğunu önerir. Bu öngörüleri ilginçtir ve daha sonra izlemek istediğiniz. 
 
Görselleştirme tarafından 13.44 aylık çalışma süresi artar her seferinde, ortalama düşük derecelendirme olasılığını 1,23 kat arttığını gösterir. Bu örnekte 13,44 ay kullanım süresinin standart sapması oluyor. Aldığınız Insight adımları ele alınmaktadır. Bu nedenle çalışma süresi çalışma süresi standart sapmasını olan standart bir tutara göre artan, düşük derecelendirme alma olasılığını etkiler. 
 
Dağılım grafiğinde noktalara sağ bölmede, düşük derecelendirme çalışma süresi, her bir değer için ortalama yüzdesini çizer. Bu, bir eğilim çizgisi birlikte eğimi vurgular.


![Çalışma süresi için dağılım](media/power-bi-visualization-influencers/power-bi-tenure.png)

## <a name="interpret-measures-and-aggregates-as-key-influencers"></a>Ölçüler ve toplamlar kilit yorumlayın. 
 
Ölçüler ve toplamlar açıklayıcı faktörleri analizinizi içinde kullanabilirsiniz. Örneğin, müşteri destek biletlerini sayısı veya ortalama süresi açık bir bilet puanına göre etkisini aldığınız görmek isteyebilirsiniz. 
 
Bu durumda, bir müşterinin destek biletlerini sayısını verdikleri puanı etkiler, görmek istediğiniz. Aktardığınız artık **bilet kimliği destekleyen** destek bileti tablosundan. Bir müşteri birden çok destek biletlerini olabileceğinden, müşteri düzeyine kimliği toplama. Toplama, çözümleme, müşteri düzeyi, çalışır, böylece tüm sürücüleri bu ayrıntı düzeyinde tanımlanması için önemlidir. 
 
Kimlikleri sayısı göz atalım. Her müşteri satır, destek biletlerini ilişkili sayısını sahiptir. Bu durumda, destek biletlerini arttıkça, sayısı olarak derecelendirme olma olasılığı düşük 5.51 sürelerini gider. Sağ taraftaki görsel destek biletlerini ortalama sayısı tarafından farklı gösterir **derecelendirme** değerleri müşteri düzeyinde değerlendirilir. 

![Destek bileti kimliği etki](media/power-bi-visualization-influencers/power-bi-support-ticket.png)


## <a name="interpret-the-results-top-segments"></a>Sonuçları yorumlamanıza: En üst parçalar 
 
Kullanabileceğiniz **anahtar öğrenilenler** tek tek her faktör değerlendirmek için sekmesinde. Ayrıca **ilk Segment** çeşitli faktörlerin bir bileşimine çözümlediğiniz ölçümü nasıl etkilediğini görmek için sekmesinde. 
 
Üst segmentleri başlangıçta Power BI bulunan tüm parçaları genel bir bakış gösterir. Aşağıdaki örnek, altı Segment bulunamadı gösterir. Bu kesimler, düşük derecelendirme segmentteki yüzdesine göre sıralanır. Segment 1, örneğin, düşük %74.3 müşteri derecelendirmeleri vardır. Kabarcık ne kadar yüksekteyse düşük derecelendirmelerin oranı o kadar yüksektir. Kabarcık boyutunu Segmentte kaç müşterilerdir temsil eder. 

![Üst kesimler sekmesi seçin](media/power-bi-visualization-influencers/power-bi-top-segments-tab.png)

Kabarcık seçildiğinde ilgili segmentin detayına gidilir. Örneğin, Segment 1'i seçin, bunu görece kurulan müşterileri oluşur, bulun. Bunlar, müşteriler için 29 ay boyunca netleştirilmesi ve dörtten fazla destek biletlerini özelliğine sahip. Tüketiciler ya da yöneticiler bulunmaları son olarak, yayımcılar olmadıklarını. 
 
Bu grupta, düşük derecelendirme %74.3 müşterilerin getirdi. Bu kesimin düşük derecelendirme daha büyük bir kısmı bu %11.7 zaman, derecelendirme düşük ortalama müşteri getirdi. Bu, daha yüksek 63 yüzdesi noktaları olur. Popülasyon adreslenebilir bir bölümünü temsil ettiği şekilde segment 1 yaklaşık %2.2 verileri de içerir. 

![ilk üst segmenti seçin](media/power-bi-visualization-influencers/power-bi-top-segments2.png)

## <a name="working-with-numerical-data"></a>Sayısal verileri ile çalışma

Bir sayısal alana taşırsanız **Çözümle** alan, sahip olduğunuz bir seçim bu senaryonun nasıl ele alınacağını. Uygulamasına giderek görsel davranışını değiştirebilirsiniz **biçimlendirme bölmesinde** ve arasında geçiş yapma **kategorik çözümleme türü** ve **sürekli Analiz türü**.

![Kategorik olarak değiştirme](media/power-bi-visualization-influencers/power-bi-ki-formatting.png)

A **kategorik çözümleme türü** yukarıda açıklandığı gibi davranır. 1 ile 10 arasında değişen anket puanları bakarak, örneğin, 'Ne anket 1 olması puanları Firmalar?' sorabilirsiniz

A **sürekli Analiz türü** sürekli bir soru değiştirir. Yukarıdaki örnekte, sunduğumuz yeni soru 'Ne, anket artırma/azaltma için puanları Firmalar?' olmalıdır

Bu ayrım, analiz alanında benzersiz değerleri çok sayıda olduğunda çok yararlıdır. Aşağıdaki örnekte ev fiyatları bakacağız. 'Ne ev 156,214 olmasını fiyatı etkiler mi?' istemek için çok anlamlı değil Bu çok olduğu gibi özel ve bir desen çıkarsamak için yeterli veri yok olasılığı düşüktür.

Bunun yerine size, 'Ne, ev artırmak için fiyat etkiler' isteyebilir mi? hangi ev fiyatları farklı değerler yerine bir aralık değerlendirilecek sağlıyor.

![Sayısal soru](media/power-bi-visualization-influencers/power-bi-ki-numeric-question.png)

## <a name="interpret-the-results-key-influencers"></a>Sonuçları yorumlamanıza: Başlıca etkileyiciler 

Bu senaryoda 'Ne ev artırmak için fiyat etkiler ' bakacağız. Gibi bir ev fiyatı etkileyebilir açıklayıcı bir dizi etkene adresindeki arıyoruz **yıllık** (yıl), ev derlendiği **KitchenQual** (mutfak kalite) ve **YearRemodAdd** (evin yeniden modellenmiş yıl). 

Aşağıdaki örnekte, mutfak kalitesi mükemmel olan bizim en çok etkileyen bakacağız. Sonuçlar, biz bazı önemli farklar kategorik Ölçümleriyle analiz edilirken gördüğümüz olanlara oldukça benzerdir:

- Sağdaki sütun grafiği ortalamalar yüzdeleri yerine arıyor. Bu nedenle bize mükemmel bir mutfak hizmeti ile bir ev ortalama ev fiyatı (çubuk yeşil) nedir mükemmel bir mutfak (noktalı çizgi) olmadan bir ev ortalama ev fiyatına kıyasla gösterir
- Kabarcık numara hala yeşil bir çubuk ve kırmızı noktalı çizgi arasındaki farkı ancak bir sayı olarak ifade edilir ($158. 49K) yerine bir olasılığını (1.93 x). Ortalama benzeri, görev açısından kritik uygulamaları ile mükemmel kitchens neredeyse $160 K görev açısından kritik uygulamaları mükemmel kitchens olmadan daha pahalıdır.

![Sayısal hedef kategorik öğrenilenler](media/power-bi-visualization-influencers/power-bi-ki-numeric-categorical.png)

Etkiyi arıyoruz aşağıdaki örnekte ev fiyatı temel alınarak sürekli bir faktör (ev yeniden modellenmiş yıl) sahiptir. Nasıl sürekli öğrenilenler kategorik ölçümler için analiz ediyoruz için karşılaştırıldığında farkları aşağıdaki gibidir:

-   Sağ bölmede dağılım grafiğinde noktalara yeniden modellenmiş yılın her benzersiz değer için ortalama ev fiyat çizer. 
-   Kabarcık değer ne kadar ortalama Merkezi tarafından fiyat artırır gösterir (Bu durumda $2. 87k) ne zaman evi olan yıl yeniden modellenmiş artar, standart sapma (Bu durumda 20 yıl)

![Sayısal hedef sürekli öğrenilenler](media/power-bi-visualization-influencers/power-bi-ki-numeric-continuous.png)

Son olarak, ortalama yılı arıyoruz ölçüler söz konusu olduğunda bir ev oluşturulmuştur. Analiz burada aşağıdaki gibidir:

-   Tablodaki her bir benzersiz değer için ortalama ev fiyat sağ bölmesinde dağılım grafiği çizim
-   Kabarcık değer ne kadar ortalama Merkezi tarafından fiyat artırır gösterir (Bu durumda 1 ABD Doları. 35K) olduğunda ortalama yıl artar, standart sapma (Bu durumda 30 yıl)

![Sayısal hedef öğrenilenler ölçer](media/power-bi-visualization-influencers/power-bi-ki-numeric-measures.png)

## <a name="interpret-the-results-top-segments"></a>Sonuçları yorumlamanıza: Üst segmentleri

Burada evi ortalama fiyatları grupları sayısal hedefleri göstermek için üst segmentleri genel kümesinde daha yüksektir. Örneğin, aşağıdaki görebiliriz **Segment 1** görev açısından kritik uygulamaları yapılan burada **GarageCars** (otomobiller Garaj uygun olabilir sayısı) 2'den büyük ve **RoofStyle** HIP olduğu. Görev açısından kritik uygulamaları bu özelliklere sahip, ortalama fiyatını, $355 genel ortalama $180 K olan veri karşılaştırıldığında K vardır.

![Sayısal hedef öğrenilenler ölçer](media/power-bi-visualization-influencers/power-bi-ki-numeric-segments.png)

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme 
 
**Önizleme sınırlamaları nelerdir?** 
 
Görsel kilit şu anda genel Önizleme aşamasındadır ve bazı sınırlamalar vardır. Şu anda kullanılabilir değil işlevselliğini içerir: 
- Toplamaları veya ölçüler olan ölçümleri analiz ediliyor.
- Power BI Embedded görselde kullanma.
- Power BI mobil uygulamalarında görselde kullanma.
- RLS desteği.
- Doğrudan sorgu desteği.
- Canlı bağlantı desteği.

![Sayısal soru](media/power-bi-visualization-influencers/power-bi-ki-numeric-question.png)

**Hiçbir öğrenilenler veya Segment bulunamadı bir hata görüyorum Bunun nedeni nedir?** 

![Hiçbir öğrenilenler hata bulundu](media/power-bi-visualization-influencers/power-bi-error1.png)


Alanları dahil olduğunda bu hata oluşur. **tarafından açıklayan** ancak hiçbir öğrenilenler bulunamadı. 
- Ölçüm çözümleme hem de dahil **Çözümle** ve **tarafından açıklayan**. Kaldırın **tarafından açıklayan**. 
- Açıklayıcı alanlarınızın çok az gözlem içeren çok fazla kategorisi var. Bu durum öğrenilenler faktörlerdir belirlemek görselleştirmenin zorlaştırır. Yalnızca birkaç gözlemlere tabanlı genelleştirmek zordur. Sayısal bir alan analiz, geçiş isteyebilirsiniz **kategorik analiz** için **sürekli analiz** içinde **biçimlendirme bölmesinde** altında  **Analiz** kart.
- Genelleştirmek için yeterli gözlemleri, açıklayıcı Etkenler vardır, ancak görselleştirme rapora anlamlı bağıntıları bulamadı.
 
**Çözümleme ölçüm analizi çalıştırmak için yeterli veri yok bir hata görüyorum Bunun nedeni nedir?** 

![Yeterli veri hatası](media/power-bi-visualization-influencers/power-bi-not-enough-data.png)

Görselleştirmenin, diğer gruplara göre bir grup için veri desenlerinde bakarak çalışır. Örneğin, düşük derecelendirme kıyasla yüksek derecelendirme verdiğiniz müşteriler verdiğiniz müşteriler arar. Modelinizdeki verileri yalnızca birkaç gözlemler varsa, desenleri bulmak zordur. Görselleştirmeyi anlamlı öğrenilenler bulmak için yeterli veri yoksa, daha fazla veri analizi çalıştırmak için gereklidir gösterir. 

Seçili durum için en az 100 gözlemleri sahip olmasını öneririz. Bu durumda, değişim sıklığı müşteriler durumudur. Ayrıca, karşılaştırma için kullandığınız durumlar için en az 10 gözlemler gerekir. Bu durumda, karşılaştırma durum değişim olmayan müşteriler şeklindedir.

Sayısal bir alan analiz, geçiş isteyebilirsiniz **kategorik analiz** için **sürekli analiz** içinde **biçimlendirme bölmesinde** altında  **Analiz** kart.

**Bir hata görüyorum, bir alanda *tarafından açıklayan* ı çözümleme ölçüm içeren tablo için benzersiz bir şekilde ilişkili değil. Bunun nedeni nedir?**
 
Analiz analiz ediliyor. alanın tablo düzeyi üzerinde çalışır. Örneğin, müşteri geri bildirimi hizmetiniz için Analiz, bir müşteri, yüksek derecelendirme veya düşük derecelendirme olup verdiğiniz belirten bir tablo olabilir. Bu durumda, analiz müşteri tablo düzeyinde çalışıyor. 

Ölçümünüzün içeren tabloda daha ayrıntılı bir düzeyde tanımlanan bir ilişkili tablo varsa, bu hatayı görürsünüz. Bir örnek aşağıda verilmiştir: 
 
- Hizmetinizin düşük derecelendirme müşteriye yönetendir analiz edin.
- Müşteri, hizmeti tüketiyor cihaz verdikleri incelemeleri etkiler, görmek istediğiniz.
- Bir müşteri hizmeti birden çok farklı şekillerde kullanabilir.
- Aşağıdaki örnekte, müşteri 10000000 hizmetiyle etkileşim kurmak için bir tarayıcı hem bir tablet kullanır.

![Ölçümünüzün içeren tabloda daha ayrıntılı bir düzeyde tanımlanan bir ilişkili tablo](media/power-bi-visualization-influencers/power-bi-error2.png)

Cihaz sütunu açıklayıcı bir faktör olarak kullanmayı denerseniz, şu hatayı bakın: 

![Yanlış sütun hatasını](media/power-bi-visualization-influencers/power-bi-error3.png)

Cihaz müşteri düzeyinde tanımlı olmaması nedeniyle bu hata görüntülenir. Bir müşteri hizmeti birden fazla cihazda kullanabilir. Görselleştirme kalıpları bulmak müşterinin bir öznitelik cihazı olması gerekir. Anlayışınızı iş bağımlı çeşitli çözümler vardır: 
 
- Cihaz sayısı özetleme değiştirebilirsiniz. Örneğin, bir müşteri veren puanı cihaz sayısını etkileyebilir, sayısı kullanın. 
- Belirli bir cihazdaki hizmet kullanan bir müşterinin derecelendirme etkiler, görmek için cihaz sütunu Özet.
 
Bu örnekte, tablet ve tarayıcı, mobil, yeni sütun oluşturmak için verileri özetlenmiş. Artık bu belirli cihazları kullanabilirsiniz **tarafından açıklayan**. Tüm cihazlar öğrenilenler olmasını açın ve tarayıcı müşteri puanı üzerinde en büyük etkisi.

Daha kesin Tarayıcı hizmeti kullanmak için kullanmayın müşteriler yapan müşteriler daha düşük bir puan vermek 3.79 bir kez daha yüksektir. Alt Aşağı listede, mobil tersi için de geçerlidir. Mobil uygulamayı kullanan müşteriler olmayan müşterilerin daha düşük bir puan vermek daha yüksektir. 

![Çözüldü](media/power-bi-visualization-influencers/power-bi-error3-solution.png)

**Ölçüler my analizi eklenmeyen bir uyarı görüyorum. Bunun nedeni nedir?** 

![Ölçüler hata dahil değil](media/power-bi-visualization-influencers/power-bi-measures-not-included.png)


Analiz analiz ediliyor. alanın tablo düzeyi üzerinde çalışır. Müşteri karmaşıklığını çözümleyin, bir müşteri veya çoğaltılmaları olup olmadığını belirten bir tablo olabilir. Bu durumda, analiz müşteri tablo düzeyinde çalışır.
 
Ölçüler ve toplamlar tablo düzeyinde analiz varsayılan olarak. Ortalama aylık harcama için bir ölçü varsa, müşteri tablo düzeyinde çözümleniyordu. 

Müşteri tablosu benzersiz bir tanımlayıcı yoksa, ölçü değerlendirilemiyor ve analiz tarafından göz ardı edilir. Bu durumu önlemek için benzersiz bir tanımlayıcı, ölçüm olan tablo olduğundan emin olun. Bu durumda, müşteri tablo olduğundan ve müşteri kimliğidir benzersiz tanımlayıcısı. Power Query kullanarak bir dizin sütunu eklemek kolaydır.
 
**Çözümleme ölçüm 10'dan fazla benzersiz değerler olduğunu ve bu miktar my analiz kalitesini etkileyebilecek bir uyarı görüyorum. Bunun nedeni nedir?** 

Yapay ZEKA görselleştirme kategorik alanlar ve sayısal alanlar çözümleyebilirsiniz. Kategorik alanlar söz konusu olduğunda, örnek karmaşası gösterilebilir Evet veya Hayır, ve müşteri memnuniyetini yüksek, Orta veya düşük. Analiz etmek için kategorileri sayısının artırılması Kategori başına daha az gözlemler olduğu anlamına gelir. Bu durum, verileri kalıpları bulmak görselleştirme zorlaştırır. 

Sayısal alanlar analiz edilirken sayısal alanlar gibi metin sütunları ise kategorik veriler için yaptığınız gibi bu durumda aynı analiz çalışacak değerlendirmesini arasında seçim yapmanız (**kategorik analiz**). Farklı sayıda varsa analiz öneririz değerleri Değiştir **sürekli analiz** biz ne zaman numaraları artırmak veya azaltmak yerine bunları gibi farklı değerleri değerlendirmesini desenleri Infer anlamına gelir. Geçiş yapabilirsiniz **kategorik analiz** için **sürekli analiz** içinde **biçimlendirme bölmesinde** altında **analiz** kart.

Daha güçlü öğrenilenler bulmak için benzer değerler tek bir birim gruplandırmanız önerilir. Fiyat için bir ölçüm varsa, örneğin, yüksek, Orta ve düşük kategorileri ve tek tek fiyat noktalarını kullanarak benzer fiyatları gruplandırarak daha iyi sonuçlar elde olasılığınız vardır. 

![Uyarı 10'dan fazla benzersiz faktörleri](media/power-bi-visualization-influencers/power-bi-error4.png)


**Kilit olmaları gerektiği şekilde, görünen verilerimi Etkenler vardır, ancak bunlar değil. Bu nasıl olur?**

Aşağıdaki örnekte, düşük derecelendirme 14.93 yüzdesi ile düşük derecelendirme tüketiciler müşterileri sürücü. Yönetici rolü de bir yüksek oranda %13.42, düşük derecelendirme sahiptir ancak bir yetkili olarak kabul değil. 

Bu belirleme öğrenilenler bulduğunda görselleştirmeyi veri noktalarının sayısını da dikkate nedeni. Aşağıdaki örnek, birden fazla 29,000 Tüketicileri ve 10 kat daha az Yöneticiler, ilgili 2,900 sahiptir. Bunların yalnızca 390 düşük derecelendirme getirdi. Görsel yönetici dereceye sahip bir deseni bulunup veya yeni bir fırsat olup olmadığını belirlemek için yeterli veri yok bulma. 

![Öğrenilenler nasıl belirlenir](media/power-bi-visualization-influencers/power-bi-error5.png)

**Kategorik analiz için kilit nasıl hesaplar?**

Yapay ZEKA görselleştirme arka planda kullanan [ML.NET](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet) kilit hesaplamak için bir Lojistik regresyon çalıştırılacak. Lojistik regresyon, farklı grupları birbiriyle karşılaştıran istatistiksel bir modeldir. 

Düşük derecelendirme yönetendir görmek istiyorsanız, düşük puanı verdiğinizi müşteriler yüksek puanı verdiğinizi müşterilerden farkı Lojistik regresyon arar. Yüksek, bağımsız ve düşük puanlar gibi birden çok kategori varsa, düşük derecelendirme vermediniz müşterilerden farkı en düşük derecelendirme verdiğiniz müşterileri arayın. Bu durumda, nasıl düşük puanı verdiğinizi müşteriler yüksek derecelendirme veya bağımsız bir derecelendirme veren müşterilerden farklıdır? 
 
Lojistik regresyon, veri desenlerinde arar ve müşteriler, düşük derecelendirme verdiğiniz yüksek derecelendirme veren müşterilerden nasıl değişebilir için görünür. Bu, örneğin, daha fazla destek biletlerini müşterilerle veya çok az destek biletlerini müşterilerle daha düşük derecelendirme daha yüksek oranda verdiğiniz bulabilirsiniz.
 
Lojistik regresyon nasıl çok sayıda veri noktanız varsa dikkate alır. Örneğin, bir yönetici rolü oynar müşteriler orantılı olarak daha negatif puan verin, ancak yalnızca birkaç Yöneticiler vardır, bu etkili kabul değil. Bir desen çıkarsamak yeterli veri noktası olmadığından, bu belirlemeyi yapılır. Bir wald anlatıyor test olarak bilinen bir istatistik test bir faktör bir yetkili olarak kabul edilip edilmediğini belirlemek için kullanılır. Görsel, eşiği belirlemek için 0,05 p-değeri kullanır. 

**Sayısal analiz için kilit nasıl hesaplar?**

Yapay ZEKA görselleştirme arka planda kullanan [ML.NET](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet) kilit hesaplamak için bir doğrusal regresyon çalıştırılacak. Bir doğrusal regresyon, alanın, analiz sonucunu nasıl değiştiğini, görünümler, açıklayıcı etkenlere bağlı olarak bir istatistik modelidir.

Örneğin, biz ev fiyatları analiz, doğrusal regresyon mükemmel bir mutfak ev fiyatı temel alınarak olacaktır etkili en arayın. Görev açısından kritik uygulamaları mükemmel kitchens ile görev açısından kritik uygulamaları mükemmel kitchens olmadan kıyasla daha az veya ev fiyatları genellikle var mı?

Kümenin doğrusal regresyonunu veri noktası sayısı da göz önünde bulundurur. Örneğin, görev açısından kritik uygulamaları tenis mahkemelerde ile daha yüksek fiyatları varsa ancak çok az sayıda görev açısından kritik uygulamaları tenis mahkeme sahip sahibiz bu etkili olarak kabul edilmez. Bir desen çıkarsamak yeterli veri noktası olmadığından, bu belirlemeyi yapılır. Bir wald anlatıyor test olarak bilinen bir istatistik test bir faktör bir yetkili olarak kabul edilip edilmediğini belirlemek için kullanılır. Görsel, eşiği belirlemek için 0,05 p-değeri kullanır. 

**Segmentleri nasıl hesaplıyorsunuz?**

Yapay ZEKA görselleştirme arka planda kullanan [ML.NET](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet) ilginç alt grupları bulmak için bir karar ağacı çalıştırılacak. Karar ağacının amacı, ilgilendiğiniz ölçümündeki görece yüksek bir veri noktaları alt elde edersiniz sağlamaktır. Bu, düşük derecelendirme müşterilerle veya görev açısından kritik uygulamaları yüksek fiyatlarla olabilir.

Karar ağacı her açıklayıcı faktörü alır ve neden hangi faktörü verir, en iyi şekilde çalışır *bölme*. Yalnızca büyük işletmelere dahil edilecek verileri filtreleme, örneğin, düşük derecelendirme ve yüksek derecelendirme verdiğiniz müşteriler kullanıma ayrı? Veya belki de daha iyi yalnızca güvenlik hakkında yorum müşteriler dahil edilecek verileri filtrelemek için? 

Karar ağacı bölme yaptıktan sonra veri alt alır ve bu veriler için en iyi sonraki bölme belirler. Bu durumda, müşterilerin güvenlik açıklamalı alt grubudur. Her bölme sonra ayrıca bir deseni veya veri ve gerçek bir kesimini bir anomali olup çıkarsamak için yeterli olması bu grup için yeterli veri noktası olup olmadığını göz önünde bulundurur. Başka bir istatistik test 0,05, p değeriyle bölünmüş koşulun istatistiksel önemi denetlemek için uygulanır. 

Karar ağacı çalışmayı tamamladıktan sonra güvenlik açıklamaları ve büyük bir kurumsal gibi tüm bölmeleri, alır ve Power BI filtreler oluşturur. Bu filtre bileşimi görselde bir segment olarak paketlenir. 
 
**Neden bazı faktörleri öğrenilenler haline veya daha fazla alanlarına taşırım gibi öğrenilenler olan Durdur *tarafından açıklayan* alan?**

Görselleştirme tüm açıklayıcı faktörleri birlikte değerlendirir. Bir faktör bir etkileyen tek başına olabilir, ancak diğer faktörlerle edildiği durumlarda da etkileyemez. Yatak ve açıklayıcı bir faktör olarak ev boyutu ile yüksek olacak şekilde bir merkezi fiyat yönetendir çözümlemek istediğiniz varsayalım:

- Tek başına daha fazla yatak ev fiyatlarıyla yüksek olması için bir sürücü olabilir.
- Analizi de dahil olmak üzere merkezi boyutu, ev boyutu sabit kaldığı sürece yatak için ne Şimdi Ara anlamına gelir.
- 1500 metrekare ev boyutundadır, yatak sayısı sürekli bir artış ev fiyat önemli ölçüde artırır düşüktür. 
- Yatak ev boyutu olarak kabul ediliyordu haliyle bir faktör, önemli olmayabilir. 




## <a name="next-steps"></a>Sonraki adımlar
- [Power BI'daki birleşik grafikler](power-bi-visualization-combo-chart.md)
- [Power BI'daki görselleştirme türleri](power-bi-visualization-types-for-reports-and-q-and-a.md)
