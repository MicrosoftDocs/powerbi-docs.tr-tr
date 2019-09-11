---
title: Sayfalandırılmış raporlardaki URL parametreleri - Power BI Rapor Oluşturucusu
description: Bu konu başlığında, Power BI Sayfalandırılmış Rapor Oluşturucusu’nun rapor parametrelerine, ayarlayabileceğiniz özelliklere ve çok daha fazlasına yönelik yaygın kullanımlar açıklanmaktadır.
ms.service: powerbi
ms.subservice: report-builder
ms.custom: ''
ms.topic: conceptual
author: maggiesMSFT
ms.author: maggies
ms.reviewer: cfinlan
ms.date: 08/29/2019
ms.openlocfilehash: bda35bfb4690d8109f7bd611e3d319278d235f33
ms.sourcegitcommit: 09ee1b4697aad84d8f4c9421015d7e4dbd3cf25f
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70302666"
---
# <a name="url-parameters-in-paginated-reports-in-power-bi"></a>Power BI’da bulunan sayfalandırılmış raporlardaki URL parametreleri

Bir URL’ye parametre ekleyerek, Power BI’daki sayfalandırılmış raporlara komut gönderebilirsiniz. Örneğin, belirli rapor parametresi değerlerini kullanarak raporu görüntülemiş olabilirsiniz. Önceden tanımlanmış URL erişimi parametrelerini kullanarak, URL’de bulunan bu bilgileri kapsülleyebilirsiniz. Power BI’ın raporu işleyiş biçimini daha da özelleştirerek işleme biçimlerine yönelik parametreler ekleyebilir veya rapor araç çubuğunun görünümünü ve kullanımını değiştirebilirsiniz. Ardından, diğer kişilerin rapor deneyiminin tarayıcıdaki gibi olması için bu URL’yi bir e-posta iletisine veya web sayfasına doğrudan yapıştırabilirsiniz. 

URL erişimi parametreleri aracılığıyla gerçekleştirebileceğiniz eylemler şunlardır: 

- Bir rapora rapor parametresi gönderme. 
- Rapor içeriğinin desteklenen bir dosya formatında dışarı aktarılmasını başlatma. 
- Parametreler bölmesini gizleme veya gösterme. 
- DeviceInfo ayarını belirtme. 

URL erişimi aracılığıyla kullanılabilen komut ve ayarların tam listesi için, bu makalenin sonraki kısımlarında bulabileceğiniz  [URL erişimi parametresi başvurusu](#url-access-parameter-reference) bölümüne bakın. 

## <a name="url-access-concepts"></a>URL erişimi kavramları 

Power BI’a gönderilen URL istekleri, hizmet tarafından işlenen parametreleri içerir. Hizmetin URL isteklerini işleme yöntemi, parametrelere, parametrelerin ön eklerine ve URL’nin içerdiği öğelerin türlerine bağlıdır. Sayfalandırılmış rapor URL’si işlevi, standart URL işlemeyi destekleyen çoğu tarayıcı ve uygulamayla uyumludur. 

## <a name="url-access-syntax"></a>URL erişimi söz dizimi 

URL istekleri, herhangi bir sırayla listelenen birden fazla parametreyi içerebilir. Parametreler & işaretiyle ayrılır. Ad ve değer çiftleri eşittir işareti (=) ile ayrılır. Örnek:

```
powerbiserviceurl?rp:parametervalueh&rdl:parameter=value  
```

## <a name="syntax-description"></a>söz dizimi açıklaması 

### <a name="powerbiserviceurl"></a>powerbiserviceurl 

Power BI kiracınızın Web hizmeti URL’si. Örnek: 

URL erişimi parametrelerinin ad ve değer çiftlerini ayırmak için **&** kullanılır.

**ön ek** Power BI hizmetindeki bir eylemi belirten, URL parametresine yönelik ön ek (örneğin, rp: veya rdl:). 

> [!NOTE]
> Büyük/küçük harfe duyarlı olan rapor parametreleri için bir parametre ön eki gerekir. 

**parameter** Parametrenin adı. 

### <a name="value"></a>değer 

Kullanılan parametrenin değerine karşılık gelen URL Metni. 

Rapor parametrelerini URL’ye geçirme örnekleri için bkz.  [Bir rapor parametresini URL’ye geçirme](report-builder-url-pass-parameters.md).

## <a name="url-access-parameter-reference"></a>URL erişimi parametresi başvurusu

Power BI’daki sayfalandırılmış raporlarınızın görünümünü ve kullanımını yapılandırmak için, aşağıdaki parametreleri URL’nin bir parçası olarak kullanabilirsiniz. En sık kullanılan parametreler bu bölümde listelenir. Parametreler büyük/küçük harfe duyarlı değildir ve çıkış biçimiyle ilişkili olanlar, parametre ön ekiyle `rdl:` başlar.  

### <a name="report-commands-rdl"></a>Rapor komutları (`rdl:`) 

**Dışarı aktarma biçimi** Bir raporun işleneceği ve dışarı aktarılacağı biçimi belirtir. Kullanılabilir değerler şunlardır: 
- PPTX (PowerPoint)
- MHTML 
- GÖRÜNTÜ 
- EXCELOPENXML (EXCEL) 
- WORDOPENXML (WORD) 
- CSV 
- PDF 
- XML 

## <a name="next-steps"></a>Sonraki adımlar

- [Power BI’da, bir sayfalandırılmış rapor için URL’de rapor parametresi geçirme](report-builder-url-pass-parameters.md)
- [Power BI Premium’da sayfalandırılmış raporlar nelerdir?](paginated-reports-report-builder-power-bi.md)
