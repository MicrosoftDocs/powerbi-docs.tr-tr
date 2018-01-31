---
title: "iFrame kullanarak rapor gömme"
description: "Power BI Rapor Sunucusunu yüklemek oldukça hızlı bir işlemdir. İndirmede işleminden yükleme ve yapılandırma aşamasına kadar geçen birkaç dakika içinde çalışmaya başlayabilirsiniz."
services: powerbi
documentationcenter: 
author: markingmyname
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
ms.date: 11/09/2017
ms.author: maghan
ms.openlocfilehash: 56835bfb25c8c930099fadf710137f69fa89fc2e
ms.sourcegitcommit: 6e693f9caf98385a2c45890cd0fbf2403f0dbb8a
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2018
---
# <a name="quickstart-embed-a-power-bi-report-using-an-iframe-and-url-parameters"></a>Hızlı Başlangıç: iFrame ve URL parametrelerini kullanarak Power BI raporu ekleme

Uygulamanızda iFrame kullanarak herhangi bir raporu ekleyebilirsiniz. 

## <a name="url-parameter"></a>URL parametresi

Bir rapora ilişkin herhangi bir URL için `?rs:Embed=true` sorgu dizesi parametresini ekleyebilirsiniz.

Örneğin:

```
http://myserver/reports/powerbi/Sales?rs:embed=true
```

Bu, Power BI Rapor Sunucusu'ndaki tüm rapor türlerinde çalışır.

## <a name="iframe"></a>iFrame

URL'nizi edindikten sonra, raporun barındırılması için bir web sayfasında iFrame oluşturabilirsiniz.

Örneğin:

```
<iframe width="800" height="600" src="http://myserver/reports/powerbi/Sales?rs:embed=true" frameborder="0" allowFullScreen="true"></iframe>
```

## <a name="url-filter"></a>URL filtresi

Power BI raporunda döndürülen verileri filtrelemek için URL'ye sorgu dizesi parametresi ekleyebilirsiniz.

Söz dizimi basittir; rapor URL'si ile başlayın, bir soru işareti ekleyin, ardından bu filtre söz dizimini ekleyin.

URL?filter=***Tablo***/***Alan*** eq '***değer***'

Şu noktaları göz önünde bulundurun:

- **Tablo** ve **Alan** adları büyük/küçük harfe duyarlıdır, **değer** ise değildir.
- Bir raporu, rapor görünümünde alanlar gizlenmiş olacak şekilde filtreleyebilirsiniz.
- **Değer** tek tırnak içine alınmalıdır.
- Alan türünün dize olması gerekir.
- Tablo ve alan adlarında boşluk olamaz.

###  <a name="example-filter-on-a-field"></a>Örnek: Bir alanı filtreleme

Örnek olarak [Perakende Analizi Örneği](../sample-datasets.md)'ni alalım. Bunun, rapor sunucusundaki "power-bi" adlı bir klasörde bulunan raporun URL'si olduğunu varsayalım:

```
https://report-server/reports/power-bi/Retail-Analysis-Sample
```

Perakende Analizi Örneği'ndeki harita görselleştirmesinde, Kuzey Carolina ve diğer eyaletlerdeki mağazaların gösterildiğine dikkat edin.

![Perakende Analizi Örneği harita görselleştirmesi](media/quickstart-embed/report-server-retail-analysis-sample-map.png)

*NC*, **Store** tablosunun **Territory** alanında depolanan Kuzey Carolina değeridir. Raporu yalnızca Kuzey Carolina'da bulunan mağazaları göstermek üzere filtrelemek için URL'ye aşağıdakileri ekleyin:

?filter=Store/Territory eq 'NC'

Rapor Kuzey Carolina için filtrelendiğinden rapor sayfasında bulunan tüm görselleştirmeler yalnızca Kuzey Carolina'ya ait verileri gösterir.

![Perakende Analizi Örneği'nde filtrelenmiş görselleştirmeler](media/quickstart-embed/report-server-retail-analysis-sample-filtered-map.png)

### <a name="create-a-dax-formula-to-filter-on-multiple-values"></a>Birden çok değeri filtrelemek için DAX formülü oluşturma

Birden çok alanı filtrelemenin başka bir yolu da, Power BI Desktop'ta iki alanı tek bir değerde birleştiren hesaplanmış bir sütun oluşturmaktır. Ardından, elde ettiğiniz bu değeri filtreleyebilirsiniz.

Örneğin, Perakende Analizi Örneği'nde iki alan vardır: Territory ve Chain. Power BI Desktop'ta, TerritoryChain (Alan) adlı [hesaplanmış bir sütun oluşturabilirsiniz](../desktop-tutorial-create-calculated-columns.md). **Alan** adında boşluk olamayacağını unutmayın. Bu sütun için DAX formülü aşağıdadır.

TerritoryChain = [Territory] & "-" & [Chain]

Raporu Power BI Rapor Sunucusu'nda yayımlayın ve ardından yalnızca NC'deki Lindseys mağazalarına ait verileri görüntülemek üzere filtreleme yapmak için URL sorgu dizesini kullanın.

```
https://report-server/reports/power-bi/Retail-Analysis-Sample?filter=Store/TerritoryChain eq 'NC-Lindseys'

```

## <a name="next-steps"></a>Sonraki adımlar

[Hızlı Başlangıç: Power BI Rapor Sunucusu için Power BI raporu oluşturma](quickstart-create-powerbi-report.md)  
[Hızlı Başlangıç: Power BI Rapor Sunucusu için sayfalandırılmış rapor oluşturma](quickstart-create-paginated-report.md)  

Başka bir sorunuz mu var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)