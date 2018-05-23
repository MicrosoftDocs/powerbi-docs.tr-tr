---
title: URL'yi kullanarak Power BI rapor parametreleri ekleme
description: URL sorgu dizesi parametrelerini kullanarak bir raporu ve hatta birden fazla alanı filtreleyebilirsiniz.
author: mihart
manager: kfile
ms.reviewer: ''
featuredvideoid: ''
ms.service: powerbi
ms.component: powerbi-service
ms.topic: conceptual
ms.date: 04/11/2018
ms.author: mihart
LocalizationGroup: Reports
ms.openlocfilehash: 071f7ea0c324ec8fe0160766f65cf929f811362a
ms.sourcegitcommit: 638de55f996d177063561b36d95c8c71ea7af3ed
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="filter-a-report-using-query-string-parameters-in-the-url"></a>URL'de sorgu dizesi parametreleri kullanarak bir raporu filtreleme
Power BI hizmetinde bir raporu açtığınızda, rapordaki her sayfanın kendine ait bir URL'si bulunur. Bu rapor sayfasının filtrelemek için rapor tuvalindeki Filtreler bölmesini kullanabilirsiniz.  Alternatif olarak URL'ye sorgu dizesi parametreleri ekleyerek raporu filtreleyebilirsiniz. İş arkadaşlarınıza göstermek istediğiniz bir raporunuz olabilir ve bu raporu onlar için önceden filtrelemek isteyebilirsiniz. Bunu yapmanın bir yolu raporun varsayılan URL'si ile başlamak, filtre parametrelerini URL'ye eklemek ve ardından iş arkadaşlarınıza URL'nin tamamını e-posta ile göndermektir.

![Hizmette Power BI raporu](media/service-url-filters/power-bi-report2.png)

<iframe width="640" height="360" src="https://www.youtube.com/embed/WQFtN8nvM4A?list=PLv2BtOtLblH3YE_Ycas5B1GtcoFfJXavO&amp;showinfo=0" frameborder="0" allowfullscreen></iframe>

## <a name="query-string-parameter-syntax-for-filtering"></a>Filtreleme için sorgu dizesi parametresi söz dizimi
Söz dizimi oldukça basittir; rapor URL'si ile başlayın, bir soru işareti ekleyin ve ardından filtre söz diziminizi ekleyin.

URL?filter=***Tablo***/***Alan*** eq '***değer***'

![Filtre ile URL](media/service-url-filters/power-bi-filter-urls7b.png)

* **Tablo** ve **Alan** adları büyük/küçük harfe duyarlıdır, **değer** ise değildir.
* Rapor görünümünden gizlenen alanlar yine de filtrelenebilir.
* **Değer** tek tırnak içinde olmalıdır.
* Alan türünün bir sayı veya dize olması gerekir
* Tablo ve alan adlarında boşluk olamaz.

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
> 

Raporumuz Kuzey Carolina için filtrelendi, rapor sayfasında bulunan tüm görselleştirmeler yalnızca Kuzey Carolina'ya ait verileri gösterir.

![](media/service-url-filters/power-bi-report4.png)

## <a name="filter-on-multiple-fields"></a>Birden çok alanda filtreleme
Ayrıca URL'nize ek parametreler ekleyerek birden çok alanda filtreleme yapabilirsiniz. Özgün filtre parametremize geri dönelim.

```
?filter=Store/Territory eq 'NC'
```

Ek alanlarda filtreleme yapmak için bir `and` ve yukarıdaki biçimde başka bir alan ekleyin. Bu işlemin bir örneği aşağıdadır.

```
?filter=Store/Territory eq 'NC' and Store/Chain eq 'Fashions Direct'
```

<iframe width="640" height="360" src="https://www.youtube.com/embed/0sDGKxOaC8w?showinfo=0" frameborder="0" allowfullscreen></iframe>


### <a name="using-dax-to-filter-on-multiple-values"></a>DAX kullanarak birden fazla değerde filtreleme
Birden fazla alanda filtrelemenin başka bir yolu da iki alanı tek bir alanda birleştiren bir hesaplanmış sütun oluşturmaktır. Ardından elde ettiğiniz bu değeri filtreleyebilirsiniz.

Örneğin iki alanımız bulunuyor: Territory ve Chain. Power BI Desktop'ta, TerritoryChain adlı [yeni bir Hesaplanmış sütun oluşturun](desktop-tutorial-create-calculated-columns.md) (Alan). **Alan** adında boşluk olamayacağını unutmayın. Bu sütun için DAX formülü aşağıdadır.

TerritoryChain = [Territory] & " - " & [Chain]

Raporu Power BI hizmetinde yayımlayın ve ardından yalnızca NC'deki Lindseys mağazalarına ait verileri görüntülemek üzere filtrelemek için URL sorgu dizesini kullanın.

    https://app.powerbi.com/groups/me/reports/8d6e300b-696f-498e-b611-41ae03366851/ReportSection3?filter=Store/TerritoryChain eq 'NC–Lindseys'

## <a name="pin-a-tile-from-a-filtered-report"></a>Filtrelenen bir rapordan kutucuk sabitleme
Sorgu dizesi parametrelerini kullanarak raporu filtreledikten sonra bu rapordaki görselleştirmeleri panonuza sabitleyebilirsiniz. Pano üzerindeki kutucuk filtrelenmiş verileri gösterir ve bu pano kutucuğunu seçtiğinizde, kutucuğu oluşturmak için kullanılan rapor açılır.  Ancak, URL'yi kullanarak yaptığınız filtreleme raporla kaydedilmez ve pano kutucuğu seçildiği zaman, rapor filtrelenmemiş durumda açılır.  Bu, pano kutucuğunda görüntülenen verilerin, rapor görselleştirmesinde görüntülenen verilerle eşleşmeyeceği anlamına gelir.

Panoda filtrelenmiş ve raporda filtrelenmemiş olarak değişik sonuçlar görmek istediğiniz bazı durumlarda bu farklılık yararlı olabilir.

## <a name="limitations-and-troubleshooting"></a>Sınırlamalar ve sorun giderme
Sorgu dizesi parametrelerini kullanırken dikkat edilmesi gereken bazı noktalar vardır.

* Sorgu dizesi filtreleme özelliği [Web'de yayımla](service-publish-to-web.md) seçeneği veya Power BI Embedded ile kullanılamaz.   
* Alan türünün sayı veya dize olması gerekir.
* Tablo ve alan adlarında boşluk olamaz.

## <a name="next-steps"></a>Sonraki adımlar
[Panoya görselleştirme sabitleme](service-dashboard-pin-tile-from-report.md)  
[Ücretsiz deneyin!](https://powerbi.com/)

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](http://community.powerbi.com/)

