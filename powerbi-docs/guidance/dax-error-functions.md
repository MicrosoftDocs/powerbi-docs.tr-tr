---
title: 'DAX: Hata işlevlerinin uygun kullanımı'
description: DAX hata işlevlerinin ne zaman kullanılacağına yönelik rehber.
author: peter-myers
ms.author: kfollis
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi
ms.topic: conceptual
ms.date: 09/26/2019
ms.openlocfilehash: c0766a989ea3dbfe42620fd53b4c49d6144b4c5f
ms.sourcegitcommit: fb529c4532fbbdfde7ce28e2b4b35f990e8f21d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/30/2021
ms.locfileid: "99088477"
---
# <a name="dax-appropriate-use-of-error-functions"></a>DAX: Hata işlevlerinin uygun kullanımı

Veri modelleyicisi olarak, değerlendirme zamanı hatasını tetiklemenize sebep olabilecek bir DAX ifadesi yazdığınıda şu iki yararlı DAX işlevini kullanabilirsiniz:

- Bir tek ifadeyi alan ve ifade hatayla sonuçlanırsa TRUE değeri döndüren [ISERROR](/dax/iserror-function-dax) işlevi.
- İki ifadeyi alan [IFERROR](/dax/iferror-function-dax) işlevi. İlk ifade hatayla sonuçlanırsa, ikinci ifadeye yönelik değer döndürülür. ISERROR işlevini bir [IF](/dax/if-function-dax) işlevinde iç içe yerleştirmenin iyileştirilmiş bir uygulamasıdır.

Ancak, yararlı olabilen ve kolayca anlaşılabilir ifadelerin yazılmasına katkıda bulunabilen bu ifadeler hesaplamaların performansını önemli ölçüde azaltabilir. Bu durum, bu işlevlerin gereken depolama motoru taraması sayısını artırmasından kaynaklanabilir.

Çoğu değerlendirme zamanı hataları beklenmeyen BLANK değerlerinden, sıfır değerlerinden veya geçersiz veri türü dönüştürmesinden kaynaklanır.

## <a name="recommendations"></a>Öneriler

ISERROR ve IFERROR işlevlerini kullanmaktan kaçınmak daha iyi sonuçlar verir. Bunun yerine, modeli geliştirirken ve ifadeleri yazarken savunmaya yönelik stratejiler uygulayın. Stratejiler şunlar olabilir:

- **Verilere kaliteli modellerin yüklendiğinden emin olma:** Geçersiz veya eksik değerleri kaldırmak ya da değiştirmek ve doğru veri türlerini ayarlamak için Power Query dönüşümlerini kullanın. Geçersiz veri dönüştürme gibi hatalar oluştuğunda bir Power Query dönüşümü de kullanılabilir.

    Veri kalitesi, model sütununun **Null atanabilir** özelliği devre dışı bırakılarak da denetlenebilir. Bu özellik, BLANK değerler ile karşılaşılırsa veri yenilemesinin başarısız olmasına sebep olur. Bu hata oluşursa başarılı bir yenileme işleminin sonucu olarak yüklenen veriler tablolarda kalır.
- **IF işlevini kullanma:** IF işlevi mantıksal test ifadesi bir hata sonucunun oluşup oluşmayacağını belirleyebilir. ISERROR ve IFERROR işlevleri gibi bu işlevin de ek depolama motoru taraması yapılmasına neden olabileceğini, ancak herhangi bir hatanın tetiklenmesi gerekmediği için muhtemelen bunlardan daha iyi bir performans göstereceğini unutmayın.
- **Hataya dayanıklı işlevleri kullanma:** Bazı DAX işlevleri hata koşullarını test edip dengeler. Bu işlevler, bunun yenine döndürülecek olan alternatif bir sonuç girmenize olanak tanır. [DIVIDE](/dax/divide-function-dax) işlevi bunun bir örneğidir. Bu işleve yönelik daha fazla rehberlik için [DAX: DIVIDE işleviyle bölme işlecini (/) karşılaştırma](dax-divide-function-operator.md) makalesini okuyun.

## <a name="example"></a>Örnek

Aşağıdaki ölçüm ifadesi, bir hatanın tetiklenip tetiklenmeyeceğini test eder. Bu örnekte BLANK değerini döndürür. (IF işlevine “yanlış ise değer” ifadesi sağlamadığınızda bu durum oluşur.)

```dax
Profit Margin
= IF(ISERROR([Profit] / [Sales]))
```

IF ve ISERROR işlevlerinin yerine IFERROR işlevi kullanılarak ölçüm ifadesinin sonraki sürümü geliştirildi.

```dax
Profit Margin
= IFERROR([Profit] / [Sales], BLANK())
```

Ancak, ölçü ifadesinin son sürümü, aynı sonuca daha verimli ve zarif bir şekilde ulaşır.

```dax
Profit Margin
= DIVIDE([Profit], [Sales])
```

## <a name="next-steps"></a>Sonraki adımlar

Bu makale hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın:

- [Veri Çözümleme İfadeleri (DAX) Başvurusu](/dax/)

- Öğrenme yolu: [Power BI Desktop’ta DAX kullanma](/learn/paths/dax-power-bi/)
- Sorularınız mı var? [Power BI Topluluğu'na sorun](https://community.powerbi.com/)
- Önerileriniz mi var? [Power BI'ı geliştirmek için fikirlerinizi paylaşın](https://ideas.powerbi.com)