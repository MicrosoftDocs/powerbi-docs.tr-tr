---
title: 'DAX: BOŞLUKLARI değerlere dönüştürmekten kaçınma'
description: BOŞLUKLARI değerlere dönüştürme yönergeleri.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 11/24/2019
ms.author: v-pemyer
ms.openlocfilehash: 6b130016bf4514b817edbf8c91cfb24d2063e6f1
ms.sourcegitcommit: c83146ad008ce13bf3289de9b76c507be2c330aa
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2020
ms.locfileid: "86215453"
---
# <a name="dax-avoid-converting-blanks-to-values"></a>DAX: BOŞLUKLARI değerlere dönüştürmekten kaçınma

Veri modelleyicisi olarak ölçü ifadeleri yazarken anlamlı bir değerin döndürülemediği örneklerle karşılaşabilirsiniz. Bu örneklerde size sıfır gibi bir değer döndürmek cazip gelebilir. Bu tasarımın verimli ve pratik olup olmadığını dikkatle belirlemenizi öneririz.

BLANK sonuçlarını açıkça sıfıra dönüştüren aşağıdaki ölçü tanımını düşünün.

```dax
Sales (No Blank) =
IF(
    ISBLANK([Sales]),
    0,
    [Sales]
)
```

BLANK sonuçlarını yine sıfıra dönüştüren başka bir ölçü tanımı düşünün.

```dax
Profit Margin =
DIVIDE([Profit], [Sales], 0)
```

[DIVIDE](/dax/divide-function-dax) işlevi **Profit** ölçüsünü **Sales** ölçüsüne böler. Sonucun sıfır veya BOŞLUK olması durumunda üçüncü bağımsız değişken, yani alternatif sonuç (isteğe bağlıdır) döndürülür. Bu örnekte alternatif sonuç olarak sıfır geçirildiğinden, ölçünün her zaman bir değer döndürmesi garanti edilmiş olur.

Bu ölçü tasarımları verimsizdir ve başarısız rapor tasarımlarına yol açabilir.

Bunlar rapor görseline eklendiğinde Power BI filtre bağlamı içindeki tüm gruplandırmaları almaya çalışır. Büyük sorgu sonuçlarının hesaplanması ve alınması genellikle raporun yavaş işlenmesine yol açar. Her örnek ölçü seyrek bir hesaplamayı etkili bir şekilde yoğun bir hesaplamaya dönüştürür ve Power BI'ı gerekenden daha fazla bellek kullanmaya zorlar.

Ayrıca çok fazla gruplandırma genellikle rapor kullanıcılarınızı bunaltır.

Müşteriye göre gruplandırılmış bir tablo görseline **Profit Margin** ölçüsü eklendiğinde neler olduğuna bakalım.

![Müşteri başına bir satır içeren, verilerin tablo görselini gösteren Power BI Desktop’ın ekran görüntüsü. Satış değerleri BLANK, Kar Marjı değerleri ise sent başına sıfırdır. ](media/dax-avoid-converting-blank/table-visual-poor.png)

Tablo görseli kullanıcıyı bunaltacak kadar çok satır görüntüler. (Modelde aslında 18.484 müşteri vardır ve tablo da hepsini görüntülemeye çalışır.) Görünümdeki müşterilerin hiçbir satış yapamadığına dikkat edin. Yine de, **Profit Margin** ölçüsü her zaman bir değer döndürdüğünden bunlar görüntülenmektedir.

> [!NOTE]
> Görselde görüntülenecek çok fazla veri noktası olduğunda, Power BI büyük sorgu sonuçlarını kaldırmak veya özetlemek için veri azaltma stratejileri kullanabilir. Daha fazla bilgi için bkz. [Görsel türüne göre stratejiler ve veri noktası sınırları](../visuals/power-bi-data-points.md).

**Profit Margin** ölçü tanımı geliştirildiğinde neler olduğuna bakalım. Artık yalnızca **Sales** ölçüsü BOŞLUK (veya sıfır) olmadığında değer döndürür.

```dax
Profit Margin =
DIVIDE([Profit], [Sales])
```

Tablo görselinde şimdi yalnızca geçerli filtre bağlamında satış yapmış olan müşteriler görüntülenir. Geliştirilmiş ölçü sonuçta rapor kullanıcılarınız için daha verimli ve pratik bir deneyim sağlar.

![İçeriği filtrelemiş, verilerin tablo görselini gösteren Power BI Desktop’ın ekran görüntüsü.](media/dax-avoid-converting-blank/table-visual-good.png)

> [!TIP]
> Gerektiğinde [Veri İçermeyen Öğeleri Göster](../create-reports/desktop-show-items-no-data.md) seçeneğini etkinleştirerek filtre bağlamındaki tüm gruplandırmaları (değer veya BOŞLUK döndürenler) görüntüleyecek şekilde görseli yapılandırabilirsiniz.

## <a name="recommendation"></a>Öneri

Anlamlı bir değer döndürülmediğinde ölçülerinizin BOŞLUK döndürmesini öneririz.

Bu tasarım yaklaşımı verimlidir ve Power BI'ın raporları daha hızlı işlemesine olanak tanır. Ayrıca özetlemeler BOŞLUK olduğunda rapor görselleri varsayılan olarak gruplandırmaları ortadan kaldırdığından, BOŞLUK döndürmesi daha iyidir.

## <a name="next-steps"></a>Sonraki adımlar

Bu makale hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

- [Veri Çözümleme İfadeleri (DAX) Başvurusu](/dax/)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
