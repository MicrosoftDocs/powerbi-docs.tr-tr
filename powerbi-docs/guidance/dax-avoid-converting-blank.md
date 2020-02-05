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
ms.openlocfilehash: 2f70b98ed540a2e5b87e5a949e30b0c1c02069d1
ms.sourcegitcommit: 8e3d53cf971853c32eff4531d2d3cdb725a199af
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/04/2020
ms.locfileid: "74700398"
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

![Tablo görselinin üç sütunu vardır: Customer, Sales ve Profit Margin. Tabloda yaklaşık 10 veri satırı görüntülenir, ama dikey kaydırma çubuğu görüntülenebilecek çok daha fazla satır olduğuna işaret eder. Sales sütununda hiçbir değer görüntülenmez. Profit Margin sütununda yalnızca sıfır görüntülenir.](media/dax-avoid-converting-blank/table-visual-poor.png)

Tablo görseli kullanıcıyı bunaltacak kadar çok satır görüntüler. (Modelde aslında 18.484 müşteri vardır ve tablo da hepsini görüntülemeye çalışır.) Görünümdeki müşterilerin hiçbir satış yapamadığına dikkat edin. Yine de, **Profit Margin** ölçüsü her zaman bir değer döndürdüğünden bunlar görüntülenmektedir.

> [!NOTE]
> Görselde görüntülenecek çok fazla veri noktası olduğunda, Power BI büyük sorgu sonuçlarını kaldırmak veya özetlemek için veri azaltma stratejileri kullanabilir. Daha fazla bilgi için bkz. [Görsel türüne göre stratejiler ve veri noktası sınırları](../visuals/power-bi-data-points.md).

**Profit Margin** ölçü tanımı geliştirildiğinde neler olduğuna bakalım. Artık yalnızca **Sales** ölçüsü BOŞLUK (veya sıfır) olmadığında değer döndürür.

```dax
Profit Margin =
DIVIDE([Profit], [Sales])
```

Tablo görselinde şimdi yalnızca geçerli filtre bağlamında satış yapmış olan müşteriler görüntülenir. Geliştirilmiş ölçü sonuçta rapor kullanıcılarınız için daha verimli ve pratik bir deneyim sağlar.

![Aynı tablo görseli artık dört veri satırı görüntüler. Her satır, bir satış değeri bulunan ve Profit Margin değeri sıfırdan farklı olan bir müşteri içindir.](media/dax-avoid-converting-blank/table-visual-good.png)

> [!TIP]
> Gerektiğinde [Veri İçermeyen Öğeleri Göster](../desktop-show-items-no-data.md) seçeneğini etkinleştirerek filtre bağlamındaki tüm gruplandırmaları (değer veya BOŞLUK döndürenler) görüntüleyecek şekilde görseli yapılandırabilirsiniz.

## <a name="recommendation"></a>Öneri

Anlamlı bir değer döndürülmediğinde ölçülerinizin BOŞLUK döndürmesini öneririz.

Bu tasarım yaklaşımı verimlidir ve Power BI'ın raporları daha hızlı işlemesine olanak tanır. Ayrıca özetlemeler BOŞLUK olduğunda rapor görselleri varsayılan olarak gruplandırmaları ortadan kaldırdığından, BOŞLUK döndürmesi daha iyidir.

## <a name="next-steps"></a>Sonraki adımlar

Bu makale hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

- [Veri Çözümleme İfadeleri (DAX) Başvurusu](/dax/)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
