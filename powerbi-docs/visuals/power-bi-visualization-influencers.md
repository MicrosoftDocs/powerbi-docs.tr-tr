---
title: Ana etmenler görselleştirmeleri öğreticisi
description: Öğretici - Power BI'da ana etmenler görselleştirmesi oluşturma
author: mihart
manager: kvivek
ms.reviewer: justyna
ms.service: powerbi
ms.component: powerbi-visuals
ms.topic: tutorial
ms.date: 02/10/2019
ms.author: mihart
LocalizationGroup: Visualizations
ms.openlocfilehash: d7ad1cc4ffb339aeb1a64cd28274fde4f8ef6af6
ms.sourcegitcommit: 91ac6185f7026ddbaa925dc54057bb742b4fa411
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/16/2019
ms.locfileid: "56325163"
---
# <a name="key-influencers-visualization"></a>Ana etmenler görselleştirmesi
Ana etmenler görseli ilgilendiğiniz bir ölçümü etkileyen faktörleri anlamanıza yardımcı olur. Verilerinizi çözümler, önemli faktörleri derecelendirir ve bunları ana etmenler olarak görüntüler. Örneğin, istihdam değişimini (çalışan kaybı) nelerin etkilediğiyle ilgileniyor olabilirsiniz. Faktörlerden biri istihdam sözleşmesinin süresi ve diğeri de çalışanların yaşı olabilir. 
 
## <a name="when-to-use-key-influencers"></a>Ana etmenler ne zaman kullanılmalı? 
Ana etmen görseli şunları yapmak için harika bir seçimdir: 
- Çözümlenen ölçümü hangi faktörlerin etkilediğini görmek.

- Bu faktörlerin göreli önemini karşılaştırmak. Örneğin, kısa vadeli sözleşmeler çalışan kaybını uzun vadeli sözleşmelerden daha mı fazla etkiliyor? 

## <a name="key-influencer-requirements"></a>Ana etmen gereksinimleri 
Çözümlediğiniz ölçüm kategorik bir alan olmalıdır.    


## <a name="features-of-the-key-influencer-visual"></a>Ana etmen görselinin özellikleri

![numaralandırılmış özellikler](media/power-bi-visualization-influencers/power-bi-ki-numbers-new.png)    

1. ***Sekmeler*** - görünümler arasında geçiş yapmak için bir sekme seçin. Ana etmenler size seçili ölçüm değerine en çok katkıda bulunan öğeleri gösterir. En üst segmentler seçilen ölçüm değerine katkıda bulunan en üst segmentleri gösterir. *Segment*, bir değer bileşiminden oluşur.  Örneğin, bir segment en az yirmi yıldır müşteriniz olan ve batı bölgesinde yaşayan müşterilerden oluşabilir. 

2. ***Açılan liste*** - araştırılan ölçümün değeri. Bu örnekte **rating** (derecelendirme) ölçümüne bakıyoruz ve **low** (düşük) değerini seçtik.    

3. ***Yeniden belirleme*** - sol bölmedeki görseli yorumlamamıza yardımcı olur. 

4. ***Sol bölme*** - sol bölme tek bir görsel içerir.  Bu örnekte, sol bölmede bize en önemli ana etmenlerin listesi gösteriliyor.

5. ***Yeniden belirleme*** - sağ bölmedeki görseli yorumlamamıza yardımcı olur.

6. ***Sağ bölme*** - sağ bölme tek bir görsel içerir. Bu örnekteki sütun grafiğinde, sol bölmede seçilen **ana etmenin** (**Theme** [Tema]) tüm değerleri görüntüleniyor. Sol bölmede belirtilen değer (**Usability** [Kullanılabilirlik]) yeşil ve diğer tüm **Theme** değerleri siyah gösteriliyor.

7. ***Ortalama çizgisi*** - **Theme** etmeninin **Usability** dışındaki tüm olası değerlerinin ortalaması hesaplanır. Bu nedenle hesaplama siyah renkli tüm değerleri içerir. Bu diğer **Theme** değerlerinin bize hangi oranda düşük derece verdiğini gösterir. Başka bir deyişle, müşteri düşük bir derecelendirme yaptığında bu derecelendirmenin nedenini veya **temasını** da açıklar. Kullanılabilirlik, hız ve güvenlik gibi temalar vardır. Sol bölmedeki görselimize göre düşük derecelendirmede **Usability** **Theme** değeri ikinci en yüksek ana etmendir. Diğer tüm temaların ortalamasını ve bunların **düşük** derecelendirmeye katkısını alırsak, burada kırmızıyla gösterilen sonucu elde ederiz. 

8. ***Onay kutusu*** - yalnızca etmen olan değerleri gösterin.

## <a name="create-a-key-influencers-visual"></a>Ana etmenler görseli oluşturma 
 
Ana etmenler görseli oluşturmayı öğrenmek için bu videoyu izleyin ve aşağıdaki adımları kullanarak kendiniz bir görsel oluşturun. 

<iframe width="560" height="315" src="https://www.youtube.com/embed/fDb5zZ3xmxU" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

Ürün Yöneticimiz müşterilerin bulut hizmetimiz hakkında olumsuz inceleme yazmasına hangi faktörlerin yol açtığını bulmak istiyor.  Takip etmek için, Power BI Desktop’ta [Customer Feedback (Müşteri Geri Bildirimi) PBIX dosyasını](https://github.com/Microsoft/powerbi-desktop-samples/blob/master/2019/customerfeedback.pbix) açın. [Power BI hizmeti veya Power BI Desktop için Customer Feedback Excel dosyasını](https://github.com/Microsoft/powerbi-desktop-samples/blob/master/2019/customerfeedback.xlsx) da indirebilirsiniz. 

> [!NOTE]
> Customer Feedback veri kümesinde şu makale temel alınmıştır: [Moro et al., 2014] S. Moro, P. Cortez ve P. Rita. A Data-Driven Approach to Predict the Success of Bank Telemarketing. Decision Support Systems, Elsevier, 62:22-31, Haziran 2014 

1. Raporu açın ve ana etmenler simgesini seçin.  

    ![Görselleştirmeler bölmesinde Ana etmenler şablonunu seçin](media/power-bi-visualization-influencers/power-bi-template-new.png)

2. Araştırmak istediğiniz ölçümü **Çözümle** alanına sürükleyin. **Çözümle** alanı yalnızca kategorik (sürekli olmayan) değişkenleri destekler. Hizmetimize ilişkin müşteri derecelendirmesinin neden **Düşük** olduğuyla ilgilendiğimizden **Customer Tablosu** > **Rating** öğesini seçiyoruz.    
3. Ardından **Rating** üzerinde etkisi olabileceğini düşündüğünüz alanları **Açıklama Ölçütü** haznesine sürükleyin. İstediğiniz kadar alan sürükleyebilirsiniz. Bu örnekte biz şu alanlarla başlıyoruz: 
    - Country-Region (Ülke-Bölge) 
    - Role in Org (Kuruluştaki Rol) 
    - Subscription Type (Abonelik Türü) 
    - Company Size (Şirket Boyutu) 
    - Tema     
4. Olumsuz derecelendirmelerle ilgilendiğimizden, **Rating değerini etkileyenler** açılan listesinde **Low** değerini seçin.  

    ![açılan listeden Low değerini seçin](media/power-bi-visualization-influencers/power-bi-key-influencers.png)

Çözümleme, çözümlenen alanın tablo düzeyinde çalıştırılır. Bu örnekte biz müşteri düzeyinde tanımlanan **Rating** ölçümüyle ilgileniyoruz (her müşteri yüksek puan veya düşük puan vermiştir). Tüm açıklayıcı faktörlerimizin, bunları kullanan görsel için müşteri düzeyinde tanımlanması gerekiyor. 

Yukarıdaki örnekte tüm açıklayıcı faktörlerimizle ölçümümüz arasında bire bir veya çoğa bir ilişki vardır. Örneğin, her puanla ilişkilendirilmiş tam olarak bir tema vardır (müşteri incelemesinin ana teması). Benzer şekilde, müşteriler tek bir ülkeden gelir, kuruluşlarında tek bir üyelik türüne ve tek bir role sahiptir. Dolayısıyla açıklayıcı faktörlerimiz zaten müşterinin öznitelikleridir ve hiçbir dönüştürme yapmaya gerek yoktur. Bunlar görselde hemen kullanabilir. 

Öğreticinin devamında bire çok ilişkilerin olduğu daha karmaşık örnekleri gözden geçireceğiz. Öyle durumlarda, çözümlemenin çalıştırılabilmesi için önce sütunların toplanıp müşteri düzeyine getirilmesi gerekir.  

Açıklayıcı faktörler olarak kullanılan ölçüler ve toplamlar da **Çözümle** alanındaki ölçümün tablo düzeyinde değerlendirilir. Bu makalenin devamında bazı örnekler göreceğiz. 

## <a name="interpreting-categorical-key-influencers"></a>Kategorik ana etmenleri yorumlama 
Şimdi düşük derecelendirmelerin ana etmenlerini gözden geçirelim. 

### <a name="top-single-factor-influencing-likelihood-of-a-low-rating"></a>Düşük derecelendirme olasılığını en çok etkileyen ilk faktör

Kuruluşumuzda üç rolümüz var: tüketiciler, yöneticiler ve yayımcılar. Tüketici olmanın düşük derecelendirmeye en çok katkıda bulunan faktör olduğunu görüyoruz. 

![Role in Org is consumer (Kuruluştaki rolü tüketici) öğesini seçin](media/power-bi-visualization-influencers/power-bi-role-consumer.png)


Daha kesin olarak belirtmek gerekirse, tüketicilerimizin bize olumsuz puan verme olasılığı 2,57 kat fazladır. Ana etmen grafiğinde, soldaki listede **Role in Org is consumer** (Kuruluştaki rolü tüketici) en üstte yer alıyor. **Role in Org is consumer** seçildiğinde, Power BI soldaki bölmede bize ek ayrıntılar (her **rolün** düşük derecelendirme olasılığı üzerindeki karşılaştırmalı etkisi) gösteriyor.
  
- Tüketicilerin %14,93'ü düşük puan veriyor  
- Ortalama olarak, diğer tüm roller %5,78 oranında düşük puan veriyor 
- Dolayısıyla diğer tüm rollerle karşılaştırıldığında tüketicilerin düşük puan verme olasılığı 2,57 kat daha fazla (yeşil çubukla kırmızı noktalı çizgi arasındaki fark) 

### <a name="second-single-factor-influencing-likelihood-of-a-low-rating"></a>Düşük derecelendirme olasılığını en çok etkileyen ikinci faktör

Ana etmenler görseli faktörleri birçok farklı değişkene göre karşılaştırabilir ve derecelendirebilir.  İkinci etmenimizin **Kuruluştaki Rol** ile hiç ilgisi yok.  Listede ikinci etmen olan **Theme is usability** (Tema kullanılabilirlik) faktörünü seçin. 

![Theme is usability (Tema kullanılabilirlik) öğesini seçin](media/power-bi-visualization-influencers/power-bi-theme.png)

Burada ikinci en önemli faktörün, müşteri incelemesinin temasıyla ilgili olduğunu görüyoruz. Ürünün *kullanılabilirliği* ile ilgili yorum yapan müşterilerin düşük puan verme olasılığı diğer temalarla (güvenilirlik, tasarım veya hız gibi) ilgili yorum yapanlara göre 2,21 kat daha yüksek. 

Görseller arasında ortalamanın (kırmızı noktalı çizgi) %5,78'den %11,34'e değiştiğini görebiliyorsunuz. Ortalama, tüm diğer değerlerin ortalamasını temel aldığından dinamiktir. İlk etmende müşterinin rolü ortalamanın dışında kalıyordu, ikinci etmende ise kullanılabilirlik teması ortalamanın dışında kalıyor. 
 
Görselin en altındaki kutuya tıklandığında, görsel filtreleniyor ve yalnızca etkili değerler gösteriliyor (bu örnekte düşük puana yol açan roller). Bundan dolayı 12 temadan Power BI'ın düşük derecelendirmelere yol açtığını belirlediği dört temaya düşüyoruz. 

![onay kutusunu seçin](media/power-bi-visualization-influencers/power-bi-only-show.png)

## <a name="interacting-with-other-visuals"></a>Diğer görsellerle etkileşimli çalışma 
 
Kullanıcı bir dilimleyiciye, filtreye veya tuvaldeki başka bir görsele her tıkladığında Ana etmenler görseli yeni veri parçası üzerinde çözümlemeyi yeniden çalıştırır. Örneğin, Company Size (Şirket Boyutu) alanını rapora sürükleyelim ve dilimleyici olarak kullanalım. Kurumsal müşterilerimiz (boyutu 50.000'in üzerinde olan şirketler) için ana etmenlerin nüfusun genelinden farklı olup olmadığını görmek istiyoruz.  
 
**>50.000** seçildiğinde çözümleme yeniden çalıştırılıyor ve etmenlerin değiştiğini görebiliyoruz. Büyük kurumsal müşterilerde düşük derecelendirmelerin en önemli etmeni olarak **güvenlik** ile ilgili **Tema** görünüyor. Konuyu daha fazla araştırmak ve büyük müşterilerimizi mutsuz eden belirli güvenlik özellikleri olup olmadığını görmek istiyoruz. 

![şirket boyutuna göre dilimleme](media/power-bi-visualization-influencers/power-bi-filter.png)

## <a name="interpreting-continuous-key-influencers"></a>Sürekli ana etmenleri yorumlama 
 
Şimdiye kadar farklı kategorik alanların düşük derecelendirmeleri nasıl etkilediğini incelemek için görseli kullandık. ‘Açıklama ölçütü’ olarak süreklilik gösteren faktörler de (örneğin yaş, yükseklik, fiyat) kullanılabilir. Şimdi Customer tablosundan ‘Tenure’ (Kullanım Süresi) alanını ‘Açıklama ölçütü’ne bıraktığımızda ne olduğuna bakalım. Kullanım Süresi müşterinin hizmeti ne kadar zamandır kullandığını gösteriyor. 
 
**Tenure** değeri arttıkça düşük derecelendirme alma olasılığının da arttığını görüyoruz. Bu eğilim uzun süreli müşterilerimizin olumsuz puan verme olasılığının aslında daha yüksek olduğu izlenimi veriyor. Bu ilginç bir içgörü ve daha sonra bu konuyu takip etmek isteyebilirim.  
 
Görselleştirme bize kullanım süresinin 13,44 aya ulaştığı her durumda, ortalama olarak düşük derecelendirme olasılığının 1,23 kat arttığını söylüyor. Bu örnekte 13,44 ay kullanım süresinin standart sapması oluyor. Bizim bundan çıkardığımız içgörüde, kullanım süresini standart bir miktarda artırmanın (kullanım süresinin standart sapması) düşük derecelendirme alma olasılığını nasıl etkilediğine bakılıyor. 
 
Sağ taraftaki dağılım grafiğinde her kullanım süresi değeri için ortalama düşük derecelendirme yüzdesi çiziliyor ve eğilimi vurgulamak için bir eğilim çizgisi çiziliyor.  


![Kullanım Süresi için dağılım grafiği](media/power-bi-visualization-influencers/power-bi-tenure.png)

## <a name="interpreting-measuresaggregate-as-key-influencers"></a>Ana etmenler olarak ölçüleri/toplamları yorumlama 
 
Son olarak, kullanıcılar çözümlemelerinin içinde açıklayıcı faktörler olarak ölçüleri ve toplamları da kullanabilir. Örneğin, müşteri desteği biletlerinin sayısının veya ortalama açık bilet süresinin aldığımız puan üzerindeki etkisini görmek isteyebiliriz. 
 
Bu örnekte, müşterinin destek biletleri sayısının bize verdiği puanı etkileyip etkilemediğini görmek istiyoruz. Support Ticket (Destek Bileti) tablosundan destek bileti kimliğini getiriyoruz. Müşterinin birden çok destek bileti olabileceği için, kimliği müşteri düzeyinde toplamamız gerekiyor. Bu toplama önemli çünkü çözümlemeyi müşteri düzeyinde çalıştırıyoruz ve bu nedenle etkileyen tüm faktörleri bu ayrıntı düzeyinde tanımlamamız gerekiyor. 
 
Kimliklerin sayısına bakacağız (dolayısıyla her müşteri satırında o müşteriyle ilişkilendirilmiş destek biletlerinin sayısı olacak). Bu örnekte destek biletlerinin sayısı arttıkça derecelendirmenin düşük olma olasılığının 5,51 kat arttığını görüyoruz. Sağ taraftaki görsel farklı Rating (Derecelendirme) değerlerine göre destek biletlerinin ortalama sayısını gösteriyor (müşteri düzeyinde hesaplanmış olarak). 

![Support Ticket ID (Destek Bileti Kimliği) etkisi](media/power-bi-visualization-influencers/power-bi-support-ticket.png)



## <a name="interpreting-the-results-top-segments"></a>Sonuçları yorumlama: en üst segmentler 
 
‘Ana etmenler’ sekmesi faktörleri tek tek değerlendirmemize olanak tanır, ama kullanıcılar ‘En üst segmentler’ sekmesine geçip faktörlerin bileşiminin çözümledikleri ölçümü nasıl etkilediğini görebilir. 
 
Başlangıçta En üst segmentler Power BI tarafından bulunan tüm segmentlere genel bir bakış sağlar. Aşağıdaki örnekte altı segmentin bulunduğunu görebiliriz. Bu segmentler, segment içindeki düşük derecelendirmelerin yüzdesine göre sıralanır. Örneğin, 1. segmentte müşteri derecelendirmelerinin %74,3'ü düşüktür.  Kabarcık ne kadar yüksekteyse düşük derecelendirmelerin oranı o kadar yüksektir. Öte yandan kabarcığın boyutu segment içindeki müşterilerin sayısını temsil eder. 

![En Üst Segmentler sekmesini seçin](media/power-bi-visualization-influencers/power-bi-top-segments-tab.png)

Kabarcık seçildiğinde ilgili segmentin detayına gidilir. Örneğin 1. Segmenti seçersek, bunun görece yerleşik (29 aydan uzun süredir bizimle olan) müşterilerden oluştuğunu görürüz ve bu müşterilerin destek bileti sayısı yüksektir (4'ten çok). Son olarak, bunlar yayımcı değildir (başka bir deyişle bu müşteriler tüketici veya yöneticidir).  
 
Bu grupta, %74,3 düşük derecelendirme yapmıştır. Ortalama müşterinin düşük derecelendirme yapma oranı %11,7 olduğunu göre, bu segmentte düşük derecelendirme oranı dikkat çekici ölçüde yüksektir (63 yüzde noktası daha yüksek). Ayrıca 1. segmentin, verilerin yaklaşık %2,2'sini içerdiğini de buluruz. Dolayısıyla bu segment nüfusun dikkate alınabilir bir oranını temsil eder. 

![en üst segmentlerin ilkini seçin](media/power-bi-visualization-influencers/power-bi-top-segments2.png)

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme 
 
**Önizlemenin sınırlamaları nelerdir?** 
 
Ana etmenler görseli şu anda genel önizleme aşamasındadır ve kullanıcıların bilmesi gereken bazı sınırlamaları vardır. Şu anda kullanılamayan işlevler: 
- Toplamlardan/ölçülerden oluşan ölçümleri çözümleme 
- Görseli Power BI Embedded’de kullanma
- Görseli Power BI mobil uygulamalarında kullanma
- SSL desteği 
- Doğrudan Sorgu desteği 
- Canlı Bağlantı desteği 
 
**Hiçbir etmen/segment bulunamadığına ilişkin bir hata görüyorum. Bunun nedeni nedir?**  

![hata - hiçbir etmen bulunamadı](media/power-bi-visualization-influencers/power-bi-error1.png)


Bu hata, **Açıklama ölçütü**'ne alanları eklediğinizde ama hiçbir etmen bulunamadığında oluşur.   
- Çözümlediğiniz ölçümü hem ‘Çözümle’ hem de ‘Açıklama ölçütü’ alanına eklediniz (**Açıklama ölçütü**'nden kaldırmalısınız) 
- Açıklayıcı alanlarınızın çok az gözlem içeren çok fazla kategorisi var. Bu durumda görselleştirme hangi faktörlerin etmen olduğunu saptamakta zorlanır çünkü yalnızca birkaç gözlemle öğeleri genelleştirmek zordur 
- Açıklayıcı faktörlerinizin genelleştirme yapmak için yeterli sayıda gözlemi var ama görselleştirme raporlayabileceği anlamlı bağıntılar bulamadı 
 
**Çözümlediğim ölçümün çözümlemeyi çalıştırmak için yeterli verisi olmadığına ilişkin bir hata görüyorum. Bunun nedeni nedir?**  

![hata-yeterli veri yok](media/power-bi-visualization-influencers/power-bi-not-enough-data.png)

Görselleştirmenin çalışmasında, bir gruptaki (örneğin düşük derecelendirmeler yapan müşteriler) verilerin diğer gruplarla (örneğin yüksek derecelendirmeler yapan müşteriler) karşılaştırmalı desenlerine bakılır. Modelinizdeki verilerin çok az gözlemi olduğunda desenleri bulmak zordur. Görselleştirmenin anlamlı etmenler bulmaya yetecek kadar verisi yoksa, çözümlemeyi çalıştırmak için daha fazla veri gerektiğini belirtir. Seçilen durum (giden müşteriler) için en az 100 gözleminizin ve karşılaştırma yapmak için kullandığınız durumlar (gitmeyen müşteriler) için en az 10 gözleminiz olmasını öneririz.  
 
**‘Açıklama ölçütü’ altındaki bir alanın çözümlediğim ölçümü içeren tabloyla arasında benzersiz bir ilişki olmadığını belirten bir hata görüyorum. Bunun nedeni nedir?**  
 
Çözümleme, çözümlenen alanın tablo düzeyinde çalıştırılır. Örneğin, hizmetiniz için müşteri geri bildirimlerini çözümlüyorsanız müşterinin yüksek derecelendirme mi yoksa düşük derecelendirme mi yaptığını gösteren bir tablonuz olabilir. Bu durumda, çözümlemeniz müşteri tablosu düzeyinde çalıştırılabilir. 

Bununla ilişkili olan ve ölçümünüzü içeren tablodan daha yüksek ayrıntı düzeyiyle tanımlanan bir tablonuz varsa, bu hatayla karşılaşırsınız. Şimdi bunu bir örnekle gösterelim: 
 
- Hizmetiniz için düşük derecelendirmeler yapan müşterileri neyin yönlendirdiğini çözümlüyorsunuz 
- Müşterinin hizmetinizi kullandığı cihazın, değerlendirmesini etkileyip etkilemediğini görmekle ilgileniyorsunuz 
- Müşteri bir hizmeti birçok farklı yolla kullanabilir   
- Aşağıdaki örnekte, kimlik numarası 10000000 olan müşteri hizmetle etkileşim kurmak için hem tarayıcı hem de tablet kullanıyor 

![hata - bununla ilişkili olan ve ölçümünüzü içeren tablodan daha yüksek ayrıntı düzeyiyle tanımlanan bir tablonuz vardır](media/power-bi-visualization-influencers/power-bi-error2.png)

Açıklayıcı faktör olarak cihaz sütununu kullanmaya çalışırsanız aşağıdaki hatayı görürsünüz: 

![hata-yanlış sütun](media/power-bi-visualization-influencers/power-bi-error3.png)

Bunun nedeni cihazın müşteri düzeyinde tanımlanmamış olmasıdır (bir müşteri birden çok cihazda hizmeti kullanabilir). Görselleştirmenin desenleri bulabilmesi için cihazın müşteri için bir özniteliğe dönüşmesi gerekir. Bu durumda, iş anlayışıma bağlı olarak birkaç çözümüm vardır: 
 
- Örneğin, cihaz sayısının müşterinin verdiği puan üzerinde etkisi olduğuna inanıyorsam cihazın özetleme şeklini cihaz sayısı olarak değiştirebilirim 
- Hizmeti belirli bir cihazda kullanmanın müşteri derecelendirmesini etkileyip etkilemediğini görmek için cihaz sütununu özetleyebilirim  
 
Bu örnekte, verilerimi özetleyerek ‘tarayıcı, ‘mobil ve ‘tablet için yeni sütunlar oluşturdum. Artık bunları ‘Açıklama ölçütü’ olarak kullanabilirim. Aslında tüm cihazların birer etmen olduğunu ve müşteri puanında en büyük etkinin tarayıcıya ait olduğunu buluruz. 

Daha kesin belirtmek gerekirse, hizmeti tarayıcıyla kullanmayan müşterilerin düşük puan verme olasılığı tarayıcı kullananlardan 3,79 kat fazladır. Listenin alt kısmında mobil uygulama için bunun tersinin doğru olduğunu görürüz. Mobil uygulama kullanan müşterilerin düşük puan verme olasılığı kullanmayanlara göre daha yüksektir.  

![hata-çözüldü](media/power-bi-visualization-influencers/power-bi-error3-solution.png)

**Ölçülerin çözümlememe dahil edilmediğine ilişkin bir uyarı görüyorum. Bunun nedeni nedir?** [2052261] 

![hata-ölçüler dahil değil](media/power-bi-visualization-influencers/power-bi-measures-not-included.png)


Çözümleme, çözümlenen alanın tablo düzeyinde çalıştırılır. Müşteri kaybını çözümlüyorsanız bir müşterinin gidip gitmediğini bildiren bir tablonuz olabilir. Bu durumda, çözümlemeniz müşteri tablosu düzeyinde çalıştırılabilir.
 
Ölçüler ve toplamlar varsayılan olarak tablo düzeyinde çözümlenir. ‘Ortalama aylık harcama’ için bir ölçümüz olsaydı, bu ölçü müşteri tablosu düzeyinde çözümlenebilirdi.  

Müşteri tablosunun benzersiz tanımlayıcısı yoksa, ölçüyü hesaplayamayız ve bu ölçü çözümleme tarafından yoksayılır. Bunu önlemek için, ölçümünüzün bulunduğu tablonun (bu örnekte müşteri tablosu) benzersiz tanımlayıcısı (örneğin, müşteri kimliği) olmasına dikkat edin. Ayrıca Power Query kullanarak kolayca bir dizin sütunu eklenebilir.
 
**Çözümlediğim ölçümün 10'dan fazla benzersiz değeri olduğuna ve bu durumun çözümlememin kalitesini etkileyebileceğine ilişkin bir uyarı görüyorum. Bunun nedeni nedir?**  

AI görselleştirmesi kategorileri çözümleyecek şekilde iyileştirilmiştir (örneğin, Kayıp için ‘Evet’ veya ‘Hayır’, Müşteri Memnuniyeti için ‘Yüksek’, ‘Orta’ veya ‘Düşük’). Çözümlenecek kategori sayısının artması kategori başına daha az gözlemimiz olduğu anlamına gelir ve görselleştirmenin verilerdeki desenleri bulması zorlaşır. 

Daha güçlü etmenler bulabilmek için benzer değerlerin tek bir birimde gruplandırılmasını öneririz. Örneğin fiyat için bir ölçümünüz varsa, tek tek fiyat noktalarını kullanmak yerine benzer fiyatları ‘Yüksek’, ‘Orta’, ‘Düşük’ gibi demetlerde gruplandırarak daha iyi sonuçlar elde edebilirsiniz. 

![hata-ondan fazla benzersiz faktör var](media/power-bi-visualization-influencers/power-bi-error4.png)


**Verilerimde ana etmen olması gerekiyor gibi görünen ama öyle olmayan faktörler var. Bu nasıl olur?**

Aşağıdaki örnekte tüketici olan müşterilerin düşük derecelendirmeler yaptığını görüyoruz (derecelendirmelerin %14,93'ü düşük). İlginç olan, yönetici rolünde de düşük derecelendirme oranı yüksek olmasına karşın (%13,42) bunun bir etmen olarak kabul edilmemesidir. 

Bunun ardındaki neden, görselleştirmenin etmenleri bulurken veri noktalarının sayısını da dikkate almasıdır. Aşağıdaki örnekte 29.000'den çok tüketicimiz varken yöneticilerin sayısın bunun onda biri kadardır (yaklaşık 2.900). Üstelik, bunlardan yalnızca 390 tanesi düşük derecelendirme yapmıştır. Dolayısıyla görselin yönetici derecelendirmelerinde gerçekten bir desen mi bulduğunu yoksa bunun rastlantı mı olduğunu saptamak için yeterli verisi yoktur.  

![hata-etmenler nasıl saptanır](media/power-bi-visualization-influencers/power-bi-error5.png)

**Ana etmenleri nasıl hesaplıyorsunuz?**

AI görselleştirmesi ana etmenleri hesaplamak için [ML.NET](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet) kullanarak arka planda bir lojistik regresyon çalıştırır. Lojistik regresyon, farklı grupları birbiriyle karşılaştıran istatistiksel bir modeldir. Düşük derecelendirmeye neyin yol açtığına bakıyor olsaydık, lojistik regresyon düşük puan veren müşterilerin yüksek puan verenlerden ne açıdan farklı olduğuna bakardı. Birden çok kategorimiz olsaydı (yüksek puan, nötr puan, düşük puan), düşük derecelendirme yapan müşterilerin diğerlerinden ne açıdan farklı olduğuna bakardık (bunlarla yüksek derecelendirme VEYA nötr derecelendirme yapanlar arasındaki fark). 
 
Lojistik regresyon verilerdeki desenleri arar; düşük derecelendirme yapan müşterilerin yüksek derecelendirme yapanlardan ne açıdan farklı olduğuna bakar. Örneğin, daha fazla destek bileti olan müşterilerin düşük derecelendirme yapma yüzdesinin destek bileti az olan veya hiç olmayanlardan çok daha yüksek olduğunu bulabilir.
 
Lojistik regresyon kaç veri noktası olduğunu da göz önünde bulundurur. Örneğin yönetici rolü üstlenen müşteriler nispeten daha fazla olumsuz puan veriyorsa ama çok az yönetici varsa, bu bir etmen olarak göz önüne alınmaz. Çünkü bir desen çıkarmaya yetecek kadar veri noktası yoktur. Bir faktörün etmen olarak kabul edilip edilmeyeceğini saptamak için bir istatistik testi (Wald testi) kullanılır. Görsel, eşiği belirlemek için 0,05 p-değeri kullanır. 


**Segmentleri nasıl hesaplıyorsunuz?**

AI Görselleştirmesi ilginç alt grupları bulmak için [ML.NET](https://dotnet.microsoft.com/apps/machinelearning-ai/ml-dotnet) kullanarak arka planda bir karar ağacı çalıştırır. Karar ağacının amacı ilgilendiğimiz ölçümde görece çok veri noktasından oluşan bir alt grup bulmaktır (örneğin, düşük derecelendirme yapan müşteriler). 

Karar ağacı açıklayıcı faktörlerin her birini alır ve hangi faktörün en iyi ‘bölünmeyi’ sağlayacağını gerekçelendirmeyi dener. Örneğin yalnızca büyük kurumsal müşterileri içerecek şekilde verileri filtrelersek, bizim için yüksek derecelendirme yapan müşterileri düşük derecelendirme yapanlardan ayırmış olur muyuz? Belki de yalnızca güvenlik hakkında yorum yapan müşterileri içerecek şekilde filtrelemek daha iyi sonuç verecektir. 

Karar ağacı verileri böldükten sonra söz konusu veri alt grubunu (örneğin, güvenlik hakkında yorum yapan müşteriler) alır ve yalnızca bu verilerde bir sonraki uygun bölmenin ne olacağını bulmaya çalışır. Her bölme işleminden sonra, bir desen çıkarmak için bunun yeterli veri noktası içeren bir temsil grubu mu yoksa verilerdeki bir anomali mi olduğunu da (dolayısıyla gerçek bir segment olmadığını) dikkate alır. (Bölme koşulunun istatistiksel açıdan anlamlı olup olmadığını denetlemek için 0,05 p-değeriyle başka bir istatistik testi uygulanır). 

Karar ağacının çalışması bittiğinde, tüm bölmeleri alır (güvenlik yorumları, büyük kuruluş) ve Power BI filtrelerini oluşturur. Bu filtre bileşimi görselde bir segment olarak paketlenir. 
 
**‘Açıklama Ölçütü’ altına daha fazla alan sürükledikçe neden bazı faktörler etmen haline geliyor veya etmen olmaktan çıkıyor?**

Görselleştirme tüm açıklayıcı faktörleri birlikte değerlendirir. Başka bir deyişle bir faktör kendi başına bir etmen olabilir ama diğer faktörlerle birlikte değerlendirildiğinde etmen olmayabilir. Açıklayıcı faktörler olarak yatak odası sayısı ve evin boyutunu kullanıp bir evin fiyatını neyin yükselttiğini çözümlediğimizi düşünün: 
- Kendi başına, daha fazla yatak odası ev fiyatlarını yukarı çekebilir 
- Evin boyutu da çözümlemeye eklendiğinde, artık evin boyutunu sabit tutarak yatak odası sayısına ne olduğuna bakarız 
- Evin boyutunu 140 metrekareye sabitlersek, sürekli artan yatak odası sayısının ev fiyatını ciddi düzeyde artırması düşük bir olasılıktır. Evin boyutu göz önüne alınınca, yatak odası sayısı artık eskisi kadar önemli bir faktör olmayabilir. 




## <a name="next-steps"></a>Sonraki adımlar
[Power BI'daki birleşik grafikler](power-bi-visualization-combo-chart.md)

[Power BI'daki görselleştirme türleri](power-bi-visualization-types-for-reports-and-q-and-a.md)
