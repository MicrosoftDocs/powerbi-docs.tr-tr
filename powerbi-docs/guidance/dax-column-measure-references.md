---
title: 'DAX: Sütun ve ölçü başvuruları'
description: DAX ifadelerinizdeki ölçülerde yer alan sütunlara başvurma yönergeleri.
author: peter-myers
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 12/18/2019
ms.author: v-pemyer
ms.openlocfilehash: a98ee3ff33d21dd599ddfb11166a6870ad30e6e5
ms.sourcegitcommit: 2131f7b075390c12659c76df94a8108226db084c
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/03/2020
ms.locfileid: "87537585"
---
# <a name="dax-column-and-measure-references"></a>DAX: Sütun ve ölçü başvuruları

Veri modelleyici olarak, DAX ifadeleriniz model sütunlarına ve ölçülerine başvurur. Sütunlar ve ölçüler her zaman model tablolarıyla ilişkilendirilir ama bu ilişkiler farklıdır. Dolayısıyla ifadelerinizde bunlara nasıl başvuracağınız konusunda farklı önerilerimiz vardır.

## <a name="columns"></a>Sütunlar

Sütunlar tablo düzeyi nesnelerdir ve sütun adları tablo içinde benzersiz olmalıdır. Bu nedenle, farklı tablolara ait olması koşuluyla aynı sütun adının modelinizde birden çok kez kullanılması mümkündür. Bir kural daha vardır: Sütun adı, aynı tabloda bulunan bir ölçü adıyla veya hiyerarşi adıyla aynı olamaz.

Genel olarak DAX sütuna _tam_ başvuru kullanılmasını zorunlu tutmaz. Tam başvuru, sütun adından önce tablo adının bulunacağı anlamına gelir.

Burada yalnızca sütun adı başvurularının kullanıldığı bir hesaplanmış sütun örneği verilmiştir. **Sales** ve **Cost** sütunlarının ikisi de **Orders** adlı tabloya aittir.

```dax
Profit = [Sales] - [Cost]
```

Aynı tanım tam sütun başvurularıyla yeniden yazılabilir.

```dax
Profit = Orders[Sales] - Orders[Cost]
```

Öte yandan bazen, Power BI belirsizlik algıladığında tam sütun başvurularını kullanmanız gerekir. Formül girerken sarı dalgalı çizgi ve hata iletisi sizi uyarır. Ayrıca [LOOKUPVALUE](/dax/lookupvalue-function-dax) DAX işlevi gibi bazı DAX işlevleri tam sütunların kullanılmasını gerektirir.

Her zaman tüm sütun başvurularını kullanmanızı öneririz. Bunun nedenleri [Öneriler](#recommendations) bölümünde sağlanmıştır.

## <a name="measures"></a>Ölçüler

Ölçü, model düzeyinde bir nesnedir. Bu nedenle ölçü adları model içinde benzersiz olmalıdır. Öte yandan rapor yazarları **Alanlar** bölmesinde tek bir model tablosuyla ilişkilendirilmiş her ölçüyü görebilir. Bu ilişki biçimsel nedenlerle ayarlanır ve ölçü için **Ana Tablo** özelliğini ayarlayarak ilişkiyi yapılandırabilirsiniz. Daha fazla bilgi için bkz. [Power BI Desktop'ta ölçüler (Ölçülerinizi düzenleme)](../transform-model/desktop-measures.md#organizing-your-measures).

İfadelerinizde tam ölçüleri kullanmanız mümkündür. DAX IntelliSense öneride bile bulunur. Öte yandan bu gerekli değildir ve önerilen bir uygulama da değildir. Ölçünün ana tablosunu değiştirirseniz, buna yönelik tam ölçü başvurusunu kullanan tüm ifadeler bozulur. Bundan sonra bozulan her formülü düzenleyip ölçü başvurusunu kaldırmanız (veya güncelleştirmeniz) gerekir.

Hiçbir zaman tam ölçü başvuruları kullanmamanızı öneririz. Bunun nedenleri [Öneriler](#recommendations) bölümünde sağlanmıştır.

## <a name="recommendations"></a>Öneriler

Önerilerimiz basittir ve kolayca anımsanabilir:

- Her zaman tam sütun başvuruları kullanın
- Hiçbir zaman tam ölçü başvuruları kullanmayın

Nedeni:

- **Formül girdisi**: İfadeler kabul edilir çünkü çözülmesi gereken hiçbir belirsiz başvuru olmaz. Aynı zamanda tam sütun başvuruları gerektiren DAX işlevlerinin bu gereksinimini karşılamış olursunuz.
- **Sağlamlık**: Ölçünün ana tablo özelliğini değiştirseniz bile ifadeler yine de çalışır.
- **Okunabilirlik**: İfadeler hızla ve kolayca anlaşılır; tam başvurunun kullanılıp kullanılmadığına dayanarak bunun bir sütun mu yoksa ölçü mü olduğunu hemen belirleyebilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

Bu makale hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

- [Veri Çözümleme İfadeleri (DAX) Başvurusu](/dax/)
- Öğrenme yolu: [Power BI Desktop’ta DAX kullanma](https://docs.microsoft.com/learn/paths/dax-power-bi/)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
- Önerileriniz mi var? [Power BI'ı geliştirmek için fikirlerinizi paylaşın](https://ideas.powerbi.com)
