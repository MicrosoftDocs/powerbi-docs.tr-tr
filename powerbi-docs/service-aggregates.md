---
title: "Power BI'da toplama işlemleri (toplam, ortalama, maksimum vb.)"
description: "Power BI'da bulunan bir grafikteki toplama işlemini (toplam, ortalama, maksimum vb.) değiştirme"
services: powerbi
documentationcenter: 
author: mihart
manager: kfile
backup: 
editor: 
tags: 
qualityfocus: modifying
qualitydate: 
ms.service: powerbi
ms.devlang: NA
ms.topic: article
ms.tgt_pltfrm: NA
ms.workload: powerbi
ms.date: 09/23/2017
ms.author: mihart
ms.openlocfilehash: c1b926e129e8d82edd9c329a51623908c4e7c9e0
ms.sourcegitcommit: 8f72ce6b35aa25979090a05e3827d4937dce6a0d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/27/2017
---
# <a name="aggregates-in-power-bi"></a>Power BI'da toplama işlemleri
## <a name="what-is-an-aggregate"></a>Toplam neye denir?
Bazen bir sütundaki değerleri matematiksel olarak birleştirmeniz gerekir. Bu matematiksel işlem toplam, ortalama, maksimum, sayı vb. olabilir. Bir sütundaki satırlarda bulunan veri değerlerini birleştirmeye toplama adı verilir. Bu matematik işleminin sonucu *toplam* olarak adlandırılır. 

Sayısal alanlar, toplanacak (örneğin, kategorik bir alanda toplanacak veya ortalaması alınacak) değerlerdir.  Örnek olarak, "ürüne göre satış miktarı" ve "bölgeye göre hata sayısı" verilebilir. Sayısal alanlar genellikle **ölçüler** olarak adlandırılır. Alanlar listesinde ölçüler ∑ sembolüyle gösterilir. Daha fazla bilgi için bkz. [The report editor... take a tour (Rapor düzenleyicisi için tura katılın)](service-the-report-editor-take-a-tour.md).

Bazı *ölçüler* aslında birer *hesaplanmış ölçüdür*. Power BI'daki hesaplanmış ölçüler verilerle birlikte içeri aktarılır (raporunuzun kullandığı veri modelinde tanımlandığı şekilde). Her hesaplanmış ölçünün kendi sabit kodlanmış formülü vardır. Kullanılan toplama işlemini değiştiremezsiniz. Örneğin, işlem bir toplamsa yalnızca bir toplam olarak kalabilir. Alanlar listesinde, *hesaplanmış ölçüler* hesap makinesi sembolüyle gösterilir. Hesaplanmış ölçü oluşturma ile ilgili daha fazla bilgi için bkz. [Power BI Desktop'taki ölçüler](desktop-measures.md).

Kategorik alanlar sayısal değildir ancak yine de toplanabilir.  Kategorik alanlar, **Değerler** veya **Araç ipuçları** gibi *yalnızca sayısal* bir demete yerleştirildiğinde, Power BI, her bir kategoriye ilişkin oluşumları veya her bir kategoriye ilişkin benzersiz oluşumları sayabilir.  Power BI, dizeler ve tarihler için birkaç toplama seçeneği daha sunar: en erken, en geç, ilk ve son.  

## <a name="why-dont-aggregates-work-the-way-i-want-them-to"></a>Toplama işlemleri neden istediğim şekilde gerçekleştirilmiyor?
Power BI hizmetinde toplama işlemleri gerçekleştirmek karmaşık gelebilir. Bir sayısal alanın söz konusu olması durumunda Power BI toplama işleminin değiştirilmesine izin vermiyor olabilir. Yıl gibi bir alanı ele alırken bu alanı toplamak değil, yalnızca oluşumları saymak istiyor da olabilirsiniz.

Çoğunlukla sorun, alanın Power BI veri kümesinde nasıl kategoriye ayrıldığıyla ilgilidir. Belki de alan metin olarak kategoriye ayrılmıştır; bu, neden toplanamadığı veya ortalamasının alınamadığı konusuna açıklama getirir. Ne yazık ki, [bir alanın kategorisi yalnızca veri kümesi sahibi tarafından değiştirilebilir](desktop-measures.md).  

Bu karmaşıklıktan sıyrılabilmeniz için bu makalenin sonuna **İpuçları ve sorun giderme** adlı özel bir bölüm ekledik.  Cevabı bu bölümde bulamamanız halinde, doğrudan Power BI ekibinden hızlı bir cevap almak için sorunuzu [Power BI Topluluğu forumunda](http://community.powerbi.com) yayınlayın.

## <a name="change-how-a-numeric-field-is-aggregated"></a>Bir sayısal alana yönelik toplama işlemini değiştirme
Farklı bölgelerdeki satış verilerinin toplandığı bir grafiğinizin olduğunu ancak sizin ortalamaya ihtiyaç duyduğunuzu varsayalım. 

1. Rapor Düzenleme görünümü'nde, ölçüyü bir görselleştirmeye ekleyin.
2. Görsel Öğeler bölmesinde söz konusu alanı bulun, sağ tıklayın ve ihtiyacınız olan toplama türünü seçin. İhtiyaç duyduğunuz toplama türünü görmüyorsanız veri kümesi sahibiyle iletişime geçin. Sorun, sahibin alanı hangi kategoriye dahil ettiğiyle ilgili olabilir.  
   
   ![](media/service-aggregates/aggregate_new.png)
   
   > [!NOTE]
   > Açılan menüde yer alan seçenekler şu iki unsura göre değişiklik gösterir: 1) seçilen alan ve 2) alanın veri kümesi sahibi tarafından kategoriye ayrılma şekli.
   > 
   > 

Bir alanı toplamak için kullanılabilen seçeneklerden bazıları şunlardır:

* **Özetleme**. Bu seçenek belirlendiğinde, alandaki her bir alan ayrı bir şekilde ele alınır ve özetlenmez. Genellikle bu seçenek, toplanmaması gereken bir sayısal kimlik sütunu bulunduğunda kullanılır.
* **Toplam**. Bu, alandaki tüm değerleri toplar.
* **Ortalama**. Değerlerin aritmetik ortalamasını alır.
* **Minimum**. En küçük değeri gösterir.
* **Maksimum**. En büyük değeri gösterir.
* **Sayı (Boş Olanları Değil).** Bu, alandaki boş olmayan değerleri sayar.
* **Sayı (Benzersiz).** Bu, alandaki farklı değerleri sayar.
* **Standart sapma.**
* **Varyans**.
* **Ortanca**.  Ortanca (ortadaki) değeri gösterir. Bu, üstünde ve altında aynı sayıda öğe bulunan değerdir.  2 ortancanın bulunması halinde Power BI, bu değerlerin ortalamasını alır.

Örneğin, aşağıdaki veriler kullanıldığında,

| Ülke | Miktar |
|:--- |:--- |
| Amerika Birleşik Devletleri |100 |
| Birleşik Krallık |150 |
| Kanada |100 |
| Almanya |125 |
| Fransa | |
| Japonya |125 |
| Avustralya |150 |

Şu sonuçları elde edersiniz:

* **Özetleme**: Her değer ayrı bir şekilde gösterilir
* **Toplam**: 750
* **Ortalama**: 125
* **Maksimum**: 150
* **Minimum**: 100
* **Sayı (Boş Olanları Değil):** 6
* **Sayı (Benzersiz):** 4
* **Standart sapma:** 20,4124145...
* **Varyans:** 416,666...
* **Ortanca:** 125

## <a name="use-a-non-aggregated-field-as-a-numeric-field"></a>Toplanmayan bir alanı sayısal alan olarak kullanma
Toplanmayan bir alanı sayısal alan olarak da kullanabilirsiniz. Örneğin, bir Ürün Adı alanına sahipseniz bu alanı bir değer olarak ekleyebilir ve **Sayı** veya **Ayrı sayım** olarak ayarlayabilirsiniz. 

1. Örneğin, **Store > Chain** seçeneğini belirlediğinizi varsayalım.
   
   ![](media/service-aggregates/count-of-chain-do_not_summarize.png)
2. **Özetleme** olan varsayılan toplama işlemini **Sayı (Benzersiz)** olarak değiştirirseniz Power BI, farklı zincirleri sayar. Bu örnekte, 2 farklı zincir vardır: Fashions Direct ve Lindseys.
   
   ![](media/service-aggregates/aggregates_count.png)
3. Toplama işlemini **Sayı** olarak değiştirmeniz durumunda ise Power BI, toplam sayıyı verir. Bu örnekte, **Chain** için 104 giriş vardır. **Chain** filtresini eklediğinizde, Fashions Direct için 37 satır, Lindseys için ise 67 satır bulunduğunu görürsünüz.  
   
   ![](media/service-aggregates/count_of_chain_104.png)

## <a name="tips-and-troubleshooting"></a>İpuçları ve Sorun Giderme
S:  **Özetleme** seçeneğini neden görmüyorum?

C:  Seçtiğiniz alan büyük olasılıkla bir hesaplanmış ölçüdür. Her hesaplanmış ölçünün kendi sabit kodlanmış formülünün bulunduğunu unutmayın. Hesaplamayı değiştiremezsiniz.

S:  Alanım **sayısal** olmasına rağmen neden yalnızca **Sayı** ve **Ayrı sayım** seçeneklerini görüyorum?

C:  Bu, büyük olasılıkla veri sahibinin kasıtlı olarak veya yanlışlıkla, alanı bir sayı olarak *sınıflandırmamasından* kaynaklanır. Örneğin, bir veri kümesinde **yıl** alanı yer alıyorsa veri kümesi sahibi, **yıl** alanının sayılması (ör. 1974'te doğan kişi sayısı) daha olası bir durum olduğundan (toplanmak veya ortalaması alınmak yerine) bu alanı metin kategorisine dahil etmiş olabilir. Veri kümesinin sahibi sizseniz veri kümesini Power BI Desktop'ta açabilir ve **Modelleme** sekmesini kullanarak veri türünü değiştirebilirsiniz.  

C:  Alanı yalnızca kategorik değerlere izin veren bir *demete* de yerleştirmiş olabilirsiniz.  Bu durumda, yalnızca sayı ve ayrı sayım seçeneklerine sahip olursunuz.

C:  Bir eksen alanı kullanıyor olmanız da üçüncü bir olasılıktır. Örneğin; Power BI, bir çubuk grafik ekseninde her benzersiz değer için tek bir çubuk gösterir; alan değerlerine yönelik olarak toplama gerçekleştirmez. 

>[!NOTE]
>X ve Y eksenleri için değerlerin toplanmasını *gerektiren* dağılım grafikleri bu konuda bir istisna oluşturur.


S:  Bir dağılım diyagramına sahibim ve alanımın *toplanmamasını* sağlamak istiyorum.  Bunu nasıl yaparım?

C:  Alanı, X veya Y ekseni demetlerine değil, **Ayrıntılar** demetine ekleyin.

S:  Bir görselleştirmeye sayısal alan eklediğimde, alanların çoğu için varsayılan işlem toplam işlemi olarak ayarlanırken bazıları için de sayı veya başka bir toplama işlemi olarak belirleniyor.  Varsayılan toplama işlemi neden aynı kalmıyor?

C:  Veri kümesi sahipleri, her bir alan için varsayılan özetlemeyi ayarlama seçeneğine sahiptir. Bir veri kümesi sahibiyseniz Power BI Desktop'ın **Modelleme** sekmesindeki varsayılan özetlemeyi değiştirin.

S:  Alanım **sayısal** olmasına rağmen, açılan menüde neden toplama seçeneklerini görmüyorum?

C:  Alanda bir hesap makinesi simgesi bulunuyorsa bu, alanın *hesaplanmış ölçü* olduğunu gösterir ve her bir hesaplanmış ölçü, Power BI hizmetinde değiştirilemeyen kendi sabit kodlanmış formülüne sahiptir. Kullanılan hesaplama ortalama veya toplam gibi basit bir toplama işlemi olabilirken, "üst kategoriye katkıda bulunma yüzdesi" ya da "yılın başlangıcından itibaren değişen toplam" gibi daha karmaşık bir işlem de olabilir. Power BI, sonuçları toplamaz veya bunların ortalamasını almaz ancak bunun yerine, her bir veri noktası için yeniden hesaplama yapar (sabit kodlanmış formülü kullanarak).

S:  Ben bir veri kümesi sahibiyim ve bir alanın hiçbir zaman toplanmamasını sağlamak istiyorum.

C:  Power BI Desktop'taki **Modelleme** sekmesinde, **Veri türü**'nü **Metin** olarak ayarlayın.

S:  Açılan menüde **Özetleme** seçeneği görünmüyor.

C:  Alanı kaldırıp tekrar eklemeyi deneyin.

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)

