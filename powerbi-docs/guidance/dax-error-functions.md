---
title: 'DAX: Hata işlevlerinin uygun kullanımı'
description: DAX hata işlevlerinin ne zaman kullanılacağına yönelik rehber.
author: peter-myers
manager: asaxton
ms.reviewer: asaxton
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 09/26/2019
ms.author: v-pemyer
ms.openlocfilehash: 0855a9ee4c699c4a3b65e4331b5af2fa68a5610c
ms.sourcegitcommit: 5e277dae93832d10033defb2a9e85ecaa8ffb8ec
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72021080"
---
# <a name="dax-appropriate-use-of-error-functions"></a>DAX: Hata işlevlerinin uygun kullanımı

Bu makale DAX ifadeleri tanımlayan veri modelleyicilerine yöneliktir.

## <a name="background"></a>Arka Plan

Değerlendirme zamanı hatasını tetiklemenize sebep olabilecek bir DAX ifadesi yazarken, şu iki yararlı DAX işlevini kullanabilirsiniz:

- Bir tek ifadeyi alan ve ifade hatayla sonuçlanırsa TRUE değeri döndüren [ISERROR](/dax/iserror-function-dax) işlevi.
- İki ifadeyi alan [IFERROR](/dax/iferror-function-dax) işlevi. İlk ifade hatayla sonuçlanırsa, ikinci ifadeye yönelik değer döndürülür. ISERROR işlevini bir [IF](/dax/if-function-dax) işlevinde iç içe yerleştirmenin iyileştirilmiş bir uygulamasıdır.

Ancak, yararlı olabilen ve kolayca anlaşılabilir ifadelerin yazılmasına katkıda bulunabilen bu ifadeler hesaplamaların performansını önemli ölçüde azaltabilir. Bu durum, bu işlevlerin gereken depolama motoru taraması sayısını artırmasından kaynaklanır.

Çoğu değerlendirme zamanı hatalarının beklenmeyen BLANK değerlerinden, sıfır değerlerinden veya geçersiz veri türü dönüştürmesinden kaynaklandığını unutmayın.

## <a name="recommendations"></a>Öneriler

ISERROR ve IFERROR işlevlerini kullanmaktan kaçınmak daha iyi sonuçlar verir. Bunun yerine, modeli geliştirirken ve ifadeleri yazarken savunmaya yönelik stratejiler uygulayın. Bu stratejilere şunlar örnek verilebilir:

- **Verilere kaliteli modellerin yüklendiğinden emin olma:** Geçersiz veya eksik değerleri kaldırmak ya da değiştirmek ve doğru veri türlerini ayarlamak için Power Query dönüşümlerini kullanın. Geçersiz veri dönüştürme gibi hatalar oluştuğunda bir Power Query dönüşümü de kullanılabilir.

    Veri kalitesi, model sütununun **Null atanabilir** özelliği devre dışı bırakılarak da denetlenebilir. Bu özellik, BLANK değerler ile karşılaşılırsa veri yenilemesinin başarısız olmasına sebep olur. Bu hata oluşursa başarılı bir yenileme işleminin sonucu olarak yüklenen verilerin tablolarda kalacağını unutmayın.
- **IF işlevini kullanma:** Bir hata sonucunun oluşup oluşmayacağını belirlemek için IF işlevi mantıksal test ifadesi kullanılabilir. ISERROR ve IFERROR işlevleri gibi bu işlevin de ek depolama motoru taraması yapılmasına neden olabileceğini, ancak herhangi bir hatanın tetiklenmesi gerekmediği için muhtemelen bunlardan daha iyi bir performans göstereceğini unutmayın.
- **Hataya dayanıklı işlevleri kullanma:** Bazı DAX işlevleri hata koşullarını test edip dengeler. Bu işlevler, bunun yenine döndürülecek olan alternatif bir sonuç girmenize olanak tanır. [DIVIDE](/dax/divide-function-dax) işlevi bunun bir örneğidir. Bu işleve yönelik daha fazla rehberlik için [DAX: DIVIDE işleviyle bölme işlecini (/) karşılaştırma](dax-divide-function-operator.md) makalesini okuyun.

## <a name="example"></a>Örnek

Aşağıdaki ölçüm ifadesi, bir hatanın tetiklenip tetiklenmeyeceğini test eder. Bu örnekte BLANK değerini döndürür. (IF işlevine “yanlış ise değer” ifadesi sağlamadığınızda bu durum oluşur.)
```dax
= IF(ISERROR([Profit] / [Sales]))
```
IF ve ISERROR işlevlerinin yerine IFERROR işlevi kullanılarak ölçüm ifadesinin sonraki sürümü geliştirildi.
```dax
= IFERROR([Profit] / [Sales], BLANK())
```
Ancak, ölçü ifadesinin son sürümü, aynı sonuca daha verimli ve zarif bir şekilde ulaşır.
```dax
= DIVIDE([Profit], [Sales])
```