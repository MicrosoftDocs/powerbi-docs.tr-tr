---
title: 'DAX: COUNT yerine COUNTROWS kullanma'
description: COUNTROWS işlevlerinin ne zaman kullanılacağına yönelik rehber.
author: peter-myers
ms.author: kfollis
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi
ms.topic: conceptual
ms.date: 11/23/2019
ms.openlocfilehash: 8d3baba388900a9d57d6490db13c25cb363667ba
ms.sourcegitcommit: fb529c4532fbbdfde7ce28e2b4b35f990e8f21d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2021
ms.locfileid: "99088523"
---
# <a name="dax-use-countrows-instead-of-count"></a>DAX: COUNT yerine COUNTROWS kullanma

Veri modelleyicisi olarak bazen tablo satırlarını sayan bir DAX ifadesi yazmanız gerekebilir. Tablo, bir model tablosu veya tablo döndüren bir ifade olabilir.

İhtiyacınız olan sonucu iki yolla elde edebilirsiniz. [COUNT](/dax/count-function-dax) işlevini kullanarak sütun değerlerini sayabilir veya [COUNTROWS](/dax/countrows-function-dax) işlevini kullanarak tablo satırlarını sayabilirsiniz. Sayılan sütunun hiç BOŞLUK içermemesi koşuluyla, her iki işlev de aynı sonuca ulaşır.

Aşağıdaki ölçü tanımı bir örnek oluşturur. **OrderDate** sütun değerlerinin sayısını hesaplar.

```dax
Sales Orders =
COUNT(Sales[OrderDate])
```

**Sales** tablosunda ayrıntı düzeyinin satış siparişi başına bir satır olması ve **OrderDate** sütununun BOŞLUK içermemesi koşuluyla, ölçü doğru sonucu döndürecektir.

Öte yandan aşağıdaki ölçü tanımı daha iyi bir çözümdür.

```dax
Sales Orders =
COUNTROWS(Sales)
```

İkinci ölçü tanımının daha iyi olmasının üç nedeni vardır:

- Daha verimlidir ve dolayısıyla daha iyi performans gösterir.
- Tablonun herhangi bir sütununda yer alan BOŞLUKLARI dikkate almaz.
- Formülün amacı daha açıktır, hatta kendi kendini açıklayacak kadar nettir.

## <a name="recommendation"></a>Öneri

Tablo satırlarını saymayı amaçladığınız durumlarda her zaman COUNTROWS işlevini kullanmanızı öneririz.

## <a name="next-steps"></a>Sonraki adımlar

Bu makale hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

- [Veri Çözümleme İfadeleri (DAX) Başvurusu](/dax/)
- Öğrenme yolu: [Power BI Desktop’ta DAX kullanma](/learn/paths/dax-power-bi/)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
- Önerileriniz mi var? [Power BI'ı geliştirmek için fikirlerinizi paylaşın](https://ideas.powerbi.com)