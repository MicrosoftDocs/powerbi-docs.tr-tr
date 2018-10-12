---
title: URL'yi kullanarak Power BI rapor parametreleri ekleme
description: URL sorgu dizesi parametrelerini kullanarak bir raporu ve hatta birden fazla alanı filtreleyebilirsiniz.
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 10/01/2018
LocalizationGroup: Reports
ms.openlocfilehash: 562af0b21c4ecd4617de0e524cca20ec6935ca7a
ms.sourcegitcommit: 31f9da5f562cd02a729b6f012b4b3326416adb0e
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/03/2018
ms.locfileid: "48232938"
---
# <a name="filter-a-report-using-query-string-parameters-in-the-url"></a>URL'de sorgu dizesi parametreleri kullanarak bir raporu filtreleme

Power BI hizmetinde bir raporu açtığınızda, rapordaki her sayfanın kendine ait bir URL'si bulunur. Bu rapor sayfasının filtrelemek için rapor tuvalindeki Filtreler bölmesini kullanabilirsiniz.  Alternatif olarak URL'ye sorgu dizesi parametreleri ekleyerek rapora ön filtreleme uygulayabilirsiniz. İş arkadaşlarınıza göstermek istediğiniz bir raporunuz olabilir ve bu raporu onlar için önceden filtrelemek isteyebilirsiniz. Bunu yapmanın bir yolu raporun varsayılan URL'si ile başlamak, filtre parametrelerini URL'ye eklemek ve ardından iş arkadaşlarınıza yeni URL'nin tamamını e-posta ile göndermektir.

![Hizmette Power BI raporu](media/service-url-filters/power-bi-report2.png)

## <a name="uses-for-query-string-parameters"></a>Sorgu dizisi parametrelerinin kullanımları

Power BI Desktop'ta çalıştığınızı ve diğer Power BI raporlarına bağlantılı bir rapor oluşturmak istediğinizi ancak diğer raporlardaki bilgilerin yalnızca bir bölümünü göstermek istediğinizi düşünelim. İlk olarak sorgu dizesi parametrelerini kullanarak raporları filtrelemeniz ve URL'leri kaydetmeniz gerekir. Ardından bu rapor URL'leriyle Desktop uygulamasında yeni bir tablo oluşturabilirsiniz.  Son adımda da bu raporu yayımlayıp paylaşabilirsiniz.

Sorgu dizesi parametrelerinin başka bir kullanımı da gelişmiş Power BI çözümü oluşturmaktır.  DAX kullanarak dinamik olarak müşterisinin geçerli raporda yaptığı seçimleri temel alan filtrelenmiş rapor URL'si üreten bir rapor oluşturur. Müşteriler URL'yi seçtiğinde yalnızca istenen bilgileri görür. 

## <a name="query-string-parameter-syntax-for-filtering"></a>Filtreleme için sorgu dizesi parametresi söz dizimi

Parametreleri kullanarak boşluk veya özel karakter içerenler dahil olmak üzere raporu bir veya daha fazla değer için filtreleyebilirsiniz. Temel söz dizimi oldukça basittir; rapor URL'si ile başlayın, bir soru işareti ekleyin ve ardından filtre söz diziminizi ekleyin.

URL?filter=***Tablo***/***Alan*** eq '***değer***'

![Filtre ile URL](media/service-url-filters/power-bi-filter-urls7b.png)

* **Tablo** ve **Alan** adları büyük/küçük harfe duyarlıdır, **değer** ise değildir.
* Rapor görünümünden gizlenen alanlar yine de filtrelenebilir.

### <a name="field-types"></a>Alan türleri

Alan türü sayı, tarih saat veya dize olabilir ve kullanılan türün veri kümesindeki tür kümesiyle eşleşmesi gerekir.  Örneğin tarih olarak belirlenmiş bir veri kümesi sütununda (örneğin, Table/StringColumn eq 1) bir tarih saat veya sayısal değer arıyorsanız tablo sütununun "dize" türünde belirtilmesi uygun olmayacaktır.

* **Dizelerin** tek tırnak içine alınması gerekir: 'yönetici adı'.
* **Sayılar** için özel biçimlendirmeye gerek yoktur
* **Tarih ve saatlerin** tek tırnak içine alınması ve önüne **DateTime** sözcüğünün yazılması gerekir.

Yine de karmaşık geliyorsa ayrıntıları görmek için okumaya devam edin.  

## <a name="filter-on-a-field"></a>Bir alanı filtreleme

Aşağıdakinin raporumuzun URL'si olduğunu kabul edelim.

![URL’yi başlatma](media/service-url-filters/power-bi-filter-urls6.png)

Harita görselleştirmemizde (yukarıda) Kuzey Carolina'da mağazalarımız olduğunu görüyoruz.

>[!NOTE]
>Bu örnekte [Perakende Analiz Örneği](sample-datasets.md) temel alınmıştır.
> 

Raporu yalnızca "NC"de (Kuzey Carolina) bulunan mağazaları göstermek üzere filtrelemek için URL'ye aşağıdakileri ekleyin;

?filter=Store/Territory eq 'NC'

![Filtre ile URL](media/service-url-filters/power-bi-filter-urls7.png)

>[!NOTE]
>*NC*, **Store** tablosunun **Territory** alanında depolanan bir değerdir.
> 

Raporumuz Kuzey Carolina için filtrelendi, rapor sayfasında bulunan tüm görselleştirmeler yalnızca Kuzey Carolina'ya ait verileri gösterir.

![](media/service-url-filters/power-bi-report4.png)

## <a name="filter-on-multiple-fields"></a>Birden çok alanda filtreleme

Ayrıca URL'nize ek parametreler ekleyerek birden çok alanda filtreleme yapabilirsiniz. Özgün filtre parametremize geri dönelim.

```
?filter=Store/Territory eq 'NC'
```

Ek alanlarda filtreleme yapmak için bir **and** ve yukarıdaki biçimde başka bir alan ekleyin. Bu işlemin bir örneği aşağıdadır.

```
?filter=Store/Territory eq 'NC' and Store/Chain eq 'Fashions Direct'
```

<iframe width="640" height="360" src="https://www.youtube.com/embed/0sDGKxOaC8w?showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="operators"></a>İşleçler

Power BI, **and** haricinde birçok işleci de destekler. Aşağıdaki tabloda bu işleçler ve destekledikleri içerik türleri listelenmiştir.

|işleç  | tanım | dize  | sayı | Tarih |  Örnek|
|---------|---------|---------|---------|---------|---------|
|**and**     | ve |  evet      | evet |  evet|  product/price le 200 and price gt 3.5 |
|**eq**     | eşittir |  evet      | evet   |  evet       | Address/City eq 'Redmond' |
|**ne**     | eşit değildir |   evet      | evet  | evet        |  Address/City ne 'London' |
|**ge**     |  büyüktür veya eşittir       | hayır | evet |evet |  product/price ge 10
|**gt**     | büyüktür        |hayır | evet | evet  | product/price gt 20
|**le**     |   küçüktür veya eşittir      | hayır | evet | evet  | product/price le 100
|**lt**     |  küçüktür       | hayır | evet | evet |  product/price lt 20
|**in****     |  dahil       | evet | evet |  evet | Student/Age in (27, 29)


\** **in** işlecini kullanırken **in** ifadesinin sağ tarafındaki değerler parantez içinde virgülle ayrılmış liste veya koleksiyon döndüren tek bir ifade olabilir.

### <a name="numeric-data-types"></a>Sayısal veri türleri

Power BI URL filtresi aşağıdaki biçimlerde sayı içerebilir.

|Sayı türü  |Örnek  |
|---------|---------|
|**integer**     |   5      |
|**long**     |   5L veya 5l      |
|**double**     |   5,5 veya 55e-1 veya 0,55e+1 veya 5D veya 5d veya 0,5e1D veya 0,5e1d veya 5,5D veya 5,5d veya 55e-1D veya 55e-1d     |
|**decimal**     |   5M veya 5m veya 5,5M veya 5,5m      |
|**float**     | 5F veya 5f veya 0,5e1F veya 0,5e-1d        |

### <a name="date-data-types"></a>Tarih veri türleri

Power BI, **Date** ve **DateTimeOffset** veri türleri için OData V3 ve V4 desteği sunar.  Tarihler EDM biçiminde (2019-02-12T00:00:00) gösterilir. Bu da YYYY-AA-GG biçiminde bir tarih belirttiğinizde Power BI'ın bunu YYYY-AA-GGT00:00:00 şeklinde yorumlayacağı anlamına gelir.

Bu ayrım neden önemlidir? **Table/Date gt 2018-08-03** şeklinde bir sorgu dizesi parametresi oluşturduğunuzu düşünelim.  Sonuçlar 3 Ağustos 2018'i kapsayacak mı yoksa 4 Ağustos 2018'den mi başlayacak? Power BI sorgunuzu**Table/Date gt 2018-08-03T00:00:00** şekline dönüştürdüğünden sonuçlarınız saat bölümü sıfır olmayan tarihleri **2018-08-03T00:00:00** tarihinden büyük olacağından kapsayacaktır.

## <a name="special-characters-in-url-filters"></a>URL filtrelerindeki özel karakterler

Özel karakter ve boşluk kullanımı için gerçekleştirilmesi gereken ek biçimlendirme adımları vardır. Sorgunuz; boşluklar, tireler veya ASCII olmayan başka karakterler içerdiğinde, o özel karakterlere önek olarak bir alt çizgi ve bir X (**_x**) ile başlayan, ardından 4 haneli **Unicode** ve başka bir alt çizgi ile devam eden bir *kaçış kodu* verin. Unicode 4 karakterden kısaysa sıfırlarla ile tamamlamanız gerekir. Aşağıda bazı örnekler verilmiştir.

|Tanımlayıcı  |Unicode  | Power BI için kodlama  |
|---------|---------|---------|
|**Tablo Adı**     | Boşluk 0x20        |  Tablo_x0020_Adı       |
|**Sütun**@**Numarası**     |   @ 0x40     |  Sütun_x0040_Numarası       |
|**[Sütun]**     |  [ is 0x0058 ] 0x0050       |  _x0058_Sütun_x0050       |
|**Sütun+Artı**     | + 0x2B        |  Sütun_x002B_Artı       |

Table_x0020_Name/Column_x002B_Plus eq 3 ![özel karakterler içeren tablo görseli](media/service-url-filters/power-bi-special-characters1.png)


Table_x0020_Special/_x005B_Column_x0020_Brackets_x005D_ eq '[C]' ![özel karakterler içeren tablo görseli](media/service-url-filters/power-bi-special-characters2.png)

### <a name="use-dax-to-filter-on-multiple-values"></a>DAX kullanarak birden fazla değerde filtreleme

Birden fazla alanda filtrelemenin başka bir yolu da iki alanı tek bir alanda birleştiren bir hesaplanmış sütun oluşturmaktır. Ardından elde ettiğiniz bu değeri filtreleyebilirsiniz.

Örneğin iki alanımız bulunuyor: Territory ve Chain. Power BI Desktop'ta, TerritoryChain adlı [yeni bir Hesaplanmış sütun oluşturun](desktop-tutorial-create-calculated-columns.md) (Alan). **Alan** adında boşluk olamayacağını unutmayın. Bu sütun için DAX formülü aşağıdadır.

TerritoryChain = [Territory] & " - " & [Chain]

Raporu Power BI hizmetinde yayımlayın ve ardından yalnızca NC'deki Lindseys mağazalarına ait verileri görüntülemek üzere filtrelemek için URL sorgu dizesini kullanın.

    https://app.powerbi.com/groups/me/reports/8d6e300b-696f-498e-b611-41ae03366851/ReportSection3?filter=Store/TerritoryChain eq 'NC–Lindseys'

## <a name="pin-a-tile-from-a-filtered-report"></a>Filtrelenen bir rapordan kutucuk sabitleme

Sorgu dizesi parametrelerini kullanarak raporu filtreledikten sonra bu rapordaki görselleştirmeleri panonuza sabitleyebilirsiniz.  Pano üzerindeki kutucuk filtrelenmiş verileri görüntüler ve bu pano kutucuğunu seçtiğinizde, kutucuğu oluşturmak için kullanılan rapor açılır.  Ancak, URL'yi kullanarak yaptığınız filtreleme raporla kaydedilmez ve pano kutucuğu seçildiği zaman, rapor filtrelenmemiş durumda açılır.  Bu, pano kutucuğunda görüntülenen verilerin, rapor görselleştirmesinde görüntülenen verilerle eşleşmeyeceği anlamına gelir.

Bu durum panoda filtrelenmiş ve raporda filtrelenmemiş olarak değişik sonuçlar görmek istediğinizde yararlıdır.

## <a name="considerations-and-troubleshooting"></a>Önemli noktalar ve sorun giderme

Sorgu dizesi parametrelerini kullanırken dikkat edilmesi gereken bazı noktalar vardır.

* *in* işlecini kullanırken *in* ifadesinin sağındaki değerlerin parantez içinde virgülle ayrılmış değerler listesi olması gerekir.    
* Power BI Rapor Sunucusu’nda, rapor URL’sine eklediğiniz [rapor parametrelerini geçirebilirsiniz](https://docs.microsoft.com/sql/reporting-services/pass-a-report-parameter-within-a-url?view=sql-server-2017.md). Bu URL parametreleri doğrudan rapor işleme altyapısına geçirildiğinden ön ek almaz.
* Sorgu dizesi filtreleme özelliği [Web'de yayımla](service-publish-to-web.md) seçeneği veya Power BI Embedded ile kullanılamaz.   
* Javascript sınırlamaları nedeniyle uzun veri türü (2^53-1) olarak belirlenmiştir.
* Rapor URL filtrelerinin 10 ifade sınırı vardır (AND ile bağlanan 10 filtre).

## <a name="next-steps"></a>Sonraki adımlar

[Panoya görselleştirme sabitleme](service-dashboard-pin-tile-from-report.md)  
[Ücretsiz deneme için kaydolun](https://powerbi.microsoft.com/get-started/)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)
