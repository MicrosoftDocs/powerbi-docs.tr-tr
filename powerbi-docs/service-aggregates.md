---
title: Power BI hizmetinde toplamlar (toplam, ortalama vb.) ile çalışma
description: Toplama, Power BI hizmetinde bir hesap (toplam, ortalama, maksimum ve benzeri) değiştirileceğini öğrenin.
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-service
ms.topic: conceptual
ms.date: 05/03/2019
ms.author: mblythe
ms.custom: seodec18
LocalizationGroup: Reports
ms.openlocfilehash: 7cee05df6a7d13e18bc31bc1a1f34a5f89711c0d
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2019
ms.locfileid: "65710609"
---
# <a name="work-with-aggregates-sum-average-and-so-on-in-the-power-bi-service"></a>Power BI hizmetinde toplamlar (toplam, ortalama vb.) ile çalışma

## <a name="what-is-an-aggregate"></a>Toplam neye denir?

Bazı durumlarda verilerinizdeki değerleri matematiksel olarak birleştirmek istersiniz. Bu matematiksel işlem toplam, ortalama, maksimum, sayısı vb. olabilir. Verilerinizdeki değerleri birleştirmek için gerçekleştirdiğiniz adlı *toplayarak*. Bu matematik işleminin sonucu *toplam* olarak adlandırılır.

Power BI hizmetinde ve Power BI Desktop'ta görselleştirmeler oluşturulurken verileriniz toplanabilir. Genellikle tüm ihtiyacınız olan toplama ulaşmaktır ancak belirli durumlarda değerleri farklı bir şekilde toplamanız gerekebilir.  Örneğin, toplam yerine ortalama. Yönetme ve Power BI görselleştirmeleri kullanır toplama değiştirmek için birkaç farklı yolu vardır.

İlk olarak, verileri bir göz atalım *türleri* çünkü nasıl ve hangi olup, Power BI, toplayabilirsiniz verilerin türünü belirler.

## <a name="types-of-data"></a>Veri türleri

Çoğu veri kümesinde birden fazla türde veri bulunur. En temel düzeyde veriler, sayısal ya da değildir. Power BI, sayısal veriler toplam, ortalama, sayısı, minimum, varyans ve çok daha fazlasını kullanarak toplayabilirsiniz. Hizmet bile genellikle adlı metinsel veriler toplayabilirsiniz *kategorik* veri. Yalnızca sayısal bir kova gibi yerleştirerek Kategorik bir alanı toplamak çalışırsanız **değerleri** veya **araç ipuçları**, Power BI her bir kategoriye ilişkin oluşumları veya her ilişkin benzersiz oluşumları sayabilir Kategori. Özel tarihler gibi bir veri türlerine sahip birkaç toplama seçeneği kendi: en erken, en geç, ilk ve son.

Aşağıdaki örnekte:

- **Units Sold** ve **Manufacturing Price** sayısal veriler içeren sütunlardır

- **Segment**, **Country**, **Product**, **Month** ve **Month Name** sütunları ise kategorik veriler içerir

   ![Bir örnek veri kümesinin ekran görüntüsü.](media/service-aggregates/power-bi-aggregate-chart.png)

Power BI'da bir görselleştirme oluştururken, hizmet sayısal alanlar toplayacak (varsayılan değer *toplam*) bazı kategorik alanlarla.  Örneğin, "Units Sold ***ürüne göre***", "Units Sold ***aya göre***" ve "Manufacturing Price ***segmente göre***". Power BI, bazı sayısal alanlara başvurduğu **ölçüler**. --Power BI rapor düzenleyicisinde ölçüleri kolayca **alanları** listede ölçüler yanında ∑ sembolü ile gösterilir. Bkz: [rapor Düzenleyicisi... tura katılın](service-the-report-editor-take-a-tour.md) daha fazla bilgi için.

![Ekran görüntüsü, Power BI ile çağrılan alanlar listesi.](media/service-aggregates/power-bi-aggregate-fields.png)

## <a name="why-dont-aggregates-work-the-way-i-want-them-to"></a>Toplama işlemleri neden istediğim şekilde gerçekleştirilmiyor?

Power bı'da toplama işlemleri ile çalışma, hizmet kafa karıştırıcı olabilir. Bir sayısal alana sahip olabilir ve Power BI toplama işleminin değiştirilmesine izin vermiyor. Yıl gibi bir alanı ele alırken bu alanı toplamak değil, yalnızca oluşumları saymak istiyor da olabilirsiniz.

Genellikle, temel alınan veri kümesi alan tanımında sorunudur. Belki de veri kümesi sahibi alan metin olarak tanımlanmış ve Power BI neden Topla veya ortalama bunu açıklar. Ne yazık ki, [bir alanın kategorisi yalnızca veri kümesi sahibi tarafından değiştirilebilir](desktop-measures.md). Bu nedenle Desktop'ta veya veri kümesini (Excel gibi) oluşturmak için kullanılan program veri kümesine sahip izinleriniz varsa bu sorunu düzeltebilirsiniz. Aksi halde, yardım almak için veri kümesinin sahibine ulaşmanız gerekir.  

Özel bir bölümü olarak adlandırılan bu makalenin sonunda [ **önemli noktalar ve sorun giderme**](#considerations-and-troubleshooting). Bu, ipuçları ve rehberlik sağlar. Sorunuzun cevabı Bu bölümde bulamamanız halinde gönderin [Power BI topluluğu Forumunda](http://community.powerbi.com). Doğrudan Power BI ekibinden hızlı bir cevap alırsınız.

## <a name="change-how-a-numeric-field-is-aggregated"></a>Bir sayısal alana yönelik toplama işlemini değiştirme

Farklı ürünler için satılan birim sayısının toplandığı bir grafiğe sahip olduğunuzu ancak bunun yerine ortalamaya ihtiyaç duyduğunuzu varsayalım.

1. Oluşturma bir **kümelenmiş sütun grafik** bir ölçü ve bir kategori kullanır. Bu örnekte, Units Sold by Product grafiğini kullanmayı tercih ettik.  Varsayılan olarak, Power BI satılan birim toplayan bir grafik oluşturur. (ölçüsüne sürükleyin **değer** iyi) her ürün için (kategoriye sürükleyin **eksen** da).

   ![Çağrılan toplam grafiği ve görsel öğeler bölmesindeki alanlar listesinde görüntüsü.](media/service-aggregates/power-bi-aggregate-sum.png)

1. İçinde **görselleştirmeler** bölmesinde ölçüye sağ tıklayın ve ihtiyacınız olan toplama türünü seçin. Bu durumda, biz seçeneğini belirliyoruz **ortalama**. Toplama görmüyorsanız, görmeniz gereken [ **önemli noktalar ve sorun giderme** ](#considerations-and-troubleshooting) bölümü.

   ![Ortalama toplam listesinin ekran, seçilen ve çekilerek.](media/service-aggregates/power-bi-aggregate-average.png)

   > [!NOTE]
   > Aşağı açılan listede kullanılabilir seçenekleri 1) bir alana bağlı olarak farklılık gösterir ve bu alanı yolu 2) veri kümesi sahibi kategorilere.

1. Görselleştirmeniz artık ortalama işlemiyle toplanmaktadır.

   ![Ürüne göre ortalama, Units Sold artık görüntüleme grafiğin ekran görüntüsü.](media/service-aggregates/power-bi-aggregate-average-2.png)

## <a name="ways-to-aggregate-your-data"></a>Verilerinizi toplamak için izleyebileceğiniz yollar

Bir alanı toplamak için kullanılabilen seçeneklerden bazıları şunlardır:

- **Özetleme**. Bu seçenekle, seçilen Power BI bu alandaki her değer ayrı olarak değerlendirir ve özetleyin değil. Hizmet toplamı olmamalıdır bir sayısal kimlik sütunu varsa bu seçeneği kullanın.

- **Toplam**. Bu alandaki tüm değerleri toplar.

- **Ortalama**. Değerlerin aritmetik ortalamasını alır.

- **Minimum**. En küçük değeri gösterir.

- **Maksimum**. En büyük değeri gösterir.

- **Sayı (Boş Olanları Değil).** Alandaki boş olmayan değerleri sayar.

- **Sayı (Benzersiz).** Bu alandaki farklı değerleri sayar.

- **Standart sapma.**

- **Varyans**.

- **Ortanca**.  Ortanca (ortadaki) değeri gösterir. Bu değerin üstünde ve altında aynı sayıda öğe vardır.  İki ortancanın bulunması halinde Power BI, bu değerlerin ortalamasını alır.

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

- **Özetleme**: Her değer ayrı bir şekilde gösterilir

- **Toplam**: 750

- **Ortalama**: 125

- **Maksimum**:  150

- **Minimum**: 100

- **Sayı (Boş Olanları Değil):** 6

- **Sayı (Benzersiz):** 4

- **Standart sapma:** 20,4124145...

- **Varyans:** 416,666...

- **Ortanca Değer:** 125

## <a name="create-an-aggregate-using-a-category-text-field"></a>Bir kategori (metin) alanı kullanarak toplam oluşturma

Sayısal olmayan bir alanı da toplayabilirsiniz. Örneğin, bir ürün adı alanına sahipseniz bu alanı bir değer olarak ekleyebilir ve **Sayı**, **Ayrı sayım**, **İlk** veya **Son** olarak ayarlayabilirsiniz.

1. Sürükleme **ürün** alanını **değerleri** iyi. **Değerleri** de genellikle sayısal alanlar için kullanılır. Power BI, bu alan bir metin alanıdır, toplama ayarlar tanır **özetleme**, tek sütunlu bir tablo sunar.

   ![Değerlerin iyi ürün alanının ekran görüntüsü.](media/service-aggregates/power-bi-aggregate-value.png)

1. Varsayılan toplama değiştirirseniz **özetleme** için **sayı (benzersiz)** , Power BI, farklı ürünleri sayar. Bu durumda, var olan dört.
  
   ![Ekran görüntüsü ürünler ayrı sayımı.](media/service-aggregates/power-bi-aggregate-count.png)

1. Toplama işlemini **Sayı** olarak değiştirmeniz durumunda ise Power BI, toplam sayıyı verir. Bu durumda, için yedi giriş vardır **ürün**.

   ![Ekran görüntüsü ürünler sayısı.](media/service-aggregates/power-bi-aggregate-count-2.png)

1. Aynı alanı sürükleyerek (Bu durumda **ürün**) içine **değerleri** kutusuna sürükleyip varsayılan toplamayı **özetleme**, Power BI, sayı böler Ürün.

   ![Ürün ve ürün sayısı ekran görüntüsü.](media/service-aggregates/power-bi-aggregate-final.png)

## <a name="considerations-and-troubleshooting"></a>Önemli Noktalar ve Sorun Giderme

S:  **Özetleme** seçeneğini neden görmüyorum?

C:  Seçtiğiniz alan büyük olasılıkla, Excel veya [Power BI Desktop](desktop-measures.md)’ta oluşturulan bir hesaplanmış ya da gelişmiş ölçüdür. Her hesaplanmış ölçünün kendi sabit kodlanmış formülü vardır. Power BI'ı kullanan toplama işlemini değiştiremezsiniz. Örneğin, toplama işlemi toplam ise yalnızca toplam olarak kalabilir. **Alanları** listesinde gösterir *hesaplanmış ölçüler* hesap makinesi simgesiyle.

S:  Alanım **sayısal** olmasına rağmen neden yalnızca **Sayı** ve **Ayrı sayım** seçeneklerini görüyorum?

C1:  Veri kümesi sahibi olduğunu büyük olasılıkla açıklaması olan *değil* alanın bir sayı olarak sınıflandırılmış. Örneğin, bir veri kümesi varsa bir **yıl** alan, veri kümesi sahibi değeri metin olarak kategorilere. Power BI'ın sayılır daha büyük bir olasılıkla **yıl** alan (örneğin, içinde 1974 doğan kişi sayısı). Power BI Topla veya ortalama, bunu daha az olasıdır. Sahibi sizseniz veri kümesini Power BI Desktop'ta açın ve kullanmak **modelleme** veri türünü değiştirmek için sekmesinde.

C2: Alanda bir hesap makinesi simgesi bulunuyorsa anlamına olduğu bir *hesaplanmış ölçüdür*. Her ölçü, yalnızca veri kümesi sahibi kendi sabit kodlanmış formülüne sahiptir. Power BI'ı kullanan hesaplama ortalama veya toplam gibi basit bir toplama olabilir. Ayrıca, yüzdesi"üst kategoriye katkıda bulunma" gibi bir şey daha karmaşık veya "Toplam yılın başlangıcından itibaren" olabilir. Power BI Topla veya ortalama sonuçları bozmayacağı. Bunun yerine, yalnızca (sabit kodlanmış formülü kullanarak) her veri noktası için yeniden hesaplar.

C3:  Alanı yalnızca kategorik değerlere izin veren bir *demete* de yerleştirmiş olabilirsiniz.  Bu durumda, yalnızca sayı ve ayrı sayım seçeneklerine sahip olursunuz.

C4:  Ve bir dördüncü bir eksen alanı kullanıyor bir olasılıktır. Örneğin; Power BI, bir çubuk grafik ekseninde her benzersiz değer için tek bir çubuk gösterir; alan değerlerine yönelik olarak toplama gerçekleştirmez.

>[!NOTE]
>X ve Y eksenleri için değerlerin toplanmasını *gerektiren* dağılım grafikleri bu konuda bir istisna oluşturur.

S:  SQL Server Analysis Services (SSAS) veri kaynaklarının metin alanlarını neden toplayamıyorum?

Y:  SSAS çok boyutlu modelleriyle kurulan canlı bağlantılar ilk, son, maksimum, minimum ve toplam gibi istemci tarafı toplama işlemlerine izin vermez.

S:  Bir dağılım grafiğine sahibim ve alanımın *toplanmamasını* sağlamak istiyorum.  Nasıl yapabilirim?

Y:  Alanı, X veya Y ekseni demetlerine değil, **Ayrıntılar** demetine ekleyin.

S:  Bir görselleştirmeye sayısal alan eklediğimde, alanların çoğu için varsayılan işlem toplam işlemi olarak ayarlanırken bazıları için de sayı veya başka bir toplama işlemi olarak belirleniyor.  Varsayılan toplama işlemi neden aynı kalmıyor?

Y:  Veri kümesi sahipleri, her bir alan için varsayılan özetleme ayarlayabilirsiniz. Bir veri kümesinin sahibi sizseniz, varsayılan özetlemeyi değiştirin **modelleme** Power BI Desktop'ın sekmesi.

S:  Ben bir veri kümesi sahibiyim ve bir alanın hiçbir zaman toplanmamasını sağlamak istiyorum.

C:  Power BI Desktop'taki **Modelleme** sekmesinde, **Veri türü**'nü **Metin** olarak ayarlayın.

S:  Göremiyorum **özetleme** my açılan listesindeki bir seçeneği olarak.

Y:  Alanı kaldırıp tekrar eklemeyi deneyin.

Başka bir sorunuz mu var? [Power BI Topluluğu'na başvurun](http://community.powerbi.com/)